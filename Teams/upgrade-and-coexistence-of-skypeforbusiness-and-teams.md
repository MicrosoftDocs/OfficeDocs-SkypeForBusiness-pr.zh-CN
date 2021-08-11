---
title: 选择从Skype for Business到Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: 有关Skype for Business和Microsoft Teams选项的详细信息，以及可能的升级过程Teams示例方案。
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
ms.openlocfilehash: e9cf6d911f77f47ad2631a6560afd5be8df171e32ee3e0d3907eb59f3ba01146
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300828"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>选择从Skype for Business到Teams

![升级过程图，强调"项目定义"阶段](media/upgrade-banner-project-definition.png "升级过程的各个阶段，重点是项目定义阶段")

本文是升级历程中“项目定义”阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解两者共存Skype for Business互操作性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

作为现有的Skype for Business客户，完成到 Teams可能需要一些时间。 但是，通过让用户能够将 Teams 与 Skype for Business 一起，可以立即开始实现 Teams 的值。 鉴于这两个应用之间的功能存在一些重叠，建议查看可用的共存和升级模式，以帮助确定适合组织的路径。 例如，可以选择在两个解决方案上启用所有工作负荷，而无需互操作性。 或者，您可以决定通过逐渐引入 Teams 功能或针对用户组选择功能来管理用户体验，直到您的组织准备好将所有人升级到 Teams。 使用试点的结果来帮助评估组织正确的升级过程。

> [!IMPORTANT]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大程度地实现权益并确保组织有适当的时间来实施升级，我们鼓励你立即开始Microsoft Teams之旅。

本文概述了各种模式，这些模式可用于管理用户Skype for Business Teams哪些形式。 与任何部署一样，我们强烈建议在将组织[](pilot-essentials.md)升级到新计划之前，先与选定的一组用户Teams。 请记住，引入新技术可能会给用户造成干扰。 在实施此处概述的任何模式之前，请花些时间评估用户准备情况并实施通信和培训计划。

> [!TIP]
> 和我们一起参加实时交互式研讨会，我们将分享指导、最佳做法和资源，旨在启动升级规划和实施。
>
>先加入 [计划升级](./upgrade-workshops-landing-page.yml) 会话才能开始。


## <a name="upgrade-journey-building-blocks"></a>升级旅程构建基块

若要正式准备组织Teams，需要开始规划升级方案，最终让组织完全接受 Teams 作为唯一的通信和协作解决方案。

若要帮助指导您的决策流程，请熟悉与从云升级到 Skype for Business Teams 相关的各种模式、概念和术语。 有关详细信息，请参阅[Microsoft Teams Skype for Business和互操作性。](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

> [!NOTE]
> 还需要考虑语音迁移方案。 电话系统是 Microsoft 在云或云中启用呼叫控制和专用分支Exchange (PBX) 功能Microsoft 365 Office 365技术。 若要电话系统公用电话交换网 (PSTN) 以便用户可以在世界各地进行电话呼叫，你可以根据业务需求选择选项。 有关语音和 PSTN 电话系统选项的详细信息，请参阅[语音 - 电话系统 和 PSTN 连接](cloud-voice-landing-page.md)。

已迁移到 Teams的用户不再使用 Skype for Business 客户端，除非加入在 Skype for Business 中托管的会议。 所有传入聊天和呼叫都进入用户的Teams客户端，无论发送方是使用Teams还是Skype for Business。 升级后的用户组织的任何新会议都将安排为Teams会议。 如果用户尝试使用客户端Skype for Business，则阻止发起聊天和通话<sup>1。</sup> 但是，用户可以 (，) 仍然使用Skype for Business客户端加入受邀加入的会议。

管理员使用模式Teams管理到游戏的[转换，模式](migration-interop-guidance-for-teams-with-skype.md)是[TeamsUpgradePolicy 的一个属性](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)。 如上所述迁移到 Teams的用户位于"TeamsOnly"模式下。 对于要迁移到 Teams 的组织，最终目标是将所有用户移动到 TeamsOnly 模式。

有两种方法可以迁移现有组织，无论Skype for Business (联机还是本地) 组织Teams：

- 使用 (模式) 的重叠功能方法：现有 Skype for Business 组织的用户被引入 Teams，以便他们可以在过渡阶段同时使用这两个客户端。 在此期间，大多数（但并非所有）Teams可用。 此配置的模式称为"群岛"，这是任何具有此配置的现有组织的默认Skype for Business。 组织准备就绪后，管理员会将用户移到 TeamsOnly 模式。

- 选择 (**使用** 一个或多个 Skype for Business 模式) 的功能方法) ：管理员管理 (从 Skype for Business 到 Teams) 的聊天、呼叫和会议计划功能转换。 其中每个函数在 Skype for Business 或 Teams 中可用，但不能同时提供。 管理员使用 TeamsUpgradePolicy 来控制何时将此功能转移到Teams用户。 尚未进入 TeamsOnly 模式的用户继续使用 Skype for Business聊天和通话，这两组用户可以通过互操作功能进行通信。 管理员通过逐渐将更多用户迁移到 TeamsOnly 模式来管理转换。

