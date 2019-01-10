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
description: 摘要： 配置测试用户帐户和业务服务器综合事务的 Skype 的观察程序节点设置。
ms.openlocfilehash: 257814108a276d049ed4ac9173fde6dfa4473ff2
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789389"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>配置观察程序节点测试用户和设置
 
**摘要：** 配置测试用户帐户和业务服务器综合事务的 Skype 的观察程序节点设置。
  
配置将充当观察程序节点计算机之后，您必须：
  
1. [配置测试用户帐户](test-users-and-settings.md#testuser)，使用这些观察程序节点。 如果您使用的协商身份验证方法，您还必须使用**Set-cstestusercredential** cmdlet 来启用这些测试观察程序节点上使用的帐户。
    
2. 更新观察程序节点配置设置。
    
## <a name="configure-test-user-accounts"></a>配置测试用户帐户
<a name="testuser"> </a>

测试帐户不需要表示实际的人员，但他们必须是有效的 Active Directory 帐户。 此外，这些帐户必须为 Business Server 启用的 Skype、 它们必须具有有效的 SIP 地址和它们应启用企业语音 （以便使用 Test-cspstnpeertopeercall 综合事务）。 
  
如果您使用的 TrustedServer 身份验证方法，您需要执行所有是确保这些帐户存在，并将其如前所述配置。 为每个要测试的池的至少两个测试用户，您应将其分配。 如果您使用的协商身份验证方法，您还必须使用 Set-cstestusercredential cmdlet 和业务 Server 命令行管理程序启用这些 Skype 测试帐户的综合事务处理。 执行此操作通过运行类似以下 （这些命令假定已创建了两个 Active Directory 用户帐户并为业务服务器的 Skype 启用这些帐户） 的命令：
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

您必须包括不仅的 SIP 地址，但还用户名和密码。 如果不包括密码，Set-cstestusercredential cmdlet 将提示您输入的信息。 可以通过使用前面的代码块中所示的域 name\user 名称格式指定的用户的用户名。
  
若要验证已创建的测试用户凭据，请从 Skype 的业务 Server 命令行管理程序运行以下命令：
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

为每个用户，将返回类似于以下的信息：
  
|**用户名**|**密码**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用默认综合事务配置基本观察程序节点

创建测试用户之后，您可以使用类似如下的命令创建观察程序节点：
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

此命令创建一个新的观察程序节点的使用默认设置并在运行综合事务的默认设置。 新的观察程序节点还使用的测试用户 watcher1@litwareinc.com 和 watcher2@litwareinc.com。 如果观察程序节点使用 TrustedServer 身份验证，两个测试帐户可以是任何有效的用户帐户启用 Active Directory 和 Skype 业务 Server。 如果观察程序节点使用的协商身份验证方法，这些用户帐户必须也启用观察程序节点使用 Set-cstestusercredential cmdlet。
  
若要验证目标的自动发现登录的池已正确配置，而不是直接目标池改为使用以下步骤：
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>配置扩展的测试

如果您想要启用 PSTN 测试，验证与公用电话交换网的连接，您需要执行其他一些配置设置的观察程序节点时。 首先，必须通过运行 Business Server 命令行管理程序从 Skype 类似于以下命令将测试用户与 PSTN 测试类型关联：
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 此命令的结果必须存储在变量中。 本示例中，该变量名为 $pstnTest。 
  
接下来，您可以使用**New-cswatchernodeconfiguration** cmdlet 将业务服务器池 Skype 的测试类型 （存储在变量 $pstnTest） 相关联。 例如，以下命令创建新观察程序节点配置的池 atl-cs-001.litwareinc.com，添加两个测试用户之前，创建和添加 PSTN 测试类型：
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

如果您尚未安装 Skype 业务 Server 核心文件和 RTCLocal 数据库在观察程序节点计算机上，上述命令将失败。 
  
若要测试多个语音策略，可以使用**New-csextendedtest** cmdlet 创建每个策略扩展的的测试。 应与所需的语音策略配置提供的用户。 扩展的测试传递到**New-cswatchernodeconfiguration** cmdlet 通过使用逗号分隔的分隔符，如：
  
-ExtendedTests @{添加 = $pstnTest1$ pstnTest2、 $pstnTest3}
  
由于无需使用 Tests 参数调用**New-cswatchernodeconfiguration** cmdlet，将为新观察程序节点启用仅默认综合事务 （和指定的扩展综合事务）。 因此，观察程序节点将测试以下组件：
  
- 注册
    
- 即时消息
    
- GroupIM
    
- P2PAV （对等音频/视频会话）
    
- AvConference （音频/会议）
    
- 状态
    
- ABS （通讯簿服务）
    
- ABWQ （通讯簿 web 服务）
    
默认情况下不会测试以下组件：
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity （Exchange 统一消息）
    
- JoinLauncher
    
- MCXP2PIM （旧的移动设备即时消息）
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN （PSTN 网关呼叫，作为扩展测试指定）
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>添加和删除综合事务

在配置观察程序节点之后，您可以使用 Set-cswatchernodeconfiguration cmdlet 添加或删除节点的综合事务。 例如，若要添加到观察程序节点 PersistentChatMessage 测试，使用 Add 方法和类似于以下命令：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

通过使用逗号分隔的测试名称可以添加多个测试。 例如：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

如果一个或多个这些测试 (例如，DataConference) 已启用观察程序节点上，将发生错误。 在这种情况下，您会收到类似于以下错误消息：
  
Set-cswatchernodeconfiguration： 没有重复的键序列 DataConference' 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName 键或唯一标识约束。
  
发生此错误时，将不应用任何更改。 应与重复测试删除重新运行该命令。
  
若要从观察程序节点删除综合事务，请使用 Remove 方法。 例如，此命令会删除 ABWQ 测试从观察程序节点：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

您可以使用 Replace 方法替换所有当前已启用的测试与一个或更多新测试。 例如，如果您希望仅来运行该 IM 测试观察程序节点，您可以配置的使用以下命令：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

运行此命令时，除了 IM 以外，将禁用指定观察程序节点上的所有综合事务。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看和测试观察程序节点配置

如果您想要查看已分配给观察程序节点测试，使用类似如下的命令：
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

此命令将返回信息类似于以下，具体取决于已分配给节点的综合事务：
  
注册 IM GroupIM P2PAV AvConference 状态 PersistentChatMessage DataConference
> [!TIP]
> 若要按字母顺序查看综合事务，请改为使用以下命令： 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

若要验证已创建观察程序节点，键入业务 Server 命令行管理程序从 Skype 以下命令：
  
```
Get-CsWatcherNodeConfiguration
```

您将获得信息类似如下：
  
标识： atl-cs-001.litwareinc.com <br/>
TestUsers: {sip:watcher1@litwareinc.com，sip:watcher2@litwareinc.com...}<br/>
ExtendedTests: {TestUsers = IList < System.String >;名称 = PSTN 测试;Te...}<br/>
TargetFqdn: atl-cs-001.litwareinc.com<br/>
端口号： 5061<br/>

若要验证已正确配置观察程序节点，键入业务 Server 命令行管理程序从 Skype 以下命令：
  
```
Test-CsWatcherNodeConfiguration
```

此命令将测试您的部署中的每个观察程序节点，并确认是否已完成以下操作：
  
- 安装所需的注册器角色。
    
- 创建必需的注册表项 （完成您运行 Set-cswatchernodeconfiguration cmdlet 时）。
    
- 您的服务器的企业服务器运行 Skype 的正确版本。
    
- 您的端口配置正确。
    
- 您已分配的测试用户具有所需的凭据。
    
## <a name="managing-watcher-nodes"></a>管理观察程序节点
<a name="testuser"> </a>

除了修改执行观察程序节点的综合事务，您可以使用**Set-cswatchernodeconfiguration** cmdlet 执行两个其他重要任务： 启用和禁用观察程序节点，以及配置运行测试时，使用内部 Web Url 或外部 Web Url 的观察程序节点。
  
默认情况下，旨在定期运行其所有已启用的综合事务观察程序节点。 有时，但是，您可能想要暂停这些事务。 例如，如果从网络上暂时断开观察程序节点，则没有理由运行综合事务。 没有网络连接，这些事务将失败。 要暂时禁用观察程序节点，请对业务 Server 命令行管理程序运行从 Skype 类似于以下命令：
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

此命令将禁用综合事务观察程序节点 atl 观察程序 001.litwareinc.com 上的执行。 若要继续执行的综合事务，设置 Enabled 属性返回为 True ($True):
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled 属性可用于打开或关闭观察程序节点。 如果您想要永久删除观察程序节点，使用**Remove-cswatchernodeconfiguration** cmdlet:
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

该命令删除指定的计算机，这样可以防止在该计算机自动运行综合事务的所有观察程序节点配置设置。 但是，该命令不会卸载 System Center 代理文件或业务 Server 系统文件 Skype。
  
默认情况下，观察程序节点使用组织的外部 Web Url 时进行测试。 但是，观察程序节点，还可以配置为使用组织的内部 Web Url。 这使管理员可以确认 for 位于外围网络的用户的 URL 访问。 若要配置观察程序节点以使用内部 Url，而不是外部 Url，请将 UseInternalWebURls 属性设置为 True ($True):
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

重置为默认值为 false，表示 ($False) 的此属性将导致观察程序再次使用的外部 Url:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>综合事务的特殊设置说明
<a name="special_synthetictrans"> </a>

大多数综合事务可以作为观察程序节点上运行的是。 在大多数情况下，只要综合事务将添加到观察程序节点配置设置，观察程序节点可以开始的使用其测试期间的综合事务将传递。 但是，有一些综合事务需要特殊设置说明的以下各节中所述。
  
### <a name="data-conferencing-synthetic-transaction"></a>数据会议综合事务

如果您观察程序节点计算机位于外围网络外，您将可能无法运行数据会议综合事务，除非您先禁用网络的 Windows Internet Explorer® Internet 浏览器代理设置通过完成以下步骤的服务帐户：
  
1. 在观察程序节点计算机上，表中，单击**开始**、 单击**所有程序**，都单击**附件**数据，右键都单击**命令提示符处**，，然后都单击**以管理员身份运行**。
    
2. 在控制台窗口中，键入以下命令，然后按 ENTER。 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

您将看到命令窗口中显示以下消息：
  
BITSAdmin 已弃用，不保证在将来版本的 Windows 中不可用。 现在由位 PowerShell cmdlet 提供 BITS 服务管理工具。
  
Internet NetworkService 帐户的代理设置设置为 NO_PROXY。 
  
(连接 = 默认值)
  
此消息表明您已禁用网络服务帐户的 Internet Explorer 代理设置。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 统一消息综合事务

Exchange 统一消息 (UM) 综合事务验证测试用户可以连接到帐户驻留在 Exchange 中的语音邮件。
  
测试用户将需要预配置了语音邮件帐户。 
  
### <a name="persistent-chat-synthetic-transaction"></a>持久聊天综合事务

若要使用持久聊天的综合事务，必须首先创建通道，并授予用户权限以使用它的测试。
  
您可以使用持久聊天的综合事务配置此通道： 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

您必须运行此安装程序必须从企业内部运行任务：
  
- 如果从非服务器计算机运行，执行 cmdlet 的用户必须是基于角色的访问控制 (RBAC) 的 CsPersistentChatAdministrators 角色的成员。
    
- 如果从服务器本身运行，执行 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 对等呼叫综合事务

Test-cspstnpeertopeercall 综合事务验证发起和接收通过公用电话交换网 (PSTN) 呼叫的能力。
  
若要运行此综合事务，您必须配置：
  
- 两个启用 UC 的测试用户 （呼叫者和接收者）。
    
- 每个用户帐户的外线直拨分机 (DID) 号码。
    
- 允许对接收者的号码的呼叫到达 PSTN 网关的 VoIP 策略和语音路由。
    
- 拨打接受呼叫并将路由回接收者主池，基于该号码的呼叫的媒体的 PSTN 网关。
    
### <a name="unified-contact-store-synthetic-transaction"></a>统一的联系人存储库综合事务

统一联系人存储库综合事务验证业务服务器从 Exchange 中检索代表用户的联系人的 Skype 的能力。
  
若要使用此综合事务，必须满足以下条件：
  
- 必须配置 Lyss Exchange 服务器到服务器身份验证。
    
- 测试用户必须具有有效的 Exchange 邮箱。
    
满足这些条件后，您可以运行以下 Windows PowerShell cmdlet 将测试用户的联系人列表迁移到 Exchange:
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

可能需要一些时间，测试将迁移到 Exchange 的用户联系人列表。 若要监视迁移进度，相同的命令行可以运行-安装标记的情况下：
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

迁移完成后，将会成功此命令行。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 综合事务

可扩展消息传递和状态协议 (XMPP) IM 综合事务需要与一个或多个联盟域配置 XMPP 功能。
  
若要启用 XMPP 综合事务，必须使用可路由的 XMPP 域的用户帐户提供 XmppTestReceiverMailAddress 参数。 例如：
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

本示例中，业务服务器规则 Skype 需要路由到 XMPP 网关的 litwareinc.com 的消息已存在。

> [!NOTE]
> XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。 有关详细信息，请参阅[迁移 XMPP 联盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>视频互操作性服务器 (VIS) 综合事务

视频互操作服务器 (VIS) 综合事务需要您下载并安装综合事务支持文件 ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921))。 
  
