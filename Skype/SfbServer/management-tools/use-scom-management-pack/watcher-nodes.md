---
title: 如何安装和配置观察程序节点
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 如何为综合事务安装和配置观察程序Skype for Business Server节点。
ms.openlocfilehash: aca051b005c3ec9a901c5366a7788af5e95d06f0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766210"
---
# <a name="how-to-install-and-configure-watcher-nodes"></a>如何安装和配置观察程序节点
 
**摘要：** 为综合事务安装和配置观察Skype for Business Server节点。
  
观察程序节点是定期运行综合Skype for Business Server的计算机。 综合事务Windows PowerShell cmdlet，用于验证关键用户方案（如登录或交换即时消息的能力）是否正常工作。 对于 Skype for Business Server 2015，System Center Operations Manager 可以运行下表中所示的综合事务，其中包括三种综合事务类型：
  
- **默认** 默认情况下，观察程序节点运行的综合事务。 创建新的观察程序节点时，可以指定节点将运行的综合事务。  (这是 New-CsWatcherNodeConfiguration cmdlet.) 使用的 Tests 参数的用途。如果在创建观察程序节点时不使用 Tests 参数，则它将自动运行所有默认综合事务，并且不会运行任何非默认综合事务。 这意味着，例如，观察程序节点将配置为运行 Test-CsAddressBookService 测试，但不能配置为运行 Test-CsExumConnectivity 测试。
    
- **非默认** 默认情况下，观察程序节点不运行的测试。  (有关详细信息，请参阅 Default type.) 但是，可以启用观察程序节点来运行任何非默认综合事务。 可以使用 New-CsWatcherNodeConfiguration cmdlet (创建观察程序节点或创建观察程序) 后随时创建观察程序节点。 请注意，许多非默认综合事务需要额外的设置步骤。 有关这些步骤的更多详细信息，请参阅 [特殊设置说明综合事务](test-users-and-settings.md#special_synthetictrans)。
    
- **扩展** 特殊类型的非默认综合事务。 与其他综合事务不同，扩展测试可在每次通过的情况下运行多次。 这可用于验证行为，例如多个公用电话交换网 (PSTN) 池的语音路由。 只需将扩展测试的多个实例添加到观察程序节点，就可以进行此配置。
    
有关向观察程序节点添加其他综合事务的过程的详细信息，请参阅将观察程序 [节点配置为运行综合事务](watcher-nodes.md#enable_synthetic_trans)。 您还可以使用命令行管理Skype for Business Server从观察程序节点中删除综合事务。
  
可用于观察程序节点的综合事务包括：
  
|**Cmdlet 名称（测试名称）**|**说明**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |确认用户能够查找不在联系人列表中的用户。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |确认用户能够通过 HTTP 查找不在联系人列表中的用户。  <br/> |
|Test-CsAVConference (AvConference)   <br/> |确保用户能够创建和参与音频/视频会议。  <br/> |
|Test-CsGroupIM (IM 会议)   <br/> |确保用户能够在会议中发送即时消息并且可参与三个或三个以上的人员组成的即时消息对话。  <br/> |
|Test-CsIM (P2P IM)   <br/> |确保用户能够发送对等即时消息。  <br/> |
|Test-CsP2PAV (P2PAV)   <br/> |确保用户能够发出对等音频呼叫（仅信号）。  <br/> |
|Test-CsPresence (Presence)  <br/> |确认用户能够查看其他用户状态。  <br/> |
|Test-CsRegistration (Registration)  <br/> |确认用户能够登录Skype for Business。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |确保用户能够向企业外部人员发出呼叫以及接收其发出的呼叫（PSTN 号码）。  <br/> |
|Test-CsASConference (ASConference)   <br/> |确认用户能够创建和参与应用程序共享会议。  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)   <br/> |确认音频视频边缘服务器能够接受对等呼叫和电话会议的连接。  <br/> |
|Test-CsDataConference (DataConference)   <br/> |确认用户可以参加包含白板 (投票等活动的联机会议的数据) 。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)   <br/> |确认用户能够拨打电话号码以加入会议。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)   <br/> |确认用户能够拨打电话号码以加入会议。  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)   <br/> |确认用户可以连接到统一消息Exchange UM (um) 。  <br/> |
|Test-CsGroupIM -TestJoinLauncher (JoinLauncher)   <br/> |确认用户能够通过 Web 地址链接 (和加入安排的会议) 。  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)   <br/> |确保移动设备用户能够注册和发送即时消息。  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)   <br/> |确认视频互操作服务器已启动，并且可以通过视频 SIP 中继处理传入连接。  <br/> **注意：** 2019 年 3 月不再提供对旧版移动客户端Skype for Business Server MCX。 |
|Test-CsPersistentChatMessage (PersistentChatMessage)   <br/> |确认用户可以使用持久聊天服务交换消息。  <br/> |
|Test-CsUcwaConference (UcwaConference)   <br/> |确认用户可以通过 Web 加入会议。  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)   <br/> |确保可通过统一的联系人存储库访问用户的联系人。 统一联系人存储为用户提供了一种维护一组联系人的方法，这些联系人可通过使用 Skype for Business Server 2015、Outlook 消息传递和协作客户端和/或 Outlook Web Access 访问。  <br/> |
|Test-CsXmppIM (XmppIM)   <br/> |确认可以通过 XMPP 网关的可扩展消息传递和状态协议 (即时消息) 消息。  <br/> XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。  |

