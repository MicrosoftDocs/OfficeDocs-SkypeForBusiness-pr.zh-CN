---
title: 安装 Power BI 连接器以使用 CQD 查询模板
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 安装 Power BI 连接器以使用 CQD (查询) 呼叫质量仪表板
ms.openlocfilehash: 15e02ed85720cf96babc470e021df1a960d4b608
ms.sourcegitcommit: 4e1f5d99c1d0612dc5b50f850280983867ff53d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51874478"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a><span data-ttu-id="42ce2-103">安装 Power BI 连接器以使用 CQD 查询模板</span><span class="sxs-lookup"><span data-stu-id="42ce2-103">Install Power BI Connector to use CQD query templates</span></span>

<span data-ttu-id="42ce2-104">在使用 Power BI 查询模板 (PBIX 文件) for Microsoft Teams 呼叫质量仪表板 (CQD) 之前，需使用下载中包含的 *MicrosoftCallQuality.pqx* 文件安装适用于 Microsoft CQD 的 Power BI [连接器。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="42ce2-104">Before you can use the Power BI query templates (PBIX files) for Microsoft Teams Call Quality Dashboard (CQD), you'll need to install the Power BI Connector for Microsoft CQD, using the *MicrosoftCallQuality.pqx* file included in the [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span>

<span data-ttu-id="42ce2-105">请参阅[使用Power BI分析 CQD 数据Teams](CQD-Power-BI-query-templates.md)了解这些模板。</span><span class="sxs-lookup"><span data-stu-id="42ce2-105">Read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md) to learn about these templates.</span></span>

<span data-ttu-id="42ce2-106">请确保拥有正确的[CQD 访问角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)，以访问Power BI报告。</span><span class="sxs-lookup"><span data-stu-id="42ce2-106">Make sure you have the right [CQD access role](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) to access the Power BI reports.</span></span>

> [!NOTE]
> <span data-ttu-id="42ce2-107">CQD Power BI 连接器仅在 Power BI 中支持 DirectQuery;不支持导入模式。</span><span class="sxs-lookup"><span data-stu-id="42ce2-107">The CQD Power BI Connector only supports DirectQuery in Power BI; Import mode is not supported.</span></span> 

## <a name="installation"></a><span data-ttu-id="42ce2-108">安装</span><span class="sxs-lookup"><span data-stu-id="42ce2-108">Installation</span></span>

<span data-ttu-id="42ce2-109">以下文档详细介绍了安装自定义连接器和调整安全性以启用[连接器使用Power BI过程](/power-bi/desktop-connector-extensibility)。</span><span class="sxs-lookup"><span data-stu-id="42ce2-109">The process for installing a custom connector and adjusting security to enable use of the connector is described in detail in the [Power BI documentation](/power-bi/desktop-connector-extensibility).</span></span> <span data-ttu-id="42ce2-110">为简单起见，下面是一个快速说明：</span><span class="sxs-lookup"><span data-stu-id="42ce2-110">For the sake of simplicity, here's a quick explanation:</span></span>

1. <span data-ttu-id="42ce2-111">检查计算机是否已在"自定义连接器"文件夹中 *\[ \] \\ Power BI Desktop \\ 文档"。*</span><span class="sxs-lookup"><span data-stu-id="42ce2-111">Check to see if your computer already has a *\[Documents\]\\Power BI Desktop\\Custom Connectors* folder.</span></span> <span data-ttu-id="42ce2-112">如果没有，请创建此文件夹。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="42ce2-112">If not, create this folder.<sup>1</sup></span></span>

2. <span data-ttu-id="42ce2-113">将连接器文件 (*\* .mez* 或 *\* .pqx* 文件) 并放在 *自定义连接器* 目录中。</span><span class="sxs-lookup"><span data-stu-id="42ce2-113">Download the connector file (either a *\*.mez* or *\*.pqx* file) and place it in the *Custom Connectors* directory.</span></span>

3. <span data-ttu-id="42ce2-114">**如果连接器文件是 *\* .mez*** 文件，则还需要根据自定义连接器设置文档 中所述调整 [安全设置](/power-bi/desktop-connector-extensibility#data-extension-security)。</span><span class="sxs-lookup"><span data-stu-id="42ce2-114">**If the connector file is a *\*.mez* file,** you will also need to adjust your security settings as described in the [custom connector setup documentation](/power-bi/desktop-connector-extensibility#data-extension-security).</span></span>

<span data-ttu-id="42ce2-115">如果已发布此 Power BI 连接器的新版本Microsoft Teams，只需将自定义连接器目录中的旧连接器文件替换为新文件。 </span><span class="sxs-lookup"><span data-stu-id="42ce2-115">If a new version of this Power BI Connector for Microsoft Teams is released, simply replace the old connector file in the *Custom Connectors* directory with the new file.</span></span>

## <a name="setup"></a><span data-ttu-id="42ce2-116">设置</span><span class="sxs-lookup"><span data-stu-id="42ce2-116">Setup</span></span>

<span data-ttu-id="42ce2-117">若要生成报表并运行查询，首先需要连接到 CQD 数据源。</span><span class="sxs-lookup"><span data-stu-id="42ce2-117">In order to build a report and run queries, you will first need to connect to the CQD data source.</span></span> <span data-ttu-id="42ce2-118">请按照以下步骤进行连接：</span><span class="sxs-lookup"><span data-stu-id="42ce2-118">Follow the steps below in order to connect:</span></span>

1. <span data-ttu-id="42ce2-119">在"开始"选项卡Power BI Desktop，单击"*获取数据"。*</span><span class="sxs-lookup"><span data-stu-id="42ce2-119">In the Home tab of Power BI Desktop, click on *Get Data*.</span></span>

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector1-resize.png)

