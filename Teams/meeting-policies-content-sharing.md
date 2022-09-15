---
title: 管理内容共享的会议策略
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
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
description: 了解如何管理 Teams 中用于内容共享的会议策略设置。
ms.openlocfilehash: d3ae689ceb2c864f3f70da91728b8607aaa1e0e2
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706689"
---
# <a name="meeting-policy-settings---content-sharing"></a>会议策略设置 - 内容共享

<a name="bkcontentsharing"> </a>

本文介绍与内容共享相关的以下会议策略设置：

- [屏幕共享模式](#screen-sharing-mode)
- [允许参与者授予或请求控制权](#allow-a-participant-to-give-or-request-control)
- [外部参与者可以提供或请求控制](#external-participants-can-give-or-request-control)
- [PowerPoint Live](#powerpoint-live)
- [白板](#whiteboard)
- [共享笔记](#shared-notes)

## <a name="screen-sharing-mode"></a>屏幕共享模式

此设置是每个组织者和每个用户策略的组合。 此设置控制是否允许在用户的会议中共享桌面和窗口。 没有分配任何策略的会议参与者 (例如，外部参与者) 继承会议组织者的策略。

|设置值 |行为  |
|---------|---------|
|**整个屏幕**    | 会议中可以实现完全的桌面共享和应用共享 |
|**单个应用程序**   | 会议中允许应用共享        |
|**禁用**     |会议中关闭了屏幕共享和应用共享。       |

查看以下示例。

|用户 |会议策略 |屏幕共享模式 |
|---------|---------|---------|
|Daniela  | 全局   | 整个屏幕 |
|Amanda   | Location1MeetingPolicy  | 已禁用 |

由 Daniela 主持的会议允许会议参与者分享他们的整个屏幕或特定的应用程序。 如果 Amanda 加入 Daniela 的会议，Amanda 则无法分享她的屏幕或特定的应用程序，因为她已禁用她的策略设置。 在 Amanda 主持的会议中，无论分配给他们的屏幕共享模式策略是什么，都不允许任何人共享他们的屏幕或单个应用程序。  因此，Daniela 无法在 Amanda 的会议中共享她的屏幕或单个应用程序。  

目前，如果用户使用谷歌浏览器，就无法在 Teams 会议中播放视频或分享屏幕。

## <a name="allow-a-participant-to-give-or-request-control"></a>允许参加者授予或请求控制权

此设置是每用户策略。 此设置可控制用户是否可以将共享桌面或窗口的控制权交给其他会议参与者。 若要想进行控制，请将鼠标悬停在屏幕上方。

如果为用户开启此设置，则在共享会话中的顶部栏中会显示 **“授予控制”** 选项。

![显示“授予控制”选项的屏幕截图。](media/meeting-policies-give-control.png)

如果已关闭用户的设置，则“**授予控制**”选项将不可用。

![显示“授予控制”选项不可用的屏幕截图。](media/meeting-policies-give-control-not-available.png)

查看以下示例。

|用户 |会议策略  |允许参加者授予或请求控制权 |
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Babek    | Location1MeetingPolicy        | 关闭   |

Daniela 可以将共享桌面或窗口的控制权授予 Babek 组织的会议中的其他参与者。 但是，Babek 无法将控制权授予其他参与者。

若要使用 PowerShell 来控制可以授予控制权或接受控制权请求的人选，请使用 AllowParticipantGiveRequestControl cmdlet。

> [!NOTE]
> 若要在共享过程中授予并控制共享内容，双方必须都使用 Teams 桌面客户端。 如果任何一方在浏览器中运行 Teams，则不支持控制。 这是由我们计划修复的一个技术限制造成。

## <a name="external-participants-can-give-or-request-control"></a>外部参与者可以提供或请求控制

此设置是每用户策略。 组织是否为用户设置了此策略，无论会议组织者设置了什么，都无法控制外部参与者可以执行的操作。 该参数控制是否可以让外部参与者控制或请求控制共享者的屏幕，这取决于共享者在其组织的会议策略中设置的内容。 Teams 会议的外部与会者可分为以下几类:  

- 匿名参与者
- 来宾
- 外部访问用户

外部访问用户是否可以在共享时将控制权授予其他外部参与者，外部 **参与者可以在其组织中提供或请求控制** 设置。

要使用 PowerShell 来控制外部参与者是否可以授予控制权或接受控制权请求，请使用AllowExternalParticipantGiveRequestControl cmdlet。

### <a name="powerpoint-live"></a>PowerPoint Live

这是按用户策略。 此设置可控制用户是否可以在会议中共享 PowerPoint 幻灯片。 外部参与者（包括匿名、来宾和外部访问用户）继承会议组织者的策略。

查看以下示例。

|用户 |会议策略  |PowerPoint Live |
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Amanda   | Location1MeetingPolicy        | 关闭   |

Amanda 无法在会议上共享 PowerPoint 幻灯片，即使她是会议组织者。 Daniela 可以分享 PowerPoint 幻灯片，即使会议是由 Amanda 组织的。 Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片，尽管她不能共享 PowerPoint 幻灯片。

## <a name="whiteboard"></a>白板

此设置是每用户策略。 此设置控制用户是否可以在会议中共享白板。 外部参与者（包括匿名、来宾和外部访问用户）继承会议组织者的策略。

查看以下示例。

|用户 |会议策略  |白板|
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Amanda   | Location1MeetingPolicy        | 关闭   |

Amanda 不能在会议上共享白板，即使她是会议组织者。 Daniela 可以共享白板，即使会议是由 Amanda 组织的。

若要使用 PowerShell 启用 Whiteboard，请将 IsWBFluidEnabled cmdlet 设置为从 [Set-SPOTenant $true。](/powershell/module/sharepoint-online/set-spotenant)

### <a name="annotation"></a>注释

启用白板后，用户将可以选择使用 [批注](/office/use-annotation-while-sharing-your-screen-in-teams)，这一功能允许参与者在 Teams 会议中共享屏幕时进行协作。 如果禁用白板，用户将无法访问批注。

## <a name="shared-notes"></a>共享笔记

此设置是每用户策略。 此设置控制用户是否可以在会议中创建和共享笔记。 外部参与者（包括匿名、来宾和外部访问）继承会议组织者的策略。 “ **会议笔记”** 选项卡目前仅在参与者少于 20 的会议中受支持。

查看以下示例。

|用户 |会议策略  |共享笔记 |
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Amanda   | Location1MeetingPolicy | 关闭 |

Daniela 可以在 Amanda 的会议上做笔记，而 Amanda 不能在任何会议上做笔记。




## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](policy-assignment-overview.md)
- [从用户删除 RestrictedAnonymousAccess Teams 会议策略](meeting-policies-restricted-anonymous-access.md)
