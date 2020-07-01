---
title: Microsoft 团队应用使用情况报表
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用 Microsoft 团队管理中心中的 "团队应用使用情况" 报表。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 565a3cb28b73a37162947859effc6ec154b59258
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938201"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft 团队应用使用情况报表

Microsoft 团队管理中心中的 "团队应用使用情况" 报表向你提供有关用户在团队中使用哪些应用的信息。  

## <a name="view-the-app-usage-report"></a>查看应用使用情况报表

1.  在管理中心的左侧导航中 <https://admin.teams.microsoft.com> ，单击 "**分析 & 报告** \> **使用情况报告**"。 在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 "**应用使用情况**"。

     :::image type="content" source="media/app-usage-report1.png" alt-text=""使用情况报告" 菜单项的屏幕截图":::

2.  在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

      :::image type="content" source="media/app-usage-report2.png" alt-text="应用使用情况报表的屏幕截图":::

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 "团队应用使用情况" 报表，了解过去7、30或90天的趋势。 |
|**2**   |每个报表都具有生成报表的日期。 报告通常反映从打开应用的时间起的24小时延迟。 <br><br>![显示日期范围的应用使用情况报表的屏幕截图](media/app-usage-report3.png)|
|**3**    | <ul><li>图表上的 X 轴表示特定报表的选定日期范围。</li><li>Y 轴表示在图表中悬停的给定日的用户数，这些用户至少已打开一个应用一次，这样做会被视为活动用户，并计入鼠标悬停时看到的总数。</li></ul>|
|**4**   |将鼠标悬停在表示日期上的应用使用情况的点上，可查看该应用在给定日期的总活动用户的实例数。  |
|**5**   |将包括所有应用，但通过选择 "筛选器" 图标，可使用其他筛选器。  |
|**6**   |该表通过应用名称向你提供活动用户和团队的细目。<br><ul><li>**应用名称**是团队中使用的应用的显示名称。</li><li>"**活动用户**" 是指在指定时间段内至少打开过一次应用的用户数。</li><li>**应用类型**是 "Microsoft" 或 "第三方" 的静态值。</li><li>**活动团队**是已由团队的至少一个成员以及在指定时间段内打开应用的团队数。</li><li>**Publisher**是应用程序的软件发行者。</li><li>**版本**是应用的软件版本，从应用发布者开始。</li></ul><br>![应用使用情况报表的屏幕截图](media/app-usage-report4.png)  |
|**7**  |选择“**编辑列**”可在表格中添加或删除列。<br><br>!["编辑栏" 页面的屏幕截图](media/app-usage-report5.png)  |
|**个**  |你可以将报表导出到 CSV 文件，以便脱机分析。 单击 "**导出到 Excel**"，然后在 "**下载**" 选项卡上，单击 "**下载**" 以在准备就绪后下载报告。<br>![下载页面的屏幕截图](media/app-usage-report7.png)  |
|**db-9**   |在 Excel 中查看报表时，你还会看到一个**Id**列，它表示应用 Id。 团队 ID 通常是一个字母数字字符串。 如果**Id**列显示为 * * \n * * * *，这意味着用户请求删除其信息。<br>![下载的 Excel 报表的屏幕截图](media/app-usage-report8.png)  |

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)