---
title: 安装 Power BI Connector 以使用 CQD 查询模板
ms.author: lolaj
author: LolaJacobsen
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
description: 安装 Power BI Connector 以使用 CQD 查询模板
ms.openlocfilehash: c9987d05c5b057adf55791ffb2105d9ddb252722
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559389"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a><span data-ttu-id="74cfc-103">安装 Power BI Connector 以使用 CQD 查询模板</span><span class="sxs-lookup"><span data-stu-id="74cfc-103">Install Power BI Connector to use CQD query templates</span></span>

<span data-ttu-id="74cfc-104">在你可以对 CQD （.PBIX 文件）使用 Power BI 查询模板之前，你需要使用[下载](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)中包含的*MicrosoftCallQuality*文件来安装 MICROSOFT CQD 的 power bi 连接器。</span><span class="sxs-lookup"><span data-stu-id="74cfc-104">Before you can use the Power BI query templates for CQD (PBIX files), you’ll need to install the Power BI Connector for Microsoft CQD, using the *MicrosoftCallQuality.pqx* file included in the [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="74cfc-105">已阅读 "[使用 POWER BI" 来分析 CQD 数据，以供团队](CQD-Power-BI-query-templates.md)了解有关这些模板的信息。</span><span class="sxs-lookup"><span data-stu-id="74cfc-105">Read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md) to learn about these templates.</span></span>


## <a name="installation"></a><span data-ttu-id="74cfc-106">安装</span><span class="sxs-lookup"><span data-stu-id="74cfc-106">Installation</span></span>

<span data-ttu-id="74cfc-107">[POWER BI 文档](https://docs.microsoft.com/power-bi/desktop-connector-extensibility)中详细介绍了安装自定义连接线和调整安全性以启用连接器使用的过程。</span><span class="sxs-lookup"><span data-stu-id="74cfc-107">The process for installing a custom connector and adjusting security to enable use of the connector is described in detail in the [Power BI documentation](https://docs.microsoft.com/power-bi/desktop-connector-extensibility).</span></span> <span data-ttu-id="74cfc-108">为了简便起见，下面是一个快速说明：</span><span class="sxs-lookup"><span data-stu-id="74cfc-108">For the sake of simplicity, here’s a quick explanation:</span></span>

1.  <span data-ttu-id="74cfc-109">检查 您的\* \[\]\\计算机是否已有 "Power\\BI desktop 自定义连接线\*" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="74cfc-109">Check to see if your computer already has a *\[Documents\]\\Power BI Desktop\\Custom Connectors* folder.</span></span> <span data-ttu-id="74cfc-110">如果不是，请创建此文件夹。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="74cfc-110">If not, create this folder.<sup>1</sup></span></span>

2.  <span data-ttu-id="74cfc-111">下载连接器文件（即\* \*mez*或* \*pqx*文件），并将其放在 "*自定义连接器\*" 目录中。</span><span class="sxs-lookup"><span data-stu-id="74cfc-111">Download the connector file (either a *\*.mez* or *\*.pqx* file) and place it in the *Custom Connectors* directory.</span></span>

3.  <span data-ttu-id="74cfc-112">**如果连接器文件是* \*mez*文件，\*\* 则还需要调整您的安全设置，如[自定义连接器设置文档](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security)中所述。</span><span class="sxs-lookup"><span data-stu-id="74cfc-112">**If the connector file is a *\*.mez* file,** you will also need to adjust your security settings as described in the [custom connector setup documentation](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security).</span></span>

<span data-ttu-id="74cfc-113">如果已释放此 Power BI Connector for Microsoft 团队的新版本，只需将*自定义连接器*目录中的旧的连接线文件替换为新文件。</span><span class="sxs-lookup"><span data-stu-id="74cfc-113">If a new version of this Power BI Connector for Microsoft Teams is released, simply replace the old connector file in the *Custom Connectors* directory with the new file.</span></span>

## <a name="setup"></a><span data-ttu-id="74cfc-114">设置</span><span class="sxs-lookup"><span data-stu-id="74cfc-114">Setup</span></span>

<span data-ttu-id="74cfc-115">为了生成报表并运行查询，首先需要连接到 CQD 数据源。</span><span class="sxs-lookup"><span data-stu-id="74cfc-115">In order to build a report and run queries, you will first need to connect to the CQD data source.</span></span> <span data-ttu-id="74cfc-116">请按照以下步骤进行连接：</span><span class="sxs-lookup"><span data-stu-id="74cfc-116">Follow the steps below in order to connect:</span></span>

1.  <span data-ttu-id="74cfc-117">在 Power BI Desktop 的 "开始" 选项卡中，单击 "*获取数据*"。</span><span class="sxs-lookup"><span data-stu-id="74cfc-117">In the Home tab of Power BI Desktop, click on *Get Data*.</span></span>

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector1.png)

