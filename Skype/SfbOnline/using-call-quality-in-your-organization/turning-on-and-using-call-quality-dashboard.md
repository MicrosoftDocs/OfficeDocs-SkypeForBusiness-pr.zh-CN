---
title: "打开并使用呼叫质量仪表板"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: "请参阅如何打开和使用 Skype 业务在线呼叫质量仪表板和获取的呼叫质量的摘要报告。 "
ms.openlocfilehash: aabe15be72c3860c9f6e3bb3ea60619cc9aab85f
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="42c33-103">打开并使用呼叫质量仪表板 Microsoft 小组和 Skype 的在线业务</span><span class="sxs-lookup"><span data-stu-id="42c33-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="42c33-104">了解如何配置您的 Office 365 组织使用调用质量面板监视呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="42c33-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="42c33-105">呼叫质量仪表板 (CQD) 为 Microsoft 小组和 Skype 的在线业务允许您深入了解调用使用 Microsoft 小组和 Skype 业务服务的质量。</span><span class="sxs-lookup"><span data-stu-id="42c33-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="42c33-106">本主题中介绍的步骤操作，您将需要完成后再开始收集数据。</span><span class="sxs-lookup"><span data-stu-id="42c33-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42c33-107">详细的 CQD 报告目前为技术预览可用，但提供给所有客户。</span><span class="sxs-lookup"><span data-stu-id="42c33-107">The CQD detailed reports are currently available as Tech Preview but available to all customers.</span></span> 
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="42c33-108">最新的更改和更新</span><span class="sxs-lookup"><span data-stu-id="42c33-108">Latest changes and updates</span></span>

<span data-ttu-id="42c33-109">对 CQD 的最新更改，如下所示：</span><span class="sxs-lookup"><span data-stu-id="42c33-109">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="42c33-110">包括 Microsoft 小组除了 Skype 的数据业务在线数据。</span><span class="sxs-lookup"><span data-stu-id="42c33-110">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="42c33-111">摘要报告所包含的产品筛选来选择所有数据、 Microsoft 小组数据或 Skype 的在线业务数据。</span><span class="sxs-lookup"><span data-stu-id="42c33-111">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>
    
