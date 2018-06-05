---
title: 在 Skype for Business Server 2015 中搜索集中日志记录服务创建的捕获日志
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 摘要： 了解如何搜索和业务服务器 2015年阅读 Centralized Logging Service 中 Skype 的捕获日志。
ms.openlocfilehash: eb90fcab49bca13e1a3cbe89102301167e059fda
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570162"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中搜索集中日志记录服务创建的捕获日志
 
**摘要：** 了解如何搜索和业务服务器 2015年阅读 Centralized Logging Service 中 Skype 的捕获日志。
  
The Centralized Logging Service 中的搜索功能很有用，并且强大原因如下： 
  
- 根据您定义的条件，搜索和结果可在单台计算机、池、站点或全局范围运行。
    
- 搜索最初可以很宽泛，然后范围缩小至更具针对性的条件，如时间、组件或计算机。 您对相同的日志搜索并不需要运行日志记录会话再次更改搜索条件时。
    
- 搜索的结果是从范围内的所有计算机和池中收集的，收集并聚合到单个输出文件中，该输出文件表示搜索条件的所有结果（限于已在运行的方案和这些方案捕获的数据）。使用熟悉的工具（如 **Snooper** 或**记事本**）可以读取该输出文件和来自部署的跟踪消息。
    
每台计算机上的 CLSAgent 会根据方案创建日志（在任意给定时间，每台计算机上可以运行两个方案）。日志及其关联的索引和缓存文件由 CLSAgent 来管理。当您定义和执行搜索时，搜索命令会向 CLSAgent 指示应检索的信息。CLSAgent 针对日志文件、缓存文件和索引文件执行查询并将搜索结果返回至 CLSContoller。CLSController 接收来自搜索范围内的所有计算机和池的搜索结果。然后，CLSController 聚合（组合）日志并使其按时间增量排序，最早的条目在最前面，最新的条目在最后。
  
每个搜索之后, 运行**Sync-csclslogging** cmdlet 并刷新缓存用于搜索 （不能与 clsagent 的通信由保留缓存文件混淆）。 刷新缓存有助于确保在 CLSController 中存在用于下一次搜索操作的干净日志和跟踪文件捕获缓冲区。
  
若要获得 the Centralized Logging Service 的最大好处，您需要如何配置搜索以返回只跟踪消息从计算机和池日志与您研究该问题相关的更好地理解。 问题
  
若要使用 Skype 业务 Server 命令行管理程序中运行的集中日志记录服务搜索功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中或自定义 RBAC 角色的成员包含这两个组之一。 若要返回的已分配此 cmdlet 的所有 RBAC 角色的列表 （包括您自己创建任何自定义 RBAC 角色），请业务 Server 命令行管理程序或 Windows PowerShell 提示符从 Skype 运行以下命令：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主题的其余部分重点介绍如何通过定义搜索来优化故障排除。
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>使用 the Centralized Logging Service 中运行基本搜索

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 确保 AlwaysOn 方案在部署中的全局范围内运行，然后在命令提示符处键入以下内容：
    
  ```
  Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
  ```

> [!NOTE]
> 默认情况下，Search-CsClsLogging 将搜索结果发送至控制台。 如果您想要将搜索结果保存到文件，使用-OutputFilePath_\<字符串完全限定的文件路径\>_。 若要定义-OutputFilePath 参数，提供的路径和文件名 （例如; 括在引号的字符串格式中的参数的一部分C:\LogFiles\SearchOutput.txt)。 在此示例中，必须确保目录 C:\LogFiles 存在，并且您有权在该文件夹中读取和写入（NTFS 权限修改）文件。 输出将进行追加而不会被覆盖。 如果需要不同文件，请为每个搜索定义不同文件名。 
  
例如：
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>使用 the Centralized Logging Service 在池或计算机上运行基本搜索

1. 若要限制到特定的池或计算机的搜索，请使用与计算机由计算机的完全限定名称定义和括在引号内，如下所示并用逗号分隔-Computers 参数：
    
  ```
  Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
  ```

例如：
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. 若要搜索多台计算机，请键入用引号括起并用逗号隔开的多个计算机名称，例如：
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

3. 如果您需要搜索整个池而不是一台计算机，更改为-池、 删除计算机名和替换-Computers 参数它与池或在引号内的池以逗号分隔。
    
    例如：
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 在使用搜索命令时，池可以是在部署中，如前端池、 边缘池、 持久聊天服务器池，或为池部署中定义的其他任何池。
    
    例如：
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-a-search-by-using-time-parameters"></a>使用时间参数运行搜索

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 默认情况下，搜索的时间特定参数的开始时间为启动搜索前 25 分钟到后五分钟。 换言之，如果在 4:00:00 PM 进行搜索，搜索开始时间将显示为 3:35:00 PM 到 4:05:00 PM。 如果您需要搜索 60 分钟或 3 小时当前时间之前，请使用-StartTime 参数，并设置来指示希望搜索开始的时间的日期和时间的字符串。 
    
    例如，通过使用-StartTime 和-EndTime 定义的日期和时间范围，您可以定义搜索上午 8 和 9 AM 之间在 2012 年 11/20 池上。 可以设置输出路径，以将结果写入名为 c:\logfile.txt 的文件，如下所示：
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

