---
title: Lync Server 2013：每周任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a723c17e5c909ba0313b962cf97a508b17487309
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="463c1-102">Lync Server 2013 中的每周任务</span><span class="sxs-lookup"><span data-stu-id="463c1-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="463c1-103">_**上次修改的主题：** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="463c1-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="463c1-104">每周任务通常与收集和分析日志和报告有关。</span><span class="sxs-lookup"><span data-stu-id="463c1-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="463c1-105">存档事件日志</span><span class="sxs-lookup"><span data-stu-id="463c1-105">Archive event logs</span></span>

<span data-ttu-id="463c1-106">如果未将事件日志配置为根据需要覆盖事件，则必须定期存档并删除它们。</span><span class="sxs-lookup"><span data-stu-id="463c1-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="463c1-107">此操作对于安全日志尤其重要，在调查尝试的安全违规时，这可能是必需的。</span><span class="sxs-lookup"><span data-stu-id="463c1-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="463c1-108">您的组织将必须定义日志存档的策略和过程。</span><span class="sxs-lookup"><span data-stu-id="463c1-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="463c1-109">创建报表</span><span class="sxs-lookup"><span data-stu-id="463c1-109">Create reports</span></span>

<span data-ttu-id="463c1-110">创建状态报告以帮助进行容量规划、SLA 审查和性能分析。</span><span class="sxs-lookup"><span data-stu-id="463c1-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="463c1-111">使用事件日志和系统监视器中的日常数据来创建有关磁盘、内存和 CPU 使用率的报告。</span><span class="sxs-lookup"><span data-stu-id="463c1-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="463c1-112">使用 System Center Operations Manager 生成正常运行时间和可用性报告。</span><span class="sxs-lookup"><span data-stu-id="463c1-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="463c1-113">您的组织将必须定义状态报告的策略和过程。</span><span class="sxs-lookup"><span data-stu-id="463c1-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="463c1-114">事件报告</span><span class="sxs-lookup"><span data-stu-id="463c1-114">Incident reports</span></span>

<span data-ttu-id="463c1-115">对与 Lync Server 相关的组织事件报告执行每周审核。</span><span class="sxs-lookup"><span data-stu-id="463c1-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="463c1-116">此审核应包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="463c1-116">This audit should include the following:</span></span>

  - <span data-ttu-id="463c1-117">最上面生成、解析和挂起的事件。</span><span class="sxs-lookup"><span data-stu-id="463c1-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="463c1-118">未解决事件的解决方案。</span><span class="sxs-lookup"><span data-stu-id="463c1-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="463c1-119">将报告更新为包含新的故障单。</span><span class="sxs-lookup"><span data-stu-id="463c1-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="463c1-120">更新用于故障排除指南和 post 剖析的文档存储库关于中断。</span><span class="sxs-lookup"><span data-stu-id="463c1-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="463c1-121">由于您组织的事件跟踪系统是独立于 Lync Server 的选择，因此特定说明或指针不可用。</span><span class="sxs-lookup"><span data-stu-id="463c1-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="463c1-122">请参阅您的组织选择的系统的相关文档。</span><span class="sxs-lookup"><span data-stu-id="463c1-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="463c1-123">检查 IIS 日志和性能</span><span class="sxs-lookup"><span data-stu-id="463c1-123">Check IIS logs and performance</span></span>

<span data-ttu-id="463c1-124">每周对 Internet 信息服务（IIS）日志和性能进行审阅。</span><span class="sxs-lookup"><span data-stu-id="463c1-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="463c1-125">有关如何监视 IIS 日志和性能的详细信息，请参阅[Windows Server 2003 Internet Information Services （IIS）事件日志记录概述](https://go.microsoft.com/fwlink/?linkid=36077)。</span><span class="sxs-lookup"><span data-stu-id="463c1-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="463c1-126">评审应包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="463c1-126">The review should include the following:</span></span>

  - <span data-ttu-id="463c1-127">用于监视 WWW 服务缓存的 Web 服务缓存计数器。</span><span class="sxs-lookup"><span data-stu-id="463c1-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="463c1-128">用于监视以 Asp 形式运行的应用程序的 Active Server Pages （Asp）计数器。</span><span class="sxs-lookup"><span data-stu-id="463c1-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="463c1-129">生成数据库报告</span><span class="sxs-lookup"><span data-stu-id="463c1-129">Generate database reports</span></span>

