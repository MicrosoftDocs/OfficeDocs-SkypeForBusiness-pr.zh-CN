---
title: 在由集中日志服务创建的捕获日志上使用搜索
TOCTitle: 在由集中日志服务创建的捕获日志上使用搜索
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49888320
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在由集中日志服务创建的捕获日志上使用搜索

 

_**上一次修改主题：** 2013-02-21_

由于以下原因，集中日志记录服务中的搜索功能很有用，并且很强大：

  - 根据您定义的条件，搜索和结果可在单台计算机、池、站点或全局范围运行。

  - 搜索最初可以很宽泛，然后范围缩小至更具针对性的条件，如时间、组件或计算机。您针对相同日志进行搜索，当搜索条件更改时，无需再次运行日志记录会话。

  - 搜索的结果是从范围内的所有计算机和池中收集的，收集并聚合到单个输出文件中，该输出文件表示搜索条件的所有结果（限于已在运行的方案和这些方案捕获的数据）。使用熟悉的工具（如 **Snooper** 或**记事本**）可以读取该输出文件和来自部署的跟踪消息。

每台计算机上的 CLSAgent 会根据方案创建日志（在任意给定时间，每台计算机上可以运行两个方案）。日志及其关联的索引和缓存文件由 CLSAgent 来管理。当您定义和执行搜索时，搜索命令会向 CLSAgent 指示应检索的信息。CLSAgent 针对日志文件、缓存文件和索引文件执行查询并将搜索结果返回至 CLSContoller。CLSController 接收来自搜索范围内的所有计算机和池的搜索结果。然后，CLSController 聚合（组合）日志并使其按时间增量排序，最早的条目在最前面，最新的条目在最后。

在每次搜索后，**Sync-CsClsLogging** cmdlet 都会运行并且它会刷新搜索使用的缓存（不要与 CLSAgent 维护的缓存文件混淆）。刷新缓存有助于确保在 CLSController 中存在用于下一次搜索操作的干净日志和跟踪文件捕获缓冲区。

为了充分发挥集中日志记录服务的优势，您需要充分理解如何配置搜索，才能只从与您研究的问题有关的计算机和池日志返回跟踪消息。

若要使用 Lync Server 命令行管理程序运行集中日志记录服务搜索功能，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或包含其中任一组的自定义 RBAC 角色。若要返回此 cmdlet 已分配至的所有 RBAC 角色的列表（包括您亲自创建的任何自定义 RBAC 角色），请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主题的其余部分重点介绍如何通过定义搜索来优化故障排除。

## 使用集中日志记录服务运行基本搜索

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  确保 AlwaysOn 方案在部署中的全局范围内运行，然后在命令提示符处键入以下内容：
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    > [!NOTE]
    > 默认情况下，Search-CsClsLogging 将搜索结果发送至控制台。如果要将搜索结果保存至文件，请使用 –OutputFilePath <em>&lt;字符串完全限定的文件路径&gt;</em>。若要定义 –OutputFilePath 参数，请在参数中以用引号括起的字符串格式提供路径和文件名（例如；C:\LogFiles\SearchOutput.txt）。在此示例中，必须确保目录 C:\LogFiles 存在，并且您有权在该文件夹中读取和写入（NTFS 权限修改）文件。输出将进行追加而不会被覆盖。如果需要不同文件，请为每个搜索定义不同文件名。
    
    例如：
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

## 使用集中日志记录服务在池或计算机中运行基本搜索

1.  若要将搜索限制于特定池或计算机，请将 –Computers 参数与计算机完全限定名称所定义的计算机（用引号括起并用逗号隔开）结合使用，如下所示：
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    例如：
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  若要搜索多台计算机，请键入用引号括起并用逗号隔开的多个计算机名称，例如：
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  如果您需要搜索整个池而不是单台计算机，请将 –Computers 参数更改为 –Pools，删除计算机名称，并将其替换为用引号括起并用逗号隔开的一个或多个池。
    
    例如：
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  在使用搜索命令时，池可以是部署中的任意池，如前端池、边缘池、持久聊天服务器池或在部署中定义为池的其他池。
    
    例如：
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

## 使用时间参数运行搜索

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  默认情况下，搜索的时间特定参数的开始时间是在启动搜索之前 30 分钟。换言之，如果在 4:00:00 PM 启动搜索，搜索将在 3:30:00 PM 到 4:00:00 PM 之间搜索您定义的计算机和池的日志。如果需要在当前时间之前搜索 60 分钟或 3 小时，请使用 –StartTime 参数，并设置日期和时间字符串，以指示希望搜索开始的时间。
    
    例如，通过使用 –StartTime 和 –EndTime 定义时间和日期范围，可以定义在 11/20/2012 的 8 AM 到 9 AM 之间对池执行的搜索。可以设置输出路径，以将结果写入名为 c:\\logfile.txt 的文件，如下所示：
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    > [!NOTE]
    > 您指定的时间和日期字符串可以为“日期时间”或“时间日期”。该命令将分析字符串，并对日期和时间使用适当的值。


3.  如果要从 11/20/2012 的 11:00:00 AM 开始检索日志，需定义 –StartTime。除非定义特定的 –EndTime，否则，搜索的默认时间范围是 30 分钟。生成的搜索将在 11:00:00 AM 到 11:30:00 AM 之间从已定义计算机或池中返回日志。
    
    例如：
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  若要对特定时间段内的日志执行搜索，请定义 –StartTime 和 –EndTime。您需要计算机 edge01.contoso.net 上从 1 PM 到 2:45 PM 的日志。
    
    例如：
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

## 使用其他条件和匹配选项运行高级搜索

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  若要运行命令以收集特定组件的跟踪，请键入以下命令：
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    例如：
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    生成的搜索将返回在过去 30 分钟内，在部署中的所有计算机和池中具有 SIPStack、S4 和 UserServices 的跟踪组件的所有日志条目。

3.  若要将具有相同组件的搜索仅限于名为 pool01.contoso.net 的前端池，请键入：
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  使用多个参数的命令的默认搜索逻辑是将逻辑 OR 用于每个已定义参数。可通过指定 **–MatchAll** 参数来更改此行为。为此，请键入以下内容：
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  如果您的方案设置为经常运行（例如 AlwaysOn）或您已定义长期运行的方案，则日志可能从本地计算机转到文件共享中。通过使用 New-CsClsConfiguration 创建新配置或用 Set-CsClsConfiguration 修改现有配置，可使用 CacheFileNetworkFolder 参数定义文件共享。如果不希望搜索将文件共享包括在要搜索的日志集合中，请按如下所示使用 SkipNetworkLogs 参数：
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