<span data-ttu-id="42c33-112">请参考本文列表的[维度和度量值在 Microsoft 小组和 Skype 的在线业务呼叫质量仪表板中可用](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="42c33-112">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="42c33-113">有关更新和更改仪表板的信息可通过单击**好 ！**</span><span class="sxs-lookup"><span data-stu-id="42c33-113">Information about updates and changes to the dashboard can be found by clicking **Good news!**</span></span> <span data-ttu-id="42c33-114">在仪表板中。</span><span class="sxs-lookup"><span data-stu-id="42c33-114">in the dashboard.</span></span> <span data-ttu-id="42c33-115">您可以转到[调用质量仪表板](https://aka.ms/CQDOnline)。</span><span class="sxs-lookup"><span data-stu-id="42c33-115">You can go to [Call Quality dashboard](https://aka.ms/CQDOnline).</span></span> 
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="42c33-116">激活 Microsoft 通话质量 (CQD) 的仪表板汇总报表</span><span class="sxs-lookup"><span data-stu-id="42c33-116">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="42c33-117">您可以开始使用 CQD 之前，您需要将其激活 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="42c33-117">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>
  
1. <span data-ttu-id="42c33-118">在 Office 365 组织使用管理员帐户，登录，然后选择**管理**图块以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="42c33-118">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="42c33-119">在左窗格中，在**中心的管理**，选择打开业务管理中心为 Skype**业务的 Skype** 。</span><span class="sxs-lookup"><span data-stu-id="42c33-119">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="42c33-120">在业务管理中心的 Skype，在左窗格中，选择**工具**，然后选择**Skype 业务在线呼叫质量仪表板**。</span><span class="sxs-lookup"><span data-stu-id="42c33-120">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![Skype 业务工具](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="42c33-122">在打开的页面，使用您的全局管理员帐户，登录，然后当系统提示您的帐户提供凭据。</span><span class="sxs-lookup"><span data-stu-id="42c33-122">On the page that opens, log in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![CQD 登录](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="42c33-124">您登录后，一旦激活后, CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="42c33-124">After you login, once activated, the CQD will begin collecting and processing data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42c33-125">它可能需要几个小时来处理数据不足，无法在报告中显示有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="42c33-125">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a><span data-ttu-id="42c33-126">在线业务的 Skype 的通话质量仪表板的功能</span><span class="sxs-lookup"><span data-stu-id="42c33-126">Features of the Call Quality Dashboard for Skype for Business Online</span></span>
<span data-ttu-id="42c33-127"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="42c33-127"></span></span>

<span data-ttu-id="42c33-128">CQD 摘要报告提供了计划的详细报告功能的一个子集。</span><span class="sxs-lookup"><span data-stu-id="42c33-128">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="42c33-129">两个版本之间的差异汇总如下：</span><span class="sxs-lookup"><span data-stu-id="42c33-129">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="42c33-130">**功能**</span><span class="sxs-lookup"><span data-stu-id="42c33-130">**Feature**</span></span>|<span data-ttu-id="42c33-131">**摘要报告**</span><span class="sxs-lookup"><span data-stu-id="42c33-131">**Summary Reports**</span></span>|<span data-ttu-id="42c33-132">**详细的报告**</span><span class="sxs-lookup"><span data-stu-id="42c33-132">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="42c33-133">应用程序共享的跃点计数</span><span class="sxs-lookup"><span data-stu-id="42c33-133">Application sharing metric</span></span>  <br/> |<span data-ttu-id="42c33-134">否</span><span class="sxs-lookup"><span data-stu-id="42c33-134">No</span></span>  <br/> |<span data-ttu-id="42c33-135">是</span><span class="sxs-lookup"><span data-stu-id="42c33-135">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-136">构建信息支持的客户</span><span class="sxs-lookup"><span data-stu-id="42c33-136">Customer building information support</span></span>  <br/> |<span data-ttu-id="42c33-137">是</span><span class="sxs-lookup"><span data-stu-id="42c33-137">Yes</span></span>  <br/> |<span data-ttu-id="42c33-138">是</span><span class="sxs-lookup"><span data-stu-id="42c33-138">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-139">深入分析支持</span><span class="sxs-lookup"><span data-stu-id="42c33-139">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="42c33-140">否</span><span class="sxs-lookup"><span data-stu-id="42c33-140">No</span></span>  <br/> |<span data-ttu-id="42c33-141">是</span><span class="sxs-lookup"><span data-stu-id="42c33-141">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-142">介质可靠性度量法</span><span class="sxs-lookup"><span data-stu-id="42c33-142">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="42c33-143">否</span><span class="sxs-lookup"><span data-stu-id="42c33-143">No</span></span>  <br/> |<span data-ttu-id="42c33-144">是</span><span class="sxs-lookup"><span data-stu-id="42c33-144">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-145">优秀的报告</span><span class="sxs-lookup"><span data-stu-id="42c33-145">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="42c33-146">是</span><span class="sxs-lookup"><span data-stu-id="42c33-146">Yes</span></span>  <br/> |<span data-ttu-id="42c33-147">是</span><span class="sxs-lookup"><span data-stu-id="42c33-147">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-148">总览报表</span><span class="sxs-lookup"><span data-stu-id="42c33-148">Overview reports</span></span>  <br/> |<span data-ttu-id="42c33-149">是</span><span class="sxs-lookup"><span data-stu-id="42c33-149">Yes</span></span>  <br/> |<span data-ttu-id="42c33-150">是</span><span class="sxs-lookup"><span data-stu-id="42c33-150">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-151">每个用户报告集</span><span class="sxs-lookup"><span data-stu-id="42c33-151">Per-user report set</span></span>  <br/> |<span data-ttu-id="42c33-152">否</span><span class="sxs-lookup"><span data-stu-id="42c33-152">No</span></span>  <br/> |<span data-ttu-id="42c33-153">是</span><span class="sxs-lookup"><span data-stu-id="42c33-153">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-154">设置自定义报表 （添加、 删除、 修改报表）</span><span class="sxs-lookup"><span data-stu-id="42c33-154">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="42c33-155">否</span><span class="sxs-lookup"><span data-stu-id="42c33-155">No</span></span>  <br/> |<span data-ttu-id="42c33-156">是</span><span class="sxs-lookup"><span data-stu-id="42c33-156">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-157">基于视频的屏幕共享标准</span><span class="sxs-lookup"><span data-stu-id="42c33-157">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="42c33-158">否</span><span class="sxs-lookup"><span data-stu-id="42c33-158">No</span></span>  <br/> |<span data-ttu-id="42c33-159">是</span><span class="sxs-lookup"><span data-stu-id="42c33-159">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-160">视频标准</span><span class="sxs-lookup"><span data-stu-id="42c33-160">Video metrics</span></span>  <br/> |<span data-ttu-id="42c33-161">否</span><span class="sxs-lookup"><span data-stu-id="42c33-161">No</span></span>  <br/> |<span data-ttu-id="42c33-162">是</span><span class="sxs-lookup"><span data-stu-id="42c33-162">Yes</span></span>  <br/> |
|<span data-ttu-id="42c33-163">可用的数据量</span><span class="sxs-lookup"><span data-stu-id="42c33-163">Amount of data available</span></span>  <br/> |<span data-ttu-id="42c33-164">过去 6 个月</span><span class="sxs-lookup"><span data-stu-id="42c33-164">Last 6 months</span></span>  <br/> |<span data-ttu-id="42c33-165">过去 6 个月</span><span class="sxs-lookup"><span data-stu-id="42c33-165">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="42c33-166">Microsoft 小组数据</span><span class="sxs-lookup"><span data-stu-id="42c33-166">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="42c33-167">是</span><span class="sxs-lookup"><span data-stu-id="42c33-167">Yes</span></span>  <br/> |<span data-ttu-id="42c33-168">是</span><span class="sxs-lookup"><span data-stu-id="42c33-168">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="42c33-169">优秀的报告</span><span class="sxs-lookup"><span data-stu-id="42c33-169">Out-of-the-box reports</span></span>

<span data-ttu-id="42c33-170">这两个版本的 CQD 提供--全新体验，使您可以调用而不需要创建任何新报表的质量标准。</span><span class="sxs-lookup"><span data-stu-id="42c33-170">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="42c33-171">一旦在后端处理数据时，您可以开始看到报告中呼叫质量数据。</span><span class="sxs-lookup"><span data-stu-id="42c33-171">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="42c33-172">总览报表</span><span class="sxs-lookup"><span data-stu-id="42c33-172">Overview reports</span></span>

<span data-ttu-id="42c33-173">这两个版本的 CQD 提供高级别入口点到总体的呼叫质量信息，但信息显示在摘要报表的方式是不同的详细的报告。</span><span class="sxs-lookup"><span data-stu-id="42c33-173">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="42c33-174">摘要报告提供简化的选项卡式的页面报表视图，使用户可以快速浏览和理解总体通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="42c33-174">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="42c33-175">四个选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="42c33-175">The four tabs include:</span></span>
  
- <span data-ttu-id="42c33-176">**调用的总体质量**-提供所有流中，服务器-客户端流的聚合和客户流，以及单独的服务器-客户端和客户端客户端流时，在窗体的每月和每日趋势有关的信息。</span><span class="sxs-lookup"><span data-stu-id="42c33-176">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="42c33-177">**服务器-客户端**-服务器和客户端终结点之间流提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="42c33-177">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="42c33-178">**客户端-客户端**-流两个客户端终结点之间提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="42c33-178">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="42c33-179">**语音质量 SLA** -提供有关被纳入业务在线语音质量 SLA Skype 的呼叫信息。</span><span class="sxs-lookup"><span data-stu-id="42c33-179">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="42c33-180">整个呼叫质量选项卡</span><span class="sxs-lookup"><span data-stu-id="42c33-180">Overall Call Quality tab</span></span>

<span data-ttu-id="42c33-181">使用此选项卡上的数据通过查看流计数和较差的百分比来计算通话质量状态和发展趋势。</span><span class="sxs-lookup"><span data-stu-id="42c33-181">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="42c33-182">在右上角的图例显示的颜色和视觉元素表示这些度量标准。</span><span class="sxs-lookup"><span data-stu-id="42c33-182">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![CQD 数据键](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="42c33-184">流可分为三个组： 好、 较差，以及未分类。</span><span class="sxs-lookup"><span data-stu-id="42c33-184">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="42c33-185">那里也计算*差 %*值您的流率属于该授予 * 差 * 总保密的流数。</span><span class="sxs-lookup"><span data-stu-id="42c33-185">There are also calculated  *Poor %*  values that give you the ratio of streams classified as * Poor*  to the total classified stream count.</span></span> <span data-ttu-id="42c33-186">由于*差 %= 差流 / （差流 + 良好的流） \* 100* ，这样*差 %*与多个*自解除保密*流的存在不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="42c33-186">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="42c33-187">什么用于分类为较差或很好的流，请参阅[呼叫质量阈值](https://aka.ms/cqd_quality_thresholds)。</span><span class="sxs-lookup"><span data-stu-id="42c33-187">For what is used for classifying a stream as poor or good, refer to [Call Quality Thresholds](https://aka.ms/cqd_quality_thresholds).</span></span>
  
<span data-ttu-id="42c33-188">使用左侧的比例来衡量的调用计数值。</span><span class="sxs-lookup"><span data-stu-id="42c33-188">Use the scale on the left to measure the call count values.</span></span>
  
![CQD 数据计数](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="42c33-190">使用右侧的比例测量值差 %。</span><span class="sxs-lookup"><span data-stu-id="42c33-190">Use the scale on the right to measure the Poor % values.</span></span>
  
![CQD 数据每年会](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="42c33-192">您还可以通过将鼠标悬停在条上获取实际的数字值。</span><span class="sxs-lookup"><span data-stu-id="42c33-192">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42c33-193">下面的示例是从非常小的示例数据集和值不适合实际部署。</span><span class="sxs-lookup"><span data-stu-id="42c33-193">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![CQD 数据数字](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="42c33-195">总体流卷是在确定计算差百分比相关程度的一个重要因素。</span><span class="sxs-lookup"><span data-stu-id="42c33-195">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="42c33-196">总体流量小、 可靠性较低是报告不佳的百分比值。</span><span class="sxs-lookup"><span data-stu-id="42c33-196">The smaller the volume of overall stream, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="42c33-197">服务器-客户端选项卡和客户端选项卡</span><span class="sxs-lookup"><span data-stu-id="42c33-197">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="42c33-198">这两个选项卡提供流在其终结点的终结点的情况下发生的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="42c33-198">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="42c33-199">这两个选项卡都具有四个可折叠的部分，表示流媒体流将在其下的四种情形。</span><span class="sxs-lookup"><span data-stu-id="42c33-199">Both tabs have four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="42c33-200">内部连接</span><span class="sxs-lookup"><span data-stu-id="42c33-200">Wired Inside</span></span>
    
- <span data-ttu-id="42c33-201">外部连接</span><span class="sxs-lookup"><span data-stu-id="42c33-201">Wired Outside</span></span>
    
- <span data-ttu-id="42c33-202">Wifi 内侧</span><span class="sxs-lookup"><span data-stu-id="42c33-202">Wifi Inside</span></span>
    
- <span data-ttu-id="42c33-203">Wifi 外</span><span class="sxs-lookup"><span data-stu-id="42c33-203">Wifi Outside</span></span>
    
#### <a name="inside-test"></a><span data-ttu-id="42c33-204">内部测试</span><span class="sxs-lookup"><span data-stu-id="42c33-204">Inside Test</span></span>

<span data-ttu-id="42c33-205">处理期间，CQD 后端分类为*内部*或*外部*使用建筑物信息的流，如果有的话。</span><span class="sxs-lookup"><span data-stu-id="42c33-205">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="42c33-206">每个流的终结点都使用子网掩码地址相关联。</span><span class="sxs-lookup"><span data-stu-id="42c33-206">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="42c33-207">如果子网列表中的子网中上载的构建信息，则被视为内部。</span><span class="sxs-lookup"><span data-stu-id="42c33-207">If the subnet is in the list of the subnets in the uploaded Building information, then it is considered Inside.</span></span> <span data-ttu-id="42c33-208">如果建筑物信息尚未尚未上载，内部测试将始终作为*外部*分类流。</span><span class="sxs-lookup"><span data-stu-id="42c33-208">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*  .</span></span> <span data-ttu-id="42c33-209">请注意，服务器-客户端方案中测试只考虑客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="42c33-209">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="42c33-210">因为服务器始终之外从用户的角度来看，这不被占测试中。</span><span class="sxs-lookup"><span data-stu-id="42c33-210">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="42c33-211">有线与 wifi</span><span class="sxs-lookup"><span data-stu-id="42c33-211">Wired vs. wifi</span></span>

<span data-ttu-id="42c33-212">名称表示，这是基于客户端的连接的类型分类标准。</span><span class="sxs-lookup"><span data-stu-id="42c33-212">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="42c33-213">同样，服务器始终有线，它并不包括在计算中。</span><span class="sxs-lookup"><span data-stu-id="42c33-213">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42c33-214">如果一个两个终结点连接到 Wifi 网络，给出流，然后归为 Wifi CQD 中。</span><span class="sxs-lookup"><span data-stu-id="42c33-214">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="42c33-215">选择要在报表中查看的产品数据</span><span class="sxs-lookup"><span data-stu-id="42c33-215">Selecting product data to see in reports</span></span>
<span data-ttu-id="42c33-216"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="42c33-216"></span></span>

<span data-ttu-id="42c33-217">在摘要和位置增强报表中，您可以使用**产品筛选器**下拉列表以显示所有产品数据，只有 Microsoft 小组数据或仅 Skype 的在线业务数据。</span><span class="sxs-lookup"><span data-stu-id="42c33-217">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![屏幕抓图显示所有选项、 Microsoft 团队和业务的 Skype 的产品筛选器控件。](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="42c33-219">在详细的报表中，可以使用团队维度到 Microsoft 小组或 Skype 为报表定义的一部分的在线业务数据的数据进行筛选。</span><span class="sxs-lookup"><span data-stu-id="42c33-219">In Detailed reports, you can use the Teams dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-building-information"></a><span data-ttu-id="42c33-220">上载的构建信息</span><span class="sxs-lookup"><span data-stu-id="42c33-220">Upload Building information</span></span>
<span data-ttu-id="42c33-221"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="42c33-221"></span></span>

<span data-ttu-id="42c33-222">CQD 摘要报告控制板包括**租户数据上载**页面，通过从右上角的设置菜单中选择**租户的数据上载**。</span><span class="sxs-lookup"><span data-stu-id="42c33-222">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="42c33-223">此页用于管理员上载他们自己的信息，如 IP 地址和地理位置的信息，映射映射每个无线 AP 和它的 MAC 地址，等等。</span><span class="sxs-lookup"><span data-stu-id="42c33-223">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, etc.</span></span>
  
![CQD 仪表板](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="42c33-225">在**租户数据上载**页上，使用下拉菜单选择上载的数据文件类型。</span><span class="sxs-lookup"><span data-stu-id="42c33-225">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="42c33-226">文件数据类型表示该文件的内容 （例如，"大厦"是指映射的 IP 地址和建筑物以及其他地理信息）。</span><span class="sxs-lookup"><span data-stu-id="42c33-226">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information).</span></span> <span data-ttu-id="42c33-227">目前我们只支持"建立"数据类型。</span><span class="sxs-lookup"><span data-stu-id="42c33-227">Currently we are only supporting the "Building" data type.</span></span> <span data-ttu-id="42c33-228">与后续版本将添加一些更多的数据类型。</span><span class="sxs-lookup"><span data-stu-id="42c33-228">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="42c33-229">选择文件数据类型后, 请单击**浏览**以选择一个数据文件。</span><span class="sxs-lookup"><span data-stu-id="42c33-229">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
  - <span data-ttu-id="42c33-230">数据文件必须.tsv （制表符分隔值） 文件或.csv （逗号分隔值） 文件。</span><span class="sxs-lookup"><span data-stu-id="42c33-230">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="42c33-231">如果使用.csv 文件，包含逗号的任何字段必须包含引号或删除逗号。</span><span class="sxs-lookup"><span data-stu-id="42c33-231">If using a .csv file, any field that contains a comma must contain quotes or have the comma removed.</span></span> <span data-ttu-id="42c33-232">例如，如果建筑物名称是纽约州，纽约州，在.csv 文件中应输入为"纽约州，NY"。</span><span class="sxs-lookup"><span data-stu-id="42c33-232">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
  - <span data-ttu-id="42c33-233">数据文件必须是不超过 50 MB 的大小。</span><span class="sxs-lookup"><span data-stu-id="42c33-233">The data file must be no larger than 50MB in size.</span></span>
    
  - <span data-ttu-id="42c33-234">每个数据文件，文件中的每个列必须匹配预定义的数据类型，本主题中稍后讨论。</span><span class="sxs-lookup"><span data-stu-id="42c33-234">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="42c33-235">选择数据文件之后，指定**开始日期**和 （可选）**指定的结束日期**。</span><span class="sxs-lookup"><span data-stu-id="42c33-235">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="42c33-236">选择**开始日期**之后, 选择**上载**到 CQD 服务器上载文件。</span><span class="sxs-lookup"><span data-stu-id="42c33-236">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="42c33-237">在上载文件之前，请先验证。</span><span class="sxs-lookup"><span data-stu-id="42c33-237">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="42c33-238">一旦验证，它存储在 Azure 的 blob。</span><span class="sxs-lookup"><span data-stu-id="42c33-238">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="42c33-239">如果验证失败，或者该文件不能存储在 Azure 的斑点，请求对该文件的更正显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="42c33-239">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="42c33-240">下图显示了在数据文件中的列的数目不正确时出现错误。</span><span class="sxs-lookup"><span data-stu-id="42c33-240">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![CQD 示例上载验证错误](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="42c33-242">如果在验证过程中不出现任何错误，将会成功上载文件。</span><span class="sxs-lookup"><span data-stu-id="42c33-242">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="42c33-243">然后，您可以看到在**我上载**表中，显示在该页面底部当前的租户的所有上载的文件的完整列表上载的数据文件。</span><span class="sxs-lookup"><span data-stu-id="42c33-243">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="42c33-244">每个录制节目一个上载的租户数据文件的文件类型、 上次更新时间、 时间段、 说明、 移除和下载图标。</span><span class="sxs-lookup"><span data-stu-id="42c33-244">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, remove, and a download icon.</span></span> <span data-ttu-id="42c33-245">要删除一个文件，请选择表中的回收站图标。</span><span class="sxs-lookup"><span data-stu-id="42c33-245">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="42c33-246">要下载文件，请**下载**的表的列中选择下载图标。</span><span class="sxs-lookup"><span data-stu-id="42c33-246">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![CQD 我上载表](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a><span data-ttu-id="42c33-248">租户的数据文件格式和生成数据文件结构</span><span class="sxs-lookup"><span data-stu-id="42c33-248">Tenant data file format and Building data file structure</span></span>
<span data-ttu-id="42c33-249"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="42c33-249"></span></span>

<span data-ttu-id="42c33-250">您上载的数据文件的格式必须满足以下操作以通过上载之前，验证检查。</span><span class="sxs-lookup"><span data-stu-id="42c33-250">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="42c33-251">该文件必须.tsv 文件中，这意味着，在每一行，列由制表符分隔或逗号分隔每个列的.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="42c33-251">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="42c33-252">数据文件的内容不包括表标题。</span><span class="sxs-lookup"><span data-stu-id="42c33-252">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="42c33-253">不头，意味着数据文件的第一行应该是真实的数据，如"网络"等。</span><span class="sxs-lookup"><span data-stu-id="42c33-253">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="42c33-254">对于每个列，数据类型只能是字符串、 数字或布尔值。</span><span class="sxs-lookup"><span data-stu-id="42c33-254">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="42c33-255">如果它是数字，值必须为数字值;它是布尔值，如果值必须是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="42c33-255">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="42c33-256">对于每一列，如果数据类型是字符串，数据可以为空 (但仍必须用适当的分隔分隔 （如制表符或逗号）。</span><span class="sxs-lookup"><span data-stu-id="42c33-256">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimited (i.e., a tab or comma).</span></span> <span data-ttu-id="42c33-257">这只是该为字段指定空字符串值。</span><span class="sxs-lookup"><span data-stu-id="42c33-257">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="42c33-258">必须有 14 列，对于每一行，并且每一列必须具有下面的数据类型和列必须是下表中列出的顺序：</span><span class="sxs-lookup"><span data-stu-id="42c33-258">There must be 14 columns for each row, and each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="42c33-259">**列名称**</span><span class="sxs-lookup"><span data-stu-id="42c33-259">**Column Name**</span></span>|<span data-ttu-id="42c33-260">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="42c33-260">**Data type**</span></span>|<span data-ttu-id="42c33-261">**示例**</span><span class="sxs-lookup"><span data-stu-id="42c33-261">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="42c33-262">网络</span><span class="sxs-lookup"><span data-stu-id="42c33-262">Network</span></span>  <br/> |<span data-ttu-id="42c33-263">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-263">String</span></span>  <br/> |<span data-ttu-id="42c33-264">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="42c33-264">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="42c33-265">NetworkName</span><span class="sxs-lookup"><span data-stu-id="42c33-265">NetworkName</span></span>  <br/> |<span data-ttu-id="42c33-266">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-266">String</span></span>  <br/> |<span data-ttu-id="42c33-267">美国/西雅图/西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="42c33-267">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="42c33-268">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="42c33-268">NetworkRange</span></span>  <br/> |<span data-ttu-id="42c33-269">数字</span><span class="sxs-lookup"><span data-stu-id="42c33-269">Number</span></span>  <br/> |<span data-ttu-id="42c33-270">26</span><span class="sxs-lookup"><span data-stu-id="42c33-270">26</span></span>  <br/> |
|<span data-ttu-id="42c33-271">BuildingName</span><span class="sxs-lookup"><span data-stu-id="42c33-271">BuildingName</span></span>  <br/> |<span data-ttu-id="42c33-272">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-272">String</span></span>  <br/> |<span data-ttu-id="42c33-273">西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="42c33-273">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="42c33-274">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="42c33-274">OwnershipType</span></span>  <br/> |<span data-ttu-id="42c33-275">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-275">String</span></span>  <br/> |<span data-ttu-id="42c33-276">Contoso</span><span class="sxs-lookup"><span data-stu-id="42c33-276">Contoso</span></span>  <br/> |
|<span data-ttu-id="42c33-277">BuildingType</span><span class="sxs-lookup"><span data-stu-id="42c33-277">BuildingType</span></span>  <br/> |<span data-ttu-id="42c33-278">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-278">String</span></span>  <br/> |<span data-ttu-id="42c33-279">IT 终止</span><span class="sxs-lookup"><span data-stu-id="42c33-279">IT Termination</span></span>  <br/> |
|<span data-ttu-id="42c33-280">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="42c33-280">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="42c33-281">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-281">String</span></span>  <br/> |<span data-ttu-id="42c33-282">工程</span><span class="sxs-lookup"><span data-stu-id="42c33-282">Engineering</span></span>  <br/> |
|<span data-ttu-id="42c33-283">城市</span><span class="sxs-lookup"><span data-stu-id="42c33-283">City</span></span>  <br/> |<span data-ttu-id="42c33-284">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-284">String</span></span>  <br/> |<span data-ttu-id="42c33-285">西雅图</span><span class="sxs-lookup"><span data-stu-id="42c33-285">Seattle</span></span>  <br/> |
|<span data-ttu-id="42c33-286">邮政编码</span><span class="sxs-lookup"><span data-stu-id="42c33-286">ZipCode</span></span>  <br/> |<span data-ttu-id="42c33-287">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-287">String</span></span>  <br/> |<span data-ttu-id="42c33-288">98001</span><span class="sxs-lookup"><span data-stu-id="42c33-288">98001</span></span>  <br/> |
|<span data-ttu-id="42c33-289">国家/地区</span><span class="sxs-lookup"><span data-stu-id="42c33-289">Country</span></span>  <br/> |<span data-ttu-id="42c33-290">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-290">String</span></span>  <br/> |<span data-ttu-id="42c33-291">我们</span><span class="sxs-lookup"><span data-stu-id="42c33-291">US</span></span>  <br/> |
|<span data-ttu-id="42c33-292">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="42c33-292">State</span></span>  <br/> |<span data-ttu-id="42c33-293">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-293">String</span></span>  <br/> |<span data-ttu-id="42c33-294">WA</span><span class="sxs-lookup"><span data-stu-id="42c33-294">WA</span></span>  <br/> |
|<span data-ttu-id="42c33-295">区域</span><span class="sxs-lookup"><span data-stu-id="42c33-295">Region</span></span>  <br/> |<span data-ttu-id="42c33-296">字符串</span><span class="sxs-lookup"><span data-stu-id="42c33-296">String</span></span>  <br/> |<span data-ttu-id="42c33-297">MSU</span><span class="sxs-lookup"><span data-stu-id="42c33-297">MSUS</span></span>  <br/> |
|<span data-ttu-id="42c33-298">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="42c33-298">InsideCorp</span></span>  <br/> |<span data-ttu-id="42c33-299">Bool</span><span class="sxs-lookup"><span data-stu-id="42c33-299">Bool</span></span>  <br/> |<span data-ttu-id="42c33-300">1</span><span class="sxs-lookup"><span data-stu-id="42c33-300">1</span></span>  <br/> |
|<span data-ttu-id="42c33-301">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="42c33-301">ExpressRoute</span></span>  <br/> |<span data-ttu-id="42c33-302">Bool</span><span class="sxs-lookup"><span data-stu-id="42c33-302">Bool</span></span>  <br/> |<span data-ttu-id="42c33-303">0</span><span class="sxs-lookup"><span data-stu-id="42c33-303">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="42c33-304">网络范围可以用于表示 supernet （若干个子网，具有单个路由前缀的组合）。</span><span class="sxs-lookup"><span data-stu-id="42c33-304">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="42c33-305">所有新的建筑物上载将检查有任何重叠范围。</span><span class="sxs-lookup"><span data-stu-id="42c33-305">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="42c33-306">如果您以前上载的构建文件，您应下载当前文件并重新上载识别任何重叠并再次上传之前解决此问题。</span><span class="sxs-lookup"><span data-stu-id="42c33-306">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="42c33-307">任何重叠以前上载的文件的情况可能会导致错误的子网与报告中的建筑映射。</span><span class="sxs-lookup"><span data-stu-id="42c33-307">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="42c33-308">某些 VPN 实现无法准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="42c33-308">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="42c33-309">当将 VPN 网添加到构建文件中，而不是子网的一项建议，单独条目添加 VPN 网中的每个地址作为单独的 32 位网络。</span><span class="sxs-lookup"><span data-stu-id="42c33-309">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="42c33-310">每行可有相同的生成元数据。</span><span class="sxs-lookup"><span data-stu-id="42c33-310">Each row can have the same building metadata.</span></span> <span data-ttu-id="42c33-311">例如，而不是 172.16.18.0/24 一行，应该有 256 行，通过 172.16.18.0/32 和 172.16.18.255/32，包括之间的每个地址都占一行。</span><span class="sxs-lookup"><span data-stu-id="42c33-311">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 
  
## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="42c33-312">在详细报告选择介质类型</span><span class="sxs-lookup"><span data-stu-id="42c33-312">Selecting media type in detailed reports</span></span>
<span data-ttu-id="42c33-313"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="42c33-313"></span></span>

<span data-ttu-id="42c33-314">详细的报告支持看质量和介质可靠性的音频、 视频、 应用程序共享和基于视频屏幕共享的媒体类型。</span><span class="sxs-lookup"><span data-stu-id="42c33-314">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="42c33-315">维度、 度量值和特定于单个媒体类型的筛选器具有"音频"、"视频"、"AppSharing"或"VBSS"为前缀。</span><span class="sxs-lookup"><span data-stu-id="42c33-315">Dimensions, measures, and filters that are specific for a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![呼叫质量仪表板尺寸。](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="42c33-317">如果您想要查看的维度和度量值的单个媒体类型，可能需要新的媒体类型维度和筛选器。</span><span class="sxs-lookup"><span data-stu-id="42c33-317">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="42c33-318">例如，若要显示总会话计算在不同媒体类型的报告，包括媒体类型维度。</span><span class="sxs-lookup"><span data-stu-id="42c33-318">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![呼叫质量仪表板总流计数。](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="42c33-320">相关主题</span><span class="sxs-lookup"><span data-stu-id="42c33-320">Related topics</span></span>
[<span data-ttu-id="42c33-321">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="42c33-321">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="42c33-322">使用调用分析解决差呼叫质量</span><span class="sxs-lookup"><span data-stu-id="42c33-322">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="42c33-323">调用分析和通话质量仪表板之间的区别吗？</span><span class="sxs-lookup"><span data-stu-id="42c33-323">Difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

## <a name="feedback"></a><span data-ttu-id="42c33-324">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="42c33-324">Feedback?</span></span>
<span data-ttu-id="42c33-325">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="42c33-325">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>