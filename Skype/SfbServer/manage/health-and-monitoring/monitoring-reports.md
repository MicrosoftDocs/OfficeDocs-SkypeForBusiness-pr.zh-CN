---
title: 在 Skype for Business Server 中使用监控报告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 摘要：了解 Skype for Business Server 中的监控报告。
ms.openlocfilehash: 32e16d02f458ca36fb18b52790966c68a354503e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827762"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a><span data-ttu-id="3020d-103">在 Skype for Business Server 中使用监控报告</span><span class="sxs-lookup"><span data-stu-id="3020d-103">Using Monitoring Reports in Skype for Business Server</span></span> 
 
<span data-ttu-id="3020d-104">**摘要：** 了解 Skype for Business Server 中的监控报告。</span><span class="sxs-lookup"><span data-stu-id="3020d-104">**Summary:** Learn about Monitoring Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="3020d-105">Skype for Business Server 包括由 Microsoft SQL Server Reporting Service 发布的一组标准报告。</span><span class="sxs-lookup"><span data-stu-id="3020d-105">Skype for Business Server includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="3020d-106">这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="3020d-106">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>
  
<span data-ttu-id="3020d-107">若要使用这些报告，必须在运行报告实例的计算机上安装监控SQL Server。</span><span class="sxs-lookup"><span data-stu-id="3020d-107">To use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="3020d-108">本部分内容</span><span class="sxs-lookup"><span data-stu-id="3020d-108">In This Section</span></span>

- <span data-ttu-id="3020d-109">[在 Skype for Business Server 中使用监控仪表板](monitoring-dashboard.md) 为管理员提供其系统运行状况和系统使用情况的快速概述。</span><span class="sxs-lookup"><span data-stu-id="3020d-109">[Using the Monitoring Dashboard in Skype for Business Server](monitoring-dashboard.md) Provides administrators with a quick overview of their system health and system usage.</span></span>
    
- <span data-ttu-id="3020d-110">[Skype for Business Server 中的系统使用情况报告](system-usage-reports.md) 基于 Skype for Business Server 收集的 CDR 数据提供系统使用情况信息。</span><span class="sxs-lookup"><span data-stu-id="3020d-110">[System usage reports in Skype for Business Server](system-usage-reports.md) Provides system usage information based on CDR data collected by Skype for Business Server.</span></span>
    
- <span data-ttu-id="3020d-111">[Skype for Business Server (每个用户) 诊断报告](call-diagnostic-reports-per-user.md) 提供有关失败的对等会话和会议会话的每个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="3020d-111">[Call Diagnostic Reports (per user) in Skype for Business Server](call-diagnostic-reports-per-user.md) Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="3020d-112">[Skype for Business Server 中的呼叫诊断报告](call-diagnostic-reports.md) 提供失败的对等会话和会议会话的摘要信息和诊断数据。</span><span class="sxs-lookup"><span data-stu-id="3020d-112">[Call Diagnostic Reports in Skype for Business Server](call-diagnostic-reports.md) Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="3020d-113">[Skype for Business Server 中的媒体质量诊断报告](media-quality-diagnostic-reports.md) 提供有关呼叫质量的信息，以及失败的呼叫的诊断和故障排除信息。</span><span class="sxs-lookup"><span data-stu-id="3020d-113">[Media Quality Diagnostic Reports in Skype for Business Server](media-quality-diagnostic-reports.md) Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>
    
## <a name="locating-records"></a><span data-ttu-id="3020d-114">查找记录</span><span class="sxs-lookup"><span data-stu-id="3020d-114">Locating Records</span></span>

<span data-ttu-id="3020d-115">监控报告在任一时刻仅在屏幕上显示有限数量的记录。</span><span class="sxs-lookup"><span data-stu-id="3020d-115">Monitoring Reports only show a limited number of records on the screen at any one time.</span></span> <span data-ttu-id="3020d-116">屏幕上显示的实际记录数因报告而异。</span><span class="sxs-lookup"><span data-stu-id="3020d-116">The actual number of records displayed on a screen varies depending on the report.</span></span> <span data-ttu-id="3020d-117">若要查看屏幕上当前未显示的记录，可以使用在每个报表的工具栏 (上找到的标准向前和向后控件) 该控件使您能够分页查看数据。</span><span class="sxs-lookup"><span data-stu-id="3020d-117">To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report's toolbar) that enable you to page through the data.</span></span> <span data-ttu-id="3020d-118">您还可以快速跳转到数据集的第一页或最后一页。</span><span class="sxs-lookup"><span data-stu-id="3020d-118">You can also quickly jump to the first page or the last page of the dataset.</span></span>
  
<span data-ttu-id="3020d-119">除了使用前进和后退控件，您还可以通过在“当前页”框中键入页码，然后按 Enter 来跳转到数据集中的任一页。</span><span class="sxs-lookup"><span data-stu-id="3020d-119">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>
  
<span data-ttu-id="3020d-p103">除了提供逐页查看数据的功能，每个报告还包括查找记录的有限功能。若要根据给定值查找记录，请在“查找”框中键入该值，然后单击“查找”。报告将开始搜索数据，然后在找到您在“查找”框中输入的值的第一个实例时停止。若要查找符合搜索条件的下一条记录，请单击“下一个”。</span><span class="sxs-lookup"><span data-stu-id="3020d-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>
  
