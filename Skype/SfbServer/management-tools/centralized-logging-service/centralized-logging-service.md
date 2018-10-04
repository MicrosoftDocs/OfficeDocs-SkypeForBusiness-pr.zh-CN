---
title: Skype for Business 2015 中的集中日志记录服务
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 摘要： 了解有关服务组件和业务服务器 2015 the Centralized Logging Service 中 Skype 的配置设置。
ms.openlocfilehash: b2234ac1b52ff41108573f6a90a07bfa28c50a58
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372458"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Skype for Business 2015 中的集中日志记录服务
 
**摘要：** 了解服务组件和业务服务器 2015 the Centralized Logging Service 中 Skype 的配置设置。
  
The Centralized Logging Service 可以： 
  
- 启动或停止日志记录对一个或多个计算机和池使用单个命令从一个中心位置。
    
- 在一台或多台计算机和池中搜索日志。 您可以定制搜索返回所有计算机上的所有日志或都返回更简洁的结果。
    
- 按如下方式配置日志记录会话：
    
  - 定义一个**方案**，或使用默认方案。 Centralized Logging Service 中的方案构成范围 (全局或站点)，用于标识的方案和一个或多个提供程序用途的方案名称。 可以在任何给定时间运行的默认方案和一个定义的方案，计算机上。
    
  - 使用现有提供程序或创建新提供程序。 Aprovider 定义日志记录会话所收集、 什么级别的详细信息、 跟踪，哪些组件和应用哪些标志。
    
    > [!TIP]
    >  如果您熟悉 OCSLogger，termproviders 指的**组件**（例如，S4、 SIPStack）、**日志记录类型**（例如，WPP、 事件日志或 IIS 的日志文件）、**跟踪级别**(例如，All、 verbose 和 debug) 的集合和**标志**（例如，TF_COMPONENT、 TF_DIAG）。 这些项提供程序 （Windows PowerShell 变量） 中定义和传递到 Centralized Logging Service 命令。
  
  - 配置特定计算机和池的日志。
    
  - 从选项“**站点**”（仅在该站点中的计算机上运行日志记录捕获）或“**全局**”（在部署中的所有计算机上运行日志记录捕获）定义日志记录会话的作用域。
    
The Centralized Logging Service 是问题大或小，从根源分析的性能问题的强大故障排除工具。 所有的示例所示的业务 Server 命令行管理程序中使用 Skype。 通过命令行工具本身为其提供了帮助，但是，您可以从命令行执行的功能集有限。 通过使用 Skype 业务 Server 命令行管理程序，您有权访问一大得多和更加可配置的功能，因此，应始终为第一个选择。 
  
## <a name="logging-service-components"></a>日志记录服务组件

 The Centralized Logging Service 在部署中的所有服务器上运行并以下代理和服务组成：
  
- 业务服务器部署与 Skype 的每台计算机上运行的集中日志记录服务代理 clsagent 的通信。 它通过 WCF （上端口**TCP 50001 50003**） 侦听来自 ClsController 命令，并将发送回控制器的响应。 它管理日志会话 （停止/开始/更新），并搜索日志。 它还可执行日志存档和清除等管理操作。 
    
- 集中日志记录服务控制器 Cmdlet Skype 的业务 Server 命令行管理程序将启动、 停止、 刷新、 和搜索的命令发送与 clsagent 的通信。 当发送搜索命令时，返回到 ClsControllerLib.dll 并聚合生成的日志。 控制器将命令发送到代理、 接收这些命令的状态和管理搜索日志文件数据，因为它从所有代理返回的搜索范围中的任何计算机上，为有意义且有序输出组聚合的日志数据。 以下主题中的信息致力于 Skype 用于业务 Server Management Shell。
    
**ClsController 与 ClsAgent 的通信**

![CLSController 和 CLSAgent 之间的关系。](../../media/Ops_CLS_Architecture.jpg)
  
发出命令使用 Windows Server 命令行界面或 Skype 用于业务 Server Management Shell。 这些命令将在您登录的计算机上执行，并将本地发送到 ClsAgent 或发送到部署中的其他计算机和池。
  