<sup>1</sup> Skype for Business 2017 之前交付的旧版客户端不履行 TeamsUpgradePolicy。 请确保使用频道中Skype for Business的最新客户端Office客户端。

了解并选择升级方法后，可以了解用于管理组织升级到 Teams[的工具](upgrade-to-teams-on-prem-tools.md)。

下面是可帮助确定组织适当路径的关键因素。

## <a name="overlapping-capabilities-method-using-islands-mode"></a>使用群岛模式 (重叠功能方法) 

使用重叠功能方法，用户可以将Teams和Skype for Business客户端用于聊天、VoIP 呼叫和会议。 在此方法中，Teams 中的聊天和 VOIP 呼叫侧重于组织内部，而 Skype for Business 则允许与外部组织进行聊天和 VOIP/PSTN (（如果) ）。 这两种产品都可以安排和参加会议。

使用重叠功能方法时，Skype for Business 和 Teams 的通信流量将保持单独的 (即使对于同一用户) ，对于同一组织) 中的用户，这两个不同的客户端也永远不会相互通信 (。 用户体验基于收件人的配置。 例如，假设收件人用户 A 在群岛模式下：

- 从另一用户的客户端发起的Skype for Business始终位于用户 A 的客户端Skype for Business客户端。

- 从同一Teams用户启动 *的通信始终位于* 用户 A 的客户端Teams客户端。

- 从外部Teams用户从客户端发起的 *通信将始终* 位于用户 A 的客户端Skype for Business客户端。

如果为用户分配了Microsoft 365或Office 365许可证，则这是组织的默认升级体验。 当您分配 Microsoft 365 或 Office 365 许可证时，Teams Skype for Business Online 许可证均默认分配。<sup>2</sup>

若要有效地使用此方法，所有用户必须同时运行这两个客户端。 从组织内部传入的聊天和呼叫以群岛模式向用户进行，可以登陆 Skype for Business 或 Teams 客户端- 这不由接收人控制。 这取决于发送方用来发起通信的客户端。 如果发送方和接收人位于不同的组织中，则以群岛模式向用户传入呼叫和聊天始终位于Skype for Business客户端。

例如，如果群岛模式收件人登录到 Skype for Business 但不登录 Teams，而某人从 Teams 发来的邮件，则岛屿模式收件人不会看到邮件 (但他们最终会收到一封电子邮件，指出他们在 Teams) 中错过一封邮件。 同样，如果用户在Teams但Skype for Business，以及用户从 Skype for Business 的消息，用户将看不到该聊天。 上述每种情况的行为与调用类似。 如果用户不同时运行这两个客户端，则很容易导致沮丧。

使用此升级方法时，Teams Skype for Business状态也独立运行。 这意味着其他用户可能会看到用户 A 的不同状态，具体取决于他们使用的客户端。 有关详细信息， [请参阅状态](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)。

- 其他用户在使用 Teams 时，将看到基于用户 A 在 Teams 中的状态。

- 其他用户在使用 Skype for Business 时，将看到基于用户 A 在 Skype for Business 中的活动。

准备好将用户升级到 TeamsOnly 模式后，可以单独升级用户，或者可以使用租户范围策略<sup>3</sup>一次升级整个租户。 将用户升级到 TeamsOnly 模式后，他们会收到所有传入聊天和呼叫Teams。  (请注意，将 Skype for Business 会议迁移到 Teams 仅在将 TeamsUpgradePolicy 应用于单个用户时触发，而不是基于每个租户。 有关详细信息 [，请参阅](upgrade-to-teams-on-prem-tools.md#meeting-migration) 会议迁移) 

但是，在群岛模式下未升级的收件人可能会继续接收 TeamsOnly 用户的聊天和呼叫，这些聊天和呼叫来自其Skype for Business或Teams客户端。 对于现有对话，TeamsOnly 用户将回复发件人发起聊天或呼叫的客户端。 

从 TeamsOnly 用户的角度来看，对于新对话，聊天或通话将始终转到"群岛"模式用户Teams客户端。 这是因为，Teams客户端为Teams到Teams通信Teams会话Skype for Business会话线程，即使对于同一用户。 若要了解有关详细信息，请参阅Teams[对话 - 互操作与本机线程。](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)

下表汇总了Teams和 TeamsOnly 模式的体验：

| Teams体验 | 在群岛模式下 | 在 TeamsOnly 模式下 |
|:------------------ | :------------------- | :------------------ |
| 接收的传入聊天和呼叫：|  Teams或Skype for Business | Teams |
| PSTN 呼叫接收时间： | Skype for Business <br> (在群岛模式下使用 PSTN Teams在群岛模式下不受支持。)      | Teams |   
 |状态    | 在Skype for Business和Teams状态是独立的。 用户可能会看到同一个群岛用户的不同状态，具体取决于他们使用的客户端。 | 状态仅基于用户在 Teams 中的活动。 所有其他用户（无论他们使用哪个客户端）都能看到该状态。 | 
 | 会议安排    | 用户可以在会议或会议Teams Skype for Business。 默认情况下，他们将看到两个加载项都Outlook。 您可以设置 Teams 会议策略，以控制用户是只能使用 Teams 会议加载项，还是同时使用 Teams 会议加载项和 Skype for Business 会议加载项。若要了解有关详细信息，请参阅[在群岛模式下为用户设置会议提供程序](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode)。 |     用户仅在 Teams 中安排会议。 只有Teams加载项才能在 Outlook。 | 

下表汇总了使用重叠功能方法将组织迁移到 Teams。

| 专业人士     |       Cons |
| :------------------ | :---------------- |
| 允许在组织中快速采用。| 最终用户可能感到困惑，因为有两个客户端具有类似的功能，但用户界面不同。 此外，他们无法控制传入聊天/呼叫进入的客户端。 |
| 允许用户了解并熟悉Teams，同时仍可完全访问Skype for Business。 | 如果用户未同时运行这两个客户端，则最终用户可能会因为错过的消息而不满意。|
| 在管理方面投入极少的精力来开始使用Teams。 | 如果用户及其定期通信的用户未主动使用"退出群岛"模式并转移到 TeamsOnly 模式，则可能会Teams。 例如，将一部分用户升级到 TeamsOnly 模式后，这些用户只会在 Teams。 对于以群岛模式显示的其他人口，这些消息将始终位于Teams。 但是，如果其中一些用户未在Teams，他们将这些消息视为错过。|
|使用户能够利用功能来增强团队协作，这些功能在 Skype for Business。| 在本地使用 Skype for Business 和 Teams 的用户无法从 Teams 与在本地使用 Skype for Business 但没有Teams 的用户进行通信。  |
|  | 使用 Teams 时，在 Skype for Business Server 本地帐户的用户没有互操作或联合身份验证支持。  如果你混合使用群岛用户（一些用户位于 Skype for Business Online 中，而一些用户位于本地，Skype for Business可能会造成混淆。   |

<sup>2</sup>即使用户位于本地，也是如此Skype for Business Server。 无论用户是在本地还是联机，请保持启用 Skype for Business Online 许可证，因为当前需要它才能获得完整的Teams功能。

<sup>3</sup>请注意，将 Skype for Business 会议迁移到 Teams 仅在将 TeamsUpgradePolicy 应用于单个用户时触发，而不是基于每个租户。 有关详细信息 [，请参阅会议](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) 迁移。

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>使用模式 (选择Skype for Business方法) 

某些组织可能希望为最终用户提供更可预测的体验，因为组织从Skype for Business转换到Teams。 在此模型中，IT 管理员使用 TeamsUpgradePolicy 中的 Skype for Business 模式之一显式指定在迁移到 TeamsOnly 模式之前哪些功能保留在 Skype for Business 中。 当他们准备好将所选功能转移到 TeamsOnly 模式时，管理员将这些用户的模式更新为 TeamsOnly。 在此转换期间：

- 在用户移动到 TeamsOnly 体验之前，管理员Teams为用户启用某些聊天和通话功能，同时Skype for Business聊天和通话功能。 管理可以启用Teams功能或Teams + 协作功能。

- 仍在Skype for Business的用户在 Skype for Business 客户端中接收所有传入聊天和呼叫，无论通信是源自其他用户的 Teams 还是 Skype for Business 客户端。 此外，对于这些Skype for Business，Teams客户端中的呼叫和聊天功能将被禁用，以帮助防止最终用户混淆并确保正确的路由和状态。

- TeamsOnly 模式下的用户在 Teams 客户端中接收所有传入聊天和呼叫，并且状态由 Teams 提供，无论通信源自何处：Teams、Skype for Business 或任何类型的联合用户。

与 Islands (方法) 功能不同，在 select capabilities 方法中，使用 Skype for Business 的用户可以与 TeamsOnly 中的用户通信。 用户与Skype for Business之间的Teams称为[互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)或"互操作"。 互操作通信可以一对一进行，以在 Skype for Business 中的用户与 Teams 中的用户之间聊天和Teams。 此外，受邀用户始终可以Skype for Business或Teams会议，但是，他们必须使用与会议类型对应的客户端。 有关详细信息，请参阅 [会议](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings)。

对于采用选择功能转换方法的用户，无论其他用户使用哪个客户端，用户状态都是一致的。 如果用户位于以下模式之一Skype for Business，则所有其他用户将基于该用户的活动在 Skype for Business。 同样，如果用户在 TeamsOnly 模式下，则所有其他用户都可以看到基于该用户在 Teams 中的活动。 有关详细信息 [，请参阅状态](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)。

对于尚未开始使用 Teams，管理员应将租户范围模式从 Islands 更改为 SfbWithTeamsCollab。  (对于已具有一些Teams的组织，管理员应"Teams"用户，以确保此更改不适用于他们。 有关详细信息，请参阅已在群岛模式下使用 Teams[的组织选择](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)功能)  

来宾用户体验将遵循分配给租户的共存模式。 如果在租户级别Skype for Business模式，则来宾无法聊天、呼叫或显示其状态。 要了解详细信息，请阅读 [Teams 中的来宾访问](guest-access.md)。

当模式从 Islands 更改到 SfbWithTeamsCollab 时，从未使用过该Teams用户不会看到其使用 Skype for Business。 但是，如果用户开始使用 Teams，则只会向通道和Teams &等功能公开。 聊天、呼叫和会议安排在 Teams 中不可用，因为管理员 () 指定为这些Skype for Business所需的客户端。

> [!NOTE]
> 当用户 A 从群岛更改为 Skype for Business 模式之一时，与用户 A 通信的任何其他用户的 Teams 客户端需要知道用户 A 的模式已更改，以便它可以将通信路由到用户 A 的适当客户端。对于已与用户 A 建立本机 Teams 到 Teams 聊天的任何用户，这些其他用户的 Teams 客户端可能需要 36 小时才能注意到模式从群岛更改为任何 Skype for Business 模式。 相比之下，其他客户端在 2 小时内发现现有用户对 TeamsOnly 模式的更改。<br>
> 管理员准备就绪后，可以将给定用户的聊天、呼叫和会议计划Teams将用户模式更新为 TeamsOnly，一次完成所有操作。

或者，管理员可以先将会议计划转移到 Teams，同时使用 SfBWithTeamsCollabAndMeetings 模式将聊天和Skype for Business保留为 Skype for Business。 此模式允许组织转换到 Teams 会议 - 如果用户尚未准备好迁移到 TeamsOnly 模式 (例如，如果你尚未准备好迁移现有 PSTN 功能) 。 这种过渡方案称为"会议[第一"。](meetings-first.md)


|Teams体验  |在 SfBWithTeamsCollab 模式下 |在 SfBWithTeamsCollabAndMeetings 模式下 |在 TeamsOnly 模式下  |
|---------|---------|---------|---------|
|从组织中收到的用户的传入聊天和 VOIP 呼叫包括：     | Skype for Business        | Skype for Business       | Teams        |
|PSTN 呼叫接收时间：     | Skype for Business        |Skype for Business         | Teams        |
|状态     | Skype for Business        |Skype for Business         | Teams        |
|会议安排     | Skype for Business         | Teams        | Teams        |


下表总结了将游戏模式用作 teamsOnly 模式的过渡Skype for Business的优缺点。

| 专业人士     |       Cons |
| :------------------ | :---------------- |
| 最终用户的可预测路由。 所有通话和聊天都Skype for Business或Teams (，但不能同时) 管理员选择。|互操作对话不支持格式文本、文件共享和屏幕共享。 这可围绕利用"立即开会"功能启动会议进行。 |
|可以减少最终用户的混淆，因为给定的功能仅在一个客户端中可用。 | 在将用户升级到 TeamsOnly 之前，他们无法访问Teams聊天和通话Skype for Business常见活动的访问权限。 这意味着，没有并排功能。|
|管理员在从本地用户转换到 Teams 时，可以控制一组可供Skype for Business的功能。 此控件包括以增量方式引入Teams的功能。 | |
| 允许组织使用 Teams会议，即使它尚未准备好完全移动到 TeamsOnly 模式。||
|其他人查看的给定用户的存在是相同的，无论他们使用哪个客户端。||

## <a name="summary-of-upgrade-methods"></a>升级方法摘要
下表汇总了升级方法：


|使用岛屿模式 (重叠)   |所选功能 (使用Skype for Business模式)   |
|---------|---------|
|升级到 TeamsOnly 之前，用户必须同时运行这两个客户端，因为传入的聊天和通话可能进入任一客户端。     | 聊天和通话仅基于收件人的模式进入一个客户端。 未升级的用户可能同时运行这两个客户端，但与通话 (没有功能重叠，聊天在 Teams) 。 管理员还可以控制用户是安排会议Teams还是Skype for Business。         |
|允许管理员在 Skype for Business 和 Teams 中向最终用户引入重叠功能 (聊天、会议、VOIP 呼叫)  (允许并行功能) ，以及 Teams 中的新功能 (Teams 和频道) 。     | 允许管理员向最终用户和频道Teams用户 (Teams选择) ，而不提供与 Skype for Business 相同的功能。        |
|当两个用户Skype for Business Teams时，两者之间的互操作不存在。 将某些用户升级到 TeamsOnly 互操作后，这些用户与仍处于群岛模式的其他用户之间可能会发生互操作对话。 但是，群岛用户可以选择使用Teams并避免互操作对话。      |用户与用户之间的通信Skype for Business互Teams互操作。         |

> [!NOTE]
> 如果无法按照支持的方法将 Skype for Business Server 用户迁移到 Teams，则有可能在 Active Directory 中删除 Skype for Business Server 和所有用户属性，将用户转换为 Teams。 用户 Azure Active Directory 属性被清除后，Skype for Business Server 属性和 DNS 记录重新指向 Microsoft 365 或 Office 365，然后，可以授权 Microsoft 365 或 Office 365 中的用户，并升级到 Teams。 

> [!IMPORTANT]
> 使用直接转换迁移时，联系人数据和会议数据不会从本地环境迁移到Microsoft Teams。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul> 哪种升级过程适合组织的业务需求？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>后续步骤</td><td><ul> 确定当前的部署模型、用例方案和组织的关键注意事项，将告知Teams最适合组织的部署过程。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul> 哪种升级方案适用于组织？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>下一步</td><td><ul> 根据消息传递、会议和呼叫业务需求确定组织的升级过程日程表。<br><br> 确定完成升级旅程所需的额外工作。<br><br></ul></td></tr>
</table>

为组织选择最佳升级旅程后，[请执行升级到 Teams。](./upgrade-to-teams.md)

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)