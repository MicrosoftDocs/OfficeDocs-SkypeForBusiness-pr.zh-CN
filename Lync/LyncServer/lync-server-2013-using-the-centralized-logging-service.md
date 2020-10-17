---
title: Lync Server 2013：使用集中日志记录服务
description: Lync Server 2013：使用集中日志记录服务。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8b9edf839de889e9f0b01c10311f6b5c70ced8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548518"
---
# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中使用集中日志记录服务

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

集中日志记录服务是 Lync Server 2013 中的一项新功能。 这是以前版本中提供的 **OCSLogger** 和 **OCSTracer** 工具的增强替代。 您可以使用集中日志记录服务执行以下任务：

  - 从一个位置使用单个命令在一台或多台计算机和池上开始日志记录。

  - 从一个位置使用单个命令在一台或多台计算机和池上停止日志记录。

  - 从一个位置使用单个命令在一台或多台计算机和池中搜索日志。您可以定制搜索命令以返回在所有计算机上捕获和存储的日志的整个聚合，或返回捕获特定数据的拼接结果。

  - 按如下方式配置日志记录会话：
    
      - 定义一个**方案**，或使用默认方案。 集中日志记录服务中的 *方案* 由作用域 (全局或站点) 组成，方案名称用于标识方案的用途和一个或多个提供程序。 您在任何给定的时间都可以在一台计算机上运行两个方案。
    
      - 使用现有*提供程序* 或创建新提供程序。*提供程序* 定义日志记录会话收集的内容、详细信息级别、要跟踪的组件以及应用的标志。
        
        <div>
        

        > [!TIP]  
        > 如果您熟悉 OCSLogger，那就知道术语<EM>提供程序</EM> 指的是<STRONG>组件</STRONG>（例如，S4、SIPStack）、<STRONG>日志记录类型</STRONG>（例如，WPP、EventLog 或 IIS 日志文件）、<STRONG>跟踪级别</STRONG>（例如，全部、详细、调试）和<STRONG>标志</STRONG>（例如，TF_COMPONENT、TF_DIAG）的集合。 这些项目在提供程序 (Windows PowerShell 变量) 并传递到集中日志记录服务命令中进行定义。

        
        </div>
    
      - 配置要从中收集日志的计算机和池。
    
      - 从选项“站点”****（仅在该站点中的计算机上运行日志记录捕获）或“全局”****（在部署中的所有计算机上运行日志记录捕获）定义日志记录会话的作用域。

集中式日志记录服务极其强大，可以满足几乎所有对解决问题的需求—大或小。 从根本原因分析到性能问题，集中日志记录服务可能是任何管理员的重要工具。 所有示例都是使用 Lync Server 命令行管理程序显示的。 有一个命令行组件，其中包含名为 **CLSController.exe**的集中日志记录服务。 通过命令行工具本身为其提供了帮助。 但是，您可以从命令行执行的功能集有限。 通过使用 Lync Server 命令行管理程序，可以访问更大和更多可配置的功能集。 在使用集中式日志记录服务时，应始终将 Lync Server 命令行管理程序视为第一个和最重要的方法。

本节中的主题介绍如何使用集中日志记录服务以及如何使用其多项功能的示例。

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的集中日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [在 Lync Server 2013 中管理集中日志记录服务配置设置](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [了解 Lync Server 2013 中的集中日志记录服务配置设置](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [使用 Start 实现集中日志记录服务以在 Lync Server 2013 中捕获日志](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [在 Lync Server 2013 中对集中日志记录服务使用停止](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [使用 Lync Server 2013 中的集中日志记录服务创建的捕获日志的搜索](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [从 Lync Server 2013 中的集中日志记录服务读取捕获日志](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

