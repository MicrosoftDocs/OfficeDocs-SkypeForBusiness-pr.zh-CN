---
title: 使用集中日志记录服务创建的捕获日志的搜索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edfc176934479aef04d6850a8ebbae3b38a553a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="ee4b6-102">对 Lync Server 2013 中的集中式日志记录服务创建的捕获日志使用搜索</span><span class="sxs-lookup"><span data-stu-id="ee4b6-102">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee4b6-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ee4b6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ee4b6-104">集中日志记录服务中的搜索功能非常有用且功能强大，原因如下：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-104">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="ee4b6-105">根据您定义的条件，搜索和结果可在单台计算机、池、站点或全局范围运行。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-105">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="ee4b6-p101">搜索最初可以很宽泛，然后范围缩小至更具针对性的条件，如时间、组件或计算机。您针对相同日志进行搜索，当搜索条件更改时，无需再次运行日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="ee4b6-p102">搜索的结果是从范围内的所有计算机和池中收集的，收集并聚合到单个输出文件中，该输出文件表示搜索条件的所有结果（限于已在运行的方案和这些方案捕获的数据）。使用熟悉的工具（如 **Snooper** 或**记事本**）可以读取该输出文件和来自部署的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="ee4b6-p103">每台计算机上的 CLSAgent 会根据方案创建日志（在任意给定时间，每台计算机上可以运行两个方案）。日志及其关联的索引和缓存文件由 CLSAgent 来管理。当您定义和执行搜索时，搜索命令会向 CLSAgent 指示应检索的信息。CLSAgent 针对日志文件、缓存文件和索引文件执行查询并将搜索结果返回至 CLSContoller。CLSController 接收来自搜索范围内的所有计算机和池的搜索结果。然后，CLSController 聚合（组合）日志并使其按时间增量排序，最早的条目在最前面，最新的条目在最后。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="ee4b6-116">在每次搜索后，**Sync-CsClsLogging** cmdlet 都会运行并且它会刷新搜索使用的缓存（不要与 CLSAgent 维护的缓存文件混淆）。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-116">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="ee4b6-117">刷新缓存有助于确保在 CLSController 中存在用于下一次搜索操作的干净日志和跟踪文件捕获缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-117">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="ee4b6-118">若要从集中式日志记录服务获得最大好处，你需要了解如何配置搜索以仅从计算机和池日志中返回跟踪消息，这些消息与你正在研究的问题相关。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-118">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="ee4b6-119">故障</span><span class="sxs-lookup"><span data-stu-id="ee4b6-119">issues</span></span>

