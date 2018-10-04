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
description: 摘要： 安装和配置观察程序节点的 Skype Business Server 综合事务。
ms.openlocfilehash: 6719826515954290f30eac272f638b846f45142a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375984"
---
# <a name="install-and-configure-watcher-nodes"></a>安装和配置观察程序节点
 
**摘要：** 安装和配置观察程序节点的 Skype Business Server 综合事务。
  
观察程序节点是定期运行的业务服务器综合事务的 Skype 的计算机。 综合事务是验证关键用户方案（如能否登录或交换即时消息）是否正常起作用的 Windows PowerShell cmdlet。 对于业务服务器 2015年的 Skype，System Center Operations Manager 可以运行下表中，其中包括三种综合事务类型中所示的综合事务：
  
- **默认值**默认情况下运行观察程序节点的综合事务。 创建新的观察程序节点时，可以指定该节点将运行哪些综合事务。 （这是通过 New-cswatchernodeconfiguration cmdlet 使用的测试参数的用途）。如果您不使用 Tests 参数创建观察程序节点时，它将自动运行所有默认综合事务，并将不会都运行任何非默认综合事务。 这意味着，例如，观察程序节点将配置为运行 Test-CsAddressBookService 测试，但不会配置为运行 Test-CsExumConnectivity 测试。
    
