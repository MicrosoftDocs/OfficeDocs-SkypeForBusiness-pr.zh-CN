---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc8afc48db6264cef5c5ad959f33dd7e738e116
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515789"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>&mdash;IT 管理员的升级方法

本文介绍了迁移到团队的升级方法。 本文是介绍 IT 管理员的升级概念和实现的第二个。  

- [概述](upgrade-to-teams-on-prem-overview.md)
- 本文 (的**升级方法**) 
- [用于管理升级的工具](upgrade-to-teams-on-prem-tools.md)
- [具有 Skype for business 内部部署的组织的其他注意事项](upgrade-to-teams-on-prem-considerations.md)
- [实施升级](upgrade-to-teams-on-prem-implement.md)
- [ (PSTN) 注意事项的公共交换电话网络](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，以下文章介绍了重要的升级概念和共存行为：

- [团队和 Skype for business 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>升级方法

有两种方法可以使用 Skype for Business 升级现有组织 (无论是联机还是本地) 到团队：重叠的功能方法，以及 "选择功能" 方法。 本文通过描述两种方法并展示每个方法的优缺点，帮助你为你的组织选择正确的方法。 

- [使用孤岛模式 (重叠的功能方法) ](#overlapping-capabilities-method-using-islands-mode)

   现有 Skype for Business 组织中的用户将引入团队，以便他们可以在过渡阶段使用这两个客户端。 在此期间内，团队的大部分功能（但不是所有）都可供他们使用。 此配置的模式称为 "岛"，这是任何具有 Skype for Business 的现有组织的默认模式。 组织准备就绪后，管理员会将用户移动到 TeamsOnly 模式。

- ["选择功能" 方法 (使用一个或多个 Skype for Business 模式) ](#select-capabilities-method-using-skype-for-business-modes)

   管理员) 可管理 Skype for Business 中的切换 (组织中用户的聊天、通话和会议安排功能。  其中的每个功能均可在 Skype for Business 或团队中使用，但不能同时使用。 管理员使用 TeamsUpgradePolicy 控制何时将此功能转移给其用户的团队。 尚未处于 TeamsOnly 模式的用户将继续使用 Skype for Business 进行聊天和通话，两组用户可以通过互操作功能进行通信。 管理员通过将更多用户逐步迁移到 TeamsOnly 模式来管理切换。  

了解并选择升级方法后，您可以了解 [用于管理组织升级到团队的工具](upgrade-to-teams-on-prem-tools.md)。

## <a name="overlapping-capabilities-method-using-islands-mode"></a>使用孤岛模式 (重叠的功能方法) 

使用重叠的功能方法，用户可以使用团队和 Skype for Business 客户端进行聊天、VoIP 呼叫和会议。 此状态称为 "孤岛" 模式，因为 Skype for business 和团队的通信流量在同一用户的情况下仍然是独立的 () 并且两个不同的客户端与同一) 组织中的用户之间不会互相通信 (。 例如，假设收件人用户 A 处于 "孤岛" 模式下：

- 从其他用户的 Skype for business 客户端发起的通信将始终位于用户 A 的 Skype for business 客户端。

- 从另一个用户的团队客户端发起的通信将始终位于用户 A 的团队客户端（ *如果其他用户位于同一组织中*）。 

- 从另一个用户的团队客户发起的通信将始终位于用户 A 的 Skype for business 客户端中（ *如果其他用户位于联合组织*中）。

对于尚未升级到 TeamsOnly 的任何现有组织，"岛模式" 是 TeamsUpgradePolicy 的默认模式。 分配 Microsoft 365 或 Office 365 许可证时，默认情况下会分配团队和 Skype for business Online 许可证。  (即使用户在 Skype for Business 服务器内部托管，也是如此。 无论用户是在本地还是在网上托管，都将启用 Skype for Business Online 许可证，因为当前需要完整的团队功能。 ) 事实上，如果你未采取任何步骤来更改默认配置，则你的组织中可能已有团队的大量用途。  这是重叠功能方法的优点之一。 它允许在组织内快速、最终用户推动采用。

为使此方法有效工作，它要求所有用户同时运行两个客户端。 在 "Skype for business" 或 "团队客户端" 中，组织内部的聊天和从组织内部进行的通话可以居住在 Skype for business 或团队客户端中，这不受收件人的控制。 如果发件人和收件人位于同一组织中，则取决于发件人用于发起通信的客户端。 如果发件人和收件人位于不同组织中，则在 "岛" 模式下传入呼叫和聊天始终位于 Skype for Business 客户端中。  

例如，如果一种 "孤岛模式" 收件人运行的是 Skype for Business，而不是团队，并且同一组织中的某人使用团队发送邮件，则 "岛模式" 收件人将看不到该邮件 (，但他们最终会收到一封电子邮件，告知他们错过了团队) 中的邮件。 同样，如果用户运行的是团队，而不是 Skype for business，并且某人从 Skype for business 发送消息，用户将看不到该聊天。  他们将收到一封电子邮件，说明错过的消息。 这两种情况下的行为与通话类似。 如果用户不运行这两个客户端，很容易导致不满。

当用户 A 处于 "孤岛" 模式时，团队和 Skype for business 中的其他用户看到的用户 A 的状态是独立的：

- 其他用户在使用团队时，将根据用户 A 的团队活动查看状态。 
- 使用 Skype for Business 时，其他用户将根据用户 A 在 Skype for Business 中的活动查看状态。 

这意味着其他用户可能会看到用户 A 的不同状态，具体取决于其使用的客户端。 有关详细信息，请参阅 [联机状态](upgrade-to-teams-on-prem-coexistence.md#presence)。

准备好将用户升级到 TeamsOnly 模式后，你可以单独升级用户，也可以使用租户范围的策略一次性升级整个租户。 用户升级到 TeamsOnly 模式后，他们将收到团队中的所有传入聊天和通话。  (请注意，仅当向单个用户应用 TeamsUpgradePolicy 时，才会触发将 Skype for Business 会议迁移到团队会议，而不是在每租户基础上进行。 有关详细信息，请参阅 [会议迁移](upgrade-to-teams-on-prem-tools.md#meeting-migration) 。 ) 

但是，在孤岛模式下未升级的收件人可能会继续接收来自其 Skype for Business 或团队客户的 TeamsOnly 用户的聊天和呼叫。  这是因为团队客户为团队到团队和团队到 Skype for business 通信（即使是对于同一用户）维护单独的对话线程。   (请参阅 [团队对话-互操作与本机线程](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)。 ) 例如，假设孤岛用户 A 使用团队 TeamsOnly 用户 B 的消息。当用户 B 回复该聊天时，通信将位于用户 A 的团队客户端。 现在，假设用户 A 使用 Skype for Business 客户端进行邮件 TeamsOnly 用户 B。用户 B 将在团队中接收聊天，但这将是用户 B 的团队客户端与其他对话的单独对话。 如果用户 B 使用用户 A 答复此对话，则它将在用户 A 的 Skype for Business 客户端中居住。 

下表总结了孤岛模式和 TeamsOnly 模式的团队体验：  

| 团队体验 | 在 "孤岛" 模式下 | 在 TeamsOnly 模式下 |
|:------------------ | :------------------- | :------------------ |
| 传入聊天和通话接收时间：|  团队或 Skype for business | Teams |
| 在以下情况中接收 PSTN 呼叫： | Skype for Business <br>在孤岛模式下，不支持使用团队中的 PSTN 功能 (。 )     | Teams |   
 |状态  | Skype for business 和团队中的状态是独立的。 对于同一孤岛用户，用户可能会看到不同的状态，具体取决于他们使用的客户端。 | 状态仅基于用户在团队中的活动。 所有其他用户，无论他们使用哪种客户端，都可以查看该状态。 | 
 | 会议计划   | 默认情况下，用户可以在团队或 Skype for Business 中安排会议。 它们将在 Outlook 中看到两个外接程序。 |   用户仅在团队中安排会议。 Outlook 中仅提供团队外接程序。 | 

下表总结了使用重叠的功能方法将组织迁移到团队的优点和缺点。

| 专业人士     |       各有利弊 |
| :------------------ | :---------------- |
| 允许在组织内进行快速采纳。| 由于两个客户端具有类似的功能，但用户界面不同，因此可能导致最终用户混淆。 而且，他们无法控制传入聊天/呼叫在哪个客户端。 |
| 允许用户在仍然拥有 Skype for business 的完全访问权限的情况下了解和熟悉团队。 | 如果用户未在两个客户端运行时错过的消息，则可能导致最终用户不满。 用户可能会抱怨他们没有收到消息。|
| 在团队中开始的最少管理工作。 | 如果不是组织中的每个人都使用团队，尤其是当组织中的所有用户都未处于活动状态时，"使用孤岛" 模式非常有挑战性并移至 TeamsOnly 模式。 例如，一旦用户的子集升级到 TeamsOnly 模式，这些用户将仅在团队中发送。 对于在孤岛模式下填充的其余部分，这些消息将始终位于团队中。 但是，如果其中一些人口不运行团队，他们会将这些消息视为错过。 |
|  | 使用团队时，Skype for Business 服务器中具有本地帐户的用户没有互操作或联合身份验证支持。  如果您有一种混合的孤岛用户，这可能会造成混乱，因为这种用户在 Skype for business Online 中托管，而有些在本地 Skype for business 中。   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>使用 Skype for Business 模式 (选择功能方法) 

某些组织可能希望向最终用户提供其组织从 Skype for Business 转换到团队的更简单、更具可预测的体验。 在此模型中，IT 管理员使用 TeamsUpgradePolicy 中的 Skype for Business 模式之一，在迁移到 TeamsOnly 模式之前明确指定哪些用户在 Skype for Business 中保留。 当他们准备将所选用户移动到 TeamsOnly 模式时，管理员会将这些用户的模式更新为 TeamsOnly。 随着部署的进展，越来越多的用户将从 Skype for Business 转换到 TeamsOnly 模式。  在此过渡期间：

- 无论通信来源于其他用户的团队还是 Skype for business 客户端，仍在使用 Skype for business 的用户接收 Skype for business 客户端的所有传入聊天和呼叫。 此外，对于这些 Skype for Business 用户，将禁用团队客户端中的 "调用和聊天" 功能，以帮助防止最终用户混淆和确保正确路由。 

- TeamsOnly 模式中的用户可接收其团队客户端中的所有传入聊天和通话，无论通信来源：团队、Skype for Business 或任何类型的联盟用户。 

与孤岛方法不同，在 "选择功能" 方法中，Skype for Business 用户和 TeamsOnly 用户可以相互通信。 Skype for Business 用户和团队用户之间的通信称为互操作性或 "互操作"。 在 Skype for business 中的用户和团队中的另一用户之间进行聊天和通话的同时，互操作通信是可行的。但是，某些高级功能可能不可用。  (请参阅 [互操作性](upgrade-to-teams-on-prem-coexistence.md#interoperability)。 ) 此外，受邀请的用户始终可以加入 Skype for Business 或团队会议，但是他们必须使用与会议类型对应的客户端。 有关详细信息，请参阅 [会议](upgrade-to-teams-on-prem-coexistence.md#meetings)。

由于选择功能转换中的用户通常不在孤岛模式下，因此无论其他用户使用哪种客户端，用户的状态都是一致的。 如果用户处于 Skype for business 模式之一，则所有其他用户将在 Skype for Business 中根据该用户的活动看到状态。 同样，如果用户处于 TeamsOnly 模式，则所有其他用户将根据团队中的用户活动查看状态。 有关详细信息，请参阅 [状态](upgrade-to-teams-on-prem-coexistence.md#presence)。

对于尚未使用团队开始的组织，管理员应将租户范围内的模式从 "岛" 更改为 "SfbWithTeamsCollab"。  (对于已有团队使用的组织而言，管理员应 "grandfather" 已在团队中激活的用户，以确保此更改不适用于他们。 有关详细信息，请参阅 [已在 "孤岛" 模式下使用团队的组织的 "选择功能" 方法](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)。 ) 

当模式从孤岛更改为 SfbWithTeamsCollab 时，从未使用过团队的用户在使用 Skype for Business 的方式上没有任何区别。 但是，如果用户开始使用团队，则它们仅对功能（如团队 & 频道和文件）公开。 "聊天"、"呼叫和会议计划" 在团队中不可用，因为现在管理员已 (指定的 Skype for business 作为这些功能的所需客户) 。  

注意：当用户从孤岛更改为 Skype for Business 模式之一时，与用户进行通信的任何其他用户的团队客户都需要知道用户 A 的模式已更改，以便它可以将通信路由到用户 A 的相应客户端。 对于已建立了与用户 A 的本机团队间聊天的任何用户，可能需要长达36小时才能使这些其他用户的团队客户知道从岛到任何 Skype for Business 模式的模式更改。   相比之下，现有用户到 TeamsOnly 模式的更改将由其他客户在2个小时内发现。

管理员准备就绪后，他们可以通过将用户模式更新到 TeamsOnly，将给定用户的聊天、通话和会议计划一次性转移到所有团队。  

或者，管理员可以先将会议计划转移到团队，同时使用 SfBWithTeamsCollabAndMeetings 模式在 Skype for Business 中保留聊天和通话功能。 此模式允许组织切换到团队 for 会议-如果用户尚未准备好转到 TeamsOnly 模式 (，这通常是因为可能需要更多时间来迁移现有的 PSTN 功能) 。 此过渡方案 [首先称为会议](meetings-first.md)。

下表总结了使用 Skype for Business 模式的优点和缺点作为 TeamsOnly 模式的过渡步骤。


| 专业人士     |       各有利弊 |
| :------------------ | :---------------- |
| 最终用户的可预测路由。  所有通话和聊天均可在 Skype for Business 或团队 (，但不能同时根据管理员选择) 。  | 互操作对话缺少对格式文本、文件共享和屏幕共享的支持。  这可以与按需式会议配合使用，但这并不无缝。  |
| 消除对最终用户造成的混淆，因为给定的功能仅在一个客户端中可用。  | 用户不能同时尝试这两个客户端来查看同一组功能。 如果用户认为从 Skype for Business 切换到团队的主要模式班次，这可能会是一个因素。 |
| 允许增量引入团队。  |  | |
| 管理员完全控制从 Skype for Business 切换到团队。 |  | | 
| 允许组织在会议中使用团队，即使尚未准备好移动到 TeamsOnly 模式。 |  | |
| 由其他人查看的指定用户的状态是相同的，无论他们使用哪种客户端。  |  | |

## <a name="summary-of-upgrade-methods"></a>升级方法摘要

下表总结了升级方法：

| 使用孤岛模式 (重叠功能)      |      使用 Skype for Business 模式 (选择功能)  |
| :------------------ | :---------------- |
| 在升级到 TeamsOnly 之前，用户必须同时运行这两个客户端，因为传入聊天和通话可能会在客户端中居住。   | 聊天和呼叫仅在一台客户端中根据收件人的模式呼叫。 未升级的用户可以同时运行两个客户端，但不存在任何功能重叠 (呼叫和聊天在团队) 中不可用。  管理员还可以控制用户是在团队中还是在 Skype for business 中安排会议。   |
| 用户可以并排使用 Skype for Business 和团队进行相同的功能。   | 允许管理员引入团队的全新功能，以便 (团队和频道) 的最终用户，并且在 Skype for Business 中也不提供相同的功能。   |
|当两个用户都处于 "孤岛" 模式时，Skype for Business 和团队之间的互操作不存在。 将某些用户升级到 TeamsOnly 后，将在这些用户和其他用户（仍处于 "岛" 模式）之间进行互操作对话。 但是，孤岛用户可以选择使用团队并避免互操作对话。 | Skype for business 和团队用户之间的通信需要互操作。   |


## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

