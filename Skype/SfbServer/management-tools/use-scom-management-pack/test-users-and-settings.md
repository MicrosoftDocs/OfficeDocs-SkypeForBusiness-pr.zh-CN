---
title: 配置观察程序节点测试用户和设置
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 摘要： 配置测试用户帐户和服务器业务综合事务 Skype 的观察程序节点设置。
ms.openlocfilehash: 55172fb152b3b02e87e8d46048c820c2c1b2dd04
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-watcher-node-test-users-and-settings"></a>配置观察程序节点测试用户和设置
 
**摘要：**配置测试用户帐户和服务器业务综合事务 Skype 的观察程序节点设置。
  
在配置后将充当观察者节点的计算机，您必须：
  
1. [配置测试用户帐户](test-users-and-settings.md#testuser)，将由这些观察者节点。 如果您使用协商身份验证方法，您还必须使用**集 CsTestUserCredential** cmdlet 以启用这些测试用于观察程序节点上的帐户。
    
2. 更新的观察程序节点配置设置。
    
## <a name="configure-test-user-accounts"></a>配置测试用户帐户
<a name="testuser"> </a>

测试帐户不需要代表实际的人，但它们必须是有效的 Active Directory 帐户。 此外，这些帐户必须启用为 Skype 业务服务器 2015年，它们必须具有有效的 SIP 地址，并应为企业语音 （用于测试 CsPstnPeerToPeerCall 综合事务） 启用它们。 
  
如果您使用的 TrustedServer 身份验证方法，您需要做是确保这些帐户存在，并对其所述配置。 您应该指定您想要测试每个池的至少三个测试用户。 如果您使用协商身份验证方法，则还必须使用一组 CsTestUserCredential cmdlet 和 Skype 的业务服务器命令行管理程序来启用这些测试帐户要使用综合事务。 通过运行命令类似于以下 （这些命令假定已创建了三个活动目录用户帐户，这些帐户启用的 Skype 的业务服务器 2015年） 执行此操作：
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

您必须包括不仅 SIP 地址，但同时用户名称和密码。 如果不包括密码，集 CsTestUserCredential cmdlet 将提示您输入该信息。 可以通过使用前面的代码块中所示的域 name\user 名称格式指定的用户名。
  
要验证已创建的测试用户凭据，请从 Skype 的业务服务器管理外壳程序运行这些命令：
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

将为每个用户返回类似以下的信息：
  
|**用户名**|**密码**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用默认综合事务配置基本的观察者节点

在创建测试用户之后，可以使用类似以下的命令来创建观察者节点：
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

此命令创建一个新的观察程序节点，将使用默认设置运行综合事务的默认设置。 新观察程序节点还使用测试用户 watcher1@litwareinc.com、 watcher2@litwareinc.com 和 watcher3@litwareinc.com。如果观察者节点使用 TrustedServer 身份验证，三种测试帐户可以是启用 Active Directory 和 Skype 业务服务器的任何有效的用户帐户。 如果观察者节点使用协商身份验证方法，这些用户帐户还必须被启用观察程序节点通过设置 CsTestUserCredential cmdlet。
  
验证目标的自动发现池来登录配置正确，而不是直接面向池改为使用下列步骤：
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>配置扩展的测试

如果您想要启用 PSTN 测试，验证与公共交换的电话网络的连接，您需要执行一些额外的配置设置的观察程序节点时。 首先，您必须将测试用户与 PSTN 测试类型关联由业务服务器管理外壳程序运行从 Skype 与以下类似的命令：
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 此命令的结果必须存储在一个变量中。 在此示例中，变量被命名为 $pstnTest。 
  
接下来，可以使用**新建 CsWatcherNodeConfiguration** cmdlet 将 Skype 业务服务器 2015年池的测试类型 （存储在变量 $pstnTest 中） 相关联。 例如，以下命令将创建池 atl-cs-001.litwareinc.com，添加以前创建的三个测试用户的新观察程序节点配置和添加 PSTN 测试类型：
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

如果您尚未安装 Skype 业务服务器核心文件和 RTCLocal 数据库的观察程序节点计算机上，上面的命令将失败。 
  
若要测试多个语音策略，可以通过使用**New CsExtendedTest** cmdlet 创建为每个策略扩展的测试。 提供的用户应与所需的语音策略配置。 通过使用逗号分隔符，如到**新建 CsWatcherNodeConfiguration** cmdlet 传递扩展的测试：
  
-ExtendedTests @ {0} 添加 = $pstnTest1，pstnTest2 美元，美元 pstnTest3}
  
