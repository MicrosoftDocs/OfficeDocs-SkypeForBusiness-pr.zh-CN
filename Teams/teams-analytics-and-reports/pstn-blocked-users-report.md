---
title: Microsoft 团队 PSTN 已阻止用户报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何使用 Microsoft 团队管理中心中的 PSTN "阻止的用户" 报表，大致了解组织中被阻止进行 PSTN 呼叫的团队用户。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d7bfff166eec388247b65760c3338cb892984f3
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131674"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft 团队 PSTN 已阻止用户报告

Microsoft 团队管理中心中的 PSTN "已阻止用户" 报表显示你的组织中阻止在团队中进行 PSTN 呼叫的用户。 您可以查看有关每个被阻止用户的详细信息，包括其分配的电话号码以及阻止他们进行呼叫的原因。

## <a name="view-the-report"></a>查看报告

在 Microsoft 团队管理中心的左侧导航中，单击 "**分析" & 报告** > **使用情况报告**。 在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 " **PSTN 阻止的用户**"，然后单击 "**运行报告**"。

![管理中心的 PSTN 已阻止用户报告报告的屏幕截图](../media/teams-reports-pstn-blocked-users-with-callouts.png "Microsoft 团队管理中心中带有编号标注的 PSTN 已阻止用户报告的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有一个生成日期的日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**2**   |X 轴是日期。 Y 轴是用户数。 <br>将鼠标悬停在给定日期的点上可查看该日期阻止的用户数。 |
|**3**   |该表提供阻止进行 PSTN 呼叫的所有用户的细目。  它显示已分配电话系统或音频会议的所有用户，并提供有关每个用户的详细信息。 <ul><li>"**显示名称**" 是用户的显示名称。 你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。 </li> <li>"**电话**" 表示分配给用户的号码。</li> <li>"已**阻止" 原因**是阻止用户进行呼叫的原因。</li><li>**阻止的操作**告诉你用户是否被阻止或取消阻止在团队中进行 PSTN 呼叫。</li> <li>"**阻塞时间**" 是阻止用户进行呼叫的日期和时间（UTC）。</li></li> </ul>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**4**   |选择“**编辑列**”可在表格中添加或删除列。|
|**5**   |选择 "**全屏**" 以全屏模式查看报表。|

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)