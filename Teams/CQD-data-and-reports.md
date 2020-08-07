---
title: '通话质量仪表板中的数据和报表 (CQD) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 了解 Microsoft 通话质量仪表板 (CQD) 中提供的数据和报告。
ms.openlocfilehash: ec9714e0eae187bc82edf01809b50d8512d04e01
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583089"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a><span data-ttu-id="96d84-103">通话质量仪表板中的数据和报表 (CQD) </span><span class="sxs-lookup"><span data-stu-id="96d84-103">Data and reports in Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="96d84-104">Microsoft 通话质量仪表板 (CQD) 使用近实时 (NRT) 数据馈送。</span><span class="sxs-lookup"><span data-stu-id="96d84-104">Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed.</span></span> <span data-ttu-id="96d84-105">通话记录在通话结束后的30分钟内 CQD 可用。</span><span class="sxs-lookup"><span data-stu-id="96d84-105">Call records are available in CQD within 30 minutes of the end of a call.</span></span> <span data-ttu-id="96d84-106">从 NRT 管道中调用记录仅在从数据集内删除几个月后才可用。</span><span class="sxs-lookup"><span data-stu-id="96d84-106">Call records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> 


## <a name="many-ways-to-access-cqd-data"></a><span data-ttu-id="96d84-107">访问 CQD 数据的多种方法</span><span class="sxs-lookup"><span data-stu-id="96d84-107">Many ways to access CQD data</span></span>