<span data-ttu-id="3020d-p104">如前所述，监控报告仅提供最基本的搜索功能。例如，您无法指定应在哪个字段中查找值。搜索机制自动在每条记录中的每个字段中搜索匹配值。您无法在搜索中使用通配符，所有搜索都将查找部分值。这意味着，如果您搜索 111，则搜索不仅将返回值 111，还返回值 11100、811、3112、611A5B 以及在字段中的任何位置包含值 111 的任何其他字段。</span><span class="sxs-lookup"><span data-stu-id="3020d-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>
  
<span data-ttu-id="3020d-129">每个报告配置为显示一组默认记录。</span><span class="sxs-lookup"><span data-stu-id="3020d-129">Each report is configured to show a default set of records.</span></span> <span data-ttu-id="3020d-130">例如，默认情况下，用户注册报告显示上周的用户注册活动。</span><span class="sxs-lookup"><span data-stu-id="3020d-130">For example, by default the User Registration Report shows user registration activities for the past week.</span></span> <span data-ttu-id="3020d-131">有些情况下，这可能生成不返回任何记录的报告。</span><span class="sxs-lookup"><span data-stu-id="3020d-131">In some cases, this might result in a report that returns no records.</span></span> <span data-ttu-id="3020d-132">在这种情况下，意味着上周没有发生任何用户注册。</span><span class="sxs-lookup"><span data-stu-id="3020d-132">In this case, it means that no user registrations have taken place in the past week.</span></span> <span data-ttu-id="3020d-133">如果您看到消息"没有与报告筛选器匹配的结果"，请尝试更改筛选器值 (例如，将时间段更改为过去一个月而不是过去一周) 并重新运行查询。</span><span class="sxs-lookup"><span data-stu-id="3020d-133">If you see the message "No results match the report filters," try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query.</span></span> <span data-ttu-id="3020d-134">有关详细信息，请参阅本主题后面的“筛选数据”一节。</span><span class="sxs-lookup"><span data-stu-id="3020d-134">For details, see the "Filtering Data" section later in this topic.</span></span>
  
## <a name="filtering-data"></a><span data-ttu-id="3020d-135">筛选数据</span><span class="sxs-lookup"><span data-stu-id="3020d-135">Filtering Data</span></span>

<span data-ttu-id="3020d-p106">有时您可能希望只查看一部分记录。例如，只查看点对点会话，而非点对点会话和会议会话。同样，有时您需要减少返回的记录数。默认情况下，报告只能显示数据集中的前 1,000 条记录。为解决这些问题，大多数报告都包含大量筛选选项。例如，如果您希望仅查看 2011 年 1 月 1 日至 2011 年 1 月 15 日这个时间段的记录，则您可以在“从”框中输入 2011 年 1 月 1 日，在“到”框中输入 2011 年 1 月 15 日。然后，如果您单击“查看报告”，返回的数据将仅限于在 2011 年 1 月 1 日和 2011 年 1 月 15 日之间发生的活动。</span><span class="sxs-lookup"><span data-stu-id="3020d-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>
  
<span data-ttu-id="3020d-p107">可供您使用的筛选器将因您要查看的报告而异。有关特定报告的详细信息，请参阅该报告的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="3020d-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>
  
## <a name="exporting-data"></a><span data-ttu-id="3020d-145">导出数据</span><span class="sxs-lookup"><span data-stu-id="3020d-145">Exporting Data</span></span>

<span data-ttu-id="3020d-p108">监控报告至少提供两种导出报告中包括的数据的不同方法。可以使用每个报告顶部显示的工具栏中的“导出”选项。若要使用此选项，请从“选择格式”下拉列表中选择所需的导出格式。可使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="3020d-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>
  
- <span data-ttu-id="3020d-150">具有报告数据的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="3020d-150">XML file with report data</span></span>
    
- <span data-ttu-id="3020d-151">CSV（逗号分隔）</span><span class="sxs-lookup"><span data-stu-id="3020d-151">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="3020d-152">Acrobat (PDF) 文件</span><span class="sxs-lookup"><span data-stu-id="3020d-152">Acrobat (PDF) file</span></span>
    
- <span data-ttu-id="3020d-153">MHTML（Web 存档）</span><span class="sxs-lookup"><span data-stu-id="3020d-153">MHTML (web archive)</span></span>
    
- <span data-ttu-id="3020d-154">Excel</span><span class="sxs-lookup"><span data-stu-id="3020d-154">Excel</span></span>
    
- <span data-ttu-id="3020d-155">TIFF 文件</span><span class="sxs-lookup"><span data-stu-id="3020d-155">TIFF file</span></span>
    
- <span data-ttu-id="3020d-156">Word</span><span class="sxs-lookup"><span data-stu-id="3020d-156">Word</span></span>
    
<span data-ttu-id="3020d-p109">选择格式后，单击“导出”。出现“文件下载”对话框时，单击“保存”。在“另存为”对话框中，选择目标文件夹，输入文件名，然后单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="3020d-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>
  
<span data-ttu-id="3020d-p110">如果安装了 Microsoft OneNote，还可以将报告数据复制到 OneNote 中。为此，请右键单击工具栏上的“查看报告”按钮。在“在 OneNote 中选择位置”对话框中，选择要将数据复制到的 OneNote 中的节，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="3020d-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>
  