2. <span data-ttu-id="42ce2-121">此时 *应会显示* "获取数据"窗口。</span><span class="sxs-lookup"><span data-stu-id="42ce2-121">The *Get Data* window should appear at this point.</span></span> <span data-ttu-id="42ce2-122">导航到 *"联机服务"，* 然后选择 *"Microsoft 呼叫质量 (Beta* 版) 并 *连接"*。</span><span class="sxs-lookup"><span data-stu-id="42ce2-122">Navigate to *Online Services*, then select *Microsoft Call Quality (Beta)* and hit *Connect*.</span></span>

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector2-resize.png)

3. <span data-ttu-id="42ce2-124">系统会提示你下一步登录。</span><span class="sxs-lookup"><span data-stu-id="42ce2-124">You will be prompted to sign in next.</span></span> <span data-ttu-id="42ce2-125">使用用于 CQD 的相同凭据。<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="42ce2-125">Use the same credentials that you use for CQD.<sup>2</sup></span></span>

4. <span data-ttu-id="42ce2-126">下一个提示会提供两种数据连接 *模式之间的选项*。</span><span class="sxs-lookup"><span data-stu-id="42ce2-126">The next prompt will give you the option between two *Data Connectivity modes*.</span></span> <span data-ttu-id="42ce2-127">选择 *"DirectQuery"，* 并点击"*确定"。*</span><span class="sxs-lookup"><span data-stu-id="42ce2-127">Select *DirectQuery* and hit *OK*.</span></span>

5. <span data-ttu-id="42ce2-128">最后，系统会提供最终提示，显示 CQD 的整个数据模型。</span><span class="sxs-lookup"><span data-stu-id="42ce2-128">Finally, you will be given a final prompt showing you the entire data model for CQD.</span></span> <span data-ttu-id="42ce2-129">此时将看不到任何数据，只有 CQD 的数据模型可见。</span><span class="sxs-lookup"><span data-stu-id="42ce2-129">No data will be visible at this point, only the data model for CQD.</span></span> <span data-ttu-id="42ce2-130">选择 *"* 加载"完成设置过程。</span><span class="sxs-lookup"><span data-stu-id="42ce2-130">Select *Load* to complete the setup process.</span></span>

6. <span data-ttu-id="42ce2-131">此时，Power BI将数据模型加载到窗口右侧。</span><span class="sxs-lookup"><span data-stu-id="42ce2-131">At this point, Power BI will load the data model onto the right side of the window.</span></span> <span data-ttu-id="42ce2-132">页面将保留为空，默认情况下不会加载任何查询。</span><span class="sxs-lookup"><span data-stu-id="42ce2-132">The page will remain otherwise blank, and no queries will be loaded by default.</span></span> <span data-ttu-id="42ce2-133">继续 **下面的生成查询** ，以便生成查询并返回数据。</span><span class="sxs-lookup"><span data-stu-id="42ce2-133">Proceed to **Building Queries** below in order to build a query and return data.</span></span>

<span data-ttu-id="42ce2-134">如果此设置过程中的任何步骤未完全清楚，可以在快速入门：连接中查看有关[Power BI Desktop。](/power-bi/desktop-quickstart-connect-to-data)</span><span class="sxs-lookup"><span data-stu-id="42ce2-134">If any of the steps during this setup process were not completely clear, a more detailed explanation of the process can be found in [Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).</span></span>

## <a name="building-queries"></a><span data-ttu-id="42ce2-135">生成查询</span><span class="sxs-lookup"><span data-stu-id="42ce2-135">Building Queries</span></span>

<span data-ttu-id="42ce2-136">设置完成后，"字段"窗格中应显示数百个维度的名称和 *度量负载* 。</span><span class="sxs-lookup"><span data-stu-id="42ce2-136">Once setup is complete, you should see the names of several hundred dimensions and measures load in the *Fields* pane.</span></span> <span data-ttu-id="42ce2-137">从此处构造实际查询非常简单，只需选择查询的维度和度量值，然后将其拖放到页面上。</span><span class="sxs-lookup"><span data-stu-id="42ce2-137">Constructing actual queries from here is simple, just select the dimensions and measures you want for your query, then drag and drop them onto the page.</span></span> <span data-ttu-id="42ce2-138">下面是一个包含简单示例的更详细说明：</span><span class="sxs-lookup"><span data-stu-id="42ce2-138">Here's a more detailed explanation, with a simple example:</span></span>