2.  <span data-ttu-id="74cfc-119">此时应显示 "*获取数据*" 窗口。</span><span class="sxs-lookup"><span data-stu-id="74cfc-119">The *Get Data* window should appear at this point.</span></span> <span data-ttu-id="74cfc-120">导航到 "*联机服务*"，然后选择 " *Microsoft 通话质量（Beta）* " 和 "点击*连接*"。</span><span class="sxs-lookup"><span data-stu-id="74cfc-120">Navigate to *Online Services*, then select *Microsoft Call Quality (Beta)* and hit *Connect*.</span></span>

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector2.png)

3.  <span data-ttu-id="74cfc-122">系统将提示您登录下一步。</span><span class="sxs-lookup"><span data-stu-id="74cfc-122">You will be prompted to login next.</span></span> <span data-ttu-id="74cfc-123">使用与用于 CQD 的凭据相同的凭据。<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="74cfc-123">Use the same credentials that you use for CQD.<sup>2</sup></span></span>

4.  <span data-ttu-id="74cfc-124">下一条提示将为你提供两种*数据连接模式*之间的选项。</span><span class="sxs-lookup"><span data-stu-id="74cfc-124">The next prompt will give you the option between two *Data Connectivity modes*.</span></span> <span data-ttu-id="74cfc-125">选择 " *DirectQuery* "，然后点击 *"确定"*。</span><span class="sxs-lookup"><span data-stu-id="74cfc-125">Select *DirectQuery* and hit *OK*.</span></span>

5.  <span data-ttu-id="74cfc-126">最后，你将获得最终提示，显示 CQD 的整个数据模型。</span><span class="sxs-lookup"><span data-stu-id="74cfc-126">Finally, you will be given a final prompt showing you the entire data model for CQD.</span></span> <span data-ttu-id="74cfc-127">在此情况下，将仅显示数据，CQD 的数据模型。</span><span class="sxs-lookup"><span data-stu-id="74cfc-127">No data will be visible at this point, only the data model for CQD.</span></span> <span data-ttu-id="74cfc-128">选择 "*加载*" 以完成设置过程。</span><span class="sxs-lookup"><span data-stu-id="74cfc-128">Select *Load* to complete the setup process.</span></span>

6.  <span data-ttu-id="74cfc-129">此时，Power BI 会将数据模型加载到窗口右侧。</span><span class="sxs-lookup"><span data-stu-id="74cfc-129">At this point, Power BI will load the data model onto the right side of the window.</span></span> <span data-ttu-id="74cfc-130">该页将保留为空，并且默认情况下不会加载任何查询。</span><span class="sxs-lookup"><span data-stu-id="74cfc-130">The page will remain otherwise blank, and no queries will be loaded by default.</span></span> <span data-ttu-id="74cfc-131">继续**构建以下查询**，以便构建查询并返回数据。</span><span class="sxs-lookup"><span data-stu-id="74cfc-131">Proceed to **Building Queries** below in order to build a query and return data.</span></span>

<span data-ttu-id="74cfc-132">如果此设置过程中的任何步骤不完全明确，可在[此处](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data)找到更详细的流程说明。</span><span class="sxs-lookup"><span data-stu-id="74cfc-132">If any of the steps during this setup process were not completely clear, a more detailed explanation of the process can be found [here](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data).</span></span>

