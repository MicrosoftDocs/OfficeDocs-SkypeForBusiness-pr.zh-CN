---
title: 如何配置观察程序节点测试用户和设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 如何为综合事务配置测试用户帐户和观察程序Skype for Business Server设置。
ms.openlocfilehash: 7e7c318f6e9176c46a7dbbab6c8d1833f74911e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599937"
---
# <a name="how-to-configure-watcher-node-test-users-and-settings"></a>如何配置观察程序节点测试用户和设置
 
**摘要：** 为综合事务配置测试用户帐户和观察Skype for Business Server设置。
  
在配置将充当观察程序节点的计算机之后，您必须：
  
1. [配置要由这些](test-users-and-settings.md#testuser) 观察程序节点使用的测试用户帐户。 如果您使用的是 Negotiate 身份验证方法，则必须同时使用 **Set-CsTestUserCredential** cmdlet 来启用这些测试帐户，以在观察程序节点上使用。
    
2. 更新观察程序节点配置设置。
    
## <a name="configure-test-user-accounts"></a>配置测试用户帐户
<a name="testuser"> </a>

测试帐户不需要表示实际人员，但它们必须是有效的 Active Directory 帐户。 此外，必须为这些帐户启用Skype for Business Server，它们必须具有有效的 SIP 地址，并且应启用这些帐户企业语音 (以使用 Test-CsPstnPeerToPeerCall 事务) 。 
  
如果使用 TrustedServer 身份验证方法，只需确保这些帐户存在并按说明进行配置。 为每个要测试的池分配至少两个测试用户。 如果使用 Negotiate 身份验证方法，还必须使用 Set-CsTestUserCredential cmdlet 和 Skype for Business Server 命令行管理程序使这些测试帐户能够处理综合事务。 为此，运行与以下命令类似的命令 (这些命令假定已创建两个 Active Directory 用户帐户，并且这些帐户已启用Skype for Business Server) ：
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

您不仅必须包括 SIP 地址，还必须包括用户名和密码。 如果您不包括密码，则 Set-CsTestUserCredential cmdlet 将提示您输入该信息。 可以使用前面代码块中显示的域名\用户名格式来指定用户名。
  
若要验证是否创建了测试用户凭据，请从命令行管理程序Skype for Business Server以下命令：
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

将为每个用户返回与以下内容类似的信息：
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用默认综合事务配置基本观察程序节点

创建测试用户后，可以使用与以下命令类似的命令创建观察程序节点：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

此命令会创建一个新的观察程序节点，该节点使用默认设置并运行默认的综合事务集。 新的观察程序节点还使用测试 watcher1@litwareinc.com，watcher2@litwareinc.com。 如果观察程序节点使用 TrustedServer 身份验证，则两个测试帐户可以是任何为 Active Directory 启用的有效用户帐户，Skype for Business Server。 如果观察程序节点使用 Negotiate 身份验证方法，则还必须使用 Set-CsTestUserCredential cmdlet 为观察程序节点启用这些用户帐户。
  
若要验证是否正确配置了目标池的自动发现以登录，而不是直接将目标池作为目标，请改为使用以下步骤：
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>配置扩展的测试

如果要启用 PSTN 测试（用于验证与公用电话交换网的连接），则需要在设置观察程序节点时执行一些额外的配置。 首先，必须通过从命令行管理程序运行类似Skype for Business Server PSTN 测试类型：
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 此命令的结果必须存储在变量中。 本示例将变量命名为 $pstnTest。 
  
接下来，您可以使用 **New-CsWatcherNodeConfiguration** cmdlet 将变量 (中存储的测试类型 $pstnTest) 关联到Skype for Business Server池。 例如，以下命令为池池创建新的观察程序节点 atl-cs-001.litwareinc.com，添加之前创建的两个测试用户，并添加 PSTN 测试类型：
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

如果您尚未在观察程序节点计算机上安装 Skype for Business Server核心文件和 RTCLocal 数据库，则上述命令将失败。 
  
若要测试多个语音策略，可以使用 **New-CsExtendedTest** cmdlet 为每个策略创建一个扩展测试。 所提供的用户应配置所需的语音策略。 扩展测试通过使用逗号分隔符传递到 **New-CsWatcherNodeConfiguration** cmdlet，例如：
  
-ExtendedTests @{Add=$pstnTest 1，$pstnTest 2，$pstnTest 3}
  
由于 **调用 New-CsWatcherNodeConfiguration** cmdlet 时没有使用 Tests 参数，因此只会为新的观察程序节点启用默认综合事务 (和指定的扩展综合事务) 。 因此，观察程序节点将测试以下组件：
  
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
    
- MCXP2PIM (旧版移动设备即时消息) 
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN 网关呼叫，指定为扩展测试) 
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>添加和删除综合事务

