---
title: 打开并使用通话质量仪表板
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: '请参阅如何启用和 Skype 用于业务联机呼叫质量仪表板并获取呼叫的质量摘要报告。 '
ms.openlocfilehash: bfbca275afb6da9dbe0f809906e6053f87e960e8
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401795"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="fabd9-103">打开和使用呼叫质量仪表板的 Microsoft 团队和 Skype 业务 online</span><span class="sxs-lookup"><span data-stu-id="fabd9-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="fabd9-104">了解如何配置 Office 365 组织使用呼叫质量仪表板来监视呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="fabd9-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="fabd9-105">呼叫质量仪表板 (CQD) 的 Microsoft 团队和 Skype 业务 online 使您能够获得见解进行业务服务使用的 Microsoft 团队和 Skype 的呼叫的质量。</span><span class="sxs-lookup"><span data-stu-id="fabd9-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="fabd9-106">本主题介绍的步骤，您需要完成要开始收集数据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fabd9-107">详细 CQD 报告当前是可用作技术预览版，但适用于所有的客户。</span><span class="sxs-lookup"><span data-stu-id="fabd9-107">The CQD detailed reports are currently available as Tech Preview but available to all customers.</span></span> 
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="fabd9-108">最新更改和更新</span><span class="sxs-lookup"><span data-stu-id="fabd9-108">Latest changes and updates</span></span>

