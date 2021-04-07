---
title: 管理参与者和来宾的会议策略
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 了解如何在 Teams 中管理参与者和来宾的会议策略设置。
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598698"
---
# <a name="meeting-policy-settings---participants--guests"></a>会议策略设置 - 参与者&来宾

<a name="bkmeetingparticipants"> </a>

这些设置控制哪些会议参与者在获准参加会议之前在大厅中等待，以及允许他们参加会议的参与级别。

- [让匿名人员启动会议](#let-anonymous-people-start-a-meeting)
- [自动允许人员](#automatically-admit-people)
- [允许拨入用户绕过大厅](#allow-dial-in-users-to-bypass-the-lobby)
- [启用实时字幕](#enable-live-captions)
- [允许在会议中聊天](#allow-chat-in-meetings)

> [!NOTE]
>用于加入会议的选项因每个 Teams 组的设置和连接方法而异。 如果你的群组有音频会议，并使用它进行连接，请参阅 [音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。 如果你的 Teams 组没有音频会议，请参阅 [在 Teams 中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

## <a name="let-anonymous-people-start-a-meeting"></a>让匿名人员启动会议

此设置是一个按组织者的策略，允许召开无领导电话拨入式会议。 此设置控制拨入用户是否可以在没有组织中经过身份验证的用户参加会议的情况下加入会议。 默认情况下，此设置已关闭，这意味着拨入用户将在大厅中等待，直到组织中经过身份验证的用户加入会议。

> [!NOTE]
> 如果此设置已关闭，并且拨入用户先加入会议并放置在大厅中，则组织用户必须通过 Teams 客户端加入会议，以允许用户从大厅访问。 拨入用户没有可用的大厅控件。

## <a name="automatically-admit-people"></a>自动允许人员

这是按组织者的策略。 此设置控制用户是直接加入会议，还是等待大厅，直到经过身份验证的用户获准。 此设置不适用于拨入用户。

![显示与大厅中用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 会议组织者可以在会议 **邀请中** 单击"会议选项"，更改他们计划的每个会议的此设置。

> [!NOTE]
> 在会议选项中，设置标记为"谁可以绕过大厅"。 如果更改任何用户的默认设置，它将应用于该用户组织的所有新会议以及用户未修改会议选项的任何以前会议。
  
|设置值  |联接行为 |
|---------|---------|
|**所有人**   |所有会议参与者都直接加入会议，无需在大厅中等待。 这包括经过身份验证的用户、来自受信任组织的外部用户 (联合) 、来宾和匿名用户。     |
|**组织与联盟组织中的每个人**     |组织中经过身份验证的用户（包括来宾用户和来自受信任组织的用户）可以直接加入会议，无需在大厅中等待。  匿名用户在大厅中等待。   |
|**您的组织中的每个人**    |组织中经过身份验证的用户（包括来宾用户）可以直接加入会议，无需在大厅中等待。  来自受信任组织和匿名用户的用户在大厅中等待。 这是默认设置。           |
|**仅组织者**    |只有会议组织者可以直接加入会议，而无需在大厅中等待。 其他所有人（包括组织中经过身份验证的用户、来宾用户、来自受信任组织的用户和匿名用户）必须在大厅中等待。           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>允许拨入用户绕过大厅

这是按组织者的策略。 此设置控制通过电话拨入的人是直接加入会议还是等待在大厅中，而不考虑" **自动允许人员"** 设置。 默认情况下，此设置已关闭。 当此设置关闭时，拨入用户将在大厅中等待，直到组织用户使用 Teams 客户端加入会议并准许他们加入会议。 启用此设置后，当组织用户加入会议时，拨入用户将自动加入会议。

> [!NOTE]
> 如果拨入用户在组织用户加入会议之前加入会议，他们将被放置在大厅中，直到组织用户使用 Teams 客户端加入会议并准许他们加入。 如果更改任何用户的默认设置，它将应用于该用户组织的所有新会议以及用户未修改会议选项的任何以前会议。

## <a name="enable-live-captions"></a>启用实时字幕

此设置是按用户的策略，在会议期间适用。 此设置控制" **启用实时** 字幕"选项是否可供用户在用户参加的会议中打开和关闭实时字幕。  

![显示"启用实时字幕"选项的屏幕截图](media/meeting-policies-live-captions.png)

|设置值 |行为  |
|---------|---------|
|**已禁用，但用户可以替代**     | 在会议期间，用户不会自动打开实时字幕。 用户会看到溢出 **菜单中的"** 启用实时字幕" (...) 打开它们。  这是默认设置。 |
|**已禁用**     | 会议期间为用户禁用了实时字幕。 用户没有启用它们的选项。          |

<a name="bkcontentsharing"> </a>

## <a name="allow-chat-in-meetings"></a>允许在会议中聊天

此设置是每个参与者的设置。 此设置控制是否在用户的会议中允许会议聊天。

<a name="bkparticipantsandguests"> </a>






## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](assign-policies.md)
- [从用户中删除 RestrictedAnonymousAccess Teams 会议策略](meeting-policies-restricted-anonymous-access.md)