在配置观察程序节点之后，您可以使用 Set-CsWatcherNodeConfiguration cmdlet 添加或从节点中删除综合事务。例如，要将 PersistentChatMessage 测试添加到观察程序节点，请使用 Add 方法和与以下类似的命令：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

可以通过使用逗号分隔测试名称来添加多个测试。例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

如果其中一个或多个测试已启动， (例如，已在观察程序节点上启用 dataConference) ，将发生错误。 在这种情况下，您将收到与以下类似的错误消息：
  
Set-CsWatcherNodeConfiguration："urn：schema：Microsoft.Rtc.Management"存在重复键序列"DataConference"。设置。WatcherNode.2010：TestName 的键或唯一标识约束。
  
发生此错误时，不会应用任何更改。 该命令应在删除重复测试后重新运行。
  
若要从观察程序节点中删除综合事务，请使用 Remove 方法。 例如，以下命令会从观察程序节点中删除 ABWQ 测试：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

可以使用 Replace 方法将当前启用的所有测试替换为一个或多个新测试。 例如，如果希望观察程序节点仅运行 IM 测试，可以使用此命令进行配置：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

运行此命令时，将禁用指定观察程序节点上的所有综合事务（IM 除外）。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看和测试观察程序节点配置

如果您想要查看已分配给观察程序节点的测试，请使用与以下类似的命令：
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

此命令将返回类似此信息，具体取决于已分配给节点的综合事务：
  
注册 IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> 要按字母顺序查看综合事务，请改为使用以下命令： 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

若要验证是否创建了观察程序节点，请从命令行管理程序Skype for Business Server命令：
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

您将获得与以下类似的信息：
  
标识 ：atl-cs-001.litwareinc.com <br/>
TestUsers ： {sip:watcher1@litwareinc.com， sip:watcher2@litwareinc.com ...}<br/>
ExtendedTests ： {TestUsers=IList<System.String>;Name=PSTN Test;Te...}<br/>
TargetFqdn ： atl-cs-001.litwareinc.com<br/>
PortNumber ： 5061<br/>

若要验证观察程序节点是否配置正确，请从命令行管理程序Skype for Business Server命令：
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

此命令将测试部署中的每个观察程序节点并确认是否已完成以下操作：
  
- 已安装所需的注册器角色。
    
- 在运行 cmdlet cmdlet (时，将创建所需的Set-CsWatcherNodeConfiguration注册表) 。
    
- 您的服务器运行的是正确版本的 Skype for Business Server。
    
- 您的端口配置正确。
    
- 所分配的测试用户是否具有所需的凭据。
    
## <a name="managing-watcher-nodes"></a>管理观察程序节点
<a name="testuser"> </a>

除了修改在观察程序节点上执行的综合事务之外，您还可以使用 **Set-CsWatcherNodeConfiguration** cmdlet 执行另外两项重要任务：启用和禁用观察程序节点，以及将观察程序节点配置为在运行其测试时使用内部 Web URL 或外部 Web URL。
  
默认情况下，观察程序节点旨在定期运行其所有启用的综合事务。 但是，有时您可能需要暂停这些事务。 例如，如果观察程序节点临时断开了网络连接，则没有必要运行综合事务。 如果没有网络连接，这些事务将失败。 若要临时禁用观察程序节点，请从命令行管理程序运行Skype for Business Server命令：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

此命令将禁止在观察程序节点 atl 观察程序上执行综合 001.litwareinc.com。 若要恢复综合事务的执行，请将 Enabled 属性设置回 True ($True)：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled 属性可用于启用或禁用观察程序节点。如果要永久删除观察程序节点，请使用 **Remove-CsWatcherNodeConfiguration** cmdlet：
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

