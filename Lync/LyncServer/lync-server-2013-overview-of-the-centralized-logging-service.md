---
title: Lync Server 2013：集中日志记录服务概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c485293fe747a16cc9c2b392d053137105306da4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="1b13b-102">Lync Server 2013 中的集中日志记录服务概述</span><span class="sxs-lookup"><span data-stu-id="1b13b-102">Overview of the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b13b-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1b13b-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1b13b-104">集中日志记录服务旨在提供一种对数据的受控制集合的方法，其中包含广泛或较窄的范围。</span><span class="sxs-lookup"><span data-stu-id="1b13b-104">The Centralized Logging Service is designed to provide a means for controlled collection of data—with a broad or narrow scope.</span></span> <span data-ttu-id="1b13b-105">您可以从部署中的所有服务器同时收集数据，定义要跟踪的特定元素，设置跟踪标记，并从单个计算机或从所有服务器返回的所有数据的聚合中返回搜索结果。</span><span class="sxs-lookup"><span data-stu-id="1b13b-105">You can collect data from all servers in the deployment concurrently, define specific elements to trace, set trace flags and return search results from a single computer or an aggregation of all data from all servers.</span></span> <span data-ttu-id="1b13b-106">集中日志记录服务在部署中的所有服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="1b13b-106">The Centralized Logging Service runs on all servers in your deployment.</span></span> <span data-ttu-id="1b13b-107">集中日志记录服务的体系结构由以下代理和服务组成：</span><span class="sxs-lookup"><span data-stu-id="1b13b-107">The architecture of the Centralized Logging Service is comprised of the following agents and services:</span></span>

  - <span data-ttu-id="1b13b-108">*集中日志记录服务代理*   ClsAgent 是与控制器通信的服务可执行文件，它接收由管理员发出的命令。</span><span class="sxs-lookup"><span data-stu-id="1b13b-108">*Centralized Logging Service Agent*   ClsAgent.exe is the service executable that communicates with the controller and receives the commands that the controller is issued by the administrator.</span></span> <span data-ttu-id="1b13b-109">代理作为服务在每台 Lync Server 计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="1b13b-109">The agent is run as a service on each Lync Server computer.</span></span> <span data-ttu-id="1b13b-110">当代理收到命令时，它执行命令，将邮件发送到已定义的跟踪组件，并将跟踪日志写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="1b13b-110">When the agent receives a command, it executes the command, sends messages to the defined components for tracing, and writes the trace logs to disk.</span></span> <span data-ttu-id="1b13b-111">它还会读取其计算机的跟踪日志，并在请求时将跟踪数据发送回控制器。</span><span class="sxs-lookup"><span data-stu-id="1b13b-111">It also reads the trace logs for its computer and sends the trace data back to the controller when requested.</span></span> <span data-ttu-id="1b13b-112">ClsAgent 侦听以下端口上的命令： **tcp 50001**、 **Tcp 50002**和**tcp 50003**。</span><span class="sxs-lookup"><span data-stu-id="1b13b-112">The ClsAgent listens for commands on the following ports: **TCP 50001**, **TCP 50002**, and **TCP 50003**.</span></span>

  - <span data-ttu-id="1b13b-113">*集中日志记录服务控制器*   ClsControllerLib 是 Lync Server 命令行管理程序和 ClsController 的命令执行引擎。</span><span class="sxs-lookup"><span data-stu-id="1b13b-113">*Centralized Logging Service Controller*   ClsControllerLib.dll is the command execution engine for the Lync Server Management Shell and for ClsController.exe.</span></span> <span data-ttu-id="1b13b-114">CLSControllerLib 向 ClsAgent 发送启动、停止、刷新和搜索命令。</span><span class="sxs-lookup"><span data-stu-id="1b13b-114">CLSControllerLib.dll sends Start, Stop, Flush, and Search commands to the ClsAgent.</span></span> <span data-ttu-id="1b13b-115">当发送搜索命令时，生成的日志将返回到 ClsControllerLib 并进行聚合。</span><span class="sxs-lookup"><span data-stu-id="1b13b-115">When search commands are sent, the resulting logs are returned to the ClsControllerLib.dll and aggregated.</span></span> <span data-ttu-id="1b13b-116">控制器负责向代理发送命令，接收这些命令的状态，并在从搜索范围内的任何计算机上的所有代理返回时管理搜索日志文件数据，并将日志数据聚合到有意义的且已排序输出集。</span><span class="sxs-lookup"><span data-stu-id="1b13b-116">The controller is responsible for sending commands to the agent, receiving the status of those commands and managing the search log file data as it is returned from all agents on any computer in the search scope, and aggregating the log data into a meaningful and ordered output set.</span></span> <span data-ttu-id="1b13b-117">以下主题中的信息重点介绍了如何使用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="1b13b-117">The information in the following topics is focused on using the Lync Server Management Shell.</span></span> <span data-ttu-id="1b13b-118">ClsController 仅限于 Lync Server 命令行管理程序中提供的功能和功能的子集。</span><span class="sxs-lookup"><span data-stu-id="1b13b-118">ClsController.exe is limited to a subset of the features and functions that are available in the Lync Server Management Shell.</span></span> <span data-ttu-id="1b13b-119">在命令行中，可通过在默认的目录 C： `ClsController` \\Program Files\\Common files\\Microsoft Lync Server 2013\\ClsAgent 中键入 ClsController 帮助。</span><span class="sxs-lookup"><span data-stu-id="1b13b-119">Help for ClsController.exe is available at the command line by typing `ClsController` in the default directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\ClsAgent.</span></span>

