---
title: Teams 客户端体验和共存模式的一致性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 了解 SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollab (、SfBWithTeamsCollabAndMeetings) 的 Teams 客户端体验和共存模式的一致性。
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
ms.openlocfilehash: 91ea07d74bf9b08f627d86191ea08fc0eda1ac4c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605831"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 客户端体验和共存模式的一致性

<a name="about-upgrade-basic"></a>

Skype for Business共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在组织从Skype for Business过渡到 Teams 时为最终用户提供一种简单、可预测的体验。  对于迁移到 Teams 的组织， **仅限 Teams** 模式是每个用户的最终目标，但并非所有用户都需要同时分配 **Teams (** 或任何其他模式) 。  在用户达到 TeamsOnly 模式之前，组织可以使用任何Skype for Business共存模式来确保 **仅限 Teams** 的用户与尚未使用的用户之间进行可预测的通信。 

当用户处于任何Skype for Business模式时，所有传入聊天和呼叫都会路由到用户的Skype for Business客户端。 为了避免最终用户混淆并确保正确的路由，当用户处于任何Skype for Business模式时，Teams 客户端中的呼叫和聊天功能将被禁用。 同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，Teams 中的会议计划会被显式禁用，并在用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用。

因为存在是通过聊天和通话实现的一个指示，所以当聊天和呼叫被禁用时，Teams 中的自我存在 (即，用户图片) 中 Teams 客户端中显示自己的状态也会被隐藏。 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Teams 客户端中的可用功能如何根据模式进行更改

Teams 中的可用功能取决于 TeamsUpgradePolicy 设置的用户共存模式。 下表总结了以下行为：

|用户的有效模式|Teams 客户端中的体验|
|---|---|
|任何Skype for Business模式|呼叫、聊天和自我存在被禁用。|
|SfBWithTeamsCollabAndMeetings|会议日程安排可用|
|SfBWithTeamsCollab 或 SfBOnly<sup>1</sup>|会议日程安排不可用|
|||

以下屏幕截图说明了 **Teams Only** 或 **Islands** 模式与所有其他模式之间的差异。 请注意，默认情况下，聊天和呼叫图标在 **“仅限 Teams** ”或 **“岛屿** ”模式 (左侧屏幕截图) 可用，但不适用于其他模式 (右侧屏幕截图) ：

![Teams 模式的并行比较。](media/teams-mode-comparison.png)

此外，自存在在其他模式下不可用，如下所示。

![“会议第一”中自我状态的屏幕截图。](media/meetings-first-no-self-presence-general.png)
 
**注意：**
<sup>1</sup> 目前，SfBwithTeamsCollab 和 SfBOnly 的行为相同，但意图是 SfBOnly 模式也禁用 Teams 中的频道和文件功能。 在此期间，可以使用应用权限策略隐藏通道。


## <a name="impact-of-mode-on-other-policy-settings"></a>模式对其他策略设置的影响
如上所述，用户的共存模式影响是用户 Teams 客户端中可用的功能。 这意味着模式的值可以优先于其他策略设置的值，具体取决于模式。 具体而言，共存模式会影响是否遵循以下策略设置：

|**应用)  (模式**|**Policy.Setting**|
|---|---|
|聊天|TeamsMessagingPolicy.AllowUserChat|
|通话|TeamsCallingPolicy.AllowPrivateCalling|
|会议日程安排|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

管理员在使用共存模式时 *不需要* 显式设置这些策略设置，但务必了解这些设置在给定模式下的行为方式是否有效。 

|模式|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或 Islands|已启用|已启用|已启用|已启用|
|SfBWithTeamsCollabAndMeetings|已禁用|已禁用|已启用|已启用|
|SfBWithTeamsCollab 或 SfBOnly|已禁用|已禁用|已禁用|已禁用|
||||||

使用 PowerShell 时， `Grant-CsTeamsUpgradePolicy` cmdlet 会检查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中相应设置的配置，以确定这些设置是否会被 TeamsUpgradePolicy 取代，如果是，PowerShell 中会提供一条信息性消息。  如上所述，不再需要设置这些其他策略设置。 下面是 PowerShell 警告的外观示例：

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>相关主题

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](./migration-interop-guidance-for-teams-with-skype.md)