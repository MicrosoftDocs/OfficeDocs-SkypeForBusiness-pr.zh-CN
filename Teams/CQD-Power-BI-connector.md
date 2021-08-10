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
ms.openlocfilehash: 388dddc683340238ccff968261595bd46d4bfc65e323cfd1929f699d3c5eed83
ms.sourcegitcommit: 02485b5f4bc8de106b064adf5c96dfc041f64e34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2021
ms.locfileid: "57799053"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>安装 Microsoft 呼叫质量连接器Power BI使用呼叫质量仪表板查询模板

在使用 Power BI 查询模板 (PBIX 文件) for Microsoft Teams 呼叫质量仪表板 (CQD) 之前，需使用下载中包含的 *MicrosoftCallQuality.pqx* 文件安装适用于 Power BI 的 Microsoft 呼叫质量 [连接器。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

请参阅[使用Power BI分析 CQD 数据Teams](CQD-Power-BI-query-templates.md)了解这些模板。

请确保拥有正确的[CQD 访问角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)，以访问Power BI报告。

> [!NOTE]
> Microsoft 呼叫质量连接器仅在 Power BI 中支持 DirectQuery;不支持导入模式。 

## <a name="installation"></a>安装

以下文档详细介绍了安装自定义连接器和调整安全性以启用[连接器使用Power BI过程](/power-bi/desktop-connector-extensibility)。 为简单起见，下面是一个快速说明：

1. 检查计算机是否已在"自定义连接器"文件夹中 *\[ \] \\ Power BI Desktop \\ 文档"。* 如果没有，请创建此文件夹。<sup>1</sup>

2. 将连接器文件 (*\* .mez* 或 *\* .pqx* 文件) 并放在 *自定义连接器* 目录中。

3. **如果连接器文件是 *\* .mez*** 文件，则还需要根据自定义连接器设置文档 中所述调整 [安全设置](/power-bi/desktop-connector-extensibility#data-extension-security)。

如果发布了新版本的 Microsoft 呼叫质量连接器，请将自定义连接器目录中的旧连接器文件替换为新文件。

## <a name="setup"></a>设置

若要生成报表并运行查询，首先需要连接到 CQD 数据源。 请按照以下步骤进行连接：

1. 在"开始"选项卡Power BI Desktop，单击"*获取数据"。*

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector1-resize.png)

2. 此时 *应会显示* "获取数据"窗口。 导航到 *"联机服务"，* 然后选择 *"Microsoft 呼叫质量 (Beta* 版) 并 *连接"*。

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector2-resize.png)

3. 系统会提示你下一步登录。 使用用于呼叫质量仪表板的相同凭据。<sup>2</sup>

4. 下一个提示会提供两种数据连接 *模式之间的选项*。 选择 *"DirectQuery"，* 并点击"*确定"。*

5. 最后，系统将提供最终提示，显示呼叫质量仪表板的整个数据模型。 此时将看不到任何数据，只有 CQD 的数据模型可见。 选择 *"* 加载"完成设置过程。

6. 此时，Power BI将数据模型加载到窗口右侧。 页面将保留为空，默认情况下不会加载任何查询。 继续 **下面的生成查询** ，以便生成查询并返回数据。

如果此设置过程中的任何步骤都不清楚，可以在快速入门：连接中查看有关[Power BI Desktop。](/power-bi/desktop-quickstart-connect-to-data)

## <a name="building-queries"></a>生成查询

设置完成后，"字段"窗格中应显示数百个维度的名称和 *度量负载* 。 从此处构造实际查询非常简单，只需选择查询的维度和度量值，然后将其拖放到页面上。 下面是一个包含简单示例的更详细说明：

1. 从"可视化"窗格中选择 *想要使用的可视化* 效果。 该可视化效果的空白版本应显示在页面上。 对于此示例，我们将使用表 *可视化* 效果。

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector3-resize.png)

2. 确定聚合符号 (其名称表示的维度和度量值) 用于查询，然后手动选择它们并将其拖动到黑色可视化效果上。 或者，将它们拖动到可视化 *选项下的* "值"字段。

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > 调用质量仪表板要求测量要运行的任何查询。 未能向查询添加度量值将导致该查询失败。

3. 接下来，选择要筛选的任何维度，并将其拖动到"筛选器"窗格中 *此可视* 字段上的 *"筛选器* "。 Microsoft 呼叫质量连接器目前支持基本筛选 (从可能维度值) 列表中选择值，高级筛选 (手动指定要筛选的值和操作数，类似于呼叫质量仪表板) ，而相对日期筛选 *(* 仅适用于"结束时间和开始时间"维度) 。    呼叫质量仪表板不支持根据 *前 N* 个进行筛选。

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > 筛选器仅在应用于维度时受支持。 通话质量仪表板中不支持筛选度量值。

