---
title: Lync Server 2013：检查事件日志
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 862d419d9db5d8465b3507c40fde32acd01bb659
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="6d72f-102">在 Lync Server 2013 中检查事件日志</span><span class="sxs-lookup"><span data-stu-id="6d72f-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d72f-103">_**主题上次修改时间：** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="6d72f-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="6d72f-104">你可以使用[Windows 事件查看器](http://go.microsoft.com/fwlink/p/?linkid=314067)查看事件日志，获取有关服务失败、AD DS 中的复制错误以及有关系统资源（如虚拟内存和磁盘空间）的警告的信息。</span><span class="sxs-lookup"><span data-stu-id="6d72f-104">You can use [Windows Event Viewer](http://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="6d72f-105">事件查看器包含在 Windows Server 2008 和2012中。</span><span class="sxs-lookup"><span data-stu-id="6d72f-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="6d72f-106">在 Lync Server 2013 日志记录工具中，当你结束调试会话时，单击 "**分析日志文件**" 以使用 Snooper 工具查看日志文件。</span><span class="sxs-lookup"><span data-stu-id="6d72f-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="6d72f-107">事件查看器在计算机上维护有关应用程序、安全性和系统事件的日志。</span><span class="sxs-lookup"><span data-stu-id="6d72f-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="6d72f-108">Lync Server 2013 和 Windows 报告警告和错误条件到事件日志。</span><span class="sxs-lookup"><span data-stu-id="6d72f-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="6d72f-109">因此，请每天查看事件日志。</span><span class="sxs-lookup"><span data-stu-id="6d72f-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="6d72f-110">使用事件查看器执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d72f-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="6d72f-111">查看和管理事件日志。</span><span class="sxs-lookup"><span data-stu-id="6d72f-111">View and manage event logs.</span></span>

  - <span data-ttu-id="6d72f-112">获取有关必须解决的硬件、软件和系统问题的信息。</span><span class="sxs-lookup"><span data-stu-id="6d72f-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="6d72f-113">确定需要未来行动的趋势。</span><span class="sxs-lookup"><span data-stu-id="6d72f-113">Identify trends that require future action.</span></span>

