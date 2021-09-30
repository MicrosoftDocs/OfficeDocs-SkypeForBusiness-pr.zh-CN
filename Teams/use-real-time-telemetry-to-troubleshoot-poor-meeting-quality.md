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
ms.openlocfilehash: c33e3309995d82fd16e9eb1deb2fa5fe24b04330
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007893"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>使用实时遥测排查会议质量不佳的问题

> [!NOTE]
> 此功能目前以公共预览版提供。

本文介绍如何使用实时遥测来排查单个Microsoft Teams会议质量不佳的问题。 如果具有以下角色之一，可以看到实时遥测：

- Teams 管理员
- Teams通信支持专家
- Teams 通信支持工程师

有关管理员角色Teams，请参阅使用 Microsoft Teams[管理员角色管理Teams。](/MicrosoftTeams/using-admin-roles)

实时遥测可让 IT 管理员查看重要用户的计划会议，并查看音频、视频、内容共享和网络相关的问题。 作为管理员，可以在会议期间使用遥测数据调查这些问题，并实时进行故障排除。

## <a name="what-is-real-time-telemetry"></a>什么是实时遥测？

目前，各个会议疑难解答[Teams会议结束后](use-call-analytics-to-troubleshoot-poor-call-quality.md)通过呼叫分析为管理员提供。 实时遥测可让管理员排查计划会议进行中的问题。

实时遥测显示有关Teams帐户中每个用户的Office 365实时更新的详细信息。 它包括有关设备、网络、连接、音频、视频和内容共享问题的信息，可帮助管理员更有效地对呼叫质量进行故障排除。

作为Teams管理员，可以完全访问每个用户的所有实时遥测数据。 此外，还可以为Azure Active Directory人员分配其他角色。 若要详细了解这些角色，请参阅 [授予支持和支持人员的权限](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>在何处查找每个用户实时遥测故障排除

若要查看用户的所有会议信息和数据，请转到管理[Teams中心](https://admin.teams.microsoft.com)。 在 **"**  >  **用户管理用户**"下，选择一个用户，然后打开&个人资料页上的"会议"选项卡。 在 **"** 最近的会议"下，你将看到用户在过去 24 小时内参加的、实时遥测可用的会议的列表，包括任何进行中的会议。 如果会议未进行或没有实时遥测数据，它将显示在"过去的会议 **"中**。

![最近会议表的屏幕截图。](media/recent-meetings.png)

若要获取有关正在进行中会议的参与者的其他信息，包括其设备、网络和音频统计信息，请在"最近会议"中查找会议，然后选择"参与者"列 **下** 的链接。

![参与者详细信息表的屏幕截图。](media/participant-details.png)

若要查看正在进行中的会议给定用户实时遥测数据，包括有关设备、网络、音频、视频和内容共享详细信息的信息，请选择"会议 **ID"。**

![调用分析用户会话数据的屏幕截图。](media/real-time-telemetry.png)

## <a name="platforms-supported-for-real-time-telemetry"></a>实时遥测支持的平台

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-support-with-real-time-telemetry"></a>Teams设备支持实时遥测

- 公司 - Surface Hub
- 计划 - Teams 显示
- 公司 - 协作栏
- IP 电话设备

## <a name="limitations"></a>限制

- 实时遥测仅适用于计划的会议。 对于临时会议，例如"现在开会"、PSTN、1：1 呼叫和群组呼叫，实时遥测不起作用。
- 实时遥测仅适用于计划实时事件的演示者。 它当前不可用于实时事件与会者。
- 在会议结束后的 24 小时内，实时遥测数据可用于"最近会议"下的会议。 24 小时后，你无法访问数据，会议将移至"**过去的会议"。** 如果会议超过 3 小时，则实时遥测仅可用于过去 *3 小时*。
- 遥测数据不能与早期版本的 Teams。 如果没有可用的遥测数据，请尝试更新客户端。
- 如果外部参与者或匿名用户加入会议，其显示名称 **将显示为无法** 保留跨租户隐私。

## <a name="related-topics"></a>相关主题

[设置按用户调用分析](set-up-call-analytics.md)

[使用Microsoft Teams管理员角色来管理Teams。](/MicrosoftTeams/using-admin-roles)
