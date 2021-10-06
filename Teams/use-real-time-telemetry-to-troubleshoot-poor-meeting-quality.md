---
title: 使用实时遥测排查会议质量不佳的问题
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用包含设备、网络和连接详细信息实时遥测，排查用户与Microsoft Teams的问题。
ms.openlocfilehash: 94b303687995ac3bcd765991dbfeb41c6f1459e7
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138358"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>使用实时遥测排查会议质量不佳的问题

> [!NOTE]
> 此功能目前以公共预览版提供，直到 2021 年底。 此后，想要实时查看其遥测数据的每个用户Microsoft Teams高级通信加载项。 有关详细信息，请参阅 [Microsoft Teams 高级通信附加产品](/MicrosoftTeams/teams-add-on-licensing/advanced-communications)。

本文介绍如何使用 Real-Time Analytics (RTA) 排查Microsoft Teams用户会议质量不佳的问题。 如果具有以下Real-Time之一，可以访问 Real-Time Analytics：

- Teams 管理员
- Teams通信支持专家
- Teams 通信支持工程师

有关管理员角色Teams，请参阅使用 Microsoft Teams[管理员角色管理Teams。](/MicrosoftTeams/using-admin-roles)

Real-Time Analytics 可让 IT 管理员查看重要用户的计划会议，并查看音频、视频、内容共享和网络相关的问题。 作为管理员，可以使用此遥测数据在会议期间调查这些问题并实时进行故障排除。

## <a name="what-is-real-time-analytics"></a>什么是 Real-Time Analytics？

目前，各个会议疑难解答可供[Teams在会议](use-call-analytics-to-troubleshoot-poor-call-quality.md)结束后通过呼叫分析进行。 Real-Time Analytics 允许管理员排查计划会议进行中的问题。

Real-Time Analytics 显示有关Teams帐户中每个用户的会议的详细信息，Office 365实时更新。 它包括有关设备、网络、连接、音频、视频和内容共享问题的信息，可帮助管理员更有效地对呼叫质量进行故障排除。

作为Teams管理员，可以完全访问每个用户的所有实时遥测数据。 此外，还可以为Azure Active Directory人员分配其他角色。 若要详细了解这些角色，请参阅 [授予支持和支持人员的权限](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>在何处查找每个用户实时遥测故障排除

若要查看用户的所有会议信息和数据，请转到 Teams[管理中心](https://admin.teams.microsoft.com)。 在 **"**  >  **用户管理用户**"下，选择一个用户，然后打开&个人资料页上的"会议"选项卡。 在 **"** 最近的会议"下，你将看到用户在过去 24 小时内参加的、实时遥测可用的会议的列表，包括任何进行中的会议。 如果会议未进行或没有实时遥测数据，它将显示在"过去的会议 **"中**。

![最近会议表的屏幕截图。](media/recent-meetings.png)

若要获取有关正在进行中会议的参与者的其他信息，包括其设备、网络和音频统计信息，请在"最近会议"中查找会议，然后选择"参与者"列 **下** 的链接。

![参与者详细信息表的屏幕截图。](media/participant-details.png)

若要查看正在进行中的会议给定用户的遥测数据，包括有关设备、网络、音频、视频和内容共享详细信息的信息，请选择"会议 **ID"。**

![调用分析用户会话数据的屏幕截图。](media/real-time-telemetry.png)

## <a name="measures-available-in-real-time-analytics"></a>Real-Time Analytics 中可用的度量值

|衡量指标名称 |单位 |良好阈值 |说明 |
|:---|:---|:---|:---|
|抖动 |毫秒 |小于 30 毫秒 |抖动是数据流数据包延迟变化的度量值。 如果此数据过高，音频可能会变得不稳定。 | 
|丢包 |百分比 |小于 5% |数据包无法到达其目标时，会发生数据包丢失。 丢包百分比取决于发送的数据包总数。 |
|往返行程时间 |毫秒 |小于 500 毫秒 |往返时间是单个数据包从客户端到达远程终结点并返回到客户端所花的时间。 往返时间长可能会导致流播放延迟。 例如，由于延迟，会议中的两个人无意中相互说话。 |
|音频 (比特率)  |Kbps 每秒千 (kbps)  |大于 24 Kbps |以千位/秒表示的音频流的吞吐量。 |
|比特 (视频&应用共享)  |每秒兆位 (Mbps)  | 仅信息 |以兆位/秒表示的视频流的吞吐量。 |
|帧速率 (视频)  |帧/秒 |360p 或更佳：25-30 FPS <br/> 270p 或更低：7-15 FPS |对于出站视频流，帧速率 (FPS) 是客户端正在发送的视频的每秒帧数。 低于此处的预期值可能表明系统资源约束、网络带宽不足或视频捕获设备行为不当。 不同的分辨率具有不同的可接受的 FPS 范围。 |
|帧速率 (应用共享)  |每秒帧数 (FPS)  |仅信息 |对于应用共享，帧速率是内容感知的，以确保根据需要发送多个帧，以确保获得良好的体验，同时避免在不需要发送帧时发送帧。 例如，在屏幕上共享文本文档只需要每秒 1 帧才能产生良好的体验，而共享具有更多活动的视频或内容将每秒帧数增加至最多 30 FPS，以产生更流畅的体验。 |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>实时遥测支持的客户端平台

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teams支持实时遥测的设备

- 计划 - Surface Hub
- 计划 - Teams 显示
- 公司 - 协作栏
- IP 电话设备

## <a name="limitations"></a>限制

- 实时遥测仅适用于计划的会议。 对于临时会议，例如"现在开会"、PSTN、1：1 呼叫和群组呼叫，实时遥测不可用。
- 实时遥测仅适用于计划实时事件的演示者。 它当前不可用于实时事件与会者。
- 在会议结束后的 24 小时内，实时遥测数据可用于"最近会议"下的会议。 24 小时后，你无法访问数据，会议将移至"**过去的会议"。** 如果会议超过 3 小时，则实时遥测仅可用于过去 *3 小时*。
- 使用较旧版本的遥测功能时，无法实时Teams。 如果没有可用的遥测数据，请尝试更新客户端。
- 如果外部参与者或匿名用户加入会议，其显示名称 **将显示为无法** 保留跨租户隐私。

## <a name="related-topics"></a>相关主题

[设置按用户调用分析](set-up-call-analytics.md)

[使用Microsoft Teams管理员角色来管理Teams。](/MicrosoftTeams/using-admin-roles)
