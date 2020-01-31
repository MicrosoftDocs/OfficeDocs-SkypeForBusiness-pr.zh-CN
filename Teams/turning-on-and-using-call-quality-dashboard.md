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
f1keywords:
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: '了解如何打开和使用呼叫质量仪表板，获取通话质量的摘要报告。 '
ms.openlocfilehash: 4aea268e2c25e655b7f2dee914497ae3154f0008
ms.sourcegitcommit: 43a17ce6fea3951719b55bfbda03c500cef4816c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41619994"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="62d4d-103">打开和使用 Microsoft 团队和 Skype for business Online 的通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="62d4d-103">Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="62d4d-104">了解如何配置 Office 365 组织以使用呼叫质量仪表板来监控通话质量。</span><span class="sxs-lookup"><span data-stu-id="62d4d-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="62d4d-105">通话质量仪表板（CQD）可深入了解使用 Microsoft 团队和 Skype for business Online 服务进行的通话的质量。</span><span class="sxs-lookup"><span data-stu-id="62d4d-105">Call Quality Dashboard (CQD) provides insight into the quality of calls made using Microsoft Teams and Skype for Business Online services.</span></span> <span data-ttu-id="62d4d-106">本主题介绍了开始收集可用于解决通话质量问题的数据的步骤。</span><span class="sxs-lookup"><span data-stu-id="62d4d-106">This topic describes the steps to start collecting data you can use to troubleshoot call quality issues.</span></span>

<span data-ttu-id="62d4d-107">目前，高级 CQD 和 CQD 都可供使用。</span><span class="sxs-lookup"><span data-stu-id="62d4d-107">Currently, Advanced CQD and CQD are both available for use.</span></span> <span data-ttu-id="62d4d-108">可在<span>https://cqd.teams.microsoft.com</span>使用高级 CQD。</span><span class="sxs-lookup"><span data-stu-id="62d4d-108">Advanced CQD is available at <span>https://cqd.teams.microsoft.com</span>.</span></span> <span data-ttu-id="62d4d-109">新 URL，但具有管理员凭据的相同日志。</span><span class="sxs-lookup"><span data-stu-id="62d4d-109">New URL but the same log in with your administrator credentials.</span></span>

## <a name="latest-changes-and-updates"></a><span data-ttu-id="62d4d-110">最新更改和更新</span><span class="sxs-lookup"><span data-stu-id="62d4d-110">Latest changes and updates</span></span>


<span data-ttu-id="62d4d-111">更新后的 CQD （2019年11月早些时候）提供接近实时 CQD 仪表板的时间。</span><span class="sxs-lookup"><span data-stu-id="62d4d-111">The updated CQD (as of early November 2019) delivers a Near Real-Time CQD dashboard.</span></span> <span data-ttu-id="62d4d-112">CQD 数据现在将在30分钟内可用（与上一个 CQD 相比，它平均为24小时）。</span><span class="sxs-lookup"><span data-stu-id="62d4d-112">CQD data is now available on average in 30 minutes (in comparison to the previous CQD which is on average of 24 hours).</span></span>  <span data-ttu-id="62d4d-113">已更新的 CQD 使用最终用户可识别信息（EUII），使管理员能够向下钻取并放大到用户级别。</span><span class="sxs-lookup"><span data-stu-id="62d4d-113">The updated CQD uses End User Identifiable Information (EUII), giving admins the ability to drill down and zoom in to the user level.</span></span> <span data-ttu-id="62d4d-114">还提供支持新方案的报表交互，例如：</span><span class="sxs-lookup"><span data-stu-id="62d4d-114">There is also report interactivity to support new scenarios such as:</span></span>


- <span data-ttu-id="62d4d-115">按地区呼叫质量：</span><span class="sxs-lookup"><span data-stu-id="62d4d-115">Call Quality by Region:</span></span>
  - <span data-ttu-id="62d4d-116">按区域日期</span><span class="sxs-lookup"><span data-stu-id="62d4d-116">date-by-region</span></span>
  - <span data-ttu-id="62d4d-117">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="62d4d-117">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="62d4d-118">特定位置</span><span class="sxs-lookup"><span data-stu-id="62d4d-118">specific locations</span></span>
  - <span data-ttu-id="62d4d-119">特定子网</span><span class="sxs-lookup"><span data-stu-id="62d4d-119">specific subnet</span></span>
  - <span data-ttu-id="62d4d-120">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="62d4d-120">impacted user or users</span></span>

- <span data-ttu-id="62d4d-121">按地区呼叫可靠性/失败：</span><span class="sxs-lookup"><span data-stu-id="62d4d-121">Call Reliability/Failure by Region:</span></span>
  - <span data-ttu-id="62d4d-122">按区域日期</span><span class="sxs-lookup"><span data-stu-id="62d4d-122">date-by-region</span></span>
  - <span data-ttu-id="62d4d-123">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="62d4d-123">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="62d4d-124">特定位置</span><span class="sxs-lookup"><span data-stu-id="62d4d-124">specific locations</span></span>
  - <span data-ttu-id="62d4d-125">特定子网</span><span class="sxs-lookup"><span data-stu-id="62d4d-125">specific subnet</span></span>
  - <span data-ttu-id="62d4d-126">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="62d4d-126">impacted user or users</span></span>

- <span data-ttu-id="62d4d-127">按区域对我的呼叫（RMC）进行评级：从按区域聚合到特定位置的特定位置到提供低 RMC 等级的用户。</span><span class="sxs-lookup"><span data-stu-id="62d4d-127">Rate My Call (RMC) by Region: from month-by-region aggregated down to specific locations to users who provide low RMC ratings.</span></span> <span data-ttu-id="62d4d-128">CQD v3 还包括逐字反馈。</span><span class="sxs-lookup"><span data-stu-id="62d4d-128">CQD v3 also includes verbatim feedback.</span></span>
- <span data-ttu-id="62d4d-129">帮助者：可用于 P2P 呼叫或会议的特定用户或所有参与者和通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-129">Helpdesk: available for a specific user on P2P calls or Meetings, or for all participants and call details.</span></span> <span data-ttu-id="62d4d-130">帮助识别基于网络位置、设备或固件的可能系统问题。</span><span class="sxs-lookup"><span data-stu-id="62d4d-130">Helps identify possible system issues based on network location, devices, or firmware.</span></span>  
- <span data-ttu-id="62d4d-131">客户端版本：查看每个客户端版本的会话和用户计数，或向下钻取以查看每个客户端版本的用户名。</span><span class="sxs-lookup"><span data-stu-id="62d4d-131">Client Versions: View the Session and Users counts for each Client Version, or drill down to User names for each client version.</span></span> <span data-ttu-id="62d4d-132">产品和客户端类型的预生成筛选器帮助将版本集中到特定客户端。</span><span class="sxs-lookup"><span data-stu-id="62d4d-132">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>
- <span data-ttu-id="62d4d-133">终结点：显示映射到电脑/Mac 的 "生成/模型" 的计算机终结点。</span><span class="sxs-lookup"><span data-stu-id="62d4d-133">Endpoints: Shows Machine Endpoints mapped to Make/Model of the PC/Mac.</span></span> <span data-ttu-id="62d4d-134">按 "生成/模型" 显示聚合质量。</span><span class="sxs-lookup"><span data-stu-id="62d4d-134">Shows aggregated quality by Make/Model.</span></span> <span data-ttu-id="62d4d-135">映射数据的上载类似于生成数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-135">Mapping data is uploaded similar to Building data.</span></span>

<span data-ttu-id="62d4d-136">如果 EUII access 不可用，则高级 CQD （V3）还提供 RBAC 支持。</span><span class="sxs-lookup"><span data-stu-id="62d4d-136">Advanced CQD (V3) also provides RBAC support, in case EUII access is not available.</span></span>  

