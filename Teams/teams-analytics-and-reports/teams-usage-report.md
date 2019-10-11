---
title: Microsoft Teams 使用情况报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何在 Microsoft Teams 管理中心使用 Teams 使用情况报告来概要了解组织中的 Teams 活动。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a31d3a6bf374e512dde0549dbbd59ed90904cd0
ms.sourcegitcommit: a71ad6762e18267faaaac09533bac80a181102af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "37439568"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams 使用情况报告

通过 Microsoft Teams 管理中心的 Teams 使用情况报告，可概要了解 Teams 中的活跃用户和频道数等使用活动，从而能快速查看组织中有多少用户正在使用 Teams 进行通信和协作。 你可查看团队的使用情况信息，包括每个团队中的活跃用户和频道数量、来宾数和消息数。

## <a name="view-the-report"></a>查看报告

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**分析" & 报告** > **使用情况报告**。 在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 "**团队使用情况**"。
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    团队管理中心中 "团队使用情况"![报表的屏幕截图]，其中包含(../media/teams-reports-teams-usage-with-callouts.png "标注的团队管理中心中的 \"团队使用情况\" 报表的标注屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可查看 Teams 使用情况活动报告，了解过去 7 天或 28 天内的趋势。 |
|**2**   |每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴表示活跃项目或活动的计数。</li> </ul>将鼠标悬停在表示给定日期中某项目或活动的点可查看该项目或活动在该给定日期的实例数量。|
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击 "**总活动用户**"、"**工作组 & 频道活动用户**"、"**活动频道**" 或 "**邮件**"，以仅查看与每个用户相关的信息。 更改此选项不会更改表格中的信息。 |
|**5**   |表格按团队细分显示了使用情况。 <ul><li>"**团队名称**" 是团队的显示名称。 你可以单击团队名称以转到 Microsoft 团队管理中心中的团队设置页面。 </li> <li>“**隐私**”表示团队是私人团队还是公共团队。</li> <li>“**活跃用户数**”是指定时间段内活跃用户的数量。</li><li>“**来宾数**”是指定时间段内团队中来宾的数量。</li> </li> </ul>请注意，如果用户帐户在 Azure AD 中不再存在，则用户名在表中显示为 "-"。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**6**   |选择“**编辑列**”可在表格中添加或删除列。|
|**7**   |你可以将报表导出到 CSV 文件，以便脱机分析。 单击 "**导出到 Excel**"，然后在 "**下载**" 选项卡上，单击 "**下载**" 以在准备就绪后下载报告。<br><br>!["下载" 选项卡的屏幕截图，显示导出的下载报告](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
