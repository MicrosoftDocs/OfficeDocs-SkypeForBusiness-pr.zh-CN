---
title: 打开并使用通话质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
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
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: '了解如何打开和使用 Skype for Business Online 呼叫质量仪表板和获取通话质量的摘要报告。 '
ms.openlocfilehash: eaadd80030b04d5fb10fd8f29d656fe07e24a1db
ms.sourcegitcommit: ab259764dc50bdd52efed3abb1d065ee19486946
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "36393489"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="a70c3-103">打开和使用 Microsoft 团队和 Skype for business Online 的通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="a70c3-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="a70c3-104">了解如何配置 Office 365 组织以使用呼叫质量仪表板来监控通话质量。</span><span class="sxs-lookup"><span data-stu-id="a70c3-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="a70c3-105">Microsoft 团队和 Skype for business Online 的通话质量仪表板 (CQD) 使你可以深入了解使用 Microsoft 团队和 Skype for business 服务时所进行的通话质量。</span><span class="sxs-lookup"><span data-stu-id="a70c3-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="a70c3-106">本主题介绍了开始收集数据需要完成的步骤。</span><span class="sxs-lookup"><span data-stu-id="a70c3-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="a70c3-107">最新更改和更新</span><span class="sxs-lookup"><span data-stu-id="a70c3-107">Latest changes and updates</span></span>

