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
description: 摘要： 了解如何搜索和阅读业务服务器 2015 Skype 在集中式日志记录服务捕获日志。
ms.openlocfilehash: ccf9827848d190179b5f942646a74947047c02c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中搜索集中日志记录服务创建的捕获日志
 
**摘要：**了解如何搜索和阅读业务服务器 2015 Skype 在集中式日志记录服务捕获日志。
  
在集中式日志记录服务的搜索功能是有用且功能强大，原因如下： 
  
- 根据您定义的条件，搜索和结果可在单台计算机、池、站点或全局范围运行。
    
- 搜索最初可以很宽泛，然后范围缩小至更具针对性的条件，如时间、组件或计算机。 对相同的日志搜索，无需运行的日志记录会话再次更改的搜索条件时。
    
- 搜索的结果是从范围内的所有计算机和池中收集的，收集并聚合到单个输出文件中，该输出文件表示搜索条件的所有结果（限于已在运行的方案和这些方案捕获的数据）。使用熟悉的工具（如 **Snooper** 或**记事本**）可以读取该输出文件和来自部署的跟踪消息。
    
每台计算机上的 CLSAgent 会根据方案创建日志（在任意给定时间，每台计算机上可以运行两个方案）。日志及其关联的索引和缓存文件由 CLSAgent 来管理。当您定义和执行搜索时，搜索命令会向 CLSAgent 指示应检索的信息。CLSAgent 针对日志文件、缓存文件和索引文件执行查询并将搜索结果返回至 CLSContoller。CLSController 接收来自搜索范围内的所有计算机和池的搜索结果。然后，CLSController 聚合（组合）日志并使其按时间增量排序，最早的条目在最前面，最新的条目在最后。
  
每次的搜索之后, 运行**同步 CsClsLogging** cmdlet 和刷新高速缓存用于搜索 （不能混淆与 CLSAgent 所维护的缓存文件）。 刷新缓存有助于确保在 CLSController 中存在用于下一次搜索操作的干净日志和跟踪文件捕获缓冲区。
  
要从集中式日志记录服务中获得最大益处，需要很好地了解如何配置搜索返回从计算机和池日志相关的问题，正在研究的仅跟踪消息。 问题
  
若要通过 Skype 业务服务器管理外壳程序运行集中式日志记录服务搜索功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中，或自定义的 RBAC 角色成员包含这两个组之一。 要返回的已分配此 cmdlet 的 RBAC 角色的列表 （包括您自己创建的任何自定义的 RBAC 角色），请为业务服务器管理外壳程序或 Windows PowerShell 提示从 Skype 运行下面的命令：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主题的其余部分重点介绍如何通过定义搜索来优化故障排除。
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>若要使用集中式日志记录服务运行基本搜索

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 确保 AlwaysOn 方案在部署中的全局范围内运行，然后在命令提示符处键入以下内容：
    
  ```
  Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
  ```

> [!NOTE]
> 默认情况下，Search-CsClsLogging 将搜索结果发送至控制台。 如果您想要将搜索结果保存到一个文件，使用-OutputFilePath_\<字符串完全限定的文件路径\>_。 若要定义-OutputFilePath 参数，提供路径和文件名 （例如; 用引号括起来的字符串格式的参数的一部分C:\LogFiles\SearchOutput.txt)。 在此示例中，必须确保目录 C:\LogFiles 存在，并且您有权在该文件夹中读取和写入（NTFS 权限修改）文件。 输出将进行追加而不会被覆盖。 如果需要不同文件，请为每个搜索定义不同文件名。 
  
例如：
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>若要使用集中式日志记录服务池或计算机上运行一个基本的搜索

1. 若要将搜索限制为特定的池或计算机，请使用-计算机参数与计算机定义的计算机的完全限定名称用引号括起来，用逗号隔开，如下所示：
    
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

3. 如果您需要搜索整个池而不是一台计算机，更改为-池、 计算机名称，删除和替换的计算机参数与池或池在引号之间用逗号分开。
    
    例如：
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 当使用搜索命令时，池可以在部署中，前端池、 边缘池、 持久聊天服务器池或其他人定义为您的部署中池等任何池。
    
    例如：
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-a-search-by-using-time-parameters"></a>使用时间参数运行搜索

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 默认情况下，搜索的时间特定参数的开始时间为启动搜索前 25 分钟到后五分钟。 换言之，如果在 4:00:00 PM 进行搜索，搜索开始时间将显示为 3:35:00 PM 到 4:05:00 PM。 如果您需要搜索 60 分钟或在当前时间之前的 3 个小时，使用的开始时间参数并设置日期和时间字符串，指示您想要开始搜索的时间。 
    
    例如，通过使用的开始时间和结束时间-定义时间和日期的区域，您可以定义搜索上午 8 点到 9 点之间在 2012 年 11/20 在池上。 可以设置输出路径，以将结果写入名为 c:\logfile.txt 的文件，如下所示：
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