## <a name="building-queries"></a><span data-ttu-id="74cfc-133">构建查询</span><span class="sxs-lookup"><span data-stu-id="74cfc-133">Building Queries</span></span>

<span data-ttu-id="74cfc-134">安装完成后，应在 "*字段*" 窗格中看到几百个维度的名称和度量值的加载。</span><span class="sxs-lookup"><span data-stu-id="74cfc-134">Once setup is complete, you should see the names of several hundred dimensions and measures load in the *Fields* pane.</span></span> <span data-ttu-id="74cfc-135">从此处构建实际查询非常简单，只需选择所需的查询的维度和度量值，然后将其拖放到页面上。</span><span class="sxs-lookup"><span data-stu-id="74cfc-135">Constructing actual queries from here is simple, just select the dimensions and measures you want for your query, then drag and drop them onto the page.</span></span> <span data-ttu-id="74cfc-136">下面是更详细的说明，有一个简单的示例：</span><span class="sxs-lookup"><span data-stu-id="74cfc-136">Here’s a more detailed explanation, with a simple example:</span></span>

1.  <span data-ttu-id="74cfc-137">从 "*可视化*" 窗格中选择要使用的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="74cfc-137">Select the visualization you want to use from the *Visualizations* pane.</span></span> <span data-ttu-id="74cfc-138">该可视化对象的空白版本应显示在页面上。</span><span class="sxs-lookup"><span data-stu-id="74cfc-138">A blank version of that visualization should appear on the page.</span></span> <span data-ttu-id="74cfc-139">对于此示例，我们将使用*表格*可视化效果。</span><span class="sxs-lookup"><span data-stu-id="74cfc-139">For the purposes of this example, we will be using the *Table* visualization.</span></span>

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector3.png)

2.  <span data-ttu-id="74cfc-141">确定要用于查询的维度和度量值（由聚合符号表示），然后手动选择它们并将其拖动到黑色可视化效果中。</span><span class="sxs-lookup"><span data-stu-id="74cfc-141">Determine which dimensions and measures (denoted by an aggregation symbol by their name) you wish to use for your query, then manually select them and drag them onto the black visualization.</span></span> <span data-ttu-id="74cfc-142">或者，将其拖动到 "可视化" 选项下方的 "*值*" 字段。</span><span class="sxs-lookup"><span data-stu-id="74cfc-142">Alternately, drag them onto the *Values* field beneath the visualization options.</span></span>

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector4.png)

<span data-ttu-id="74cfc-144">**重要说明：** 通话质量仪表板要求运行任何查询的度量值。</span><span class="sxs-lookup"><span data-stu-id="74cfc-144">**Important Note:** Call Quality Dashboard requires a measure for any query to run.</span></span> <span data-ttu-id="74cfc-145">无法将度量值添加到查询将导致该查询失败。</span><span class="sxs-lookup"><span data-stu-id="74cfc-145">Failure to add a measure to a query will cause that query to fail.</span></span>

3.  <span data-ttu-id="74cfc-146">接下来，选择要筛选的任何维度，并将其拖动到 "*筛选器*" 窗格中*此视觉字段上的筛选器*。</span><span class="sxs-lookup"><span data-stu-id="74cfc-146">Next, select any dimensions you want to filter on and drag them to the *Filters on this visual* field in the *Filters* pane.</span></span> <span data-ttu-id="74cfc-147">CQD Power BI 连接器当前支持*基本筛选*（从可能的维度值列表中选择值）、*高级筛选*（手动指定值和要筛选的操作数，类似于高级 CQD），以及*相对日期筛选*（仅适用于 "*结束时间*" 和 "*开始时间*" 维度）。</span><span class="sxs-lookup"><span data-stu-id="74cfc-147">The CQD Power BI Connector currently supports *Basic filtering* (select values from a list of possible dimension values), *Advanced filtering* (manually specify values and operands to filter on, similar to Advanced CQD), and *Relative date filtering* (only available for the *End Time* and *Start Time* dimensions).</span></span> <span data-ttu-id="74cfc-148">CQD 不支持按*Top N*进行筛选。</span><span class="sxs-lookup"><span data-stu-id="74cfc-148">Filtering according to *Top N* is not supported by CQD.</span></span>

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector5.png)