1. <span data-ttu-id="42ce2-139">从"可视化"窗格中选择 *想要使用的可视化* 效果。</span><span class="sxs-lookup"><span data-stu-id="42ce2-139">Select the visualization you want to use from the *Visualizations* pane.</span></span> <span data-ttu-id="42ce2-140">该可视化效果的空白版本应显示在页面上。</span><span class="sxs-lookup"><span data-stu-id="42ce2-140">A blank version of that visualization should appear on the page.</span></span> <span data-ttu-id="42ce2-141">对于此示例，我们将使用表 *可视化* 效果。</span><span class="sxs-lookup"><span data-stu-id="42ce2-141">For the purposes of this example, we will be using the *Table* visualization.</span></span>

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector3-resize.png)

2. <span data-ttu-id="42ce2-143">确定聚合符号 (其名称表示的维度和度量值) 用于查询，然后手动选择它们并将其拖动到黑色可视化效果上。</span><span class="sxs-lookup"><span data-stu-id="42ce2-143">Determine which dimensions and measures (denoted by an aggregation symbol by their name) you wish to use for your query, then manually select them and drag them onto the black visualization.</span></span> <span data-ttu-id="42ce2-144">或者，将它们拖动到可视化 *选项下的* "值"字段。</span><span class="sxs-lookup"><span data-stu-id="42ce2-144">Alternately, drag them onto the *Values* field beneath the visualization options.</span></span>

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > <span data-ttu-id="42ce2-146">调用质量仪表板要求测量要运行的任何查询。</span><span class="sxs-lookup"><span data-stu-id="42ce2-146">Call Quality Dashboard requires a measure for any query to run.</span></span> <span data-ttu-id="42ce2-147">未能向查询添加度量值将导致该查询失败。</span><span class="sxs-lookup"><span data-stu-id="42ce2-147">Failure to add a measure to a query will cause that query to fail.</span></span>

3. <span data-ttu-id="42ce2-148">接下来，选择要筛选的任何维度，并将其拖动到"筛选器"窗格中 *此可视* 字段上的 *"筛选器* "。</span><span class="sxs-lookup"><span data-stu-id="42ce2-148">Next, select any dimensions you want to filter on and drag them to the *Filters on this visual* field in the *Filters* pane.</span></span> <span data-ttu-id="42ce2-149">CQD Power BI 连接器目前支持基本筛选 *(* 从可能维度值) 列表中选择值，高级筛选 (手动指定要筛选的值和操作数，类似于高级 CQD) ，而相对日期筛选 *(* 仅适用于结束时间和开始时间维度) 。  </span><span class="sxs-lookup"><span data-stu-id="42ce2-149">The CQD Power BI Connector currently supports *Basic filtering* (select values from a list of possible dimension values), *Advanced filtering* (manually specify values and operands to filter on, similar to Advanced CQD), and *Relative date filtering* (only available for the *End Time* and *Start Time* dimensions).</span></span> <span data-ttu-id="42ce2-150">CQD 不支持根据 *前 N* 个进行筛选。</span><span class="sxs-lookup"><span data-stu-id="42ce2-150">Filtering according to *Top N* is not supported by CQD.</span></span>

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector5-resize.png)

4. <span data-ttu-id="42ce2-152">最后， *选择"可视化* 效果"窗格中 *的"* 格式"选项卡，设置查询的样式和格式。</span><span class="sxs-lookup"><span data-stu-id="42ce2-152">Finally, select the *Format* tab within the *Visualizations* pane to style and format your query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="42ce2-153">CQD 查询至少需要一个度量值才能运行。</span><span class="sxs-lookup"><span data-stu-id="42ce2-153">CQD queries require at least one measure in order to run.</span></span> <span data-ttu-id="42ce2-154">如果查询未加载，请仔细检查查询中是否包含度量值。</span><span class="sxs-lookup"><span data-stu-id="42ce2-154">If your query does not load, double check that you have included a measure in the query.</span></span>

## <a name="creating-a-drillthrough-report"></a><span data-ttu-id="42ce2-155">创建钻取报表</span><span class="sxs-lookup"><span data-stu-id="42ce2-155">Creating a Drillthrough Report</span></span>