<span data-ttu-id="1b13b-120">**ClsController 到 ClsAgent 的通信**</span><span class="sxs-lookup"><span data-stu-id="1b13b-120">**ClsController communications to ClsAgent**</span></span>

<span data-ttu-id="1b13b-121">![CLSController 和 CLSAgent 之间的关系。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController 和 CLSAgent 之间的关系。")</span><span class="sxs-lookup"><span data-stu-id="1b13b-121">![Relationship between CLSController and CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relationship between CLSController and CLSAgent.")</span></span>

<span data-ttu-id="1b13b-122">您可以使用 Windows Server 命令行界面或 Lync Server 命令行管理程序发出命令。</span><span class="sxs-lookup"><span data-stu-id="1b13b-122">You issue commands using the Windows Server command-line interface or using the Lync Server Management Shell.</span></span> <span data-ttu-id="1b13b-123">命令在您登录到的计算机上执行，并将其发送到您的部署中的 ClsAgent 本地或其他计算机和池。</span><span class="sxs-lookup"><span data-stu-id="1b13b-123">The commands are executed on the computer you are logged in to and sent to the ClsAgent locally or to the other computers and pools in your deployment.</span></span>

<span data-ttu-id="1b13b-124">ClsAgent 维护全部的索引文件。在本地计算机上缓存文件。</span><span class="sxs-lookup"><span data-stu-id="1b13b-124">ClsAgent maintains an index file of all .CACHE files that it has on the local machine.</span></span> <span data-ttu-id="1b13b-125">ClsAgent 将其分配给它们，以便在选项 80 CacheFileLocalFolders 定义的各个卷上均匀分布这些卷（即，本地缓存位置和百分比可使用**new-csclsconfiguration** cmdlet 进行配置）。</span><span class="sxs-lookup"><span data-stu-id="1b13b-125">ClsAgent allocates them so that they are evenly distributed across volumes defined by the option CacheFileLocalFolders, never consuming more than 80% of each volume (that is, the local cache location and the percentage is configurable using the **Set-CsClsConfiguration** cmdlet).</span></span> <span data-ttu-id="1b13b-126">ClsAgent 还负责将旧的缓存事件跟踪日志（.etl）文件从本地计算机中注销。</span><span class="sxs-lookup"><span data-stu-id="1b13b-126">ClsAgent is also responsible for aging old cached event trace log (.etl) files off the local machine.</span></span> <span data-ttu-id="1b13b-127">两周后（即使用**new-csclsconfiguration** cmdlet 可配置的时间范围），这些文件将被复制到文件共享，并从本地计算机中删除。</span><span class="sxs-lookup"><span data-stu-id="1b13b-127">After two weeks (that is, the timeframe is configurable using the **Set-CsClsConfiguration** cmdlet) these files are copied to a file share and deleted from the local computer.</span></span> <span data-ttu-id="1b13b-128">有关详细信息，请参阅[new-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="1b13b-128">For details, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration).</span></span> <span data-ttu-id="1b13b-129">收到搜索请求时，搜索条件将用于选择一组缓存的 .etl 文件，以根据代理维护的索引中的值执行搜索。</span><span class="sxs-lookup"><span data-stu-id="1b13b-129">When a search request is received, the search criteria is used to select the set of cached .etl files to perform the search based on the values in the index maintained by the agent.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b13b-130">从本地计算机移动到文件共享的文件可以通过 ClsAgent 进行搜索。</span><span class="sxs-lookup"><span data-stu-id="1b13b-130">Files that are moved to the file share from the local computer can be searched by ClsAgent.</span></span> <span data-ttu-id="1b13b-131">一旦 ClsAgent 将文件移动到文件共享，ClsAgent 将不会维护文件的老化和删除。</span><span class="sxs-lookup"><span data-stu-id="1b13b-131">Once ClsAgent moves the files to the file share, the aging and removal of files is not maintained by ClsAgent.</span></span> <span data-ttu-id="1b13b-132">应定义管理任务以监视文件共享中的文件大小，并将其删除或存档。</span><span class="sxs-lookup"><span data-stu-id="1b13b-132">You should define an administrative task to monitor the size of the files in the file share and delete them or archive them.</span></span>