由于**新建 CsWatcherNodeConfiguration** cmdlet 曾不使用测试参数的情况下，只有默认综合事务 （和指定的扩展综合事务） 将启用新观察程序节点。 因此，观察者节点将测试以下组件：
  
- 注册
    
- IM
    
- GroupIM
    
- P2PAV （对等音频/视频会话）
    
- AvConference （音频/会议）
    
- 状态
    
- ABS （通讯簿服务）
    
- ABWQ （地址簿 web 服务）
    
默认情况下，下列组件也不会测试：
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity （Exchange 统一消息）
    
- JoinLauncher
    
- MCXP2PIM （移动设备即时消息）
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN （PSTN 网关呼叫，指定为扩展测试）
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>添加和移除综合事务

观察者节点配置后，可以使用一组 CsWatcherNodeConfiguration cmdlet 以添加或删除节点的综合事务。 例如，若要向观察者节点的 PersistentChatMessage 测试，使用 Add 方法并与以下类似的命令：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

可以通过用逗号隔开的测试名称添加多个测试。 例如：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

如果一个或多个这些测试 (例如，DataConference) 已经在观察程序节点上已启用，则将发生错误。 在这种情况下，您将收到类似于以下的错误信息：
  
组-CsWatcherNodeConfiguration： 没有重复的键序列 DataConference urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName 键或唯一标识约束。
  
发生此错误时，会不应用任何更改。 应与删除重复测试重新运行该命令。
  
要从观察者节点删除综合事务处理，请使用 Remove 方法。 例如，此命令将从观察者节点删除 ABWQ 测试：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Replace 方法可用于替换所有当前已启用的测试与一个或更多新的测试。 例如，如果您希望只是为了运行 IM 测试观察程序节点，您可以配置，使用此命令：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

当您运行此命令时，指定观察程序节点上的所有综合事务将被禁用，除了 IM。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看和测试观察程序节点配置

如果您想要查看已分配给观察者节点测试，使用与以下类似的命令：
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

此命令将返回的信息类似，具体取决于已分配给节点的综合交易记录：
  
注册 IM GroupIM P2PAV AvConference 出席 PersistentChatMessage DataConference
> [!TIP]
> 若要按字母顺序查看综合事务，而是使用以下命令： 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

来验证已创建了一个观察程序节点，请键入下面的命令从 Skype 业务服务器管理外壳程序：
  
```
Get-CsWatcherNodeConfiguration
```

您将得到的信息与以下类似：
  
身份： atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com、 sip:watcher2@litwareinc.com...} ExtendedTests: {TestUsers = IList < System.String >;名称 = PSTN 测试;Te...} TargetFqdn: atl-cs-001.litwareinc.com 端口号： 5061To 验证观察程序节点是否已配置正确，键入下面的命令从 Skype 业务服务器管理外壳程序：
  
```
Test-CsWatcherNodeConfiguration
```

此命令将在您的部署中测试每个观察者节点并确认是否已完成以下操作：
  
- 安装所需的注册器角色
    
- 创建必需的注册表项 （完成时运行一组 CsWatcherNodeConfiguration cmdlet）
    
- 您的服务器业务服务器运行 Skype 的正确版本
    
- 您的端口已正确配置
    
- 分配的测试用户具有所需的凭据
    
## <a name="managing-watcher-nodes"></a>管理观察程序节点
<a name="testuser"> </a>

除了修改综合观察程序节点执行的事务，还可以使用**一组 CsWatcherNodeConfiguration** cmdlet 执行两项重要任务： 启用和禁用的观察程序节点，以及配置要在运行测试时使用内部 Web Url 或外部的 Web Url 的观察程序节点。
  
默认情况下，旨在定期运行其所有已启用的综合事务观察者节点。 有时，但是，您可能需要挂起这些交易记录。 例如，如果观察者节点暂时从网络上断开，则没有必要运行综合事务。 没有网络连接，这些事务将失败。 若要暂时禁用观察程序节点，请运行业务服务器管理外壳从 Skype 与以下类似的命令：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

此命令将禁用上观察程序节点 atl 观察程序 001.litwareinc.com 的综合事务的执行。若要继续执行综合事务，可用属性重新设置为 True ($True):
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> 可用属性可用于打开或关闭的观察者节点。 如果您想要永久删除观察者节点，使用**删除 CsWatcherNodeConfiguration** cmdlet:
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

