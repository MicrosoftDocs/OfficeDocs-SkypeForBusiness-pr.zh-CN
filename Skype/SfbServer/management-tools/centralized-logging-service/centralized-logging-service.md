---
title: Skype for Business 2015 中的集中日志记录服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 摘要：了解 Skype for Business Server 2015 中的集中日志记录服务的服务组件和配置设置。
ms.openlocfilehash: e65ea3a0a5ed4d86591b630df6d84e436a7efd66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221886"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Skype for Business 2015 中的集中日志记录服务
 
**摘要：** 了解 Skype for Business Server 2015 中的集中日志记录服务的服务组件和配置设置。
  
集中日志记录服务可以： 
  
- 在一个或多个计算机和池上启动或停止日志记录，其中包含一个来自中心位置的单个命令。
    
- 在一个或多个计算机和池上搜索日志。 您可以定制搜索以返回所有计算机上的所有日志，或返回更简明的结果。
    
- 按如下方式配置日志记录会话：
    
  - 定义一个**方案**，或使用默认方案。 集中日志记录服务中的方案由作用域（全局或站点）、方案名称（用于确定方案的用途）和一个或多个提供程序组成。 您可以在任意给定时间在计算机上运行默认方案和一个定义的方案。
    
  - 使用现有提供程序 或创建新提供程序。 Aprovider 定义日志记录会话收集的内容、详细程度、要跟踪的组件以及要应用的标志。
    
    > [!TIP]
    >  如果您熟悉 OCSLogger，则 termproviders 指的是**组件**的集合（例如，S4、SIPStack）、**日志记录类型**（例如，WPP、EventLog 或 IIS 日志文件）、**跟踪级别**（例如，All、verbose、debug）和**flags** （例如，TF_COMPONENT、TF_DIAG）。 这些项在提供程序（Windows PowerShell 变量）中定义并传递到集中日志记录服务命令。
  
  - 配置特定计算机和池的日志。
    
  - 从 "选项"**网站**中定义日志记录会话的作用域（仅在该站点中的计算机上运行日志捕获）或**全局**（在部署中的所有计算机上运行日志捕获）。
    
集中日志记录服务是一种功能强大的故障排除工具，可解决从根本原因分析到性能问题的大或小问题。 所有示例都是使用 Skype for Business Server 命令行管理程序显示的。 帮助是通过工具本身为命令行工具提供的，但您可以从命令行执行的一组有限的函数。 通过使用 Skype for Business Server 命令行管理程序，您可以访问更大和更多可配置的功能集，因此应始终为您的第一个选择。 
  
## <a name="logging-service-components"></a>日志记录服务组件

 集中日志记录服务在部署中的所有服务器上运行，由以下代理和服务组成：
  
- 集中日志记录服务代理 ClsAgent 在部署了 Skype for Business Server 的每台计算机上运行。 它侦听（在端口**TCP 50001-50003**）上来自 WCF 的 ClsController 命令，并将响应发送回控制器。 它管理日志会话（启动/停止/更新）和搜索日志。 它还执行日志存档和清除等日常操作。 
    
- 集中日志记录服务控制器 Cmdlet Skype for Business Server 命令行管理程序向 ClsAgent 发送启动、停止、刷新和搜索命令。 当发送搜索命令时，生成的日志将返回到 ClsControllerLib 并进行聚合。 控制器将命令发送给代理，接收这些命令的状态，并管理从搜索范围内任何计算机上的所有代理返回的搜索日志文件数据，并将日志数据聚合到有意义的已排序输出集。 以下主题中的信息重点介绍了如何使用 Skype for Business Server 命令行管理程序。
    
**ClsController 到 ClsAgent 的通信**

![CLSController 和 CLSAgent 之间的关系。](../../media/Ops_CLS_Architecture.jpg)
  
您可以使用 Windows Server 命令行界面或 Skype for Business Server 命令行管理程序发出命令。 命令在您登录到的计算机上执行，并将其发送到您的部署中的 ClsAgent 本地或其他计算机和池。
  
