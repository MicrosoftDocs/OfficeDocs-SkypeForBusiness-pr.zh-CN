---
title: 配置观察程序节点测试用户和设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 摘要：为 Skype for business Server 合成事务配置测试用户帐户和观察程序节点设置。
ms.openlocfilehash: 877e7256c31bf5bf66f25e80c9625078cfc15b02
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888851"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>配置观察程序节点测试用户和设置
 
**摘要：** 为 Skype for business Server 合成事务配置测试用户帐户和观察程序节点设置。
  
在配置将用作观察者节点的计算机后，必须：
  
1. 配置要由这些观察程序节点使用的[测试用户帐户](test-users-and-settings.md#testuser)。 如果你使用协商身份验证方法，你还必须使用**CsTestUserCredential** cmdlet 来启用这些测试帐户，以便在 "观察程序" 节点上使用。
    
2. 更新观察程序节点配置设置。
    
## <a name="configure-test-user-accounts"></a>配置测试用户帐户
<a name="testuser"> </a>

测试帐户不需要表示实际人员，但它们必须是有效的 Active Directory 帐户。 此外，必须为 Skype for Business Server 启用这些帐户，它们必须具有有效的 SIP 地址，并且应该为企业语音启用（以使用 CsPstnPeerToPeerCall 合成事务）。 
  
如果你使用的是 TrustedServer 身份验证方法，你需要做的就是确保这些帐户存在并按说明进行配置。 你应该为要测试的每个池至少分配两个测试用户。 如果你使用的是协商身份验证方法，你还必须使用 CsTestUserCredential cmdlet 和 Skype for Business Server Management Shell 来启用这些测试帐户以处理合成事务。 通过运行类似于以下内容的命令来执行此操作（这些命令假设已创建两个 Active Directory 用户帐户，并且为 Skype for Business Server 启用了这些帐户）：
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

你不仅必须包括 SIP 地址，还必须包括用户名和密码。 如果不包含密码，CsTestUserCredential cmdlet 将提示你输入该信息。 可以使用上述代码块中所示的域名 \ 用户名格式指定用户名。
  
若要验证是否已创建测试用户凭据，请从 Skype for Business Server 命令行管理程序运行以下命令：
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

将为每个用户返回类似于以下内容的信息：
  
|**用户名**|**口令**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用默认合成事务配置基本观察程序节点

创建测试用户后，您可以使用类似下面的命令创建观察程序节点：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

此命令将创建一个新的监视程序节点，该节点使用默认设置并运行一组默认的合成事务。 新的观察程序节点还使用 test users watcher1@litwareinc.com 和 watcher2@litwareinc.com。 如果观察程序节点使用 TrustedServer 身份验证，则两个测试帐户可以是为 Active Directory 和 Skype for business 服务器启用的任何有效用户帐户。 如果观察程序节点使用协商身份验证方法，则还必须通过使用 CsTestUserCredential cmdlet 为观察程序节点启用这些用户帐户。
  
若要验证是否正确配置了目标池的自动发现，而不是定向到池，请改用以下步骤：
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>配置扩展测试

如果你想要启用 PSTN 测试，从而验证与公共交换电话网络的连接，你需要在设置观察程序节点时执行其他一些配置。 首先，您必须将测试用户与 PSTN 测试类型关联，方法是从 Skype for Business Server 命令行管理程序中运行如下命令：
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 此命令的结果必须存储在变量中。 在此示例中，变量被命名为 "$pstnTest"。 
  
接下来，你可以使用**CsWatcherNodeConfiguration** cmdlet 将测试类型（存储在变量 $pstnTest 中）关联到 Skype For business 服务器池。 例如，以下命令为池 atl-cs-001.litwareinc.com 创建新的观察程序节点配置、添加之前创建的两个测试用户以及添加 PSTN 测试类型：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

如果尚未在观察程序节点计算机上安装 Skype for business Server core 文件和 RTCLocal 数据库，上述命令将失败。 
  
若要测试多个语音策略，可以使用**CsExtendedTest** cmdlet 为每个策略创建扩展测试。 所提供的用户应配置所需的语音策略。 扩展测试通过使用逗号分隔符传递到**CsWatcherNodeConfiguration** cmdlet，例如：
  
-ExtendedTests @ {Add = $pstnTest 1，$pstnTest 2，$pstnTest 3}
  
由于在未使用 "测试" 参数的情况下调用了**CsWatcherNodeConfiguration** cmdlet，因此将仅为新的观察程序节点启用默认合成事务（和指定的扩展合成事务）。 因此，观察程序节点将测试以下组件：
  
- 注册
    
- 即时消息
    
- GroupIM
    
- P2PAV （对等音频/视频会话）
    
- AvConference （音频/会议）
    
- 状态
    
- ABS （通讯簿服务）
    
- ABWQ （通讯簿 web 服务）
    
默认情况下，不会测试以下组件：
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity （Exchange 统一消息）
    
- JoinLauncher
    
- MCXP2PIM （旧版移动设备即时消息）
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN （PSTN 网关呼叫，指定为扩展测试）
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>添加和删除综合事务

配置了观察程序节点后，你可以使用 CsWatcherNodeConfiguration cmdlet 在节点中添加或删除合成事务。 例如，若要向观察程序节点添加 PersistentChatMessage 测试，请使用 Add 方法和类似如下的命令：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

可通过使用逗号分隔测试名称来添加多个测试。 例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

如果这些测试中的一个或多个（例如，DataConference）已在观察程序节点上启用，将发生错误。 在这种情况下，你将收到类似于以下内容的错误消息：
  
Set-CsWatcherNodeConfiguration： "urn： schema： WatcherNode： TestName ' key 或 unique identity 约束有一个重复的键序列" DataConference "。
  
发生此错误时，将不会应用任何更改。 应在删除重复的测试后重新运行该命令。
  
若要从观察程序节点中删除合成事务，请使用 Remove 方法。 例如，此命令将从观察程序节点中删除 ABWQ 测试：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

可以使用 Replace 方法将当前启用的所有测试替换为一个或多个新测试。 例如，如果你希望观察程序节点仅运行 IM 测试，则可以通过使用以下命令来配置它：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

运行此命令时，除 IM 外，指定的观察程序节点上的所有合成事务都将被禁用。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看和测试观察程序节点配置

如果要查看已分配给观察程序节点的测试，请使用类似下面的命令：
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

此命令将根据分配给节点的合成事务返回类似于此的信息：
  
注册 IM GroupIM P2PAV AvConference 状态 PersistentChatMessage DataConference
> [!TIP]
> 若要按字母顺序查看合成事务，请改用以下命令： 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

若要验证是否已创建观察程序节点，请在 Skype for Business Server Management Shell 中键入以下命令：
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

您将获得类似以下内容的信息：
  
标识： atl-cs-001.litwareinc.com <br/>
TestUsers： {sip:watcher1@litwareinc.com，sip:watcher2@litwareinc.com ...}<br/>
ExtendedTests： {TestUsers = IList<String>;Name = PSTN 测试;Te ...}<br/>
TargetFqdn： atl-cs-001.litwareinc.com<br/>
PortNumber：5061<br/>

若要验证是否正确配置了观察程序节点，请在 Skype for Business Server Management Shell 中键入以下命令：
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

此命令将在你的部署中测试每个观察程序节点并确认是否已完成以下操作：
  
- 已安装所需的注册机构角色。
    
- 将创建所需的注册表项（在运行 CsWatcherNodeConfiguration cmdlet 时已完成）。
    
- 您的服务器运行的是正确版本的 Skype for Business 服务器。
    
- 您的端口配置正确。
    
- 您分配的测试用户具有所需的凭据。
    
## <a name="managing-watcher-nodes"></a>管理观察程序节点
<a name="testuser"> </a>

除了修改在观察程序节点上执行的合成事务，还可以使用**CsWatcherNodeConfiguration** cmdlet 执行两个其他重要任务：启用和禁用 "观察程序" 节点，以及将观察程序节点配置为在运行其测试时使用内部 web url 或外部 web url。
  
默认情况下，观察程序节点设计为定期运行其所有启用的合成事务。 但是，有时您可能希望暂停这些交易。 例如，如果观察程序节点暂时与网络断开连接，则没有理由运行合成事务。 如果没有网络连接，这些事务将失败。 若要暂时禁用观察程序节点，请从 Skype for Business 服务器管理外壳程序运行类似下面的命令：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

此命令将禁用观察程序节点 atl 观察程序001.litwareinc.com 上的合成事务的执行。 若要恢复合成事务的执行，请将 Enabled 属性设置回 True （$True）：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled 属性可用于打开或关闭观察程序节点。 如果要永久删除观察程序节点，请使用**CsWatcherNodeConfiguration** cmdlet：
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

该命令将从指定的计算机中删除所有观察程序节点配置设置，这将阻止计算机自动运行合成事务。 但是，该命令不会卸载 System Center agent 文件或 Skype for business Server 系统文件。
  
默认情况下，在执行测试时，观察程序节点使用组织的外部 Web Url。 但是，观察程序节点也可以配置为使用组织的内部 Web Url。 这使管理员能够验证位于外围网络内的用户的 URL 访问。 若要将观察程序节点配置为使用内部 Url 而不是外部 Url，请将 UseInternalWebURls 属性设置为 True （$True）：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

将此属性重置为默认值 False （$False）将导致观察程序再次使用外部 Url：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>综合交易的特殊设置说明
<a name="special_synthetictrans"> </a>

大多数合成事务可以按原样在观察程序节点上运行。 在大多数情况下，一旦将合成事务添加到观察程序节点配置设置，观察程序节点就可以在其测试传递期间开始使用该合成事务。 但是，存在一些需要特殊设置说明的合成事务，如下部分所述。
  
### <a name="data-conferencing-synthetic-transaction"></a>数据会议综合事务

如果你的观察程序节点计算机位于你的外围网络之外，则你可能无法运行数据会议合成事务，除非你首先禁用 Windows Internet Explorer®网络的 Internet 浏览器代理设置服务帐户，方法是完成以下步骤：
  
1. 在观察程序节点计算机上，单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。
    
2. 在控制台窗口中，键入以下命令，然后按 ENTER。 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    您将在 "命令" 窗口中看到以下消息：

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    此消息表示你已禁用网络服务帐户的 Internet Explorer 代理设置。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 统一消息综合事务

Exchange 统一消息（UM）合成事务验证测试用户是否可以连接到位于 Exchange 中的语音邮件帐户。
  
测试用户将需要通过语音邮件帐户进行预配置。 
  
### <a name="persistent-chat-synthetic-transaction"></a>持久聊天合成事务

若要使用持久聊天合成事务，必须首先创建一个通道，并向测试用户提供使用它的权限。
  
你可以使用持久聊天合成事务来配置此通道： 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

必须运行此设置任务才能从企业内部运行：
  
- 如果从非服务器计算机运行，则执行 cmdlet 的用户必须是基于角色的访问控制（RBAC）的 CsPersistentChatAdministrators 角色的成员。
    
- 如果从服务器本身运行，则执行 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 对等呼叫综合事务

CsPstnPeerToPeerCall 合成事务可验证通过公共交换电话网络（PSTN）拨打和接听呼叫的能力。
  
若要运行此合成事务，必须配置：
  
- 两个启用 UC 的测试用户（呼叫方和接收方）。
    
- 为每个用户帐户直接拨入（已有）号码。
    
- 允许呼叫接收器网关的 VoIP 策略和语音路由。
    
- 可接受呼叫和媒体的 PSTN 网关，它根据所拨打的号码将呼叫路由回接收器的主池。
    
### <a name="unified-contact-store-synthetic-transaction"></a>统一联系人存储综合事务

"统一联系人存储" 综合事务可验证 Skype for Business 服务器从 Exchange 代表用户检索联系人的能力。
  
若要使用此合成事务，必须满足以下条件：
  
- Lyss-必须配置 Exchange server 到服务器身份验证。
    
- 测试用户必须具有有效的 Exchange 邮箱。
    
满足这些条件后，你可以运行以下 Windows PowerShell cmdlet 将测试用户的联系人列表迁移到 Exchange：
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

将测试用户联系人列表迁移到 Exchange 可能需要一些时间。 若要监视迁移进度，可以在没有-Setup 标志的情况下运行相同的命令行：
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

完成迁移后，此命令行将成功。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 合成事务

可扩展消息和状态协议（XMPP） IM 合成事务要求你将 XMPP 功能配置为一个或多个联合域。
  
若要启用 XMPP 合成事务，必须在可路由的 XMPP 域中提供具有用户帐户的 XmppTestReceiverMailAddress 参数。 例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

在此示例中，需要有 Skype for Business 服务器规则才能将 litwareinc.com 的邮件路由到 XMPP 网关。

> [!NOTE]
> XMPP 网关和代理在 Skype for business Server 2015 中可用，但 Skype for business Server 2019 不再支持。 有关详细信息，请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>视频互操作服务器（VIS）合成事务

视频互操作服务器（VIS）合成事务需要你下载并安装合成事务支持文件（[VISSTSupportPackage](https://www.microsoft.com/en-us/download/details.aspx?id=46921)）。 
  
若要安装 VISSTSupportPackage，请确保已安装 msi 的依赖关系（在 "系统要求" 下）。 运行 VISSTSupportPackage 以执行简单安装。 .Msi 将在以下路径中安装所有文件： "%ProgramFiles%\VIS 合成事务支持程序包"。
  
有关如何运行 VIS 合成事务的更多详细信息，请参阅[CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet 的文档。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>更改综合事务的运行频率
<a name="special_synthetictrans"> </a>

默认情况下，综合事务将每15分钟与配置的用户一起运行。 在一组用户中按顺序运行合成事务，以避免两个合成事务相互冲突。 需要较长的时间间隔才能完成所有合成事务的完成。
  
如果需要更频繁地运行合成事务，则应减少使用一组给定用户运行的合成事务的数量，以便可以在所需的时间范围内完成测试，以便在偶尔的网络延迟中使用某些缓冲区。 如果需要运行更多合成事务，请创建更多用户集以运行其他合成事务。
  
若要更改运行合成事务的频率，请按照下列步骤操作：
  
1. 打开 System Center Operations Manager。 单击 "创作分区"。 单击 "规则" 部分（在 "创作" 下）。
    
2. 在 "规则" 部分中，找到名称为 "主合成事务运行程序性能收集规则" 的规则。
    
3. 右键单击该规则，然后选择 "替代"，选择 "替代规则"，然后选择 "对于类：池监视程序的所有对象"。
    
4. 在 "替代属性" 窗口中，选择 "参数名称" "Frequency"，然后将替代值设置为所需值。
    
5. 在同一窗口中，选择需要应用此覆盖的管理包。
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>对综合事务使用丰富日志记录
<a name="special_synthetictrans"> </a>

综合事务证明在帮助识别系统问题方面极其有用。 例如，CsRegistration cmdlet 可以向管理员发出警告，指出用户在向 Skype for Business 服务器注册时遇到困难。 但是，可能需要其他详细信息来确定失败的实际原因。
  
出于此原因，综合事务提供了丰富的日志记录。 对于综合事务仅负责的每个活动，有丰富的日志记录，记录以下信息：
  
- 活动开始的时间。
    
- 活动完成的时间。
    
- 执行的操作（例如，创建、加入或离开会议; 登录到 Skype for Business 服务器; 发送即时消息）。
    
- 在活动运行时生成的信息、详细、警告或错误消息。
    
- SIP 注册消息。
    
- 在活动运行时生成的异常记录或诊断代码。
    
- 运行活动的最终结果。
    
此信息会在每次运行合成事务时自动生成，但不会自动显示或保存到日志文件。 如果你手动运行合成事务，则可以使用 OutLoggerVariable 参数指定将在其中存储信息的 Windows PowerShell 变量。 从这里，你可以选择使用两种方法之一以 XML 或 HTML 格式在富短日志中保存和/或查看错误消息。 
  
若要检索疑难解答信息，请指定 OutLoggerVariable 参数，后跟你选择的变量名称：
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> 不要在变量名前面加 $ 字符。 使用变量名称，例如 RegistrationTest （not $RegistrationTest）。 
  
运行此命令时，将看到类似以下内容的输出：
  
目标 Fqdn： atl-cs-001.litwareinc.com 结果：故障延迟：00:00:00 错误消息：此计算机没有任何已分配的证书。 诊断：你可以访问与此处所示错误消息更详细的此失败信息。

若要以 HTML 格式访问此信息，请使用与此类似的命令将变量 RegistrationTest 中存储的信息保存到 HTML 文件中：
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

或者，你可以使用 ToXML （）方法将数据保存到 XML 文件：
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

你可以使用 Windows Internet Explorer、Microsoft Visual Studio 或任何能够打开 HTML/XML 文件的其他应用程序查看这些文件。
  
从 System Center Operations Manager 内部运行的合成事务将自动为故障生成这些日志文件。 如果在 Skype for business Server PowerShell 能够加载和运行合成事务之前执行失败，则不会生成这些日志。 
  
> [!IMPORTANT]
> 默认情况下，Skype for business 服务器将日志文件保存到未共享的文件夹中。 为使这些日志易于访问，您应该共享此文件夹。 例如： \\atl-观察程序-001. litwareinc com\WatcherNode。 