<span data-ttu-id="62d4d-137">管理员可通过 CQD 版本3管理 Skype for business Server 2019 （不仅仅是 Skype for business Online 和 Microsoft 团队）。</span><span class="sxs-lookup"><span data-stu-id="62d4d-137">An admin can manage Skype for Business Server 2019 (not just Skype for Business Online and Microsoft Teams) through CQD version 3.</span></span> <span data-ttu-id="62d4d-138">这需要混合实现和使用 "调用数据" 连接器。</span><span class="sxs-lookup"><span data-stu-id="62d4d-138">This requires a hybrid implementation and the use of Call Data Connector.</span></span> <span data-ttu-id="62d4d-139">有关详细信息，请参阅[计划通话数据连接器](/SkypeForBusiness/hybrid/plan-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="62d4d-139">See [Plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) for more information.</span></span>

<span data-ttu-id="62d4d-140">已添加 CQD 版本2：</span><span class="sxs-lookup"><span data-stu-id="62d4d-140">CQD version 2 added:</span></span>

- <span data-ttu-id="62d4d-141">Microsoft 团队和 Skype for business Online 的数据</span><span class="sxs-lookup"><span data-stu-id="62d4d-141">Data for Microsoft Teams and Skype for Business Online</span></span>
- <span data-ttu-id="62d4d-142">摘要报告包括一个用于选择所有数据、Microsoft 团队数据或 Skype for Business Online 数据的产品筛选器</span><span class="sxs-lookup"><span data-stu-id="62d4d-142">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data</span></span>
- <span data-ttu-id="62d4d-143">更新了视频和 VBSS 流质量分类逻辑。</span><span class="sxs-lookup"><span data-stu-id="62d4d-143">Updated Video and VBSS stream quality classification logic.</span></span> <span data-ttu-id="62d4d-144">请参阅用于分类器定义的[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="62d4d-144">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the classifier definitions.</span></span>

<span data-ttu-id="62d4d-145">有关[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)的列表，请参阅本文。</span><span class="sxs-lookup"><span data-stu-id="62d4d-145">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="62d4d-146">若要查看有关仪表板的更新和更改的信息，请单击 "**好消息**" 中的链接！</span><span class="sxs-lookup"><span data-stu-id="62d4d-146">To see information about updates and changes to the dashboard,  click the link in the **Good news!**</span></span> <span data-ttu-id="62d4d-147">在仪表板上显示时横幅。</span><span class="sxs-lookup"><span data-stu-id="62d4d-147">banner when it displays on the dashboard.</span></span>

<span data-ttu-id="62d4d-148">CQD 版本1已提供 Skype for Business Server 2015 管理员以下功能：</span><span class="sxs-lookup"><span data-stu-id="62d4d-148">CQD version 1 provided Skype for Business Server 2015 admins the following features:</span></span>

- <span data-ttu-id="62d4d-149">访问缓存的报表数据以快速访问</span><span class="sxs-lookup"><span data-stu-id="62d4d-149">Access to cached report data for fast access</span></span>
- <span data-ttu-id="62d4d-150">指向用于共享和发布信息的报表页面的深层链接</span><span class="sxs-lookup"><span data-stu-id="62d4d-150">Deep links to report pages for sharing and publishing information</span></span>
- <span data-ttu-id="62d4d-151">简化的报表编辑和创建以及报表说明的可编辑元数据</span><span class="sxs-lookup"><span data-stu-id="62d4d-151">Streamlined report editing and creation, and editable metadata for report descriptions</span></span>
- <span data-ttu-id="62d4d-152">为在自定义仪表板中使用而提供对多维数据集数据的编程访问的 Web Api</span><span class="sxs-lookup"><span data-stu-id="62d4d-152">Web APIs that give programmatic access to the cube data for use in custom dashboards</span></span>

## <a name="cqd-near-real-time-nrt-data"></a><span data-ttu-id="62d4d-153">CQD 近实时（NRT）数据</span><span class="sxs-lookup"><span data-stu-id="62d4d-153">CQD Near-Real-Time (NRT) Data</span></span>

<span data-ttu-id="62d4d-154">高级 CQD （V3，发布2019年11月）使用近乎实时的数据馈送。</span><span class="sxs-lookup"><span data-stu-id="62d4d-154">Advanced CQD (V3, released November 2019) uses a near-real-time data feed.</span></span> <span data-ttu-id="62d4d-155">通话记录在通话结束后的30分钟内将在 CQD 门户中可用。</span><span class="sxs-lookup"><span data-stu-id="62d4d-155">Call Records are available at the CQD portal within 30 minutes of the end of the call.</span></span> <span data-ttu-id="62d4d-156">从 NRT 管道中调用记录仅在从数据集内删除几个月后才可用。</span><span class="sxs-lookup"><span data-stu-id="62d4d-156">Call Records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> <span data-ttu-id="62d4d-157">CQD v3 将当前 v2 管道中的数据与 v3 管道中的 NRT 数据合并。</span><span class="sxs-lookup"><span data-stu-id="62d4d-157">CQD v3 merges data from the current v2 pipeline with NRT data from the v3 pipeline.</span></span> <span data-ttu-id="62d4d-158">来自存档周期的数据的 v2 和 v3 门户查询将产生相同的结果。</span><span class="sxs-lookup"><span data-stu-id="62d4d-158">Queries on the v2 and v3 portals for the data from the Archival period produce the same results.</span></span> <span data-ttu-id="62d4d-159">NRT 数据的 V2 和 v3 数据查询和 NRT Data + PII 期间将有所不同。</span><span class="sxs-lookup"><span data-stu-id="62d4d-159">V2 and v3 data queries for the NRT Data and NRT Data + PII periods will be different.</span></span>

### <a name="piieuii-data"></a><span data-ttu-id="62d4d-160">PII/EUII 数据</span><span class="sxs-lookup"><span data-stu-id="62d4d-160">PII/EUII Data</span></span>

<span data-ttu-id="62d4d-161">PII 或 EUII 数据仅来自 v3 管道。</span><span class="sxs-lookup"><span data-stu-id="62d4d-161">PII or EUII data only comes from the v3 pipeline.</span></span> <span data-ttu-id="62d4d-162">由于合规性原因，PII/EUII 数据仅保留30天。</span><span class="sxs-lookup"><span data-stu-id="62d4d-162">Due to compliance reasons, PII/EUII data is only kept for 30 days.</span></span> <span data-ttu-id="62d4d-163">由于 NRT 数据超过30天的标记，将清除 PII/EUII 字段，从而导致 PII NRT 数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-163">As NRT data crosses the 30-day mark, the PII/EUII fields are cleared out, resulting in PII-free NRT data.</span></span> <span data-ttu-id="62d4d-164">PII/EUII 字段是：</span><span class="sxs-lookup"><span data-stu-id="62d4d-164">The PII/EUII fields are:</span></span>

- <span data-ttu-id="62d4d-165">完整 IP 地址</span><span class="sxs-lookup"><span data-stu-id="62d4d-165">Full IP address</span></span>
- <span data-ttu-id="62d4d-166">媒体访问控制（MAC）地址</span><span class="sxs-lookup"><span data-stu-id="62d4d-166">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="62d4d-167">基本服务集标识符（BSSID）</span><span class="sxs-lookup"><span data-stu-id="62d4d-167">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="62d4d-168">会话初始协议（SIP） URI （仅 Skype for business）</span><span class="sxs-lookup"><span data-stu-id="62d4d-168">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="62d4d-169">用户主体名称 (UPN)</span><span class="sxs-lookup"><span data-stu-id="62d4d-169">User Principal Name (UPN)</span></span>
- <span data-ttu-id="62d4d-170">计算机终结点名称</span><span class="sxs-lookup"><span data-stu-id="62d4d-170">Machine Endpoint Name</span></span>
- <span data-ttu-id="62d4d-171">用户逐字反馈</span><span class="sxs-lookup"><span data-stu-id="62d4d-171">User Verbatim Feedback</span></span>
- <span data-ttu-id="62d4d-172">对象 ID （终结点用户的 Active Directory 对象 ID）</span><span class="sxs-lookup"><span data-stu-id="62d4d-172">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="date-controls"></a><span data-ttu-id="62d4d-173">日期控件</span><span class="sxs-lookup"><span data-stu-id="62d4d-173">Date controls</span></span>

<span data-ttu-id="62d4d-174">CQD v3 将添加以下新的滚动趋势类型：</span><span class="sxs-lookup"><span data-stu-id="62d4d-174">CQD v3 adds the following new Rolling Trend types:</span></span>

- <span data-ttu-id="62d4d-175">5天</span><span class="sxs-lookup"><span data-stu-id="62d4d-175">5-day</span></span>
- <span data-ttu-id="62d4d-176">7天</span><span class="sxs-lookup"><span data-stu-id="62d4d-176">7-day</span></span>
- <span data-ttu-id="62d4d-177">30天</span><span class="sxs-lookup"><span data-stu-id="62d4d-177">30-day</span></span>
- <span data-ttu-id="62d4d-178">60-day</span><span class="sxs-lookup"><span data-stu-id="62d4d-178">60-day</span></span>
- <span data-ttu-id="62d4d-179">90-day</span><span class="sxs-lookup"><span data-stu-id="62d4d-179">90-day</span></span>

<span data-ttu-id="62d4d-180">URL 日期参数现在可接受 "天" 字段。</span><span class="sxs-lookup"><span data-stu-id="62d4d-180">The URL Date parameter can now accept a Day field.</span></span> <span data-ttu-id="62d4d-181">"滚动日期" 报告将 "YYYY-MM-DD 格式" 中指定的日期用作趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="62d4d-181">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span>  <span data-ttu-id="62d4d-182">URL 日期参数 "00" 表示 "今日"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-182">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="62d4d-183">URL</span><span class="sxs-lookup"><span data-stu-id="62d4d-183">URL</span></span>| <span data-ttu-id="62d4d-184">滚动日趋势的结束日期</span><span class="sxs-lookup"><span data-stu-id="62d4d-184">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="62d4d-185"><span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="62d4d-185"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="62d4d-186">2019年2月的当前日期</span><span class="sxs-lookup"><span data-stu-id="62d4d-186">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="62d4d-187"><span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="62d4d-187"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="62d4d-188">2019年2月15日</span><span class="sxs-lookup"><span data-stu-id="62d4d-188">Feb 15, 2019</span></span>|
|<span data-ttu-id="62d4d-189"><span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/00/</span></span><span class="sxs-lookup"><span data-stu-id="62d4d-189"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="62d4d-190">当前日期</span><span class="sxs-lookup"><span data-stu-id="62d4d-190">Current Day</span></span>|
|||

<span data-ttu-id="62d4d-191">默认情况下，该月的当前日期用作滚动日期趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="62d4d-191">By default the current day of the month is used as the last day of the Rolling Day Trend.</span></span>

### <a name="drill-thru-functionality"></a><span data-ttu-id="62d4d-192">钻取功能</span><span class="sxs-lookup"><span data-stu-id="62d4d-192">Drill Thru Functionality</span></span>

<span data-ttu-id="62d4d-193">CQD v3 支持使用 SPD 报表中的钻取或向下钻取字段。</span><span class="sxs-lookup"><span data-stu-id="62d4d-193">CQD v3 supports the use of drill through or drill-down fields in SPD reports.</span></span> <span data-ttu-id="62d4d-194">如果选择这些维度字段，报表将自动打开不同的 "报表" 选项卡，并筛选所选值。</span><span class="sxs-lookup"><span data-stu-id="62d4d-194">If these dimension fields are selected,  the report automatically opens a different report tab and filters on the selected value.</span></span> <span data-ttu-id="62d4d-195">将鼠标悬停在其上方时，具有分配的钻取筛选器的字段将由不同的光标图标（指针）进行区分。</span><span class="sxs-lookup"><span data-stu-id="62d4d-195">Fields with an assigned drill through filter are distinguished by a different cursor icon (the pointer) when you hover over them.</span></span>

<span data-ttu-id="62d4d-196">选中 "钻取" 字段时，仪表板将自动导航到新的指定选项卡，并应用具有所选值的筛选器。</span><span class="sxs-lookup"><span data-stu-id="62d4d-196">When a drill through field is selected, the Dashboard automatically navigates to the new, specified tab and applies a filter with the selected value.</span></span> <span data-ttu-id="62d4d-197">如果该选项卡具有自己的钻取字段，并且选择了一个，则以前的钻取筛选器和新的钻取筛选器以及新的钻取。</span><span class="sxs-lookup"><span data-stu-id="62d4d-197">If that tab has its own drill through fields and one is selected, the previous drill through filters and the new one all propagate forward.</span></span> <span data-ttu-id="62d4d-198">这允许你构建可逐渐缩小结果数据集的报表。</span><span class="sxs-lookup"><span data-stu-id="62d4d-198">This allows you to build a report that progressively narrows the resulting data set.</span></span>

<span data-ttu-id="62d4d-199">例如，在通话质量的钻取报表中，用户可以单击想要 "钻取" 的日期，这将导致 "位置" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="62d4d-199">For example, in a Call quality drill-through report, a user can click the date they would like to 'drill-through', which leads to the Location tab.</span></span>

![屏幕截图：显示钻取报表](media/CQD-drill-thru-report.png)

<span data-ttu-id="62d4d-201">可以从 "位置" 选项卡添加多个日期，例如将2019-09-22 添加到日期：2019-09-24：</span><span class="sxs-lookup"><span data-stu-id="62d4d-201">You can add multiple dates from the location tab, such as adding 2019-09-22 to Date: 2019-09-24:</span></span> 

![屏幕截图：向钻取报表添加日期](media/CQD-add-date.png)

> [!NOTE]
> <span data-ttu-id="62d4d-203">不要直接跳转到最后一个选项卡。没有从以前的钻取中选择的筛选器，结果将太大，无法在表格上显示。</span><span class="sxs-lookup"><span data-stu-id="62d4d-203">Don't jump directly to the last tab. Without filters selected from a previous drill-through the results would be too large to show on a table.</span></span>

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="62d4d-204">激活 Microsoft 通话质量仪表板（CQD）摘要报告</span><span class="sxs-lookup"><span data-stu-id="62d4d-204">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="62d4d-205">在开始使用 CQD 之前，请为您的 Office 365 组织激活它，如下所示：</span><span class="sxs-lookup"><span data-stu-id="62d4d-205">Before you can start using CQD, activate it for your Office 365 organization as follows:</span></span>

<span data-ttu-id="62d4d-206">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="62d4d-206">![An icon that shows the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="62d4d-207">使用 Microsoft 团队服务管理员帐户登录到你的 Office 365 组织，然后选择 "**管理员**" 磁贴以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="62d4d-207">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="62d4d-208">在左窗格中的 "**管理中心**" 下，选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-208">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
3. <span data-ttu-id="62d4d-209">在 "Microsoft 团队管理中心" 中，在左窗格中选择 "**呼叫质量" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="62d4d-209">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
4. <span data-ttu-id="62d4d-210">\(在打开 https://<span>cqd.teams.microsoft.com<span/>\)的页面上，单击 "**登录**"，然后输入全局管理员帐户或 microsoft 团队服务管理员帐户信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-210">On the page that opens \(https://<span>cqd.teams.microsoft.com<span/>\), click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span>

    ![屏幕截图：显示凭据提示](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="62d4d-212">登录后，一旦激活，CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-212">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="62d4d-213">可能需要一个或多个小时才能处理足够的数据，以在报表中显示有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="62d4d-213">It may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="62d4d-214">![](media/sfb-logo-30x30.png) **使用 skype for business 旧版门户**的 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="62d4d-214">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="62d4d-215">使用管理员帐户登录到您的 Office 365 组织，然后选择 "**管理员**" 磁贴以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="62d4d-215">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="62d4d-216">在左窗格中的 "**管理中心**" 下，选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-216">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
3. <span data-ttu-id="62d4d-217">在 Microsoft 团队管理中心中，在左窗格中选择 "**旧版门户**"，选择 "**工具**"，然后选择 " **Skype for Business Online 呼叫质量" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="62d4d-217">In the Microsoft Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

     ![屏幕截图：选择 "呼叫质量" 仪表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="62d4d-219">在打开的页面上，用全局管理员帐户登录，然后在出现提示时提供帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-219">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="62d4d-220">登录后，"呼叫质量" 仪表板将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-220">After you sign in, once activated, the Call Quality Dashboard will begin collecting and processing data.</span></span>

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="62d4d-221">Microsoft 团队和 Skype for business Online 的通话质量仪表板的功能</span><span class="sxs-lookup"><span data-stu-id="62d4d-221">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="62d4d-222"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="62d4d-222"><a name="BKMKFeaturesOfTheCQD"> </a></span></span>


<span data-ttu-id="62d4d-223">CQD 摘要报告提供为详细报告规划的功能的子集。</span><span class="sxs-lookup"><span data-stu-id="62d4d-223">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="62d4d-224">此处概括介绍了版本之间的差异：</span><span class="sxs-lookup"><span data-stu-id="62d4d-224">The differences between the editions are summarized here:</span></span>
  
|<span data-ttu-id="62d4d-225">功能</span><span class="sxs-lookup"><span data-stu-id="62d4d-225">Feature</span></span>|<span data-ttu-id="62d4d-226">摘要报告</span><span class="sxs-lookup"><span data-stu-id="62d4d-226">Summary Reports</span></span>|<span data-ttu-id="62d4d-227">详细报告</span><span class="sxs-lookup"><span data-stu-id="62d4d-227">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="62d4d-228">应用程序共享跃点数</span><span class="sxs-lookup"><span data-stu-id="62d4d-228">Application sharing metric</span></span> | <span data-ttu-id="62d4d-229">否</span><span class="sxs-lookup"><span data-stu-id="62d4d-229">No</span></span> | <span data-ttu-id="62d4d-230">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-230">Yes</span></span> |
|<span data-ttu-id="62d4d-231">客户构建信息支持</span><span class="sxs-lookup"><span data-stu-id="62d4d-231">Customer building information support</span></span> | <span data-ttu-id="62d4d-232">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-232">Yes</span></span> | <span data-ttu-id="62d4d-233">是 </span><span class="sxs-lookup"><span data-stu-id="62d4d-233">Yes</span></span> |
|<span data-ttu-id="62d4d-234">客户终结点信息支持</span><span class="sxs-lookup"><span data-stu-id="62d4d-234">Customer endpoint information support</span></span> | <span data-ttu-id="62d4d-235">仅在<span>cqd.teams.microsoft.com 中<span/></span><span class="sxs-lookup"><span data-stu-id="62d4d-235">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="62d4d-236">仅在<span>cqd.teams.microsoft.com 中<span/></span><span class="sxs-lookup"><span data-stu-id="62d4d-236">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="62d4d-237">向下钻取分析支持</span><span class="sxs-lookup"><span data-stu-id="62d4d-237">Drill down analysis support</span></span>   | <span data-ttu-id="62d4d-238">否</span><span class="sxs-lookup"><span data-stu-id="62d4d-238">No</span></span>   | <span data-ttu-id="62d4d-239">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-239">Yes</span></span>   |
|<span data-ttu-id="62d4d-240">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="62d4d-240">Media reliability metrics</span></span>   | <span data-ttu-id="62d4d-241">否</span><span class="sxs-lookup"><span data-stu-id="62d4d-241">No</span></span>   | <span data-ttu-id="62d4d-242">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-242">Yes</span></span>   |
|<span data-ttu-id="62d4d-243">现成的报表</span><span class="sxs-lookup"><span data-stu-id="62d4d-243">Out-of-the-box reports</span></span>   | <span data-ttu-id="62d4d-244">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-244">Yes</span></span>   | <span data-ttu-id="62d4d-245">是 </span><span class="sxs-lookup"><span data-stu-id="62d4d-245">Yes</span></span>   |
|<span data-ttu-id="62d4d-246">概述报表</span><span class="sxs-lookup"><span data-stu-id="62d4d-246">Overview reports</span></span>   | <span data-ttu-id="62d4d-247">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-247">Yes</span></span>   | <span data-ttu-id="62d4d-248">是 </span><span class="sxs-lookup"><span data-stu-id="62d4d-248">Yes</span></span>   |
|<span data-ttu-id="62d4d-249">每用户报告集</span><span class="sxs-lookup"><span data-stu-id="62d4d-249">Per-user report set</span></span>   | <span data-ttu-id="62d4d-250">否</span><span class="sxs-lookup"><span data-stu-id="62d4d-250">No</span></span>   | <span data-ttu-id="62d4d-251">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-251">Yes</span></span>   |
|<span data-ttu-id="62d4d-252">报表集自定义（添加、删除、修改报表）</span><span class="sxs-lookup"><span data-stu-id="62d4d-252">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="62d4d-253">否</span><span class="sxs-lookup"><span data-stu-id="62d4d-253">No</span></span>   | <span data-ttu-id="62d4d-254">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-254">Yes</span></span>   |
|<span data-ttu-id="62d4d-255">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="62d4d-255">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="62d4d-256">否</span><span class="sxs-lookup"><span data-stu-id="62d4d-256">No</span></span>   | <span data-ttu-id="62d4d-257">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-257">Yes</span></span>   |
|<span data-ttu-id="62d4d-258">视频指标</span><span class="sxs-lookup"><span data-stu-id="62d4d-258">Video metrics</span></span>   | <span data-ttu-id="62d4d-259">否</span><span class="sxs-lookup"><span data-stu-id="62d4d-259">No</span></span>   | <span data-ttu-id="62d4d-260">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-260">Yes</span></span>   |
|<span data-ttu-id="62d4d-261">可用数据量</span><span class="sxs-lookup"><span data-stu-id="62d4d-261">Amount of data available</span></span>   | <span data-ttu-id="62d4d-262">过去12个月</span><span class="sxs-lookup"><span data-stu-id="62d4d-262">Last 12 months</span></span>   | <span data-ttu-id="62d4d-263">过去12个月</span><span class="sxs-lookup"><span data-stu-id="62d4d-263">Last 12 months</span></span>   |
|<span data-ttu-id="62d4d-264">Microsoft 团队数据</span><span class="sxs-lookup"><span data-stu-id="62d4d-264">Microsoft Teams data</span></span>   | <span data-ttu-id="62d4d-265">是</span><span class="sxs-lookup"><span data-stu-id="62d4d-265">Yes</span></span>   | <span data-ttu-id="62d4d-266">是 </span><span class="sxs-lookup"><span data-stu-id="62d4d-266">Yes</span></span>   |
| | | |

### <a name="out-of-the-box-reports"></a><span data-ttu-id="62d4d-267">现成的报表</span><span class="sxs-lookup"><span data-stu-id="62d4d-267">Out-of-the-box reports</span></span>

<span data-ttu-id="62d4d-268">所有版本的 CQD 都提供了一种可提供通话质量指标的体验，无需创建新报表。</span><span class="sxs-lookup"><span data-stu-id="62d4d-268">All editions of CQD provide an experience that gives you call quality metrics without the need to create new reports.</span></span> <span data-ttu-id="62d4d-269">在后端处理完数据后，您将在报告中看到通话质量数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-269">Once data is processed in the back-end, you see call quality data in the reports.</span></span>

<span data-ttu-id="62d4d-270">2020年1月[的新增功能：下载 CQD 的 POWER BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD Power BI query templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="62d4d-270">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD Power BI query templates.zip?raw=true).</span></span> <span data-ttu-id="62d4d-271">可用于分析和报告 CQD 数据的自定义 Power BI 模板。</span><span class="sxs-lookup"><span data-stu-id="62d4d-271">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="62d4d-272">概述报表</span><span class="sxs-lookup"><span data-stu-id="62d4d-272">Overview reports</span></span>

<span data-ttu-id="62d4d-273">CQD 的所有版本都为整体通话质量信息提供高级别的入口点，但信息在摘要报告中的显示方式不同于详细的报告。</span><span class="sxs-lookup"><span data-stu-id="62d4d-273">All editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from Detailed Reports.</span></span>  
  
<span data-ttu-id="62d4d-274">摘要报告提供简化的选项卡式页面报告视图，以便你可以快速浏览和理解整体通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="62d4d-274">Summary Reports provide a simplified tabbed page report view so you can quickly browse and understand the overall call quality status and trends.</span></span>

<span data-ttu-id="62d4d-275">四个选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="62d4d-275">The four tabs include:</span></span>
  
- <span data-ttu-id="62d4d-276">**整体通话质量**-提供有关所有流的信息，它是显示每月和每天的趋势的聚合：</span><span class="sxs-lookup"><span data-stu-id="62d4d-276">**Overall Call Quality** — provides information about all streams, which is an aggregation that shows monthly and daily trends for:</span></span>
  - <span data-ttu-id="62d4d-277">服务器-客户端流</span><span class="sxs-lookup"><span data-stu-id="62d4d-277">Server-Client streams</span></span>
  - <span data-ttu-id="62d4d-278">客户端-客户端流</span><span class="sxs-lookup"><span data-stu-id="62d4d-278">Client-Client streams</span></span>
  - <span data-ttu-id="62d4d-279">单独的服务器-客户端和客户端-客户端流</span><span class="sxs-lookup"><span data-stu-id="62d4d-279">Separate Server-Client and Client-Client streams</span></span>
- <span data-ttu-id="62d4d-280">**服务器-客户端**-提供服务器和客户端终结点之间的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-280">**Server—Client** — provides details for the streams between Server and Client endpoints.</span></span>
- <span data-ttu-id="62d4d-281">**客户端-客户端**-提供两个客户端终结点之间的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-281">**Client—Client** — provides details for the streams between two Client endpoints.</span></span>
- <span data-ttu-id="62d4d-282">**语音质量 SLA** —提供有关 Skype For Business Online 语音质量 SLA 中所含通话的信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-282">**Voice Quality SLA** — provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>

> [!NOTE]
> <span data-ttu-id="62d4d-283">CQD 版本3适用于 Microsoft 团队、Skype for business Online 和 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="62d4d-283">CQD Version 3 works with Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span> <span data-ttu-id="62d4d-284">要将 CQD 与 Skype for Business Server 2019 配合使用，您必须[配置 "呼叫数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-284">To use CQD with Skype for Business Server 2019, you will have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="62d4d-285">请参阅在开始之前[计划通话数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="62d4d-285">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>

- <span data-ttu-id="62d4d-286">按地区呼叫质量：</span><span class="sxs-lookup"><span data-stu-id="62d4d-286">Call Quality by Region:</span></span>

  - <span data-ttu-id="62d4d-287">按区域日期</span><span class="sxs-lookup"><span data-stu-id="62d4d-287">date-by-region</span></span>
  - <span data-ttu-id="62d4d-288">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="62d4d-288">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="62d4d-289">特定位置</span><span class="sxs-lookup"><span data-stu-id="62d4d-289">specific locations</span></span>
  - <span data-ttu-id="62d4d-290">特定子网</span><span class="sxs-lookup"><span data-stu-id="62d4d-290">specific subnet</span></span>
  - <span data-ttu-id="62d4d-291">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="62d4d-291">impacted user or users</span></span>

- <span data-ttu-id="62d4d-292">按地区呼叫可靠性/失败：</span><span class="sxs-lookup"><span data-stu-id="62d4d-292">Call Reliability/Failure by Region:</span></span>
  - <span data-ttu-id="62d4d-293">按区域日期</span><span class="sxs-lookup"><span data-stu-id="62d4d-293">date-by-region</span></span>
  - <span data-ttu-id="62d4d-294">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="62d4d-294">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="62d4d-295">特定位置</span><span class="sxs-lookup"><span data-stu-id="62d4d-295">specific locations</span></span>
  - <span data-ttu-id="62d4d-296">特定子网</span><span class="sxs-lookup"><span data-stu-id="62d4d-296">specific subnet</span></span>
  - <span data-ttu-id="62d4d-297">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="62d4d-297">impacted user or users</span></span>

- <span data-ttu-id="62d4d-298">按区域对我的呼叫（RMC）进行评级：从按区域聚合到特定位置的特定位置到提供低 RMC 等级的用户。</span><span class="sxs-lookup"><span data-stu-id="62d4d-298">Rate My Call (RMC) by Region: from month-by-region aggregated down to specific locations to users who provide low RMC ratings.</span></span> <span data-ttu-id="62d4d-299">CQD v3 还包括逐字反馈。</span><span class="sxs-lookup"><span data-stu-id="62d4d-299">CQD v3 also includes verbatim feedback.</span></span>
- <span data-ttu-id="62d4d-300">帮助者：可用于 P2P 呼叫或会议的特定用户或所有参与者和通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-300">Helpdesk: available for a specific user on P2P calls or Meetings, or for all participants and call details.</span></span> <span data-ttu-id="62d4d-301">帮助识别基于网络位置、设备或固件的可能系统问题。</span><span class="sxs-lookup"><span data-stu-id="62d4d-301">Helps identify possible system issues based on network location, devices, or firmware.</span></span>  
- <span data-ttu-id="62d4d-302">客户端版本：查看每个客户端版本的会话和用户计数，或向下钻取以查看每个客户端版本的用户名。</span><span class="sxs-lookup"><span data-stu-id="62d4d-302">Client Versions: View the Session and Users counts for each Client Version, or drill down to User names for each client version.</span></span> <span data-ttu-id="62d4d-303">产品和客户端类型的预生成筛选器帮助将版本集中到特定客户端。</span><span class="sxs-lookup"><span data-stu-id="62d4d-303">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>
- <span data-ttu-id="62d4d-304">终结点：显示映射到电脑/Mac 的 "生成/模型" 的计算机终结点。</span><span class="sxs-lookup"><span data-stu-id="62d4d-304">Endpoints: Shows Machine Endpoints mapped to Make/Model of the PC/Mac.</span></span> <span data-ttu-id="62d4d-305">按 "生成/模型" 显示聚合质量。</span><span class="sxs-lookup"><span data-stu-id="62d4d-305">Shows aggregated quality by Make/Model.</span></span> <span data-ttu-id="62d4d-306">映射数据的上载类似于生成数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-306">Mapping data is uploaded similar to Building data.</span></span>

### <a name="overall-call-quality-tab"></a><span data-ttu-id="62d4d-307">"整体通话质量" 选项卡</span><span class="sxs-lookup"><span data-stu-id="62d4d-307">Overall Call Quality tab</span></span>

<span data-ttu-id="62d4d-308">使用此选项卡上的数据根据流计数和不良百分比评估通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="62d4d-308">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="62d4d-309">右上角的图例将显示哪些颜色和视觉元素表示这些指标。</span><span class="sxs-lookup"><span data-stu-id="62d4d-309">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![屏幕截图：显示 "通话质量" 选项卡](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="62d4d-311">流分为三个组： "完好"、"差" 和 "未分类"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-311">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="62d4d-312">还计算出的*百分比*值太差，可让你将流的比率划分为*较差*的分类流计数。</span><span class="sxs-lookup"><span data-stu-id="62d4d-312">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="62d4d-313">由于*较差的% = 不良流/（差流 + 正常流） \* 100*，*差%* 不受多个未*分类*流的存在的影响。</span><span class="sxs-lookup"><span data-stu-id="62d4d-313">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="62d4d-314">若要查看将流分类为差或好的内容，请参阅["呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-314">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="62d4d-315">使用左侧的刻度测量流计数值。</span><span class="sxs-lookup"><span data-stu-id="62d4d-315">Use the scale on the left to measure the stream count values.</span></span>
  
![屏幕截图：显示流计数值](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="62d4d-317">使用右侧的刻度测量差的百分比值。</span><span class="sxs-lookup"><span data-stu-id="62d4d-317">Use the scale on the right to measure the Poor % values.</span></span>
  
![屏幕截图：显示差的% 值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="62d4d-319">也可以通过将鼠标悬停在条上来获取实际数值。</span><span class="sxs-lookup"><span data-stu-id="62d4d-319">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62d4d-320">下面的示例来自非常小的示例数据集，并且值对于实际部署不切合实际。</span><span class="sxs-lookup"><span data-stu-id="62d4d-320">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![屏幕截图：显示用于访问数据的鼠标](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="62d4d-322">整个流卷可帮助确定计算出的较差百分比的相关程度。</span><span class="sxs-lookup"><span data-stu-id="62d4d-322">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="62d4d-323">总体流的数量越小，报告的百分比值越低越可靠。</span><span class="sxs-lookup"><span data-stu-id="62d4d-323">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="62d4d-324">服务器-客户端选项卡和客户端-客户端选项卡</span><span class="sxs-lookup"><span data-stu-id="62d4d-324">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="62d4d-325">这两个选项卡提供了在其终结点到终结点应用场景中发生的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-325">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="62d4d-326">"服务器-客户端" 选项卡具有四个可折叠的部分，表示媒体流将流经的四个方案。</span><span class="sxs-lookup"><span data-stu-id="62d4d-326">The Server-Client tab has four collapsible sections  that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="62d4d-327">内部有线</span><span class="sxs-lookup"><span data-stu-id="62d4d-327">Wired Inside</span></span>
- <span data-ttu-id="62d4d-328">外部有线</span><span class="sxs-lookup"><span data-stu-id="62d4d-328">Wired Outside</span></span>
- <span data-ttu-id="62d4d-329">内部 Wifi</span><span class="sxs-lookup"><span data-stu-id="62d4d-329">Wifi Inside</span></span>
- <span data-ttu-id="62d4d-330">外部 Wifi</span><span class="sxs-lookup"><span data-stu-id="62d4d-330">Wifi Outside</span></span>

<span data-ttu-id="62d4d-331">同样，"客户端-客户端" 选项卡具有五个可折叠部分：</span><span class="sxs-lookup"><span data-stu-id="62d4d-331">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="62d4d-332">有线内部-有线内部</span><span class="sxs-lookup"><span data-stu-id="62d4d-332">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="62d4d-333">有线内部-有线外部</span><span class="sxs-lookup"><span data-stu-id="62d4d-333">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="62d4d-334">有线外部-有线外部</span><span class="sxs-lookup"><span data-stu-id="62d4d-334">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="62d4d-335">内部有线-内部 Wifi</span><span class="sxs-lookup"><span data-stu-id="62d4d-335">Wired Inside — Wifi Inside</span></span>
- <span data-ttu-id="62d4d-336">内部有线-外部 Wifi</span><span class="sxs-lookup"><span data-stu-id="62d4d-336">Wired Inside — Wifi Outside</span></span>

#### <a name="inside-test"></a><span data-ttu-id="62d4d-337">内部测试</span><span class="sxs-lookup"><span data-stu-id="62d4d-337">Inside Test</span></span>

<span data-ttu-id="62d4d-338">在处理期间，CQD 后端使用建筑物信息将流分类为*内部*或*外部*流（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="62d4d-338">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="62d4d-339">每个流的终结点与子网地址相关联。</span><span class="sxs-lookup"><span data-stu-id="62d4d-339">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="62d4d-340">如果子网位于上载的生成信息中标记为 "InsideCorp" 的子网列表中，则将其视为*内部*。</span><span class="sxs-lookup"><span data-stu-id="62d4d-340">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="62d4d-341">如果尚未上载生成信息，则内部测试始终会将流分类为*外部*流。</span><span class="sxs-lookup"><span data-stu-id="62d4d-341">If Building information has not yet been uploaded, then Inside Test  always classifies the streams as *Outside*.</span></span>  

> [!NOTE]
> <span data-ttu-id="62d4d-342">服务器客户端方案的内部测试仅考虑客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="62d4d-342">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="62d4d-343">由于服务器始终来自用户的视角，因此不会在测试中考虑。</span><span class="sxs-lookup"><span data-stu-id="62d4d-343">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="62d4d-344">有线与 wifi</span><span class="sxs-lookup"><span data-stu-id="62d4d-344">Wired vs. wifi</span></span>

<span data-ttu-id="62d4d-345">根据名称指示，分类标准基于客户端连接的类型。</span><span class="sxs-lookup"><span data-stu-id="62d4d-345">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="62d4d-346">同样，服务器始终是有线的，并且不会包含在计算中。</span><span class="sxs-lookup"><span data-stu-id="62d4d-346">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62d4d-347">如果有一个流，则如果两个终结点中的一个终结点连接到 Wifi 网络，则会在 CQD 中将其分类为 Wifi。</span><span class="sxs-lookup"><span data-stu-id="62d4d-347">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span>
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="62d4d-348">选择要在报表中查看的产品数据</span><span class="sxs-lookup"><span data-stu-id="62d4d-348">Selecting product data to see in reports</span></span>

<a name="BKMKProductFilter"></a>

<span data-ttu-id="62d4d-349">在摘要和位置增强的报表中，你可以使用 "**产品筛选器**" 下拉列表显示所有产品数据、仅 Microsoft 团队数据或仅 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-349">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![屏幕截图：显示产品筛选器控件选项](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="62d4d-351">在 "详细报表" 中，可以使用 "**属于团队**" 维度将数据筛选到 Microsoft 团队或 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-351">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="62d4d-352">上载租户数据信息</span><span class="sxs-lookup"><span data-stu-id="62d4d-352">Upload Tenant Data information</span></span>

<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="62d4d-353">CQD 摘要报告仪表板包括**租户数据上载**页面，该页面从右上角的 "设置" 菜单中选择 "**租户数据上载**"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-353">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="62d4d-354">此页面用于管理员上载其自己的信息，例如：</span><span class="sxs-lookup"><span data-stu-id="62d4d-354">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="62d4d-355">IP 地址和地理信息的地图</span><span class="sxs-lookup"><span data-stu-id="62d4d-355">A map of IP address and geographical information</span></span>
- <span data-ttu-id="62d4d-356">每个无线 AP 及其 MAC 地址的地图</span><span class="sxs-lookup"><span data-stu-id="62d4d-356">A map of each wireless AP and its MAC address</span></span>
- <span data-ttu-id="62d4d-357">终结点到终结点的映射/模型/类型等。</span><span class="sxs-lookup"><span data-stu-id="62d4d-357">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62d4d-358">你上载到 CQD 的报告标签将按你的 Office 365 协议下的*支持数据*进行处理，包括任何其他被视为*客户数据*或*个人资料*的信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-358">Reporting Labels that you upload to CQD will be handled as *Support Data* under your agreement for Office 365, including any information that would otherwise be considered *Customer Data* or *Personal Data*.</span></span> <span data-ttu-id="62d4d-359">请不要包含不希望作为*支持数据*提供给 microsoft 的数据，此信息将对 microsoft 工程师可见，以便于支持之用。</span><span class="sxs-lookup"><span data-stu-id="62d4d-359">Please do not include data you do not wish to provide to Microsoft as *Support Data*, this information will be visible to Microsoft Engineers for support purposes.</span></span>

![屏幕截图：显示呼叫质量仪表板租户数据](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="62d4d-361">在 "**租户数据上载**" 页面上，使用下拉菜单选择要上传的数据文件类型。</span><span class="sxs-lookup"><span data-stu-id="62d4d-361">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type to upload.</span></span> <span data-ttu-id="62d4d-362">"文件" 数据类型表示文件的内容（例如，"建筑物" 指的是 IP 地址和建筑物和其他地理信息的映射，"终结点" 指终结点名称和模型/类型信息的映射。</span><span class="sxs-lookup"><span data-stu-id="62d4d-362">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building and other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type information).</span></span> <span data-ttu-id="62d4d-363">当前 CQD 支持 cqd.teams.microsoft.com 的 "建筑物" 和 "终结点" 数据类型（在预览阶段和尚未正式提供），cqd.lync.com 仅支持 "建筑物" 数据类型。</span><span class="sxs-lookup"><span data-stu-id="62d4d-363">Currently CQD supports “Building” and “Endpoint” data types for cqd.teams.microsoft.com (in preview stage and not officially available yet), cqd.lync.com only supports the "Building" data type.</span></span>



2. <span data-ttu-id="62d4d-364">选择文件数据类型后，单击 "**浏览**" 以选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="62d4d-364">After you select the file data type, click **Browse** to choose a data file.</span></span>

   - <span data-ttu-id="62d4d-365">数据文件必须为 tsv （以制表符分隔的值）文件或 .csv （以逗号分隔的值）文件。</span><span class="sxs-lookup"><span data-stu-id="62d4d-365">A data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="62d4d-366">使用 .csv 文件时，包含逗号的任何字段都必须用引号引起来，或者删除逗号。</span><span class="sxs-lookup"><span data-stu-id="62d4d-366">With a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="62d4d-367">例如，如果建筑物名称为 NY，则在 .csv 文件中输入 "纽约州，NY"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-367">For example, if your building name is NY,NY,  enter  "NY,NY" in the .csv file.</span></span>
   - <span data-ttu-id="62d4d-368">数据文件不能大于 50 MB。</span><span class="sxs-lookup"><span data-stu-id="62d4d-368">The data file must be no larger than 50 MB.</span></span>
   - <span data-ttu-id="62d4d-369">上载到 cqd.teams.microsoft.com 的文件具有展开的行限制1000000以使查询性能更快。</span><span class="sxs-lookup"><span data-stu-id="62d4d-369">Files uploaded to cqd.teams.microsoft.com have an expanded row limit of 1,000,000 to keep query performance fast.</span></span> <span data-ttu-id="62d4d-370">此限制也适用于 CQD<span></span><span></span>上的 CQD v2。</span><span class="sxs-lookup"><span data-stu-id="62d4d-370">This limit also applies to CQD v2  on cqd<span></span>.lync<span></span>.com.</span></span>
   - <span data-ttu-id="62d4d-371">对于每个数据文件，文件中的每一列都必须与本主题后面部分所述的预定义数据类型匹配。</span><span class="sxs-lookup"><span data-stu-id="62d4d-371">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
3. <span data-ttu-id="62d4d-372">接下来，指定**开始日期**，并根据需要**指定结束日期**。</span><span class="sxs-lookup"><span data-stu-id="62d4d-372">Next, specify a **Start date** and, optionally, **Specify an end date**.</span></span>
4. <span data-ttu-id="62d4d-373">最后，选择 "**上传**" 将文件上载到 CQD 服务器。</span><span class="sxs-lookup"><span data-stu-id="62d4d-373">Finally, select **Upload** to upload the file to the CQD server.</span></span>
    <span data-ttu-id="62d4d-374">上载文件之前，首先验证该文件。</span><span class="sxs-lookup"><span data-stu-id="62d4d-374">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="62d4d-375">验证后，它将存储在 Azure blob 中。</span><span class="sxs-lookup"><span data-stu-id="62d4d-375">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="62d4d-376">如果验证失败或文件无法存储在 Azure blob 中，则会显示一条错误消息请求对文件的更正。</span><span class="sxs-lookup"><span data-stu-id="62d4d-376">If validation fails or the file fails to be stored in an Azure blob, an error message requests a correction to the file.</span></span> <span data-ttu-id="62d4d-377">下图显示了数据文件中的列数不正确的示例错误。</span><span class="sxs-lookup"><span data-stu-id="62d4d-377">The following image shows a sample error with an incorrect number of columns in the data file.</span></span>

     ![屏幕截图：显示上载验证错误](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="62d4d-379">如果验证期间未出现任何错误，则文件上载成功。</span><span class="sxs-lookup"><span data-stu-id="62d4d-379">If no errors occur during validation, the file upload succeeds.</span></span> <span data-ttu-id="62d4d-380">然后，您可以在 "我的上**传**" 表中看到上载的数据文件。</span><span class="sxs-lookup"><span data-stu-id="62d4d-380">You can then see the uploaded data file in the **My uploads** table.</span></span> <span data-ttu-id="62d4d-381">该页面底部还显示为当前租户上载的所有文件的完整列表。</span><span class="sxs-lookup"><span data-stu-id="62d4d-381">The bottom of that page also shows a full list of all files uploaded for the current tenant.</span></span>
    <span data-ttu-id="62d4d-382">每个记录显示一个上载的租户数据文件，其中包含文件类型、上次更新时间、时间段、说明、删除图标和下载图标。</span><span class="sxs-lookup"><span data-stu-id="62d4d-382">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="62d4d-383">若要删除文件，请选择表格中的垃圾桶图标。</span><span class="sxs-lookup"><span data-stu-id="62d4d-383">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="62d4d-384">若要下载文件，请选择表格的 "**下载**" 列中的 "下载" 图标。</span><span class="sxs-lookup"><span data-stu-id="62d4d-384">To download a file, select the download icon in the **Download** column of the table.</span></span>

     ![屏幕截图：显示 "我的上传" 表](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. <span data-ttu-id="62d4d-386">如果你选择使用多个生成数据文件或多个终结点数据文件，则某些报表的生成速度较慢。</span><span class="sxs-lookup"><span data-stu-id="62d4d-386">If you choose to use multiple building data files or multiple endpoint data files, some reports generate more slowly.</span></span>

### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="62d4d-387">租户数据文件格式和结构</span><span class="sxs-lookup"><span data-stu-id="62d4d-387">Tenant data file format and structure</span></span>

<span data-ttu-id="62d4d-388"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="62d4d-388"><a name="BKMKTenantDataFile"> </a></span></span>

### <a name="building-data-file"></a><span data-ttu-id="62d4d-389">生成数据文件</span><span class="sxs-lookup"><span data-stu-id="62d4d-389">Building data file</span></span>

<span data-ttu-id="62d4d-390">CQD 使用构建数据文件，这有助于提供有用的通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-390">CQD uses a Building data file, which helps provide useful call details.</span></span> <span data-ttu-id="62d4d-391">通过展开 "网络 + NetworkRange" 列，然后将 "子网" 列联接到呼叫记录的第一个子网或 "第二个子网" 列中，显示建筑物、城市、国家或地区信息，从而派生出子网列。</span><span class="sxs-lookup"><span data-stu-id="62d4d-391">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="62d4d-392">你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="62d4d-392">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

<span data-ttu-id="62d4d-393">可以[在此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下载示例模板</span><span class="sxs-lookup"><span data-stu-id="62d4d-393">You can download a sample template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)</span></span>
  
- <span data-ttu-id="62d4d-394">文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="62d4d-394">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>
- <span data-ttu-id="62d4d-395">数据文件不包含表格标题行。</span><span class="sxs-lookup"><span data-stu-id="62d4d-395">The data file doesn't include a table header row.</span></span> <span data-ttu-id="62d4d-396">数据文件的第一行应为真实数据，而不是标题标签（如 "Network"）。</span><span class="sxs-lookup"><span data-stu-id="62d4d-396">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>
- <span data-ttu-id="62d4d-397">文件中的数据类型只能是 String、Integer 或 Boolean。</span><span class="sxs-lookup"><span data-stu-id="62d4d-397">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="62d4d-398">对于整数数据类型，值必须是一个数值。</span><span class="sxs-lookup"><span data-stu-id="62d4d-398">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="62d4d-399">布尔值必须是0或1。</span><span class="sxs-lookup"><span data-stu-id="62d4d-399">Boolean values must be either 0 or 1.</span></span>
- <span data-ttu-id="62d4d-400">如果列使用字符串数据类型，则数据字段可以为空，但仍须由制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="62d4d-400">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="62d4d-401">空数据字段只是分配一个空字符串值。</span><span class="sxs-lookup"><span data-stu-id="62d4d-401">An empty data field just assigns an empty String value.</span></span>
- <span data-ttu-id="62d4d-402">每一行必须有14列，每一列必须具有相应的数据类型，并且列必须遵循下表中列出的顺序：</span><span class="sxs-lookup"><span data-stu-id="62d4d-402">There must be 14 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table:</span></span>

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|<span data-ttu-id="62d4d-403">**列字段名称**</span><span class="sxs-lookup"><span data-stu-id="62d4d-403">**Column field name**</span></span>|<span data-ttu-id="62d4d-404">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="62d4d-404">NetworkIP</span></span>  |<span data-ttu-id="62d4d-405">NetworkName</span><span class="sxs-lookup"><span data-stu-id="62d4d-405">NetworkName</span></span>              |<span data-ttu-id="62d4d-406">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="62d4d-406">NetworkRange</span></span>|<span data-ttu-id="62d4d-407">BuildingName</span><span class="sxs-lookup"><span data-stu-id="62d4d-407">BuildingName</span></span>  |<span data-ttu-id="62d4d-408">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="62d4d-408">OwnershipType</span></span>| <span data-ttu-id="62d4d-409">BuildingType</span><span class="sxs-lookup"><span data-stu-id="62d4d-409">BuildingType</span></span>  |<span data-ttu-id="62d4d-410">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="62d4d-410">BuildingOfficeType</span></span>|<span data-ttu-id="62d4d-411">城市</span><span class="sxs-lookup"><span data-stu-id="62d4d-411">City</span></span>   |<span data-ttu-id="62d4d-412">ZipCode</span><span class="sxs-lookup"><span data-stu-id="62d4d-412">ZipCode</span></span>|<span data-ttu-id="62d4d-413">该国</span><span class="sxs-lookup"><span data-stu-id="62d4d-413">Country</span></span>|<span data-ttu-id="62d4d-414">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="62d4d-414">State</span></span> |<span data-ttu-id="62d4d-415">区域</span><span class="sxs-lookup"><span data-stu-id="62d4d-415">Region</span></span>|<span data-ttu-id="62d4d-416">InsideCorp&dagger;</span><span class="sxs-lookup"><span data-stu-id="62d4d-416">InsideCorp&dagger;</span></span>|<span data-ttu-id="62d4d-417">ExpressRoute&Dagger;</span><span class="sxs-lookup"><span data-stu-id="62d4d-417">ExpressRoute&Dagger;</span></span>|<span data-ttu-id="62d4d-418">VPN （可选）</span><span class="sxs-lookup"><span data-stu-id="62d4d-418">VPN (optional)</span></span>|
|<span data-ttu-id="62d4d-419">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="62d4d-419">**Data type**</span></span>        | <span data-ttu-id="62d4d-420">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-420">String</span></span>    | <span data-ttu-id="62d4d-421">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-421">String</span></span>                  |<span data-ttu-id="62d4d-422">数字</span><span class="sxs-lookup"><span data-stu-id="62d4d-422">Number</span></span>      | <span data-ttu-id="62d4d-423">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-423">String</span></span>       | <span data-ttu-id="62d4d-424">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-424">String</span></span>      | <span data-ttu-id="62d4d-425">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-425">String</span></span>        |<span data-ttu-id="62d4d-426">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-426">String</span></span>            |<span data-ttu-id="62d4d-427">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-427">String</span></span> |<span data-ttu-id="62d4d-428">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-428">String</span></span> |<span data-ttu-id="62d4d-429">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-429">String</span></span> |<span data-ttu-id="62d4d-430">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-430">String</span></span>|<span data-ttu-id="62d4d-431">String</span><span class="sxs-lookup"><span data-stu-id="62d4d-431">String</span></span>|<span data-ttu-id="62d4d-432">Boolean</span><span class="sxs-lookup"><span data-stu-id="62d4d-432">Boolean</span></span>   |<span data-ttu-id="62d4d-433">Boolean</span><span class="sxs-lookup"><span data-stu-id="62d4d-433">Boolean</span></span>     |<span data-ttu-id="62d4d-434">Boolean</span><span class="sxs-lookup"><span data-stu-id="62d4d-434">Boolean</span></span>|
|<span data-ttu-id="62d4d-435">**示例值**</span><span class="sxs-lookup"><span data-stu-id="62d4d-435">**Example value**</span></span>    |<span data-ttu-id="62d4d-436">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="62d4d-436">192.168.1.0</span></span>|<span data-ttu-id="62d4d-437">美国/西雅图/西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="62d4d-437">USA/Seattle/SEATTLE-SEA-1</span></span>| <span data-ttu-id="62d4d-438">个</span><span class="sxs-lookup"><span data-stu-id="62d4d-438">26</span></span>         | <span data-ttu-id="62d4d-439">西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="62d4d-439">SEATTLE-SEA-1</span></span>| <span data-ttu-id="62d4d-440">制定</span><span class="sxs-lookup"><span data-stu-id="62d4d-440">Contoso</span></span>     | <span data-ttu-id="62d4d-441">终止</span><span class="sxs-lookup"><span data-stu-id="62d4d-441">IT Termination</span></span>|<span data-ttu-id="62d4d-442">技术</span><span class="sxs-lookup"><span data-stu-id="62d4d-442">Engineering</span></span>       |<span data-ttu-id="62d4d-443">西雅图</span><span class="sxs-lookup"><span data-stu-id="62d4d-443">Seattle</span></span>|<span data-ttu-id="62d4d-444">98001</span><span class="sxs-lookup"><span data-stu-id="62d4d-444">98001</span></span>  |<span data-ttu-id="62d4d-445">我们</span><span class="sxs-lookup"><span data-stu-id="62d4d-445">US</span></span>     |<span data-ttu-id="62d4d-446">WA</span><span class="sxs-lookup"><span data-stu-id="62d4d-446">WA</span></span>    |<span data-ttu-id="62d4d-447">MSUS</span><span class="sxs-lookup"><span data-stu-id="62d4d-447">MSUS</span></span>  | <span data-ttu-id="62d4d-448">1</span><span class="sxs-lookup"><span data-stu-id="62d4d-448">1</span></span>        |<span data-ttu-id="62d4d-449">0</span><span class="sxs-lookup"><span data-stu-id="62d4d-449">0</span></span>           | <span data-ttu-id="62d4d-450">0</span><span class="sxs-lookup"><span data-stu-id="62d4d-450">0</span></span>|
|||||||||||||||||

<span data-ttu-id="62d4d-451">&dagger;此设置可用于反映子网是否位于企业网络内。</span><span class="sxs-lookup"><span data-stu-id="62d4d-451">&dagger; This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="62d4d-452">如果你决定，可以自定义其他用途的用法。</span><span class="sxs-lookup"><span data-stu-id="62d4d-452">You can customize usage for other purposes if you decide to.</span></span>

<span data-ttu-id="62d4d-453">&Dagger;此设置可用于反映网络是否使用 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="62d4d-453">&Dagger; This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="62d4d-454">如果你决定，可以自定义其他用途的用法。</span><span class="sxs-lookup"><span data-stu-id="62d4d-454">You can customize usage for other purposes if you decide to.</span></span>  

<span data-ttu-id="62d4d-455">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="62d4d-455">**Sample row:**</span></span>

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="62d4d-456">网络范围可用于表示 supernet （具有单个路由前缀的若干子网的组合）。</span><span class="sxs-lookup"><span data-stu-id="62d4d-456">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="62d4d-457">将检查所有新的生成上载，查找任何重叠区域。</span><span class="sxs-lookup"><span data-stu-id="62d4d-457">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="62d4d-458">如果你以前上载了一个生成文件，则应下载当前文件，然后重新上载它以标识任何重叠，并在再次上载之前修复该问题。</span><span class="sxs-lookup"><span data-stu-id="62d4d-458">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="62d4d-459">以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。</span><span class="sxs-lookup"><span data-stu-id="62d4d-459">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="62d4d-460">某些 VPN 实现不能准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-460">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="62d4d-461">建议将 VPN 子网添加到生成文件，而不是子网的一个条目时，将 VPN 子网中每个地址的单独条目添加为单独的32位网络。</span><span class="sxs-lookup"><span data-stu-id="62d4d-461">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="62d4d-462">每一行可以有相同的建筑物元数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-462">Each row can have the same building metadata.</span></span> <span data-ttu-id="62d4d-463">例如，对于 172.16.18.0/24，而不是一行，您应该有256行，每个地址对应于 172.16.18.0/32 和 172.16.18.255/32 之间（包括这两个地址）的一行。</span><span class="sxs-lookup"><span data-stu-id="62d4d-463">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="62d4d-464">"VPN" 列是可选的，默认值为0。</span><span class="sxs-lookup"><span data-stu-id="62d4d-464">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="62d4d-465">如果 VPN 列的值设置为1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="62d4d-465">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="62d4d-466">请谨慎使用，并且仅针对 VPN 子网，因为完全展开这些子网将对涉及生成数据的查询的查询时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="62d4d-466">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

### <a name="endpoint-data-file"></a><span data-ttu-id="62d4d-467">终结点数据文件</span><span class="sxs-lookup"><span data-stu-id="62d4d-467">Endpoint data file</span></span>

<span data-ttu-id="62d4d-468">CQD 使用终结点数据文件。</span><span class="sxs-lookup"><span data-stu-id="62d4d-468">CQD uses an Endpoint data file.</span></span> <span data-ttu-id="62d4d-469">在调用记录的第一个客户端终结点名称列或第二个客户端终结点名称列中使用列值来显示终结点的 "创建"、"模型" 或 "类型" 信息。</span><span class="sxs-lookup"><span data-stu-id="62d4d-469">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="62d4d-470">你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="62d4d-470">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="62d4d-471">文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="62d4d-471">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>
- <span data-ttu-id="62d4d-472">数据文件的内容不包含表格标题。</span><span class="sxs-lookup"><span data-stu-id="62d4d-472">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="62d4d-473">数据文件的第一行应为真实数据，而不是标题标签（如 "终结点"）。</span><span class="sxs-lookup"><span data-stu-id="62d4d-473">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>
- <span data-ttu-id="62d4d-474">所有七列仅使用字符串数据类型。</span><span class="sxs-lookup"><span data-stu-id="62d4d-474">All seven columns use the String data type only.</span></span> <span data-ttu-id="62d4d-475">允许的最大长度为64个字符。</span><span class="sxs-lookup"><span data-stu-id="62d4d-475">The maximum allowed length is 64 characters.</span></span>
- <span data-ttu-id="62d4d-476">数据字段可以为空，但仍须由制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="62d4d-476">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="62d4d-477">空数据字段只是分配一个空字符串值。</span><span class="sxs-lookup"><span data-stu-id="62d4d-477">An empty data field just assigns an empty String value.</span></span>
- <span data-ttu-id="62d4d-478">终结点必须是唯一的，否则上传将失败。</span><span class="sxs-lookup"><span data-stu-id="62d4d-478">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="62d4d-479">如果存在重复的行或两行使用同一终结点，则冲突将导致不正确的联接。</span><span class="sxs-lookup"><span data-stu-id="62d4d-479">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>
- <span data-ttu-id="62d4d-480">EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。</span><span class="sxs-lookup"><span data-stu-id="62d4d-480">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="62d4d-481">它们可以是空字符串或值，如 "IT 部门指定的2018膝上型计算机" 或 "资产标签 5678"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-481">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>
- <span data-ttu-id="62d4d-482">每行必须有七列，并且列必须按以下顺序排列：</span><span class="sxs-lookup"><span data-stu-id="62d4d-482">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="62d4d-483">**字段顺序：**</span><span class="sxs-lookup"><span data-stu-id="62d4d-483">**Field order:**</span></span>

<span data-ttu-id="62d4d-484">终结点、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="62d4d-484">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="62d4d-485">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="62d4d-485">**Sample row:**</span></span>

<span data-ttu-id="62d4d-486">"1409W3534，123制造商，Fabrikam 型号123，笔记本电脑，已指定2018笔记本电脑、资产标签5678、购买2018</span><span class="sxs-lookup"><span data-stu-id="62d4d-486">\`1409W3534, 123 manufacturer, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018</span></span>

## <a name="migrate-reports-from-previous-version-of-cqd"></a><span data-ttu-id="62d4d-487">从早期版本的 CQD 迁移报表</span><span class="sxs-lookup"><span data-stu-id="62d4d-487">Migrate reports from previous version of CQD</span></span>

<span data-ttu-id="62d4d-488">如果你为 Skype for Business 将报表或已上载的租户数据（映射）文件创建https://cqd.lync.com)到 CQD （并希望将它们迁移到团队https://cqd.teams.microsoft.com)的 CQD （），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="62d4d-488">If  you created reports or uploaded tenant data (mapping) files to CQD for Skype for Business (https://cqd.lync.com) and want to migrate them to CQD for Teams (https://cqd.teams.microsoft.com), here’s how:</span></span>

1.  <span data-ttu-id="62d4d-489">转到[https://cqd.lync.com/cqd/](https://cqd.lync.com/cqd/)并浏览到要导出的报表集。</span><span class="sxs-lookup"><span data-stu-id="62d4d-489">Go to [https://cqd.lync.com/cqd/](https://cqd.lync.com/cqd/) and browse to the report set you want to export.</span></span> 
2.  <span data-ttu-id="62d4d-490">将鼠标悬停在报表上，然后在 "..."菜单上，选择 "**导出报表树**"。</span><span class="sxs-lookup"><span data-stu-id="62d4d-490">Hover over the report and, on the "..." menu, choose **Export Report Tree**.</span></span> <span data-ttu-id="62d4d-491">保存导出文件。</span><span class="sxs-lookup"><span data-stu-id="62d4d-491">Save the export file.</span></span>
3.  <span data-ttu-id="62d4d-492">转到[https://cqd.teams.microsoft.com/cqd/](https://cqd.teams.microsoft.com/cqd/)并浏览到要导入报表的位置。</span><span class="sxs-lookup"><span data-stu-id="62d4d-492">Go to [https://cqd.teams.microsoft.com/cqd/](https://cqd.teams.microsoft.com/cqd/)  and browse to the location where you want to import the reports.</span></span>
4.  <span data-ttu-id="62d4d-493">从左侧的链接中，单击 "**导入**"，然后选择导出的文件。</span><span class="sxs-lookup"><span data-stu-id="62d4d-493">From the links on the left, click **Import** and select the exported file.</span></span> 
5.  <span data-ttu-id="62d4d-494">导入报告后，您将看到以下消息： "报告导入成功。</span><span class="sxs-lookup"><span data-stu-id="62d4d-494">After the reports are imported, you'll see this message: "Report import was successful.</span></span> <span data-ttu-id="62d4d-495">新报表已添加到报表集末尾。 "</span><span class="sxs-lookup"><span data-stu-id="62d4d-495">The new report has been added at the end of report set."</span></span> 


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="62d4d-496">创建自定义详细报告</span><span class="sxs-lookup"><span data-stu-id="62d4d-496">Create custom detailed reports</span></span>

<span data-ttu-id="62d4d-497">如果您想要创建一个特定报表，使其关注所提供的详细报表所提供的数据的维度，请创建一个自定义报表。</span><span class="sxs-lookup"><span data-stu-id="62d4d-497">If you find you want to create a specific report that focuses on a dimension of the data in a way the provided detailed reports do not, create a custom report.</span></span>

<span data-ttu-id="62d4d-498">在 "登录\(**摘要报告**"\)屏幕上显示的屏幕顶部显示的报告下拉列表中，选择 "**详细报告**"，然后**单击**报表的 "操作" 菜单中的 "编辑"，以查看查询编辑器。</span><span class="sxs-lookup"><span data-stu-id="62d4d-498">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New** d Click "Edit" in the action menu of a report to see the Query Editor.</span></span> <span data-ttu-id="62d4d-499">每个报告都可以通过对多维数据集进行查询得到。</span><span class="sxs-lookup"><span data-stu-id="62d4d-499">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="62d4d-500">报告是其查询返回的数据的可视化形式。</span><span class="sxs-lookup"><span data-stu-id="62d4d-500">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="62d4d-501">查询编辑器可帮助您编辑报表的这些查询和显示选项。</span><span class="sxs-lookup"><span data-stu-id="62d4d-501">The Query Editor helps you edit these queries and the display options of the report.</span></span> <span data-ttu-id="62d4d-502">为新报表打开 "查询编辑器" 时，你会看到类似于以下屏幕截图的内容：</span><span class="sxs-lookup"><span data-stu-id="62d4d-502">When you open the Query Editor for a new report, you see something similar to this screenshot:</span></span>

![编辑新报表](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. <span data-ttu-id="62d4d-504">左侧窗格中选择了维度、度量和筛选器。</span><span class="sxs-lookup"><span data-stu-id="62d4d-504">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="62d4d-505">单击标题旁边的 "加号" 按钮以打开对话框，您可以在其中添加维度、测量或筛选，并选中相应的框。</span><span class="sxs-lookup"><span data-stu-id="62d4d-505">Click the "plus" button next to a heading to open the dialog where you can add a  dimension, measure, or filter and check the corresponding box.</span></span> <span data-ttu-id="62d4d-506">如果您编辑现有报表，则可以取消选中现有值以将其删除。</span><span class="sxs-lookup"><span data-stu-id="62d4d-506">If you edit an existing report, you can uncheck existing values to remove them.</span></span> <span data-ttu-id="62d4d-507">有关详细信息，请参阅[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="62d4d-507">For details, see [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
2. <span data-ttu-id="62d4d-508">顶部显示了图表自定义选项。</span><span class="sxs-lookup"><span data-stu-id="62d4d-508">Options for chart customization are displayed at the top.</span></span>
3. <span data-ttu-id="62d4d-509">报表的预览在查询编辑器中可用。</span><span class="sxs-lookup"><span data-stu-id="62d4d-509">A preview of the report is available in the Query Editor.</span></span>
4. <span data-ttu-id="62d4d-510">可以使用底部的 "编辑" 框创建详细的报表名称和说明。</span><span class="sxs-lookup"><span data-stu-id="62d4d-510">A detailed report name and description can be created with the edit box at the bottom.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="62d4d-511">常见问题</span><span class="sxs-lookup"><span data-stu-id="62d4d-511">Frequently Asked Questions</span></span>

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a><span data-ttu-id="62d4d-512">为什么 CQD v2 报表数据看起来与 CQD v3 报表数据不同？</span><span class="sxs-lookup"><span data-stu-id="62d4d-512">Why does my CQD v2 report data look different than the CQD v3 report data?</span></span> 

<span data-ttu-id="62d4d-513">如果你看到 CQD v2 和 v3 之间的数据差异，请确保在 "苹果" 和 "窄" 级别（而不是聚合级别）上执行数据比较或验证。</span><span class="sxs-lookup"><span data-stu-id="62d4d-513">If you see data differences between CQD v2 and v3, make sure that data comparison or validation is done on an 'apples-to-apples'  and narrow level, not an aggregated level.</span></span> <span data-ttu-id="62d4d-514">例如，如果你筛选 MSIT "建筑物 30" WiFi 团队桌面客户端数据的两个报表，则 v2 和 v3 的低质量百分比应该相同。</span><span class="sxs-lookup"><span data-stu-id="62d4d-514">For example, if you filter both reports for MSIT ‘Building 30' WiFi Teams Desktop client data, the Percentage of Poor Quality should be the same between v2 and v3.</span></span>

<span data-ttu-id="62d4d-515">CQD v2 和 CQD v3 具有不同的总数，因为 CQD v3 具有 CQD v2 中不存在的新方案。</span><span class="sxs-lookup"><span data-stu-id="62d4d-515">CQD v2 and CQD v3 have different total counts since CQD v3 has new scenarios not present in CQD v2.</span></span> <span data-ttu-id="62d4d-516">摘要总数或聚合的所有不带筛选器的数字均应不同。</span><span class="sxs-lookup"><span data-stu-id="62d4d-516">Summary Total or Aggregated all-up numbers with no filters are expected to be different.</span></span>  

<span data-ttu-id="62d4d-517">如果使用方案包括 Skype for Business Server 2019 调用，CQD v3 数据包括 Skype 机器人呼叫（自动助理、CVI、虚拟桌面界面）、实时事件和 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="62d4d-517">If the usage scenario includes Skype for Business Server 2019 calls, CQD v3 data includes Skype Bot calls (auto attendant, CVI, Virtual Desktop Interface), Live Events, and PSTN calls.</span></span> <span data-ttu-id="62d4d-518">CQD v2 不使用此数据。</span><span class="sxs-lookup"><span data-stu-id="62d4d-518">CQD v2 does not use this data.</span></span> <span data-ttu-id="62d4d-519">（CQD v3 需要配置了 cloud data connector 的 Skype for business Server 2019。）</span><span class="sxs-lookup"><span data-stu-id="62d4d-519">(CQD v3 requires Skype for Business Server 2019 with cloud data connector configured.)</span></span>

<span data-ttu-id="62d4d-520">例如，如果你在 CQD v2 摘要报告中看到200000音频5000流，但在5500失败时看到300000音频流是不寻常的（区别可能是由于 Skype for business 服务器2019通话、CVI 呼叫、PSTN 呼叫等）在 CQD v3 摘要报告中。</span><span class="sxs-lookup"><span data-stu-id="62d4d-520">For instance, if you see 200,000 audio streams with 5000 failures in a CQD v2 Summary Report it would not be unusual to see 300,000 audio streams with 5500 failures (the difference can be due to Skype for Business Server 2019 calls, CVI calls, PSTN calls, and so on) in a CQD v3 Summary report.</span></span>

<span data-ttu-id="62d4d-521">为消除意外的差异，请查看整个数据的多个细目。</span><span class="sxs-lookup"><span data-stu-id="62d4d-521">To disambiguate unexpected differences, look at more than one breakdown of the overall data.</span></span> <span data-ttu-id="62d4d-522">通过一个或多个以下参数对数据进行筛选：</span><span class="sxs-lookup"><span data-stu-id="62d4d-522">Filter the data by one or more of the following parameters:</span></span>

- <span data-ttu-id="62d4d-523">User Agent Category Pair</span><span class="sxs-lookup"><span data-stu-id="62d4d-523">User Agent Category Pair</span></span>
- <span data-ttu-id="62d4d-524">第一产品</span><span class="sxs-lookup"><span data-stu-id="62d4d-524">First Product</span></span>
- <span data-ttu-id="62d4d-525">第二产品</span><span class="sxs-lookup"><span data-stu-id="62d4d-525">Second Product</span></span>

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a><span data-ttu-id="62d4d-526">CQD v2 和 CQD v3 之间的其他预期差异</span><span class="sxs-lookup"><span data-stu-id="62d4d-526">Other expected differences between CQD v2 and CQD v3</span></span>

<span data-ttu-id="62d4d-527">团队中有多种质量和可靠性改进，而不是 Skype for business Online：</span><span class="sxs-lookup"><span data-stu-id="62d4d-527">There are several Quality and Reliability improvements in Teams but not Skype for Business Online:</span></span>

- <span data-ttu-id="62d4d-528">自动重新连接</span><span class="sxs-lookup"><span data-stu-id="62d4d-528">Auto-reconnect</span></span>
- <span data-ttu-id="62d4d-529">快速漫游</span><span class="sxs-lookup"><span data-stu-id="62d4d-529">Fast roaming</span></span>
- <span data-ttu-id="62d4d-530">改进的黑白管理</span><span class="sxs-lookup"><span data-stu-id="62d4d-530">Improved BW management</span></span>

<span data-ttu-id="62d4d-531">比较这两个服务的数据时：</span><span class="sxs-lookup"><span data-stu-id="62d4d-531">When you compare data for these two services:</span></span>

- <span data-ttu-id="62d4d-532">选择具有紧密焦点的方案，如企业有线连接、Windows 桌面或单个区域或建筑物。</span><span class="sxs-lookup"><span data-stu-id="62d4d-532">Pick a scenario with a tight focus, such as corporate wired connections, Windows Desktops, or a single region or building.</span></span>
- <span data-ttu-id="62d4d-533">检查团队 MR、TR 或 MP IP 范围。</span><span class="sxs-lookup"><span data-stu-id="62d4d-533">Check the Teams MR, TR, or MP IP ranges.</span></span> <span data-ttu-id="62d4d-534">团队范围比 Skype for business Online 更新，并且可能导致与防火墙的连接问题</span><span class="sxs-lookup"><span data-stu-id="62d4d-534">The Teams ranges are newer than Skype for Business Online, and that can cause connectivity issues involving firewalls</span></span>
- <span data-ttu-id="62d4d-535">不要比较汇总或顶级数字。</span><span class="sxs-lookup"><span data-stu-id="62d4d-535">Don't compare summary or top-level numbers.</span></span> <span data-ttu-id="62d4d-536">这些比较将使你能够将企业有线连接上的 Skype for business Online 通话的大型通话量与 LTE 或专用网络上的一小大量团队通话进行比较。</span><span class="sxs-lookup"><span data-stu-id="62d4d-536">These comparisons will lead you to compare a large call volume of Skype for Business Online calls on a corporate wired connection to a small volume of Teams calls on an LTE or private network.</span></span>
- <span data-ttu-id="62d4d-537">注意位置偏向和人口差异：有许多比较过于不同的比较非常有用：</span><span class="sxs-lookup"><span data-stu-id="62d4d-537">Beware of location bias and population differences: There are many comparisons that are too dissimilar to be useful:</span></span>
  - <span data-ttu-id="62d4d-538">NOAM： APAC</span><span class="sxs-lookup"><span data-stu-id="62d4d-538">NOAM : APAC</span></span>
  - <span data-ttu-id="62d4d-539">纽约州： Goa</span><span class="sxs-lookup"><span data-stu-id="62d4d-539">NY : Goa</span></span>
  - <span data-ttu-id="62d4d-540">有线 : wifi</span><span class="sxs-lookup"><span data-stu-id="62d4d-540">Wired : wifi</span></span>
  - <span data-ttu-id="62d4d-541">公司网络：家庭网络</span><span class="sxs-lookup"><span data-stu-id="62d4d-541">Corporate network : home network</span></span>
  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="62d4d-542">为什么我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="62d4d-542">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="62d4d-543">这些管理员角色可以访问 CQD，但不能查看 EUII （最终用户身份信息）：</span><span class="sxs-lookup"><span data-stu-id="62d4d-543">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="62d4d-544">Office 365 报表阅读器</span><span class="sxs-lookup"><span data-stu-id="62d4d-544">Office 365 Reports Reader</span></span>
- <span data-ttu-id="62d4d-545">团队沟通支持专家</span><span class="sxs-lookup"><span data-stu-id="62d4d-545">Teams Communications Support Specialist</span></span>

<span data-ttu-id="62d4d-546">若要了解有关可访问 CQD 的角色的详细信息-包括 EUII-读取[分配角色以访问 CQD](quality-of-experience-review-guide.md#assign-roles-for-accessing-cqd)。</span><span class="sxs-lookup"><span data-stu-id="62d4d-546">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](quality-of-experience-review-guide.md#assign-roles-for-accessing-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="62d4d-547">为什么我仅当我筛选了团队时，我在 CQD 中看到 Skype for Business 信息？</span><span class="sxs-lookup"><span data-stu-id="62d4d-547">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="62d4d-548">当仅在 CQD 报表（isTeams = 1）中筛选团队时，将筛选*第一个终结点*为团队的所有调用。</span><span class="sxs-lookup"><span data-stu-id="62d4d-548">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="62d4d-549">如果*第二个终结点*是 Skype for business，则该信息将显示在您的 CQD 报告中。</span><span class="sxs-lookup"><span data-stu-id="62d4d-549">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

## <a name="related-topics"></a><span data-ttu-id="62d4d-550">相关主题</span><span class="sxs-lookup"><span data-stu-id="62d4d-550">Related topics</span></span>

[<span data-ttu-id="62d4d-551">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="62d4d-551">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="62d4d-552">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="62d4d-552">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="62d4d-553">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="62d4d-553">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="62d4d-554">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="62d4d-554">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="62d4d-555">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="62d4d-555">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