<span data-ttu-id="6d72f-114">在 Windows Server 操作系统上运行 Lync Server 的服务器在以下四种类型的日志中记录事件：</span><span class="sxs-lookup"><span data-stu-id="6d72f-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="6d72f-115">**应用**程序日志应用程序日志包含由应用程序或程序记录的事件。   </span><span class="sxs-lookup"><span data-stu-id="6d72f-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="6d72f-116">开发人员确定要记录哪些事件。</span><span class="sxs-lookup"><span data-stu-id="6d72f-116">Developers determine which events to log.</span></span> <span data-ttu-id="6d72f-117">例如，数据库程序可能会在应用程序日志中记录文件错误。</span><span class="sxs-lookup"><span data-stu-id="6d72f-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="6d72f-118">大多数 Lync Server 2013 相关事件都显示在应用程序日志中。</span><span class="sxs-lookup"><span data-stu-id="6d72f-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="6d72f-119">**安全**   日志记录除与资源使用相关的事件（如创建、打开或删除文件或其他对象）以外的有效和无效登录尝试等事件。</span><span class="sxs-lookup"><span data-stu-id="6d72f-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="6d72f-120">例如，如果启用了登录审核，登录到系统的尝试将记录在安全日志中。</span><span class="sxs-lookup"><span data-stu-id="6d72f-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="6d72f-121">**系统日志**   系统日志包含 Windows 系统组件记录的事件。</span><span class="sxs-lookup"><span data-stu-id="6d72f-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="6d72f-122">例如，在启动过程中要加载的驱动程序或其他系统组件失败将记录在系统日志中。</span><span class="sxs-lookup"><span data-stu-id="6d72f-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="6d72f-123">由系统组件记录的事件类型由服务器预先确定。</span><span class="sxs-lookup"><span data-stu-id="6d72f-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="6d72f-124">**Lync Server 2013**   记录工具记录与身份验证、连接和用户操作相关的重要事件。</span><span class="sxs-lookup"><span data-stu-id="6d72f-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="6d72f-125">启用诊断日志记录后，您可以在事件查看器中查看日志条目。</span><span class="sxs-lookup"><span data-stu-id="6d72f-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d72f-126">我们不建议你使用最大日志记录设置，除非你被指示通过 Microsoft 客户支持服务执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6d72f-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="6d72f-127">最大日志消耗大量的资源，并且可以提供许多 "误报"，即仅在最大日志记录中记录的错误，而不是问题的原因。</span><span class="sxs-lookup"><span data-stu-id="6d72f-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="6d72f-128">我们还建议您不要永久启用诊断日志记录。</span><span class="sxs-lookup"><span data-stu-id="6d72f-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="6d72f-129">仅在进行故障排除时使用。</span><span class="sxs-lookup"><span data-stu-id="6d72f-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="6d72f-130">在每个事件查看器日志中，Lync Server 2013 记录信息、警告和错误事件。</span><span class="sxs-lookup"><span data-stu-id="6d72f-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="6d72f-131">密切监视这些日志，跟踪 Lync Server 2013 服务器上正在执行的事务类型。</span><span class="sxs-lookup"><span data-stu-id="6d72f-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="6d72f-132">你应定期将日志存档或使用自动滚动更新以避免空间耗尽。</span><span class="sxs-lookup"><span data-stu-id="6d72f-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="6d72f-133">由于日志文件可以占用有限数量的空间，增加日志大小（例如，到 50 MB），并将其设置为 "覆盖"，以便 Lync Server 2013 服务器可以继续写入新事件。</span><span class="sxs-lookup"><span data-stu-id="6d72f-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="6d72f-134">还可以使用以下工具和技术自动执行事件日志管理：</span><span class="sxs-lookup"><span data-stu-id="6d72f-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="6d72f-135">System Center Operations Manager 监视 Lync Server 2013 服务器的运行状况和使用情况。</span><span class="sxs-lookup"><span data-stu-id="6d72f-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="6d72f-136">适用于 Operations Manager 的 Lync Server 2013 管理包通过为运行 Lync Server 2013 的服务器提供专用监视来扩展操作管理器。</span><span class="sxs-lookup"><span data-stu-id="6d72f-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="6d72f-137">Operations Manager 的 Lync Server 2013 管理包监控 Lync Server 2013 的标准版和企业版。</span><span class="sxs-lookup"><span data-stu-id="6d72f-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="6d72f-138">此版本还包含以前是单独的管理包的体验质量（QoE）管理包。</span><span class="sxs-lookup"><span data-stu-id="6d72f-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="6d72f-139">受监视的类型为 QoE 的事件日志条目、性能计数器和状态监视。</span><span class="sxs-lookup"><span data-stu-id="6d72f-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="6d72f-140">此版本的管理包仅监视 Lync Server 2013 和2010，无法用于监视 Office 通信服务器2007。</span><span class="sxs-lookup"><span data-stu-id="6d72f-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="6d72f-141">管理包提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="6d72f-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="6d72f-142">指示影响事件的服务的警报</span><span class="sxs-lookup"><span data-stu-id="6d72f-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="6d72f-143">指示配置和其他非服务影响问题的警报</span><span class="sxs-lookup"><span data-stu-id="6d72f-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="6d72f-144">Lync Server 服务的状态监视</span><span class="sxs-lookup"><span data-stu-id="6d72f-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="6d72f-145">产品知识：确定的问题的原因和解决方法</span><span class="sxs-lookup"><span data-stu-id="6d72f-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="6d72f-146">有关 Lync Server 2013 管理包的详细信息，请参阅[通过 System Center Operations Manager 监视 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="6d72f-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="6d72f-147">**事件梳理**   事件梳理工具将从多台计算机的事件日志中收集特定事件到一个中心位置。</span><span class="sxs-lookup"><span data-stu-id="6d72f-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="6d72f-148">它使你可以仅报告它指定的事件 Id 或事件源。</span><span class="sxs-lookup"><span data-stu-id="6d72f-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="6d72f-149">有关事件梳理的详细信息，请参阅[帐户锁定和管理工具](http://go.microsoft.com/fwlink/?linkid=35607)网站。</span><span class="sxs-lookup"><span data-stu-id="6d72f-149">For more information about Event Comb, see the [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="6d72f-150">\*\*\*\*   Windows Server 2012 中的事件触发器可以在 windows 事件查看器中 "将任务附加到此事件" ——管理员可以运行程序、发送电子邮件或显示屏幕消息。</span><span class="sxs-lookup"><span data-stu-id="6d72f-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="6d72f-151">有关此功能的详细信息，请参阅 Windows Server 2008 R2 主题[运行任务以响应给定的事件](http://technet.microsoft.com/en-us/library/cc748900.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6d72f-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span></span> <span data-ttu-id="6d72f-152">你还可以使用命令行工具（如 "Eventtrigger"）创建和查询事件日志，并将程序与特定的已记录事件相关联。</span><span class="sxs-lookup"><span data-stu-id="6d72f-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="6d72f-153">通过使用 Eventtriggers，你可以创建在特定事件发生时运行程序的事件触发器。</span><span class="sxs-lookup"><span data-stu-id="6d72f-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6d72f-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d72f-154">See Also</span></span>


[<span data-ttu-id="6d72f-155">Windows 事件查看器</span><span class="sxs-lookup"><span data-stu-id="6d72f-155">Windows Event Viewer</span></span>](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

