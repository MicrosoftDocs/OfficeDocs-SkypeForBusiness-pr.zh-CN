---
title: Microsoft Teams 用户活动报告
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
description: 了解如何使用 Microsoft 团队管理中心中的 "团队用户活动" 报表查看组织中的用户使用团队的方式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 19f1ef23e29805e53d819752e3f6313c4989d295
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372151"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams 用户活动报告

团队用户活动报表使你可以深入了解你的组织中的用户在团队中执行的活动类型。 例如，你可以查看多少个用户通过1:1 呼叫进行通信、通过通道消息进行通信的用户数以及参与私人聊天消息的用户数。

## <a name="view-the-user-activity-report"></a>查看用户活动报表

您必须是团队服务管理员才能进行这些更改。 请参阅[使用团队管理员角色管理团队](https://docs.microsoft.com/microsoftteams/using-admin-roles)，了解如何获取管理员角色和权限。

1. 在管理中心的左侧导航中，单击 "**分析" & 报告**  >  **使用情况报告**。 在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 "**团队用户活动**"。
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    ![团队管理员中心中带有标注的团队用户活动报表的屏幕截图](../media/teams-reports-user-activity-with-callouts.png "团队管理员中心中带有标注的团队用户活动报表的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 "团队用户活动" 报表，了解过去7天、28或90天的趋势。 |
|**2**   |每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |<ul><li>图表上的 X 轴表示特定报表的选定日期范围。 </li><li>Y 轴是参与活动的用户数。</li></ul>将鼠标悬停在给定日期上代表活动的点上，可查看该日期的活动实例数。 |
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击 " **1:1 通话**"、"**频道消息**" 或 "**聊天消息**"，仅查看与每个消息相关的信息。 更改所选内容不会更改表格中的信息。 |
|**5**   |此表提供了用户的使用情况细目。   <ul><li>"**显示名称**" 是用户的显示名称。 你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。</li><li>**1:1 通话**是指用户在指定时间段内参与的1:1 通话次数。</li><li>**信道消息**表示在指定时间段内用户在团队聊天中发布的唯一消息数。</li><li>"**答复邮件**" 表示在指定时间段内用户在团队频道中发布的唯一答复消息的数量。</li> <li>**发布消息**表示在指定时间段内用户在团队频道中发布的唯一发布消息的数量。</li><li>"**组织会议**" 是指用户在指定时间段内组织的计划会议数。</li><li>"**会议参与**时间" 是指用户在指定时间段内参与的计划会议数。</li><li>"**聊天消息**" 表示指定时间段内用户在私人聊天中发布的唯一消息数。</li><li>**紧急消息**表示用户在指定时间段内通过聊天发布的紧急邮件数。</li><li>**群组通话**表示用户在指定时间段内参与的组呼叫数。</li><li>"**音频时间**" 表示用户在指定时间段内参与的总音频时间。</li><li>**视频时间**是指用户在指定时间段内参与的总视频时间。</li><li>**屏幕共享时间**是指用户在指定时间段内参与的屏幕共享时间的总时间。</li>  <li>"**上次活动**" 是用户参与团队活动的最后日期（UTC）。</li> </ul>请注意，如果用户帐户在 Azure AD 中不再存在，则用户名在表中显示为 "-"。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。
|**6**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**7**   |你可以将报表导出到 CSV 文件，以便脱机分析。 单击 "**导出到 Excel**"，然后在 "**下载**" 选项卡上，单击 "**下载**" 以在准备就绪后下载报告。<br><br>!["下载" 选项卡的屏幕截图，显示导出的下载报告](../media/teams-reports-export-to-csv.png) <br>在 Excel 中查看报表时，你还会看到一个**Id**列，它表示团队 Id。 团队 ID 通常是一个字母数字字符串。 如果**Id**列显示为**\n**，则表示用户请求删除其信息。 ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
