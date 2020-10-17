---
title: Lync Server 2013：使用监控仪表板
description: Lync Server 2013：使用监控仪表板。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a68fa1e55b7d0b8305c53802ddabaa904fa214
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556038"
---
# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="5dabc-103">在 Lync Server 2013 中使用监控仪表板</span><span class="sxs-lookup"><span data-stu-id="5dabc-103">Using the Monitoring Dashboard in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dabc-104">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="5dabc-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="5dabc-105">监控仪表板为管理员提供其 Microsoft Lync Server 2013 系统运行状况和系统使用情况的快速概述。</span><span class="sxs-lookup"><span data-stu-id="5dabc-105">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="5dabc-106">仪表板旨在显示关键系统指标的聚合视图，通过显示以下任一内容来实现此目标：</span><span class="sxs-lookup"><span data-stu-id="5dabc-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="5dabc-107">当天的汇总。</span><span class="sxs-lookup"><span data-stu-id="5dabc-107">Totals for the current day.</span></span> <span data-ttu-id="5dabc-108">请注意，当前日期显示的值表示从午夜开始记录的数据，直到当前时间 (基于报告服务器) 的本地时间。</span><span class="sxs-lookup"><span data-stu-id="5dabc-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="5dabc-109">这意味着您通常会查看部分日期的数据，而不是24小时的时间。</span><span class="sxs-lookup"><span data-stu-id="5dabc-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="5dabc-110">例如，如果服务器的本地时间为 8:00 AM，则会看到8小时的数据，因为午夜和当前时间为 8:00 AM 之间有八个小时。</span><span class="sxs-lookup"><span data-stu-id="5dabc-110">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="5dabc-111">一周的总计和过去六周的趋势总计。</span><span class="sxs-lookup"><span data-stu-id="5dabc-111">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="5dabc-112">月份总数和过去六个月的趋势总计 (仅供系统使用) 。</span><span class="sxs-lookup"><span data-stu-id="5dabc-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="5dabc-113">请注意，您可以使用 [CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet 返回用于访问 Lync Server 2013 监视报告的 URL：</span><span class="sxs-lookup"><span data-stu-id="5dabc-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="5dabc-114">默认情况下，监控仪表板显示当前周的以下指标的数据 (和前六周的趋势总计) ：</span><span class="sxs-lookup"><span data-stu-id="5dabc-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="5dabc-115">系统使用指标</span><span class="sxs-lookup"><span data-stu-id="5dabc-115">System Usage Metrics</span></span>

<span data-ttu-id="5dabc-116">**Registration**</span><span class="sxs-lookup"><span data-stu-id="5dabc-116">**Registration**</span></span>

  - <span data-ttu-id="5dabc-117">唯一用户登录</span><span class="sxs-lookup"><span data-stu-id="5dabc-117">Unique user logons</span></span>

<span data-ttu-id="5dabc-118">**对等**</span><span class="sxs-lookup"><span data-stu-id="5dabc-118">**Peer-to-peer**</span></span>

  - <span data-ttu-id="5dabc-119">会话总数</span><span class="sxs-lookup"><span data-stu-id="5dabc-119">Total sessions</span></span>

  - <span data-ttu-id="5dabc-120">IM 会话</span><span class="sxs-lookup"><span data-stu-id="5dabc-120">IM sessions</span></span>

  - <span data-ttu-id="5dabc-121">音频会话</span><span class="sxs-lookup"><span data-stu-id="5dabc-121">Audio sessions</span></span>

  - <span data-ttu-id="5dabc-122">视频会话</span><span class="sxs-lookup"><span data-stu-id="5dabc-122">Video sessions</span></span>

  - <span data-ttu-id="5dabc-123">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="5dabc-123">Application sharing</span></span>

  - <span data-ttu-id="5dabc-124">音频会话总分钟数</span><span class="sxs-lookup"><span data-stu-id="5dabc-124">Total audio session minutes</span></span>

  - <span data-ttu-id="5dabc-125">平均音频会话分钟数</span><span class="sxs-lookup"><span data-stu-id="5dabc-125">Avg. audio session minutes</span></span>

