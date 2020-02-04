---
title: Lync Server 2013：集中式日志记录服务概述
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
ms.openlocfilehash: 1460699b6516ab4e510c9715b2464ce442466faa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="943d5-102">Lync Server 2013 中的集中式日志记录服务概述</span><span class="sxs-lookup"><span data-stu-id="943d5-102">Overview of the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="943d5-103">_**主题上次修改时间：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="943d5-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="943d5-104">集中式日志记录服务旨在为数据的受控制集合提供一种方法，范围较广，范围较窄。</span><span class="sxs-lookup"><span data-stu-id="943d5-104">The Centralized Logging Service is designed to provide a means for controlled collection of data—with a broad or narrow scope.</span></span> <span data-ttu-id="943d5-105">你可以同时从部署中的所有服务器收集数据，定义要跟踪的特定元素，设置跟踪标记并从单个计算机或所有服务器的所有数据的聚合中返回搜索结果。</span><span class="sxs-lookup"><span data-stu-id="943d5-105">You can collect data from all servers in the deployment concurrently, define specific elements to trace, set trace flags and return search results from a single computer or an aggregation of all data from all servers.</span></span> <span data-ttu-id="943d5-106">集中式日志记录服务在部署中的所有服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="943d5-106">The Centralized Logging Service runs on all servers in your deployment.</span></span> <span data-ttu-id="943d5-107">集中式日志记录服务的体系结构由以下代理和服务组成：</span><span class="sxs-lookup"><span data-stu-id="943d5-107">The architecture of the Centralized Logging Service is comprised of the following agents and services:</span></span>

  - <span data-ttu-id="943d5-108">*集中式日志记录服务代理*   ClsAgent 是与控制器通信并接收由管理员发出的命令的服务可执行文件。</span><span class="sxs-lookup"><span data-stu-id="943d5-108">*Centralized Logging Service Agent*   ClsAgent.exe is the service executable that communicates with the controller and receives the commands that the controller is issued by the administrator.</span></span> <span data-ttu-id="943d5-109">代理以服务的形式在每台 Lync 服务器计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="943d5-109">The agent is run as a service on each Lync Server computer.</span></span> <span data-ttu-id="943d5-110">当代理收到命令时，它执行命令、将消息发送到已定义的跟踪组件，并将跟踪日志写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="943d5-110">When the agent receives a command, it executes the command, sends messages to the defined components for tracing, and writes the trace logs to disk.</span></span> <span data-ttu-id="943d5-111">它还会读取其计算机的跟踪日志，并在请求时将跟踪数据发送回控制器。</span><span class="sxs-lookup"><span data-stu-id="943d5-111">It also reads the trace logs for its computer and sends the trace data back to the controller when requested.</span></span> <span data-ttu-id="943d5-112">ClsAgent 侦听以下端口上的命令： **tcp 50001**、 **Tcp 50002**和**tcp 50003**。</span><span class="sxs-lookup"><span data-stu-id="943d5-112">The ClsAgent listens for commands on the following ports: **TCP 50001**, **TCP 50002**, and **TCP 50003**.</span></span>

  - <span data-ttu-id="943d5-113">*集中式日志记录服务控制器*   ClsControllerLib 是 Lync Server Management Shell 和 ClsController 的命令执行引擎。</span><span class="sxs-lookup"><span data-stu-id="943d5-113">*Centralized Logging Service Controller*   ClsControllerLib.dll is the command execution engine for the Lync Server Management Shell and for ClsController.exe.</span></span> <span data-ttu-id="943d5-114">CLSControllerLib 将启动、停止、刷新和搜索命令发送到 ClsAgent。</span><span class="sxs-lookup"><span data-stu-id="943d5-114">CLSControllerLib.dll sends Start, Stop, Flush, and Search commands to the ClsAgent.</span></span> <span data-ttu-id="943d5-115">发送搜索命令时，生成的日志将返回到 ClsControllerLib 并进行聚合。</span><span class="sxs-lookup"><span data-stu-id="943d5-115">When search commands are sent, the resulting logs are returned to the ClsControllerLib.dll and aggregated.</span></span> <span data-ttu-id="943d5-116">控制器负责向代理发送命令，接收这些命令的状态，并管理从搜索范围内任何计算机上的所有代理返回的搜索日志文件数据，并将日志数据聚合到有意义的排序中输出设置。</span><span class="sxs-lookup"><span data-stu-id="943d5-116">The controller is responsible for sending commands to the agent, receiving the status of those commands and managing the search log file data as it is returned from all agents on any computer in the search scope, and aggregating the log data into a meaningful and ordered output set.</span></span> <span data-ttu-id="943d5-117">以下主题中的信息重点介绍如何使用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="943d5-117">The information in the following topics is focused on using the Lync Server Management Shell.</span></span> <span data-ttu-id="943d5-118">ClsController 仅限于 Lync Server Management Shell 中可用的功能和功能的子集。</span><span class="sxs-lookup"><span data-stu-id="943d5-118">ClsController.exe is limited to a subset of the features and functions that are available in the Lync Server Management Shell.</span></span> <span data-ttu-id="943d5-119">在命令行中，通过在 "默认`ClsController`目录 C：\\程序文件\\" 中键入 "Microsoft Lync Server 2013\\\\ClsAgent" 常用文件，可在命令行中使用 ClsController 帮助。</span><span class="sxs-lookup"><span data-stu-id="943d5-119">Help for ClsController.exe is available at the command line by typing `ClsController` in the default directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\ClsAgent.</span></span>

