---
title: Microsoft Teams 用户活动报告
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/22/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何使用 Microsoft 团队管理中心中的 "团队用户活动" 报表查看组织中的用户使用团队的方式。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217ae2d1344c8998e9dd8035f8c96d48a110a6d
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433005"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams 用户活动报告

团队用户活动报表使你可以深入了解你的组织中的用户在团队中执行的活动类型。 例如, 你可以查看多少个用户通过1:1 呼叫进行通信、通过通道消息进行通信的用户数以及参与私人聊天消息的用户数。

![团队用户活动报表的屏幕截图](../media/teams-reports-user-activity.png "Microsoft 团队管理中心中 \"团队用户活动\" 报表的屏幕截图")

## <a name="view-the-report"></a>查看报告

1. 转到 Microsoft 团队管理中心, 在左侧导航中单击 "**分析 & 报表**", 然后在 "**报表**" 下选择 "**团队用户活动**"。 
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。 

## <a name="interpret-the-report"></a>解释报告

![带有编号标注的 "团队用户活动" 报表的屏幕截图](../media/teams-reports-user-activity-with-callouts.png "Microsoft 团队管理中心中具有编号标注的 \"团队用户活动\" 报表的屏幕截图")

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 "团队用户活动" 报表, 了解过去7天或28天的趋势。 |
|**2**   |每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |<ul><li>图表上的 X 轴表示特定报表的选定日期范围。 </li><li>Y 轴是参与活动的用户数。</li></ul>将鼠标悬停在给定日期上代表活动的点上, 可查看该日期的活动实例数。 |
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如, 单击 " **1:1 通话**"、"**频道消息**" 或 "**聊天消息**", 仅查看与每个消息相关的信息。 更改所选内容不会更改表格中的信息。 |
|**5**   |此表提供了用户的使用情况细目。   <ul><li>"**显示名称**" 是用户的显示名称。 你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。</li><li>**1:1 通话**是指用户在指定时间段内参与的1:1 通话次数。</li><li>**信道消息**表示在指定时间段内用户在团队聊天中发布的唯一消息数。</li> <li>"**聊天消息**" 表示指定时间段内用户在私人聊天中发布的唯一消息数。</li>  <li>"**上次活动**" 是用户参与团队活动的最后日期 (UTC)。</li> </ul>要查看希望在表格中显示的信息，请确保向表格添加了相关列。
|**6**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**7**   |你可以将报表导出到 CSV 文件, 以便脱机分析。 单击 "**导出到 Excel**", 然后在 "**下载**" 选项卡上, 单击 "**下载**" 以在准备就绪后下载报告。<br>!["下载" 选项卡的屏幕截图, 显示已导出的要下载的报表](../media/teams-reports-export-to-csv.png)||

## <a name="related-topics"></a>相关主题
- [Teams 分析和报告](teams-reporting-reference.md)
- [Teams 使用情况报告](teams-usage-report.md)
- [Teams 设备使用报告](device-usage-report.md)