<span data-ttu-id="42ce2-156">[使用 Power BI](/power-bi/desktop-drillthrough)中的钻取可创建具有焦点的报表，可以使用其他报表的值作为上下文快速筛选这些报表。</span><span class="sxs-lookup"><span data-stu-id="42ce2-156">[Drillthrough in Power BI](/power-bi/desktop-drillthrough) allows you to create focused reports that you can quickly filter using the values of other reports as context.</span></span> <span data-ttu-id="42ce2-157">了解如何使用 CQD 连接器创建第一个查询后，创建钻取会更简单。</span><span class="sxs-lookup"><span data-stu-id="42ce2-157">Once you know how to create your first query with the CQD Connector, creating a drillthrough is even simpler.</span></span>

1. <span data-ttu-id="42ce2-158">为重点报表创建另一个页面，然后将查询添加到该页。</span><span class="sxs-lookup"><span data-stu-id="42ce2-158">Create another page for the focused report, and then add your queries to that page.</span></span>

2. <span data-ttu-id="42ce2-159">选择要用作钻取筛选器的维度，并将其拖动到"可视化"窗格下的 *"钻* 取 *"* 字段。</span><span class="sxs-lookup"><span data-stu-id="42ce2-159">Select the dimension you want to use as a drillthrough filter and drag them onto the *Drillthrough* field under on the *Visualizations* pane.</span></span>

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector6-resize.png)

3. <span data-ttu-id="42ce2-161">**就是这样\!**</span><span class="sxs-lookup"><span data-stu-id="42ce2-161">**That's it\!**</span></span> <span data-ttu-id="42ce2-162">现在，使用该维度的另一页上的其他任何查询都可以钻取到该页面，自动将钻取维度的值作为筛选器应用。</span><span class="sxs-lookup"><span data-stu-id="42ce2-162">Any other query on another page that uses that dimension can now drillthrough to that page, automatically applying the drillthrough dimension's value as a filter.</span></span>

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector7-resize.png)

<span data-ttu-id="42ce2-164">与高级 CQD 不同，Power BI支持非连续钻取。</span><span class="sxs-lookup"><span data-stu-id="42ce2-164">Unlike Advanced CQD, Power BI supports non-sequential drillthrough.</span></span> <span data-ttu-id="42ce2-165">只要查询包含必要的维度，它就可以钻取到任何其他页面。</span><span class="sxs-lookup"><span data-stu-id="42ce2-165">So long as a query includes the necessary dimension, it can drillthrough to any other page.</span></span>

### <a name="best-practice"></a><span data-ttu-id="42ce2-166">最佳做法</span><span class="sxs-lookup"><span data-stu-id="42ce2-166">Best practice</span></span>

<span data-ttu-id="42ce2-167">在设计调用质量连接器查询时，应牢记钻取功能。</span><span class="sxs-lookup"><span data-stu-id="42ce2-167">Call Quality connector queries should be designed with drillthrough functionality in mind.</span></span> <span data-ttu-id="42ce2-168">从更广泛的低基数查询开始，向下钻取到高基数查询，而不是尝试一次加载所有数据，然后使用筛选器进行切片。</span><span class="sxs-lookup"><span data-stu-id="42ce2-168">Instead of trying to load all the data at once, and then slicing down with filters, start with broader, low-cardinality queries and drill down to high-cardinality queries.</span></span> <span data-ttu-id="42ce2-169">例如，尝试诊断哪些子网对质量问题影响最大时，首先确定导致该问题的区域和/地区，然后向下钻取到该区域或国家/地区的子网会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="42ce2-169">For instance, when attempting to diagnose which subnets contribute most to quality issues, it's helpful to first identify those regions and countries which contribute to the problem, then drill down to the subnets in that region or country.</span></span> <span data-ttu-id="42ce2-170">呼叫质量连接器模板的设计方式就是为了作为示例。</span><span class="sxs-lookup"><span data-stu-id="42ce2-170">The Call Quality connector templates have been designed in this manner in order to act as an example.</span></span>

## <a name="limitations"></a><span data-ttu-id="42ce2-171">限制</span><span class="sxs-lookup"><span data-stu-id="42ce2-171">Limitations</span></span>

<span data-ttu-id="42ce2-172">尽管使用了 Power BI，但并非所有 Power BI 功能都受 CQD 连接器的支持，无论是由于 CQD 数据模型的限制还是 DirectQuery 连接器的一般限制。</span><span class="sxs-lookup"><span data-stu-id="42ce2-172">Despite making use of Power BI, not all Power BI functionality is support by the CQD Connector, either as a result of limitations on CQD data model or on DirectQuery connectors in general.</span></span> <span data-ttu-id="42ce2-173">以下列表列出了连接器的一些更值得注意的限制，但不应将此列表视为详尽：</span><span class="sxs-lookup"><span data-stu-id="42ce2-173">The list below notes some of the Connector's more noteworthy limitations, but this list should not be considered exhaustive:</span></span>