4. 最后， *选择"可视化* 效果"窗格中 *的"* 格式"选项卡，设置查询的样式和格式。

    > [!NOTE]
    > 调用质量仪表板查询至少需要一个度量值才能运行。 如果查询未加载，请仔细检查查询中是否包含度量值。

## <a name="creating-a-drillthrough-report"></a>创建钻取报表

[使用 Power BI](/power-bi/desktop-drillthrough)中的钻取可创建具有焦点的报表，可以使用其他报表的值作为上下文快速筛选这些报表。 了解如何使用 Microsoft 呼叫质量连接器创建第一个查询后，创建钻取会更简单。

1. 为重点报表创建另一个页面，然后将查询添加到该页。

2. 选择要用作钻取筛选器的维度，并将其拖动到"可视化"窗格下的 *"钻* 取 *"* 字段。

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector6-resize.png)

3. **就是这样\!** 使用该维度的另一页上的其他任何钻取现在可以添加到该页面，并自动将钻取维度的值作为筛选器应用。

    ![屏幕截图：Power BI连接器](media/CQD-power-bi-connector7-resize.png)

与呼叫质量仪表板不同，Power BI支持非连续钻取。 如果查询包含必要的维度，它可以钻取任何其他页面。

### <a name="best-practice&quot;></a>最佳做法

设计 Microsoft 呼叫质量连接器查询时，应牢记钻取功能。 从更广泛的低基数查询开始，向下钻取到高基数查询，而不是尝试一次加载所有数据，然后使用筛选器进行切片。 例如，尝试诊断哪些子网对质量问题影响最大时，首先确定导致该问题的区域和/地区，然后向下钻取到该区域或国家/地区的子网会很有帮助。 呼叫质量连接器模板的设计方式就是为了作为示例。

## <a name=&quot;limitations&quot;></a>限制

尽管使用 Power BI，但并非所有 Power BI 功能都受 Microsoft 呼叫质量连接器的支持，无论是由于呼叫质量仪表板的数据模型限制还是 DirectQuery 连接器的一般限制。 以下列表列出了连接器的一些更值得注意的限制，但不应将此列表视为详尽：

1. **计算列 –** DirectQuery 连接器通常对计算列中的计算列的支持有限Power BI。 某些计算列可能与连接器一起工作，这些列例外。 一般而言，计算列不工作。

2. **聚合 –** 呼叫质量仪表板数据模型基于多维数据集模型，这意味着已支持度量形式的聚合。 尝试手动将聚合添加到不同的维度或更改度量值的聚合类型将不起作用连接器，并且通常会导致错误。

3. **自定义视觉对象 –** 虽然 Microsoft 呼叫质量连接器可以处理一系列自定义视觉对象，但我们无法保证与所有自定义视觉对象兼容。 许多自定义视觉对象依赖于使用计算列或导入的数据，DirectQuery 连接器不支持这两者。

4. **引用缓存数据 –** Power BI目前不支持从 DirectQuery 连接器以任何方式引用缓存的数据。 任何引用查询结果的尝试都将导致新的查询。

5. **相对数据筛选 –** 在 Microsoft 呼叫质量连接器中受支持，但仅支持&quot;开始时间&quot;*和&quot;**结束时间&quot;* 维度。 虽然 *&quot;日期*&quot;维度可能是相对日期筛选的明显选择，但日期不存储为日期时间对象，因此不支持在 Power BI。

