---
title: 在 Skype for Business 服务器中使用 "监视" 仪表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: '摘要: 了解 Skype for Business 服务器中的 "监视" 仪表板。'
ms.openlocfilehash: 0ca85bff7cfcad7f3b64a4b0f5b92a22299e5719
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279926"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="a09f9-103">在 Skype for Business 服务器中使用 "监视" 仪表板</span><span class="sxs-lookup"><span data-stu-id="a09f9-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="a09f9-104">**摘要:** 了解 Skype for Business 服务器中的 "监视" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="a09f9-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="a09f9-105">"监视" 仪表板为管理员提供其 Skype for Business Server 系统运行状况和系统使用情况的快速概述。</span><span class="sxs-lookup"><span data-stu-id="a09f9-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="a09f9-106">该仪表板设计为显示关键系统指标的聚合视图，这通过显示以下内容来实现：</span><span class="sxs-lookup"><span data-stu-id="a09f9-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="a09f9-107">当天汇总。</span><span class="sxs-lookup"><span data-stu-id="a09f9-107">Totals for the current day.</span></span> <span data-ttu-id="a09f9-108">请注意，显示的当天数值表示从午夜开始记录到当前时间的数据（基于报告服务器的本地时间）。</span><span class="sxs-lookup"><span data-stu-id="a09f9-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="a09f9-109">这意味着您通常看到的是一天数据的一部分，而不是 24 小时的数据。</span><span class="sxs-lookup"><span data-stu-id="a09f9-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="a09f9-110">例如, 如果服务器的本地时间为 8:00 AM, 则会看到8小时的数据, 因为午夜和 8:00 AM 的当前时间之间有八个小时。</span><span class="sxs-lookup"><span data-stu-id="a09f9-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="a09f9-111">周汇总，以及过去六周的趋势汇总。</span><span class="sxs-lookup"><span data-stu-id="a09f9-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="a09f9-112">月汇总，以及过去六个月的趋势汇总（仅限系统使用情况）。</span><span class="sxs-lookup"><span data-stu-id="a09f9-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="a09f9-113">请注意, 你可以使用[CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet 返回用于访问 Skype For Business Server Monitoring REPORTS 的 URL:</span><span class="sxs-lookup"><span data-stu-id="a09f9-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```
Get-CsReportingConfiguration
```

<span data-ttu-id="a09f9-114">默认情况下，监控仪表板显示当周的以下指标数据（以及过去六周的趋势汇总）：</span><span class="sxs-lookup"><span data-stu-id="a09f9-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="a09f9-115">系统使用情况指标</span><span class="sxs-lookup"><span data-stu-id="a09f9-115">System Usage Metrics</span></span>

 <span data-ttu-id="a09f9-116">**注册**</span><span class="sxs-lookup"><span data-stu-id="a09f9-116">**Registration**</span></span>
  
- <span data-ttu-id="a09f9-117">唯一用户登录</span><span class="sxs-lookup"><span data-stu-id="a09f9-117">Unique user logons</span></span>
    
  <span data-ttu-id="a09f9-118">**对等**</span><span class="sxs-lookup"><span data-stu-id="a09f9-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="a09f9-119">会话总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-119">Total sessions</span></span>
    
- <span data-ttu-id="a09f9-120">IM 会话</span><span class="sxs-lookup"><span data-stu-id="a09f9-120">IM sessions</span></span>
    
- <span data-ttu-id="a09f9-121">音频会话</span><span class="sxs-lookup"><span data-stu-id="a09f9-121">Audio sessions</span></span>
    
- <span data-ttu-id="a09f9-122">视频会话数</span><span class="sxs-lookup"><span data-stu-id="a09f9-122">Video sessions</span></span>
    
- <span data-ttu-id="a09f9-123">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="a09f9-123">Application sharing</span></span>
    
- <span data-ttu-id="a09f9-124">音频会话总分钟数</span><span class="sxs-lookup"><span data-stu-id="a09f9-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="a09f9-125">音频会话平均分钟数</span><span class="sxs-lookup"><span data-stu-id="a09f9-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="a09f9-126">**会议**</span><span class="sxs-lookup"><span data-stu-id="a09f9-126">**Conference**</span></span>
  
- <span data-ttu-id="a09f9-127">会议总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-127">Total conferences</span></span>
    
- <span data-ttu-id="a09f9-128">IM 会议</span><span class="sxs-lookup"><span data-stu-id="a09f9-128">IM conferences</span></span>
    
- <span data-ttu-id="a09f9-129">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="a09f9-129">A/V conferences</span></span>
    
- <span data-ttu-id="a09f9-130">应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="a09f9-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="a09f9-131">Web 会议</span><span class="sxs-lookup"><span data-stu-id="a09f9-131">Web conferences</span></span>
    
- <span data-ttu-id="a09f9-132">组织者总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-132">Total organizers</span></span>
    
- <span data-ttu-id="a09f9-133">A/V 会议总分钟数</span><span class="sxs-lookup"><span data-stu-id="a09f9-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="a09f9-134">A/V 会议平均分钟数</span><span class="sxs-lookup"><span data-stu-id="a09f9-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="a09f9-135">PSTN 会议总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="a09f9-136">PSTN 参与者总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="a09f9-137">PSTN 参与者总分钟数</span><span class="sxs-lookup"><span data-stu-id="a09f9-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="a09f9-138">除了系统使用情况指标之外，以下指标也显示当天和过去六天的汇总（如果选择“**周视图**”）或者当周和过去六周的汇总（如果选择“**月视图**”）。</span><span class="sxs-lookup"><span data-stu-id="a09f9-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="a09f9-139">每用户呼叫诊断</span><span class="sxs-lookup"><span data-stu-id="a09f9-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="a09f9-140">**呼叫失败的用户**</span><span class="sxs-lookup"><span data-stu-id="a09f9-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="a09f9-141">呼叫失败的用户总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-141">Total users with call failures</span></span>
    
- <span data-ttu-id="a09f9-142">呼叫失败的会议组织者</span><span class="sxs-lookup"><span data-stu-id="a09f9-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="a09f9-143">**劣质呼叫的用户**</span><span class="sxs-lookup"><span data-stu-id="a09f9-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="a09f9-144">遇到劣质呼叫的用户总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="a09f9-145">呼叫诊断</span><span class="sxs-lookup"><span data-stu-id="a09f9-145">Call Diagnostics</span></span>

<span data-ttu-id="a09f9-146">对等</span><span class="sxs-lookup"><span data-stu-id="a09f9-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="a09f9-147">失败总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-147">Total failures</span></span>
    
- <span data-ttu-id="a09f9-148">总体失败率</span><span class="sxs-lookup"><span data-stu-id="a09f9-148">Overall failure rate</span></span>
    
- <span data-ttu-id="a09f9-149">IM 失败率</span><span class="sxs-lookup"><span data-stu-id="a09f9-149">IM failure rate</span></span>
    
- <span data-ttu-id="a09f9-150">音频失败率</span><span class="sxs-lookup"><span data-stu-id="a09f9-150">Audio failure rate</span></span>
    
- <span data-ttu-id="a09f9-151">应用程序共享失败率</span><span class="sxs-lookup"><span data-stu-id="a09f9-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="a09f9-152">会议</span><span class="sxs-lookup"><span data-stu-id="a09f9-152">Conference</span></span>
  
- <span data-ttu-id="a09f9-153">失败总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-153">Total failures</span></span>
    
- <span data-ttu-id="a09f9-154">总体失败率</span><span class="sxs-lookup"><span data-stu-id="a09f9-154">Overall failure rate</span></span>
    
- <span data-ttu-id="a09f9-155">IM 失败率</span><span class="sxs-lookup"><span data-stu-id="a09f9-155">IM failure rate</span></span>
    
- <span data-ttu-id="a09f9-156">A/V 失败率</span><span class="sxs-lookup"><span data-stu-id="a09f9-156">A/V failure rate</span></span>
    
- <span data-ttu-id="a09f9-157">应用程序共享失败率</span><span class="sxs-lookup"><span data-stu-id="a09f9-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="a09f9-158">按失败会话列出的前 5 个服务器</span><span class="sxs-lookup"><span data-stu-id="a09f9-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="a09f9-159">媒体质量诊断</span><span class="sxs-lookup"><span data-stu-id="a09f9-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="a09f9-160">对等</span><span class="sxs-lookup"><span data-stu-id="a09f9-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="a09f9-161">劣质呼叫总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="a09f9-162">劣质呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="a09f9-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="a09f9-163">劣质 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="a09f9-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="a09f9-164">会议</span><span class="sxs-lookup"><span data-stu-id="a09f9-164">Conference</span></span>
  
- <span data-ttu-id="a09f9-165">劣质呼叫总数</span><span class="sxs-lookup"><span data-stu-id="a09f9-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="a09f9-166">劣质呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="a09f9-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="a09f9-167">劣质 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="a09f9-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="a09f9-168">按劣质呼叫百分比列出的最差服务器</span><span class="sxs-lookup"><span data-stu-id="a09f9-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="a09f9-169">使用监控仪表板</span><span class="sxs-lookup"><span data-stu-id="a09f9-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="a09f9-p103">如前文所述，默认情况下显示当周的汇总以及过去六周的趋势值。如果您希望查看当月汇总（以及过去六个月的趋势值），请单击仪表板右上角的“**月视图**”链接。如果您决定查看月汇总，该链接文本将更改为“**周视图**”。您可以单击该链接切换回周视图。</span><span class="sxs-lookup"><span data-stu-id="a09f9-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="a09f9-p104">监控仪表板限制您只能查看当周（或当月）的汇总以及过去六周（或六个月）的趋势值。您不能更改这些日期和时间。例如，不能使用仪表板查看从九个月前开始的时间段的报告汇总。</span><span class="sxs-lookup"><span data-stu-id="a09f9-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="a09f9-p105">“**本周**”、“**本月**”或“**今天**”列中显示的值可链接到项目的更详细信息。请记住，列中显示的列名称和值通常会不同，具体取决于所选指标以及您选择了周视图还是月视图。例如，如果单击针对“**唯一用户登录数**”指标显示的汇总，您将看到指定时间段的“**用户注册报告**”。您可以随时单击“**仪表板**”返回到监控仪表板。</span><span class="sxs-lookup"><span data-stu-id="a09f9-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="a09f9-181">您也可以通过单击仪表板右上角的 "**报告**" 链接来访问 "监视服务器报告" 主页。</span><span class="sxs-lookup"><span data-stu-id="a09f9-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="a09f9-p106">“**趋势**”列显示简单的折线图，表示过去六周（或者过去六天或六个月，具体取决于指标和时间间隔）的汇总。这些简单的折线图为每个时间段显示一个未标记的数据点（例如，过去六周的每周对应一个未标记的数据点）。但是，你可以通过将鼠标指针保持在图上来检索这些图的实际值。在这种情况下，工具提示将显示图中的最大和最小值。</span><span class="sxs-lookup"><span data-stu-id="a09f9-p106">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months). These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks). However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph. In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="a09f9-186">从监控仪表板导出数据</span><span class="sxs-lookup"><span data-stu-id="a09f9-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="a09f9-p107">监控仪表板提供了多种方式导出当前仪表板视图。在仪表板工具栏上，您将看到一个看起来是附加了绿色箭头的软盘的图标。如果单击此图标，将显示一个下拉列表，为您提供以下数据导出格式：</span><span class="sxs-lookup"><span data-stu-id="a09f9-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="a09f9-190">含有报告数据的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="a09f9-190">XML file with report data</span></span>
    
- <span data-ttu-id="a09f9-191">CSV（逗号分隔）</span><span class="sxs-lookup"><span data-stu-id="a09f9-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="a09f9-192">PDF</span><span class="sxs-lookup"><span data-stu-id="a09f9-192">PDF</span></span>
    
- <span data-ttu-id="a09f9-193">MHTML（Web 存档）</span><span class="sxs-lookup"><span data-stu-id="a09f9-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="a09f9-194">Excel</span><span class="sxs-lookup"><span data-stu-id="a09f9-194">Excel</span></span>
    
- <span data-ttu-id="a09f9-195">TIFF 文件</span><span class="sxs-lookup"><span data-stu-id="a09f9-195">TIFF file</span></span>
    
- <span data-ttu-id="a09f9-196">Word</span><span class="sxs-lookup"><span data-stu-id="a09f9-196">Word</span></span>
    
<span data-ttu-id="a09f9-197">要导出当前的仪表板视图（及其值），请单击所需的导出选项。</span><span class="sxs-lookup"><span data-stu-id="a09f9-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="a09f9-198">Skype for Business 服务器以指定的格式生成报表, 然后提供打开该报表或保存该报表的选项。</span><span class="sxs-lookup"><span data-stu-id="a09f9-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="a09f9-199">请注意, 默认情况下, Skype for business 服务器标题为 "报告**监视" 仪表板**, 并将其保存到 "下载" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="a09f9-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="a09f9-200">要向报告赋予不同名称或将其存储到不同的文件夹，请单击“**保存**”按钮旁边的箭头，然后单击“**另存为**”。</span><span class="sxs-lookup"><span data-stu-id="a09f9-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="a09f9-201">如果您同意“**监控仪表板**”的名称并让报告保存在“下载”文件夹，只需单击“**保存**”按钮。</span><span class="sxs-lookup"><span data-stu-id="a09f9-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="a09f9-p109">当您尝试导出仪表板数据时，可能会显示“**安全警报**”对话框连同消息“您的当前设置不允许下载此文件。”如果发生这种情况，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a09f9-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>
  
- <span data-ttu-id="a09f9-204">在 Internet Explorer 中，选择“**Internet 选项**”。</span><span class="sxs-lookup"><span data-stu-id="a09f9-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="a09f9-205">在“**Internet 选项**”对话框中的“**安全**”选项卡上，单击“**受信任的站点**”，然后单击“**站点**”。</span><span class="sxs-lookup"><span data-stu-id="a09f9-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="a09f9-206">在 "**受信任的站点**" 对话框中, 单击 "**添加**" 以将运行 Skype for Business 服务器报告的 skype for business 服务器添加到受信任的网站的集合。</span><span class="sxs-lookup"><span data-stu-id="a09f9-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="a09f9-207">单击“**关闭**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a09f9-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="a09f9-p110">随后需要刷新监控仪表板才能使更改生效。为此，请按 F5  或单击仪表板工具栏上的“**刷新**”图标。（“**刷新**”图标是一个含有绿色箭头的圆圈。）</span><span class="sxs-lookup"><span data-stu-id="a09f9-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="a09f9-p111">您还可以创建包括实时数据馈送的 Excel 电子表格，其中包括最新的监控仪表板数据的链接。要创建实时数据馈送文件，请单击工具栏中橙色的“**导出到数据馈送**”图标。</span><span class="sxs-lookup"><span data-stu-id="a09f9-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="a09f9-213">如果要打印当前仪表板，则单击工具栏中的打印机图标。</span><span class="sxs-lookup"><span data-stu-id="a09f9-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