1. <span data-ttu-id="42ce2-174">**计算列 –** DirectQuery 连接器通常对计算列中的计算列的支持有限Power BI。</span><span class="sxs-lookup"><span data-stu-id="42ce2-174">**Calculated Columns –** DirectQuery connectors in general have limited support for calculated columns in Power BI.</span></span> <span data-ttu-id="42ce2-175">虽然某些计算列可能与连接器一起工作，但应认为这些列例外。</span><span class="sxs-lookup"><span data-stu-id="42ce2-175">While some calculated columns may work with the Connector, these should be considered exceptions.</span></span> <span data-ttu-id="42ce2-176">一般而言，计算列将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="42ce2-176">As a general rule, calculated columns will not function.</span></span>

2. <span data-ttu-id="42ce2-177">**聚合 –** CQD 数据模型构建在多维数据集模型上，这意味着已支持度量形式的聚合。</span><span class="sxs-lookup"><span data-stu-id="42ce2-177">**Aggregations –** The CQD data model is built on a cube model, meaning that aggregations are already supported in the form of measures.</span></span> <span data-ttu-id="42ce2-178">尝试手动将聚合添加到不同的维度或更改度量值的聚合类型将不起作用连接器，并且通常会导致错误。</span><span class="sxs-lookup"><span data-stu-id="42ce2-178">Attempting to manually add aggregations to different dimensions or changing the aggregation type of a measure will not work with the Connector, and it will generally result in an error.</span></span>

3. <span data-ttu-id="42ce2-179">**自定义视觉对象 –** 虽然 CQD 连接器可以处理一系列自定义视觉对象，但我们无法保证与所有自定义视觉对象的兼容性。</span><span class="sxs-lookup"><span data-stu-id="42ce2-179">**Custom Visuals –** While the CQD Connector does work with a range of custom visuals, we are unable to guarantee compatibility with all custom visuals.</span></span> <span data-ttu-id="42ce2-180">许多自定义视觉对象依赖于使用计算列或导入的数据，而 DirectQuery 连接器不支持 或 。</span><span class="sxs-lookup"><span data-stu-id="42ce2-180">Many custom visuals rely on the use of calculated columns or imported data, neither or which are supported by DirectQuery connectors.</span></span>

4. <span data-ttu-id="42ce2-181">**引用缓存数据 –** Power BI目前不支持从 DirectQuery 连接器以任何方式引用缓存的数据。</span><span class="sxs-lookup"><span data-stu-id="42ce2-181">**Referencing Cached Data –** Power BI currently does not support referencing cached data from a DirectQuery connector in any way.</span></span> <span data-ttu-id="42ce2-182">任何引用查询结果的尝试都将导致新的查询。</span><span class="sxs-lookup"><span data-stu-id="42ce2-182">Any attempt to reference the results of a query will result in a new query.</span></span>

5. <span data-ttu-id="42ce2-183">**相对数据筛选 –** 在 CQD 连接器中受支持，但仅支持"开始时间"*和"\*\*结束时间"* 维度。</span><span class="sxs-lookup"><span data-stu-id="42ce2-183">**Relative Data Filtering –** Is supported in the CQD Connector, but only with the *Start Time* and *End Time* dimensions.</span></span> <span data-ttu-id="42ce2-184">虽然 *"日期*"维度可能是相对日期筛选的明显选择，但日期不存储为日期时间对象，因此不支持在 Power BI。</span><span class="sxs-lookup"><span data-stu-id="42ce2-184">Although the *Date* dimension may be the obvious choice for relative date filtering, *Date* is not stored as a date time object and thus does not support relative date filtering in Power BI.</span></span>

6. <span data-ttu-id="42ce2-185">**政府社区云 (GCC) 支持 -** 对于在 GCC 环境中的客户，使用 Power BI 连接器时，CQD Power BI Desktop。</span><span class="sxs-lookup"><span data-stu-id="42ce2-185">**Government Community Cloud (GCC) Support –** For customers in the GCC environment, the CQD Power BI Connector will work when using Power BI Desktop.</span></span> <span data-ttu-id="42ce2-186">CQD Power BI 连接器当前与 Power BI 客户的 GCC 服务不兼容。</span><span class="sxs-lookup"><span data-stu-id="42ce2-186">The CQD Power BI connector is not presently compatible with the Power BI service for GCC customers.</span></span>

<span data-ttu-id="42ce2-187">这些问题中的大多数是 DirectQuery 连接器设计的限制Power BI是 CQD 数据模型设计的基础。</span><span class="sxs-lookup"><span data-stu-id="42ce2-187">Most of these issues are either restrictions to DirectQuery connector design in Power BI or fundamental to the design of the CQD data model.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="42ce2-188">疑难解答</span><span class="sxs-lookup"><span data-stu-id="42ce2-188">Troubleshooting</span></span>

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a><span data-ttu-id="42ce2-189">我正在尝试使用"日期"列作为日期切片器。</span><span class="sxs-lookup"><span data-stu-id="42ce2-189">I'm trying to use the Date column as a Date slicer.</span></span> <span data-ttu-id="42ce2-190">将此列的数据类型转换为日期后，就会收到此错误</span><span class="sxs-lookup"><span data-stu-id="42ce2-190">As soon as I convert the data type of this column to Date, I get this error</span></span>

