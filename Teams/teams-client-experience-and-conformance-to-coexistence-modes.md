---
title: Teams 客户端体验和共存模式的一致性
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: 团队客户体验和 comformance 到共存模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08bc09ac316a41dfe7ff39bc741dbaa514f30044
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548650"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 客户端体验和共存模式的一致性

> [!NOTE]
> 此页面介绍团队客户端在用户处于任何 Skype for Business 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 时的行为中的重要、最近发布的更改。


当组织从 Skype for Business 切换到团队时, 共存模式的用途是为最终用户提供简单且可预测的体验。  对于迁移到团队的组织, TeamsOnly 模式是每个用户的最终目标, 但并非所有用户都需要同时分配 TeamsOnly (或任何其他模式)。  在用户到达 TeamsOnly 模式之前, 组织可以使用任何 Skype for Business 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 确保 TeamsOnly 用户和尚未使用的用户之间可预测的通信。 

当用户处于任何 Skype for Business 模式时, 所有传入聊天和通话都将路由到用户的 Skype for business 客户端。 为避免最终用户混淆和确保正确路由, 当用户处于任何 Skype for Business 模式时, 将禁用团队客户端中的 "调用和聊天" 功能。 同样, 当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时, 将显式禁用团队中的会议计划, 并在用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用。   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>团队客户端中的可用功能如何根据模式更改
团队中的可用功能取决于用户的共存模式 (由 TeamsUpgradePolicy 设置)。 下表总结了该行为:

|用户的有效模式|团队客户端中的体验|
|---|---|
|任何 Skype for Business 模式|已禁用通话和聊天。|
|SfBWithTeamsCollabAndMeetings|会议计划可用|
|SfBWithTeamsCollab 或 SfBOnly<sup>1</sup>|会议日程安排不可用|
|||

下面的屏幕截图演示了 TeamsOnly 或孤岛模式与所有其他模式之间的差异。 请注意, 聊天和呼叫图标可通过 TeamsOnly 或孤岛模式 (左屏幕截图) 使用, 但不适用于其他模式 (右屏幕截图):

![团队模式的并排比较](media/teams-mode-comparison.png)


 
**注意:**
<sup>1</sup>现在, SfBwithTeamsCollab 和 SfBOnly 的行为相同, 但意图适用于 SfBOnly 模式以禁用团队中的频道和文件功能;但是, 当前没有任何可允许团队中的此功能被禁用的设置。


## <a name="impact-of-mode-on-other-policy-settings"></a>模式对其他策略设置的影响
如上所述, 用户的共存模式影响的是用户的团队客户端提供的功能。 这意味着, mode 的值可以优先于其他策略设置的值, 具体取决于模式。 特别是, 共存模式会影响是否遵守下列策略设置:

|**模态 (应用)**|**策略。设置**|
|---|---|
|聊天|TeamsMessagingPolicy.AllowUserChat|
|通话|TeamsCallingPolicy.AllowPrivateCalling|
|会议计划|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

管理员*无*需在使用共存模式时显式设置这些策略设置, 但重要的是要了解这些设置在给定模式下的行为方式是有效的。 

|众|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或孤岛|已启用|已启用|已启用|已启用|
|SfBWithTeamsCollabAndMeetings|已禁用|已禁用|已启用|已启用|
|SfBWithTeamsCollab 或 SfBOnly|已禁用|已禁用|已禁用|已禁用|
||||||

使用 PowerShell 时, `Grant-CsTeamsUpgradePolicy` Cmdlet 检查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中的相应设置的配置, 以确定这些设置是否会被 TeamsUpgradePolicy 取代, 如果是, 则PowerShell 中提供了信息性消息。  如上所述, 不需要再设置其他策略设置。 下面是 PowerShell 警告的示例如下:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>相关主题

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




