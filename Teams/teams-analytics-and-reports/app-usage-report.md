---
title: Microsoft Teams 应用使用情况报告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在 Microsoft Teams 管理中心使用 Teams 应用使用情况报告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 745761b80bd2507a31cb76cdadc015eac8e9f7fd
ms.sourcegitcommit: a4a65283e85d0c393c844dfd335df0d48e0e4105
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2022
ms.locfileid: "67313924"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams 应用使用情况报告

Microsoft Teams 管理中心的 Teams 应用使用情况报告提供有关用户在 Teams 中使用的应用的信息。  

## <a name="view-the-app-usage-report"></a>查看应用使用情况报告

1. 在 Teams 管理中心的左侧导航中，选择 **“分析”&报告** > **[使用情况报告](https://admin.teams.microsoft.com/analytics/reports)**。

   :::image type="content" source="media/app-usage-report1.png" alt-text="“使用情况报告”菜单项的屏幕截图。":::

1. 在 **“查看报表** ”选项卡上的 **“报表**”下，选择 **“应用使用情况**”。

1. 在 **“日期”范围** 下，选择一个区域，然后选择 **“运行报表**”。 可以查看 Teams 应用使用情况报告，了解过去 7 天、30 天或 90 天的趋势。

   :::image type="content" source="media/app-usage-report2-trimmed.png" alt-text="“应用使用情况”报表界面的屏幕截图。" lightbox="media/app-usage-report2.png":::

## <a name="interpret-the-report"></a>解释报告

:::image type="content" alt-text="Teams 管理中心中带有标注的 Teams 应用使用情况报告的屏幕截图。" source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

每个报表的左上角都有一个日期，显示创建报表的日期。 报表通常反映从应用打开时起的 24 小时延迟。

管理员中心提供活动用户和日期的图表。 活动用户是在所选时间段内至少打开一次应用的用户数。

将鼠标悬停在点 (4) 表示应用在任何日期的使用情况，以查看该应用在该日期的活动用户总数。

若要选择其他应用，请在右上角选择“ **筛选器”** 图标 (5) ，选择或键入新条件，然后选择 **“应用**”。

报表底部的表 (6) 按应用名称显示活动用户和团队。

   - **应用名称** 是 Teams 中使用的应用的显示名称。
   - **活动用户** 是在指定的时间段内至少打开应用一次的用户数。
   - **应用类型** 是“Microsoft”或“第三方”的静态值。
   - **活动团队** 是团队中至少一名成员在指定时间段内打开应用的团队数。
   - **Publisher** 是应用的软件开发人员。
   - **版本** 是应用开发人员提供的应用的软件版本。

   > [!NOTE]
   > **活动用户** 和 **活动团队** 仅针对频道中使用的应用进行计算。

若要在表中添加或删除列，请在右上角选择“ **编辑列** ”图标 (7) ，在“ **编辑列”** 选项卡上选择新条件，然后选择 **“应用**”。

若要将报表导出到 CSV 文件以进行脱机分析，请在右上角选择“**导出到 Excel”** 图标 (8) ，然后在“**状态**”下 **的“下载”** 选项卡上选择 **“下载**”。

   :::image type="content" alt-text="“下载”窗格的屏幕截图。" source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

在 Microsoft Excel 中查看报表时，还会看到一个 `Id` 列，该列表示应用 ID，通常是字母数字字符串。 `Id`如果 **\n** 值，则表示用户要求删除其信息。

   :::image type="content" source="media/app-usage-report8.png" alt-text="下载的 Excel 报表的屏幕截图。":::

## <a name="related-articles"></a>相关文章

- [Teams 分析和报告](teams-reporting-reference.md)
