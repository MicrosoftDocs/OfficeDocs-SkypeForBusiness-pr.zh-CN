---
title: CQD 开发示例
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
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 摘要：查看通话质量仪表板的教程和开发示例。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832722"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="1140b-104">CQD 开发示例</span><span class="sxs-lookup"><span data-stu-id="1140b-104">CQD Development Samples</span></span>

<span data-ttu-id="1140b-105">**摘要：** 查看通话质量仪表板的教程和开发示例。</span><span class="sxs-lookup"><span data-stu-id="1140b-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="1140b-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="1140b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="1140b-107">本文提供了有关通话质量仪表板和 CQD (的) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="1140b-108">通话质量仪表板 (CQD) 示例</span><span class="sxs-lookup"><span data-stu-id="1140b-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="1140b-109">教程：使用 CQD 数据服务和存储库服务 API 生成自定义报表演示文稿。</span><span class="sxs-lookup"><span data-stu-id="1140b-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="1140b-110">CQD 简介</span><span class="sxs-lookup"><span data-stu-id="1140b-110">Introduction to CQD</span></span>

<span data-ttu-id="1140b-111">CQD 提供快速而轻松地访问本地 Skype for Business Server 部署的聚合呼叫质量信息。</span><span class="sxs-lookup"><span data-stu-id="1140b-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="1140b-112">CQD 由三个组件组成：QoE 存档数据库、多维数据集和门户。</span><span class="sxs-lookup"><span data-stu-id="1140b-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="1140b-113">门户是主表示层，可以进一步划分为以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="1140b-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="1140b-114">数据服务，可通过 Skype for Business Server 中 [CQD (CQD](data-api.md)) 数据 API 供经过身份验证的用户访问。</span><span class="sxs-lookup"><span data-stu-id="1140b-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="1140b-115">存储库服务，可通过 Skype for Business Server 中的呼叫质量仪表板存储库 API ([CQD](repository-api.md)) 用户访问。</span><span class="sxs-lookup"><span data-stu-id="1140b-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="1140b-116">Web 门户，它是 CQD 用户查看并与之交互的基于 HTML5 的界面。</span><span class="sxs-lookup"><span data-stu-id="1140b-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="1140b-117">这可供经过身份验证的用户访问。</span><span class="sxs-lookup"><span data-stu-id="1140b-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="1140b-118">Web 门户上显示的报告分为"报告集"。</span><span class="sxs-lookup"><span data-stu-id="1140b-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="1140b-119">下图显示了一个报告集，其中具有两个报告。</span><span class="sxs-lookup"><span data-stu-id="1140b-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="1140b-120">下面此仪表板中的每个报表都显示有关好通话数、质量欠佳的呼叫数和几个月内质量欠佳的呼叫百分比的查询结果，并应用了各种筛选器。</span><span class="sxs-lookup"><span data-stu-id="1140b-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![CQD 示例报告](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="1140b-122">CQD 是按照 CQM (方法) 创建的，因此默认报告集旨在与 CQM 引入的调查流保持一致。</span><span class="sxs-lookup"><span data-stu-id="1140b-122">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM.</span></span> <span data-ttu-id="1140b-123">用户还可以灵活地编辑或创建自定义报告以满足其需求。</span><span class="sxs-lookup"><span data-stu-id="1140b-123">Users also have the flexibility to edit or create custom reports to meet their needs.</span></span> <span data-ttu-id="1140b-124">但是，由于有多种可视化数据的方法，CQD 提供的可视化可能无法完全满足每个用户的需求。</span><span class="sxs-lookup"><span data-stu-id="1140b-124">However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user.</span></span> <span data-ttu-id="1140b-125">在这种情况下，用户可以利用数据 API 和存储库 API 创建自定义报告页面。</span><span class="sxs-lookup"><span data-stu-id="1140b-125">In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages.</span></span> <span data-ttu-id="1140b-126">我们将在本教程中介绍一系列示例。</span><span class="sxs-lookup"><span data-stu-id="1140b-126">We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="1140b-127">仪表板如何使用数据服务</span><span class="sxs-lookup"><span data-stu-id="1140b-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="1140b-128">导航到 CQD 主页 (例如，从存储库服务检索经过身份验证和授权的用户的报告集和相应 http://localhost/cqd) 报告。</span><span class="sxs-lookup"><span data-stu-id="1140b-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="1140b-129">完整 URL 将基于报告集 ID 构建，而年-月 (报告集 ID 是 URL 中"/#/"部分后的整数，默认情况下，当前年份的追加位置为斜杠) 后的报告集 ID 的末尾。</span><span class="sxs-lookup"><span data-stu-id="1140b-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="1140b-130">报告定义以 JSON 格式存储，从存储库服务检索时，将用作数据服务的输入。</span><span class="sxs-lookup"><span data-stu-id="1140b-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="1140b-131">数据服务根据输入 (MDX) 生成多维表达式，然后针对多维数据集运行这些 MDX 查询以检索每个报告的数据。</span><span class="sxs-lookup"><span data-stu-id="1140b-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="1140b-132">生成自定义报告</span><span class="sxs-lookup"><span data-stu-id="1140b-132">Building customized reports</span></span>

<span data-ttu-id="1140b-133">CQD 在自定义报告方面已经具有很大的灵活性，但在某些情况下，用户可能希望聚合 CQD 中创建的多个报告的数据。</span><span class="sxs-lookup"><span data-stu-id="1140b-133">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD.</span></span> <span data-ttu-id="1140b-134">例如，可能需要创建一个报告，该报告显示表中所有可能组合的有线呼叫的欠佳呼叫百分比， (结果如下所示：) ：</span><span class="sxs-lookup"><span data-stu-id="1140b-134">For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![CQD 表](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="1140b-136">使用 CQD 提供的门户，用户必须导航到多个报告，以提取并记录每个报告质量欠佳的呼叫百分比，如果有许多需要收集的数据点，这将非常费时。</span><span class="sxs-lookup"><span data-stu-id="1140b-136">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected.</span></span> <span data-ttu-id="1140b-137">数据 API 为用户提供了一种编程方式来完成此操作，方法为从数据服务应用程序检索数据 (例如，通过 AJAX) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-137">The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="1140b-138">**示例 1：简单报告示例**</span><span class="sxs-lookup"><span data-stu-id="1140b-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="1140b-139">让我们首先看一个简单的示例。</span><span class="sxs-lookup"><span data-stu-id="1140b-139">Let us take a simple example first.</span></span> <span data-ttu-id="1140b-140">如果我们希望在如下所示的 HTML 页面上显示 2015 年 2 月的音频良好流和音频错误流计数：</span><span class="sxs-lookup"><span data-stu-id="1140b-140">If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![CQD 示例报告](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="1140b-142">我们需要使用正确的参数向数据服务发送调用，并将查询结果显示在 HTML 表中。</span><span class="sxs-lookup"><span data-stu-id="1140b-142">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table.</span></span> <span data-ttu-id="1140b-143">下面是 JavaScript 代码的示例：</span><span class="sxs-lookup"><span data-stu-id="1140b-143">The following is a sample of the JavaScript code:</span></span>

```javascript        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

<span data-ttu-id="1140b-144">此示例可以进一步解构为三个步骤：</span><span class="sxs-lookup"><span data-stu-id="1140b-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="1140b-145">构造该 ("查询"变量中定义的查询) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="1140b-146">查询定义为 JSON 对象，其中包含以下数据：</span><span class="sxs-lookup"><span data-stu-id="1140b-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="1140b-147">a.</span><span class="sxs-lookup"><span data-stu-id="1140b-147">a.</span></span> <span data-ttu-id="1140b-148">零个或多个维度。</span><span class="sxs-lookup"><span data-stu-id="1140b-148">Zero or more dimensions.</span></span> <span data-ttu-id="1140b-149">每个维度由 DataModelName 指示。</span><span class="sxs-lookup"><span data-stu-id="1140b-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="1140b-150">b.</span><span class="sxs-lookup"><span data-stu-id="1140b-150">b.</span></span> <span data-ttu-id="1140b-151">零个或多个筛选器。</span><span class="sxs-lookup"><span data-stu-id="1140b-151">Zero or more filters.</span></span> <span data-ttu-id="1140b-152">每个筛选器具有：</span><span class="sxs-lookup"><span data-stu-id="1140b-152">Each filter has:</span></span>

   - <span data-ttu-id="1140b-153">DataModelName (将设置筛选器的维度) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="1140b-154">值 (操作数值进行比较的值) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="1140b-155">操作 (类型，0 表示"等于") 。</span><span class="sxs-lookup"><span data-stu-id="1140b-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="1140b-156">c.</span><span class="sxs-lookup"><span data-stu-id="1140b-156">c.</span></span> <span data-ttu-id="1140b-157">一个或多个度量。</span><span class="sxs-lookup"><span data-stu-id="1140b-157">One or more measurements.</span></span>

2. <span data-ttu-id="1140b-158">通过 AJAX 调用将查询发送到数据服务。</span><span class="sxs-lookup"><span data-stu-id="1140b-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="1140b-159">需要提供以下请求参数：</span><span class="sxs-lookup"><span data-stu-id="1140b-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="1140b-160">a.</span><span class="sxs-lookup"><span data-stu-id="1140b-160">a.</span></span> <span data-ttu-id="1140b-161">url (应为 http：//[ServerName]/QoEDataService/RunQuery) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="1140b-162">b.</span><span class="sxs-lookup"><span data-stu-id="1140b-162">b.</span></span> <span data-ttu-id="1140b-163">data (这是在"query"变量中定义的 JSON 对象的字符串) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="1140b-164">数据服务将返回查询结果作为调用回叫函数的一个参数以成功。</span><span class="sxs-lookup"><span data-stu-id="1140b-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="1140b-165">c.</span><span class="sxs-lookup"><span data-stu-id="1140b-165">c.</span></span> <span data-ttu-id="1140b-166">type (For QoEDataService， RunQuery only accepts 'POST' requests) .</span><span class="sxs-lookup"><span data-stu-id="1140b-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="1140b-167">d.</span><span class="sxs-lookup"><span data-stu-id="1140b-167">d.</span></span> <span data-ttu-id="1140b-168">异步 (一个标志，指示 AJAX 调用是同步调用还是异步) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="1140b-169">e.</span><span class="sxs-lookup"><span data-stu-id="1140b-169">e.</span></span> <span data-ttu-id="1140b-170">contentType (应为"application/json") 。</span><span class="sxs-lookup"><span data-stu-id="1140b-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="1140b-171">f.</span><span class="sxs-lookup"><span data-stu-id="1140b-171">f.</span></span> <span data-ttu-id="1140b-172">成功 (AJAX 调用何时成功完成) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="1140b-173">g.</span><span class="sxs-lookup"><span data-stu-id="1140b-173">g.</span></span> <span data-ttu-id="1140b-174">错误 (AJAX 调用失败时的错误处理) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="1140b-175">将数据放入 HTML (代码示例中的 div 元素中，这是在 AJAX 请求成功完成之后通过匿名函数调用) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="1140b-176">将 JavaScript 代码包含在 HTML 页中，该页面将显示如图所示的报告。</span><span class="sxs-lookup"><span data-stu-id="1140b-176">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure.</span></span> <span data-ttu-id="1140b-177">完整的 html 如下所示：</span><span class="sxs-lookup"><span data-stu-id="1140b-177">The full html is as follows:</span></span>

```javascript
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

<span data-ttu-id="1140b-178">到目前为止，报告仍然非常简单。</span><span class="sxs-lookup"><span data-stu-id="1140b-178">So far, the report is still very simple.</span></span> <span data-ttu-id="1140b-179">用户可以添加更多度量、维度或筛选器来自定义报表。</span><span class="sxs-lookup"><span data-stu-id="1140b-179">The user can add more measurements, dimensions, or filters to customize the report.</span></span> <span data-ttu-id="1140b-180">例如，如果你想要显示 AppSharing 质量欠佳的呼叫百分比，那么需要添加关于 AppSharing 的新度量。</span><span class="sxs-lookup"><span data-stu-id="1140b-180">For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added.</span></span> <span data-ttu-id="1140b-181">如果要显示所有 TCP 调用 v.s。</span><span class="sxs-lookup"><span data-stu-id="1140b-181">If you want to show all TCP calls v.s.</span></span> <span data-ttu-id="1140b-182">UDP 调用，应添加与交通类型有关的新维度。</span><span class="sxs-lookup"><span data-stu-id="1140b-182">UDP calls, a new dimension regarding transportation type should be added.</span></span> <span data-ttu-id="1140b-183">如果要显示特定建筑物内质量欠佳的呼叫数，应添加一个新筛选器，以选择该建筑物的呼叫。</span><span class="sxs-lookup"><span data-stu-id="1140b-183">If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="1140b-184">**示例 2：报告定义示例**</span><span class="sxs-lookup"><span data-stu-id="1140b-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="1140b-185">在构造查询时，可能很难找出如何编写度量/维度/筛选器及其对应值的完整列表。</span><span class="sxs-lookup"><span data-stu-id="1140b-185">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query.</span></span> <span data-ttu-id="1140b-186">在这种情况下，您可以转到门户，使用报告编辑器生成报表，并查看报告定义的 JSON 字符串，然后将定义复制到自定义报告中。</span><span class="sxs-lookup"><span data-stu-id="1140b-186">In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="1140b-187">本示例中，我们将创建一个网页，如图所示，用户可以输入任何现有报告集 (或报表) 的 ID，并在此网页上显示报告集或报表的定义。</span><span class="sxs-lookup"><span data-stu-id="1140b-187">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page.</span></span> <span data-ttu-id="1140b-188">然后，用户可以将每个报告的 JSON 字符串插入类似于示例 1 中所示的代码，并构造用户期望的任何自定义报告。</span><span class="sxs-lookup"><span data-stu-id="1140b-188">The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![CQD 示例](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="1140b-190">若要创建报告定义查看器工具，我们需要向存储库服务发送调用，以检索所需的每个报告集定义的 JSON 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="1140b-190">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want.</span></span> <span data-ttu-id="1140b-191">存储库 API 将基于给定的报告集 ID 返回报告集定义。</span><span class="sxs-lookup"><span data-stu-id="1140b-191">The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="1140b-192">一个快速示例如下所示，代码包含一个块，该块是一个简单示例，用于向存储库服务发送查询，以基于存储库项的标识符获取存储库项的内容。</span><span class="sxs-lookup"><span data-stu-id="1140b-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="1140b-193">下一部分代码 (processReportSetData 方法) 发送 AJAX 调用，获取该报表集内每个报告的定义。</span><span class="sxs-lookup"><span data-stu-id="1140b-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="1140b-194">由于 CQD Web 门户中的 ID 是报告集的 ID，因此 AJAX 调用将返回报告集项。</span><span class="sxs-lookup"><span data-stu-id="1140b-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="1140b-195">有关存储库 API（特别是 GetItems）的更多详细信息，可以在"获取项目" [中找到](get-items.md)。</span><span class="sxs-lookup"><span data-stu-id="1140b-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

<span data-ttu-id="1140b-196">上述内容将导致网页（如图所示） (首次访问时没有报告) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="1140b-197">从 CQD 门户获取报告集 ID (/#/> 登录 CQD 门户 URL 之后，例如 (ID。</span><span class="sxs-lookup"><span data-stu-id="1140b-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="1140b-198">第一个图的报表集 ID 为 3024) ，将此报告集 ID 放入此网页的输入部分。</span><span class="sxs-lookup"><span data-stu-id="1140b-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="1140b-199">按"加载"按钮，查看 (、维度、筛选器列表) 报告集的完整定义。</span><span class="sxs-lookup"><span data-stu-id="1140b-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="1140b-200">总之，为了快速获取报告/报告集的完整定义。</span><span class="sxs-lookup"><span data-stu-id="1140b-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="1140b-201">步骤如下：</span><span class="sxs-lookup"><span data-stu-id="1140b-201">The steps are:</span></span>

1. <span data-ttu-id="1140b-202">转到门户并使用查询编辑器自定义报表 (单击报表上方的"编辑"按钮以编辑、添加、删除度量/维度/筛选器，然后将报表) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="1140b-203">从 URL 获取报告集 ID， ("/#/"登录 URL 之后获取) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="1140b-204">启动在示例 2 中创建的此报告定义网页，并输入报告集 ID，并检索要用于数据 API 调用 (报告集) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="1140b-205">**示例 3：记分卡示例**</span><span class="sxs-lookup"><span data-stu-id="1140b-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="1140b-206">更复杂的任务的时间。</span><span class="sxs-lookup"><span data-stu-id="1140b-206">Time for a more complicated task.</span></span> <span data-ttu-id="1140b-207">如果我们希望创建如图所示的网页，该做什么？</span><span class="sxs-lookup"><span data-stu-id="1140b-207">What if we want to create a web page like the figure?</span></span> <span data-ttu-id="1140b-208">我们需要更新示例 1， (在示例 2 中生成的网页的帮助下，检索任何报表) 的完整定义，以便我们可以处理更多的数据。</span><span class="sxs-lookup"><span data-stu-id="1140b-208">We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="1140b-209">在这种情况下，我们需要更新度量和维度列表。</span><span class="sxs-lookup"><span data-stu-id="1140b-209">In this case, we need to update the measurement and dimension list.</span></span> <span data-ttu-id="1140b-210">若要了解如何添加/编辑度量和/或维度，请按照示例 2 中的说明操作，并检索完整的报告定义，包括完整的度量和维度列表。</span><span class="sxs-lookup"><span data-stu-id="1140b-210">The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists.</span></span> <span data-ttu-id="1140b-211">将完整的报告定义插入示例代码中。</span><span class="sxs-lookup"><span data-stu-id="1140b-211">Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="1140b-212">下面是从示例 1 中提供的示例获取图中记分卡页面的详细步骤：</span><span class="sxs-lookup"><span data-stu-id="1140b-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="1140b-213">将"query"变量中的度量从和  `[Measures].[Audio Good Streams JPDR Count]` 更新 `[Measures].[Audio Poor Streams JPDR Count]` 到 `[Measures].[AudioPoorJPDRPercentage]` 。</span><span class="sxs-lookup"><span data-stu-id="1140b-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="1140b-214">更新筛选器。</span><span class="sxs-lookup"><span data-stu-id="1140b-214">Update the filters.</span></span> <span data-ttu-id="1140b-215">示例 1 中 Filters 的 JSON 数据具有一个筛选器，该筛选器在维度上设置  `[StartDate].[Month]` 。</span><span class="sxs-lookup"><span data-stu-id="1140b-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="1140b-216">由于 Filters 是 JSON 数组，因此可以将其他维度添加到筛选器列表中。</span><span class="sxs-lookup"><span data-stu-id="1140b-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="1140b-217">例如，若要在"currentMonth"的有线呼叫内获取服务器-客户端，应具有以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="1140b-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```javascript
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   <span data-ttu-id="1140b-218">此处将维度  `[Scenarios].[ScenarioPair]` 设置为相等 `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` 。</span><span class="sxs-lookup"><span data-stu-id="1140b-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="1140b-219">这是  `[Scenario.][ScenarioPair]` 为简化报表创建而创建的特殊维度。</span><span class="sxs-lookup"><span data-stu-id="1140b-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="1140b-220">它对应六个值 `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` 。</span><span class="sxs-lookup"><span data-stu-id="1140b-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="1140b-221">因此，我们只需要使用 1 个筛选器，而不是使用 6 个筛选器的组合来定义方案。</span><span class="sxs-lookup"><span data-stu-id="1140b-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="1140b-222">在我们的示例中，值转换为以下方案：第一个为服务器，第二个不是服务器，第一个位于内部，第一个连接类型为有线，第二个连接类型为有线，这是  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` "Server-Client-Inside Wired"的确切定义。</span><span class="sxs-lookup"><span data-stu-id="1140b-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="1140b-223">每个方案创建一个筛选器集。</span><span class="sxs-lookup"><span data-stu-id="1140b-223">Create one filter set per scenario.</span></span> <span data-ttu-id="1140b-224">图中记分卡的每一行表示不同的方案，即不同的筛选器 (而维度和度量保持不变) 。</span><span class="sxs-lookup"><span data-stu-id="1140b-224">Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="1140b-225">分析 AJAX 调用的结果，将它们放在表的正确位置。</span><span class="sxs-lookup"><span data-stu-id="1140b-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span></span> <span data-ttu-id="1140b-226">由于这主要是 HTML 和 JavaScript 操作，因此我们不会在此处了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="1140b-226">Since this is mostly HTML and JavaScript manipulation, we will not go into the details here.</span></span> <span data-ttu-id="1140b-227">相反，代码在附录 A 中提供。</span><span class="sxs-lookup"><span data-stu-id="1140b-227">Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="1140b-228">如果启用了跨源资源 (CORS) ，则用户可能会遇到"请求的资源上不存在"Access-Control-Allow-Origin"标头等错误。</span><span class="sxs-lookup"><span data-stu-id="1140b-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="1140b-229">因此，不允许访问原点"null"。</span><span class="sxs-lookup"><span data-stu-id="1140b-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="1140b-230">若要解决此问题，将 HTML 文件放在默认情况下安装门户 (文件夹下，它应该是 `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` 。</span><span class="sxs-lookup"><span data-stu-id="1140b-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="1140b-231">然后，通过具有 URL 的任何浏览器访问  `http://<servername>/cqd/<html_file_name>` html。</span><span class="sxs-lookup"><span data-stu-id="1140b-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="1140b-232"> (本地 CQD 仪表板的默认 URL 为  `http://<servername>/cqd.`) </span><span class="sxs-lookup"><span data-stu-id="1140b-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="1140b-233">附录 A</span><span class="sxs-lookup"><span data-stu-id="1140b-233">Appendix A</span></span>

<span data-ttu-id="1140b-234">示例 3 的 HTML 代码 (记分卡示例) ：</span><span class="sxs-lookup"><span data-stu-id="1140b-234">HTML code for Example 3 (Scorecard sample):</span></span>

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```