> <span data-ttu-id="42ce2-191">**无法加载此视觉对象的数据**：OLE DB 或 ODBC 错误：[Expression.Error] 无法将表达式折叠到数据源。</span><span class="sxs-lookup"><span data-stu-id="42ce2-191">**Couldn't load the data for this visual**: OLE DB or ODBC error: [Expression.Error] We couldn't fold the expression to the data source.</span></span> <span data-ttu-id="42ce2-192">请尝试更简单的表达式。</span><span class="sxs-lookup"><span data-stu-id="42ce2-192">Please try a simpler expression.</span></span>

<span data-ttu-id="42ce2-193">数据连接器不支持日期切片器Power BI连接器。</span><span class="sxs-lookup"><span data-stu-id="42ce2-193">Date slicers aren't supported with the Power BI Connector.</span></span> <span data-ttu-id="42ce2-194">若要指定日期范围，请对报表应用两个筛选器，指定小于和大于日期。</span><span class="sxs-lookup"><span data-stu-id="42ce2-194">To specify a date range, apply two filters to the report, specifying a less than and greater than date.</span></span>

<span data-ttu-id="42ce2-195">或者，如果要查看的日期是最近的日期，请应用相对日期筛选器以仅显示过去 N 天/周/月的数据。</span><span class="sxs-lookup"><span data-stu-id="42ce2-195">Alternatively, if the dates you want to view are recent, apply a relative date filter to show only data for the last N days/weeks/months.</span></span>

## <a name="error-codes"></a><span data-ttu-id="42ce2-196">错误代码</span><span class="sxs-lookup"><span data-stu-id="42ce2-196">Error Codes</span></span>

<span data-ttu-id="42ce2-197">由于 CQD Power BI 连接器在可构造的查询类型方面比浏览器应用的限制更少，因此在构建查询时，有时可能会遇到许多错误。</span><span class="sxs-lookup"><span data-stu-id="42ce2-197">Because the CQD Power BI Connector is less restricted than the browser app in terms of kinds of queries you can construct, you may occasionally encounter a number of errors while building your queries.</span></span> <span data-ttu-id="42ce2-198">如果收到"CQDError"类型的错误消息。</span><span class="sxs-lookup"><span data-stu-id="42ce2-198">In the event that you receive an error message of the type "CQDError.</span></span> <span data-ttu-id="42ce2-199">RunQuery – 查询执行错误"，使用提供的 ErrorType 编号引用以下列表，以排查查询可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="42ce2-199">RunQuery – Query Execution Error", reference the list below with the ErrorType number provided in order to troubleshoot the possible issue with the query.</span></span> <span data-ttu-id="42ce2-200">以下是使用 CQD 连接器时可能会遇到的最常见错误类型Power BI代码：</span><span class="sxs-lookup"><span data-stu-id="42ce2-200">The following are the most common Error Type codes you may encounter with the CQD Power BI Connector:</span></span>

- <span data-ttu-id="42ce2-201">**ErrorType 1 - 查询结构错误：** 查询结构错误通常是由于连接器未能生成格式正确的查询导致的。</span><span class="sxs-lookup"><span data-stu-id="42ce2-201">**ErrorType 1 - Query Structure Error:** A query structure error is typically caused by the Connector failing to build a properly formatted query.</span></span> <span data-ttu-id="42ce2-202">使用不受支持的功能时（如上述限制中指定）时，通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="42ce2-202">This happens most often when using unsupported functionality, as specified in the Limitations above.</span></span> <span data-ttu-id="42ce2-203">仔细检查是否未对查询使用任何计算列或自定义视觉对象。</span><span class="sxs-lookup"><span data-stu-id="42ce2-203">Double check that you are not using any calculated columns or custom visuals for that query.</span></span>

  - <span data-ttu-id="42ce2-204">**ErrorType 2 - 查询生成错误：** 查询生成错误是由 CQD 连接器无法正确分析尝试构建的查询导致的。</span><span class="sxs-lookup"><span data-stu-id="42ce2-204">**ErrorType 2 - Query Building Error:** A query building error is caused by the CQD Connector being unable to properly parse the query you are attempting to build.</span></span> <span data-ttu-id="42ce2-205">使用不受支持的功能时（如上述限制中指定）时，通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="42ce2-205">This happens most often when using unsupported functionality, as specified in the Limitations above.</span></span> <span data-ttu-id="42ce2-206">仔细检查是否未对查询使用任何计算列或自定义视觉对象。</span><span class="sxs-lookup"><span data-stu-id="42ce2-206">Double check that you are not using any calculated columns or custom visuals for that query.</span></span>

  - <span data-ttu-id="42ce2-207">**ErrorType 5 - 执行超时：** 在超时之前，查询已达到可能的最大运行时。尝试向查询添加更多筛选器，以限制其范围。</span><span class="sxs-lookup"><span data-stu-id="42ce2-207">**ErrorType 5 - Execution Timeout:** The query has reached the maximum possible runtime before timing out. Try adding more filters to the query in order to limit its scope.</span></span> <span data-ttu-id="42ce2-208">缩小数据范围通常是实现此目的最有效的方法。</span><span class="sxs-lookup"><span data-stu-id="42ce2-208">Narrowing the data range is often the most effective way to achieve this.</span></span>

  - <span data-ttu-id="42ce2-209">**ErrorType 7 - 无度量错误：** CQD 查询需要一个度量值才能运行。</span><span class="sxs-lookup"><span data-stu-id="42ce2-209">**ErrorType 7 - No Measurements Error:** CQD queries require a measure in order to function.</span></span> <span data-ttu-id="42ce2-210">仔细检查查询是否包含度量值。</span><span class="sxs-lookup"><span data-stu-id="42ce2-210">Double check that your query includes measure.</span></span> <span data-ttu-id="42ce2-211">CQD 连接器中的度量值由聚合值 (其名称) 和符号表示。</span><span class="sxs-lookup"><span data-stu-id="42ce2-211">Measures in the CQD Connector are denoted by the aggregation (sum) symbol before their name.</span></span>