<span data-ttu-id="fabd9-109">对 CQD 的最新更改如下所示：</span><span class="sxs-lookup"><span data-stu-id="fabd9-109">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="fabd9-110">包括除了 Skype Online 业务数据的 Microsoft 团队数据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-110">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="fabd9-111">摘要报告包括产品筛选器以选择所有数据、 Microsoft 团队数据或 Skype Online 业务数据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-111">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="fabd9-112">已更新视频和 VBSS 流质量分类逻辑。</span><span class="sxs-lookup"><span data-stu-id="fabd9-112">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="fabd9-113">最新的分类器定义，请参阅[呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="fabd9-113">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="fabd9-114">请参阅此列表的[维度和度量值可用呼叫质量仪表板中](dimensions-and-measures-available-in-call-quality-dashboard.md)的文章。</span><span class="sxs-lookup"><span data-stu-id="fabd9-114">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fabd9-115">有关更新和向仪表板的更改的信息可通过单击中的链接**好消息 ！**</span><span class="sxs-lookup"><span data-stu-id="fabd9-115">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="fabd9-116">标题显示仪表板上时。</span><span class="sxs-lookup"><span data-stu-id="fabd9-116">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="fabd9-117">激活 Microsoft 呼叫质量仪表板 (CQD) 摘要报告</span><span class="sxs-lookup"><span data-stu-id="fabd9-117">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="fabd9-118">您可以开始使用 CQD 之前，您需要激活的 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="fabd9-118">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>
 
<span data-ttu-id="fabd9-119">![sfb-徽标-30x30.png](media/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="fabd9-119">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="fabd9-120">登录到 Office 365 组织使用管理帐户，，然后选择**管理员**图块打开在管理中心。</span><span class="sxs-lookup"><span data-stu-id="fabd9-120">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="fabd9-121">在左窗格中，在**管理中心**，选择打开业务管理中心的 Skype **for Business 的 Skype** 。</span><span class="sxs-lookup"><span data-stu-id="fabd9-121">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="fabd9-122">在业务管理中心的 Skype，在左侧窗格中，选择**工具**，然后选择**业务联机呼叫质量仪表板的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="fabd9-122">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![Skype 业务工具](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="fabd9-124">在打开页上，使用您的全局管理员帐户，登录，然后提供出现提示时的帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-124">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![CQD 登录](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="fabd9-126">登录，一旦被激活后后, CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-126">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>

<span data-ttu-id="fabd9-127">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="fabd9-127">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
 
1. <span data-ttu-id="fabd9-128">登录到 Office 365 组织使用的 Microsoft 团队服务管理帐户，然后选择**管理员**图块打开在管理中心。</span><span class="sxs-lookup"><span data-stu-id="fabd9-128">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="fabd9-129">在左窗格中，在**管理中心**，选择**Microsoft 团队**打开的 Microsoft 团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="fabd9-129">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
    
3. <span data-ttu-id="fabd9-130">在 Microsoft 团队管理中心中，选择的左窗格中的**呼叫质量仪表板**。</span><span class="sxs-lookup"><span data-stu-id="fabd9-130">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
    
  
4. <span data-ttu-id="fabd9-131">在打开页上，使用您的全局管理员帐户或 Microsoft 团队服务管理员帐户登录，然后提供出现提示时的帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-131">On the page that opens, sign in with your Global Administrator account or Microsoft Teams Service Admin account, and then provide the credentials for the account when prompted.</span></span>
    
     ![CQD 登录](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="fabd9-133">登录，一旦被激活后后, CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-133">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="fabd9-134">可能需要几个小时处理数据不足，无法在报表中显示有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="fabd9-134">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 
  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="fabd9-135">联机为 Microsoft 团队的呼叫质量仪表板和 Skype for Business 的功能</span><span class="sxs-lookup"><span data-stu-id="fabd9-135">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span> 
<span data-ttu-id="fabd9-136"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="fabd9-136"></span></span>

<span data-ttu-id="fabd9-137">CQD 摘要报告提供计划的详细的报告功能的子集。</span><span class="sxs-lookup"><span data-stu-id="fabd9-137">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="fabd9-138">下面总结了两种版本之间的差异：</span><span class="sxs-lookup"><span data-stu-id="fabd9-138">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="fabd9-139">**功能**</span><span class="sxs-lookup"><span data-stu-id="fabd9-139">**Feature**</span></span>|<span data-ttu-id="fabd9-140">**摘要报告**</span><span class="sxs-lookup"><span data-stu-id="fabd9-140">**Summary Reports**</span></span>|<span data-ttu-id="fabd9-141">**详细的报告**</span><span class="sxs-lookup"><span data-stu-id="fabd9-141">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fabd9-142">应用程序共享指标</span><span class="sxs-lookup"><span data-stu-id="fabd9-142">Application sharing metric</span></span>  <br/> |<span data-ttu-id="fabd9-143">否</span><span class="sxs-lookup"><span data-stu-id="fabd9-143">No</span></span>  <br/> |<span data-ttu-id="fabd9-144">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-144">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-145">构建信息支持的客户</span><span class="sxs-lookup"><span data-stu-id="fabd9-145">Customer building information support</span></span>  <br/> |<span data-ttu-id="fabd9-146">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-146">Yes</span></span>  <br/> |<span data-ttu-id="fabd9-147">是 </span><span class="sxs-lookup"><span data-stu-id="fabd9-147">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-148">客户终结点的信息支持</span><span class="sxs-lookup"><span data-stu-id="fabd9-148">Customer endpoint information support</span></span>  <br/> |<span data-ttu-id="fabd9-149">仅在 cqd.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fabd9-149">Only in cqd.teams.microsoft.com</span></span>  <br/> |<span data-ttu-id="fabd9-150">仅在 cqd.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fabd9-150">Only in cqd.teams.microsoft.com</span></span>  <br/> |
|<span data-ttu-id="fabd9-151">深入分析支持</span><span class="sxs-lookup"><span data-stu-id="fabd9-151">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="fabd9-152">否</span><span class="sxs-lookup"><span data-stu-id="fabd9-152">No</span></span>  <br/> |<span data-ttu-id="fabd9-153">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-153">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-154">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="fabd9-154">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="fabd9-155">否</span><span class="sxs-lookup"><span data-stu-id="fabd9-155">No</span></span>  <br/> |<span data-ttu-id="fabd9-156">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-156">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-157">即开报告</span><span class="sxs-lookup"><span data-stu-id="fabd9-157">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="fabd9-158">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-158">Yes</span></span>  <br/> |<span data-ttu-id="fabd9-159">是 </span><span class="sxs-lookup"><span data-stu-id="fabd9-159">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-160">概述报告</span><span class="sxs-lookup"><span data-stu-id="fabd9-160">Overview reports</span></span>  <br/> |<span data-ttu-id="fabd9-161">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-161">Yes</span></span>  <br/> |<span data-ttu-id="fabd9-162">是 </span><span class="sxs-lookup"><span data-stu-id="fabd9-162">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-163">每个用户报告集</span><span class="sxs-lookup"><span data-stu-id="fabd9-163">Per-user report set</span></span>  <br/> |<span data-ttu-id="fabd9-164">否</span><span class="sxs-lookup"><span data-stu-id="fabd9-164">No</span></span>  <br/> |<span data-ttu-id="fabd9-165">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-165">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-166">设置自定义报表 （添加、 删除、 修改报表）</span><span class="sxs-lookup"><span data-stu-id="fabd9-166">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="fabd9-167">否</span><span class="sxs-lookup"><span data-stu-id="fabd9-167">No</span></span>  <br/> |<span data-ttu-id="fabd9-168">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-168">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-169">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="fabd9-169">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="fabd9-170">否</span><span class="sxs-lookup"><span data-stu-id="fabd9-170">No</span></span>  <br/> |<span data-ttu-id="fabd9-171">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-171">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-172">视频指标</span><span class="sxs-lookup"><span data-stu-id="fabd9-172">Video metrics</span></span>  <br/> |<span data-ttu-id="fabd9-173">否</span><span class="sxs-lookup"><span data-stu-id="fabd9-173">No</span></span>  <br/> |<span data-ttu-id="fabd9-174">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-174">Yes</span></span>  <br/> |
|<span data-ttu-id="fabd9-175">可用的数据量</span><span class="sxs-lookup"><span data-stu-id="fabd9-175">Amount of data available</span></span>  <br/> |<span data-ttu-id="fabd9-176">过去 6 个月</span><span class="sxs-lookup"><span data-stu-id="fabd9-176">Last 6 months</span></span>  <br/> |<span data-ttu-id="fabd9-177">过去 6 个月</span><span class="sxs-lookup"><span data-stu-id="fabd9-177">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="fabd9-178">Microsoft 团队数据</span><span class="sxs-lookup"><span data-stu-id="fabd9-178">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="fabd9-179">是</span><span class="sxs-lookup"><span data-stu-id="fabd9-179">Yes</span></span>  <br/> |<span data-ttu-id="fabd9-180">是 </span><span class="sxs-lookup"><span data-stu-id="fabd9-180">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="fabd9-181">即开报告</span><span class="sxs-lookup"><span data-stu-id="fabd9-181">Out-of-the-box reports</span></span>

<span data-ttu-id="fabd9-182">CQD 这两个版本提供的-全新体验，请为您提供呼叫质量指标，无需创建任何新的报表。</span><span class="sxs-lookup"><span data-stu-id="fabd9-182">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="fabd9-183">一旦在后端处理数据时，您可以开始查看在报告呼叫质量数据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-183">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="fabd9-184">概述报告</span><span class="sxs-lookup"><span data-stu-id="fabd9-184">Overview reports</span></span>

<span data-ttu-id="fabd9-185">CQD 这两个版本提供高级入口点的整个呼叫质量信息，但信息显示在摘要报表的方式是不同的详细报告。</span><span class="sxs-lookup"><span data-stu-id="fabd9-185">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="fabd9-186">摘要报告提供使用户能够快速浏览和了解整个呼叫质量状态和趋势的简化的选项卡式的页面报表视图。</span><span class="sxs-lookup"><span data-stu-id="fabd9-186">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="fabd9-187">四个选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="fabd9-187">The four tabs include:</span></span>
  
- <span data-ttu-id="fabd9-188">**总体呼叫质量**-提供有关所有流，即服务器到客户端流聚合和客户端客户端流，以及单独的服务器到客户端和客户端客户端流时，在每月和每日的趋势的窗体的信息。</span><span class="sxs-lookup"><span data-stu-id="fabd9-188">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="fabd9-189">**服务器的客户端**-服务器和客户端终结点之间的流提供其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="fabd9-189">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="fabd9-190">**客户端的客户端**-提供两个客户端终结点之间的流的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="fabd9-190">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="fabd9-191">**语音质量 SLA** -提供有关呼叫的业务联机语音质量 SLA Skype 中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="fabd9-191">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="fabd9-192">总体呼叫质量选项卡</span><span class="sxs-lookup"><span data-stu-id="fabd9-192">Overall Call Quality tab</span></span>

<span data-ttu-id="fabd9-193">使用此选项卡上的数据评估呼叫质量状态和趋势看流计数和质量欠佳的百分比。</span><span class="sxs-lookup"><span data-stu-id="fabd9-193">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="fabd9-194">在右上角的图例显示的颜色和可视元素表示这些指标。</span><span class="sxs-lookup"><span data-stu-id="fabd9-194">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![CQD 数据键](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="fabd9-196">流分为三个组： 良好、 不佳，和未分类。</span><span class="sxs-lookup"><span data-stu-id="fabd9-196">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="fabd9-197">存在进行还计算*差 %* 值的授予您的流比率归类为*质量欠佳*到总保密的流计数。</span><span class="sxs-lookup"><span data-stu-id="fabd9-197">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="fabd9-198">由于*差 %= 差流 / （不佳流 + 良好流） \* 100* ，这将使*差 %* 受到与多个*自解除保密*流状态。</span><span class="sxs-lookup"><span data-stu-id="fabd9-198">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="fabd9-199">有关将用于分类为质量欠佳或良好流，请参阅[呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="fabd9-199">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="fabd9-200">使用左侧刻度度量值流计数。</span><span class="sxs-lookup"><span data-stu-id="fabd9-200">Use the scale on the left to measure the stream count values.</span></span>
  
![CQD 数据计数](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="fabd9-202">使用右侧比例来测量的差 %值。</span><span class="sxs-lookup"><span data-stu-id="fabd9-202">Use the scale on the right to measure the Poor % values.</span></span>
  
![CQD 数据每年会](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="fabd9-204">您还可以通过将鼠标悬停在条上获取实际数值。</span><span class="sxs-lookup"><span data-stu-id="fabd9-204">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fabd9-205">下面的示例是一个非常小示例数据集，从，值不是实际的实际部署。</span><span class="sxs-lookup"><span data-stu-id="fabd9-205">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![CQD 数据数字](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="fabd9-207">整体流卷是确定如何相关差的计算的百分比的重要因素。</span><span class="sxs-lookup"><span data-stu-id="fabd9-207">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="fabd9-208">整体流量较小，不可靠的报告不佳的百分比值。</span><span class="sxs-lookup"><span data-stu-id="fabd9-208">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="fabd9-209">服务器到客户端选项卡和客户端客户端选项卡</span><span class="sxs-lookup"><span data-stu-id="fabd9-209">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="fabd9-210">以下两个选项卡提供其他详细信息发生在其终结点到终结点方案中的流。</span><span class="sxs-lookup"><span data-stu-id="fabd9-210">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="fabd9-211">这两个选项卡具有四个可折叠部分，表示将在其下流媒体流的四种情况。</span><span class="sxs-lookup"><span data-stu-id="fabd9-211">Both tabs have four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="fabd9-212">有线内</span><span class="sxs-lookup"><span data-stu-id="fabd9-212">Wired Inside</span></span>
    
- <span data-ttu-id="fabd9-213">外部有线</span><span class="sxs-lookup"><span data-stu-id="fabd9-213">Wired Outside</span></span>
    
- <span data-ttu-id="fabd9-214">Wifi 内部</span><span class="sxs-lookup"><span data-stu-id="fabd9-214">Wifi Inside</span></span>
    
- <span data-ttu-id="fabd9-215">Wifi 以外</span><span class="sxs-lookup"><span data-stu-id="fabd9-215">Wifi Outside</span></span>
    
#### <a name="inside-test"></a><span data-ttu-id="fabd9-216">内部测试</span><span class="sxs-lookup"><span data-stu-id="fabd9-216">Inside Test</span></span>

<span data-ttu-id="fabd9-217">在处理期间，CQD 后端分类为*内部*或*外部*使用构建信息流，如果存在。</span><span class="sxs-lookup"><span data-stu-id="fabd9-217">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="fabd9-218">终结点的每个流是与子网地址关联。</span><span class="sxs-lookup"><span data-stu-id="fabd9-218">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="fabd9-219">如果子网为子 InsideCorp 标记中上载的构建信息的列表中，将其视为*内部*。</span><span class="sxs-lookup"><span data-stu-id="fabd9-219">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="fabd9-220">如果在构建信息具有尚未上载内, 测试将始终为*外部*分类流。</span><span class="sxs-lookup"><span data-stu-id="fabd9-220">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="fabd9-221">请注意，内部服务器到客户端方案的测试只考虑客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="fabd9-221">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="fabd9-222">因为服务器始终之外从用户的角度来看，这不占测试中。</span><span class="sxs-lookup"><span data-stu-id="fabd9-222">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="fabd9-223">与 wifi 有线</span><span class="sxs-lookup"><span data-stu-id="fabd9-223">Wired vs. wifi</span></span>

<span data-ttu-id="fabd9-224">指示名称，这是基于客户端连接类型分类标准。</span><span class="sxs-lookup"><span data-stu-id="fabd9-224">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="fabd9-225">同样，服务器始终有线，且该不包含计算中。</span><span class="sxs-lookup"><span data-stu-id="fabd9-225">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fabd9-226">如果两个终结点之一连接到 Wifi 网络给定流，然后归为 Wifi CQD 中。</span><span class="sxs-lookup"><span data-stu-id="fabd9-226">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="fabd9-227">选择要查看报告中的产品数据</span><span class="sxs-lookup"><span data-stu-id="fabd9-227">Selecting product data to see in reports</span></span>
<a name="BKMKProductFilter"></a>

<span data-ttu-id="fabd9-228">在摘要和位置增强报告中，您可以使用**产品筛选器**下拉列表以显示所有产品数据，只有 Microsoft 团队数据或仅联机业务数据的 Skype。</span><span class="sxs-lookup"><span data-stu-id="fabd9-228">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![屏幕快照显示了具有所有选项、 Microsoft 团队和 for Business 的 Skype 的产品筛选器控件。](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="fabd9-230">在详细的报告，您可以使用**是团队**维度筛选 Online 业务数据的报表定义一部分的 Microsoft 团队或 Skype 的数据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-230">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="fabd9-231">上载租户数据信息</span><span class="sxs-lookup"><span data-stu-id="fabd9-231">Upload Tenant Data information</span></span>
<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="fabd9-232">CQD 摘要报告仪表板包含一个**租户数据上载**的页，通过从右上角的设置菜单中选择**租户数据上载**访问。</span><span class="sxs-lookup"><span data-stu-id="fabd9-232">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="fabd9-233">此页用于 admins 上载自己的信息，如映射的 IP 地址和地理信息、 映射每个无线 AP 和其 MAC 地址、 终结点进行/模型/类型等的终结点的映射。</span><span class="sxs-lookup"><span data-stu-id="fabd9-233">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, mapping of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
![CQD 仪表板](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="fabd9-235">在**租户数据上载**页上，使用下拉菜单中选择上载的数据文件类型。</span><span class="sxs-lookup"><span data-stu-id="fabd9-235">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="fabd9-236">文件数据类型表示文件的内容 （例如，"Building"指的 IP 地址映射，生成以及其他地理信息，"终结点"指映射的终结点名称终结点进行/模型/类型到...信息）。</span><span class="sxs-lookup"><span data-stu-id="fabd9-236">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type…information).</span></span> <span data-ttu-id="fabd9-237">当前的 cqd.teams.microsoft.com 支持上载"Building"和"终结点"数据类型 (在预览阶段和正式并非尚未)，cqd.lync.com 只支持上载"构建"数据类型。</span><span class="sxs-lookup"><span data-stu-id="fabd9-237">Currently we support upload “Building” and “Endpoint” data types for cqd.teams.microsoft.com(in preview stage and not officially available yet), cqd.lync.com only supports upload "Building" data type.</span></span> <span data-ttu-id="fabd9-238">将与后续版本添加几个更多的数据类型。</span><span class="sxs-lookup"><span data-stu-id="fabd9-238">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="fabd9-239">选择后的文件数据类型，单击**浏览**选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="fabd9-239">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="fabd9-240">数据文件必须.tsv （制表符分隔值） 文件或.csv （以逗号分隔值） 文件。</span><span class="sxs-lookup"><span data-stu-id="fabd9-240">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="fabd9-241">如果使用.csv 文件，包含逗号分隔的任何字段必须用引号引起来，或已删除的逗号。</span><span class="sxs-lookup"><span data-stu-id="fabd9-241">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="fabd9-242">例如，如果您构建的名称是 NY，NY.csv 文件中其应以输入"NY，NY"。</span><span class="sxs-lookup"><span data-stu-id="fabd9-242">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="fabd9-243">数据文件必须是不超过 50 MB 的大小。</span><span class="sxs-lookup"><span data-stu-id="fabd9-243">The data file must be no larger than 50MB in size.</span></span>

   - <span data-ttu-id="fabd9-244">文件上载到 cqd.teams.microsoft.com 已扩展 1,000,000 以加速调制查询性能的行限制。</span><span class="sxs-lookup"><span data-stu-id="fabd9-244">File uploaded to cqd.teams.microsoft.com has expanded row limit of 1,000,000 to speed up query performance.</span></span> <span data-ttu-id="fabd9-245">我们可能会实施 cqd.lync.com 以及该限制。</span><span class="sxs-lookup"><span data-stu-id="fabd9-245">We may impose that limit on cqd.lync.com as well.</span></span>
    
   - <span data-ttu-id="fabd9-246">对于每个数据文件，文件中的每个列必须匹配一个预定义的数据类型，本主题后面所述。</span><span class="sxs-lookup"><span data-stu-id="fabd9-246">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="fabd9-247">选择数据文件之后，指定**开始日期**和 （可选）**指定的结束日期**。</span><span class="sxs-lookup"><span data-stu-id="fabd9-247">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="fabd9-248">选择后**开始日期**，选择**上载**以将文件上载到 CQD 服务器。</span><span class="sxs-lookup"><span data-stu-id="fabd9-248">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="fabd9-249">上载文件之前，请首先验证。</span><span class="sxs-lookup"><span data-stu-id="fabd9-249">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="fabd9-250">一旦验证，它在 Azure blob 存储。</span><span class="sxs-lookup"><span data-stu-id="fabd9-250">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="fabd9-251">如果验证失败或文件无法在 Azure 的 blob 存储请求更正文件显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="fabd9-251">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="fabd9-252">下图显示在数据文件中的列数不正确时出现错误。</span><span class="sxs-lookup"><span data-stu-id="fabd9-252">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![CQD 示例上载验证错误](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="fabd9-254">如果验证过程中不发生任何错误，将会成功上载文件。</span><span class="sxs-lookup"><span data-stu-id="fabd9-254">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="fabd9-255">您随后可以看到**我上载**表，其中显示所有上载文件的完整列表，该页面底部当前租户中上载的数据文件。</span><span class="sxs-lookup"><span data-stu-id="fabd9-255">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="fabd9-256">每个记录显示一个上载的租户数据文件的文件类型、 上次更新时间、 时间段、 说明、 删除图标和下载图标。</span><span class="sxs-lookup"><span data-stu-id="fabd9-256">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="fabd9-257">若要删除文件，请选择表中的回收站图标。</span><span class="sxs-lookup"><span data-stu-id="fabd9-257">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="fabd9-258">若要下载文件，在**下载**列中的表中选择下载图标。</span><span class="sxs-lookup"><span data-stu-id="fabd9-258">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![CQD 我上载表](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="fabd9-260">租户数据文件格式和结构</span><span class="sxs-lookup"><span data-stu-id="fabd9-260">Tenant data file format and structure</span></span>
<span data-ttu-id="fabd9-261"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="fabd9-261"></span></span>

### <a name="building-data-file"></a><span data-ttu-id="fabd9-262">正在创建数据文件</span><span class="sxs-lookup"><span data-stu-id="fabd9-262">Building data file</span></span>
<span data-ttu-id="fabd9-263">CQD 使用构建的第一个数据文件到呼叫记录的第一个 Subnet/Second 子网列显示构建/城市/国家/地区从展开网络 + NetworkRange 列中，然后加入子网列派生子网列...</span><span class="sxs-lookup"><span data-stu-id="fabd9-263">CQD uses Building data file by first derive Subnet column from expanding Network+NetworkRange column, then joining Subnet column to the call record’s First Subnet/Second Subnet column to show Building/City/Country/Region…</span></span> <span data-ttu-id="fabd9-264">信息。</span><span class="sxs-lookup"><span data-stu-id="fabd9-264">information.</span></span> <span data-ttu-id="fabd9-265">您上载的数据文件的格式必须满足以下内容以通过在上载之前验证检查。</span><span class="sxs-lookup"><span data-stu-id="fabd9-265">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="fabd9-266">文件必须.tsv 文件，这意味着在每个行中，列分隔选项卡上或以逗号分隔每一列的.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="fabd9-266">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="fabd9-267">数据文件的内容不包括表格标题。</span><span class="sxs-lookup"><span data-stu-id="fabd9-267">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="fabd9-268">不头，表示的数据文件的第一行应该真实数据，如"网络"等。</span><span class="sxs-lookup"><span data-stu-id="fabd9-268">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="fabd9-269">每个列的数据类型仅可以是字符串、 号码或 Bool。</span><span class="sxs-lookup"><span data-stu-id="fabd9-269">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="fabd9-270">如果它是数字，值必须是数值;如果是 Bool，值必须是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="fabd9-270">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="fabd9-271">每个列的数据类型为 string，如果数据可以为空 （但仍必须用相应的分隔符 （即，选项卡或逗号分隔） 分隔。</span><span class="sxs-lookup"><span data-stu-id="fabd9-271">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="fabd9-272">这只是分配该字段空字符串值。</span><span class="sxs-lookup"><span data-stu-id="fabd9-272">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="fabd9-273">必须为每个行的 14 列，每个列必须具有以下数据类型和列必须下表中列出的顺序：</span><span class="sxs-lookup"><span data-stu-id="fabd9-273">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="fabd9-274">**列名称**</span><span class="sxs-lookup"><span data-stu-id="fabd9-274">**Column Name**</span></span>|<span data-ttu-id="fabd9-275">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fabd9-275">**Data type**</span></span>|<span data-ttu-id="fabd9-276">**示例**</span><span class="sxs-lookup"><span data-stu-id="fabd9-276">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fabd9-277">网络</span><span class="sxs-lookup"><span data-stu-id="fabd9-277">Network</span></span>  <br/> |<span data-ttu-id="fabd9-278">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-278">String</span></span>  <br/> |<span data-ttu-id="fabd9-279">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="fabd9-279">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="fabd9-280">NetworkName</span><span class="sxs-lookup"><span data-stu-id="fabd9-280">NetworkName</span></span>  <br/> |<span data-ttu-id="fabd9-281">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-281">String</span></span>  <br/> |<span data-ttu-id="fabd9-282">美国/西雅图/西雅图-SEA-1</span><span class="sxs-lookup"><span data-stu-id="fabd9-282">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="fabd9-283">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="fabd9-283">NetworkRange</span></span>  <br/> |<span data-ttu-id="fabd9-284">数字</span><span class="sxs-lookup"><span data-stu-id="fabd9-284">Number</span></span>  <br/> |<span data-ttu-id="fabd9-285">26</span><span class="sxs-lookup"><span data-stu-id="fabd9-285">26</span></span>  <br/> |
|<span data-ttu-id="fabd9-286">BuildingName</span><span class="sxs-lookup"><span data-stu-id="fabd9-286">BuildingName</span></span>  <br/> |<span data-ttu-id="fabd9-287">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-287">String</span></span>  <br/> |<span data-ttu-id="fabd9-288">西雅图-SEA-1</span><span class="sxs-lookup"><span data-stu-id="fabd9-288">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="fabd9-289">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="fabd9-289">OwnershipType</span></span>  <br/> |<span data-ttu-id="fabd9-290">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-290">String</span></span>  <br/> |<span data-ttu-id="fabd9-291">Contoso</span><span class="sxs-lookup"><span data-stu-id="fabd9-291">Contoso</span></span>  <br/> |
|<span data-ttu-id="fabd9-292">BuildingType</span><span class="sxs-lookup"><span data-stu-id="fabd9-292">BuildingType</span></span>  <br/> |<span data-ttu-id="fabd9-293">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-293">String</span></span>  <br/> |<span data-ttu-id="fabd9-294">IT 终止</span><span class="sxs-lookup"><span data-stu-id="fabd9-294">IT Termination</span></span>  <br/> |
|<span data-ttu-id="fabd9-295">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="fabd9-295">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="fabd9-296">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-296">String</span></span>  <br/> |<span data-ttu-id="fabd9-297">Engineering</span><span class="sxs-lookup"><span data-stu-id="fabd9-297">Engineering</span></span>  <br/> |
|<span data-ttu-id="fabd9-298">城市</span><span class="sxs-lookup"><span data-stu-id="fabd9-298">City</span></span>  <br/> |<span data-ttu-id="fabd9-299">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-299">String</span></span>  <br/> |<span data-ttu-id="fabd9-300">西雅图</span><span class="sxs-lookup"><span data-stu-id="fabd9-300">Seattle</span></span>  <br/> |
|<span data-ttu-id="fabd9-301">ZipCode</span><span class="sxs-lookup"><span data-stu-id="fabd9-301">ZipCode</span></span>  <br/> |<span data-ttu-id="fabd9-302">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-302">String</span></span>  <br/> |<span data-ttu-id="fabd9-303">98001</span><span class="sxs-lookup"><span data-stu-id="fabd9-303">98001</span></span>  <br/> |
|<span data-ttu-id="fabd9-304">国家/地区</span><span class="sxs-lookup"><span data-stu-id="fabd9-304">Country</span></span>  <br/> |<span data-ttu-id="fabd9-305">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-305">String</span></span>  <br/> |<span data-ttu-id="fabd9-306">我们</span><span class="sxs-lookup"><span data-stu-id="fabd9-306">US</span></span>  <br/> |
|<span data-ttu-id="fabd9-307">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="fabd9-307">State</span></span>  <br/> |<span data-ttu-id="fabd9-308">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-308">String</span></span>  <br/> |<span data-ttu-id="fabd9-309">WA</span><span class="sxs-lookup"><span data-stu-id="fabd9-309">WA</span></span>  <br/> |
|<span data-ttu-id="fabd9-310">区域</span><span class="sxs-lookup"><span data-stu-id="fabd9-310">Region</span></span>  <br/> |<span data-ttu-id="fabd9-311">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-311">String</span></span>  <br/> |<span data-ttu-id="fabd9-312">MSU</span><span class="sxs-lookup"><span data-stu-id="fabd9-312">MSUS</span></span>  <br/> |
|<span data-ttu-id="fabd9-313">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="fabd9-313">InsideCorp</span></span>  <br/> |<span data-ttu-id="fabd9-314">Bool</span><span class="sxs-lookup"><span data-stu-id="fabd9-314">Bool</span></span>  <br/> |<span data-ttu-id="fabd9-315">1</span><span class="sxs-lookup"><span data-stu-id="fabd9-315">1</span></span>  <br/> |
|<span data-ttu-id="fabd9-316">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="fabd9-316">ExpressRoute</span></span>  <br/> |<span data-ttu-id="fabd9-317">Bool</span><span class="sxs-lookup"><span data-stu-id="fabd9-317">Bool</span></span>  <br/> |<span data-ttu-id="fabd9-318">0</span><span class="sxs-lookup"><span data-stu-id="fabd9-318">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="fabd9-319">网络范围可以用于表示 supernet （单个路由前缀开头的几个子网的组合）。</span><span class="sxs-lookup"><span data-stu-id="fabd9-319">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="fabd9-320">所有新的生成上载将检查有任何重叠的区域。</span><span class="sxs-lookup"><span data-stu-id="fabd9-320">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="fabd9-321">如果先前已上载的生成文件，您应将当前文件下载并重新上载以找出任何重叠并再次上载之前修复问题。</span><span class="sxs-lookup"><span data-stu-id="fabd9-321">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="fabd9-322">重叠之前上载文件的任何情况可能会导致建筑物报告中的子网的错误映射。</span><span class="sxs-lookup"><span data-stu-id="fabd9-322">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="fabd9-323">某些 VPN 实现未准确报告的子网信息。</span><span class="sxs-lookup"><span data-stu-id="fabd9-323">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="fabd9-324">当将 VPN 子网添加到该生成文件，而不是一个条目的子网，建议的单独添加条目的 VPN 子网中每个地址作为单独的 32 位网络。</span><span class="sxs-lookup"><span data-stu-id="fabd9-324">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="fabd9-325">每行可以有相同的构建元数据。</span><span class="sxs-lookup"><span data-stu-id="fabd9-325">Each row can have the same building metadata.</span></span> <span data-ttu-id="fabd9-326">例如，而不是一个 172.16.18.0/24 行中，您应具有 256 行，通过为每个地址之间 172.16.18.0/32 172.16.18.255/32，非独占一行。</span><span class="sxs-lookup"><span data-stu-id="fabd9-326">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 

### <a name="endpoint-data-file"></a><span data-ttu-id="fabd9-327">终结点数据文件</span><span class="sxs-lookup"><span data-stu-id="fabd9-327">Endpoint data file</span></span>
<span data-ttu-id="fabd9-328">CQD 使用终结点数据文件通过其 EndpointName 列加入到呼叫记录的第一个客户端终结点 Name/Second 客户端终结点名称列显示终结点进行/模型/类型信息。</span><span class="sxs-lookup"><span data-stu-id="fabd9-328">CQD uses Endpoint data file by joining its EndpointName column to the call record’s First Client Endpoint Name/Second Client Endpoint Name column to show Endpoint Make/Model/Type information.</span></span> <span data-ttu-id="fabd9-329">您上载的数据文件的格式必须满足以下内容以通过在上载之前验证检查。</span><span class="sxs-lookup"><span data-stu-id="fabd9-329">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>

- <span data-ttu-id="fabd9-330">文件必须.tsv 文件，这意味着在每个行中，列分隔选项卡上或以逗号分隔每一列的.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="fabd9-330">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>

- <span data-ttu-id="fabd9-331">数据文件的内容不包括表格标题。</span><span class="sxs-lookup"><span data-stu-id="fabd9-331">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="fabd9-332">这意味着第一行的数据文件应真实数据，不像"EndpointName，"头等。</span><span class="sxs-lookup"><span data-stu-id="fabd9-332">That means the first line of the data file should be real data, not headers like "EndpointName," etc.</span></span>

- <span data-ttu-id="fabd9-333">每个列的数据类型只能字符串和它应具有不能超过 64 个字符，这是最大允许长度。</span><span class="sxs-lookup"><span data-stu-id="fabd9-333">For each column, the data type can only be String and it should have no more than 64 chars, which is maximum allowed length.</span></span>

- <span data-ttu-id="fabd9-334">每个列的数据可以为空 （但仍必须用相应的分隔符 （即，选项卡或逗号分隔） 分隔。</span><span class="sxs-lookup"><span data-stu-id="fabd9-334">For each column, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="fabd9-335">这只是分配该字段空字符串值。</span><span class="sxs-lookup"><span data-stu-id="fabd9-335">This just assigns that field an empty string value.</span></span>

- <span data-ttu-id="fabd9-336">必须为每个行的 7 列和列必须下表中列出的顺序。</span><span class="sxs-lookup"><span data-stu-id="fabd9-336">There must be 7 columns for each row and the columns must be in the order listed in the following table.</span></span>

- <span data-ttu-id="fabd9-337">否则 EndpointName 必须唯一上载将由于重复的行失败，因为这会导致不正确加入。</span><span class="sxs-lookup"><span data-stu-id="fabd9-337">EndpointName must be unique otherwise upload will fail due to duplicate row as it will cause incorrect joining.</span></span>

-  <span data-ttu-id="fabd9-338">EndpointLabel1 EndpointLabel2、 EndpointLable3 是用户可自定义标签，也可以是空字符串或值用户更喜欢在如"IT 部门指定 2018年便携式计算机"，"资产标记 5678"...等。</span><span class="sxs-lookup"><span data-stu-id="fabd9-338">EndpointLabel1, EndpointLabel2, EndpointLable3 are user customizable labels, they can be empty strings or value users prefer such as “IT Department designated 2018 Laptop”, “Asset Tag 5678” …etc.</span></span>

|<span data-ttu-id="fabd9-339">**列名称**</span><span class="sxs-lookup"><span data-stu-id="fabd9-339">**Column Name**</span></span>|<span data-ttu-id="fabd9-340">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fabd9-340">**Data type**</span></span>|<span data-ttu-id="fabd9-341">**示例**</span><span class="sxs-lookup"><span data-stu-id="fabd9-341">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fabd9-342">EndpointName</span><span class="sxs-lookup"><span data-stu-id="fabd9-342">EndpointName</span></span>  <br/> |<span data-ttu-id="fabd9-343">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-343">String</span></span>  <br/> |<span data-ttu-id="fabd9-344">1409W3534</span><span class="sxs-lookup"><span data-stu-id="fabd9-344">1409W3534</span></span>  <br/> |
|<span data-ttu-id="fabd9-345">EndpointMake</span><span class="sxs-lookup"><span data-stu-id="fabd9-345">EndpointMake</span></span>  <br/> |<span data-ttu-id="fabd9-346">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-346">String</span></span>  <br/> |<span data-ttu-id="fabd9-347">Fabrikam Inc</span><span class="sxs-lookup"><span data-stu-id="fabd9-347">Fabrikam Inc</span></span>  <br/> |
|<span data-ttu-id="fabd9-348">EndpointModel</span><span class="sxs-lookup"><span data-stu-id="fabd9-348">EndpointModel</span></span>  <br/> |<span data-ttu-id="fabd9-349">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-349">String</span></span>  <br/> |<span data-ttu-id="fabd9-350">Fabrikam 模型 123</span><span class="sxs-lookup"><span data-stu-id="fabd9-350">Fabrikam Model 123</span></span>  <br/> |
|<span data-ttu-id="fabd9-351">EndpointType</span><span class="sxs-lookup"><span data-stu-id="fabd9-351">EndpointType</span></span>   <br/> |<span data-ttu-id="fabd9-352">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-352">String</span></span>  <br/> |<span data-ttu-id="fabd9-353">便携式计算机</span><span class="sxs-lookup"><span data-stu-id="fabd9-353">Laptop</span></span>  <br/> |
|<span data-ttu-id="fabd9-354">EndpointLabel1</span><span class="sxs-lookup"><span data-stu-id="fabd9-354">EndpointLabel1</span></span>  <br/> |<span data-ttu-id="fabd9-355">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-355">String</span></span>  <br/> |<span data-ttu-id="fabd9-356">指定的 IT 2018 便携式计算机</span><span class="sxs-lookup"><span data-stu-id="fabd9-356">IT designated 2018 Laptop</span></span>  <br/> |
|<span data-ttu-id="fabd9-357">EndpointLabel2</span><span class="sxs-lookup"><span data-stu-id="fabd9-357">EndpointLabel2</span></span>  <br/> |<span data-ttu-id="fabd9-358">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-358">String</span></span>  <br/> |<span data-ttu-id="fabd9-359">资产标记 5678</span><span class="sxs-lookup"><span data-stu-id="fabd9-359">Asset Tag 5678</span></span>  <br/> |
|<span data-ttu-id="fabd9-360">EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="fabd9-360">EndpointLabel3</span></span>  <br/> |<span data-ttu-id="fabd9-361">String</span><span class="sxs-lookup"><span data-stu-id="fabd9-361">String</span></span>  <br/> |<span data-ttu-id="fabd9-362">购买 2018</span><span class="sxs-lookup"><span data-stu-id="fabd9-362">Purchase 2018</span></span>   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="fabd9-363">详细的报告中的选择媒体类型</span><span class="sxs-lookup"><span data-stu-id="fabd9-363">Selecting media type in detailed reports</span></span>
<a name="BKMKMediaType"></a>

<span data-ttu-id="fabd9-364">详细的报告支持看质量和媒体可靠性的音频、 视频、 应用程序共享和基于视频的屏幕共享的媒体类型。</span><span class="sxs-lookup"><span data-stu-id="fabd9-364">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="fabd9-365">维度、 度量和特定于单个媒体类型的筛选器具有"音频"、"视频"、"的"或"VBSS"作为前缀。</span><span class="sxs-lookup"><span data-stu-id="fabd9-365">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![呼叫质量仪表板尺寸。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="fabd9-367">如果您想要查看的维度和度量的单个媒体类型，可能需要的新 MediaType 维度和筛选器。</span><span class="sxs-lookup"><span data-stu-id="fabd9-367">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="fabd9-368">例如，要让显示会话总数的计数不同媒体类型的报告，包括 MediaType 维度。</span><span class="sxs-lookup"><span data-stu-id="fabd9-368">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![呼叫质量仪表板总流计数。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="fabd9-370">相关主题</span><span class="sxs-lookup"><span data-stu-id="fabd9-370">Related topics</span></span>
[<span data-ttu-id="fabd9-371">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="fabd9-371">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="fabd9-372">使用呼叫分析解决质量欠佳的呼叫质量</span><span class="sxs-lookup"><span data-stu-id="fabd9-372">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="fabd9-373">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="fabd9-373">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