该命令从指定的计算机，这样可以防止该计算机自动运行综合事务中删除所有的观察者节点配置设置。 但是，该命令不会卸载系统中心代理文件或 Skype 业务服务器 2015年系统文件。
  
默认情况下，观察者节点进行测试时使用组织的外部 Web Url。 但是，观察者节点，也可以配置为使用组织的内部 Web Url。 这使管理员可以验证 URL 位于周边网络内的用户的访问权限。 配置要使用内部 Url 而不是外部 Url，请将 UseInternalWebURls 属性设置为 True ($True) 的观察程序节点：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

正在此属性重置为 False ($False) 的默认值将导致观察程序再次使用外部 Url:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>综合事务的特殊安装说明
<a name="special_synthetictrans"> </a>

大多数的综合事务可以作为观察者节点上运行的是。 在大多数情况下，只要综合事务添加到观察程序节点配置设置，观察程序节点可以使用综合事务在其测试期间传递。 但是，有一些综合事务需要特殊的安装说明进行操作，如以下各节所述。
  
### <a name="data-conferencing-synthetic-transaction"></a>数据会议综合事务

如果您观察程序节点计算机位于外围网络以外，您将可能不能运行数据会议综合事务，除非您先禁用网络的 Windows Internet Explorer® Internet 浏览器代理服务器设置服务帐户通过完成以下步骤：
  
1. 在观察程序节点计算机上，单击**开始**，单击**所有程序**，都单击**附件**、 右键都单击**命令提示符**下，然后都单击**以管理员身份运行**。
    
2. 在控制台窗口中，键入以下命令，然后按 enter 键。 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

您将看到在命令窗口中显示以下信息：
  
BITSAdmin 已被否决，并不能保证在未来版本的 Windows 中不可用。 现在由位 PowerShell cmdlet 提供用于 BITS 服务管理工具。
  
因特网代理设置为网络服务帐户设置为 NO_PROXY。 
  
(连接 = 默认值)
  
此消息表明您已禁用 Internet Explorer 代理设置为网络服务帐户。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 统一消息综合事务

Exchange 统一消息 (UM) 综合事务验证测试用户可以连接到语音邮件帐户驻留在 Exchange。
  
测试用户将需要进行预配置语音邮件帐户了。 
  
### <a name="persistent-chat-synthetic-transaction"></a>持续聊天综合事务

若要使用持久聊天综合事务，首先要创建一个通道，并授予用户权限以使用它的测试。
  
您可以使用持久聊天综合事务配置此通道： 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true

