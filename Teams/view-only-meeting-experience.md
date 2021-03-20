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
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875052"
---
# <a name="teams-view-only-meeting-experience"></a>Teams 仅查看会议体验

> [!Note]
> Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供了仅查看广播。 该功能将于 2021 年 3 月 1 日启用，默认为“关闭”。 Microsoft 365 政府社区云 (GCC) 中的该功能将于 2021 年 3 月底开始推出。 政府社区云高 (GCCH) 和国防部 (DoD) 将在日后推出。 如果想让该功能默认为 “启动”，必须在该日期之后更改默认策略。 使用 PowerShell 启用策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。

> [!Note]
> 如果会议或网络研讨会达到饱和状态，Teams 将无缝扩展至容纳 10,000 人的仅限观看广播体验。 另外，在这个远程工作增加的时期，利用更大规模的 20,000 人广播到今年年底。

Microsoft Teams 允许最多 10,000 名与会者加入一个 Teams 会议。 达到主会场的容量后，更多的参会人员将参加仅查看体验。

先加入会议的参会者，以会议容量为限，将获得完整的 Teams 会议体验。 他们可以共享音频和视频、查看共享视频、并参与会议聊天。

在达到主会场容量后加入的与会者将有仅查看体验。

我们有完整的 Android 和 iOS 手机支持供与会者加入。

> [!Note]
> 目前，WWW 的聊天和电话会议人数限制是 300 人，GCC、GCC High 和 DoD 的是 250 人。

凡是拥有 E3/E5/A3/A5 SKU 的组织者，默认禁用仅查看体验。 无需进一步配置或设置。

## <a name="disable-teams-view-only-experience"></a>禁用 Teams 仅查看体验

管理员可以使用 PowerShell 禁用仅查看体验。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

未来，管理员还可以在 Teams 管理中心中禁用仅查看体验。

## <a name="impact-to-users"></a>对用户的影响

用户的体验会因多种因素而有所不同。

当主会场容量已满时，如有下列情况之一，与会者将无法参加会议:

- 一位管理员已经禁用了团队仅查看体验。
- 与会者没有绕过大厅的权限。

当达到主会议的容量时，会议组织者和演讲者会看到一条横幅，通知他们会议容量已经达到，新的参会者将加入仅查看与会者中。

  ![为组织者和演讲者提供 Teams 客户端和横幅信息](media/chat-and-banner-message.png)

当达到主会议的容量时，会议平台会在预加入界面上通知他们以仅查看模式加入。

  ![Teams 预加入屏幕和告诉参与者他们将以纯视图模式加入的信息](media/view-only-pre-join-screen.png)

如果有空间，用户将始终加入主会议。 如果主会场达到容纳量，有一名或多名与会者离开主会场，则主会场有可用容量。 加入 (或重新加入) 会议的与会者将加入主会议，直到会议再次达到饱和。 处于仅查看体验中的参会者不会自动晋升到主会议，目前无法手动晋升到主会议。

如果没有确定演示者/与会者的角色，主会场的位置将按照先到先得的原则填补。 一旦达到会议容量，所有其他用户都将以进查看体验加入。

## <a name="impact-to-meeting-presenters"></a>对会议演示者的影响

对会议演示者的限制包括：

- 你不会有任何关于仅查看与会者的信息。 我们不支持仅查与会者的电子数据展示。
- 用户无法看到仅查看的与会者。
- 不能从会议中删除仅查看的与会者。

> [!Note]
> 出席人数将只反映会议中的人员，而不反映仅查看会议室中的人员。 因此，演示者无法准确统计仅查看体验中的用户。

## <a name="experience-for-view-only-attendees"></a>仅查看与会者的体验

通过 Teams 的仅查看体验，与会者可以:

- 收听主 Teams 会议中参与者的发言。
- 查看当前发言者的视频源 (如果当前发言者正在共享视频)。
- 查看使用共享桌面功能共享的内容。

仅查看中的与会者将无法在会议中体验以下选项:

- 如果与会者没有根据设定的大厅政策或选项绕过大厅的权限，加入会议。
- 使用音频会议加入仅查看会议室。
- 使用 Microsoft Teams 会议室系统或使用云视频互操作(CVI) 服务，加入仅查看会议室。
- 共享他们的音频或视频。
- 查看或参与会议聊天。
- 除非与会者是主动发言的人，否则可以看到会议参与者的视频源。
- 请参阅使用本机共享 PowerPoint 功能或单个应用程序共享 (除桌面共享外) 共享的 PowerPoint 文件。

## <a name="view-only-feature-limitations"></a>仅查看功能限制

- 无论该会议的实时字幕设置如何，仅查看的与会者将始终看到实时字幕。 目前只支持英文字幕。
- 仅查看的与会者将得到流媒体处理技术的支持。
- 仅查看的与会者不会列入出席报告中。
- 仅查看的与会者将有单一的视频体验。 他们可以看到活动发言人或共享的内容，但不能两者同时看到。
- 我们当前不支持 **库**、**大型库** 或仅供与会者浏览的 **同框场景模式**。  
- 仅查看的与会者不会有和普通与会者一样的延迟。 <sup>1</sup>

  <sup>1</sup> 仅查看的与会者将在会议上有 30 秒的视频和音频延迟。  
