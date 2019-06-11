---
title: 'Lync Server 2013: 使用 "监视" 仪表板'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50c5a435baf9ef6b2ef24e235270326507b68789
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="0ab3e-102">在 Lync Server 2013 中使用 "监视" 仪表板</span><span class="sxs-lookup"><span data-stu-id="0ab3e-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ab3e-103">_**主题上次修改时间:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="0ab3e-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="0ab3e-104">"监视" 仪表板为管理员提供其 Microsoft Lync Server 2013 系统运行状况和系统使用情况的快速概述。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="0ab3e-105">该仪表板设计为显示关键系统指标的聚合视图，这通过显示以下内容来实现：</span><span class="sxs-lookup"><span data-stu-id="0ab3e-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="0ab3e-p102">当天汇总。请注意，显示的当天数值表示从午夜开始记录到当前时间的数据（基于报告服务器的本地时间）。这意味着您通常看到的是一天数据的一部分，而不是 24 小时的数据。例如，服务器的本地时间是早上 8:00，您看到的是 8 个小时的数据，因为午夜到早上 8:00 之间有 8 个小时。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-p102">Totals for the current day. Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server). That means that you will typically be viewing data for a partial day and not for a 24-hour period. For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="0ab3e-110">周汇总，以及过去六周的趋势汇总。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="0ab3e-111">月汇总，以及过去六个月的趋势汇总（仅限系统使用情况）。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="0ab3e-112">请注意, 你可以使用[CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet 返回用于访问 Lync Server 2013 监视报告的 URL:</span><span class="sxs-lookup"><span data-stu-id="0ab3e-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="0ab3e-113">默认情况下，监控仪表板显示当周的以下指标数据（以及过去六周的趋势汇总）：</span><span class="sxs-lookup"><span data-stu-id="0ab3e-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="0ab3e-114">系统使用情况指标</span><span class="sxs-lookup"><span data-stu-id="0ab3e-114">System Usage Metrics</span></span>

<span data-ttu-id="0ab3e-115">**注册**</span><span class="sxs-lookup"><span data-stu-id="0ab3e-115">**Registration**</span></span>

  - <span data-ttu-id="0ab3e-116">唯一用户登录</span><span class="sxs-lookup"><span data-stu-id="0ab3e-116">Unique user logons</span></span>

<span data-ttu-id="0ab3e-117">**对等**</span><span class="sxs-lookup"><span data-stu-id="0ab3e-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="0ab3e-118">会话总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-118">Total sessions</span></span>

  - <span data-ttu-id="0ab3e-119">IM 会话</span><span class="sxs-lookup"><span data-stu-id="0ab3e-119">IM sessions</span></span>

  - <span data-ttu-id="0ab3e-120">音频会话</span><span class="sxs-lookup"><span data-stu-id="0ab3e-120">Audio sessions</span></span>

  - <span data-ttu-id="0ab3e-121">视频会话数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-121">Video sessions</span></span>

  - <span data-ttu-id="0ab3e-122">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="0ab3e-122">Application sharing</span></span>

  - <span data-ttu-id="0ab3e-123">音频会话总分钟数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-123">Total audio session minutes</span></span>

  - <span data-ttu-id="0ab3e-124">音频会话平均分钟数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-124">Avg. audio session minutes</span></span>

<span data-ttu-id="0ab3e-125">**会议**</span><span class="sxs-lookup"><span data-stu-id="0ab3e-125">**Conference**</span></span>

  - <span data-ttu-id="0ab3e-126">会议总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-126">Total conferences</span></span>

  - <span data-ttu-id="0ab3e-127">IM 会议</span><span class="sxs-lookup"><span data-stu-id="0ab3e-127">IM conferences</span></span>

  - <span data-ttu-id="0ab3e-128">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="0ab3e-128">A/V conferences</span></span>

  - <span data-ttu-id="0ab3e-129">应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="0ab3e-129">Application sharing conferences</span></span>

  - <span data-ttu-id="0ab3e-130">Web 会议</span><span class="sxs-lookup"><span data-stu-id="0ab3e-130">Web conferences</span></span>

  - <span data-ttu-id="0ab3e-131">组织者总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-131">Total organizers</span></span>

  - <span data-ttu-id="0ab3e-132">A/V 会议总分钟数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="0ab3e-133">A/V 会议平均分钟数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="0ab3e-134">PSTN 会议总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="0ab3e-135">PSTN 参与者总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-135">Total PSTN participants</span></span>

  - <span data-ttu-id="0ab3e-136">PSTN 参与者总分钟数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="0ab3e-137">除了系统使用情况指标之外，以下指标也显示当天和过去六天的汇总（如果选择“**周视图**”）或者当周和过去六周的汇总（如果选择“**月视图**”）。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="0ab3e-138">每用户呼叫诊断</span><span class="sxs-lookup"><span data-stu-id="0ab3e-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="0ab3e-139">**呼叫失败的用户**</span><span class="sxs-lookup"><span data-stu-id="0ab3e-139">**Users with call failures**</span></span>

  - <span data-ttu-id="0ab3e-140">呼叫失败的用户总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-140">Total users with call failures</span></span>

  - <span data-ttu-id="0ab3e-141">呼叫失败的会议组织者</span><span class="sxs-lookup"><span data-stu-id="0ab3e-141">Conference organizers with call failures</span></span>

