---
title: 打开和使用呼叫质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: '了解如何打开和使用呼叫质量仪表板，获取通话质量的摘要报告。 '
ms.openlocfilehash: 9e9c70c88aec9fcdf898d94a17f46f76bd2c608a
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559883"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="860dc-103">打开和使用 Microsoft 团队和 Skype for business Online 的通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="860dc-103">Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="860dc-104">了解如何配置 Office 365 组织以使用呼叫质量仪表板来监控通话质量。</span><span class="sxs-lookup"><span data-stu-id="860dc-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="860dc-105">通话质量仪表板（CQD）可深入了解使用 Microsoft 团队和 Skype for business Online 服务进行的通话的质量。</span><span class="sxs-lookup"><span data-stu-id="860dc-105">Call Quality Dashboard (CQD) provides insight into the quality of calls made using Microsoft Teams and Skype for Business Online services.</span></span> <span data-ttu-id="860dc-106">本主题介绍了开始收集可用于解决通话质量问题的数据的步骤。</span><span class="sxs-lookup"><span data-stu-id="860dc-106">This topic describes the steps to start collecting data you can use to troubleshoot call quality issues.</span></span>

<span data-ttu-id="860dc-107">目前，高级 CQD 和 CQD 都可供使用。</span><span class="sxs-lookup"><span data-stu-id="860dc-107">Currently, Advanced CQD and CQD are both available for use.</span></span> <span data-ttu-id="860dc-108">可在<span>https://cqd.teams.microsoft.com</span>使用高级 CQD。</span><span class="sxs-lookup"><span data-stu-id="860dc-108">Advanced CQD is available at <span>https://cqd.teams.microsoft.com</span>.</span></span> <span data-ttu-id="860dc-109">新 URL，但具有管理员凭据的相同日志。</span><span class="sxs-lookup"><span data-stu-id="860dc-109">New URL but the same log in with your administrator credentials.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="860dc-110">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="860dc-110">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="860dc-111">2020年1月[的新增功能：下载 CQD 的 POWER BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="860dc-111">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="860dc-112">可用于分析和报告 CQD 数据的自定义 Power BI 模板。</span><span class="sxs-lookup"><span data-stu-id="860dc-112">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="860dc-113">已阅读 "[使用 POWER BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)" 以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-113">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="latest-changes-and-updates"></a><span data-ttu-id="860dc-114">最新更改和更新</span><span class="sxs-lookup"><span data-stu-id="860dc-114">Latest changes and updates</span></span>


<span data-ttu-id="860dc-115">更新后的 CQD （2019年11月早些时候）提供接近实时 CQD 仪表板的时间。</span><span class="sxs-lookup"><span data-stu-id="860dc-115">The updated CQD (as of early November 2019) delivers a Near Real-Time CQD dashboard.</span></span> <span data-ttu-id="860dc-116">CQD 数据现在将在30分钟内可用（与上一个 CQD 相比，它平均为24小时）。</span><span class="sxs-lookup"><span data-stu-id="860dc-116">CQD data is now available on average in 30 minutes (in comparison to the previous CQD which is on average of 24 hours).</span></span>  <span data-ttu-id="860dc-117">已更新的 CQD 使用最终用户可识别信息（EUII），使管理员能够向下钻取并放大到用户级别。</span><span class="sxs-lookup"><span data-stu-id="860dc-117">The updated CQD uses End User Identifiable Information (EUII), giving admins the ability to drill down and zoom in to the user level.</span></span> <span data-ttu-id="860dc-118">还提供支持新方案的报表交互，例如：</span><span class="sxs-lookup"><span data-stu-id="860dc-118">There is also report interactivity to support new scenarios such as:</span></span>


- <span data-ttu-id="860dc-119">按地区呼叫质量：</span><span class="sxs-lookup"><span data-stu-id="860dc-119">Call Quality by Region:</span></span>
  - <span data-ttu-id="860dc-120">按区域日期</span><span class="sxs-lookup"><span data-stu-id="860dc-120">date-by-region</span></span>
  - <span data-ttu-id="860dc-121">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="860dc-121">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="860dc-122">特定位置</span><span class="sxs-lookup"><span data-stu-id="860dc-122">specific locations</span></span>
  - <span data-ttu-id="860dc-123">特定子网</span><span class="sxs-lookup"><span data-stu-id="860dc-123">specific subnet</span></span>
  - <span data-ttu-id="860dc-124">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="860dc-124">impacted user or users</span></span>

- <span data-ttu-id="860dc-125">按地区呼叫可靠性/失败：</span><span class="sxs-lookup"><span data-stu-id="860dc-125">Call Reliability/Failure by Region:</span></span>
  - <span data-ttu-id="860dc-126">按区域日期</span><span class="sxs-lookup"><span data-stu-id="860dc-126">date-by-region</span></span>
  - <span data-ttu-id="860dc-127">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="860dc-127">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="860dc-128">特定位置</span><span class="sxs-lookup"><span data-stu-id="860dc-128">specific locations</span></span>
  - <span data-ttu-id="860dc-129">特定子网</span><span class="sxs-lookup"><span data-stu-id="860dc-129">specific subnet</span></span>
  - <span data-ttu-id="860dc-130">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="860dc-130">impacted user or users</span></span>

- <span data-ttu-id="860dc-131">按区域对我的呼叫（RMC）进行评级：从按区域聚合到特定位置的特定位置到提供低 RMC 等级的用户。</span><span class="sxs-lookup"><span data-stu-id="860dc-131">Rate My Call (RMC) by Region: from month-by-region aggregated down to specific locations to users who provide low RMC ratings.</span></span> <span data-ttu-id="860dc-132">CQD v3 还包括逐字反馈。</span><span class="sxs-lookup"><span data-stu-id="860dc-132">CQD v3 also includes verbatim feedback.</span></span>
- <span data-ttu-id="860dc-133">帮助者：可用于 P2P 呼叫或会议的特定用户或所有参与者和通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-133">Helpdesk: available for a specific user on P2P calls or Meetings, or for all participants and call details.</span></span> <span data-ttu-id="860dc-134">帮助识别基于网络位置、设备或固件的可能系统问题。</span><span class="sxs-lookup"><span data-stu-id="860dc-134">Helps identify possible system issues based on network location, devices, or firmware.</span></span>  
- <span data-ttu-id="860dc-135">客户端版本：查看每个客户端版本的会话和用户计数，或向下钻取以查看每个客户端版本的用户名。</span><span class="sxs-lookup"><span data-stu-id="860dc-135">Client Versions: View the Session and Users counts for each Client Version, or drill down to User names for each client version.</span></span> <span data-ttu-id="860dc-136">产品和客户端类型的预生成筛选器帮助将版本集中到特定客户端。</span><span class="sxs-lookup"><span data-stu-id="860dc-136">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>
- <span data-ttu-id="860dc-137">终结点：显示映射到电脑/Mac 的 "生成/模型" 的计算机终结点。</span><span class="sxs-lookup"><span data-stu-id="860dc-137">Endpoints: Shows Machine Endpoints mapped to Make/Model of the PC/Mac.</span></span> <span data-ttu-id="860dc-138">按 "生成/模型" 显示聚合质量。</span><span class="sxs-lookup"><span data-stu-id="860dc-138">Shows aggregated quality by Make/Model.</span></span> <span data-ttu-id="860dc-139">映射数据的上载类似于生成数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-139">Mapping data is uploaded similar to Building data.</span></span>

<span data-ttu-id="860dc-140">如果 EUII access 不可用，则高级 CQD （V3）还提供 RBAC 支持。</span><span class="sxs-lookup"><span data-stu-id="860dc-140">Advanced CQD (V3) also provides RBAC support, in case EUII access is not available.</span></span>  

