---
title: 在 Skype for Business Server 2015 中搜索集中日志记录服务创建的捕获日志
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '摘要: 了解如何在 Skype for Business Server 2015 中搜索和读取集中式日志记录服务捕获日志。'
ms.openlocfilehash: 81bf539c6a06c52354db23bbeea97fb9525cbbd5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274371"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="2c028-103">在 Skype for Business Server 2015 中搜索集中日志记录服务创建的捕获日志</span><span class="sxs-lookup"><span data-stu-id="2c028-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2c028-104">**摘要:** 了解如何在 Skype for Business Server 2015 中搜索和读取集中式日志记录服务捕获日志。</span><span class="sxs-lookup"><span data-stu-id="2c028-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2c028-105">集中日志记录服务中的搜索功能非常有用且功能强大, 原因如下:</span><span class="sxs-lookup"><span data-stu-id="2c028-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="2c028-106">根据您定义的条件，搜索和结果可在单台计算机、池、站点或全局范围运行。</span><span class="sxs-lookup"><span data-stu-id="2c028-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="2c028-107">搜索最初可以很宽泛，然后范围缩小至更具针对性的条件，如时间、组件或计算机。</span><span class="sxs-lookup"><span data-stu-id="2c028-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="2c028-108">搜索相同的日志, 并且在搜索条件更改时无需再次运行日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="2c028-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="2c028-p102">搜索的结果是从范围内的所有计算机和池中收集的，收集并聚合到单个输出文件中，该输出文件表示搜索条件的所有结果（限于已在运行的方案和这些方案捕获的数据）。使用熟悉的工具（如 **Snooper** 或**记事本**）可以读取该输出文件和来自部署的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="2c028-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="2c028-p103">每台计算机上的 CLSAgent 会根据方案创建日志（在任意给定时间，每台计算机上可以运行两个方案）。日志及其关联的索引和缓存文件由 CLSAgent 来管理。当您定义和执行搜索时，搜索命令会向 CLSAgent 指示应检索的信息。CLSAgent 针对日志文件、缓存文件和索引文件执行查询并将搜索结果返回至 CLSContoller。CLSController 接收来自搜索范围内的所有计算机和池的搜索结果。然后，CLSController 聚合（组合）日志并使其按时间增量排序，最早的条目在最前面，最新的条目在最后。</span><span class="sxs-lookup"><span data-stu-id="2c028-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="2c028-117">在每次搜索后，**Sync-CsClsLogging** cmdlet 都会运行并且它会刷新搜索使用的缓存（不要与 CLSAgent 维护的缓存文件混淆）。</span><span class="sxs-lookup"><span data-stu-id="2c028-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="2c028-118">刷新缓存有助于确保在 CLSController 中存在用于下一次搜索操作的干净日志和跟踪文件捕获缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2c028-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="2c028-119">若要从集中式日志记录服务获得最大好处, 你需要了解如何配置搜索以仅从计算机和池日志中返回跟踪消息, 这些消息与你正在研究的问题相关。</span><span class="sxs-lookup"><span data-stu-id="2c028-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="2c028-120">故障</span><span class="sxs-lookup"><span data-stu-id="2c028-120">issues</span></span>
  
