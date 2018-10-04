---
title: 启用和使用通话质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: '请参阅如何启用和 Skype 用于业务联机呼叫质量仪表板并获取呼叫的质量摘要报告。 '
ms.openlocfilehash: 008fbeca5ae9b81d74e9a38f60c12a6fc1f919cc
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373805"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="d2cce-103">打开和使用呼叫质量仪表板的 Microsoft 团队和 Skype 业务 online</span><span class="sxs-lookup"><span data-stu-id="d2cce-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="d2cce-104">了解如何配置 Office 365 组织使用呼叫质量仪表板来监视呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="d2cce-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="d2cce-105">呼叫质量仪表板 (CQD) 的 Microsoft 团队和 Skype 业务 online 使您能够获得见解进行业务服务使用的 Microsoft 团队和 Skype 的呼叫的质量。</span><span class="sxs-lookup"><span data-stu-id="d2cce-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="d2cce-106">本主题介绍的步骤，您需要完成要开始收集数据。</span><span class="sxs-lookup"><span data-stu-id="d2cce-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2cce-107">详细 CQD 报告当前是可用作技术预览版，但适用于所有的客户。</span><span class="sxs-lookup"><span data-stu-id="d2cce-107">The CQD detailed reports are currently available as Tech Preview but available to all customers.</span></span> 
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="d2cce-108">最新更改和更新</span><span class="sxs-lookup"><span data-stu-id="d2cce-108">Latest changes and updates</span></span>