<span data-ttu-id="860dc-141">管理员可通过 CQD 版本3管理 Skype for business Server 2019 （不仅仅是 Skype for business Online 和 Microsoft 团队）。</span><span class="sxs-lookup"><span data-stu-id="860dc-141">An admin can manage Skype for Business Server 2019 (not just Skype for Business Online and Microsoft Teams) through CQD version 3.</span></span> <span data-ttu-id="860dc-142">这需要混合实现和使用 "调用数据" 连接器。</span><span class="sxs-lookup"><span data-stu-id="860dc-142">This requires a hybrid implementation and the use of Call Data Connector.</span></span> <span data-ttu-id="860dc-143">有关详细信息，请参阅[计划通话数据连接器](/SkypeForBusiness/hybrid/plan-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="860dc-143">See [Plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) for more information.</span></span>

<span data-ttu-id="860dc-144">已添加 CQD 版本2：</span><span class="sxs-lookup"><span data-stu-id="860dc-144">CQD version 2 added:</span></span>

- <span data-ttu-id="860dc-145">Microsoft 团队和 Skype for business Online 的数据</span><span class="sxs-lookup"><span data-stu-id="860dc-145">Data for Microsoft Teams and Skype for Business Online</span></span>
- <span data-ttu-id="860dc-146">摘要报告包括一个用于选择所有数据、Microsoft 团队数据或 Skype for Business Online 数据的产品筛选器</span><span class="sxs-lookup"><span data-stu-id="860dc-146">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data</span></span>
- <span data-ttu-id="860dc-147">更新了视频和 VBSS 流质量分类逻辑。</span><span class="sxs-lookup"><span data-stu-id="860dc-147">Updated Video and VBSS stream quality classification logic.</span></span> <span data-ttu-id="860dc-148">请参阅用于分类器定义的[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="860dc-148">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the classifier definitions.</span></span>

<span data-ttu-id="860dc-149">有关[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)的列表，请参阅本文。</span><span class="sxs-lookup"><span data-stu-id="860dc-149">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="860dc-150">若要查看有关仪表板的更新和更改的信息，请单击 "**好消息**" 中的链接！</span><span class="sxs-lookup"><span data-stu-id="860dc-150">To see information about updates and changes to the dashboard,  click the link in the **Good news!**</span></span> <span data-ttu-id="860dc-151">在仪表板上显示时横幅。</span><span class="sxs-lookup"><span data-stu-id="860dc-151">banner when it displays on the dashboard.</span></span>

<span data-ttu-id="860dc-152">CQD 版本1已提供 Skype for Business Server 2015 管理员以下功能：</span><span class="sxs-lookup"><span data-stu-id="860dc-152">CQD version 1 provided Skype for Business Server 2015 admins the following features:</span></span>

- <span data-ttu-id="860dc-153">访问缓存的报表数据以快速访问</span><span class="sxs-lookup"><span data-stu-id="860dc-153">Access to cached report data for fast access</span></span>
- <span data-ttu-id="860dc-154">指向用于共享和发布信息的报表页面的深层链接</span><span class="sxs-lookup"><span data-stu-id="860dc-154">Deep links to report pages for sharing and publishing information</span></span>
- <span data-ttu-id="860dc-155">简化的报表编辑和创建以及报表说明的可编辑元数据</span><span class="sxs-lookup"><span data-stu-id="860dc-155">Streamlined report editing and creation, and editable metadata for report descriptions</span></span>
- <span data-ttu-id="860dc-156">为在自定义仪表板中使用而提供对多维数据集数据的编程访问的 Web Api</span><span class="sxs-lookup"><span data-stu-id="860dc-156">Web APIs that give programmatic access to the cube data for use in custom dashboards</span></span>

## <a name="cqd-near-real-time-nrt-data"></a><span data-ttu-id="860dc-157">CQD 近实时（NRT）数据</span><span class="sxs-lookup"><span data-stu-id="860dc-157">CQD Near-Real-Time (NRT) Data</span></span>

<span data-ttu-id="860dc-158">高级 CQD （V3，发布2019年11月）使用近乎实时的数据馈送。</span><span class="sxs-lookup"><span data-stu-id="860dc-158">Advanced CQD (V3, released November 2019) uses a near-real-time data feed.</span></span> <span data-ttu-id="860dc-159">通话记录在通话结束后的30分钟内将在 CQD 门户中可用。</span><span class="sxs-lookup"><span data-stu-id="860dc-159">Call Records are available at the CQD portal within 30 minutes of the end of the call.</span></span> <span data-ttu-id="860dc-160">从 NRT 管道中调用记录仅在从数据集内删除几个月后才可用。</span><span class="sxs-lookup"><span data-stu-id="860dc-160">Call Records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> <span data-ttu-id="860dc-161">CQD v3 将当前 v2 管道中的数据与 v3 管道中的 NRT 数据合并。</span><span class="sxs-lookup"><span data-stu-id="860dc-161">CQD v3 merges data from the current v2 pipeline with NRT data from the v3 pipeline.</span></span> <span data-ttu-id="860dc-162">来自存档周期的数据的 v2 和 v3 门户查询将产生相同的结果。</span><span class="sxs-lookup"><span data-stu-id="860dc-162">Queries on the v2 and v3 portals for the data from the Archival period produce the same results.</span></span> <span data-ttu-id="860dc-163">NRT 数据的 V2 和 v3 数据查询和 NRT Data + PII 期间将有所不同。</span><span class="sxs-lookup"><span data-stu-id="860dc-163">V2 and v3 data queries for the NRT Data and NRT Data + PII periods will be different.</span></span>

### <a name="piieuii-data"></a><span data-ttu-id="860dc-164">PII/EUII 数据</span><span class="sxs-lookup"><span data-stu-id="860dc-164">PII/EUII Data</span></span>

<span data-ttu-id="860dc-165">PII 或 EUII 数据仅来自 v3 管道。</span><span class="sxs-lookup"><span data-stu-id="860dc-165">PII or EUII data only comes from the v3 pipeline.</span></span> <span data-ttu-id="860dc-166">由于合规性原因，PII/EUII 数据仅保留30天。</span><span class="sxs-lookup"><span data-stu-id="860dc-166">Due to compliance reasons, PII/EUII data is only kept for 30 days.</span></span> <span data-ttu-id="860dc-167">由于 NRT 数据超过30天的标记，将清除 PII/EUII 字段，从而导致 PII NRT 数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-167">As NRT data crosses the 30-day mark, the PII/EUII fields are cleared out, resulting in PII-free NRT data.</span></span> <span data-ttu-id="860dc-168">PII/EUII 字段是：</span><span class="sxs-lookup"><span data-stu-id="860dc-168">The PII/EUII fields are:</span></span>

- <span data-ttu-id="860dc-169">完整 IP 地址</span><span class="sxs-lookup"><span data-stu-id="860dc-169">Full IP address</span></span>
- <span data-ttu-id="860dc-170">媒体访问控制（MAC）地址</span><span class="sxs-lookup"><span data-stu-id="860dc-170">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="860dc-171">基本服务集标识符（BSSID）</span><span class="sxs-lookup"><span data-stu-id="860dc-171">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="860dc-172">会话初始协议（SIP） URI （仅 Skype for business）</span><span class="sxs-lookup"><span data-stu-id="860dc-172">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="860dc-173">用户主体名称 (UPN)</span><span class="sxs-lookup"><span data-stu-id="860dc-173">User Principal Name (UPN)</span></span>
- <span data-ttu-id="860dc-174">计算机终结点名称</span><span class="sxs-lookup"><span data-stu-id="860dc-174">Machine Endpoint Name</span></span>
- <span data-ttu-id="860dc-175">用户逐字反馈</span><span class="sxs-lookup"><span data-stu-id="860dc-175">User Verbatim Feedback</span></span>
- <span data-ttu-id="860dc-176">对象 ID （终结点用户的 Active Directory 对象 ID）</span><span class="sxs-lookup"><span data-stu-id="860dc-176">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="date-controls"></a><span data-ttu-id="860dc-177">日期控件</span><span class="sxs-lookup"><span data-stu-id="860dc-177">Date controls</span></span>

<span data-ttu-id="860dc-178">CQD v3 将添加以下新的滚动趋势类型：</span><span class="sxs-lookup"><span data-stu-id="860dc-178">CQD v3 adds the following new Rolling Trend types:</span></span>

- <span data-ttu-id="860dc-179">5天</span><span class="sxs-lookup"><span data-stu-id="860dc-179">5-day</span></span>
- <span data-ttu-id="860dc-180">7天</span><span class="sxs-lookup"><span data-stu-id="860dc-180">7-day</span></span>
- <span data-ttu-id="860dc-181">30天</span><span class="sxs-lookup"><span data-stu-id="860dc-181">30-day</span></span>
- <span data-ttu-id="860dc-182">60-day</span><span class="sxs-lookup"><span data-stu-id="860dc-182">60-day</span></span>
- <span data-ttu-id="860dc-183">90-day</span><span class="sxs-lookup"><span data-stu-id="860dc-183">90-day</span></span>

<span data-ttu-id="860dc-184">URL 日期参数现在可接受 "天" 字段。</span><span class="sxs-lookup"><span data-stu-id="860dc-184">The URL Date parameter can now accept a Day field.</span></span> <span data-ttu-id="860dc-185">"滚动日期" 报告将 "YYYY-MM-DD 格式" 中指定的日期用作趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="860dc-185">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span>  <span data-ttu-id="860dc-186">URL 日期参数 "00" 表示 "今日"。</span><span class="sxs-lookup"><span data-stu-id="860dc-186">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="860dc-187">URL</span><span class="sxs-lookup"><span data-stu-id="860dc-187">URL</span></span>| <span data-ttu-id="860dc-188">滚动日趋势的结束日期</span><span class="sxs-lookup"><span data-stu-id="860dc-188">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="860dc-189"><span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="860dc-189"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="860dc-190">2019年2月的当前日期</span><span class="sxs-lookup"><span data-stu-id="860dc-190">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="860dc-191"><span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="860dc-191"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="860dc-192">2019年2月15日</span><span class="sxs-lookup"><span data-stu-id="860dc-192">Feb 15, 2019</span></span>|
|<span data-ttu-id="860dc-193"><span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/00/</span></span><span class="sxs-lookup"><span data-stu-id="860dc-193"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="860dc-194">当前日期</span><span class="sxs-lookup"><span data-stu-id="860dc-194">Current Day</span></span>|
|||

<span data-ttu-id="860dc-195">默认情况下，该月的当前日期用作滚动日期趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="860dc-195">By default the current day of the month is used as the last day of the Rolling Day Trend.</span></span>

### <a name="drill-thru-functionality"></a><span data-ttu-id="860dc-196">钻取功能</span><span class="sxs-lookup"><span data-stu-id="860dc-196">Drill Thru Functionality</span></span>

<span data-ttu-id="860dc-197">CQD v3 支持使用 SPD 报表中的钻取或向下钻取字段。</span><span class="sxs-lookup"><span data-stu-id="860dc-197">CQD v3 supports the use of drill through or drill-down fields in SPD reports.</span></span> <span data-ttu-id="860dc-198">如果选择这些维度字段，报表将自动打开不同的 "报表" 选项卡，并筛选所选值。</span><span class="sxs-lookup"><span data-stu-id="860dc-198">If these dimension fields are selected,  the report automatically opens a different report tab and filters on the selected value.</span></span> <span data-ttu-id="860dc-199">将鼠标悬停在其上方时，具有分配的钻取筛选器的字段将由不同的光标图标（指针）进行区分。</span><span class="sxs-lookup"><span data-stu-id="860dc-199">Fields with an assigned drill through filter are distinguished by a different cursor icon (the pointer) when you hover over them.</span></span>

<span data-ttu-id="860dc-200">选中 "钻取" 字段时，仪表板将自动导航到新的指定选项卡，并应用具有所选值的筛选器。</span><span class="sxs-lookup"><span data-stu-id="860dc-200">When a drill through field is selected, the Dashboard automatically navigates to the new, specified tab and applies a filter with the selected value.</span></span> <span data-ttu-id="860dc-201">如果该选项卡具有自己的钻取字段，并且选择了一个，则以前的钻取筛选器和新的钻取筛选器以及新的钻取。</span><span class="sxs-lookup"><span data-stu-id="860dc-201">If that tab has its own drill through fields and one is selected, the previous drill through filters and the new one all propagate forward.</span></span> <span data-ttu-id="860dc-202">这允许你构建可逐渐缩小结果数据集的报表。</span><span class="sxs-lookup"><span data-stu-id="860dc-202">This allows you to build a report that progressively narrows the resulting data set.</span></span>

<span data-ttu-id="860dc-203">例如，在通话质量的钻取报表中，用户可以单击想要 "钻取" 的日期，这将导致 "位置" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="860dc-203">For example, in a Call quality drill-through report, a user can click the date they would like to 'drill-through', which leads to the Location tab.</span></span>

![屏幕截图：显示钻取报表](media/CQD-drill-thru-report.png)

<span data-ttu-id="860dc-205">可以从 "位置" 选项卡添加多个日期，例如将2019-09-22 添加到日期：2019-09-24：</span><span class="sxs-lookup"><span data-stu-id="860dc-205">You can add multiple dates from the location tab, such as adding 2019-09-22 to Date: 2019-09-24:</span></span> 

![屏幕截图：向钻取报表添加日期](media/CQD-add-date.png)

> [!NOTE]
> <span data-ttu-id="860dc-207">不要直接跳转到最后一个选项卡。没有从以前的钻取中选择的筛选器，结果将太大，无法在表格上显示。</span><span class="sxs-lookup"><span data-stu-id="860dc-207">Don't jump directly to the last tab. Without filters selected from a previous drill-through the results would be too large to show on a table.</span></span>

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="860dc-208">激活 Microsoft 通话质量仪表板（CQD）摘要报告</span><span class="sxs-lookup"><span data-stu-id="860dc-208">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="860dc-209">在开始使用 CQD 之前，请为您的 Office 365 组织激活它，如下所示：</span><span class="sxs-lookup"><span data-stu-id="860dc-209">Before you can start using CQD, activate it for your Office 365 organization as follows:</span></span>

<span data-ttu-id="860dc-210">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="860dc-210">![An icon that shows the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="860dc-211">使用 Microsoft 团队服务管理员帐户登录到你的 Office 365 组织，然后选择 "**管理员**" 磁贴以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="860dc-211">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="860dc-212">在左窗格中的 "**管理中心**" 下，选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。</span><span class="sxs-lookup"><span data-stu-id="860dc-212">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
3. <span data-ttu-id="860dc-213">在 "Microsoft 团队管理中心" 中，在左窗格中选择 "**呼叫质量" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="860dc-213">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
4. <span data-ttu-id="860dc-214">\(在打开 https://<span>cqd.teams.microsoft.com<span/>\)的页面上，单击 "**登录**"，然后输入全局管理员帐户或 microsoft 团队服务管理员帐户信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-214">On the page that opens \(https://<span>cqd.teams.microsoft.com<span/>\), click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span>

    ![屏幕截图：显示凭据提示](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="860dc-216">登录后，一旦激活，CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-216">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="860dc-217">可能需要一个或多个小时才能处理足够的数据，以在报表中显示有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="860dc-217">It may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="860dc-218">![](media/sfb-logo-30x30.png) **使用 skype for business 旧版门户**的 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="860dc-218">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="860dc-219">使用管理员帐户登录到您的 Office 365 组织，然后选择 "**管理员**" 磁贴以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="860dc-219">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="860dc-220">在左窗格中的 "**管理中心**" 下，选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。</span><span class="sxs-lookup"><span data-stu-id="860dc-220">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
3. <span data-ttu-id="860dc-221">在 Microsoft 团队管理中心中，在左窗格中选择 "**旧版门户**"，选择 "**工具**"，然后选择 " **Skype for Business Online 呼叫质量" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="860dc-221">In the Microsoft Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

     ![屏幕截图：选择 "呼叫质量" 仪表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="860dc-223">在打开的页面上，用全局管理员帐户登录，然后在出现提示时提供帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="860dc-223">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="860dc-224">登录后，"呼叫质量" 仪表板将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-224">After you sign in, once activated, the Call Quality Dashboard will begin collecting and processing data.</span></span>

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="860dc-225">Microsoft 团队和 Skype for business Online 的通话质量仪表板的功能</span><span class="sxs-lookup"><span data-stu-id="860dc-225">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="860dc-226"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="860dc-226"><a name="BKMKFeaturesOfTheCQD"> </a></span></span>


<span data-ttu-id="860dc-227">CQD 摘要报告提供为详细报告规划的功能的子集。</span><span class="sxs-lookup"><span data-stu-id="860dc-227">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="860dc-228">此处概括介绍了版本之间的差异：</span><span class="sxs-lookup"><span data-stu-id="860dc-228">The differences between the editions are summarized here:</span></span>
  
|<span data-ttu-id="860dc-229">功能</span><span class="sxs-lookup"><span data-stu-id="860dc-229">Feature</span></span>|<span data-ttu-id="860dc-230">摘要报告</span><span class="sxs-lookup"><span data-stu-id="860dc-230">Summary Reports</span></span>|<span data-ttu-id="860dc-231">详细报告</span><span class="sxs-lookup"><span data-stu-id="860dc-231">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="860dc-232">应用程序共享跃点数</span><span class="sxs-lookup"><span data-stu-id="860dc-232">Application sharing metric</span></span> | <span data-ttu-id="860dc-233">否</span><span class="sxs-lookup"><span data-stu-id="860dc-233">No</span></span> | <span data-ttu-id="860dc-234">是</span><span class="sxs-lookup"><span data-stu-id="860dc-234">Yes</span></span> |
|<span data-ttu-id="860dc-235">客户构建信息支持</span><span class="sxs-lookup"><span data-stu-id="860dc-235">Customer building information support</span></span> | <span data-ttu-id="860dc-236">是</span><span class="sxs-lookup"><span data-stu-id="860dc-236">Yes</span></span> | <span data-ttu-id="860dc-237">是 </span><span class="sxs-lookup"><span data-stu-id="860dc-237">Yes</span></span> |
|<span data-ttu-id="860dc-238">客户终结点信息支持</span><span class="sxs-lookup"><span data-stu-id="860dc-238">Customer endpoint information support</span></span> | <span data-ttu-id="860dc-239">仅在<span>cqd.teams.microsoft.com 中<span/></span><span class="sxs-lookup"><span data-stu-id="860dc-239">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="860dc-240">仅在<span>cqd.teams.microsoft.com 中<span/></span><span class="sxs-lookup"><span data-stu-id="860dc-240">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="860dc-241">向下钻取分析支持</span><span class="sxs-lookup"><span data-stu-id="860dc-241">Drill down analysis support</span></span>   | <span data-ttu-id="860dc-242">否</span><span class="sxs-lookup"><span data-stu-id="860dc-242">No</span></span>   | <span data-ttu-id="860dc-243">是</span><span class="sxs-lookup"><span data-stu-id="860dc-243">Yes</span></span>   |
|<span data-ttu-id="860dc-244">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="860dc-244">Media reliability metrics</span></span>   | <span data-ttu-id="860dc-245">否</span><span class="sxs-lookup"><span data-stu-id="860dc-245">No</span></span>   | <span data-ttu-id="860dc-246">是</span><span class="sxs-lookup"><span data-stu-id="860dc-246">Yes</span></span>   |
|<span data-ttu-id="860dc-247">现成的报表</span><span class="sxs-lookup"><span data-stu-id="860dc-247">Out-of-the-box reports</span></span>   | <span data-ttu-id="860dc-248">是</span><span class="sxs-lookup"><span data-stu-id="860dc-248">Yes</span></span>   | <span data-ttu-id="860dc-249">是 </span><span class="sxs-lookup"><span data-stu-id="860dc-249">Yes</span></span>   |
|<span data-ttu-id="860dc-250">概述报表</span><span class="sxs-lookup"><span data-stu-id="860dc-250">Overview reports</span></span>   | <span data-ttu-id="860dc-251">是</span><span class="sxs-lookup"><span data-stu-id="860dc-251">Yes</span></span>   | <span data-ttu-id="860dc-252">是 </span><span class="sxs-lookup"><span data-stu-id="860dc-252">Yes</span></span>   |
|<span data-ttu-id="860dc-253">每用户报告集</span><span class="sxs-lookup"><span data-stu-id="860dc-253">Per-user report set</span></span>   | <span data-ttu-id="860dc-254">否</span><span class="sxs-lookup"><span data-stu-id="860dc-254">No</span></span>   | <span data-ttu-id="860dc-255">是</span><span class="sxs-lookup"><span data-stu-id="860dc-255">Yes</span></span>   |
|<span data-ttu-id="860dc-256">报表集自定义（添加、删除、修改报表）</span><span class="sxs-lookup"><span data-stu-id="860dc-256">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="860dc-257">否</span><span class="sxs-lookup"><span data-stu-id="860dc-257">No</span></span>   | <span data-ttu-id="860dc-258">是</span><span class="sxs-lookup"><span data-stu-id="860dc-258">Yes</span></span>   |
|<span data-ttu-id="860dc-259">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="860dc-259">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="860dc-260">否</span><span class="sxs-lookup"><span data-stu-id="860dc-260">No</span></span>   | <span data-ttu-id="860dc-261">是</span><span class="sxs-lookup"><span data-stu-id="860dc-261">Yes</span></span>   |
|<span data-ttu-id="860dc-262">视频指标</span><span class="sxs-lookup"><span data-stu-id="860dc-262">Video metrics</span></span>   | <span data-ttu-id="860dc-263">否</span><span class="sxs-lookup"><span data-stu-id="860dc-263">No</span></span>   | <span data-ttu-id="860dc-264">是</span><span class="sxs-lookup"><span data-stu-id="860dc-264">Yes</span></span>   |
|<span data-ttu-id="860dc-265">可用数据量</span><span class="sxs-lookup"><span data-stu-id="860dc-265">Amount of data available</span></span>   | <span data-ttu-id="860dc-266">过去12个月</span><span class="sxs-lookup"><span data-stu-id="860dc-266">Last 12 months</span></span>   | <span data-ttu-id="860dc-267">过去12个月</span><span class="sxs-lookup"><span data-stu-id="860dc-267">Last 12 months</span></span>   |
|<span data-ttu-id="860dc-268">Microsoft 团队数据</span><span class="sxs-lookup"><span data-stu-id="860dc-268">Microsoft Teams data</span></span>   | <span data-ttu-id="860dc-269">是</span><span class="sxs-lookup"><span data-stu-id="860dc-269">Yes</span></span>   | <span data-ttu-id="860dc-270">是 </span><span class="sxs-lookup"><span data-stu-id="860dc-270">Yes</span></span>   |
| | | |

### <a name="out-of-the-box-reports"></a><span data-ttu-id="860dc-271">现成的报表</span><span class="sxs-lookup"><span data-stu-id="860dc-271">Out-of-the-box reports</span></span>

<span data-ttu-id="860dc-272">所有版本的 CQD 都提供了一种可提供通话质量指标的体验，无需创建新报表。</span><span class="sxs-lookup"><span data-stu-id="860dc-272">All editions of CQD provide an experience that gives you call quality metrics without the need to create new reports.</span></span> <span data-ttu-id="860dc-273">在后端处理完数据后，您将在报告中看到通话质量数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-273">Once data is processed in the back-end, you see call quality data in the reports.</span></span>

<span data-ttu-id="860dc-274">2020年1月[的新增功能：下载 CQD 的 POWER BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="860dc-274">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="860dc-275">可用于分析和报告 CQD 数据的自定义 Power BI 模板。</span><span class="sxs-lookup"><span data-stu-id="860dc-275">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="860dc-276">概述报表</span><span class="sxs-lookup"><span data-stu-id="860dc-276">Overview reports</span></span>

<span data-ttu-id="860dc-277">CQD 的所有版本都为整体通话质量信息提供高级别的入口点，但信息在摘要报告中的显示方式不同于详细的报告。</span><span class="sxs-lookup"><span data-stu-id="860dc-277">All editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from Detailed Reports.</span></span>  
  
<span data-ttu-id="860dc-278">摘要报告提供简化的选项卡式页面报告视图，以便你可以快速浏览和理解整体通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="860dc-278">Summary Reports provide a simplified tabbed page report view so you can quickly browse and understand the overall call quality status and trends.</span></span>

<span data-ttu-id="860dc-279">四个选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="860dc-279">The four tabs include:</span></span>
  
- <span data-ttu-id="860dc-280">**整体通话质量**-提供有关所有流的信息，它是显示每月和每天的趋势的聚合：</span><span class="sxs-lookup"><span data-stu-id="860dc-280">**Overall Call Quality** — provides information about all streams, which is an aggregation that shows monthly and daily trends for:</span></span>
  - <span data-ttu-id="860dc-281">服务器-客户端流</span><span class="sxs-lookup"><span data-stu-id="860dc-281">Server-Client streams</span></span>
  - <span data-ttu-id="860dc-282">客户端-客户端流</span><span class="sxs-lookup"><span data-stu-id="860dc-282">Client-Client streams</span></span>
  - <span data-ttu-id="860dc-283">单独的服务器-客户端和客户端-客户端流</span><span class="sxs-lookup"><span data-stu-id="860dc-283">Separate Server-Client and Client-Client streams</span></span>
- <span data-ttu-id="860dc-284">**服务器-客户端**-提供服务器和客户端终结点之间的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-284">**Server—Client** — provides details for the streams between Server and Client endpoints.</span></span>
- <span data-ttu-id="860dc-285">**客户端-客户端**-提供两个客户端终结点之间的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-285">**Client—Client** — provides details for the streams between two Client endpoints.</span></span>
- <span data-ttu-id="860dc-286">**语音质量 SLA** —提供有关 Skype For Business Online 语音质量 SLA 中所含通话的信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-286">**Voice Quality SLA** — provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>

> [!NOTE]
> <span data-ttu-id="860dc-287">CQD 版本3适用于 Microsoft 团队、Skype for business Online 和 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="860dc-287">CQD Version 3 works with Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span> <span data-ttu-id="860dc-288">要将 CQD 与 Skype for Business Server 2019 配合使用，您必须[配置 "呼叫数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)"。</span><span class="sxs-lookup"><span data-stu-id="860dc-288">To use CQD with Skype for Business Server 2019, you will have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="860dc-289">请参阅在开始之前[计划通话数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="860dc-289">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>

- <span data-ttu-id="860dc-290">按地区呼叫质量：</span><span class="sxs-lookup"><span data-stu-id="860dc-290">Call Quality by Region:</span></span>

  - <span data-ttu-id="860dc-291">按区域日期</span><span class="sxs-lookup"><span data-stu-id="860dc-291">date-by-region</span></span>
  - <span data-ttu-id="860dc-292">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="860dc-292">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="860dc-293">特定位置</span><span class="sxs-lookup"><span data-stu-id="860dc-293">specific locations</span></span>
  - <span data-ttu-id="860dc-294">特定子网</span><span class="sxs-lookup"><span data-stu-id="860dc-294">specific subnet</span></span>
  - <span data-ttu-id="860dc-295">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="860dc-295">impacted user or users</span></span>

- <span data-ttu-id="860dc-296">按地区呼叫可靠性/失败：</span><span class="sxs-lookup"><span data-stu-id="860dc-296">Call Reliability/Failure by Region:</span></span>
  - <span data-ttu-id="860dc-297">按区域日期</span><span class="sxs-lookup"><span data-stu-id="860dc-297">date-by-region</span></span>
  - <span data-ttu-id="860dc-298">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="860dc-298">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="860dc-299">特定位置</span><span class="sxs-lookup"><span data-stu-id="860dc-299">specific locations</span></span>
  - <span data-ttu-id="860dc-300">特定子网</span><span class="sxs-lookup"><span data-stu-id="860dc-300">specific subnet</span></span>
  - <span data-ttu-id="860dc-301">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="860dc-301">impacted user or users</span></span>

- <span data-ttu-id="860dc-302">按区域对我的呼叫（RMC）进行评级：从按区域聚合到特定位置的特定位置到提供低 RMC 等级的用户。</span><span class="sxs-lookup"><span data-stu-id="860dc-302">Rate My Call (RMC) by Region: from month-by-region aggregated down to specific locations to users who provide low RMC ratings.</span></span> <span data-ttu-id="860dc-303">CQD v3 还包括逐字反馈。</span><span class="sxs-lookup"><span data-stu-id="860dc-303">CQD v3 also includes verbatim feedback.</span></span>
- <span data-ttu-id="860dc-304">帮助者：可用于 P2P 呼叫或会议的特定用户或所有参与者和通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-304">Helpdesk: available for a specific user on P2P calls or Meetings, or for all participants and call details.</span></span> <span data-ttu-id="860dc-305">帮助识别基于网络位置、设备或固件的可能系统问题。</span><span class="sxs-lookup"><span data-stu-id="860dc-305">Helps identify possible system issues based on network location, devices, or firmware.</span></span>  
- <span data-ttu-id="860dc-306">客户端版本：查看每个客户端版本的会话和用户计数，或向下钻取以查看每个客户端版本的用户名。</span><span class="sxs-lookup"><span data-stu-id="860dc-306">Client Versions: View the Session and Users counts for each Client Version, or drill down to User names for each client version.</span></span> <span data-ttu-id="860dc-307">产品和客户端类型的预生成筛选器帮助将版本集中到特定客户端。</span><span class="sxs-lookup"><span data-stu-id="860dc-307">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>
- <span data-ttu-id="860dc-308">终结点：显示映射到电脑/Mac 的 "生成/模型" 的计算机终结点。</span><span class="sxs-lookup"><span data-stu-id="860dc-308">Endpoints: Shows Machine Endpoints mapped to Make/Model of the PC/Mac.</span></span> <span data-ttu-id="860dc-309">按 "生成/模型" 显示聚合质量。</span><span class="sxs-lookup"><span data-stu-id="860dc-309">Shows aggregated quality by Make/Model.</span></span> <span data-ttu-id="860dc-310">映射数据的上载类似于生成数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-310">Mapping data is uploaded similar to Building data.</span></span>

### <a name="overall-call-quality-tab"></a><span data-ttu-id="860dc-311">"整体通话质量" 选项卡</span><span class="sxs-lookup"><span data-stu-id="860dc-311">Overall Call Quality tab</span></span>

<span data-ttu-id="860dc-312">使用此选项卡上的数据根据流计数和不良百分比评估通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="860dc-312">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="860dc-313">右上角的图例将显示哪些颜色和视觉元素表示这些指标。</span><span class="sxs-lookup"><span data-stu-id="860dc-313">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![屏幕截图：显示 "通话质量" 选项卡](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="860dc-315">流分为三个组： "完好"、"差" 和 "未分类"。</span><span class="sxs-lookup"><span data-stu-id="860dc-315">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="860dc-316">还计算出的*百分比*值太差，可让你将流的比率划分为*较差*的分类流计数。</span><span class="sxs-lookup"><span data-stu-id="860dc-316">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="860dc-317">由于*较差的% = 不良流/（差流 + 正常流） \* 100*，*差%* 不受多个未*分类*流的存在的影响。</span><span class="sxs-lookup"><span data-stu-id="860dc-317">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="860dc-318">若要查看将流分类为差或好的内容，请参阅["呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。</span><span class="sxs-lookup"><span data-stu-id="860dc-318">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="860dc-319">使用左侧的刻度测量流计数值。</span><span class="sxs-lookup"><span data-stu-id="860dc-319">Use the scale on the left to measure the stream count values.</span></span>
  
![屏幕截图：显示流计数值](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="860dc-321">使用右侧的刻度测量差的百分比值。</span><span class="sxs-lookup"><span data-stu-id="860dc-321">Use the scale on the right to measure the Poor % values.</span></span>
  
![屏幕截图：显示差的% 值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="860dc-323">也可以通过将鼠标悬停在条上来获取实际数值。</span><span class="sxs-lookup"><span data-stu-id="860dc-323">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="860dc-324">下面的示例来自非常小的示例数据集，并且值对于实际部署不切合实际。</span><span class="sxs-lookup"><span data-stu-id="860dc-324">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![屏幕截图：显示用于访问数据的鼠标](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="860dc-326">整个流卷可帮助确定计算出的较差百分比的相关程度。</span><span class="sxs-lookup"><span data-stu-id="860dc-326">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="860dc-327">总体流的数量越小，报告的百分比值越低越可靠。</span><span class="sxs-lookup"><span data-stu-id="860dc-327">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="860dc-328">服务器-客户端选项卡和客户端-客户端选项卡</span><span class="sxs-lookup"><span data-stu-id="860dc-328">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="860dc-329">这两个选项卡提供了在其终结点到终结点应用场景中发生的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-329">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="860dc-330">"服务器-客户端" 选项卡具有四个可折叠的部分，表示媒体流将流经的四个方案。</span><span class="sxs-lookup"><span data-stu-id="860dc-330">The Server-Client tab has four collapsible sections  that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="860dc-331">内部有线</span><span class="sxs-lookup"><span data-stu-id="860dc-331">Wired Inside</span></span>
- <span data-ttu-id="860dc-332">外部有线</span><span class="sxs-lookup"><span data-stu-id="860dc-332">Wired Outside</span></span>
- <span data-ttu-id="860dc-333">内部 Wifi</span><span class="sxs-lookup"><span data-stu-id="860dc-333">Wifi Inside</span></span>
- <span data-ttu-id="860dc-334">外部 Wifi</span><span class="sxs-lookup"><span data-stu-id="860dc-334">Wifi Outside</span></span>

<span data-ttu-id="860dc-335">同样，"客户端-客户端" 选项卡具有五个可折叠部分：</span><span class="sxs-lookup"><span data-stu-id="860dc-335">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="860dc-336">有线内部-有线内部</span><span class="sxs-lookup"><span data-stu-id="860dc-336">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="860dc-337">有线内部-有线外部</span><span class="sxs-lookup"><span data-stu-id="860dc-337">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="860dc-338">有线外部-有线外部</span><span class="sxs-lookup"><span data-stu-id="860dc-338">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="860dc-339">内部有线-内部 Wifi</span><span class="sxs-lookup"><span data-stu-id="860dc-339">Wired Inside — Wifi Inside</span></span>
- <span data-ttu-id="860dc-340">内部有线-外部 Wifi</span><span class="sxs-lookup"><span data-stu-id="860dc-340">Wired Inside — Wifi Outside</span></span>

#### <a name="inside-test"></a><span data-ttu-id="860dc-341">内部测试</span><span class="sxs-lookup"><span data-stu-id="860dc-341">Inside Test</span></span>

<span data-ttu-id="860dc-342">在处理期间，CQD 后端使用建筑物信息将流分类为*内部*或*外部*流（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="860dc-342">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="860dc-343">每个流的终结点与子网地址相关联。</span><span class="sxs-lookup"><span data-stu-id="860dc-343">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="860dc-344">如果子网位于上载的生成信息中标记为 "InsideCorp" 的子网列表中，则将其视为*内部*。</span><span class="sxs-lookup"><span data-stu-id="860dc-344">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="860dc-345">如果尚未上载生成信息，则内部测试始终会将流分类为*外部*流。</span><span class="sxs-lookup"><span data-stu-id="860dc-345">If Building information has not yet been uploaded, then Inside Test  always classifies the streams as *Outside*.</span></span>  

> [!NOTE]
> <span data-ttu-id="860dc-346">服务器客户端方案的内部测试仅考虑客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="860dc-346">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="860dc-347">由于服务器始终来自用户的视角，因此不会在测试中考虑。</span><span class="sxs-lookup"><span data-stu-id="860dc-347">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="860dc-348">有线与 wifi</span><span class="sxs-lookup"><span data-stu-id="860dc-348">Wired vs. wifi</span></span>

<span data-ttu-id="860dc-349">根据名称指示，分类标准基于客户端连接的类型。</span><span class="sxs-lookup"><span data-stu-id="860dc-349">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="860dc-350">同样，服务器始终是有线的，并且不会包含在计算中。</span><span class="sxs-lookup"><span data-stu-id="860dc-350">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="860dc-351">如果有一个流，则如果两个终结点中的一个终结点连接到 Wifi 网络，则会在 CQD 中将其分类为 Wifi。</span><span class="sxs-lookup"><span data-stu-id="860dc-351">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span>
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="860dc-352">选择要在报表中查看的产品数据</span><span class="sxs-lookup"><span data-stu-id="860dc-352">Selecting product data to see in reports</span></span>

<a name="BKMKProductFilter"></a>

<span data-ttu-id="860dc-353">在摘要和位置增强的报表中，你可以使用 "**产品筛选器**" 下拉列表显示所有产品数据、仅 Microsoft 团队数据或仅 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-353">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![屏幕截图：显示产品筛选器控件选项](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="860dc-355">在 "详细报表" 中，可以使用 "**属于团队**" 维度将数据筛选到 Microsoft 团队或 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-355">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="860dc-356">上载租户数据信息</span><span class="sxs-lookup"><span data-stu-id="860dc-356">Upload Tenant Data information</span></span>

<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="860dc-357">CQD 摘要报告仪表板包括**租户数据上载**页面，该页面从右上角的 "设置" 菜单中选择 "**租户数据上载**"。</span><span class="sxs-lookup"><span data-stu-id="860dc-357">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="860dc-358">此页面用于管理员上载其自己的信息，例如：</span><span class="sxs-lookup"><span data-stu-id="860dc-358">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="860dc-359">IP 地址和地理信息的地图</span><span class="sxs-lookup"><span data-stu-id="860dc-359">A map of IP address and geographical information</span></span>
- <span data-ttu-id="860dc-360">每个无线 AP 及其 MAC 地址的地图</span><span class="sxs-lookup"><span data-stu-id="860dc-360">A map of each wireless AP and its MAC address</span></span>
- <span data-ttu-id="860dc-361">终结点到终结点的映射/模型/类型等。</span><span class="sxs-lookup"><span data-stu-id="860dc-361">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
> [!NOTE]
> <span data-ttu-id="860dc-362">你上载到 CQD 的报告标签将按你的 Office 365 协议下的*支持数据*进行处理，包括任何其他被视为*客户数据*或*个人资料*的信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-362">Reporting Labels that you upload to CQD will be handled as *Support Data* under your agreement for Office 365, including any information that would otherwise be considered *Customer Data* or *Personal Data*.</span></span> <span data-ttu-id="860dc-363">请不要包含不希望作为*支持数据*提供给 microsoft 的数据，此信息将对 microsoft 工程师可见，以便于支持之用。</span><span class="sxs-lookup"><span data-stu-id="860dc-363">Please do not include data you do not wish to provide to Microsoft as *Support Data*, this information will be visible to Microsoft Engineers for support purposes.</span></span>

![屏幕截图：显示呼叫质量仪表板租户数据](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="860dc-365">在 "**租户数据上载**" 页面上，使用下拉菜单选择要上传的数据文件类型。</span><span class="sxs-lookup"><span data-stu-id="860dc-365">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type to upload.</span></span> <span data-ttu-id="860dc-366">"文件" 数据类型表示文件的内容（例如，"建筑物" 指的是 IP 地址和建筑物和其他地理信息的映射，"终结点" 指终结点名称和模型/类型信息的映射。</span><span class="sxs-lookup"><span data-stu-id="860dc-366">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building and other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type information).</span></span> <span data-ttu-id="860dc-367">当前 CQD 支持 cqd.teams.microsoft.com 的 "建筑物" 和 "终结点" 数据类型（在预览阶段和尚未正式提供），cqd.lync.com 仅支持 "建筑物" 数据类型。</span><span class="sxs-lookup"><span data-stu-id="860dc-367">Currently CQD supports “Building” and “Endpoint” data types for cqd.teams.microsoft.com (in preview stage and not officially available yet), cqd.lync.com only supports the "Building" data type.</span></span>



2. <span data-ttu-id="860dc-368">选择文件数据类型后，单击 "**浏览**" 以选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="860dc-368">After you select the file data type, click **Browse** to choose a data file.</span></span>

   - <span data-ttu-id="860dc-369">数据文件必须为 tsv （以制表符分隔的值）文件或 .csv （以逗号分隔的值）文件。</span><span class="sxs-lookup"><span data-stu-id="860dc-369">A data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="860dc-370">使用 .csv 文件时，包含逗号的任何字段都必须用引号引起来，或者删除逗号。</span><span class="sxs-lookup"><span data-stu-id="860dc-370">With a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="860dc-371">例如，如果建筑物名称为 NY，则在 .csv 文件中输入 "纽约州，NY"。</span><span class="sxs-lookup"><span data-stu-id="860dc-371">For example, if your building name is NY,NY,  enter  "NY,NY" in the .csv file.</span></span>
   - <span data-ttu-id="860dc-372">数据文件不能大于 50 MB。</span><span class="sxs-lookup"><span data-stu-id="860dc-372">The data file must be no larger than 50 MB.</span></span>
   - <span data-ttu-id="860dc-373">上载到 cqd.teams.microsoft.com 的文件具有展开的行限制1000000以使查询性能更快。</span><span class="sxs-lookup"><span data-stu-id="860dc-373">Files uploaded to cqd.teams.microsoft.com have an expanded row limit of 1,000,000 to keep query performance fast.</span></span> <span data-ttu-id="860dc-374">此限制也适用于 CQD<span></span><span></span>上的 CQD v2。</span><span class="sxs-lookup"><span data-stu-id="860dc-374">This limit also applies to CQD v2  on cqd<span></span>.lync<span></span>.com.</span></span>
   - <span data-ttu-id="860dc-375">对于每个数据文件，文件中的每一列都必须与本主题后面部分所述的预定义数据类型匹配。</span><span class="sxs-lookup"><span data-stu-id="860dc-375">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
3. <span data-ttu-id="860dc-376">接下来，指定**开始日期**，并根据需要**指定结束日期**。</span><span class="sxs-lookup"><span data-stu-id="860dc-376">Next, specify a **Start date** and, optionally, **Specify an end date**.</span></span>
4. <span data-ttu-id="860dc-377">最后，选择 "**上传**" 将文件上载到 CQD 服务器。</span><span class="sxs-lookup"><span data-stu-id="860dc-377">Finally, select **Upload** to upload the file to the CQD server.</span></span>
    <span data-ttu-id="860dc-378">上载文件之前，首先验证该文件。</span><span class="sxs-lookup"><span data-stu-id="860dc-378">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="860dc-379">验证后，它将存储在 Azure blob 中。</span><span class="sxs-lookup"><span data-stu-id="860dc-379">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="860dc-380">如果验证失败或文件无法存储在 Azure blob 中，则会显示一条错误消息请求对文件的更正。</span><span class="sxs-lookup"><span data-stu-id="860dc-380">If validation fails or the file fails to be stored in an Azure blob, an error message requests a correction to the file.</span></span> <span data-ttu-id="860dc-381">下图显示了数据文件中的列数不正确的示例错误。</span><span class="sxs-lookup"><span data-stu-id="860dc-381">The following image shows a sample error with an incorrect number of columns in the data file.</span></span>

     ![屏幕截图：显示上载验证错误](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="860dc-383">如果验证期间未出现任何错误，则文件上载成功。</span><span class="sxs-lookup"><span data-stu-id="860dc-383">If no errors occur during validation, the file upload succeeds.</span></span> <span data-ttu-id="860dc-384">然后，您可以在 "我的上**传**" 表中看到上载的数据文件。</span><span class="sxs-lookup"><span data-stu-id="860dc-384">You can then see the uploaded data file in the **My uploads** table.</span></span> <span data-ttu-id="860dc-385">该页面底部还显示为当前租户上载的所有文件的完整列表。</span><span class="sxs-lookup"><span data-stu-id="860dc-385">The bottom of that page also shows a full list of all files uploaded for the current tenant.</span></span>
    <span data-ttu-id="860dc-386">每个记录显示一个上载的租户数据文件，其中包含文件类型、上次更新时间、时间段、说明、删除图标和下载图标。</span><span class="sxs-lookup"><span data-stu-id="860dc-386">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="860dc-387">若要删除文件，请选择表格中的垃圾桶图标。</span><span class="sxs-lookup"><span data-stu-id="860dc-387">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="860dc-388">若要下载文件，请选择表格的 "**下载**" 列中的 "下载" 图标。</span><span class="sxs-lookup"><span data-stu-id="860dc-388">To download a file, select the download icon in the **Download** column of the table.</span></span>

     ![屏幕截图：显示 "我的上传" 表](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. <span data-ttu-id="860dc-390">如果你选择使用多个生成数据文件或多个终结点数据文件，则某些报表的生成速度较慢。</span><span class="sxs-lookup"><span data-stu-id="860dc-390">If you choose to use multiple building data files or multiple endpoint data files, some reports generate more slowly.</span></span>

### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="860dc-391">租户数据文件格式和结构</span><span class="sxs-lookup"><span data-stu-id="860dc-391">Tenant data file format and structure</span></span>

<span data-ttu-id="860dc-392"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="860dc-392"><a name="BKMKTenantDataFile"> </a></span></span>

### <a name="building-data-file"></a><span data-ttu-id="860dc-393">生成数据文件</span><span class="sxs-lookup"><span data-stu-id="860dc-393">Building data file</span></span>

<span data-ttu-id="860dc-394">CQD 使用构建数据文件，这有助于提供有用的通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-394">CQD uses a Building data file, which helps provide useful call details.</span></span> <span data-ttu-id="860dc-395">通过展开 "网络 + NetworkRange" 列，然后将 "子网" 列联接到呼叫记录的第一个子网或 "第二个子网" 列中，显示建筑物、城市、国家或地区信息，从而派生出子网列。</span><span class="sxs-lookup"><span data-stu-id="860dc-395">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="860dc-396">你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="860dc-396">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

<span data-ttu-id="860dc-397">可以[在此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下载示例模板</span><span class="sxs-lookup"><span data-stu-id="860dc-397">You can download a sample template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)</span></span>
  
- <span data-ttu-id="860dc-398">文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="860dc-398">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>
- <span data-ttu-id="860dc-399">数据文件不包含表格标题行。</span><span class="sxs-lookup"><span data-stu-id="860dc-399">The data file doesn't include a table header row.</span></span> <span data-ttu-id="860dc-400">数据文件的第一行应为真实数据，而不是标题标签（如 "Network"）。</span><span class="sxs-lookup"><span data-stu-id="860dc-400">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>
- <span data-ttu-id="860dc-401">文件中的数据类型只能是 String、Integer 或 Boolean。</span><span class="sxs-lookup"><span data-stu-id="860dc-401">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="860dc-402">对于整数数据类型，值必须是一个数值。</span><span class="sxs-lookup"><span data-stu-id="860dc-402">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="860dc-403">布尔值必须是0或1。</span><span class="sxs-lookup"><span data-stu-id="860dc-403">Boolean values must be either 0 or 1.</span></span>
- <span data-ttu-id="860dc-404">如果列使用字符串数据类型，则数据字段可以为空，但仍须由制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="860dc-404">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="860dc-405">空数据字段只是分配一个空字符串值。</span><span class="sxs-lookup"><span data-stu-id="860dc-405">An empty data field just assigns an empty String value.</span></span>
- <span data-ttu-id="860dc-406">每一行必须有14列（如果要添加可选列，则为15），每列必须具有相应的数据类型，并且列必须采用下表中列出的顺序：</span><span class="sxs-lookup"><span data-stu-id="860dc-406">There must be 14 columns for each row (or 15 if you want to add the optional column), each column must have the appropriate data type, and the columns must be in the order listed in the following table:</span></span>

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|<span data-ttu-id="860dc-407">**列字段名称**</span><span class="sxs-lookup"><span data-stu-id="860dc-407">**Column field name**</span></span>|<span data-ttu-id="860dc-408">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="860dc-408">NetworkIP</span></span>  |<span data-ttu-id="860dc-409">NetworkName</span><span class="sxs-lookup"><span data-stu-id="860dc-409">NetworkName</span></span>              |<span data-ttu-id="860dc-410">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="860dc-410">NetworkRange</span></span>|<span data-ttu-id="860dc-411">BuildingName</span><span class="sxs-lookup"><span data-stu-id="860dc-411">BuildingName</span></span>  |<span data-ttu-id="860dc-412">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="860dc-412">OwnershipType</span></span>| <span data-ttu-id="860dc-413">BuildingType</span><span class="sxs-lookup"><span data-stu-id="860dc-413">BuildingType</span></span>  |<span data-ttu-id="860dc-414">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="860dc-414">BuildingOfficeType</span></span>|<span data-ttu-id="860dc-415">城市</span><span class="sxs-lookup"><span data-stu-id="860dc-415">City</span></span>   |<span data-ttu-id="860dc-416">ZipCode</span><span class="sxs-lookup"><span data-stu-id="860dc-416">ZipCode</span></span>|<span data-ttu-id="860dc-417">该国</span><span class="sxs-lookup"><span data-stu-id="860dc-417">Country</span></span>|<span data-ttu-id="860dc-418">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="860dc-418">State</span></span> |<span data-ttu-id="860dc-419">区域</span><span class="sxs-lookup"><span data-stu-id="860dc-419">Region</span></span>|<span data-ttu-id="860dc-420">InsideCorp&dagger;</span><span class="sxs-lookup"><span data-stu-id="860dc-420">InsideCorp&dagger;</span></span>|<span data-ttu-id="860dc-421">ExpressRoute&Dagger;</span><span class="sxs-lookup"><span data-stu-id="860dc-421">ExpressRoute&Dagger;</span></span>|<span data-ttu-id="860dc-422">VPN （可选）</span><span class="sxs-lookup"><span data-stu-id="860dc-422">VPN (optional)</span></span>|
|<span data-ttu-id="860dc-423">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="860dc-423">**Data type**</span></span>        | <span data-ttu-id="860dc-424">String</span><span class="sxs-lookup"><span data-stu-id="860dc-424">String</span></span>    | <span data-ttu-id="860dc-425">String</span><span class="sxs-lookup"><span data-stu-id="860dc-425">String</span></span>                  |<span data-ttu-id="860dc-426">数字</span><span class="sxs-lookup"><span data-stu-id="860dc-426">Number</span></span>      | <span data-ttu-id="860dc-427">String</span><span class="sxs-lookup"><span data-stu-id="860dc-427">String</span></span>       | <span data-ttu-id="860dc-428">String</span><span class="sxs-lookup"><span data-stu-id="860dc-428">String</span></span>      | <span data-ttu-id="860dc-429">String</span><span class="sxs-lookup"><span data-stu-id="860dc-429">String</span></span>        |<span data-ttu-id="860dc-430">String</span><span class="sxs-lookup"><span data-stu-id="860dc-430">String</span></span>            |<span data-ttu-id="860dc-431">String</span><span class="sxs-lookup"><span data-stu-id="860dc-431">String</span></span> |<span data-ttu-id="860dc-432">String</span><span class="sxs-lookup"><span data-stu-id="860dc-432">String</span></span> |<span data-ttu-id="860dc-433">String</span><span class="sxs-lookup"><span data-stu-id="860dc-433">String</span></span> |<span data-ttu-id="860dc-434">String</span><span class="sxs-lookup"><span data-stu-id="860dc-434">String</span></span>|<span data-ttu-id="860dc-435">String</span><span class="sxs-lookup"><span data-stu-id="860dc-435">String</span></span>|<span data-ttu-id="860dc-436">Boolean</span><span class="sxs-lookup"><span data-stu-id="860dc-436">Boolean</span></span>   |<span data-ttu-id="860dc-437">Boolean</span><span class="sxs-lookup"><span data-stu-id="860dc-437">Boolean</span></span>     |<span data-ttu-id="860dc-438">Boolean</span><span class="sxs-lookup"><span data-stu-id="860dc-438">Boolean</span></span>|
|<span data-ttu-id="860dc-439">**示例值**</span><span class="sxs-lookup"><span data-stu-id="860dc-439">**Example value**</span></span>    |<span data-ttu-id="860dc-440">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="860dc-440">192.168.1.0</span></span>|<span data-ttu-id="860dc-441">美国/西雅图/西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="860dc-441">USA/Seattle/SEATTLE-SEA-1</span></span>| <span data-ttu-id="860dc-442">个</span><span class="sxs-lookup"><span data-stu-id="860dc-442">26</span></span>         | <span data-ttu-id="860dc-443">西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="860dc-443">SEATTLE-SEA-1</span></span>| <span data-ttu-id="860dc-444">制定</span><span class="sxs-lookup"><span data-stu-id="860dc-444">Contoso</span></span>     | <span data-ttu-id="860dc-445">终止</span><span class="sxs-lookup"><span data-stu-id="860dc-445">IT Termination</span></span>|<span data-ttu-id="860dc-446">技术</span><span class="sxs-lookup"><span data-stu-id="860dc-446">Engineering</span></span>       |<span data-ttu-id="860dc-447">西雅图</span><span class="sxs-lookup"><span data-stu-id="860dc-447">Seattle</span></span>|<span data-ttu-id="860dc-448">98001</span><span class="sxs-lookup"><span data-stu-id="860dc-448">98001</span></span>  |<span data-ttu-id="860dc-449">我们</span><span class="sxs-lookup"><span data-stu-id="860dc-449">US</span></span>     |<span data-ttu-id="860dc-450">WA</span><span class="sxs-lookup"><span data-stu-id="860dc-450">WA</span></span>    |<span data-ttu-id="860dc-451">MSUS</span><span class="sxs-lookup"><span data-stu-id="860dc-451">MSUS</span></span>  | <span data-ttu-id="860dc-452">1</span><span class="sxs-lookup"><span data-stu-id="860dc-452">1</span></span>        |<span data-ttu-id="860dc-453">0</span><span class="sxs-lookup"><span data-stu-id="860dc-453">0</span></span>           | <span data-ttu-id="860dc-454">0</span><span class="sxs-lookup"><span data-stu-id="860dc-454">0</span></span>|
|||||||||||||||||

<span data-ttu-id="860dc-455">&dagger;此设置可用于反映子网是否位于企业网络内。</span><span class="sxs-lookup"><span data-stu-id="860dc-455">&dagger; This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="860dc-456">如果你决定，可以自定义其他用途的用法。</span><span class="sxs-lookup"><span data-stu-id="860dc-456">You can customize usage for other purposes if you decide to.</span></span>

<span data-ttu-id="860dc-457">&Dagger;此设置可用于反映网络是否使用 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="860dc-457">&Dagger; This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="860dc-458">如果你决定，可以自定义其他用途的用法。</span><span class="sxs-lookup"><span data-stu-id="860dc-458">You can customize usage for other purposes if you decide to.</span></span>  

<span data-ttu-id="860dc-459">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="860dc-459">**Sample row:**</span></span>

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="860dc-460">网络范围可用于表示 supernet （具有单个路由前缀的若干子网的组合）。</span><span class="sxs-lookup"><span data-stu-id="860dc-460">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="860dc-461">将检查所有新的生成上载，查找任何重叠区域。</span><span class="sxs-lookup"><span data-stu-id="860dc-461">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="860dc-462">如果你以前上载了一个生成文件，则应下载当前文件，然后重新上载它以标识任何重叠，并在再次上载之前修复该问题。</span><span class="sxs-lookup"><span data-stu-id="860dc-462">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="860dc-463">以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。</span><span class="sxs-lookup"><span data-stu-id="860dc-463">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="860dc-464">某些 VPN 实现不能准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-464">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="860dc-465">建议将 VPN 子网添加到生成文件，而不是子网的一个条目时，将 VPN 子网中每个地址的单独条目添加为单独的32位网络。</span><span class="sxs-lookup"><span data-stu-id="860dc-465">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="860dc-466">每一行可以有相同的建筑物元数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-466">Each row can have the same building metadata.</span></span> <span data-ttu-id="860dc-467">例如，对于 172.16.18.0/24，而不是一行，您应该有256行，每个地址对应于 172.16.18.0/32 和 172.16.18.255/32 之间（包括这两个地址）的一行。</span><span class="sxs-lookup"><span data-stu-id="860dc-467">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="860dc-468">"VPN" 列是可选的，默认值为0。</span><span class="sxs-lookup"><span data-stu-id="860dc-468">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="860dc-469">如果 VPN 列的值设置为1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="860dc-469">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="860dc-470">请谨慎使用，并且仅针对 VPN 子网，因为完全展开这些子网将对涉及生成数据的查询的查询时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="860dc-470">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

### <a name="endpoint-data-file"></a><span data-ttu-id="860dc-471">终结点数据文件</span><span class="sxs-lookup"><span data-stu-id="860dc-471">Endpoint data file</span></span>

<span data-ttu-id="860dc-472">CQD 使用终结点数据文件。</span><span class="sxs-lookup"><span data-stu-id="860dc-472">CQD uses an Endpoint data file.</span></span> <span data-ttu-id="860dc-473">在调用记录的第一个客户端终结点名称列或第二个客户端终结点名称列中使用列值来显示终结点的 "创建"、"模型" 或 "类型" 信息。</span><span class="sxs-lookup"><span data-stu-id="860dc-473">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="860dc-474">你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="860dc-474">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="860dc-475">文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="860dc-475">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>
- <span data-ttu-id="860dc-476">数据文件的内容不包含表格标题。</span><span class="sxs-lookup"><span data-stu-id="860dc-476">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="860dc-477">数据文件的第一行应为真实数据，而不是标题标签（如 "终结点"）。</span><span class="sxs-lookup"><span data-stu-id="860dc-477">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>
- <span data-ttu-id="860dc-478">所有七列仅使用字符串数据类型。</span><span class="sxs-lookup"><span data-stu-id="860dc-478">All seven columns use the String data type only.</span></span> <span data-ttu-id="860dc-479">允许的最大长度为64个字符。</span><span class="sxs-lookup"><span data-stu-id="860dc-479">The maximum allowed length is 64 characters.</span></span>
- <span data-ttu-id="860dc-480">数据字段可以为空，但仍须由制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="860dc-480">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="860dc-481">空数据字段只是分配一个空字符串值。</span><span class="sxs-lookup"><span data-stu-id="860dc-481">An empty data field just assigns an empty String value.</span></span>
- <span data-ttu-id="860dc-482">终结点必须是唯一的，否则上传将失败。</span><span class="sxs-lookup"><span data-stu-id="860dc-482">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="860dc-483">如果存在重复的行或两行使用同一终结点，则冲突将导致不正确的联接。</span><span class="sxs-lookup"><span data-stu-id="860dc-483">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>
- <span data-ttu-id="860dc-484">EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。</span><span class="sxs-lookup"><span data-stu-id="860dc-484">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="860dc-485">它们可以是空字符串或值，如 "IT 部门指定的2018膝上型计算机" 或 "资产标签 5678"。</span><span class="sxs-lookup"><span data-stu-id="860dc-485">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>
- <span data-ttu-id="860dc-486">每行必须有七列，并且列必须按以下顺序排列：</span><span class="sxs-lookup"><span data-stu-id="860dc-486">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="860dc-487">**字段顺序：**</span><span class="sxs-lookup"><span data-stu-id="860dc-487">**Field order:**</span></span>

<span data-ttu-id="860dc-488">终结点、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="860dc-488">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="860dc-489">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="860dc-489">**Sample row:**</span></span>

<span data-ttu-id="860dc-490">"1409W3534，123制造商，Fabrikam 型号123，笔记本电脑，已指定2018笔记本电脑、资产标签5678、购买2018</span><span class="sxs-lookup"><span data-stu-id="860dc-490">\`1409W3534, 123 manufacturer, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018</span></span>

## <a name="migrate-reports-from-previous-version-of-cqd"></a><span data-ttu-id="860dc-491">从早期版本的 CQD 迁移报表</span><span class="sxs-lookup"><span data-stu-id="860dc-491">Migrate reports from previous version of CQD</span></span>

<span data-ttu-id="860dc-492">如果你为 Skype for Business 将报表或已上载的租户数据（映射）文件创建https://cqd.lync.com)到 CQD （并希望将它们迁移到团队https://cqd.teams.microsoft.com)的 CQD （），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="860dc-492">If  you created reports or uploaded tenant data (mapping) files to CQD for Skype for Business (https://cqd.lync.com) and want to migrate them to CQD for Teams (https://cqd.teams.microsoft.com), here’s how:</span></span>

1.  <span data-ttu-id="860dc-493">转到[https://cqd.lync.com/cqd/](https://cqd.lync.com/cqd/)并浏览到要导出的报表集。</span><span class="sxs-lookup"><span data-stu-id="860dc-493">Go to [https://cqd.lync.com/cqd/](https://cqd.lync.com/cqd/) and browse to the report set you want to export.</span></span> 
2.  <span data-ttu-id="860dc-494">将鼠标悬停在报表上，然后在 "..."菜单上，选择 "**导出报表树**"。</span><span class="sxs-lookup"><span data-stu-id="860dc-494">Hover over the report and, on the "..." menu, choose **Export Report Tree**.</span></span> <span data-ttu-id="860dc-495">保存导出文件。</span><span class="sxs-lookup"><span data-stu-id="860dc-495">Save the export file.</span></span>
3.  <span data-ttu-id="860dc-496">转到[https://cqd.teams.microsoft.com/cqd/](https://cqd.teams.microsoft.com/cqd/)并浏览到要导入报表的位置。</span><span class="sxs-lookup"><span data-stu-id="860dc-496">Go to [https://cqd.teams.microsoft.com/cqd/](https://cqd.teams.microsoft.com/cqd/)  and browse to the location where you want to import the reports.</span></span>
4.  <span data-ttu-id="860dc-497">从左侧的链接中，单击 "**导入**"，然后选择导出的文件。</span><span class="sxs-lookup"><span data-stu-id="860dc-497">From the links on the left, click **Import** and select the exported file.</span></span> 
5.  <span data-ttu-id="860dc-498">导入报告后，您将看到以下消息： "报告导入成功。</span><span class="sxs-lookup"><span data-stu-id="860dc-498">After the reports are imported, you'll see this message: "Report import was successful.</span></span> <span data-ttu-id="860dc-499">新报表已添加到报表集末尾。 "</span><span class="sxs-lookup"><span data-stu-id="860dc-499">The new report has been added at the end of report set."</span></span> 


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="860dc-500">创建自定义详细报告</span><span class="sxs-lookup"><span data-stu-id="860dc-500">Create custom detailed reports</span></span>

<span data-ttu-id="860dc-501">如果您想要创建一个特定报表，使其关注所提供的详细报表所提供的数据的维度，请创建一个自定义报表。</span><span class="sxs-lookup"><span data-stu-id="860dc-501">If you find you want to create a specific report that focuses on a dimension of the data in a way the provided detailed reports do not, create a custom report.</span></span>

<span data-ttu-id="860dc-502">在 "登录\(**摘要报告**"\)屏幕上显示的屏幕顶部显示的报告下拉列表中，选择 "**详细报告**"，然后**单击**报表的 "操作" 菜单中的 "编辑"，以查看查询编辑器。</span><span class="sxs-lookup"><span data-stu-id="860dc-502">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New** d Click "Edit" in the action menu of a report to see the Query Editor.</span></span> <span data-ttu-id="860dc-503">每个报告都可以通过对多维数据集进行查询得到。</span><span class="sxs-lookup"><span data-stu-id="860dc-503">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="860dc-504">报告是其查询返回的数据的可视化形式。</span><span class="sxs-lookup"><span data-stu-id="860dc-504">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="860dc-505">查询编辑器可帮助您编辑报表的这些查询和显示选项。</span><span class="sxs-lookup"><span data-stu-id="860dc-505">The Query Editor helps you edit these queries and the display options of the report.</span></span> <span data-ttu-id="860dc-506">为新报表打开 "查询编辑器" 时，你会看到类似于以下屏幕截图的内容：</span><span class="sxs-lookup"><span data-stu-id="860dc-506">When you open the Query Editor for a new report, you see something similar to this screenshot:</span></span>

![编辑新报表](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. <span data-ttu-id="860dc-508">左侧窗格中选择了维度、度量和筛选器。</span><span class="sxs-lookup"><span data-stu-id="860dc-508">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="860dc-509">单击标题旁边的 "加号" 按钮以打开对话框，您可以在其中添加维度、测量或筛选，并选中相应的框。</span><span class="sxs-lookup"><span data-stu-id="860dc-509">Click the "plus" button next to a heading to open the dialog where you can add a  dimension, measure, or filter and check the corresponding box.</span></span> <span data-ttu-id="860dc-510">如果您编辑现有报表，则可以取消选中现有值以将其删除。</span><span class="sxs-lookup"><span data-stu-id="860dc-510">If you edit an existing report, you can uncheck existing values to remove them.</span></span> <span data-ttu-id="860dc-511">有关详细信息，请参阅[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="860dc-511">For details, see [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
2. <span data-ttu-id="860dc-512">顶部显示了图表自定义选项。</span><span class="sxs-lookup"><span data-stu-id="860dc-512">Options for chart customization are displayed at the top.</span></span>
3. <span data-ttu-id="860dc-513">报表的预览在查询编辑器中可用。</span><span class="sxs-lookup"><span data-stu-id="860dc-513">A preview of the report is available in the Query Editor.</span></span>
4. <span data-ttu-id="860dc-514">可以使用底部的 "编辑" 框创建详细的报表名称和说明。</span><span class="sxs-lookup"><span data-stu-id="860dc-514">A detailed report name and description can be created with the edit box at the bottom.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="860dc-515">常见问题</span><span class="sxs-lookup"><span data-stu-id="860dc-515">Frequently Asked Questions</span></span>

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="860dc-516">如果一个或多个会议参与者的体验不好，CQD 为什么将呼叫标记为 "正常"？</span><span class="sxs-lookup"><span data-stu-id="860dc-516">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="860dc-517">查看[流分类](stream-classification-in-call-quality-dashboard.md)CQD 使用的规则。</span><span class="sxs-lookup"><span data-stu-id="860dc-517">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="860dc-518">对于音频流，任何5个分类器（根据调用的平均长度计算）都可能位于 "良好" 参数中。</span><span class="sxs-lookup"><span data-stu-id="860dc-518">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="860dc-519">这并不意味着用户不会遇到对音频的丢弃、静态或故障的内容。</span><span class="sxs-lookup"><span data-stu-id="860dc-519">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="860dc-520">若要确定是否是网络问题，请查看会话平均值与最大值之间的增量。</span><span class="sxs-lookup"><span data-stu-id="860dc-520">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="860dc-521">最大值是会话期间检测和报告的最大值。</span><span class="sxs-lookup"><span data-stu-id="860dc-521">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="860dc-522">下面是如何解决这种情况的示例。</span><span class="sxs-lookup"><span data-stu-id="860dc-522">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="860dc-523">假设你在呼叫过程中获取网络跟踪，并且前20分钟，没有丢失数据包，但你的数据包的间隔为1.5 秒，然后就可以在通话的其余部分中使用。</span><span class="sxs-lookup"><span data-stu-id="860dc-523">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="860dc-524">平均 <10% （0.1）数据包丢失，即使在 Wireshark 跟踪 RTP 分析中也是如此。</span><span class="sxs-lookup"><span data-stu-id="860dc-524">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="860dc-525">最大数据包丢失程度是多少？</span><span class="sxs-lookup"><span data-stu-id="860dc-525">What was the Max Packet Loss?</span></span> <span data-ttu-id="860dc-526">5秒内的1.5 秒将是30% （0.3）。</span><span class="sxs-lookup"><span data-stu-id="860dc-526">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="860dc-527">在五秒的采样周期内发生（也许还是可以在采样周期内拆分）？</span><span class="sxs-lookup"><span data-stu-id="860dc-527">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="860dc-528">如果网络指标在平均值和最大值中看起来很好，请查看其他遥测数据：</span><span class="sxs-lookup"><span data-stu-id="860dc-528">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="860dc-529">检查 CPU 的事件比率不足，查看检测到的 CPU 资源是否不足，导致质量较差。</span><span class="sxs-lookup"><span data-stu-id="860dc-529">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="860dc-530">音频设备是否处于半双工模式下，以防止因麦克风接近扬声器而导致的反馈？</span><span class="sxs-lookup"><span data-stu-id="860dc-530">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="860dc-531">检查 Device 半双工 AEC 事件比率。</span><span class="sxs-lookup"><span data-stu-id="860dc-531">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="860dc-532">当插入集线器或坞站时，设备 glitching 或麦克风 glitching 引入噪音或静态信号的原因如下：</span><span class="sxs-lookup"><span data-stu-id="860dc-532">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="860dc-533">检查设备故障和麦克风故障事件比率。</span><span class="sxs-lookup"><span data-stu-id="860dc-533">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="860dc-534">设备本身是否正常工作？</span><span class="sxs-lookup"><span data-stu-id="860dc-534">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="860dc-535">检查捕获和呈现设备无法正常工作的事件比率。</span><span class="sxs-lookup"><span data-stu-id="860dc-535">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="860dc-536">有关 CQD 遥测中可用的维度和度量值的详细信息，请参阅[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="860dc-536">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="860dc-537">对于背景噪音，请选中 "静音事件比率" 以查看参与者静音的时间长度。</span><span class="sxs-lookup"><span data-stu-id="860dc-537">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="860dc-538">在 CQD 中创建详细报表，并筛选会议 ID 以查看会议中的所有用户和流并添加感兴趣的字段。</span><span class="sxs-lookup"><span data-stu-id="860dc-538">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="860dc-539">报告问题的用户可能不是遇到该问题的用户。</span><span class="sxs-lookup"><span data-stu-id="860dc-539">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="860dc-540">他们只是报告体验。</span><span class="sxs-lookup"><span data-stu-id="860dc-540">They are just reporting the experience.</span></span>
 
<span data-ttu-id="860dc-541">遥测不一定会解决该问题，但它可以帮助您更好地了解在何处查看和通知您的决策。</span><span class="sxs-lookup"><span data-stu-id="860dc-541">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="860dc-542">是网络、设备、驱动程序还是固件更新、使用或用户？</span><span class="sxs-lookup"><span data-stu-id="860dc-542">Is it network, device, driver or firmware updates, usage, or user?</span></span>


### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a><span data-ttu-id="860dc-543">为什么 CQD v2 报表数据看起来与 CQD v3 报表数据不同？</span><span class="sxs-lookup"><span data-stu-id="860dc-543">Why does my CQD v2 report data look different than the CQD v3 report data?</span></span> 

<span data-ttu-id="860dc-544">如果你看到 CQD v2 和 v3 之间的数据差异，请确保在 "苹果" 和 "窄" 级别（而不是聚合级别）上执行数据比较或验证。</span><span class="sxs-lookup"><span data-stu-id="860dc-544">If you see data differences between CQD v2 and v3, make sure that data comparison or validation is done on an 'apples-to-apples'  and narrow level, not an aggregated level.</span></span> <span data-ttu-id="860dc-545">例如，如果你筛选 MSIT "建筑物 30" WiFi 团队桌面客户端数据的两个报表，则 v2 和 v3 的低质量百分比应该相同。</span><span class="sxs-lookup"><span data-stu-id="860dc-545">For example, if you filter both reports for MSIT ‘Building 30' WiFi Teams Desktop client data, the Percentage of Poor Quality should be the same between v2 and v3.</span></span>

<span data-ttu-id="860dc-546">CQD v2 和 CQD v3 具有不同的总数，因为 CQD v3 具有 CQD v2 中不存在的新方案。</span><span class="sxs-lookup"><span data-stu-id="860dc-546">CQD v2 and CQD v3 have different total counts since CQD v3 has new scenarios not present in CQD v2.</span></span> <span data-ttu-id="860dc-547">摘要总数或聚合的所有不带筛选器的数字均应不同。</span><span class="sxs-lookup"><span data-stu-id="860dc-547">Summary Total or Aggregated all-up numbers with no filters are expected to be different.</span></span>  

<span data-ttu-id="860dc-548">如果使用方案包括 Skype for Business Server 2019 调用，CQD v3 数据包括 Skype 机器人呼叫（自动助理、CVI、虚拟桌面界面）、实时事件和 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="860dc-548">If the usage scenario includes Skype for Business Server 2019 calls, CQD v3 data includes Skype Bot calls (auto attendant, CVI, Virtual Desktop Interface), Live Events, and PSTN calls.</span></span> <span data-ttu-id="860dc-549">CQD v2 不使用此数据。</span><span class="sxs-lookup"><span data-stu-id="860dc-549">CQD v2 does not use this data.</span></span> <span data-ttu-id="860dc-550">（CQD v3 需要配置了 cloud data connector 的 Skype for business Server 2019。）</span><span class="sxs-lookup"><span data-stu-id="860dc-550">(CQD v3 requires Skype for Business Server 2019 with cloud data connector configured.)</span></span>

<span data-ttu-id="860dc-551">例如，如果你在 CQD v2 摘要报告中看到200000音频5000流，但在5500失败时看到300000音频流是不寻常的（区别可能是由于 Skype for business 服务器2019通话、CVI 呼叫、PSTN 呼叫等）在 CQD v3 摘要报告中。</span><span class="sxs-lookup"><span data-stu-id="860dc-551">For instance, if you see 200,000 audio streams with 5000 failures in a CQD v2 Summary Report it would not be unusual to see 300,000 audio streams with 5500 failures (the difference can be due to Skype for Business Server 2019 calls, CVI calls, PSTN calls, and so on) in a CQD v3 Summary report.</span></span>

<span data-ttu-id="860dc-552">为消除意外的差异，请查看整个数据的多个细目。</span><span class="sxs-lookup"><span data-stu-id="860dc-552">To disambiguate unexpected differences, look at more than one breakdown of the overall data.</span></span> <span data-ttu-id="860dc-553">通过一个或多个以下参数对数据进行筛选：</span><span class="sxs-lookup"><span data-stu-id="860dc-553">Filter the data by one or more of the following parameters:</span></span>

- <span data-ttu-id="860dc-554">User Agent Category Pair</span><span class="sxs-lookup"><span data-stu-id="860dc-554">User Agent Category Pair</span></span>
- <span data-ttu-id="860dc-555">第一产品</span><span class="sxs-lookup"><span data-stu-id="860dc-555">First Product</span></span>
- <span data-ttu-id="860dc-556">第二产品</span><span class="sxs-lookup"><span data-stu-id="860dc-556">Second Product</span></span>

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a><span data-ttu-id="860dc-557">CQD v2 和 CQD v3 之间的其他预期差异</span><span class="sxs-lookup"><span data-stu-id="860dc-557">Other expected differences between CQD v2 and CQD v3</span></span>

<span data-ttu-id="860dc-558">团队中有多种质量和可靠性改进，而不是 Skype for business Online：</span><span class="sxs-lookup"><span data-stu-id="860dc-558">There are several Quality and Reliability improvements in Teams but not Skype for Business Online:</span></span>

- <span data-ttu-id="860dc-559">自动重新连接</span><span class="sxs-lookup"><span data-stu-id="860dc-559">Auto-reconnect</span></span>
- <span data-ttu-id="860dc-560">快速漫游</span><span class="sxs-lookup"><span data-stu-id="860dc-560">Fast roaming</span></span>
- <span data-ttu-id="860dc-561">改进的黑白管理</span><span class="sxs-lookup"><span data-stu-id="860dc-561">Improved BW management</span></span>

<span data-ttu-id="860dc-562">比较这两个服务的数据时：</span><span class="sxs-lookup"><span data-stu-id="860dc-562">When you compare data for these two services:</span></span>

- <span data-ttu-id="860dc-563">选择具有紧密焦点的方案，如企业有线连接、Windows 桌面或单个区域或建筑物。</span><span class="sxs-lookup"><span data-stu-id="860dc-563">Pick a scenario with a tight focus, such as corporate wired connections, Windows Desktops, or a single region or building.</span></span>
- <span data-ttu-id="860dc-564">检查团队 MR、TR 或 MP IP 范围。</span><span class="sxs-lookup"><span data-stu-id="860dc-564">Check the Teams MR, TR, or MP IP ranges.</span></span> <span data-ttu-id="860dc-565">团队范围比 Skype for business Online 更新，并且可能导致与防火墙的连接问题</span><span class="sxs-lookup"><span data-stu-id="860dc-565">The Teams ranges are newer than Skype for Business Online, and that can cause connectivity issues involving firewalls</span></span>
- <span data-ttu-id="860dc-566">不要比较汇总或顶级数字。</span><span class="sxs-lookup"><span data-stu-id="860dc-566">Don't compare summary or top-level numbers.</span></span> <span data-ttu-id="860dc-567">这些比较将使你能够将企业有线连接上的 Skype for business Online 通话的大型通话量与 LTE 或专用网络上的一小大量团队通话进行比较。</span><span class="sxs-lookup"><span data-stu-id="860dc-567">These comparisons will lead you to compare a large call volume of Skype for Business Online calls on a corporate wired connection to a small volume of Teams calls on an LTE or private network.</span></span>
- <span data-ttu-id="860dc-568">注意位置偏向和人口差异：有许多比较过于不同的比较非常有用：</span><span class="sxs-lookup"><span data-stu-id="860dc-568">Beware of location bias and population differences: There are many comparisons that are too dissimilar to be useful:</span></span>
  - <span data-ttu-id="860dc-569">NOAM： APAC</span><span class="sxs-lookup"><span data-stu-id="860dc-569">NOAM : APAC</span></span>
  - <span data-ttu-id="860dc-570">纽约州： Goa</span><span class="sxs-lookup"><span data-stu-id="860dc-570">NY : Goa</span></span>
  - <span data-ttu-id="860dc-571">有线 : wifi</span><span class="sxs-lookup"><span data-stu-id="860dc-571">Wired : wifi</span></span>
  - <span data-ttu-id="860dc-572">公司网络：家庭网络</span><span class="sxs-lookup"><span data-stu-id="860dc-572">Corporate network : home network</span></span>
  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="860dc-573">为什么我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="860dc-573">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="860dc-574">这些管理员角色可以访问 CQD，但不能查看 EUII （最终用户身份信息）：</span><span class="sxs-lookup"><span data-stu-id="860dc-574">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="860dc-575">Office 365 报表阅读器</span><span class="sxs-lookup"><span data-stu-id="860dc-575">Office 365 Reports Reader</span></span>
- <span data-ttu-id="860dc-576">团队沟通支持专家</span><span class="sxs-lookup"><span data-stu-id="860dc-576">Teams Communications Support Specialist</span></span>

<span data-ttu-id="860dc-577">若要了解有关可访问 CQD 的角色的详细信息-包括 EUII-读取[分配角色以访问 CQD](quality-of-experience-review-guide.md#assign-roles-for-accessing-cqd)。</span><span class="sxs-lookup"><span data-stu-id="860dc-577">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](quality-of-experience-review-guide.md#assign-roles-for-accessing-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="860dc-578">为什么我仅当我筛选了团队时，我在 CQD 中看到 Skype for Business 信息？</span><span class="sxs-lookup"><span data-stu-id="860dc-578">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="860dc-579">当仅在 CQD 报表（isTeams = 1）中筛选团队时，将筛选*第一个终结点*为团队的所有调用。</span><span class="sxs-lookup"><span data-stu-id="860dc-579">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="860dc-580">如果*第二个终结点*是 Skype for business，则该信息将显示在您的 CQD 报告中。</span><span class="sxs-lookup"><span data-stu-id="860dc-580">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

## <a name="related-topics"></a><span data-ttu-id="860dc-581">相关主题</span><span class="sxs-lookup"><span data-stu-id="860dc-581">Related topics</span></span>

[<span data-ttu-id="860dc-582">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="860dc-582">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="860dc-583">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="860dc-583">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="860dc-584">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="860dc-584">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="860dc-585">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="860dc-585">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="860dc-586">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="860dc-586">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 