<span data-ttu-id="96d84-108">你可以通过多种不同的途径访问 CQD 数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-108">You can access CQD data by several different avenues.</span></span> <span data-ttu-id="96d84-109">选择最能满足你的需求的一个：</span><span class="sxs-lookup"><span data-stu-id="96d84-109">Pick the one that best meets your needs:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="96d84-110">团队管理中心[ (https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="96d84-110">Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)</span></span>    | <span data-ttu-id="96d84-111">CQD 数据包含在团队管理中心的 "**用户**" 页面上，以易于阅读的格式显示所需的最常见数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-111">CQD data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format.</span></span> <span data-ttu-id="96d84-112">您不能自定义在 "**用户**" 下找到的 CQD 数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-112">You can't customize CQD data that you find under **Users**.</span></span>  |
|<span data-ttu-id="96d84-113">CQD 门户[ (https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="96d84-113">CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)</span></span>     | <span data-ttu-id="96d84-114">具有钻取筛选功能的强大摘要和详细报表，可满足大多数需求。</span><span class="sxs-lookup"><span data-stu-id="96d84-114">Robust summary and detailed reports that meet most needs, with drill-through filtering.</span></span> <span data-ttu-id="96d84-115">你还可以在 CQD 门户中自定义报表。</span><span class="sxs-lookup"><span data-stu-id="96d84-115">You can also customize reports in the CQD portal.</span></span> <br><br><span data-ttu-id="96d84-116">获取两个[CQD 报表模板](#import-the-cqd-report-templates)以帮助你分析 CQD 门户中的数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-116">Get two [CQD report templates](#import-the-cqd-report-templates) to help you analyze data in the CQD portal.</span></span>       |
|<span data-ttu-id="96d84-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="96d84-117">Power BI</span></span>     | <span data-ttu-id="96d84-118">使用直接查询在 Power BI 中使用[可自定义的 POWER bi 模板](CQD-Power-BI-query-templates.md)查看你的 CQD 数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-118">Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](CQD-Power-BI-query-templates.md).</span></span> <span data-ttu-id="96d84-119">[下载 CQD 的 POWER BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="96d84-119">[Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span><br><br><span data-ttu-id="96d84-120">你还可以[使用 REST API 通过 POWER BI 访问 CQD 数据](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api)。</span><span class="sxs-lookup"><span data-stu-id="96d84-120">You can also [use the REST API to access CQD data](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) through Power BI.</span></span> <span data-ttu-id="96d84-121">如果想要下载 CQD 数据以便可以脱机处理它，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="96d84-121">Use this method if you want to download your CQD data so you can work on it offline.</span></span> <span data-ttu-id="96d84-122">使用此方法的好处是提高了性能，当您在线时，在 Power BI 中 bog 的大型数据集尤其有用。</span><span class="sxs-lookup"><span data-stu-id="96d84-122">The benefit of using this method is better performance, especially useful for large data sets that bog down in Power BI when you're online.</span></span>       |
|<span data-ttu-id="96d84-123">Graph API</span><span class="sxs-lookup"><span data-stu-id="96d84-123">Graph API</span></span>     | <span data-ttu-id="96d84-124">使用[图形 API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta)访问呼叫质量数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-124">Access call quality data yourself using the [Graph API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta).</span></span> <span data-ttu-id="96d84-125">这是最复杂的方法，但它为你提供了分析通话质量数据的最大控制和灵活性。</span><span class="sxs-lookup"><span data-stu-id="96d84-125">This is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data.</span></span> <span data-ttu-id="96d84-126">例如，如果你需要将其与你的组织的其他数据结合使用，则可以使用 Graph API 创建数据模型并合并通话质量数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-126">For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data.</span></span>        |

## <a name="import-the-cqd-report-templates"></a><span data-ttu-id="96d84-127">导入 CQD 报表模板</span><span class="sxs-lookup"><span data-stu-id="96d84-127">Import the CQD report templates</span></span>

<span data-ttu-id="96d84-128">下载[两个特选 CQD 报表模板](https://aka.ms/qertemplates) (所有网络和托管) 网络，以帮助你快速快速掌握 CQD。</span><span class="sxs-lookup"><span data-stu-id="96d84-128">Download [two curated CQD report templates](https://aka.ms/qertemplates) (All Networks and Managed Networks) to help you get up to speed quickly with CQD.</span></span> <span data-ttu-id="96d84-129">"所有网络" 模板（虽然已优化为使用生成数据文件）可用于在 CQD 中收集和上载构建信息，如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="96d84-129">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="96d84-130">**若要导入模板 (。CQDX) CQD**</span><span class="sxs-lookup"><span data-stu-id="96d84-130">**To import the templates (.CQDX) into CQD**</span></span>

1. <span data-ttu-id="96d84-131">在 CQD 中，从页面顶部的菜单中选择 "**详细报告**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-131">In CQD, select **Detailed Reports** from the menu at the top of the page.</span></span>

2. <span data-ttu-id="96d84-132">在左面板中，选择 "**导入**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-132">In the left panel, select **Import**.</span></span> <span data-ttu-id="96d84-133">浏览到第一个 CQDX 模板，然后选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-133">Browse to the first CQDX template and select **Open**.</span></span>

3. <span data-ttu-id="96d84-134">上载模板后，将显示一个弹出窗口，显示 "报表导入成功" 消息。</span><span class="sxs-lookup"><span data-stu-id="96d84-134">After the template is uploaded, a pop-up window will display the message "Report import was successful."</span></span> 

4. <span data-ttu-id="96d84-135">对第二个 CQD 模板重复步骤2和步骤3。</span><span class="sxs-lookup"><span data-stu-id="96d84-135">Repeat steps 2 and 3 for the second CQD template.</span></span>

> [!NOTE]
> <span data-ttu-id="96d84-136">每个用户都必须将 CQD 模板导入其 CQD 实例。</span><span class="sxs-lookup"><span data-stu-id="96d84-136">Each user must import the CQD templates into their CQD instance.</span></span> 



## <a name="euii-data"></a><span data-ttu-id="96d84-137">EUII 数据</span><span class="sxs-lookup"><span data-stu-id="96d84-137">EUII data</span></span>

<span data-ttu-id="96d84-138">出于合规性原因， (EUII 的最终用户可识别信息) 数据 (也称为个人身份信息或 PII) 仅保留30天。</span><span class="sxs-lookup"><span data-stu-id="96d84-138">For compliance reasons, end-user identifiable information (EUII) data (also known as personally-identifiable information or PII) is only kept for 30 days.</span></span> <span data-ttu-id="96d84-139">由于 NRT 数据与30天的标记相比较，包含 EUII 的字段将被清除，从而导致 EUII 无 NRT 数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-139">As NRT data crosses the 30-day mark, fields that contain EUII are cleared, resulting in EUII-free NRT data.</span></span> <span data-ttu-id="96d84-140">包含 EUII 数据的字段是：</span><span class="sxs-lookup"><span data-stu-id="96d84-140">Fields that contain EUII data are:</span></span>

- <span data-ttu-id="96d84-141">完整 IP 地址</span><span class="sxs-lookup"><span data-stu-id="96d84-141">Full IP address</span></span>
- <span data-ttu-id="96d84-142">媒体访问控制 (MAC) 地址</span><span class="sxs-lookup"><span data-stu-id="96d84-142">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="96d84-143">基本服务设置标识符 (BSSID) </span><span class="sxs-lookup"><span data-stu-id="96d84-143">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="96d84-144">会话初始协议 (SIP) URI 仅 (Skype for business) </span><span class="sxs-lookup"><span data-stu-id="96d84-144">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="96d84-145">用户主体名称 (UPN)</span><span class="sxs-lookup"><span data-stu-id="96d84-145">User Principal Name (UPN)</span></span>
- <span data-ttu-id="96d84-146">计算机终结点名称</span><span class="sxs-lookup"><span data-stu-id="96d84-146">Machine Endpoint Name</span></span>
- <span data-ttu-id="96d84-147">用户逐字反馈</span><span class="sxs-lookup"><span data-stu-id="96d84-147">User Verbatim Feedback</span></span>
- <span data-ttu-id="96d84-148"> (终结点用户的 Active Directory 对象 ID 的对象 ID) </span><span class="sxs-lookup"><span data-stu-id="96d84-148">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="admin-roles-with-and-without-euii-access"></a><span data-ttu-id="96d84-149">具有和不具有 EUII 访问权限的管理员角色</span><span class="sxs-lookup"><span data-stu-id="96d84-149">Admin roles with and without EUII access</span></span>

<span data-ttu-id="96d84-150">这些[RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview)角色**确实**具有 EUII 访问权限：</span><span class="sxs-lookup"><span data-stu-id="96d84-150">These [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) roles **DO** have EUII access:</span></span>
- <span data-ttu-id="96d84-151">全局管理员</span><span class="sxs-lookup"><span data-stu-id="96d84-151">Global Admin</span></span>
- <span data-ttu-id="96d84-152">团队服务管理员</span><span class="sxs-lookup"><span data-stu-id="96d84-152">Teams Service Admin</span></span>
- <span data-ttu-id="96d84-153">团队通信管理员</span><span class="sxs-lookup"><span data-stu-id="96d84-153">Teams Communications Admin</span></span>
- <span data-ttu-id="96d84-154">Teams 通信支持工程师</span><span class="sxs-lookup"><span data-stu-id="96d84-154">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="96d84-155">全局阅读器</span><span class="sxs-lookup"><span data-stu-id="96d84-155">Global Reader</span></span>
- <span data-ttu-id="96d84-156">Skype for Business 管理员</span><span class="sxs-lookup"><span data-stu-id="96d84-156">Skype for Business Admin</span></span>

<span data-ttu-id="96d84-157">这些 RBAC 角色**没有**EUII 访问权限：</span><span class="sxs-lookup"><span data-stu-id="96d84-157">These RBAC roles **DON'T** have EUII access:</span></span>
- <span data-ttu-id="96d84-158">报表读者</span><span class="sxs-lookup"><span data-stu-id="96d84-158">Reports Reader</span></span>
- <span data-ttu-id="96d84-159">团队沟通支持专家</span><span class="sxs-lookup"><span data-stu-id="96d84-159">Teams Communications Support Specialist</span></span>


## <a name="date-controls"></a><span data-ttu-id="96d84-160">日期控件</span><span class="sxs-lookup"><span data-stu-id="96d84-160">Date controls</span></span>

<span data-ttu-id="96d84-161">CQD 支持以下滚动趋势类型：</span><span class="sxs-lookup"><span data-stu-id="96d84-161">CQD supports the following Rolling Trend types:</span></span>

- <span data-ttu-id="96d84-162">5天</span><span class="sxs-lookup"><span data-stu-id="96d84-162">5-day</span></span>
- <span data-ttu-id="96d84-163">7天</span><span class="sxs-lookup"><span data-stu-id="96d84-163">7-day</span></span>
- <span data-ttu-id="96d84-164">30天</span><span class="sxs-lookup"><span data-stu-id="96d84-164">30-day</span></span>
- <span data-ttu-id="96d84-165">60-day</span><span class="sxs-lookup"><span data-stu-id="96d84-165">60-day</span></span>
- <span data-ttu-id="96d84-166">90-day</span><span class="sxs-lookup"><span data-stu-id="96d84-166">90-day</span></span>

<span data-ttu-id="96d84-167">URL 日期参数接受 Day 字段。</span><span class="sxs-lookup"><span data-stu-id="96d84-167">The URL Date parameter accepts a Day field.</span></span> <span data-ttu-id="96d84-168">"滚动日期" 报告将 "YYYY-MM-DD 格式" 中指定的日期用作趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="96d84-168">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span> <span data-ttu-id="96d84-169">URL 日期参数 "00" 表示 "今日"。</span><span class="sxs-lookup"><span data-stu-id="96d84-169">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="96d84-170">URL</span><span class="sxs-lookup"><span data-stu-id="96d84-170">URL</span></span>| <span data-ttu-id="96d84-171">滚动日趋势的结束日期</span><span class="sxs-lookup"><span data-stu-id="96d84-171">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="96d84-172"><span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="96d84-172"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="96d84-173">2019年2月的当前日期</span><span class="sxs-lookup"><span data-stu-id="96d84-173">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="96d84-174"><span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="96d84-174"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="96d84-175">2019年2月15日</span><span class="sxs-lookup"><span data-stu-id="96d84-175">Feb 15, 2019</span></span>|
|<span data-ttu-id="96d84-176"><span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span></span><span class="sxs-lookup"><span data-stu-id="96d84-176"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="96d84-177">当前日期</span><span class="sxs-lookup"><span data-stu-id="96d84-177">Current Day</span></span>|
|||

<span data-ttu-id="96d84-178">默认情况下，该月的当前日期用作滚动日期趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="96d84-178">By default, the current day of the month is used as the last day of the Rolling Day Trend.</span></span>


## <a name="data-available-in-cqd-reports"></a><span data-ttu-id="96d84-179">CQD 报表中的可用数据</span><span class="sxs-lookup"><span data-stu-id="96d84-179">Data available in CQD reports</span></span>

<span data-ttu-id="96d84-180">默认摘要和详细 CQD 报表可能是管理组织的通话质量所需的全部信息。如果需要，您可以[创建自定义报表](#create-custom-detailed-reports)。</span><span class="sxs-lookup"><span data-stu-id="96d84-180">The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can [create custom reports](#create-custom-detailed-reports).</span></span> 

<span data-ttu-id="96d84-181">如果你想要使用 Power BI 分析你的 CQD 数据，请参阅[使用 POWER bi 分析团队的 CQD 数据](CQD-Power-BI-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="96d84-181">If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md).</span></span>

|<span data-ttu-id="96d84-182">功能</span><span class="sxs-lookup"><span data-stu-id="96d84-182">Feature</span></span>|<span data-ttu-id="96d84-183">摘要报告</span><span class="sxs-lookup"><span data-stu-id="96d84-183">Summary Reports</span></span>|<span data-ttu-id="96d84-184">详细报告</span><span class="sxs-lookup"><span data-stu-id="96d84-184">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="96d84-185">应用程序共享跃点数</span><span class="sxs-lookup"><span data-stu-id="96d84-185">Application sharing metric</span></span> | <span data-ttu-id="96d84-186">否</span><span class="sxs-lookup"><span data-stu-id="96d84-186">No</span></span> | <span data-ttu-id="96d84-187">是</span><span class="sxs-lookup"><span data-stu-id="96d84-187">Yes</span></span> |
|<span data-ttu-id="96d84-188">客户构建信息支持</span><span class="sxs-lookup"><span data-stu-id="96d84-188">Customer building information support</span></span> | <span data-ttu-id="96d84-189">是</span><span class="sxs-lookup"><span data-stu-id="96d84-189">Yes</span></span> | <span data-ttu-id="96d84-190">是</span><span class="sxs-lookup"><span data-stu-id="96d84-190">Yes</span></span> |
|<span data-ttu-id="96d84-191">客户终结点信息支持</span><span class="sxs-lookup"><span data-stu-id="96d84-191">Customer endpoint information support</span></span> | <span data-ttu-id="96d84-192">仅在 <span> cqd.teams.microsoft.com 中<span/></span><span class="sxs-lookup"><span data-stu-id="96d84-192">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="96d84-193">仅在 <span> cqd.teams.microsoft.com 中<span/></span><span class="sxs-lookup"><span data-stu-id="96d84-193">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="96d84-194">向下钻取分析支持</span><span class="sxs-lookup"><span data-stu-id="96d84-194">Drill down analysis support</span></span>   | <span data-ttu-id="96d84-195">否</span><span class="sxs-lookup"><span data-stu-id="96d84-195">No</span></span>   | <span data-ttu-id="96d84-196">是</span><span class="sxs-lookup"><span data-stu-id="96d84-196">Yes</span></span>   |
|<span data-ttu-id="96d84-197">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="96d84-197">Media reliability metrics</span></span>   | <span data-ttu-id="96d84-198">否</span><span class="sxs-lookup"><span data-stu-id="96d84-198">No</span></span>   | <span data-ttu-id="96d84-199">是</span><span class="sxs-lookup"><span data-stu-id="96d84-199">Yes</span></span>   |
|<span data-ttu-id="96d84-200">现成的报表</span><span class="sxs-lookup"><span data-stu-id="96d84-200">Out-of-the-box reports</span></span>   | <span data-ttu-id="96d84-201">是</span><span class="sxs-lookup"><span data-stu-id="96d84-201">Yes</span></span>   | <span data-ttu-id="96d84-202">是</span><span class="sxs-lookup"><span data-stu-id="96d84-202">Yes</span></span>   |
|<span data-ttu-id="96d84-203">概述报表</span><span class="sxs-lookup"><span data-stu-id="96d84-203">Overview reports</span></span>   | <span data-ttu-id="96d84-204">是</span><span class="sxs-lookup"><span data-stu-id="96d84-204">Yes</span></span>   | <span data-ttu-id="96d84-205">是</span><span class="sxs-lookup"><span data-stu-id="96d84-205">Yes</span></span>   |
|<span data-ttu-id="96d84-206">每用户报告集</span><span class="sxs-lookup"><span data-stu-id="96d84-206">Per-user report set</span></span>   | <span data-ttu-id="96d84-207">否</span><span class="sxs-lookup"><span data-stu-id="96d84-207">No</span></span>   | <span data-ttu-id="96d84-208">是</span><span class="sxs-lookup"><span data-stu-id="96d84-208">Yes</span></span>   |
|<span data-ttu-id="96d84-209">报表集自定义 (添加、删除、修改报表) </span><span class="sxs-lookup"><span data-stu-id="96d84-209">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="96d84-210">否</span><span class="sxs-lookup"><span data-stu-id="96d84-210">No</span></span>   | <span data-ttu-id="96d84-211">是</span><span class="sxs-lookup"><span data-stu-id="96d84-211">Yes</span></span>   |
|<span data-ttu-id="96d84-212">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="96d84-212">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="96d84-213">否</span><span class="sxs-lookup"><span data-stu-id="96d84-213">No</span></span>   | <span data-ttu-id="96d84-214">是</span><span class="sxs-lookup"><span data-stu-id="96d84-214">Yes</span></span>   |
|<span data-ttu-id="96d84-215">视频指标</span><span class="sxs-lookup"><span data-stu-id="96d84-215">Video metrics</span></span>   | <span data-ttu-id="96d84-216">否</span><span class="sxs-lookup"><span data-stu-id="96d84-216">No</span></span>   | <span data-ttu-id="96d84-217">是</span><span class="sxs-lookup"><span data-stu-id="96d84-217">Yes</span></span>   |
|<span data-ttu-id="96d84-218">可用数据量</span><span class="sxs-lookup"><span data-stu-id="96d84-218">Amount of data available</span></span>   | <span data-ttu-id="96d84-219">过去12个月</span><span class="sxs-lookup"><span data-stu-id="96d84-219">Last 12 months</span></span>   | <span data-ttu-id="96d84-220">过去12个月</span><span class="sxs-lookup"><span data-stu-id="96d84-220">Last 12 months</span></span>   |
|<span data-ttu-id="96d84-221">Microsoft 团队数据</span><span class="sxs-lookup"><span data-stu-id="96d84-221">Microsoft Teams data</span></span>   | <span data-ttu-id="96d84-222">是</span><span class="sxs-lookup"><span data-stu-id="96d84-222">Yes</span></span>   | <span data-ttu-id="96d84-223">是</span><span class="sxs-lookup"><span data-stu-id="96d84-223">Yes</span></span>   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a><span data-ttu-id="96d84-224">选择要在报表中查看的产品数据</span><span class="sxs-lookup"><span data-stu-id="96d84-224">Select product data to see in reports</span></span>

<span data-ttu-id="96d84-225">在摘要和位置增强的报表中，你可以使用 "**产品筛选器**" 下拉列表显示所有产品数据、仅 Microsoft 团队数据或仅 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-225">In the Summary and Location-Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![屏幕截图：显示产品筛选器控件选项](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="96d84-227">在 "详细报表" 中，可以使用 "**属于团队**" 维度将数据筛选到 Microsoft 团队或 Skype For business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-227">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>

## <a name="summary-reports"></a><span data-ttu-id="96d84-228">摘要报告</span><span class="sxs-lookup"><span data-stu-id="96d84-228">Summary Reports</span></span>

<span data-ttu-id="96d84-229">这些是你首次登录 CQD 时将在 CQD 仪表板上看到的报表。</span><span class="sxs-lookup"><span data-stu-id="96d84-229">These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD.</span></span> <span data-ttu-id="96d84-230">它们通过 "每天"、"每月" 和 "表" 报表为您提供概览的质量趋势，以帮助识别质量较差的子网。</span><span class="sxs-lookup"><span data-stu-id="96d84-230">They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.</span></span> 

|<span data-ttu-id="96d84-231">选项卡</span><span class="sxs-lookup"><span data-stu-id="96d84-231">Tab</span></span>  |  |
|---------|---------|
|<span data-ttu-id="96d84-232">整体通话质量</span><span class="sxs-lookup"><span data-stu-id="96d84-232">Overall Call Quality</span></span>     | <span data-ttu-id="96d84-233">聚合其他3个选项卡</span><span class="sxs-lookup"><span data-stu-id="96d84-233">Aggregate of the other 3 tabs</span></span>        |
|<span data-ttu-id="96d84-234">服务器-客户端</span><span class="sxs-lookup"><span data-stu-id="96d84-234">Server—Client</span></span>     |<span data-ttu-id="96d84-235">服务器和客户端终结点之间的流的详细信息</span><span class="sxs-lookup"><span data-stu-id="96d84-235">Details of the streams between server and client endpoints</span></span>         |
|<span data-ttu-id="96d84-236">客户端-客户端</span><span class="sxs-lookup"><span data-stu-id="96d84-236">Client—Client</span></span>     |<span data-ttu-id="96d84-237">两个客户端终结点之间的流的详细信息</span><span class="sxs-lookup"><span data-stu-id="96d84-237">Details of the streams between two client endpoints</span></span>         |
|<span data-ttu-id="96d84-238">语音质量 SLA</span><span class="sxs-lookup"><span data-stu-id="96d84-238">Voice Quality SLA</span></span>     |<span data-ttu-id="96d84-239">有关 Skype for Business 语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)中包含的通话的信息</span><span class="sxs-lookup"><span data-stu-id="96d84-239">Info about calls included in the Skype for Business voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)</span></span>         |

### <a name="overall-call-quality-tab"></a><span data-ttu-id="96d84-240">"整体通话质量" 选项卡</span><span class="sxs-lookup"><span data-stu-id="96d84-240">Overall Call Quality tab</span></span>

<span data-ttu-id="96d84-241">使用此选项卡上的数据根据流计数和不良百分比评估通话质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="96d84-241">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="96d84-242">右上角的图例将显示哪些颜色和视觉元素表示这些指标。</span><span class="sxs-lookup"><span data-stu-id="96d84-242">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![屏幕截图：显示 "通话质量" 选项卡](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="96d84-244">流分为三个组： "完好"、"差" 和 "未分类"。</span><span class="sxs-lookup"><span data-stu-id="96d84-244">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="96d84-245">还计算出的*百分比*值太差，可让你将流的比率划分为*较差*的分类流计数。</span><span class="sxs-lookup"><span data-stu-id="96d84-245">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="96d84-246">由于*差% = 不良流/ (不良流 + 正常流) \* 100*，*较差的%* 不受多个未*分类*流的存在的影响。</span><span class="sxs-lookup"><span data-stu-id="96d84-246">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="96d84-247">若要查看将流分类为差或好的内容，请参阅["呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。</span><span class="sxs-lookup"><span data-stu-id="96d84-247">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="96d84-248">使用左侧的刻度测量流计数值。</span><span class="sxs-lookup"><span data-stu-id="96d84-248">Use the scale on the left to measure the stream count values.</span></span>
  
![屏幕截图：显示流计数值](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="96d84-250">使用右侧的刻度测量差的百分比值。</span><span class="sxs-lookup"><span data-stu-id="96d84-250">Use the scale on the right to measure the Poor % values.</span></span>
  
![屏幕截图：显示差的% 值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="96d84-252">也可以通过将鼠标悬停在条上来获取实际数值。</span><span class="sxs-lookup"><span data-stu-id="96d84-252">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96d84-253">下面的示例来自非常小的示例数据集，并且值对于实际部署不切合实际。</span><span class="sxs-lookup"><span data-stu-id="96d84-253">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![屏幕截图：显示用于访问数据的鼠标](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="96d84-255">整个流卷可帮助确定计算出的较差百分比的相关程度。</span><span class="sxs-lookup"><span data-stu-id="96d84-255">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="96d84-256">总体流的数量越小，报告的百分比值越低越可靠。</span><span class="sxs-lookup"><span data-stu-id="96d84-256">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="96d84-257">服务器-客户端选项卡和客户端-客户端选项卡</span><span class="sxs-lookup"><span data-stu-id="96d84-257">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="96d84-258">这两个选项卡提供了在其终结点到终结点应用场景中发生的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="96d84-258">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="96d84-259">"服务器-客户端" 选项卡具有四个可折叠的部分，表示媒体流将流经的四个方案。</span><span class="sxs-lookup"><span data-stu-id="96d84-259">The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="96d84-260">内部有线</span><span class="sxs-lookup"><span data-stu-id="96d84-260">Wired Inside</span></span>
- <span data-ttu-id="96d84-261">外部有线</span><span class="sxs-lookup"><span data-stu-id="96d84-261">Wired Outside</span></span>
- <span data-ttu-id="96d84-262">内部 WiFi</span><span class="sxs-lookup"><span data-stu-id="96d84-262">WiFi Inside</span></span>
- <span data-ttu-id="96d84-263">外部 WiFi</span><span class="sxs-lookup"><span data-stu-id="96d84-263">WiFi Outside</span></span>

<span data-ttu-id="96d84-264">同样，"客户端-客户端" 选项卡具有五个可折叠部分：</span><span class="sxs-lookup"><span data-stu-id="96d84-264">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="96d84-265">有线内部-有线内部</span><span class="sxs-lookup"><span data-stu-id="96d84-265">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="96d84-266">有线内部-有线外部</span><span class="sxs-lookup"><span data-stu-id="96d84-266">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="96d84-267">有线外部-有线外部</span><span class="sxs-lookup"><span data-stu-id="96d84-267">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="96d84-268">内部有线-内部 WiFi</span><span class="sxs-lookup"><span data-stu-id="96d84-268">Wired Inside — WiFi Inside</span></span>
- <span data-ttu-id="96d84-269">内部有线-外部 WiFi</span><span class="sxs-lookup"><span data-stu-id="96d84-269">Wired Inside — WiFi Outside</span></span>

#### <a name="inside-versus-outside"></a><span data-ttu-id="96d84-270">内部和外部</span><span class="sxs-lookup"><span data-stu-id="96d84-270">Inside versus Outside</span></span>

<span data-ttu-id="96d84-271">CQD 使用建筑物信息将流分类为*内部*或*外部*流（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="96d84-271">CQD classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="96d84-272">每个流的终结点与子网地址相关联。</span><span class="sxs-lookup"><span data-stu-id="96d84-272">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="96d84-273">如果子网位于上载的生成信息中标记为 "InsideCorp" 的子网列表中，则将其视为*内部*。</span><span class="sxs-lookup"><span data-stu-id="96d84-273">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="96d84-274">如果尚未上载生成信息，则内部测试始终会将流分类为*外部*流。</span><span class="sxs-lookup"><span data-stu-id="96d84-274">If Building information has not yet been uploaded, then Inside Test always classifies the streams as *Outside*.</span></span> 

<span data-ttu-id="96d84-275">服务器客户端方案的内部测试仅考虑客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="96d84-275">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="96d84-276">由于服务器始终来自用户的视角，因此不会在测试中考虑。</span><span class="sxs-lookup"><span data-stu-id="96d84-276">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-versus-wifi"></a><span data-ttu-id="96d84-277">有线与 WiFi</span><span class="sxs-lookup"><span data-stu-id="96d84-277">Wired versus WiFi</span></span>

<span data-ttu-id="96d84-278">根据名称指示，分类标准基于客户端连接的类型。</span><span class="sxs-lookup"><span data-stu-id="96d84-278">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="96d84-279">服务器始终处于有线，并且不会包含在计算中。</span><span class="sxs-lookup"><span data-stu-id="96d84-279">Server is always wired and it isn't included in the calculation.</span></span> <span data-ttu-id="96d84-280">在给定流中，如果两个终结点之一连接到 WiFi 网络，则 CQD 将其分类为 WiFi。</span><span class="sxs-lookup"><span data-stu-id="96d84-280">In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.</span></span>
> [!NOTE]
> <span data-ttu-id="96d84-281">如果有一个流，则如果两个终结点中的一个终结点连接到 WiFi 网络，则会在 CQD 中将其分类为 WiFi。</span><span class="sxs-lookup"><span data-stu-id="96d84-281">Given a stream, if one of the two endpoints is connected to a WiFi network, then it is classified as WiFi in CQD.</span></span>
  
  
## <a name="tenant-data-information"></a><span data-ttu-id="96d84-282">租户数据信息</span><span class="sxs-lookup"><span data-stu-id="96d84-282">Tenant Data information</span></span>

<span data-ttu-id="96d84-283">CQD 摘要报告仪表板包括**租户数据上载**页面，该页面从右上角的 "设置" 菜单中选择 "**租户数据上载**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-283">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="96d84-284">此页面用于管理员上载其自己的信息，例如：</span><span class="sxs-lookup"><span data-stu-id="96d84-284">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="96d84-285">IP 地址和地理信息的地图</span><span class="sxs-lookup"><span data-stu-id="96d84-285">A map of IP address and geographical information</span></span>
- <span data-ttu-id="96d84-286">每个无线 AP 及其 MAC 地址的地图</span><span class="sxs-lookup"><span data-stu-id="96d84-286">A map of each wireless AP and its MAC address</span></span>
- <span data-ttu-id="96d84-287">终结点到终结点的映射/模型/类型等。</span><span class="sxs-lookup"><span data-stu-id="96d84-287">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
<span data-ttu-id="96d84-288">我们建议你上载租户、构建和位置数据，以便 CQD 可以将此信息包含在你的报表中。</span><span class="sxs-lookup"><span data-stu-id="96d84-288">We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports.</span></span> <span data-ttu-id="96d84-289">如果尚未上载此数据，请阅读[上载租户和生成数据](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="96d84-289">If you haven't already uploaded this data, read [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span> 


## <a name="detailed-reports"></a><span data-ttu-id="96d84-290">详细报告</span><span class="sxs-lookup"><span data-stu-id="96d84-290">Detailed reports</span></span>

|<span data-ttu-id="96d84-291">名称</span><span class="sxs-lookup"><span data-stu-id="96d84-291">Name</span></span>  |  |
|---------|---------|
|<span data-ttu-id="96d84-292">位置增强的报表</span><span class="sxs-lookup"><span data-stu-id="96d84-292">Location-Enhanced Reports</span></span>     |<span data-ttu-id="96d84-293">基于位置信息显示质量趋势。</span><span class="sxs-lookup"><span data-stu-id="96d84-293">Shows quality trends based on location information.</span></span> <span data-ttu-id="96d84-294">仅当你[上载了租户数据](CQD-upload-tenant-building-data.md)时，才会显示此报告。</span><span class="sxs-lookup"><span data-stu-id="96d84-294">This report appears only if you've [uploaded your tenant data](CQD-upload-tenant-building-data.md).</span></span>        |
|<span data-ttu-id="96d84-295">可靠性报告</span><span class="sxs-lookup"><span data-stu-id="96d84-295">Reliability Reports</span></span>     |<span data-ttu-id="96d84-296">包括音频、视频、基于视频的屏幕共享 (VBSS) 和应用共享报告</span><span class="sxs-lookup"><span data-stu-id="96d84-296">Includes audio, video, video-based screen sharing (VBSS), and app sharing reports</span></span>         |
|<span data-ttu-id="96d84-297">体验报告质量</span><span class="sxs-lookup"><span data-stu-id="96d84-297">Quality of Experience Reports</span></span>     |<span data-ttu-id="96d84-298">所有客户端和设备（包括会议室）的音频质量和可靠性。</span><span class="sxs-lookup"><span data-stu-id="96d84-298">Audio quality and reliability for all clients and devices, including meeting rooms.</span></span> <span data-ttu-id="96d84-299">这些报表是可下载的[CQD 模板](https://aka.ms/QERtemplates)的 "slimmed" 版本，侧重于分析音频质量和可靠性的关键区域。</span><span class="sxs-lookup"><span data-stu-id="96d84-299">These reports are a “slimmed-down” version of the downloadable [CQD templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability.</span></span>         |
|<span data-ttu-id="96d84-300">质量向下钻取报表</span><span class="sxs-lookup"><span data-stu-id="96d84-300">Quality Drill Down Reports</span></span>     | <span data-ttu-id="96d84-301">钻取：按区域、位置、子网、小时和用户的日期</span><span class="sxs-lookup"><span data-stu-id="96d84-301">Drill downs: Date by region, locations, subnets, hour, and users</span></span>         |
|<span data-ttu-id="96d84-302">故障深化报告</span><span class="sxs-lookup"><span data-stu-id="96d84-302">Failure Drill Down Reports</span></span>     | <span data-ttu-id="96d84-303">钻取：按区域、位置、子网、小时和用户的日期</span><span class="sxs-lookup"><span data-stu-id="96d84-303">Drill downs: Date by region, locations, subnets, hour, and users</span></span>        |
|<span data-ttu-id="96d84-304">评价我的呼叫报告</span><span class="sxs-lookup"><span data-stu-id="96d84-304">Rate My Call Reports</span></span>     |<span data-ttu-id="96d84-305">按区域、位置或用户分析用户呼叫分级。</span><span class="sxs-lookup"><span data-stu-id="96d84-305">Analyze user call ratings by region, location, or by user.</span></span> <span data-ttu-id="96d84-306">包括逐字反馈。</span><span class="sxs-lookup"><span data-stu-id="96d84-306">Includes verbatim feedback.</span></span>         |
|<span data-ttu-id="96d84-307">技术支持报表</span><span class="sxs-lookup"><span data-stu-id="96d84-307">Help Desk Reports</span></span>     |<span data-ttu-id="96d84-308">技术支持报告查看单个用户、用户组或每个人的呼叫和会议数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-308">Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone.</span></span> <span data-ttu-id="96d84-309">通过结合构建和 EUII 数据，这些报告可帮助识别基于网络位置、会议详细信息、设备或固件的可能的系统问题。</span><span class="sxs-lookup"><span data-stu-id="96d84-309">Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware.</span></span>         |
|<span data-ttu-id="96d84-310">客户端版本报告</span><span class="sxs-lookup"><span data-stu-id="96d84-310">Client Version Reports</span></span>     |<span data-ttu-id="96d84-311">客户端版本摘要：查看每个客户端应用版本的会话和用户计数</span><span class="sxs-lookup"><span data-stu-id="96d84-311">Client Version Summary: View the Sessions and Users counts for each client app version</span></span><br><br><span data-ttu-id="96d84-312">客户端版本（按用户）：查看每个客户端应用版本的用户名称</span><span class="sxs-lookup"><span data-stu-id="96d84-312">Client Version by User: View user names for each client app version</span></span> <br><br><span data-ttu-id="96d84-313">产品和客户端类型的预生成筛选器帮助将版本集中到特定客户端。</span><span class="sxs-lookup"><span data-stu-id="96d84-313">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>         |
|<span data-ttu-id="96d84-314">终结点报表</span><span class="sxs-lookup"><span data-stu-id="96d84-314">Endpoint Reports</span></span>     |<span data-ttu-id="96d84-315">按计算机终结点 (计算机和型号) 显示呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="96d84-315">Shows call quality by machine endpoints (computer make and model).</span></span> <span data-ttu-id="96d84-316">这些报表包括生成数据（如果已上载）。</span><span class="sxs-lookup"><span data-stu-id="96d84-316">These reports include building data, if you've uploaded it.</span></span>         |


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="96d84-317">创建自定义详细报告</span><span class="sxs-lookup"><span data-stu-id="96d84-317">Create custom detailed reports</span></span>

<span data-ttu-id="96d84-318">如果默认 CQD 报表不能满足您的需要，请按照以下说明创建自定义报表。</span><span class="sxs-lookup"><span data-stu-id="96d84-318">If the default CQD reports don't meet your needs, use these instructions to create a custom report.</span></span> <span data-ttu-id="96d84-319">或 (至2020年1月) [使用 POWER BI FOR CQD 报表](cqd-power-bi-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="96d84-319">Or (as of January 2020) [Use Power BI for CQD reports ](cqd-power-bi-query-templates.md)instead.</span></span>

<span data-ttu-id="96d84-320">从 "登录摘要报告" 屏幕上显示的屏幕顶部显示的报告下拉列表中， \( **Summary Reports**选择 " \) **详细报告**"，然后选择 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-320">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New**.</span></span> <span data-ttu-id="96d84-321">单击报表中的 "**编辑**" 以查看查询编辑器。</span><span class="sxs-lookup"><span data-stu-id="96d84-321">Click **Edit** in a report to see the Query Editor.</span></span> <span data-ttu-id="96d84-322">每个报告都可以通过对多维数据集进行查询得到。</span><span class="sxs-lookup"><span data-stu-id="96d84-322">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="96d84-323">报告是其查询返回的数据的可视化形式。</span><span class="sxs-lookup"><span data-stu-id="96d84-323">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="96d84-324">查询编辑器可帮助您编辑报表的这些查询和显示选项。</span><span class="sxs-lookup"><span data-stu-id="96d84-324">The Query Editor helps you edit these queries and the display options of the report.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="96d84-325">网络范围可用于表示具有单个路由前缀) 的多个子网的 supernet (组合。</span><span class="sxs-lookup"><span data-stu-id="96d84-325">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="96d84-326">将检查所有新的生成上载，查找任何重叠区域。</span><span class="sxs-lookup"><span data-stu-id="96d84-326">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="96d84-327">如果你以前上载了一个生成文件，则应下载当前文件，然后重新上载它以标识任何重叠，并在再次上载之前修复该问题。</span><span class="sxs-lookup"><span data-stu-id="96d84-327">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="96d84-328">以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。</span><span class="sxs-lookup"><span data-stu-id="96d84-328">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="96d84-329">某些 VPN 实现不能准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="96d84-329">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="96d84-330">建议将 VPN 子网添加到生成文件，而不是子网的一个条目时，将 VPN 子网中每个地址的单独条目添加为单独的32位网络。</span><span class="sxs-lookup"><span data-stu-id="96d84-330">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="96d84-331">每一行可以有相同的建筑物元数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-331">Each row can have the same building metadata.</span></span> <span data-ttu-id="96d84-332">例如，对于 172.16.18.0/24，而不是一行，您应该有256行，每个地址对应于 172.16.18.0/32 和 172.16.18.255/32 之间（包括这两个地址）的一行。</span><span class="sxs-lookup"><span data-stu-id="96d84-332">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="96d84-333">"VPN" 列是可选的，默认值为0。</span><span class="sxs-lookup"><span data-stu-id="96d84-333">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="96d84-334">如果 VPN 列的值设置为1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="96d84-334">If the VPN column's value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="96d84-335">请谨慎使用，并且仅针对 VPN 子网，因为完全展开这些子网将对涉及生成数据的查询的查询时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="96d84-335">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

<span data-ttu-id="96d84-336">指向报表中的 "条形图" 和 "趋势线" 以显示详细值。</span><span class="sxs-lookup"><span data-stu-id="96d84-336">Point to bar charts and trend lines in the report to display detailed values.</span></span> <span data-ttu-id="96d84-337">具有焦点的报表将显示 "操作" 菜单： "**编辑**"、"**复制**"、"**删除**"、"**下载**" 和 "**导出" 报表树**。</span><span class="sxs-lookup"><span data-stu-id="96d84-337">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>



## <a name="query-filters"></a><span data-ttu-id="96d84-338">查询筛选器</span><span class="sxs-lookup"><span data-stu-id="96d84-338">Query filters</span></span>

<span data-ttu-id="96d84-339">查询筛选器通过在 CQD 中使用查询编辑器实现。</span><span class="sxs-lookup"><span data-stu-id="96d84-339">Query filters are implemented by using the Query Editor in CQD.</span></span> <span data-ttu-id="96d84-340">这些筛选器用于减少 CQD 返回的记录数，从而最大程度减少报表的总体大小和查询时间。</span><span class="sxs-lookup"><span data-stu-id="96d84-340">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size and query times.</span></span> <span data-ttu-id="96d84-341">这对于筛选出非托管网络尤其有用。</span><span class="sxs-lookup"><span data-stu-id="96d84-341">This is especially useful for filtering out unmanaged networks.</span></span> <span data-ttu-id="96d84-342">下表中列出的筛选器使用正则表达式 (RegEx) 。</span><span class="sxs-lookup"><span data-stu-id="96d84-342">The filters listed in the following table use regular expressions (RegEx).</span></span>


| <span data-ttu-id="96d84-343">筛选器</span><span class="sxs-lookup"><span data-stu-id="96d84-343">Filter</span></span>         | <span data-ttu-id="96d84-344">说明</span><span class="sxs-lookup"><span data-stu-id="96d84-344">Description</span></span>          | <span data-ttu-id="96d84-345">CQD 查询筛选器示例</span><span class="sxs-lookup"><span data-stu-id="96d84-345">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="96d84-346">无空值</span><span class="sxs-lookup"><span data-stu-id="96d84-346">No blank values</span></span>   | <span data-ttu-id="96d84-347">某些筛选器没有用于筛选空值的选项。</span><span class="sxs-lookup"><span data-stu-id="96d84-347">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="96d84-348">若要手动筛选空值，请使用空白表达式，并将筛选器设置为等于或不等于，具体取决于你的需求。</span><span class="sxs-lookup"><span data-stu-id="96d84-348">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="96d84-349">第二建筑物名称 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="96d84-349">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="96d84-350">排除公共子网</span><span class="sxs-lookup"><span data-stu-id="96d84-350">Exclude common subnets</span></span> | <span data-ttu-id="96d84-351">如果没有有效的生成文件以从非托管网络单独托管，则报告中将包含家庭网络。</span><span class="sxs-lookup"><span data-stu-id="96d84-351">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="96d84-352">这些主子网位于其控制范围之外，可以从报表中快速排除。</span><span class="sxs-lookup"><span data-stu-id="96d84-352">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="96d84-353">本指南中定义的常用子网是10.0.0.0、192.168.1.0 和192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="96d84-353">Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="96d84-354">第二子网 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1。0</span><span class="sxs-lookup"><span data-stu-id="96d84-354">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="96d84-355">仅限内部查看</span><span class="sxs-lookup"><span data-stu-id="96d84-355">View inside only</span></span>  | <span data-ttu-id="96d84-356">用于在) 之外的) 或非托管 (内筛选托管 (的报表。</span><span class="sxs-lookup"><span data-stu-id="96d84-356">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="96d84-357">托管 CQD 模板已预配置了这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="96d84-357">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="96d84-358">第二内部公司内部公司 = 内部</span><span class="sxs-lookup"><span data-stu-id="96d84-358">Second Inside Corp = Inside</span></span>        |

## <a name="report-filters"></a><span data-ttu-id="96d84-359">报表筛选器</span><span class="sxs-lookup"><span data-stu-id="96d84-359">Report filters</span></span>

<span data-ttu-id="96d84-360">使用 CQD 报表筛选器缩小调查的重点。</span><span class="sxs-lookup"><span data-stu-id="96d84-360">Use CQD report filters to narrow the focus of your investigations.</span></span> <span data-ttu-id="96d84-361">通过在查询编辑器或直接在报表中向呈现的报表添加筛选器，可以使用报表筛选器。</span><span class="sxs-lookup"><span data-stu-id="96d84-361">Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.</span></span> <span data-ttu-id="96d84-362">以下报表筛选器在整个[CQD 模板](https://aka.ms/QERtemplates)中使用。</span><span class="sxs-lookup"><span data-stu-id="96d84-362">The following report filters are used throughout the [CQD templates](https://aka.ms/QERtemplates).</span></span>


| <span data-ttu-id="96d84-363">筛选器</span><span class="sxs-lookup"><span data-stu-id="96d84-363">Filter</span></span>     | <span data-ttu-id="96d84-364">说明</span><span class="sxs-lookup"><span data-stu-id="96d84-364">Description</span></span>                            | <span data-ttu-id="96d84-365">CQD 报表筛选器示例</span><span class="sxs-lookup"><span data-stu-id="96d84-365">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="96d84-366">Month</span><span class="sxs-lookup"><span data-stu-id="96d84-366">Month</span></span>      | <span data-ttu-id="96d84-367">首先从年开始，然后是 "月"。</span><span class="sxs-lookup"><span data-stu-id="96d84-367">Start with the year first, then month.</span></span> | <span data-ttu-id="96d84-368">2017-10</span><span class="sxs-lookup"><span data-stu-id="96d84-368">2017-10</span></span>                           |
| <span data-ttu-id="96d84-369">字母</span><span class="sxs-lookup"><span data-stu-id="96d84-369">Alphabetic</span></span> | <span data-ttu-id="96d84-370">筛选任何字母字符。</span><span class="sxs-lookup"><span data-stu-id="96d84-370">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="96d84-371">[a-z]</span><span class="sxs-lookup"><span data-stu-id="96d84-371">[a-z]</span></span>                             |
| <span data-ttu-id="96d84-372">整数</span><span class="sxs-lookup"><span data-stu-id="96d84-372">Numeric</span></span>    | <span data-ttu-id="96d84-373">筛选任何数字字符。</span><span class="sxs-lookup"><span data-stu-id="96d84-373">Filters for any numeric characters.</span></span>    | <span data-ttu-id="96d84-374">[0-9]</span><span class="sxs-lookup"><span data-stu-id="96d84-374">[0-9]</span></span>                             |
| <span data-ttu-id="96d84-375">百分比</span><span class="sxs-lookup"><span data-stu-id="96d84-375">Percentage</span></span> | <span data-ttu-id="96d84-376">按百分比筛选。</span><span class="sxs-lookup"><span data-stu-id="96d84-376">Filters for a percentage.</span></span>              | <span data-ttu-id="96d84-377"> ( [3-9] \\ . ) \| ( [3-9] ) \| ( [1-9] [0-9] ) </span><span class="sxs-lookup"><span data-stu-id="96d84-377">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |


### <a name="drill-down-filters"></a><span data-ttu-id="96d84-378">向下钻取筛选器</span><span class="sxs-lookup"><span data-stu-id="96d84-378">Drill-down filters</span></span>

<span data-ttu-id="96d84-379">CQD 报表功能有多种分级式筛选器，这些筛选器是用于缩小通话质量调查重点的强大工具。</span><span class="sxs-lookup"><span data-stu-id="96d84-379">CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations.</span></span> <span data-ttu-id="96d84-380">如果选择 "向下钻取" 字段，报表将自动打开相应的选项卡并筛选所选值。</span><span class="sxs-lookup"><span data-stu-id="96d84-380">If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value.</span></span> <span data-ttu-id="96d84-381">如果该选项卡具有自己的向下钻取字段，并且选择了一个，则会同时应用两组筛选器，从而逐渐缩小生成的数据集。</span><span class="sxs-lookup"><span data-stu-id="96d84-381">If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.</span></span>

![演示向下钻取报表流的图表](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a><span data-ttu-id="96d84-383">添加和编辑向下钻取字段</span><span class="sxs-lookup"><span data-stu-id="96d84-383">Adding and editing drill-down fields</span></span>

<span data-ttu-id="96d84-384">编辑报表时，你可以选择使用查询编辑器指定你自己的向下钻取字段。</span><span class="sxs-lookup"><span data-stu-id="96d84-384">When editing a report, you have the option to specify drill-down fields of your own using the Query Editor.</span></span>

<span data-ttu-id="96d84-385">首先单击 " **...** "</span><span class="sxs-lookup"><span data-stu-id="96d84-385">Start by clicking **…**</span></span> <span data-ttu-id="96d84-386">对于要编辑的报表，然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-386">for the report you want to edit, then select **Edit**.</span></span>

![编辑向下钻取字段的屏幕截图](media/qerguide-image-addeditdrilldownfields.png)

<span data-ttu-id="96d84-388">从查询编辑器左侧的列表中选择一个维度。</span><span class="sxs-lookup"><span data-stu-id="96d84-388">Select a Dimension from the list on the left side of the Query Editor.</span></span> <span data-ttu-id="96d84-389">然后单击 "**导航到**标签" 下方的下拉列表，然后选择要该维度钻取到的选项卡和展开器组。</span><span class="sxs-lookup"><span data-stu-id="96d84-389">Then click on the dropdown below the **Navigate To** label and select the tab and expander group that you want that Dimension to drill through to.</span></span> <span data-ttu-id="96d84-390">注意：目前，向下钻取功能仅通过导航到不同的选项卡来工作。</span><span class="sxs-lookup"><span data-stu-id="96d84-390">Note: Presently, drill-down functionality only works by navigating to different tabs.</span></span> <span data-ttu-id="96d84-391">稍后将添加对特定展开器的钻取支持。</span><span class="sxs-lookup"><span data-stu-id="96d84-391">Support for drilling through to a specific expander will be added later.</span></span> <span data-ttu-id="96d84-392">最后，单击 "**关闭**" 以保存对维度所做的更改，然后单击 "**保存**" 以保存并关闭 "查询编辑器"。</span><span class="sxs-lookup"><span data-stu-id="96d84-392">Finally, click **Close** to save your changes to the Dimension, then click **Save** to save and close the Query Editor.</span></span>

![在查询编辑器中选择维度的屏幕截图](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a><span data-ttu-id="96d84-394">多选筛选器</span><span class="sxs-lookup"><span data-stu-id="96d84-394">Multi-select filters</span></span>

<span data-ttu-id="96d84-395">除了向下钻取功能之外，CQD 还支持指定具有多个值的筛选器 (或筛选) 。</span><span class="sxs-lookup"><span data-stu-id="96d84-395">In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).</span></span>

<span data-ttu-id="96d84-396">若要选择多个筛选值，请首先向报表添加新筛选器。</span><span class="sxs-lookup"><span data-stu-id="96d84-396">In order to select multiple filter values, begin by adding a new filter to the report.</span></span> <span data-ttu-id="96d84-397">单击 **+** "**筛选器**" 标签旁边的 "输入要使用的维度名称"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-397">Click **+** beside the **Filters** label, enter the name of the Dimension you want to use, and click **Add**.</span></span>

![添加多选筛选器的屏幕截图](media/qerguide-image-addmultiselectfilter.png)

<span data-ttu-id="96d84-399">然后，单击 "**搜索**" (新筛选) 旁边的放大镜图标。</span><span class="sxs-lookup"><span data-stu-id="96d84-399">Then, click **Search** (a magnifying glass icon next to the new filter).</span></span> <span data-ttu-id="96d84-400">你将看到一个文本字段和多个选项，包括 "全**选**" 和 "**反转**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-400">You'll see a text field, and a number of options, including **Select All** and **Invert**.</span></span> <span data-ttu-id="96d84-401">输入一个值，然后单击要搜索的字段旁边的 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-401">Enter a value,  and click **Search** next to that field to search.</span></span> <span data-ttu-id="96d84-402">或者，将文本字段保留为空，然后单击 "**搜索**" 以查看到最多第一个100选项。</span><span class="sxs-lookup"><span data-stu-id="96d84-402">Alternatively, leave the text field empty and click **Search** to view up to the first 100 options.</span></span>

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="96d84-403">上例</span><span class="sxs-lookup"><span data-stu-id="96d84-403">Example:</span></span>  

![添加查询筛选器的屏幕截图](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a><span data-ttu-id="96d84-405">仪表板级别筛选器</span><span class="sxs-lookup"><span data-stu-id="96d84-405">Dashboard level filters</span></span>
<span data-ttu-id="96d84-406">某些 CQD 报表将向其添加仪表板级筛选器，以便轻松按常用参数进行筛选。</span><span class="sxs-lookup"><span data-stu-id="96d84-406">Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters.</span></span> <span data-ttu-id="96d84-407">这些筛选器显示在常规报表选项卡之外和产品筛选器的正下方，它们应用于仪表板中的所有筛选器。</span><span class="sxs-lookup"><span data-stu-id="96d84-407">These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.</span></span>

![仪表板筛选器的屏幕截图](media/qerguide-image-dashboardfilters.png)
```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a><span data-ttu-id="96d84-409">URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="96d84-409">URL filters</span></span>

<span data-ttu-id="96d84-410">CQD 支持将筛选器添加到 URL。</span><span class="sxs-lookup"><span data-stu-id="96d84-410">CQD supports adding filters to the URL.</span></span> <span data-ttu-id="96d84-411">这使你可以轻松地共享或书签 CQD 查询。</span><span class="sxs-lookup"><span data-stu-id="96d84-411">This makes it easy to share or bookmark a CQD query.</span></span> <span data-ttu-id="96d84-412">可以在 URL 中定义参数，如 "趋势月份"、"租户 ID" 或 "语言"。</span><span class="sxs-lookup"><span data-stu-id="96d84-412">You can define parameters in the URL, such as Trending Month, tenant ID, or language.</span></span> <span data-ttu-id="96d84-413">您还可以将产品或仪表板级别的筛选器添加到 URL。</span><span class="sxs-lookup"><span data-stu-id="96d84-413">You can also add Product or Dashboard level filters to the URL.</span></span>
<span data-ttu-id="96d84-414">当修正托管建筑物或网络（其中联合终结点可能会影响你的报表）时，从 CQD 报告中排除联合数据将非常有用。</span><span class="sxs-lookup"><span data-stu-id="96d84-414">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

<span data-ttu-id="96d84-415">若要添加筛选器，请将以下内容附加到 URL 的末尾：</span><span class="sxs-lookup"><span data-stu-id="96d84-415">To add a filter, append the following to the end of the URL:</span></span>

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="96d84-416">上例</span><span class="sxs-lookup"><span data-stu-id="96d84-416">Example:</span></span>  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

<span data-ttu-id="96d84-417">若要将仪表板级别的筛选器添加到 URL，该筛选器必须作为产品或仪表板级别的筛选器存在于 CQD 中。</span><span class="sxs-lookup"><span data-stu-id="96d84-417">To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter.</span></span> <span data-ttu-id="96d84-418">将这些筛选器添加到趋势月份后和 URL 参数之前的 URL：</span><span class="sxs-lookup"><span data-stu-id="96d84-418">Add these filters to the URL after the Trending Month and before the URL parameters:</span></span>

```filter/DATA_MODEL_NAME|VALUE```

<span data-ttu-id="96d84-419">例如，若要应用 Microsoft 团队的产品筛选器值，请添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="96d84-419">For example, to apply a Product filter value of Microsoft Teams, you'd add the following:</span></span>

```filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="96d84-420">整个 URL 将如下所示：</span><span class="sxs-lookup"><span data-stu-id="96d84-420">Your entire URL would look something like this:</span></span>

```https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="96d84-421">若要将 URL 筛选器应用于多选值，请使用管道 ( | 分隔每个值。) 字符。</span><span class="sxs-lookup"><span data-stu-id="96d84-421">To apply URL filters with multi-select values, separate each value with a pipe ( | ) character.</span></span> <span data-ttu-id="96d84-422">例如：</span><span class="sxs-lookup"><span data-stu-id="96d84-422">For example:</span></span>

```filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]```

<span data-ttu-id="96d84-423">如果指定了无效的名称或值，则不会应用 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="96d84-423">If you specify an invalid name or value, the URL filter won't be applied.</span></span>


<span data-ttu-id="96d84-424">可以使用 URL 筛选器筛选特定维度的每个报表。</span><span class="sxs-lookup"><span data-stu-id="96d84-424">You can use a URL filter to filter every report for a specific dimension.</span></span> <span data-ttu-id="96d84-425">最常用的 URL 筛选器用于筛选报表以排除联合参与者遥测，或者仅关注团队或 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="96d84-425">The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business Online.</span></span> <span data-ttu-id="96d84-426">当修正托管建筑物或网络（其中联合终结点可能会影响你的报表）时，从 CQD 报告中排除联合数据将非常有用。</span><span class="sxs-lookup"><span data-stu-id="96d84-426">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

| <span data-ttu-id="96d84-427">筛选器</span><span class="sxs-lookup"><span data-stu-id="96d84-427">Filter</span></span>         | <span data-ttu-id="96d84-428">说明</span><span class="sxs-lookup"><span data-stu-id="96d84-428">Description</span></span>          | <span data-ttu-id="96d84-429">CQD 查询筛选器示例</span><span class="sxs-lookup"><span data-stu-id="96d84-429">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="96d84-430">无空值</span><span class="sxs-lookup"><span data-stu-id="96d84-430">No blank values</span></span>   | <span data-ttu-id="96d84-431">某些筛选器没有用于筛选空值的选项。</span><span class="sxs-lookup"><span data-stu-id="96d84-431">Some filters don't have the option to filter for blank values.</span></span> <span data-ttu-id="96d84-432">若要手动筛选空值，请使用空白表达式，并将筛选器设置为等于或不等于，具体取决于你的需求。</span><span class="sxs-lookup"><span data-stu-id="96d84-432">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="96d84-433">第二建筑物名称 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="96d84-433">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="96d84-434">排除公共子网</span><span class="sxs-lookup"><span data-stu-id="96d84-434">Exclude common subnets</span></span> | <span data-ttu-id="96d84-435">如果没有有效的生成文件以从非托管网络单独托管，则报告中将包含家庭网络。</span><span class="sxs-lookup"><span data-stu-id="96d84-435">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="96d84-436">这些主子网位于其控制范围之外，可以从报表中快速排除。</span><span class="sxs-lookup"><span data-stu-id="96d84-436">These home subnets are outside the scope of IT's control and can be quickly excluded from a report.</span></span> <span data-ttu-id="96d84-437">如本文中所述，常见子网是10.0.0.0、192.168.1.0 和192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="96d84-437">Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="96d84-438">第二子网 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1。0</span><span class="sxs-lookup"><span data-stu-id="96d84-438">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="96d84-439">仅限内部查看</span><span class="sxs-lookup"><span data-stu-id="96d84-439">View inside only</span></span>  | <span data-ttu-id="96d84-440">用于在) 之外的) 或非托管 (内筛选托管 (的报表。</span><span class="sxs-lookup"><span data-stu-id="96d84-440">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="96d84-441">托管 CQD 模板已预配置了这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="96d84-441">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="96d84-442">第二内部公司内部公司 = 内部</span><span class="sxs-lookup"><span data-stu-id="96d84-442">Second Inside Corp = Inside</span></span>        |


#### <a name="how-to-find-your-tenant-id"></a><span data-ttu-id="96d84-443">如何查找你的租户 ID</span><span class="sxs-lookup"><span data-stu-id="96d84-443">How to find your tenant ID</span></span>

<span data-ttu-id="96d84-444">CQD 中的租户 ID 对应于 Azure 中的目录 ID。</span><span class="sxs-lookup"><span data-stu-id="96d84-444">The tenant ID in CQD corresponds to the Directory ID in Azure.</span></span> <span data-ttu-id="96d84-445">如果你不知道你的目录 ID，可以在 Azure 门户中找到它：</span><span class="sxs-lookup"><span data-stu-id="96d84-445">If you don't know your Directory ID, you can find it in the Azure portal:</span></span>

1.  <span data-ttu-id="96d84-446">登录到 Microsoft Azure 门户：<https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="96d84-446">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="96d84-447">选择 " **Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-447">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="96d84-448">在 "**管理**" 下，选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="96d84-448">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="96d84-449">你的租户 ID 位于 "**目录 id** " 框中。</span><span class="sxs-lookup"><span data-stu-id="96d84-449">Your tenant ID is in the **Directory ID** box.</span></span>

<span data-ttu-id="96d84-450">你还可以使用 PowerShell 查找租户 ID：</span><span class="sxs-lookup"><span data-stu-id="96d84-450">You can also find your tenant ID by using PowerShell:</span></span> 
  ```
  Login-AzureRmAccount
  ```



## <a name="comparing-teams-and-skype-for-business-cqd-data"></a><span data-ttu-id="96d84-451">比较团队和 Skype for Business CQD 数据</span><span class="sxs-lookup"><span data-stu-id="96d84-451">Comparing Teams and Skype for Business CQD data</span></span>

<span data-ttu-id="96d84-452">即使在最新的 CQD (cqd.teams.microsoft.com) 中，你也可以看到团队和 Skype for business 之间的数据差异。</span><span class="sxs-lookup"><span data-stu-id="96d84-452">Even within the latest CQD (cqd.teams.microsoft.com), you'll see differences in data between Teams and Skype for Business.</span></span> <span data-ttu-id="96d84-453">原因如下：</span><span class="sxs-lookup"><span data-stu-id="96d84-453">Some reasons:</span></span>
- <span data-ttu-id="96d84-454">确保性能和可靠性的机制的差异</span><span class="sxs-lookup"><span data-stu-id="96d84-454">Differences in the mechanisms for ensuring performance and reliability</span></span>
  - <span data-ttu-id="96d84-455">团队已自动重新连接和快速漫游。</span><span class="sxs-lookup"><span data-stu-id="96d84-455">Teams has auto-reconnect and fast roaming.</span></span> <span data-ttu-id="96d84-456">Skype for Business 不支持。</span><span class="sxs-lookup"><span data-stu-id="96d84-456">Skype for Business doesn't.</span></span>
  - <span data-ttu-id="96d84-457">团队拥有动态带宽管理。</span><span class="sxs-lookup"><span data-stu-id="96d84-457">Teams has dynamic bandwidth management.</span></span> <span data-ttu-id="96d84-458">Skype for Business 不支持。</span><span class="sxs-lookup"><span data-stu-id="96d84-458">Skype for Business doesn't.</span></span>
- <span data-ttu-id="96d84-459">团队和 Skype for business 之间[IP 地址范围](Office-365-URLs-IP-address-ranges.md)的差异。</span><span class="sxs-lookup"><span data-stu-id="96d84-459">Differences in [IP address ranges](Office-365-URLs-IP-address-ranges.md) between Teams and Skype for Business.</span></span> <span data-ttu-id="96d84-460">团队 IP 范围较新，这可能会导致防火墙出现连接问题。</span><span class="sxs-lookup"><span data-stu-id="96d84-460">The Teams IP ranges are newer, which could cause connectivity problems at the firewall.</span></span>

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a><span data-ttu-id="96d84-461">从 Skype for Business 旧版门户打开 CQD</span><span class="sxs-lookup"><span data-stu-id="96d84-461">Open CQD from the Skype for Business legacy portal</span></span>

<span data-ttu-id="96d84-462">![](media/sfb-logo-30x30.png)**使用 skype for business 旧版门户**的 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="96d84-462">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="96d84-463">使用管理员帐户登录到您的 Office 365 组织，然后选择 "**管理员**" 磁贴以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="96d84-463">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="96d84-464">在左窗格中的 "**管理中心**" 下，选择 " **Microsoft 团队**" 以打开 "团队管理中心"。</span><span class="sxs-lookup"><span data-stu-id="96d84-464">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Teams admin center.</span></span>
3. <span data-ttu-id="96d84-465">在 "团队管理中心" 中，选择左窗格中的 "**旧版门户**"，选择 "**工具**"，然后选择 " **Skype for Business Online 呼叫质量" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="96d84-465">In the Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

     ![屏幕截图：选择 "呼叫质量" 仪表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="96d84-467">在打开的页面上，用全局管理员帐户登录，然后在出现提示时提供帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="96d84-467">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="96d84-468">第一次登录后，CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-468">After the first time you sign in, CQD will begin collecting and processing data.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="96d84-469">从2019年12月到，您仍然可以访问 CQD (cqd.lync.com) 的旧版本，尽管旧版门户提供了指向最新 CQD (cqd.teams.microsoft.com) 的链接。</span><span class="sxs-lookup"><span data-stu-id="96d84-469">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="96d84-470">最终，旧版本的 CQD 将会停止。</span><span class="sxs-lookup"><span data-stu-id="96d84-470">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="96d84-471">从2020年7月1日起，较早版本的 CQD 将从新的 CQD (中访问数据 https://CQD.teams.microsoft.com) ，并且不再可以导出生成和报告数据。</span><span class="sxs-lookup"><span data-stu-id="96d84-471">As of July 1, 2020, the older version of CQD accesses data from the new CQD (https://CQD.teams.microsoft.com), and you can no longer export building and report data.</span></span> <span data-ttu-id="96d84-472">在后期2020中，我们将关闭旧的 CQD，您将无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="96d84-472">Sometime in late 2020, we'll turn off the old CQD and you'll no longer be able to access it.</span></span>


## <a name="related-topics"></a><span data-ttu-id="96d84-473">相关主题</span><span class="sxs-lookup"><span data-stu-id="96d84-473">Related topics</span></span>

[<span data-ttu-id="96d84-474">改善和监控团队的通话质量</span><span class="sxs-lookup"><span data-stu-id="96d84-474">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="96d84-475">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="96d84-475">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="96d84-476">设置通话质量仪表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="96d84-476">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="96d84-477">上载租户和生成数据</span><span class="sxs-lookup"><span data-stu-id="96d84-477">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="96d84-478">使用 CQD 管理通话和会议质量</span><span class="sxs-lookup"><span data-stu-id="96d84-478">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="96d84-479">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="96d84-479">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="96d84-480">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="96d84-480">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="96d84-481">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="96d84-481">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