<span data-ttu-id="42ce2-212">如果在此范围之外遇到任何其他错误，请通知 CQD 团队，以便我们可以帮助排查问题并适当地更新文档。</span><span class="sxs-lookup"><span data-stu-id="42ce2-212">If you encounter any additional errors outside of this scope, please notify the CQD team so that we can help troubleshoot the issue and update the documentation as appropriate.</span></span>

## <a name="footnotes"></a><span data-ttu-id="42ce2-213">脚注</span><span class="sxs-lookup"><span data-stu-id="42ce2-213">Footnotes</span></span>

<span data-ttu-id="42ce2-214">**<sup>1</sup>** 某些进程 (应用，例如，OneDrive) 可能导致"文档"根文件夹更改;确保自定义 *连接器Power BI Desktop \\* 放在当前根文件夹"文档"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="42ce2-214">**<sup>1</sup>** Certain processes and apps (e.g., OneDrive) may cause your Documents root folder to change; make sure that the *Power BI Desktop\\Custom Connectors* directory is placed inside of the current root folder Documents folder.</span></span>

<span data-ttu-id="42ce2-215">**<sup>2</sup>** 用于 CQD 的登录凭据不需要是登录应用本身时Power BI Desktop凭据。</span><span class="sxs-lookup"><span data-stu-id="42ce2-215">**<sup>2</sup>** The login credentials you use for CQD *do not* need to be the same credentials you use for logging into the Power BI Desktop app itself.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="42ce2-216">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="42ce2-216">Frequently asked questions</span></span>

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a><span data-ttu-id="42ce2-217">何时从Power BI"状态更新连接器</span><span class="sxs-lookup"><span data-stu-id="42ce2-217">When will the Power BI Connector be updated from "Beta" status</span></span>

<span data-ttu-id="42ce2-218">尽管使用 Beta 标记，Power BI的呼叫质量连接器是连接器的发布版本，并且已经由 Power BI 团队正式签名，以反映这一点。</span><span class="sxs-lookup"><span data-stu-id="42ce2-218">Despite the Beta tag, the Call Quality Connector for Power BI is the release version of the connector and has been officially security signed by the Power BI team to reflect this.</span></span> <span data-ttu-id="42ce2-219">删除该 Beta 版标记的认证过程是一个广泛的过程，需要Power BI团队做出承诺，为连接器提供直接支持。</span><span class="sxs-lookup"><span data-stu-id="42ce2-219">The certification process to remove that Beta tag is an extensive one and requires a commitment from the Power BI team to provide direct support to the connector as well.</span></span> <span data-ttu-id="42ce2-220">由于时间限制，Power BI团队当前无法提供该支持和更广泛的认证，但仍准备证明 Microsoft 呼叫质量连接器的安全性、真实性和常规功能。</span><span class="sxs-lookup"><span data-stu-id="42ce2-220">Due to time constraints, the Power BI team is currently unable to provide that support and broader certification, but is still prepared to attest to the security, authenticity, and general functionality of the Microsoft Call Quality connector.</span></span>

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a><span data-ttu-id="42ce2-221">与浏览器中的高级 CQD 相比，连接器为何看起来较慢？</span><span class="sxs-lookup"><span data-stu-id="42ce2-221">Why does the connector seem slower compared to Advanced CQD in the browser?</span></span> <span data-ttu-id="42ce2-222">可以执行哪些功能来提高性能</span><span class="sxs-lookup"><span data-stu-id="42ce2-222">What can I do to improve performance</span></span>

