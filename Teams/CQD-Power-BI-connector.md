---
title: 安装Power BI连接器以使用 CQD 查询模板
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
ms.localizationpriority: medium
description: 安装Power BI连接器以使用调用质量仪表板 (CQD) 查询模板
ms.openlocfilehash: 3ca8a4c70b23923dcf49906b85529c7b7e369008
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675254"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>安装 Microsoft 呼叫质量连接器，以便Power BI使用呼叫质量仪表板查询模板

在Microsoft Teams调用质量仪表板 (CQD) 使用Power BI查询模板 (PBIX 文件) 之前，需要使用 [下载](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)中包含的 *MicrosoftCallQuality.pqx* 文件安装适用于Power BI的 Microsoft 呼叫质量连接器。

读[取使用Power BI分析 CQD 数据以供Teams](CQD-Power-BI-query-templates.md)了解这些模板。

确保具有正确的 [CQD 访问角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)来访问Power BI报表。

> [!NOTE]
> Microsoft 呼叫质量连接器仅支持 Power BI 中的 DirectQuery;不支持导入模式。 

## <a name="installation"></a>安装

[Power BI文档](/power-bi/desktop-connector-extensibility)详细介绍了安装自定义连接器和调整安全性以启用连接器的过程。 为了简单起见，下面是一个快速的解释：

1. 检查计算机是否已具有 Documents *\[\]\\Power BI Desktop\\ Custom 连接器* 文件夹。 如果没有，请创建此文件夹。<sup>1</sup>

2.  (.mez 或 *\*.pqx* 文件) *\** 下载连接器文件，并将其置于 *自定义连接器* 目录中。

3. **如果连接器文件是 *\*.mez* 文件，** 则还需要根据 [自定义连接器设置文档](/power-bi/desktop-connector-extensibility#data-extension-security)中所述调整安全设置。

如果发布了新版本的 Microsoft 呼叫质量连接器，请将 *自定义连接器* 目录中的旧连接器文件替换为新文件。

## <a name="setup"></a>设置

若要生成报表并运行查询，首先需要连接到 CQD 数据源。 请按照以下步骤进行连接：

1. 在Power BI Desktop的“开始”选项卡中，单击 *“获取数据*”。

    ![获取Power BI连接器中的数据。](media/CQD-power-bi-connector1-resize.png)

2. 此时应显示 *“获取数据* ”窗口。 导航到 *联机服务*，然后选择 *Microsoft 呼叫质量 (Beta)* 并点击 *连接*。

    ![Power BI连接器中的 Microsoft 呼叫质量。](media/CQD-power-bi-connector2-resize.png)

3. 系统会提示你下一步登录。 使用用于通话质量仪表板的同一凭据。<sup>2</sup>

4. 下一个提示将提供两种 *数据连接模式* 之间的选项。 选择 *DirectQuery* 并点击 *“确定*”。

5. 最后，系统会向你提供最终提示，显示调用质量仪表板的整个数据模型。 此时不会显示任何数据，只有 CQD 的数据模型。 选择 *“加载* ”以完成安装过程。

6. 此时，Power BI会将数据模型加载到窗口的右侧。 否则，页面将保持空白，默认情况下不会加载任何查询。 继续生成下面的 **查询** ，以便生成查询并返回数据。

如果此设置过程中的任何步骤都不清楚，则可以在快速入门中找到该过程的更详细的说明[：连接Power BI Desktop中的数据](/power-bi/desktop-quickstart-connect-to-data)。

## <a name="building-queries"></a>生成查询

设置完成后，应会在“ *字段* ”窗格中看到数百个维度的名称和度量值加载。 从此处构造实际查询很简单，只需选择查询所需的维度和度量值，然后拖放到页面上即可。 下面是一个更详细的说明，其中包含一个简单的示例：

1. 从“ *可视化效果* ”窗格中选择要使用的可视化效果。 该可视化效果的空白版本应显示在页面上。 对于本示例，我们将使用 *表* 可视化效果。

    ![Power BI连接器中的“可视化效果”窗格。](media/CQD-power-bi-connector3-resize.png)

2. 确定要用于查询 () 由聚合符号表示的维度和度量值，然后手动选择它们并将其拖动到黑色可视化效果。 或者，将它们拖到可视化效果选项下的 *“值* ”字段。

    !Power BI连接器中的可视化效果查询。] (媒体/CQD-power-bi-connector4-resize2.png) 

    > [!IMPORTANT]
    > 调用质量仪表板需要一个度量值来运行任何查询。 无法向查询添加度量值将导致该查询失败。