<span data-ttu-id="0ab3e-142">**劣质呼叫的用户**</span><span class="sxs-lookup"><span data-stu-id="0ab3e-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="0ab3e-143">遇到劣质呼叫的用户总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="0ab3e-144">呼叫诊断</span><span class="sxs-lookup"><span data-stu-id="0ab3e-144">Call Diagnostics</span></span>

<span data-ttu-id="0ab3e-145">对等</span><span class="sxs-lookup"><span data-stu-id="0ab3e-145">Peer-to-peer</span></span>

  - <span data-ttu-id="0ab3e-146">失败总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-146">Total failures</span></span>

  - <span data-ttu-id="0ab3e-147">总体失败率</span><span class="sxs-lookup"><span data-stu-id="0ab3e-147">Overall failure rate</span></span>

  - <span data-ttu-id="0ab3e-148">IM 失败率</span><span class="sxs-lookup"><span data-stu-id="0ab3e-148">IM failure rate</span></span>

  - <span data-ttu-id="0ab3e-149">音频失败率</span><span class="sxs-lookup"><span data-stu-id="0ab3e-149">Audio failure rate</span></span>

  - <span data-ttu-id="0ab3e-150">应用程序共享失败率</span><span class="sxs-lookup"><span data-stu-id="0ab3e-150">Application sharing failure rate</span></span>

<span data-ttu-id="0ab3e-151">会议</span><span class="sxs-lookup"><span data-stu-id="0ab3e-151">Conference</span></span>

  - <span data-ttu-id="0ab3e-152">失败总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-152">Total failures</span></span>

  - <span data-ttu-id="0ab3e-153">总体失败率</span><span class="sxs-lookup"><span data-stu-id="0ab3e-153">Overall failure rate</span></span>

  - <span data-ttu-id="0ab3e-154">IM 失败率</span><span class="sxs-lookup"><span data-stu-id="0ab3e-154">IM failure rate</span></span>

  - <span data-ttu-id="0ab3e-155">A/V 失败率</span><span class="sxs-lookup"><span data-stu-id="0ab3e-155">A/V failure rate</span></span>

  - <span data-ttu-id="0ab3e-156">应用程序共享失败率</span><span class="sxs-lookup"><span data-stu-id="0ab3e-156">Application sharing failure rate</span></span>

