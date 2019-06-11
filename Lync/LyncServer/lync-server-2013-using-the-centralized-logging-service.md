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

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="3974b-102">在 Lync Server 2013 中使用集中式日志记录服务</span><span class="sxs-lookup"><span data-stu-id="3974b-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3974b-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3974b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3974b-104">集中式日志记录服务是 Lync Server 2013 中的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="3974b-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="3974b-105">它是以前版本中提供的**OCSLogger**和**OCSTracer**工具的增强替代项。</span><span class="sxs-lookup"><span data-stu-id="3974b-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="3974b-106">可以使用集中式日志记录服务执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="3974b-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="3974b-107">从单个位置和命令开始记录一台或多台计算机和池。</span><span class="sxs-lookup"><span data-stu-id="3974b-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="3974b-108">从单个位置和命令停止记录一个或多个计算机和池。</span><span class="sxs-lookup"><span data-stu-id="3974b-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="3974b-109">在一台或多台计算机和池上搜索日志, 查找单个位置和命令。</span><span class="sxs-lookup"><span data-stu-id="3974b-109">Search logs on one or more computers and pools for a single location and command.</span></span> <span data-ttu-id="3974b-110">你可以定制搜索命令以返回已捕获并存储在所有计算机上的日志的整个聚合, 或返回捕获特定数据的已修整结果。</span><span class="sxs-lookup"><span data-stu-id="3974b-110">You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="3974b-111">按如下方式配置日志记录会话：</span><span class="sxs-lookup"><span data-stu-id="3974b-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="3974b-112">定义一个**方案**，或使用默认方案。</span><span class="sxs-lookup"><span data-stu-id="3974b-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="3974b-113">集中式日志记录服务中的*方案*由作用域 (全局或网站)、方案名称 (用于标识方案的用途) 和一个或多个提供程序组成。</span><span class="sxs-lookup"><span data-stu-id="3974b-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="3974b-114">你可以在任何给定时间在计算机上运行两种方案。</span><span class="sxs-lookup"><span data-stu-id="3974b-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="3974b-p104">使用现有*提供程序*或创建新提供程序。*提供程序*定义日志记录会话收集的内容、详细信息级别、要跟踪的组件以及应用的标志。</span><span class="sxs-lookup"><span data-stu-id="3974b-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="3974b-117">如果您熟悉 OCSLogger，那就知道术语<EM>提供程序</EM>指的是<STRONG>组件</STRONG>（例如，S4、SIPStack）、<STRONG>日志记录类型</STRONG>（例如，WPP、EventLog 或 IIS 日志文件）、<STRONG>跟踪级别</STRONG>（例如，全部、详细、调试）和<STRONG>标志</STRONG>（例如，TF_COMPONENT、TF_DIAG）的集合。</span><span class="sxs-lookup"><span data-stu-id="3974b-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="3974b-118">这些项在提供程序 (Windows PowerShell 变量) 中定义并传递到集中式日志记录服务命令。</span><span class="sxs-lookup"><span data-stu-id="3974b-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="3974b-119">配置要从中收集日志的计算机和池。</span><span class="sxs-lookup"><span data-stu-id="3974b-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="3974b-120">定义 "选项"**网站**中的日志记录会话的范围 (仅在该网站上的计算机上运行日志捕获) 或**全局**(在部署中的所有计算机上运行日志记录捕获)。</span><span class="sxs-lookup"><span data-stu-id="3974b-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="3974b-121">集中式日志记录服务极其强大, 可以满足几乎所有对解决问题的需要。</span><span class="sxs-lookup"><span data-stu-id="3974b-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="3974b-122">从根本原因分析到性能问题, 集中式日志记录服务可能是任何管理员的重要工具。</span><span class="sxs-lookup"><span data-stu-id="3974b-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="3974b-123">所有示例都使用 Lync Server 命令行管理程序进行显示。</span><span class="sxs-lookup"><span data-stu-id="3974b-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="3974b-124">有一个名为**CLSController**的集中日志记录服务的命令行组件。</span><span class="sxs-lookup"><span data-stu-id="3974b-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="3974b-125">通过工具本身为命令行工具提供帮助。</span><span class="sxs-lookup"><span data-stu-id="3974b-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="3974b-126">但是, 你可以从命令行执行一组有限的函数。</span><span class="sxs-lookup"><span data-stu-id="3974b-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="3974b-127">通过使用 Lync Server 命令行管理程序, 你可以访问更大、更多的可配置功能集。</span><span class="sxs-lookup"><span data-stu-id="3974b-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="3974b-128">在使用集中式日志记录服务时, 您应始终将 Lync Server Management Shell 视为第一和最重要的方法。</span><span class="sxs-lookup"><span data-stu-id="3974b-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="3974b-129">本部分中的主题介绍如何使用集中式日志记录服务以及如何使用其多项功能的示例。</span><span class="sxs-lookup"><span data-stu-id="3974b-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3974b-130">本节内容</span><span class="sxs-lookup"><span data-stu-id="3974b-130">In This Section</span></span>

  - [<span data-ttu-id="3974b-131">Lync Server 2013 中的集中式日志记录服务概述</span><span class="sxs-lookup"><span data-stu-id="3974b-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="3974b-132">在 Lync Server 2013 中管理集中式日志记录服务配置设置</span><span class="sxs-lookup"><span data-stu-id="3974b-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="3974b-133">了解 Lync Server 2013 中的集中日志记录服务配置设置</span><span class="sxs-lookup"><span data-stu-id="3974b-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="3974b-134">使用 "开始使用集中式日志记录" 服务捕获 Lync Server 2013 中的日志</span><span class="sxs-lookup"><span data-stu-id="3974b-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="3974b-135">在 Lync Server 2013 中为集中式日志记录服务使用停止</span><span class="sxs-lookup"><span data-stu-id="3974b-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="3974b-136">对 Lync Server 2013 中的集中式日志记录服务创建的捕获日志使用搜索</span><span class="sxs-lookup"><span data-stu-id="3974b-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="3974b-137">从 Lync Server 2013 中的集中式日志记录服务读取捕获日志</span><span class="sxs-lookup"><span data-stu-id="3974b-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

