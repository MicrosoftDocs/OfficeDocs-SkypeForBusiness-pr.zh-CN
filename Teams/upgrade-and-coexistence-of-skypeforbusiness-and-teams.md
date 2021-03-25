---
title: 选择从 Skype for Business 到 Microsoft Teams 的升级旅程
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: 有关 Skype for Business 和 Microsoft Teams 共存选项的详细信息，以及 Teams 可能的升级过程（示例方案）。
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
ms.openlocfilehash: 680bfad9090899ecce1f6e2be7bd9a0a25f5099a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112168"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>选择从 Skype for Business 到 Teams 的升级旅程

![升级过程图，强调"项目定义"阶段](media/upgrade-banner-project-definition.png "升级过程的各个阶段，重点是项目定义阶段")

本文是升级历程中“项目定义”阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解 Skype for Business 和 Teams 的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

作为现有 Skype for Business 客户，你向 Teams 的完整转换可能需要一些时间。 但是，现在，你可以让用户将 Teams 与 Skype for Business 一起使用，从而开始意识到 Teams 的价值。 鉴于这两个应用之间的功能存在一些重叠，建议查看可用的共存和升级模式，以帮助确定适合组织的路径。 例如，可以选择在两个解决方案上启用所有工作负荷，而无需互操作性。 或者，你可能会决定通过逐渐引入 Teams 功能或针对用户组选择功能来管理用户体验，直到组织准备好将所有人升级到 Teams。 使用试点的结果来帮助评估组织正确的升级过程。

> [!IMPORTANT]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大程度地实现权益并确保组织有适当的时间来实施升级，我们鼓励你立即开始 Microsoft Teams 之旅。

本文概述了可用于管理 Skype for Business 和 Teams 中可供用户使用的各种模式。 与任何部署一样，我们强烈建议在将组织[](pilot-essentials.md)升级到 Teams 之前，先与选定的一组用户试点计划。 请记住，引入新技术可能会给用户造成干扰。 在实施此处概述的任何模式之前，请花些时间评估用户准备情况并实施通信和培训计划。

> [!TIP]
> 和我们一起参加实时交互式研讨会，我们将分享指导、最佳做法和资源，旨在启动升级规划和实施。
>
>先加入 [计划升级](./upgrade-workshops-landing-page.yml) 会话才能开始。


## <a name="upgrade-journey-building-blocks"></a>升级旅程构建基块

若要正式准备组织到 Teams 之旅，需要开始规划升级方案，最终让组织完全接受 Teams 作为唯一的通信和协作解决方案。

