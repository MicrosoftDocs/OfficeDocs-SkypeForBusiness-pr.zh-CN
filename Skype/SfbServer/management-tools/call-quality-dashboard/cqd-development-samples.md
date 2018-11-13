---
title: CQD 开发示例
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 摘要： 查看呼叫质量仪表板的教程和开发的示例。 呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 6bd6031e1d7fc94ed463c53efb068fd1e2e51378
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296124"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="2e296-104">CQD 开发示例</span><span class="sxs-lookup"><span data-stu-id="2e296-104">CQD Development Samples</span></span>

<span data-ttu-id="2e296-p102">**摘要：** 查看呼叫质量仪表板的教程和开发示例。呼叫质量仪表板是 Skype for Business Server 2015 的一个工具。</span><span class="sxs-lookup"><span data-stu-id="2e296-p102">**Summary:** Review a tutorial and development samples for Call Quality Dashboard. Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>

<span data-ttu-id="2e296-107">本文提供开发呼叫质量仪表板 (CQD) 的教程和示例。</span><span class="sxs-lookup"><span data-stu-id="2e296-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="2e296-108">呼叫质量仪表板 (CQD) 开发示例</span><span class="sxs-lookup"><span data-stu-id="2e296-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="2e296-109">教程：使用 CQD 数据服务和存储库服务 API 生成自定义报告表示。</span><span class="sxs-lookup"><span data-stu-id="2e296-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="2e296-110">CQD 简介</span><span class="sxs-lookup"><span data-stu-id="2e296-110">Introduction to CQD</span></span>

<span data-ttu-id="2e296-111">通过 CQD，可以快速轻松地访问本地 Skype for Business Server 部署的聚合呼叫质量信息。</span><span class="sxs-lookup"><span data-stu-id="2e296-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="2e296-112">CQD 由三个组件组成：QoE 存档数据库、多维数据集和门户。</span><span class="sxs-lookup"><span data-stu-id="2e296-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="2e296-113">门户是主要表示层，可以再进一步分成以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="2e296-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="2e296-114">数据服务，它是通过[数据 API 的呼叫质量仪表板 (CQD) 中的业务服务器 2015 Skype](data-api.md)的经过身份验证用户访问。</span><span class="sxs-lookup"><span data-stu-id="2e296-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015](data-api.md).</span></span>

2. <span data-ttu-id="2e296-115">存储库服务，它是通过[库 API 的呼叫质量仪表板 (CQD) 中的业务服务器 2015 Skype](repository-api.md)的经过身份验证用户访问。</span><span class="sxs-lookup"><span data-stu-id="2e296-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015](repository-api.md).</span></span>