</div>

<span data-ttu-id="1b13b-133">可以使用各种工具读取和分析生成的日志文件，其中包括**snooper.exe**和可读取文本文件的任何工具（如**notepad.exe**）。</span><span class="sxs-lookup"><span data-stu-id="1b13b-133">The resulting log files can be read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="1b13b-134">Snooper.exe 是 Lync Server 2013 调试工具的一部分，可从[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)下载 Web。</span><span class="sxs-lookup"><span data-stu-id="1b13b-134">Snooper.exe is part of the Lync Server 2013 Debug Tools and is available as a Web download from [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257).</span></span>

<span data-ttu-id="1b13b-135">与 OCSLogger 一样，集中日志记录服务有多个要跟踪的组件，并提供了选择 flags 的选项，\_如 tf COMPONENT\_和 tf settings。</span><span class="sxs-lookup"><span data-stu-id="1b13b-135">Like OCSLogger, the Centralized Logging Service has several components to trace against, and provides options to select flags, such as TF\_COMPONENT and TF\_DIAG.</span></span> <span data-ttu-id="1b13b-136">集中日志记录服务还保留 OCSLogger 的日志记录级别选项。</span><span class="sxs-lookup"><span data-stu-id="1b13b-136">Centralized Logging Service also retains the logging level options of OCSLogger.</span></span>

<span data-ttu-id="1b13b-137">在命令行 ClsController 中使用 Lync Server 命令行管理程序的最重要的优势在于，您可以使用针对问题空间、自定义标记和日志记录级别的选定提供程序来配置和定义新方案。</span><span class="sxs-lookup"><span data-stu-id="1b13b-137">The most important advantage to using the Lync Server Management Shell over the command-line ClsController is that you can configure and define new scenarios using selected providers that target the problem space, custom flags, and logging levels.</span></span> <span data-ttu-id="1b13b-138">可用于 ClsController 的方案仅限于为可执行文件定义的方案。</span><span class="sxs-lookup"><span data-stu-id="1b13b-138">The scenarios available to ClsController are limited to those that are defined for the executable.</span></span>

<span data-ttu-id="1b13b-139">在以前的版本中，提供了 OCSLogger，以使管理员和支持人员能够从部署中的计算机收集跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="1b13b-139">In previous versions, OCSLogger.exe was provided to enable administrators and support personnel to collect trace files from computers in the deployment.</span></span> <span data-ttu-id="1b13b-140">OCSLogger 对于其所有优势而言都存在缺陷。</span><span class="sxs-lookup"><span data-stu-id="1b13b-140">OCSLogger, for all of its strengths, had a shortcoming.</span></span> <span data-ttu-id="1b13b-141">在给定时间，您只能在一台计算机上收集日志。</span><span class="sxs-lookup"><span data-stu-id="1b13b-141">You could only collect logs on one computer at a given time.</span></span> <span data-ttu-id="1b13b-142">您可以通过使用 OCSLogger 的单独副本登录到多台计算机，但最终要使用多个日志，而不是聚合结果的简单方法。</span><span class="sxs-lookup"><span data-stu-id="1b13b-142">You could log on to multiple computers by using separate copies of OCSLogger, but you ended up with multiple logs and no easy way to aggregate the results.</span></span>