<span data-ttu-id="a70c3-108">对 CQD 的最新更改如下所示:</span><span class="sxs-lookup"><span data-stu-id="a70c3-108">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="a70c3-109">除了 Skype for Business Online 数据之外, 还包括 Microsoft 团队数据。</span><span class="sxs-lookup"><span data-stu-id="a70c3-109">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="a70c3-110">摘要报告包括一个用于选择所有数据、Microsoft 团队数据或 Skype for Business Online 数据的产品筛选器。</span><span class="sxs-lookup"><span data-stu-id="a70c3-110">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="a70c3-111">视频和 VBSS 流质量分类逻辑已更新。</span><span class="sxs-lookup"><span data-stu-id="a70c3-111">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="a70c3-112">有关最新分类器定义, 请参阅[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="a70c3-112">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="a70c3-113">有关[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)的列表, 请参阅本文。</span><span class="sxs-lookup"><span data-stu-id="a70c3-113">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a70c3-114">通过单击**好消息**中的链接可找到有关仪表板的更新和更改的信息!</span><span class="sxs-lookup"><span data-stu-id="a70c3-114">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="a70c3-115">仪表板上显示的标题。</span><span class="sxs-lookup"><span data-stu-id="a70c3-115">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="a70c3-116">激活 Microsoft 通话质量仪表板 (CQD) 摘要报告</span><span class="sxs-lookup"><span data-stu-id="a70c3-116">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="a70c3-117">在开始使用 CQD 之前, 你需要为你的 Office 365 组织激活它。</span><span class="sxs-lookup"><span data-stu-id="a70c3-117">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>

<span data-ttu-id="a70c3-118">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="a70c3-118">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
 
1. <span data-ttu-id="a70c3-119">使用 Microsoft 团队服务管理员帐户登录到你的 Office 365 组织, 然后选择 "**管理员**" 磁贴以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="a70c3-119">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="a70c3-120">在左窗格中的 "**管理中心**" 下, 选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。</span><span class="sxs-lookup"><span data-stu-id="a70c3-120">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
    
3. <span data-ttu-id="a70c3-121">在 "Microsoft 团队管理中心" 中, 在左窗格中选择 "**呼叫质量" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="a70c3-121">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
    
  
4. <span data-ttu-id="a70c3-122">在打开的页面上, 用全局管理员帐户或 Microsoft 团队服务管理员帐户登录, 然后在出现提示时提供帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="a70c3-122">On the page that opens, sign in with your Global Administrator account or Microsoft Teams Service Admin account, and then provide the credentials for the account when prompted.</span></span>
    
     ![显示凭据提示的屏幕截图](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="a70c3-124">登录后, 一旦激活, CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="a70c3-124">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="a70c3-125">可能需要几个小时才能处理足够多的数据, 以在报表中显示有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="a70c3-125">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 

<span data-ttu-id="a70c3-126">![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="a70c3-126">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="a70c3-127">使用管理员帐户登录到您的 Office 365 组织, 然后选择 "**管理员**" 磁贴以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="a70c3-127">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="a70c3-128">在左窗格中, 在 "**管理中心**" 下, 选择 " **skype** for Business" 以打开 skype for business 管理中心。</span><span class="sxs-lookup"><span data-stu-id="a70c3-128">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="a70c3-129">在 Skype for Business 管理中心中, 选择左窗格中的 "**工具**", 然后选择 " **Skype For Business Online 呼叫质量" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="a70c3-129">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![屏幕截图, 显示选择呼叫质量仪表板的屏幕截图](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="a70c3-131">在打开的页面上, 用全局管理员帐户登录, 然后在出现提示时提供帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="a70c3-131">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![显示凭据提示的屏幕截图](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="a70c3-133">登录后, 一旦激活, CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="a70c3-133">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>


  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="a70c3-134">Microsoft 团队和 Skype for business Online 的通话质量仪表板的功能</span><span class="sxs-lookup"><span data-stu-id="a70c3-134">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span> 
<span data-ttu-id="a70c3-135"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="a70c3-135"></span></span>

<span data-ttu-id="a70c3-136">CQD 摘要报告提供为详细报告规划的功能的子集。</span><span class="sxs-lookup"><span data-stu-id="a70c3-136">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="a70c3-137">下面总结了这两个版本之间的差异:</span><span class="sxs-lookup"><span data-stu-id="a70c3-137">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="a70c3-138">**功能**</span><span class="sxs-lookup"><span data-stu-id="a70c3-138">**Feature**</span></span>|<span data-ttu-id="a70c3-139">**摘要报告**</span><span class="sxs-lookup"><span data-stu-id="a70c3-139">**Summary Reports**</span></span>|<span data-ttu-id="a70c3-140">**详细报告**</span><span class="sxs-lookup"><span data-stu-id="a70c3-140">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a70c3-141">应用程序共享跃点数</span><span class="sxs-lookup"><span data-stu-id="a70c3-141">Application sharing metric</span></span>  <br/> |<span data-ttu-id="a70c3-142">否</span><span class="sxs-lookup"><span data-stu-id="a70c3-142">No</span></span>  <br/> |<span data-ttu-id="a70c3-143">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-143">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-144">客户构建信息支持</span><span class="sxs-lookup"><span data-stu-id="a70c3-144">Customer building information support</span></span>  <br/> |<span data-ttu-id="a70c3-145">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-145">Yes</span></span>  <br/> |<span data-ttu-id="a70c3-146">是 </span><span class="sxs-lookup"><span data-stu-id="a70c3-146">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-147">客户终结点信息支持</span><span class="sxs-lookup"><span data-stu-id="a70c3-147">Customer endpoint information support</span></span>  <br/> |<span data-ttu-id="a70c3-148">仅在 cqd.teams.microsoft.com 中</span><span class="sxs-lookup"><span data-stu-id="a70c3-148">Only in cqd.teams.microsoft.com</span></span>  <br/> |<span data-ttu-id="a70c3-149">仅在 cqd.teams.microsoft.com 中</span><span class="sxs-lookup"><span data-stu-id="a70c3-149">Only in cqd.teams.microsoft.com</span></span>  <br/> |
|<span data-ttu-id="a70c3-150">向下钻取分析支持</span><span class="sxs-lookup"><span data-stu-id="a70c3-150">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="a70c3-151">否</span><span class="sxs-lookup"><span data-stu-id="a70c3-151">No</span></span>  <br/> |<span data-ttu-id="a70c3-152">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-152">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-153">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="a70c3-153">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="a70c3-154">否</span><span class="sxs-lookup"><span data-stu-id="a70c3-154">No</span></span>  <br/> |<span data-ttu-id="a70c3-155">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-155">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-156">现成的报表</span><span class="sxs-lookup"><span data-stu-id="a70c3-156">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="a70c3-157">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-157">Yes</span></span>  <br/> |<span data-ttu-id="a70c3-158">是 </span><span class="sxs-lookup"><span data-stu-id="a70c3-158">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-159">概述报表</span><span class="sxs-lookup"><span data-stu-id="a70c3-159">Overview reports</span></span>  <br/> |<span data-ttu-id="a70c3-160">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-160">Yes</span></span>  <br/> |<span data-ttu-id="a70c3-161">是 </span><span class="sxs-lookup"><span data-stu-id="a70c3-161">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-162">每用户报告集</span><span class="sxs-lookup"><span data-stu-id="a70c3-162">Per-user report set</span></span>  <br/> |<span data-ttu-id="a70c3-163">否</span><span class="sxs-lookup"><span data-stu-id="a70c3-163">No</span></span>  <br/> |<span data-ttu-id="a70c3-164">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-164">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-165">报表集自定义 (添加、删除、修改报表)</span><span class="sxs-lookup"><span data-stu-id="a70c3-165">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="a70c3-166">否</span><span class="sxs-lookup"><span data-stu-id="a70c3-166">No</span></span>  <br/> |<span data-ttu-id="a70c3-167">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-167">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-168">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="a70c3-168">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="a70c3-169">否</span><span class="sxs-lookup"><span data-stu-id="a70c3-169">No</span></span>  <br/> |<span data-ttu-id="a70c3-170">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-170">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-171">视频指标</span><span class="sxs-lookup"><span data-stu-id="a70c3-171">Video metrics</span></span>  <br/> |<span data-ttu-id="a70c3-172">否</span><span class="sxs-lookup"><span data-stu-id="a70c3-172">No</span></span>  <br/> |<span data-ttu-id="a70c3-173">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-173">Yes</span></span>  <br/> |
|<span data-ttu-id="a70c3-174">可用数据量</span><span class="sxs-lookup"><span data-stu-id="a70c3-174">Amount of data available</span></span>  <br/> |<span data-ttu-id="a70c3-175">过去6个月</span><span class="sxs-lookup"><span data-stu-id="a70c3-175">Last 6 months</span></span>  <br/> |<span data-ttu-id="a70c3-176">过去6个月</span><span class="sxs-lookup"><span data-stu-id="a70c3-176">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="a70c3-177">Microsoft 团队数据</span><span class="sxs-lookup"><span data-stu-id="a70c3-177">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="a70c3-178">是</span><span class="sxs-lookup"><span data-stu-id="a70c3-178">Yes</span></span>  <br/> |<span data-ttu-id="a70c3-179">是 </span><span class="sxs-lookup"><span data-stu-id="a70c3-179">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="a70c3-180">现成的报表</span><span class="sxs-lookup"><span data-stu-id="a70c3-180">Out-of-the-box reports</span></span>

<span data-ttu-id="a70c3-181">这两个版本的 CQD 都提供全新的体验, 从而为你提供了无需创建任何新报表的通话质量指标。</span><span class="sxs-lookup"><span data-stu-id="a70c3-181">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="a70c3-182">在后端处理完数据后, 您可以在报告中开始查看通话质量数据。</span><span class="sxs-lookup"><span data-stu-id="a70c3-182">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="a70c3-183">概述报表</span><span class="sxs-lookup"><span data-stu-id="a70c3-183">Overview reports</span></span>

<span data-ttu-id="a70c3-184">CQD 的两个版本都为整体通话质量信息提供高级别的入口点, 但在摘要报告中显示信息的方式与详细报告不同。</span><span class="sxs-lookup"><span data-stu-id="a70c3-184">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="a70c3-185">摘要报告提供简化的选项卡式页面报告视图, 使用户可以快速浏览并理解整体通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="a70c3-185">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="a70c3-186">四个选项卡包括:</span><span class="sxs-lookup"><span data-stu-id="a70c3-186">The four tabs include:</span></span>
  
- <span data-ttu-id="a70c3-187">**整体通话质量**-提供有关所有流的信息, 这些流是服务器客户端流和客户端客户端流以及独立的服务器客户端和客户端客户端流 (按月和每天的趋势的形式)。</span><span class="sxs-lookup"><span data-stu-id="a70c3-187">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="a70c3-188">**服务器-客户**端-提供服务器和客户端终结点之间的流的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="a70c3-188">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="a70c3-189">**客户**端-客户端-提供两个客户端终结点之间的数据流的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="a70c3-189">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="a70c3-190">**语音质量 SLA** -提供有关 Skype For Business Online 语音质量 SLA 中所含通话的信息。</span><span class="sxs-lookup"><span data-stu-id="a70c3-190">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="a70c3-191">"整体通话质量" 选项卡</span><span class="sxs-lookup"><span data-stu-id="a70c3-191">Overall Call Quality tab</span></span>

<span data-ttu-id="a70c3-192">使用此选项卡上的数据, 通过查看流计数和较差的百分比来评估通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="a70c3-192">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="a70c3-193">右上角的图例将显示哪些颜色和视觉元素表示这些指标。</span><span class="sxs-lookup"><span data-stu-id="a70c3-193">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![显示 "通话质量" 选项卡的屏幕截图](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="a70c3-195">流分为三个组: "完好"、"差" 和 "未分类"。</span><span class="sxs-lookup"><span data-stu-id="a70c3-195">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="a70c3-196">还计算出的*百分比*值太差, 可让你将流的比率划分为*较差*的分类流计数。</span><span class="sxs-lookup"><span data-stu-id="a70c3-196">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="a70c3-197">由于*较差的% = 不良流/(差流 + 正常流) \* 100* , 因此\*\* 不受与多个未*分类*流的影响导致不受影响。</span><span class="sxs-lookup"><span data-stu-id="a70c3-197">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="a70c3-198">对于用于将流分类为差或好的内容, 请参阅["呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。</span><span class="sxs-lookup"><span data-stu-id="a70c3-198">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="a70c3-199">使用左侧的刻度测量流计数值。</span><span class="sxs-lookup"><span data-stu-id="a70c3-199">Use the scale on the left to measure the stream count values.</span></span>
  
![显示流计数值的屏幕截图](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="a70c3-201">使用右侧的刻度测量差的百分比值。</span><span class="sxs-lookup"><span data-stu-id="a70c3-201">Use the scale on the right to measure the Poor % values.</span></span>
  
![显示% 值差的屏幕截图](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="a70c3-203">也可以通过将鼠标悬停在条上来获取实际数值。</span><span class="sxs-lookup"><span data-stu-id="a70c3-203">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a70c3-204">下面的示例来自非常小的示例数据集, 并且值对于实际部署不切合实际。</span><span class="sxs-lookup"><span data-stu-id="a70c3-204">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![显示使用鼠标访问数据的屏幕截图](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="a70c3-206">整个流卷是确定计算出的较差百分比的相关程度的重要因素。</span><span class="sxs-lookup"><span data-stu-id="a70c3-206">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="a70c3-207">总体流的数量越小, 报告的百分比值越低越可靠。</span><span class="sxs-lookup"><span data-stu-id="a70c3-207">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="a70c3-208">服务器-客户端选项卡和客户端-客户端选项卡</span><span class="sxs-lookup"><span data-stu-id="a70c3-208">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="a70c3-209">这两个选项卡提供了在其终结点到终结点方案中发生的流的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="a70c3-209">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="a70c3-210">"服务器-客户端" 选项卡具有四个可折叠的部分, 表示媒体流将流经的四个方案。</span><span class="sxs-lookup"><span data-stu-id="a70c3-210">The Server-Client tab has four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="a70c3-211">内部有线</span><span class="sxs-lookup"><span data-stu-id="a70c3-211">Wired Inside</span></span>
    
- <span data-ttu-id="a70c3-212">外部有线</span><span class="sxs-lookup"><span data-stu-id="a70c3-212">Wired Outside</span></span>
    
- <span data-ttu-id="a70c3-213">内部 Wifi</span><span class="sxs-lookup"><span data-stu-id="a70c3-213">Wifi Inside</span></span>
    
- <span data-ttu-id="a70c3-214">外部 Wifi</span><span class="sxs-lookup"><span data-stu-id="a70c3-214">Wifi Outside</span></span>

<span data-ttu-id="a70c3-215">同样, "客户端-客户端" 选项卡具有五个可折叠部分:</span><span class="sxs-lookup"><span data-stu-id="a70c3-215">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="a70c3-216">内部有线内部-有线内部</span><span class="sxs-lookup"><span data-stu-id="a70c3-216">Wired Inside - Wired Inside</span></span>

- <span data-ttu-id="a70c3-217">有线内部-有线外部</span><span class="sxs-lookup"><span data-stu-id="a70c3-217">Wired Inside - Wired Outside</span></span>

- <span data-ttu-id="a70c3-218">有线外部-有线外部</span><span class="sxs-lookup"><span data-stu-id="a70c3-218">Wired Outside - Wired Outside</span></span>

- <span data-ttu-id="a70c3-219">内部的有线内部-Wifi</span><span class="sxs-lookup"><span data-stu-id="a70c3-219">Wired Inside - Wifi Inside</span></span>

- <span data-ttu-id="a70c3-220">有线内部-Wifi 外</span><span class="sxs-lookup"><span data-stu-id="a70c3-220">Wired Inside - Wifi Outside</span></span>
    
    
#### <a name="inside-test"></a><span data-ttu-id="a70c3-221">内部测试</span><span class="sxs-lookup"><span data-stu-id="a70c3-221">Inside Test</span></span>

<span data-ttu-id="a70c3-222">在处理期间, CQD 后端使用建筑物信息将流分类为*内部*或*外部*流 (如果存在)。</span><span class="sxs-lookup"><span data-stu-id="a70c3-222">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="a70c3-223">每个流的终结点与子网地址相关联。</span><span class="sxs-lookup"><span data-stu-id="a70c3-223">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="a70c3-224">如果子网位于上载的生成信息中标记为 "InsideCorp" 的子网列表中, 则将其视为*内部*。</span><span class="sxs-lookup"><span data-stu-id="a70c3-224">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="a70c3-225">如果尚未上载生成信息, 则内部测试将始终将流分类为*外部*。</span><span class="sxs-lookup"><span data-stu-id="a70c3-225">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="a70c3-226">请注意, 内部测试服务器-客户端方案仅考虑客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="a70c3-226">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="a70c3-227">由于服务器始终来自用户的视角, 因此不会在测试中考虑。</span><span class="sxs-lookup"><span data-stu-id="a70c3-227">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="a70c3-228">有线与 wifi</span><span class="sxs-lookup"><span data-stu-id="a70c3-228">Wired vs. wifi</span></span>

<span data-ttu-id="a70c3-229">根据名称指示, 这是基于客户端连接类型的分类标准。</span><span class="sxs-lookup"><span data-stu-id="a70c3-229">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="a70c3-230">同样, 服务器始终是有线的, 并且不会包含在计算中。</span><span class="sxs-lookup"><span data-stu-id="a70c3-230">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a70c3-231">如果有一个流, 则如果两个终结点中的一个终结点连接到 Wifi 网络, 则会在 CQD 中将其分类为 Wifi。</span><span class="sxs-lookup"><span data-stu-id="a70c3-231">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="a70c3-232">选择要在报表中查看的产品数据</span><span class="sxs-lookup"><span data-stu-id="a70c3-232">Selecting product data to see in reports</span></span>
<a name="BKMKProductFilter"></a>

<span data-ttu-id="a70c3-233">在摘要和位置增强的报表中, 你可以使用 "**产品筛选器**" 下拉列表显示所有产品数据、仅 Microsoft 团队数据或仅 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="a70c3-233">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![显示产品筛选器控件选项的屏幕截图](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="a70c3-235">在 "详细报告" 中, 你可以使用 "**属于团队**" 维度在定义报表的过程中将数据筛选到 Microsoft 团队或 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="a70c3-235">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="a70c3-236">上载租户数据信息</span><span class="sxs-lookup"><span data-stu-id="a70c3-236">Upload Tenant Data information</span></span>
<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="a70c3-237">CQD 摘要报告仪表板包括**租户数据上载**页面, 该页面从右上角的 "设置" 菜单中选择 "**租户数据上载**"。</span><span class="sxs-lookup"><span data-stu-id="a70c3-237">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="a70c3-238">此页面用于管理员上载其自己的信息, 例如 IP 地址和地理信息的映射、映射每个无线 AP 及其 MAC 地址、将终结点映射到终结点的映射以及模型/类型等。</span><span class="sxs-lookup"><span data-stu-id="a70c3-238">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, mapping of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
![显示呼叫质量仪表板的屏幕截图](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="a70c3-240">在 "**租户数据上载**" 页面上, 使用下拉菜单选择要上载的数据文件类型。</span><span class="sxs-lookup"><span data-stu-id="a70c3-240">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="a70c3-241">"文件" 数据类型表示文件的内容 (例如, "建筑物" 指的是 IP 地址和建筑物的映射以及其他地理信息, "终结点" 指的是将终结点名称映射到终结点 "生成/模型/类型 ..."。</span><span class="sxs-lookup"><span data-stu-id="a70c3-241">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type…</span></span> <span data-ttu-id="a70c3-242">信息)。</span><span class="sxs-lookup"><span data-stu-id="a70c3-242">information).</span></span> <span data-ttu-id="a70c3-243">目前, 我们支持为 cqd.teams.microsoft.com 上载 "建筑物" 和 "终结点" 数据类型 (在预览阶段和尚未正式提供), cqd.lync.com 仅支持上载 "建筑物" 数据类型。</span><span class="sxs-lookup"><span data-stu-id="a70c3-243">Currently we support uploading “Building” and “Endpoint” data types for cqd.teams.microsoft.com (in preview stage and not officially available yet), cqd.lync.com only supports uploading "Building" data type.</span></span> <span data-ttu-id="a70c3-244">后续版本中将添加更多数据类型。</span><span class="sxs-lookup"><span data-stu-id="a70c3-244">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="a70c3-245">选择文件数据类型后, 单击 "**浏览**" 以选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="a70c3-245">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="a70c3-246">数据文件必须为 tsv (以制表符分隔的值) 文件或 .csv (以逗号分隔的值) 文件。</span><span class="sxs-lookup"><span data-stu-id="a70c3-246">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="a70c3-247">如果使用 .csv 文件, 则包含逗号的任何字段都必须用引号引起来, 或者删除了逗号。</span><span class="sxs-lookup"><span data-stu-id="a70c3-247">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="a70c3-248">例如, 如果你的建筑物名称是纽约州, 则在 .csv 文件中, 它应输入为 "纽约州, NY"。</span><span class="sxs-lookup"><span data-stu-id="a70c3-248">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="a70c3-249">数据文件的大小不应大于50MB。</span><span class="sxs-lookup"><span data-stu-id="a70c3-249">The data file must be no larger than 50MB in size.</span></span>

   - <span data-ttu-id="a70c3-250">上载到 cqd.teams.microsoft.com 的文件具有展开的行限制 1000000, 以使查询性能更快。</span><span class="sxs-lookup"><span data-stu-id="a70c3-250">Files uploaded to cqd.teams.microsoft.com have an expanded row limit of 1,000,000 in order to keep query performance fast.</span></span> <span data-ttu-id="a70c3-251">我们也可能对 cqd.lync.com 施加该限制。</span><span class="sxs-lookup"><span data-stu-id="a70c3-251">We may impose that limit on cqd.lync.com as well.</span></span>
    
   - <span data-ttu-id="a70c3-252">对于每个数据文件, 文件中的每一列都必须与本主题后面部分所述的预定义数据类型匹配。</span><span class="sxs-lookup"><span data-stu-id="a70c3-252">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="a70c3-253">选择数据文件后, 指定 "**开始日期**", (可选)**指定结束日期**。</span><span class="sxs-lookup"><span data-stu-id="a70c3-253">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="a70c3-254">选择 "**开始日期**" 后, 选择 "**上传**" 将文件上传到 CQD 服务器。</span><span class="sxs-lookup"><span data-stu-id="a70c3-254">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="a70c3-255">上载文件之前, 首先验证该文件。</span><span class="sxs-lookup"><span data-stu-id="a70c3-255">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="a70c3-256">验证后, 它将存储在 Azure blob 中。</span><span class="sxs-lookup"><span data-stu-id="a70c3-256">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="a70c3-257">如果验证失败或文件无法存储在 Azure blob 中, 则会显示一条错误消息, 要求对文件进行更正。</span><span class="sxs-lookup"><span data-stu-id="a70c3-257">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="a70c3-258">下图显示了当数据文件中的列数不正确时出现的错误。</span><span class="sxs-lookup"><span data-stu-id="a70c3-258">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![显示上载验证错误的屏幕截图](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="a70c3-260">如果验证期间没有出现错误, 文件上载将成功。</span><span class="sxs-lookup"><span data-stu-id="a70c3-260">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="a70c3-261">然后, 你可以在 "我的上**传**" 表中看到上载的数据文件, 其中显示了当前租户在该页面底部的所有上载文件的完整列表。</span><span class="sxs-lookup"><span data-stu-id="a70c3-261">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="a70c3-262">每个记录显示一个上载的租户数据文件, 其中包含文件类型、上次更新时间、时间段、说明、删除图标和下载图标。</span><span class="sxs-lookup"><span data-stu-id="a70c3-262">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="a70c3-263">若要删除文件, 请选择表格中的垃圾桶图标。</span><span class="sxs-lookup"><span data-stu-id="a70c3-263">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="a70c3-264">若要下载文件, 请选择表格的 "**下载**" 列中的 "下载" 图标。</span><span class="sxs-lookup"><span data-stu-id="a70c3-264">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![显示 "我的上载" 表的屏幕截图](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. <span data-ttu-id="a70c3-266">请注意, 如果你选择使用多个生成数据文件或多个终结点数据文件, 则某些报表的运行速度将较慢。</span><span class="sxs-lookup"><span data-stu-id="a70c3-266">Note that if you choose to use multiple building data files or multiple endpoint data files, the operation speed of some reports will be slower.</span></span>

### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="a70c3-267">租户数据文件格式和结构</span><span class="sxs-lookup"><span data-stu-id="a70c3-267">Tenant data file format and structure</span></span>
<span data-ttu-id="a70c3-268"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="a70c3-268"></span></span>

### <a name="building-data-file"></a><span data-ttu-id="a70c3-269">生成数据文件</span><span class="sxs-lookup"><span data-stu-id="a70c3-269">Building data file</span></span>
<span data-ttu-id="a70c3-270">CQD 使用生成数据文件的方法是首先从展开 "网络 + NetworkRange" 列中派生出子网列, 然后将子网列联接到呼叫记录的第一个子网/第二个子网列, 以显示建筑物/城市/国家/地区 .。。</span><span class="sxs-lookup"><span data-stu-id="a70c3-270">CQD uses Building data file by first deriving the Subnet column from expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet/Second Subnet column to show Building/City/Country/Region…</span></span> <span data-ttu-id="a70c3-271">信息.</span><span class="sxs-lookup"><span data-stu-id="a70c3-271">information.</span></span> <span data-ttu-id="a70c3-272">你上载的数据文件的格式必须满足以下情况才能在上载之前通过验证检查。</span><span class="sxs-lookup"><span data-stu-id="a70c3-272">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="a70c3-273">文件必须是 tsv 文件, 这意味着在每行中, 列由选项卡或 .csv 文件分隔, 每个列由逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="a70c3-273">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="a70c3-274">数据文件的内容不包含表格标题。</span><span class="sxs-lookup"><span data-stu-id="a70c3-274">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="a70c3-275">这意味着数据文件的第一行应该是真实数据, 而不是像 "Network" 之类的标题。</span><span class="sxs-lookup"><span data-stu-id="a70c3-275">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="a70c3-276">对于每个列, 数据类型只能是 String、Number 或 Bool。</span><span class="sxs-lookup"><span data-stu-id="a70c3-276">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="a70c3-277">如果是数字, 则该值必须是一个数值;如果是 Bool, 则该值必须是0或1。</span><span class="sxs-lookup"><span data-stu-id="a70c3-277">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="a70c3-278">对于每一列, 如果数据类型为 string, 则数据可以为空 (但必须用适当的分隔符 (即制表符或逗号) 分隔。</span><span class="sxs-lookup"><span data-stu-id="a70c3-278">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="a70c3-279">这只是将该字段分配为空字符串值。</span><span class="sxs-lookup"><span data-stu-id="a70c3-279">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="a70c3-280">每一行必须有14列, 每一列必须具有以下数据类型, 并且列必须遵循下表中列出的顺序:</span><span class="sxs-lookup"><span data-stu-id="a70c3-280">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="a70c3-281">**列名称**</span><span class="sxs-lookup"><span data-stu-id="a70c3-281">**Column Name**</span></span>|<span data-ttu-id="a70c3-282">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a70c3-282">**Data type**</span></span>|<span data-ttu-id="a70c3-283">**示例**</span><span class="sxs-lookup"><span data-stu-id="a70c3-283">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a70c3-284">网络</span><span class="sxs-lookup"><span data-stu-id="a70c3-284">Network</span></span>  <br/> |<span data-ttu-id="a70c3-285">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-285">String</span></span>  <br/> |<span data-ttu-id="a70c3-286">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="a70c3-286">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="a70c3-287">NetworkName</span><span class="sxs-lookup"><span data-stu-id="a70c3-287">NetworkName</span></span>  <br/> |<span data-ttu-id="a70c3-288">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-288">String</span></span>  <br/> |<span data-ttu-id="a70c3-289">美国/西雅图/西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="a70c3-289">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="a70c3-290">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="a70c3-290">NetworkRange</span></span>  <br/> |<span data-ttu-id="a70c3-291">数字</span><span class="sxs-lookup"><span data-stu-id="a70c3-291">Number</span></span>  <br/> |<span data-ttu-id="a70c3-292">个</span><span class="sxs-lookup"><span data-stu-id="a70c3-292">26</span></span>  <br/> |
|<span data-ttu-id="a70c3-293">BuildingName</span><span class="sxs-lookup"><span data-stu-id="a70c3-293">BuildingName</span></span>  <br/> |<span data-ttu-id="a70c3-294">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-294">String</span></span>  <br/> |<span data-ttu-id="a70c3-295">西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="a70c3-295">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="a70c3-296">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="a70c3-296">OwnershipType</span></span>  <br/> |<span data-ttu-id="a70c3-297">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-297">String</span></span>  <br/> |<span data-ttu-id="a70c3-298">制定</span><span class="sxs-lookup"><span data-stu-id="a70c3-298">Contoso</span></span>  <br/> |
|<span data-ttu-id="a70c3-299">BuildingType</span><span class="sxs-lookup"><span data-stu-id="a70c3-299">BuildingType</span></span>  <br/> |<span data-ttu-id="a70c3-300">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-300">String</span></span>  <br/> |<span data-ttu-id="a70c3-301">终止</span><span class="sxs-lookup"><span data-stu-id="a70c3-301">IT Termination</span></span>  <br/> |
|<span data-ttu-id="a70c3-302">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="a70c3-302">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="a70c3-303">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-303">String</span></span>  <br/> |<span data-ttu-id="a70c3-304">技术</span><span class="sxs-lookup"><span data-stu-id="a70c3-304">Engineering</span></span>  <br/> |
|<span data-ttu-id="a70c3-305">城市</span><span class="sxs-lookup"><span data-stu-id="a70c3-305">City</span></span>  <br/> |<span data-ttu-id="a70c3-306">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-306">String</span></span>  <br/> |<span data-ttu-id="a70c3-307">西雅图</span><span class="sxs-lookup"><span data-stu-id="a70c3-307">Seattle</span></span>  <br/> |
|<span data-ttu-id="a70c3-308">ZipCode</span><span class="sxs-lookup"><span data-stu-id="a70c3-308">ZipCode</span></span>  <br/> |<span data-ttu-id="a70c3-309">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-309">String</span></span>  <br/> |<span data-ttu-id="a70c3-310">98001</span><span class="sxs-lookup"><span data-stu-id="a70c3-310">98001</span></span>  <br/> |
|<span data-ttu-id="a70c3-311">该国</span><span class="sxs-lookup"><span data-stu-id="a70c3-311">Country</span></span>  <br/> |<span data-ttu-id="a70c3-312">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-312">String</span></span>  <br/> |<span data-ttu-id="a70c3-313">我们</span><span class="sxs-lookup"><span data-stu-id="a70c3-313">US</span></span>  <br/> |
|<span data-ttu-id="a70c3-314">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="a70c3-314">State</span></span>  <br/> |<span data-ttu-id="a70c3-315">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-315">String</span></span>  <br/> |<span data-ttu-id="a70c3-316">WA</span><span class="sxs-lookup"><span data-stu-id="a70c3-316">WA</span></span>  <br/> |
|<span data-ttu-id="a70c3-317">区域</span><span class="sxs-lookup"><span data-stu-id="a70c3-317">Region</span></span>  <br/> |<span data-ttu-id="a70c3-318">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-318">String</span></span>  <br/> |<span data-ttu-id="a70c3-319">MSUS</span><span class="sxs-lookup"><span data-stu-id="a70c3-319">MSUS</span></span>  <br/> |
|<span data-ttu-id="a70c3-320">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="a70c3-320">InsideCorp</span></span>  <br/> |<span data-ttu-id="a70c3-321">Bool</span><span class="sxs-lookup"><span data-stu-id="a70c3-321">Bool</span></span>  <br/> |<span data-ttu-id="a70c3-322">1</span><span class="sxs-lookup"><span data-stu-id="a70c3-322">1</span></span>  <br/> |
|<span data-ttu-id="a70c3-323">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="a70c3-323">ExpressRoute</span></span>  <br/> |<span data-ttu-id="a70c3-324">Bool</span><span class="sxs-lookup"><span data-stu-id="a70c3-324">Bool</span></span>  <br/> |<span data-ttu-id="a70c3-325">0</span><span class="sxs-lookup"><span data-stu-id="a70c3-325">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="a70c3-326">网络范围可用于表示 supernet (具有单个路由前缀的若干子网的组合)。</span><span class="sxs-lookup"><span data-stu-id="a70c3-326">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="a70c3-327">将检查所有新的生成上载, 查找任何重叠区域。</span><span class="sxs-lookup"><span data-stu-id="a70c3-327">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="a70c3-328">如果你以前上载了一个生成文件, 则应下载当前文件, 然后重新上载它以标识任何重叠, 并在再次上载之前修复该问题。</span><span class="sxs-lookup"><span data-stu-id="a70c3-328">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="a70c3-329">以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。</span><span class="sxs-lookup"><span data-stu-id="a70c3-329">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="a70c3-330">某些 VPN 实现不能准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="a70c3-330">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="a70c3-331">建议将 VPN 子网添加到生成文件, 而不是子网的一个条目时, 将 VPN 子网中每个地址的单独条目添加为单独的32位网络。</span><span class="sxs-lookup"><span data-stu-id="a70c3-331">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="a70c3-332">每一行可以有相同的建筑物元数据。</span><span class="sxs-lookup"><span data-stu-id="a70c3-332">Each row can have the same building metadata.</span></span> <span data-ttu-id="a70c3-333">例如, 对于 172.16.18.0/24, 而不是一行, 您应该有256行, 每个地址对应于 172.16.18.0/32 和 172.16.18.255/32 之间 (包括这两个地址) 的一行。</span><span class="sxs-lookup"><span data-stu-id="a70c3-333">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 

### <a name="endpoint-data-file"></a><span data-ttu-id="a70c3-334">终结点数据文件</span><span class="sxs-lookup"><span data-stu-id="a70c3-334">Endpoint data file</span></span>
<span data-ttu-id="a70c3-335">CQD 通过将终结点数据文件联接到调用记录的第一个客户端终结点名称/第二个客户端终结点名称列来显示终结点生成/模型/类型信息, 从而使用终结点数据文件。</span><span class="sxs-lookup"><span data-stu-id="a70c3-335">CQD uses Endpoint data file by joining its EndpointName column to the call record’s First Client Endpoint Name/Second Client Endpoint Name column to show Endpoint Make/Model/Type information.</span></span> <span data-ttu-id="a70c3-336">你上载的数据文件的格式必须满足以下情况才能在上载之前通过验证检查。</span><span class="sxs-lookup"><span data-stu-id="a70c3-336">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>

- <span data-ttu-id="a70c3-337">文件必须是 tsv 文件, 这意味着在每行中, 列由选项卡或 .csv 文件分隔, 每个列由逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="a70c3-337">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>

- <span data-ttu-id="a70c3-338">数据文件的内容不包含表格标题。</span><span class="sxs-lookup"><span data-stu-id="a70c3-338">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="a70c3-339">这意味着数据文件的第一行应该是真实数据, 而不是像 "终结点" 等标题。</span><span class="sxs-lookup"><span data-stu-id="a70c3-339">That means the first line of the data file should be real data, not headers like "EndpointName," etc.</span></span>

- <span data-ttu-id="a70c3-340">对于每个列, 数据类型只能是字符串, 并且长度不应超过64个字符, 这是允许的最大长度。</span><span class="sxs-lookup"><span data-stu-id="a70c3-340">For each column, the data type can only be String and it should have no more than 64 chars, which is maximum allowed length.</span></span>

- <span data-ttu-id="a70c3-341">对于每个列, 数据可以是空的 (但仍须使用适当的分隔符 (即制表符或逗号) 分隔。</span><span class="sxs-lookup"><span data-stu-id="a70c3-341">For each column, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="a70c3-342">这只是将该字段分配为空字符串值。</span><span class="sxs-lookup"><span data-stu-id="a70c3-342">This just assigns that field an empty string value.</span></span>

- <span data-ttu-id="a70c3-343">每行必须有7列, 并且列必须按照下表中列出的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="a70c3-343">There must be 7 columns for each row and the columns must be in the order listed in the following table.</span></span>

- <span data-ttu-id="a70c3-344">终结点必须是唯一的, 否则上传将因重复行而失败, 因为它会导致不正确的联接。</span><span class="sxs-lookup"><span data-stu-id="a70c3-344">EndpointName must be unique otherwise upload will fail due to duplicate row as it will cause incorrect joining.</span></span>

-  <span data-ttu-id="a70c3-345">EndpointLabel1、EndpointLabel2、EndpointLable3 是用户可自定义的标签, 它们可以是空字符串或用户喜欢的值, 如 "IT 部门指定的2018笔记本电脑"、"资产标签 5678" .。。如此.</span><span class="sxs-lookup"><span data-stu-id="a70c3-345">EndpointLabel1, EndpointLabel2, EndpointLable3 are user customizable labels, they can be empty strings or value users prefer such as “IT Department designated 2018 Laptop”, “Asset Tag 5678” …etc.</span></span>

|<span data-ttu-id="a70c3-346">**列名称**</span><span class="sxs-lookup"><span data-stu-id="a70c3-346">**Column Name**</span></span>|<span data-ttu-id="a70c3-347">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a70c3-347">**Data type**</span></span>|<span data-ttu-id="a70c3-348">**示例**</span><span class="sxs-lookup"><span data-stu-id="a70c3-348">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a70c3-349">点</span><span class="sxs-lookup"><span data-stu-id="a70c3-349">EndpointName</span></span>  <br/> |<span data-ttu-id="a70c3-350">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-350">String</span></span>  <br/> |<span data-ttu-id="a70c3-351">1409W3534</span><span class="sxs-lookup"><span data-stu-id="a70c3-351">1409W3534</span></span>  <br/> |
|<span data-ttu-id="a70c3-352">EndpointMake</span><span class="sxs-lookup"><span data-stu-id="a70c3-352">EndpointMake</span></span>  <br/> |<span data-ttu-id="a70c3-353">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-353">String</span></span>  <br/> |<span data-ttu-id="a70c3-354">Fabrikam Inc。</span><span class="sxs-lookup"><span data-stu-id="a70c3-354">Fabrikam Inc</span></span>  <br/> |
|<span data-ttu-id="a70c3-355">EndpointModel</span><span class="sxs-lookup"><span data-stu-id="a70c3-355">EndpointModel</span></span>  <br/> |<span data-ttu-id="a70c3-356">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-356">String</span></span>  <br/> |<span data-ttu-id="a70c3-357">Fabrikam 模型123</span><span class="sxs-lookup"><span data-stu-id="a70c3-357">Fabrikam Model 123</span></span>  <br/> |
|<span data-ttu-id="a70c3-358">EndpointType</span><span class="sxs-lookup"><span data-stu-id="a70c3-358">EndpointType</span></span>   <br/> |<span data-ttu-id="a70c3-359">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-359">String</span></span>  <br/> |<span data-ttu-id="a70c3-360">着</span><span class="sxs-lookup"><span data-stu-id="a70c3-360">Laptop</span></span>  <br/> |
|<span data-ttu-id="a70c3-361">EndpointLabel1</span><span class="sxs-lookup"><span data-stu-id="a70c3-361">EndpointLabel1</span></span>  <br/> |<span data-ttu-id="a70c3-362">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-362">String</span></span>  <br/> |<span data-ttu-id="a70c3-363">它指定了2018笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="a70c3-363">IT designated 2018 Laptop</span></span>  <br/> |
|<span data-ttu-id="a70c3-364">EndpointLabel2</span><span class="sxs-lookup"><span data-stu-id="a70c3-364">EndpointLabel2</span></span>  <br/> |<span data-ttu-id="a70c3-365">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-365">String</span></span>  <br/> |<span data-ttu-id="a70c3-366">资产标签5678</span><span class="sxs-lookup"><span data-stu-id="a70c3-366">Asset Tag 5678</span></span>  <br/> |
|<span data-ttu-id="a70c3-367">EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="a70c3-367">EndpointLabel3</span></span>  <br/> |<span data-ttu-id="a70c3-368">String</span><span class="sxs-lookup"><span data-stu-id="a70c3-368">String</span></span>  <br/> |<span data-ttu-id="a70c3-369">购买2018</span><span class="sxs-lookup"><span data-stu-id="a70c3-369">Purchase 2018</span></span>   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="a70c3-370">在 "详细报告" 中选择媒体类型</span><span class="sxs-lookup"><span data-stu-id="a70c3-370">Selecting media type in detailed reports</span></span>
<a name="BKMKMediaType"></a>

<span data-ttu-id="a70c3-371">详细报告支持查看音频、视频、应用程序共享和基于视频的屏幕共享媒体类型的质量和媒体可靠性。</span><span class="sxs-lookup"><span data-stu-id="a70c3-371">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="a70c3-372">特定于单个媒体类型的维度、度量值和筛选器具有 "音频"、"视频"、"应用共享" 或 "VBSS" 作为前缀。</span><span class="sxs-lookup"><span data-stu-id="a70c3-372">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![显示呼叫质量仪表板维度的屏幕截图。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="a70c3-374">如果要查看单个媒体类型的维度和度量值, 可能需要新的媒体类型维度和筛选器。</span><span class="sxs-lookup"><span data-stu-id="a70c3-374">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="a70c3-375">例如, 若要使用显示不同媒体类型的总会话计数的报表, 请包括 "媒体类型" 维度。</span><span class="sxs-lookup"><span data-stu-id="a70c3-375">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![显示呼叫质量仪表板总流计数的屏幕截图。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="a70c3-377">相关主题</span><span class="sxs-lookup"><span data-stu-id="a70c3-377">Related topics</span></span>
[<span data-ttu-id="a70c3-378">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="a70c3-378">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="a70c3-379">使用呼叫分析解决较差的通话质量</span><span class="sxs-lookup"><span data-stu-id="a70c3-379">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="a70c3-380">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="a70c3-380">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