<span data-ttu-id="5dabc-126">**Conference**</span><span class="sxs-lookup"><span data-stu-id="5dabc-126">**Conference**</span></span>

  - <span data-ttu-id="5dabc-127">会议总数</span><span class="sxs-lookup"><span data-stu-id="5dabc-127">Total conferences</span></span>

  - <span data-ttu-id="5dabc-128">IM 会议</span><span class="sxs-lookup"><span data-stu-id="5dabc-128">IM conferences</span></span>

  - <span data-ttu-id="5dabc-129">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="5dabc-129">A/V conferences</span></span>

  - <span data-ttu-id="5dabc-130">应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="5dabc-130">Application sharing conferences</span></span>

  - <span data-ttu-id="5dabc-131">Web 会议</span><span class="sxs-lookup"><span data-stu-id="5dabc-131">Web conferences</span></span>

  - <span data-ttu-id="5dabc-132">组织者总数</span><span class="sxs-lookup"><span data-stu-id="5dabc-132">Total organizers</span></span>

  - <span data-ttu-id="5dabc-133">A/V 会议总分钟数</span><span class="sxs-lookup"><span data-stu-id="5dabc-133">Total A/V conference minutes</span></span>

  - <span data-ttu-id="5dabc-134">Avg.A/V 会议分钟数</span><span class="sxs-lookup"><span data-stu-id="5dabc-134">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="5dabc-135">PSTN 会议总数</span><span class="sxs-lookup"><span data-stu-id="5dabc-135">Total PSTN conferences</span></span>

  - <span data-ttu-id="5dabc-136">PSTN 参与者总数</span><span class="sxs-lookup"><span data-stu-id="5dabc-136">Total PSTN participants</span></span>

  - <span data-ttu-id="5dabc-137">PSTN 参与者总分钟数</span><span class="sxs-lookup"><span data-stu-id="5dabc-137">Total PSTN participant minutes</span></span>

<span data-ttu-id="5dabc-138">除了系统使用指标，以下指标还显示当前日期和前六天的总计 (如果选择 " **每周视图** ") 或在选择 " **每月视图**" 时为当前星期和过去六周。</span><span class="sxs-lookup"><span data-stu-id="5dabc-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="5dabc-139">Per-User 呼叫诊断</span><span class="sxs-lookup"><span data-stu-id="5dabc-139">Per-User Call Diagnostics</span></span>

<span data-ttu-id="5dabc-140">**具有呼叫失败的用户**</span><span class="sxs-lookup"><span data-stu-id="5dabc-140">**Users with call failures**</span></span>

  - <span data-ttu-id="5dabc-141">具有呼叫故障的用户总数</span><span class="sxs-lookup"><span data-stu-id="5dabc-141">Total users with call failures</span></span>

  - <span data-ttu-id="5dabc-142">具有呼叫故障的会议组织者</span><span class="sxs-lookup"><span data-stu-id="5dabc-142">Conference organizers with call failures</span></span>

<span data-ttu-id="5dabc-143">**具有较差的呼叫质量较差的用户**</span><span class="sxs-lookup"><span data-stu-id="5dabc-143">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="5dabc-144">使用质量较差的呼叫的用户总数</span><span class="sxs-lookup"><span data-stu-id="5dabc-144">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="5dabc-145">呼叫诊断</span><span class="sxs-lookup"><span data-stu-id="5dabc-145">Call Diagnostics</span></span>

<span data-ttu-id="5dabc-146">对等</span><span class="sxs-lookup"><span data-stu-id="5dabc-146">Peer-to-peer</span></span>

  - <span data-ttu-id="5dabc-147">失败总次数</span><span class="sxs-lookup"><span data-stu-id="5dabc-147">Total failures</span></span>

  - <span data-ttu-id="5dabc-148">整体故障率</span><span class="sxs-lookup"><span data-stu-id="5dabc-148">Overall failure rate</span></span>

  - <span data-ttu-id="5dabc-149">IM 故障率</span><span class="sxs-lookup"><span data-stu-id="5dabc-149">IM failure rate</span></span>

  - <span data-ttu-id="5dabc-150">音频故障率</span><span class="sxs-lookup"><span data-stu-id="5dabc-150">Audio failure rate</span></span>

  - <span data-ttu-id="5dabc-151">应用程序共享故障率</span><span class="sxs-lookup"><span data-stu-id="5dabc-151">Application sharing failure rate</span></span>

<span data-ttu-id="5dabc-152">Conference</span><span class="sxs-lookup"><span data-stu-id="5dabc-152">Conference</span></span>

  - <span data-ttu-id="5dabc-153">失败总次数</span><span class="sxs-lookup"><span data-stu-id="5dabc-153">Total failures</span></span>

  - <span data-ttu-id="5dabc-154">整体故障率</span><span class="sxs-lookup"><span data-stu-id="5dabc-154">Overall failure rate</span></span>

  - <span data-ttu-id="5dabc-155">IM 故障率</span><span class="sxs-lookup"><span data-stu-id="5dabc-155">IM failure rate</span></span>

  - <span data-ttu-id="5dabc-156">A/V 故障率</span><span class="sxs-lookup"><span data-stu-id="5dabc-156">A/V failure rate</span></span>

  - <span data-ttu-id="5dabc-157">应用程序共享故障率</span><span class="sxs-lookup"><span data-stu-id="5dabc-157">Application sharing failure rate</span></span>