<span data-ttu-id="1b13b-143">当用户请求日志搜索时，ClsController 将确定要将请求发送到的计算机（即，根据所选的方案）。</span><span class="sxs-lookup"><span data-stu-id="1b13b-143">When a user requests a log search, the ClsController determines which machines to send the request to (that is, based on the scenarios selected).</span></span> <span data-ttu-id="1b13b-144">它还确定是否需要将搜索发送到保存的 .etl 文件所在的文件共享。</span><span class="sxs-lookup"><span data-stu-id="1b13b-144">It also determines whether the search needs to be sent to the file share where the saved .etl files are located.</span></span> <span data-ttu-id="1b13b-145">当搜索结果返回到 ClsController 时，该控制器会将结果合并到一个显示给用户的单个按时间排序的结果集。</span><span class="sxs-lookup"><span data-stu-id="1b13b-145">When the search results are returned to the ClsController, the controller merges the results into a single time-ordered result set that is presented to the user.</span></span> <span data-ttu-id="1b13b-146">用户可以将搜索结果保存到本地计算机，以供进一步分析。</span><span class="sxs-lookup"><span data-stu-id="1b13b-146">Users can save the search results to their local machine for further analysis.</span></span>

<span data-ttu-id="1b13b-147">启动日志记录会话时，将指定与您尝试解决的问题相关的方案。</span><span class="sxs-lookup"><span data-stu-id="1b13b-147">When you start a logging session, you specify scenarios that are relative to the problem that you are trying to resolve.</span></span> <span data-ttu-id="1b13b-148">您可以随时运行两个方案。</span><span class="sxs-lookup"><span data-stu-id="1b13b-148">You can have two scenarios running at any time.</span></span> <span data-ttu-id="1b13b-149">这两种方案中的一种应是 AlwaysOn 方案。</span><span class="sxs-lookup"><span data-stu-id="1b13b-149">One of these two scenarios should be the AlwaysOn scenario.</span></span> <span data-ttu-id="1b13b-150">顾名思义，它应始终在您的部署中运行，并收集所有计算机、池和组件的信息。</span><span class="sxs-lookup"><span data-stu-id="1b13b-150">As the name implies, it should always be running in your deployment, collecting information on all computers, pools, and components.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1b13b-151">默认情况下，AlwaysOn 方案未在您的部署中运行。</span><span class="sxs-lookup"><span data-stu-id="1b13b-151">By default, the AlwaysOn scenario is not running in your deployment.</span></span> <span data-ttu-id="1b13b-152">您必须显式启动方案。</span><span class="sxs-lookup"><span data-stu-id="1b13b-152">You must explicitly start the scenario.</span></span> <span data-ttu-id="1b13b-153">启动后，它将继续运行，直到显式停止，并且运行状态将在计算机重新启动后保持。</span><span class="sxs-lookup"><span data-stu-id="1b13b-153">Once started, it will continue to run until explicitly stopped, and the running state will persist through reboots of the computers.</span></span> <span data-ttu-id="1b13b-154">有关启动和停止方案的详细信息，请参阅<A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">使用 Start For 集中日志记录服务捕获 Lync server 2013 中的日志</A>和<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 lync Server 2013 中使用集中日志记录服务的停止</A>。</span><span class="sxs-lookup"><span data-stu-id="1b13b-154">For details on starting and stopping scenarios, see <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</A> and <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1b13b-155">出现问题时，请启动与报告的问题相关的第二个方案。</span><span class="sxs-lookup"><span data-stu-id="1b13b-155">When a problem occurs, start a second scenario that relates to the problem reported.</span></span> <span data-ttu-id="1b13b-156">重现该问题，并停止第二个方案的日志记录。</span><span class="sxs-lookup"><span data-stu-id="1b13b-156">Reproduce the problem, and stop the logging for the second scenario.</span></span> <span data-ttu-id="1b13b-157">相对于报告的问题开始进行日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1b13b-157">Begin your log searches relative to the problem reported.</span></span> <span data-ttu-id="1b13b-158">日志的聚合集合将生成一个日志文件，其中包含来自网站中的所有计算机或部署全局范围的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="1b13b-158">The aggregated collection of logs produces a log file that contains trace messages from all computers in your site or global scope of your deployment.</span></span> <span data-ttu-id="1b13b-159">如果搜索返回的数据多于您可以 feasibly 分析的数据（通常称为噪声比率过高），则使用较窄的参数运行另一个搜索。</span><span class="sxs-lookup"><span data-stu-id="1b13b-159">If the search returns more data than you can feasibly analyze (typically known as a signal-to-noise ratio, where the noise is too high), you run another search with narrower parameters.</span></span> <span data-ttu-id="1b13b-160">此时，您可以开始注意显示的模式，并可帮助您更清楚地关注问题。</span><span class="sxs-lookup"><span data-stu-id="1b13b-160">At this point, you can begin to notice patterns that show up and can help you get a clearer focus on the problem.</span></span> <span data-ttu-id="1b13b-161">最终，在执行几个改进的搜索之后，您可以找到与该问题相关的数据，并确定根本原因。</span><span class="sxs-lookup"><span data-stu-id="1b13b-161">Ultimately, after you perform a couple of refined searches you can find data that is relevant to the problem and figure out the root cause.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1b13b-162">在 Lync Server 中出现问题的情况下，请首先询问自己 "我已经知道问题是什么？"。</span><span class="sxs-lookup"><span data-stu-id="1b13b-162">When presented with a problem scenario in Lync Server, start by asking yourself “What do I already know about the problem?”</span></span> <span data-ttu-id="1b13b-163">如果您量化问题边界，则可以在 Lync Server 中消除大部分操作实体的组成部分。</span><span class="sxs-lookup"><span data-stu-id="1b13b-163">If you quantify the problem boundaries, you can eliminate a large part of the operational entities in Lync Server.</span></span><BR><span data-ttu-id="1b13b-164">考虑一个您知道用户在查找联系人时没有获取当前结果的示例方案。</span><span class="sxs-lookup"><span data-stu-id="1b13b-164">Consider an example scenario where you know that users are not getting current results when looking for a contact.</span></span> <span data-ttu-id="1b13b-165">在媒体组件、企业语音、会议和许多其他组件中找不到问题。</span><span class="sxs-lookup"><span data-stu-id="1b13b-165">There is no point in looking for problems in the media components, Enterprise Voice, conferencing, and a number of other components.</span></span> <span data-ttu-id="1b13b-166">您可能不知道问题实际上是什么：在客户端上，或者是服务器端问题？</span><span class="sxs-lookup"><span data-stu-id="1b13b-166">What you may not know is where the problem actually is: on the client, or is this a server-side problem?</span></span> <span data-ttu-id="1b13b-167">联系人通过用户复制程序从 Active Directory 收集，并通过通讯簿服务器（ABServer）传递到客户端。</span><span class="sxs-lookup"><span data-stu-id="1b13b-167">Contacts are collected from Active Directory by the User Replicator and delivered to the client by way of the Address Book Server (ABServer).</span></span> <span data-ttu-id="1b13b-168">ABServer 从 RTC 数据库中获取其更新（用户副本在其中写入它们），并将其收集到通讯簿文件中（默认– 1:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="1b13b-168">The ABServer gets its updates from the RTC database (where User Replicator wrote them) and collects them into address book files, by default – 1:30 AM.</span></span> <span data-ttu-id="1b13b-169">Lync Server 客户端按随机计划检索新的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="1b13b-169">The Lync Server clients retrieve the new address book on a randomized schedule.</span></span> <span data-ttu-id="1b13b-170">由于您知道进程的工作方式，因此您可以将搜索范围减少到与从 Active Directory 收集的数据相关的问题（用户复制程序从 Active Directory 中收集）的潜在原因，ABServer 不检索和创建通讯簿文件，或者客户端下载通讯簿文件。</span><span class="sxs-lookup"><span data-stu-id="1b13b-170">Because you know how the process works, you can reduce your search for the potential cause to an issue related to data being collected from Active Directory by the User Replicator, the ABServer not retrieving and creating the address book files, or the clients not downloading the address book file.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

