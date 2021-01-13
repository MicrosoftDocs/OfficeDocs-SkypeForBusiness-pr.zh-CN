---
title: Skype for Business Server 中的 IP 电话清单报告
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
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: 摘要：了解 Skype for Business Server 中的 IP 电话清单报告。
ms.openlocfilehash: 513b4ac54cf337a13cd95523fa3de750ce5f8c17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823452"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a><span data-ttu-id="3480b-103">Skype for Business Server 中的 IP 电话清单报告</span><span class="sxs-lookup"><span data-stu-id="3480b-103">IP Phone Inventory Report in Skype for Business Server</span></span>
 
<span data-ttu-id="3480b-104">**摘要：** 了解 Skype for Business Server 中的 IP 电话清单报告。</span><span class="sxs-lookup"><span data-stu-id="3480b-104">**Summary:** Learn about the IP Phone Inventory Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="3480b-p101">IP 电话清单报告会报告有关您的组织中目前所使用的 IP 电话的信息。IP 清单报告提供了在指定的报告期间实际上所使用的详细 IP 电话列表。除此之外，管理员还可以通过此报告了解是否存在应进行替换但仍在使用中的任何旧的、过时的电话；该报告还可以就组织中存在很少使用的昂贵电话这一实际情况，向管理员发出警报。当应该购买新电话或重新分配现有的电话时，该类型的信息非常重要。（例如，可能要求很少使用其昂贵电话的用户与较为频繁使用其电话的用户交换电话。）</span><span class="sxs-lookup"><span data-stu-id="3480b-p101">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization. The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period. Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used. That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones. (For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>
  
<span data-ttu-id="3480b-110">值得注意的是，此报告在用作真正的清单报告时存在几点限制。</span><span class="sxs-lookup"><span data-stu-id="3480b-110">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="3480b-111">首先，IP 电话报告仅列出指定时段内登录到 Skype for Business Server 的所有电话（按其上次登录时间排序）。</span><span class="sxs-lookup"><span data-stu-id="3480b-111">For one thing, the IP Phone Report simply lists all the phones that logged on to Skype for Business Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="3480b-112">如果某个电话在指定的时间段内未登录，那么就不会在清单报告中列出。</span><span class="sxs-lookup"><span data-stu-id="3480b-112">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="3480b-113">这包括在该时间段开始前已登录并且在指定的时间间隔内仍保持登录的电话。</span><span class="sxs-lookup"><span data-stu-id="3480b-113">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="3480b-114">例如，假设你想要查看 2015 年 7 月的所有电话清单。</span><span class="sxs-lookup"><span data-stu-id="3480b-114">For example, suppose you wanted to look at all the phone inventory for July, 2015.</span></span> <span data-ttu-id="3480b-115">还假定 2015 年 6 月 30 日，多个电话登录到 Skype for Business Server，截至 7 月 1 日仍登录。</span><span class="sxs-lookup"><span data-stu-id="3480b-115">Suppose, as well, that several phones logged on to Skype for Business Server on June 30, 2015, and were still logged on as of July 1st.</span></span> <span data-ttu-id="3480b-116">这些电话将不会在 7 月 1 日的清单报告上出现。</span><span class="sxs-lookup"><span data-stu-id="3480b-116">Those phones will not show up on the inventory report for July 1st.</span></span>
  
<span data-ttu-id="3480b-117">还必须注意的是，清单报告可能包括您的组织不再使用的电话。</span><span class="sxs-lookup"><span data-stu-id="3480b-117">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="3480b-118">例如，假设许多 Fabrikam 电话在 2015 年 7 月 1 日登录到系统;5 天后，贵组织清除了所有这些 Fabrikam 电话，并替换为较新的 Contoso 模型。</span><span class="sxs-lookup"><span data-stu-id="3480b-118">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2015; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="3480b-119">Fabrikam 电话仍会显示在“清单”报告中，原因很简单，就是它们在 7 月份已登录到系统。</span><span class="sxs-lookup"><span data-stu-id="3480b-119">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>
  
<span data-ttu-id="3480b-p104">此外，IP 电话清单报告不会报告不同类型的电话总数摘要。例如，假设您拥有 105 个 Polycom CX600 电话。该报告不会告知您拥有 105 个此类电话；相反，您只会看到 105 个单独的 Polycom Cx600 条目。知道有 105 个 Polycom Cx600 条目的唯一方法是手动计算其中每一个条目。</span><span class="sxs-lookup"><span data-stu-id="3480b-p104">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones. For example, suppose you have 105 Polycom CX600 phones. The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600. The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>
  
> [!TIP]
> <span data-ttu-id="3480b-124">或者，导出数据，然后使用 Microsoft Excel 或 Windows PowerShell 为您进行计数。</span><span class="sxs-lookup"><span data-stu-id="3480b-124">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span> 
  
## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="3480b-125">访问 IP 电话清单报告</span><span class="sxs-lookup"><span data-stu-id="3480b-125">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="3480b-p105">可以从“监控报告”主页访问 IP 电话清单报告。如果您单击“用户 URI”指标，即可访问该用户的“用户活动报告”。针对对等呼叫单击“最后一次活动”指标，会将您带到“对等会话详细信息报告”；针对会议单击相同的指标，会将您带到“会议详细信息报告”。</span><span class="sxs-lookup"><span data-stu-id="3480b-p105">The IP Phone Inventory Report is accessed from the Monitoring Reports home page. If you click the User URI metric you can access the User Activity Report for that user. Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="3480b-129">充分利用 IP 电话清单报告</span><span class="sxs-lookup"><span data-stu-id="3480b-129">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="3480b-p106">如果您只对某特定类型的电话的使用信息（例如，“用户多久使用一次 Polycom CX600 电话？”）感兴趣，则可以通过筛选该特定类型的电话，直接从 IP 电话清单报告中获取该信息。但是，如果您想要了解所有电话的摘要信息（多少人正在使用 Polycom CX600、多少人正在使用 LG-Nortel IP8540 等），则需要导出数据，然后使用另一个应用程序（如 Windows PowerShell）执行该类型的分析。例如，假设将数据导出到逗号分隔值文件 (C:\Data\IP_Phone_Inventory_Report.csv)。在这种情况下，您可以使用以下这两个命令提供所有电话的摘要数据：</span><span class="sxs-lookup"><span data-stu-id="3480b-p106">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone. However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis. For example, suppose you export the data to a comma-separated values file (C:\Data\IP_Phone_Inventory_Report.csv). In that case, you could use these two commands to provide summary data for all your phones:</span></span>
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="3480b-134">这将返回与以下类似的数据：</span><span class="sxs-lookup"><span data-stu-id="3480b-134">That will return data similar to this:</span></span>
  
<pre>
Count    Name
-----    ----
  267    POLYCOM, CX700
  267    POLYCOM, CX600
  166    POLYCOM, C
   68    Microsoft, CPE
   64    LG-Nortel, IP8540
   59    Aastra, 6725ip
   37    LG-Nortel, IP
   22    POLYCOM, CX3000
   11    Microsoft, CPE_A
    9    POLYCOM, CX500
    7    Aastra, 6721ip
</pre>

<span data-ttu-id="3480b-135">类似地，这两个命令会告诉您哪些电话已登录到系统，但实际上从未用来发出呼叫（“最后一次活动”指标的值为空白，表示没有任何最后一次活动）：</span><span class="sxs-lookup"><span data-stu-id="3480b-135">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones | Where-Object {$_."Last activity" -eq ""}
```

<span data-ttu-id="3480b-136">针对尚未使用的每一个电话，将返回与以下类似的数据：</span><span class="sxs-lookup"><span data-stu-id="3480b-136">That returns data similar to this for each phone that has not been used:</span></span>
  
<pre>
Manufacturer     : POLYCOM
Hardware version : CX600
MAC address      : 00-04-F2-00-01-76
User URI         : 422
User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
Last logon time  : 8/30/2010 4:44:48 PM
Last logoff time : 8/30/2010 5:59:07 PM
Last activity    :
</pre>

<span data-ttu-id="3480b-137">使用 IP 电话清单报告的另一种有趣的方式如下：如果您具有 IP 电话的 MAC 地址，则只需在 MAC 地址文本框中输入该地址，即可判断最后一次使用该电话的用户。</span><span class="sxs-lookup"><span data-stu-id="3480b-137">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="3480b-138">然后，IP 电话清单报告将返回使用该电话最后一次登录的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="3480b-138">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="3480b-139">或者，您可以在“用户 URI”前缀框中输入用户 SIP 地址，以查明该用户已使用的所有电话。</span><span class="sxs-lookup"><span data-stu-id="3480b-139">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>
  
## <a name="filters"></a><span data-ttu-id="3480b-140">筛选器</span><span class="sxs-lookup"><span data-stu-id="3480b-140">Filters</span></span>

<span data-ttu-id="3480b-p108">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，通过 IP 电话清单，您可以只查看特定公司制造的电话，甚至只查看这些电话的某个特定版本。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对注册进行分组。</span><span class="sxs-lookup"><span data-stu-id="3480b-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones. You can also choose how data should be grouped. In this case, registrations are grouped by hour, day, week, or month.</span></span>
  
<span data-ttu-id="3480b-145">下表列出了可用于 IP 电话清单报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3480b-145">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>
  
<span data-ttu-id="3480b-146">**IP 电话清单报告筛选器**</span><span class="sxs-lookup"><span data-stu-id="3480b-146">**IP Phone Inventory Report Filters**</span></span>

|<span data-ttu-id="3480b-147">**名称**</span><span class="sxs-lookup"><span data-stu-id="3480b-147">**Name**</span></span>|<span data-ttu-id="3480b-148">**说明**</span><span class="sxs-lookup"><span data-stu-id="3480b-148">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3480b-149">**From**</span><span class="sxs-lookup"><span data-stu-id="3480b-149">**From**</span></span> <br/> |<span data-ttu-id="3480b-p109">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3480b-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="3480b-152">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="3480b-152">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="3480b-p110">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="3480b-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="3480b-155">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="3480b-155">7/7/2015</span></span>  <br/> <span data-ttu-id="3480b-156">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="3480b-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="3480b-157">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="3480b-157">7/3/2015</span></span>  <br/> <span data-ttu-id="3480b-158">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="3480b-158">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="3480b-159">"自"</span><span class="sxs-lookup"><span data-stu-id="3480b-159">**To**</span></span> <br/> |<span data-ttu-id="3480b-p111">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3480b-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="3480b-162">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="3480b-162">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="3480b-p112">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="3480b-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="3480b-165">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="3480b-165">7/7/2015</span></span>  <br/> <span data-ttu-id="3480b-166">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="3480b-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="3480b-167">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="3480b-167">7/3/2015</span></span>  <br/> <span data-ttu-id="3480b-168">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="3480b-168">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="3480b-169">**制造商**</span><span class="sxs-lookup"><span data-stu-id="3480b-169">**Manufacturer**</span></span> <br/> |<span data-ttu-id="3480b-p113">制造 IP 电话的公司的名称。此筛选器的值将根据数据库中当前存有的 IP 电话自动填充。</span><span class="sxs-lookup"><span data-stu-id="3480b-p113">Name of the company that manufactured the IP phone. The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span>  <br/> |
|<span data-ttu-id="3480b-172">**硬件版本**</span><span class="sxs-lookup"><span data-stu-id="3480b-172">**Hardware version**</span></span> <br/> |<span data-ttu-id="3480b-173">IP 电话的版本号；使用您可以专门识别特定电话类型的制造商和硬件版本筛选器。</span><span class="sxs-lookup"><span data-stu-id="3480b-173">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="3480b-174">此筛选器的值将根据数据库中当前存有的 IP 电话自动填充。</span><span class="sxs-lookup"><span data-stu-id="3480b-174">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span>  <br/> |
|<span data-ttu-id="3480b-175">**用户代理**</span><span class="sxs-lookup"><span data-stu-id="3480b-175">**User agent**</span></span> <br/> |<span data-ttu-id="3480b-p115">IP 电话使用的软件的标识符。此筛选器的值将根据数据库中当前存有的 IP 电话自动填充。</span><span class="sxs-lookup"><span data-stu-id="3480b-p115">Identifier for the software used by the IP phone. The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span>  <br/> |
|<span data-ttu-id="3480b-178">**MAC 地址**</span><span class="sxs-lookup"><span data-stu-id="3480b-178">**MAC address**</span></span> <br/> |<span data-ttu-id="3480b-p116">IP 电话的网络接口的唯一标识符。媒体访问控制 (MAC) 地址通常在电话制造时分配，并硬接线到设备硬件。</span><span class="sxs-lookup"><span data-stu-id="3480b-p116">Unique identifier for the network interface on the IP phone. The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span>  <br/> <span data-ttu-id="3480b-p117">要搜索与特定 MAC 地址有关的记录，只需输入该地址。例如：</span><span class="sxs-lookup"><span data-stu-id="3480b-p117">To search for records pertaining to a specific MAC address simply enter that address. For example:</span></span>  <br/> <span data-ttu-id="3480b-183">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="3480b-183">00-08-5D-16-16-48</span></span>  <br/> <span data-ttu-id="3480b-p118">您必须输入完整地址。只输入一部分地址（例如 00-08-5D）不会返回任何数据。</span><span class="sxs-lookup"><span data-stu-id="3480b-p118">You must enter the complete address. A partial address (for example 00-08-5D) does not return any data.</span></span>  <br/> |
|<span data-ttu-id="3480b-186">**此天数前的最后一次活动**</span><span class="sxs-lookup"><span data-stu-id="3480b-186">**Last activity before days**</span></span> <br/> | <span data-ttu-id="3480b-187">选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="3480b-187">Select one of the following values:</span></span> <br/>  <span data-ttu-id="3480b-188">[全部]</span><span class="sxs-lookup"><span data-stu-id="3480b-188">[All]</span></span> <br/>  <span data-ttu-id="3480b-189">10 </span><span class="sxs-lookup"><span data-stu-id="3480b-189">10</span></span> <br/>  <span data-ttu-id="3480b-190">20</span><span class="sxs-lookup"><span data-stu-id="3480b-190">20</span></span> <br/>  <span data-ttu-id="3480b-191">30</span><span class="sxs-lookup"><span data-stu-id="3480b-191">30</span></span> <br/> |
|<span data-ttu-id="3480b-192">**此天数前的最后注销时间**</span><span class="sxs-lookup"><span data-stu-id="3480b-192">**Last logoff time before days**</span></span> <br/> | <span data-ttu-id="3480b-193">选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="3480b-193">Select one of the following values:</span></span> <br/>  <span data-ttu-id="3480b-194">[全部]</span><span class="sxs-lookup"><span data-stu-id="3480b-194">[All]</span></span> <br/>  <span data-ttu-id="3480b-195">10 </span><span class="sxs-lookup"><span data-stu-id="3480b-195">10</span></span> <br/>  <span data-ttu-id="3480b-196">20</span><span class="sxs-lookup"><span data-stu-id="3480b-196">20</span></span> <br/>  <span data-ttu-id="3480b-197">30</span><span class="sxs-lookup"><span data-stu-id="3480b-197">30</span></span> <br/> |
|<span data-ttu-id="3480b-198">**用户 URI 前缀**</span><span class="sxs-lookup"><span data-stu-id="3480b-198">**User URI prefix**</span></span> <br/> |<span data-ttu-id="3480b-199">使用 IP 电话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="3480b-199">SIP address of the user who used the IP phone.</span></span>  <br/> |
   
## <a name="metrics"></a><span data-ttu-id="3480b-200">指标</span><span class="sxs-lookup"><span data-stu-id="3480b-200">Metrics</span></span>

<span data-ttu-id="3480b-201">下表列出了 IP 电话清单报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="3480b-201">The following table lists the information provided in the IP Phone Inventory Report.</span></span>
  
<span data-ttu-id="3480b-202">**IP 电话清单报告指标**</span><span class="sxs-lookup"><span data-stu-id="3480b-202">**IP Phone Inventory Report Metrics**</span></span>

|<span data-ttu-id="3480b-203">**名称**</span><span class="sxs-lookup"><span data-stu-id="3480b-203">**Name**</span></span>|<span data-ttu-id="3480b-204">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="3480b-204">**Can you sort on this item?**</span></span>|<span data-ttu-id="3480b-205">**说明**</span><span class="sxs-lookup"><span data-stu-id="3480b-205">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3480b-206">**制造商**</span><span class="sxs-lookup"><span data-stu-id="3480b-206">**Manufacturer**</span></span> <br/> |<span data-ttu-id="3480b-207">是</span><span class="sxs-lookup"><span data-stu-id="3480b-207">Yes</span></span>  <br/> |<span data-ttu-id="3480b-208">制造 IP 电话的公司的名称。</span><span class="sxs-lookup"><span data-stu-id="3480b-208">Name of the company that manufactured the IP phone.</span></span>  <br/> |
|<span data-ttu-id="3480b-209">**硬件版本**</span><span class="sxs-lookup"><span data-stu-id="3480b-209">**Hardware version**</span></span> <br/> |<span data-ttu-id="3480b-210">是</span><span class="sxs-lookup"><span data-stu-id="3480b-210">Yes</span></span>  <br/> |<span data-ttu-id="3480b-211">IP 电话的版本号。</span><span class="sxs-lookup"><span data-stu-id="3480b-211">Version number of the IP phone.</span></span>  <br/> |
|<span data-ttu-id="3480b-212">**MAC 地址**</span><span class="sxs-lookup"><span data-stu-id="3480b-212">**MAC address**</span></span> <br/> |<span data-ttu-id="3480b-213">是</span><span class="sxs-lookup"><span data-stu-id="3480b-213">Yes</span></span>  <br/> |<span data-ttu-id="3480b-p119">IP 电话的网络接口的唯一标识符。MAC 地址通常在电话制造时分配，并硬接线到设备硬件。</span><span class="sxs-lookup"><span data-stu-id="3480b-p119">Unique identifier for the network interface on the IP phone. The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span>  <br/> |
|<span data-ttu-id="3480b-216">**用户 URI**</span><span class="sxs-lookup"><span data-stu-id="3480b-216">**User URI**</span></span> <br/> |<span data-ttu-id="3480b-217">是</span><span class="sxs-lookup"><span data-stu-id="3480b-217">Yes</span></span>  <br/> |<span data-ttu-id="3480b-218">使用 IP 电话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="3480b-218">SIP address of the user who used the IP phone.</span></span>  <br/> |
|<span data-ttu-id="3480b-219">**用户代理**</span><span class="sxs-lookup"><span data-stu-id="3480b-219">**User agent**</span></span> <br/> |<span data-ttu-id="3480b-220">是</span><span class="sxs-lookup"><span data-stu-id="3480b-220">Yes</span></span>  <br/> |<span data-ttu-id="3480b-221">IP 电话使用的软件的标识符。</span><span class="sxs-lookup"><span data-stu-id="3480b-221">Identifier for the software used by the IP phone.</span></span>  <br/> |
|<span data-ttu-id="3480b-222">**上次登录时间**</span><span class="sxs-lookup"><span data-stu-id="3480b-222">**Last logon time**</span></span> <br/> |<span data-ttu-id="3480b-223">是</span><span class="sxs-lookup"><span data-stu-id="3480b-223">Yes</span></span>  <br/> |<span data-ttu-id="3480b-224">IP 电话上次登录到 Skype for Business Server 的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3480b-224">Date and time that the IP phone last logged on to Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="3480b-225">**上次注销时间**</span><span class="sxs-lookup"><span data-stu-id="3480b-225">**Last logoff time**</span></span> <br/> |<span data-ttu-id="3480b-226">是</span><span class="sxs-lookup"><span data-stu-id="3480b-226">Yes</span></span>  <br/> |<span data-ttu-id="3480b-227">IP 电话上次从 Skype for Business Server 注销的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3480b-227">Date and time that the IP phone last logged off from Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="3480b-228">**最后一次活动**</span><span class="sxs-lookup"><span data-stu-id="3480b-228">**Last activity**</span></span> <br/> |<span data-ttu-id="3480b-229">是</span><span class="sxs-lookup"><span data-stu-id="3480b-229">Yes</span></span>  <br/> |<span data-ttu-id="3480b-230">上一次使用 IP 电话的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3480b-230">Date and time that the IP phone was last used.</span></span>  <br/> |
   