3. <span data-ttu-id="2e296-116">Web 门户，这是基于 HTML5 的界面，CQD 用户会看到此界面，并与之交互。</span><span class="sxs-lookup"><span data-stu-id="2e296-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="2e296-117">通过身份验证的用户可以访问 Web 门户。</span><span class="sxs-lookup"><span data-stu-id="2e296-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="2e296-118">Web 门户上显示的报表分为"报表设置"。</span><span class="sxs-lookup"><span data-stu-id="2e296-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="2e296-119">图中显示了有两份报告的报告集。</span><span class="sxs-lookup"><span data-stu-id="2e296-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="2e296-120">以下仪表板中的每个报告显示了在应用不同的筛选器后得到的查询结果，这些结果反映了多个月内质量良好呼叫和质量欠佳呼叫的数量，以及质量欠佳呼叫所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="2e296-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![CQD 示例报告](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="2e296-p106">CQD 是按照呼叫质量方法 (CQM) 创建的，所以默认报告集设计为与 CQM 引入的调查流程一致。用户也可以灵活编辑或创建自定义报告来满足自己的需求。然而，由于有多种方式可用来可视化呈现数据，因此 CQD 提供的可视化可能无法完全满足每个用户的需求。在这样的情况下，用户可以利用数据 API 和存储库 API 来创建自定义报告页。我们将在本教程中介绍一系列示例。</span><span class="sxs-lookup"><span data-stu-id="2e296-p106">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM. Users also have the flexibility to edit or create custom reports to meet their needs. However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user. In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages. We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="2e296-127">仪表板如何使用数据服务</span><span class="sxs-lookup"><span data-stu-id="2e296-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="2e296-128">导航到 CQD 主页时 (例如http://localhost/cqd)、 设置报表和将从存储库服务中检索的经过身份验证和授权的用户的相应报告。</span><span class="sxs-lookup"><span data-stu-id="2e296-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="2e296-129">将从报表设置 ID 和年-月构造的完整 URL （报告集 ID 是在 URL 的 / #/ 节之后的整数个数和默认情况下当前年-月追加报告集 ID 末尾斜杠后）。</span><span class="sxs-lookup"><span data-stu-id="2e296-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="2e296-130">报告定义以 JSON 格式存储，在从存储库服务检索到该定义后，该定义将随后作为数据服务的输入。</span><span class="sxs-lookup"><span data-stu-id="2e296-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="2e296-131">数据服务根据该输入生成多维表达式 (MDX) 查询，然后对多维数据集运行这些 MDX 查询来为每个报告检索数据。</span><span class="sxs-lookup"><span data-stu-id="2e296-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="2e296-132">生成自定义报告</span><span class="sxs-lookup"><span data-stu-id="2e296-132">Building customized reports</span></span>

<span data-ttu-id="2e296-p108">在自定义报告方面，CQD 已经具备了极高的灵活性，但是有些情况下，用户可能想聚合在 CQD 中创建的多个报告的数据。例如，有人可能需要创建这样的报告，该报告在一个表中显示质量欠佳呼叫在所有可能的有线呼叫组合中所占的百分比（类似下图的结果）：</span><span class="sxs-lookup"><span data-stu-id="2e296-p108">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD. For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![CQD 表](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="2e296-p109">如果使用 CQD 提供的门户，用户将必须转到多个报告来提取和记录每个报告的质量欠佳呼叫百分比，如果需要采集很多数据点，那么工作量就会很大。数据 API 为用户提供了从数据服务检索数据（例如，通过 AJAX 调用）的编程方法来完成此任务。</span><span class="sxs-lookup"><span data-stu-id="2e296-p109">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected. The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="2e296-138">**示例 1：简单报告示例**</span><span class="sxs-lookup"><span data-stu-id="2e296-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="2e296-p110">我们先给出一个简单示例。如果要像下图那样，在 HTML 页中显示 2015 年 2 月质量良好音频流与质量欠佳音频流的计数：</span><span class="sxs-lookup"><span data-stu-id="2e296-p110">Let us take a simple example first. If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![CQD 示例报告](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="2e296-p111">我们所要做的是，以正确的参数向数据服务发出调用，然后在 HTML 表中显示查询结果。下面是 JavaScript 示例代码：</span><span class="sxs-lookup"><span data-stu-id="2e296-p111">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table. The following is a sample of the JavaScript code:</span></span>

```        
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

<span data-ttu-id="2e296-144">此示例可进一步解构成三个步骤：</span><span class="sxs-lookup"><span data-stu-id="2e296-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="2e296-145">构造 （这变量查询中定义的示例） 中的查询。</span><span class="sxs-lookup"><span data-stu-id="2e296-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="2e296-146">query 定义为 JSON 对象，它包含以下数据：</span><span class="sxs-lookup"><span data-stu-id="2e296-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="2e296-147">a.</span><span class="sxs-lookup"><span data-stu-id="2e296-147">a.</span></span> <span data-ttu-id="2e296-148">零个或更多维度。</span><span class="sxs-lookup"><span data-stu-id="2e296-148">Zero or more dimensions.</span></span> <span data-ttu-id="2e296-149">每个维度由 DataModelName 表示。</span><span class="sxs-lookup"><span data-stu-id="2e296-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="2e296-150">b.</span><span class="sxs-lookup"><span data-stu-id="2e296-150">b.</span></span> <span data-ttu-id="2e296-151">零个或更多筛选器。</span><span class="sxs-lookup"><span data-stu-id="2e296-151">Zero or more filters.</span></span> <span data-ttu-id="2e296-152">每个筛选器包含：</span><span class="sxs-lookup"><span data-stu-id="2e296-152">Each filter has:</span></span>

   - <span data-ttu-id="2e296-153">DataModelName（将设置筛选器的维度）。</span><span class="sxs-lookup"><span data-stu-id="2e296-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="2e296-154">Value（将由操作数比较的值）。</span><span class="sxs-lookup"><span data-stu-id="2e296-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="2e296-155">操作数 （比较类型，0 表示"等于"）。</span><span class="sxs-lookup"><span data-stu-id="2e296-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="2e296-156">c.</span><span class="sxs-lookup"><span data-stu-id="2e296-156">c.</span></span> <span data-ttu-id="2e296-157">一项或多项指标。</span><span class="sxs-lookup"><span data-stu-id="2e296-157">One or more measurements.</span></span>

2. <span data-ttu-id="2e296-158">通过 AJAX 调用将查询发给数据服务。</span><span class="sxs-lookup"><span data-stu-id="2e296-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="2e296-159">需要提供以下 request 参数：</span><span class="sxs-lookup"><span data-stu-id="2e296-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="2e296-160">a.</span><span class="sxs-lookup"><span data-stu-id="2e296-160">a.</span></span> <span data-ttu-id="2e296-161">url（应为 http://[ServerName]/QoEDataService/RunQuery）。</span><span class="sxs-lookup"><span data-stu-id="2e296-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="2e296-162">b.</span><span class="sxs-lookup"><span data-stu-id="2e296-162">b.</span></span> <span data-ttu-id="2e296-163">（这是在查询变量中定义的 JSON 对象的字符串表示形式） 的数据。</span><span class="sxs-lookup"><span data-stu-id="2e296-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="2e296-164">数据服务将查询结果作为查询成功时调用的回调函数的参数返回。</span><span class="sxs-lookup"><span data-stu-id="2e296-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="2e296-165">c.</span><span class="sxs-lookup"><span data-stu-id="2e296-165">c.</span></span> <span data-ttu-id="2e296-166">键入 （QoEDataService，为仅接受 RunQuery 发布请求）。</span><span class="sxs-lookup"><span data-stu-id="2e296-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="2e296-167">d.</span><span class="sxs-lookup"><span data-stu-id="2e296-167">d.</span></span> <span data-ttu-id="2e296-168">async（指出 AJAX 调用应该为同步还是异步的标志）。</span><span class="sxs-lookup"><span data-stu-id="2e296-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="2e296-169">e。</span><span class="sxs-lookup"><span data-stu-id="2e296-169">e.</span></span> <span data-ttu-id="2e296-170">contentType （应为"application/json"）。</span><span class="sxs-lookup"><span data-stu-id="2e296-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="2e296-171">f。</span><span class="sxs-lookup"><span data-stu-id="2e296-171">f.</span></span> <span data-ttu-id="2e296-172">success（AJAX 调用成功完成时调用的回调函数）。</span><span class="sxs-lookup"><span data-stu-id="2e296-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="2e296-173">g。</span><span class="sxs-lookup"><span data-stu-id="2e296-173">g.</span></span> <span data-ttu-id="2e296-174">error（AJAX 调用失败时调用的错误处理函数）。</span><span class="sxs-lookup"><span data-stu-id="2e296-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="2e296-175">将数据放入 HTML 中的 div 元素（在示例代码中，这是通过在 AJAX 请求成功完成后调用的匿名函数调用来完成的）。</span><span class="sxs-lookup"><span data-stu-id="2e296-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="2e296-p124">将 JavaScript 代码包含到 HTML 页面中，页面就会显示类似图中所示的报告。完整 html 如下：</span><span class="sxs-lookup"><span data-stu-id="2e296-p124">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure. The full html is as follows:</span></span>

```
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

<span data-ttu-id="2e296-p125">目前为止，报告仍然显得非常简单。用户可以添加更多指标、维度或筛选器来自定义报告。例如，如果要显示 AppSharing 质量欠佳呼叫百分比，那么需要添加有关 AppSharing 的新指标。如果要显示所有 TCP 呼叫与 UDP 呼叫的对比，那么应添加有关传输类型的新维度。如果要显示特定大楼内质量欠佳呼叫的数量，那么应添加新的筛选器来选择进出该大楼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2e296-p125">So far, the report is still very simple. The user can add more measurements, dimensions, or filters to customize the report. For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added. If you want to show all TCP calls v.s. UDP calls, a new dimension regarding transportation type should be added. If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="2e296-184">**示例 2：报告定义示例**</span><span class="sxs-lookup"><span data-stu-id="2e296-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="2e296-p126">在构造查询时，可能很难想出如何编写指标/维度/筛选器的完整列表及其对应的值。这种情况下，可以转至门户，使用报告编辑器生成报告，然后查看表示报告定义的 JSON 字符串，再将这些定义复制到自定义报告中。</span><span class="sxs-lookup"><span data-stu-id="2e296-p126">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query. In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="2e296-p127">本例中，我们将创建类似下图所示的网页，在该网页中，用户可输入任何现有报告集（或报告）的 ID，然后在网页上显示该报告集或报告的定义。而后，用户可将每个报告的 JSON 字符串插入类似示例 1 所示的代码中，从而构造用户所要的任何自定义报告。</span><span class="sxs-lookup"><span data-stu-id="2e296-p127">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page. The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![CQD 示例](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="2e296-p128">为了创建报告定义查看器工具，我们需要向存储库服务发出调用，以检索我们所要的每个报告集定义的 JSON 字符串表示形式。存储库 API 将根据给定的报告集 ID 返回报告集定义。</span><span class="sxs-lookup"><span data-stu-id="2e296-p128">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want. The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="2e296-192">快速示例如下，代码所含的代码块是一个简单示例，它向存储库服务发出查询，以根据存储库项的标识符获取该项的内容。</span><span class="sxs-lookup"><span data-stu-id="2e296-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="2e296-193">下一段代码（processReportSetData 方法）发出 AJAX 调用来获取该报告集内每个报告的定义。</span><span class="sxs-lookup"><span data-stu-id="2e296-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="2e296-194">由于 CQD Web 门户中的 ID 是报告集的 ID，因此 AJAX 调用将返回报告集项。</span><span class="sxs-lookup"><span data-stu-id="2e296-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="2e296-195">更多详细信息在存储库 API，具体而言，GetItems，可以[获取项](get-items.md)中找到。</span><span class="sxs-lookup"><span data-stu-id="2e296-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```
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

<span data-ttu-id="2e296-196">上述将导致网页 （不在初次访问时的报告定义） 图中所示。</span><span class="sxs-lookup"><span data-stu-id="2e296-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="2e296-197">获取报告的集 ID 从 CQD 门户 (' / #/ CQD 门户登录后 URL （例如</span><span class="sxs-lookup"><span data-stu-id="2e296-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="2e296-198">在报表的第一个图形集 ID 为编号为 3024），并将此报告的集 ID 放入该网页上的输入部分。</span><span class="sxs-lookup"><span data-stu-id="2e296-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="2e296-199">按"加载"按钮并查看报告集中的完整定义 （度量、 维度、 筛选器列表）。</span><span class="sxs-lookup"><span data-stu-id="2e296-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="2e296-200">在摘要，以便快速获取一报表/报表的完整定义。</span><span class="sxs-lookup"><span data-stu-id="2e296-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="2e296-201">步骤包括：</span><span class="sxs-lookup"><span data-stu-id="2e296-201">The steps are:</span></span>

1. <span data-ttu-id="2e296-202">转到门户，并使用查询编辑器自定义报表 （单击"编辑"按钮上方报表编辑、 添加、 删除筛选器度量/维度，然后保存报告）。</span><span class="sxs-lookup"><span data-stu-id="2e296-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="2e296-203">从 （' / #/ 之后的整数登录 URL） 的 URL 获取报告的集 ID。</span><span class="sxs-lookup"><span data-stu-id="2e296-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="2e296-204">启动示例 2 中创建的报告定义网页，输入报告集 ID，检索报告集的完整定义（将在数据 API 调用中使用）。</span><span class="sxs-lookup"><span data-stu-id="2e296-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="2e296-205">**示例 3：记分卡示例**</span><span class="sxs-lookup"><span data-stu-id="2e296-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="2e296-p132">现在我们来看一个更复杂的任务。如果我们想创建一个类似图中的网页，该怎么办？我们需要更新示例 1（借助示例 2 生成的网页来检索任何报告的完整定义），以便处理更大量的数据。</span><span class="sxs-lookup"><span data-stu-id="2e296-p132">Time for a more complicated task. What if we want to create a web page like the figure? We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="2e296-p133">此例中，我们需要更新指标和维度列表。遵循示例 2 中的说明弄清如何添加/编辑指标和/或维度，然后检索完整的报告定义，包括完整的指标和维度列表。将完整报告定义插入示例代码。</span><span class="sxs-lookup"><span data-stu-id="2e296-p133">In this case, we need to update the measurement and dimension list. The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists. Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="2e296-212">以下是基于示例 1 提供的示例，获得图中的记分卡页所需的详细步骤：</span><span class="sxs-lookup"><span data-stu-id="2e296-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="2e296-213">更新度量值中的查询变量从`[Measures].[Audio Good Streams JPDR Count]`和`[Measures].[Audio Poor Streams JPDR Count]`到`[Measures].[AudioPoorJPDRPercentage]`。</span><span class="sxs-lookup"><span data-stu-id="2e296-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="2e296-214">更新筛选器。</span><span class="sxs-lookup"><span data-stu-id="2e296-214">Update the filters.</span></span> <span data-ttu-id="2e296-215">示例 1 中的筛选器的 JSON 数据具有一个筛选器，它在维度设置`[StartDate].[Month]`。</span><span class="sxs-lookup"><span data-stu-id="2e296-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="2e296-216">由于 Filters 是 JSON 数组，因此其他维度可添加到筛选器列表中。</span><span class="sxs-lookup"><span data-stu-id="2e296-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="2e296-217">例如，若要获取"currentMonth"有线呼叫内部服务器客户端，我们应具有以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="2e296-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```
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

   <span data-ttu-id="2e296-218">此处维度`[Scenarios].[ScenarioPair]`设置为等于`[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`。</span><span class="sxs-lookup"><span data-stu-id="2e296-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="2e296-219">`[Scenario.][ScenarioPair]`是创建用于简化报告创建的特殊维度。</span><span class="sxs-lookup"><span data-stu-id="2e296-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="2e296-220">它有六个值，分别对应于 `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`。</span><span class="sxs-lookup"><span data-stu-id="2e296-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="2e296-221">因此，我们只需要使用 1 个筛选器，而无需使用 6 个筛选器的组合来定义方案。</span><span class="sxs-lookup"><span data-stu-id="2e296-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="2e296-222">在我们的示例，值`[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`于的方案转换其中： 首先是服务器、 第二不是服务器，首先位于，第二位于第一种连接类型有线，和第二个连接类型有线，即的确切定义"服务器的客户端-内部有线"。</span><span class="sxs-lookup"><span data-stu-id="2e296-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="2e296-p136">每个方案创建一个筛选器集。图中记分卡的每一行表示一个不同的方案，这些方案将成为不同的筛选器（虽然维度和指标保持不变）。</span><span class="sxs-lookup"><span data-stu-id="2e296-p136">Create one filter set per scenario. Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="2e296-p137">解析从 AJAX 调用获得的结果，将其放入表格的正确位置。由于这主要是 HTML 和 JavaScript 处理，因此这里我们不深入研究细节，而是在附录 A 中提供相关代码。</span><span class="sxs-lookup"><span data-stu-id="2e296-p137">Parse the results from the AJAX calls and place them in the correct position of the table. Since this is mostly HTML and JavaScript manipulation, we will not go into the details here. Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="2e296-228">如果启用跨源资源共享 (CORS)，则用户可能会遇到错误，如"无 Access-控件-允许-原点标头是存在于请求的资源。</span><span class="sxs-lookup"><span data-stu-id="2e296-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="2e296-229">原点 null 因此不允许访问"。</span><span class="sxs-lookup"><span data-stu-id="2e296-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="2e296-230">若要解决该问题，放置门户的安装位置的文件夹下的 HTML 文件 (默认情况下该文件应该是`%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`。</span><span class="sxs-lookup"><span data-stu-id="2e296-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="2e296-231">然后通过使用 URL 的任何浏览器访问 html `http://<servername>/cqd/<html_file_name>`。</span><span class="sxs-lookup"><span data-stu-id="2e296-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="2e296-232">(本地 CQD 仪表板的默认 url `http://<servername>/cqd.`)</span><span class="sxs-lookup"><span data-stu-id="2e296-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="2e296-233">附录 A</span><span class="sxs-lookup"><span data-stu-id="2e296-233">Appendix A</span></span>

<span data-ttu-id="2e296-234">示例 3 的 HTML 代码（记分卡示例）：</span><span class="sxs-lookup"><span data-stu-id="2e296-234">HTML code for Example 3 (Scorecard sample):</span></span>

```
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