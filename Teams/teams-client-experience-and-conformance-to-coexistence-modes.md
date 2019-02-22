---
title: Teams 客户端体验和共存模式的一致性
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: 团队客户端体验和 comformance 到共存模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d97bf7230e8d1f78f2cf5c169fbf48a93f415bb
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178643"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 客户端体验和共存模式的一致性

> [!NOTE]
> 当用户在任何业务模式 （SfBOnly、 SfBWithTeamsCollab SfBWithTeamsCollabAndMeetings） Skype 中时，此页介绍团队客户端的行为重要即将发生变化。


共存模式旨在简单、 可预测体验的最终用户提供组织转换为从 for Business 的 Skype 向工作组。  将移动到团队的组织，TeamsOnly 模式是最终目标为每个用户，但并非所有用户都需要分配有 TeamsOnly （或任何其他模式） 在同一时间。  之前达到 TeamsOnly 模式的用户，组织可以使用任何 Skype 业务模式 （SfBOnly SfBWithTeamsCollab、 SfBWithTeamsCollabAndMeetings） 以确保可预测 TeamsOnly 用户和那些尚未之间的通信。 

当用户在任何业务模式 Skype，所有传入的聊天和呼叫路由至业务客户端的用户的 Skype。 若要避免最终用户混淆情况和确保正确路由，在客户端中的团队呼叫和聊天功能旨在时用户是在任何业务模式 Skype 禁用。 同样，在工作组中计划会议是应将其显式禁用 SfBOnly 或 SfBWithTeamsCollab 模式，用户时，明确启用当用户处于 SfBWithTeamsCollabAndMeetings 模式。  自动禁用的功能聊天和呼叫功能，以及启用/禁用会议安排基于模式立即启动到向点击客户推出。  

此功能之前, Microsoft 的指南是通过消息、 呼叫和会议策略中设置相应的设置确保正确的用户体验。 但是，出现此，不正式强制执行，因为默认情况下用户在工作组客户端具有完全访问权限的所有功能，可能有某些用户保留访问部分或所有这些团队客户端，而不考虑其模式中的体验。  因此，滚动此功能，如某些用户可能会看到团队客户端中其体验中的更改的用户体验开始符合其模式。  下表显示了新的行为：


|用户的有效模式|在工作组客户端体验|
|---|---|
|业务模式的任何 Skype|禁用呼叫和聊天<sup>1</sup> 。|
|SfBWithTeamsCollabAndMeetings|会议安排位于|
|SfBWithTeamsCollab 或 SfBOnly<sup>2</sup>|会议安排不可用|
|||

**说明：**
<sup>1</sup>会议聊天是仍然可用。

<sup>2</sup>现在，SfBwithTeamsCollab 和 SfBOnly 的行为相同，但 SfBOnly 模式也禁用团队; 中的通道和文件功能的用途是但是，当前此功能允许在要禁用的团队中没有设置。


## <a name="how-organizations-can-prepare-for-automatic-ux-conformance-to-modes"></a>组织可以如何准备自动 UX 符合模式

之前推出此更改，组织可以实现此部分中所述使用其他策略的团队客户端中的所需的体验。 这样可确保推出是无缝面向最终用户。 请注意，一旦更改滚动，设置这些策略不需要。  此外，不希望用户团队客户端中的，功能有所缩减的组织可以转向其用户群岛模式或 TeamsOnly 模式，但将影响以及路由。

若要手动配置最终用户体验，管理员使用的以下策略和设置：


|**形式 （应用程序）**|**Policy.Setting**|
|---|---|
|聊天|TeamsMessagingPolicy.AllowUserChat|
|通话|TeamsCallingPolicy.AllowPrivateCalling|
|会议日程安排|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||


管理员应将每个这些设置设置为给定的模式的下列值：

|模式|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或群岛|已启用|已启用|已启用|已启用|
|SfBWithTeamsCollabAndMeetings|已禁用|已禁用|已启用|已启用|
|SfBWithTeamsCollab 或 SfBOnly|已禁用|已禁用|已禁用|已禁用|
||||||

自动根据模式，用户体验的一致性声明推出之前`Grant-CsTeamsUpgradePolicy`cmdlet 检查 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy，以确定它们是否中相应的设置的配置设置可以与指定模式兼容。 如果任何未正确配置，则授予会成功，但警告将提供在 PowerShell 中指示的特定设置的配置不正确。 下面是 PowerShell 警告可能外观的示例：


授予 CsTeamsUpgradePolicy-Identity user1@contoso.com-PolicyName SfBWithTeamsCollab

警告: user1@contoso.com' 用户当前已启用的有效策略值： AllowUserChat AllowPrivateCalling、 AllowPrivateMeetingScheduling、 AllowChannelMeetingScheduling。 Near 术语，当使用模式授予 TeamsUpgradePolicy = SfBWithTeamsCollab 给用户，您必须单独还分配策略，以确保用户具有有效策略禁用值： AllowUserChat、 AllowPrivateCalling，AllowPrivateMeetingScheduling，AllowChannelMeetingScheduling。 将来，功能将自动服从 TeamsUpgradePolicy。

时看到这样的警告，管理员随后应更新指示的策略中团队提供兼容的最终用户体验。 如果管理员决定不执行任何操作由于警告，用户仍可以访问聊天，呼叫和/或会议中团队的日程安排功能，具体取决于 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy 的值可能会造成的混乱的最终用户体验。

可用自动根据 TeamsUpgradePolicy 模式的团队客户端体验的一致性声明后，它将不再需要将这些策略设置。 TeamsUpgradePolicy 模式的值将优先于这些特定设置的值。 自动一致性声明被通过解析策略策略基础结构。 在发生冲突的不同设置的基于模式的行为将 win 通过 AllowUserChat、 AllowPrivateCalling、 AllowPrivateMeetingScheduling 和 AllowChannelMeetingScheduling 的值。 自动一致性声明是传递之后，将更新 PowerShell 警告，告知客户端体验将自动应用，而不考虑 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy 的任何值的管理员。







