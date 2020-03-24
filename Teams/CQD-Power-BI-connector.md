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
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>安装 Power BI Connector 以使用 CQD 查询模板

在你可以对 CQD （.PBIX 文件）使用 Power BI 查询模板之前，你需要使用[下载](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)中包含的*MicrosoftCallQuality*文件来安装 MICROSOFT CQD 的 power bi 连接器。 

已阅读 "[使用 POWER BI" 来分析 CQD 数据，以供团队](CQD-Power-BI-query-templates.md)了解有关这些模板的信息。


## <a name="installation"></a>安装

[POWER BI 文档](https://docs.microsoft.com/power-bi/desktop-connector-extensibility)中详细介绍了安装自定义连接线和调整安全性以启用连接器使用的过程。 为了简便起见，下面是一个快速说明：

1.  检查 您的* \[\]\\计算机是否已有 "Power\\BI desktop 自定义连接线*" 文件夹。 如果不是，请创建此文件夹。<sup>1</sup>

2.  下载连接器文件（即* \*mez*或* \*pqx*文件），并将其放在 "*自定义连接器*" 目录中。

3.  **如果连接器文件是* \*mez*文件，** 则还需要调整您的安全设置，如[自定义连接器设置文档](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security)中所述。

如果已释放此 Power BI Connector for Microsoft 团队的新版本，只需将*自定义连接器*目录中的旧的连接线文件替换为新文件。

## <a name="setup"></a>设置

为了生成报表并运行查询，首先需要连接到 CQD 数据源。 请按照以下步骤进行连接：

1.  在 Power BI Desktop 的 "开始" 选项卡中，单击 "*获取数据*"。

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector1.png)

2.  此时应显示 "*获取数据*" 窗口。 导航到 "*联机服务*"，然后选择 " *Microsoft 通话质量（Beta）* " 和 "点击*连接*"。

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector2.png)

3.  系统将提示您登录下一步。 使用与用于 CQD 的凭据相同的凭据。<sup>2</sup>

4.  下一条提示将为你提供两种*数据连接模式*之间的选项。 选择 " *DirectQuery* "，然后点击 *"确定"*。

5.  最后，你将获得最终提示，显示 CQD 的整个数据模型。 在此情况下，将仅显示数据，CQD 的数据模型。 选择 "*加载*" 以完成设置过程。

6.  此时，Power BI 会将数据模型加载到窗口右侧。 该页将保留为空，并且默认情况下不会加载任何查询。 继续**构建以下查询**，以便构建查询并返回数据。

如果此设置过程中的任何步骤不完全明确，可在[此处](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data)找到更详细的流程说明。

## <a name="building-queries"></a>构建查询

安装完成后，应在 "*字段*" 窗格中看到几百个维度的名称和度量值的加载。 从此处构建实际查询非常简单，只需选择所需的查询的维度和度量值，然后将其拖放到页面上。 下面是更详细的说明，有一个简单的示例：

1.  从 "*可视化*" 窗格中选择要使用的可视化效果。 该可视化对象的空白版本应显示在页面上。 对于此示例，我们将使用*表格*可视化效果。

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector3.png)

2.  确定要用于查询的维度和度量值（由聚合符号表示），然后手动选择它们并将其拖动到黑色可视化效果中。 或者，将其拖动到 "可视化" 选项下方的 "*值*" 字段。

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector4.png)

**重要说明：** 通话质量仪表板要求运行任何查询的度量值。 无法将度量值添加到查询将导致该查询失败。

3.  接下来，选择要筛选的任何维度，并将其拖动到 "*筛选器*" 窗格中*此视觉字段上的筛选器*。 CQD Power BI 连接器当前支持*基本筛选*（从可能的维度值列表中选择值）、*高级筛选*（手动指定值和要筛选的操作数，类似于高级 CQD），以及*相对日期筛选*（仅适用于 "*结束时间*" 和 "*开始时间*" 维度）。 CQD 不支持按*Top N*进行筛选。

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector5.png)

4.  最后，选择 "*可视化*" 窗格中的 "*格式*" 选项卡以设置查询样式并设置其格式。

**注意：** CQD 查询至少需要一个度量值才能运行。 如果查询未加载，请仔细检查查询中是否已包含度量值。

## <a name="creating-a-drillthrough-report"></a>创建钻取报表

[POWER BI 中的钻取](https://docs.microsoft.com/power-bi/desktop-drillthrough)允许你创建具有焦点的报表，你可以使用其他报表的值作为上下文快速筛选。 了解如何使用 CQD 连接器创建你的第一个查询后，创建钻取变得更简单。

1.  为焦点报表创建另一页，然后将查询添加到该页面。

2.  选择要用作钻取筛选器的维度，并将其拖到 "*可视化*" 窗格上的 "*钻取*" 字段中。

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector6.png)

