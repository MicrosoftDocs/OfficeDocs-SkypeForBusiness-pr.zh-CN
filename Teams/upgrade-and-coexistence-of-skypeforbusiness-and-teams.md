---
title: Microsoft 团队从 Skype for Business 升级 |模式、共存
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen, bjwhalen
description: Skype for business 和 Microsoft 团队共存选项和模式的详细信息，以及通过示例方案将慷慨升级到来自 Skype for Business 的团队。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6a1e54d677436b2441e9174cc265eb67b7664d2
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416742"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>选择从 Skype for Business 到团队的升级旅程

![升级旅行图，强调项目定义阶段](media/upgrade-banner-project-definition.png "升级旅行的阶段，重点关注项目定义阶段")

本文是升级历程的项目定义阶段的一部分。 继续之前，请确认你已完成以下活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)

作为现有的 Skype for Business 客户，您对团队的完全过渡可能需要一段时间。 但是，你现在可以通过让你的用户与 Skype for Business 一起使用团队，开始实现团队的价值。 假设两个应用之间存在一些重叠的功能，我们建议你查看可用的共存和升级模式，以帮助确定适合你的组织的路径。 例如，你可以选择在不具有互操作性的两个解决方案上启用所有工作负荷。 或者，你可以决定管理用户体验，方法是逐步引入团队功能或面向用户组选择功能，直到你的组织准备好将每个人升级到团队。 使用试点结果帮助评估适合您的组织的升级旅程。

> [!IMPORTANT]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大程度地实现收益并确保你的组织有适当的时间实施升级，我们鼓励你立即开始迁移到 Microsoft 团队。

本文概述了各种模式，使你能够管理 Skype for Business 和团队的哪些形式可供你的用户使用。 与任何部署一样，我们强烈建议你在将组织升级到团队之前使用选定的一组用户[试验你的预定计划](pilot-essentials.md)。 请记住，新技术的引入会使用户中断。 在实施此处所述的任何模式之前，请花一些时间来评估用户准备情况并实施通信和培训计划。