> [!NOTE]
> 您指定的时间和日期字符串可以为“日期时间”或“时间日期”。 "该命令将分析字符串，并对日期和时间以及您运行的 cmdlet 的计算机上的区域设置和区域性设置使用适当的值。 
  
3. 如果您想要检索 11:00:00 2012 年 11/20 的开头的日志，则定义-StartTime。 搜索的默认时间范围为 30 分钟，除非您定义特定结束时间。 生成的搜索将在 11:00:00 AM 到 11:30:00 AM 之间从已定义计算机或池中返回日志。
    
例如：
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 若要在特定时间段内执行的日志搜索，定义-StartTime 和-EndTime。 您需要计算机 edge01.contoso.net 上从 1 PM 到 2:45 PM 的日志。 
    
例如：
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>使用其他条件和匹配选项运行高级搜索

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 若要运行命令以收集特定组件的跟踪，请键入以下命令：
    
  ```
  Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
  ```

例如：
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

生成的搜索将返回在过去 30 分钟内，在部署中的所有计算机和池中具有 SIPStack、S4 和 UserServices 的跟踪组件的所有日志条目。
    
3. 若要限制具有到刚名为 pool01.contoso.net 您前端池的相同组件的搜索，请键入：
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 使用多个参数的命令的默认搜索逻辑是将逻辑 OR 用于每个已定义参数。 您可以通过指定 **-MatchAll**参数来更改此行为。 为此，请键入以下内容：
    
  ```
  Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

5. 如果您的方案设置为经常运行（例如 AlwaysOn）或您已定义长期运行的方案，则日志可能从本地计算机转到文件共享中。通过使用 New-CsClsConfiguration 创建新配置或用 Set-CsClsConfiguration 修改现有配置，可使用 CacheFileNetworkFolder 参数定义文件共享。如果不希望搜索将文件共享包括在要搜索的日志集合中，请按如下所示使用 SkipNetworkLogs 参数：
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>从集中日志记录服务读取捕获的日志

运行搜索和必须可用来跟踪报告问题的文件后，您可以实现实际 the Centralized Logging Service 的好处。 读取该文件有多种方法。 输出文件为标准文本格式，可以使用 Notepad.exe 或任何其他可以打开和读取文本文件的程序。 对于较大的文件和更复杂的问题，可以使用的工具 Snooper.exe，旨在读取并分析 the Centralized Logging Service 中的日志记录输出类似。 Snooper 包含在可单独下载的调试工具中。 您可以下载调试工具此处： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)。 在安装调试工具时，不会创建快捷方式和菜单项。 安装调试工具后，打开 Windows 资源管理器、 命令行窗口或 Skype 业务 Server 命令行管理程序和业务 Server 2015\Debugging 工具的 C:\Program Files\Skype 转到的目录 （默认位置）。 双击 Snooper.exe 或键入 Snooper.exe，，如果您使用命令行或 Skype for Business Server 命令行管理程序，然后按 ENTER。
  
> [!IMPORTANT]
> 本主题的目的不是详细介绍和讨论疑难解答技术。 疑难解答及其相关过程是一个复杂的主题。 疑难解答基本知识和特定的工作负载疑难解答的详细信息，请参阅在 Microsoft Lync Server 2010 资源工具包书籍内，在[https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)。 流程和过程仍适用于 Skype 的业务服务器 2015年。 
  
### <a name="to-open-a-log-file-in-snooper"></a>在 Snooper 中打开日志文件

1. 要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。 
    
2. 安装调试工具 (LyncDebugTools.msi) 后，使用 Windows 资源管理器或从命令行将目录切换到 Snooper.exe 的位置。 默认情况下调试工具都位于 C:\Program Files\Skype Business Server 2015\Debugging 工具。 双击或运行 Snooper.exe。
    
3. 打开 Snooper 后，右键单击“**文件**”，单击“**打开文件**”，查找日志文件，在“**打开**”对话框中选择文件，然后单击“**打开**”。
    
4. 显示日志文件的**跟踪**消息**跟踪**在选项卡，单击**邮件**选项卡查看收集的跟踪消息的内容。
    
### <a name="to-display-a-call-flow-diagram"></a>显示呼叫流程图

1. 要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您需要是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。
    
2. 打开日志文件并单击“**消息**”选项卡，在消息视图中选择对话或在“**跟踪**”选项卡上选择跟踪组件。
    
3. 单击“**呼叫流**”。
    
> [!NOTE]
> 如果您单击邮件或不是呼叫流的一部分的跟踪，不显示图表，并且在 Snooper 指出"This message is 不适合 callfow"的底部显示状态信息。 选择另一条属于呼叫流的消息或跟踪，将显示呼叫流。 
  
4. 在消息或跟踪行间移动，并注意呼叫流程图是否更新或更改为显示新图。
    
5. 在元素上悬停可获得有关呼叫消息、终结点和其他组件的信息。