---
title: 配置观察程序节点测试用户和设置
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：为 Skype for business Server 合成事务配置测试用户帐户和观察程序节点设置。
ms.openlocfilehash: f13680d16a248be339ee7cd4a085d7d0894146dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033671"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>配置观察程序节点测试用户和设置
 
**摘要：** 为 Skype for business Server 合成事务配置测试用户帐户和观察程序节点设置。
  
在配置将充当观察程序节点的计算机之后，您必须：
  
1. 配置这些观察程序节点要使用的[测试用户帐户](test-users-and-settings-2019.md#testuser)。 如果您使用的是 Negotiate 身份验证方法，则必须同时使用 **Set-CsTestUserCredential** cmdlet 来启用这些测试帐户，以在观察程序节点上使用。
    
2. 更新观察程序节点配置设置。
    
## <a name="configure-test-user-accounts"></a>配置测试用户帐户
<a name="testuser"> </a>

测试帐户不需要表示实际人员，但它们必须是有效的 Active Directory 帐户。 此外，必须为 Skype for business Server 启用这些帐户，它们必须具有有效的 SIP 地址，并且应为企业语音启用这些帐户（以使用 CsPstnPeerToPeerCall 综合事务）。 
  
如果使用的是 TrustedServer 身份验证方法，您只需确保这些帐户存在并按说明进行配置即可。 您应为要测试的每个池至少分配三个测试用户。 如果使用的是协商身份验证方法，则还必须使用 CsTestUserCredential cmdlet 和 Skype for Business Server 命令行管理程序，以使这些测试帐户能够使用综合事务。 若要执行此操作，请运行与以下内容类似的命令（这些命令假定已创建三个 Active Directory 用户帐户，并且为 Skype for business Server 启用了这些帐户）：
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

除 SIP 地址之外，还必须包括用户名和密码。 如果不包含密码，CsTestUserCredential cmdlet 将提示您输入该信息。 可以使用前面代码块中所示的域名 \ 用户名格式来指定用户名称。
  
若要验证是否已创建测试用户凭据，请从 Skype for Business Server 命令行管理程序运行以下命令：
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

将为每个用户返回与以下类似的信息：
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用默认综合事务配置基本观察程序节点

在创建测试用户之后，可以使用类似如下的命令创建观察程序节点：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

此命令会创建一个新的观察程序节点，该节点使用默认设置并运行默认的综合事务集。 新的观察程序节点还使用测试用户 watcher1@litwareinc.com、watcher2@litwareinc.com 和 watcher3@litwareinc.com。 如果观察程序节点使用 TrustedServer 身份验证，则这三个测试帐户可以是为 Active Directory 和 Skype for business Server 启用的任何有效的用户帐户。 如果观察程序节点使用协商身份验证方法，则还必须使用 CsTestUserCredential cmdlet 为观察程序节点启用这些用户帐户。
  
若要验证是否已正确配置目标池的自动发现，而不是以某个池为目标，请改为直接使用这些步骤：
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>配置扩展的测试

如果要启用 PSTN 测试（它会验证与公用电话交换网的连接），则需要在设置观察程序节点时执行一些额外的配置。 首先，您必须通过在 Skype for Business Server 命令行管理程序中运行与以下内容类似的命令，将测试用户与 PSTN 测试类型关联起来：
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 此命令的结果必须存储在变量中。 在此示例中，变量被命名为 $pstnTest。 
  
接下来，可以使用**new-cswatchernodeconfiguration** cmdlet 将测试类型（存储在变量 $pstnTest 中）与 Skype For business Server 池相关联。 例如，以下命令为池 atl-cs-001.litwareinc.com 创建新的观察程序节点配置，添加之前创建的三个测试用户，并添加 PSTN 测试类型：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

如果尚未在观察程序节点计算机上安装 Skype for Business Server core 文件和 RTCLocal 数据库，上述命令将失败。 
  
若要测试多个语音策略，您可以使用**CsExtendedTest** cmdlet 为每个策略创建扩展测试。 提供的用户应使用所需的语音策略进行配置。 扩展测试通过使用逗号分隔符传递给**new-cswatchernodeconfiguration** cmdlet，例如：
  
-ExtendedTests @ {Add = $pstnTest 1，$pstnTest 2，$pstnTest 3}
  
由于在未使用测试参数的情况下调用**new-cswatchernodeconfiguration** cmdlet，因此将仅为新的观察程序节点启用默认的合成事务（和指定的扩展的合成事务）。 因此，观察程序节点将测试以下组件：
  
- 注册
    
- IM
    
- GroupIM
    
- P2PAV（对等音频/视频会话）
    
- AvConference（音频/会议）
    
- 状态
    
- ABS（通讯簿服务）
    
- ABWQ（通讯簿 Web 服务）
    
默认情况下，不会测试以下组件：
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity（Exchange 统一消息）
    
- JoinLauncher
    
- MCXP2PIM （旧版移动设备即时消息）
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN （PSTN 网关呼叫，指定为扩展测试）
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>添加和删除综合事务

在配置观察程序节点之后，您可以使用 Set-CsWatcherNodeConfiguration cmdlet 添加或从节点中删除综合事务。 例如，要将 PersistentChatMessage 测试添加到观察程序节点，请使用 Add 方法和与以下类似的命令：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

可以通过使用逗号分隔测试名称来添加多个测试。 例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

如果已在观察程序节点上启用了一个或多个这些测试（例如，DataConference），则会发生错误。 在这种情况下，您将收到与以下类似的错误消息：
  
New-cswatchernodeconfiguration： "urn： schema： TestName" 键或唯一标识约束中存在重复的键序列 "DataConference" （"urn： Watchernode.msi："）。
  
发生此错误时，不会应用任何更改。 应重新运行该命令，并删除重复的测试。
  
若要从观察程序节点中删除综合事务，请使用 Remove 方法。 例如，以下命令会从观察程序节点中删除 ABWQ 测试：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

可以使用 Replace 方法将所有当前启用的测试替换为一个或多个新的测试。 例如，如果您希望观察程序节点仅运行 IM 测试，则可以使用以下命令对其进行配置：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

运行此命令时，除 IM 外，指定的观察程序节点上的所有综合事务都将被禁用。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看和测试观察程序节点配置

如果您想要查看已分配给观察程序节点的测试，请使用与以下类似的命令：
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

此命令将返回与此类似的信息，具体取决于已分配给该节点的综合事务：
  
注册 IM GroupIM P2PAV AvConference 状态 PersistentChatMessage DataConference
> [!TIP]
> 要按字母顺序查看综合事务，请改为使用以下命令： 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

若要验证是否已创建观察程序节点，请在 Skype for Business Server 命令行管理程序中键入以下命令：
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

将返回类似于以下内容的信息：
  
Identity： atl-cs-001.litwareinc.com TestUsers： {sip:watcher1@litwareinc.com，sip:watcher2@litwareinc.com ...} ExtendedTests： {TestUsers = IList<System.string>;Name = PSTN 测试;Te ...} TargetFqdn： atl-cs-001.litwareinc.com PortNumber：5061To 验证是否已正确配置观察程序节点，请在 Skype for Business Server Management Shell 中键入以下命令：
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

此命令将测试部署中的每个观察程序节点，并确认是否已完成以下操作：
  
- 安装了所需的注册者角色
    
- 将创建所需的注册表项（在运行 New-cswatchernodeconfiguration cmdlet 时完成）
    
- 你的服务器运行的是 Skype for Business Server 的正确版本
    
- 端口配置正确
    
- 您分配的测试用户具有所需的凭据
    
## <a name="managing-watcher-nodes"></a>管理观察程序节点
<a name="testuser"> </a>

除了修改在观察程序节点上执行的合成事务之外，您还可以使用**new-cswatchernodeconfiguration** cmdlet 执行两个其他重要任务：启用和禁用观察程序节点，以及将观察程序节点配置为在运行其测试时使用内部 web url 或外部 web url。
  
默认情况下，观察程序节点旨在定期运行其所有启用的综合事务。 但是，有时您可能希望挂起这些事务。 例如，如果观察程序节点临时断开了网络连接，则没有必要运行综合事务。 如果没有网络连接，这些事务将会失败。 若要暂时禁用观察程序节点，请从 Skype for Business Server 命令行管理程序运行与以下内容类似的命令：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

此命令将禁用在观察程序节点 atl 观察程序001.litwareinc.com 上执行综合事务。 若要恢复综合事务的执行，请将 Enabled 属性设置回 True ($True)：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled 属性可用于启用或禁用观察程序节点。 如果要永久删除观察程序节点，请使用 **Remove-CsWatcherNodeConfiguration** cmdlet：
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

该命令将从指定的计算机中删除所有观察程序节点配置设置，这将阻止计算机自动运行综合事务。 但是，该命令不会卸载 System Center agent 文件或 Skype for Business Server 系统文件。
  
默认情况下，观察程序节点在实施测试时使用组织的外部 Web Url。 但是，观察程序节点也可以配置为使用组织的内部 Web Url。 这使管理员可验证位于外围网络内的用户的 URL 访问权限。 若要将观察程序节点配置为使用内部 Url 而不是外部 Url，请将 UseInternalWebURls 属性设置为 True （$True）：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

将此属性重置为默认值 False （$False）将导致观察程序再次使用外部 Url：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>综合事务的特殊设置说明
<a name="special_synthetictrans"> </a>

大多数综合事务可以按方式在观察程序节点上运行。 在大多数情况下，一旦将综合事务添加到观察程序节点配置设置，观察程序节点就可以开始在其测试传递过程中使用该合成事务。 但是，有些合成事务需要特殊的安装说明，如以下各节所述。
  
### <a name="data-conferencing-synthetic-transaction"></a>数据会议综合事务

如果您的观察程序节点计算机位于您的外围网络之外，则您可能无法运行数据会议综合事务，除非您先禁用 Windows Internet Explorer®网络的 Internet 浏览器代理设置服务帐户，方法是完成以下步骤：
  
1. 在观察程序节点计算机上，单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。
    
2. 在控制台窗口中，键入以下命令，然后按 ENTER 键。 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

您将在命令窗口中看到以下消息：
  
BITSAdmin 已弃用，并不保证在将来的 Windows 版本中可用。 BITS 服务的管理工具现在由 BITS PowerShell cmdlet 提供。
  
帐户 NetworkService 的 Internet 代理设置设置为 NO_PROXY。 
  
（connection = default）
  
此消息表明您已禁用网络服务帐户的 Internet Explorer 代理设置。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 统一消息综合事务

Exchange 统一消息（UM）综合事务验证测试用户是否可以连接到 Exchange 中托管的语音邮件帐户。
  
将需要使用语音邮件帐户对测试用户进行预配置。 
  
### <a name="persistent-chat-synthetic-transaction"></a>持久聊天综合事务

若要使用持久聊天综合事务，必须先创建一个通道，并向测试用户授予使用该功能的权限。
  
您可以使用持久聊天综合事务来配置此通道： 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

必须运行此安装任务，才能从企业内部运行：
  
- 如果从非服务器计算机运行，则执行 cmdlet 的用户必须是基于角色的访问控制（RBAC）的 CsPersistentChatAdministrators 角色的成员。
    
- 如果从服务器本身运行，则执行 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 对等呼叫综合事务

CsPstnPeerToPeerCall 综合事务验证通过公用电话交换网（PSTN）拨打和接听呼叫的能力。
  
若要运行此综合事务，您必须进行以下配置：
  
- 启用了 UC 的两个测试用户（一个呼叫者和一个接收器）。
    
- 为每个用户帐户配置外线直拨分机 (DID) 号码。
    
- 允许呼叫接收器的号码以到达 PSTN 网关的 VoIP 策略和语音路由。
    
- 一种 PSTN 网关，该网关接受根据拨打的号码将呼叫路由回接收器主池的呼叫和媒体。
    
### <a name="unified-contact-store-synthetic-transaction"></a>统一联系人存储综合事务

统一联系人存储综合事务可验证 Skype for Business Server 代表用户从 Exchange 检索联系人的能力。
  
若要使用此综合事务，必须满足以下条件：
  
- Lyss-必须配置 Exchange server 到服务器身份验证。
    
- 测试用户必须具有有效的 Exchange 邮箱。
    
满足这些条件后，可以运行以下 Windows PowerShell cmdlet 将测试用户的联系人列表迁移到 Exchange：
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

测试用户联系人列表可能需要一段时间才能迁移到 Exchange。 若要监视迁移进度，可以在没有-Setup 标志的情况下运行相同的命令行：
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

迁移完成后，此命令行将会成功。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 综合事务

可扩展消息传递和状态协议（XMPP） IM 合成事务要求您为 XMPP 功能配置一个或多个联盟域。
  
若要启用 XMPP 综合事务，必须在可路由的 XMPP 域中提供具有用户帐户的 XmppTestReceiverMailAddress 参数。 例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

在此示例中，需要有一个 Skype for Business 服务器规则，以将 litwareinc.com 的邮件路由到 XMPP 网关。

> [!NOTE]
> XMPP 网关和代理在 Skype for business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 有关详细信息，请参阅[迁移 XMPP 联合](../migration/migrating-xmpp-federation.md)。
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>视频互操作服务器（VIS）综合事务

视频互操作服务器（VIS）综合事务要求您下载并安装综合事务支持文件（[VISSTSupportPackage](https://www.microsoft.com/download/details.aspx?id=46921)）。 
  
若要安装 VISSTSupportPackage，请确保已安装 msi 的依赖项（在 "系统要求" 下）。 运行 VISSTSupportPackage 以执行简单安装。 .Msi 安装以下路径中的所有文件： "%ProgramFiles%\VIS 综合事务支持包"。
  
有关如何运行 VIS 综合事务的更多详细信息，请参阅[CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet 的文档。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>更改综合事务的运行频率
<a name="special_synthetictrans"> </a>

默认情况下，综合事务将每15分钟运行一次配置的用户。 综合事务在一组用户中按顺序运行，以避免两个合成事务相互冲突。 需要更长的时间间隔，以提供所有综合事务的完成时间。
  
如果需要更频繁地运行综合事务，应减少使用一组给定用户运行的合成事务的数量，以便可以在所需的时间范围内完成这些测试，以避免偶尔出现的网络延迟。 如果需要运行更多的合成事务，请创建更多的用户集来运行其他综合事务。
  
若要更改运行综合事务的频率，请按照下列步骤操作：
  
1. 打开 System Center Operations Manager。 单击 "创作部分"。 单击 "规则" 部分（在 "创作" 下）
    
2. 在 "规则" 部分中，查找名称为 "主合成事务运行程序性能收集规则" 的规则
    
3. 右键单击该规则，然后选择 "覆盖"，选择 "覆盖规则"，然后选择 "对类的所有对象：池监视程序"
    
4. 在 "替代属性" 窗口中，选择 "参数名称" "Frequency"，并将替代值设置为所需的值。
    
5. 在同一窗口中，选择需要应用此替代的管理包
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>使用综合事务的富日志记录
<a name="special_synthetictrans"> </a>

综合事务证明在帮助确定系统问题方面极其有用。 例如，CsRegistration cmdlet 可能会提醒管理员，这实际上是用户在使用 Skype for business 服务器注册时遇到困难。 但是，可能需要更多详细信息来确定失败的实际原因。
  
因此，综合事务提供了丰富的日志记录。 对于综合事务 undertakes 的每个活动，使用丰富的日志记录，记录以下信息：
  
- 活动启动的时间。
    
- 活动完成的时间。
    
- 执行的操作（例如，创建、加入或离开会议; 登录到 Skype for business 服务器; 发送即时消息）。
    
- 在活动运行时生成的参考消息、详细消息、警告消息或错误消息
    
- SIP 注册邮件。
    
- 在活动运行时生成的异常记录或诊断代码。
    
- 运行活动的最终结果。
    
每次运行一个综合事务时，都会自动生成此信息，但不会自动将其显示或保存到日志文件中。 如果手动运行的是综合事务，则可以使用 OutLoggerVariable 参数指定将在其中存储信息的 Windows PowerShell 变量。 在这里，可以选择使用两种方法之一以 XML 或 HTML 格式在富日志中保存和/或查看错误消息。 
  
若要检索故障排除信息，请指定 OutLoggerVariable 参数，后跟您选择的变量名称：
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> ：请勿在变量名称前面加上 $ 字符。 使用变量名，如 RegistrationTest （不 $RegistrationTest）。 
  
运行此命令时，将看到类似如下的输出：
  
目标 Fqdn： atl-cs-001.litwareinc.com 结果：故障延迟：00:00:00 错误消息：此计算机没有任何已分配的证书。 诊断：您可以访问有关此故障的更多详细信息，而不只是此处显示的错误消息。 若要以 HTML 格式访问此信息，请使用与此类似的命令将变量 RegistrationTest 中存储的信息保存到 HTML 文件中：
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

您也可以使用 ToXML() 方法将数据保存到 XML 文件：
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

您可以使用 Windows Internet Explorer、Microsoft Visual Studio 或任何其他能够打开 HTML/XML 文件的应用程序来查看这些文件。
  
从 System Center Operations Manager 内部运行的综合事务将自动为故障生成这些日志文件。 如果在 Skype for business Server PowerShell 能够加载和运行综合事务之前执行失败，则不会生成这些日志。 
  
> [!IMPORTANT]
> 默认情况下，Skype for Business Server 将日志文件保存到未共享的文件夹中。 若要方便地访问这些日志，应共享此文件夹。 例如： \\atl-观察程序-litwareinc. com\WatcherNode。 
