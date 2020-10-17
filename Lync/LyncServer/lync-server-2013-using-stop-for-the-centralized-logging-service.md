---
title: Lync Server 2013：对集中日志记录服务使用停止
description: Lync Server 2013：对集中日志记录服务使用停止。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114530d976b623bd4e5d75555a91a0ec3240ba07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560218"
---
# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="ebb04-103">在 Lync Server 2013 中对集中日志记录服务使用停止</span><span class="sxs-lookup"><span data-stu-id="ebb04-103">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebb04-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ebb04-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ebb04-105">您可以使用 Stop-CsClsLogging cmdlet 停止当前正在运行的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="ebb04-105">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="ebb04-106">通常，需要停止日志记录会话的情形并不多。</span><span class="sxs-lookup"><span data-stu-id="ebb04-106">Generally, there aren’t many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="ebb04-107">例如，无需先停止日志记录就可以搜索日志和更改配置。</span><span class="sxs-lookup"><span data-stu-id="ebb04-107">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="ebb04-108">如果您有两种方案（例如 AlwaysOn 和 UserReplicator）在运行，并且您需要收集与身份验证相关的信息，则您需要停止其他方案之一（在全局、站点、池或计算机范围内），然后才能开始运行身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="ebb04-108">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="ebb04-109">有关详细信息，请参阅 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)。</span><span class="sxs-lookup"><span data-stu-id="ebb04-109">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ebb04-110">在确定了可以在给定部署、池或计算机上运行哪些方案后，您需要记住，在<STRONG>每台计算机</STRONG>上只能运行两个方案。</span><span class="sxs-lookup"><span data-stu-id="ebb04-110">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="ebb04-111">如果您要记录某个池上的活动，应将一个池视为单一实体。</span><span class="sxs-lookup"><span data-stu-id="ebb04-111">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="ebb04-112">在大多数情况下，在池中的每台计算机上运行不同方案没有意义。</span><span class="sxs-lookup"><span data-stu-id="ebb04-112">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="ebb04-113">了解正在收集其数据的问题以及考虑哪些方案在总体部署中的给定计算机上运行最有意义才是合理的。</span><span class="sxs-lookup"><span data-stu-id="ebb04-113">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="ebb04-114">例如，如果考虑使用 UserReplicator 方案，则在边缘服务器或边缘池上运行 UserReplicator 会有非常小的价值。</span><span class="sxs-lookup"><span data-stu-id="ebb04-114">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="ebb04-p103">在了解了问题和影响范围后，应谨慎选择哪些方案在哪些计算机和池上运行。AlwaysOn 方案对于广泛的应用具有意义，因为它收集各类提供商的信息，而具体方案只在特定计算机或池上具有应用价值。此外，在随机启动日志记录会话而不先了解给定方案的价值时务必小心。如果使用的方案错误，或者虽然使用的方案适合任务，但应用范围（全局、站点、池或计算机）错误，您可以获得不是很有用的可疑数据，就像您根本没有运行该方案一样。</span><span class="sxs-lookup"><span data-stu-id="ebb04-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="ebb04-119">若要使用 Lync Server 命令行管理程序控制集中日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组中任一组的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ebb04-119">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="ebb04-120">若要返回已将此 cmdlet 分配给的所有 RBAC 角色的列表 (包括您自己) 创建的任何自定义 RBAC 角色，请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ebb04-120">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="ebb04-121">例如：</span><span class="sxs-lookup"><span data-stu-id="ebb04-121">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="ebb04-122">停止当前正在运行的集中日志记录服务会话</span><span class="sxs-lookup"><span data-stu-id="ebb04-122">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="ebb04-123">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebb04-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ebb04-124">通过键入以下命令，查询集中日志记录服务以确定当前正在运行的方案：</span><span class="sxs-lookup"><span data-stu-id="ebb04-124">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="ebb04-125">![在调用 CsCl 后显示 Windows PowerShell 控制台](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "调用 Show-CsCl 后的 Windows PowerShell 控制台")</span><span class="sxs-lookup"><span data-stu-id="ebb04-125">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="ebb04-126">Show-CsClsLogging 的结果是正在运行的方案以及它们所运行的范围的摘要。</span><span class="sxs-lookup"><span data-stu-id="ebb04-126">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="ebb04-127">有关详细信息，请参阅 [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)。</span><span class="sxs-lookup"><span data-stu-id="ebb04-127">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="ebb04-128">若要使用特定方案停止当前正在运行的日志记录会话，请键入：</span><span class="sxs-lookup"><span data-stu-id="ebb04-128">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="ebb04-129">例如：</span><span class="sxs-lookup"><span data-stu-id="ebb04-129">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="ebb04-130">此命令将在 pool01.contoso.net 上使用 UserReplicatior 方案停止日志记录。</span><span class="sxs-lookup"><span data-stu-id="ebb04-130">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebb04-131">在此日志记录会话期间使用 UserReplicator 方案创建的日志不会被删除。</span><span class="sxs-lookup"><span data-stu-id="ebb04-131">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="ebb04-132">您仍然可以使用 Search-CsClsLogging 命令对日志记录执行搜索。</span><span class="sxs-lookup"><span data-stu-id="ebb04-132">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="ebb04-133">有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>。</span><span class="sxs-lookup"><span data-stu-id="ebb04-133">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="ebb04-p107">作为 Start-CsClsLogging 的配套命令，Stop-CsClsLogging cmdlet 会结束方案定义的日志记录会话，并保留日志记录会话创建的日志。任何时候都可以在给定计算机上运行两个方案。停止一个方案而使用另一个方案收集信息的方法是一项常见的任务，您可以在大多数工作负荷故障排除过程中执行该任务。</span><span class="sxs-lookup"><span data-stu-id="ebb04-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ebb04-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebb04-137">See Also</span></span>


[<span data-ttu-id="ebb04-138">使用 Start 实现集中日志记录服务以在 Lync Server 2013 中捕获日志</span><span class="sxs-lookup"><span data-stu-id="ebb04-138">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="ebb04-139">Lync Server 2013 中的集中日志记录服务概述</span><span class="sxs-lookup"><span data-stu-id="ebb04-139">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="ebb04-140">显示-Search-csclslogging</span><span class="sxs-lookup"><span data-stu-id="ebb04-140">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="ebb04-141">启动-Search-csclslogging</span><span class="sxs-lookup"><span data-stu-id="ebb04-141">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="ebb04-142">Search-csclslogging</span><span class="sxs-lookup"><span data-stu-id="ebb04-142">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