4.  <span data-ttu-id="74cfc-150">最后，选择 "*可视化*" 窗格中的 "*格式*" 选项卡以设置查询样式并设置其格式。</span><span class="sxs-lookup"><span data-stu-id="74cfc-150">Finally, select the *Format* tab within the *Visualizations* pane to style and format your query.</span></span>

<span data-ttu-id="74cfc-151">**注意：** CQD 查询至少需要一个度量值才能运行。</span><span class="sxs-lookup"><span data-stu-id="74cfc-151">**Note:** CQD queries require at least one measure in order to run.</span></span> <span data-ttu-id="74cfc-152">如果查询未加载，请仔细检查查询中是否已包含度量值。</span><span class="sxs-lookup"><span data-stu-id="74cfc-152">If your query does not load, double check that you have included a measure in the query.</span></span>

## <a name="creating-a-drillthrough-report"></a><span data-ttu-id="74cfc-153">创建钻取报表</span><span class="sxs-lookup"><span data-stu-id="74cfc-153">Creating a Drillthrough Report</span></span>

<span data-ttu-id="74cfc-154">[POWER BI 中的钻取](https://docs.microsoft.com/power-bi/desktop-drillthrough)允许你创建具有焦点的报表，你可以使用其他报表的值作为上下文快速筛选。</span><span class="sxs-lookup"><span data-stu-id="74cfc-154">[Drillthrough in Power BI](https://docs.microsoft.com/power-bi/desktop-drillthrough) allows you to create focused reports that you can quickly filter using the values of other reports as context.</span></span> <span data-ttu-id="74cfc-155">了解如何使用 CQD 连接器创建你的第一个查询后，创建钻取变得更简单。</span><span class="sxs-lookup"><span data-stu-id="74cfc-155">Once you know how to create your first query with the CQD Connector, creating a drillthrough is even simpler.</span></span>

1.  <span data-ttu-id="74cfc-156">为焦点报表创建另一页，然后将查询添加到该页面。</span><span class="sxs-lookup"><span data-stu-id="74cfc-156">Create another page for the focused report, and then add your queries to that page.</span></span>

2.  <span data-ttu-id="74cfc-157">选择要用作钻取筛选器的维度，并将其拖到 "*可视化*" 窗格上的 "*钻取*" 字段中。</span><span class="sxs-lookup"><span data-stu-id="74cfc-157">Select the dimension you want to use as a drillthrough filter and drag them onto the *Drillthrough* field under on the *Visualizations* pane.</span></span>

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector6.png)

3.  <span data-ttu-id="74cfc-159">**就是这样\!**</span><span class="sxs-lookup"><span data-stu-id="74cfc-159">**That’s it\!**</span></span> <span data-ttu-id="74cfc-160">其他使用该维度的页面上的任何其他查询现在都可以钻取到该页面，并自动将钻取维度的值应用为筛选器。</span><span class="sxs-lookup"><span data-stu-id="74cfc-160">Any other query on another page that uses that dimension can now drillthrough to that page, automatically applying the drillthrough dimension’s value as a filter.</span></span>

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector7.png)

<span data-ttu-id="74cfc-162">与高级 CQD 不同，Power BI 支持非顺序钻取。</span><span class="sxs-lookup"><span data-stu-id="74cfc-162">Unlike Advanced CQD, Power BI supports non-sequential drillthrough.</span></span> <span data-ttu-id="74cfc-163">只要查询包含必要的维度，它就可以钻取到任何其他页面。</span><span class="sxs-lookup"><span data-stu-id="74cfc-163">So long as a query includes the necessary dimension, it can drillthrough to any other page.</span></span>