6. **仅度量查询 -** Microsoft 呼叫质量连接器目前不支持 。 创建具有三个或多个度量且无维度的可视化效果时，将转置列数据。 若要避免这种情况，请始终在可视化 (至少包含一个维度：") 年"值。 这一问题预计将在即将发布的 Microsoft 呼叫质量连接器版本中解决，Power BI。

7. **政府社区云 (GCC) 支持 -** 对于在 GCC 环境中的客户，Microsoft 呼叫质量连接器仅在使用 Power BI Desktop 时工作。 Microsoft 呼叫质量连接器目前与 Power BI 服务GCC兼容。

这些问题中的大多数是 DirectQuery 连接器设计的限制Power BI是 CQD 数据模型设计的基础。

## <a name="troubleshooting"></a>疑难解答

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>我正在尝试使用"日期"列作为日期切片器。 将此列的数据类型转换为日期后，就会收到此错误

> **无法加载此视觉对象的数据**：OLE DB 或 ODBC 错误：[Expression.Error] 无法将表达式折叠到数据源。 请尝试更简单的表达式。

Microsoft 呼叫质量连接器不支持日期切片器。 若要指定日期范围，请对报表应用两个筛选器，指定小于和大于日期。

或者，如果要查看的日期是最近的日期，请应用相对日期筛选器以仅显示过去 N 天/周/月的数据。

## <a name="error-codes"></a>错误代码

由于适用于 Power BI 的 Microsoft 呼叫质量连接器在可构造的查询类型方面比浏览器应用的限制更少，因此在构建查询时，有时可能会遇到许多错误。 如果收到"CQDError"类型的错误消息。 RunQuery – 查询执行错误"，使用提供的 ErrorType 编号引用以下列表，以排查查询可能出现的问题。 以下是使用 CQD 连接器时可能会遇到的最常见错误类型Power BI代码：

- **ErrorType 1 - 查询结构错误：** 查询结构错误通常是由于连接器未能生成格式正确的查询导致的。 使用不受支持的功能时（如上述限制中指定）时，通常会发生这种情况。 仔细检查是否未对查询使用任何计算列或自定义视觉对象。

  - **ErrorType 2 - 查询生成错误：** 由于 Microsoft 呼叫质量连接器无法正确分析你尝试构建的查询，导致查询生成错误。 使用不受支持的功能时（如上述限制中指定）时，通常会发生这种情况。 仔细检查是否未对查询使用任何计算列或自定义视觉对象。

  - **ErrorType 5 - 执行超时：** 在超时之前，查询已达到可能的最大运行时。尝试向查询添加更多筛选器，以限制其范围。 缩小数据范围通常是实现此目的最有效的方法。

  - **ErrorType 7 - 无度量错误：** 调用质量仪表板查询需要一个度量值才能正常运行。 仔细检查查询是否包含度量值。 Microsoft 呼叫质量连接器中的度量值由聚合 (表示，) 名称前加和符号。

如果在此范围内遇到任何其他错误，请通知呼叫质量仪表板团队，以便我们可以帮助解决问题并适当地更新文档。

## <a name="footnotes"></a>脚注

**<sup>1</sup>** 某些进程 (应用，例如，OneDrive) 可能导致"文档"根文件夹更改;确保自定义 *连接器Power BI Desktop \\* 放在当前根文件夹"文档"文件夹中。

**<sup>2</sup>** 用于呼叫质量仪表板的登录凭据不需要是登录应用本身时Power BI Desktop凭据。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>何时将 Power BI连接器从"Beta"状态更新？

尽管具有 Beta 版标记，但适用于 Power BI 的 Microsoft 呼叫质量 (Beta) 连接器是该连接器的第一个"发布"版本，并且已由 Power BI 团队正式签名，以反映这一点。 在连接器初始发布时，Power BI 团队无法提供支持和更广泛的认证，但仍准备证明 Microsoft 呼叫质量连接器的安全性、真实性和常规功能。 未来，我们计划在不久的将来投资 Microsoft 呼叫质量连接器Power BI服务。

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>与浏览器中的"呼叫质量仪表板"相比，连接器为何看起来较慢？ 如何提高性能？

在浏览器和连接器中，各种模板的查询性能实际上是相同的。  与其他任何独立应用一样，Power BI将身份验证和呈现时间添加到我们的性能。 此外，差异在于运行的并发查询数。 由于浏览器内版本的呼叫质量仪表板具有开发较少且信息密集型的可视化选项，因此我们的大多数报告限制为一次加载 2-3 个查询。 另一方面，连接器模板通常显示 20 多个并发查询。 如果希望生成的响应与以前使用的报表一样高，请尝试创建每个选项卡不超过 2-3 个查询的报表。

有关详细信息，请参阅以下文章：

- [优化指南Power BI](/power-bi/guidance/power-bi-optimization)
- [DirectQuery 模型指南](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>在运行查询时，我发现自己经常遇到 10，000 行的限制。 如何让连接器返回超过 10，000 行？

API 端实际指定了 10，000 行的限制，旨在帮助显著提高性能并降低因内存不足导致查询执行错误的风险。

最好根据连接器最佳做法重构报表，而不是尝试增加结果行计数。 我们包含的模板旨在演示这些最佳做法。 在可能的情况下，首先使用更大、基数较低的维度（如月、年、日期、区域、国家/地区等）查看 KPI。从该维度中，可以向下钻取到基数越高的维度。 支持人员报表Location-Enhanced报表都提供了此向下钻取工作流的良好示例。



## <a name="related-topics"></a>相关主题

[使用Power BI分析用于存储的 CQD Teams](CQD-Power-BI-query-templates.md)
