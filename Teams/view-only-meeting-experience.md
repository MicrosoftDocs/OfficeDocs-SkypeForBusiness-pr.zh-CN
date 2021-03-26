---
title: 仅查看会议体验
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解管理员、演示者和与会者的 Teams 专用视图会议体验
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25cd674e5f93e4f52f0a2cecd2acff97e4844834
ms.sourcegitcommit: f4393657584666842e874d526a08cfa1137b911d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215327"
---
# <a name="teams-view-only-meeting-experience"></a>Teams 仅查看会议体验

> [!Note]
> Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供了仅查看广播。 该功能将于 2021 年 3 月 1 日启用，默认为“关闭”。 Microsoft 365 政府社区云 (GCC) 中的该功能将于 2021 年 3 月底开始推出。 政府社区云高 (GCCH) 和国防部 (DoD) 将在日后推出。 如果想让该功能默认为 “启动”，必须在该日期之后更改默认策略。 使用 PowerShell 启用策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。

> [!Note]
> 如果会议或网络研讨会达到饱和状态，Teams 将无缝扩展至容纳 10,000 人的仅限观看广播体验。 另外，在这个远程工作增加的时期，利用更大规模的 20,000 人广播到今年年底。

Microsoft Teams 允许最多 10,000 名与会者加入一个 Teams 会议。 在达到主会议的容量后 (在 WW 中为 300 人，GCC 用户为 250 人进入会议) 时，其他与会者将加入仅查看体验。

首先加入会议的与会者（最多是主会议的容量）将获得完整的 Teams 会议体验。 他们可以共享音频和视频、查看共享视频、并参与会议聊天。

在达到主会场容量后加入的与会者将有仅查看体验。

与会者可以通过 Android 和 iOS 桌面版、Web 版和 Teams (加入仅查看) 。

> [!Note]
> "主会议"的当前限制容量（换句话说，完全交互用户的数量）在 WW 中为 300，GCC、GCC High 和 DoD 为 250。

## <a name="teams-view-only-experience-controls"></a>Teams 仅查看体验控件

使用 PowerShell 启用仅查看体验。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

若要禁用仅查看体验，还可使用 PowerShell。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

将来，你将能够在 Teams 管理中心启用或禁用仅查看体验。

## <a name="impact-to-users"></a>对用户的影响

用户的体验会因多种因素而有所不同。

当主会场容量已满时，如有下列情况之一，与会者将无法参加会议:

- 管理员已针对组织者或整个租户禁用了 Teams 仅查看体验。
- 仅查看与会者不能绕过大厅。 例如，如果会议的组织者选择仅让"我组织的人"绕过大厅，而组织外部的与会者尝试以仅查看与会者的与会者加入，则他们将被拒绝。

当达到主会议的容量时，会议组织者和演示者将看到一个横幅，通知他们新与会者将作为仅查看的与会者加入。

  ![为组织者和演讲者提供 Teams 客户端和横幅信息](media/chat-and-banner-message.png)

当达到主会议的容量时，会议平台会在预加入界面上通知他们以仅查看模式加入。

  ![Teams 预加入屏幕和告诉参与者他们将以纯视图模式加入的信息](media/view-only-pre-join-screen.png)

如果有空间，用户将始终加入主会议。 如果主会场达到容纳量，有一名或多名与会者离开主会场，则主会场有可用容量。 加入 (或重新加入) 会议的与会者将加入主会议，直到会议再次达到饱和。 处于仅查看体验中的参会者不会自动晋升到主会议，目前无法手动晋升到主会议。

如果已设置演示者和与会者角色，并且演示者在 的主会议达到容量后尝试加入会议，他们将作为仅查看的与会者加入，并且与其他仅查看的与会者具有相同的限制。 支持确保所有演示者加入主会议将在以后推出。 组织者将始终获得主会议空间保证。

## <a name="impact-to-meeting-presenters"></a>对会议演示者的影响

对会议演示者的限制包括：

- 你不会有任何关于仅查看与会者的信息。 我们不支持仅查与会者的电子数据展示。
- 主会议中的用户看不到仅查看与会者。
- 不能从会议中删除仅查看的与会者。

> [!Note]
> 与会者计数仅反映主会议中的人员，而不是仅查看会议室中的人员。 因此，演示者无法准确统计仅查看体验中的用户。

## <a name="experience-for-view-only-attendees"></a>仅查看与会者的体验

通过 Teams 的仅查看体验，与会者可以:

- 收听主 Teams 会议中参与者的发言。
- 查看当前发言者的视频源 (如果当前发言者正在共享视频)。
- 查看使用共享桌面或屏幕功能共享的内容。

仅查看中的与会者将无法在会议中体验以下选项:

- 如果与会者没有根据设定的大厅政策或选项绕过大厅的权限，加入会议。
- 使用音频会议加入仅查看会议室。
- 使用 Microsoft Teams 会议室系统或 CVI 服务中的云视频互操作 (仅) 聊天室。
- 共享他们的音频或视频。
- 查看或参与会议聊天。
  - 前 1000 (或 300（具体取决于主会议限制) 受邀加入会议的用户将被添加到聊天中。
  - 虽然仅查看用户不会在会议中看到聊天，但如果是受邀的前 350 名用户，他们仍可以在主应用上聊天。
  - 相反，如果交互式用户不是前 350 位受邀加入会议的用户的一部分，他们将无法访问主 Teams 应用和会议中的会议聊天。
- 除非与会者是主动发言的人，否则可以看到会议参与者的视频源。
- 查看使用 PowerPoint Live 功能共享的 PowerPoint 文件，或者使用桌面或屏幕共享功能 (应用程序共享共享) 。
- 在会议中举手。
- 发送或查看回应。
- 与集成到 Teams 会议的任何 3P 应用（包括投票）交互。

## <a name="view-only-feature-limitations"></a>仅查看功能限制

- 仅查看与会者只能在桌面和 Web 上看到实时字幕。 目前只支持英文字幕。
- 仅查看的与会者将得到流媒体处理技术的支持。
- 仅查看的与会者不会列入出席报告中。
- 仅查看的与会者将有单一的视频体验。 他们可以看到活动发言人或共享的内容，但不能两者同时看到。
- 我们当前不支持 **库**、**大型库** 或仅供与会者浏览的 **同框场景模式**。  
- 仅查看的与会者不会有和普通与会者一样的延迟。 <sup>1</sup>

  <sup>1</sup> 仅查看的与会者将在会议上有 30 秒的视频和音频延迟。  
