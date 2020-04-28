---
title: Teams 客户端体验和共存模式的一致性
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 了解团队客户端体验和与共存模式的一致性（SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings）。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c67046128c79608f19a4a1f4474164a949f37ef
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903357"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 客户端体验和共存模式的一致性

<a name="about-upgrade-basic"></a>

Skype for Business 共存模式（SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings）的用途是为最终用户提供简单、可预测的体验，因为组织从 Skype for Business 过渡到团队。  对于迁移到团队的组织，"**仅团队**" 模式是每个用户的最终目标，但并非所有用户都需要同时分配**团队**（或任何其他模式）。  在用户到达 TeamsOnly 模式之前，组织可以使用任何 Skype for Business 共存模式来确保**仅有团队**的用户和尚未使用的用户之间的可预测通信。 

当用户处于任何 Skype for Business 模式时，所有传入聊天和通话都将路由到用户的 Skype for business 客户端。 为避免最终用户混淆和确保正确路由，当用户处于任何 Skype for Business 模式时，将禁用团队客户端中的 "调用和聊天" 功能。 同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，将显式禁用团队中的会议计划，并在用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用。

由于状态是通过聊天和通话的可访问性指示，当聊天和通话处于禁用状态时，团队中的自保持状态（即用户图片中的团队客户端的显示状态）也会隐藏。 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>团队客户端中的可用功能如何根据模式更改

团队中的可用功能取决于用户的共存模式（由 TeamsUpgradePolicy 设置）。 下表总结了该行为：

|用户的有效模式|团队客户端中的体验|
|---|---|
|任何 Skype for Business 模式|已禁用通话、聊天和自展示。|
|SfBWithTeamsCollabAndMeetings|会议计划可用|
|SfBWithTeamsCollab 或 SfBOnly<sup>1</sup>|会议日程安排不可用|
|||

下面的屏幕截图演示**团队**的区别或**孤岛**模式与所有其他模式之间的区别。 请注意，"聊天" 和 "呼叫" 图标默认情况下仅适用于**团队**或**孤岛**模式（左屏幕截图），但不适用于其他模式（右屏幕截图）：

![团队模式的并排比较](media/teams-mode-comparison.png)

此外，自联机状态在其他模式下不可用，如下所示。

![会议中的自我出席的屏幕截图](media/meetings-first-no-self-presence-general.png)
 
**注意：**
<sup>1</sup>此时，SfBwithTeamsCollab 和 SfBOnly 的行为相同，但意图适用于 SfBOnly 模式，以禁用团队中的频道和文件功能。 在过渡期间，可以使用应用权限策略隐藏频道。


## <a name="impact-of-mode-on-other-policy-settings"></a>模式对其他策略设置的影响
如上所述，用户的共存模式影响的是用户的团队客户端提供的功能。 这意味着，mode 的值可以优先于其他策略设置的值，具体取决于模式。 特别是，共存模式会影响是否遵守下列策略设置：

|**模态（应用）**|**策略。设置**|
|---|---|
|聊天|TeamsMessagingPolicy.AllowUserChat|
|通话|TeamsCallingPolicy.AllowPrivateCalling|
|会议计划|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

管理员*无*需在使用共存模式时显式设置这些策略设置，但重要的是要了解这些设置在给定模式下的行为方式是有效的。 

|众|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或孤岛|已启用|已启用|已启用|已启用|
|SfBWithTeamsCollabAndMeetings|已禁用|已禁用|已启用|已启用|
|SfBWithTeamsCollab 或 SfBOnly|已禁用|已禁用|已禁用|已禁用|
||||||

使用 PowerShell 时， `Grant-CsTeamsUpgradePolicy` Cmdlet 检查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中的相应设置的配置，以确定这些设置是否将被 TeamsUpgradePolicy 取代，如果是，则会在 PowerShell 中提供一条信息性消息。  如上所述，不需要再设置其他策略设置。 下面是 PowerShell 警告的示例：

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>相关主题

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