<span data-ttu-id="943d5-120">**ClsController 与 ClsAgent 的通信**</span><span class="sxs-lookup"><span data-stu-id="943d5-120">**ClsController communications to ClsAgent**</span></span>

<span data-ttu-id="943d5-121">![CLSController 和 CLSAgent 之间的关系。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController 和 CLSAgent 之间的关系。")</span><span class="sxs-lookup"><span data-stu-id="943d5-121">![Relationship between CLSController and CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relationship between CLSController and CLSAgent.")</span></span>

<span data-ttu-id="943d5-122">使用 Windows Server 命令行界面发出命令，或使用 Lync Server Management Shell 发出命令。</span><span class="sxs-lookup"><span data-stu-id="943d5-122">You issue commands using the Windows Server command-line interface or using the Lync Server Management Shell.</span></span> <span data-ttu-id="943d5-123">这些命令将在您登录的计算机上执行，并将本地发送到 ClsAgent 或发送到部署中的其他计算机和池。</span><span class="sxs-lookup"><span data-stu-id="943d5-123">The commands are executed on the computer you are logged in to and sent to the ClsAgent locally or to the other computers and pools in your deployment.</span></span>

<span data-ttu-id="943d5-124">ClsAgent 维护其在本地计算机上具有的所有 .CACHE 文件的索引文件。</span><span class="sxs-lookup"><span data-stu-id="943d5-124">ClsAgent maintains an index file of all .CACHE files that it has on the local machine.</span></span> <span data-ttu-id="943d5-125">ClsAgent 将分配这些文件，使其均匀分布在由选项 CacheFileLocalFolders 定义的卷上，并且绝不会占用每个卷的 80% 以上的容量（即，可使用 **Set-CsClsConfiguration** cmdlet 配置本地缓存位置和百分比）。</span><span class="sxs-lookup"><span data-stu-id="943d5-125">ClsAgent allocates them so that they are evenly distributed across volumes defined by the option CacheFileLocalFolders, never consuming more than 80% of each volume (that is, the local cache location and the percentage is configurable using the **Set-CsClsConfiguration** cmdlet).</span></span> <span data-ttu-id="943d5-126">ClsAgent 还负责从本地计算机中清除旧的缓存事件跟踪日志 (.etl) 文件。</span><span class="sxs-lookup"><span data-stu-id="943d5-126">ClsAgent is also responsible for aging old cached event trace log (.etl) files off the local machine.</span></span> <span data-ttu-id="943d5-127">两周之后（即，可使用 **Set-CsClsConfiguration** cmdlet 配置时间范围时），会将这些文件复制到一个文件共享中并从本地计算机中删除它们。</span><span class="sxs-lookup"><span data-stu-id="943d5-127">After two weeks (that is, the timeframe is configurable using the **Set-CsClsConfiguration** cmdlet) these files are copied to a file share and deleted from the local computer.</span></span> <span data-ttu-id="943d5-128">有关详细信息，请参阅 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="943d5-128">For details, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration).</span></span> <span data-ttu-id="943d5-129">在收到一个搜索请求时，搜索条件将用于选择一组缓存的 .etl 文件以便根据代理所维护的索引中的值来执行搜索。</span><span class="sxs-lookup"><span data-stu-id="943d5-129">When a search request is received, the search criteria is used to select the set of cached .etl files to perform the search based on the values in the index maintained by the agent.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="943d5-p106">从本地计算机移至文件共享中的文件可通过 ClsAgent 进行搜索。一旦 ClsAgent 将这些文件移至文件共享中，ClsAgent 将不会维护文件的清楚和删除。您应定义一个管理任务来监控文件共享中的文件大小，并删除这些文件或对其进行存档。</span><span class="sxs-lookup"><span data-stu-id="943d5-p106">Files that are moved to the file share from the local computer can be searched by ClsAgent. Once ClsAgent moves the files to the file share, the aging and removal of files is not maintained by ClsAgent. You should define an administrative task to monitor the size of the files in the file share and delete them or archive them.</span></span>



</div>