<span data-ttu-id="463c1-130">**生成 SQL 数据库的报告**</span><span class="sxs-lookup"><span data-stu-id="463c1-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="463c1-131">打开 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="463c1-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="463c1-132">在控制台树中，展开 "林" 节点，展开 "**企业版池**"，然后单击要为其生成数据库报告的池。</span><span class="sxs-lookup"><span data-stu-id="463c1-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="463c1-133">在详细信息窗格中，单击 "**数据库**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="463c1-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="463c1-134">在 "**数据库**" 选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="463c1-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="463c1-135">若要查看数据库的名称，请展开 "**常规设置**"，然后查看数据库名称。</span><span class="sxs-lookup"><span data-stu-id="463c1-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="463c1-136">若要检索池的当前用户汇总统计信息，请展开 "**用户摘要报告**"，单击 "**开始**"，然后查看结果。</span><span class="sxs-lookup"><span data-stu-id="463c1-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="463c1-137">若要检索池的单个用户的当前每用户数据，请展开 "**每用户报告**"，键入用户的 SIP URI，单击 "**开始**"，然后查看结果。</span><span class="sxs-lookup"><span data-stu-id="463c1-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="463c1-138">若要检索池的当前会议摘要统计信息，请展开 "**会议摘要报告**"，单击 "**开始**"，然后查看结果。</span><span class="sxs-lookup"><span data-stu-id="463c1-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="463c1-139">检查安全和 Lync Server 更新</span><span class="sxs-lookup"><span data-stu-id="463c1-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="463c1-140">确定任何新的 service pack、修补程序或更新。</span><span class="sxs-lookup"><span data-stu-id="463c1-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="463c1-141">如果适用，请在测试实验室中进行测试，并使用更改控制过程安排部署到生产服务器。</span><span class="sxs-lookup"><span data-stu-id="463c1-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="463c1-142">此外，Lync Server 组件更新现已作为 Windows 更新的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="463c1-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="463c1-143">必须同时在运行 Lync Server 且适用这些更新的所有服务器上同时更新所有 Lync Server 组件更新。</span><span class="sxs-lookup"><span data-stu-id="463c1-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="463c1-144">运行 Lync Server 2013 最佳实践分析工具</span><span class="sxs-lookup"><span data-stu-id="463c1-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="463c1-145">Lync Server 2013 最佳实践分析工具是一种诊断工具，它收集配置信息，并根据 Microsoft 最佳实践确定是否设置配置。</span><span class="sxs-lookup"><span data-stu-id="463c1-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="463c1-146">此工具的文档位于[Lync Server 2013 最佳实践分析](lync-server-2013-lync-server-best-practices-analyzer.md)工具中。</span><span class="sxs-lookup"><span data-stu-id="463c1-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="463c1-147">该工具会将部署的配置数据与 Lync Server 的一组预定义的规则进行比较，并报告潜在问题。</span><span class="sxs-lookup"><span data-stu-id="463c1-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="463c1-148">对于报告的每个问题，该工具都提供了 Lync Server 环境中的当前配置以及建议的配置。</span><span class="sxs-lookup"><span data-stu-id="463c1-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="463c1-149">使用正确的网络访问，该工具可以检查运行 Lync Server 2013 的 AD DS 和服务器，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="463c1-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="463c1-150">主动执行运行状况检查，验证是否根据建议的最佳实践设置了配置</span><span class="sxs-lookup"><span data-stu-id="463c1-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="463c1-151">生成问题列表，如最佳配置设置或不受支持的或建议的选项</span><span class="sxs-lookup"><span data-stu-id="463c1-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="463c1-152">判断系统的常规运行状况</span><span class="sxs-lookup"><span data-stu-id="463c1-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="463c1-153">帮助解决特定问题</span><span class="sxs-lookup"><span data-stu-id="463c1-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="463c1-154">提示您下载更新（如果有）</span><span class="sxs-lookup"><span data-stu-id="463c1-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="463c1-155">提供有关报告问题的联机和本地文档，并包括故障排除提示</span><span class="sxs-lookup"><span data-stu-id="463c1-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="463c1-156">生成可被捕获以供以后查看的配置信息</span><span class="sxs-lookup"><span data-stu-id="463c1-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="463c1-157">确保在所有 Lync Server 2013 服务器上安装 RTCBPA，并生成每周运行状况检查报告。</span><span class="sxs-lookup"><span data-stu-id="463c1-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="463c1-158">如果需要，请记下结果并更正。</span><span class="sxs-lookup"><span data-stu-id="463c1-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="463c1-159">查看 SLA 性能图</span><span class="sxs-lookup"><span data-stu-id="463c1-159">Review SLA performance figures</span></span>

