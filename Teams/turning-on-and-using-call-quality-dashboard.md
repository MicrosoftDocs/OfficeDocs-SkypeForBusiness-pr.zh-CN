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
- Teams_ITAdmin_Help
- M365-collaboration
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
ms.openlocfilehash: 25f141f30691700414c3a24e705c7d8b490fd265
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328349"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="88835-103">打开和使用 Microsoft 团队和 Skype for business Online 的通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="88835-103">Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="88835-104">了解如何配置 Office 365 组织以使用呼叫质量仪表板来监控通话质量。</span><span class="sxs-lookup"><span data-stu-id="88835-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="88835-105">通话质量仪表板（CQD）可深入了解使用 Microsoft 团队和 Skype for business Online 服务进行的通话的质量。</span><span class="sxs-lookup"><span data-stu-id="88835-105">Call Quality Dashboard (CQD) provides insight into the quality of calls made using Microsoft Teams and Skype for Business Online services.</span></span> <span data-ttu-id="88835-106">本主题介绍了开始收集可用于解决通话质量问题的数据的步骤。</span><span class="sxs-lookup"><span data-stu-id="88835-106">This topic describes the steps to start collecting data you can use to troubleshoot call quality issues.</span></span>

<span data-ttu-id="88835-107">目前，CQD 版本3和 CQD 版本2都可供使用。</span><span class="sxs-lookup"><span data-stu-id="88835-107">Currently, CQD version 3 and CQD version 2 are both available for use.</span></span> <span data-ttu-id="88835-108">CQD v3 可在<span>https://cqd.teams.microsoft.com</span>。</span><span class="sxs-lookup"><span data-stu-id="88835-108">CQD v3 is available at <span>https://cqd.teams.microsoft.com</span>.</span></span> <span data-ttu-id="88835-109">用您的 Microsoft 团队管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="88835-109">Log in with your Microsoft Teams administrator credentials.</span></span>

## <a name="latest-changes-and-updates"></a><span data-ttu-id="88835-110">最新更改和更新</span><span class="sxs-lookup"><span data-stu-id="88835-110">Latest changes and updates</span></span>

<span data-ttu-id="88835-111">CQD 版本3提供接近实时的 CQD 仪表板（延迟接近30分钟），并使用最终用户可识别信息（EUII），从而使管理员能够放大到用户级别。</span><span class="sxs-lookup"><span data-stu-id="88835-111">CQD version 3 delivers a near real-time CQD dashboard (latency close to 30 minutes), and uses End User Identifiable Information (EUII), giving admins the ability to zoom in to the user level.</span></span> <span data-ttu-id="88835-112">此外，还可通过报表交互来支持新方案，例如：</span><span class="sxs-lookup"><span data-stu-id="88835-112">There is also and report interactivity to support new scenarios such as:</span></span>

- <span data-ttu-id="88835-113">按地区呼叫质量：</span><span class="sxs-lookup"><span data-stu-id="88835-113">Call Quality by Region:</span></span>
  - <span data-ttu-id="88835-114">按区域日期</span><span class="sxs-lookup"><span data-stu-id="88835-114">date-by-region</span></span>
  - <span data-ttu-id="88835-115">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="88835-115">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="88835-116">特定位置</span><span class="sxs-lookup"><span data-stu-id="88835-116">specific locations</span></span>
  - <span data-ttu-id="88835-117">特定子网</span><span class="sxs-lookup"><span data-stu-id="88835-117">specific subnet</span></span>
  - <span data-ttu-id="88835-118">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="88835-118">impacted user or users</span></span>

- <span data-ttu-id="88835-119">按地区呼叫可靠性/失败：</span><span class="sxs-lookup"><span data-stu-id="88835-119">Call Reliability/Failure by Region:</span></span>
  - <span data-ttu-id="88835-120">按区域日期</span><span class="sxs-lookup"><span data-stu-id="88835-120">date-by-region</span></span>
  - <span data-ttu-id="88835-121">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="88835-121">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="88835-122">特定位置</span><span class="sxs-lookup"><span data-stu-id="88835-122">specific locations</span></span>
  - <span data-ttu-id="88835-123">特定子网</span><span class="sxs-lookup"><span data-stu-id="88835-123">specific subnet</span></span>
  - <span data-ttu-id="88835-124">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="88835-124">impacted user or users</span></span>

- <span data-ttu-id="88835-125">按区域对我的呼叫（RMC）进行评级：从按区域聚合到特定位置的特定位置到提供低 RMC 等级的用户。</span><span class="sxs-lookup"><span data-stu-id="88835-125">Rate My Call (RMC) by Region: from month-by-region aggregated down to specific locations to users who provide low RMC ratings.</span></span> <span data-ttu-id="88835-126">CQD v3 还包括逐字反馈。</span><span class="sxs-lookup"><span data-stu-id="88835-126">CQD v3 also includes verbatim feedback.</span></span>
- <span data-ttu-id="88835-127">帮助者：可用于 P2P 呼叫或会议的特定用户或所有参与者和通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="88835-127">Helpdesk: available for a specific user on P2P calls or Meetings, or for all participants and call details.</span></span> <span data-ttu-id="88835-128">帮助识别基于网络位置、设备或固件的可能系统问题。</span><span class="sxs-lookup"><span data-stu-id="88835-128">Helps identify possible system issues based on network location, devices, or firmware.</span></span>  
- <span data-ttu-id="88835-129">客户端版本：查看每个客户端版本的会话和用户计数，或向下钻取以查看每个客户端版本的用户名。</span><span class="sxs-lookup"><span data-stu-id="88835-129">Client Versions: View the Session and Users counts for each Client Version, or drill down to User names for each client version.</span></span> <span data-ttu-id="88835-130">产品和客户端类型的预生成筛选器帮助将版本集中到特定客户端。</span><span class="sxs-lookup"><span data-stu-id="88835-130">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>
- <span data-ttu-id="88835-131">终结点：显示映射到电脑/Mac 的 "生成/模型" 的计算机终结点。</span><span class="sxs-lookup"><span data-stu-id="88835-131">Endpoints: Shows Machine Endpoints mapped to Make/Model of the PC/Mac.</span></span> <span data-ttu-id="88835-132">按 "生成/模型" 显示聚合质量。</span><span class="sxs-lookup"><span data-stu-id="88835-132">Shows aggregated quality by Make/Model.</span></span> <span data-ttu-id="88835-133">映射数据的上载类似于生成数据。</span><span class="sxs-lookup"><span data-stu-id="88835-133">Mapping data is uploaded similar to Building data.</span></span>

<span data-ttu-id="88835-134">如果 EUII 访问不可用，则版本3还提供 RBAC 支持。</span><span class="sxs-lookup"><span data-stu-id="88835-134">Version 3 also provides RBAC support, in case EUII access is not available.</span></span>  