3.  **就是这样\!** 其他使用该维度的页面上的任何其他查询现在都可以钻取到该页面，并自动将钻取维度的值应用为筛选器。

    ![屏幕截图： Power BI Connector](media/CQD-power-bi-connector7.png)

与高级 CQD 不同，Power BI 支持非顺序钻取。 只要查询包含必要的维度，它就可以钻取到任何其他页面。

## <a name="limitations"></a>优缺点

尽管使用 Power BI，但并非所有 Power BI 功能都是由 CQD 连接器支持的，这是由于 CQD 数据模型或对 DirectQuery 连接器的限制。 下面的列表显示了其他连接线的一些更值得注意的限制，但此列表不应被认为是详尽的：

1.  **计算列-** DirectQuery 连接器通常对 Power BI 中的计算列有有限支持。 虽然某些计算列可能与连接线一起使用，但这些计算列应视为异常。 作为一般规则，计算列将不起作用。

2.  **聚合-** CQD 数据模型基于多维数据集模型构建，这意味着聚合在度量形式中已受支持。 尝试手动将聚合添加到不同的维度或更改度量值的聚合类型将不会与连接器一起使用，并且通常会导致错误。

3.  **自定义视觉对象-** 虽然 CQD 连接器与一系列自定义视觉对象一起工作，但我们无法保证与所有自定义视觉对象的兼容性。 许多自定义视觉对象依赖于使用计算列或导入的数据，而不受 DirectQuery 连接线支持。

4.  **引用缓存的数据-** Power BI 目前不支持以任何方式引用 DirectQuery 连接器中的缓存数据。 任何引用查询结果的尝试都将导致新查询。

5.  **相对数据筛选-** 在 CQD 连接器中受支持，但仅限 "*开始时间*" 和 "*结束时间*" 维度。 虽然*日期*维度可能是相对日期筛选的明显选择，但*日期*不会存储为日期时间对象，因此不支持 Power BI 中的相对日期筛选。

请注意，虽然连接线在预览中，但这些限制不太可能与连接器的最终版本一起更改。 大多数问题都是对 CQD 数据模型设计而言，Power BI 或基础中的 DirectQuery 连接器设计的限制。

## <a name="error-codes"></a>错误代码

由于 CQD Power BI 连接器的限制与你可以构造的查询种类的浏览器应用的限制更小，因此在构建查询时可能偶尔会遇到许多错误。 在收到类型为 "CQDError" 的错误消息的情况中。 RunQuery-查询执行错误 "，请在下面的列表中引用所提供的 ErrorType 数字，以便对查询可能存在的问题进行故障排除。 以下是你可能遇到的 CQD Power BI 连接器最常见的错误类型代码：

  - **ErrorType 1-查询结构错误：** 查询结构错误通常是由连接器无法生成格式正确的查询导致的。 这种情况最常发生于使用不受支持的功能时，如以上限制中所述。 仔细检查你没有为该查询使用任何计算列或自定义视觉对象。

  - **ErrorType 2-查询构建错误：** 查询生成错误是由 CQD 连接器无法正确分析你试图构建的查询所导致的。 这种情况最常发生于使用不受支持的功能时，如以上限制中所述。 仔细检查你没有为该查询使用任何计算列或自定义视觉对象。

  - **ErrorType 5-执行超时：** 查询在超时之前已达到最大可能的运行时。尝试向查询添加更多筛选器，以便限制其范围。 缩小数据区域通常是实现此目的的最有效方式。

  - **ErrorType 7-无测量错误：** CQD 查询需要一个度量单位才能正常工作。 仔细检查查询是否包含度量值。 CQD 连接器中的度量值在其名称前由聚合（sum）符号表示。

如果您在此范围外遇到任何其他错误，请通知 CQD 团队，以便我们能够帮助您解决问题，并根据需要更新文档。

## <a name="footnotes"></a>页脚

**<sup>1</sup>** 某些流程和应用（例如，OneDrive）可能会导致您的文档根文件夹发生更改;请确保*POWER BI 桌面\\自定义连接器*目录位于当前根文件夹 "文档" 文件夹内。

**<sup>2</sup>** 用于 CQD 的登录凭据*不*需要与用于登录到 power BI 桌面应用本身的凭据相同。



## <a name="related-topics"></a>相关主题

[使用 Power BI 分析团队的 CQD 数据](CQD-Power-BI-query-templates.md)