<span data-ttu-id="943d5-133">可使用多种工具读取和分析生成的日志文件，其中包括 **Snooper.exe** 以及任何可读取文本文件的工具（例如 **Notepad.exe**）。</span><span class="sxs-lookup"><span data-stu-id="943d5-133">The resulting log files can be read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="943d5-134">Snooper 是 Lync Server 2013 调试工具的一部分，可从[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)下载 Web。</span><span class="sxs-lookup"><span data-stu-id="943d5-134">Snooper.exe is part of the Lync Server 2013 Debug Tools and is available as a Web download from [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257).</span></span>

<span data-ttu-id="943d5-135">与 OCSLogger 一样，集中式日志记录服务有多个要跟踪的组件，并提供选择标志的选项，\_如 tf 组件\_和 tf 诊断。</span><span class="sxs-lookup"><span data-stu-id="943d5-135">Like OCSLogger, the Centralized Logging Service has several components to trace against, and provides options to select flags, such as TF\_COMPONENT and TF\_DIAG.</span></span> <span data-ttu-id="943d5-136">集中式日志记录服务还保留 OCSLogger 的日志记录级别选项。</span><span class="sxs-lookup"><span data-stu-id="943d5-136">Centralized Logging Service also retains the logging level options of OCSLogger.</span></span>

<span data-ttu-id="943d5-137">在命令行 ClsController 上使用 Lync Server 管理外壳的最重要的好处是，你可以使用针对问题空间、自定义标记和日志记录级别的选定提供程序配置和定义新方案。</span><span class="sxs-lookup"><span data-stu-id="943d5-137">The most important advantage to using the Lync Server Management Shell over the command-line ClsController is that you can configure and define new scenarios using selected providers that target the problem space, custom flags, and logging levels.</span></span> <span data-ttu-id="943d5-138">对 ClsController 可用的方案仅为针对可执行文件定义的方案。</span><span class="sxs-lookup"><span data-stu-id="943d5-138">The scenarios available to ClsController are limited to those that are defined for the executable.</span></span>

<span data-ttu-id="943d5-p110">在早期版本中，提供了 OCSLogger.exe 以使管理员和支持人员能够从部署中的计算机中收集跟踪文件。尽管 OCSLogger 具有的优点不少，但它也有一个缺点。在给定时间内，您只能在一台计算机上收集日志。虽然可通过使用 OCSLogger 的独立副本来登录多台计算机，但最终将获得多个日志且无法轻松聚合结果。</span><span class="sxs-lookup"><span data-stu-id="943d5-p110">In previous versions, OCSLogger.exe was provided to enable administrators and support personnel to collect trace files from computers in the deployment. OCSLogger, for all of its strengths, had a shortcoming. You could only collect logs on one computer at a given time. You could log on to multiple computers by using separate copies of OCSLogger, but you ended up with multiple logs and no easy way to aggregate the results.</span></span>

<span data-ttu-id="943d5-p111">当用户请求一个日志搜索时，ClsController 将确定将请求发送到哪些计算机（即，基于选定方案）。它还确定是否需要将搜索发送到已保存的 .etl 文件所在的文件共享。当搜索结果返回到 ClsController 时，控制器会将结果合并到一个呈现给用户的按时间排序的结果集中。用户可以将搜索结果保存到其本地计算机中以供进一步分析。</span><span class="sxs-lookup"><span data-stu-id="943d5-p111">When a user requests a log search, the ClsController determines which machines to send the request to (that is, based on the scenarios selected). It also determines whether the search needs to be sent to the file share where the saved .etl files are located. When the search results are returned to the ClsController, the controller merges the results into a single time-ordered result set that is presented to the user. Users can save the search results to their local machine for further analysis.</span></span>

