---
title: Skype for Business 2015 中的集中日志记录服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：了解 Skype for Business Server 2015 中集中日志记录服务的服务组件和配置设置。
ms.openlocfilehash: 112a8d59637048729afcdf142fc891863365943593ac6ed7b0cd8f8cc84947d2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295399"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Skype for Business 2015 中的集中日志记录服务
 
**摘要：** 了解 2015 年 10 月集中日志记录服务的服务组件Skype for Business Server设置。
  
集中日志记录服务可以： 
  
- 从中央位置使用单个命令在一台或多台计算机和池中启动或停止日志记录。
    
- 在一台或多台计算机和池中搜索日志。 你可以定制搜索以返回所有计算机上的所有日志，或返回更简洁的结果。
    
- 按如下方式配置日志记录会话：
    
  - 定义一个 **方案**，或使用默认方案。 集中日志记录服务中的方案由范围 (全局或站点) 、用于标识方案用途的方案名称和一个或多个提供程序。 可以在任何给定时间在计算机上运行默认方案和一个定义的方案。
    
  - 使用现有提供程序 或创建新提供程序。 provider定义日志记录会话收集哪些内容、详细信息级别、要跟踪的组件以及应用的标志。
    
    > [!TIP]
    >  如果您熟悉 OCSLogger，则术语providers是指 **组件集合** (例如，S4、SIPStack) 、日志记录类型 **(** 例如 WPP、EventLog 或 IIS 日志文件) 、跟踪级别 **(（** 如 All、verbose、debug) ）和标志 **(** 例如 TF_COMPONENT、TF_DIAG) 。 这些项目在提供程序中定义， (一Windows PowerShell变量) 并传递到集中日志记录服务命令。
  
  - 配置特定计算机和池的日志。
    
  - 从选项"站点 **("** 定义日志记录会话的范围，以仅在该站点中的计算机上运行日志记录捕获) ，或从全局 **(** 在部署) 的所有计算机上运行日志记录捕获。
    
集中日志记录服务是解决从根本原因分析到性能问题等大问题或小问题的强大故障排除工具。 所有示例都使用命令行管理程序Skype for Business Server显示。 通过工具本身为命令行工具提供了帮助，但可以从命令行执行的功能集有限。 通过使用 Skype for Business Server命令行管理程序，您可以访问一组更大且可配置性更多的功能，因此这应始终成为您的第一选择。 
  
## <a name="logging-service-components"></a>日志记录服务组件

 集中日志记录服务在部署的所有服务器上运行，由以下代理和服务决定：
  
- 集中日志记录服务代理 ClsAgent 在部署了日志记录Skype for Business Server上运行。 它侦听 ( **TCP 50001-50003**) 通过 WCF 从 ClsController 发送的命令，并将响应发送回控制器。 它管理日志会话 (/停止/更新) 和搜索日志。 它还执行管理操作，如日志存档和清除。 
    
- 集中日志记录服务控制器 Cmdlet 命令行Skype for Business Server命令行管理程序向 ClsAgent 发送 Start、Stop、Flush 和 Search 命令。 发送搜索命令时，生成的日志将返回到ClsControllerLib.dll聚合。 控制器向代理发送命令，接收这些命令的状态，并管理搜索 日志文件 数据，因为搜索范围中任何计算机上的所有代理都返回了这些数据，并将日志数据聚合到一个有意义且有序的输出集。 以下主题中的信息侧重于使用 Skype for Business Server 命令行管理程序。
    
**ClsController 与 ClsAgent 的通信**

![CLSController 和 CLSAgent 之间的关系。](../../media/Ops_CLS_Architecture.jpg)
  
使用 Windows Server 命令行界面或命令行管理程序发出Skype for Business Server命令。 这些命令在登录到的计算机上执行，并在本地或发送到部署中的其他计算机和池的 ClsAgent。
  