若要安装 VISSTSupportPackage.msi 确保的 msi 已安装了 （下系统要求） 的依赖关系。 运行 VISSTSupportPackage.msi 进行简单的安装。 .Msi 安装在以下路径中的所有文件:"%ProgramFiles%\VIS 综合事务支持包"。
  
有关如何运行 VIS 综合事务的详细信息，请参阅[测试 CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet 的文档。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>综合事务的更改的运行的频率
<a name="special_synthetictrans"> </a>

默认情况下综合事务将与配置用户每 15 分钟运行。 综合事务的用户，以避免相互冲突的两个综合事务一组按顺序运行。 较长的间隔需要提供所有综合事务，若要完成的时间。
  
它是否需要更频繁地运行综合事务，以便与偶尔网络延迟一些缓冲区所需的时间范围内完成测试应减少与给定的用户设置运行综合事务数。 如果运行的更多的综合事务，需要创建多个用户设置运行其他综合事务。
  
若要更改频率运行综合事务的频率，请按照下列步骤：
  
1. 打开 System Center Operations Manager。 单击创作节。 单击 （在创作） 下的规则部分。
    
2. 在规则部分中，找到名为"Main 综合事务运行程序性能集合规则"规则。
    
3. 右键单击该规则，并选中覆盖，选择该规则，重写方法，然后选择"类别的所有对象： 池观察程序"。
    
4. 覆盖属性窗口中选择参数名称"频率"，并将覆盖值设置为所需的一个。
    
5. 在同一窗口中，选择此重写需要应用的管理包。
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>使用综合事务的富日志记录
<a name="special_synthetictrans"> </a>

综合事务证明中帮助确定系统与问题非常有用。 例如，Test-csregistration cmdlet 无法通知用户已有难度业务服务器注册 Skype 事实的管理员。 但是，可能需要其他详细信息，以确定实际失败的原因。
  
因此，对于综合事务提供丰富的日志记录。 使用富日志记录，每个活动的综合事务不承担，记录以下信息：
  
- 活动的开始时间。
    
- 活动的完成时间。
    
- 已执行的操作 (例如，创建、 加入或离开会议; 登录到 Skype 并 Business Server; 发送即时消息)。
    
- 信息性、 verbose 和警告或在活动运行时生成的错误消息。
    
- SIP 注册消息。
    
- 异常记录或诊断代码生成在活动运行时。
    
- 运行活动的最终结果。
    
此信息将自动生成每次运行时综合事务，但不是会自动显示或保存到日志文件。 如果手动运行综合事务，您可以使用 OutLoggerVariable 参数指定的信息将存储在其中的 Windows PowerShell 变量。 从此处，您可以使用两种方法之一将保存的选择和/或视图中丰富的错误消息日志以 XML 或 HTML 格式。 
  
若要检索的疑难解答信息，请指定 OutLoggerVariable 参数，后, 跟您选择的变量名：
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> 不以 $ 字符在变量名。 使用一个变量的名称，例如 RegistrationTest (而不是 $RegistrationTest)。 
  
运行此命令时，您将看到类似如下的输出：
  
目标 Fqdn: atl-cs-001.litwareinc.com 结果： 故障延迟： 00:00:00 错误消息： 此计算机不具有任何已分配的证书。 诊断： 您可以访问此故障比刚刚此处显示的错误消息的更详细的信息。

若要访问此信息以 HTML 格式，使用与此类似的命令以保存到 HTML 文件的 RegistrationTest 变量中存储的信息：
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

此外，您可以使用 ToXML() 方法将数据保存到 XML 文件：
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

您可以通过使用 Windows Internet Explorer、 Microsoft Visual Studio 或任何其他应用程序能够打开 HTML/XML 文件中查看这些文件。
  
在 System Center Operations Manager 从运行综合事务将自动生成这些日志文件的故障。 如果在执行失败，无法加载并运行综合事务的业务 Server PowerShell Skype 之前，将不会生成这些日志。 
  
> [!IMPORTANT]
> 默认情况下，业务服务器 Skype 将日志文件存储不共享的文件夹。 若要使无法访问这些日志，您应共享该文件夹。 例如： \\atl-watcher-001.litwareinc.com\WatcherNode。 
