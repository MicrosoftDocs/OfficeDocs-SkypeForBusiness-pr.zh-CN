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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2af0ae753357497be6ea54b89534f2220b7cbf6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732291"
---
# <a name="teams-view-only-meeting-experience"></a>Teams 仅查看会议体验

> [!Note]
> Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供了仅查看广播。 该功能将于 2021 年 3 月 1 日启用，默认为“关闭”。 Microsoft 365 政府社区云 (GCC) 中的该功能将于 2021 年 3 月底开始推出。 政府社区云高 (GCCH) 和国防部 (DoD) 将在日后推出。 如果想让该功能默认为 “启动”，必须在该日期之后更改默认策略。 使用 PowerShell 启用策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。

> [!Note]
> 如果会议达到容纳人数上限，Teams 将无缝扩展以容纳 10,000 人的仅限查看广播体验。 另外，在这个远程工作增加的时期，利用更大规模的 20,000 人广播到今年年底。 网络研讨会当前不支持仅限查看广播体验。

Microsoft Teams 允许最多 10,000 名与会者加入一个 Teams 会议。 达到主会议的容纳人数后（即 1000 个用户进入会议时），其他与会者将以仅限查看体验加入会议。

先加入会议的与会者（以主会议容纳人数为限）将获得完整的 Teams 会议体验。 他们可以共享音频和视频、查看共享视频、并参与会议聊天。

在达到主会场容量后加入的与会者将有仅查看体验。

与会者将能够通过桌面、Web 和 Teams 移动设备（Android 和 iOS）加入仅限查看体验。

> [!Note]
> “主会议”的当前限制容纳人数，即完全交互式用户的数量，为 1000，包括 GCC 和网络研讨会。

## <a name="teams-view-only-experience-controls"></a>Teams 仅限查看体验控件

你可以使用 [SkypeForBusiness PowerShell 模块](/powershell/module/skype/?view=skype-ps)中的 [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)cmdlet 或至少版本 2.0.0 的 [MicrosoftTeams 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)启用仅限查看体验。

若要使用建议的 `MicrosoftTeams` 模块：

```PowerShell
Install-Module -Name "MicrosoftTeams" -MinimumVersion 2.0.0
Connect-MicrosoftTeams
```

若要启用仅限查看体验，可以使用以下 PowerShell 代码片段：

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

若要禁用仅限查看体验，还可以使用 PowerShell。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

未来，你将能够在 Teams 管理中心启用或禁用仅限查看体验。

## <a name="impact-to-users"></a>对用户的影响

用户的体验会因多种因素而有所不同。

当主会场容量已满时，如有下列情况之一，与会者将无法参加会议:

- 管理员已为组织者或整个租户禁用 Teams 仅限查看体验。
- 仅限查看的与会者不能绕过大厅。 例如，如果会议组织者选择仅让 **我的组织中的人员** 绕过大厅，而组织外部的与会者尝试以仅限查看与会者的身份加入，则他们将无法加入会议。

达到主会议容纳人数时，会议组织者和演示者会看到一条横幅，通知他们新与会者将作为仅限查看与会者加入会议。

  ![组织者和演示者的 Teams 客户端和标题消息。](media/chat-and-banner-message.png)

当达到主会议的容量时，会议平台会在预加入界面上通知他们以仅查看模式加入。

  ![Teams 预加入屏幕和参与者信息告知他们将以仅限查看模式加入。](media/view-only-pre-join-screen.png)

如果有空间，用户将始终加入主会议。 如果主会场达到容纳量，有一名或多名与会者离开主会场，则主会场有可用容量。 加入 (或重新加入) 会议的与会者将加入主会议，直到会议再次达到饱和。 处于仅限查看体验的与会者不会自动升级到主会议，也不能手动升级到主会议。

如果已设置演示者和与会者角色，并且演示者在主会议达到容纳人数上限后尝试加入会议，则他们将作为仅限查看参与者加入会议，并且与其他仅限查看参与者具有相同的限制。 确保所有演示者参加主会议的支持将在稍后推出。 将始终保证组织者在主会议中的空间。

## <a name="impact-to-meeting-presenters-and-organizers"></a>对会议演示者和组织者的影响

对会议演示者和组织者的限制包括：

- 你不会有任何关于仅查看与会者的信息。 我们不支持仅查与会者的电子数据展示。
- 主会议中的用户无法看到仅限查看与会者。
- 不能从会议中删除仅查看的与会者。

> [!Note]
> 与会者人数仅反映主会议中的人数，而不是仅限查看会议室中的人数。 因此，演示者无法准确统计仅查看体验中的用户。

## <a name="experience-for-view-only-attendees"></a>仅查看与会者的体验

通过 Teams 的仅查看体验，与会者可以:

- 收听主 Teams 会议中参与者的发言。
- 查看当前发言者的视频源 (如果当前发言者正在共享视频)。
- 查看使用共享桌面或屏幕功能共享的内容。

仅查看中的与会者将无法在会议中体验以下选项:

- 如果与会者没有根据设定的大厅政策或选项绕过大厅的权限，加入会议。
- 使用音频会议加入仅查看会议室。
- 使用 Microsoft Teams 会议室系统或使用云视频互操作 (CVI) 服务，加入仅限查看会议室。
- 共享他们的音频或视频。
- 查看或参与会议聊天。
- 除非与会者是主动发言的人，否则可以看到会议参与者的视频源。
- 查看使用 PowerPoint Live 功能或单个应用程序共享（桌面或屏幕共享除外）共享的 PowerPoint 文件。
- 在会议中举手。
- 发送或查看反应。
- 与集成到 Teams 会议中的任何 3P 应用交互，包括投票。

## <a name="view-only-feature-limitations"></a>仅查看功能限制

- 仅限查看的与会者将只能在桌面和 Web 上看到实时辅助字幕。 目前只支持英文字幕。
- 仅限查看的与会者无法注册网络研讨会。
- 仅查看的与会者将得到流媒体处理技术的支持。
- 仅查看的与会者不会列入出席报告中。
- 仅查看的与会者将有单一的视频体验。 他们可以看到活动发言人或共享的内容，但不能两者同时看到。
- 我们当前不支持 **库**、**大型库** 或仅供与会者浏览的 **同框场景模式**。
- 仅限查看的与会者仅受以下大厅政策的支持：“仅限您”、“我组织中的人员和来宾”、“我组织中的人员和受信任组织中的人员以及来宾”和“所有人”。 如果你使用的大厅策略不支持仅限查看与会者，则该会议将拒绝仅限查看与会者加入会议。 
- 仅限查看与会者的延迟时间与普通与会者的延迟时间不同。<sup>1</sup>

  <sup>1</sup> 仅查看的与会者将在会议上有 30 秒的视频和音频延迟。  