<span data-ttu-id="d2cce-109">对 CQD 的最新更改如下所示：</span><span class="sxs-lookup"><span data-stu-id="d2cce-109">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="d2cce-110">包括除了 Skype Online 业务数据的 Microsoft 团队数据。</span><span class="sxs-lookup"><span data-stu-id="d2cce-110">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="d2cce-111">摘要报告包括产品筛选器以选择所有数据、 Microsoft 团队数据或 Skype Online 业务数据。</span><span class="sxs-lookup"><span data-stu-id="d2cce-111">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="d2cce-112">已更新视频和 VBSS 流质量分类逻辑。</span><span class="sxs-lookup"><span data-stu-id="d2cce-112">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="d2cce-113">最新的分类器定义，请参阅[呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="d2cce-113">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="d2cce-114">请参阅此列表的[维度和度量值可用呼叫质量仪表板中](dimensions-and-measures-available-in-call-quality-dashboard.md)的文章。</span><span class="sxs-lookup"><span data-stu-id="d2cce-114">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2cce-115">有关更新和向仪表板的更改的信息可通过单击中的链接**好消息 ！**</span><span class="sxs-lookup"><span data-stu-id="d2cce-115">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="d2cce-116">标题显示仪表板上时。</span><span class="sxs-lookup"><span data-stu-id="d2cce-116">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="d2cce-117">激活 Microsoft 呼叫质量仪表板 (CQD) 摘要报告</span><span class="sxs-lookup"><span data-stu-id="d2cce-117">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="d2cce-118">您可以开始使用 CQD 之前，您需要激活的 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="d2cce-118">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>
 
<span data-ttu-id="d2cce-119">![sfb-徽标-30x30.png](media/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="d2cce-119">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="d2cce-120">登录到 Office 365 组织使用管理帐户，，然后选择**管理员**图块打开在管理中心。</span><span class="sxs-lookup"><span data-stu-id="d2cce-120">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="d2cce-121">在左窗格中，在**管理中心**，选择打开业务管理中心的 Skype **for Business 的 Skype** 。</span><span class="sxs-lookup"><span data-stu-id="d2cce-121">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="d2cce-122">在业务管理中心的 Skype，在左侧窗格中，选择**工具**，然后选择**业务联机呼叫质量仪表板的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="d2cce-122">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![Skype 业务工具](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="d2cce-124">在打开页上，使用您的全局管理员帐户，登录，然后提供出现提示时的帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="d2cce-124">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![CQD 登录](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="d2cce-126">登录，一旦被激活后后, CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="d2cce-126">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2cce-127">可能需要几个小时处理数据不足，无法在报表中显示有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="d2cce-127">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a><span data-ttu-id="d2cce-128">联机 for Business 的 Skype 呼叫质量仪表板的功能</span><span class="sxs-lookup"><span data-stu-id="d2cce-128">Features of the Call Quality Dashboard for Skype for Business Online</span></span>
<span data-ttu-id="d2cce-129"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="d2cce-129"></span></span>

<span data-ttu-id="d2cce-130">CQD 摘要报告提供计划的详细的报告功能的子集。</span><span class="sxs-lookup"><span data-stu-id="d2cce-130">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="d2cce-131">下面总结了两种版本之间的差异：</span><span class="sxs-lookup"><span data-stu-id="d2cce-131">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="d2cce-132">**功能**</span><span class="sxs-lookup"><span data-stu-id="d2cce-132">**Feature**</span></span>|<span data-ttu-id="d2cce-133">**摘要报告**</span><span class="sxs-lookup"><span data-stu-id="d2cce-133">**Summary Reports**</span></span>|<span data-ttu-id="d2cce-134">**详细的报告**</span><span class="sxs-lookup"><span data-stu-id="d2cce-134">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d2cce-135">应用程序共享指标</span><span class="sxs-lookup"><span data-stu-id="d2cce-135">Application sharing metric</span></span>  <br/> |<span data-ttu-id="d2cce-136">否</span><span class="sxs-lookup"><span data-stu-id="d2cce-136">No</span></span>  <br/> |<span data-ttu-id="d2cce-137">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-137">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-138">构建信息支持的客户</span><span class="sxs-lookup"><span data-stu-id="d2cce-138">Customer building information support</span></span>  <br/> |<span data-ttu-id="d2cce-139">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-139">Yes</span></span>  <br/> |<span data-ttu-id="d2cce-140">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-140">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-141">深入分析支持</span><span class="sxs-lookup"><span data-stu-id="d2cce-141">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="d2cce-142">否</span><span class="sxs-lookup"><span data-stu-id="d2cce-142">No</span></span>  <br/> |<span data-ttu-id="d2cce-143">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-143">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-144">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="d2cce-144">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="d2cce-145">否</span><span class="sxs-lookup"><span data-stu-id="d2cce-145">No</span></span>  <br/> |<span data-ttu-id="d2cce-146">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-146">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-147">即开报告</span><span class="sxs-lookup"><span data-stu-id="d2cce-147">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="d2cce-148">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-148">Yes</span></span>  <br/> |<span data-ttu-id="d2cce-149">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-149">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-150">概述报告</span><span class="sxs-lookup"><span data-stu-id="d2cce-150">Overview reports</span></span>  <br/> |<span data-ttu-id="d2cce-151">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-151">Yes</span></span>  <br/> |<span data-ttu-id="d2cce-152">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-152">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-153">每个用户报告集</span><span class="sxs-lookup"><span data-stu-id="d2cce-153">Per-user report set</span></span>  <br/> |<span data-ttu-id="d2cce-154">否</span><span class="sxs-lookup"><span data-stu-id="d2cce-154">No</span></span>  <br/> |<span data-ttu-id="d2cce-155">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-155">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-156">设置自定义报表 （添加、 删除、 修改报表）</span><span class="sxs-lookup"><span data-stu-id="d2cce-156">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="d2cce-157">否</span><span class="sxs-lookup"><span data-stu-id="d2cce-157">No</span></span>  <br/> |<span data-ttu-id="d2cce-158">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-158">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-159">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="d2cce-159">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="d2cce-160">否</span><span class="sxs-lookup"><span data-stu-id="d2cce-160">No</span></span>  <br/> |<span data-ttu-id="d2cce-161">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-161">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-162">视频指标</span><span class="sxs-lookup"><span data-stu-id="d2cce-162">Video metrics</span></span>  <br/> |<span data-ttu-id="d2cce-163">否</span><span class="sxs-lookup"><span data-stu-id="d2cce-163">No</span></span>  <br/> |<span data-ttu-id="d2cce-164">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-164">Yes</span></span>  <br/> |
|<span data-ttu-id="d2cce-165">可用的数据量</span><span class="sxs-lookup"><span data-stu-id="d2cce-165">Amount of data available</span></span>  <br/> |<span data-ttu-id="d2cce-166">过去 6 个月</span><span class="sxs-lookup"><span data-stu-id="d2cce-166">Last 6 months</span></span>  <br/> |<span data-ttu-id="d2cce-167">过去 6 个月</span><span class="sxs-lookup"><span data-stu-id="d2cce-167">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="d2cce-168">Microsoft 团队数据</span><span class="sxs-lookup"><span data-stu-id="d2cce-168">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="d2cce-169">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-169">Yes</span></span>  <br/> |<span data-ttu-id="d2cce-170">是</span><span class="sxs-lookup"><span data-stu-id="d2cce-170">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="d2cce-171">即开报告</span><span class="sxs-lookup"><span data-stu-id="d2cce-171">Out-of-the-box reports</span></span>

<span data-ttu-id="d2cce-172">CQD 这两个版本提供的-全新体验，请为您提供呼叫质量指标，无需创建任何新的报表。</span><span class="sxs-lookup"><span data-stu-id="d2cce-172">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="d2cce-173">一旦在后端处理数据时，您可以开始查看在报告呼叫质量数据。</span><span class="sxs-lookup"><span data-stu-id="d2cce-173">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="d2cce-174">概述报告</span><span class="sxs-lookup"><span data-stu-id="d2cce-174">Overview reports</span></span>

<span data-ttu-id="d2cce-175">CQD 这两个版本提供高级入口点的整个呼叫质量信息，但信息显示在摘要报表的方式是不同的详细报告。</span><span class="sxs-lookup"><span data-stu-id="d2cce-175">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="d2cce-176">摘要报告提供使用户能够快速浏览和了解整个呼叫质量状态和趋势的简化的选项卡式的页面报表视图。</span><span class="sxs-lookup"><span data-stu-id="d2cce-176">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="d2cce-177">四个选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="d2cce-177">The four tabs include:</span></span>
  
- <span data-ttu-id="d2cce-178">**总体呼叫质量**-提供有关所有流，即服务器到客户端流聚合和客户端客户端流，以及单独的服务器到客户端和客户端客户端流时，在每月和每日的趋势的窗体的信息。</span><span class="sxs-lookup"><span data-stu-id="d2cce-178">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="d2cce-179">**服务器的客户端**-服务器和客户端终结点之间的流提供其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="d2cce-179">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="d2cce-180">**客户端的客户端**-提供两个客户端终结点之间的流的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="d2cce-180">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="d2cce-181">**语音质量 SLA** -提供有关呼叫的业务联机语音质量 SLA Skype 中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="d2cce-181">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="d2cce-182">总体呼叫质量选项卡</span><span class="sxs-lookup"><span data-stu-id="d2cce-182">Overall Call Quality tab</span></span>

<span data-ttu-id="d2cce-183">使用此选项卡上的数据评估呼叫质量状态和趋势看流计数和质量欠佳的百分比。</span><span class="sxs-lookup"><span data-stu-id="d2cce-183">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="d2cce-184">在右上角的图例显示的颜色和可视元素表示这些指标。</span><span class="sxs-lookup"><span data-stu-id="d2cce-184">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![CQD 数据键](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="d2cce-186">流分为三个组： 良好、 不佳，和未分类。</span><span class="sxs-lookup"><span data-stu-id="d2cce-186">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="d2cce-187">存在进行还计算*差 %* 值的授予您的流比率归类为*质量欠佳*到总保密的流计数。</span><span class="sxs-lookup"><span data-stu-id="d2cce-187">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="d2cce-188">由于*差 %= 差流 / （不佳流 + 良好流） \* 100* ，这将使*差 %* 受到与多个*自解除保密*流状态。</span><span class="sxs-lookup"><span data-stu-id="d2cce-188">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="d2cce-189">有关将用于分类为质量欠佳或良好流，请参阅[呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="d2cce-189">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="d2cce-190">使用左侧刻度度量值流计数。</span><span class="sxs-lookup"><span data-stu-id="d2cce-190">Use the scale on the left to measure the stream count values.</span></span>
  
![CQD 数据计数](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="d2cce-192">使用右侧比例来测量的差 %值。</span><span class="sxs-lookup"><span data-stu-id="d2cce-192">Use the scale on the right to measure the Poor % values.</span></span>
  
![CQD 数据每年会](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="d2cce-194">您还可以通过将鼠标悬停在条上获取实际数值。</span><span class="sxs-lookup"><span data-stu-id="d2cce-194">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2cce-195">下面的示例是一个非常小示例数据集，从，值不是实际的实际部署。</span><span class="sxs-lookup"><span data-stu-id="d2cce-195">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![CQD 数据数字](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="d2cce-197">整体流卷是确定如何相关差的计算的百分比的重要因素。</span><span class="sxs-lookup"><span data-stu-id="d2cce-197">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="d2cce-198">整体流量较小，不可靠的报告不佳的百分比值。</span><span class="sxs-lookup"><span data-stu-id="d2cce-198">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="d2cce-199">服务器到客户端选项卡和客户端客户端选项卡</span><span class="sxs-lookup"><span data-stu-id="d2cce-199">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="d2cce-200">以下两个选项卡提供其他详细信息发生在其终结点到终结点方案中的流。</span><span class="sxs-lookup"><span data-stu-id="d2cce-200">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="d2cce-201">这两个选项卡具有四个可折叠部分，表示将在其下流媒体流的四种情况。</span><span class="sxs-lookup"><span data-stu-id="d2cce-201">Both tabs have four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="d2cce-202">有线内</span><span class="sxs-lookup"><span data-stu-id="d2cce-202">Wired Inside</span></span>
    
- <span data-ttu-id="d2cce-203">外部有线</span><span class="sxs-lookup"><span data-stu-id="d2cce-203">Wired Outside</span></span>
    
- <span data-ttu-id="d2cce-204">Wifi 内部</span><span class="sxs-lookup"><span data-stu-id="d2cce-204">Wifi Inside</span></span>
    
- <span data-ttu-id="d2cce-205">Wifi 以外</span><span class="sxs-lookup"><span data-stu-id="d2cce-205">Wifi Outside</span></span>
    
#### <a name="inside-test"></a><span data-ttu-id="d2cce-206">内部测试</span><span class="sxs-lookup"><span data-stu-id="d2cce-206">Inside Test</span></span>

<span data-ttu-id="d2cce-207">在处理期间，CQD 后端分类为*内部*或*外部*使用构建信息流，如果存在。</span><span class="sxs-lookup"><span data-stu-id="d2cce-207">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="d2cce-208">终结点的每个流是与子网地址关联。</span><span class="sxs-lookup"><span data-stu-id="d2cce-208">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="d2cce-209">如果子网为子 InsideCorp 标记中上载的构建信息的列表中，将其视为*内部*。</span><span class="sxs-lookup"><span data-stu-id="d2cce-209">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="d2cce-210">如果在构建信息具有尚未上载内, 测试将始终为*外部*分类流。</span><span class="sxs-lookup"><span data-stu-id="d2cce-210">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="d2cce-211">请注意，内部服务器到客户端方案的测试只考虑客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="d2cce-211">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="d2cce-212">因为服务器始终之外从用户的角度来看，这不占测试中。</span><span class="sxs-lookup"><span data-stu-id="d2cce-212">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="d2cce-213">与 wifi 有线</span><span class="sxs-lookup"><span data-stu-id="d2cce-213">Wired vs. wifi</span></span>

<span data-ttu-id="d2cce-214">指示名称，这是基于客户端连接类型分类标准。</span><span class="sxs-lookup"><span data-stu-id="d2cce-214">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="d2cce-215">同样，服务器始终有线，且该不包含计算中。</span><span class="sxs-lookup"><span data-stu-id="d2cce-215">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2cce-216">如果两个终结点之一连接到 Wifi 网络给定流，然后归为 Wifi CQD 中。</span><span class="sxs-lookup"><span data-stu-id="d2cce-216">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="d2cce-217">选择要查看报告中的产品数据</span><span class="sxs-lookup"><span data-stu-id="d2cce-217">Selecting product data to see in reports</span></span>
<span data-ttu-id="d2cce-218"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="d2cce-218"></span></span>

<span data-ttu-id="d2cce-219">在摘要和位置增强报告中，您可以使用**产品筛选器**下拉列表以显示所有产品数据，只有 Microsoft 团队数据或仅联机业务数据的 Skype。</span><span class="sxs-lookup"><span data-stu-id="d2cce-219">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![屏幕快照显示了具有所有选项、 Microsoft 团队和 for Business 的 Skype 的产品筛选器控件。](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="d2cce-221">在详细的报告，您可以使用**是团队**维度筛选 Online 业务数据的报表定义一部分的 Microsoft 团队或 Skype 的数据。</span><span class="sxs-lookup"><span data-stu-id="d2cce-221">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-building-information"></a><span data-ttu-id="d2cce-222">上载构建信息</span><span class="sxs-lookup"><span data-stu-id="d2cce-222">Upload Building information</span></span>
<span data-ttu-id="d2cce-223"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="d2cce-223"></span></span>

<span data-ttu-id="d2cce-224">CQD 摘要报告仪表板包含一个**租户数据上载**的页，通过从右上角的设置菜单中选择**租户数据上载**访问。</span><span class="sxs-lookup"><span data-stu-id="d2cce-224">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="d2cce-225">此页用于 admins 上载他们自己的信息，如映射的 IP 地址和地理信息，每个无线 AP 和其 MAC 地址映射，等等。</span><span class="sxs-lookup"><span data-stu-id="d2cce-225">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, etc.</span></span>
  
![CQD 仪表板](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="d2cce-227">在**租户数据上载**页上，使用下拉菜单中选择上载的数据文件类型。</span><span class="sxs-lookup"><span data-stu-id="d2cce-227">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="d2cce-228">文件数据类型表示文件的内容 （例如，"Building"指的 IP 地址映射和构建以及其他地理信息）。</span><span class="sxs-lookup"><span data-stu-id="d2cce-228">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information).</span></span> <span data-ttu-id="d2cce-229">当前我们要仅支持"构建"数据类型。</span><span class="sxs-lookup"><span data-stu-id="d2cce-229">Currently we are only supporting the "Building" data type.</span></span> <span data-ttu-id="d2cce-230">将与后续版本添加几个更多的数据类型。</span><span class="sxs-lookup"><span data-stu-id="d2cce-230">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="d2cce-231">选择后的文件数据类型，单击**浏览**选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="d2cce-231">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="d2cce-232">数据文件必须.tsv （制表符分隔值） 文件或.csv （以逗号分隔值） 文件。</span><span class="sxs-lookup"><span data-stu-id="d2cce-232">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="d2cce-233">如果使用.csv 文件，包含逗号分隔的任何字段必须用引号引起来，或已删除的逗号。</span><span class="sxs-lookup"><span data-stu-id="d2cce-233">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="d2cce-234">例如，如果您构建的名称是 NY，NY.csv 文件中其应以输入"NY，NY"。</span><span class="sxs-lookup"><span data-stu-id="d2cce-234">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="d2cce-235">数据文件必须是不超过 50 MB 的大小。</span><span class="sxs-lookup"><span data-stu-id="d2cce-235">The data file must be no larger than 50MB in size.</span></span>
    
   - <span data-ttu-id="d2cce-236">对于每个数据文件，文件中的每个列必须匹配一个预定义的数据类型，本主题后面所述。</span><span class="sxs-lookup"><span data-stu-id="d2cce-236">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="d2cce-237">选择数据文件之后，指定**开始日期**和 （可选）**指定的结束日期**。</span><span class="sxs-lookup"><span data-stu-id="d2cce-237">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="d2cce-238">选择后**开始日期**，选择**上载**以将文件上载到 CQD 服务器。</span><span class="sxs-lookup"><span data-stu-id="d2cce-238">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="d2cce-239">上载文件之前，请首先验证。</span><span class="sxs-lookup"><span data-stu-id="d2cce-239">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="d2cce-240">一旦验证，它在 Azure blob 存储。</span><span class="sxs-lookup"><span data-stu-id="d2cce-240">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="d2cce-241">如果验证失败或文件无法在 Azure 的 blob 存储请求更正文件显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="d2cce-241">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="d2cce-242">下图显示在数据文件中的列数不正确时出现错误。</span><span class="sxs-lookup"><span data-stu-id="d2cce-242">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![CQD 示例上载验证错误](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="d2cce-244">如果验证过程中不发生任何错误，将会成功上载文件。</span><span class="sxs-lookup"><span data-stu-id="d2cce-244">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="d2cce-245">您随后可以看到**我上载**表，其中显示所有上载文件的完整列表，该页面底部当前租户中上载的数据文件。</span><span class="sxs-lookup"><span data-stu-id="d2cce-245">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="d2cce-246">每个记录显示一个上载的租户数据文件的文件类型、 上次更新时间、 时间段、 说明、 删除图标和下载图标。</span><span class="sxs-lookup"><span data-stu-id="d2cce-246">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="d2cce-247">若要删除文件，请选择表中的回收站图标。</span><span class="sxs-lookup"><span data-stu-id="d2cce-247">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="d2cce-248">若要下载文件，在**下载**列中的表中选择下载图标。</span><span class="sxs-lookup"><span data-stu-id="d2cce-248">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![CQD 我上载表](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a><span data-ttu-id="d2cce-250">租户数据文件格式和构建数据文件结构</span><span class="sxs-lookup"><span data-stu-id="d2cce-250">Tenant data file format and Building data file structure</span></span>
<span data-ttu-id="d2cce-251"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="d2cce-251"></span></span>

<span data-ttu-id="d2cce-252">您上载的数据文件的格式必须满足以下内容以通过在上载之前验证检查。</span><span class="sxs-lookup"><span data-stu-id="d2cce-252">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="d2cce-253">文件必须.tsv 文件，这意味着在每个行中，列分隔选项卡上或以逗号分隔每一列的.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="d2cce-253">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="d2cce-254">数据文件的内容不包括表格标题。</span><span class="sxs-lookup"><span data-stu-id="d2cce-254">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="d2cce-255">不头，表示的数据文件的第一行应该真实数据，如"网络"等。</span><span class="sxs-lookup"><span data-stu-id="d2cce-255">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="d2cce-256">每个列的数据类型仅可以是字符串、 号码或 Bool。</span><span class="sxs-lookup"><span data-stu-id="d2cce-256">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="d2cce-257">如果它是数字，值必须是数值;如果是 Bool，值必须是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="d2cce-257">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="d2cce-258">每个列的数据类型为 string，如果数据可以为空 （但仍必须用相应的分隔符 （即，选项卡或逗号分隔） 分隔。</span><span class="sxs-lookup"><span data-stu-id="d2cce-258">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="d2cce-259">这只是分配该字段空字符串值。</span><span class="sxs-lookup"><span data-stu-id="d2cce-259">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="d2cce-260">必须为每个行的 14 列，每个列必须具有以下数据类型和列必须下表中列出的顺序：</span><span class="sxs-lookup"><span data-stu-id="d2cce-260">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="d2cce-261">**列名称**</span><span class="sxs-lookup"><span data-stu-id="d2cce-261">**Column Name**</span></span>|<span data-ttu-id="d2cce-262">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d2cce-262">**Data type**</span></span>|<span data-ttu-id="d2cce-263">**示例**</span><span class="sxs-lookup"><span data-stu-id="d2cce-263">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d2cce-264">网络</span><span class="sxs-lookup"><span data-stu-id="d2cce-264">Network</span></span>  <br/> |<span data-ttu-id="d2cce-265">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-265">String</span></span>  <br/> |<span data-ttu-id="d2cce-266">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="d2cce-266">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="d2cce-267">NetworkName</span><span class="sxs-lookup"><span data-stu-id="d2cce-267">NetworkName</span></span>  <br/> |<span data-ttu-id="d2cce-268">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-268">String</span></span>  <br/> |<span data-ttu-id="d2cce-269">美国/西雅图/西雅图-SEA-1</span><span class="sxs-lookup"><span data-stu-id="d2cce-269">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="d2cce-270">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="d2cce-270">NetworkRange</span></span>  <br/> |<span data-ttu-id="d2cce-271">数字</span><span class="sxs-lookup"><span data-stu-id="d2cce-271">Number</span></span>  <br/> |<span data-ttu-id="d2cce-272">26</span><span class="sxs-lookup"><span data-stu-id="d2cce-272">26</span></span>  <br/> |
|<span data-ttu-id="d2cce-273">BuildingName</span><span class="sxs-lookup"><span data-stu-id="d2cce-273">BuildingName</span></span>  <br/> |<span data-ttu-id="d2cce-274">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-274">String</span></span>  <br/> |<span data-ttu-id="d2cce-275">西雅图-SEA-1</span><span class="sxs-lookup"><span data-stu-id="d2cce-275">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="d2cce-276">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="d2cce-276">OwnershipType</span></span>  <br/> |<span data-ttu-id="d2cce-277">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-277">String</span></span>  <br/> |<span data-ttu-id="d2cce-278">Contoso</span><span class="sxs-lookup"><span data-stu-id="d2cce-278">Contoso</span></span>  <br/> |
|<span data-ttu-id="d2cce-279">BuildingType</span><span class="sxs-lookup"><span data-stu-id="d2cce-279">BuildingType</span></span>  <br/> |<span data-ttu-id="d2cce-280">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-280">String</span></span>  <br/> |<span data-ttu-id="d2cce-281">IT 终止</span><span class="sxs-lookup"><span data-stu-id="d2cce-281">IT Termination</span></span>  <br/> |
|<span data-ttu-id="d2cce-282">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="d2cce-282">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="d2cce-283">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-283">String</span></span>  <br/> |<span data-ttu-id="d2cce-284">Engineering</span><span class="sxs-lookup"><span data-stu-id="d2cce-284">Engineering</span></span>  <br/> |
|<span data-ttu-id="d2cce-285">城市</span><span class="sxs-lookup"><span data-stu-id="d2cce-285">City</span></span>  <br/> |<span data-ttu-id="d2cce-286">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-286">String</span></span>  <br/> |<span data-ttu-id="d2cce-287">西雅图</span><span class="sxs-lookup"><span data-stu-id="d2cce-287">Seattle</span></span>  <br/> |
|<span data-ttu-id="d2cce-288">邮政编码</span><span class="sxs-lookup"><span data-stu-id="d2cce-288">ZipCode</span></span>  <br/> |<span data-ttu-id="d2cce-289">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-289">String</span></span>  <br/> |<span data-ttu-id="d2cce-290">98001</span><span class="sxs-lookup"><span data-stu-id="d2cce-290">98001</span></span>  <br/> |
|<span data-ttu-id="d2cce-291">国家/地区</span><span class="sxs-lookup"><span data-stu-id="d2cce-291">Country</span></span>  <br/> |<span data-ttu-id="d2cce-292">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-292">String</span></span>  <br/> |<span data-ttu-id="d2cce-293">我们</span><span class="sxs-lookup"><span data-stu-id="d2cce-293">US</span></span>  <br/> |
|<span data-ttu-id="d2cce-294">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="d2cce-294">State</span></span>  <br/> |<span data-ttu-id="d2cce-295">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-295">String</span></span>  <br/> |<span data-ttu-id="d2cce-296">WA</span><span class="sxs-lookup"><span data-stu-id="d2cce-296">WA</span></span>  <br/> |
|<span data-ttu-id="d2cce-297">区域</span><span class="sxs-lookup"><span data-stu-id="d2cce-297">Region</span></span>  <br/> |<span data-ttu-id="d2cce-298">字符串</span><span class="sxs-lookup"><span data-stu-id="d2cce-298">String</span></span>  <br/> |<span data-ttu-id="d2cce-299">MSU</span><span class="sxs-lookup"><span data-stu-id="d2cce-299">MSUS</span></span>  <br/> |
|<span data-ttu-id="d2cce-300">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="d2cce-300">InsideCorp</span></span>  <br/> |<span data-ttu-id="d2cce-301">Bool</span><span class="sxs-lookup"><span data-stu-id="d2cce-301">Bool</span></span>  <br/> |<span data-ttu-id="d2cce-302">1</span><span class="sxs-lookup"><span data-stu-id="d2cce-302">1</span></span>  <br/> |
|<span data-ttu-id="d2cce-303">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="d2cce-303">ExpressRoute</span></span>  <br/> |<span data-ttu-id="d2cce-304">Bool</span><span class="sxs-lookup"><span data-stu-id="d2cce-304">Bool</span></span>  <br/> |<span data-ttu-id="d2cce-305">0</span><span class="sxs-lookup"><span data-stu-id="d2cce-305">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="d2cce-306">网络范围可以用于表示 supernet （单个路由前缀开头的几个子网的组合）。</span><span class="sxs-lookup"><span data-stu-id="d2cce-306">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="d2cce-307">所有新的生成上载将检查有任何重叠的区域。</span><span class="sxs-lookup"><span data-stu-id="d2cce-307">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="d2cce-308">如果先前已上载的生成文件，您应将当前文件下载并重新上载以找出任何重叠并再次上载之前修复问题。</span><span class="sxs-lookup"><span data-stu-id="d2cce-308">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="d2cce-309">重叠之前上载文件的任何情况可能会导致建筑物报告中的子网的错误映射。</span><span class="sxs-lookup"><span data-stu-id="d2cce-309">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="d2cce-310">某些 VPN 实现未准确报告的子网信息。</span><span class="sxs-lookup"><span data-stu-id="d2cce-310">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="d2cce-311">当将 VPN 子网添加到该生成文件，而不是一个条目的子网，建议的单独添加条目的 VPN 子网中每个地址作为单独的 32 位网络。</span><span class="sxs-lookup"><span data-stu-id="d2cce-311">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="d2cce-312">每行可以有相同的构建元数据。</span><span class="sxs-lookup"><span data-stu-id="d2cce-312">Each row can have the same building metadata.</span></span> <span data-ttu-id="d2cce-313">例如，而不是一个 172.16.18.0/24 行中，您应具有 256 行，通过为每个地址之间 172.16.18.0/32 172.16.18.255/32，非独占一行。</span><span class="sxs-lookup"><span data-stu-id="d2cce-313">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 
  
## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="d2cce-314">详细的报告中的选择媒体类型</span><span class="sxs-lookup"><span data-stu-id="d2cce-314">Selecting media type in detailed reports</span></span>
<span data-ttu-id="d2cce-315"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="d2cce-315"></span></span>

<span data-ttu-id="d2cce-316">详细的报告支持看质量和媒体可靠性的音频、 视频、 应用程序共享和基于视频的屏幕共享的媒体类型。</span><span class="sxs-lookup"><span data-stu-id="d2cce-316">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="d2cce-317">维度、 度量和特定于单个媒体类型的筛选器具有"音频"、"视频"、"的"或"VBSS"作为前缀。</span><span class="sxs-lookup"><span data-stu-id="d2cce-317">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![呼叫质量仪表板尺寸。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="d2cce-319">如果您想要查看的维度和度量的单个媒体类型，可能需要的新 MediaType 维度和筛选器。</span><span class="sxs-lookup"><span data-stu-id="d2cce-319">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="d2cce-320">例如，要让显示会话总数的计数不同媒体类型的报告，包括 MediaType 维度。</span><span class="sxs-lookup"><span data-stu-id="d2cce-320">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![呼叫质量仪表板总流计数。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="d2cce-322">相关主题</span><span class="sxs-lookup"><span data-stu-id="d2cce-322">Related topics</span></span>
[<span data-ttu-id="d2cce-323">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="d2cce-323">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="d2cce-324">使用呼叫分析解决质量欠佳的呼叫质量</span><span class="sxs-lookup"><span data-stu-id="d2cce-324">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="d2cce-325">呼叫分析和呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="d2cce-325">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 