## <a name="limitations"></a><span data-ttu-id="74cfc-164">优缺点</span><span class="sxs-lookup"><span data-stu-id="74cfc-164">Limitations</span></span>

<span data-ttu-id="74cfc-165">尽管使用 Power BI，但并非所有 Power BI 功能都是由 CQD 连接器支持的，这是由于 CQD 数据模型或对 DirectQuery 连接器的限制。</span><span class="sxs-lookup"><span data-stu-id="74cfc-165">Despite making use of Power BI, not all Power BI functionality is support by the CQD Connector, either as a result of limitations on CQD data model or on DirectQuery connectors in general.</span></span> <span data-ttu-id="74cfc-166">下面的列表显示了其他连接线的一些更值得注意的限制，但此列表不应被认为是详尽的：</span><span class="sxs-lookup"><span data-stu-id="74cfc-166">The list below notes some of the Connector’s more noteworthy limitations, but this list should not be considered exhaustive:</span></span>

1.  <span data-ttu-id="74cfc-167">**计算列-** DirectQuery 连接器通常对 Power BI 中的计算列有有限支持。</span><span class="sxs-lookup"><span data-stu-id="74cfc-167">**Calculated Columns –** DirectQuery connectors in general have limited support for calculated columns in Power BI.</span></span> <span data-ttu-id="74cfc-168">虽然某些计算列可能与连接线一起使用，但这些计算列应视为异常。</span><span class="sxs-lookup"><span data-stu-id="74cfc-168">While some calculated columns may work with the Connector, these should be considered exceptions.</span></span> <span data-ttu-id="74cfc-169">作为一般规则，计算列将不起作用。</span><span class="sxs-lookup"><span data-stu-id="74cfc-169">As a general rule, calculated columns will not function.</span></span>

2.  <span data-ttu-id="74cfc-170">**聚合-** CQD 数据模型基于多维数据集模型构建，这意味着聚合在度量形式中已受支持。</span><span class="sxs-lookup"><span data-stu-id="74cfc-170">**Aggregations –** The CQD data model is built on a cube model, meaning that aggregations are already supported in the form of measures.</span></span> <span data-ttu-id="74cfc-171">尝试手动将聚合添加到不同的维度或更改度量值的聚合类型将不会与连接器一起使用，并且通常会导致错误。</span><span class="sxs-lookup"><span data-stu-id="74cfc-171">Attempting to manually add aggregations to different dimensions or changing the aggregation type of a measure will not work with the Connector, and it will generally result in an error.</span></span>

3.  <span data-ttu-id="74cfc-172">**自定义视觉对象-** 虽然 CQD 连接器与一系列自定义视觉对象一起工作，但我们无法保证与所有自定义视觉对象的兼容性。</span><span class="sxs-lookup"><span data-stu-id="74cfc-172">**Custom Visuals –** While the CQD Connector does work with a range of custom visuals, we are unable to guarantee compatibility with all custom visuals.</span></span> <span data-ttu-id="74cfc-173">许多自定义视觉对象依赖于使用计算列或导入的数据，而不受 DirectQuery 连接线支持。</span><span class="sxs-lookup"><span data-stu-id="74cfc-173">Many custom visuals rely on the use of calculated columns or imported data, neither or which are supported by DirectQuery connectors.</span></span>

4.  <span data-ttu-id="74cfc-174">**引用缓存的数据-** Power BI 目前不支持以任何方式引用 DirectQuery 连接器中的缓存数据。</span><span class="sxs-lookup"><span data-stu-id="74cfc-174">**Referencing Cached Data –** Power BI currently does not support referencing cached data from a DirectQuery connector in any way.</span></span> <span data-ttu-id="74cfc-175">任何引用查询结果的尝试都将导致新查询。</span><span class="sxs-lookup"><span data-stu-id="74cfc-175">Any attempt to reference the results of a query will result in a new query.</span></span>

