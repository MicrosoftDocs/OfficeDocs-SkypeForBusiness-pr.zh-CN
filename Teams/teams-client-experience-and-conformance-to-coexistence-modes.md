---
title: Teams 客户端体验和共存模式的一致性
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 了解Teams体验以及符合共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 。
ms.localizationpriority: medium
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
ms.openlocfilehash: d346f8f6259eef89b798bec6298f1c1fde0ac0a5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865651"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 客户端体验和共存模式的一致性

<a name="about-upgrade-basic"></a>

Skype for Business 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在组织从 Skype for Business 过渡到 Teams 时为最终用户提供简单且可预测的体验。  对于迁移到 Teams 的组织，Teams 仅模式是每个用户的最终目标，尽管并非所有用户都需要同时分配 Teams **(** 或其他任何) 模式。  在用户进入 TeamsOnly 模式之前，组织可以使用任何 Skype for Business 共存模式来确保仅拥有 Teams 用户与尚未登录的用户之间的通信可预测。 

当用户位于任何聊天Skype for Business时，所有传入聊天和呼叫将路由到用户的Skype for Business客户端。 为了避免最终用户混淆并确保正确的路由，当用户处于任何聊天模式时Teams客户端中的呼叫和聊天Skype for Business禁用。 同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，显式禁用 Teams 中的会议计划，当用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用会议计划。

由于状态通过聊天和呼叫指示可联系性，因此当禁用聊天和呼叫时，Teams (中的自我状态，即，在 Teams 客户端中用户的图片中显示自己的状态也会隐藏) 。 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>客户端中的可用功能Teams模式更改

Teams中的可用功能取决于 TeamsUpgradePolicy 设置的共存模式。 下表汇总了行为：

|用户的有效模式|客户端Teams体验|
|---|---|
|任何Skype for Business模式|通话、聊天和自我状态被禁用。|
|SfBWithTeamsCollabAndMeetings|会议安排可用|
|SfBWithTeamsCollab 或 SfBOnly<sup>1</sup>|会议计划不可用|
|||

以下屏幕截图演示了"仅Teams或群岛模式 **与** 所有其他模式的区别。 请注意，聊天和通话图标默认可用于"仅Teams"或"群岛"模式 (屏幕截图) ，但不适用于其他模式 (屏幕截图) ：

![并行比较不同模式Teams比较。](media/teams-mode-comparison.png)

此外，自我状态在其他模式下不可用，如下所示。

!["会议第一"中的自我存在的屏幕截图。](media/meetings-first-no-self-presence-general.png)
 
**注意：** 
<sup>1</sup>目前，SfBwithTeamsCollab 和 SfBOnly 的行为相同，但 SfBOnly 模式的目的是在 Teams 中禁用通道和文件功能。 在过渡期间，可以使用应用权限策略隐藏通道。


## <a name="impact-of-mode-on-other-policy-settings"></a>模式对其他策略设置的影响
如上所述，用户的共存模式会影响用户的客户端中可用的Teams功能。 这意味着 mode 的值可以优先于其他策略设置的值，具体取决于模式。 具体而言，共存模式会影响是否遵循以下策略设置：

|**Modality (App)**|**Policy.Setting**|
|---|---|
|聊天|TeamsMessagingPolicy.AllowUserChat|
|通话|TeamsCallingPolicy.AllowPrivateCalling|
|会议安排|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

使用共存 *模式* 时，管理员无需显式设置这些策略设置，但必须了解这些设置在给定模式下的行为方式如下。 

|模式|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或群岛|已启用|已启用|已启用|已启用|
|SfBWithTeamsCollabAndMeetings|已禁用|已禁用|已启用|已启用|
|SfBWithTeamsCollab 或 SfBOnly|已禁用|已禁用|已禁用|已禁用|
||||||

使用 PowerShell 时，该 cmdlet 会检查 `Grant-CsTeamsUpgradePolicy` TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中相应设置的配置，以确定这些设置是否被 TeamsUpgradePolicy 取代，如果是，PowerShell 中会提供一条信息性消息。  如上所述，不再需要设置这些其他策略设置。 下面是 PowerShell 警告的示例：

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>相关主题

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](./migration-interop-guidance-for-teams-with-skype.md)