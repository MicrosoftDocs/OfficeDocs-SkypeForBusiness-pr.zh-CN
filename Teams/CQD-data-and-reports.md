---
title: 'CQD 呼叫质量仪表板 (数据和) '
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
description: 了解 Microsoft 呼叫质量仪表板和 CQD (提供的数据) 。
ms.openlocfilehash: 47fce642bf90b1be9285a11cf19a5e6421aa262b
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212195"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a><span data-ttu-id="a75d4-103">CQD 呼叫质量仪表板 (数据和) </span><span class="sxs-lookup"><span data-stu-id="a75d4-103">Data and reports in Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="a75d4-104">Microsoft 呼叫质量仪表板 (CQD) 使用近实时的 NRT (NRT) 数据源。</span><span class="sxs-lookup"><span data-stu-id="a75d4-104">Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed.</span></span> <span data-ttu-id="a75d4-105">通话记录在通话结束后 30 分钟内在 CQD 中提供。</span><span class="sxs-lookup"><span data-stu-id="a75d4-105">Call records are available in CQD within 30 minutes of the end of a call.</span></span> <span data-ttu-id="a75d4-106">NRT 管道中的呼叫记录仅在从数据集中删除前几个月才可用。</span><span class="sxs-lookup"><span data-stu-id="a75d4-106">Call records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> 


## <a name="many-ways-to-access-cqd-data"></a><span data-ttu-id="a75d4-107">访问 CQD 数据的多种方式</span><span class="sxs-lookup"><span data-stu-id="a75d4-107">Many ways to access CQD data</span></span>