3. 接下来，选择要筛选的任何维度，并将其拖动到“筛选器”窗格中 *此视觉* 对象字段上的“ *筛选器* ”。 Microsoft 呼叫质量连接器目前支持 *基本筛选* (从可能维度值列表中选择值) ，*高级筛选* (手动指定要筛选的值和操作数，类似于通话质量仪表板) ，*相对日期筛选* (仅适用于 *结束时间* 和 *"开始"菜单时间* 维度) 。 调用质量仪表板不支持根据 *Top N* 进行筛选。

    ![Power BI连接器中的可视化效果筛选器。](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > 仅在应用于维度时才支持筛选器。 调用质量仪表板不支持筛选度量值。

4. 最后，选择 *“可视化效果*”窗格中的 *“格式”* 选项卡以设置查询的样式和格式。

    > [!NOTE]
    > 调用质量仪表板查询至少需要一个度量值才能运行。 如果查询未加载，请仔细检查查询中是否包含了度量值。

## <a name="creating-a-drillthrough-report"></a>创建钻取报表

[通过Power BI](/power-bi/desktop-drillthrough)钻取，可以创建重点报表，以便可以使用其他报表的值作为上下文进行快速筛选。 了解如何使用 Microsoft 呼叫质量连接器创建第一个查询后，创建钻取更简单。

1. 为重点报表创建另一页，然后将查询添加到该页面。

2. 选择要用作钻取筛选器的维度，并将其拖到 *“可视化效果*”窗格下的 *“钻取*”字段。

    ![在Power BI连接器中钻取。](media/CQD-power-bi-connector6-resize.png)

3. **就是这样\!** 使用该维度的另一页上的任何其他查询现在都可以钻取到该页面，自动将钻取维度的值应用为筛选器。

    ![Power BI连接器中的钻取筛选器。](media/CQD-power-bi-connector7-resize.png)

与通话质量仪表板不同，Power BI支持非顺序钻取。 如果查询包含必要的维度，则可以钻取到任何其他页面。

### <a name="best-practice"></a>最佳做法

Microsoft 调用质量连接器查询应考虑到钻取功能进行设计。 而不是尝试一次性加载所有数据，然后使用筛选器向下切片，从更广泛的低基数查询开始，向下钻取到高基数查询。 例如，尝试诊断哪些子网对质量问题的贡献最大时，首先确定导致问题的区域和国家，然后向下钻取到该区域或国家/地区的子网会很有帮助。 调用质量连接器模板是以这种方式设计的，以作为示例。

## <a name="limitations"></a>限制

尽管使用Power BI，但并非所有Power BI功能都由 Microsoft 呼叫质量连接器提供支持，无论是由于通话质量仪表板的数据模型或 DirectQuery 连接器上的一般限制。 下面的列表指出了连接器的一些更值得注意的限制，但不应将此列表视为详尽无遗：

1. **计算列 –** 通常，DirectQuery 连接器对Power BI中的计算列的支持有限。 某些计算列可能适用于连接器，这些列是例外。 一般情况下，计算列不起作用。

2. **聚合 –** 调用质量仪表板数据模型基于多维数据集模型构建，这意味着已以度量值的形式支持聚合。 尝试手动将聚合添加到不同的维度或更改度量值的聚合类型将不适用于连接器，这通常会导致错误。

3. **自定义视觉对象 –** 虽然 Microsoft 呼叫质量连接器确实适用于一系列自定义视觉对象，但我们无法保证与所有自定义视觉对象兼容。 许多自定义视觉对象依赖于计算列或导入的数据的使用，DirectQuery 连接器不支持这两种数据。

4. **引用缓存的数据 –** Power BI当前不支持以任何方式引用 DirectQuery 连接器中的缓存数据。 任何引用查询结果的尝试都将导致新的查询。

5. **相对数据筛选 –** Microsoft 呼叫质量连接器支持，但仅支持 *"开始"菜单时间* 和 *结束时间* 维度。 虽然 *Date* 维度可能是相对日期筛选的明显选择，但 *Date* 不存储为日期时间对象，因此不支持在Power BI中进行相对日期筛选。

6. **仅度量查询 -** Microsoft 呼叫质量连接器目前不支持此功能。 创建具有三个或更多度量值且没有维度的可视化效果时，将转置列数据。 为了避免这种情况，请始终在可视化效果中至少包括一个维度 (例如：月年) 。 此问题将在即将发布的适用于 Power BI 的 Microsoft 呼叫质量连接器中解决。

7. **政府社区云 (GCC) 支持 –** 对于GCC环境中的客户，仅使用Power BI Desktop时，Microsoft 呼叫质量连接器将正常工作。 Microsoft 呼叫质量连接器目前与GCC客户的Power BI 服务不兼容。

其中大多数问题要么限制了 Power BI 中的 DirectQuery 连接器设计，要么是 CQD 数据模型设计的基础。

## <a name="troubleshooting"></a>疑难解答

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>我尝试将“日期”列用作日期切片器。 一旦我将此列的数据类型转换为 Date，就会收到此错误

> **无法加载此视觉对象的数据**：OLE DB 或 ODBC 错误：[Expression.Error] 无法将表达式折叠到数据源。 请尝试更简单的表达式。

Microsoft 调用质量连接器不支持日期切片器。 若要指定日期范围，请向报表应用两个筛选器，指定小于和大于日期。

或者，如果要查看的日期是最近查看的日期，则应用相对日期筛选器以仅显示过去 N 天/周/月的数据。


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>将某些维度添加到报表时，视觉对象会立即返回 **“无法加载此视觉对象的数据”。** 删除维度可修复视觉对象 -- 发生了什么情况？

这是 Microsoft 呼叫质量连接器中的已知问题;作为整数公开的任何维度都将作为“聚合”列显示在Power BI中，其中Power BI将尝试默认汇总操作 (通常为“Sum”) 。 在某些情况下，即使结果没有用处，此行为也会成功总结值，因为像第二 WiFi 通道这样的维度的“总和”毫无意义。 在其他情况下，此汇总操作将失败并导致视觉对象中的错误。

若要解决此问题，请首先从视觉对象中删除维度。 从“字段”列表中选择维度，浏览到功能区中的“列工具”选项卡，单击“汇总”下拉菜单，然后选择 **“不汇总**”。 现在可以再次将维度添加到视觉对象。


## <a name="error-codes"></a>错误代码

由于适用于Power BI的 Microsoft 调用质量连接器在可构造的查询种类方面比浏览器应用受到的限制要小，因此在生成查询时，有时可能会遇到许多错误。 如果收到“CQDError”类型的错误消息。 RunQuery – 查询执行错误“，使用提供的 ErrorType 编号引用下面的列表，以便排查查询可能出现的问题。 以下是使用 CQD Power BI连接器可能会遇到的最常见错误类型代码：

- **ErrorType 1 - 查询结构错误：** 查询结构错误通常是由于连接器无法生成格式正确的查询而导致的。 使用不受支持的功能时，最常发生这种情况，如上述限制中所述。 仔细检查是否未对该查询使用任何计算列或自定义视觉对象。

  - **ErrorType 2 - 查询生成错误：** 查询生成错误是由 Microsoft 呼叫质量连接器无法正确分析尝试生成的查询引起的。 使用不受支持的功能时，最常发生这种情况，如上述限制中所述。 仔细检查是否未对该查询使用任何计算列或自定义视觉对象。

  - **ErrorType 5 - 执行超时：** 在超时之前，查询已达到可能的最长运行时。尝试向查询添加更多筛选器，以限制其范围。 缩小数据范围通常是实现此目的的最有效方法。

  - **ErrorType 7 - 无度量错误：** 调用质量仪表板查询需要度量值才能正常运行。 仔细检查查询是否包含度量值。 Microsoft 调用质量连接器中的度量值由其名称前面的聚合 (总和) 符号表示。

如果在此范围之外遇到任何其他错误，请通知呼叫质量仪表板团队，以便我们能够帮助排查问题并根据需要更新文档。

## <a name="footnotes"></a>脚注

**<sup>1</sup>** 某些进程和应用 (，例如，OneDrive) 可能会导致文档根文件夹更改;请确保 *将Power BI Desktop\\ Custom 连接器* 目录放置在当前根文件夹 Documents 文件夹内。

**<sup>2</sup>** 用于呼叫质量仪表板的登录凭据 *不需要* 是用于登录到Power BI Desktop应用本身的凭据。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>何时会从“Beta”状态更新Power BI连接器？

尽管有 Beta 标记，但适用于Power BI的 Microsoft 呼叫质量 (Beta) 连接器是连接器的第一个“版本”，并且已由Power BI团队正式签署安全性，以反映这一点。 在连接器初始发布时，Power BI团队无法提供支持和更广泛的认证，但仍准备好证明 Microsoft 呼叫质量连接器的安全性、真实性和一般功能。 展望未来，我们计划在不久的将来投资 Microsoft 呼叫质量连接器，以便Power BI。

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>与浏览器中的通话质量仪表板相比，为什么连接器看起来较慢？ 可以做些什么来提高性能？

在浏览器和连接器中，各种模板的查询性能实际上相同。  与任何其他独立应用一样，Power BI将其身份验证和呈现时间添加到性能中。 此外，区别在于正在运行的并发查询数。 由于调用质量仪表板的浏览器内版本的可视化效果不太完善，并且信息密集型可视化选项较少，因此大多数报表仅限于一次加载 2-3 个查询。 另一方面，连接器模板通常会显示 20 多个并发查询。 如果想要生成的报表的响应速度与以前使用的报表相同，请尝试创建每个选项卡不超过 2-3 个查询的报表。

有关详细信息，请参阅以下文章：

- [Power BI优化指南](/power-bi/guidance/power-bi-optimization)
- [DirectQuery 模型指南](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>我发现在运行查询时，我经常遇到 10，000 行的限制。 如何让连接器返回超过 10，000 行？

10，000 行限制实际上是在 API 末尾指定的，旨在帮助显著提高性能并降低内存不足导致的查询执行错误的风险。

最好是根据连接器最佳做法重新构造报表，而不是尝试增加结果行计数。 我们包含的模板旨在演示这些最佳做法。 在可能的情况下，首先使用更广泛的低基数维度（如月份、年份、日期、区域、国家/地区等）查看 KPI。可以从那里向下钻取到越来越高的基数维度。 Helpdesk 和 Location-Enhanced 报表都提供了此向下钻取工作流的良好示例。



## <a name="related-topics"></a>相关主题

[使用Power BI分析Teams的 CQD 数据](CQD-Power-BI-query-templates.md)
