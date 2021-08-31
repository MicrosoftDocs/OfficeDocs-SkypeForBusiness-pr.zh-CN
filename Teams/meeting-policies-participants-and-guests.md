---
title: 管理参与者和来宾的会议策略
author: CarolynRowe
ms.author: crowe
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 了解如何在参与者和来宾的Teams管理会议策略设置。
ms.openlocfilehash: b377c1c391f1fb3a82976db6d58e84c9eb2f9b94
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728631"
---
# <a name="meeting-policy-settings---participants--guests"></a>会议策略设置 - 参与者和来宾

<a name="bkmeetingparticipants"> </a>

这些设置可以控制哪些与会者在进入会议之前在大厅等待，以及允许他们参与会议的级别。

- [允许匿名用户启动会议](#let-anonymous-people-start-a-meeting)
- [自动管理人员](#automatically-admit-people)
- [允许拨入用户绕过问题](#allow-dial-in-users-to-bypass-the-lobby)
- [启用实时字幕](#enable-live-captions)
- [在会议中允许聊天](#allow-chat-in-meetings)

> [!NOTE]
>加入会议的选项会有所不同，这取决于每个 Teams 组的设置和连接方法。 如果小组有音频会议，并使用它来连接，请参阅 [音频会议](/microsoftteams/audio-conferencing-in-office-365)。 如果 Teams 组没有音频会议，请参阅 [在 Teams 中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

## <a name="let-anonymous-people-start-a-meeting"></a>允许匿名人员发起会议

此设置是一个按组织者的策略，允许召开无领导电话拨入式会议。 此设置控制拨入用户是否可以在没有组织中经过身份验证的用户出席的情况下加入会议。 默认情况下，此设置已关闭，这意味着拨入用户将在大厅中等待，直到组织中经过身份验证的用户加入会议。

> [!NOTE]
> 如果此设置已关闭，并且拨入用户先加入会议并放置在大厅中，则组织用户必须使用 Teams 客户端加入会议，以允许用户从大厅访问。 拨号用户没有大厅控制功能。

## <a name="automatically-admit-people"></a>自动允许人员

这是按组织者的策略。 此设置可以控制人员是直接加入会议还是在大厅里等待，直到受认证的用户入场。 此设置不适用于拨入用户。

![显示与大厅中用户的会议的屏幕截图。](media/meeting-policies-lobby.png)

 会议组织者可以单击 **会议邀请** 中的"会议选项"，更改他们计划的每个会议的此设置。

> [!NOTE]
> 在会议选项中，设置标记为"谁可以绕过问题"。如果更改任何用户的默认设置，它将应用于该用户组织的所有新会议以及用户未修改会议选项的任何之前会议。
  
|设置值  |加入行为 |
|---------|---------|
|**每个人**   |所有参会人员无需在大厅等待，直接加入会议。 这包括经过认证的用户、来自受信任组织的外部用户 (联合)、客人和匿名用户。     |
|**组织中用户和来宾**     |组织中经过身份验证的用户（包括来宾用户）可以直接加入会议，无需在大厅中等待。 来自受信任组织和匿名用户的用户在大厅中等待。 这是默认设置。    |
|**我的组织中人员、受信任的组织和来宾**     |组织内经过认证的用户，包括嘉宾用户和来自可信组织的用户，直接加入会议，无需在大厅等待。  匿名用户在大厅里等待。   |
|**我的组织中人员**    |组织中经过身份验证的用户直接加入会议，无需在大厅中等待。  来自受信任组织、来宾用户和匿名用户的用户在大厅中等待。          |
|**仅管理器**    |只有会议组织者才能直接参加会议，无需在大厅等待。 其他所有人（包括组织中经过身份验证的用户、来宾用户、来自受信任组织的用户和匿名用户）必须在大厅中等待。 在Teams会议选项"页面上，它显示为"仅我"。          |
|**仅受邀用户**    |只有受邀用户和会议组织者可以直接加入会议，而无需在大厅中等待。 其他所有人（包括组织中经过身份验证的用户、来宾用户、来自受信任组织的用户和匿名用户）必须在大厅中等待。 在"Teams客户端会议选项"页面上，它显示为"我邀请的人"。          |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>允许拨入用户绕过大厅

这是按组织者的策略。 此设置可控制通过电话拨入的人是直接加入会议还是在大厅等待，而不考虑 **“自动接收人员”** 设置。 默认情况下，此设置已关闭。 当此设置关闭时，拨号用户将在大厅中等待，直到组织用户用 Teams 客户端加入会议并接收他们。 开启此设置后，当组织用户加入会议时，拨号用户将自动加入会议。

> [!NOTE]
> 如果拨号用户在组织用户加入会议之前加入会议，将放置他们在大厅中，直到组织用户使用 Teams 客户端加入会议并接纳他们。 如果更改任何用户的默认设置，它将适用于该用户组织的所有新会议以及该用户没有修改会议选项的任何之前会议。

## <a name="enable-live-captions"></a>启用实时字幕

此设置是按用户的策略，在会议期间适用。 此设置控制 **开启实时字幕** 选项是否可以让用户在参加的会议中开启和关闭实时字幕。  

![显示"启用实时字幕"选项的屏幕截图。](media/meeting-policies-live-captions.png)

|设置值 |行为  |
|---------|---------|
|**已禁用，但用户可以替代**     | 在会议期间，实时字幕不会自动为用户开启。 用户在溢出 (**...**) 菜单中看到 **“开启实时字幕”** 选项，即可其打开。 这是默认设置。 |
|**禁用**     | 在会议期间，将禁用用户的实时字幕。 用户无法选择启用它们。          |

<a name="bkcontentsharing"> </a>

## <a name="allow-chat-in-meetings"></a>允许在会议中聊天

此设置是每个参与者的设置。 此设置控制是否允许在用户的会议中进行会议聊天。

<a name="bkparticipantsandguests"> </a>






## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](assign-policies.md)
- [从用户删除 RestrictedAnonymousAccess Teams 会议策略](meeting-policies-restricted-anonymous-access.md)