<span data-ttu-id="5dabc-158">按失败会话排列的前5台服务器</span><span class="sxs-lookup"><span data-stu-id="5dabc-158">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="5dabc-159">媒体质量诊断</span><span class="sxs-lookup"><span data-stu-id="5dabc-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="5dabc-160">对等</span><span class="sxs-lookup"><span data-stu-id="5dabc-160">Peer-to-peer</span></span>

  - <span data-ttu-id="5dabc-161">质量较差的呼叫总数</span><span class="sxs-lookup"><span data-stu-id="5dabc-161">Total poor quality calls</span></span>

  - <span data-ttu-id="5dabc-162">质量较差的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="5dabc-162">Poor quality call percentage</span></span>

  - <span data-ttu-id="5dabc-163">质量较差的 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="5dabc-163">PSTN calls with poor quality</span></span>

<span data-ttu-id="5dabc-164">Conference</span><span class="sxs-lookup"><span data-stu-id="5dabc-164">Conference</span></span>

  - <span data-ttu-id="5dabc-165">质量较差的呼叫总数</span><span class="sxs-lookup"><span data-stu-id="5dabc-165">Total poor quality calls</span></span>

  - <span data-ttu-id="5dabc-166">质量较差的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="5dabc-166">Poor quality call percentage</span></span>

  - <span data-ttu-id="5dabc-167">质量较差的 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="5dabc-167">PSTN calls with poor quality</span></span>

<span data-ttu-id="5dabc-168">低质量呼叫百分比最差的服务器</span><span class="sxs-lookup"><span data-stu-id="5dabc-168">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="5dabc-169">使用监控仪表板</span><span class="sxs-lookup"><span data-stu-id="5dabc-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="5dabc-170">如前所述，默认情况下显示当前周的汇总，并且趋势值显示过去六周。</span><span class="sxs-lookup"><span data-stu-id="5dabc-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="5dabc-171">如果您想要查看当前月的总计 (以及过去六个月的趋势值) ，请单击仪表板右上角的 " **月视图** " 链接。</span><span class="sxs-lookup"><span data-stu-id="5dabc-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="5dabc-172">如果您决定查看每月总计，则链接文本将更改为 **每周视图**。</span><span class="sxs-lookup"><span data-stu-id="5dabc-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="5dabc-173">您可以通过单击该链接切换回每周视图。</span><span class="sxs-lookup"><span data-stu-id="5dabc-173">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5dabc-174">监控仪表板限制您查看当前周 (或月的总计，) 和过去六周 (或月) 的趋势值。</span><span class="sxs-lookup"><span data-stu-id="5dabc-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="5dabc-175">您不能更改这些日期和时间。</span><span class="sxs-lookup"><span data-stu-id="5dabc-175">You cannot change these dates and times.</span></span> <span data-ttu-id="5dabc-176">例如，不能使用仪表板查看每九个月前的时间段的报告总计。</span><span class="sxs-lookup"><span data-stu-id="5dabc-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="5dabc-177">" **本周**"、" **本月**" 或 " **今日** " 列中显示的值将链接到有关项目的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5dabc-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="5dabc-178">请记住，列名称和列中显示的值通常会有所不同，具体取决于所选的指标，取决于您是否选择了 "每周" 视图或 "按月" 视图。</span><span class="sxs-lookup"><span data-stu-id="5dabc-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="5dabc-179">例如，如果单击显示的 **唯一用户登录** 指标的总计，则将在指定时间段内看到 **用户注册报告** 。</span><span class="sxs-lookup"><span data-stu-id="5dabc-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="5dabc-180">您可以通过单击 " **仪表板**" 随时返回到 "监控" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="5dabc-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5dabc-181">您还可以通过单击仪表板右上角的 " <STRONG>报告</STRONG> " 链接来访问 "监视服务器报告" 主页。</span><span class="sxs-lookup"><span data-stu-id="5dabc-181">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="5dabc-182">" **趋势** " 列显示的简单折线图显示过去六周 (的总计，或者根据指标和时间间隔、过去六天或过去六个月) 显示总计。</span><span class="sxs-lookup"><span data-stu-id="5dabc-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="5dabc-183">这些简单的折线图显示每个时间段的一个未标记的数据点 (例如，过去六周中每一个未标记的数据点) 。</span><span class="sxs-lookup"><span data-stu-id="5dabc-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="5dabc-184">但是，您可以通过将鼠标指针悬停在关系图上来检索这些关系图的实际值。</span><span class="sxs-lookup"><span data-stu-id="5dabc-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="5dabc-185">在这种情况下，工具提示会向您显示图形中的最大值和最小值。</span><span class="sxs-lookup"><span data-stu-id="5dabc-185">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="5dabc-186">从监控仪表板导出数据</span><span class="sxs-lookup"><span data-stu-id="5dabc-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="5dabc-187">监控仪表板提供了多种方法来导出当前的仪表板视图。</span><span class="sxs-lookup"><span data-stu-id="5dabc-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="5dabc-188">在仪表板工具栏上，你将看到一个图标，看起来像一个附加了绿色箭头的软盘。</span><span class="sxs-lookup"><span data-stu-id="5dabc-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="5dabc-189">如果单击此图标，将显示一个下拉列表，提供以下数据导出格式：</span><span class="sxs-lookup"><span data-stu-id="5dabc-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="5dabc-190">具有报告数据的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="5dabc-190">XML file with report data</span></span>

  - <span data-ttu-id="5dabc-191">CSV（逗号分隔）</span><span class="sxs-lookup"><span data-stu-id="5dabc-191">CSV (comma delimited)</span></span>

  - <span data-ttu-id="5dabc-192">PDF</span><span class="sxs-lookup"><span data-stu-id="5dabc-192">PDF</span></span>

  - <span data-ttu-id="5dabc-193">MHTML（Web 存档）</span><span class="sxs-lookup"><span data-stu-id="5dabc-193">MHTML (web archive)</span></span>

  - <span data-ttu-id="5dabc-194">Excel</span><span class="sxs-lookup"><span data-stu-id="5dabc-194">Excel</span></span>

  - <span data-ttu-id="5dabc-195">TIFF 文件</span><span class="sxs-lookup"><span data-stu-id="5dabc-195">TIFF file</span></span>

  - <span data-ttu-id="5dabc-196">Word</span><span class="sxs-lookup"><span data-stu-id="5dabc-196">Word</span></span>