> [!NOTE]
> 您指定的时间和日期字符串可以为“日期时间”或“时间日期”。 "命令将分析该字符串，并使用日期和时间以及区域设置和区域性 cmdlet 从运行的计算机上设置适当的值。 
  
3. 如果您想要检索日志在 11:00:00 AM 2012 年 11/20 开头，您定义的开始时间。 除非您定义特定结束时间，搜索的默认时间范围为 30 分钟。 生成的搜索将在 11:00:00 AM 到 11:30:00 AM 之间从已定义计算机或池中返回日志。
    
例如：
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 要在特定时间段内进行搜索的日志，定义的开始时间的结束时间。 您需要计算机 edge01.contoso.net 上从 1 PM 到 2:45 PM 的日志。 
    
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
    
3. 要将限制到只是前端池名为 pool01.contoso.net 的相同组件的搜索，请键入：
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 使用多个参数的命令的默认搜索逻辑是将逻辑 OR 用于每个已定义参数。 您可以通过指定**-MatchAll**参数来更改此行为。 为此，请键入以下内容：
    
  ```
  Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

5. 如果您的方案设置为经常运行（例如 AlwaysOn）或您已定义长期运行的方案，则日志可能从本地计算机转到文件共享中。通过使用 New-CsClsConfiguration 创建新配置或用 Set-CsClsConfiguration 修改现有配置，可使用 CacheFileNetworkFolder 参数定义文件共享。如果不希望搜索将文件共享包括在要搜索的日志集合中，请按如下所示使用 SkipNetworkLogs 参数：
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

  ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>从集中日志记录服务读取捕获的日志

运行搜索，并具有可用于跟踪报告问题的文件后，您可以实现集中式日志记录服务的真正好处。 读取该文件有多种方法。 输出文件为标准文本格式，可以使用 Notepad.exe 或任何其他可以打开和读取文本文件的程序。 对于较大的文件和更复杂的问题，您可以使用像 Snooper.exe，用来读取和分析日志输出从集中式日志记录服务的工具。 Snooper 包含在可单独下载的调试工具中。 您可以下载调试工具在此处： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)。 安装调试工具时，不创建快捷方式和菜单项。 安装调试工具后，打开 Windows 资源管理器、 命令行窗口中或 Skype 业务服务器管理外壳程序和业务服务器 2015\Debugging 工具的 C:\Program Files\Skype 转至目录 （默认位置）。 双击 Snooper.exe 或键入 Snooper.exe，，如果您使用命令行或 Skype 业务服务器管理外壳程序，然后按 enter 键。
  
> [!IMPORTANT]
> 本主题的目的不是详细介绍和讨论疑难解答技术。 疑难解答及其相关过程是一个复杂的主题。 有关故障诊断基础知识以及解决特定的工作负载的详细信息，请参阅 Microsoft Lync Server 2010 资源工具包簿[https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)。 过程和步骤仍然适用于 Skype 的业务服务器 2015年。 
  
### <a name="to-open-a-log-file-in-snooper"></a>在 Snooper 中打开日志文件

1. 要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。 
    
2. 安装调试工具 (LyncDebugTools.msi) 后，使用 Windows 资源管理器或从命令行将目录切换到 Snooper.exe 的位置。 默认情况下，调试工具都位于 C:\Program Files\Skype 的业务服务器 2015\Debugging 工具。 双击或运行 Snooper.exe。
    
3. 打开 Snooper 后，右键单击“**文件**”，单击“**打开文件**”，查找日志文件，在“**打开**”对话框中选择文件，然后单击“**打开**”。
    
4. 日志文件的**跟踪**消息会显示在**跟踪**选项卡，单击**邮件**选项卡查看收集到的跟踪的消息的内容。
    
### <a name="to-display-a-call-flow-diagram"></a>显示呼叫流程图

1. 要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您需要是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。
    
2. 打开日志文件并单击“**消息**”选项卡，在消息视图中选择对话或在“**跟踪**”选项卡上选择跟踪组件。
    
3. 单击“**呼叫流**”。
    
> [!NOTE]
> 如果您单击邮件或不属于呼叫流的跟踪，将不会显示该关系图和窥探，指出"此消息没有资格享受 callfow"的底部会显示一条状态消息。 选择另一条属于呼叫流的消息或跟踪，将显示呼叫流。 
  
4. 在消息或跟踪行间移动，并注意呼叫流程图是否更新或更改为显示新图。
    
5. 在元素上悬停可获得有关呼叫消息、终结点和其他组件的信息。