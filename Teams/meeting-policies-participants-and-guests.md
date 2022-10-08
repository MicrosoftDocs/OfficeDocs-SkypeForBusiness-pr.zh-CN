---
title: 管理参与者和来宾的会议策略
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 了解如何在 Teams 中为参与者和来宾管理会议策略设置。
ms.openlocfilehash: 5b489f312dd1fd1fcd9bdb6a301a65e76ab9ed91
ms.sourcegitcommit: 9522d951700d19ab13c60a6452b3a8a4c824ee36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2022
ms.locfileid: "68018088"
---
# <a name="meeting-policy-settings---participants--guests"></a>会议策略设置 - 参与者和来宾

<a name="bkmeetingparticipants"> </a>

这些设置控制哪些会议参与者在进入会议之前在大厅中等待，以及允许他们参加会议的级别。

- [让匿名人员加入会议](#let-anonymous-people-join-a-meeting)
- [允许匿名用户启动会议](#let-anonymous-people-start-a-meeting)
- [自动管理人员](#automatically-admit-people)
- [允许拨入用户绕过问题](#allow-dial-in-users-to-bypass-the-lobby)
- [实时字幕](#live-captions)
- [在会议中聊天](#chat-in-meetings)

> [!NOTE]
> 加入会议的选项会有所不同，这取决于每个 Teams 组的设置和连接方法。 如果小组有音频会议，并使用它来连接，请参阅 [音频会议](/microsoftteams/audio-conferencing-in-office-365)。 如果 Teams 组没有音频会议，请参阅 [在 Teams 中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

## <a name="let-anonymous-people-join-a-meeting"></a>让匿名人员加入会议

此按组织者设置允许任何人通过选择会议邀请中的链接以匿名用户身份加入会议。 要了解更多信息，请参阅[在没有 Teams 帐户的情况下加入会议](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)。 匿名用户加入会议的能力也会在组织级别受到控制，限制性越高，设置就越有效。 若要了解详细信息，请参阅 [使用 Microsoft Teams 管理中心配置组织范围的策略](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。

## <a name="let-anonymous-people-start-a-meeting"></a>允许匿名人员发起会议

此设置是允许无领导电话拨入式会议的按组织者策略。 此设置控制拨入用户是否可以在没有组织中经过身份验证的用户的情况下加入会议。 默认情况下，此设置处于关闭状态，这意味着拨入用户将在大厅中等待，直到组织中经过身份验证的用户加入会议。

> [!NOTE]
> 如果此设置已关闭，并且拨入用户首先加入会议并放置在大厅中，则组织用户必须与 Teams 客户端一起加入会议，才能从大厅中接纳该用户。 拨号用户没有大厅控制功能。

## <a name="automatically-admit-people"></a>自动允许人员

这是按组织者的策略。 此设置控制是直接加入会议，还是在大厅中等待，直到经过身份验证的用户允许。 此设置不适用于拨入用户。

![显示在大厅里会见用户的屏幕截图。](media/meeting-policies-lobby.png)

 会议组织者可以在会议邀请中单击 **“会议选项** ”，以更改他们安排的每个会议的此设置。

> [!NOTE]
> In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.
  
|设置值  |加入行为 |
|---------|---------|
|**每个人**   |所有参会人员无需在大厅等待，直接加入会议。 这包括经过身份验证的用户、受信任组织的用户、来宾和匿名用户。     |
|**组织中用户和来宾**     |组织内经过身份验证的用户（包括来宾）直接加入会议，而无需在大厅中等待。 来自可信组织的用户和匿名用户在大厅里等待。 这是默认设置。    |
|**我的组织中人员、受信任的组织和来宾**     |组织内经过身份验证的用户（包括来宾和受信任组织的用户）直接加入会议，而无需在大厅中等待。  匿名用户在大厅里等待。   |
|**我的组织中人员**    |组织内经过身份验证的用户直接加入会议，无需在大厅中等待。  来自受信任组织、来宾和匿名用户的用户在大厅中等待。          |
|**仅管理器**    |只有会议组织者才能直接参加会议，无需在大厅等待。 其他所有人（包括组织内经过身份验证的用户、来宾、受信任组织的用户和匿名用户）必须在大厅中等待。 在 Teams 客户端会议选项页上，它显示为“仅限我”。          |
|**仅邀请用户**    |只有受邀的用户和会议组织者才能直接加入会议，而无需在大厅中等待。 其他所有人（包括组织内经过身份验证的用户、来宾、受信任组织的用户和匿名用户）必须在大厅中等待。 在 Teams 客户端会议选项页上，它显示为“人员我邀请”。 作为通讯组的一部分添加的用户必须经过大厅。      |

 > [!NOTE]
> 受信任的组织是允许在 Teams 中进行联合通信的域。 如果在 Teams 管理中心启用 **允许所有外部域** 进行外部访问，则任何 Teams 组织中任何经过身份验证的用户都将受信任。 如果选择指定允许的外部域并阻止所有其他域，则允许的域将成为受信任的组织。 任何被阻止的域都被视为不受信任的组织。

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>允许拨入用户绕过大厅

这是按组织者的策略。 此设置可控制通过电话拨入的人是直接加入会议还是在大厅等待，而不考虑 **“自动接收人员”** 设置。 默认情况下，此设置已关闭。 当此设置关闭时，拨号用户将在大厅中等待，直到组织用户用 Teams 客户端加入会议并接收他们。 打开此设置后，当组织用户与 Teams 客户端加入会议时，拨入用户将自动加入会议。

> [!NOTE]
> 如果拨号用户在组织用户加入会议之前加入会议，将放置他们在大厅中，直到组织用户使用 Teams 客户端加入会议并接纳他们。 如果更改任何用户的默认设置，它将适用于该用户组织的所有新会议以及该用户没有修改会议选项的任何之前会议。

## <a name="live-captions"></a>实时字幕

此设置是每用户策略，在会议期间适用。 此设置控制 **开启实时字幕** 选项是否可以让用户在参加的会议中开启和关闭实时字幕。  

![显示启用辅助字幕选项的屏幕截图。](media/meeting-policies-live-captions.png)

|设置值 |行为  |
|---------|---------|
|**未启用，但用户可以替代**     | 在会议期间，实时字幕不会自动为用户开启。 用户在溢出 (**...**) 菜单中看到 **“开启实时字幕”** 选项，即可其打开。 这是默认设置。 |
|**未启用**     | 在会议期间，将禁用用户的实时字幕。 用户无法选择启用它们。          |

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>在会议中聊天

这是按用户和按组织者的策略。 此设置控制是否允许在用户的会议中进行会议聊天。 此设置不适用于频道会议。

|设置值 |行为  |
|---------|---------|
|**为每个人打开它**     | 所有参与者都可以写入和查看聊天消息。 |
|**为每个人关闭它**     | 所有参与者的会议聊天都已关闭。  |
|**为除匿名用户之外的所有人启用它**     | 仅对匿名参与者关闭会议聊天写入访问权限。  |

将此 **聊天会议策略** 应用于用户后，组织者无法通过 **会议选项** 替代此策略。

应用于会议组织者的策略可能会影响会议中的其他用户。 例如：

- 如果组织者 **在会议中** 设置 **为为所有人打开** 聊天，或 **为除匿名用户之外的所有人打开聊天，** 则将应用用户的个人策略，并且所有设置 **为“关闭”的** 用户都无法在会议中聊天。
- 如果组织者 **在会议中将聊天** 设置 **为为“为所有人关闭聊天**”，则组织者的政策适用，并且没有人能够在会议中聊天。

<a name="bkparticipantsandguests"> </a>

## <a name="qa-in-meetings"></a>会议中的 Q&A

这是按组织者的策略。 此设置使 Microsoft 365 租户管理员能够 (Q&A) 启用或禁用问题&解答体验。

当组织者创建或更新会议时，将强制执行此设置。 默认情况下，此设置已关闭。 在此处详细了解 Q [&A。](/manage-qna-for-meetings)

参数 QnAEngagementMode 在 PowerShell 中控制此策略。 Q&A 也可以在管理门户中进行调整。

|设置值 |行为  |
|---------|---------|
|**已启用**     | 组织者可以在创建会议时添加 Q&A。 |
|**禁用**     | 组织者在创建会议时无法选择添加 Q&A。  |

## <a name="enable-meeting-policy-settings"></a>启用会议策略设置

若要启用会议策略设置，可以使用 [Teams 管理中心](https://admin.teams.microsoft.com/policies/meetings) (**会议策略** > **编辑** > **策略参与者&来宾**) 或 Teams PowerShell 中的 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet。 

在此示例中，我们使用 PowerShell 修改全局会议策略，以允许任何人开始或加入会议。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

设置策略后，需要将其应用到用户。 如果修改了全局 (组织范围的默认) 策略，它将自动应用于用户。 需要等待至少 4 小时才能使任何策略更改生效，但最多可能需要 24 小时。


## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](policy-assignment-overview.md)
- [从用户删除 RestrictedAnonymousAccess Teams 会议策略](meeting-policies-restricted-anonymous-access.md)