5.  <span data-ttu-id="74cfc-176">**相对数据筛选-** 在 CQD 连接器中受支持，但仅限 "*开始时间*" 和 "*结束时间*" 维度。</span><span class="sxs-lookup"><span data-stu-id="74cfc-176">**Relative Data Filtering –** Is supported in the CQD Connector, but only with the *Start Time* and *End Time* dimensions.</span></span> <span data-ttu-id="74cfc-177">虽然*日期*维度可能是相对日期筛选的明显选择，但*日期*不会存储为日期时间对象，因此不支持 Power BI 中的相对日期筛选。</span><span class="sxs-lookup"><span data-stu-id="74cfc-177">Although the *Date* dimension may be the obvious choice for relative date filtering, *Date* is not stored as a date time object and thus does not support relative date filtering in Power BI.</span></span>

<span data-ttu-id="74cfc-178">请注意，虽然连接线在预览中，但这些限制不太可能与连接器的最终版本一起更改。</span><span class="sxs-lookup"><span data-stu-id="74cfc-178">Please note, although the Connector is in preview, these limitations are unlikely to change with the final release of the Connector.</span></span> <span data-ttu-id="74cfc-179">大多数问题都是对 CQD 数据模型设计而言，Power BI 或基础中的 DirectQuery 连接器设计的限制。</span><span class="sxs-lookup"><span data-stu-id="74cfc-179">Most of these issues are either restrictions to DirectQuery connector design in Power BI or fundamental to the design of the CQD data model.</span></span>

## <a name="error-codes"></a><span data-ttu-id="74cfc-180">错误代码</span><span class="sxs-lookup"><span data-stu-id="74cfc-180">Error Codes</span></span>

<span data-ttu-id="74cfc-181">由于 CQD Power BI 连接器的限制与你可以构造的查询种类的浏览器应用的限制更小，因此在构建查询时可能偶尔会遇到许多错误。</span><span class="sxs-lookup"><span data-stu-id="74cfc-181">Because the CQD Power BI Connector is less restricted than the browser app in terms of kinds of queries you can construct, you may occasionally encounter a number of errors while building your queries.</span></span> <span data-ttu-id="74cfc-182">在收到类型为 "CQDError" 的错误消息的情况中。</span><span class="sxs-lookup"><span data-stu-id="74cfc-182">In the event that you receive an error message of the type “CQDError.</span></span> <span data-ttu-id="74cfc-183">RunQuery-查询执行错误 "，请在下面的列表中引用所提供的 ErrorType 数字，以便对查询可能存在的问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="74cfc-183">RunQuery – Query Execution Error”, reference the list below with the ErrorType number provided in order to troubleshoot the possible issue with the query.</span></span> <span data-ttu-id="74cfc-184">以下是你可能遇到的 CQD Power BI 连接器最常见的错误类型代码：</span><span class="sxs-lookup"><span data-stu-id="74cfc-184">The following are the most common Error Type codes you may encounter with the CQD Power BI Connector:</span></span>

  - <span data-ttu-id="74cfc-185">**ErrorType 1-查询结构错误：** 查询结构错误通常是由连接器无法生成格式正确的查询导致的。</span><span class="sxs-lookup"><span data-stu-id="74cfc-185">**ErrorType 1 - Query Structure Error:** A query structure error is typically caused by the Connector failing to build a properly formatted query.</span></span> <span data-ttu-id="74cfc-186">这种情况最常发生于使用不受支持的功能时，如以上限制中所述。</span><span class="sxs-lookup"><span data-stu-id="74cfc-186">This happens most often when using unsupported functionality, as specified in the Limitations above.</span></span> <span data-ttu-id="74cfc-187">仔细检查你没有为该查询使用任何计算列或自定义视觉对象。</span><span class="sxs-lookup"><span data-stu-id="74cfc-187">Double check that you are not using any calculated columns or custom visuals for that query.</span></span>

  - <span data-ttu-id="74cfc-188">**ErrorType 2-查询构建错误：** 查询生成错误是由 CQD 连接器无法正确分析你试图构建的查询所导致的。</span><span class="sxs-lookup"><span data-stu-id="74cfc-188">**ErrorType 2 - Query Building Error:** A query building error is caused by the CQD Connector being unable to properly parse the query you are attempting to build.</span></span> <span data-ttu-id="74cfc-189">这种情况最常发生于使用不受支持的功能时，如以上限制中所述。</span><span class="sxs-lookup"><span data-stu-id="74cfc-189">This happens most often when using unsupported functionality, as specified in the Limitations above.</span></span> <span data-ttu-id="74cfc-190">仔细检查你没有为该查询使用任何计算列或自定义视觉对象。</span><span class="sxs-lookup"><span data-stu-id="74cfc-190">Double check that you are not using any calculated columns or custom visuals for that query.</span></span>

  - <span data-ttu-id="74cfc-191">**ErrorType 5-执行超时：** 查询在超时之前已达到最大可能的运行时。尝试向查询添加更多筛选器，以便限制其范围。</span><span class="sxs-lookup"><span data-stu-id="74cfc-191">**ErrorType 5 - Execution Timeout:** The query has reached the maximum possible runtime before timing out. Try adding more filters to the query in order to limit its scope.</span></span> <span data-ttu-id="74cfc-192">缩小数据区域通常是实现此目的的最有效方式。</span><span class="sxs-lookup"><span data-stu-id="74cfc-192">Narrowing the data range is often the most effective way to achieve this.</span></span>

  - <span data-ttu-id="74cfc-193">**ErrorType 7-无测量错误：** CQD 查询需要一个度量单位才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="74cfc-193">**ErrorType 7 - No Measurements Error:** CQD queries require a measure in order to function.</span></span> <span data-ttu-id="74cfc-194">仔细检查查询是否包含度量值。</span><span class="sxs-lookup"><span data-stu-id="74cfc-194">Double check that your query includes measure.</span></span> <span data-ttu-id="74cfc-195">CQD 连接器中的度量值在其名称前由聚合（sum）符号表示。</span><span class="sxs-lookup"><span data-stu-id="74cfc-195">Measures in the CQD Connector are denoted by the aggregation (sum) symbol before their name.</span></span>

