---
title: 安装和配置观察程序节点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 摘要：为 Skype for business Server 综合事务安装和配置观察程序节点。
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640939"
---
# <a name="install-and-configure-watcher-nodes"></a>安装和配置观察程序节点
 
**摘要：** 为 Skype for business Server 综合事务安装和配置观察程序节点。
  
观察程序节点是定期运行 Skype for Business Server 合成事务的计算机。 综合事务是用于验证关键用户方案（如登录或 exchange 即时消息的功能）是否按预期工作的 Windows PowerShell cmdlet。 对于 Skype for business Server 2015，System Center Operations Manager 可以运行下表中所示的综合事务，其中包括三个综合事务类型：
  
- **默认值**默认情况下，观察程序节点运行的综合事务。 在创建新的观察程序节点时，可以指定将运行该节点的合成事务。  (New-cswatchernodeconfiguration cmdlet 使用的测试参数的用途。 ) 如果在创建观察程序节点时不使用测试参数，它将自动运行所有默认的综合事务，并且不会运行任何非默认的综合事务。 例如，这意味着观察程序节点将配置为运行 CsAddressBookService 测试，但不会配置为运行测试 Test-csexumconnectivity 测试。
    
- **非默认**测试观察程序节点是否在默认情况下不运行。  (有关详细信息，请参阅默认类型的说明。 ) 但是，可以启用观察程序节点以运行任何非默认的综合事务。 在使用 New-cswatchernodeconfiguration cmdlet) 创建观察程序节点 (时，或者在创建观察程序节点之后的任何时间，都可以执行此操作。 请注意，许多非默认的综合事务需要额外的安装步骤。 有关这些步骤的更多详细信息，请参阅[专用的综合事务设置说明](test-users-and-settings.md#special_synthetictrans)。
    
- **扩展**一种特殊类型的非默认综合事务。 与其他综合事务不同，扩展测试可在每次通过的情况下运行多次。 这在验证行为（如多个公开交换的电话网络） (PSTN) 语音路由以用于池时非常有用。 只需将扩展测试的多个实例添加到观察程序节点即可配置此设置。
    
有关将其他综合事务添加到观察程序节点的过程的详细信息，请参阅[Configure a 观察程序节点以运行综合事务](watcher-nodes.md#enable_synthetic_trans)。 您还可以使用 Skype for Business Server 命令行管理程序从观察程序节点中删除综合事务。
  
可用于观察程序节点的综合事务包括：
  
|**Cmdlet 名称（测试名称）**|**说明**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |确认用户能够查找不在其联系人列表中的用户。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |确认用户能够通过 HTTP 查找不在其联系人列表中的用户。  <br/> |
|Test-CsAVConference (AvConference)   <br/> |确保用户能够创建和参与音频/视频会议。  <br/> |
|CsGroupIM (IM 会议) 的测试-  <br/> |确保用户能够在会议中发送即时消息并且可参与三个或三个以上的人员组成的即时消息对话。  <br/> |
|CsIM (P2P IM)   <br/> |确保用户能够发送对等即时消息。  <br/> |
|Test-CsP2PAV (P2PAV)   <br/> |确保用户能够发出对等音频呼叫（仅信号）。  <br/> |
|Test-CsPresence (Presence)  <br/> |确认用户能够查看其他用户的状态。  <br/> |
|Test-CsRegistration (Registration)  <br/> |确认用户能够登录 Skype for Business。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |确保用户能够向企业外部人员发出呼叫以及接收其发出的呼叫（PSTN 号码）。  <br/> |
|Test-CsASConference (ASConference)   <br/> |确认用户能够创建和参与应用程序共享会议。  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)   <br/> |确认音频视频边缘服务器能够接受对等呼叫和会议呼叫的连接。  <br/> |
|Test-CsDataConference (DataConference)   <br/> |确认用户可以参与数据协作会议 (包含诸如白板和轮询等活动的联机会议) 。  <br/> |
|Test-Test-csdialinconferencing (DialinConferencing)   <br/> |确认用户能够拨打电话号码以加入会议。  <br/> |
|Test-Test-csdialinconferencing (DialinConferencing)   <br/> |确认用户能够拨打电话号码以加入会议。  <br/> |
|Test-Test-csexumconnectivity (ExumConnectivity)   <br/> |确认用户可以连接到 Exchange 统一消息 (UM) 。  <br/> |
|CsGroupIM-TestJoinLauncher (JoinLauncher)   <br/> |确认用户能够创建和加入 web 地址链接)  (的计划会议。  <br/> |
|Test-Test-csmcxp2pim (MCXP2PIM)   <br/> |确保移动设备用户能够注册和发送即时消息。  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)   <br/> |确认视频互操作服务器已启动，并且可以通过视频 SIP 中继处理传入连接。  <br/> **注意：** MCX 对旧版移动客户端的支持不再在 Skype for Business Server 2019 中可用。 |
|Test-CsPersistentChatMessage (PersistentChatMessage)   <br/> |确认用户可以使用持久聊天服务交换邮件。  <br/> |
|Test-Test-csucwaconference (UcwaConference)   <br/> |确认用户可以通过 web 加入会议。  <br/> |
|Test-Test-csunifiedcontactstore (UnifiedContactStore)   <br/> |确保可通过统一的联系人存储库访问用户的联系人。 统一联系人存储为用户提供了一种方法来维护一组可通过使用 Skype for Business Server 2015、Outlook 消息传递和协作客户端和/或 Outlook Web Access 访问的联系人。  <br/> |
|Test-CsXmppIM (XmppIM)   <br/> |确认即时消息可以通过可扩展消息和状态协议 (XMPP) 网关发送。  <br/> XMPP 网关和代理在 Skype for business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。  |

您无需安装观察程序节点即可使用 System Center Operations Manager。 如果不安装这些节点，则在出现问题时，您仍可以获取 Skype for Business Server 2015 组件的实时警报。  (组件和用户管理包不使用观察程序节点。 ) 但是，如果要使用活动监视管理包监视端到端方案，则需要观察程序节点。
  
> [!NOTE]
> 管理员还可以手动运行综合事务，而无需使用或安装 Operations Manager。 根据 Skype for Business Server 部署的大小，综合事务可以使用大量计算机内存和处理器时间。 因此，我们建议您将专用计算机用作观察程序节点。 例如，您不应将 Skype for business Server 前端服务器配置为充当观察程序节点。 观察程序节点应满足与 Skype for Business Server 拓扑中的任何其他计算机相同的基本硬件要求。 
  
> [!NOTE]
> 旧版 Lync Server 2013 观察程序节点不能与 Skype for Business Server 2015 观察程序节点在同一台计算机上并置，因为 Lync Server 2013 和 Skype for Business Server 2015 的核心系统文件无法安装在同一台计算机上。 但是，Skype for Business Server 2015 观察程序节点可以同时监视 Skype for business Server 2015 和 Lync Server 2013。 这两个产品版本都支持默认的综合事务。 
  
Lync Server 2013 观察程序节点可以部署在企业内部或外部，以帮助验证：
  
- 至企业内部用户的池的连接。
    
- 通过外围网络连接到企业外部工作的远程用户的连接。
    
- 至分支机构装置的连接。
    
- 在企业内部和通过外围网络连接到 Lync Server 2013。
    
为了帮助简化管理，企业内部和外部提供了不同的身份验证选项。 有关详细信息，请参阅[Configure a 观察程序节点以运行综合事务](watcher-nodes.md#enable_synthetic_trans)。
  
若要配置计算机充当观察程序节点，必须首先完成以下先决条件： 
  
- 安装 System Center Operations Manager 并导入 Skype for Business Server 2015 管理包。 此外，还必须先验证观察程序节点计算机是否满足安装 Skype for Business Server 2015 的所有先决条件。
    
- 在观察程序节点计算机上安装以下项：
    
  - .NET Framework 4.5 的完整版本
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
满足先决条件后，可以通过执行以下步骤来配置观察程序节点：
  
1. 在观察程序节点计算机上安装 Skype for Business Server 2015 core 文件。
    
2. 在观察程序节点计算机上安装 System Center Operations Manager 代理。
    
3. 运行 Watchernode.msi 的可执行文件。
    
4. 使用**new-cswatchernodeconfiguration** cmdlet 可以配置要由观察程序节点使用的测试用户帐户。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>安装 Skype for Business Server 2015 Core 文件和 RTCLocal 数据库

若要在计算机上安装 Skype for Business Server 2015 core 文件，请完成以下过程。 安装核心文件时，将自动安装 RTCLocal 数据库。 请注意，不需要在观察程序节点上安装 SQL Server。 将自动安装 SQL Server Express。
  
若要安装 Skype for Business Server 2015 core 文件和 RTCLocal 数据库，请执行以下操作：
  
1. 在观察程序节点计算机上，依次单击“开始”、“所有程序”和“附件”，再右键单击“命令提示符”，然后单击“以管理员身份运行”。
    
2. 在控制台窗口中，键入以下命令，然后按 ENTER 键。 请务必输入 Skype for business Server 安装程序文件的相应路径： D:\Setup.exe/BootstrapLocalMgmtTo 验证是否已成功安装核心 Skype for business Server 组件，请依次单击 "**开始**"、"**所有程序**"、" **skype for business server 2015**"，然后单击 " **skype for business server Management Shell**"。 在 Skype for Business Server 命令行管理程序中，键入以下 Windows PowerShell 命令，然后按 ENTER：
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 首次运行此命令时，将不会返回任何数据，因为您尚未配置任何观察程序节点计算机。 如果命令运行时不返回错误，则可以假定 Skype for Business Server 安装已成功完成。 
  
如果您的观察程序节点计算机位于您的外围网络中，则可以运行以下命令来验证 Skype for Business Server 2015 的安装：
  
CsPinPolicyYou 将接收与此类似的信息，具体取决于配置为在组织中使用的 PIN 策略数：
  
标识：全局
  
产品介绍
  
MinPasswordLength：5
  
PINHistoryCount：0
  
AllowCommonPatterns： False
  
PINLifetime：0
  
MaximumLogonAttempts :
  
如果您看到有关 PIN 策略的信息，则说明已成功安装核心组件。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>在观察程序节点上安装 Operation Manager 代理文件

与用于报告组件警报的 Skype for business Server 安装程序类似，Skype for business Server 2015 观察程序节点需要安装 System Center Operations Manager 代理文件。 这样，就可以运行合成事务，并将警报报告给 System Center Operations Manager 根管理服务器。
  
若要安装代理文件，请按照[配置将受监视的 Skype for Business Server 计算机](configure-computers-to-monitor.md)中列出的过程操作。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>配置观察程序节点以运行综合事务
<a name="enable_synthetic_trans"> </a>

安装 System Center Operations Manager 代理文件后，必须配置观察程序节点本身。 执行此操作所执行的步骤将有所不同，具体取决于观察程序节点计算机位于外围网络内部还是外部外围网络。 
  
配置观察程序节点时，还必须选择该节点要采用的身份验证方法类型。 Skype for Business Server 2015 使您能够选择以下两种身份验证方法之一：受信任的服务器或凭据身份验证。 下表显示了这两种方法之间的差异：
  
||**说明**|**支持的位置**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |使用证书可模拟内部服务器并绕过身份验证质询。  <br/> 对于更喜欢管理单个证书（而不是在每个观察程序节点上的多个用户密码）的管理员很有用。  <br/> |企业内部。  <br/> 使用此方法时，观察程序节点必须与受监视的池位于同一个域中。 如果观察程序节点和池位于不同的域中，请改用凭据身份验证。  <br/> |
|沟通  <br/> |将用户名和密码安全地存储在每个观察程序节点的 Windows 凭据管理器中。  <br/> 此模式需要更多的密码管理，但这是企业外部的观察程序节点的唯一选项。 不能将这些观察程序节点视为经过身份验证的受信任终结点。  <br/> |企业外部。  <br/> 企业内部。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>将观察程序节点配置为使用受信任的服务器身份验证
<a name="enable_synthetic_trans"> </a>

如果您的观察程序节点计算机位于外围网络内部，则使用受信任的服务器身份验证可以通过维护单个证书大大减少管理任务，而不是使用多个用户帐户密码。
  
若要配置受信任的服务器身份验证，必须首先创建受信任的应用程序池以承载观察程序节点计算机。 创建受信任的应用程序池后，必须将该观察程序节点上的综合事务配置为作为受信任的应用程序运行。
  
> [!NOTE]
> 受信任的应用程序是指作为 Skype for Business Server 2015 的一部分运行的受信任状态的应用程序，但它不是产品的内置部件。 受信任的状态意味着，每次运行该应用程序时，将不会要求其进行身份验证。
  
若要创建受信任的应用程序池，请打开 Skype for Business Server 命令行管理程序，并运行与以下内容类似的命令：
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 有关上述命令中的参数的详细信息，请通过 Skype for Business Server 命令行管理程序提示符键入以下内容： 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

在创建受信任的应用程序池之后，可以使用**CsTrustedApplication** cmdlet 和类似如下的命令，将观察程序节点计算机配置为将综合事务作为受信任的应用程序运行：
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

完成此命令并创建受信任的应用程序后，您必须运行**enable-cstopology** cmdlet，以确保更改生效：
  
```PowerShell
Enable-CsTopology
```

观察程序节点计算机帐户要求能够查询用于某些合成事务的 CMS。 若要允许此功能，请将观察程序节点的计算机帐户添加到 RTCUniversalReadOnlyAdmins 安全组。 AD 复制发生后，重新启动计算机。
  
若要验证是否已创建新的受信任应用程序，请在 Skype for Business Server 命令行管理程序提示符处键入以下内容：
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>在观察程序节点上配置默认证书
<a name="enable_synthetic_trans"> </a>

使用 TrustedServer 身份验证的每个观察程序节点必须具有使用 Skype for Business Server 部署向导分配的默认证书。 
  
要分配默认证书，请执行以下操作：
  
1. 依次单击 "开始"、"所有程序"、"Skype for Business Server 2015"，然后单击 "Skype for Business Server 部署向导"。 
    
2. 在 "Skype for Business Server 部署向导" 中，单击 "安装或更新 Skype for Business Server 系统"，然后单击 "标题请求" 下的 "运行"，安装或分配证书。 
    
> [!NOTE]
> 如果禁用“运行”按钮，则您可能需要先单击“安装本地配置存储”下方的“运行”。 
  
执行下列操作之一：
  
- 如果您已拥有可用作默认证书的证书，请单击证书向导中的 "默认"，然后单击 "分配"。 按照证书分配向导中的步骤进行操作以分配此证书。
    
- 如果需要申请证书以使用默认证书，请单击 "请求"，然后按照证书请求向导中的步骤请求证书。 如果您使用 Web Server 证书的默认值，则您将获得可作为默认证书分配的证书。
    
## <a name="install-and-configure-a-watcher-node"></a>安装和配置观察程序节点
<a name="enable_synthetic_trans"> </a>

在重新启动观察程序节点计算机并配置证书之后，您必须运行 Watchernode.msi 的文件。  (必须在安装了 Operations Manager 代理文件和 Skype for Business Server 2015 core 组件的任何计算机上运行 Watchernode.msi。 )  
  
若要安装和配置观察程序节点，请执行以下操作：
  
1. 依次单击 "开始"、"所有程序" 和 "Skype for Business Server 2015"，然后单击 "Skype for Business Server Management Shell"，打开 Skype for Business Server 命令行管理程序。 
    
2. 在命令行管理程序中，键入以下命令，然后按 ENTER (确保并指定您的 Watchernode.msi 的副本的实际路径) ：
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> 您还可以从命令窗口中运行 Watchernode.msi n。 若要打开命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。 当命令窗口打开时，键入与上面的步骤2中所示的相同命令。 
  
> [!IMPORTANT]
> 在上面的命令中，名称/值对 Authentication = TrustedServer 区分大小写。 必须完全按照所示键入。 例如，此命令将失败，因为它不使用正确的字母大小写： 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer 模式只能用于位于外围网络内部的计算机。 当观察程序节点在 TrustedServer 模式下运行时，管理员无需在计算机上维护测试用户密码。
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>配置观察程序节点以使用协商
<a name="enable_synthetic_trans"> </a>

如果您的观察程序节点计算机位于外围网络之外，则您必须执行略微不同的过程，以便将该观察程序节点配置为运行综合事务：尤其是，您不应创建受信任的应用程序池或受信任的应用程序。 这意味着您需要完成接下来的两个任务。
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>更新 RTC 本地只读 Administrators 组中的成员身份

如果您的观察程序节点位于外围网络之外，则必须通过在观察程序节点上完成以下过程，将网络服务帐户添加到观察程序节点计算机上的 RTC 本地只读 Administrators 组中：
  
1. 单击“开始”，右键单击“计算机”，然后单击“管理”。
    
2. 在服务器管理器中，展开“配置”，展开“本地用户和组”，然后单击“组”。
    
3. 在“组”窗格中，双击“RTC Local Read-only Administrators”。
    
4. 在“RTC Local Read-only Administrators 属性”对话框中，单击“添加”。
    
5. 在“选择用户、计算机、服务帐户或组”对话框中，单击“位置”。
    
6. 在“位置”对话框中，选择观察程序节点计算机的名称，然后单击“确定”。
    
7. 在“输入要选择的对象名称”框中，键入“Network Service”，然后单击“确定”。
    
8. 在“RTC Local Read-only Administrators 属性”对话框中，单击“确定”，然后关闭“服务器管理器”。
    
9. 重新启动观察程序节点计算机。
    
### <a name="install-the-watcher-node-configuration-files"></a>安装观察程序节点配置文件

下一步是运行文件 Watchernode.msi： 
  
1. 打开 Microsoft Skype for Business Server 2015 命令行管理程序。 依次单击 "开始"、"所有程序"、"Microsoft Skype for Business Server 2015"，然后单击 "Skype for Business Server Management Shell"。 
    
2. 在 Skype for Business Server 命令行管理程序中，键入以下命令，然后按 ENTER (确保指定 Watchernode.msi) 副本的实际路径：
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 如前所述，也可以从命令窗口运行 Watchernode.msi。 若要打开命令窗口，请单击“开始”****，右键单击“命令提示符”****，然后单击“以管理员身份运行”****。 当命令窗口打开时，键入与上面的步骤2中所示的相同命令。 
  
任何时候如果无法将观察程序节点设置为一个受信任应用程序池，都将使用协商模式。 在此模式中，管理员需要管理观察程序节点上的测试用户密码。
  

