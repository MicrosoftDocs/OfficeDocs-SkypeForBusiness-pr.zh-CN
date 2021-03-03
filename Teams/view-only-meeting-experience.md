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
description: 了解管理员、演示者和与会者的 Teams 仅查看会议体验
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49f65e1ff47caefd61a9b2753b12da23fd2184e9
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401316"
---
# <a name="teams-view-only-meeting-experience"></a>Teams 仅查看会议体验

> [!Note]
> 仅查看会议体验将于 2021 年 3 月初提供。 此功能将在 2021 年 3 月 1 日启用为默认关闭。 如果希望将该功能设置为"默认打开"，则必须在此日期之后更改默认策略。 使用 PowerShell 启用策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` 。

> [!Note]
> 如果会议或网络研讨会达到容量要求，Teams 将无缝缩放，以容纳 10，000 人仅查看的直播体验。 此外，在这期间增加远程工作，充分利用今年年底甚至更多的 20，000 人直播。

Microsoft Teams 允许最多 10，000 名与会者加入 Teams 会议。 达到主会议的容量后，其他与会者将加入仅查看体验。

首先加入会议的与会者（最多是会议容量）将获得完整的 Teams 会议体验。 他们可以共享音频和视频、查看共享的视频以及参与会议聊天。

达到主要会议容量后加入的与会者将拥有仅查看体验。

我们提供完整的 Android 和 iOS 移动支持，与会者可加入。

> [!Note]
> 在 WW 中，可以聊天和呼叫会议的人数当前限制为 300 人，GCC、GCC High 和 DoD 中为 250 人。

对于拥有 E3/E5/A3/A5 SKU 的任何组织者，默认禁用仅查看体验。 无需进一步配置或设置。

## <a name="disable-teams-view-only-experience"></a>禁用 Teams 仅查看体验

管理员可以使用 PowerShell 禁用仅查看体验。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

将来，管理员还可以在 Teams 管理中心禁用仅查看体验。

## <a name="impact-to-users"></a>对用户的影响

用户的体验因若干因素而异。

当达到主会议的容量时，如果满足以下任一条件，与会者将无法加入会议：

- 管理员已禁用 Teams 仅查看体验。
- 与会者无权绕过大厅。

达到主会议的容量后，会议组织者和演示者将看到一个横幅，通知他们已达到会议容量，新与会者将加入仅查看的与会者。

  ![组织者和演示者的 Teams 客户端和横幅混乱](media/chat-and-banner-message.png)

当达到主会议的容量时，会议与会者将在加入前屏幕上通知他们以仅查看模式加入。

  ![Teams 预加入屏幕和参与者的消息，告知他们将在仅查看模式下加入](media/view-only-pre-join-screen.png)

如果有空间，用户始终会加入主会议。 如果主会议达到容量，并且一个或多个与会者离开主会议，则主会议具有可用容量。 加入会议或 (会议) 与会者将加入主会议，直到再次达到容量。 处于"仅查看"体验的与会者不会自动提升为主会议，当前无法手动提升为主会议。

如果尚未设置演示者/与会者角色，主会议中的空间将先到先得地填充。 达到会议容量后，所有其他用户将使用仅查看体验加入。

## <a name="impact-to-meeting-presenters"></a>对会议演示者的影响

会议演示者的限制包括：

- 您将没有有关仅查看与会者的信息。 我们不支持仅查看与会者的 E-discovery。
- 用户看不到仅查看的与会者。
- 不能从会议中删除仅查看与会者。

> [!Note]
> 与会者计数将仅反映会议中的人员，而不是溢出会议室中的人员。 因此，演示者无法获取仅查看体验中的人员的确切计数。

## <a name="experience-for-view-only-attendees"></a>仅查看与会者的体验

Teams 仅查看体验允许与会者：

- 在 Teams 主要会议中听取参与者的意见。
- 如果活动发言人正在共享视频， (活动扬声器的视频源) 。
- 查看使用共享桌面功能共享的内容。

仅查看与会者将无法在会议中体验以下选项：

- 如果与会者没有权限根据设置的大厅策略或选项绕过大厅，请加入会议。
- 通过音频会议加入溢出会议室。
- 通过 Microsoft Teams Room 系统或通过 CVI 云视频互操作 (加入溢出) 服务。
- 共享其音频或视频。
- 查看或参与会议聊天。
- 查看会议参与者的视频源，除非参与者是活动发言人。
- 查看使用本机共享 PowerPoint 功能共享的 PowerPoint 文件或桌面共享 (应用程序共享) 。

## <a name="view-only-feature-limitations"></a>仅查看功能限制

- 无论会议的实时字幕设置如何，仅查看的与会者将始终看到实时字幕。 目前仅支持英语字幕。
- 流式处理技术将支持仅查看与会者。
- 仅查看的与会者不会包括在出席报告中。
- 仅查看与会者将拥有单个视频体验。 他们可以看到活动发言人或正在共享的内容，但不能同时看到这两者。
- 我们当前不支持仅查看与会者的库、大型库或"共同"模式布局。   
- 仅查看与会者的延迟与普通与会者不同。 <sup>1</sup>

  <sup>1</sup> 个仅查看与会者将在会议进行 30 秒的视频和音频延迟。  

## <a name="related-topics"></a>相关主题

- [Teams 的高级通信加载项](teams-add-on-licensing/advanced-communications.md)
- [Teams 限制和规范](limits-specifications-teams.md)