ClsAgent 维护所有 的索引文件。缓存本地计算机上具有的文件。 ClsAgent 分配它们，以便它们均匀分布在由 CacheFileLocalFolders 选项定义的卷中，并且绝不会占用每个卷 (即本地缓存位置和百分比的 80% 以上，即使用 **Set-CsClsConfiguration** cmdlet) 可配置该百分比。 ClsAgent 还负责对旧缓存事件跟踪日志进行 (.etl) 本地计算机的文件。 两周 (即，使用 **Set-CsClsConfiguration** cmdlet 可配置时间范围) 这些文件将复制到文件共享中，然后从本地计算机中删除。 有关详细信息，请参阅 [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)。 当收到搜索请求时，搜索条件用于选择缓存的 .etl 文件集，以基于代理维护的索引中的值执行搜索。
  
> [!NOTE]
> ClsAgent 可以搜索从本地计算机移动到文件共享的文件。 ClsAgent 将文件移动到文件共享后，ClsAgent 不会保留文件的分页和删除。 您应定义一个管理任务来监视文件共享中文件的大小，并删除这些文件或将其存档。 
  
可以使用各种工具读取和分析生成的日志文件，包括Snooper.exe读取文本文件的任何工具（如 **Notepad.exe）。** Snooper.exe是 Skype for Business Server 2015 调试工具的一部分，并作为[Web 下载提供](https://go.microsoft.com/fwlink/p/?LinkId=285257)。
  
与 OCSLogger 一样，集中日志记录服务具有多个要跟踪的组件，并提供用于选择标志的选项，如TF_COMPONENT和TF_DIAG。 集中日志记录服务还保留 OCSLogger 的日志记录级别选项。
  
与命令行 ClsController 使用 Skype for Business Server 命令行管理程序最重要的优点是，您可以使用面向问题空间、自定义标志和日志记录级别的所选提供程序配置和定义新方案。 ClsController 可用的方案仅限于为可执行文件定义的方案。
  
在以前的版本中，OCSLogger.exe，以便管理员和支持人员从部署中的计算机收集跟踪文件。 OCSLogger 的所有优点都有一个缺点。 在给定时间，只能在一台计算机中收集日志。 可以使用 OCSLogger 的单独副本登录到多台计算机，但最终获得多个日志，并且没有聚合结果的简便方法。
  
当用户请求日志搜索时，ClsController 将确定哪些计算机将请求发送到 (，即，根据所选的) 。 它还确定是否需要将搜索发送到保存的 .etl 文件所在的文件共享。 当搜索结果返回到 ClsController 时，控制器会将结果合并到一个按时间结果集向用户显示的结果。 用户可以将搜索结果保存到其本地计算机以进一步分析。
  
启动日志记录会话时，您指定与尝试解决的问题相关的方案。 你随时都可以运行两个方案。 这两个方案之一应为 AlwaysOn 方案。 正如该名称所示，它应始终在部署中运行，并收集所有计算机、池和组件上的信息。
  
> [!IMPORTANT]
> 默认情况下，AlwaysOn 方案未在部署中运行。 必须显式启动方案。 一旦启动，它将继续运行，直到显式停止，并且运行状态通过重新启动计算机将保持。 有关启动和停止方案的详细信息，请参阅 Start [or stop CLS log capture in Skype for Business Server 2015。](start-or-stop-log-capture.md) 
  
当出现问题时，启动与报告的问题相关的第二个方案。 重现问题，并停止第二种方案的日志记录。 开始相对于报告的问题进行日志搜索。 日志的聚合集合生成一日志文件，其中包含来自站点或部署全局范围内的所有计算机的跟踪消息。 如果搜索返回的数据多于实际分析 (通常称为信号噪音比（其中噪音太高）) ，则使用更窄的参数运行另一个搜索。 此时，你可以开始注意到显示的模式，并且可以帮助你更清楚地关注问题。 最后，执行几个优化搜索后，你可以找到与问题相关的数据，并找出根本原因。
  
> [!TIP]
> 在系统呈现问题Skype for Business Server时，请首先询问自己"我已经知道有关该问题的哪些信息？" 如果量化问题边界，可以消除工作中大部分操作实体Skype for Business Server。 
  
请考虑一个示例方案，其中你知道用户在查找联系人时不会获得当前结果。 在媒体组件、企业语音、会议和大量其他组件中查找问题没有意义。 您可能不知道问题实际上在哪里：在客户端上，还是服务器端问题？ 联系人由用户复制程序从 Active Directory 中收集，然后通过通讯簿服务器或 ABServer (传递到客户端) 。 ABServer 从 RTC 数据库获取其更新 (其中用户复制程序将更新) 并收集到通讯簿文件中，默认为上午 1：30。 客户端Skype for Business Server随机计划检索新通讯簿。 由于你了解此过程的工作方式，因此可以减少搜索，以查找与用户复制程序从 Active Directory 收集的数据相关的问题、ABServer 不检索和创建通讯簿文件或客户端不下载通讯簿文件的潜在原因。
  
## <a name="current-configuration"></a>当前配置

集中日志记录服务配置为定义日志记录服务要收集哪些信息、收集方式、收集位置以及日志设置是什么。 全局定义这些设置 (，即，针对整个部署) 或为站点 (，即部署部署中的命名) 。 您定义的任何日志记录都将使用适用于某个标识（对启动、停止、刷新和搜索日志的命令使用）的设置。
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>显示当前的集中日志记录服务配置

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
2. 在命令行提示符处键入以下内容：
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > 您可以通过定义 和 范围（如"Site：Redmond"）缩小或扩展返回的配置设置的范围，以仅返回站点 Redmond 的  `-Identity` CsClsConfiguration。 如果需要有关配置给定部分的详细信息，可以通过管道将输出通过管道Windows PowerShell cmdlet。 例如，要获取有关在站点"Redmond"的配置中定义的方案的详细信息，请键入： `Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    此 cmdlet 的结果显示集中日志记录服务的当前配置。
    
|**配置设置**|**说明**|
|:-----|:-----|
|**Identity** <br/> |标识此配置的作用域和名称。只有一个“全局”配置，且每个站点只有一个配置。  <br/> |
|**Scenarios** <br/> |为此配置定义的所有方案的列表。  <br/> |
|**SearchTerms** <br/> |为此配置定义的搜索词。 Microsoft 365或Office 365部署，而不是本地部署。  <br/> |
|**SecurityGroups** <br/> |定义的安全组，用于控制能查看计算机的人员（即，安全组的成员），具体取决于这些人员所在的站点。 在此上下文中，Site 是拓扑生成器中定义的站点。  <br/> |
|**地区** <br/> |定义了用于将 SecurityGroups 收集到某个区域（例如，EMEA）中的区域。  <br/> |
|**EtlFileRolloverSizeMB** <br/> |该参数指示在创建新的事件跟踪日志 (.etl) 文件之前日志文件需要达到的最大大小。在达到定义的大小之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverMinutes 中设置的最长时间也是如此。  <br/> |
|**EtlFileRolloverMinutes** <br/> |在创建新的 .etl 文件之前日志可等待的定义的最大时间量（以分钟为单位）。在计时器过期之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverSizeMB 中设置的最大大小也是如此。  <br/> |
|**TmfFileSearchPath** <br/> |搜索跟踪消息格式文件的位置。  <br/> |
|**CacheFileLocalFolders** <br/> |定义了在计算机上写入缓存文件的位置的路径。CLSAgent 将写入缓存文件并在网络服务的上下文中运行。在这种情况下，%TEMP% 将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。默认情况下，缓存文件和日志文件将写入相同的目录。  <br/> |
|**CacheFileNetworkFolder** <br/> |您可以定义在日志记录操作过程中接收缓存文件的通用命名约定 (UNC) 路径。  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |已定义为保留缓存文件的最长时间（以天为单位）。  <br/> |
|**CacheFileMaxDiskUsage** <br/> |已定义为可由缓存文件使用的磁盘空间的百分比。  <br/> |
|**ComponentThrottleLimit** <br/> |已定义为在触发自动阻止限制器之前组件每秒可生成的最大跟踪数。  <br/> |
|**ComponentThrottleSample** <br/> |在 60 秒内可超出 ComponentThrottleLimit 的次数。  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |允许运行的 CLSAgent 的最低版本。 此元素用于Microsoft 365 Office 365。  <br/> |
