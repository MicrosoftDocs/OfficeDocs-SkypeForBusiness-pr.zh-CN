---
title: Microsoft 团队实时事件使用率报告
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
description: 了解如何使用 Microsoft 团队管理中心中的 "团队实时事件使用率" 报表大致了解组织中的团队活动事件活动。
appliesto:
- Microsoft Teams
ms.openlocfilehash: af8a7d0225c3098f48de689a15921cd6f1f2f1c9
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827240"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft 团队实时事件使用率报告

Microsoft 团队管理中心中的 "团队实时事件使用率" 报表显示组织中的实时事件的活动概述。 你可以查看每个事件的使用信息，包括事件状态、开始时间、视图和生产类型。 你可以深入了解使用趋势，并查看你的组织安排、提出和生成实时事件的人员。

## <a name="view-the-report"></a>查看报告

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**分析" & 报告** > **使用情况报告**。 在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 "**团队实时事件使用率**"。
2. 在 "**日期范围**" 下，选择预定义区域或设置自定义范围。 你可以将区域设置为在当前日期前后的六个月显示数据。
3. 可选在 "**管理器**" 下，你可以选择仅显示由特定用户组织的实时事件。
4. 单击 "**运行报告**"。  

    ![团队管理员中心中具有标注的团队实时事件使用率报表的屏幕截图](../media/teams-live-event-usage-report-with-callouts.png "团队管理员中心中具有标注的团队实时事件使用率报表的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 "团队实时事件" 报表，了解过去7天、28天或您设置的自定义日期范围内的趋势。 |
|**2**   |每个报表都有一个生成日期的日期。 当刷新页面时，该报告会反映接近的实时活动。 |
|**3**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴是汇总视图计数。</li> </ul>将鼠标悬停在给定日期的点上可查看该日期上所有实时事件的视图数。|
|**4**   |此表提供了每个实时事件的细目。 <ul><li>**事件**是实时事件的显示名称。 单击事件名称以获取有关事件的[更多详细信息](#view-event-details)。 </li> <li>"**开始时间**" 指事件的开始日期和时间。</li> <li>**事件状态**显示是否已发生事件。  </li><li>"**组织者**" 是事件组织者的名称。</li> <li>**演示**者是事件演示者的名称。</li><li>**发生器**是事件发生器的名称。</li><li>"**视图**" 是唯一视图的数量。</li><li>**录制**显示是否打开或关闭录制设置。</li><li>**生产类型**显示是否在团队或由外部应用程序或设备生成事件。</li></li> </ul>请注意，如果用户帐户在 Azure AD 中不再存在，则用户名在表中显示为 "-"。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**5**   |选择“**编辑列**”可在表格中添加或删除列。|

## <a name="view-event-details"></a>查看事件详细信息

实时事件详细信息页面提供实时事件的详细信息摘要，并列出与事件相关联的所有文件，包括脚本和录制。 单击文件名以查看或下载该文件。

![显示实时事件详细信息的屏幕截图](../media/teams-live-event-usage-report-event-detail.png)

如果您的组织已启用[蜂巢](https://www.hivestreaming.com/partners/integration-partners/microsoft/)ECDN 或[Kollective](https://kollective.com) eCDN，则可以通过单击 "合作伙伴报告" 链接来获取其他与会者分析。

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
- [什么是 Teams 实时事件？](../teams-live-events/what-are-teams-live-events.md)