---
title: 在 Skype for Business Server 2015 中搜索集中日志记录服务创建的捕获日志
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 摘要： 了解如何搜索和业务服务器 2015年阅读 Centralized Logging Service 中 Skype 的捕获日志。
ms.openlocfilehash: 463daf41d0e1e1e7c5a718adcd48bdb3f227feff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914910"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="f61e3-103">在 Skype for Business Server 2015 中搜索集中日志记录服务创建的捕获日志</span><span class="sxs-lookup"><span data-stu-id="f61e3-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f61e3-104">**摘要：** 了解如何搜索和业务服务器 2015年阅读 Centralized Logging Service 中 Skype 的捕获日志。</span><span class="sxs-lookup"><span data-stu-id="f61e3-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f61e3-105">The Centralized Logging Service 中的搜索功能很有用，并且强大原因如下：</span><span class="sxs-lookup"><span data-stu-id="f61e3-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="f61e3-106">根据您定义的条件，搜索和结果可在单台计算机、池、站点或全局范围运行。</span><span class="sxs-lookup"><span data-stu-id="f61e3-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="f61e3-107">搜索最初可以很宽泛，然后范围缩小至更具针对性的条件，如时间、组件或计算机。</span><span class="sxs-lookup"><span data-stu-id="f61e3-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="f61e3-108">您对相同的日志搜索并不需要运行日志记录会话再次更改搜索条件时。</span><span class="sxs-lookup"><span data-stu-id="f61e3-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="f61e3-p102">搜索的结果是从范围内的所有计算机和池中收集的，收集并聚合到单个输出文件中，该输出文件表示搜索条件的所有结果（限于已在运行的方案和这些方案捕获的数据）。使用熟悉的工具（如 **Snooper** 或**记事本**）可以读取该输出文件和来自部署的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="f61e3-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="f61e3-p103">每台计算机上的 CLSAgent 会根据方案创建日志（在任意给定时间，每台计算机上可以运行两个方案）。日志及其关联的索引和缓存文件由 CLSAgent 来管理。当您定义和执行搜索时，搜索命令会向 CLSAgent 指示应检索的信息。CLSAgent 针对日志文件、缓存文件和索引文件执行查询并将搜索结果返回至 CLSContoller。CLSController 接收来自搜索范围内的所有计算机和池的搜索结果。然后，CLSController 聚合（组合）日志并使其按时间增量排序，最早的条目在最前面，最新的条目在最后。</span><span class="sxs-lookup"><span data-stu-id="f61e3-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="f61e3-117">在每次搜索后，**Sync-CsClsLogging** cmdlet 都会运行并且它会刷新搜索使用的缓存（不要与 CLSAgent 维护的缓存文件混淆）。</span><span class="sxs-lookup"><span data-stu-id="f61e3-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="f61e3-118">刷新缓存有助于确保在 CLSController 中存在用于下一次搜索操作的干净日志和跟踪文件捕获缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f61e3-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="f61e3-119">若要获得 the Centralized Logging Service 的最大好处，您需要如何配置搜索以返回只跟踪消息从计算机和池日志与您研究该问题相关的更好地理解。</span><span class="sxs-lookup"><span data-stu-id="f61e3-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="f61e3-120">问题</span><span class="sxs-lookup"><span data-stu-id="f61e3-120">issues</span></span>
  