> [!TIP]
> 加入我们的现场互动式研讨会，我们将分享指导、最佳做法和资源，旨在开始升级规划和实施。
>
>首先加入[升级](https://aka.ms/SkypeToTeamsPlanning)会话的计划以开始使用。


## <a name="upgrade-journey-building-blocks"></a>升级旅程构建基块

若要正式准备您的组织以供团队旅行，您需要开始规划升级方案，最终让您的组织完全接纳团队作为您的唯一的通信和协作解决方案。

为帮助指导制定决策过程，请熟悉各种模式、概念和与从 Skype for Business 升级到团队相关的术语。 有关详细信息，请参阅[Microsoft 团队和 Skype for business 共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)

已迁移到团队的用户不再使用 Skype for business 客户端，除非加入 Skype for business 中托管的会议。 所有传入聊天和呼叫用户团队客户端中的土地，无论发件人是使用团队还是 Skype for business。 由升级用户组织的任何新会议都将计划为团队会议。 如果用户尝试使用 Skype for Business 客户端，则聊天和通话的启动将被阻止<sup>1</sup>。 但是，用户可以（且必须）使用 Skype for Business 客户端加入他们受邀参加的会议。

管理员使用[模式](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)概念（ [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的属性）管理其对团队的过渡。 按照上述说明迁移到团队的用户处于 "TeamsOnly" 模式。 对于迁移到团队的组织，最终目标是将所有用户移到 TeamsOnly 模式。

有两种方法可将现有组织与 Skype for Business （无论是在线还是本地）迁移到团队：

- **重叠的功能方法**（使用 "孤岛" 模式）：现有的 Skype for business 组织中的用户将引入团队，以便他们可以在过渡阶段同时使用这两个客户端。 在此期间内，团队的大部分功能（但不是所有）都可供他们使用。 此配置的模式称为 "岛"，这是任何具有 Skype for Business 的现有组织的默认模式。 组织准备就绪后，管理员会将用户移动到 TeamsOnly 模式。
- **选择 "功能" 方法**（使用一个或多个 Skype for business 模式）：管理员为组织中的用户管理聊天、通话和会议安排功能的过渡（从 Skype for Business 到团队）。 其中的每个功能均可在 Skype for Business 或团队中使用，但不能同时使用。 管理员使用 TeamsUpgradePolicy 控制何时将此功能转移给其用户的团队。 尚未处于 TeamsOnly 模式的用户将继续使用 Skype for Business 进行聊天和通话，两组用户可以通过互操作功能进行通信。 管理员通过将更多用户逐步迁移到 TeamsOnly 模式来管理切换。

<sup>1</sup>2017之前发运的较旧的 Skype for business 客户端不接受 TeamsUpgradePolicy。 请确保您使用的是 Office 频道中可用的最新 Skype for Business 客户端。

下面是帮助你确定组织的相应路径的关键因素。 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>重叠的功能方法（使用孤岛模式）

使用重叠的功能方法，用户可以使用团队和 Skype for Business 客户端进行聊天、VoIP 呼叫和会议。 在此方法中，团队中的聊天和 VOIP 呼叫是组织内的中心通话，而 Skype for Business 可与外部组织（如果已配置）进行聊天和 VOIP/PSTN 呼叫。 可在两种产品中安排和参加会议。

使用重叠的功能方法时，Skype for business 和团队的通信流量保持独立（即使对于同一用户），并且两个不同的客户端彼此之间不会相互通信（对于同一组织内的用户）。 用户体验基于收件人的配置。 例如，假设收件人用户 A 使用此升级方法：

- 从其他用户的 Skype for business 客户端发起的通信将始终位于用户 A 的 Skype for business 客户端。
- 从*同一组织中的用户*发起的来自团队客户端的通信将始终位于用户 a 的团队客户端。
- 从*外部组织中的用户*发起的通讯将始终位于用户 a 的 Skype for business 客户端中。

如果你为用户分配了 Office 365 许可证，这将是你的组织的默认升级体验。 分配 Office 365 许可证时，默认情况下会分配团队和 Skype for business Online 许可证。<sup>2</sup>

为使此方法有效工作，所有用户都必须同时运行这两个客户端。 在 "Skype for business" 或 "团队客户端" 中，组织内部的聊天和从组织内部进行的通话可以居住在 Skype for business 或团队客户端中，这不受收件人的控制。 这取决于发件人用于发起通信的客户端。 如果发件人和收件人位于不同组织中，则在 "岛" 模式下传入呼叫和聊天始终位于 Skype for Business 客户端中。

例如，如果将 "一种模式" 收件人登录到 Skype for Business，而不是 "团队"，并且某人将其从团队中发送给他们，则 "孤岛模式" 收件人将看不到该邮件（但他们最终会收到一封电子邮件，告知他们错过了工作组中的邮件）。 同样，如果用户运行的是团队，而不是 Skype for business，并且某人从 Skype for business 发送消息，用户将看不到该聊天。 这两种情况下的行为与通话类似。 如果用户不运行这两个客户端，很容易导致不满。

状态还独立于团队和 Skype for business 之间使用此升级方法。 这意味着其他用户可能会看到用户 A 的不同状态，具体取决于其使用的客户端。 有关详细信息，请参阅[联机状态](upgrade-to-Teams-on-prem-overview.md#presence)。

- 其他用户在使用团队时，将根据用户 A 的团队活动查看状态。
- 使用 Skype for Business 时，其他用户将根据用户 A 在 Skype for Business 中的活动查看状态。

准备好将用户升级到 TeamsOnly 模式后，您可以单独升级用户，也可以使用租户范围内的策略<sup>3</sup>一次性升级整个租户。 用户升级到 TeamsOnly 模式后，他们将收到团队中的所有传入聊天和通话。

但是，在孤岛模式下未升级的收件人可能会继续接收来自其 Skype for Business 或团队客户的 TeamsOnly 用户的聊天和呼叫。 对于现有对话，TeamsOnly 用户将答复发件人发起聊天或呼叫的客户。 

对于从 TeamsOnly 用户的观点进行的新对话，聊天或呼叫将始终转到 "孤岛模式用户团队客户端"。 这是因为团队客户为团队到团队和团队到 Skype for business 通信（即使是对于同一用户）维护单独的对话线程。 若要了解详细信息，请参阅[团队对话-互操作与本机线程](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads)。

下表总结了孤岛模式和 TeamsOnly 模式的团队体验：

| 团队体验 | 在 "孤岛" 模式下 | 在 TeamsOnly 模式下 |
|:------------------ | :------------------- | :------------------ |
| 传入聊天和通话接收时间：|  团队或 Skype for business | Teams |
| 在以下情况中接收 PSTN 呼叫： | Skype for Business <br>（在孤岛模式下不支持使用团队中的 PSTN 功能。）     | Teams |   
 |状态    | Skype for business 和团队中的状态是独立的。 对于同一孤岛用户，用户可能会看到不同的状态，具体取决于他们使用的客户端。 | 状态仅基于用户在团队中的活动。 所有其他用户，无论他们使用哪种客户端，都可以查看该状态。 | 
 | 会议计划    | 用户可以在团队或 Skype for Business 中安排会议。 默认情况下，他们将在 Outlook 中看到两个外接程序。 你可以设置团队会议策略来控制用户是否只能使用团队会议加载项或同时使用团队会议外接程序和 Skype for business 会议加载项（即将**推出**）。 若要了解详细信息，请参阅[为用户在 "孤岛" 模式下设置会议提供商](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)。 |     用户仅在团队中安排会议。 Outlook 中仅提供团队外接程序。 | 

下表总结了使用重叠的功能方法将组织迁移到团队的优点和缺点。

| 专业人士     |       各有利弊 |
| :------------------ | :---------------- |
| 允许在组织内进行快速采纳。| 由于存在两个具有类似功能但不同用户界面的客户端，导致最终用户混淆的可能性。 而且，他们无法控制传入聊天/呼叫在哪个客户端。 |
| 允许用户在仍然拥有 Skype for business 的完全访问权限的情况下了解和熟悉团队。 | 由于未在用户运行两个客户端时丢失的消息，导致最终用户不满的可能性。|
| 在团队中开始的最少管理工作。 | 如果用户和他们经常与之通信的用户与不在使用团队的用户和他们进行通信的用户以及它们之间的通信，则 "使用孤岛" 模式会很难。|
|使用户能够利用功能增强 Skype for Business 中不可用的团队协作。| 在本地和团队使用 Skype for Business 的用户将无法与使用 Skype for business 的其他用户进行通信，但没有团队。  |

<sup>2</sup>即使用户在 Skype for Business 服务器内部托管，也是如此。 无论用户是在本地还是在网上托管，都将启用 Skype for Business Online 许可证，因为当前需要完整的团队功能。

<sup>3</sup>请注意，仅当向单个用户应用 TeamsUpgradePolicy 时，才会触发将 Skype for Business 会议迁移到团队会议，而不是在每租户基础上进行。 有关详细信息，请参阅[会议迁移](upgrade-to-Teams-on-prem-overview.md#meeting-migration)。

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>"选择功能" 方法（使用 Skype for Business 模式）

某些组织可能更希望向最终用户提供其组织从 Skype for Business 转换到团队的更可预测的体验。 在此模型中，IT 管理员使用 TeamsUpgradePolicy 中的 Skype for Business 模式之一，显式指定在迁移到 TeamsOnly 模式之前在 Skype for business 中保留的功能。 当他们准备将选定的功能移动到 TeamsOnly 模式时，管理员会将这些用户的模式更新为 TeamsOnly。 在此过渡期间：

- 管理员拥有为用户启用某些团队功能的选项，同时在用户迁移到 TeamsOnly 体验之前在 Skype for business 中保持聊天和通话功能。 管理可以启用团队协作功能或团队会议 + 协作功能。
- 无论通信来源于其他用户的团队还是 Skype for business 客户端，仍在使用 Skype for business 的用户接收 Skype for business 客户端的所有传入聊天和呼叫。 此外，对于这些 Skype for Business 用户，将禁用团队客户端中的 "调用和聊天" 功能，以帮助防止最终用户混淆和确保正确的路由和状态。
- TeamsOnly 模式中的用户接收其团队客户端中的所有传入聊天和通话状态由团队提供，无论通信来源：团队、Skype for Business 或任何类型的联盟用户。

与重叠的功能方法不同，使用 Skype for Business 的用户可以与 TeamsOnly 中的用户进行通信。 Skype for Business 用户和团队用户之间的通信称为[互操作性](upgrade-to-Teams-on-prem-overview.md#interoperability)或 "互操作"。 在 Skype for business 中的用户与团队中的另一用户之间进行聊天和通话之间，互操作通信是可行的。 此外，受邀请的用户始终可以加入 Skype for business 或团队会议，但是他们必须使用对应于会议类型的客户端。 有关详细信息，请参阅[会议](upgrade-to-Teams-on-prem-overview.md#meetings)。

对于 "选择功能" 方法中的用户，无论其他用户使用哪种客户端，用户的状态保持一致。 如果用户处于 Skype for business 模式之一，则所有其他用户将在 Skype for Business 中根据该用户的活动看到状态。 同样，如果用户处于 TeamsOnly 模式，则所有其他用户将根据团队中的用户活动查看状态。 有关详细信息，请参阅[状态](upgrade-to-Teams-on-prem-overview.md#presence)。

对于已选择关注 "选择功能" 方法的组织，管理员应将租户范围内的模式从 "岛" 更改为相应的 Skype for Business 共存模式（SfbWithTeamsCollab 或 SfBWithTeamsCollabAndMeetings）。  

来宾用户体验将遵循分配给租户的共存模式。 如果您在租户级别设置了 Skype for Business 模式，来宾将无法进行聊天、呼叫或显示其状态。 要了解详细信息，请阅读 [Teams 中的来宾访问](guest-access.md)。

当模式从 "岛" 更改为 "SfbWithTeamsCollab" 时，从未使用过团队的用户在使用 Skype for Business 的方式上看不到任何区别。 但是，如果用户开始使用团队，则它们仅对功能（如团队 & 频道和文件）公开。 "聊天"、"呼叫和会议计划" 将不会在团队中提供，因为管理员已将 Skype for Business 指定为这些功能的所需客户端。

> [!NOTE]
> 当用户从孤岛更改为 Skype for Business 模式之一时，与用户 a 进行通信的任何其他用户的团队客户都需要知道用户 A 的模式已更改，以便它可以将通信路由到用户 A 的相应客户端。对于已建立了与用户 A 的本机团队间聊天的任何用户，这些用户的团队客户可能需要花费一些时间来了解从孤岛到任何 Skype for Business 模式的模式更改。 管理员准备就绪后，他们可以通过将用户模式更新到 TeamsOnly，将给定用户的聊天、通话和会议计划一次性转移到所有团队。

或者，管理员可以先将会议计划转移到团队，同时使用 SfBWithTeamsCollabAndMeetings 模式在 Skype for Business 中保留聊天和通话功能。 此模式允许组织切换到会议的团队-如果用户尚未准备好转到 TeamsOnly 模式（例如，尚未准备好迁移现有的 PSTN 功能）。 此过渡方案[首先称为会议](meetings-first.md)。


|团队体验  |在 SfBWithTeamsCollab 模式下 |在 SfBWithTeamsCollabAndMeetings 模式下 |在 TeamsOnly 模式下  |
|---------|---------|---------|---------|
|来自组织内用户的传入聊天和 VOIP 呼叫在以下情况中收到：     | Skype for Business        | Skype for Business       | Teams        |
|在以下情况中接收 PSTN 呼叫：     | Skype for Business        |Skype for Business         | Teams        |
|状态     | Skype for Business        |Skype for Business         | Teams        |
|会议计划     | Skype for Business         | Teams        | Teams        |


下表总结了使用 Skype for Business 模式的优点和缺点作为 TeamsOnly 模式的过渡步骤。

| 专业人士     |       各有利弊 |
| :------------------ | :---------------- |
| 最终用户的可预测路由。 根据管理员选择，所有通话和聊天均可在 Skype for business 或团队（但不是两者）中进行。|互操作对话缺少对格式文本、文件共享和屏幕共享的支持。 这可以通过利用 "立即开会" 功能启动会议。 |
|由于给定的功能仅在一个客户端中可用，因此可能会降低最终用户的混乱。 | 对于在 Skype for Business 中执行的常见活动（如聊天和呼叫提前升级到 TeamsOnly），用户无法访问团队。|
|管理员在从 Skype for Business 切换到团队时，对用户可用的一组功能进行了更多的控制。 | |
| 允许组织在会议中使用团队，即使尚未准备好移动到 TeamsOnly 模式。||
|由其他人查看的指定用户的状态是相同的，无论他们使用哪种客户端。||

## <a name="summary-of-upgrade-methods"></a>升级方法摘要
下表总结了升级方法：


|重叠的功能（使用孤岛模式）  |所选功能（使用 Skype for Business 模式）  |
|---------|---------|
|在升级到 TeamsOnly 之前，用户必须同时运行这两个客户端，因为传入聊天和通话可能会在客户端中居住。     | 聊天和呼叫仅在一台客户端中根据收件人的模式呼叫。 未升级的用户可以同时运行两个客户端，但不存在任何功能重叠（呼叫和聊天在团队中不可用）。         |
|允许管理员在多个 Skype for Business 和团队中为最终用户以及团队中的新功能（团队和频道）引入重叠的功能（聊天、会议、VOIP 呼叫）。     | 允许管理员向最终用户（团队和频道）引入选择团队的功能，而不提供在 Skype for Business 中也存在的相同功能。        |
|当两个用户都处于 "孤岛" 模式时，Skype for Business 和团队之间的互操作不存在。      |Skype for business 和团队用户之间的通信需要互操作。         |

> [!NOTE]
> 如果无法关注将 Skype for Business 服务器用户迁移到团队所支持的方法，则可以通过删除 Active Directory 中的 Skype for business 服务器和所有相关用户属性来将用户切换到团队。 一旦用户 Azure Active Directory 属性已清除 Skype for Business 服务器属性，并且 DNS 记录已重新指向 Office 365，则可以在 Office 365 中向用户授予许可证并将其升级到团队。 

> [!IMPORTANT]
> 通过转换迁移，联系人数据和会议数据将不会从本地环境迁移到 Microsoft 团队。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul> 哪些升级旅程适用于组织的业务需求？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>后续步骤</td><td><ul> 确定你的当前部署模型、使用案例方案以及你的组织的关键注意事项将通知迁移到最适合你的组织的团队。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul> 哪种升级方案适用于您的组织？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul> 根据消息、会议和通话业务要求，确定组织的升级旅程的日程表。<br><br> 确定完成升级旅行所需的额外工作。<br><br></ul></td></tr>
</table>

为你的组织选择最佳升级旅行后，请[向团队执行升级](https://aka.ms/SkypeToTeams-Upgrade)。