- **非默认**默认情况下不运行观察程序节点的测试。 （有关详细信息，请参阅默认类型的说明）。但是，可以启用观察程序节点要运行任何非默认综合事务。 当您创建观察程序节点 （通过使用 New-cswatchernodeconfiguration cmdlet），或已创建观察程序节点后的随时时，您可以这样做。 请注意，多个非默认综合事务需要额外的安装步骤。 有关这些步骤的详细信息，请参阅综合事务的特殊设置说明。 有关这些步骤的详细信息，请参阅[综合事务的特殊设置说明](test-users-and-settings.md#special_synthetictrans)。
    
- **扩展**一种非默认综合事务的特殊类型。 与其他综合事务，不同扩展测试可多次运行在每个过程。 验证行为，例如，池中的多个公用电话交换网 (pstn) 语音路由时，这很有用。 您可以配置此只需通过观察程序节点到添加的扩展测试的多个实例。
    
有关向观察程序节点添加其他综合事务的过程的详细信息，请参阅[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)。 您可以使用 Skype 的业务 Server 命令行管理程序以删除观察程序节点的综合事务。
  
可用于观察程序节点的综合事务包括：
  
|**Cmdlet 名称（测试名称）**|**说明**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |确保用户能够查找不在其联系人列表中的用户。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |确保用户能够查找不在其联系人列表中通过 HTTP 的用户。  <br/> |
|Test-csavconference (AvConference)  <br/> |确认用户能够创建和参与音频/视频会议。  <br/> |
|Test-CsGroupIM (IM Conferencing)  <br/> |确认用户能够在会议中发送即时消息并且可参与三个或三个以上的人员组成的即时消息对话。  <br/> |
|Test-CsIM (P2P IM)  <br/> |确认用户能够发送对等即时消息。  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |确认用户能够发出对等音频呼叫（仅信号）。  <br/> |
|Test-CsPresence (Presence)  <br/> |确保用户能够查看其他用户的状态。  <br/> |
|Test-CsRegistration (Registration)  <br/> |确保用户能够登录到 for Business 的 Skype。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |确认用户能够向企业外部人员发出呼叫以及接收其发出的呼叫（PSTN 号码）。  <br/> |
|Test-CsASConference (ASConference)  <br/> |确认用户能够创建和参与应用程序共享会议。  <br/> |
|Test-csavedgeconnectivity (AVEdgeConnectivity)  <br/> |确认音频视频边缘服务器能够接受对等呼叫和会议呼叫的连接。  <br/> |
|Test-csdataconference (DataConference)  <br/> |确认用户可参与数据协作会议（包含白板和投票等活动的联机会议）。  <br/> |
|Test-csdialinconferencing (DialinConferencing)  <br/> |确认用户能够拨打电话号码加入会议。  <br/> |
|Test-csdialinconferencing (DialinConferencing)  <br/> |确认用户能够拨打电话号码加入会议。  <br/> |
|Test-csexumconnectivity (ExumConnectivity)  <br/> |确认用户可以连接到 Exchange 统一消息 (UM)。  <br/> |
|Test-csgroupim TestJoinLauncher (JoinLauncher)  <br/> |确认用户能够创建并加入计划的会议（通过 Web 地址链接）。  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |确认移动设备用户能够注册和发送即时消息。  <br/> |
|测试 CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |确认视频互操作服务器已启动，可以通过视频的 SIP 中继处理传入连接。  <br/> **注意：** MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。 |
|Test-cspersistentchatmessage (PersistentChatMessage)  <br/> |确认用户可使用持久聊天服务交换消息。  <br/> |
|Test-csucwaconference (UcwaConference)  <br/> |确认用户可通过 Web 加入会议。  <br/> |
|Test-csunifiedcontactstore (UnifiedContactStore)  <br/> |确认可通过统一的联系人存储库访问用户的联系人。 统一联系人存储库提供了一种方法来维护一组可访问的业务服务器 2015年、 Outlook 消息和协作客户端和/或 Outlook Web Access 使用 Skype 联系人的用户。  <br/> |
|Test-csxmppim (XmppIM)  <br/> |确认可通过可扩展消息传递和状态协议 (XMPP) 网关发送即时消息。  <br/> XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。  |

不需要安装观察程序节点以使用 System Center Operations Manager。 如果未安装这些节点，您仍可以获取实时通知从 Skype 业务服务器 2015年组件时出现问题。 （的组件和用户管理包不使用观察程序节点。）但是，观察程序节点是必需的如果您想要使用的主动监控管理包监视的端到端方案。
  
> [!NOTE]
> 管理员还可手动运行综合事务，而无需使用或安装 Operations Manager。 根据您 Skype Business Server 部署的大小，综合事务可以使用大量的计算机内存和处理器时间。 因此，建议您使用专用计算机作为观察程序节点。 例如，不应该配置 Business Server 前端服务器充当观察程序节点的 Skype。 观察程序节点应满足基本硬件要求与任何其他计算机中的企业服务器拓扑您 Skype 相同。 
  
> [!NOTE]
> 因为不能在同一台计算机上安装 Lync Server 2013 和业务服务器 2015年的 Skype 的核心系统文件，旧的 Lync Server 2013 观察程序节点不能并置为 Skype 业务服务器 2015年观察程序节点的相同计算机上。 但是，业务服务器 2015年观察程序节点的 Skype 可以同时监视 Skype 业务服务器 2015年和 Lync Server 2013。 默认综合事务同时支持两种产品版本。 
  
内部或外部企业以帮助验证，则可能部署 Lync Server 2013 观察程序节点：
  
- 至企业内部用户的池的连接。
    
- 通过在企业外部工作的远程用户的外围网络的连接。
    
- 至分支机构装置的连接。
    
- 连接到 Lync Server 2013 企业内部和通过外围网络。
    
为了帮助简化管理，企业内部和外部有不同的身份验证选项。有关详细信息，请参阅[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)。
  
为了将计算机配置为观察程序节点，必须先完成以下前提任务： 
  
- 安装 System Center Operations Manager 和导入业务服务器 2015年管理包的 Skype。 您必须还首先验证观察程序节点计算机满足所有先决条件安装业务服务器 2015 Skype。
    
- 在观察程序节点上安装以下项目：
    
  - 完整版的.NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
在满足先决条件后，可按下面的步骤配置观察程序节点：
  
1. 安装观察程序节点计算机上的业务服务器 2015年核心文件 Skype。
    
2. 在观察程序节点计算机上安装 System Center Operations Manager 代理。
    
3. 运行 Watchernode.msi 可执行文件。
    
4. 使用 **New-CsWatcherNodeConfiguration** cmdlet 配置观察程序节点要采用的测试用户帐户。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>安装 Skype for Business Server 2015 核心文件和 RTCLocal 数据库

若要安装的计算机上的业务服务器 2015年核心文件 Skype，完成以下过程。 当您安装的核心文件时，将自动安装 RTCLocal 数据库。 请注意，您不需要观察程序节点上安装 SQL Server。 SQL Server Express 将会自动安装。
  
安装 Business Server 2015 核心文件和 RTCLocal 数据库 Skype:
  
1. 在观察程序节点计算机上，依次单击“开始”、“所有程序”和“附件”，再右键单击“命令提示符”，然后单击“以管理员身份运行”。
    
2. 在控制台窗口中，键入以下命令，再按 Enter。 确保输入您 Skype Business Server 安装程序文件的相应路径： D:\Setup.exe /BootstrapLocalMgmtTo 验证是否成功安装核心 Skype 业务服务器组件，单击**开始**，单击**所有程序**单击**业务服务器 2015年的 Skype**，，然后单击**业务 Server Management Shell 的 Skype**。 中的业务 Server 命令行管理程序 Skype，键入以下 Windows PowerShell 命令并按 ENTER:
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 首次运行此命令时，不会返回任何数据，因为您尚未配置任何观察程序节点计算机。 如果不返回出错的情况下运行该命令，可以假定 Skype 业务服务器安装已成功完成。 
  
如果您的观察程序节点计算机位于您的外围网络内部，则可以运行以下命令来验证 Skype for Business Server 2015 的安装：
  
Get CsPinPolicyYou 会收到类似于以下，具体取决于数配置为在组织中使用的 PIN 策略的信息：
  
标识： 全局
  
说明：
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: False
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
如果看到有关 PIN 策略的信息，表明核心组件已安装成功。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>在观察程序节点上安装 Operation Manager 代理文件

类似于业务服务器安装程序报告组件通知 Skype，业务服务器 2015年观察程序节点的 Skype 需要安装 System Center Operations Manager 代理文件。 这样的综合事务，要运行和通知要报告给 System Center Operations Manager 根管理服务器。
  
若要安装代理文件，请按照[配置将受监控的企业服务器计算机的 Skype](configure-computers-to-monitor.md)中列出的过程。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>将观察程序节点配置为运行综合事务
<a name="enable_synthetic_trans"> </a>

安装了 System Center Operations Manager 代理文件后，您必须配置观察程序节点本身。 配置步骤将因观察程序节点计算机位于外围网络内部还是外部而有所不同。 
  
配置观察程序节点时，还必须选择该节点要采用的身份验证方法类型。 Skype 的业务服务器 2015年让您能够选择两种身份验证方法之一： 受信任的服务器或凭据身份验证。 下表显示了这两种方法间的差异：
  
||**说明**|**支持的位置**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |使用证书可模拟内部服务器并绕过身份验证质询。  <br/> 这对于喜欢在每个观察程序节点管理单个证书而不是多个用户密码的管理员来说很有用。  <br/> |企业内部。  <br/> 采用这种方法时，观察程序节点必须与要监控的池位于同一个域中。如果观察程序节点与池在不同的域中，请改用凭据身份验证。  <br/> |
|Negotiate  <br/> |将用户名和密码安全地存储在每个观察程序节点的 Windows 凭据管理器中。  <br/> 此模式需要更多密码管理，但它是企业外部的观察程序节点的唯一选择。不能将这些观察程序节点视为经过身份验证的受信任终结点。  <br/> |企业外部。  <br/> 企业内部。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>配置观察程序节点以使用受信任的服务器身份验证
<a name="enable_synthetic_trans"> </a>

如果观察程序节点计算机位于外围网络中，则使用受信任服务器身份验证可大大减少管理任务，只需维护单个证书即可，而无需使用大量用户帐户密码。
  
若要配置受信任服务器身份验证，必须先创建受信任应用程序池来承载观察程序节点计算机。 您已创建的受信任应用程序池后，然后必须在受信任应用程序以运行该观察程序节点配置综合事务。
  
> [!NOTE]
> 受信任的应用程序是授予受信任的状态运行业务服务器 2015 Skype 的一部分，但不是内置一部分的产品的应用程序。 受信任状态意味着，每次运行该应用程序时，将不会要求其进行身份验证。
  
若要创建受信任应用程序池，打开 Skype 业务 Server 命令行管理程序，并运行类似于以下命令：
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 有关上述命令中参数的详细信息，键入从业务 Server 命令行管理程序提示符 Skype 以下内容： 
  
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
  
若要验证已创建新的受信任应用程序，在 Skype 的业务 Server 命令行管理程序提示符处键入以下内容：
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>在观察程序节点上配置默认证书
<a name="enable_synthetic_trans"> </a>

使用 TrustedServer 身份验证每个观察程序节点必须使用适用于业务 Server 部署向导 Skype 分配一个默认证书。 
  
若要分配默认证书：
  
1. 单击开始、 单击所有程序、 都单击业务服务器 2015 Skype，然后都单击 Skype 业务 Server 部署向导。 
    
2. 在业务 Server 部署向导的 Skype，单击安装或更新 Skype 业务 Server 系统，然后单击运行范畴请求、 安装或分配证书。 
    
> [!NOTE]
> 如果禁用“运行”按钮，则您可能需要先单击“安装本地配置存储”下方的“运行”。 
  
请执行下列操作之一：
  
- 如果您已有一个可用作默认证书的证书，请单击证书向导中的“默认”，然后单击“分配”。按照证书分配向导中的步骤分配此证书。
    
- 如果您需要请求用作默认证书的证书，请单击“请求”，然后按照证书请求向导中的步骤进行操作以请求该证书。如果您使用 Web Server 证书的默认值，则您将获得可作为默认证书分配的证书。
    
## <a name="install-and-configure-a-watcher-node"></a>安装和配置观察程序节点
<a name="enable_synthetic_trans"> </a>

您已重新启动观察程序节点计算机并配置证书之后，您必须运行 Watchernode.msi 文件。 （必须运行 Watchernode.msi 的任何计算机上安装 Operations Manager 代理文件和业务服务器 2015年核心组件的 Skype。） 
  
若要安装和配置观察程序节点：
  
1. 通过单击开始，单击所有程序、 Skype 的业务服务器 2015年，然后都单击的业务 Server Management Shell Skype 业务 Server 命令行管理程序打开 Skype。 
    
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
  