ClsAgent 维护全部的索引文件。在本地计算机上缓存文件。 ClsAgent 将其分配给它们，以便在选项 80 CacheFileLocalFolders 定义的各个卷上均匀分布这些卷（即，本地缓存位置和百分比可使用**new-csclsconfiguration** cmdlet 进行配置）。 ClsAgent 还负责将旧的缓存事件跟踪日志（.etl）文件从本地计算机中注销。 两周后（即使用**new-csclsconfiguration** cmdlet 可配置的时间范围），这些文件将被复制到文件共享，并从本地计算机中删除。 有关详细信息，请参阅[new-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)。 收到搜索请求时，搜索条件将用于选择一组缓存的 .etl 文件，以根据代理维护的索引中的值执行搜索。
  
> [!NOTE]
> 从本地计算机移动到文件共享的文件可以通过 ClsAgent 进行搜索。 一旦 ClsAgent 将文件移动到文件共享，ClsAgent 将不会维护文件的老化和删除。 应定义管理任务以监视文件共享中的文件大小，并将其删除或存档。 
  
可以使用各种工具读取和分析生成的日志文件，其中包括**snooper.exe**和可读取文本文件的任何工具（如**notepad.exe**）。 Snooper.exe 是 Skype for Business Server 2015 调试工具的一部分，可用作[Web 下载](https://go.microsoft.com/fwlink/p/?LinkId=285257)。
  
与 OCSLogger 一样，集中日志记录服务有多个要跟踪的组件，并提供了选择标志的选项，如 TF_COMPONENT 和 TF_DIAG。 集中日志记录服务还保留 OCSLogger 的日志记录级别选项。
  
在命令行 ClsController 上使用 Skype for Business Server 命令行管理程序的最重要的优势在于，您可以使用针对问题空间、自定义标记和日志记录级别的选定提供程序来配置和定义新方案。 可用于 ClsController 的方案仅限于为可执行文件定义的方案。
  
在以前的版本中，提供了 OCSLogger，以使管理员和支持人员能够从部署中的计算机收集跟踪文件。 OCSLogger 对于其所有优势而言都存在缺陷。 在给定时间，您只能在一台计算机上收集日志。 您可以通过使用 OCSLogger 的单独副本登录到多台计算机，但最终要使用多个日志，而不是聚合结果的简单方法。
  
当用户请求日志搜索时，ClsController 将确定要将请求发送到的计算机（即，根据所选的方案）。 它还确定是否需要将搜索发送到保存的 .etl 文件所在的文件共享。 当搜索结果返回到 ClsController 时，该控制器会将结果合并到一个显示给用户的单个按时间排序的结果集。 用户可以将搜索结果保存到本地计算机，以供进一步分析。
  
启动日志记录会话时，将指定与您尝试解决的问题相关的方案。 您可以随时运行两个方案。 这两种方案中的一种应是 AlwaysOn 方案。 顾名思义，它应始终在您的部署中运行，并收集所有计算机、池和组件的信息。
  
> [!IMPORTANT]
> 默认情况下，AlwaysOn 方案未在您的部署中运行。 您必须显式启动方案。 启动后，它将继续运行，直到显式停止，并且运行状态将在计算机重新启动后保持。 有关启动和停止方案的详细信息，请参阅[在 Skype For Business Server 2015 中启动或停止 CLS 日志捕获](start-or-stop-log-capture.md)。 
  
出现问题时，请启动与报告的问题相关的第二个方案。 重现该问题，并停止第二个方案的日志记录。 相对于报告的问题开始进行日志搜索。 日志的聚合集合将生成一个日志文件，其中包含来自网站中的所有计算机或部署全局范围的跟踪消息。 如果搜索返回的数据多于您可以 feasibly 分析的数据（通常称为噪声比率过高），则使用较窄的参数运行另一个搜索。 此时，您可以开始注意显示的模式，并可帮助您更清楚地关注问题。 最终，在执行几个改进的搜索之后，您可以找到与该问题相关的数据，并确定根本原因。
  
> [!TIP]
> 如果在 Skype for Business Server 中出现问题方案，请首先询问自己 "我已经了解问题的哪些信息？" 如果您量化问题边界，则可以在 Skype for Business Server 中消除大部分运营实体的大部分。 
  
考虑一个您知道用户在查找联系人时没有获取当前结果的示例方案。 在媒体组件、企业语音、会议和许多其他组件中找不到问题。 您可能不知道问题实际上是什么：在客户端上，或者是服务器端问题？ 联系人通过用户复制程序从 Active Directory 收集，并通过通讯簿服务器（ABServer）传递到客户端。 ABServer 从 RTC 数据库中获取其更新（用户副本在其中写入它们），并将其收集到通讯簿文件中（默认情况下为-1:30 AM）。 Skype for Business Server 客户端按随机计划检索新的通讯簿。 由于您知道该过程的工作方式，因此您可以将您的搜索范围降低到用户复制程序从 Active Directory 收集的数据相关问题的潜在原因，ABServer 不检索和创建通讯簿文件，或者客户端不会下载通讯簿文件。
  
## <a name="current-configuration"></a>当前配置

集中日志记录服务配置为定义要收集的日志记录服务、它的收集方式、收集位置以及日志设置。 您可以全局定义这些设置（即整个部署），也可以为网站（即部署中的已命名网站）定义这些设置。 您定义的任何日志记录都将使用适用于某个标识（对启动、停止、刷新和搜索日志的命令使用）的设置。
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>显示当前的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。
    
2. 在命令行提示符处键入以下内容：
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > 您可以缩小或扩展由定义 `-Identity` 和作用域（例如 "site： Redmond"）返回的配置设置的范围，以仅返回网站 Redmond 的 new-csclsconfiguration。 如果您需要有关配置的给定部分的详细信息，您可以通过管道将输出传送到另一个 Windows PowerShell cmdlet。 例如，若要获取有关站点 "Redmond" 的配置中定义的方案的详细信息，请键入：`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![New-csclsconfiguration 中的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Cmdlet 中的结果显示集中日志记录服务的当前配置。
    
|**配置设置**|**说明**|
|:-----|:-----|
|**Identity** <br/> |标识此配置的作用域和名称。只有一个“全局”配置，且每个站点只有一个配置。  <br/> |
|**Scenarios** <br/> |为此配置定义的所有方案的列表。  <br/> |
|**SearchTerms** <br/> |为此配置定义的搜索词。 Microsoft 365 或 Office 365，不是本地部署。  <br/> |
|**SecurityGroups** <br/> |定义的安全组，用于控制能查看计算机的人员（即，安全组的成员），具体取决于这些人员所在的站点。 在此上下文中，网站是在拓扑生成器中定义的网站。  <br/> |
|**区域** <br/> |定义了用于将 SecurityGroups 收集到某个区域（例如，EMEA）中的区域。  <br/> |
|**EtlFileRolloverSizeMB** <br/> |该参数指示在创建新的事件跟踪日志 (.etl) 文件之前日志文件需要达到的最大大小。在达到定义的大小之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverMinutes 中设置的最长时间也是如此。  <br/> |
|**EtlFileRolloverMinutes** <br/> |在创建新的 .etl 文件之前日志可等待的定义的最大时间量（以分钟为单位）。在计时器过期之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverSizeMB 中设置的最大大小也是如此。  <br/> |
|**TmfFileSearchPath** <br/> |搜索跟踪消息格式文件的位置。  <br/> |
|**CacheFileLocalFolders** <br/> |定义了在计算机上写入缓存文件的位置的路径。CLSAgent 将写入缓存文件并在网络服务的上下文中运行。在这种情况下，%TEMP% 将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。默认情况下，缓存文件和日志文件将写入相同的目录。  <br/> |
|**CacheFileNetworkFolder** <br/> |您可以定义在日志记录操作过程中接收缓存文件的通用命名约定 (UNC) 路径。  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |已定义为保留缓存文件的最长时间（以天为单位）。  <br/> |
|**CacheFileMaxDiskUsage** <br/> |已定义为可由缓存文件使用的磁盘空间的百分比。  <br/> |
|**ComponentThrottleLimit** <br/> |已定义为在触发自动阻止限制器之前组件每秒可生成的最大跟踪数。  <br/> |
|**ComponentThrottleSample** <br/> |在 60 秒内可超出 ComponentThrottleLimit 的次数。  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |允许运行的 CLSAgent 的最低版本。 此元素适用于 Microsoft 365 或 Office 365。  <br/> |
   

