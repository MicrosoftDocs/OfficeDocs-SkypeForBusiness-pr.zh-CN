---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b801f9dfe27aec4cb35dc6d28b80e9dfbf55390
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010625"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>从 Skype for Business 升级到 IT &mdash;管理员的团队

## <a name="overview"></a>概述

从 Skype for Business 升级到团队时，某些组织需要由其 IT 部门计划和管理的渐进式推出。 本文主要面向大型、本地组织中的 IT 管理员，但也可能适用于某些 Skype for Business Online 组织。  阅读本文之前，请务必阅读[团队升级](upgrade-start-here.md)入门和[升级框架](upgrade-framework.md)。

>[!NOTE]
>本文使用 "Skype for business Online"、"本地 Skype for business" 和 "Skype for business" 这一术语。  后一术语既指联机版本，也是本地版本。

已迁移到团队的用户不再使用 Skype for business 客户端，除非加入 Skype for business 中托管的会议。  所有传入聊天和呼叫用户团队客户端中的土地，无论发件人是使用团队还是 Skype for business。 由迁移用户组织的任何新会议将计划为团队会议。 如果用户尝试使用 Skype for Business 客户端，将阻止启动聊天和通话。  但是，用户可以（且必须）使用 Skype for Business 客户端加入他们受邀参加的会议。 （2017之前发运的旧版 Skype for business 客户端不提供 TeamsUpgradePolicy。 请确保您使用的是最新的 Skype for Business 客户端。）
 
