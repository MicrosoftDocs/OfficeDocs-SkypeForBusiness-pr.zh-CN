---
title: Microsoft Teams 使用情况报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在 Microsoft Teams 管理中心使用 Teams 使用情况报告来概要了解组织中的 Teams 活动。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0252478a1ca41962ecdc424f97c85025b6b7dda9
ms.sourcegitcommit: f4beced1a74d123253e166c7d402c1f24653d452
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528417"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams 使用情况报告

通过 Microsoft Teams 管理中心的 Teams 使用情况报告，可概要了解 Teams 中的活跃用户和频道数等使用活动，从而能快速查看组织中有多少用户正在使用 Teams 进行通信和协作。 你可查看团队的使用情况信息，包括每个团队中的活跃用户和频道数量、来宾数和消息数。

## <a name="view-the-report"></a>查看报告

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**分析" & 报告** > **使用情况报告**。 在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 "**团队使用情况**"。
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    ![团队管理员中心中带有标注的 "团队使用情况" 报表的屏幕截图](../media/teams-reports-teams-usage-with-callouts.png "团队管理员中心中带有标注的 "团队使用情况" 报表的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 "团队使用情况" 活动报表，了解过去7天、28或90天的趋势。 |
|**2**   |每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴表示活跃项目或活动的计数。</li> </ul>将鼠标悬停在表示给定日期中某项目或活动的点可查看该项目或活动在该给定日期的实例数量。|
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击 "**总活动用户**"、"**工作组 & 频道活动用户**"、"**活动频道**" 或 "**邮件**"，以仅查看与每个用户相关的信息。 更改此选项不会更改表格中的信息。 |
|**5**   |表格按团队细分显示了使用情况。 <ul><li>"**团队名称**" 是团队的显示名称。 你可以单击团队名称以转到 Microsoft 团队管理中心中的团队设置页面。 </li> <li>“**隐私**”表示团队是私人团队还是公共团队。</li> <li>“**活跃用户数**”是指定时间段内活跃用户的数量。</li><li>“**来宾数**”是指定时间段内团队中来宾的数量。</li> <li>"**活动频道**" 表示指定时间段内至少有一个活动用户的频道数。</li> <li>**发布消息**是指定时间段内频道中所有发布消息的数量。</li> <li>"**答复邮件**" 是指在指定时间段内频道中所有答复消息的数量。</li> <li>"**组织会议**" 是指用户组织的所有计划会议的数量。 定期会议的每个实例都作为一个会议进行计算。</li><li>**紧急消息**是指在指定时间段内所有紧急邮件的数量。</li><li>"**反应**" 是指在指定时间段内对邮件的所有反应的数量。</li><li>**提及**是在指定时间段内消息中使用的所有提及数。</li><li>**信道消息**表示指定时间段内团队用户在团队聊天室中发布的唯一消息数。</li> </li> </ul>请注意，如果用户帐户在 Azure AD 中不再存在，则用户名在表中显示为 "-"。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**6**   |选择“**编辑列**”可在表格中添加或删除列。|
|**7**   |你可以将报表导出到 CSV 文件，以便脱机分析。 单击 "**导出到 Excel**"，然后在 "**下载**" 选项卡上，单击 "**下载**" 以在准备就绪后下载报告。<br><br>!["下载" 选项卡的屏幕截图，显示导出的下载报告](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