<span data-ttu-id="42ce2-223">在浏览器和连接器中，各种模板的查询性能实际上是相同的。</span><span class="sxs-lookup"><span data-stu-id="42ce2-223">Query performance for the various templates is actually the same in both the browser and in the connector.</span></span>  <span data-ttu-id="42ce2-224">与其他任何独立应用一样，Power BI将身份验证和呈现时间添加到我们的性能。</span><span class="sxs-lookup"><span data-stu-id="42ce2-224">Just like any other standalone app, Power BI adds its authentication and rendering time to our performance.</span></span> <span data-ttu-id="42ce2-225">此外，差异在于运行的并发查询数。</span><span class="sxs-lookup"><span data-stu-id="42ce2-225">In addition, the difference comes in the number of concurrent queries being run.</span></span> <span data-ttu-id="42ce2-226">由于 CQD 的浏览器内版本具有开发较少且信息密集型的可视化选项，因此我们的大多数报告限制为一次加载 2-3 个查询。</span><span class="sxs-lookup"><span data-stu-id="42ce2-226">Because the in-browser version of CQD had less well-developed and information-dense visualization options, most of our reports were limited to loading 2-3 queries at a time.</span></span> <span data-ttu-id="42ce2-227">另一方面，连接器模板通常显示 20 多个并发查询。</span><span class="sxs-lookup"><span data-stu-id="42ce2-227">On the other hand, the connector templates often display 20+ concurrent queries.</span></span> <span data-ttu-id="42ce2-228">如果希望生成的响应与以前使用的报表一样高，请尝试创建每个选项卡不超过 2-3 个查询的报表。</span><span class="sxs-lookup"><span data-stu-id="42ce2-228">If you wish to build reports that are just as responsive as the older ones you were used to, try creating reports with no more than 2-3 queries per tab.</span></span>

<span data-ttu-id="42ce2-229">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="42ce2-229">For more information, see the following articles:</span></span>

- [<span data-ttu-id="42ce2-230">优化指南Power BI</span><span class="sxs-lookup"><span data-stu-id="42ce2-230">Optimization guide for Power BI</span></span>](/power-bi/guidance/power-bi-optimization)
- [<span data-ttu-id="42ce2-231">DirectQuery 模型指南</span><span class="sxs-lookup"><span data-stu-id="42ce2-231">DirectQuery model guidance</span></span>](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a><span data-ttu-id="42ce2-232">在运行查询时，我发现自己经常遇到 10，000 行的限制。</span><span class="sxs-lookup"><span data-stu-id="42ce2-232">I find that I routinely run into the 10,000-row limit when running queries.</span></span> <span data-ttu-id="42ce2-233">如何让连接器返回超过 10，000 行</span><span class="sxs-lookup"><span data-stu-id="42ce2-233">How can I get the connector to return more than 10,000 rows</span></span>

<span data-ttu-id="42ce2-234">API 端实际指定了 10，000 行的限制，旨在帮助显著提高性能并降低因内存不足导致查询执行错误的风险。</span><span class="sxs-lookup"><span data-stu-id="42ce2-234">The 10,000-row limit is actually specified on the API end, and it is designed to help significantly improve performance and reduce the risk of query execution errors resulting from low memory conditions.</span></span>

<span data-ttu-id="42ce2-235">最好根据连接器最佳做法重构报表，而不是尝试增加结果行计数。</span><span class="sxs-lookup"><span data-stu-id="42ce2-235">Instead of attempting to increase the result row count, it is best to restructure your reports according to connector best practices.</span></span> <span data-ttu-id="42ce2-236">我们包含的模板旨在演示这些最佳做法。</span><span class="sxs-lookup"><span data-stu-id="42ce2-236">The templates we have included are designed to demonstrate these best practices.</span></span> <span data-ttu-id="42ce2-237">在可能的情况下，首先使用更大、基数较低的维度（如月、年、日期、区域、国家/地区等）查看 KPI。从该维度中，可以向下钻取到基数越高的维度。</span><span class="sxs-lookup"><span data-stu-id="42ce2-237">Where possible, start by looking at your KPIs using broader, lower-cardinality dimensions, such as Month, Year, Date, Region, Country, etc. From there, you can drill down into increasingly higher-cardinality dimensions.</span></span> <span data-ttu-id="42ce2-238">支持人员报表Location-Enhanced报表都提供了此向下钻取工作流的良好示例。</span><span class="sxs-lookup"><span data-stu-id="42ce2-238">The Helpdesk and Location-Enhanced Reports both provide good examples of this drill down workflow.</span></span>



## <a name="related-topics"></a><span data-ttu-id="42ce2-239">相关主题</span><span class="sxs-lookup"><span data-stu-id="42ce2-239">Related topics</span></span>

[<span data-ttu-id="42ce2-240">使用Power BI分析用于存储的 CQD Teams</span><span class="sxs-lookup"><span data-stu-id="42ce2-240">Use Power BI to analyze CQD data for Teams</span></span>](CQD-Power-BI-query-templates.md)
