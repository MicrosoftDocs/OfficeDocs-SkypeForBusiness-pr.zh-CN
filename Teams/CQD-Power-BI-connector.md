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
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>安装 Power BI 连接器以使用 CQD 查询模板

在使用 Power BI 查询模板 (PBIX 文件) for Microsoft Teams 呼叫质量仪表板 (CQD) 之前，你需要使用下载中包含的 *MicrosoftCallQuality.pqx* 文件安装适用于 Microsoft CQD 的 Power BI 连接器 [。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

请阅读使用 Power BI 分析 Teams 的 [CQD](CQD-Power-BI-query-templates.md) 数据，了解这些模板。

请确保拥有适当的 [CQD 访问角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 来访问 Power BI 报表。

> [!NOTE]
> CQD Power BI 连接器仅支持 Power BI 中的 DirectQuery;不支持导入模式。 

## <a name="installation"></a>安装

Power BI 文档中详细介绍了安装自定义连接器和调整安全性以启用 [连接器使用的过程](/power-bi/desktop-connector-extensibility)。 为简单起见，下面是一个快速说明：

1. 检查计算机是否已有"文档 *\[ \] \\ "Power BI Desktop \\ 自定义连接器* 文件夹。 如果没有，请创建此文件夹。<sup>1</sup>

2. 将连接器文件 (*\* .mez* 或 *\* .pqx* 文件) 并放在 *自定义连接器* 目录中。

3. **如果连接器文件是 *\* .mez*** 文件，则还需要根据自定义连接器设置文档 中所述调整 [安全设置](/power-bi/desktop-connector-extensibility#data-extension-security)。

如果已发布此 Power BI Connector for Microsoft Teams 的新版本，只需将自定义连接器目录中的旧连接器文件替换为新文件。

## <a name="setup"></a>设置

若要生成报表并运行查询，首先需要连接到 CQD 数据源。 请按照以下步骤进行连接：

1. 在 Power BI Desktop 的"开始"选项卡中，单击"*获取数据"。*

    ![屏幕截图：Power BI 连接器](media/CQD-power-bi-connector1-resize.png)

2. 此时 *应会显示* "获取数据"窗口。 导航到 *"联机服务"，* 然后选择"Microsoft 呼叫质量 *" (Beta) 并点击"连接**"。*

    ![屏幕截图：Power BI 连接器](media/CQD-power-bi-connector2-resize.png)

3. 系统会提示你下一步登录。 使用用于 CQD 的相同凭据。<sup>2</sup>

4. 下一个提示会提供两种数据连接 *模式之间的选项*。 选择 *"DirectQuery"，* 并点击"*确定"。*

5. 最后，系统会提供最终提示，显示 CQD 的整个数据模型。 此时将看不到任何数据，只有 CQD 的数据模型可见。 选择 *"* 加载"完成设置过程。

6. 此时，Power BI 将数据模型加载到窗口右侧。 页面将保留为空，默认情况下不会加载任何查询。 继续 **下面的生成查询** ，以便生成查询并返回数据。

如果此设置过程中的任何步骤不完全清晰，可以在快速入门：连接到 Power BI Desktop 中的数据中找到该过程 [的更详细说明](/power-bi/desktop-quickstart-connect-to-data)。

## <a name="building-queries"></a>生成查询

设置完成后，"字段"窗格中应显示数百个维度的名称和 *度量负载* 。 从此处构造实际查询非常简单，只需选择查询的维度和度量值，然后将其拖放到页面上。 下面是一个包含简单示例的更详细说明：

1. 从"可视化"窗格中选择 *想要使用的可视化* 效果。 该可视化效果的空白版本应显示在页面上。 对于此示例，我们将使用表 *可视化* 效果。

    ![屏幕截图：Power BI 连接器](media/CQD-power-bi-connector3-resize.png)

2. 确定聚合符号 (其名称表示的维度和度量值) 用于查询，然后手动选择它们并将其拖动到黑色可视化效果上。 或者，将它们拖动到可视化 *选项下的* "值"字段。

    ![屏幕截图：Power BI 连接器](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > 调用质量仪表板要求测量要运行的任何查询。 未能向查询添加度量值将导致该查询失败。

3. 接下来，选择要筛选的任何维度，并将其拖动到"筛选器"窗格中 *此可视* 字段上的 *"筛选器* "。 CQD Power BI 连接器目前支持基本筛选 (从可能维度值) 列表中选择值;高级筛选 *(* 手动指定要筛选的值和操作数，类似于高级 CQD) ;相对日期筛选 *(* 仅适用于结束时间和开始时间维度) 。    CQD 不支持根据 *前 N* 个进行筛选。

    ![屏幕截图：Power BI 连接器](media/CQD-power-bi-connector5-resize.png)

4. 最后， *选择"可视化* 效果"窗格中 *的"* 格式"选项卡，设置查询的样式和格式。

    > [!NOTE]
    > CQD 查询至少需要一个度量值才能运行。 如果查询未加载，请仔细检查查询中是否包含度量值。

## <a name="creating-a-drillthrough-report"></a>创建钻取报表

[Power BI 中的钻](/power-bi/desktop-drillthrough) 取允许你创建具有焦点的报表，可以使用其他报表的值作为上下文快速筛选这些报表。 了解如何使用 CQD 连接器创建第一个查询后，创建钻取会更简单。

1. 为重点报表创建另一个页面，然后将查询添加到该页。

2. 选择要用作钻取筛选器的维度，并将其拖动到"可视化"窗格下的 *"钻* 取 *"* 字段。

    ![屏幕截图：Power BI 连接器](media/CQD-power-bi-connector6-resize.png)

3. **就是这样\!** 现在，使用该维度的另一页上的其他任何查询都可以钻取到该页面，自动将钻取维度的值作为筛选器应用。

    ![屏幕截图：Power BI 连接器](media/CQD-power-bi-connector7-resize.png)

与高级 CQD 不同，Power BI 支持非连续钻取。 只要查询包含必要的维度，它就可以钻取到任何其他页面。

### <a name="best-practice"></a>最佳做法

在设计调用质量连接器查询时，应牢记钻取功能。 从更广泛的低基数查询开始，向下钻取到高基数查询，而不是尝试一次加载所有数据，然后使用筛选器进行切片。 例如，尝试诊断哪些子网对质量问题影响最大时，首先确定导致该问题的区域和/地区，然后向下钻取到该区域或国家/地区的子网会很有帮助。 呼叫质量连接器模板的设计方式就是为了作为示例。

## <a name="limitations"></a>限制

尽管使用 Power BI，但并非所有 Power BI 功能都受 CQD 连接器的支持，无论是由于 CQD 数据模型的限制还是 DirectQuery 连接器的一般限制。 以下列表列出了连接器的一些更值得注意的限制，但不应将此列表视为详尽：

1. **计算列 –** DirectQuery 连接器通常对 Power BI 中的计算列的支持有限。 虽然某些计算列可能与连接器一起工作，但应认为这些列例外。 一般而言，计算列将无法正常工作。

2. **聚合 –** CQD 数据模型构建在多维数据集模型上，这意味着已支持度量形式的聚合。 尝试手动将聚合添加到不同的维度或更改度量值的聚合类型将不起作用连接器，并且通常会导致错误。

3. **自定义视觉对象 –** 虽然 CQD 连接器可以处理一系列自定义视觉对象，但我们无法保证与所有自定义视觉对象的兼容性。 许多自定义视觉对象依赖于使用计算列或导入的数据，而 DirectQuery 连接器不支持 或 。

4. **引用缓存数据 –** Power BI 当前不支持从 DirectQuery 连接器以任何方式引用缓存的数据。 任何引用查询结果的尝试都将导致新的查询。

5. **相对数据筛选 –** 在 CQD 连接器中受支持，但仅支持"开始时间"*和"**结束时间"* 维度。 虽然 *"日期* "维度可能是相对日期筛选的明显选择，但 *日期* 不存储为日期时间对象，因此不支持 Power BI 中的相对日期筛选。

6. **政府社区云 (GCC) 支持 –** 对于 GCC 环境中的客户，使用 Power BI Desktop 时，CQD Power BI 连接器将正常工作。 CQD Power BI 连接器目前与 GCC 客户的 Power BI 服务不兼容。

大多数这些问题是 Power BI 中 DirectQuery 连接器设计的限制，或者是 CQD 数据模型设计的基础。

## <a name="troubleshooting"></a>疑难解答

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>我正在尝试使用"日期"列作为日期切片器。 将此列的数据类型转换为日期后，就会收到此错误

> **无法加载此视觉对象的数据**：OLE DB 或 ODBC 错误：[Expression.Error] 无法将表达式折叠到数据源。 请尝试更简单的表达式。

Power BI 连接器不支持日期切片器。 若要指定日期范围，请对报表应用两个筛选器，指定小于和大于日期。

或者，如果要查看的日期是最近的日期，请应用相对日期筛选器以仅显示过去 N 天/周/月的数据。

## <a name="error-codes"></a>错误代码

由于 CQD Power BI 连接器在可构造的查询类型方面比浏览器应用的限制更少，因此在构建查询时，有时可能会遇到许多错误。 如果收到"CQDError"类型的错误消息。 RunQuery – 查询执行错误"，使用提供的 ErrorType 编号引用以下列表，以排查查询可能出现的问题。 以下是使用 CQD Power BI 连接器时可能会遇到的最常见错误类型代码：

- **ErrorType 1 - 查询结构错误：** 查询结构错误通常是由于连接器未能生成格式正确的查询导致的。 使用不受支持的功能时（如上述限制中指定）时，通常会发生这种情况。 仔细检查是否未对查询使用任何计算列或自定义视觉对象。

  - **ErrorType 2 - 查询生成错误：** 查询生成错误是由 CQD 连接器无法正确分析尝试构建的查询导致的。 使用不受支持的功能时（如上述限制中指定）时，通常会发生这种情况。 仔细检查是否未对查询使用任何计算列或自定义视觉对象。

  - **ErrorType 5 - 执行超时：** 在超时之前，查询已达到可能的最大运行时。尝试向查询添加更多筛选器，以限制其范围。 缩小数据范围通常是实现此目的最有效的方法。

  - **ErrorType 7 - 无度量错误：** CQD 查询需要一个度量值才能运行。 仔细检查查询是否包含度量值。 CQD 连接器中的度量值由聚合值 (其名称) 和符号表示。

如果在此范围之外遇到任何其他错误，请通知 CQD 团队，以便我们可以帮助排查问题并适当地更新文档。

## <a name="footnotes"></a>脚注

**<sup>1</sup>** 某些进程 (应用，例如 OneDrive) 可能会导致"文档"根文件夹更改;确保 Power *BI Desktop \\ 自定义连接器* 目录放置在当前根文件夹"文档"文件夹中。

**<sup>2</sup>** 用于 CQD 的登录凭据不需要与用于登录 Power BI Desktop 应用本身的凭据相同。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>何时从"Beta"状态更新 Power BI 连接器

尽管使用 Beta 标记，但 Power BI 的呼叫质量连接器是连接器的发布版本，已经过 Power BI 团队正式签名，以反映这一点。 删除该 Beta 标记的认证过程是一个广泛的过程，需要 Power BI 团队做出承诺，同时为连接器提供直接支持。 由于时间限制，Power BI 团队当前无法提供该支持和更广泛的认证，但仍准备证明 Microsoft 呼叫质量连接器的安全性、真实性和一般功能。

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>与浏览器中的高级 CQD 相比，连接器为何看起来较慢？ 可以执行哪些功能来提高性能

在浏览器和连接器中，各种模板的查询性能实际上是相同的。  与其他任何独立应用一样，Power BI 将身份验证和呈现时间添加到我们的性能。 此外，差异在于运行的并发查询数。 由于 CQD 的浏览器内版本具有开发较少且信息密集型的可视化选项，因此我们的大多数报告限制为一次加载 2-3 个查询。 另一方面，连接器模板通常显示 20 多个并发查询。 如果希望生成的响应与以前使用的报表一样高，请尝试创建每个选项卡不超过 2-3 个查询的报表。

有关详细信息，请参阅以下文章：

- [Power BI 优化指南](/power-bi/guidance/power-bi-optimization)
- [DirectQuery 模型指南](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>在运行查询时，我发现自己经常遇到 10，000 行的限制。 如何让连接器返回超过 10，000 行

API 端实际指定了 10，000 行的限制，旨在帮助显著提高性能并降低因内存不足导致查询执行错误的风险。

最好根据连接器最佳做法重构报表，而不是尝试增加结果行计数。 我们包含的模板旨在演示这些最佳做法。 在可能的情况下，首先使用更大、基数较低的维度（如月、年、日期、区域、国家/地区等）查看 KPI。从该维度中，可以向下钻取到基数越高的维度。 支持人员报表Location-Enhanced报表都提供了此向下钻取工作流的良好示例。



## <a name="related-topics"></a>相关主题

[使用 Power BI 分析 Teams 的 CQD 数据](CQD-Power-BI-query-templates.md)