<span data-ttu-id="88835-135">管理员可通过 CQD 版本3管理 Skype for business Server 2019 （不仅仅是 Skype for business Online 和 Microsoft 团队）。</span><span class="sxs-lookup"><span data-stu-id="88835-135">An admin can manage Skype for Business Server 2019 (not just Skype for Business Online and Microsoft Teams) through CQD version 3.</span></span> <span data-ttu-id="88835-136">这需要混合实现和使用 "调用数据" 连接器。</span><span class="sxs-lookup"><span data-stu-id="88835-136">This requires a hybrid implementation and the use of Call Data Connector.</span></span> <span data-ttu-id="88835-137">有关详细信息，请参阅[计划通话数据连接器](/SkypeForBusiness/hybrid/plan-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="88835-137">See [Plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) for more information.</span></span>

<span data-ttu-id="88835-138">已添加 CQD 版本2：</span><span class="sxs-lookup"><span data-stu-id="88835-138">CQD version 2 added:</span></span>

- <span data-ttu-id="88835-139">Microsoft 团队和 Skype for business Online 的数据</span><span class="sxs-lookup"><span data-stu-id="88835-139">Data for Microsoft Teams and Skype for Business Online</span></span>
- <span data-ttu-id="88835-140">摘要报告包括一个用于选择所有数据、Microsoft 团队数据或 Skype for Business Online 数据的产品筛选器</span><span class="sxs-lookup"><span data-stu-id="88835-140">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data</span></span>
- <span data-ttu-id="88835-141">更新了视频和 VBSS 流质量分类逻辑。</span><span class="sxs-lookup"><span data-stu-id="88835-141">Updated Video and VBSS stream quality classification logic.</span></span> <span data-ttu-id="88835-142">请参阅用于分类器定义的[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="88835-142">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the classifier definitions.</span></span>

<span data-ttu-id="88835-143">有关[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)的列表，请参阅本文。</span><span class="sxs-lookup"><span data-stu-id="88835-143">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="88835-144">若要查看有关仪表板的更新和更改的信息，请单击 "**好消息**" 中的链接！</span><span class="sxs-lookup"><span data-stu-id="88835-144">To see information about updates and changes to the dashboard,  click the link in the **Good news!**</span></span> <span data-ttu-id="88835-145">在仪表板上显示时横幅。</span><span class="sxs-lookup"><span data-stu-id="88835-145">banner when it displays on the dashboard.</span></span>

<span data-ttu-id="88835-146">CQD 版本1已提供 Skype for Business Server 2015 管理员以下功能：</span><span class="sxs-lookup"><span data-stu-id="88835-146">CQD version 1 provided Skype for Business Server 2015 admins the following features:</span></span>

- <span data-ttu-id="88835-147">访问缓存的报表数据以快速访问</span><span class="sxs-lookup"><span data-stu-id="88835-147">Access to cached report data for fast access</span></span>
- <span data-ttu-id="88835-148">指向用于共享和发布信息的报表页面的深层链接</span><span class="sxs-lookup"><span data-stu-id="88835-148">Deep links to report pages for sharing and publishing information</span></span>
- <span data-ttu-id="88835-149">简化的报表编辑和创建以及报表说明的可编辑元数据</span><span class="sxs-lookup"><span data-stu-id="88835-149">Streamlined report editing and creation, and editable metadata for report descriptions</span></span>
- <span data-ttu-id="88835-150">为在自定义仪表板中使用而提供对多维数据集数据的编程访问的 Web Api</span><span class="sxs-lookup"><span data-stu-id="88835-150">Web APIs that give programmatic access to the cube data for use in custom dashboards</span></span>

## <a name="cqd-near-real-time-nrt-data"></a><span data-ttu-id="88835-151">CQD 近实时（NRT）数据</span><span class="sxs-lookup"><span data-stu-id="88835-151">CQD Near-Real-Time (NRT) Data</span></span>

<span data-ttu-id="88835-152">CQD v3 利用近乎实时的数据馈送。</span><span class="sxs-lookup"><span data-stu-id="88835-152">CQD v3 utilizes a near-real-time data feed.</span></span> <span data-ttu-id="88835-153">通话记录在通话结束后的30分钟内将在 CQD 门户中可用。</span><span class="sxs-lookup"><span data-stu-id="88835-153">Call Records are available at the CQD portal within 30 minutes of the end of the call.</span></span> <span data-ttu-id="88835-154">从 NRT 管道中调用记录仅在从数据集内删除几个月后才可用。</span><span class="sxs-lookup"><span data-stu-id="88835-154">Call Records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> <span data-ttu-id="88835-155">CQD v3 将当前 v2 管道中的数据与 v3 管道中的 NRT 数据合并。</span><span class="sxs-lookup"><span data-stu-id="88835-155">CQD v3 merges data from the current v2 pipeline with NRT data from the v3 pipeline.</span></span> <span data-ttu-id="88835-156">来自存档周期的数据的 v2 和 v3 门户查询将产生相同的结果。</span><span class="sxs-lookup"><span data-stu-id="88835-156">Queries on the v2 and v3 portals for the data from the Archival period produce the same results.</span></span> <span data-ttu-id="88835-157">NRT 数据的 V2 和 v3 数据查询和 NRT Data + PII 期间将有所不同。</span><span class="sxs-lookup"><span data-stu-id="88835-157">V2 and v3 data queries for the NRT Data and NRT Data + PII periods will be different.</span></span>

### <a name="piieuii-data"></a><span data-ttu-id="88835-158">PII/EUII 数据</span><span class="sxs-lookup"><span data-stu-id="88835-158">PII/EUII Data</span></span>

<span data-ttu-id="88835-159">PII 或 EUII 数据仅来自 v3 管道。</span><span class="sxs-lookup"><span data-stu-id="88835-159">PII or EUII data only comes from the v3 pipeline.</span></span> <span data-ttu-id="88835-160">由于合规性原因，PII/EUII 数据仅保留30天。</span><span class="sxs-lookup"><span data-stu-id="88835-160">Due to compliance reasons, PII/EUII data is only kept for 30 days.</span></span> <span data-ttu-id="88835-161">由于 NRT 数据超过30天的标记，将清除 PII/EUII 字段，从而导致 PII NRT 数据。</span><span class="sxs-lookup"><span data-stu-id="88835-161">As NRT data crosses the 30-day mark, the PII/EUII fields are cleared out, resulting in PII-free NRT data.</span></span> <span data-ttu-id="88835-162">PII/EUII 字段是：</span><span class="sxs-lookup"><span data-stu-id="88835-162">The PII/EUII fields are:</span></span>

- <span data-ttu-id="88835-163">完整 IP 地址</span><span class="sxs-lookup"><span data-stu-id="88835-163">Full IP address</span></span>
- <span data-ttu-id="88835-164">媒体访问控制（MAC）地址</span><span class="sxs-lookup"><span data-stu-id="88835-164">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="88835-165">基本服务集标识符（BSSID）</span><span class="sxs-lookup"><span data-stu-id="88835-165">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="88835-166">会话初始协议（SIP） URI （仅 Skype for business）</span><span class="sxs-lookup"><span data-stu-id="88835-166">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="88835-167">用户主体名称 (UPN)</span><span class="sxs-lookup"><span data-stu-id="88835-167">User Principal Name (UPN)</span></span>
- <span data-ttu-id="88835-168">计算机终结点名称</span><span class="sxs-lookup"><span data-stu-id="88835-168">Machine Endpoint Name</span></span>
- <span data-ttu-id="88835-169">用户逐字反馈</span><span class="sxs-lookup"><span data-stu-id="88835-169">User Verbatim Feedback</span></span>
- <span data-ttu-id="88835-170">对象 ID （终结点用户的 Active Directory 对象 ID）</span><span class="sxs-lookup"><span data-stu-id="88835-170">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="date-controls"></a><span data-ttu-id="88835-171">日期控件</span><span class="sxs-lookup"><span data-stu-id="88835-171">Date controls</span></span>

<span data-ttu-id="88835-172">CQD v3 将添加以下新的滚动趋势类型：</span><span class="sxs-lookup"><span data-stu-id="88835-172">CQD v3 adds the following new Rolling Trend types:</span></span>

- <span data-ttu-id="88835-173">5天</span><span class="sxs-lookup"><span data-stu-id="88835-173">5-day</span></span>
- <span data-ttu-id="88835-174">7天</span><span class="sxs-lookup"><span data-stu-id="88835-174">7-day</span></span>
- <span data-ttu-id="88835-175">30天</span><span class="sxs-lookup"><span data-stu-id="88835-175">30-day</span></span>
- <span data-ttu-id="88835-176">60-day</span><span class="sxs-lookup"><span data-stu-id="88835-176">60-day</span></span>
- <span data-ttu-id="88835-177">90-day</span><span class="sxs-lookup"><span data-stu-id="88835-177">90-day</span></span>

<span data-ttu-id="88835-178">URL 日期参数现在可接受 "天" 字段。</span><span class="sxs-lookup"><span data-stu-id="88835-178">The URL Date parameter can now accept a Day field.</span></span> <span data-ttu-id="88835-179">"滚动日期" 报告将 "YYYY-MM-DD 格式" 中指定的日期用作趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="88835-179">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span>  <span data-ttu-id="88835-180">URL 日期参数 "00" 表示 "今日"。</span><span class="sxs-lookup"><span data-stu-id="88835-180">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="88835-181">URL</span><span class="sxs-lookup"><span data-stu-id="88835-181">URL</span></span>| <span data-ttu-id="88835-182">滚动日趋势的结束日期</span><span class="sxs-lookup"><span data-stu-id="88835-182">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="88835-183"><span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="88835-183"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="88835-184">2019年2月的当前日期</span><span class="sxs-lookup"><span data-stu-id="88835-184">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="88835-185"><span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="88835-185"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="88835-186">2019年2月15日</span><span class="sxs-lookup"><span data-stu-id="88835-186">Feb 15, 2019</span></span>|
|<span data-ttu-id="88835-187"><span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/00/</span></span><span class="sxs-lookup"><span data-stu-id="88835-187"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="88835-188">当前日期</span><span class="sxs-lookup"><span data-stu-id="88835-188">Current Day</span></span>|
|||

<span data-ttu-id="88835-189">默认情况下，该月的当前日期用作滚动日期趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="88835-189">By default the current day of the month is used as the last day of the Rolling Day Trend.</span></span>

### <a name="drill-thru-functionality"></a><span data-ttu-id="88835-190">钻取功能</span><span class="sxs-lookup"><span data-stu-id="88835-190">Drill Thru Functionality</span></span>

<span data-ttu-id="88835-191">CQD v3 支持使用 SPD 报表中的钻取或向下钻取字段。</span><span class="sxs-lookup"><span data-stu-id="88835-191">CQD v3 supports the use of drill through or drill-down fields in SPD reports.</span></span> <span data-ttu-id="88835-192">如果选择这些维度字段，报表将自动打开不同的 "报表" 选项卡，并筛选所选值。</span><span class="sxs-lookup"><span data-stu-id="88835-192">If these dimension fields are selected,  the report automatically opens a different report tab and filters on the selected value.</span></span> <span data-ttu-id="88835-193">将鼠标悬停在其上方时，具有分配的钻取筛选器的字段将由不同的光标图标（指针）进行区分。</span><span class="sxs-lookup"><span data-stu-id="88835-193">Fields with an assigned drill through filter are distinguished by a different cursor icon (the pointer) when you hover over them.</span></span>

<span data-ttu-id="88835-194">选中 "钻取" 字段时，仪表板将自动导航到新的指定选项卡，并应用具有所选值的筛选器。</span><span class="sxs-lookup"><span data-stu-id="88835-194">When a drill through field is selected, the Dashboard automatically navigates to the new, specified tab and applies a filter with the selected value.</span></span> <span data-ttu-id="88835-195">如果该选项卡具有自己的钻取字段，并且选择了一个，则以前的钻取筛选器和新的钻取筛选器以及新的钻取。</span><span class="sxs-lookup"><span data-stu-id="88835-195">If that tab has its own drill through fields and one is selected, the previous drill through filters and the new one all propagate forward.</span></span> <span data-ttu-id="88835-196">这允许你构建可逐渐缩小结果数据集的报表。</span><span class="sxs-lookup"><span data-stu-id="88835-196">This allows you to build a report that progressively narrows the resulting data set.</span></span>

<span data-ttu-id="88835-197">例如，在通话质量的钻取报表中，用户可以单击想要 "钻取" 的日期，这将导致 "位置" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="88835-197">For example, in a Call quality drill-through report, a user can click the date they would like to 'drill-through', which leads to the Location tab.</span></span>

    ![Screenshot: shows the drill thru report](media/CQD-drill-thru-report.png)

<span data-ttu-id="88835-198">可以从 "位置" 选项卡添加多个日期，例如将2019-09-22 添加到日期：2019-09-24：</span><span class="sxs-lookup"><span data-stu-id="88835-198">You can add multiple dates from the location tab, such as adding 2019-09-22 to Date: 2019-09-24:</span></span> 

    ![Screenshot: add a date to the drill thru report](media/CQD-add-date.png)

> [!NOTE]
> <span data-ttu-id="88835-199">不要直接跳转到最后一个选项卡。没有从以前的钻取中选择的筛选器，结果将太大，无法在表格上显示。</span><span class="sxs-lookup"><span data-stu-id="88835-199">Don't jump directly to the last tab. Without filters selected from a previous drill-through the results would be too large to show on a table.</span></span>

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="88835-200">激活 Microsoft 通话质量仪表板（CQD）摘要报告</span><span class="sxs-lookup"><span data-stu-id="88835-200">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="88835-201">在开始使用 CQD 之前，请为您的 Office 365 组织激活它，如下所示：</span><span class="sxs-lookup"><span data-stu-id="88835-201">Before you can start using CQD, activate it for your Office 365 organization as follows:</span></span>

<span data-ttu-id="88835-202">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="88835-202">![An icon that shows the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="88835-203">使用 Microsoft 团队服务管理员帐户登录到你的 Office 365 组织，然后选择 "**管理员**" 磁贴以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="88835-203">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="88835-204">在左窗格中的 "**管理中心**" 下，选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。</span><span class="sxs-lookup"><span data-stu-id="88835-204">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
3. <span data-ttu-id="88835-205">在 "Microsoft 团队管理中心" 中，在左窗格中选择 "**呼叫质量" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="88835-205">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
4. <span data-ttu-id="88835-206">\(在打开 https://<span>cqd.teams.microsoft.com<span/>\)的页面上，单击 "**登录**"，然后输入全局管理员帐户或 microsoft 团队服务管理员帐户信息。</span><span class="sxs-lookup"><span data-stu-id="88835-206">On the page that opens \(https://<span>cqd.teams.microsoft.com<span/>\), click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span>

    ![屏幕截图：显示凭据提示](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="88835-208">登录后，一旦激活，CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="88835-208">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="88835-209">可能需要一个或多个小时才能处理足够的数据，以在报表中显示有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="88835-209">It may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="88835-210">![](media/sfb-logo-30x30.png) **使用 skype for business 旧版门户**的 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="88835-210">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="88835-211">使用管理员帐户登录到您的 Office 365 组织，然后选择 "**管理员**" 磁贴以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="88835-211">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="88835-212">在左窗格中的 "**管理中心**" 下，选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。</span><span class="sxs-lookup"><span data-stu-id="88835-212">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
3. <span data-ttu-id="88835-213">在 Microsoft 团队管理中心中，在左窗格中选择 "**旧版门户**"，选择 "**工具**"，然后选择 " **Skype for Business Online 呼叫质量" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="88835-213">In the Microsoft Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

     ![屏幕截图：选择 "呼叫质量" 仪表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="88835-215">在打开的页面上，用全局管理员帐户登录，然后在出现提示时提供帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="88835-215">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="88835-216">登录后，"呼叫质量" 仪表板将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="88835-216">After you sign in, once activated, the Call Quality Dashboard will begin collecting and processing data.</span></span>

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="88835-217">Microsoft 团队和 Skype for business Online 的通话质量仪表板的功能</span><span class="sxs-lookup"><span data-stu-id="88835-217">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="88835-218"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="88835-218"></span></span>

<!-- Siunies, this isn't very clear, it doesn't call out v1 and v2. unsure how to elaborate for v3, please comment -->
<span data-ttu-id="88835-219">CQD 摘要报告提供为详细报告规划的功能的子集。</span><span class="sxs-lookup"><span data-stu-id="88835-219">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="88835-220">此处概括介绍了版本之间的差异：</span><span class="sxs-lookup"><span data-stu-id="88835-220">The differences between the editions are summarized here:</span></span>
  
|<span data-ttu-id="88835-221">功能</span><span class="sxs-lookup"><span data-stu-id="88835-221">Feature</span></span>|<span data-ttu-id="88835-222">摘要报告</span><span class="sxs-lookup"><span data-stu-id="88835-222">Summary Reports</span></span>|<span data-ttu-id="88835-223">详细报告</span><span class="sxs-lookup"><span data-stu-id="88835-223">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="88835-224">应用程序共享跃点数</span><span class="sxs-lookup"><span data-stu-id="88835-224">Application sharing metric</span></span> | <span data-ttu-id="88835-225">否</span><span class="sxs-lookup"><span data-stu-id="88835-225">No</span></span> | <span data-ttu-id="88835-226">是</span><span class="sxs-lookup"><span data-stu-id="88835-226">Yes</span></span> |
|<span data-ttu-id="88835-227">客户构建信息支持</span><span class="sxs-lookup"><span data-stu-id="88835-227">Customer building information support</span></span> | <span data-ttu-id="88835-228">是</span><span class="sxs-lookup"><span data-stu-id="88835-228">Yes</span></span> | <span data-ttu-id="88835-229">是 </span><span class="sxs-lookup"><span data-stu-id="88835-229">Yes</span></span> |
|<span data-ttu-id="88835-230">客户终结点信息支持</span><span class="sxs-lookup"><span data-stu-id="88835-230">Customer endpoint information support</span></span> | <span data-ttu-id="88835-231">仅在<span>cqd.teams.microsoft.com 中<span/></span><span class="sxs-lookup"><span data-stu-id="88835-231">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="88835-232">仅在<span>cqd.teams.microsoft.com 中<span/></span><span class="sxs-lookup"><span data-stu-id="88835-232">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="88835-233">向下钻取分析支持</span><span class="sxs-lookup"><span data-stu-id="88835-233">Drill down analysis support</span></span>   | <span data-ttu-id="88835-234">否</span><span class="sxs-lookup"><span data-stu-id="88835-234">No</span></span>   | <span data-ttu-id="88835-235">是</span><span class="sxs-lookup"><span data-stu-id="88835-235">Yes</span></span>   |
|<span data-ttu-id="88835-236">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="88835-236">Media reliability metrics</span></span>   | <span data-ttu-id="88835-237">否</span><span class="sxs-lookup"><span data-stu-id="88835-237">No</span></span>   | <span data-ttu-id="88835-238">是</span><span class="sxs-lookup"><span data-stu-id="88835-238">Yes</span></span>   |
|<span data-ttu-id="88835-239">现成的报表</span><span class="sxs-lookup"><span data-stu-id="88835-239">Out-of-the-box reports</span></span>   | <span data-ttu-id="88835-240">是</span><span class="sxs-lookup"><span data-stu-id="88835-240">Yes</span></span>   | <span data-ttu-id="88835-241">是 </span><span class="sxs-lookup"><span data-stu-id="88835-241">Yes</span></span>   |
|<span data-ttu-id="88835-242">概述报表</span><span class="sxs-lookup"><span data-stu-id="88835-242">Overview reports</span></span>   | <span data-ttu-id="88835-243">是</span><span class="sxs-lookup"><span data-stu-id="88835-243">Yes</span></span>   | <span data-ttu-id="88835-244">是 </span><span class="sxs-lookup"><span data-stu-id="88835-244">Yes</span></span>   |
|<span data-ttu-id="88835-245">每用户报告集</span><span class="sxs-lookup"><span data-stu-id="88835-245">Per-user report set</span></span>   | <span data-ttu-id="88835-246">否</span><span class="sxs-lookup"><span data-stu-id="88835-246">No</span></span>   | <span data-ttu-id="88835-247">是</span><span class="sxs-lookup"><span data-stu-id="88835-247">Yes</span></span>   |
|<span data-ttu-id="88835-248">报表集自定义（添加、删除、修改报表）</span><span class="sxs-lookup"><span data-stu-id="88835-248">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="88835-249">否</span><span class="sxs-lookup"><span data-stu-id="88835-249">No</span></span>   | <span data-ttu-id="88835-250">是</span><span class="sxs-lookup"><span data-stu-id="88835-250">Yes</span></span>   |
|<span data-ttu-id="88835-251">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="88835-251">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="88835-252">否</span><span class="sxs-lookup"><span data-stu-id="88835-252">No</span></span>   | <span data-ttu-id="88835-253">是</span><span class="sxs-lookup"><span data-stu-id="88835-253">Yes</span></span>   |
|<span data-ttu-id="88835-254">视频指标</span><span class="sxs-lookup"><span data-stu-id="88835-254">Video metrics</span></span>   | <span data-ttu-id="88835-255">否</span><span class="sxs-lookup"><span data-stu-id="88835-255">No</span></span>   | <span data-ttu-id="88835-256">是</span><span class="sxs-lookup"><span data-stu-id="88835-256">Yes</span></span>   |
|<span data-ttu-id="88835-257">可用数据量</span><span class="sxs-lookup"><span data-stu-id="88835-257">Amount of data available</span></span>   | <span data-ttu-id="88835-258">过去6个月</span><span class="sxs-lookup"><span data-stu-id="88835-258">Last 6 months</span></span>   | <span data-ttu-id="88835-259">过去6个月</span><span class="sxs-lookup"><span data-stu-id="88835-259">Last 6 months</span></span>   |
|<span data-ttu-id="88835-260">Microsoft 团队数据</span><span class="sxs-lookup"><span data-stu-id="88835-260">Microsoft Teams data</span></span>   | <span data-ttu-id="88835-261">是</span><span class="sxs-lookup"><span data-stu-id="88835-261">Yes</span></span>   | <span data-ttu-id="88835-262">是 </span><span class="sxs-lookup"><span data-stu-id="88835-262">Yes</span></span>   |
| | | |

### <a name="out-of-the-box-reports"></a><span data-ttu-id="88835-263">现成的报表</span><span class="sxs-lookup"><span data-stu-id="88835-263">Out-of-the-box reports</span></span>

<span data-ttu-id="88835-264">所有版本的 CQD 都提供了一种可提供通话质量指标的体验，无需创建新报表。</span><span class="sxs-lookup"><span data-stu-id="88835-264">All editions of CQD provide an experience that gives you call quality metrics without the need to create new reports.</span></span> <span data-ttu-id="88835-265">在后端处理完数据后，您将在报告中看到通话质量数据。</span><span class="sxs-lookup"><span data-stu-id="88835-265">Once data is processed in the back-end, you see call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="88835-266">概述报表</span><span class="sxs-lookup"><span data-stu-id="88835-266">Overview reports</span></span>

<span data-ttu-id="88835-267">CQD 的所有版本都为整体通话质量信息提供高级别的入口点，但信息在摘要报告中的显示方式不同于详细的报告。</span><span class="sxs-lookup"><span data-stu-id="88835-267">All editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from Detailed Reports.</span></span>  
  
<span data-ttu-id="88835-268">摘要报告提供简化的选项卡式页面报告视图，以便你可以快速浏览和理解整体通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="88835-268">Summary Reports provide a simplified tabbed page report view so you can quickly browse and understand the overall call quality status and trends.</span></span>

<span data-ttu-id="88835-269">四个选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="88835-269">The four tabs include:</span></span>
  
- <span data-ttu-id="88835-270">**整体通话质量**-提供有关所有流的信息，它是显示每月和每天的趋势的聚合：</span><span class="sxs-lookup"><span data-stu-id="88835-270">**Overall Call Quality** — provides information about all streams, which is an aggregation that shows monthly and daily trends for:</span></span>
  - <span data-ttu-id="88835-271">服务器-客户端流</span><span class="sxs-lookup"><span data-stu-id="88835-271">Server-Client streams</span></span>
  - <span data-ttu-id="88835-272">客户端-客户端流</span><span class="sxs-lookup"><span data-stu-id="88835-272">Client-Client streams</span></span>
  - <span data-ttu-id="88835-273">单独的服务器-客户端和客户端-客户端流</span><span class="sxs-lookup"><span data-stu-id="88835-273">Separate Server-Client and Client-Client streams</span></span>
- <span data-ttu-id="88835-274">**服务器-客户端**-提供服务器和客户端终结点之间的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88835-274">**Server—Client** — provides details for the streams between Server and Client endpoints.</span></span>
- <span data-ttu-id="88835-275">**客户端-客户端**-提供两个客户端终结点之间的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88835-275">**Client—Client** — provides details for the streams between two Client endpoints.</span></span>
- <span data-ttu-id="88835-276">**语音质量 SLA** —提供有关 Skype For Business Online 语音质量 SLA 中所含通话的信息。</span><span class="sxs-lookup"><span data-stu-id="88835-276">**Voice Quality SLA** — provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>

> [!NOTE]
> <span data-ttu-id="88835-277">CQD 版本3适用于 Microsoft 团队、Skype for business Online 和 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="88835-277">CQD Version 3 works with Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span> <span data-ttu-id="88835-278">要将 CQD 与 Skype for Business Server 2019 配合使用，您必须[配置 "呼叫数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)"。</span><span class="sxs-lookup"><span data-stu-id="88835-278">To use CQD with Skype for Business Server 2019, you will have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="88835-279">请参阅在开始之前[计划通话数据连接器](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/plan-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="88835-279">See [Plan Call Data Connector](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>

- <span data-ttu-id="88835-280">按地区呼叫质量：</span><span class="sxs-lookup"><span data-stu-id="88835-280">Call Quality by Region:</span></span>

  - <span data-ttu-id="88835-281">按区域日期</span><span class="sxs-lookup"><span data-stu-id="88835-281">date-by-region</span></span>
  - <span data-ttu-id="88835-282">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="88835-282">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="88835-283">特定位置</span><span class="sxs-lookup"><span data-stu-id="88835-283">specific locations</span></span>
  - <span data-ttu-id="88835-284">特定子网</span><span class="sxs-lookup"><span data-stu-id="88835-284">specific subnet</span></span>
  - <span data-ttu-id="88835-285">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="88835-285">impacted user or users</span></span>

- <span data-ttu-id="88835-286">按地区呼叫可靠性/失败：</span><span class="sxs-lookup"><span data-stu-id="88835-286">Call Reliability/Failure by Region:</span></span>
  - <span data-ttu-id="88835-287">按区域日期</span><span class="sxs-lookup"><span data-stu-id="88835-287">date-by-region</span></span>
  - <span data-ttu-id="88835-288">按区域聚合到每个小时</span><span class="sxs-lookup"><span data-stu-id="88835-288">aggregated down to hour-by-region</span></span>
  - <span data-ttu-id="88835-289">特定位置</span><span class="sxs-lookup"><span data-stu-id="88835-289">specific locations</span></span>
  - <span data-ttu-id="88835-290">特定子网</span><span class="sxs-lookup"><span data-stu-id="88835-290">specific subnet</span></span>
  - <span data-ttu-id="88835-291">受影响的用户或用户</span><span class="sxs-lookup"><span data-stu-id="88835-291">impacted user or users</span></span>

- <span data-ttu-id="88835-292">按区域对我的呼叫（RMC）进行评级：从按区域聚合到特定位置的特定位置到提供低 RMC 等级的用户。</span><span class="sxs-lookup"><span data-stu-id="88835-292">Rate My Call (RMC) by Region: from month-by-region aggregated down to specific locations to users who provide low RMC ratings.</span></span> <span data-ttu-id="88835-293">CQD v3 还包括逐字反馈。</span><span class="sxs-lookup"><span data-stu-id="88835-293">CQD v3 also includes verbatim feedback.</span></span>
- <span data-ttu-id="88835-294">帮助者：可用于 P2P 呼叫或会议的特定用户或所有参与者和通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="88835-294">Helpdesk: available for a specific user on P2P calls or Meetings, or for all participants and call details.</span></span> <span data-ttu-id="88835-295">帮助识别基于网络位置、设备或固件的可能系统问题。</span><span class="sxs-lookup"><span data-stu-id="88835-295">Helps identify possible system issues based on network location, devices, or firmware.</span></span>  
- <span data-ttu-id="88835-296">客户端版本：查看每个客户端版本的会话和用户计数，或向下钻取以查看每个客户端版本的用户名。</span><span class="sxs-lookup"><span data-stu-id="88835-296">Client Versions: View the Session and Users counts for each Client Version, or drill down to User names for each client version.</span></span> <span data-ttu-id="88835-297">产品和客户端类型的预生成筛选器帮助将版本集中到特定客户端。</span><span class="sxs-lookup"><span data-stu-id="88835-297">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>
- <span data-ttu-id="88835-298">终结点：显示映射到电脑/Mac 的 "生成/模型" 的计算机终结点。</span><span class="sxs-lookup"><span data-stu-id="88835-298">Endpoints: Shows Machine Endpoints mapped to Make/Model of the PC/Mac.</span></span> <span data-ttu-id="88835-299">按 "生成/模型" 显示聚合质量。</span><span class="sxs-lookup"><span data-stu-id="88835-299">Shows aggregated quality by Make/Model.</span></span> <span data-ttu-id="88835-300">映射数据的上载类似于生成数据。</span><span class="sxs-lookup"><span data-stu-id="88835-300">Mapping data is uploaded similar to Building data.</span></span>

### <a name="overall-call-quality-tab"></a><span data-ttu-id="88835-301">"整体通话质量" 选项卡</span><span class="sxs-lookup"><span data-stu-id="88835-301">Overall Call Quality tab</span></span>

<span data-ttu-id="88835-302">使用此选项卡上的数据根据流计数和不良百分比评估通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="88835-302">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="88835-303">右上角的图例将显示哪些颜色和视觉元素表示这些指标。</span><span class="sxs-lookup"><span data-stu-id="88835-303">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![屏幕截图：显示 "通话质量" 选项卡](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="88835-305">流分为三个组： "完好"、"差" 和 "未分类"。</span><span class="sxs-lookup"><span data-stu-id="88835-305">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="88835-306">还计算出的*百分比*值太差，可让你将流的比率划分为*较差*的分类流计数。</span><span class="sxs-lookup"><span data-stu-id="88835-306">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="88835-307">由于*较差的% = 不良流/（差流 + 正常流） \* 100*，*差%* 不受多个未*分类*流的存在的影响。</span><span class="sxs-lookup"><span data-stu-id="88835-307">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="88835-308">若要查看将流分类为差或好的内容，请参阅["呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。</span><span class="sxs-lookup"><span data-stu-id="88835-308">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="88835-309">使用左侧的刻度测量流计数值。</span><span class="sxs-lookup"><span data-stu-id="88835-309">Use the scale on the left to measure the stream count values.</span></span>
  
![屏幕截图：显示流计数值](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="88835-311">使用右侧的刻度测量差的百分比值。</span><span class="sxs-lookup"><span data-stu-id="88835-311">Use the scale on the right to measure the Poor % values.</span></span>
  
![屏幕截图：显示差的% 值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="88835-313">也可以通过将鼠标悬停在条上来获取实际数值。</span><span class="sxs-lookup"><span data-stu-id="88835-313">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88835-314">下面的示例来自非常小的示例数据集，并且值对于实际部署不切合实际。</span><span class="sxs-lookup"><span data-stu-id="88835-314">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![屏幕截图：显示用于访问数据的鼠标](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="88835-316">整个流卷可帮助确定计算出的较差百分比的相关程度。</span><span class="sxs-lookup"><span data-stu-id="88835-316">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="88835-317">总体流的数量越小，报告的百分比值越低越可靠。</span><span class="sxs-lookup"><span data-stu-id="88835-317">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="88835-318">服务器-客户端选项卡和客户端-客户端选项卡</span><span class="sxs-lookup"><span data-stu-id="88835-318">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="88835-319">这两个选项卡提供了在其终结点到终结点应用场景中发生的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88835-319">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="88835-320">"服务器-客户端" 选项卡具有四个可折叠的部分，表示媒体流将流经的四个方案。</span><span class="sxs-lookup"><span data-stu-id="88835-320">The Server-Client tab has four collapsible sections  that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="88835-321">内部有线</span><span class="sxs-lookup"><span data-stu-id="88835-321">Wired Inside</span></span>
- <span data-ttu-id="88835-322">外部有线</span><span class="sxs-lookup"><span data-stu-id="88835-322">Wired Outside</span></span>
- <span data-ttu-id="88835-323">内部 Wifi</span><span class="sxs-lookup"><span data-stu-id="88835-323">Wifi Inside</span></span>
- <span data-ttu-id="88835-324">外部 Wifi</span><span class="sxs-lookup"><span data-stu-id="88835-324">Wifi Outside</span></span>

<span data-ttu-id="88835-325">同样，"客户端-客户端" 选项卡具有五个可折叠部分：</span><span class="sxs-lookup"><span data-stu-id="88835-325">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="88835-326">有线内部-有线内部</span><span class="sxs-lookup"><span data-stu-id="88835-326">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="88835-327">有线内部-有线外部</span><span class="sxs-lookup"><span data-stu-id="88835-327">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="88835-328">有线外部-有线外部</span><span class="sxs-lookup"><span data-stu-id="88835-328">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="88835-329">内部有线-内部 Wifi</span><span class="sxs-lookup"><span data-stu-id="88835-329">Wired Inside — Wifi Inside</span></span>
- <span data-ttu-id="88835-330">内部有线-外部 Wifi</span><span class="sxs-lookup"><span data-stu-id="88835-330">Wired Inside — Wifi Outside</span></span>

#### <a name="inside-test"></a><span data-ttu-id="88835-331">内部测试</span><span class="sxs-lookup"><span data-stu-id="88835-331">Inside Test</span></span>

<span data-ttu-id="88835-332">在处理期间，CQD 后端使用建筑物信息将流分类为*内部*或*外部*流（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="88835-332">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="88835-333">每个流的终结点与子网地址相关联。</span><span class="sxs-lookup"><span data-stu-id="88835-333">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="88835-334">如果子网位于上载的生成信息中标记为 "InsideCorp" 的子网列表中，则将其视为*内部*。</span><span class="sxs-lookup"><span data-stu-id="88835-334">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="88835-335">如果尚未上载生成信息，则内部测试始终会将流分类为*外部*流。</span><span class="sxs-lookup"><span data-stu-id="88835-335">If Building information has not yet been uploaded, then Inside Test  always classifies the streams as *Outside*.</span></span>  

> [!NOTE]
> <span data-ttu-id="88835-336">服务器客户端方案的内部测试仅考虑客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="88835-336">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="88835-337">由于服务器始终来自用户的视角，因此不会在测试中考虑。</span><span class="sxs-lookup"><span data-stu-id="88835-337">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="88835-338">有线与 wifi</span><span class="sxs-lookup"><span data-stu-id="88835-338">Wired vs. wifi</span></span>

<span data-ttu-id="88835-339">根据名称指示，分类标准基于客户端连接的类型。</span><span class="sxs-lookup"><span data-stu-id="88835-339">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="88835-340">同样，服务器始终是有线的，并且不会包含在计算中。</span><span class="sxs-lookup"><span data-stu-id="88835-340">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88835-341">如果有一个流，则如果两个终结点中的一个终结点连接到 Wifi 网络，则会在 CQD 中将其分类为 Wifi。</span><span class="sxs-lookup"><span data-stu-id="88835-341">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span>
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="88835-342">选择要在报表中查看的产品数据</span><span class="sxs-lookup"><span data-stu-id="88835-342">Selecting product data to see in reports</span></span>

<a name="BKMKProductFilter"></a>

<span data-ttu-id="88835-343">在摘要和位置增强的报表中，你可以使用 "**产品筛选器**" 下拉列表显示所有产品数据、仅 Microsoft 团队数据或仅 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="88835-343">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![屏幕截图：显示产品筛选器控件选项](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="88835-345">在 "详细报表" 中，可以使用 "**属于团队**" 维度将数据筛选到 Microsoft 团队或 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="88835-345">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="88835-346">上载租户数据信息</span><span class="sxs-lookup"><span data-stu-id="88835-346">Upload Tenant Data information</span></span>

<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="88835-347">CQD 摘要报告仪表板包括**租户数据上载**页面，该页面从右上角的 "设置" 菜单中选择 "**租户数据上载**"。</span><span class="sxs-lookup"><span data-stu-id="88835-347">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="88835-348">此页面用于管理员上载其自己的信息，例如：</span><span class="sxs-lookup"><span data-stu-id="88835-348">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="88835-349">IP 地址和地理信息的地图</span><span class="sxs-lookup"><span data-stu-id="88835-349">A map of IP address and geographical information</span></span>
- <span data-ttu-id="88835-350">每个无线 AP 及其 MAC 地址的地图</span><span class="sxs-lookup"><span data-stu-id="88835-350">A map of each wireless AP and its MAC address</span></span>
- <span data-ttu-id="88835-351">终结点到终结点的映射/模型/类型等。</span><span class="sxs-lookup"><span data-stu-id="88835-351">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
![屏幕截图：显示呼叫质量仪表板租户数据](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="88835-353">在 "**租户数据上载**" 页面上，使用下拉菜单选择要上传的数据文件类型。</span><span class="sxs-lookup"><span data-stu-id="88835-353">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type to upload.</span></span> <span data-ttu-id="88835-354">"文件" 数据类型表示文件的内容（例如，"建筑物" 指的是 IP 地址和建筑物和其他地理信息的映射，"终结点" 指终结点名称和模型/类型信息的映射。</span><span class="sxs-lookup"><span data-stu-id="88835-354">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building and other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type information).</span></span> <span data-ttu-id="88835-355">当前 CQD 支持 cqd.teams.microsoft.com 的 "建筑物" 和 "终结点" 数据类型（在预览阶段和尚未正式提供），cqd.lync.com 仅支持 "建筑物" 数据类型。</span><span class="sxs-lookup"><span data-stu-id="88835-355">Currently CQD supports “Building” and “Endpoint” data types for cqd.teams.microsoft.com (in preview stage and not officially available yet), cqd.lync.com only supports the "Building" data type.</span></span>
2. <span data-ttu-id="88835-356">选择文件数据类型后，单击 "**浏览**" 以选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="88835-356">After you select the file data type, click **Browse** to choose a data file.</span></span>

   - <span data-ttu-id="88835-357">数据文件必须为 tsv （以制表符分隔的值）文件或 .csv （以逗号分隔的值）文件。</span><span class="sxs-lookup"><span data-stu-id="88835-357">A data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="88835-358">使用 .csv 文件时，包含逗号的任何字段都必须用引号引起来，或者删除逗号。</span><span class="sxs-lookup"><span data-stu-id="88835-358">With a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="88835-359">例如，如果建筑物名称为 NY，则在 .csv 文件中输入 "纽约州，NY"。</span><span class="sxs-lookup"><span data-stu-id="88835-359">For example, if your building name is NY,NY,  enter  "NY,NY" in the .csv file.</span></span>
   - <span data-ttu-id="88835-360">数据文件不能大于 50 MB。</span><span class="sxs-lookup"><span data-stu-id="88835-360">The data file must be no larger than 50 MB.</span></span>
   - <span data-ttu-id="88835-361">上载到 cqd.teams.microsoft.com 的文件具有展开的行限制1000000以使查询性能更快。</span><span class="sxs-lookup"><span data-stu-id="88835-361">Files uploaded to cqd.teams.microsoft.com have an expanded row limit of 1,000,000 to keep query performance fast.</span></span> <span data-ttu-id="88835-362">此限制也适用于 CQD<span></span><span></span>上的 CQD v2。</span><span class="sxs-lookup"><span data-stu-id="88835-362">This limit also applies to CQD v2  on cqd<span></span>.lync<span></span>.com.</span></span>
   - <span data-ttu-id="88835-363">对于每个数据文件，文件中的每一列都必须与本主题后面部分所述的预定义数据类型匹配。</span><span class="sxs-lookup"><span data-stu-id="88835-363">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
3. <span data-ttu-id="88835-364">接下来，指定**开始日期**，并根据需要**指定结束日期**。</span><span class="sxs-lookup"><span data-stu-id="88835-364">Next, specify a **Start date** and, optionally, **Specify an end date**.</span></span>
4. <span data-ttu-id="88835-365">最后，选择 "**上传**" 将文件上载到 CQD 服务器。</span><span class="sxs-lookup"><span data-stu-id="88835-365">Finally, select **Upload** to upload the file to the CQD server.</span></span>
    <span data-ttu-id="88835-366">上载文件之前，首先验证该文件。</span><span class="sxs-lookup"><span data-stu-id="88835-366">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="88835-367">验证后，它将存储在 Azure blob 中。</span><span class="sxs-lookup"><span data-stu-id="88835-367">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="88835-368">如果验证失败或文件无法存储在 Azure blob 中，则会显示一条错误消息请求对文件的更正。</span><span class="sxs-lookup"><span data-stu-id="88835-368">If validation fails or the file fails to be stored in an Azure blob, an error message requests a correction to the file.</span></span> <span data-ttu-id="88835-369">下图显示了数据文件中的列数不正确的示例错误。</span><span class="sxs-lookup"><span data-stu-id="88835-369">The following image shows a sample error with an incorrect number of columns in the data file.</span></span>

     ![屏幕截图：显示上载验证错误](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="88835-371">如果验证期间未出现任何错误，则文件上载成功。</span><span class="sxs-lookup"><span data-stu-id="88835-371">If no errors occur during validation, the file upload succeeds.</span></span> <span data-ttu-id="88835-372">然后，您可以在 "我的上**传**" 表中看到上载的数据文件。</span><span class="sxs-lookup"><span data-stu-id="88835-372">You can then see the uploaded data file in the **My uploads** table.</span></span> <span data-ttu-id="88835-373">该页面底部还显示为当前租户上载的所有文件的完整列表。</span><span class="sxs-lookup"><span data-stu-id="88835-373">The bottom of that page also shows a full list of all files uploaded for the current tenant.</span></span>
    <span data-ttu-id="88835-374">每个记录显示一个上载的租户数据文件，其中包含文件类型、上次更新时间、时间段、说明、删除图标和下载图标。</span><span class="sxs-lookup"><span data-stu-id="88835-374">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="88835-375">若要删除文件，请选择表格中的垃圾桶图标。</span><span class="sxs-lookup"><span data-stu-id="88835-375">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="88835-376">若要下载文件，请选择表格的 "**下载**" 列中的 "下载" 图标。</span><span class="sxs-lookup"><span data-stu-id="88835-376">To download a file, select the download icon in the **Download** column of the table.</span></span>

     ![屏幕截图：显示 "我的上传" 表](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. <span data-ttu-id="88835-378">如果你选择使用多个生成数据文件或多个终结点数据文件，则某些报表的生成速度较慢。</span><span class="sxs-lookup"><span data-stu-id="88835-378">If you choose to use multiple building data files or multiple endpoint data files, some reports generate more slowly.</span></span>

### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="88835-379">租户数据文件格式和结构</span><span class="sxs-lookup"><span data-stu-id="88835-379">Tenant data file format and structure</span></span>

<span data-ttu-id="88835-380"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="88835-380"></span></span>

### <a name="building-data-file"></a><span data-ttu-id="88835-381">生成数据文件</span><span class="sxs-lookup"><span data-stu-id="88835-381">Building data file</span></span>

<span data-ttu-id="88835-382">CQD 使用构建数据文件，这有助于提供有用的通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="88835-382">CQD uses a Building data file, which helps provide useful call details.</span></span> <span data-ttu-id="88835-383">通过展开 "网络 + NetworkRange" 列，然后将 "子网" 列联接到呼叫记录的第一个子网或 "第二个子网" 列中，显示建筑物、城市、国家或地区信息，从而派生出子网列。</span><span class="sxs-lookup"><span data-stu-id="88835-383">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="88835-384">你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="88835-384">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="88835-385">文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="88835-385">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>
- <span data-ttu-id="88835-386">数据文件不包含表格标题行。</span><span class="sxs-lookup"><span data-stu-id="88835-386">The data file doesn't include a table header row.</span></span> <span data-ttu-id="88835-387">数据文件的第一行应为真实数据，而不是标题标签（如 "Network"）。</span><span class="sxs-lookup"><span data-stu-id="88835-387">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>
- <span data-ttu-id="88835-388">文件中的数据类型只能是 String、Integer 或 Boolean。</span><span class="sxs-lookup"><span data-stu-id="88835-388">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="88835-389">对于整数数据类型，值必须是一个数值。</span><span class="sxs-lookup"><span data-stu-id="88835-389">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="88835-390">布尔值必须是0或1。</span><span class="sxs-lookup"><span data-stu-id="88835-390">Boolean values must be either 0 or 1.</span></span>
- <span data-ttu-id="88835-391">如果列使用字符串数据类型，则数据字段可以为空，但仍须由制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="88835-391">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="88835-392">空数据字段只是分配一个空字符串值。</span><span class="sxs-lookup"><span data-stu-id="88835-392">An empty data field just assigns an empty String value.</span></span>
- <span data-ttu-id="88835-393">每一行必须有14列，每一列必须具有相应的数据类型，并且列必须遵循下表中列出的顺序：</span><span class="sxs-lookup"><span data-stu-id="88835-393">There must be 14 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table:</span></span>

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|<span data-ttu-id="88835-394">**列字段名称**</span><span class="sxs-lookup"><span data-stu-id="88835-394">**Column field name**</span></span>|<span data-ttu-id="88835-395">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="88835-395">NetworkIP</span></span>  |<span data-ttu-id="88835-396">NetworkName</span><span class="sxs-lookup"><span data-stu-id="88835-396">NetworkName</span></span>              |<span data-ttu-id="88835-397">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="88835-397">NetworkRange</span></span>|<span data-ttu-id="88835-398">BuildingName</span><span class="sxs-lookup"><span data-stu-id="88835-398">BuildingName</span></span>  |<span data-ttu-id="88835-399">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="88835-399">OwnershipType</span></span>| <span data-ttu-id="88835-400">BuildingType</span><span class="sxs-lookup"><span data-stu-id="88835-400">BuildingType</span></span>  |<span data-ttu-id="88835-401">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="88835-401">BuildingOfficeType</span></span>|<span data-ttu-id="88835-402">城市</span><span class="sxs-lookup"><span data-stu-id="88835-402">City</span></span>   |<span data-ttu-id="88835-403">ZipCode</span><span class="sxs-lookup"><span data-stu-id="88835-403">ZipCode</span></span>|<span data-ttu-id="88835-404">该国</span><span class="sxs-lookup"><span data-stu-id="88835-404">Country</span></span>|<span data-ttu-id="88835-405">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="88835-405">State</span></span> |<span data-ttu-id="88835-406">区域</span><span class="sxs-lookup"><span data-stu-id="88835-406">Region</span></span>|<span data-ttu-id="88835-407">InsideCorp&dagger;</span><span class="sxs-lookup"><span data-stu-id="88835-407">InsideCorp&dagger;</span></span>|<span data-ttu-id="88835-408">ExpressRoute&Dagger;</span><span class="sxs-lookup"><span data-stu-id="88835-408">ExpressRoute&Dagger;</span></span>|<span data-ttu-id="88835-409">VPN （可选）</span><span class="sxs-lookup"><span data-stu-id="88835-409">VPN (optional)</span></span>|
|<span data-ttu-id="88835-410">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="88835-410">**Data type**</span></span>        | <span data-ttu-id="88835-411">String</span><span class="sxs-lookup"><span data-stu-id="88835-411">String</span></span>    | <span data-ttu-id="88835-412">String</span><span class="sxs-lookup"><span data-stu-id="88835-412">String</span></span>                  |<span data-ttu-id="88835-413">数字</span><span class="sxs-lookup"><span data-stu-id="88835-413">Number</span></span>      | <span data-ttu-id="88835-414">String</span><span class="sxs-lookup"><span data-stu-id="88835-414">String</span></span>       | <span data-ttu-id="88835-415">String</span><span class="sxs-lookup"><span data-stu-id="88835-415">String</span></span>      | <span data-ttu-id="88835-416">String</span><span class="sxs-lookup"><span data-stu-id="88835-416">String</span></span>        |<span data-ttu-id="88835-417">String</span><span class="sxs-lookup"><span data-stu-id="88835-417">String</span></span>            |<span data-ttu-id="88835-418">String</span><span class="sxs-lookup"><span data-stu-id="88835-418">String</span></span> |<span data-ttu-id="88835-419">String</span><span class="sxs-lookup"><span data-stu-id="88835-419">String</span></span> |<span data-ttu-id="88835-420">String</span><span class="sxs-lookup"><span data-stu-id="88835-420">String</span></span> |<span data-ttu-id="88835-421">String</span><span class="sxs-lookup"><span data-stu-id="88835-421">String</span></span>|<span data-ttu-id="88835-422">String</span><span class="sxs-lookup"><span data-stu-id="88835-422">String</span></span>|<span data-ttu-id="88835-423">Boolean</span><span class="sxs-lookup"><span data-stu-id="88835-423">Boolean</span></span>   |<span data-ttu-id="88835-424">Boolean</span><span class="sxs-lookup"><span data-stu-id="88835-424">Boolean</span></span>     |<span data-ttu-id="88835-425">Boolean</span><span class="sxs-lookup"><span data-stu-id="88835-425">Boolean</span></span>|
|<span data-ttu-id="88835-426">**示例值**</span><span class="sxs-lookup"><span data-stu-id="88835-426">**Example value**</span></span>    |<span data-ttu-id="88835-427">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="88835-427">192.168.1.0</span></span>|<span data-ttu-id="88835-428">美国/西雅图/西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="88835-428">USA/Seattle/SEATTLE-SEA-1</span></span>| <span data-ttu-id="88835-429">个</span><span class="sxs-lookup"><span data-stu-id="88835-429">26</span></span>         | <span data-ttu-id="88835-430">西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="88835-430">SEATTLE-SEA-1</span></span>| <span data-ttu-id="88835-431">制定</span><span class="sxs-lookup"><span data-stu-id="88835-431">Contoso</span></span>     | <span data-ttu-id="88835-432">终止</span><span class="sxs-lookup"><span data-stu-id="88835-432">IT Termination</span></span>|<span data-ttu-id="88835-433">技术</span><span class="sxs-lookup"><span data-stu-id="88835-433">Engineering</span></span>       |<span data-ttu-id="88835-434">西雅图</span><span class="sxs-lookup"><span data-stu-id="88835-434">Seattle</span></span>|<span data-ttu-id="88835-435">98001</span><span class="sxs-lookup"><span data-stu-id="88835-435">98001</span></span>  |<span data-ttu-id="88835-436">我们</span><span class="sxs-lookup"><span data-stu-id="88835-436">US</span></span>     |<span data-ttu-id="88835-437">WA</span><span class="sxs-lookup"><span data-stu-id="88835-437">WA</span></span>    |<span data-ttu-id="88835-438">MSUS</span><span class="sxs-lookup"><span data-stu-id="88835-438">MSUS</span></span>  | <span data-ttu-id="88835-439">1</span><span class="sxs-lookup"><span data-stu-id="88835-439">1</span></span>        |<span data-ttu-id="88835-440">0</span><span class="sxs-lookup"><span data-stu-id="88835-440">0</span></span>           | <span data-ttu-id="88835-441">0</span><span class="sxs-lookup"><span data-stu-id="88835-441">0</span></span>|
|||||||||||||||||

<span data-ttu-id="88835-442">&dagger;此设置可用于反映子网是否位于企业网络内。</span><span class="sxs-lookup"><span data-stu-id="88835-442">&dagger; This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="88835-443">如果你决定，可以自定义其他用途的用法。</span><span class="sxs-lookup"><span data-stu-id="88835-443">You can customize usage for other purposes if you decide to.</span></span>

<span data-ttu-id="88835-444">&Dagger;此设置可用于反映网络是否使用 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="88835-444">&Dagger; This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="88835-445">如果你决定，可以自定义其他用途的用法。</span><span class="sxs-lookup"><span data-stu-id="88835-445">You can customize usage for other purposes if you decide to.</span></span>  

<span data-ttu-id="88835-446">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="88835-446">**Sample row:**</span></span>

```
192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0
```

> [!IMPORTANT]
> <span data-ttu-id="88835-447">网络范围可用于表示 supernet （具有单个路由前缀的若干子网的组合）。</span><span class="sxs-lookup"><span data-stu-id="88835-447">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="88835-448">将检查所有新的生成上载，查找任何重叠区域。</span><span class="sxs-lookup"><span data-stu-id="88835-448">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="88835-449">如果你以前上载了一个生成文件，则应下载当前文件，然后重新上载它以标识任何重叠，并在再次上载之前修复该问题。</span><span class="sxs-lookup"><span data-stu-id="88835-449">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="88835-450">以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。</span><span class="sxs-lookup"><span data-stu-id="88835-450">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="88835-451">某些 VPN 实现不能准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="88835-451">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="88835-452">建议将 VPN 子网添加到生成文件，而不是子网的一个条目时，将 VPN 子网中每个地址的单独条目添加为单独的32位网络。</span><span class="sxs-lookup"><span data-stu-id="88835-452">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="88835-453">每一行可以有相同的建筑物元数据。</span><span class="sxs-lookup"><span data-stu-id="88835-453">Each row can have the same building metadata.</span></span> <span data-ttu-id="88835-454">例如，对于 172.16.18.0/24，而不是一行，您应该有256行，每个地址对应于 172.16.18.0/32 和 172.16.18.255/32 之间（包括这两个地址）的一行。</span><span class="sxs-lookup"><span data-stu-id="88835-454">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="88835-455">"VPN" 列是可选的，默认值为0。</span><span class="sxs-lookup"><span data-stu-id="88835-455">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="88835-456">如果 VPN 列的值设置为1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="88835-456">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="88835-457">请谨慎使用，并且仅针对 VPN 子网，因为完全展开这些子网将对涉及生成数据的查询的查询时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="88835-457">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

### <a name="endpoint-data-file"></a><span data-ttu-id="88835-458">终结点数据文件</span><span class="sxs-lookup"><span data-stu-id="88835-458">Endpoint data file</span></span>

<span data-ttu-id="88835-459">CQD 使用终结点数据文件。</span><span class="sxs-lookup"><span data-stu-id="88835-459">CQD uses an Endpoint data file.</span></span> <span data-ttu-id="88835-460">在调用记录的第一个客户端终结点名称列或第二个客户端终结点名称列中使用列值来显示终结点的 "创建"、"模型" 或 "类型" 信息。</span><span class="sxs-lookup"><span data-stu-id="88835-460">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="88835-461">你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="88835-461">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="88835-462">文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="88835-462">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>
- <span data-ttu-id="88835-463">数据文件的内容不包含表格标题。</span><span class="sxs-lookup"><span data-stu-id="88835-463">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="88835-464">数据文件的第一行应为真实数据，而不是标题标签（如 "终结点"）。</span><span class="sxs-lookup"><span data-stu-id="88835-464">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>
- <span data-ttu-id="88835-465">所有七列仅使用字符串数据类型。</span><span class="sxs-lookup"><span data-stu-id="88835-465">All seven columns use the String data type only.</span></span> <span data-ttu-id="88835-466">允许的最大长度为64个字符。</span><span class="sxs-lookup"><span data-stu-id="88835-466">The maximum allowed length is 64 characters.</span></span>
- <span data-ttu-id="88835-467">数据字段可以为空，但仍须由制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="88835-467">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="88835-468">空数据字段只是分配一个空字符串值。</span><span class="sxs-lookup"><span data-stu-id="88835-468">An empty data field just assigns an empty String value.</span></span>
- <span data-ttu-id="88835-469">终结点必须是唯一的，否则上传将失败。</span><span class="sxs-lookup"><span data-stu-id="88835-469">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="88835-470">如果存在重复的行或两行使用同一终结点，则冲突将导致不正确的联接。</span><span class="sxs-lookup"><span data-stu-id="88835-470">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>
- <span data-ttu-id="88835-471">EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。</span><span class="sxs-lookup"><span data-stu-id="88835-471">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="88835-472">它们可以是空字符串或值，如 "IT 部门指定的2018膝上型计算机" 或 "资产标签 5678"。</span><span class="sxs-lookup"><span data-stu-id="88835-472">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>
- <span data-ttu-id="88835-473">每行必须有七列，并且列必须按以下顺序排列：</span><span class="sxs-lookup"><span data-stu-id="88835-473">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="88835-474">**字段顺序：**</span><span class="sxs-lookup"><span data-stu-id="88835-474">**Field order:**</span></span>

  <span data-ttu-id="88835-475">终结点、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="88835-475">EndpointName, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="88835-476">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="88835-476">**Sample row:**</span></span>

  `1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  

## <a name="create-custom-detailed-reports"></a><span data-ttu-id="88835-477">创建自定义详细报告</span><span class="sxs-lookup"><span data-stu-id="88835-477">Create custom detailed reports</span></span>

<span data-ttu-id="88835-478">如果您想要创建一个特定报表，使其关注所提供的详细报表所提供的数据的维度，请创建一个自定义报表。</span><span class="sxs-lookup"><span data-stu-id="88835-478">If you find you want to create a specific report that focuses on a dimension of the data in a way the provided detailed reports do not, create a custom report.</span></span>

<span data-ttu-id="88835-479">在 "登录\(**摘要报告**"\)屏幕上显示的屏幕顶部显示的报告下拉列表中，选择 "**详细报告**"，然后**单击**报表的 "操作" 菜单中的 "编辑"，以查看查询编辑器。</span><span class="sxs-lookup"><span data-stu-id="88835-479">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New** d Click "Edit" in the action menu of a report to see the Query Editor.</span></span> <span data-ttu-id="88835-480">每个报告都可以通过对多维数据集进行查询得到。</span><span class="sxs-lookup"><span data-stu-id="88835-480">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="88835-481">报告是其查询返回的数据的可视化形式。</span><span class="sxs-lookup"><span data-stu-id="88835-481">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="88835-482">查询编辑器可帮助您编辑报表的这些查询和显示选项。</span><span class="sxs-lookup"><span data-stu-id="88835-482">The Query Editor helps you edit these queries and the display options of the report.</span></span> <span data-ttu-id="88835-483">为新报表打开 "查询编辑器" 时，你会看到类似于以下屏幕截图的内容：</span><span class="sxs-lookup"><span data-stu-id="88835-483">When you open the Query Editor for a new report, you see something similar to this screenshot:</span></span>

![编辑新报表](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. <span data-ttu-id="88835-485">左侧窗格中选择了维度、度量和筛选器。</span><span class="sxs-lookup"><span data-stu-id="88835-485">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="88835-486">单击标题旁边的 "加号" 按钮以打开对话框，您可以在其中添加维度、测量或筛选，并选中相应的框。</span><span class="sxs-lookup"><span data-stu-id="88835-486">Click the "plus" button next to a heading to open the dialog where you can add a  dimension, measure, or filter and check the corresponding box.</span></span> <span data-ttu-id="88835-487">如果您编辑现有报表，则可以取消选中现有值以将其删除。</span><span class="sxs-lookup"><span data-stu-id="88835-487">If you edit an existing report, you can uncheck existing values to remove them.</span></span> <span data-ttu-id="88835-488">有关详细信息，请参阅[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="88835-488">For details, see [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
2. <span data-ttu-id="88835-489">顶部显示了图表自定义选项。</span><span class="sxs-lookup"><span data-stu-id="88835-489">Options for chart customization are displayed at the top.</span></span>
3. <span data-ttu-id="88835-490">报表的预览在查询编辑器中可用。</span><span class="sxs-lookup"><span data-stu-id="88835-490">A preview of the report is available in the Query Editor.</span></span>
4. <span data-ttu-id="88835-491">可以使用底部的 "编辑" 框创建详细的报表名称和说明。</span><span class="sxs-lookup"><span data-stu-id="88835-491">A detailed report name and description can be created with the edit box at the bottom.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="88835-492">常见问题</span><span class="sxs-lookup"><span data-stu-id="88835-492">Frequently Asked Questions</span></span>

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a><span data-ttu-id="88835-493">为什么 CQD v2 报表数据看起来与 CQD v3 报表数据不同？</span><span class="sxs-lookup"><span data-stu-id="88835-493">Why does my CQD v2 report data look different than the CQD v3 report data?</span></span> 

<span data-ttu-id="88835-494">如果你看到 CQD v2 和 v3 之间的数据差异，请确保在 "苹果" 和 "窄" 级别（而不是聚合级别）上执行数据比较或验证。</span><span class="sxs-lookup"><span data-stu-id="88835-494">If you see data differences between CQD v2 and v3, make sure that data comparison or validation is done on an 'apples-to-apples'  and narrow level, not an aggregated level.</span></span> <span data-ttu-id="88835-495">例如，如果你筛选 MSIT "建筑物 30" WiFi 团队桌面客户端数据的两个报表，则 v2 和 v3 的低质量百分比应该相同。</span><span class="sxs-lookup"><span data-stu-id="88835-495">For example, if you filter both reports for MSIT ‘Building 30' WiFi Teams Desktop client data, the Percentage of Poor Quality should be the same between v2 and v3.</span></span>

<span data-ttu-id="88835-496">CQD v2 和 CQD v3 具有不同的总数，因为 CQD v3 具有 CQD v2 中不存在的新方案。</span><span class="sxs-lookup"><span data-stu-id="88835-496">CQD v2 and CQD v3 have different total counts since CQD v3 has new scenarios not present in CQD v2.</span></span> <span data-ttu-id="88835-497">摘要总数或聚合的所有不带筛选器的数字均应不同。</span><span class="sxs-lookup"><span data-stu-id="88835-497">Summary Total or Aggregated all-up numbers with no filters are expected to be different.</span></span>  

<span data-ttu-id="88835-498">如果使用方案包括 Skype for Business Server 2019 调用，CQD v3 数据包括 Skype 机器人呼叫（自动助理、CVI、虚拟桌面界面）、实时事件和 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="88835-498">If the usage scenario includes Skype for Business Server 2019 calls, CQD v3 data includes Skype Bot calls (auto attendant, CVI, Virtual Desktop Interface), Live Events, and PSTN calls.</span></span> <span data-ttu-id="88835-499">CQD v2 不使用此数据。</span><span class="sxs-lookup"><span data-stu-id="88835-499">CQD v2 does not use this data.</span></span> <span data-ttu-id="88835-500">（CQD v3 需要配置了 cloud data connector 的 Skype for business Server 2019。）</span><span class="sxs-lookup"><span data-stu-id="88835-500">(CQD v3 requires Skype for Business Server 2019 with cloud data connector configured.)</span></span>

<span data-ttu-id="88835-501">例如，如果你在 CQD v2 摘要报告中看到200000音频5000流，但在5500失败时看到300000音频流是不寻常的（区别可能是由于 Skype for business 服务器2019通话、CVI 呼叫、PSTN 呼叫等）在 CQD v3 摘要报告中。</span><span class="sxs-lookup"><span data-stu-id="88835-501">For instance, if you see 200,000 audio streams with 5000 failures in a CQD v2 Summary Report it would not be unusual to see 300,000 audio streams with 5500 failures (the difference can be due to Skype for Business Server 2019 calls, CVI calls, PSTN calls, and so on) in a CQD v3 Summary report.</span></span>

<span data-ttu-id="88835-502">为消除意外的差异，请查看整个数据的多个细目。</span><span class="sxs-lookup"><span data-stu-id="88835-502">To disambiguate unexpected differences, look at more than one breakdown of the overall data.</span></span> <span data-ttu-id="88835-503">通过一个或多个以下参数对数据进行筛选：</span><span class="sxs-lookup"><span data-stu-id="88835-503">Filter the data by one or more of the following parameters:</span></span>

- <span data-ttu-id="88835-504">User Agent Category Pair</span><span class="sxs-lookup"><span data-stu-id="88835-504">User Agent Category Pair</span></span>
- <span data-ttu-id="88835-505">第一产品</span><span class="sxs-lookup"><span data-stu-id="88835-505">First Product</span></span>
- <span data-ttu-id="88835-506">第二产品</span><span class="sxs-lookup"><span data-stu-id="88835-506">Second Product</span></span>

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a><span data-ttu-id="88835-507">CQD v2 和 CQD v3 之间的其他预期差异</span><span class="sxs-lookup"><span data-stu-id="88835-507">Other expected differences between CQD v2 and CQD v3</span></span>

<span data-ttu-id="88835-508">团队中有多种质量和可靠性改进，而不是 Skype for business Online：</span><span class="sxs-lookup"><span data-stu-id="88835-508">There are several Quality and Reliability improvements in Teams but not Skype for Business Online:</span></span>

- <span data-ttu-id="88835-509">自动重新连接</span><span class="sxs-lookup"><span data-stu-id="88835-509">Auto-reconnect</span></span>
- <span data-ttu-id="88835-510">快速漫游</span><span class="sxs-lookup"><span data-stu-id="88835-510">Fast roaming</span></span>
- <span data-ttu-id="88835-511">改进的黑白管理</span><span class="sxs-lookup"><span data-stu-id="88835-511">Improved BW management</span></span>

<span data-ttu-id="88835-512">比较这两个服务的数据时：</span><span class="sxs-lookup"><span data-stu-id="88835-512">When you compare data for these two services:</span></span>

- <span data-ttu-id="88835-513">选择具有紧密焦点的方案，如企业有线连接、Windows 桌面或单个区域或建筑物。</span><span class="sxs-lookup"><span data-stu-id="88835-513">Pick a scenario with a tight focus, such as corporate wired connections, Windows Desktops, or a single region or building.</span></span>
- <span data-ttu-id="88835-514">检查团队 MR、TR 或 MP IP 范围。</span><span class="sxs-lookup"><span data-stu-id="88835-514">Check the Teams MR, TR, or MP IP ranges.</span></span> <span data-ttu-id="88835-515">团队范围比 Skype for business Online 更新，并且可能导致与防火墙的连接问题</span><span class="sxs-lookup"><span data-stu-id="88835-515">The Teams ranges are newer than Skype for Business Online, and that can cause connectivity issues involving firewalls</span></span>
- <span data-ttu-id="88835-516">不要比较汇总或顶级数字。</span><span class="sxs-lookup"><span data-stu-id="88835-516">Don't compare summary or top-level numbers.</span></span> <span data-ttu-id="88835-517">这些比较将使你能够将企业有线连接上的 Skype for business Online 通话的大型通话量与 LTE 或专用网络上的一小大量团队通话进行比较。</span><span class="sxs-lookup"><span data-stu-id="88835-517">These comparisons will lead you to compare a large call volume of Skype for Business Online calls on a corporate wired connection to a small volume of Teams calls on an LTE or private network.</span></span>
- <span data-ttu-id="88835-518">注意位置偏向和人口差异：有许多比较过于不同的比较非常有用：</span><span class="sxs-lookup"><span data-stu-id="88835-518">Beware of location bias and population differences: There are many comparisons that are too dissimilar to be useful:</span></span>
  - <span data-ttu-id="88835-519">NOAM： APAC</span><span class="sxs-lookup"><span data-stu-id="88835-519">NOAM : APAC</span></span>
  - <span data-ttu-id="88835-520">纽约州： Goa</span><span class="sxs-lookup"><span data-stu-id="88835-520">NY : Goa</span></span>
  - <span data-ttu-id="88835-521">有线 : wifi</span><span class="sxs-lookup"><span data-stu-id="88835-521">Wired : wifi</span></span>
  - <span data-ttu-id="88835-522">公司网络：家庭网络</span><span class="sxs-lookup"><span data-stu-id="88835-522">Corporate network : home network</span></span>
  


## <a name="related-topics"></a><span data-ttu-id="88835-523">相关主题</span><span class="sxs-lookup"><span data-stu-id="88835-523">Related topics</span></span>

[<span data-ttu-id="88835-524">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="88835-524">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="88835-525">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="88835-525">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="88835-526">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="88835-526">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="88835-527">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="88835-527">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="88835-528">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="88835-528">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