为了帮助指导你的决策流程，请熟悉与从 Skype for Business 升级到 Teams 相关的各种模式、概念和术语。 有关详细信息，请参阅 [Microsoft Teams 和 Skype for Business 共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

> [!NOTE]
> 还需要考虑语音迁移方案。 电话系统是 Microsoft 的技术，用于启用 Microsoft 365 或 Office 365 云中的呼叫控制和专用交换机 (PBX) 功能。 若要将电话系统连接到 PSTN (电话交换) 以便用户可以在世界各地进行电话呼叫，你可以根据业务需求选择选项。 有关电话系统和 PSTN 连接选项的详细信息，请参阅 [语音 - 电话系统和 PSTN 连接](cloud-voice-landing-page.md)。

已迁移到 Teams 的用户不再使用 Skype for Business 客户端，除非加入在 Skype for Business 中托管的会议。 无论发送方是使用 Teams 还是 Skype for Business，所有传入的聊天和呼叫都会进入用户的 Teams 客户端。 升级后的用户组织的任何新会议都将安排为 Teams 会议。 如果用户尝试使用 Skype for Business 客户端，则阻止发起聊天和<sup>通话 1。</sup> 但是，用户可以 (，) 仍然使用 Skype for Business 客户端加入受邀加入的会议。

管理员使用模式 的概念（TeamsUpgradePolicy 的一个属性）管理其到[Teams 的转换](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)。 [](migration-interop-guidance-for-teams-with-skype.md) 如上所述迁移到 Teams 的用户位于"TeamsOnly"模式。 对于要迁移到 Teams 的组织，最终目标是将所有用户移到 TeamsOnly 模式。

有两种方法使用 Skype for Business 将现有组织 (联机或本地) Teams：

- **使用** 群岛模式 (的重叠功能方法) ：现有 Skype for Business 组织的用户被引入 Teams，以便他们可以在过渡阶段同时使用这两个客户端。 在此期间，大多数（但并非所有）Teams 功能可供他们使用。 此配置的模式称为"群岛"，这是任何使用 Skype for Business 的现有组织的默认模式。 组织准备就绪后，管理员会将用户移到 TeamsOnly 模式。

- 选择 **使用** 一个或多个 Skype for Business 模式 (的功能方法) ：管理员管理从 (Skype for Business 到 Teams) 的聊天、呼叫和会议计划功能的转换（适用于其组织的用户）。 其中每个功能在 Skype for Business 或 Teams 中均可用，但不能同时在两者中使用。 管理员使用 TeamsUpgradePolicy 来控制何时将此功能转移到其用户的 Teams。 尚未进入 TeamsOnly 模式的用户继续使用 Skype for Business 进行聊天和通话，这两组用户可以通过互操作功能进行通信。 管理员通过逐渐将更多用户迁移到 TeamsOnly 模式来管理转换。

<sup>1</sup> 2017 之前交付的旧版 Skype for Business 客户端不履行 TeamsUpgradePolicy。 确保使用的是 Office 频道中提供的最新 Skype for Business 客户端。

了解并选择升级方法后，可以了解用于管理组织升级到 [Teams 的工具](upgrade-to-teams-on-prem-tools.md)。

下面是可帮助确定组织适当路径的关键因素。

## <a name="overlapping-capabilities-method-using-islands-mode"></a>使用群岛模式 (重叠功能方法) 

借助重叠功能方法，用户可以将 Teams 和 Skype for Business 客户端用于聊天、VoIP 呼叫和会议。 在此方法中，Teams 中的聊天和 VOIP 呼叫侧重于组织内部，而 Skype for Business 支持与外部组织聊天和 VOIP/PSTN (（如果) ）。 这两种产品都可以安排和参加会议。

使用重叠功能方法时，Skype for Business 和 Teams 的通信流量将保持单独的 (即使对于同一用户) ，对于同一组织内部的用户 (永远不会相互通信) 。 用户体验基于收件人的配置。 例如，假设收件人用户 A 在群岛模式下：

- 从另一用户的 Skype for Business 客户端发起的通信将始终位于用户 A 的 Skype for Business 客户端中。

- 来自同一组织中用户的 Teams 客户端发起的 *通信* 将始终位于用户 A 的 Teams 客户端中。

- 从外部组织的用户从 Teams 客户端发起的 *通信* 将始终位于用户 A 的 Skype for Business 客户端中。

如果已向用户分配了 Microsoft 365 或 Office 365 许可证，则这是组织的默认升级体验。 分配 Microsoft 365 或 Office 365 许可证时，默认情况下会同时分配 Teams 和 Skype for Business Online 许可证。<sup>2</sup>

若要有效地使用此方法，所有用户必须同时运行这两个客户端。 从组织内部传入的聊天和呼叫到以岛屿模式的用户可以进入 Skype for Business 或 Teams 客户端，这不由接收人控制。 这取决于发送方用来发起通信的客户端。 如果发送方和接收人位于不同的组织中，则以岛屿模式向用户传入呼叫和聊天始终位于 Skype for Business 客户端中。

例如，如果群岛模式收件人登录了 Skype for Business，但没有登录到 Teams，而某人从 Teams 发送了消息，则岛屿模式收件人不会看到消息 (但他们最终会收到一封电子邮件，指出他们在 Teams) 中错过一条消息。 同样，如果用户在运行 Teams，但不运行 Skype for Business，并且有人从 Skype for Business 收到消息，用户将看不到该聊天。 上述每种情况的行为与调用类似。 如果用户不同时运行这两个客户端，则很容易导致沮丧。

使用此升级方法时，状态还可以在 Teams 和 Skype for Business 之间独立运行。 这意味着其他用户可能会看到用户 A 的不同状态，具体取决于他们使用的客户端。 有关详细信息， [请参阅状态](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)。

- 其他用户在使用 Teams 时，将基于 Teams 中的用户 A 活动查看状态。

- 其他用户在使用 Skype for Business 时，将看到基于用户 A 在 Skype for Business 中的活动状态。

准备好将用户升级到 TeamsOnly 模式后，可以单独升级用户，或者可以使用租户范围策略<sup>3</sup>一次升级整个租户。 将用户升级到 TeamsOnly 模式后，他们会收到 Teams 中所有传入的聊天和呼叫。  (请注意，将 Skype for Business 会议迁移到 Teams 会议仅在将 TeamsUpgradePolicy 应用于单个用户时触发，而不是基于每个租户。 有关详细信息 [，请参阅](upgrade-to-teams-on-prem-tools.md#meeting-migration) 会议迁移) 

但是，在群岛模式下未升级的收件人可能会继续在 Skype for Business 或 Teams 客户端中接收 TeamsOnly 用户的聊天和呼叫。 对于现有对话，TeamsOnly 用户将回复发件人发起聊天或呼叫的客户端。 

对于 TeamsOnly 用户的新对话，聊天或通话将始终转到群岛模式用户 Teams 客户端。 这是因为 Teams 客户端为 Teams 到 Teams 和 Teams 到 Skype for Business 通信维护单独的会话线程，即使对于同一用户。 有关详细信息，请参阅 [Teams 对话 - 互操作与本机线程](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)。

下表总结了岛屿模式和 TeamsOnly 模式的 Teams 体验：

| Teams 体验 | 在群岛模式下 | 在 TeamsOnly 模式下 |
|:------------------ | :------------------- | :------------------ |
| 接收的传入聊天和呼叫：|  Teams 或 Skype for Business | Teams |
| PSTN 呼叫接收时间： | Skype for Business <br> (在 Teams 中使用 PSTN 功能在群岛模式下不受支持。)      | Teams |   
 |状态    | Skype for Business 和 Teams 中的状态是独立的。 用户可能会看到同一个群岛用户的不同状态，具体取决于他们使用的客户端。 | 状态仅基于用户在 Teams 中的活动。 所有其他用户（无论他们使用哪个客户端）都能看到该状态。 | 
 | 会议安排    | 用户可以在 Teams 或 Skype for Business 中安排会议。 默认情况下，他们将在 Outlook 中同时看到这两个加载项。 你可以设置 Teams 会议策略来控制用户是只能使用 Teams 会议加载项，还是同时使用 Teams 会议加载项和 Skype for Business 会议加载项。若要了解有关详细信息，请参阅 [在群岛模式下为用户设置会议提供程序](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)。 |     用户仅在 Teams 中安排会议。 Outlook 中仅提供 Teams 加载项。 | 

下表总结了使用重叠功能方法将组织迁移到 Teams 的优缺点。

| 专业人士     |       Cons |
| :------------------ | :---------------- |
| 允许在组织中快速采用。| 最终用户可能感到困惑，因为有两个客户端具有类似的功能，但用户界面不同。 此外，他们无法控制传入聊天/呼叫进入的客户端。 |
| 允许用户学习和熟悉 Teams，同时仍具有对 Skype for Business 的完全访问权限。 | 如果用户未同时运行这两个客户端，则最终用户可能会因为错过的消息而不满意。|
| 在 Teams 中入门的管理工作量最小。 | 如果用户和经常通信的用户未主动使用 Teams，则"退出群岛"模式并转移到 TeamsOnly 模式可能很有难度。 例如，将一部分用户升级到 TeamsOnly 模式后，这些用户只会在 Teams 中发送。 对于以岛屿模式显示的其他人口，这些消息将始终位于 Teams 中。 但如果其中一些用户未运行 Teams，他们将这些消息视为错过。|
|使用户能够利用 Skype for Business 中不可用的功能来增强团队合作。| 在本地使用 Skype for Business 和 Teams 的用户将无法从 Teams 与在本地使用 Skype for Business 但没有 Teams 的另一个用户进行通信。  |
|  | 使用 Teams 时，在 Skype for Business Server 中拥有本地帐户的用户没有互操作或联合支持。  如果你混合使用群岛用户（一些用户位于 Skype for Business Online 中，一些位于本地 Skype for Business 中）可能会引起混淆。   |

<sup>2</sup> 即使用户位于 Skype for Business Server 本地，也是如此。 无论用户是在本地还是在线，都保持启用 Skype for Business Online 许可证，因为当前需要它才能使用完整的 Teams 功能。

<sup>3</sup> 请注意，将 Skype for Business 会议迁移到 Teams 会议仅在将 TeamsUpgradePolicy 应用于单个用户时触发，而不是基于每个租户。 有关详细信息 [，请参阅会议](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) 迁移。

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>使用 Skype for Business (选择功能方法) 

某些组织可能希望随着其组织从 Skype for Business 过渡到 Teams，为最终用户提供更加可预测的体验。 在此模型中，IT 管理员使用 TeamsUpgradePolicy 中的 Skype for Business 模式之一显式指定在迁移到 TeamsOnly 模式之前，哪些功能保留在 Skype for Business 中。 当他们准备好将所选功能转移到 TeamsOnly 模式时，管理员将这些用户的模式更新为 TeamsOnly。 在此转换期间：

- 在用户转移到 TeamsOnly 体验之前，管理员提供选项来为用户启用某些 Teams 功能，同时在 Skype for Business 中保留聊天和通话功能。 管理可以启用 Teams 协作功能或 Teams 会议 + 协作功能。

- 仍在使用 Skype for Business 的用户在 Skype for Business 客户端中接收所有传入的聊天和呼叫，无论通信来自其他用户的 Teams 还是 Skype for Business 客户端。 此外，对于这些 Skype for Business 用户，Teams 客户端中的呼叫和聊天功能将被禁用，以帮助防止最终用户混淆并确保正确的路由和状态。

- TeamsOnly 模式下的用户在 Teams 客户端中接收所有传入的聊天和呼叫，并且状态由 Teams 提供，无论通信源自何处：Teams、Skype for Business 或任何联合用户。

与使用 Islands (方法) 功能不同，在 select capabilities 方法中，使用 Skype for Business 的用户可以与 TeamsOnly 中的用户通信。 Skype for Business 用户与 Teams 用户之间的通信称为 [互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability) 或"互操作"。 Skype for Business 中的用户与 Teams 中的另一个用户之间的聊天和通话可以一对一进行互操作通信。 此外，受邀用户始终可以加入 Skype for Business 或 Teams 会议，但是，他们必须使用与会议类型对应的客户端。 有关详细信息，请参阅 [会议](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings)。

对于采用选择功能转换方法的用户，无论其他用户使用哪个客户端，用户状态都是一致的。 如果用户位于 Skype for Business 模式之一，则所有其他用户都可以看到基于该用户在 Skype for Business 中的活动状态。 同样，如果用户在 TeamsOnly 模式下，则所有其他用户都可以看到基于该用户在 Teams 中的活动的存在状态。 有关详细信息 [，请参阅状态](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)。

对于尚未开始使用 Teams 的组织，管理员应将租户范围模式从"群岛"更改为"SfbWithTeamsCollab"。  (对于已使用某些 Teams 的组织，管理员应"父"用户已在 Teams 中活动，以确保此更改不适用于他们。 有关详细信息，请参阅 [已在群岛模式下](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)使用 Teams 的组织选择功能方法。)  

来宾用户体验将遵循分配给租户的共存模式。 如果你在租户级别设置了 Skype for Business 模式，则来宾无法聊天、呼叫或显示其状态。 要了解详细信息，请阅读 [Teams 中的来宾访问](guest-access.md)。

当模式从 Islands 更改到 SfbWithTeamsCollab 时，从未使用过 Teams 的用户在 Skype for Business 的使用方式上没有任何差别。 但是，如果用户开始使用 Teams，则只会向 Teams 和频道和文件&功能。 聊天、通话和会议安排在 Teams 中不可用，因为管理员 (目前) Skype for Business 作为这些功能所需的客户端。

> [!NOTE]
> 当用户 A 从群岛更改为 Skype for Business 模式之一时，与用户 A 通信的任何其他用户的 Teams 客户端需要知道用户 A 的模式已更改，以便它可以将通信路由到用户 A 的适当客户端。对于已与用户 A 建立本机 Teams 到 Teams 聊天的任何用户，最多可能需要 36 小时，这些其他用户的 Teams 客户端才能知道模式从群岛更改为任何 Skype for Business 模式。 相比之下，其他客户端在 2 小时内发现现有用户对 TeamsOnly 模式的更改。<br>
> 管理员准备就绪后，可以通过将用户的模式更新为 TeamsOnly，将给定用户的聊天、通话和会议计划一次转移到 Teams。

或者，管理员可以先将会议安排转移到 Teams，同时使用 SfBWithTeamsCollabAndMeetings 模式在 Skype for Business 中退出聊天和呼叫功能。 此模式允许组织转换到 Teams 进行会议 - 如果用户尚未准备好迁移到 TeamsOnly 模式 (例如，如果你尚未准备好迁移现有 PSTN 功能) 。 这种过渡方案称为"会议[第一"。](meetings-first.md)


|Teams 体验  |在 SfBWithTeamsCollab 模式下 |在 SfBWithTeamsCollabAndMeetings 模式下 |在 TeamsOnly 模式下  |
|---------|---------|---------|---------|
|从组织中收到的用户的传入聊天和 VOIP 呼叫包括：     | Skype for Business        | Skype for Business       | Teams        |
|PSTN 呼叫接收时间：     | Skype for Business        |Skype for Business         | Teams        |
|状态     | Skype for Business        |Skype for Business         | Teams        |
|会议安排     | Skype for Business         | Teams        | Teams        |


下表总结了使用 Skype for Business 模式作为 TeamsOnly 模式的过渡步骤的优缺点。

| 专业人士     |       Cons |
| :------------------ | :---------------- |
| 最终用户的可预测路由。 所有通话和聊天均位于 Skype for Business 或 Teams (，但不能) 管理员选择。|互操作对话不支持格式文本、文件共享和屏幕共享。 这可围绕利用"立即开会"功能启动会议进行。 |
|可以减少最终用户的混淆，因为给定的功能仅在一个客户端中可用。 | 在将用户升级到 TeamsOnly 之前，他们无法访问 Teams，无法访问 Skype for Business 中执行的常见活动，例如聊天和通话。 这意味着，没有并排功能。|
|从 Skype for Business 转换到 Teams 时，管理员可控制可供用户使用的功能集。 此控件包括以增量方式引入 Teams 功能的功能。 | |
| 允许组织使用 Teams 参加会议，即使它尚未准备好完全移动到 TeamsOnly 模式。||
|其他人查看的给定用户的存在是相同的，无论他们使用哪个客户端。||

## <a name="summary-of-upgrade-methods"></a>升级方法摘要
下表汇总了升级方法：


|使用岛屿模式 (重叠)   |使用 Skype for Business (所选功能)   |
|---------|---------|
|升级到 TeamsOnly 之前，用户必须同时运行这两个客户端，因为传入的聊天和通话可能进入任一客户端。     | 聊天和通话仅基于收件人的模式进入一个客户端。 未升级的用户可能同时运行这两个客户端，但与通话和聊天 (在 Teams) 。 管理员还可以控制用户是否在 Teams 或 Skype for Business 中安排会议。         |
|允许管理员在 Skype for Business 和 Teams 中为最终用户引入重叠功能 (聊天、会议、VOIP 呼叫)  (，从而允许并行功能) ，以及 Teams 中的新功能 (Teams 和频道) 。     | 允许管理员向 Teams 和频道 (最终用户) Teams 选择功能，而不提供 Skype for Business 中也存在的相同功能。        |
|当两个用户都位于群岛模式下时，Skype for Business 和 Teams 之间不存在互操作。 将某些用户升级到 TeamsOnly 互操作后，这些用户与仍处于群岛模式的其他用户之间可能会发生互操作对话。 但是，群岛用户可以选择使用 Teams 并避免互操作对话。      |Skype for Business 和 Teams 用户之间的通信需要互操作。         |

> [!NOTE]
> 如果无法按照受支持的方法将 Skype for Business Server 用户迁移到 Teams，则有可能通过删除 Active Directory 中的 Skype for Business Server 和所有用户属性，将用户转移到 Teams。 清除用户 Azure Active Directory 属性后，Skype for Business Server 属性和 DNS 记录重新指向 Microsoft 365 或 Office 365，然后可以授权 Microsoft 365 或 Office 365 中的用户，并升级到 Teams。 

> [!IMPORTANT]
> 通过直接转换迁移，联系人数据和会议数据不会从本地环境迁移到 Microsoft Teams。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul> 哪种升级过程适合组织的业务需求？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>后续步骤</td><td><ul> 确定当前部署模型、用例方案和组织的关键注意事项将告知最适合组织的 Teams 之旅。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul> 哪种升级方案适用于组织？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul> 根据消息传递、会议和呼叫业务需求确定组织的升级过程日程表。<br><br> 确定完成升级旅程所需的额外工作。<br><br></ul></td></tr>
</table>

为组织选择最佳升级旅程后， [请执行到 Teams 的升级](./upgrade-to-teams.md)。

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)