ClsAgent 维护其在本地计算机上具有的所有 .CACHE 文件的索引文件。 Clsagent 的通信分配，以便在定义由选项 CacheFileLocalFolders，从不使用了多个 80%的 （即，本地缓存位置和百分比是可使用**配置每个卷的卷之间均匀分布Set-CsClsConfiguration** cmdlet)。 ClsAgent 还负责从本地计算机中清除旧的缓存事件跟踪日志 (.etl) 文件。 两个周后 （也就是说，时间范围是使用**Set-csclsconfiguration** cmdlet 可配置） 这些文件复制到文件共享，且从本地计算机中删除。 有关详细信息，请参阅[Set-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)。 在收到一个搜索请求时，搜索条件将用于选择一组缓存的 .etl 文件以便根据代理所维护的索引中的值来执行搜索。
  
> [!NOTE]
> 从本地计算机移至文件共享中的文件可通过 ClsAgent 进行搜索。一旦 ClsAgent 将这些文件移至文件共享中，ClsAgent 将不会维护文件的清楚和删除。您应定义一个管理任务来监控文件共享中的文件大小，并删除这些文件或对其进行存档。 
  
可使用多种工具读取和分析生成的日志文件，其中包括 **Snooper.exe** 以及任何可读取文本文件的工具（例如 **Notepad.exe**）。 Snooper.exe 是业务 Server 2015 调试工具 Skype 的一部分，并且可用作[Web 下载](https://go.microsoft.com/fwlink/p/?LinkId=285257)。
  
OCSLogger，如 the Centralized Logging Service 有几个组件跟踪，并提供选项以选择标志，如 TF_COMPONENT 和 TF_DIAG。 集中日志记录服务还保留 OCSLogger 日志记录级别选项。
  
通过命令行 ClsController 业务 Server 命令行管理程序使用 Skype 的最重要优点是，您可以配置和定义使用所选目标问题空间、 自定义标志和日志记录级别的提供程序的新方案。 对 ClsController 可用的方案仅为针对可执行文件定义的方案。
  
在早期版本中，提供了 OCSLogger.exe 以使管理员和支持人员能够从部署中的计算机中收集跟踪文件。尽管 OCSLogger 具有的优点不少，但它也有一个缺点。在给定时间内，您只能在一台计算机上收集日志。虽然可通过使用 OCSLogger 的独立副本来登录多台计算机，但最终将获得多个日志且无法轻松聚合结果。
  
当用户请求一个日志搜索时，ClsController 将确定将请求发送到哪些计算机（即，基于选定方案）。它还确定是否需要将搜索发送到已保存的 .etl 文件所在的文件共享。当搜索结果返回到 ClsController 时，控制器会将结果合并到一个呈现给用户的按时间排序的结果集中。用户可以将搜索结果保存到其本地计算机中以供进一步分析。
  
在启动日志记录会话时，您指定与您尝试解决的问题相关的方案。可以随时运行两个方案，其中一个方案应为 AlwaysOn 方案。顾名思义，此方案应始终在部署中运行，并收集有关所有计算机、池和组件的信息。
  
> [!IMPORTANT]
> 默认情况下，AlwaysOn 方案在部署中不会运行。 您必须显式启动此方案。 一旦启动此方案，它就将继续运行直到被显式停止，并且在重新启动计算机的过程中持续保持运行状态。 有关启动和停止方案的详细信息，请参阅[启动或停止 CLS 日志捕获中 Skype 业务服务器 2015年](start-or-stop-log-capture.md)。 
  
在出现问题时，启动与所报告的问题相关的另一个方案。重现该问题并停止针对该方案的日志记录。开始与所报告的问题相关的日志搜索。日志的聚合收集会生成一个日志文件，其中包含站点或全局范围部署中的所有计算机中的跟踪消息。如果搜索返回的数据多于可进行可行性分析的数据（通常称为信噪比，其中噪音过高），则可使用范围更小的参数运行另一个搜索。此时，您可以关注显示的模式并可帮助您准确了解问题。最后，在执行一组优化搜索后，您可以找到与该问题相关的数据并指出根本原因。
  
> [!TIP]
> 通过问自己"什么我已知道有关该问题？"启动时显示的问题方案中 Skype 业务服务器， 如果量化问题边界，则可以消除 Skype 中的操作实体很大程度业务服务器。 
  
考虑以下示例方案：您知道用户在查找联系人时未获得当前结果。 没有无点中查找媒体组件、 企业语音、 会议和大量其他组件中出现的问题。 您不知道出现问题的实际位置：是客户端上还是服务器端？ 从 Active Directory 收集由用户复制程序并传递给通过通讯簿服务器 (ABServer) 的客户联系人。 ABServer 获取其更新从 RTC 数据库 （其中用户复制程序编写了这些），并将它们收集到通讯簿文件中，默认情况下-1:30 AM。 为业务服务器客户端 Skype 检索随机计划上的新通讯簿。 由于您知道过程工作方式，可以减少潜在的原因您搜索与用户复制程序，ABServer 不检索和创建通讯簿文件或客户端不从 Active Directory 收集的数据相关的问题下载通讯簿文件。
  
## <a name="current-configuration"></a>当前配置

集中日志记录服务配置为定义日志记录服务用于收集、 如何收集，它将收集从，并日志设置是什么。 您将为全局（即整个部署）或站点（即部署中的命名站点）定义这些设置。 您定义的任何日志记录都将使用适用于某个标识（对启动、停止、刷新和搜索日志的命令使用）的设置。
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>若要显示当前的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 在命令行提示符处键入以下内容：
    
   ```
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > 可以缩小范围，也可以展开返回通过定义的配置设置的作用域`-Identity`和范围，例如"Site: Redmond"以返回仅站点 Redmond CsClsConfiguration。 如果您希望有关配置的指定部分的详细信息，您可以输出通过管道传递到另一个 Windows PowerShell cmdlet。 例如，若要获得有关站点“Redmond”的配置中定义的方案的详细信息，请键入：`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![来自 Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    此 cmdlet 的结果显示 the Centralized Logging Service 的当前配置。
    
|**配置设置**|**说明**|
|:-----|:-----|
|**Identity** <br/> |标识此配置的作用域和名称。只有一个“全局”配置，且每个站点只有一个配置。  <br/> |
|**Scenarios** <br/> |为此配置定义的所有方案的列表。  <br/> |
|**SearchTerms** <br/> |为此配置定义的搜索词。 Office 365 中，不在本地部署。  <br/> |
|**SecurityGroups** <br/> |定义的安全组，用于控制能查看计算机的人员（即，安全组的成员），具体取决于这些人员所在的站点。 网站，在此上下文中，是拓扑生成器中定义的网站。  <br/> |
|**Regions** <br/> |定义了用于将 SecurityGroups 收集到某个区域（例如，EMEA）中的区域。  <br/> |
|**EtlFileRolloverSizeMB** <br/> |该参数指示在创建新的事件跟踪日志 (.etl) 文件之前日志文件需要达到的最大大小。在达到定义的大小之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverMinutes 中设置的最长时间也是如此。  <br/> |
|**EtlFileRolloverMinutes** <br/> |在创建新的 .etl 文件之前日志可等待的定义的最大时间量（以分钟为单位）。在计时器过期之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverSizeMB 中设置的最大大小也是如此。  <br/> |
|**TmfFileSearchPath** <br/> |搜索跟踪消息格式文件的位置。  <br/> |
|**CacheFileLocalFolders** <br/> |定义了在计算机上写入缓存文件的位置的路径。CLSAgent 将写入缓存文件并在网络服务的上下文中运行。在这种情况下，%TEMP% 将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。默认情况下，缓存文件和日志文件将写入相同的目录。  <br/> |
|**CacheFileNetworkFolder** <br/> |您可以定义在日志记录操作过程中接收缓存文件的通用命名约定 (UNC) 路径。  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |已定义为保留缓存文件的最长时间（以天为单位）。  <br/> |
|**CacheFileMaxDiskUsage** <br/> |已定义为可由缓存文件使用的磁盘空间的百分比。  <br/> |
|**ComponentThrottleLimit** <br/> |已定义为在触发自动阻止限制器之前组件每秒可生成的最大跟踪数。  <br/> |
|**ComponentThrottleSample** <br/> |在 60 秒内可超出 ComponentThrottleLimit 的次数。  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |允许运行的 CLSAgent 的最低版本。 此元素适用于 Office 365。  <br/> |
   