<span data-ttu-id="f61e3-121">若要使用 Skype 业务 Server 命令行管理程序中运行的集中日志记录服务搜索功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中或自定义 RBAC 角色的成员包含这两个组之一。</span><span class="sxs-lookup"><span data-stu-id="f61e3-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="f61e3-122">若要返回的已分配此 cmdlet 的所有 RBAC 角色的列表 （包括您自己创建任何自定义 RBAC 角色），请业务 Server 命令行管理程序或 Windows PowerShell 提示符从 Skype 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f61e3-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="f61e3-123">例如：</span><span class="sxs-lookup"><span data-stu-id="f61e3-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="f61e3-124">本主题的其余部分重点介绍如何通过定义搜索来优化故障排除。</span><span class="sxs-lookup"><span data-stu-id="f61e3-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="f61e3-125">使用 the Centralized Logging Service 中运行基本搜索</span><span class="sxs-lookup"><span data-stu-id="f61e3-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="f61e3-126">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f61e3-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f61e3-127">确保 AlwaysOn 方案在部署中的全局范围内运行，然后在命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="f61e3-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="f61e3-128">默认情况下，Search-CsClsLogging 将搜索结果发送至控制台。</span><span class="sxs-lookup"><span data-stu-id="f61e3-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="f61e3-129">如果您想要将搜索结果保存到文件，使用-OutputFilePath_\<字符串完全限定的文件路径\>_。</span><span class="sxs-lookup"><span data-stu-id="f61e3-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="f61e3-130">若要定义-OutputFilePath 参数，提供的路径和文件名 （例如; 括在引号的字符串格式中的参数的一部分C:\LogFiles\SearchOutput.txt)。</span><span class="sxs-lookup"><span data-stu-id="f61e3-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="f61e3-131">在此示例中，必须确保目录 C:\LogFiles 存在，并且您有权在该文件夹中读取和写入（NTFS 权限修改）文件。</span><span class="sxs-lookup"><span data-stu-id="f61e3-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="f61e3-132">输出将进行追加而不会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="f61e3-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="f61e3-133">如果需要不同文件，请为每个搜索定义不同文件名。</span><span class="sxs-lookup"><span data-stu-id="f61e3-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="f61e3-134">例如：</span><span class="sxs-lookup"><span data-stu-id="f61e3-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="f61e3-135">使用 the Centralized Logging Service 在池或计算机上运行基本搜索</span><span class="sxs-lookup"><span data-stu-id="f61e3-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="f61e3-136">若要限制到特定的池或计算机的搜索，请使用与计算机由计算机的完全限定名称定义和括在引号内，如下所示并用逗号分隔-Computers 参数：</span><span class="sxs-lookup"><span data-stu-id="f61e3-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="f61e3-137">例如：</span><span class="sxs-lookup"><span data-stu-id="f61e3-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="f61e3-138">若要搜索多台计算机，请键入用引号括起并用逗号隔开的多个计算机名称，例如：</span><span class="sxs-lookup"><span data-stu-id="f61e3-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="f61e3-139">如果您需要搜索整个池而不是一台计算机，更改为-池、 删除计算机名和替换-Computers 参数它与池或在引号内的池以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="f61e3-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="f61e3-140">例如：</span><span class="sxs-lookup"><span data-stu-id="f61e3-140">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="f61e3-141">在使用搜索命令时，池可以是在部署中，如前端池、 边缘池、 持久聊天服务器池，或为池部署中定义的其他任何池。</span><span class="sxs-lookup"><span data-stu-id="f61e3-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="f61e3-142">例如：</span><span class="sxs-lookup"><span data-stu-id="f61e3-142">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="f61e3-143">使用时间参数运行搜索</span><span class="sxs-lookup"><span data-stu-id="f61e3-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="f61e3-144">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f61e3-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f61e3-145">默认情况下，搜索的时间特定参数的开始时间为启动搜索前 25 分钟到后五分钟。</span><span class="sxs-lookup"><span data-stu-id="f61e3-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="f61e3-146">换言之，如果在 4:00:00 PM 进行搜索，搜索开始时间将显示为 3:35:00 PM 到 4:05:00 PM。</span><span class="sxs-lookup"><span data-stu-id="f61e3-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="f61e3-147">如果您需要搜索 60 分钟或 3 小时当前时间之前，请使用-StartTime 参数，并设置来指示希望搜索开始的时间的日期和时间的字符串。</span><span class="sxs-lookup"><span data-stu-id="f61e3-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="f61e3-148">例如，通过使用-StartTime 和-EndTime 定义的日期和时间范围，您可以定义搜索上午 8 和 9 AM 之间在 2012 年 11/20 池上。</span><span class="sxs-lookup"><span data-stu-id="f61e3-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="f61e3-149">可以设置输出路径，以将结果写入名为 c:\logfile.txt 的文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f61e3-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="f61e3-150">您指定的时间和日期字符串可以为“日期时间”或“时间日期”。</span><span class="sxs-lookup"><span data-stu-id="f61e3-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="f61e3-151">"该命令将分析字符串，并对日期和时间以及您运行的 cmdlet 的计算机上的区域设置和区域性设置使用适当的值。</span><span class="sxs-lookup"><span data-stu-id="f61e3-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="f61e3-152">如果您想要检索 11:00:00 2012 年 11/20 的开头的日志，则定义-StartTime。</span><span class="sxs-lookup"><span data-stu-id="f61e3-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="f61e3-153">搜索的默认时间范围为 30 分钟，除非您定义特定结束时间。</span><span class="sxs-lookup"><span data-stu-id="f61e3-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="f61e3-154">生成的搜索将在 11:00:00 AM 到 11:30:00 AM 之间从已定义计算机或池中返回日志。</span><span class="sxs-lookup"><span data-stu-id="f61e3-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="f61e3-155">例如：</span><span class="sxs-lookup"><span data-stu-id="f61e3-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="f61e3-156">若要在特定时间段内执行的日志搜索，定义-StartTime 和-EndTime。</span><span class="sxs-lookup"><span data-stu-id="f61e3-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="f61e3-157">您需要计算机 edge01.contoso.net 上从 1 PM 到 2:45 PM 的日志。</span><span class="sxs-lookup"><span data-stu-id="f61e3-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="f61e3-158">例如：</span><span class="sxs-lookup"><span data-stu-id="f61e3-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="f61e3-159">使用其他条件和匹配选项运行高级搜索</span><span class="sxs-lookup"><span data-stu-id="f61e3-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="f61e3-160">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f61e3-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f61e3-161">若要运行命令以收集特定组件的跟踪，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f61e3-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="f61e3-162">例如：</span><span class="sxs-lookup"><span data-stu-id="f61e3-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="f61e3-163">生成的搜索将返回在过去 30 分钟内，在部署中的所有计算机和池中具有 SIPStack、S4 和 UserServices 的跟踪组件的所有日志条目。</span><span class="sxs-lookup"><span data-stu-id="f61e3-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="f61e3-164">若要限制具有到刚名为 pool01.contoso.net 您前端池的相同组件的搜索，请键入：</span><span class="sxs-lookup"><span data-stu-id="f61e3-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="f61e3-165">使用多个参数的命令的默认搜索逻辑是将逻辑 OR 用于每个已定义参数。</span><span class="sxs-lookup"><span data-stu-id="f61e3-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="f61e3-166">您可以通过指定 **-MatchAll**参数来更改此行为。</span><span class="sxs-lookup"><span data-stu-id="f61e3-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="f61e3-167">为此，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="f61e3-167">To do this, type the following:</span></span>
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="f61e3-p114">如果您的方案设置为经常运行（例如 AlwaysOn）或您已定义长期运行的方案，则日志可能从本地计算机转到文件共享中。通过使用 New-CsClsConfiguration 创建新配置或用 Set-CsClsConfiguration 修改现有配置，可使用 CacheFileNetworkFolder 参数定义文件共享。如果不希望搜索将文件共享包括在要搜索的日志集合中，请按如下所示使用 SkipNetworkLogs 参数：</span><span class="sxs-lookup"><span data-stu-id="f61e3-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="f61e3-171">从集中日志记录服务读取捕获的日志</span><span class="sxs-lookup"><span data-stu-id="f61e3-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="f61e3-172">运行搜索和必须可用来跟踪报告问题的文件后，您可以实现实际 the Centralized Logging Service 的好处。</span><span class="sxs-lookup"><span data-stu-id="f61e3-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="f61e3-173">读取该文件有多种方法。</span><span class="sxs-lookup"><span data-stu-id="f61e3-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="f61e3-174">输出文件为标准文本格式，可以使用 Notepad.exe 或任何其他可以打开和读取文本文件的程序。</span><span class="sxs-lookup"><span data-stu-id="f61e3-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="f61e3-175">对于较大的文件和更复杂的问题，可以使用的工具 Snooper.exe，旨在读取并分析 the Centralized Logging Service 中的日志记录输出类似。</span><span class="sxs-lookup"><span data-stu-id="f61e3-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="f61e3-176">Snooper 包含在可单独下载的调试工具中。</span><span class="sxs-lookup"><span data-stu-id="f61e3-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="f61e3-177">您可以下载调试工具此处： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)。</span><span class="sxs-lookup"><span data-stu-id="f61e3-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="f61e3-178">在安装调试工具时，不会创建快捷方式和菜单项。</span><span class="sxs-lookup"><span data-stu-id="f61e3-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="f61e3-179">安装调试工具后，打开 Windows 资源管理器、 命令行窗口或 Skype 业务 Server 命令行管理程序和业务 Server 2015\Debugging 工具的 C:\Program Files\Skype 转到的目录 （默认位置）。</span><span class="sxs-lookup"><span data-stu-id="f61e3-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="f61e3-180">双击 Snooper.exe 或键入 Snooper.exe，，如果您使用命令行或 Skype for Business Server 命令行管理程序，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="f61e3-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f61e3-181">本主题的目的不是详细介绍和讨论疑难解答技术。</span><span class="sxs-lookup"><span data-stu-id="f61e3-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="f61e3-182">疑难解答及其相关过程是一个复杂的主题。</span><span class="sxs-lookup"><span data-stu-id="f61e3-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="f61e3-183">疑难解答基本知识和特定的工作负载疑难解答的详细信息，请参阅在 Microsoft Lync Server 2010 资源工具包书籍内，在[https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)。</span><span class="sxs-lookup"><span data-stu-id="f61e3-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="f61e3-184">流程和过程仍适用于 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="f61e3-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="f61e3-185">在 Snooper 中打开日志文件</span><span class="sxs-lookup"><span data-stu-id="f61e3-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="f61e3-p117">要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="f61e3-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="f61e3-188">安装调试工具 (LyncDebugTools.msi) 后，使用 Windows 资源管理器或从命令行将目录切换到 Snooper.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="f61e3-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="f61e3-189">默认情况下调试工具都位于 C:\Program Files\Skype Business Server 2015\Debugging 工具。</span><span class="sxs-lookup"><span data-stu-id="f61e3-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="f61e3-190">双击或运行 Snooper.exe。</span><span class="sxs-lookup"><span data-stu-id="f61e3-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="f61e3-191">打开 Snooper 后，右键单击“**文件**”，单击“**打开文件**”，查找日志文件，在“**打开**”对话框中选择文件，然后单击“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="f61e3-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="f61e3-192">显示日志文件的**跟踪**消息**跟踪**在选项卡，单击**邮件**选项卡查看收集的跟踪消息的内容。</span><span class="sxs-lookup"><span data-stu-id="f61e3-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="f61e3-193">显示呼叫流程图</span><span class="sxs-lookup"><span data-stu-id="f61e3-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="f61e3-p119">要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您需要是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="f61e3-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="f61e3-196">打开日志文件并单击“**消息**”选项卡，在消息视图中选择对话或在“**跟踪**”选项卡上选择跟踪组件。</span><span class="sxs-lookup"><span data-stu-id="f61e3-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="f61e3-197">单击“**呼叫流**”。</span><span class="sxs-lookup"><span data-stu-id="f61e3-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f61e3-198">如果您单击邮件或不是呼叫流的一部分的跟踪，不显示图表，并且在 Snooper 指出"This message is 不适合 callfow"的底部显示状态信息。</span><span class="sxs-lookup"><span data-stu-id="f61e3-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="f61e3-199">选择另一条属于呼叫流的消息或跟踪，将显示呼叫流。</span><span class="sxs-lookup"><span data-stu-id="f61e3-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="f61e3-200">在消息或跟踪行间移动，并注意呼叫流程图是否更新或更改为显示新图。</span><span class="sxs-lookup"><span data-stu-id="f61e3-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="f61e3-201">在元素上悬停可获得有关呼叫消息、终结点和其他组件的信息。</span><span class="sxs-lookup"><span data-stu-id="f61e3-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