该命令将删除指定计算机的所有观察程序节点配置设置，从而阻止该计算机自动运行综合事务。 但是，该命令不会卸载System Center代理文件或Skype for Business Server文件。
  
默认情况下，观察程序节点在进行测试时使用组织的外部 Web URL。 但是，还可以将观察程序节点配置为使用组织的内部 Web URL。 这使管理员可验证位于外围网络内的用户的 URL 访问权限。 若要将观察程序节点配置为使用内部 URL 而不是外部 URL，请设置 UseInternalWebURls 属性为 True ($True) ：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

将此属性重置为默认值 False ($False) 将导致观察程序再次使用外部 URL：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>综合事务的特殊设置说明
<a name="special_synthetictrans"> </a>

大多数综合事务可以像现在一样在观察程序节点上运行。 在大多数情况下，一旦将综合事务添加到观察程序节点配置设置中，观察程序节点就可以在其测试通过期间开始使用该综合事务。 但是，有些综合事务需要特殊的设置说明，如以下各节所述。
  
### <a name="data-conferencing-synthetic-transaction"></a>数据会议综合事务

如果观察程序节点计算机位于外围网络外部，则可能无法运行数据会议综合事务，除非首先通过完成以下步骤禁用网络服务帐户的 Windows Internet Explorer® Internet 浏览器代理设置：
  
1. 在观察程序节点计算机上，依次单击“开始”、“所有程序”、“附件”，右键单击“命令提示符”，然后单击“以管理员身份运行”。
    
2. 在控制台窗口中，键入以下命令，然后按 Enter。 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    将在命令窗口中看到以下消息：

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    此消息指示你已禁用Internet Explorer服务帐户的代理设置。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange统一消息综合事务

统Exchange统一消息 (统) 综合事务验证测试用户能否连接到邮箱中Exchange。
  
测试用户将需要预配置语音邮件帐户。 
  
### <a name="persistent-chat-synthetic-transaction"></a>持久聊天综合事务

若要使用持久聊天综合事务，必须先创建一个通道，并授予测试用户使用该通道的权限。
  
您可以使用持久聊天综合事务配置此通道： 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

必须从企业内部运行此安装任务：
  
- 如果从非服务器计算机运行，则执行该 cmdlet 的用户必须是 Role-Based Access Control (RBAC) 的 CsPersistentChatAdministrators 角色的成员。
    
- 如果从服务器本身运行，则执行 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 对等呼叫综合事务

该Test-CsPstnPeerToPeerCall事务验证通过公用电话交换网和 PSTN 电话交换 (呼叫) 。
  
若要运行此综合事务，必须配置：
  
- 两个启用 UC 的测试用户 (呼叫方和一个接收器) 。
    
- 为每个用户帐户配置外线直拨分机 (DID) 号码。
    
- 允许呼叫接收者号码到达 PSTN 网关的 VoIP 策略和语音路由。
    
- 接受呼叫和媒体的 PSTN 网关，该网关将基于拨打的号码将呼叫路由回接收者主池。
    
### <a name="unified-contact-store-synthetic-transaction"></a>统一联系人存储综合事务

统一联系人存储综合事务验证用户Skype for Business Server代表用户检索联系人Exchange。
  
若要使用此综合事务，必须满足以下条件：
  
- Lyss-Exchange配置服务器到服务器身份验证。
    
- 测试用户必须具有有效的Exchange邮箱。
    
满足这些条件后，可以运行以下 Windows PowerShell cmdlet 将测试用户的联系人列表迁移到Exchange：
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

测试用户联系人列表可能需要一些时间迁移到Exchange。 若要监视迁移进度，可以在没有 -Setup 标志的情况下运行相同的命令行：
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

迁移完成后，此命令行将成功。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 综合事务

XMPP (可扩展消息传递和状态) IM 综合事务要求使用一个或多个联盟域配置 XMPP 功能。
  
若要启用 XMPP 综合事务，您必须提供 XmppTestReceiverMailAddress 参数以及可路由 XMPP 域中的用户帐户。 例如：
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

本示例中，需要Skype for Business Server规则，以将邮件路由 litwareinc.com XMPP 网关。

