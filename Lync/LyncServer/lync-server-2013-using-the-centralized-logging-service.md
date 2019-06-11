---
title: 'Lync Server 2013: 使用集中式日志记录服务'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03b5e4e2582c7b1738f0a6072197643f4df99238
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中使用集中式日志记录服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

集中式日志记录服务是 Lync Server 2013 中的一项新功能。 它是以前版本中提供的**OCSLogger**和**OCSTracer**工具的增强替代项。 可以使用集中式日志记录服务执行以下任务:

  - 从单个位置和命令开始记录一台或多台计算机和池。

  - 从单个位置和命令停止记录一个或多个计算机和池。

  - 在一台或多台计算机和池上搜索日志, 查找单个位置和命令。 你可以定制搜索命令以返回已捕获并存储在所有计算机上的日志的整个聚合, 或返回捕获特定数据的已修整结果。

  - 按如下方式配置日志记录会话：
    
      - 定义一个**方案**，或使用默认方案。 集中式日志记录服务中的*方案*由作用域 (全局或网站)、方案名称 (用于标识方案的用途) 和一个或多个提供程序组成。 你可以在任何给定时间在计算机上运行两种方案。
    
      - 使用现有*提供程序*或创建新提供程序。*提供程序*定义日志记录会话收集的内容、详细信息级别、要跟踪的组件以及应用的标志。
        
        <div>
        

        > [!TIP]  
        > 如果您熟悉 OCSLogger，那就知道术语<EM>提供程序</EM>指的是<STRONG>组件</STRONG>（例如，S4、SIPStack）、<STRONG>日志记录类型</STRONG>（例如，WPP、EventLog 或 IIS 日志文件）、<STRONG>跟踪级别</STRONG>（例如，全部、详细、调试）和<STRONG>标志</STRONG>（例如，TF_COMPONENT、TF_DIAG）的集合。 这些项在提供程序 (Windows PowerShell 变量) 中定义并传递到集中式日志记录服务命令。

        
        </div>
    
      - 配置要从中收集日志的计算机和池。
    
      - 定义 "选项"**网站**中的日志记录会话的范围 (仅在该网站上的计算机上运行日志捕获) 或**全局**(在部署中的所有计算机上运行日志记录捕获)。

集中式日志记录服务极其强大, 可以满足几乎所有对解决问题的需要。 从根本原因分析到性能问题, 集中式日志记录服务可能是任何管理员的重要工具。 所有示例都使用 Lync Server 命令行管理程序进行显示。 有一个名为**CLSController**的集中日志记录服务的命令行组件。 通过工具本身为命令行工具提供帮助。 但是, 你可以从命令行执行一组有限的函数。 通过使用 Lync Server 命令行管理程序, 你可以访问更大、更多的可配置功能集。 在使用集中式日志记录服务时, 您应始终将 Lync Server Management Shell 视为第一和最重要的方法。

本部分中的主题介绍如何使用集中式日志记录服务以及如何使用其多项功能的示例。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的集中式日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [在 Lync Server 2013 中管理集中式日志记录服务配置设置](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [了解 Lync Server 2013 中的集中日志记录服务配置设置](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [使用 "开始使用集中式日志记录" 服务捕获 Lync Server 2013 中的日志](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [在 Lync Server 2013 中为集中式日志记录服务使用停止](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [对 Lync Server 2013 中的集中式日志记录服务创建的捕获日志使用搜索](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [从 Lync Server 2013 中的集中式日志记录服务读取捕获日志](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