无需安装观察程序节点，就无需System Center Operations Manager。 如果未安装这些节点，则只要出现问题，您仍可以从 Skype for Business Server 2015 组件获取实时警报。  (组件和用户管理包不使用观察程序节点。) 但是，如果要使用主动监控管理包监视端到端方案，则观察程序节点是必需的。
  
> [!NOTE]
> 管理员还可以手动运行综合事务，而无需使用或安装 Operations Manager。 综合事务可能会占用大量计算机Skype for Business Server处理器时间，具体取决于部署部署的规模。 因此，建议使用专用计算机作为观察程序节点。 例如，不应将前端Skype for Business Server配置为充当观察程序节点。 观察程序节点应满足与拓扑中任何其他计算机相同的基本Skype for Business Server要求。 
  
> [!NOTE]
> 旧的 Lync Server 2013 观察程序节点不能与 Skype for Business Server 2015 观察程序节点并并在同一计算机上，因为 Lync Server 2013 和 Skype for Business Server 2015 的核心系统文件不能安装在同一计算机上。 但是，Skype for Business Server 2015 观察程序节点可以同时监视 Skype for Business Server 2015 和 Lync Server 2013。 两种产品版本均支持默认综合事务。 
  
Lync Server 2013 观察程序节点可以部署在企业内部或外部，以帮助验证：
  
- 至企业内部用户的池的连接。
    
- 通过外围网络为在企业外部工作的远程用户建立连接。
    
- 至分支机构装置的连接。
    
- 与企业内部和通过外围网络连接到 Lync Server 2013。
    