<span data-ttu-id="ee4b6-120">若要使用 Lync Server Management Shell 运行集中式日志记录服务搜索功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制（RBAC）安全组的成员，或者是包含以下项的自定义 RBAC 角色这两个组中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-120">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="ee4b6-121">若要返回已分配此 cmdlet 的所有 RBAC 角色（包括你自己创建的任何自定义 RBAC 角色）的列表，请从 Lync Server 命令行管理程序或 Windows PowerShell 提示中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-121">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="ee4b6-122">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-122">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="ee4b6-123">本主题的其余部分重点介绍如何通过定义搜索来优化故障排除。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-123">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="ee4b6-124">使用集中式日志记录服务运行基本搜索</span><span class="sxs-lookup"><span data-stu-id="ee4b6-124">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="ee4b6-125">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ee4b6-126">确保 AlwaysOn 方案在部署中的全局范围内运行，然后在命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-126">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ee4b6-127">默认情况下，Search-CsClsLogging 将搜索结果发送至控制台。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-127">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="ee4b6-128">如果要将搜索结果保存到文件，请使用– OutputFilePath &lt;字符串完全限定的文件路径。&gt;</span><span class="sxs-lookup"><span data-stu-id="ee4b6-128">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="ee4b6-129">若要定义 –OutputFilePath 参数，请在参数中以用引号括起的字符串格式提供路径和文件名（例如；C:\LogFiles\SearchOutput.txt）。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-129">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="ee4b6-130">在此示例中，必须确保目录 C:\LogFiles 存在，并且您有权在该文件夹中读取和写入（NTFS 权限修改）文件。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-130">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="ee4b6-131">输出将进行追加而不会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-131">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="ee4b6-132">如果需要不同文件，请为每个搜索定义不同文件名。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-132">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="ee4b6-133">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-133">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="ee4b6-134">使用集中式日志记录服务在池或计算机上运行基本搜索</span><span class="sxs-lookup"><span data-stu-id="ee4b6-134">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="ee4b6-135">若要将搜索限制于特定池或计算机，请将 –Computers 参数与计算机完全限定名称所定义的计算机（用引号括起并用逗号隔开）结合使用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-135">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="ee4b6-136">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-136">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="ee4b6-137">若要搜索多台计算机，请键入用引号括起并用逗号隔开的多个计算机名称，例如：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-137">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="ee4b6-138">如果您需要搜索整个池而不是单台计算机，请将 –Computers 参数更改为 –Pools，删除计算机名称，并将其替换为用引号括起并用逗号隔开的一个或多个池。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-138">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="ee4b6-139">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-139">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="ee4b6-140">使用搜索命令时，池可以是部署中的任何池，例如前端池、边缘池、持久聊天服务器池或在部署中定义为池的其他池。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-140">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="ee4b6-141">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-141">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="ee4b6-142">使用时间参数运行搜索</span><span class="sxs-lookup"><span data-stu-id="ee4b6-142">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="ee4b6-143">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ee4b6-144">默认情况下，搜索的时间特定参数的开始时间是开始搜索之前30分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-144">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search.</span></span> <span data-ttu-id="ee4b6-145">换言之，如果你在 4:00:00 PM 启动搜索，搜索将在 pm 3:30:00 中搜索你定义的计算机和池的日志，直到 4:00:00 PM。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-145">In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM.</span></span> <span data-ttu-id="ee4b6-146">如果需要在当前时间之前搜索 60 分钟或 3 小时，请使用 –StartTime 参数，并设置日期和时间字符串，以指示希望搜索开始的时间。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-146">If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="ee4b6-147">例如，通过使用 –StartTime 和 –EndTime 定义时间和日期范围，可以定义在 11/20/2012 的 8 AM 到 9 AM 之间对池执行的搜索。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-147">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="ee4b6-148">你可以将输出路径设置为将结果写入到名为 c：\\logfile 的文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-148">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ee4b6-149">您指定的时间和日期字符串可以为“日期时间”或“时间日期”。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-149">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="ee4b6-150">"命令将分析字符串并对日期和时间使用相应的值。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-150">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="ee4b6-p111">如果要从 11/20/2012 的 11:00:00 AM 开始检索日志，需定义 –StartTime。除非定义特定的 –EndTime，否则，搜索的默认时间范围是 30 分钟。生成的搜索将在 11:00:00 AM 到 11:30:00 AM 之间从已定义计算机或池中返回日志。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-p111">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime. The default time range for the search is 30 minutes unless you define a specific –EndTime. The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="ee4b6-154">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-154">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="ee4b6-p112">若要对特定时间段内的日志执行搜索，请定义 –StartTime 和 –EndTime。您需要计算机 edge01.contoso.net 上从 1 PM 到 2:45 PM 的日志。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-p112">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime. You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="ee4b6-157">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-157">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="ee4b6-158">使用其他条件和匹配选项运行高级搜索</span><span class="sxs-lookup"><span data-stu-id="ee4b6-158">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="ee4b6-159">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-159">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ee4b6-160">若要运行命令以收集特定组件的跟踪，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-160">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="ee4b6-161">例如：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-161">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="ee4b6-162">生成的搜索将返回在过去 30 分钟内，在部署中的所有计算机和池中具有 SIPStack、S4 和 UserServices 的跟踪组件的所有日志条目。</span><span class="sxs-lookup"><span data-stu-id="ee4b6-162">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="ee4b6-163">若要将包含相同组件的搜索限制为仅限名为 pool01.contoso.net 的前端池，请键入：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-163">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="ee4b6-p113">使用多个参数的命令的默认搜索逻辑是将逻辑 OR 用于每个已定义参数。可通过指定 **–MatchAll** 参数来更改此行为。为此，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-p113">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters. You can change this behavior by specifying the **–MatchAll** parameter. To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="ee4b6-p114">如果您的方案设置为经常运行（例如 AlwaysOn）或您已定义长期运行的方案，则日志可能从本地计算机转到文件共享中。通过使用 New-CsClsConfiguration 创建新配置或用 Set-CsClsConfiguration 修改现有配置，可使用 CacheFileNetworkFolder 参数定义文件共享。如果不希望搜索将文件共享包括在要搜索的日志集合中，请按如下所示使用 SkipNetworkLogs 参数：</span><span class="sxs-lookup"><span data-stu-id="ee4b6-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