```

您必须运行此安装程序必须从企业内部运行任务：
  
- 如果从非服务器计算机上运行，执行该 cmdlet 的用户必须是基于角色的访问控制 (RBAC) CsPersistentChatAdministrators 角色的成员。
    
- 如果从该服务器本身运行，执行该 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 呼叫对等综合事务

测试 CsPstnPeerToPeerCall 综合事务验证发出和接收呼叫通过公用交换的电话网 (PSTN) 的能力。
  
若要运行此综合交易记录，您必须配置：
  
- 两个统一通信启用测试用户 （调用方和接收方）。
    
- 直接向内拨号 (DID) 编号，为每个用户帐户的。
    
- 允许接收方的号码呼叫到达 PSTN 网关的 VoIP 策略和语音路由。
    
- 拨打 PSTN 网关，接受呼叫，并将路由调用返回到接收方的主池，根据数量的媒体。
    
### <a name="unified-contact-store-synthetic-transaction"></a>统一联系人存储库综合事务

综合统一联系人存储交易记录验证业务服务器 2015 从 Exchange 中检索联系人代表用户的 Skype 的能力。
  
若要使用此综合交易记录，必须满足以下条件：
  
- 必须配置 Lyss Exchange 服务器到服务器的身份验证。
    
- 测试的用户必须具有有效的 Exchange 邮箱。
    
满足这些条件后，您可以运行下面的 Windows PowerShell cmdlet，要迁移到 Exchange 的测试用户的联系人列表：
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

它需要一些时间测试的用户迁移到 Exchange 的联系人列表。 若要监视的迁移进度，相同的命令行可以运行没有-设置标记：
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

迁移完成后，此命令行中将会成功。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 综合事务

可扩展的消息传递和在线协议 (XMPP) IM 综合事务需要与一个或多个联盟域配置 XMPP 功能。
  
要启用 XMPP 综合事务，必须提供一个 XmppTestReceiverMailAddress 参数可穿绕的 XMPP 域的用户帐户。 例如：
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

在此示例中，Skype 业务服务器 2015年规则将需要将消息路由到 XMPP 网关 litwareinc.com 的存在
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>互操作的视频服务器 (VIS) 综合事务

视频服务器互操作 (VIS) 综合事务都要求您下载并安装综合事务的支持文件 ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921))。 
  
要安装 VISSTSupportPackage.msi 确保为已安装 msi 的依赖项 （在系统要求）。 运行 VISSTSupportPackage.msi 进行简单的安装。 .Msi 文件安装在以下路径中的所有文件:"%ProgramFiles%\VIS 综合事务支持包"。
  
有关如何运行 VIS 综合事务的更多详细信息请参阅[测试 CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet 的文档。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>综合事务更改运行的频率
<a name="special_synthetictrans"> </a>

默认情况下，综合事务将运行与已配置用户每隔 15 分钟。 综合事务是一组用户，以避免彼此发生冲突的两个综合事务中按顺序运行。 较长的间隔需要提供所有的综合事务完成的时间。
  
如果需要更频繁地运行综合事务，以便一些偶尔的网络延迟的缓冲区所需的时间范围内完成测试应减少综合使用一组给定的用户运行的事务数。 如果运行多个综合事务是理想，创建更多的用户集来运行其他综合事务。
  
若要更改的综合事务运行的频率，请执行以下步骤：
  
1. 开放式系统中心操作管理器。 单击创作节。 单击规则部分 （下创作）
    
2. 在规则部分中，查找名为"Main 综合事务流道性能收集规则"规则
    
3. 鼠标右键单击该规则，并选择重写，重写规则，选择，然后选择"类的所有对象： 池观察程序"
    
4. 重写属性窗口中选择参数名称"频率"，并设置到所需的替代值。
    
5. 在同一个窗口中，选择此重写需要应用的管理包
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>使用综合事务日志记录格式
<a name="special_synthetictrans"> </a>

综合事务证明有助于确定与系统问题非常有用。 例如，测试 CsRegistration cmdlet 可能警告管理员用户都遇到了困难与 Skype 业务服务器注册的事实。 但是，可能需要更多详细信息以确定故障的真实原因。
  
由于这个原因，综合事务提供丰富的日志记录。 丰富的记录，为综合事务承担，每个活动记录以下信息：
  
- 活动开始的时间。
    
- 活动结束的时间。
    
- 已执行的操作 (例如，创建、 加入，或离开会议; 到 Skype 业务服务器签名; 发送即时消息)。
    
- 信息性、 详细信息; 警告或活动运行时生成的错误消息
    
- SIP 注册消息。
    
- 异常错误记录或活动运行时生成的诊断代码。
    
- 正在运行活动的最终结果。
    
此信息自动生成的每次运行时的综合事务，但不是会自动显示或保存到日志文件。 如果您手动运行综合事务，您可以使用 OutLoggerVariable 参数指定将在其中存储信息的 Windows PowerShell 变量。 从那里，您可以选择使用两种方法之一保存和/或富中的查看错误消息日志以 XML 或 HTML 格式。 
  
若要检索的疑难解答信息，请指定 OutLoggerVariable 参数，跟您选择的变量名：
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> ： 前面使用 $ 字符的变量名。 使用的变量名称，如 RegistrationTest (而不是 $RegistrationTest)。 
  
当您运行此命令时，您会看到类似于下面的输出：
  
目标 Fqdn: atl-cs-001.litwareinc.com 结果： 故障延迟时间： 00:00:00 的错误消息： 此计算机不具有任何已分配的证书。 诊断： 可以访问此故障比只是此处所示的错误消息的更详细的信息。 若要访问此信息在 HTML 格式，使用类似于此的命令保存到 HTML 文件的 RegistrationTest 变量中存储的信息：
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

或者，您可以使用 ToXML() 方法将数据保存到 XML 文件：
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

您可以通过使用 Windows Internet Explorer、 Microsoft Visual Studio 或任何其他应用程序能够打开 HTML/XML 文件来查看这些文件。
  
综合事务从运行在系统中心操作管理器将自动生成这些日志文件失败。 如果前业务服务器 PowerShell 的 Skype 是能够加载并运行综合事务执行失败，将不会生成这些日志。 
  
> [!IMPORTANT]
> 默认情况下，业务服务器 2015年的 Skype 将日志文件保存到未共享的文件夹。 若要使这些日志可随时访问，应共享此文件夹。 例如： \\atl-watcher-001.litwareinc.com\WatcherNode。 
  