<span data-ttu-id="943d5-p112">在启动日志记录会话时，您指定与您尝试解决的问题相关的方案。可以随时运行两个方案，其中一个方案应为 AlwaysOn 方案。顾名思义，此方案应始终在部署中运行，并收集有关所有计算机、池和组件的信息。</span><span class="sxs-lookup"><span data-stu-id="943d5-p112">When you start a logging session, you specify scenarios that are relative to the problem that you are trying to resolve. You can have two scenarios running at any time. One of these two scenarios should be the AlwaysOn scenario. As the name implies, it should always be running in your deployment, collecting information on all computers, pools, and components.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="943d5-151">默认情况下，AlwaysOn 方案在部署中不会运行。</span><span class="sxs-lookup"><span data-stu-id="943d5-151">By default, the AlwaysOn scenario is not running in your deployment.</span></span> <span data-ttu-id="943d5-152">您必须显式启动此方案。</span><span class="sxs-lookup"><span data-stu-id="943d5-152">You must explicitly start the scenario.</span></span> <span data-ttu-id="943d5-153">一旦启动此方案，它就将继续运行直到被显式停止，并且在重新启动计算机的过程中持续保持运行状态。</span><span class="sxs-lookup"><span data-stu-id="943d5-153">Once started, it will continue to run until explicitly stopped, and the running state will persist through reboots of the computers.</span></span> <span data-ttu-id="943d5-154">有关启动和停止方案的详细信息，请参阅<A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">使用集中日志记录服务捕获 Lync server 2013 中的日志</A>和<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 lync Server 2013 中使用集中式日志记录服务的停止</A>。</span><span class="sxs-lookup"><span data-stu-id="943d5-154">For details on starting and stopping scenarios, see <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</A> and <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="943d5-p114">在出现问题时，启动与所报告的问题相关的另一个方案。重现该问题并停止针对该方案的日志记录。开始与所报告的问题相关的日志搜索。日志的聚合收集会生成一个日志文件，其中包含站点或全局范围部署中的所有计算机中的跟踪消息。如果搜索返回的数据多于可进行可行性分析的数据（通常称为信噪比，其中噪音过高），则可使用范围更小的参数运行另一个搜索。此时，您可以关注显示的模式并可帮助您准确了解问题。最后，在执行一组优化搜索后，您可以找到与该问题相关的数据并指出根本原因。</span><span class="sxs-lookup"><span data-stu-id="943d5-p114">When a problem occurs, start a second scenario that relates to the problem reported. Reproduce the problem, and stop the logging for the second scenario. Begin your log searches relative to the problem reported. The aggregated collection of logs produces a log file that contains trace messages from all computers in your site or global scope of your deployment. If the search returns more data than you can feasibly analyze (typically known as a signal-to-noise ratio, where the noise is too high), you run another search with narrower parameters. At this point, you can begin to notice patterns that show up and can help you get a clearer focus on the problem. Ultimately, after you perform a couple of refined searches you can find data that is relevant to the problem and figure out the root cause.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="943d5-162">如果在 Lync Server 中出现问题方案，请首先询问自己 "我已了解有关该问题的哪些信息？"</span><span class="sxs-lookup"><span data-stu-id="943d5-162">When presented with a problem scenario in Lync Server, start by asking yourself “What do I already know about the problem?”</span></span> <span data-ttu-id="943d5-163">如果你量化问题的边界，则可以在 Lync Server 中消除大部分运营实体的一部分。</span><span class="sxs-lookup"><span data-stu-id="943d5-163">If you quantify the problem boundaries, you can eliminate a large part of the operational entities in Lync Server.</span></span><BR><span data-ttu-id="943d5-164">考虑以下示例方案：您知道用户在查找联系人时未获得当前结果。</span><span class="sxs-lookup"><span data-stu-id="943d5-164">Consider an example scenario where you know that users are not getting current results when looking for a contact.</span></span> <span data-ttu-id="943d5-165">在媒体组件、企业语音、会议和许多其他组件中，不存在任何问题。</span><span class="sxs-lookup"><span data-stu-id="943d5-165">There is no point in looking for problems in the media components, Enterprise Voice, conferencing, and a number of other components.</span></span> <span data-ttu-id="943d5-166">您不知道出现问题的实际位置：是客户端上还是服务器端？</span><span class="sxs-lookup"><span data-stu-id="943d5-166">What you may not know is where the problem actually is: on the client, or is this a server-side problem?</span></span> <span data-ttu-id="943d5-167">联系人通过通讯簿服务器（ABServer）通过用户复制程序从 Active Directory 收集并传递到客户端。</span><span class="sxs-lookup"><span data-stu-id="943d5-167">Contacts are collected from Active Directory by the User Replicator and delivered to the client by way of the Address Book Server (ABServer).</span></span> <span data-ttu-id="943d5-168">ABServer 从 RTC 数据库获取其更新（用户复制程序将更新写入该数据库），并将其收集到一个通讯簿文件中（默认情况下为 1:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="943d5-168">The ABServer gets its updates from the RTC database (where User Replicator wrote them) and collects them into address book files, by default – 1:30 AM.</span></span> <span data-ttu-id="943d5-169">Lync 服务器客户按随机计划检索新的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="943d5-169">The Lync Server clients retrieve the new address book on a randomized schedule.</span></span> <span data-ttu-id="943d5-170">由于你知道进程的工作方式，因此你可以将搜索范围减少为与用户复制程序从 Active Directory 收集的数据相关的问题，ABServer 不会检索和创建通讯簿文件，或者客户不下载通讯簿文件。</span><span class="sxs-lookup"><span data-stu-id="943d5-170">Because you know how the process works, you can reduce your search for the potential cause to an issue related to data being collected from Active Directory by the User Replicator, the ABServer not retrieving and creating the address book files, or the clients not downloading the address book file.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