<span data-ttu-id="2c028-121">若要使用 Skype for Business Server Management Shell 运行集中式日志记录服务搜索功能, 您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 安全组的成员, 或者是自定义的 RBAC 角色其中包含两个组中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="2c028-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="2c028-122">若要返回已分配此 cmdlet 的所有 RBAC 角色 (包括你自己创建的任何自定义 RBAC 角色) 的列表, 请从 Skype for Business Server Management Shell 或 Windows PowerShell 提示中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="2c028-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="2c028-123">例如：</span><span class="sxs-lookup"><span data-stu-id="2c028-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="2c028-124">本主题的其余部分重点介绍如何通过定义搜索来优化故障排除。</span><span class="sxs-lookup"><span data-stu-id="2c028-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="2c028-125">使用集中式日志记录服务运行基本搜索</span><span class="sxs-lookup"><span data-stu-id="2c028-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="2c028-126">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c028-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2c028-127">确保 AlwaysOn 方案在部署中的全局范围内运行，然后在命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="2c028-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="2c028-128">默认情况下，Search-CsClsLogging 将搜索结果发送至控制台。</span><span class="sxs-lookup"><span data-stu-id="2c028-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="2c028-129">如果要将搜索结果保存到文件中, 请使用-OutputFilePath _ \<字符串完全限定的文件路径\>_。</span><span class="sxs-lookup"><span data-stu-id="2c028-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="2c028-130">若要定义-OutputFilePath 参数, 请以引号括起的字符串格式将路径和文件名作为参数的一部分提供 (例如,C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="2c028-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="2c028-131">在此示例中，必须确保目录 C:\LogFiles 存在，并且您有权在该文件夹中读取和写入（NTFS 权限修改）文件。</span><span class="sxs-lookup"><span data-stu-id="2c028-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="2c028-132">输出将进行追加而不会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="2c028-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="2c028-133">如果需要不同文件，请为每个搜索定义不同文件名。</span><span class="sxs-lookup"><span data-stu-id="2c028-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="2c028-134">例如：</span><span class="sxs-lookup"><span data-stu-id="2c028-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="2c028-135">使用集中式日志记录服务在池或计算机上运行基本搜索</span><span class="sxs-lookup"><span data-stu-id="2c028-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="2c028-136">若要将搜索限制到特定池或计算机, 请将-计算机参数用于计算机使用完全限定名称 (用引号括起, 并用逗号分隔, 如下所示) 定义的计算机。</span><span class="sxs-lookup"><span data-stu-id="2c028-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="2c028-137">例如：</span><span class="sxs-lookup"><span data-stu-id="2c028-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="2c028-138">若要搜索多台计算机，请键入用引号括起并用逗号隔开的多个计算机名称，例如：</span><span class="sxs-lookup"><span data-stu-id="2c028-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="2c028-139">如果你需要搜索整个池而不是一台计算机, 请将-计算机参数更改为池, 删除计算机名称, 并将其替换为用逗号分隔的引号。</span><span class="sxs-lookup"><span data-stu-id="2c028-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="2c028-140">例如：</span><span class="sxs-lookup"><span data-stu-id="2c028-140">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="2c028-141">使用搜索命令时, 池可以是部署中的任何池, 例如前端池、边缘池、持久聊天服务器池或在部署中定义为池的其他池。</span><span class="sxs-lookup"><span data-stu-id="2c028-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="2c028-142">例如：</span><span class="sxs-lookup"><span data-stu-id="2c028-142">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="2c028-143">使用时间参数运行搜索</span><span class="sxs-lookup"><span data-stu-id="2c028-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="2c028-144">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c028-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2c028-145">默认情况下，搜索的时间特定参数的开始时间为启动搜索前 25 分钟到后五分钟。</span><span class="sxs-lookup"><span data-stu-id="2c028-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="2c028-146">换言之，如果在 4:00:00 PM 进行搜索，搜索开始时间将显示为 3:35:00 PM 到 4:05:00 PM。</span><span class="sxs-lookup"><span data-stu-id="2c028-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="2c028-147">如果需要在当前时间之前搜索60分钟或3小时, 请使用-StartTime 参数并设置日期和时间字符串以指示希望搜索开始的时间。</span><span class="sxs-lookup"><span data-stu-id="2c028-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="2c028-148">例如, 通过使用-StartTime 和-EndTime 定义时间和日期范围, 你可以在你的池中的11/20/2012 上的上午8点和9点之间定义搜索。</span><span class="sxs-lookup"><span data-stu-id="2c028-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="2c028-149">可以设置输出路径，以将结果写入名为 c:\logfile.txt 的文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c028-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="2c028-150">您指定的时间和日期字符串可以为“日期时间”或“时间日期”。</span><span class="sxs-lookup"><span data-stu-id="2c028-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="2c028-151">"命令将分析字符串, 并在运行 cmdlet 的计算机上使用相应的日期和时间值以及你的区域设置和区域性设置。</span><span class="sxs-lookup"><span data-stu-id="2c028-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="2c028-152">如果你想要检索从 11:00:00 11/20/2012 凌晨的日志, 请定义-StartTime。</span><span class="sxs-lookup"><span data-stu-id="2c028-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="2c028-153">除非您定义特定的 EndTime, 否则搜索的默认时间范围是30分钟。</span><span class="sxs-lookup"><span data-stu-id="2c028-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="2c028-154">生成的搜索将在 11:00:00 AM 到 11:30:00 AM 之间从已定义计算机或池中返回日志。</span><span class="sxs-lookup"><span data-stu-id="2c028-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="2c028-155">例如：</span><span class="sxs-lookup"><span data-stu-id="2c028-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="2c028-156">若要在特定时间段内对日志进行搜索, 请定义 "开始时间" 和 "结束时间"。</span><span class="sxs-lookup"><span data-stu-id="2c028-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="2c028-157">您需要计算机 edge01.contoso.net 上从 1 PM 到 2:45 PM 的日志。</span><span class="sxs-lookup"><span data-stu-id="2c028-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="2c028-158">例如：</span><span class="sxs-lookup"><span data-stu-id="2c028-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="2c028-159">使用其他条件和匹配选项运行高级搜索</span><span class="sxs-lookup"><span data-stu-id="2c028-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="2c028-160">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c028-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2c028-161">若要运行命令以收集特定组件的跟踪，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="2c028-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="2c028-162">例如：</span><span class="sxs-lookup"><span data-stu-id="2c028-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="2c028-163">生成的搜索将返回在过去 30 分钟内，在部署中的所有计算机和池中具有 SIPStack、S4 和 UserServices 的跟踪组件的所有日志条目。</span><span class="sxs-lookup"><span data-stu-id="2c028-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="2c028-164">若要将包含相同组件的搜索限制为仅限名为 pool01.contoso.net 的前端池, 请键入:</span><span class="sxs-lookup"><span data-stu-id="2c028-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="2c028-165">使用多个参数的命令的默认搜索逻辑是将逻辑 OR 用于每个已定义参数。</span><span class="sxs-lookup"><span data-stu-id="2c028-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="2c028-166">你可以通过指定 **-MatchAll**参数来更改此行为。</span><span class="sxs-lookup"><span data-stu-id="2c028-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="2c028-167">为此，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="2c028-167">To do this, type the following:</span></span>
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="2c028-p114">如果您的方案设置为经常运行（例如 AlwaysOn）或您已定义长期运行的方案，则日志可能从本地计算机转到文件共享中。通过使用 New-CsClsConfiguration 创建新配置或用 Set-CsClsConfiguration 修改现有配置，可使用 CacheFileNetworkFolder 参数定义文件共享。如果不希望搜索将文件共享包括在要搜索的日志集合中，请按如下所示使用 SkipNetworkLogs 参数：</span><span class="sxs-lookup"><span data-stu-id="2c028-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="2c028-171">从集中日志记录服务读取捕获的日志</span><span class="sxs-lookup"><span data-stu-id="2c028-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="2c028-172">在运行搜索并拥有可用于跟踪报告的问题的文件后, 您就能充分利用集中式日志记录服务的真正优势。</span><span class="sxs-lookup"><span data-stu-id="2c028-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="2c028-173">读取该文件有多种方法。</span><span class="sxs-lookup"><span data-stu-id="2c028-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="2c028-174">输出文件为标准文本格式，可以使用 Notepad.exe 或任何其他可以打开和读取文本文件的程序。</span><span class="sxs-lookup"><span data-stu-id="2c028-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="2c028-175">对于较大的文件和更复杂的问题, 你可以使用 Snooper 之类的工具, 它旨在从集中式日志记录服务读取和分析日志记录输出。</span><span class="sxs-lookup"><span data-stu-id="2c028-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="2c028-176">Snooper 包含在可单独下载的调试工具中。</span><span class="sxs-lookup"><span data-stu-id="2c028-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="2c028-177">可在此处下载调试工具: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)。</span><span class="sxs-lookup"><span data-stu-id="2c028-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="2c028-178">安装调试工具时, 不会创建短剪切和菜单项。</span><span class="sxs-lookup"><span data-stu-id="2c028-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="2c028-179">安装调试工具后, 打开 Windows 资源管理器、命令行窗口或 Skype for Business Server 命令行管理程序, 然后转到目录 (默认位置) C:\Program Files\Skype for Business Server 2015 \ 调试工具。</span><span class="sxs-lookup"><span data-stu-id="2c028-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="2c028-180">双击 Snooper 或键入 Snooper, 如果你使用的是命令行或 Skype for business Server Management Shell, 请按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2c028-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2c028-181">本主题的目的不是详细介绍和讨论疑难解答技术。</span><span class="sxs-lookup"><span data-stu-id="2c028-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="2c028-182">疑难解答及其相关过程是一个复杂的主题。</span><span class="sxs-lookup"><span data-stu-id="2c028-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="2c028-183">有关疑难解答基础知识和特定工作负荷疑难解答的详细信息, 请参阅 Microsoft Lync Server 2010 资源[https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)工具包手册。</span><span class="sxs-lookup"><span data-stu-id="2c028-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="2c028-184">流程和过程仍适用于 Skype for business 服务器2015。</span><span class="sxs-lookup"><span data-stu-id="2c028-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="2c028-185">在 Snooper 中打开日志文件</span><span class="sxs-lookup"><span data-stu-id="2c028-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="2c028-p117">要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="2c028-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="2c028-188">安装调试工具 (LyncDebugTools.msi) 后，使用 Windows 资源管理器或从命令行将目录切换到 Snooper.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="2c028-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="2c028-189">默认情况下, 调试工具位于 C:\Program Files\Skype for Business Server 2015 \ 调试工具中。</span><span class="sxs-lookup"><span data-stu-id="2c028-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="2c028-190">双击或运行 Snooper.exe。</span><span class="sxs-lookup"><span data-stu-id="2c028-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="2c028-191">打开 Snooper 后，右键单击“**文件**”，单击“**打开文件**”，查找日志文件，在“**打开**”对话框中选择文件，然后单击“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="2c028-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="2c028-192">日志文件的**跟踪**消息将显示在 "**跟踪**" 选项卡上。单击 "**消息**" 选项卡以查看收集的跟踪的消息内容。</span><span class="sxs-lookup"><span data-stu-id="2c028-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="2c028-193">显示呼叫流程图</span><span class="sxs-lookup"><span data-stu-id="2c028-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="2c028-p119">要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您需要是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="2c028-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="2c028-196">打开日志文件并单击“**消息**”选项卡，在消息视图中选择对话或在“**跟踪**”选项卡上选择跟踪组件。</span><span class="sxs-lookup"><span data-stu-id="2c028-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="2c028-197">单击“**呼叫流**”。</span><span class="sxs-lookup"><span data-stu-id="2c028-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2c028-198">如果单击不属于某个调用流的邮件或跟踪, 将不会显示该图表, 并且在 Snooper 底部显示一条状态消息, 指出 "此消息不符合 callfow"。</span><span class="sxs-lookup"><span data-stu-id="2c028-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="2c028-199">选择另一条属于呼叫流的消息或跟踪，将显示呼叫流。</span><span class="sxs-lookup"><span data-stu-id="2c028-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="2c028-200">在消息或跟踪行间移动，并注意呼叫流程图是否更新或更改为显示新图。</span><span class="sxs-lookup"><span data-stu-id="2c028-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="2c028-201">在元素上悬停可获得有关呼叫消息、终结点和其他组件的信息。</span><span class="sxs-lookup"><span data-stu-id="2c028-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
