---
title: Teams 客户端体验和共存模式的一致性
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: 团队客户端体验和 comformance 到共存模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4865d66d4d3ff1257d0fc4bd355a65c7c1330101
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934785"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 客户端体验和共存模式的一致性

> [!NOTE]
> 当用户在任何业务模式 （SfBOnly、 SfBWithTeamsCollab SfBWithTeamsCollabAndMeetings） Skype 中时，此页描述重要，最近发布更改团队客户端的行为。


共存模式旨在简单、 可预测体验的最终用户提供组织转换为从 for Business 的 Skype 向工作组。  将移动到团队的组织，TeamsOnly 模式是最终目标为每个用户，但并非所有用户都需要分配有 TeamsOnly （或任何其他模式） 在同一时间。  之前达到 TeamsOnly 模式的用户，组织可以使用任何 Skype 业务模式 （SfBOnly SfBWithTeamsCollab、 SfBWithTeamsCollabAndMeetings） 以确保可预测 TeamsOnly 用户和那些尚未之间的通信。 

当用户在任何业务模式 Skype，所有传入的聊天和呼叫路由至业务客户端的用户的 Skype。 若要避免最终用户混淆情况和确保正确路由，在客户端中的团队呼叫和聊天功能且被禁用时用户是在任何业务模式 Skype。 同样，在工作组中计划会议是显式禁用 SfBOnly 或 SfBWithTeamsCollab 模式，用户时，将明确启用当用户处于 SfBWithTeamsCollabAndMeetings 模式。   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>如何团队客户端中可用的功能更改基于模式
用户的共存模式，团队 dependes 中由 TeamsUpgradePolicy 设置的可用功能。 下表总结了行为：

|用户的有效模式|在工作组客户端体验|
|---|---|
|业务模式的任何 Skype|禁用呼叫和聊天<sup>1</sup> 。|
|SfBWithTeamsCollabAndMeetings|会议安排位于|
|SfBWithTeamsCollab 或 SfBOnly<sup>2</sup>|会议安排不可用|
|||

以下屏幕快照说明 TeamsOnly 或群岛模式和所有其他模式之间的差异。 请注意，聊天和呼叫图标可使用 TeamsOnly 或群岛模式 （左屏幕截图），但不是与其他模式 （右屏幕截图）：

![显示工作组模式比较](media/teams-mode-comparison.png)


 
**说明：**
<sup>1</sup>会议聊天是仍然可用。

<sup>2</sup>现在，SfBwithTeamsCollab 和 SfBOnly 的行为相同，但 SfBOnly 模式也禁用团队; 中的通道和文件功能的用途是但是，当前此功能允许在要禁用的团队中没有设置。


## <a name="impact-of-mode-on-other-policy-settings"></a>对其他策略设置模式的影响
如上所述，用户的共存模式影响哪些功能，用户的工作组客户端中提供。 这意味着，模式的值可以优先于其他策略设置，具体取决于模式的值。 具体而言，共存模式影响是否有效以下策略设置：

|**形式 （应用程序）**|**Policy.Setting**|
|---|---|
|聊天|TeamsMessagingPolicy.AllowUserChat|
|通话|TeamsCallingPolicy.AllowPrivateCalling|
|会议日程安排|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

管理员需要*不*明确地设置这些策略设置，使用共存模式，但它时需要了解，这些设置有效的行为，如下所示为给定的模式。 

|模式|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或群岛|已启用|已启用|已启用|已启用|
|SfBWithTeamsCollabAndMeetings|已禁用|已禁用|已启用|已启用|
|SfBWithTeamsCollab 或 SfBOnly|已禁用|已禁用|已禁用|已禁用|
||||||

近期， `Grant-CsTeamsUpgradePolicy` cmdlet 将检查 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy，以确定是否将由 TeamsUpgradePolicy 取代这些设置，以及如果是这样中, 相应的设置的配置在 PowerShell 中提供的信息性消息。  如上所述，不再需要设置这些其他策略设置。 下面是示例 PowerShell 警告如下所示：

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>相关主题

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