<span data-ttu-id="74cfc-196">如果您在此范围外遇到任何其他错误，请通知 CQD 团队，以便我们能够帮助您解决问题，并根据需要更新文档。</span><span class="sxs-lookup"><span data-stu-id="74cfc-196">If you encounter any additional errors outside of this scope, please notify the CQD team so that we can help troubleshoot the issue and update the documentation as appropriate.</span></span>

## <a name="footnotes"></a><span data-ttu-id="74cfc-197">页脚</span><span class="sxs-lookup"><span data-stu-id="74cfc-197">Footnotes</span></span>

<span data-ttu-id="74cfc-198">**<sup>1</sup>** 某些流程和应用（例如，OneDrive）可能会导致您的文档根文件夹发生更改;请确保*POWER BI 桌面\\自定义连接器*目录位于当前根文件夹 "文档" 文件夹内。</span><span class="sxs-lookup"><span data-stu-id="74cfc-198">**<sup>1</sup>** Certain processes and apps (e.g. OneDrive) may cause your Documents root folder to change; make sure that the *Power BI Desktop\\Custom Connectors* directory is placed inside of the current root folder Documents folder.</span></span>

<span data-ttu-id="74cfc-199">**<sup>2</sup>** 用于 CQD 的登录凭据*不*需要与用于登录到 power BI 桌面应用本身的凭据相同。</span><span class="sxs-lookup"><span data-stu-id="74cfc-199">**<sup>2</sup>** The login credentials you use for CQD *do not* need to be the same credentials you use for logging into the Power BI Desktop app itself.</span></span>



## <a name="related-topics"></a><span data-ttu-id="74cfc-200">相关主题</span><span class="sxs-lookup"><span data-stu-id="74cfc-200">Related topics</span></span>

[<span data-ttu-id="74cfc-201">使用 Power BI 分析团队的 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="74cfc-201">Use Power BI to analyze CQD data for Teams</span></span>](CQD-Power-BI-query-templates.md)