管理员使用[模式](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)概念（ [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的属性）管理其对团队的过渡。 按照上述说明迁移到团队的用户处于 "TeamsOnly" 模式。  对于迁移到团队的组织，最终目标是将所有用户移到 TeamsOnly 模式。

有两种方法可将现有组织与 Skype for Business （无论是在线还是本地）迁移到团队：

- **并行方法**（使用孤岛模式）：将现有 Skype for business 组织中的用户引入团队，以便他们可以在过渡阶段中并排使用这两个客户端。 在此期间内，团队的大部分功能（但不是所有）都可供他们使用。 此配置的模式称为 "岛"，这是任何具有 Skype for Business 的现有组织的默认模式。 组织准备就绪后，管理员会将用户移动到 TeamsOnly 模式。

- **托管方法**（使用一个或多个 Skype for business 模式）：管理员管理组织中用户的聊天、通话和会议安排功能的过渡（从 Skype for Business 到团队）。  其中的每个功能均可在 Skype for Business 或团队中使用，但不能同时使用。 管理员使用 TeamsUpgradePolicy 控制何时将此功能转移给其用户的团队。 尚未处于 TeamsOnly 模式的用户将继续使用 Skype for Business 进行聊天和通话，两组用户可以通过互操作功能进行通信。 管理员通过将更多用户逐步迁移到 TeamsOnly 模式来管理切换。  

本文通过描述两种方法并展示每个方法的优缺点，帮助你为你的组织选择正确的方法。 

## <a name="side-by-side-method-using-islands-mode"></a>并行方法（使用孤岛模式）

通过并行方法，用户可以使用团队和 Skype for Business 客户端进行聊天、VoIP 呼叫和会议。 此状态称为 "孤岛" 模式，因为 Skype for business 和团队的通信流量保持独立（即使对于同一用户），并且两个不同的客户端彼此之间不会相互通信（对于同一组织内的用户）。 例如，假设收件人用户 A 处于 "孤岛" 模式下：

- 从其他用户的 Skype for business 客户端发起的通信将始终位于用户 A 的 Skype for business 客户端。
- 从另一个用户的团队客户端发起的通信将始终位于用户 A 的团队客户端（*如果其他用户位于同一组织中*）。 
- 从另一个用户的团队客户发起的通信将始终位于用户 A 的 Skype for business 客户端中（*如果其他用户位于联合组织*中）。

孤岛模式是 TeamsUpgradePolicy 尚未 TeamsOnly 的任何现有组织的默认模式。 分配 Office 365 许可证时，默认情况下会分配团队和 Skype for business Online 许可证。 （即使用户在 Skype for Business 服务器内部托管，也是如此。 无论用户是在本地还是在网上托管，都将启用 Skype for Business Online 许可证，因为当前需要完整的团队功能。事实上，如果您没有执行任何步骤来更改默认配置，您的组织中可能已有团队的大量使用。  这是并行方法的优点之一。 它允许在组织内快速、最终用户推动采用。

为使此方法有效工作，它要求所有用户同时运行两个客户端。 在 "Skype for business" 或 "团队客户端" 中，组织内部的聊天和从组织内部进行的通话可以居住在 Skype for business 或团队客户端中，这不受收件人的控制。 这取决于发件人用于发起通信的客户端。 如果发件人和收件人位于不同组织中，则在 "岛" 模式下传入呼叫和聊天始终位于 Skype for Business 客户端中。  

例如，如果一种 "一种模式" 收件人运行的是 Skype for Business，而不是团队，而其他人从团队邮件发送邮件，则 "岛模式" 收件人将看不到该邮件（但他们最终会收到一封电子邮件，告知他们错过了工作组中的邮件）。 同样，如果用户运行的是团队，而不是 Skype for business，并且某人从 Skype for business 发送消息，用户将看不到该聊天。  他们将收到一封电子邮件，说明错过的消息。 这两种情况下的行为与通话类似。 如果用户不运行这两个客户端，很容易导致不满。

当用户 A 处于 "孤岛" 模式时，团队和 Skype for business 中的其他用户看到的用户 A 的状态是独立的：

- 其他用户在使用团队时，将根据用户 A 的团队活动查看状态。 
- 使用 Skype for Business 时，其他用户将根据用户 A 在 Skype for Business 中的活动查看状态。 

这意味着其他用户可能会看到用户 A 的不同状态，具体取决于其使用的客户端。 有关详细信息，请参阅[联机状态](#presence)。

准备好将用户升级到 TeamsOnly 模式后，你可以单独升级用户，也可以使用租户范围的策略一次性升级整个租户。 用户升级到 TeamsOnly 模式后，他们将收到团队中的所有传入聊天和通话。 （请注意，仅当向单个用户应用 TeamsUpgradePolicy 时，才会触发将 Skype for Business 会议迁移到团队会议，而不是在每租户基础上进行。 有关详细信息，请参阅[会议迁移](#meeting-migration)。）

但是，在孤岛模式下未升级的收件人可能会继续接收来自其 Skype for Business 或团队客户的 TeamsOnly 用户的聊天和呼叫。  这是因为团队客户为团队到团队和团队到 Skype for business 通信（即使是对于同一用户）维护单独的对话线程。  （请参阅[团队对话-互操作与本机线程](#teams-conversations---interop-versus-native-threads)。） 例如，假设 "岛用户 A" 使用团队向 TeamsOnly 用户 B 发送消息。当用户 B 回复该聊天时，通信将位于用户 A 的团队客户端。 现在，假设用户 A 将他的 Skype for Business 客户端用作 TeamsOnly 用户 B 的消息。用户 B 将在团队中接收聊天，但这将是用户 B 的团队客户端中与其他对话进行比较的单独对话。 如果用户 B 使用用户 A 答复此对话，则它将在用户 A 的 Skype for Business 客户端中居住。 

下表总结了孤岛模式和 TeamsOnly 模式的团队体验：  

| 团队体验 | 在 "孤岛" 模式下 | 在 TeamsOnly 模式下 |
|:------------------ | :------------------- | :------------------ |
| 传入聊天和通话接收时间：|  团队或 Skype for business | Teams |
| 在以下情况中接收 PSTN 呼叫： | Skype for Business <br>（在孤岛模式下不支持使用团队中的 PSTN 功能。）    | Teams |   
 |状态  | Skype for business 和团队中的状态是独立的。 对于同一孤岛用户，用户可能会看到不同的状态，具体取决于他们使用的客户端。 | 状态仅基于用户在团队中的活动。 所有其他用户，无论他们使用哪种客户端，都可以查看该状态。 | 
 | 会议计划   | 用户可以在团队或 Skype for Business 中安排会议。 它们将在 Outlook 中看到两个外接程序。 |   用户仅在团队中安排会议。 Outlook 中仅提供团队外接程序。 | 

下表总结了使用并行方法将组织迁移到团队的优点和缺点。

| 专业人士     |       各有利弊 |
| :------------------ | :---------------- |
| 允许在组织内进行快速采纳。| 由于存在两个具有类似功能但不同用户界面的客户端，导致最终用户混淆的可能性。 而且，他们无法控制传入聊天/呼叫在哪个客户端。 |
| 允许用户在仍然拥有 Skype for business 的完全访问权限的情况下了解和熟悉团队。 | 由于未在用户运行两个客户端时丢失的消息，导致最终用户不满的可能性。 用户可能会抱怨他们没有收到消息。|
| 在团队中开始的最少管理工作。 | 如果不是组织中的每个人都使用团队，尤其是当组织中的所有用户都未处于活动状态时，"使用孤岛" 模式非常有挑战性并移至 TeamsOnly 模式。 例如，一旦用户的子集升级到 TeamsOnly 模式，这些用户将仅在团队中发送。 对于在孤岛模式下填充的其余部分，这些消息将始终位于团队中。 但是，如果其中一些人口不运行团队，他们会将这些消息视为错过。 |
|  | 使用团队时，Skype for Business 服务器中具有本地帐户的用户没有互操作或联合身份验证支持。  如果您有一种混合的孤岛用户，这可能会造成混乱，因为这种用户在 Skype for business Online 中托管，而有些在本地 Skype for business 中。   |

## <a name="managed-transition-method-using-skype-for-business-modes"></a>托管转换方法（使用 Skype for Business 模式）

某些组织可能希望向最终用户提供其组织从 Skype for Business 转换到团队的更简单、更具可预测的体验。 在此模型中，IT 管理员使用 TeamsUpgradePolicy 中的 Skype for Business 模式之一，在迁移到 TeamsOnly 模式之前明确指定哪些用户在 Skype for Business 中保留。 当他们准备将所选用户移动到 TeamsOnly 模式时，管理员会将这些用户的模式更新为 TeamsOnly。  随着部署的进展，越来越多的用户将从 Skype for Business 转换到 TeamsOnly 模式。  在此过渡期间：

- 无论通信来源于其他用户的团队还是 Skype for business 客户端，仍在使用 Skype for business 的用户接收 Skype for business 客户端的所有传入聊天和呼叫。 此外，对于这些 Skype for Business 用户，将禁用团队客户端中的 "调用和聊天" 功能，以帮助防止最终用户混淆和确保正确路由。 

- TeamsOnly 模式中的用户可接收其团队客户端中的所有传入聊天和通话，无论通信来源：团队、Skype for Business 或任何类型的联盟用户。 

与孤岛方法不同，在托管转换方法中，Skype for Business 用户和 TeamsOnly 用户可以相互通信。 Skype for Business 用户和团队用户之间的通信称为互操作性或 "互操作"。 （请参阅[互操作性](#interoperability)。）在 Skype for business 中的用户与团队中的另一用户之间进行聊天和通话之间，互操作通信是可行的。 此外，受邀请的用户始终可以加入 Skype for business 或团队会议，但是他们必须使用对应于会议类型的客户端。 有关详细信息，请参阅[会议](#meetings)。

由于托管转换中的用户通常不在孤岛模式下，因此无论其他用户使用哪种客户端，用户的状态保持一致。 如果用户处于 Skype for business 模式之一，则所有其他用户将在 Skype for Business 中根据该用户的活动看到状态。 同样，如果用户处于 TeamsOnly 模式，则所有其他用户将根据团队中的用户活动查看状态。 有关详细信息，请参阅[状态](#presence)。

对于尚未使用团队开始的组织，管理员应将租户范围内的模式从 "岛" 更改为 "SfbWithTeamsCollab"。 （对于已有团队使用的组织，管理员应 "grandfather" 用户在团队中已处于活动状态，以确保此更改不适用于他们。 有关详细信息，请参阅[已在 "孤岛" 模式下使用团队的组织的托管升级](#a-managed-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)。

当模式从孤岛更改为 SfbWithTeamsCollab 时，从未使用过团队的用户在使用 Skype for Business 的方式上没有任何区别。 但是，如果用户开始使用团队，则它们仅对功能（如团队 & 频道和文件）公开。 "聊天"、"呼叫和会议计划" 将不会在团队中提供，因为管理员已将 Skype for Business 指定为这些功能的所需客户端。  

注意：当用户从孤岛更改为 Skype for Business 模式之一时，与用户进行通信的任何其他用户的团队客户都需要知道用户 A 的模式已更改，以便它可以将通信路由到用户 A 的相应客户端。 对于已建立了与用户 A 的本机团队间聊天的任何用户，可能需要长达36小时才能使这些其他用户的团队客户知道从岛到任何 Skype for Business 模式的模式更改。   相比之下，现有用户到 TeamsOnly 模式的更改将由其他客户在2个小时内发现。

管理员准备就绪后，他们可以通过将用户模式更新到 TeamsOnly，将给定用户的聊天、通话和会议计划一次性转移到所有团队。  

或者，管理员可以先将会议计划转移到团队，同时使用 SfBWithTeamsCollabAndMeetings 模式在 Skype for Business 中保留聊天和通话功能。 此模式允许组织切换到会议的团队-如果用户尚未准备好转到 TeamsOnly 模式（通常是由于迁移现有 PSTN 功能需要更多时间）。 此过渡方案[首先称为会议](meetings-first.md)。


下表总结了使用 Skype for Business 模式的优点和缺点作为 TeamsOnly 模式的过渡步骤。


| 专业人士     |       各有利弊 |
| :------------------ | :---------------- |
| 最终用户的可预测路由。  根据管理员选择，所有通话和聊天均可在 Skype for business 或团队（但不是两者）中进行。  | 互操作对话缺少对格式文本、文件共享和屏幕共享的支持。  这可以与按需式会议配合使用，但这并不无缝。  |
| 消除最终用户的混乱，因为给定的功能仅在一个客户端中可用。  | 用户不能并行尝试同一组功能的两个客户端。 如果用户认为从 Skype for Business 切换到团队的主要模式班次，这可能会是一个因素。 |
| 允许增量引入团队。  |  | |
| 管理员完全控制从 Skype for Business 切换到团队。 |  | | 
| 允许组织在会议中使用团队，即使尚未准备好移动到 TeamsOnly 模式。 |  | |
| 由其他人查看的指定用户的状态是相同的，无论他们使用哪种客户端。  |  | |

## <a name="summary-of-upgrade-methods"></a>升级方法摘要

下表总结了升级方法：

| 并排（使用孤岛模式）     |      托管（使用 Skype for Business 模式） |
| :------------------ | :---------------- |
| 在升级到 TeamsOnly 之前，用户必须同时运行这两个客户端，因为传入聊天和通话可能会在客户端中居住。   | 聊天和呼叫仅在一台客户端中根据收件人的模式呼叫。 未升级的用户可以同时运行两个客户端，但不存在任何功能重叠（呼叫和聊天在团队中不可用）。  管理员还可以控制用户是在团队中还是在 Skype for business 中安排会议。   |
| 用户可以并排使用 Skype for Business 和团队进行相同的功能。   | 允许管理员向最终用户（团队和频道）引入团队的全新功能，而无需提供与 Skype for Business 中也存在的相同功能。   |
|当两个用户都处于 "孤岛" 模式时，Skype for Business 和团队之间的互操作不存在。 将某些用户升级到 TeamsOnly 后，将在这些用户和其他用户（仍处于 "岛" 模式）之间进行互操作对话。 但是，孤岛用户可以选择使用团队并避免互操作对话。 | Skype for business 和团队用户之间的通信需要互操作。   |

## <a name="tools-for-managing-the-upgrade"></a>用于管理升级的工具

对于上述任一方法，管理员使用[TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)（用于控制用户的共存模式）管理到 TeamsOnly 的切换。 有关每种模式的详细信息，请参阅[共存模式](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)。

无论管理员是使用 Skype for Business 模式执行托管转换，还是仅从默认孤岛配置升级到 TeamsOnly 模式，TeamsUpgradePolicy 是主要工具。  与团队中的任何其他策略一样，TeamsUpgradePolicy 可以直接分配给用户，也可以设置为租户范围内的默认值。 对用户的任何分配都优先于租户默认设置。  它可以在团队管理员控制台和 PowerShell 中进行管理。

管理员可以将用户的任何模式分配给用户，无论该用户是托管在 Skype for Business Online 还是在本地，除了只能将 TeamsOnly 模式分配给已驻留在 Skype for business Online 中的用户。 这是因为只有在用户托管在 Skype for business Online 的情况下，才可以使用 Skype for business 用户和联盟进行互操作。

具有 Skype for business 帐户的 Skype for business 帐户的用户必须在 Skype for business 内部部署工具中使用移动 Move-csuser 在本地[移动](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)（到 skype For business online 或直接使用团队）。 这些用户可以通过1个或2个步骤移到 TeamsOnly：

-   1步：在 Move-csuser 中指定-MoveToTeams 开关。 这需要 Skype for business Server 2019 或 Skype for business Server 2015 与 CU8。

-   2个步骤：运行移动 Move-csuser 后，使用 TeamsUpgradePolicy 向用户授予 TeamsOnly 模式。

与其他策略不同，不能在 Office 365 中创建新的 TeamsUpgradePolicy 实例。 所有现有实例都内置在该服务中。  （请注意，mode 是 TeamsUpgradePolicy 内的一个属性，而不是策略实例的名称。）在某些（但不是全部）情况下，策略实例的名称与模式相同。 特别是，若要为用户分配 TeamsOnly 模式，请将 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例授予该用户。 若要查看所有实例的列表，可以运行以下命令：

```
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

若要将联机用户升级到 TeamsOnly 模式，请分配 "UpgradeToTeams" 实例： 

```
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

若要将内部部署的 Skype for business 用户升级到 TeamsOnly 模式，请在本地工具集中使用移动 Move-csuser：

```
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

若要为租户中的所有用户更改模式（具有明确的每用户授权的用户除外），请运行以下命令：

```
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>如果你拥有本地 Skype for Business 帐户的任何用户，则不应在租户级别分配 TeamsOnly 模式，除非你将其他模式显式分配给具有本地 Skype for Business 帐户的所有用户。


### <a name="using-notifications-in-skype-for-business-clients"></a>在 Skype for Business 客户端中使用通知

管理员可以选择在 Skype for Business 客户端中提供最终用户通知，以通知用户即将升级到团队，如下图所示。 例如，管理员计划将一组用户升级到 TeamsOnly 模式之前的一周，管理员可能希望为该组用户启用这些通知。 使用 NotifySfbUsers = true 的 TeamsUpgradePolicy 实例启用这些通知。  对于除 TeamsOnly 之外的所有模式，实际上每个模式有两个实例，它们对应于 NotifySfbUsers 的两个值。  对于除 TeamsOnly 之外的所有模式，实际上每个模式有两个实例，它们对应于 NotifySfbUsers 的两个值。 

![显示通知的图表](media/teams-upgrade-sfb-with-notifications.png)

如果你的用户托管在 Skype for Business Online 中，只需分配与用户具有相同模式的策略实例，但 NotifySfbUsers = true。 

如果你的用户托管在本地 Skype for business 服务器中，你需要使用本地工具集，你需要使用 skype for business server 2019 或 CU8 for Skype for business Server 2015。 在本地 PowerShell 窗口中，使用 NotifySfbUsers = true 创建 TeamsUpgradePolicy 的新实例：

```
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

然后，使用相同的本地 PowerShell 窗口，将该新策略分配给所需的用户：

```
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

### <a name="meeting-migration"></a>会议迁移

当用户迁移到 TeamsOnly 模式时，默认情况下，他们组织的现有 Skype for Business 会议将被转换为团队。 你可以选择禁用向用户分配 TeamsOnly 模式时的默认行为。 从本地移动用户时，必须将会议迁移到云才能使用联机用户帐户运行，但如果未指定-MoveToTeams，则会议将作为 Skype for Business 会议进行迁移，而不是转换为团队。 

在租户级别分配 TeamsOnly 模式时，不会为任何用户触发会议迁移。 如果你希望在租户级别分配 TeamsOnly 模式和迁移会议，则可以使用 PowerShell 获取租户中的用户列表（例如，使用 CsOnlineUser 和需要的任何筛选器），然后遍历这些用户中的每个用户以触发会议使用开始-CsExMeetingMigration 的迁移。 有关详细信息，请参阅[使用会议迁移服务（MMS）](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。


### <a name="additional-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>适用于本地 Skype for business 服务器的组织的其他注意事项

- 设置 Skype for business 混合是迁移到 TeamsOnly 模式的先决条件。 虽然在不带混合的孤岛模式下可以使用团队，但在用户从本地 Skype for business Online 移动到 Skype for business Online （使用[Move move-csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)）之前，无法进行切换到 TeamsOnly 模式。 有关详细信息，请参阅[配置混合连接](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)。

- 具有本地 Skype for business 帐户的团队用户（即，他们尚未通过使用 Move-Move-csuser 移到云）无法与任何 Skype for Business 用户进行互操作，也不能与外部用户联盟。 此功能仅在用户被移动到云中后才可用（在 "孤岛" 模式下，或作为 TeamsOnly 用户）。 

- 如果你拥有本地 Skype for Business 帐户的任何用户，则不应在租户级别分配 TeamsOnly 模式，除非你将其他模式显式分配给具有本地 Skype for Business 帐户的所有用户。 

- 你必须确保你的用户与正确的 Skype for Business 属性正确同步到 Azure AD。 这些属性都是带有 "msRTCSIP-" 的所有前缀。 如果用户未正确地与 Azure AD 同步，团队中的管理工具将无法管理这些用户。 有关详细信息，请参阅[配置团队和 Skype for business 的 AZURE AD 连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- 若要在混合组织中创建新的 TeamsOnly 或 Skype for business Online 用户，*必须先在本地 Skype for Business Server 中启用用户*，然后使用 move-csuser 将用户从本地移动到云。  首先在本地创建用户可确保其他任何其他本地 Skype for business 用户能够路由到新创建的用户。 在所有用户都已联机移动后，不再需要先在本地启用用户。

- 当用户从本地移动到云时，按该用户组织的会议将迁移到 Skype for business Online 或团队中，具体取决于是否指定了-MoveToTeams 开关。

- 如果你想要在本地用户的 Skype for Business 客户端中显示通知，则必须在本地工具集中使用 TeamsUpgradePolicy。 仅 NotifySfbUsers 参数对于本地用户是相关的。  本地用户从 TeamsUpgradePolicy 的联机实例接收其模式。 请参阅[授权 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中的备注。 

>[!NOTE]
> 2019在9月3日之后创建的任何新租户均以 TeamsOnly 租户的形式创建，不具备管理员降级的能力。 如果组织的 Skype for Business Server 本地版以前从未使用过 Office 365 订阅9月3日之前的版，2019将需要联系 Microsoft 支持部门，以便在使用 Office 365 购买套餐后，将其租户降级。 


## <a name="perform-the-upgrade-for-your-organization"></a>为您的组织执行升级

本部分介绍下列升级选项：

- 并行升级（使用孤岛模式）
- 尚未使用团队开始的组织的托管升级
- 已在孤岛模式下使用团队的组织的托管升级

### <a name="side-by-side-upgrade-using-islands-mode"></a>并行升级（使用孤岛模式）

对于并行升级选项：

- 如果您可以快速升级整个组织，请考虑此选项。  由于运行这两个客户端有潜在的风险，因此最好将此时间段最小化。 你应该确保你的用户知道运行这两个客户端。

- 此选项是现成模型，不需要管理员操作即可开始使用 Office 365 许可证，而不需要管理员操作。 如果你的用户已有 Skype for Business Online，则你可能已在使用此模型。

- 在并行模式下，并移动到 TeamsOnly 可能会产生挑战性。 由于升级用户仅通过团队进行通信，因此组织中与该用户通信的任何其他用户都必须使用团队。  如果你有尚未开始使用团队的用户，这些用户将暴露给缺失的消息。 此外，他们在 Skype for Business 中看不到 TeamsOnly 用户在线。 某些组织选择使用租户全局策略执行租户范围的升级以避免这种情况，但需要等待所有用户都准备好升级。


### <a name="a-managed-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>尚未使用团队开始的组织的托管升级

如果你的组织还没有团队中的任何活动用户，第一步是将 TeamsUpgradePolicy 的默认租户范围策略设置为 Skype for Business 模式之一，例如 SfbWithTeamsCollab。  尚未开始使用团队的用户将不会注意到行为的任何差异。 但是，在租户级别设置此策略将使用户能够开始将用户升级到 TeamsOnly 模式，并确保已升级的用户仍可以与未升级的用户进行通信。  一旦你确定了你的试点用户，你可以将其升级到 TeamsOnly。  如果他们在本地，请使用 Move-csuser。 如果它们处于联机状态，只需使用 TeamsUpgradePolicy 为其分配 TeamsOnly 模式。  默认情况下，由这些用户安排的任何 Skype for Business 会议将迁移到团队。

下面是键命令：

1. 将租户范围的默认值设置为 mode SfbWithTeamsCollab，如下所示：

   ```
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 将用户升级到 TeamsOnly，如下所示：

   - 如果用户已联机：

     ```
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - 如果用户在本地：

     ```
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

注释
 
- 你可以将租户范围内的策略设置为 SfbWithTeamsCollab，而不是将其设置为 SfbWithTeamsCollabAndMeetings。 这将导致所有用户在团队中安排所有新会议。
- Move-Move-csuser 是本地工具中的一个 cmdlet。 MoveToTeams 开关需要与 CU8 的 Skype for business Server 2019 或 Skype for business Server 2015。 如果你使用的是以前的版本，你可以先将用户移动到 Skype for business Online，然后向该用户授予 TeamsOnly 模式。
- 默认情况下，当升级到 TeamsOnly 模式或分配 SfbWithTeamsCollabAndMeetings 模式时，Skype for business 会议将迁移到团队。  

下图显示了组织的托管升级的概念阶段，这些阶段没有团队的预先使用。 条形图的高度表示用户数。 在升级的任何阶段，所有用户都可以相互通信。  Skype for Business 用户使用互操作与 TeamsOnly 用户通信，反之亦然。

![显示未事先使用团队的托管升级的图表](media/teams-upgrade-1.png)


### <a name="a-managed-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>已在孤岛模式下使用团队的组织的托管升级

如果您的组织中的某些用户在以孤岛模式使用团队，则您可能不希望删除现有用户的功能。 因此，在更改租户范围的策略之前，需要额外步骤。 解决方案是先将这些现有活动团队用户 "grandfather" 用户转换为孤岛模式，然后再将租户范围内的策略设置为 "SfbWithTeamsCollab"。  完成此操作后，你可以按照上面的步骤继续部署，但是你将有两组用户迁移到 TeamsOnly：团队中处于活动状态的用户将处于 "孤岛" 模式下，其余用户将处于 "SfbWithTeamsCollab" 模式。 你可以逐步将这些用户移动到 TeamsOnly 模式。

1. 查找团队中处于活动状态的用户，如下所示：

   1. 从 Office 365 管理门户的左侧导航中，转到 "报表"，然后转到 "使用情况"。 
   2. 在 "选择报表" 下拉列表中，选择 "Microsoft 团队"，然后选择 "用户活动"。 这将提供已在团队中处于活动状态的用户的可导出表。 
   3. 单击 "导出"、"打开 Excel" 和 "筛选" 以仅显示团队中处于活动状态的用户。

2. 对于在步骤1中发现的每个活动团队用户，请在远程 PowerShell 中为其分配孤岛模式。 这允许你转到下一步，并确保不更改用户体验。  

   ```
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. 将租户范围内的策略设置为 SfbWithTeamsCollab：

   ```
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 将所选用户升级到 TeamsOnly 模式。 你可以选择在 "孤岛模式" 或 "SfbWithTeamsCollab" 模式下升级用户，但你可能希望首先优先于在孤岛模式下升级用户，以最大程度减少用户处于 "孤岛模式" 时可能出现的混淆的可能性。   

   对于驻留在 Skype for business Online 中的用户：  

   ```
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   对于驻留在本地 Skype for business 服务器的用户：  

   ```
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

下图显示了托管过渡的概念阶段，其中的开始处有活动的孤岛用户。 条形图的高度表示用户数。 在升级的任何阶段，所有用户都可以相互通信。  Skype for Business 用户使用互操作与 TeamsOnly 用户通信，反之亦然。


![在孤岛模式下显示具有活动用户的托管升级的图表](media/teams-upgrade-2.png)

   

## <a name="considerations-for-pstn-calling"></a>PSTN 呼叫的注意事项

如果涉及 PSTN 呼叫功能，则在移动到 TeamsOnly 模式时有四种可能的情形：

- *Skype For Business Online 中使用 Microsoft 通话计划的用户*。 升级后，此用户将继续拥有 Microsoft 通话计划。

- *Skype for Business Online 中的用户，* 通过 skype for business 本地或云连接器版本使用本地语音功能。 用户对团队的升级需要与用户迁移以直接路由，以确保 TeamsOnly 用户具有 PSTN 功能。

- *使用企业语音的 Skype For business online 中的用户，这些用户将移动到联机状态并保持本地 PSTN 连接*。  将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并通过将用户迁移到直接路由来协调该用户。 

- *使用企业语音的 Skype For business online 中的用户*，这些用户将移动到联机并使用 Microsoft 通话计划。  将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并将该用户的电话号码的端口协调为 "Microsoft 呼叫计划" 或 "B"，将新的订户号码指定为可用区域。

本文仅提供高级别概述。  有关详细信息，请参阅[电话系统直接路由](direct-routing-landing-page.md)和[通话计划](calling-plan-landing-page.md)。 此外，请注意，仅当用户处于 TeamsOnly 模式时，才支持将电话系统与团队配合使用。  如果用户处于 "孤岛" 模式，则只有 Skype for Business 才支持电话系统。 

### <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>通过 Microsoft 通话计划从 Skype for Business Online 

这是涉及语音的最简单的升级方案。 

1. 请确保已为用户分配了团队许可证。 默认情况下，当你分配 Office 365 许可证时，团队已启用，因此除非你以前禁用了团队许可证，否则不需要执行任何操作。

2.  如果用户已有一个包含电话号码的 Microsoft 通话计划，则唯一所需的更改是在 TeamsUpgradePolicy 中分配用户 TeamsOnly 模式。  在分配 TeamsOnly 模式之前，传入的 PSTN 呼叫将位于用户的 Skype for Business 客户端中。 升级到 TeamsOnly 模式后，传入的 PSTN 呼叫将位于用户的团队客户端。  

### <a name="from-skype-for-business-online-with-on-premises-voice"></a>通过 Skype for Business Online 与本地语音

在此方案中，用户已在 Skype for business Online 中，但其 PSTN 连接在本地，使用混合模式或云连接器版本中的 Skype for business 服务器。 通过 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着为直接路由启用它们，PSTN 中继通过本地会话边界控制器（SBC）直接连接到云中的直接路由服务。

下面列出了基本步骤。  步骤1-4 按建议的顺序列出，但可以按任意顺序完成。 关键是，所有这些都应在步骤5之前完成。

1. 如果你要将租户范围内的策略设置为 Skype for Business 模式之一，请确保通过显式分配任何现有的 grandfather 用户，如前面所述。

2. 为直接路由配置租户。 请参阅[直接路由的每租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如果需要，为这些用户配置各种团队策略（例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 可以随时执行此操作，但如果你希望确保用户在升级时具有正确的配置，最好在将用户升级到 TeamsOnly 模式之前执行此操作。

4. 准备选择要进行语音迁移的用户： 
   - 如有必要，请分配 "团队" 许可证。  假设用户在本地语音的 Skype for business Online 中已起作用，则用户已经拥有 Skype for business 计划2和 Microsoft Phone 系统。 让这些计划保持启用状态，包括 Skype for Business Online 计划2许可证。  
   - 分配所需的 OnlineVoiceRoutingPolicy。 

5. 升级用户：这些步骤应协调。 

   - 在 Office 365 中，将用户升级到 TeamsOnly 模式（Grant-CsTeamsUpgradePolicy）。
   - 在 SBC 上，将语音路由配置为通过将呼叫发送到直接路由（而不是本地中介服务器）来启用传入呼叫。


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>从具有企业语音的本地 Skype for Business 服务器到直接路由

在此方案中，用户仍托管在本地 Skype for business 中，并且其 PSTN 连接也位于本地。 通过 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着为直接路由，然后将用户移动到云。 
 
下面列出了基本步骤。  步骤1-5 按建议的顺序列出，但可以按任意顺序完成。 关键是，所有这些都应在步骤6之前完成。

1. 如果你要将租户范围内的策略设置为 Skype for Business 模式之一，请确保将现有的 grandfather 用户显式分配给其孤岛模式（如前面所述）。

2. 如果尚未执行此操作，请[为 Skype for business 混合配置组织](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 为直接路由配置租户。 请参阅[直接路由的每租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如果需要，为这些用户配置各种团队策略（例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 可以随时执行此操作，但如果你希望确保用户在升级时具有正确的配置，最好在将用户升级到 TeamsOnly 之前执行此操作。

5. 如有必要，请分配 Office 365 许可证。  用户应同时拥有团队和 Skype for business Online 计划2以及电话系统。 如果 "Skype for Business Online 计划 2" 已禁用，请重新启用它。  

6. 升级用户：这些步骤应协调。 

   - 使用本地 Skype for Business 工具，通过-MoveToTeams 开关运行 Move-csuser。 如果你使用的 Skype for Business Server 版本不支持-MoveToTeams 开关，请先运行 Move Move-csuser，然后在租户远程 PowerShell 或团队管理控制台中分配 TeamsOnly 模式。

   - 在 SBC 上，将语音路由配置为通过将呼叫发送到直接路由（而不是本地中介服务器）来启用传入呼叫。 

   - 在 Office 365 中：分配相关的 OnlineVoiceRoutingPolicy 以启用传出呼叫。 


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>从具有企业语音的本地 Skype for Business 服务器到 Microsoft 通话计划

在此方案中，用户仍托管在本地 Skype for business 中，并且其 PSTN 连接也位于本地。 通过 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着将用户移动到云，并将其编号从旧运营商移植到 Microsoft 通话计划，或为用户分配一个新号码。 

下面列出了基本步骤。步骤1-5 按建议的顺序列出，但可以按任意顺序完成。 关键是，所有这些都应在步骤6之前完成。 

1. 如果你要将租户范围内的策略设置为 Skype for Business 模式之一，请确保将现有的 grandfather 用户显式分配给其孤岛模式（如前面所述）。 

2. 如果尚未执行此操作，请[为 Skype for business 混合配置组织](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。 

3. 如果需要，为这些用户配置各种团队策略（例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 可以随时执行此操作，但如果你希望确保用户在升级时具有正确的配置，最好在将用户升级到 TeamsOnly 之前执行此操作。 

4. 如有必要，请分配 Office 365 许可证。用户应同时拥有团队和 Skype for business Online 计划2以及电话系统。 如果 "Skype for Business Online 计划 2" 已禁用，请重新启用它。  

5. 为您的用户获取电话号码。 （有关详细信息，请参阅[管理你的组织的电话号码](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。）

   - 如果您将重新使用这些号码，请向您的运营商提交一个移植请求。  
   - 或者，您可以直接从 Microsoft 获取新号码。 

6. 升级用户。 使用本地 Skype for Business 工具，通过-MoveToTeams 开关运行 Move-csuser。  

    - 如果你要将数字移植到 Microsoft，你应该将此操作的计时协调为在端口出现时发生。 

    - 如果您使用的是 Microsoft 的新号码，您需要为用户更改 LineUri。应在本地工具中执行此操作，然后通过 Azure AD Connect 将其同步到云。 当 Azure AD Connect 同步更改时，你应该与 Move-csuser 操作保持同步。 

### <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由的每租户配置摘要 

1. 通过查看[此列表](direct-routing-border-controllers.md)，确保你的会话边界控制器（SBC）支持直接路由。 您还必须确保拥有正确版本的固件。  

2. 将本地 SBC 与团队直接路由服务配对。 有关详细信息，请参阅将[SBC 与电话系统的直接路由服务配对](direct-routing-configure.md#pair-the-sbc-to-the-direct-routing-service-of-phone-system)。 

3. 此配置实质上是本地配置的镜像。 联机配置包括： 
   - OnlineVoiceRoutingPolicy （基于本地 VoiceRoutingPolicy，如果从 Skype for business Online 迁移用户，并且基于 VoicePolicy （如果从本地与企业语音）迁移用户。
   - OnlinePSTNUsage 对象（基于本地 PSTN 使用情况）。 
   - OnlineVoiceRoute 对象（基于本地 VoiceRoute）。 

有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)。 

### <a name="manage-enterprisevoiceenabled-property-during-migration"></a>迁移期间管理 EnterpriseVoiceEnabled 属性 

无论使用直接路由还是 Microsoft 呼叫计划，用户都必须在 Azure AD 中具有 EnterpriseVoiceEnabled = true，用户才能拥有 PSTN 功能。  EnterpriseVoiceEnabled （"EV-enabled"）是在本地目录和云中都存在的属性（不是策略）。 云中的值是团队的重要事项。  如何将 EV 启用的确切逻辑设置为 true 取决于以下方案： 

- 如果用户在本地 Skype for Business 服务器中启用了 EV，并且在将用户移动到云之前使用 Move-Move-csuser 为用户分配了电话系统许可证，则在线用户将预配为 "启用 EV"。 

- 如果现有的 TeamsOnly 或 Skype for business Online 用户分配有电话系统许可证，则默认情况下，启用 EV 不会设置为 true。  如果在分配电话系统许可证之前将本地用户移到云，也会出现这种情况。 在任何一种情况下，管理员都必须指定以下 cmdlet： 

  ```
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="coexistence-of-teams-with-skype-for-business"></a>具有 Skype for Business 的团队的共存

本部分概述了在同一组织中运行团队和 Skype for business 客户端时可能遇到的问题，无论使用的是何种模式和使用哪种升级方法：

- [会议](#meetings)
- [交互性](#interoperability)
- [团队对话-互操作与本机线程](#teams-conversations---interop-versus-native-threads)
- [状态](#presence)
- [联合身份验证](#federation)
- [联系人](#contacts)

### <a name="meetings"></a>会议

无论其模式如何，用户始终可以加入受邀的任何类型的会议，无论是 Skype for business 还是团队。  但是，用户必须使用与会议类型匹配的相应客户端加入会议：

- 如果会议是团队会议，则所有参与者（无论是 TeamsOnly、孤岛还是 Skype for business 用户）都可以使用团队客户端加入会议。 如果未安装团队，则在尝试加入会议时，用户将转到 web。

- 如果会议是 Skype for business 会议，则所有参与者（无论是 TeamsOnly、孤岛还是 Skype for business 用户）都可以使用 Skype for Business 客户端加入会议。 如果未安装 Skype for Business 客户端，用户将通过 Skype 会议应用定向到 web 以加入。

组织会议时，计划的会议类型基于组织者的模式，如下表所示：

| 组织者模式    |      行为 |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    在团队中安排的所有会议。 Outlook 中不提供 Skype for business 加载项。 | 
| SfbWithTeamsCollab, SfbOnly   | Skype for Business 中安排的所有会议。 "团队外接程序" 在 Outlook 中不可用。 | 
| 群岛 |     可在 Skype for Business 或团队中安排会议。 Outlook 中提供了这两个加载项。 | 


### <a name="interoperability"></a>交互性

在某些情况下，团队支持与 Skype for Business 之间的互操作性（"互操作"）。 互操作通信指的是 Skype for Business 用户与团队用户之间的聊天或通话。  互操作通信仅在两个用户之间可用;不支持多方聊天/通话或添加其他用户。

当满足以下每个条件时，将创建两个用户之间的互操作聊天或呼叫：

- 一个用户使用的是团队，另一个用户使用的是 Skype for Business。

- 初始通信的收件人模式不是孤岛（否则，通信将位于同一客户端），如果两个用户都在同一个组织中。 在联合方案中，发送用户使用团队，而收件人不处于 TeamsOnly 模式。 

- 团队用户还没有驻留在本地的 Skype for business 帐户。 

在互操作通信中，聊天仅为纯文本。 此外，在*互操作聊天中*不能进行文件共享和屏幕共享。 但是，互操作对话中的用户可以通过创建按需会议（如下所述）轻松实现文件和/或屏幕共享。

- 如果团队用户尝试共享其屏幕，将自动创建按需团队会议，并将邀请链接发送到 Skype for Business 用户的客户端。 单击该链接后，Skype for Business 用户将打开团队并加入会议。 两个用户现在都在团队会议中，可以根据需要进行共享。

- 如果 Skype for Business 用户使用的是2018或更高版本的客户端，并且尝试共享任何内容，则会自动创建一个按需 Skype for business 会议，并将邀请链接发送到团队用户的客户端。 单击该链接后，团队用户将尝试加入 Skype for Business 会议。 如果团队用户安装了 Skype for Business 客户端，它将打开，并提示用户登录（如果尚未登录）。  如果团队用户没有安装 Skype for business 客户端，系统将提示用户使用 web 版本。 这两个用户登录后，他们都在 Skype for business 会议中，并且可以根据需要进行共享。

### <a name="teams-conversations---interop-versus-native-threads"></a>团队对话-互操作与本机线程

由于互操作通信不支持本机团队对话的所有功能，因此团队客户为团队到团队和团队到 Skype for business 通信保留单独的对话线程。 这些对话在用户界面中的呈现方式不同：互操作线程可以通过以下方式与常规本机团队线程区别：

- 缺少格式文本、文件/屏幕共享的控件，无法添加用户。
- 对目标用户的图标的修改，显示 Skype for business 的 "S"。

以下屏幕截图显示了这些差异：

与用户 G3 测试的本机团队间对话

![显示本机团队间对话的图表](media/teams-upgrade-native-thread.png)

具有相同用户 G3 测试的互操作对话

![显示互操作团队到团队对话的图表](media/teams-upgrade-interop-thread.png)

一旦创建了对话线程，其类型将永远不会更改。 创建后，团队中的互操作线程将始终路由到目标用户的 Skype for Business 客户端。 本机线程将始终路由到目标用户的团队客户端。  如果收件人用户的模式发生更改，则该用户的现有团队线程将不再运行，并且将在该聊天上显示一条注释，其中包含用于启动新的本机对话的链接，如以下屏幕截图所示。 有关更多详细信息，请参阅[聊天和来自预先存在的线程的通话](coexistence-chat-calls-presence.md#chats-and-calls-from-pre-existing-threads)。


![显示已升级的 Skype for Business 用户的聊天的图表](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>状态

特定用户的状态基于通过客户端提供的服务中的用户活动。 随后将发布联机状态，供其他用户查看。  Skype for Business 和团队是具有单独客户端的独立服务，因此每个服务都有其自己的状态供用户使用。   团队和 Skype for Business Online 中的状态服务也有同步。  这允许一个服务可能会在需要时从其他服务中发布用户的状态。 

状态发布行为基于用户模式。 有三种基本情况：

- 如果用户处于 TeamsOnly 模式，则所有其他用户可查看该用户的团队状态，无论他们使用的是哪种客户端。

- 如果用户处于任何 Skype for Business 模式，则所有其他用户都可以查看该用户的 Skype for business 状态，无论他们使用哪种客户端。

- 如果用户处于 "孤岛" 模式，在 Skype for business 中发布的联机状态和团队是独立的，因此对同一组织中的用户显示的状态将取决于其他用户的客户端。 联合组织中的用户将根据其 Skype for business 活动查看该用户的状态，因为在 Skype for business 中，联盟模式用户的联盟流量。

例如，假设用户 A 处于孤岛模式。 如果用户 A 在团队中处于活动状态，但未登录到 Skype for business，则其他用户将从其团队客户端看到用户 A 是活动的，但在其 Skype for Business 客户端中，他们将把用户 A 设为 "脱机"。 这是设计使然，因为如果用户不在运行客户端，则无法访问用户 A。 

有关详细信息，请参阅[联机状态](coexistence-chat-calls-presence.md#presence)。

### <a name="federation"></a>联合身份验证

从团队到其他使用 Skype for Business 的用户的联盟要求团队用户在 Skype for business 中托管用户处于联机状态。 TeamsUpgradePolicy 控制传入联盟聊天和呼叫的路由。 除 "孤岛" 模式之外，联合路由行为与相同租户方案相同。 当收件人处于 "孤岛" 模式时：

- 在 Skype for Business 中从团队土地发起的聊天和通话（如果收件人位于联合租户中）。
- 如果收件人位于同一个租户中，则从团队中的团队土地发起聊天和通话。
- 通过 Skype for Business 发起的聊天和通话始终位于 Skype for business 中。

团队用户与 Skype for Business 之间的联盟聊天是互操作线程，因此不可能使用格式文本和共享。 用户界面以与同一租户互操作线程类似的方式公开联盟聊天，但存在指示用户是外部用户的注释。

当团队首次引入联盟时，两个团队之间的联盟聊天用户也是互操作线程，但将来会引入本机团队联合身份验证，它们为处于 TeamsOnly 模式的用户之间的对话提供了完整功能。 . 

有关详细信息，请参阅[新聊天或呼叫的联盟路由](coexistence-chat-calls-presence.md#federated-routing-for-new-chats-or-calls)。

### <a name="contacts"></a>联系人

团队和 Skype for business 具有单独的联系人列表。 这意味着在一个系统中所做的添加、删除和修改不会与其他系统同步。 但是，如果发生两个特定事件之一，来自 Skype for Business 的联系人会自动复制到团队中： 

- 对于任何 Skype for Business Online 用户，当他们第一次登录到团队时，Skype for Business 中的联系人将被复制到团队。  对于在 Skype for Business 服务器中使用本地帐户的用户，此行为不可用。  

- 将用户升级到 TeamsOnly （通过分配 TeamsUpgradePolicy 或通过移动-Move-csuser-MoveToTeams）后，当用户下次登录到团队时，Skype for Business 中的现有联系人将与已在团队中的现有联系人合并。 无论用户的 Skype for Business 帐户是托管内部还是联机，都会发生此行为。 

在这两种情况下，从 Skype for Business 到团队的联系人之间的转移是异步的，因此可能需要几分钟才能使联系人显示在团队中。 上述两个事件是触发副本的起因。  

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business 服务器与 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务（MMS）](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