<span data-ttu-id="5dabc-197">若要导出当前的仪表板视图 (及其值) ，请单击所需的导出选项。</span><span class="sxs-lookup"><span data-stu-id="5dabc-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="5dabc-198">Lync Server 2013 生成指定格式的报告，然后为您提供打开该报告或保存该报告的选项。</span><span class="sxs-lookup"><span data-stu-id="5dabc-198">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="5dabc-199">请注意，默认情况下，Lync Server 将报告 **监控仪表板** 标题，并将其保存到 "下载" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5dabc-199">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="5dabc-200">若要为报告指定不同的名称或将其存储在不同的文件夹中，请单击 " **保存** " 按钮旁边的箭头，然后单击 " **另存为**"。</span><span class="sxs-lookup"><span data-stu-id="5dabc-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="5dabc-201">如果您使用名称 **监控仪表板** 并将报告保存在 "下载" 文件夹中，只需单击 " **保存** " 按钮即可。</span><span class="sxs-lookup"><span data-stu-id="5dabc-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="5dabc-202">当您尝试导出仪表板数据时，将显示一个 **安全警告** 对话框，并显示 "当前设置不允许下载此文件" 消息。</span><span class="sxs-lookup"><span data-stu-id="5dabc-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="5dabc-203">如果出现这种情况，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5dabc-203">If that occurs, do the following:</span></span>

  - <span data-ttu-id="5dabc-204">在 Internet Explorer 中，选择 " **Internet 选项**"。</span><span class="sxs-lookup"><span data-stu-id="5dabc-204">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="5dabc-205">在 " **Internet 选项** " 对话框中的 " **安全** " 选项卡上，单击 " **受信任的网站** "，然后单击 " **网站**"。</span><span class="sxs-lookup"><span data-stu-id="5dabc-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="5dabc-206">在 " **受信任的站点** " 对话框中，单击 " **添加** " 将运行 lync Server 2013 报告的 lync server 2013 添加到受信任的网站的集合。</span><span class="sxs-lookup"><span data-stu-id="5dabc-206">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="5dabc-207">单击 " **关闭** "，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5dabc-207">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="5dabc-208">然后，您需要刷新监控仪表板，更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="5dabc-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="5dabc-209">若要执行此操作，请按 F5 或单击仪表板工具栏中的 " **刷新** " 图标。</span><span class="sxs-lookup"><span data-stu-id="5dabc-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="5dabc-210"> (**刷新** 图标是一个圆圈，其中包含一对绿色箭头。 ) </span><span class="sxs-lookup"><span data-stu-id="5dabc-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="5dabc-211">您还可以创建包含实时数据源的 Excel 电子表格，其中包括指向最新监控仪表板数据的链接。</span><span class="sxs-lookup"><span data-stu-id="5dabc-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="5dabc-212">若要创建实时数据馈送文件，请单击工具栏中的 " **将导出为数据馈送** 的橙色" 图标。</span><span class="sxs-lookup"><span data-stu-id="5dabc-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="5dabc-213">如果您希望打印当前仪表板，请单击工具栏中的打印机图标。</span><span class="sxs-lookup"><span data-stu-id="5dabc-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

