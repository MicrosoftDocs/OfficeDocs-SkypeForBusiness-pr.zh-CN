---
title: 了解 Microsoft Teams 和 Skype for Business 的共存和互操作性
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 有关 Skype for Business 和 Microsoft Teams 共存选项的详细信息，以及 Skype for Business 和 Teams 之间由此产生的互操作性。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2a83a0ec3b93f44da5f22e0423ff6199f2ce0c5
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705851"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>了解 Microsoft Teams 和 Skype for Business 的共存和互操作性

![升级旅程关系图，强调项目定义阶段。](media/upgrade-banner-project-definition.png "升级过程的各个阶段，重点是项目定义阶段")

本文是升级历程中“项目定义”阶段的一部分。 在创建赞助联盟和项目团队并确定项目范围、目标和计划后完成。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)

如果你的组织今天使用Skype for Business，并且你开始Skype for Business一起使用 Teams，或者你开始升级到 Teams，请务必了解两个应用程序如何共存、何时以及如何互操作，以及如何从最终升级一直管理用户的迁移Skype for Business到 Teams。

> [!Tip]
> 请观看下面的会话以了解 [共存和互操作性](https://aka.ms/teams-upgrade-coexistence-interop)。
>
> 此外，还可以参加我们的现场互动研讨会，我们将在研讨会上分享指导、最佳实践和资源，以启动升级规划和实施。
>
> 先加入 [计划升级](./upgrade-workshops-landing-page.yml) 会话才能开始。

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Teams 与 Skype for Business 共存概述

自 Skype for Business Online 停用以来，纯在线组织中的所有用户 (即，没有本地部署Skype for Business) 的组织具有 TeamsOnly 共存模式。 TeamsOnly 模式可确保用户具有 Teams 的完整功能。 但是，本地部署Skype for Business Server的组织可能具有仍驻地的用户;这些用户不能是 TeamsOnly。 具有本地Skype for Business Server帐户的用户可能具有 *除 TeamsOnly 以外的* 任何共存模式。 以下部分介绍了在决定将本地 Skype for Business用户升级到 TeamsOnly 之前可用的共存模式，以及每个模式提供的功能。 此外，这些部分还介绍了Skype for Business客户端上的用户与 Teams 客户端上的用户之间发生的互操作性 (互操作) ，以及互操作如何受到所选共存模式的影响。

Teams 提供协作功能、聊天、通话和会议功能。  聊天、通话和会议功能在Skype for Business中历来也可用。 根据你在提供 Teams 时选择的配置，这些功能可能与Skype for Business为给定用户提供的功能重叠。 本地用户的默认共存模式是 Islands。 “岛屿”模式允许用户同时运行 Teams 以及两个客户端中具有类似功能的Skype for Business;即功能重叠。 但是，可以为用户分配其他共存模式，以防止用户的此功能重叠，在这种情况下，Teams 和 Skype for Business 之间的互操作性可用。 例如，如果你有大量Skype for Business Server具有复杂企业语音部署的本地资产，但希望用户尽快享受新式会议，则可能需要将Skype for Business与 Teams 协作和会议模式（也称为[“会议第一”](meetings-first.md)）配合使用。

我们建议查看以下共存模式，以帮助确定哪种路径适合你的组织。

> [!Important]
> Skype for Business Online 停用后，共存模式仍然存在，但是联机用户只能有 TeamsOnly 模式。 不再可以将 TeamsOnly 以外的任何模式分配给联机用户。  与 Skype for Business Online 停用之前的情况一样，可以为本地用户分配除 *TeamsOnly 以外的* 任何模式。


### <a name="teams-only"></a>Teams Only

**仅 Teams** 是唯一适用于纯联机用户的模式。 **仅限 Teams** 的用户过去 (，有时调用 *升级* 的用户) 有权访问 Teams 中的所有功能，并且可以继续与任何其他用户通信 (无论在同一组织还是外部组织) 谁仍然使用Skype for Business (前提是Skype for Business用户不在 **Islands** 模式) 。 **仅 Teams** 用户在 Teams 中接收传入聊天和呼叫，并在 Teams 中安排会议。 他们无法在Skype for Business中发起聊天、通话或安排会议。 

**仅 Teams** 用户可以保留Skype for Business客户端，以加入他们已拥有或将来可能收到的任何Skype for Business会议 (，即来自外部方或可能来自其组织) 中的本地Skype for Business Server用户。 *但是，在 Microsoft 删除给定仅限 Teams 用户的 Skype for Business Online 基础结构后，仅限 Teams 用户只能匿名加入Skype for Business会议。* 2022 年 6 月 30 日之后，将不再使用 Skype for Business Online 基础结构预配新创建的 TeamsOnly 用户。 如果邀请这些用户参加Skype for Business会议，则需要匿名加入。 2022 年 10 月之后，用户从本地迁移到云 (即成为 TeamsOnly) 将不再使用 Skype for Business Online 基础结构进行预配。  如果邀请这些用户参加Skype for Business会议，他们还需要匿名加入。

一旦组织准备好让部分或所有用户使用 Teams 作为他们唯一的通信和协作工具，请将这些用户升级到 **Teams Only** 模式。 如果要从“**并行**”模式升级，我们建议在开始升级过程之前，先让整个组织的 Teams 采用饱和。 这种采用避免了由于“**并行**”模式不提供互操作性而导致的通信中断场景。

当处于 **Teams Only** 模式时，Teams 是 SIP/Tel 协议的默认应用。 用户在 Outlook 中的联系人卡中用于通话或聊天的链接将由 Teams 处理。

有关移动到 **Teams Only** 模式的额外注意事项，请参阅 [Teams Only 模式注意事项](teams-only-mode-considerations.md)。

![Teams 确认消息的屏幕截图。](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "用户升级为 Teams-Only 用户后，Skype for Business 客户端以特殊模式运行")


### <a name="islands-mode"></a>“并行”模式

在 **Islands** 模式下，用户可以将 Teams 与Skype for Business一起作为两个单独的解决方案运行，以提供相似和重叠的功能。 功能包括状态、聊天、通话和会议。 Teams 用户还可以利用新的协作功能，例如团队和频道、访问 Microsoft 365 中的文件和应用程序。

在此共存模式下，每个客户端应用程序都作为单独的岛屿运行。 Skype for Business 与 Skype for Business 交流，Teams 与 Teams 交流。 用户需要始终运行两个客户端，并且可以在开始通信的客户端中进行本地通信。 因此，没有必要在 **并行** 模式下进行互操作。

为了避免 Skype for Business 体验的混乱或倒退，Skype for Business 会处理以下不在 Teams “**并行**” 模式下处理的集成:

- 外部 (联合) 通信。
- PSTN 语音服务和语音应用，Office 集成。
- USB 设备的 HID 控制。
- 其他几个集成。

Microsoft Teams 电话在 **“岛屿**”模式下的 Teams 中不支持系统。 

> [!Important]
>  - 在“**并行**”模式下，所有来自联合用户 (组织外部人员) 的消息和通话都会传送到 Skype for Business。 升级到 “**Teams Only**” 模式后，所有来自组织外部的消息和呼叫都会传送到 Teams。
>  - 你可能希望要求 Islands 用户始终在 Teams 中安排会议，方法是使用 PreferredMeetingProviderForIslandsMode=Teams 向他们分配 TeamsMeetingPolicy 的实例。 这可确保所有用户都使用 Teams 安排会议，Teams 支持组织中任何用户的身份验证登录和会议加入，无论用户是 TeamsOnly 还是仍在使用Skype for Business Server。 相比之下，从 2022 年 10 月开始，Microsoft 停用混合组织的旧版 Skype for Business Online 基础结构后，TeamsOnly 用户只能匿名加入Skype for Business会议。


### <a name="skype-for-business-only"></a>仅 Skype for Business

在此共存模式下，用户仍处于Skype for Business（而不是 Teams）的聊天、会议和通话功能中，并且不将 Teams 用于团队和频道。 此模式目前可用;但是，在当前实现中，不会自动关闭用户的团队和频道。 这可以通过使用应用设置策略隐藏团队和文件来实现。

该模式可以在启动 Teams 的管理部署之前使用，以防止用户在建立就绪状态之前开始使用 Teams。 该模式也是让 Skype for Business 用户通过身份验证参与 Teams 会议的一种方式，但前提是用户必须获得 Teams 的许可。

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business 与 Teams 协作

使用该模式在环境中引入 Teams，同时继续使用现有的 Skype for Business 投资。 保持 Skype for Business 的聊天、通话和会议功能不变。 增加 Teams 协作功能:

- Teams 和频道。
- 访问 Microsoft 365 或 Office 365 中的文件。
- 应用程序。 Teams 通信功能—私人聊天、通话和安排会议。

在此模式下，Teams 的私聊、通话和会议安排默认为关闭。

从本地Skype for Business Server开始的组织如果想要在迁移期间为用户提供通信的互操作性和可预测性，则将此模式作为 **Islands** 模式的替代方法。 此模式还提供了一个可预测的时间表，用于升级到 Teams (，而不是依赖于 **岛屿** 模式) 采用饱和度。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business 和 Teams 协作及会议，也称为“会议优先”

在此模式下，专用聊天和呼叫功能保留在Skype for Business，而 Teams 用于安排和进行会议，以及使用基于频道的对话进行协作。  此共存模式有助于加速组织中 Teams 会议和协作功能的可用性，并让用户利用卓越的 Teams 会议体验：

- 高质量。
- 转录和翻译。
- 背景模糊。
- 跨越所有平台的卓越用户体验，包括移动设备和浏览器。

Teams 和 Skype for Business 受益于一系列 "better together“ 的功能，例如在场协调、自动保持/取消保持以及跨两个应用程序的 HID 设备支持。 如果需要，可以使用 Teams 应用设置策略隐藏团队和频道。

这种共存模式对于使用企业语音的 Skype for Business 本地部署的企业特别有用。 这些组织可能需要一些时间来升级到 Teams，并希望尽快从卓越的 Teams 会议中获益。

> [!NOTE]
> 自 2022 年 10 月起，建议为之前分配的所有本地用户使用 **Teams 协作** 模式 **Skype for Business** 或Skype for Business。 此模式提供与其他两个相同的功能，但用户安排的新会议将是 Teams 会议，而不是Skype for Business会议。 这可确保用户将会议安排为 Teams 会议，支持组织中任何用户进行身份验证的登录和会议加入，无论用户是 TeamsOnly 还是仍在使用Skype for Business Server。  相比之下，随着 Microsoft 停用旧版 Skype for Business Online 基础结构，TeamsOnly 用户在加入Skype for Business会议时将不再能够进行身份验证，但是，他们仍然可以匿名加入。 有关详细信息，请参阅 [退休后的预期内容](skype-for-business-online-retirement.md#what-to-expect-post-retirement)。

> [!TIP]
> 为了帮助在 Skype for Business 仍在使用时根据要在 Teams 中启用的功能确定推荐的升级模式，请利用 [Skype to Teams 升级向导](https://aka.ms/SkypeToTeamsWizard)。

有关共存模式、前提条件和管理的更多信息，请参阅[为使用 Teams 和 Skype for Business 的组织提供的迁移](./migration-interop-guidance-for-teams-with-skype.md)和[互操作性指导以及设置共存和升级设置](./setting-your-coexistence-and-upgrade-settings.md)。

|决策点图标 |图标定义 |说明 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|决策点|<ul><li>哪种共存模式最适合组织和用户的需求？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|后续步骤|<ul><li>为升级之旅选择最佳方法。</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 和 Skype for Business 的互操作性

互操作性是同一组织中的 Teams 和 Skype for Business 用户可以跨 Teams 和 Skype for Business 进行通信的功能。

互操作性由接收器的共存模式（也称为升级模式）控制。 当接收器处于 **Islands** 模式时，没有互操作性。

> [!Note]
> 在除“**并行**”之外的任何共存模式下部署时，Teams 和 Skype for Business 可以进行 [互操作](#interoperability-of-teams-and-skype-for-business)，使用户能够互相聊天和通话，并确保在升级到 Teams 的过程中使跨组织通信保持流畅。 共存模式控制互操作性。 接收方的共存模式决定了互操作性是否可用。 例如，如果接收方处于一种模式中，聊天仅在一个客户端（比如说，Teams）中可用，则在发起者使用其他客户端（本例中为 Skype for Business）启动聊天的情况下，聊天互操作性通常可用。 另一方面，如果接收方处于两个客户端中的聊天均可用的模式（“并行”模式），则互操作性将不可用于聊天。 消息将由接收方在发起者在启动聊天的同一客户端中收到。 因此，在“**并行**”模式下正确通信需要 Teams 采用饱和；也就是说，所有用户都要主动使用和监视这两个客户端。

> [!Note]
> **若要获得最新的共存体验，客户端版本必须是用户 Office 部署通道中的最新可用客户端。**

#### <a name="native-interop-and-interop-escalation"></a>本地互操作和互操作升级

互操作体验有两种类型: 本机和互操作升级。

- 用户当前正在使用的客户端中会发生 _本机互操作性_ 体验。 一个用户将位于 Skype for Business 客户端中，另一个用户位于 Teams 中。 本机互操作体验不会把他们带到另一个客户端去沟通。 用户将可以在当前使用的客户端中进行对话。 本机互操作体验是一对一的聊天和通话。
- _互操作升级_ 体验意味着，在帮助用户执行高级操作（如共享其桌面）的过程中，客户端可帮助创建会议，用户可以加入会议以继续该会议的体验。 会议是在操作发起者的平台上创建的。 不在该平台上的一个或多个用户会收到会议加入链接。 单击此链接时，它们将加入到兼容的客户端 (浏览器、Web 应用或完整客户端中，具体取决于配置) 。 Skype for Business 的互操作升级需要一个最近的客户。 现在可以从 Teams 中进行互操作升级。 在租户内的互操作性体验以及联合通信跨租户中均支持这两种方式。

#### <a name="native-interop-experiences"></a>本机互操作体验

根据分配给用户的共存模式 (如前所述)，可提供以下本机互操作体验:

Skype for Business 用户可以与 Teams 用户一对一聊天，反之亦然。 互操作聊天需要通过一个互操作网关，该网关是 Teams 云服务的一部分 (因此只存在于线上)。 互操作聊天是纯文本: 不支持多信息文本和表情符号。 会通知 Teams 和 Skype for Business 中的用户该对话是互操作对话。

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business 用户可以与 Teams 用户进行一对一的语音和视频通话，Teams 用户也可以进行同样的通话。

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 使用本地部署Skype for Business的互操作体验要求本地环境与 Teams 处于混合模式。 有关详细信息，[请在 Skype for Business Server 和 Microsoft 365 或 Office 365 之间配置混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

这些互操作体验适用于指定了以下其中一种共存模式的用户之间使用: **Skype for Business 与 Teams 协作**、**Skype for Business 与 Teams 协作和会议**、 **Skype for Business Only** 或 **Teams Only**。 在 **Islands** 模式下，用户没有互操作性。

#### <a name="native-interop-experience-limitations"></a>本机互操作体验限制

由于协议和技术的差异，无法以本机方式支持所有功能。 具体而言，以下功能不可用：

- Teams 和 Skype for Business 均不支持 Markdown、多信息文本和完整的表情符集。 不支持 Teams 聊天中撰写框的其他本机功能。
- 本机不支持 Teams 和 Skype for Business 之间的屏幕共享（桌面或应用共享）。 然而是通过互操作升级来支持的。
- Teams 中的群聊（多方对话）只能包括使用 Teams 的参与者。
- Skype for Business 中的多方 IM 对话（群聊）只能包括使用 Skype for Business 的参与者。 但是，Skype for Business 可以将互操作性升级为多方通话。
- 不支持将正在进行的点对点语音通话或视频通话升级为涉及 Teams 和 Skype for Business 用户的多方通话。
- 不支持从 Teams 到 Skype for Business 的两方聊天的文件传输或群聊中的文件附件，反之亦然。
- 与持久聊天Skype for Business没有互操作性。

对于所有这些限制（除了“持续聊天”），一个可能的变通方法是用户开始会议并邀请其他用户加入。

这种变通方法是互操作升级的基础。 特别是，屏幕共享和升级到多方不是本机实现的，但通过互操作升级支持它们。

#### <a name="interop-escalation-experiences"></a>互操作升级体验

互操作升级包括通过对会议的管理升级来补充本地互操作功能。 无论用户使用哪个客户端，会议都可为任何人提供了丰富的体验。

当互操作升级由 Teams 用户触发时，会创建一个 Teams 会议。 当 Skype for Business 用户触发该升级时，将创建一个 Skype for Business 会议。 在这两种情况下，创建的会议都是 **“立即开会** ”会议，不会反映在用户的日历上。

对方通过互操作聊天收到会议加入链接，并通过点击该链接加入。 如果Skype for Business用户有 Teams 帐户，并且受 Teams 用户的邀请，他们将加入经过身份验证的会议。 否则，他们将以匿名参与者身份加入。 Teams 用户几乎总是有一个Skype for Business帐户和一个Skype for Business客户端，他们可以使用它作为经过身份验证的参与者加入Skype for Business会议，但他们也可能以匿名参与者身份加入，例如使用Skype 会议应用。

各方加入会议后，他们可以执行会议支持的任何活动，例如桌面或内容共享、文件共享或传输、添加其他参与者等。

#### <a name="interop-escalation-from-skype-for-business"></a>Skype for Business 的互操作升级

在 2019 年 7 月构建的月度 C2R 中更新了 Skype for Business 的互操作和互操作升级。 以前，Skype for Business没有提前意识到远程方正在使用 Teams。 它只是从建立会话后收到的信号推测出的。

当信号指示响应来自 (或通过) 互操作网关时，它将显示黄色业务栏 (横幅) 指示对方未使用Skype for Business。 随着服务的发展，这会产生误报，当 Skype for Business 用户连接到 Cloud Voicemail Service 或其他云语音服务而不是实际的 **Teams Only** 用户时，他们会看到业务栏。

为了防止误报，当另一方是 **仅限 Teams** 的实际用户时，状态服务现在会通知Skype for Business客户端。 这允许Skype for Business创建互操作会话，以及特定于互操作的对话窗口。

![用于创建与Skype for Business用户的互操作对话的 Teams 消息的屏幕截图。](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

例如，如果Skype for Business用户想要共享其桌面，系统会告知他们将开始会议，并指导他们完成这些步骤。

![用于开始与 Teams 用户会面的 Teams 消息的屏幕截图。](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

同时，Teams 用户会收到一条带有会议链接的聊天信息，并引导其加入。

这种升级到 Skype for Business 会议的方式既适用于租户内的互操作，也适用于跨租户的联合通话和聊天。 默认情况下，它处于打开状态，管理员无需预配任何设置。

#### <a name="interop-escalation-from-teams"></a>由 Teams 进行互操作升级

当 Teams 用户在与 Skype for Business 用户的租户内互操作线程中或在跨租户互操作联盟线程中选择桌面共享按钮时，现在可以从 Teams 升级到 Teams 会议。 支持从 1:1 聊天对话或从 1:1 通话中进行互操作升级。

Windows 版 Teams桌面客户端、Mac 版 Teams 桌面客户端以及支持内容共享的浏览器上的 Teams Web 客户端都支持该功能，并且可以与任何 Skype for Business 客户端版本进行通信。

在互操作性线程和联合身份验证互操作性线程中，Teams 用户现在拥有开始内容共享的控件（按钮）。 当 Teams 用户选择该按钮时，会显示一个附加菜单，告知他们要共享内容，他们需要启动 Teams 会议。

如果用户在呼叫中，菜单会警告他们，在 Teams 和 Skype for Business 之间的当前呼叫会在进入 Teams 会议时终止。 如果他们选择，他们可以在接受之前警告 Skype for Business 用户。

![要与Skype for Business用户共享会议的 Teams 消息的屏幕截图。](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

接受后，他们将被提交到 Teams 会议中;他们必须从会议中的共享托盘开始共享。

同时，Skype for Business 用户会收到一条带有会议链接的聊天信息，并引导其加入。

这种升级到 Teams 会议的方式既适用于租户内互操作，也适用于跨租户联合通话和聊天。 默认情况下，它处于打开状态，管理员无需预配任何设置。 但是，如果管理员将``CsTeamsMeetingPolicy``中的``-AllowPrivateMeetNow``设置为``$false``，则会对用户关闭。

查看本文之后，请参阅 [选择升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[迁移和互操作性指南](./migration-interop-guidance-for-teams-with-skype.md)、[与 Skype for Busines 共存](coexistence-chat-calls-presence.md) 和 [设置共存和升级设置](./setting-your-coexistence-and-upgrade-settings.md)，以了解实施的详细信息。 我们还推荐以下视频: [视频: 管理 SfB 和 Teams 之间的共存和互操作性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Teams 和 Skype for Business 共存的技术细节

以下部分汇总了在同一组织中同时运行 Teams 和 Skype for Business 客户端时可能遇到的行为，无论使用何种模式和升级方法:

- [会议](#meetings)
- [互操作性](#interoperability)
- [互操作与本机对话线程](#interop-versus-native-conversation-threads)
- [状态](#presence)
- [联合身份验证](#federation)
- [联系人](#contacts)

### <a name="meetings"></a>会议

无论其模式如何，用户始终可以加入他们受邀参加的任何类型的会议，无论是Skype for Business还是 Teams。  但是，用户必须通过与会议类型相匹配的相应客户端加入会议:

- 如果会议是 Teams 会议，则所有参与者 (他们是 TeamsOnly、Islands 还是Skype for Business用户) 使用 Teams 客户端加入会议。 如果未安装 Teams，则在尝试加入会议时，用户将被定向到 Web。

- 如果会议是Skype for Business会议，则所有参与者 (他们是 TeamsOnly、Islands 还是Skype for Business用户) 使用Skype for Business客户端加入会议。 如果未安装Skype for Business客户端，则用户将被定向到 Web，以便通过Skype 会议应用加入。 

  在某些情况下，TeamsOnly 模式下的参与者只能以匿名用户身份使用 Skype for Business Web应用 或 Skype 会议应用加入Skype for Business会议。 最终，对于 TeamsOnly 模式下的所有用户来说，这种情况都是如此。 有关详细信息，请参[阅Skype for Business联机停用](skype-for-business-online-retirement.md#what-to-expect-post-retirement)。

在组织会议时，根据组织者的模式来安排会议类型，如下表所示:

| 组织者模式    |      行为 |
| :------------------ | :---------------- |
| TeamsOnly、SfbWithTeamsCollabAndMeetings | 在 Teams 中安排的所有会议。 Skype for Business外接程序在 Outlook 中不可用。 |
| SfbWithTeamsCollab、SfbOnly | Skype for Business 中安排的所有会议。 Teams 加载项在 Outlook 中不可用。 请考虑改用 SfbWithTeamsCollabAndMeetings，它允许所有用户（无论是本地用户还是 TeamsOnly）使用 Teams 进行会议。|
| 孤岛 | 默认情况下，会议可以在 Skype for Business 或 Teams 中安排。 这两个加载项都可以在 Outlook 中使用。 但是，可以选择要求在“并行“中的用户总是在 Teams 中安排会议，方法是为他们分配一个 TeamsMeetingPolicy 实例中，并使用 PreferredMeetingProviderForIslandsMode=Teams。|

### <a name="interoperability"></a>互操作性

如上文 [Teams 和 Skype for Business 的互操作性](#interoperability-of-teams-and-skype-for-business) 中所述，Teams 在某些情况下支持与 Skype for Business 的互操作。 互操作通信是指 Skype for Business 用户与 Teams 用户之间的聊天或通话。 只能在两个用户之间进行互操作通信;不支持多方聊天/呼叫或添加其他用户。

当以下各项为 true 时，两个用户之间就会产生互操作聊天或通话:

- 一个用户使用 Teams，另一个用户使用 Skype for Business。

- 初始通信的收件人模式不是 Islands (否则，如果两个用户都在同一个组织中，通信将进入同一客户端) 。 在联合方案中，发送用户使用 Teams，并且收件人不在 TeamsOnly 模式下。

- Teams 用户在本地主页没有 Skype for Business 账户。

在互操作间的通信，聊天仅支持纯文本。 此外，互 *操作聊天本身* 无法共享文件和屏幕共享。 然而，在互操作对话中的用户可以通过创建一个按需会议，从互操作聊天中轻松实现文件和/或屏幕共享，如下所述:

- 如果 Teams 用户尝试共享其屏幕，则会自动创建按需 Teams 会议，并将指向该会议的邀请链接发送到Skype for Business用户的客户端。 点击链接后，Skype for Business 用户将打开 Teams 并加入会议。 现在两个用户都在 Teams 会议中，可以根据需要进行共享。

- 如果Skype for Business用户使用 2018 年或更高版本的客户端，并尝试共享任何内容，则会自动创建按需Skype for Business会议，并将指向该会议的邀请链接发送到 Teams 用户的客户端。 点击链接后，Teams 用户将尝试加入 Skype for Business 会议。 如果 Teams 用户安装了Skype for Business客户端，它将打开，并且系统会提示用户登录 (（如果尚未登录) ）。  如果 Teams 用户没有安装 Skype for Business 客户端，将提示用户使用网页版。 两个用户登录后，他们都会参加Skype for Business会议，并可以根据需要进行共享。

### <a name="interop-versus-native-conversation-threads"></a>互操作与本机对话线程

由于互操作通信不支持本机 Teams 会话的所有功能，因此 Teams 客户端为 Teams 到 Teams 和 Teams 到Skype for Business通信维护单独的会话线程。 这些对话在用户界面上的呈现方式不同。互操作线程可以通过以下方式与常规本地 Teams 线程区分开来:

- 缺乏对多信息文本、文件/屏幕共享的控制，无法添加用户。
- 对目标用户图标的修改，显示Skype for Business的“S”。

这些差异将显示在下面的屏幕截图中:

与用户 G3 测试的本机 Teams-to-Teams 对话

![显示本机 Teams 到 Teams 对话的示意图。](media/teams-upgrade-native-thread.png)

与同一用户 G3 测试互操作对话

![显示 Teams 到 Teams 互操作对话的示意图。](media/teams-upgrade-interop-thread.png)

对话线程一旦创建，其类型就不会改变。 创建后，Teams 中的互操作线程将始终路由到目标用户的Skype for Business客户端。 本机线程将始终路由到目标用户的 Teams 客户端。  如果收件人用户的模式发生更改，则该用户的现有 Teams 线程将不再起作用，并且会在该聊天中显示一条便笺，其中包含一个链接来启动新的本机对话，如以下屏幕截图所示。

![显示与升级的Skype for Business用户聊天的示意图。](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>状态

给定用户的状态基于用户通过客户端在服务中的活动。 然后将状态公布给其他用户看。  Skype for Business 和 Teams 是具有独立客户端的独立服务，因此每个服务都有自己的用户状态。   Teams 和 Skype for Business Online 中的状态服务之间也存在同步。  这使得一个服务在需要的时候有可能从另一个服务发布用户的状态。

状态发布行为基于用户的模式。 有三个基本情况:

- 如果一个用户处于 TeamsOnly 模式，则无论所有其他用户使用的是哪个客户端，他们都会看到该用户的 Teams 状态。

- 如果一个用户处于任何一种 Skype for Business 模式，则无论所有其他用户使用的是哪个客户端，他们都会看到该用户的 Skype for Business 状态。

- 如果用户处于“并行”模式，则 Skype for Business 和 Teams 中发布的状态是独立的，因此向同一组织内的用户显示的状态将取决于其他用户的客户端。 联合组织中的用户将根据他们的 Skype for Business 活动看到该用户的状态，因为指向“并行”模式用户的联合流量将落在 Skype for Business 中。

例如，假设用户 A 处于“并行”模式。 如果用户 A 在 Teams 中处于活动状态，但未登录到 Skype for Business，则其他用户会从其 Teams 客户端看到用户 A 处于活动状态，但在其Skype for Business客户端中，他们会将用户 A 视为脱机。 这是设计上的，因为如果用户 A 未运行客户端，则无法访问该用户 A。


### <a name="federation"></a>联合

使用 Skype for Business 从 Teams 到另一个用户的联合需要 Teams 用户在 Skype for Business 中保持在线。 TeamsUpgradePolicy 管理传入的联合聊天和通话的路由。 联合路由行为与同一租户方案相同，但在 Islands 模式下除外。 档收件人处于 Islands 模式时：

- 如果收件人在联合租户中，则从 Teams 发起的聊天和通话会出现在 Skype for Business 中。
- 如果收件人在同一租户中，则从 Teams 发起的聊天和通话会进入 Teams。
- 从 Skype for Business 发起的聊天和通话总是在 Skype for Business 中进行。

联合聊天可以是本机线程，也可以是互操作线程。 请参阅 [互操作与本机对话线程](#interop-versus-native-conversation-threads)。

- 如果接收方和发件人都处于 TeamsOnly 升级模式，则会话将是一种本机聊天体验，其中包括所有丰富的消息传送和呼叫功能。 如果要了解更多信息，请阅读 [Teams 中外部 (联合) 用户的本机聊天体验](native-chat-for-external-users.md)。

- 如果对话参与者中的任何一个不处于 TeamsOnly 升级模式下，对话仍然是一个纯文本消息的互操作体验。 用户界面以与同租户互操作线程类似的方式公开联合聊天，但有一条说明指示用户是外部的。

有关详细信息，请参阅 [管理 Microsoft Teams 中的外部访问](manage-external-access.md) 和 [Teams 中外部 (联合) 用户的本机聊天体验](native-chat-for-external-users.md)。

### <a name="contacts"></a>联系人

Teams 和 Skype for Business 有单独的联系人列表。 这意味着在一个系统中进行的联系人添加、删除和修改不会同步到另一个系统。 然而，当发生两个特定事件中的任何一个时，Skype for Business 中的联系人会自动复制到 Teams 中:

- 对于任何 Skype for Business Online 用户来说，他们第一次登录 Teams 时，都将复制 Skype for Business 中的联系人到 Teams 中。 此行为不适用于在Skype for Business Server中具有本地帐户的用户。

- 当用户升级到 TeamsOnly 后 (通过指定 TeamsUpgradePolicy 或通过 Move-CsUser -MoveToTeams)，下次用户登录 Teams 时，Skype for Business 中的现有联系人将与 Teams 中已有的联系人合并。 无论用户是从本地还是联机移动到 TeamsOnly，都发生此行为。

在这两种情况下，从 Skype for Business 到 Teams 的联系人传输是异步的，因此可能要过几分钟才能在 Teams 中出现联系人。 以上两个事件就是触发副本的原因。

### <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