<span data-ttu-id="a75d4-108">可以通过几种不同的途径访问 CQD 数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-108">You can access CQD data by several different avenues.</span></span> <span data-ttu-id="a75d4-109">选择最能满足你需求的一个：</span><span class="sxs-lookup"><span data-stu-id="a75d4-109">Pick the one that best meets your needs:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="a75d4-110">Teams管理中心[ (https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a75d4-110">Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)</span></span>    | <span data-ttu-id="a75d4-111">CQD 数据包含在 Teams管理中心的"用户"页面上，以易于阅读的格式显示所需的最常见数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-111">CQD data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format.</span></span> <span data-ttu-id="a75d4-112">不能自定义在"用户"下找到的 CQD **数据**。</span><span class="sxs-lookup"><span data-stu-id="a75d4-112">You can't customize CQD data that you find under **Users**.</span></span>  |
|<span data-ttu-id="a75d4-113">CQD 门户[ (https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a75d4-113">CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)</span></span>     | <span data-ttu-id="a75d4-114">使用钻取筛选功能，提供满足大多数需求的可靠的摘要和详细报表。</span><span class="sxs-lookup"><span data-stu-id="a75d4-114">Robust summary and detailed reports that meet most needs, with drill-through filtering.</span></span> <span data-ttu-id="a75d4-115">还可以在 CQD 门户中自定义报表。</span><span class="sxs-lookup"><span data-stu-id="a75d4-115">You can also customize reports in the CQD portal.</span></span> <br><br><span data-ttu-id="a75d4-116">获取两 [个 CQD 报表](#import-the-cqd-report-templates) 模板，以帮助在 CQD 门户中分析数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-116">Get two [CQD report templates](#import-the-cqd-report-templates) to help you analyze data in the CQD portal.</span></span>       |
|<span data-ttu-id="a75d4-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="a75d4-117">Power BI</span></span>     | <span data-ttu-id="a75d4-118">使用直接查询通过可自定义的自定义Power BI在 Power BI[中查看 CQD 数据](CQD-Power-BI-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-118">Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](CQD-Power-BI-query-templates.md).</span></span> <span data-ttu-id="a75d4-119">[下载Power BI CQD 的查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-119">[Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span><br><br><span data-ttu-id="a75d4-120">也可使用[REST API 通过数据库访问 CQD](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) Power BI。</span><span class="sxs-lookup"><span data-stu-id="a75d4-120">You can also [use the REST API to access CQD data](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) through Power BI.</span></span> <span data-ttu-id="a75d4-121">如果要下载 CQD 数据以便脱机处理，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="a75d4-121">Use this method if you want to download your CQD data so you can work on it offline.</span></span> <span data-ttu-id="a75d4-122">使用此方法的好处是性能更好，对于联机时陷入Power BI的大型数据集尤其有用。</span><span class="sxs-lookup"><span data-stu-id="a75d4-122">The benefit of using this method is better performance, especially useful for large data sets that bog down in Power BI when you're online.</span></span>       |
|<span data-ttu-id="a75d4-123">Graph API</span><span class="sxs-lookup"><span data-stu-id="a75d4-123">Graph API</span></span>     | <span data-ttu-id="a75d4-124">使用 Graph [API 自己Graph数据](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-124">Access call quality data yourself using the [Graph API](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta).</span></span> <span data-ttu-id="a75d4-125">这是最复杂的方法，但它在分析呼叫质量数据方面提供了最大的控制和灵活性。</span><span class="sxs-lookup"><span data-stu-id="a75d4-125">This is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data.</span></span> <span data-ttu-id="a75d4-126">例如，如果需要将其与组织的其他数据联接，可以使用 Graph API 创建数据模型并合并呼叫质量数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-126">For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data.</span></span>        |

## <a name="import-the-cqd-report-templates"></a><span data-ttu-id="a75d4-127">导入 CQD 报表模板</span><span class="sxs-lookup"><span data-stu-id="a75d4-127">Import the CQD report templates</span></span>

<span data-ttu-id="a75d4-128">从 ["所有网络和](https://aka.ms/qertemplates) 托管网络 (下载两个特) CQD 报表模板，以帮助你快速了解 CQD。</span><span class="sxs-lookup"><span data-stu-id="a75d4-128">Download [two curated CQD report templates](https://aka.ms/qertemplates) (All Networks and Managed Networks) to help you get up to speed quickly with CQD.</span></span> <span data-ttu-id="a75d4-129">"所有网络"模板尽管经过优化，可用于处理建筑物数据文件，但可在收集建筑物信息并将其上传到 CQD 时使用，如下一部分所述。</span><span class="sxs-lookup"><span data-stu-id="a75d4-129">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="a75d4-130">**若要导入模板， (。CQDX) into CQD**</span><span class="sxs-lookup"><span data-stu-id="a75d4-130">**To import the templates (.CQDX) into CQD**</span></span>

1. <span data-ttu-id="a75d4-131">在 CQD 中 **，从** 页面顶部的菜单中选择"详细报告"。</span><span class="sxs-lookup"><span data-stu-id="a75d4-131">In CQD, select **Detailed Reports** from the menu at the top of the page.</span></span>

2. <span data-ttu-id="a75d4-132">在左侧面板中，选择"导入 **"。**</span><span class="sxs-lookup"><span data-stu-id="a75d4-132">In the left panel, select **Import**.</span></span> <span data-ttu-id="a75d4-133">浏览到第一个 CQDX 模板，然后选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="a75d4-133">Browse to the first CQDX template and select **Open**.</span></span>

3. <span data-ttu-id="a75d4-134">上传模板后，弹出窗口将显示消息"报告导入成功"。</span><span class="sxs-lookup"><span data-stu-id="a75d4-134">After the template is uploaded, a pop-up window will display the message "Report import was successful."</span></span> 

4. <span data-ttu-id="a75d4-135">为第二个 CQD 模板重复步骤 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="a75d4-135">Repeat steps 2 and 3 for the second CQD template.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a75d4-136">每个用户必须将 CQD 模板导入其 CQD 实例。</span><span class="sxs-lookup"><span data-stu-id="a75d4-136">Each user must import the CQD templates into their CQD instance.</span></span> 



## <a name="euii-data"></a><span data-ttu-id="a75d4-137">EUII 数据</span><span class="sxs-lookup"><span data-stu-id="a75d4-137">EUII data</span></span>

<span data-ttu-id="a75d4-138">出于合规性原因，EUII (标识) 数据 (也称为个人身份信息或 PII) 仅保留 28 天。</span><span class="sxs-lookup"><span data-stu-id="a75d4-138">For compliance reasons, end-user identifiable information (EUII) data (also known as personally-identifiable information or PII) is only kept for 28 days.</span></span> <span data-ttu-id="a75d4-139">当 NRT 数据超过 28 天标记时，将清除包含 EUII 的字段，从而生成无 EUII 的 NRT 数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-139">As NRT data crosses the 28-day mark, fields that contain EUII are cleared, resulting in EUII-free NRT data.</span></span> <span data-ttu-id="a75d4-140">包含 EUII 数据的字段为：</span><span class="sxs-lookup"><span data-stu-id="a75d4-140">Fields that contain EUII data are:</span></span>

- <span data-ttu-id="a75d4-141">完整的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="a75d4-141">Full IP address</span></span>
- <span data-ttu-id="a75d4-142">MAC 媒体访问控制 (MAC) 地址</span><span class="sxs-lookup"><span data-stu-id="a75d4-142">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="a75d4-143">基本服务集标识符 (BSSID) </span><span class="sxs-lookup"><span data-stu-id="a75d4-143">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="a75d4-144">会话启动协议 (SIP) URI (Skype for Business仅) </span><span class="sxs-lookup"><span data-stu-id="a75d4-144">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="a75d4-145">用户主体名称 (UPN)</span><span class="sxs-lookup"><span data-stu-id="a75d4-145">User Principal Name (UPN)</span></span>
- <span data-ttu-id="a75d4-146">计算机终结点名称</span><span class="sxs-lookup"><span data-stu-id="a75d4-146">Machine Endpoint Name</span></span>
- <span data-ttu-id="a75d4-147">用户详细反馈</span><span class="sxs-lookup"><span data-stu-id="a75d4-147">User Verbatim Feedback</span></span>
- <span data-ttu-id="a75d4-148">对象 ID (终结点用户帐户的 Active Directory 对象 ID) </span><span class="sxs-lookup"><span data-stu-id="a75d4-148">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="admin-roles-with-and-without-euii-access"></a><span data-ttu-id="a75d4-149">具有和没有 EUII 访问权限的管理员角色</span><span class="sxs-lookup"><span data-stu-id="a75d4-149">Admin roles with and without EUII access</span></span>

<span data-ttu-id="a75d4-150">这些 [RBAC](/azure/role-based-access-control/overview) 角色 **具有** EUII 访问权限：</span><span class="sxs-lookup"><span data-stu-id="a75d4-150">These [RBAC](/azure/role-based-access-control/overview) roles **DO** have EUII access:</span></span>
- <span data-ttu-id="a75d4-151">全局管理员</span><span class="sxs-lookup"><span data-stu-id="a75d4-151">Global Admin</span></span>
- <span data-ttu-id="a75d4-152">Teams服务管理员</span><span class="sxs-lookup"><span data-stu-id="a75d4-152">Teams Service Admin</span></span>
- <span data-ttu-id="a75d4-153">Teams通信管理员</span><span class="sxs-lookup"><span data-stu-id="a75d4-153">Teams Communications Admin</span></span>
- <span data-ttu-id="a75d4-154">Teams 通信支持工程师</span><span class="sxs-lookup"><span data-stu-id="a75d4-154">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="a75d4-155">全局阅读器</span><span class="sxs-lookup"><span data-stu-id="a75d4-155">Global Reader</span></span>
- <span data-ttu-id="a75d4-156">Skype for Business管理员</span><span class="sxs-lookup"><span data-stu-id="a75d4-156">Skype for Business Admin</span></span>

<span data-ttu-id="a75d4-157">这些 RBAC **角色没有** EUII 访问权限：</span><span class="sxs-lookup"><span data-stu-id="a75d4-157">These RBAC roles **DON'T** have EUII access:</span></span>
- <span data-ttu-id="a75d4-158">报表读者</span><span class="sxs-lookup"><span data-stu-id="a75d4-158">Reports Reader</span></span>
- <span data-ttu-id="a75d4-159">Teams通信支持专家</span><span class="sxs-lookup"><span data-stu-id="a75d4-159">Teams Communications Support Specialist</span></span>


## <a name="date-controls"></a><span data-ttu-id="a75d4-160">日期控件</span><span class="sxs-lookup"><span data-stu-id="a75d4-160">Date controls</span></span>

<span data-ttu-id="a75d4-161">CQD 支持以下滚动趋势类型：</span><span class="sxs-lookup"><span data-stu-id="a75d4-161">CQD supports the following Rolling Trend types:</span></span>

- <span data-ttu-id="a75d4-162">5 天</span><span class="sxs-lookup"><span data-stu-id="a75d4-162">5-day</span></span>
- <span data-ttu-id="a75d4-163">7 天</span><span class="sxs-lookup"><span data-stu-id="a75d4-163">7-day</span></span>
- <span data-ttu-id="a75d4-164">30 天</span><span class="sxs-lookup"><span data-stu-id="a75d4-164">30-day</span></span>
- <span data-ttu-id="a75d4-165">60 天</span><span class="sxs-lookup"><span data-stu-id="a75d4-165">60-day</span></span>
- <span data-ttu-id="a75d4-166">90 天</span><span class="sxs-lookup"><span data-stu-id="a75d4-166">90-day</span></span>

<span data-ttu-id="a75d4-167">URL Date 参数接受"天"字段。</span><span class="sxs-lookup"><span data-stu-id="a75d4-167">The URL Date parameter accepts a Day field.</span></span> <span data-ttu-id="a75d4-168">滚动日期报表使用以 YYYY-MM-DD 格式指定的日期作为趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="a75d4-168">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span> <span data-ttu-id="a75d4-169">URL Date 参数"00"指示"today"。</span><span class="sxs-lookup"><span data-stu-id="a75d4-169">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="a75d4-170">URL</span><span class="sxs-lookup"><span data-stu-id="a75d4-170">URL</span></span>| <span data-ttu-id="a75d4-171">滚动日期趋势的结束日期</span><span class="sxs-lookup"><span data-stu-id="a75d4-171">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="a75d4-172"><span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="a75d4-172"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="a75d4-173">2019 年 2 月的当前日</span><span class="sxs-lookup"><span data-stu-id="a75d4-173">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="a75d4-174"><span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="a75d4-174"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="a75d4-175">2019 年 2 月 15 日</span><span class="sxs-lookup"><span data-stu-id="a75d4-175">Feb 15, 2019</span></span>|
|<span data-ttu-id="a75d4-176"><span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span></span><span class="sxs-lookup"><span data-stu-id="a75d4-176"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="a75d4-177">当天</span><span class="sxs-lookup"><span data-stu-id="a75d4-177">Current Day</span></span>|
|||

<span data-ttu-id="a75d4-178">默认情况下，当月的当前天用作滚动日趋势的最后一天。</span><span class="sxs-lookup"><span data-stu-id="a75d4-178">By default, the current day of the month is used as the last day of the Rolling Day Trend.</span></span>


## <a name="data-available-in-cqd-reports"></a><span data-ttu-id="a75d4-179">CQD 报告中提供的数据</span><span class="sxs-lookup"><span data-stu-id="a75d4-179">Data available in CQD reports</span></span>

<span data-ttu-id="a75d4-180">管理组织通话质量时，可能需要使用默认摘要和详细的 CQD 报告。如果需要，可以 [创建自定义报表](#create-custom-detailed-reports)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-180">The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can [create custom reports](#create-custom-detailed-reports).</span></span> 

<span data-ttu-id="a75d4-181">如果要使用 Power BI分析 CQD 数据，请阅读使用 Power BI 分析[CQD 数据Teams。](CQD-Power-BI-query-templates.md)</span><span class="sxs-lookup"><span data-stu-id="a75d4-181">If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md).</span></span>

|<span data-ttu-id="a75d4-182">功能</span><span class="sxs-lookup"><span data-stu-id="a75d4-182">Feature</span></span>|<span data-ttu-id="a75d4-183">摘要报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-183">Summary Reports</span></span>|<span data-ttu-id="a75d4-184">详细报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-184">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="a75d4-185">应用程序共享指标</span><span class="sxs-lookup"><span data-stu-id="a75d4-185">Application sharing metric</span></span> | <span data-ttu-id="a75d4-186">否</span><span class="sxs-lookup"><span data-stu-id="a75d4-186">No</span></span> | <span data-ttu-id="a75d4-187">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-187">Yes</span></span> |
|<span data-ttu-id="a75d4-188">客户构建信息支持</span><span class="sxs-lookup"><span data-stu-id="a75d4-188">Customer building information support</span></span> | <span data-ttu-id="a75d4-189">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-189">Yes</span></span> | <span data-ttu-id="a75d4-190">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-190">Yes</span></span> |
|<span data-ttu-id="a75d4-191">客户终结点信息支持</span><span class="sxs-lookup"><span data-stu-id="a75d4-191">Customer endpoint information support</span></span> | <span data-ttu-id="a75d4-192">仅在 <span> cqd.teams.microsoft.com<span/></span><span class="sxs-lookup"><span data-stu-id="a75d4-192">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="a75d4-193">仅在 <span> cqd.teams.microsoft.com<span/></span><span class="sxs-lookup"><span data-stu-id="a75d4-193">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="a75d4-194">向下钻取分析支持</span><span class="sxs-lookup"><span data-stu-id="a75d4-194">Drill down analysis support</span></span>   | <span data-ttu-id="a75d4-195">否</span><span class="sxs-lookup"><span data-stu-id="a75d4-195">No</span></span>   | <span data-ttu-id="a75d4-196">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-196">Yes</span></span>   |
|<span data-ttu-id="a75d4-197">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="a75d4-197">Media reliability metrics</span></span>   | <span data-ttu-id="a75d4-198">否</span><span class="sxs-lookup"><span data-stu-id="a75d4-198">No</span></span>   | <span data-ttu-id="a75d4-199">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-199">Yes</span></span>   |
|<span data-ttu-id="a75d4-200">开箱后报表</span><span class="sxs-lookup"><span data-stu-id="a75d4-200">Out-of-the-box reports</span></span>   | <span data-ttu-id="a75d4-201">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-201">Yes</span></span>   | <span data-ttu-id="a75d4-202">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-202">Yes</span></span>   |
|<span data-ttu-id="a75d4-203">概述报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-203">Overview reports</span></span>   | <span data-ttu-id="a75d4-204">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-204">Yes</span></span>   | <span data-ttu-id="a75d4-205">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-205">Yes</span></span>   |
|<span data-ttu-id="a75d4-206">每用户报表集</span><span class="sxs-lookup"><span data-stu-id="a75d4-206">Per-user report set</span></span>   | <span data-ttu-id="a75d4-207">否</span><span class="sxs-lookup"><span data-stu-id="a75d4-207">No</span></span>   | <span data-ttu-id="a75d4-208">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-208">Yes</span></span>   |
|<span data-ttu-id="a75d4-209">报表集自定义 (添加、删除、修改报表) </span><span class="sxs-lookup"><span data-stu-id="a75d4-209">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="a75d4-210">否</span><span class="sxs-lookup"><span data-stu-id="a75d4-210">No</span></span>   | <span data-ttu-id="a75d4-211">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-211">Yes</span></span>   |
|<span data-ttu-id="a75d4-212">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="a75d4-212">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="a75d4-213">否</span><span class="sxs-lookup"><span data-stu-id="a75d4-213">No</span></span>   | <span data-ttu-id="a75d4-214">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-214">Yes</span></span>   |
|<span data-ttu-id="a75d4-215">视频指标</span><span class="sxs-lookup"><span data-stu-id="a75d4-215">Video metrics</span></span>   | <span data-ttu-id="a75d4-216">否</span><span class="sxs-lookup"><span data-stu-id="a75d4-216">No</span></span>   | <span data-ttu-id="a75d4-217">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-217">Yes</span></span>   |
|<span data-ttu-id="a75d4-218">可用数据量</span><span class="sxs-lookup"><span data-stu-id="a75d4-218">Amount of data available</span></span>   | <span data-ttu-id="a75d4-219">过去 12 个月</span><span class="sxs-lookup"><span data-stu-id="a75d4-219">Last 12 months</span></span>   | <span data-ttu-id="a75d4-220">过去 12 个月</span><span class="sxs-lookup"><span data-stu-id="a75d4-220">Last 12 months</span></span>   |
|<span data-ttu-id="a75d4-221">Microsoft Teams数据</span><span class="sxs-lookup"><span data-stu-id="a75d4-221">Microsoft Teams data</span></span>   | <span data-ttu-id="a75d4-222">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-222">Yes</span></span>   | <span data-ttu-id="a75d4-223">是</span><span class="sxs-lookup"><span data-stu-id="a75d4-223">Yes</span></span>   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a><span data-ttu-id="a75d4-224">选择要在报告中查看的产品数据</span><span class="sxs-lookup"><span data-stu-id="a75d4-224">Select product data to see in reports</span></span>

<span data-ttu-id="a75d4-225">在"摘要Location-Enhanced报表"中，可以使用"产品筛选器"下拉列表显示所有产品数据、仅显示Microsoft Teams数据，或仅Skype for Business联机数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-225">In the Summary and Location-Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a75d4-226">![屏幕截图：显示产品筛选器控件选项](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)</span><span class="sxs-lookup"><span data-stu-id="a75d4-226">![Screenshot: shows the Product Filter control options](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)</span></span>
  
<span data-ttu-id="a75d4-227">在"详细报表"中，可以使用"Is **Teams"** 维度筛选数据以Microsoft Teams或Skype for Business Online 数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-227">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>

## <a name="summary-reports"></a><span data-ttu-id="a75d4-228">摘要报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-228">Summary Reports</span></span>

<span data-ttu-id="a75d4-229">这些报表是首次登录到 CQD 时在 CQD 仪表板上看到的报表。</span><span class="sxs-lookup"><span data-stu-id="a75d4-229">These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD.</span></span> <span data-ttu-id="a75d4-230">它们提供每日、每月和表报表的质量趋势概览，以帮助识别质量不佳的子网。</span><span class="sxs-lookup"><span data-stu-id="a75d4-230">They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.</span></span> 

| <span data-ttu-id="a75d4-231">Tab</span><span class="sxs-lookup"><span data-stu-id="a75d4-231">Tab</span></span> | <span data-ttu-id="a75d4-232">说明</span><span class="sxs-lookup"><span data-stu-id="a75d4-232">Description</span></span> |
|---------|---------|
|<span data-ttu-id="a75d4-233">总体呼叫质量</span><span class="sxs-lookup"><span data-stu-id="a75d4-233">Overall Call Quality</span></span>     | <span data-ttu-id="a75d4-234">其他 3 个选项卡的聚合。</span><span class="sxs-lookup"><span data-stu-id="a75d4-234">Aggregate of the other 3 tabs.</span></span>       |
|<span data-ttu-id="a75d4-235">服务器 - 客户端</span><span class="sxs-lookup"><span data-stu-id="a75d4-235">Server—Client</span></span>     |<span data-ttu-id="a75d4-236">服务器和客户端终结点之间的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a75d4-236">Details of the streams between server and client endpoints.</span></span>        |
|<span data-ttu-id="a75d4-237">客户端 - 客户端</span><span class="sxs-lookup"><span data-stu-id="a75d4-237">Client—Client</span></span>     |<span data-ttu-id="a75d4-238">两个客户端终结点之间的流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a75d4-238">Details of the streams between two client endpoints.</span></span>        |
|<span data-ttu-id="a75d4-239">语音质量 SLA</span><span class="sxs-lookup"><span data-stu-id="a75d4-239">Voice Quality SLA</span></span>     |<span data-ttu-id="a75d4-240">有关语音质量 SLA Skype for Business呼叫[的信息](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-240">Info about calls included in the Skype for Business voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>        |

### <a name="overall-call-quality-tab"></a><span data-ttu-id="a75d4-241">"总体呼叫质量"选项卡</span><span class="sxs-lookup"><span data-stu-id="a75d4-241">Overall Call Quality tab</span></span>

<span data-ttu-id="a75d4-242">使用此选项卡上的数据，根据流计数和较差百分比评估呼叫质量状态和趋势。</span><span class="sxs-lookup"><span data-stu-id="a75d4-242">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="a75d4-243">右上角的图例显示哪些颜色和可视元素表示这些指标。</span><span class="sxs-lookup"><span data-stu-id="a75d4-243">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a75d4-244">![屏幕截图：显示"呼叫质量"选项卡](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)</span><span class="sxs-lookup"><span data-stu-id="a75d4-244">![Screenshot: show the Call Quality tab](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)</span></span>
  
<span data-ttu-id="a75d4-245">流分为三组：良好、较差和未分类。</span><span class="sxs-lookup"><span data-stu-id="a75d4-245">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="a75d4-246">此外，还有计算  *得出的 Poor %*  值，这些值提供分类为 *"*  差"的流与已分类流总数的比率。</span><span class="sxs-lookup"><span data-stu-id="a75d4-246">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="a75d4-247">由于 Poor % = 差流/ (差流+) \*\* 100，\**因此 Poor %* 不受存在多个未 *分类* 流的影响。</span><span class="sxs-lookup"><span data-stu-id="a75d4-247">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="a75d4-248">若要了解将流分类为差或好什么，请参阅呼叫 [质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-248">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="a75d4-249">使用左侧的刻度测量流计数值。</span><span class="sxs-lookup"><span data-stu-id="a75d4-249">Use the scale on the left to measure the stream count values.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a75d4-250">![屏幕截图：显示流计数值](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)</span><span class="sxs-lookup"><span data-stu-id="a75d4-250">![Screenshot: shows stream count values](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)</span></span>
  
<span data-ttu-id="a75d4-251">使用右侧比例度量差 % 值。</span><span class="sxs-lookup"><span data-stu-id="a75d4-251">Use the scale on the right to measure the Poor % values.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a75d4-252">![屏幕截图：显示较差的 % 值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)</span><span class="sxs-lookup"><span data-stu-id="a75d4-252">![Screenshot: shows poor % values](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)</span></span>
  
<span data-ttu-id="a75d4-253">通过将鼠标悬停在条形图上，还可以获取实际数值。</span><span class="sxs-lookup"><span data-stu-id="a75d4-253">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a75d4-254">以下示例来自非常小的样本数据集，实际部署不现实值。</span><span class="sxs-lookup"><span data-stu-id="a75d4-254">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a75d4-255">![屏幕截图：显示用于访问数据的鼠标](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)</span><span class="sxs-lookup"><span data-stu-id="a75d4-255">![Screenshot: shows mouse used to access data](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)</span></span>
  
<span data-ttu-id="a75d4-256">总体流音量有助于确定计算较差百分比的相关性。</span><span class="sxs-lookup"><span data-stu-id="a75d4-256">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="a75d4-257">总体流的数量越小，报告的较差百分比值越不可靠。</span><span class="sxs-lookup"><span data-stu-id="a75d4-257">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="a75d4-258">Server-Client选项卡和Client-Client选项卡</span><span class="sxs-lookup"><span data-stu-id="a75d4-258">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="a75d4-259">这两个选项卡提供其终结点到终结点方案中发生流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a75d4-259">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="a75d4-260">"Server-Client"选项卡包含四个可折叠的节，这些部分表示媒体流将在其中流动的四种方案。</span><span class="sxs-lookup"><span data-stu-id="a75d4-260">The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="a75d4-261">内部有线</span><span class="sxs-lookup"><span data-stu-id="a75d4-261">Wired Inside</span></span>
- <span data-ttu-id="a75d4-262">外部有线</span><span class="sxs-lookup"><span data-stu-id="a75d4-262">Wired Outside</span></span>
- <span data-ttu-id="a75d4-263">WiFi 内部</span><span class="sxs-lookup"><span data-stu-id="a75d4-263">WiFi Inside</span></span>
- <span data-ttu-id="a75d4-264">外部 WiFi</span><span class="sxs-lookup"><span data-stu-id="a75d4-264">WiFi Outside</span></span>

<span data-ttu-id="a75d4-265">同样，"Client-Client选项卡包含五个可折叠部分：</span><span class="sxs-lookup"><span data-stu-id="a75d4-265">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="a75d4-266">内部有线 - 内部有线</span><span class="sxs-lookup"><span data-stu-id="a75d4-266">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="a75d4-267">内部有线 - 外部有线</span><span class="sxs-lookup"><span data-stu-id="a75d4-267">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="a75d4-268">在外部有线 - 在外部有线</span><span class="sxs-lookup"><span data-stu-id="a75d4-268">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="a75d4-269">在内部有线 - WiFi 内部</span><span class="sxs-lookup"><span data-stu-id="a75d4-269">Wired Inside — WiFi Inside</span></span>
- <span data-ttu-id="a75d4-270">内部有线 - 外部 WiFi</span><span class="sxs-lookup"><span data-stu-id="a75d4-270">Wired Inside — WiFi Outside</span></span>

#### <a name="inside-versus-outside"></a><span data-ttu-id="a75d4-271">内部与外部</span><span class="sxs-lookup"><span data-stu-id="a75d4-271">Inside versus Outside</span></span>

<span data-ttu-id="a75d4-272">CQD 使用建筑物信息将流分类为"内部"或"外部"（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="a75d4-272">CQD classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="a75d4-273">每个流的终结点与子网地址相关联。</span><span class="sxs-lookup"><span data-stu-id="a75d4-273">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="a75d4-274">如果子网位于上传的建筑物信息中标记为 InsideCorp 的子网列表中，则它被视为"内部 *"。*</span><span class="sxs-lookup"><span data-stu-id="a75d4-274">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="a75d4-275">如果尚未上传生成信息，则"内部测试"始终将流分类为"外部 *"。*</span><span class="sxs-lookup"><span data-stu-id="a75d4-275">If Building information has not yet been uploaded, then Inside Test always classifies the streams as *Outside*.</span></span> 

<span data-ttu-id="a75d4-276">客户端终结点方案的Server-Client测试仅考虑客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="a75d4-276">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="a75d4-277">由于从用户的角度来看，服务器始终位于外部，因此在测试中未考虑到这一点。</span><span class="sxs-lookup"><span data-stu-id="a75d4-277">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-versus-wifi"></a><span data-ttu-id="a75d4-278">有线与 WiFi</span><span class="sxs-lookup"><span data-stu-id="a75d4-278">Wired versus WiFi</span></span>

<span data-ttu-id="a75d4-279">如名称所指示，分类条件基于客户端连接的类型。</span><span class="sxs-lookup"><span data-stu-id="a75d4-279">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="a75d4-280">服务器始终是有线的，并且计算中不包括服务器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-280">Server is always wired and it isn't included in the calculation.</span></span> <span data-ttu-id="a75d4-281">在给定的流中，如果两个终结点之一连接到 WiFi 网络，则 CQD 会分类为 WiFi。</span><span class="sxs-lookup"><span data-stu-id="a75d4-281">In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.</span></span>

> [!NOTE]
> <span data-ttu-id="a75d4-282">给定流后，如果两个终结点之一连接到 WiFi 网络，则它在 CQD 中归类为 WiFi。</span><span class="sxs-lookup"><span data-stu-id="a75d4-282">Given a stream, if one of the two endpoints is connected to a WiFi network, then it is classified as WiFi in CQD.</span></span>
  
  
## <a name="tenant-data-information"></a><span data-ttu-id="a75d4-283">租户数据信息</span><span class="sxs-lookup"><span data-stu-id="a75d4-283">Tenant Data information</span></span>

<span data-ttu-id="a75d4-284">CQD 摘要报表仪表板包括一个租户Upload页，通过从右上角的设置菜单中选择"租户数据"Upload访问该页面。</span><span class="sxs-lookup"><span data-stu-id="a75d4-284">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="a75d4-285">此页用于管理员上传其自己的信息，例如：</span><span class="sxs-lookup"><span data-stu-id="a75d4-285">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="a75d4-286">IP 地址和地理信息的地图。</span><span class="sxs-lookup"><span data-stu-id="a75d4-286">A map of IP address and geographical information.</span></span>
- <span data-ttu-id="a75d4-287">每个无线 AP 及其 MAC 地址的地图。</span><span class="sxs-lookup"><span data-stu-id="a75d4-287">A map of each wireless AP and its MAC address.</span></span>
- <span data-ttu-id="a75d4-288">终结点到终结点制造/模型/类型等的地图。</span><span class="sxs-lookup"><span data-stu-id="a75d4-288">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
<span data-ttu-id="a75d4-289">建议上传租户、建筑物和位置数据，以便 CQD 可以在报告中包含此信息。</span><span class="sxs-lookup"><span data-stu-id="a75d4-289">We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports.</span></span> <span data-ttu-id="a75d4-290">如果尚未上传此数据，请阅读Upload[和建筑物数据](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-290">If you haven't already uploaded this data, read [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span> 


## <a name="detailed-reports"></a><span data-ttu-id="a75d4-291">详细报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-291">Detailed reports</span></span>

| <span data-ttu-id="a75d4-292">名称</span><span class="sxs-lookup"><span data-stu-id="a75d4-292">Name</span></span> | <span data-ttu-id="a75d4-293">描述</span><span class="sxs-lookup"><span data-stu-id="a75d4-293">Description</span></span> |
|---------|---------|
|<span data-ttu-id="a75d4-294">Location-Enhanced报表</span><span class="sxs-lookup"><span data-stu-id="a75d4-294">Location-Enhanced Reports</span></span>     |<span data-ttu-id="a75d4-295">显示基于位置信息的质量趋势。</span><span class="sxs-lookup"><span data-stu-id="a75d4-295">Shows quality trends based on location information.</span></span> <span data-ttu-id="a75d4-296">此报告仅在上传租户 [数据 时显示](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-296">This report appears only if you've [uploaded your tenant data](CQD-upload-tenant-building-data.md).</span></span>        |
|<span data-ttu-id="a75d4-297">可靠性报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-297">Reliability Reports</span></span>     |<span data-ttu-id="a75d4-298">包括音频、视频、基于视频的屏幕共享 (VBSS) 以及应用共享报告。</span><span class="sxs-lookup"><span data-stu-id="a75d4-298">Includes audio, video, video-based screen sharing (VBSS), and app sharing reports.</span></span>        |
|<span data-ttu-id="a75d4-299">体验质量报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-299">Quality of Experience Reports</span></span>     |<span data-ttu-id="a75d4-300">所有客户端和设备（包括会议室）的音频质量和可靠性。</span><span class="sxs-lookup"><span data-stu-id="a75d4-300">Audio quality and reliability for all clients and devices, including meeting rooms.</span></span> <span data-ttu-id="a75d4-301">这些报告是可下载 [CQD](https://aka.ms/QERtemplates)模板的"精简"版本，侧重于分析音频质量和可靠性的关键问题。</span><span class="sxs-lookup"><span data-stu-id="a75d4-301">These reports are a “slimmed-down” version of the downloadable [CQD templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability.</span></span>         |
|<span data-ttu-id="a75d4-302">质量向下钻取报表</span><span class="sxs-lookup"><span data-stu-id="a75d4-302">Quality Drill Down Reports</span></span>     | <span data-ttu-id="a75d4-303">向下钻取：按区域、位置、子网、小时和用户划分的日期。</span><span class="sxs-lookup"><span data-stu-id="a75d4-303">Drill downs: Date by region, locations, subnets, hour, and users.</span></span>        |
|<span data-ttu-id="a75d4-304">故障向下钻取报表</span><span class="sxs-lookup"><span data-stu-id="a75d4-304">Failure Drill Down Reports</span></span>     | <span data-ttu-id="a75d4-305">向下钻取：按区域、位置、子网、小时和用户划分的日期。</span><span class="sxs-lookup"><span data-stu-id="a75d4-305">Drill downs: Date by region, locations, subnets, hour, and users.</span></span>        |
|<span data-ttu-id="a75d4-306">评价我的通话报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-306">Rate My Call Reports</span></span>     |<span data-ttu-id="a75d4-307">按区域、位置或用户分析用户通话分级。</span><span class="sxs-lookup"><span data-stu-id="a75d4-307">Analyze user call ratings by region, location, or by user.</span></span> <span data-ttu-id="a75d4-308">包括逐字反馈。</span><span class="sxs-lookup"><span data-stu-id="a75d4-308">Includes verbatim feedback.</span></span>         |
|<span data-ttu-id="a75d4-309">技术支持报表</span><span class="sxs-lookup"><span data-stu-id="a75d4-309">Help Desk Reports</span></span>     |<span data-ttu-id="a75d4-310">技术支持报告查看单个用户、用户组或所有人的呼叫和会议数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-310">Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone.</span></span> <span data-ttu-id="a75d4-311">这些报告合并了建筑物和 EUII 数据，可帮助根据网络位置、会议详细信息、设备或固件确定可能的系统问题。</span><span class="sxs-lookup"><span data-stu-id="a75d4-311">Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware.</span></span>         |
|<span data-ttu-id="a75d4-312">客户端版本报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-312">Client Version Reports</span></span>     |<span data-ttu-id="a75d4-313">客户端版本摘要：查看每个客户端应用版本的会话和用户计数</span><span class="sxs-lookup"><span data-stu-id="a75d4-313">Client Version Summary: View the Sessions and Users counts for each client app version</span></span><br><br><span data-ttu-id="a75d4-314">按用户表示的客户端版本：查看每个客户端应用版本的用户名</span><span class="sxs-lookup"><span data-stu-id="a75d4-314">Client Version by User: View user names for each client app version</span></span> <br><br><span data-ttu-id="a75d4-315">针对"产品"和"客户端类型"预构建的筛选器可帮助将版本侧重于特定客户端。</span><span class="sxs-lookup"><span data-stu-id="a75d4-315">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>         |
|<span data-ttu-id="a75d4-316">终结点报告</span><span class="sxs-lookup"><span data-stu-id="a75d4-316">Endpoint Reports</span></span>     |<span data-ttu-id="a75d4-317">按计算机终结点显示呼叫质量 (计算机制造商和型号) 。</span><span class="sxs-lookup"><span data-stu-id="a75d4-317">Shows call quality by machine endpoints (computer make and model).</span></span> <span data-ttu-id="a75d4-318">这些报表包括建筑物数据（如果已上传）。</span><span class="sxs-lookup"><span data-stu-id="a75d4-318">These reports include building data, if you've uploaded it.</span></span>         |


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="a75d4-319">创建自定义详细报表</span><span class="sxs-lookup"><span data-stu-id="a75d4-319">Create custom detailed reports</span></span>

<span data-ttu-id="a75d4-320">如果默认 CQD 报表不能满足需求，请使用这些说明创建自定义报表。</span><span class="sxs-lookup"><span data-stu-id="a75d4-320">If the default CQD reports don't meet your needs, use these instructions to create a custom report.</span></span> <span data-ttu-id="a75d4-321">或者 (2020 年 1 月) [对 CQD Power BI使用资源](cqd-power-bi-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-321">Or (as of January 2020) [Use Power BI for CQD reports ](cqd-power-bi-query-templates.md)instead.</span></span>

<span data-ttu-id="a75d4-322">从在登录时显示的屏幕顶部的报表的下拉列表中，选择"摘要报表 \( "屏幕，选择"详细报表"，然后选择 \) "**新建"。** </span><span class="sxs-lookup"><span data-stu-id="a75d4-322">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New**.</span></span> <span data-ttu-id="a75d4-323">单击 **报告中** 的"编辑"，查看查询编辑器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-323">Click **Edit** in a report to see the Query Editor.</span></span> <span data-ttu-id="a75d4-324">每个报告都可以通过对多维数据集进行查询得到。</span><span class="sxs-lookup"><span data-stu-id="a75d4-324">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="a75d4-325">报告是其查询返回的数据的可视化形式。</span><span class="sxs-lookup"><span data-stu-id="a75d4-325">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="a75d4-326">查询编辑器可帮助编辑这些查询和报表的显示选项。</span><span class="sxs-lookup"><span data-stu-id="a75d4-326">The Query Editor helps you edit these queries and the display options of the report.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a75d4-327">网络范围可用于表示具有单个路由前缀的 (子网的超网络) 。</span><span class="sxs-lookup"><span data-stu-id="a75d4-327">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="a75d4-328">所有新建筑物上载都将检查是否有重叠的范围。</span><span class="sxs-lookup"><span data-stu-id="a75d4-328">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="a75d4-329">如果以前上传过一个建筑物文件，应下载当前文件，然后重新上传该文件，以确定任何重叠，并修复问题，然后再重新上传。</span><span class="sxs-lookup"><span data-stu-id="a75d4-329">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="a75d4-330">以前上传的文件的任何重叠都可能导致报告中子网与建筑物之间的映射错误。</span><span class="sxs-lookup"><span data-stu-id="a75d4-330">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="a75d4-331">某些 VPN 实现无法准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="a75d4-331">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="a75d4-332">建议在将 VPN 子网添加到生成文件时，不要为子网添加一个条目，而是将 VPN 子网中每个地址的单独条目添加为单独的 32 位网络。</span><span class="sxs-lookup"><span data-stu-id="a75d4-332">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="a75d4-333">每行可以具有相同的建筑物元数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-333">Each row can have the same building metadata.</span></span> <span data-ttu-id="a75d4-334">例如，对于 172.16.18.0/24，应该有 256 行，每个地址各有一行，介于 172.16.18.0/32 和 172.16.18.255/32 之间（含）。</span><span class="sxs-lookup"><span data-stu-id="a75d4-334">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="a75d4-335">VPN 列是可选的，默认为 0。</span><span class="sxs-lookup"><span data-stu-id="a75d4-335">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="a75d4-336">如果 VPN 列的值设置为 1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a75d4-336">If the VPN column's value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="a75d4-337">请尽量少用，仅对 VPN 子网使用，因为完全扩展这些子网会对涉及生成数据的查询的查询时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="a75d4-337">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

<span data-ttu-id="a75d4-338">指向报告中的条形图和趋势线以显示详细值。</span><span class="sxs-lookup"><span data-stu-id="a75d4-338">Point to bar charts and trend lines in the report to display detailed values.</span></span> <span data-ttu-id="a75d4-339">具有焦点的报表将显示操作菜单："编辑、克隆、**删除**、**下载** 和 **导出报表树"。**</span><span class="sxs-lookup"><span data-stu-id="a75d4-339">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>



## <a name="query-filters"></a><span data-ttu-id="a75d4-340">查询筛选器</span><span class="sxs-lookup"><span data-stu-id="a75d4-340">Query filters</span></span>

<span data-ttu-id="a75d4-341">查询筛选器是使用 CQD 中的查询编辑器实现的。</span><span class="sxs-lookup"><span data-stu-id="a75d4-341">Query filters are implemented by using the Query Editor in CQD.</span></span> <span data-ttu-id="a75d4-342">这些筛选器用于减少 CQD 返回的记录数，从而最大程度地减少报表的总体大小和查询时间。</span><span class="sxs-lookup"><span data-stu-id="a75d4-342">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size and query times.</span></span> <span data-ttu-id="a75d4-343">这尤其适用于筛选出非托管网络。</span><span class="sxs-lookup"><span data-stu-id="a75d4-343">This is especially useful for filtering out unmanaged networks.</span></span> <span data-ttu-id="a75d4-344">下表中列出的筛选器使用正则表达式 (正则表达式) 。</span><span class="sxs-lookup"><span data-stu-id="a75d4-344">The filters listed in the following table use regular expressions (RegEx).</span></span>


| <span data-ttu-id="a75d4-345">筛选器</span><span class="sxs-lookup"><span data-stu-id="a75d4-345">Filter</span></span>         | <span data-ttu-id="a75d4-346">说明</span><span class="sxs-lookup"><span data-stu-id="a75d4-346">Description</span></span>          | <span data-ttu-id="a75d4-347">CQD 查询筛选器示例</span><span class="sxs-lookup"><span data-stu-id="a75d4-347">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="a75d4-348">无空值</span><span class="sxs-lookup"><span data-stu-id="a75d4-348">No blank values</span></span>   | <span data-ttu-id="a75d4-349">某些筛选器没有用于筛选空值的选项。</span><span class="sxs-lookup"><span data-stu-id="a75d4-349">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="a75d4-350">若要手动筛选空值，请使用空白表达式，并根据需要将筛选器设置为"等于"或"不等于"。</span><span class="sxs-lookup"><span data-stu-id="a75d4-350">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="a75d4-351">Second Building Name \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="a75d4-351">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="a75d4-352">排除常见子网</span><span class="sxs-lookup"><span data-stu-id="a75d4-352">Exclude common subnets</span></span> | <span data-ttu-id="a75d4-353">如果没有有效的建筑物文件来将托管网络与非托管网络分开，则报告中将包含家庭网络。</span><span class="sxs-lookup"><span data-stu-id="a75d4-353">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="a75d4-354">这些主子网不在 IT 控制的范围之内，可以快速从报告中排除。</span><span class="sxs-lookup"><span data-stu-id="a75d4-354">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="a75d4-355">本指南中定义的常见子网为 10.0.0.0、192.168.1.0 和 192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="a75d4-355">Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="a75d4-356">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="a75d4-356">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="a75d4-357">仅在内部查看</span><span class="sxs-lookup"><span data-stu-id="a75d4-357">View inside only</span></span>  | <span data-ttu-id="a75d4-358">用于筛选报表，以筛选 (外部) 托管 (托管) 。</span><span class="sxs-lookup"><span data-stu-id="a75d4-358">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="a75d4-359">托管的 CQD 模板已预配置了这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-359">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="a75d4-360">Second Inside Corp = Inside</span><span class="sxs-lookup"><span data-stu-id="a75d4-360">Second Inside Corp = Inside</span></span>        |

## <a name="report-filters"></a><span data-ttu-id="a75d4-361">报表筛选器</span><span class="sxs-lookup"><span data-stu-id="a75d4-361">Report filters</span></span>

<span data-ttu-id="a75d4-362">使用 CQD 报表筛选器缩小调查范围。</span><span class="sxs-lookup"><span data-stu-id="a75d4-362">Use CQD report filters to narrow the focus of your investigations.</span></span> <span data-ttu-id="a75d4-363">通过使用报表筛选器，在查询编辑器中或直接在报表内向呈现的报表添加筛选器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-363">Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.</span></span> <span data-ttu-id="a75d4-364">以下报告筛选器用于整个 [CQD 模板](https://aka.ms/QERtemplates)。</span><span class="sxs-lookup"><span data-stu-id="a75d4-364">The following report filters are used throughout the [CQD templates](https://aka.ms/QERtemplates).</span></span>


| <span data-ttu-id="a75d4-365">筛选器</span><span class="sxs-lookup"><span data-stu-id="a75d4-365">Filter</span></span>     | <span data-ttu-id="a75d4-366">说明</span><span class="sxs-lookup"><span data-stu-id="a75d4-366">Description</span></span>                            | <span data-ttu-id="a75d4-367">CQD 报表筛选器示例</span><span class="sxs-lookup"><span data-stu-id="a75d4-367">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="a75d4-368">Month</span><span class="sxs-lookup"><span data-stu-id="a75d4-368">Month</span></span>      | <span data-ttu-id="a75d4-369">首先从年份开始，然后从月份开始。</span><span class="sxs-lookup"><span data-stu-id="a75d4-369">Start with the year first, then month.</span></span> | <span data-ttu-id="a75d4-370">2017-10</span><span class="sxs-lookup"><span data-stu-id="a75d4-370">2017-10</span></span>                           |
| <span data-ttu-id="a75d4-371">字母</span><span class="sxs-lookup"><span data-stu-id="a75d4-371">Alphabetic</span></span> | <span data-ttu-id="a75d4-372">筛选任何字母字符。</span><span class="sxs-lookup"><span data-stu-id="a75d4-372">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="a75d4-373">[a-z]</span><span class="sxs-lookup"><span data-stu-id="a75d4-373">[a-z]</span></span>                             |
| <span data-ttu-id="a75d4-374">数字</span><span class="sxs-lookup"><span data-stu-id="a75d4-374">Numeric</span></span>    | <span data-ttu-id="a75d4-375">筛选任何数字字符。</span><span class="sxs-lookup"><span data-stu-id="a75d4-375">Filters for any numeric characters.</span></span>    | <span data-ttu-id="a75d4-376">[0-9]</span><span class="sxs-lookup"><span data-stu-id="a75d4-376">[0-9]</span></span>                             |
| <span data-ttu-id="a75d4-377">百分比</span><span class="sxs-lookup"><span data-stu-id="a75d4-377">Percentage</span></span> | <span data-ttu-id="a75d4-378">筛选百分比。</span><span class="sxs-lookup"><span data-stu-id="a75d4-378">Filters for a percentage.</span></span>              | <span data-ttu-id="a75d4-379"> ([3-9] \\ .) \| ([3-9]) \| ([1-9][0-9]) </span><span class="sxs-lookup"><span data-stu-id="a75d4-379">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |


### <a name="drill-down-filters"></a><span data-ttu-id="a75d4-380">向下钻取筛选器</span><span class="sxs-lookup"><span data-stu-id="a75d4-380">Drill-down filters</span></span>

<span data-ttu-id="a75d4-381">CQD 报表具有多个向下钻取筛选器，这些筛选器是缩小通话质量调查重点的强大工具。</span><span class="sxs-lookup"><span data-stu-id="a75d4-381">CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations.</span></span> <span data-ttu-id="a75d4-382">如果选择向下钻取字段，则报表会自动打开相应的选项卡，并筛选所选值。</span><span class="sxs-lookup"><span data-stu-id="a75d4-382">If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value.</span></span> <span data-ttu-id="a75d4-383">如果该选项卡具有其自己的向下钻取字段并且选择了一个字段，则应用这两组筛选器，从而逐渐缩小生成的数据集。</span><span class="sxs-lookup"><span data-stu-id="a75d4-383">If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.</span></span>

![演示向下钻取报表流的示意图](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a><span data-ttu-id="a75d4-385">添加和编辑向下钻取字段</span><span class="sxs-lookup"><span data-stu-id="a75d4-385">Adding and editing drill-down fields</span></span>

<span data-ttu-id="a75d4-386">编辑报表时，可以选择使用查询编辑器指定自己的向下钻取字段。</span><span class="sxs-lookup"><span data-stu-id="a75d4-386">When editing a report, you have the option to specify drill-down fields of your own using the Query Editor.</span></span>

<span data-ttu-id="a75d4-387">首先单击 **"...**</span><span class="sxs-lookup"><span data-stu-id="a75d4-387">Start by clicking **…**</span></span> <span data-ttu-id="a75d4-388">选择要编辑的报表，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="a75d4-388">for the report you want to edit, then select **Edit**.</span></span>

![编辑向下钻取字段的屏幕截图](media/qerguide-image-addeditdrilldownfields.png)

<span data-ttu-id="a75d4-390">从查询编辑器左侧的列表中选择"维度"。</span><span class="sxs-lookup"><span data-stu-id="a75d4-390">Select a Dimension from the list on the left side of the Query Editor.</span></span> <span data-ttu-id="a75d4-391">然后单击"导航到"标签下方的下拉列表，然后选择希望维度要导航到的选项卡钻取组。</span><span class="sxs-lookup"><span data-stu-id="a75d4-391">Then click on the dropdown below the **Navigate To** label and select the tab and expander group that you want that Dimension to drill through to.</span></span> <span data-ttu-id="a75d4-392">注意：目前，向下钻取功能仅通过导航到不同的选项卡来工作。</span><span class="sxs-lookup"><span data-stu-id="a75d4-392">Note: Presently, drill-down functionality only works by navigating to different tabs.</span></span> <span data-ttu-id="a75d4-393">稍后将添加对钻取到特定扩展器的支持。</span><span class="sxs-lookup"><span data-stu-id="a75d4-393">Support for drilling through to a specific expander will be added later.</span></span> <span data-ttu-id="a75d4-394">最后，单击 **"关闭**"将更改保存到"维度"，然后单击"保存"以保存并关闭查询编辑器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-394">Finally, click **Close** to save your changes to the Dimension, then click **Save** to save and close the Query Editor.</span></span>

![在查询编辑器中选择维度的屏幕截图](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a><span data-ttu-id="a75d4-396">多选筛选器</span><span class="sxs-lookup"><span data-stu-id="a75d4-396">Multi-select filters</span></span>

<span data-ttu-id="a75d4-397">除了向下钻取功能，CQD 还支持指定具有多个值的筛选器 (或筛选器) 。</span><span class="sxs-lookup"><span data-stu-id="a75d4-397">In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).</span></span>

<span data-ttu-id="a75d4-398">若要选择多个筛选器值，请首先向报表添加新筛选器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-398">In order to select multiple filter values, begin by adding a new filter to the report.</span></span> <span data-ttu-id="a75d4-399">在 **+** "**筛选器"标签** 旁边单击，输入想要使用的维度的名称，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a75d4-399">Click **+** beside the **Filters** label, enter the name of the Dimension you want to use, and click **Add**.</span></span>

![添加多选筛选器的屏幕截图](media/qerguide-image-addmultiselectfilter.png)

<span data-ttu-id="a75d4-401">然后单击" **搜索** (新筛选器"旁边的放大镜) 。</span><span class="sxs-lookup"><span data-stu-id="a75d4-401">Then, click **Search** (a magnifying glass icon next to the new filter).</span></span> <span data-ttu-id="a75d4-402">你将看到一个文本字段和一些选项，包括 **"全选**"和 **"反转"。**</span><span class="sxs-lookup"><span data-stu-id="a75d4-402">You'll see a text field, and a number of options, including **Select All** and **Invert**.</span></span> <span data-ttu-id="a75d4-403">输入值，然后单击 **该字段旁边的"** 搜索"进行搜索。</span><span class="sxs-lookup"><span data-stu-id="a75d4-403">Enter a value,  and click **Search** next to that field to search.</span></span> <span data-ttu-id="a75d4-404">或者，将文本字段留空，然后单击"搜索"查看最多前 100 个选项。</span><span class="sxs-lookup"><span data-stu-id="a75d4-404">Alternatively, leave the text field empty and click **Search** to view up to the first 100 options.</span></span>

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="a75d4-405">示例：</span><span class="sxs-lookup"><span data-stu-id="a75d4-405">Example:</span></span>  

![添加查询筛选器的屏幕截图](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a><span data-ttu-id="a75d4-407">仪表板级别筛选器</span><span class="sxs-lookup"><span data-stu-id="a75d4-407">Dashboard level filters</span></span>
<span data-ttu-id="a75d4-408">某些 CQD 报表添加了仪表板级筛选器，因此可以轻松按常用参数进行筛选。</span><span class="sxs-lookup"><span data-stu-id="a75d4-408">Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters.</span></span> <span data-ttu-id="a75d4-409">这些筛选器显示在常规报表选项卡外部和产品筛选器正下方，并应用于仪表板中的所有筛选器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-409">These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.</span></span>

![仪表板筛选器的屏幕截图](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a><span data-ttu-id="a75d4-411">URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="a75d4-411">URL filters</span></span>

<span data-ttu-id="a75d4-412">CQD 支持向 URL 添加筛选器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-412">CQD supports adding filters to the URL.</span></span> <span data-ttu-id="a75d4-413">这样，可以轻松共享 CQD 查询或为查询添加书签。</span><span class="sxs-lookup"><span data-stu-id="a75d4-413">This makes it easy to share or bookmark a CQD query.</span></span> <span data-ttu-id="a75d4-414">可以在 URL 中定义参数，例如趋势月份、租户 ID 或语言。</span><span class="sxs-lookup"><span data-stu-id="a75d4-414">You can define parameters in the URL, such as Trending Month, tenant ID, or language.</span></span> <span data-ttu-id="a75d4-415">还可以向 URL 添加"产品"或"仪表板"级别筛选器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-415">You can also add Product or Dashboard level filters to the URL.</span></span>
<span data-ttu-id="a75d4-416">从 CQD 报告中排除联合数据在修正托管建筑物或联合终结点可能会影响报表的网络时非常有用。</span><span class="sxs-lookup"><span data-stu-id="a75d4-416">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

<span data-ttu-id="a75d4-417">若要添加筛选器，将以下内容追加到 URL 的末尾：</span><span class="sxs-lookup"><span data-stu-id="a75d4-417">To add a filter, append the following to the end of the URL:</span></span>

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="a75d4-418">示例：</span><span class="sxs-lookup"><span data-stu-id="a75d4-418">Example:</span></span>  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

<span data-ttu-id="a75d4-419">若要将仪表板级筛选器添加到 URL，该筛选器必须作为"产品"或"仪表板"级别筛选器存在于 CQD 中。</span><span class="sxs-lookup"><span data-stu-id="a75d4-419">To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter.</span></span> <span data-ttu-id="a75d4-420">在"趋势月份"之后和 URL 参数之前，将以下筛选器添加到 URL：</span><span class="sxs-lookup"><span data-stu-id="a75d4-420">Add these filters to the URL after the Trending Month and before the URL parameters:</span></span>

`filter/DATA_MODEL_NAME|VALUE`

<span data-ttu-id="a75d4-421">例如，若要应用产品筛选器值 Microsoft Teams，需要添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="a75d4-421">For example, to apply a Product filter value of Microsoft Teams, you'd add the following:</span></span>

`filter/[AllStreams].[Is%20Teams]|[True]`

<span data-ttu-id="a75d4-422">整个 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a75d4-422">Your entire URL would look something like this:</span></span>

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

<span data-ttu-id="a75d4-423">若要应用具有多选值的 URL 筛选器，请用管道分隔每个 ( |) 字符。</span><span class="sxs-lookup"><span data-stu-id="a75d4-423">To apply URL filters with multi-select values, separate each value with a pipe ( | ) character.</span></span> <span data-ttu-id="a75d4-424">例如：</span><span class="sxs-lookup"><span data-stu-id="a75d4-424">For example:</span></span>

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

<span data-ttu-id="a75d4-425">如果指定无效的名称或值，将不会应用 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-425">If you specify an invalid name or value, the URL filter won't be applied.</span></span>


<span data-ttu-id="a75d4-426">可以使用 URL 筛选器筛选每个报表的特定维度。</span><span class="sxs-lookup"><span data-stu-id="a75d4-426">You can use a URL filter to filter every report for a specific dimension.</span></span> <span data-ttu-id="a75d4-427">最常见的 URL 筛选器用于筛选报告以排除联合参与者遥测数据，或仅关注 Teams 或 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="a75d4-427">The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business Online.</span></span> <span data-ttu-id="a75d4-428">从 CQD 报告中排除联合数据在修正托管建筑物或联合终结点可能会影响报表的网络时非常有用。</span><span class="sxs-lookup"><span data-stu-id="a75d4-428">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

| <span data-ttu-id="a75d4-429">筛选器</span><span class="sxs-lookup"><span data-stu-id="a75d4-429">Filter</span></span>         | <span data-ttu-id="a75d4-430">说明</span><span class="sxs-lookup"><span data-stu-id="a75d4-430">Description</span></span>          | <span data-ttu-id="a75d4-431">CQD 查询筛选器示例</span><span class="sxs-lookup"><span data-stu-id="a75d4-431">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="a75d4-432">无空值</span><span class="sxs-lookup"><span data-stu-id="a75d4-432">No blank values</span></span>   | <span data-ttu-id="a75d4-433">某些筛选器没有用于筛选空值的选项。</span><span class="sxs-lookup"><span data-stu-id="a75d4-433">Some filters don't have the option to filter for blank values.</span></span> <span data-ttu-id="a75d4-434">若要手动筛选空值，请使用空白表达式，并根据需要将筛选器设置为"等于"或"不等于"。</span><span class="sxs-lookup"><span data-stu-id="a75d4-434">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="a75d4-435">Second Building Name \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="a75d4-435">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="a75d4-436">排除常见子网</span><span class="sxs-lookup"><span data-stu-id="a75d4-436">Exclude common subnets</span></span> | <span data-ttu-id="a75d4-437">如果没有有效的建筑物文件来将托管网络与非托管网络分开，则报告中将包含家庭网络。</span><span class="sxs-lookup"><span data-stu-id="a75d4-437">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="a75d4-438">这些主子网不在 IT 控制的范围之内，可以快速从报告中排除。</span><span class="sxs-lookup"><span data-stu-id="a75d4-438">These home subnets are outside the scope of IT's control and can be quickly excluded from a report.</span></span> <span data-ttu-id="a75d4-439">本文中定义的常见子网为 10.0.0.0、192.168.1.0 和 192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="a75d4-439">Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="a75d4-440">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="a75d4-440">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="a75d4-441">仅在内部查看</span><span class="sxs-lookup"><span data-stu-id="a75d4-441">View inside only</span></span>  | <span data-ttu-id="a75d4-442">用于筛选报表，以筛选 (外部) 托管 (托管) 。</span><span class="sxs-lookup"><span data-stu-id="a75d4-442">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="a75d4-443">托管的 CQD 模板已预配置了这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="a75d4-443">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="a75d4-444">Second Inside Corp = Inside</span><span class="sxs-lookup"><span data-stu-id="a75d4-444">Second Inside Corp = Inside</span></span>        |


#### <a name="how-to-find-your-tenant-id"></a><span data-ttu-id="a75d4-445">如何查找租户 ID</span><span class="sxs-lookup"><span data-stu-id="a75d4-445">How to find your tenant ID</span></span>

<span data-ttu-id="a75d4-446">CQD 中的租户 ID 对应于 Azure 中的目录 ID。</span><span class="sxs-lookup"><span data-stu-id="a75d4-446">The tenant ID in CQD corresponds to the Directory ID in Azure.</span></span> <span data-ttu-id="a75d4-447">如果不知道目录 ID，可以在 Azure 门户中找到它：</span><span class="sxs-lookup"><span data-stu-id="a75d4-447">If you don't know your Directory ID, you can find it in the Azure portal:</span></span>

1.  <span data-ttu-id="a75d4-448">登录到 Microsoft Azure 门户：<https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="a75d4-448">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="a75d4-449">选择 **"Azure Active Directory"。**</span><span class="sxs-lookup"><span data-stu-id="a75d4-449">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="a75d4-450">在 **"管理"** 下，选择"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="a75d4-450">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="a75d4-451">租户 ID 位于" **目录 ID"** 框中。</span><span class="sxs-lookup"><span data-stu-id="a75d4-451">Your tenant ID is in the **Directory ID** box.</span></span>

<span data-ttu-id="a75d4-452">也可使用 PowerShell 查找租户 ID：</span><span class="sxs-lookup"><span data-stu-id="a75d4-452">You can also find your tenant ID by using PowerShell:</span></span> 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a><span data-ttu-id="a75d4-453">比较Teams和Skype for Business CQD 数据</span><span class="sxs-lookup"><span data-stu-id="a75d4-453">Comparing Teams and Skype for Business CQD data</span></span>

<span data-ttu-id="a75d4-454">查看数据时，可能会发现数据与数据Teams Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="a75d4-454">When reviewing your data, you may see differences in data between Teams and Skype for Business.</span></span> <span data-ttu-id="a75d4-455">一些原因：</span><span class="sxs-lookup"><span data-stu-id="a75d4-455">Some reasons:</span></span>
- <span data-ttu-id="a75d4-456">确保性能和可靠性的机制差异：</span><span class="sxs-lookup"><span data-stu-id="a75d4-456">Differences in the mechanisms for ensuring performance and reliability:</span></span>
  - <span data-ttu-id="a75d4-457">Teams自动重新连接和快速漫游。</span><span class="sxs-lookup"><span data-stu-id="a75d4-457">Teams has auto-reconnect and fast roaming.</span></span> <span data-ttu-id="a75d4-458">Skype for Business不会。</span><span class="sxs-lookup"><span data-stu-id="a75d4-458">Skype for Business doesn't.</span></span>
  - <span data-ttu-id="a75d4-459">Teams具有动态带宽管理。</span><span class="sxs-lookup"><span data-stu-id="a75d4-459">Teams has dynamic bandwidth management.</span></span> <span data-ttu-id="a75d4-460">Skype for Business不会。</span><span class="sxs-lookup"><span data-stu-id="a75d4-460">Skype for Business doesn't.</span></span>
- <span data-ttu-id="a75d4-461">IP 地址[范围在](Office-365-URLs-IP-address-ranges.md)Teams 和 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="a75d4-461">Differences in [IP address ranges](Office-365-URLs-IP-address-ranges.md) between Teams and Skype for Business.</span></span> <span data-ttu-id="a75d4-462">TEAMS IP 范围较新，这可能会导致防火墙出现连接问题。</span><span class="sxs-lookup"><span data-stu-id="a75d4-462">The Teams IP ranges are newer, which could cause connectivity problems at the firewall.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a75d4-463">自 2020 年 7 月 1 日起，旧版 CQD (cqd.lync.com) 从新的 CQD (访问数据，并且无法再导出建筑物和报表 https://CQD.teams.microsoft.com) 数据。</span><span class="sxs-lookup"><span data-stu-id="a75d4-463">As of July 1, 2020, the legacy version of CQD (cqd.lync.com) accesses data from the new CQD (https://CQD.teams.microsoft.com), and you can no longer export building and report data.</span></span> <span data-ttu-id="a75d4-464">自 2021 年 7 月 31 日起，随着 Skype for Business Online 的停用，我们将关闭旧版 CQD，你将无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="a75d4-464">Effective July 31, 2021, coinciding with the retirement of Skype for Business Online, we'll turn off legacy CQD and you'll no longer be able to access it.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a75d4-465">相关主题</span><span class="sxs-lookup"><span data-stu-id="a75d4-465">Related topics</span></span>

[<span data-ttu-id="a75d4-466">改进和监视呼叫质量Teams</span><span class="sxs-lookup"><span data-stu-id="a75d4-466">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="a75d4-467">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="a75d4-467">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="a75d4-468">使用 CQD (设置呼叫质量) </span><span class="sxs-lookup"><span data-stu-id="a75d4-468">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="a75d4-469">Upload租户和建筑物数据</span><span class="sxs-lookup"><span data-stu-id="a75d4-469">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="a75d4-470">使用 CQD 管理呼叫和会议质量</span><span class="sxs-lookup"><span data-stu-id="a75d4-470">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="a75d4-471">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="a75d4-471">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="a75d4-472">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="a75d4-472">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="a75d4-473">使用Power BI分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="a75d4-473">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