<span data-ttu-id="0ab3e-157">按失败会话列出的前 5 个服务器</span><span class="sxs-lookup"><span data-stu-id="0ab3e-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="0ab3e-158">媒体质量诊断</span><span class="sxs-lookup"><span data-stu-id="0ab3e-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="0ab3e-159">对等</span><span class="sxs-lookup"><span data-stu-id="0ab3e-159">Peer-to-peer</span></span>

  - <span data-ttu-id="0ab3e-160">劣质呼叫总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-160">Total poor quality calls</span></span>

  - <span data-ttu-id="0ab3e-161">劣质呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="0ab3e-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="0ab3e-162">劣质 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="0ab3e-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="0ab3e-163">会议</span><span class="sxs-lookup"><span data-stu-id="0ab3e-163">Conference</span></span>

  - <span data-ttu-id="0ab3e-164">劣质呼叫总数</span><span class="sxs-lookup"><span data-stu-id="0ab3e-164">Total poor quality calls</span></span>

  - <span data-ttu-id="0ab3e-165">劣质呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="0ab3e-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="0ab3e-166">劣质 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="0ab3e-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="0ab3e-167">按劣质呼叫百分比列出的最差服务器</span><span class="sxs-lookup"><span data-stu-id="0ab3e-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="0ab3e-168">使用监控仪表板</span><span class="sxs-lookup"><span data-stu-id="0ab3e-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="0ab3e-p103">如前文所述，默认情况下显示当周的汇总以及过去六周的趋势值。如果您希望查看当月汇总（以及过去六个月的趋势值），请单击仪表板右上角的“**月视图**”链接。如果您决定查看月汇总，该链接文本将更改为“**周视图**”。您可以单击该链接切换回周视图。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0ab3e-p104">监控仪表板限制您只能查看当周（或当月）的汇总以及过去六周（或六个月）的趋势值。您不能更改这些日期和时间。例如，不能使用仪表板查看从九个月前开始的时间段的报告汇总。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="0ab3e-p105">“**本周**”、“**本月**”或“**今天**”列中显示的值可链接到项目的更详细信息。请记住，列中显示的列名称和值通常会不同，具体取决于所选指标以及您选择了周视图还是月视图。例如，如果单击针对“**唯一用户登录数**”指标显示的汇总，您将看到指定时间段的“**用户注册报告**”。您可以随时单击“**仪表板**”返回到监控仪表板。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0ab3e-180">您也可以通过单击仪表板右上角的 "<STRONG>报告</STRONG>" 链接来访问 "监视服务器报告" 主页。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="0ab3e-181">“**趋势**”列显示简单的折线图，表示过去六周（或者过去六天或六个月，具体取决于指标和时间间隔）的汇总。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="0ab3e-182">这些简单的折线图为每个时间段显示一个未标记的数据点（例如，过去六周的每周对应一个未标记的数据点）。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="0ab3e-183">但是，你可以通过将鼠标指针保持在图上来检索这些图的实际值。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="0ab3e-184">在这种情况下, 工具提示会显示图形中的最大值和最小值。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="0ab3e-185">从监控仪表板导出数据</span><span class="sxs-lookup"><span data-stu-id="0ab3e-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="0ab3e-p107">监控仪表板提供了多种方式导出当前仪表板视图。在仪表板工具栏上，您将看到一个看起来是附加了绿色箭头的软盘的图标。如果单击此图标，将显示一个下拉列表，为您提供以下数据导出格式：</span><span class="sxs-lookup"><span data-stu-id="0ab3e-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="0ab3e-189">含有报告数据的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="0ab3e-189">XML file with report data</span></span>

  - <span data-ttu-id="0ab3e-190">CSV（逗号分隔）</span><span class="sxs-lookup"><span data-stu-id="0ab3e-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="0ab3e-191">PDF</span><span class="sxs-lookup"><span data-stu-id="0ab3e-191">PDF</span></span>

  - <span data-ttu-id="0ab3e-192">MHTML（Web 存档）</span><span class="sxs-lookup"><span data-stu-id="0ab3e-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="0ab3e-193">Excel</span><span class="sxs-lookup"><span data-stu-id="0ab3e-193">Excel</span></span>

  - <span data-ttu-id="0ab3e-194">TIFF 文件</span><span class="sxs-lookup"><span data-stu-id="0ab3e-194">TIFF file</span></span>

  - <span data-ttu-id="0ab3e-195">Word</span><span class="sxs-lookup"><span data-stu-id="0ab3e-195">Word</span></span>

<span data-ttu-id="0ab3e-196">要导出当前的仪表板视图（及其值），请单击所需的导出选项。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="0ab3e-197">Lync Server 2013 生成指定格式的报表, 然后提供打开该报表或保存该报表的选项。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="0ab3e-198">请注意, 默认情况下, Lync Server 标题为 "报告**监视" 仪表板**, 并将其保存到 "下载" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="0ab3e-199">要向报告赋予不同名称或将其存储到不同的文件夹，请单击“**保存**”按钮旁边的箭头，然后单击“**另存为**”。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="0ab3e-200">如果您同意“**监控仪表板**”的名称并让报告保存在“下载”文件夹，只需单击“**保存**”按钮。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="0ab3e-p109">当您尝试导出仪表板数据时，可能会显示“**安全警报**”对话框连同消息“您的当前设置不允许下载此文件。”如果发生这种情况，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ab3e-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>

  - <span data-ttu-id="0ab3e-203">在 Internet Explorer 中，选择“**Internet 选项**”。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="0ab3e-204">在“**Internet 选项**”对话框中的“**安全**”选项卡上，单击“**受信任的站点**”，然后单击“**站点**”。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="0ab3e-205">在 "**受信任的网站**" 对话框中, 单击 "**添加**" 以将运行 lync Server 2013 报告的 lync server 2013 添加到受信任的网站的集合。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="0ab3e-206">单击“**关闭**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="0ab3e-p110">随后需要刷新监控仪表板才能使更改生效。为此，请按 F5  或单击仪表板工具栏上的“**刷新**”图标。（“**刷新**”图标是一个含有绿色箭头的圆圈。）</span><span class="sxs-lookup"><span data-stu-id="0ab3e-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="0ab3e-p111">您还可以创建包括实时数据馈送的 Excel 电子表格，其中包括最新的监控仪表板数据的链接。要创建实时数据馈送文件，请单击工具栏中橙色的“**导出到数据馈送**”图标。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="0ab3e-212">如果要打印当前仪表板，则单击工具栏中的打印机图标。</span><span class="sxs-lookup"><span data-stu-id="0ab3e-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