> [!NOTE]
> XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 有关详细信息，请参阅迁移 [XMPP 联盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>视频互操作服务器 (VIS) 综合事务

VIS 服务 (互操作服务器) 综合事务需要您下载并安装[ (VISSTSupportPackage.msi) 。](https://www.microsoft.com/download/details.aspx?id=46921) 
  
若要安装VISSTSupportPackage.msi请确保已安装 (msi 的系统) 要求"下的依赖关系。 运行VISSTSupportPackage.msi以执行简单安装。 The .msi installs all the files in the following path： "%ProgramFiles%\VIS Synthetic Transaction Support Package".
  
若要详细了解如何运行 VIS 综合事务，请参阅 [Test-CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) cmdlet 的文档。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>更改综合事务的运行频率
<a name="special_synthetictrans"> </a>

默认情况下，综合事务将每 15 分钟与配置的用户一起运行一次。 综合事务在一组用户内按顺序运行，以避免两个综合事务相互冲突。 需要较长的间隔才能完成所有综合事务。
  
如果更频繁地运行综合事务是可取的，应减少与一组给定用户一起运行的综合事务数，以便测试可以在所需时间范围内完成，同时提供一些偶尔出现网络延迟的缓冲区。 如果需要运行更多的综合事务，请创建更多用户集以运行其他综合事务。
  
若要更改综合事务运行的频率，请按照以下步骤操作：
  
1. 打开System Center Operations Manager。 单击"创作"部分。 单击"创作 (下的规则部分) 。
    
2. 在"规则"部分，查找名称为"主综合事务运行程序性能收集规则"的规则。
    
3. 右键单击该规则，然后选择"覆盖"，选择"覆盖规则"，然后选择"对于类的所有对象：池观察程序"。
    
4. 在"替代属性"窗口中，选择"参数名称""频率"，将"替代值"设置为所需的值。
    
5. 在同一窗口中，选择需要应用此替代的管理包。
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>使用综合事务的富日志记录
<a name="special_synthetictrans"> </a>

综合事务对于帮助识别系统问题非常有用。 例如，Test-CsRegistration cmdlet 可能会提醒管理员，用户难以注册Skype for Business Server。 但是，可能需要更多详细信息来确定失败的实际原因。
  
因此，综合事务可提供丰富的日志记录。 利用丰富的日志记录，对于综合事务执行的每个活动，将记录以下信息：
  
- 活动开始的时间。
    
- 活动完成的时间。
    
- 已执行的操作 (例如，创建、加入或离开会议;登录Skype for Business Server;发送即时消息) 。
    
- 活动运行时生成的信息性、详细、警告或错误消息。
    
- SIP 注册消息。
    
- 活动运行时生成的异常记录或诊断代码。
    
- 运行活动最终结果。
    
每次运行综合事务时都会自动生成此信息，但不自动显示此信息或将此信息保存到日志文件。 如果手动运行综合事务，可以使用 OutLoggerVariable 参数指定一个Windows PowerShell存储该信息的变量。 从该日志，可以选择使用两种方法之一以 XML 或 HTML 格式在富日志中保存和/或查看错误消息。 
  
若要检索疑难解答信息，请指定 OutLoggerVariable 参数，后跟您选择的变量名称：
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> 变量名称不要以 $ 字符开头。 使用变量名称，如 RegistrationTest (，$RegistrationTest) 。 
  
运行此命令时，将看到类似以下的输出：
  
目标 Fqdn ： atl-cs-001.litwareinc.com 结果 ： 失败延迟 ： 00：00：00 错误消息 ： 此计算机没有任何分配的证书。 诊断 ：你可以访问有关此失败的详细信息，而不只是此处显示的错误消息。

若要以 HTML 格式访问此信息，请使用与此类似的命令将存储在变量 RegistrationTest 中的信息保存到 HTML 文件中：
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

您也可以使用 ToXML() 方法将数据保存到 XML 文件：
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

您可以使用可打开 HTML/XML Windows Internet Explorer Microsoft Visual Studio应用程序查看这些文件。
  
从内部运行的综合事务System Center Operations Manager 将自动生成这些日志文件以用于失败。 如果在 PowerShell 能够加载和运行综合事务Skype for Business Server执行失败，将不会生成这些日志。 
  
> [!IMPORTANT]
> 默认情况下，Skype for Business Server将日志文件保存到未共享的文件夹。 若要使这些日志易于访问，应共享此文件夹。 例如 \\ ：atl-watcher-001.litwareinc.com\WatcherNode。
