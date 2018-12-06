---
title: 使用集中日志记录服务
TOCTitle: 使用集中日志记录服务
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49888473
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用集中日志记录服务

 

_**上一次修改主题：** 2012-11-01_

集中日志记录服务是 Lync Server 2013 中的一种新功能。这是以前版本中提供的 **OCSLogger** 和 **OCSTracer** 工具的增强替代。您可以使用集中日志记录服务执行以下任务：

  - 从一个位置使用单个命令在一台或多台计算机和池上开始日志记录。

  - 从一个位置使用单个命令在一台或多台计算机和池上停止日志记录。

  - 从一个位置使用单个命令在一台或多台计算机和池中搜索日志。您可以定制搜索命令以返回在所有计算机上捕获和存储的日志的整个聚合，或返回捕获特定数据的拼接结果。

  - 按如下方式配置日志记录会话：
    
      - 定义一个**方案**，或使用默认方案。集中日志记录服务中的*方案* 由作用域（全局或站点）、用于确定方案的用途的方案名称和一个或多个提供程序组成。您在任何给定的时间都可以在一台计算机上运行两个方案。
    
      - 使用现有*提供程序* 或创建新提供程序。*提供程序* 定义日志记录会话收集的内容、详细信息级别、要跟踪的组件以及应用的标志。
        
        > [!TIP]  
        > 如果您熟悉 OCSLogger，那就知道术语<em>提供程序</em> 指的是<strong>组件</strong>（例如，S4、SIPStack）、<strong>日志记录类型</strong>（例如，WPP、EventLog 或 IIS 日志文件）、<strong>跟踪级别</strong>（例如，全部、详细、调试）和<strong>标志</strong>（例如，TF_COMPONENT、TF_DIAG）的集合。这些项目都在提供程序（Windows PowerShell 变量）中定义并传递到集中日志记录服务命令中。
    
      - 配置要从中收集日志的计算机和池。
    
      - 从选项“站点”（仅在该站点中的计算机上运行日志记录捕获）或“全局”（在部署中的所有计算机上运行日志记录捕获）定义日志记录会话的作用域。

集中日志记录服务功能极其强大，几乎可满足解决问题的所有需求 - 无论问题是大还是小。从根本原因分析到性能问题，集中日志记录服务对任何管理员都会是一个重要工具。所有示例都是使用 Lync Server 命令行管理程序显示的。集中日志记录服务有一个命令行组件，称为“CLSController.exe”。通过命令行工具本身为其提供了帮助。但是，您可以从命令行执行的功能集有限。利用 Lync Server 命令行管理程序，您可以访问规模大很多且可配置性高很多的功能集。在使用集中日志记录服务时，您应该总是将 Lync Server 命令行管理程序视为首要选择的方法。

本节中的主题说明了如何使用集中日志记录服务以及如何使用其众多功能的示例。

## 本部分内容

  - [集中日志记录服务的概述](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [使用 PowerShell 管理集中日志记录服务配置设置](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [了解日志记录服务配置设置](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [使用启动集中日志服务以捕获日志](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [对集中日志记录服务使用 Stop 命令](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [在由集中日志服务创建的捕获日志上使用搜索](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [从集中日志记录服务读取捕获的日志](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

