---
title: Microsoft Teams 应用使用情况报告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.date: 09/27/2022
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在 Teams 管理中心使用 Teams 应用使用情况报告来了解活动的团队和应用用户。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c907dc44ff7b76b3df94843d6e33f4a711b37721
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655878"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams 应用使用情况报告

Microsoft Teams 管理中心的 Teams 应用使用情况报告提供有关用户在 Teams 中使用的应用的见解。 可以深入了解组织中不同 Microsoft (Viva learning、Shifts 等) 、第三方 (Polly、Trello 等) &业务线 (LOB) Teams 应用的应用活动。   

可以使用此报表了解不同应用的使用位置，并深入了解每个应用的利用率数据。

此报告中表示的数据提供了以下问题的答案：

-  环境中的用户有多少已安装的应用？
-  有多少应用在环境中至少有一个基于类型 (Microsoft、第三方和 LOB) 的活动用户？
-  每个平台使用多少个应用 (Windows、Mac、Web 或移动) ？
-  有多少活跃用户和活动团队在使用应用？

> [!NOTE]
> 此报表中不包括 **Side 加载** 的 LOB 应用的用法。

本文介绍如何访问报表并查看和解释报表中的各种指标。 

## <a name="view-the-app-usage-report"></a>查看应用使用情况报告

必须是全局管理员、全局读者或 Teams 服务管理员才能在 Microsoft Teams 管理中心查看报表。 请参阅 [Teams 管理员角色管理 Teams](../using-admin-roles.md) ，了解管理员角色和权限。

1. 在 Microsoft Teams 管理中心的左侧导航中，选择 **“分析”&报告** > **使用情况报告**。 在 **“查看报表** ”选项卡上的 **“报表**”下，选择 **“应用使用情况**”。

2. 在 **“日期”范围** 下，选择一个区域，然后选择 **“运行报表**”。

:::image type="content" alt-text="Teams 管理中心中带有标注的 Teams 应用使用情况报告的屏幕截图。" source="media/app-usage2-report10.png" lightbox="media/app-usage2-report10.png":::

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看应用使用情况报告，了解过去 7 天、30 天、90 天和 180 天的趋势。 |
|**2**   |每个报表包含此报表的生成日期。 报表通常反映应用使用时的 24-48 小时延迟。 例如，1 月 10 日的数据应在 1 月 12 日左右显示在报告中。 |
|**3**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴是项的计数。</li> </ul>将鼠标悬停在表示给定日期的项的点上，以查看该给定日期上该项的实例数。|
|**4**   |可以通过选择图例中的项来筛选在图表上看到的内容。 例如，选择 **“Active Microsoft 应用**”、“ **已安装的应用总数**”等，以仅查看与每个应用相关的信息。 更改此选项不会更改表格中的信息。 <ul><li>**活动 Microsoft 应用** 是 Microsoft 应用 (数量，例如，Viva 学习) 在整个组织中使用。 </li> <li>**活动的第三方应用** 是 (的第三方应用的数量，例如，轮询) 在整个组织中使用。  </li> <li>**活动 LOB 应用** 是整个组织使用的业务线应用数。 </li><li>**活动应用总数** 是整个组织使用的应用总数。 </li><li>**非活动应用总数** 是组织中未使用的应用数。 </li><li>**已安装的应用总数** 是组织内安装的应用总数。 所有安装指标的开始日期为 2021 年 10 月。 仅对该日期之后安装的应用进行计数。</li></ul> 该图表显示在所选时间段内每天在组织中聚合的指标。 例如，如果选择 1 月 28 日和指标 **活动第三方应用**，图表将显示组织内 1 月 28 日使用的第三方应用总数。  |
|**5**   |该表提供了每个应用的使用情况细目。 <ul><li>**应用 ID** 是应用清单中存在的外部应用标识符。 <br/>有关应用的详细信息，请参阅 [Teams 管理中心的“管理应用”部分](/microsoftteams/manage-apps) ，并使用此外部应用 ID 进行引用。</li> <li>**应用名称** 是应用清单中存在的此应用程序的名称。 </li> <li>**Publisher** 是应用清单中存在的此应用程序的发布者。 这仅适用于发布到全局应用商店的应用。</li> <li>**使用此应用的 Teams** 是使用此应用至少有一个用户的不同 Teams 团队的数量。 </li><li>**使用此应用的用户** 是组织中使用此应用的不同用户数。</li> <li>**在 Windows 上使用** 指示组织中至少一个用户是否已在 Windows 上使用该应用。</li><li>**在 Mac 上使用** 指示组织中至少一个用户是否已在 MAC 上使用该应用。</li><li>**在 Web 上使用** 指示组织中至少有一个用户是否已在 Web 上使用该应用。 </li> <li>**上次使用的日期** 是组织中任何人上次使用该应用的日期。 </li></ul> |
|**6**   |选择“**编辑列**”可在表格中添加或删除列。|
|**7**   |将报表导出到 CSV 文件以进行脱机分析。 选择 **“导出到 Excel”** 图标，报表将在浏览器中下载。|
|**8** |顶部图中表示的时序数据显示了为整个租户聚合的不同使用指标。|
|**9** |下半部分表示的表格数据显示每个团队聚合的不同使用指标。|


## <a name="managing-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心管理应用

有关如何管理 Teams 应用的详细信息，请参阅 [Microsoft Teams 中的“关于”应用](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md)。

若要将此报表中的应用链接到 Microsoft Teams 管理中心的“管理应用”体验，可以使用以下命令：

- 应用名称
- 外部应用 ID

外部应用 ID 等效于应用商店应用的“管理应用”页中的 ID。 对于 LOB 应用，可以在 [Teams 管理中心列设置的“管理应用”部分中](/microsoftteams/manage-apps)启用 **外部应用 ID** 列。 还可以在自定义 LOB 应用的应用详细信息页上查看它。

## <a name="related-articles"></a>相关文章

- [Teams 分析和报告](teams-reporting-reference.md)