<span data-ttu-id="463c1-160">检查上一周的关键性能数据。</span><span class="sxs-lookup"><span data-stu-id="463c1-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="463c1-161">查看针对 SLA 要求的性能。</span><span class="sxs-lookup"><span data-stu-id="463c1-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="463c1-162">确定未满足其目标的趋势和项目。</span><span class="sxs-lookup"><span data-stu-id="463c1-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="463c1-163">查看 System Center Operations Manager 管理包和体验质量报告</span><span class="sxs-lookup"><span data-stu-id="463c1-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="463c1-164">获取并查看 Lync Server 2013 管理包和体验质量报告。</span><span class="sxs-lookup"><span data-stu-id="463c1-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="463c1-165">生成和查看企业版池的数据库报告</span><span class="sxs-lookup"><span data-stu-id="463c1-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="463c1-166">**生成池报告**</span><span class="sxs-lookup"><span data-stu-id="463c1-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="463c1-167">打开 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="463c1-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="463c1-168">在控制台树中，展开 "林" 节点，展开 "**企业版池**"，然后单击要为其生成数据库报告的池。</span><span class="sxs-lookup"><span data-stu-id="463c1-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="463c1-169">在详细信息窗格中，单击 "**数据库**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="463c1-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="463c1-170">在 "**数据库**" 选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="463c1-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="463c1-171">若要查看数据库的名称，请展开 "**常规设置**"，然后查看数据库名称。</span><span class="sxs-lookup"><span data-stu-id="463c1-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="463c1-172">若要检索池的当前用户汇总统计信息，请展开 "**用户摘要报告**"，单击 "**开始**"，然后查看结果。</span><span class="sxs-lookup"><span data-stu-id="463c1-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="463c1-173">若要检索池的单个用户的当前每用户数据，请展开 "**每用户报告**"，键入用户的 SIP URI，单击 "**开始**"，然后查看结果。</span><span class="sxs-lookup"><span data-stu-id="463c1-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="463c1-174">若要检索池的当前会议摘要统计信息，请展开 "**会议摘要报告**"，单击 "**开始**"，然后查看结果。</span><span class="sxs-lookup"><span data-stu-id="463c1-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="463c1-175">对于每个企业版池，管理员可以使用 "**数据库**" 选项卡查看数据库名称，并从数据库中检索和查看报告。</span><span class="sxs-lookup"><span data-stu-id="463c1-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="463c1-176">数据库报告和说明</span><span class="sxs-lookup"><span data-stu-id="463c1-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="463c1-177">分区</span><span class="sxs-lookup"><span data-stu-id="463c1-177">Section</span></span></th>
<th><span data-ttu-id="463c1-178">Description</span><span class="sxs-lookup"><span data-stu-id="463c1-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="463c1-179">用户摘要报告</span><span class="sxs-lookup"><span data-stu-id="463c1-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="463c1-180">Dbanalyze/v/report：/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="463c1-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="463c1-181">此部分显示有关池中用户的聚合信息，例如已启用的用户数、每个用户的平均联系人数以及特定功能的用户数。</span><span class="sxs-lookup"><span data-stu-id="463c1-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="463c1-182">在使用这些报告时，以下信息可能很有帮助：</span><span class="sxs-lookup"><span data-stu-id="463c1-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="463c1-183">已启用的用户是通过使用 Active Directory 用户和计算机管理单元启用了 Lync Server 2013 的用户。</span><span class="sxs-lookup"><span data-stu-id="463c1-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="463c1-184">"活动用户" 是已登录或已注册的用户。</span><span class="sxs-lookup"><span data-stu-id="463c1-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="463c1-185">摘要报告还提供了有关联系人的一组统计信息。</span><span class="sxs-lookup"><span data-stu-id="463c1-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="463c1-186">这些统计信息仅对至少已登录一次且至少有一个联系人的用户群体有效。</span><span class="sxs-lookup"><span data-stu-id="463c1-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="463c1-187">因此，您通常不会看到最小数量为0的联系人。</span><span class="sxs-lookup"><span data-stu-id="463c1-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="463c1-188">由于此行为，如果用户没有联系人（但在用户已注册的情况下处于活动状态），您可能会看到： &lt;对于某些&gt;统计信息字段为空。</span><span class="sxs-lookup"><span data-stu-id="463c1-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463c1-189">每用户报告</span><span class="sxs-lookup"><span data-stu-id="463c1-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="463c1-190">Dbanalyze/v/report： disk [/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="463c1-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="463c1-191">与通过用户群体计算的摘要报告不同，这些报告是有关特定用户的报告。</span><span class="sxs-lookup"><span data-stu-id="463c1-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463c1-192">会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="463c1-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="463c1-193">Dbanalyze/v/report：会议 [/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="463c1-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="463c1-194">此部分显示有关池的会议摘要统计信息的聚合信息，例如活动会议数和参与者总数。</span><span class="sxs-lookup"><span data-stu-id="463c1-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="463c1-195">运行带宽使用率分析器</span><span class="sxs-lookup"><span data-stu-id="463c1-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="463c1-196">带宽利用率分析器是一种工具，该工具通过企业网络中的多个 WAN 链接的 UC 终结点创建有关带宽消耗的各种视图的报告。</span><span class="sxs-lookup"><span data-stu-id="463c1-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="463c1-197">这些报告可用于了解当前的带宽使用模式，并可帮助进行带宽容量规划。</span><span class="sxs-lookup"><span data-stu-id="463c1-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="463c1-198">它还会对分配给各个链路的带宽容量进行迭代。</span><span class="sxs-lookup"><span data-stu-id="463c1-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="463c1-199">此工具执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="463c1-199">This tool does the following:</span></span>

  - <span data-ttu-id="463c1-200">通过网络生成音频使用情况的特定报告</span><span class="sxs-lookup"><span data-stu-id="463c1-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="463c1-201">有助于在分配给各个链路的带宽容量中进行更有效的容量规划和迭代</span><span class="sxs-lookup"><span data-stu-id="463c1-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="463c1-202">带宽利用率分析器可生成带宽容量和使用情况报告的图形化绘图。</span><span class="sxs-lookup"><span data-stu-id="463c1-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="463c1-203">它们分别为：</span><span class="sxs-lookup"><span data-stu-id="463c1-203">They are as follows:</span></span>

  - <span data-ttu-id="463c1-204">企业网络中的所有 WAN 链路</span><span class="sxs-lookup"><span data-stu-id="463c1-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="463c1-205">通过选定的已选择的 WAN 链接进行筛选</span><span class="sxs-lookup"><span data-stu-id="463c1-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="463c1-206">通过已超出链接容量的 WAN 链路进行筛选</span><span class="sxs-lookup"><span data-stu-id="463c1-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="463c1-207">使用预配带宽下的 WAN 链路进行筛选</span><span class="sxs-lookup"><span data-stu-id="463c1-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="463c1-208">按 WAN 链路进行筛选，这些链路达到关键级别（超过 WAN 链路的带宽使用率大于90% 的带宽使用率）</span><span class="sxs-lookup"><span data-stu-id="463c1-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="463c1-209">按 WAN 链接类型（网络站点链接、区域间链接和站点内的链接）进行筛选</span><span class="sxs-lookup"><span data-stu-id="463c1-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="463c1-210">按网络区域筛选</span><span class="sxs-lookup"><span data-stu-id="463c1-210">Filtered by network region</span></span>

<span data-ttu-id="463c1-211">此工具的文档在[Lync Server 2013 资源工具包工具文档](https://go.microsoft.com/fwlink/?linkid=623245)中提供。</span><span class="sxs-lookup"><span data-stu-id="463c1-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="463c1-212">另请参阅</span><span class="sxs-lookup"><span data-stu-id="463c1-212">See Also</span></span>


[<span data-ttu-id="463c1-213">每周任务清单</span><span class="sxs-lookup"><span data-stu-id="463c1-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

