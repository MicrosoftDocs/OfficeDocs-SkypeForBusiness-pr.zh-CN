---
title: 管理内容共享的会议策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: 了解如何在 Teams 中管理用于内容共享的会议策略设置。
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598712"
---
# <a name="meeting-policy-settings---content-sharing"></a>会议策略设置 - 内容共享

<a name="bkcontentsharing"> </a>

本文介绍与内容共享相关的以下会议策略设置：

- [屏幕共享模式](#screen-sharing-mode)
- [允许参与者授予或请求控制权](#allow-a-participant-to-give-or-request-control)
- [允许外部参与者授予或请求控制权](#allow-an-external-participant-to-give-or-request-control)
- [允许 PowerPoint 共享](#allow-powerpoint-sharing)
- [允许白板](#allow-whiteboard)
- [允许共享笔记](#allow-shared-notes)

## <a name="screen-sharing-mode"></a>屏幕共享模式

此设置是按组织者策略和按用户策略的组合。 此设置控制是否在用户的会议中允许桌面和窗口共享。 未分配任何策略的会议参与者 (匿名、来宾、B2B 和联合) 继承会议组织者的策略。

|设置值 |行为  |
|---------|---------|
|**整个屏幕**    | 会议允许完全桌面共享和应用程序共享 |
|**单个应用程序**   | 会议允许应用程序共享        |
|**已禁用**     |会议中的屏幕共享和应用程序共享已关闭。       |

让我们看看以下示例。

|用户 |会议策略 |屏幕共享模式 |
|---------|---------|---------|
|Daniela  | 全局   | 整个屏幕 |
|Amanda   | Location1MeetingPolicy  | 已禁用 |

Daniela 主持的会议允许会议参与者共享其整个屏幕或特定应用程序。 如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为禁用了策略设置。 在 Amanda 主持的会议中，不允许任何人共享其屏幕或单个应用程序，而不考虑分配给他们的屏幕共享模式策略。  因此，Daniela 无法共享她的屏幕或 Amanda 会议中的单个应用程序。  

目前，如果用户使用的是 Google Chrome，则他们无法播放视频或在 Teams 会议中共享其屏幕。

## <a name="allow-a-participant-to-give-or-request-control"></a>允许参与者授予或请求控制权

此设置是按用户的策略。 此设置控制用户是否可以将共享桌面或窗口控制权授予其他会议参与者。 若要进行控制，请将鼠标悬停在屏幕顶部。

如果为用户启用此设置，共享会话中的顶部栏中会显示"授予控制权"选项。

![显示"授予控制权"选项的屏幕截图](media/meeting-policies-give-control.png)

如果为用户关闭设置，则"授予 **控制权** "选项不可用。

![显示"授予控制权"选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

让我们看看以下示例。

|用户 |会议策略  |允许参与者授予或请求控制权 |
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Babek    | Location1MeetingPolicy        | 关   |

Daniela 可以将共享桌面或窗口的控制权授予由 Babek 组织的会议的其他参与者。 但是，Babek 无法将控制权授予其他参与者。

若要使用 PowerShell 控制谁可以授予控制权或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。

> [!NOTE]
> 若要在共享期间授予并控制共享内容，双方必须使用 Teams 桌面客户端。 如果任何一方在浏览器中运行 Teams，则不支持控制。 这是由我们计划修复的一个技术限制造成。

## <a name="allow-an-external-participant-to-give-or-request-control"></a>允许外部参与者授予或请求控制权

此设置是按用户的策略。 无论组织是否为用户设置了此策略，无论会议组织者设置什么，都无法控制外部参与者可以执行哪些操作。 此参数控制是否可以向外部参与者提供对共享者屏幕的控制或请求控制权，具体取决于共享者在其组织的会议策略中设置的内容。 Teams 会议的外部参与者可分类如下：  

- 匿名用户
- 来宾用户  
- B2B 用户
- 联合用户  

联合用户是否可以在共享时向外部用户授予控制权，同时受允许外部参与者提供或请求其组织中控制设置的控制。

若要使用 PowerShell 控制外部参与者是否可以授予控制权或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。

### <a name="allow-powerpoint-sharing"></a>允许 PowerPoint 共享

这是按用户的策略。 此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片。 外部用户（包括匿名用户、来宾用户和联合用户）继承会议组织者的策略。

让我们看看以下示例。

|用户 |会议策略  |允许 PowerPoint 共享 |
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Amanda   | Location1MeetingPolicy        | 关   |

即使 Amanda 是会议组织者，她也无法共享会议中 PowerPoint 幻灯片。 即使会议由 Amanda 组织，Daniela 也可以共享 PowerPoint 幻灯片。 Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片，即使她无法共享 PowerPoint 幻灯片。

## <a name="allow-whiteboard"></a>允许白板

此设置是按用户的策略。 此设置控制用户是否可以在会议中共享白板。 外部用户（包括匿名用户、B2B 用户和联合用户）继承会议组织者的策略。

让我们看看以下示例。

|用户 |会议策略  |允许白板|
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Amanda   | Location1MeetingPolicy        | 关   |

Amanda 不能共享会议中的白板，即使她是会议组织者。 Daniela 可以共享白板，即使会议是由 Amanda 组织的。  

## <a name="allow-shared-notes"></a>允许共享笔记

此设置是按用户的策略。 此设置控制用户是否可以在会议创建和共享笔记。 外部用户（包括匿名用户、B2B 用户和联合用户）继承会议组织者的策略。 " **会议笔记"** 选项卡当前仅在参与者少于 20 人的会议中受支持。

让我们看看以下示例。

|用户 |会议策略  |允许共享笔记 |
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Amanda   | Location1MeetingPolicy | 关 |

Daniela 可以在 Amanda 的会议中做笔记，而 Amanda 不能在任何会议中做笔记。




## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](assign-policies.md)
- [从用户中删除 RestrictedAnonymousAccess Teams 会议策略](meeting-policies-restricted-anonymous-access.md)
