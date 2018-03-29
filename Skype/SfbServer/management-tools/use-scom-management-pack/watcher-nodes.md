---
title: 安装和配置观察程序节点
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 摘要： 为安装和配置观察者节点 Skype 业务服务器综合事务。
ms.openlocfilehash: 2ba6c6e0ac201d9721d281c87665fe9bf9c0407c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-configure-watcher-nodes"></a>安装和配置观察程序节点
 
**摘要：**安装和配置为 Skype 业务服务器综合事务的观察者节点。
  
观察者节点是定期业务服务器综合事务运行 Skype 的计算机。 综合事务是验证关键用户方案（如能否登录或交换即时消息）是否正常起作用的 Windows PowerShell cmdlet。 对于业务服务器 2015年的 Skype，系统中心操作管理器可以运行下表中，其中包括三种综合事务类型中所示的综合交易记录：
  
- **默认值**综合观察者节点默认运行的事务。 创建新的观察程序节点时，可以指定该节点将运行哪些综合事务。 （这是使用 New CsWatcherNodeConfiguration cmdlet 的测试参数的目的）。如果您不使用测试参数创建观察者节点时，它会自动运行所有默认综合事务并将不会都运行任何非默认综合事务。 这意味着，例如，观察程序节点将配置为运行 Test-CsAddressBookService 测试，但不会配置为运行 Test-CsExumConnectivity 测试。
    