为了帮助简化管理，企业内外提供了不同的身份验证选项。 有关详细信息，请参阅 [将观察程序节点配置为运行综合事务](watcher-nodes.md#enable_synthetic_trans)。
  
若要将计算机配置为充当观察程序节点，必须先完成以下先决条件： 
  
- 安装System Center Operations Manager 并导入 Skype for Business Server 2015 管理包。 您还必须首先验证观察程序节点计算机是否满足安装 2015 Skype for Business Server的先决条件。
    
- 在观察程序节点计算机上安装以下项目：
    
  - 4.5 .NET Framework的完整版本
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
满足先决条件后，可以按照以下步骤配置观察程序节点：
  
1. 在观察Skype for Business Server计算机上安装 2015 核心文件。
    
2. 在System Center节点计算机上安装 Operations Manager 代理。
    
3. 运行Watchernode.msi可执行文件。
    
4. 使用 **New-CsWatcherNodeConfiguration** cmdlet 配置观察程序节点将使用的测试用户帐户。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>安装 Skype for Business Server 2015 核心文件和 RTCLocal 数据库

若要在计算机上安装 Skype for Business Server 2015 核心文件，请完成以下过程。 在您安装核心文件时，会自动安装 RTCLocal 数据库。 请注意，无需在观察程序节点SQL Server安装程序。 SQL Server Express将自动安装。
  
若要安装 Skype for Business Server 2015 核心文件和 RTCLocal 数据库：
  
1. 在观察程序节点计算机上，依次单击“开始”、“所有程序”和“附件”，再右键单击“命令提示符”，然后单击“以管理员身份运行”。
    
2. 在控制台窗口中，键入以下命令并按 Enter。 请务必输入 Skype for Business Server 安装文件的适当路径：D:\Setup.exe /BootstrapLocalMgmt 若要验证核心 Skype for Business Server 组件是否成功安装，请单击"开始"，单击"所有程序"，然后单击 **"Skype for Business Server 2015"**，然后单击"Skype for Business Server **命令行管理程序"。** 在命令行Skype for Business Server命令行管理程序中，键入Windows PowerShell命令并按 Enter：
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 首次运行此命令时，不会返回任何数据，因为您尚未配置任何观察程序节点计算机。 如果命令在未返回错误的情况下运行，您可以假定Skype for Business Server成功完成安装程序。 
  
如果您的观察程序节点计算机位于外围网络内部，您可以运行以下命令来验证 Skype for Business Server 2015 的安装：
  
Get-CsPinPolicyYou接收类似信息，具体取决于配置为在组织使用的 PIN 策略的数量：
  
标识：全局
  
说明：
  
MinPasswordLength ： 5
  
PINHistoryCount ： 0
  
AllowCommonPatterns ： False
  
PINLifetime ： 0
  
MaximumLogonAttempts ：
  
如果看到有关 PIN 策略的信息，则已成功安装核心组件。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>在观察程序节点上安装操作管理器代理文件

与Skype for Business Server组件警报的设置类似，Skype for Business Server 2015 观察程序节点System Center安装 Operations Manager 代理文件。 这使综合事务能够运行，并可以向 Operations Manager 根管理System Center报告警报。
  
若要安装代理文件，请按照 Configure the [Skype for Business Server computers that will be monitored 中列出的过程操作](configure-computers-to-monitor.md)。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>配置观察程序节点以运行综合事务
<a name="enable_synthetic_trans"> </a>

安装System Center管理器代理文件后，您必须配置观察程序节点本身。 你为此执行的步骤将有所不同，具体取决于观察程序节点计算机是位于外围网络内部还是位于外围网络之外。 
  
配置观察程序节点时，还必须选择该节点要采用的身份验证方法类型。 Skype for Business Server 2015，您可以选择以下两种身份验证方法之一：受信任的服务器或凭据身份验证。 下表显示了这两种方法之间的差异：
  
|&nbsp;|**说明**|**支持的位置**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |使用证书可模拟内部服务器并绕过身份验证质询。  <br/> 对于喜欢管理单个证书（而不是在每个观察程序节点上管理许多用户密码）的管理员很有用。  <br/> |企业内部。  <br/> 使用此方法，观察程序节点必须与要监视的池位于同一域中。 如果观察程序节点和池位于不同的域中，请改为使用凭据身份验证。  <br/> |
|协商  <br/> |将用户名和密码安全地存储在每个观察程序节点的 Windows 凭据管理器中。  <br/> 此模式需要更多的密码管理，但是企业外部观察程序节点的唯一选项。 不能将这些观察程序节点视为经过身份验证的受信任终结点。  <br/> |企业外部。  <br/> 企业内部。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>配置观察程序节点以使用受信任的服务器身份验证
<a name="enable_synthetic_trans"> </a>

如果您的观察程序节点计算机位于外围网络中，则使用受信任服务器身份验证可通过维护单个证书（而不是使用大量用户帐户密码）大大减少管理任务。
  
若要配置受信任服务器身份验证，必须先创建受信任应用程序池以承载观察程序节点计算机。 创建受信任应用程序后，应用程序池该观察程序节点上的综合事务配置为作为受信任应用程序运行。
  
> [!NOTE]
> 受信任应用程序是获得受信任的状态以作为 Skype for Business Server 2015 的一部分运行的应用程序，但不是产品的内置部分。 受信任的状态意味着，每次运行该应用程序时，将不会要求其进行身份验证。
  
若要创建受信任应用程序池，请打开命令行Skype for Business Server命令行管理程序并运行类似以下的命令：
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 有关上述命令中的参数的详细信息，请从命令行管理程序提示符Skype for Business Server以下内容： 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

创建受信任应用程序池后，可以使用 **New-CsTrustedApplication** cmdlet 和类似如下的命令将观察程序节点计算机配置为将综合事务作为受信任应用程序运行：
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

此命令完成并创建受信任应用程序后，必须运行 **Enable-CsTopology** cmdlet 以确保更改生效：
  
```PowerShell
Enable-CsTopology
```

观察程序节点计算机帐户需要能够查询 CMS 以查询某些综合事务。 若要允许此功能，将观察程序节点的计算机帐户添加到 RTCUniversalReadOnlyAdmins 安全组。 AD 复制发生后，重新启动计算机。
  
若要验证是否创建了新的受信任应用程序，在命令行管理程序提示符Skype for Business Server键入以下内容：
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>在观察程序节点上配置默认证书
<a name="enable_synthetic_trans"> </a>

使用 TrustedServer 身份验证的每个观察程序节点都必须具有使用"部署向导"分配的默认Skype for Business Server证书。 
  
分配默认证书：
  
1. 单击"开始"，单击"所有程序"，Skype for Business Server 2015"，然后单击"Skype for Business Server向导"。 
    
2. 在"Skype for Business Server向导"中，单击"安装或更新 Skype for Business Server 系统"，然后单击标题"请求、安装或分配证书"下的"运行"。 
    
> [!NOTE]
> 如果禁用“运行”按钮，则您可能需要先单击“安装本地配置存储”下方的“运行”。 
  
执行下列操作之一：
  
- 如果已有可用作默认证书的证书，请单击证书向导中的"默认"，然后单击"分配"。 按照证书分配向导中的步骤进行操作以分配此证书。
    
- 如果需要请求证书以使用默认证书，请单击"请求"，然后按照证书请求向导中的步骤请求该证书。 如果您使用 Web Server 证书的默认值，则您将获得可作为默认证书分配的证书。
    
## <a name="install-and-configure-a-watcher-node"></a>安装和配置观察程序节点
<a name="enable_synthetic_trans"> </a>

重新启动观察程序节点计算机并配置证书后，必须运行该文件Watchernode.msi。  (必须在Watchernode.msi安装 Operations Manager 代理文件和 Skype for Business Server 2015 核心组件的任何计算机上运行)  
  
安装和配置观察程序节点：
  
1. 打开"Skype for Business Server命令行管理程序"，方法是单击"开始"，单击"所有程序"，单击"Skype for Business Server 2015"，然后单击"Skype for Business Server命令行管理程序"。 
    
2. 在命令行管理程序中，键入以下命令，然后按 Enter (请确保并指定副本的实际Watchernode.msi) ：
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> 您还可以从命令Watchernode.msi n。 若要打开命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。 命令窗口打开后，键入上述步骤 2 中显示的相同命令。 
  
> [!IMPORTANT]
> 在上一个命令中，名称/值对 Authentication=TrustedServer 区分大小写。 必须完全按照所示键入它。 例如，此命令将失败，因为它不使用正确的字母大小写： 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer 模式只能用于外围网络内部的计算机。 当观察程序节点在 TrustedServer 模式下运行时，管理员不需要在计算机上维护测试用户密码。
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>配置观察程序节点以使用协商
<a name="enable_synthetic_trans"> </a>

如果您的观察程序节点计算机位于外围网络之外，则必须按照略有不同的过程来配置该观察程序节点以运行综合事务：特别是，不应创建受信任的 应用程序池 或受信任应用程序。 这意味着您需要完成接下来的两个任务。
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>更新 RTC Local Read-Only Administrators 组的成员身份

如果您的观察程序节点位于外围网络之外，则必须通过完成观察程序节点上的以下过程，将 Network Service 帐户添加到观察程序节点计算机的 RTC Local Read-only 管理员组：
  
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

下一步是运行文件Watchernode.msi： 
  
1. 打开 Microsoft Skype for Business Server 2015 命令行管理程序。 单击"开始"，单击"所有程序"，单击"Microsoft Skype for Business Server 2015"，然后单击"Skype for Business Server命令行管理程序"。 
    
2. 在Skype for Business Server命令行管理程序中，键入以下命令，然后按 Enter (以确保指定您的命令行管理程序副本的实际Watchernode.msi) ：
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 如前所述，Watchernode.msi也可从命令窗口运行。 若要打开命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。 命令窗口打开后，键入上述步骤 2 中显示的相同命令。 
  
任何时候如果无法将观察程序节点设置为一个受信任应用程序池，都将使用协商模式。 在此模式中，管理员需要管理观察程序节点上的测试用户密码。
  

