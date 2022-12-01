---
title: 在 Teams 中查看分析
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: rahulmi
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 了解 Teams 中的跨团队分析、每团队分析和每频道分析，这些分析允许用户查看他们所属的团队或频道的使用情况数据。
appliesto:
- Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.openlocfilehash: a6092a39616d78f4b85cab79fa754c770797c262
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199084"
---
# <a name="view-analytics-in-teams"></a>在 Teams 中查看分析

在 Microsoft Teams 中，用户可以查看他们所属团队和频道的分析。 此信息可让用户深入了解其团队的使用模式和活动。 用户可以在三个级别查看活动用户数、帖子数、回复数等数据。

- **跨团队分析** 可让用户在单个列表视图中大致了解其成员或所有者的所有团队的使用情况数据。
- **按团队分析** 为用户提供更精细的视图，显示特定团队的使用情况数据。
- **按通道分析** 为用户提供更精细的视图，显示特定通道的使用情况数据。

用户可以筛选这些视图中的任何一个，以查看指定时间段的数据。

## <a name="view-cross-team-analytics"></a>查看跨团队分析

1. 在 Teams 中，在团队列表底部的 **“加入或创建团队**”旁边，单击“ **管理团队**”。
2. 单击“ **分析** ”选项卡。
3. 选择一个日期范围以显示你所属或所有者的所有团队的使用情况数据。

    ![跨团队分析视图的屏幕截图。](../media/view-analytics-cross-team.png)

    |项目 |说明  |
    |--------|-------------|
    |**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。   |团队的名称。 |
    |**活动用户**   |在指定时间段内，团队中的活动用户数和团队活动趋势线。
    |**人员**   |指定时间段内团队中的总人数。 这包括团队所有者、团队成员和来宾。|
    |**来宾**   |在指定时间段内团队中的来宾数。 |
    |**职位**   |在指定时间段内在团队聊天中发布的新消息数。 |
    |**答复**   |在指定时间段内，团队聊天中的回复数。 |
    |**类型**   |团队是私人团队还是公共团队。|

## <a name="view-per-team-analytics"></a>查看每个团队的分析

1. 在 Teams 中，转到所需的团队，单击“ **更多选项 (...)**”，然后单击“ **管理团队**”。
2. 单击“ **分析** ”选项卡。
4. 选择日期范围以显示团队的使用情况数据。  

    ![每个团队分析视图的屏幕截图。](../media/view-analytics-per-team.png)

    |项目 |说明  |
    |--------|-------------|
    |**摘要**   |团队活动摘要，包括以下内容：<ul><li>**用户**：指定时间段内的用户总数。 这包括团队所有者、团队成员和来宾。</li> <li>**帖子**：在指定时间段内在团队聊天中发布的新消息数。</li><li>**答复** 数：在指定时间段内，团队聊天中的回复数。</li> <li>**应用**：添加到团队的应用数。</li><li>**会议**：在团队级别组织的 Teams 会议数。</li> </ul> |
    |**活动用户**   |活动和非活动用户数。|
    |**角色**   |按角色（包括团队所有者、团队成员和来宾）的用户数。|
    |**活动用户** 图表  |每日活动次数。 将鼠标悬停在给定日期的点上可查看该日期的活动用户数。|
    |**消息** 图表  |按日期在团队聊天中发布的消息总数。 将鼠标悬停在给定日期的点上，可查看该日期发布的新帖子数和回复数。|

> [!TIP]
> 还可以通过在跨团队分析视图中单击列表中的团队来查看每个 [团队分析](#view-cross-team-analytics)。

## <a name="view-per-channel-analytics"></a>查看每通道分析

1. 在 Teams 中，转到所需的频道，单击“ **更多选项 (...)**”，然后单击“ **管理频道**”。
2. 单击“ **分析** ”选项卡。
3. 选择日期范围以显示频道的使用情况数据。  

    ![每通道分析视图的屏幕截图。](../media/view-analytics-per-channel.png)

    |项目 |说明  |
    |--------|-------------|
    |**摘要**   |频道活动摘要，包括以下内容：<ul><li>**用户**：指定时间段内的用户总数。 这包括团队所有者、团队成员和来宾。</li> <li>**帖子**：在指定时间段内发布到通道的新消息数。</li><li>**答复** 数：指定时间段内通道中的答复数。</li> <li>**应用**：添加到通道的应用数。</li> </ul> |
    |**消息** 图表  |按日期发布到频道聊天的消息总数。 将鼠标悬停在给定日期的点上，可查看该日期发布的新帖子数和回复数。|

> [!TIP]
> 还可以通过在每团队分析视图的下拉列表框中选择频道来查看 [每通道分析](#view-per-team-analytics)。
    
> [!NOTE]
> 我们将活动用户定义为在桌面客户端、移动客户端和 Web 客户端中执行有意操作的用户。 有意操作的示例包括开始聊天、拨打电话、共享文件、在团队中编辑文档、参与会议等。 我们将取消被动操作，例如自动启动、最小化屏幕或关闭应用。 我们还对单个用户 ID 中的所有操作进行重复。

## <a name="related-topics"></a>相关主题

- [查看团队的分析](https://support.office.com/article/view-analytics-for-your-teams-5b8ad4b1-af34-4217-aff4-cd11a820b56b)
- [Teams 分析和报告](teams-reporting-reference.md)