- **非默认值**默认情况下不运行观察者节点的测试。 （有关详细信息，请参阅默认类型的描述。但是，观察者节点可以启用要运行任何非默认综合事务。 当您创建观察者节点 （例如，通过使用 New CsWatcherNodeConfiguration cmdlet），或已创建观察者节点后的任何时间，您可以这样做。 请注意，许多非默认综合事务需要额外的安装步骤。 有关这些步骤的详细信息，请参阅综合事务的特殊的安装说明进行操作。 有关这些步骤的详细信息，请参阅[综合事务的特殊安装说明](test-users-and-settings.md#special_synthetictrans)。
    
- **扩展**一种特殊类型的非默认综合事务。 与其他综合事务扩展测试可以多次运行在每个过程。 验证的行为，如一个池的多个公用交换的电话网络 (PSTN) 语音路由时，这非常有用。 您可以配置此只需通过添加到观察者节点扩展测试的多个实例。
    
有关向观察程序节点添加其他综合事务的过程的详细信息，请参阅[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)。 您可以使用业务服务器管理外壳的 Skype 去综合事务从观察者节点。
  
可用于观察程序节点的综合事务包括：
  
|**Cmdlet 名称 （测试名称）**|**说明**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |确认用户能够查找不在他们的联系人列表中的用户。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |确认用户能找到不会通过 HTTP 其联系人列表中的用户。  <br/> |
|测试-CsAVConference (AvConference)  <br/> |确认用户能够创建和参与音频/视频会议。  <br/> |
|Test-CsGroupIM (IM Conferencing)  <br/> |确认用户能够在会议中发送即时消息并且可参与三个或三个以上的人员组成的即时消息对话。  <br/> |
|Test-CsIM (P2P IM)  <br/> |确认用户能够发送对等即时消息。  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |确认用户能够发出对等音频呼叫（仅信号）。  <br/> |
|Test-CsPresence (Presence)  <br/> |确认用户就能够查看其他用户的状态。  <br/> |
|Test-CsRegistration (Registration)  <br/> |确认用户可以登录到 Skype 的业务。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |确认用户能够向企业外部人员发出呼叫以及接收其发出的呼叫（PSTN 号码）。  <br/> |
|Test-CsASConference (ASConference)  <br/> |确认用户能够创建和参与应用程序共享会议。  <br/> |
|测试-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |确认音频视频边缘服务器能够接受对等呼叫和会议呼叫的连接。  <br/> |
|测试-CsDataConference (DataConference)  <br/> |确认用户可参与数据协作会议（包含白板和投票等活动的联机会议）。  <br/> |
|测试-CsDialinConferencing (DialinConferencing)  <br/> |确认用户能够拨打电话号码加入会议。  <br/> |
|测试-CsDialinConferencing (DialinConferencing)  <br/> |确认用户能够拨打电话号码加入会议。  <br/> |
|测试-CsExumConnectivity (ExumConnectivity)  <br/> |确认用户可以连接到 Exchange 统一消息 (UM)。  <br/> |
|测试 CsGroupIM TestJoinLauncher (JoinLauncher)  <br/> |确认用户能够创建并加入计划的会议（通过 Web 地址链接）。  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |确认移动设备用户能够注册和发送即时消息。  <br/> |
|测试-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |确认互操作的视频服务器处于活动状态，可以通过视频的 SIP 中继处理传入的连接。  <br/> |
|测试-CsPersistentChatMessage (PersistentChatMessage)  <br/> |确认用户可使用持久聊天服务交换消息。  <br/> |
|测试-CsUcwaConference (UcwaConference)  <br/> |确认用户可通过 Web 加入会议。  <br/> |
|测试-CsUnifiedContactStore (UnifiedContactStore)  <br/> |确认可通过统一的联系人存储库访问用户的联系人。 统一的联系人存储库提供一种为用户维护一组可由业务服务器 2015年、 Outlook 消息传递和协作客户端和/或 Outlook Web Access 使用 Skype 的联系人。  <br/> |
|测试-CsXmppIM (XmppIM)  <br/> |确认可通过可扩展消息传递和状态协议 (XMPP) 网关发送即时消息。  <br/> |
   
您不需要安装观察程序节点使用系统中心操作管理器。 如果您不安装这些节点，您仍然可以实时警报从 Skype 业务服务器 2015年组件时出现问题。 （组件和用户管理包不使用观察者节点。）但是，观察者节点是必需的如果您想要通过主动监控管理包监视端到端方案。
  
> [!NOTE]
> 管理员还可手动运行综合事务，而无需使用或安装 Operations Manager。 根据您的业务服务器部署 Skype 的大小，综合事务可以使用大量的计算机内存和处理器时间。 因此，建议您使用专用计算机作为观察程序节点。 例如，则不应该配置业务服务器前端服务器充当观察者节点的 Skype。 观察者节点应满足您 Skype 业务服务器拓扑中的任何其他计算机的基本硬件要求相同。 
  
> [!NOTE]
> 旧式的 Lync Server 2013 观察者节点不能搭配 Skype 业务服务器 2015年观察程序节点的同一计算机上，因为不能在同一台计算机上安装 Lync Server 2013 和业务服务器 2015年的 Skype 的核心系统文件。 但是，Skype 业务服务器 2015年观察程序节点可以同时监视 Skype 业务服务器 2015年和 Lync Server 2013。 默认综合事务同时支持两种产品版本。 
  
内部或外部企业帮助验证可能部署 Lync Server 2013 观察者节点：
  
- 至企业内部用户的池的连接。
    
- 通过在企业外部工作的远程用户的外围网络的连接。
    
- 至分支机构装置的连接。
    
- 连接的 Lync Server 2013 到企业内部和通过外围网络。
    
为了帮助简化管理，企业内部和外部有不同的身份验证选项。有关详细信息，请参阅[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)。
  
为了将计算机配置为观察程序节点，必须先完成以下前提任务： 
  
- 安装系统中心操作管理器并导入管理包业务服务器 2015 Skype。 您必须也首先验证观察程序节点计算机满足所有的业务服务器 2015年安装 Skype 的先决条件。
    
- 在观察程序节点上安装以下项目：
    
  - 完整版本的.NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
在满足先决条件后，可按下面的步骤配置观察程序节点：
  
1. 安装 Skype 业务服务器 2015年观察程序节点计算机上的核心文件。
    
2. 观察程序节点计算机上安装系统中心操作管理器代理。
    
3. 运行 Watchernode.msi 可执行文件。
    
4. 使用 **New-CsWatcherNodeConfiguration** cmdlet 配置观察程序节点要采用的测试用户帐户。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>安装 Skype for Business Server 2015 核心文件和 RTCLocal 数据库

要安装业务服务器 2015年核心文件在计算机上的 Skype，请完成以下过程。 安装核心转储文件时，将自动安装的 RTCLocal 数据库。 请注意，您不需要在观察者节点上安装 SQL Server。 SQL Server Express 将被自动安装。
  
若要安装 Skype 业务服务器 2015年核心文件和 RTCLocal 数据库：
  
1. 在观察程序节点计算机上，依次单击“开始”、“所有程序”和“附件”，再右键单击“命令提示符”，然后单击“以管理员身份运行”。
    
2. 在控制台窗口中，键入以下命令，再按 Enter。 请务必输入业务服务器的安装程序文件的相应路径到您 Skype: D:\Setup.exe /BootstrapLocalMgmtTo 验证核心 Skype 业务服务器组件已成功安装，请单击**开始**，单击**所有程序****Skype 的业务服务器 2015年**，请单击，然后单击**业务服务器管理外壳的 Skype**。 在业务服务器管理外壳的 Skype，键入下面的 Windows PowerShell 命令并按 ENTER:
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 首次运行此命令时，不会返回任何数据，因为您尚未配置任何观察程序节点计算机。 如果命令运行而不会返回错误，则可以假定 Skype 业务服务器安装程序已成功完成。 
  
如果您的观察程序节点计算机位于您的外围网络内部，则可以运行以下命令来验证 Skype for Business Server 2015 的安装：
  
获得 CsPinPolicyYou 将收到类似于此，根据 PIN 策略配置为可在您的组织的数目的信息：
  
身份： 全球
  
说明：
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns： 假
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
如果看到有关 PIN 策略的信息，表明核心组件已安装成功。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>在观察程序节点上安装 Operation Manager 代理文件

类似的报告组件通知业务服务器安装 Skype，Skype 业务服务器 2015年观察程序节点需要安装系统中心操作管理器代理文件。 这样综合事务运行和警报，报告给系统中心操作管理器根管理服务器。
  
要安装代理程序文件，请按照[Skype 业务服务器计算机将监视配置](configure-computers-to-monitor.md)中列出的步骤。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>将观察程序节点配置为运行综合事务
<a name="enable_synthetic_trans"> </a>

系统中心操作管理器代理文件安装完毕后，您必须配置观察程序节点本身。 配置步骤将因观察程序节点计算机位于外围网络内部还是外部而有所不同。 
  
配置观察程序节点时，还必须选择该节点要采用的身份验证方法类型。 商业服务器 2015年的 Skype，您可以选择两种身份验证方法之一： 受信任的服务器或身份验证凭据。 下表显示了这两种方法间的差异：
  
||**说明**|**受支持的位置**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |使用证书进行模拟内部服务器，绕过身份验证质询。  <br/> 对于希望管理单个证书，而不是每个观察者节点上的多个用户密码管理员来说非常有用。  <br/> |在企业。  <br/> 采用这种方法时，观察程序节点必须与要监控的池位于同一个域中。 如果观察程序节点与池在不同的域中，请改用凭据身份验证。  <br/> |
|Negotiate  <br/> |用户名称和密码安全地存储在 Windows 凭据管理器在每个观察者节点。  <br/> 此模式需要更多密码管理，但它是企业外部的观察程序节点的唯一选择。 不能将这些观察程序节点视为经过身份验证的受信任终结点。  <br/> |企业外部。  <br/> 在企业。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>配置观察程序节点以使用受信任的服务器身份验证
<a name="enable_synthetic_trans"> </a>

如果观察程序节点计算机位于外围网络中，则使用受信任服务器身份验证可大大减少管理任务，只需维护单个证书即可，而无需使用大量用户帐户密码。
  
若要配置受信任服务器身份验证，必须先创建受信任应用程序池来承载观察程序节点计算机。 创建受信任的应用程序池后，然后必须作为受信任应用程序运行的观察程序节点上配置综合事务。
  
> [!NOTE]
> 受信任的应用程序是应用程序被授予受信任的状态运行业务服务器 2015，Skype 的一部分，但不包含内置的产品。 受信任的状态意味着，应用程序将不要求进行身份验证每次运行。
  
若要创建受信任的应用程序池，为业务服务器管理外壳程序打开 Skype 和运行与以下类似的命令：
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 上面的命令中的参数的详细信息，从 Skype 业务服务器管理外壳提示符下键入： 
  
```
Get-Help New-CsTrustedApplicationPool -Full | more
```

在创建受信任的应用程序池之后，就可使用 **New-CsTrustedApplication** cmdlet 和类似下面的命令，将观察程序节点计算机配置为，将综合事务作为受信任的应用程序来运行。
  
```
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

在完成上述命令并创建受信任的应用程序之后，请运行 **Enable-CsTopology** cmdlet，以确保更改生效：
  
```
Enable-CsTopology
```

运行 Enable-CsTopology 后，重新启动计算机。
  
要验证已创建新的受信任应用程序，Skype 业务服务器管理外壳提示符处键入以下命令：
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>在观察程序节点上配置默认证书
<a name="enable_synthetic_trans"> </a>

使用 TrustedServer 身份验证每个观察者节点必须使用 Skype 业务服务器部署向导分配一个默认证书。 
  
若要分配默认证书：
  
1. 单击开始，单击所有程序、 都单击业务服务器 2015，Skype 和业务服务器部署向导然后都单击 Skype。 
    
2. 在商业服务器部署向导的 Skype，针对业务服务器系统中，单击安装或更新 Skype，然后单击运行请求的标题下，安装或分配证书。 
    
> [!NOTE]
> 如果禁用“运行”按钮，则您可能需要先单击“安装本地配置存储”下方的“运行”。 
  
请执行下列操作之一：
  
- 如果您已有一个可用作默认证书的证书，请单击证书向导中的“默认”，然后单击“分配”。按照证书分配向导中的步骤分配此证书。
    
- 如果您需要请求用作默认证书的证书，请单击“请求”，然后按照证书请求向导中的步骤进行操作以请求该证书。如果您使用 Web Server 证书的默认值，则您将获得可作为默认证书分配的证书。
    
## <a name="install-and-configure-a-watcher-node"></a>安装和配置观察程序节点
<a name="enable_synthetic_trans"> </a>

在观察程序节点计算机重新启动并配置证书之后，必须运行 Watchernode.msi 的文件。 （您必须运行 Watchernode.msi 的任何计算机上操作管理器代理文件和 Skype 业务服务器 2015年核心组件的安装位置。） 
  
若要安装和配置观察程序节点：
  
1. 通过单击开始，单击所有程序、 Skype 的业务服务器 2015，，然后都单击 Skype 业务服务器管理外壳程序打开业务服务器管理外壳 Skype。 
    
2. 在命令行管理程序中，键入以下命令，然后按 Enter（确保指定 Watchernode.msi 副本的实际路径）：
    
```
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> 您还可以从命令窗口运行 Watchernode.msi。若要打开命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。打开命令窗口后，键入与上面的步骤 2 所示的相同命令。 
  
> [!IMPORTANT]
> 在前面的命令中，名称/值对 Authentication=TrustedServer 区分大小写。必须完全按所示输入。例如，由于没有正确使用字母大小写，下面的命令将失败： 
  
```
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer 模式只能对位于外围网络内部的计算机使用。当观察程序节点以 TrustedServer 模式运行时，管理员无需在计算机上保留测试用户密码。
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>配置观察程序节点以使用协商
<a name="enable_synthetic_trans"> </a>

如果观察程序节点计算机位于外围网络之外，则必须遵循一个略有不同的过程来配置该观察程序节点运行综合事务：具体而言，不应创建受信任的应用程序池或受信任的应用程序。这意味着，您需要完成接下来的两个任务。
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>更新 RTC Local Read-Only Administrators 组中的成员身份

如果观察程序节点位于外围网络之外，则必须在观察程序节点上完成以下过程，将 Network Service 帐户添加到观察程序节点计算机上的 RTC Local Read-only Administrators 组：
  
1. 单击“开始”，右键单击“计算机”，然后单击“管理”。
    
2. 在“服务器管理器”中，展开“配置”，展开“本地用户和组”，然后单击“组”。
    
3. 在“组”窗格中，双击“RTC Local Read-only Administrators”。
    
4. 在“RTC Local Read-only Administrators 属性”对话框中，单击“添加”。
    
5. 在“选择用户、计算机、服务帐户或组”对话框中，单击“位置”。
    
6. 在“位置”对话框中，选择观察程序节点计算机的名称，然后单击“确定”。
    
7. 在“输入要选择的对象名称”框中，键入“Network Service”，然后单击“确定”。
    
8. 在“RTC Local Read-only Administrators 属性”对话框中，单击“确定”，然后关闭“服务器管理器”。
    
9. 重新启动观察程序节点计算机。
    
### <a name="install-the-watcher-node-configuration-files"></a>安装观察程序节点配置文件

下一步是运行文件 Watchernode.msi： 
  
1. 打开 Microsoft Skype for Business Server 2015 命令行管理程序。依次单击“开始”、“所有程序”和“Microsoft Skype for Business Server 2015”，然后单击“Skype for Business Server 命令行管理程序”。 
    
2. 在 Skype for Business Server 命令行管理程序中，键入以下命令，然后按 Enter（确保指定 Watchernode.msi 副本的实际路径）：
    
  ```
  c:\Tools\Watchernode.msi Authentication=Negotiate
  ```

> [!NOTE]
> 如前所述，还可以从命令窗口运行 Watchernode.msi。若要打开命令窗口，请单击“开始”****，右键单击“命令提示符”****，然后单击“以管理员身份运行”****。命令窗口打开后，键入上面的步骤 2 所示的相同命令。 
  
任何时候如果无法将观察程序节点设置为一个受信任应用程序池，都将使用协商模式。在此模式中，管理员需要管理观察程序节点上的测试用户密码。
  

