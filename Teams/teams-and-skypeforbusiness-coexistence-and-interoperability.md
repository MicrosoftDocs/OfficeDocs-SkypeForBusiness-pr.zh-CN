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
localization_priority: Normal
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
ms.openlocfilehash: 9f28ff0d0cffd3cd370d1454c84e6645fea1a2603fa61f9a21f519e84cef5d92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342767"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>了解 Microsoft Teams 和 Skype for Business 的共存和互操作性

![升级过程图，强调"项目定义"阶段](media/upgrade-banner-project-definition.png "升级过程的各个阶段，重点是项目定义阶段")

本文是升级历程中“项目定义”阶段的一部分。 在创建赞助联盟和项目团队并确定项目范围、目标和计划后完成。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)

如果组织目前使用的是 Skype for Business，并且开始在使用 Skype for Business 的同时使用 Teams，或者要升级到 Teams，那么了解这两个应用程序如何共存、何时以及如何进行互操作，以及如何管理用户从 Skype for Business 迁移到 Teams 的整个过程则是非常重要的。

> [!Tip]
> 请观看下面的会话以了解 [共存和互操作性](https://aka.ms/teams-upgrade-coexistence-interop)。
>
> 此外，还可以参加我们的现场互动研讨会，我们将在研讨会上分享指导、最佳实践和资源，以启动升级规划和实施。
>
> 先加入 [计划升级](./upgrade-workshops-landing-page.yml) 会话才能开始。

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Teams 与 Skype for Business 共存概述

以下部分介绍了当决定升级到 Teams 时可用的共存模式，以及每个模式提供的功能。 此外，我们还介绍了 Skype-for-Business 客户端上的用户和 Teams 客户端上的用户之间发生的互操作性 (互操作)，以及所选择的共存模式对互操作的影响。

 Teams 提供协作功能、聊天、通话和会议功能。 根据所选择部署 Teams 的方式，这些功能可能与 Skype for Business 为特定用户提供的功能相重叠。 默认模式即是同时运行功能重叠的 Skype for Business 与 Teams。 然而，可以分配用户到几种共存模式 (也称为升级模式) 之一中，这些模式的设计是为了确保这些功能对该用户来说不会重叠 (在这种情况下，Teams 和 Skype for Business 之间的互操作性是可用的)。 例如，如果拥有大量的 Skype for Business Server 本地资产，并进行了复杂的企业语音部署，但又希望用户能够尽快享受现代会议，则可能需要评估“[会议优先](meetings-first.md)”作为备选路径。

我们建议查看以下共存模式，以帮助确定哪种路径适合你的组织。

> [!Important]
> 2021 年 7 月 31 日停用 Skype for Business Online 后，共存模式将继续存在，但仅与在本地部署 Skype for Business Server 的组织相关。 在停用之前，可以将本地部署中的用户分配到除 TeamsOnly 外的任何模式。 但是，停用 Skype for Business Online 后，云中的用户只能是 TeamsOnly。

### <a name="islands-mode"></a>“并行”模式

默认情况下，用户可以同时运行 Teams 和 Skype for Business 作为提供相似和重叠功能的两个独立的解决方案。 功能包括状态、聊天、通话和会议。 Teams 用户还可以利用新的协作功能，如团队和渠道，访问 Microsoft 365 或 Office 365 中的文件和应用程序。

在这种称为 “**并行**” 的共存模式中，每个客户端应用程序都作为单独的“小岛”运行。 Skype for Business 与 Skype for Business 交流，Teams 与 Teams 交流。 用户需要始终运行两个客户端，并且可以在开始通信的客户端中进行本地通信。 因此，没有必要在 **并行** 模式下进行互操作。

为了避免 Skype for Business 体验的混乱或倒退，Skype for Business 会处理以下不在 Teams “**并行**” 模式下处理的集成:

- 外部 (联合) 通信。
- PSTN 语音服务和语音应用，Office 集成。
- USB 设备的 HID 控制。
- 其他几个集成。  

“**并行**” 模式中的 Teams 不支持电话系统。 “**并行**“ 模式不支持的企业语音客户端为 Skype for Business。

> [!Important]
> 在“**并行**”模式下，所有来自联合用户 (组织外部人员) 的消息和通话都会传送到 Skype for Business。 升级到 “**Teams Only**” 模式后，所有来自组织外部的消息和呼叫都会传送到 Teams。

> [!Tip]
> Skype for Business 在线客户推荐的路径是先从默认的 “**并行**” 模式开始，推动组织中的 Teams 采用饱和，然后迅速转向 **Teams Only** 模式。 本地客户和混合客户 (尤其是复杂的客户) 可能会受益于以 **Skype for Business 与 Teams 协作** 模式作为起点，而不是 “**并行**” 模式，然后在适当情况下从该模式发展到 **Skype for Business with Teams 协作和会议** 模式 (即“会议优先”)，如果合适的话，在组织准备好采用 Teams 时发展到 **Teams Only** 模式。

### <a name="teams-only"></a>Teams Only

**Teams Only** 用户 (也称为”*已升级* 用户”) 可以使用 Teams 中的所有功能。 他们可能仍使用 Skype for Business 客户端，以便加入由未经升级的用户或外部方组织的 Skype for Business 会议。 通过使用 Teams 和 Skype for Business 之间的互操作性功能，已升级的用户可以继续与组织中仍使用 Skype for Business 的其他用户进行通信（前提是 Skype for Business 用户未处于“**并行**”模式）。 但是，已升级的用户无法启动 Skype for Business 聊天、通话或会议。

一旦组织准备好让部分或所有用户使用 Teams 作为他们唯一的通信和协作工具，请将这些用户升级到 **Teams Only** 模式。 如果要从“**并行**”模式升级，我们建议在开始升级过程之前，先让整个组织的 Teams 采用饱和。 这种采用避免了由于“**并行**”模式不提供互操作性而导致的通信中断场景。

当处于 **Teams Only** 模式时，Teams 是 SIP/Tel 协议的默认应用。 用户在 Outlook 中的联系人卡中用于通话或聊天的链接将由 Teams 处理。

有关移动到 **Teams Only** 模式的额外注意事项，请参阅 [Teams Only 模式注意事项](teams-only-mode-considerations.md)。

![Teams 确认消息的屏幕截图](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "用户升级为 Teams-Only 用户后，Skype for Business 客户端以特殊模式运行")

### <a name="skype-for-business-only"></a>仅 Skype for Business

在这种共存模式下，用户仍然使用 Skype for Business，而不是 Teams 来实现聊天、会议和通话功能，并且他们也不使用面向团队和频道的 Teams。 此模式现在可用；但是，在当前实施中，不会为用户自动关闭团队和频道。 这可以通过使用应用设置策略隐藏团队和文件来实现。

该模式可以在启动 Teams 的管理部署之前使用，以防止用户在建立就绪状态之前开始使用 Teams。 该模式也是让 Skype for Business 用户通过身份验证参与 Teams 会议的一种方式，但前提是用户必须获得 Teams 的许可。

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business 与 Teams 协作

使用该模式在环境中引入 Teams，同时继续使用现有的 Skype for Business 投资。 保持 Skype for Business 的聊天、通话和会议功能不变。 增加 Teams 协作功能:

- Teams 和频道。
- 访问 Microsoft 365 或 Office 365 中的文件。
- 应用程序。 Teams 通信功能—私人聊天、通话和安排会议。

在此模式下，Teams 的私聊、通话和会议安排默认为关闭。

如果组织希望为其用户提供通信的互操作性和可预测性，并为其升级到 Teams 提供一个可预测的时间表（而不是依赖”**并行**”模式中的采用饱和度），那么拥有 Skype for Business Server 起点的组织应该考虑将该模式作为”**并行**”模式的替代方案。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business 和 Teams 协作及会议，也称为“会议优先”

使用此共存模式可加快组织中 Teams 会议和协作功能的可用性。 共存模式让用户能够利用卓越的 Teams 会议体验:

- 高质量。
- 转录和翻译。
- 背景模糊。
- 跨越所有平台的卓越用户体验，包括移动设备和浏览器。

除了在此模式中使用 Teams 进行基于团队和频道的对话外，用户还将使用 Teams 来安排和组织其会议。 私人聊天和通话仍在 Skype for Business 上进行。 Teams 和 Skype for Business 受益于一系列 "better together“ 的功能，例如在场协调、自动保持/取消保持以及跨两个应用程序的 HID 设备支持。 如果需要，可以使用应用设置策略隐藏团队和频道。

这种共存模式对于使用企业语音的 Skype for Business 本地部署的企业特别有用。 这些组织可能需要一些时间来升级到 Teams，并希望尽快从卓越的 Teams 会议中获益。

> [!TIP]
> 为了帮助在 Skype for Business 仍在使用时根据要在 Teams 中启用的功能确定推荐的升级模式，请利用 [Skype to Teams 升级向导](https://aka.ms/SkypeToTeamsWizard)。

有关共存模式、前提条件和管理的更多信息，请参阅[为使用 Teams 和 Skype for Business 的组织提供的迁移](./migration-interop-guidance-for-teams-with-skype.md)和[互操作性指导以及设置共存和升级设置](./setting-your-coexistence-and-upgrade-settings.md)。

|决策点图标 |图标定义 |说明 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|决策点|<ul><li>哪种共存模式最适合组织和用户的需求？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|后续步骤|<ul><li>为升级之旅选择最佳方法。</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 和 Skype for Business 的互操作性

互操作性是同一组织中的 Teams 和 Skype for Business 用户可以跨 Teams 和 Skype for Business 进行通信的功能。

互操作性由接收器的共存模式（也称为升级模式）控制。 当接收器处于“**并行**”模式时，没有互操作性。

> [!Note]
> 在除“**并行**”之外的任何共存模式下部署时，Teams 和 Skype for Business 可以进行 [互操作](#interoperability-of-teams-and-skype-for-business)，使用户能够互相聊天和通话，并确保在升级到 Teams 的过程中使跨组织通信保持流畅。 共存模式控制互操作性。 接收方的共存模式决定了互操作性是否可用。 例如，如果接收方处于一种模式中，聊天仅在一个客户端（比如说，Teams）中可用，则在发起者使用其他客户端（本例中为 Skype for Business）启动聊天的情况下，聊天互操作性通常可用。 另一方面，如果接收方处于两个客户端中的聊天均可用的模式（“并行”模式），则互操作性将不可用于聊天。 消息将由接收方在发起者在启动聊天的同一客户端中收到。 因此，在“**并行**”模式下正确通信需要 Teams 采用饱和；也就是说，所有用户都要主动使用和监视这两个客户端。

> [!Note]
> **如果要想获得最新的共存体验，客户端版本必须是用户的 Office 部署渠道中最新的可用客户端。**

#### <a name="native-interop-and-interop-escalation"></a>本地互操作和互操作升级

互操作体验有两种类型: 本机和互操作升级。

- 用户当前正在使用的客户端中会发生 _本机互操作性_ 体验。 一个用户将位于 Skype for Business 客户端中，另一个用户位于 Teams 中。 本机互操作体验不会把他们带到另一个客户端去沟通。 用户将可以在当前使用的客户端中进行对话。 本机互操作体验是一对一的聊天和通话。
- _互操作升级_ 体验意味着，在帮助用户执行高级操作（如共享其桌面）的过程中，客户端可帮助创建会议，用户可以加入会议以继续该会议的体验。 会议是在操作发起者的平台上创建的。 不在该平台上的一个或多个用户会收到会议加入链接。 当他们单击此链接时，他们将在兼容客户端（浏览器、Web 应用或完整客户端，具体取决于配置）中加入会议。 Skype for Business 的互操作升级需要一个最近的客户。 现在可以从 Teams 中进行互操作升级。 在租户内的互操作性体验以及联合通信跨租户中均支持这两种方式。

#### <a name="native-interop-experiences"></a>本机互操作体验

根据分配给用户的共存模式 (如前所述)，可提供以下本机互操作体验:

Skype for Business 用户可以与 Teams 用户一对一聊天，反之亦然。 互操作聊天需要通过一个互操作网关，该网关是 Teams 云服务的一部分 (因此只存在于线上)。 互操作聊天是纯文本: 不支持多信息文本和表情符号。 会通知 Teams 和 Skype for Business 中的用户该对话是互操作对话。

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business 用户可以与 Teams 用户进行一对一的语音和视频通话，Teams 用户也可以进行同样的通话。

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 本地部署 Skype for Business 的互操作体验要求本地环境与 Microsoft 365 或 Office 365 Skype for Business 处于混合模式。 详情请参见[迁移和互操作性指南](./migration-interop-guidance-for-teams-with-skype.md)。

这些互操作体验适用于指定了以下其中一种共存模式的用户之间使用: **Skype for Business 与 Teams 协作**、**Skype for Business 与 Teams 协作和会议**、 **Skype for Business Only** 或 **Teams Only**。 处于“**并行**”模式的用户没有互操作性。

#### <a name="native-interop-experience-limitations"></a>本机互操作体验限制

由于协议和技术方面的差异，因此不可能本地支持所有功能。 具体来说，不提供以下功能：

- Teams 和 Skype for Business 均不支持 Markdown、多信息文本和完整的表情符集。 不支持 Teams 聊天中撰写框的其他本机功能。
- 本机不支持 Teams 和 Skype for Business 之间的屏幕共享（桌面或应用共享）。 然而是通过互操作升级来支持的。
- Teams 中的群聊（多方对话）只能包括使用 Teams 的参与者。
- Skype for Business 中的多方 IM 对话（群聊）只能包括使用 Skype for Business 的参与者。 但是，Skype for Business 可以将互操作性升级为多方通话。
- 不支持将正在进行的点对点语音通话或视频通话升级为涉及 Teams 和 Skype for Business 用户的多方通话。
- 不支持从 Teams 到 Skype for Business 的两方聊天的文件传输或群聊中的文件附件，反之亦然。
- Skype for Business 持久聊天没有互操作性。

对于所有这些限制（除了“持续聊天”），一个可能的变通方法是用户开始会议并邀请其他用户加入。

这种变通方法是互操作升级的基础。 尤其是屏幕共享和升级到多方的功能，虽然本机无法实现，但通过互操作升级却可以支持。

#### <a name="interop-escalation-experiences"></a>互操作升级体验

互操作升级包括通过对会议的管理升级来补充本地互操作功能。 无论用户使用哪个客户端，会议都可为任何人提供了丰富的体验。

当互操作升级由 Teams 用户触发时，会创建一个 Teams 会议。 当 Skype for Business 用户触发该升级时，将创建一个 Skype for Business 会议。 在这两种情况下，创建的会议都是“**立即开会**”会议，该会议未反映在用户的日历上。

对方通过互操作聊天收到会议加入链接，并通过点击该链接加入。 如果 Skype for Business 用户拥有一个 Teams 帐户并且受到一个 Teams 用户邀请，则他们将加入经过身份验证的会议。 否则，他们将以匿名参与者的身份加入。 相反，Teams 用户几乎都拥有一个 Skype for Business 帐户和一个 Skype for Business 客户端，他们可以用来以经过身份验证的参加者的身份加入 Skype for Business 会议，但是他们也可以以匿名参加者的身份加入，例如使用 Skype 会议应用。

各方加入会议后，他们可以执行会议支持的任何活动，例如桌面或内容共享、文件共享或传输、添加其他参与者等。

#### <a name="interop-escalation-from-skype-for-business"></a>Skype for Business 的互操作升级

在 2019 年 7 月构建的月度 C2R 中更新了 Skype for Business 的互操作和互操作升级。 以前，Skype for Business 不会提前感知远程方正在使用 Teams。 它只是从建立会话后收到的信号推测出的。

当信号表明响应来自 (或通过) 互通网关时，会显示黄色的业务栏 (横幅)，表示对方没有使用 Skype for Business。 随着服务的发展，这会产生误报，当 Skype for Business 用户连接到 Cloud Voicemail Service 或其他云语音服务而不是实际的 **Teams Only** 用户时，他们会看到业务栏。

为了防止这些误报，当对方是 **Teams Only** 实际用户时，状态服务现在会通知 Skype for Business 客户端。 这使得 Skype for Business 能够意识到它需要在创建互操作对话之前就创建一个互操作对话，并将对话窗口指定为互操作。

![与 Skype for Business 用户创建互操作对话的 Teams 消息截图](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

例如，如果 Skype for Business 用户想要共享他们的桌面，将告知他们我们将开始一个会议，并指导他们完成步骤。

![开始与 Teams 用户开会的 Teams 消息截图](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

同时，Teams 用户会收到一条带有会议链接的聊天信息，并引导其加入。

这种升级到 Skype for Business 会议的方式既适用于租户内的互操作，也适用于跨租户的联合通话和聊天。 它是默认开启的，管理员不需要预配任何设置。

#### <a name="interop-escalation-from-teams"></a>由 Teams 进行互操作升级

当 Teams 用户在与 Skype for Business 用户的租户内互操作线程中或在跨租户互操作联盟线程中选择桌面共享按钮时，现在可以从 Teams 升级到 Teams 会议。 支持从 1:1 聊天对话或从 1:1 通话中进行互操作升级。

Windows 版 Teams桌面客户端、Mac 版 Teams 桌面客户端以及支持内容共享的浏览器上的 Teams Web 客户端都支持该功能，并且可以与任何 Skype for Business 客户端版本进行通信。

在互操作性线程和联合身份验证互操作性线程中，Teams 用户现在拥有开始内容共享的控件（按钮）。 当 Teams 用户选中该按钮时，将向他们显示一个附加菜单，通知他们共享内容，他们将需要开始 Teams 会议。

如果用户正在通话中，菜单还会提醒他们在 Teams 和 Skype for Business 之间进行的当前通话将在他们进入 Teams 会议后终止。 如果他们选择，他们可以在接受之前警告 Skype for Business 用户。

![与 Skype for Business 用户共享会议的 Teams 消息截图](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

接受后，他们将进入 Teams 会议；必须从会议中的共享托盘开始共享。

同时，Skype for Business 用户会收到一条带有会议链接的聊天信息，并引导其加入。

这种升级到 Teams 会议的方式既适用于租户内互操作，也适用于跨租户联合通话和聊天。 它是默认开启的，管理员不需要预配任何设置。 但是，如果管理员将``CsTeamsMeetingPolicy``中的``-AllowPrivateMeetNow``设置为``$false``，则会对用户关闭。

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

无论用户采用何种模式，他们都可以随时加入任何类型的会议，无论是 Skype for Business 还是 Teams。  但是，用户必须通过与会议类型相匹配的相应客户端加入会议:

- 如果会议是 Teams 会议，所有参与者 (无论他们是TeamsOnly、“并行“ 还是 Skype for Business 用户) 都会使用 Teams 客户端加入会议。 如果没有安装 Teams，用户在试图加入会议时，将引导其到 Web 加入。

- 如果会议是 Skype for Business 会议，所有参与者 (无论他们是TeamsOnly、“并行“ 还是Skype for Business用户) 都会使用 Skype for Business 客户端加入会议。 如果没有安装 Skype for Business 客户端，将引导用户至 Web，通过 Skype 会议应用程序加入。

在组织会议时，根据组织者的模式来安排会议类型，如下表所示:

| 组织者模式    |      行为 |
| :------------------ | :---------------- |
| TeamsOnly、SfbWithTeamsCollabAndMeetings |    在 Teams 中安排的所有会议。 Skype for Business 加载项在 Outlook 中不可用。 | 
| SfbWithTeamsCollab、SfbOnly   | Skype for Business 中安排的所有会议。 Teams 加载项在 Outlook 中不可用。 | 
| 并行 | 默认情况下，会议可以在 Skype for Business 或 Teams 中安排。 这两个加载项都可以在 Outlook 中使用。 但是，可以选择要求在“并行“中的用户总是在 Teams 中安排会议，方法是为他们分配一个 TeamsMeetingPolicy 实例中，并使用 PreferredMeetingProviderForIslandsMode=Teams。| 


### <a name="interoperability"></a>互操作性

如上文 [Teams 和 Skype for Business 的互操作性](#interoperability-of-teams-and-skype-for-business) 中所述，Teams 在某些情况下支持与 Skype for Business 的互操作。 互操作通信是指 Skype for Business 用户与 Teams 用户之间的聊天或通话。  互操作只能在两个用户之间进行，不支持多方聊天/通话或添加其他用户。

当以下各项为 true 时，两个用户之间就会产生互操作聊天或通话:

- 一个用户使用 Teams，另一个用户使用 Skype for Business。

- 如果两个用户都在同一 组织，则初始通信的接收方模式为”非并行“ (否则通信会落在同一个客户端)。 在联合情景下，发送用户使用 Teams，而接收方不在 TeamsOnly 模式下。 

- Teams 用户在本地主页没有 Skype for Business 账户。

在互操作间的通信，聊天仅支持纯文本。 此外，无法 *在互操作聊天本身* 进行文件共享和屏幕共享。 然而，在互操作对话中的用户可以通过创建一个按需会议，从互操作聊天中轻松实现文件和/或屏幕共享，如下所述:

- 如果 Teams 用户试图共享他们的屏幕，则会自动创建一个按需的 Teams 会议，并将该会议的邀请链接发送到 Skype for Business 用户的客户端。 点击链接后，Skype for Business 用户将打开 Teams 并加入会议。 现在两个用户都在 Teams 会议中，可以根据需要进行共享。

- 如果 Skype for Business 用户使用的是 2018 年或更高版本的客户端，并试图共享任何内容，则会自动创建一个按需的 Skype for Business 会议并将该会议的邀请链接发送到 Teams 用户的客户端。 点击链接后，Teams 用户将尝试加入 Skype for Business 会议。 如果 Teams 用户已经安装了 Skype for Business 客户端，它将打开并提示用户登录 (如果尚未登录)。  如果 Teams 用户没有安装 Skype for Business 客户端，将提示用户使用网页版。 一旦两个用户都登录了，他们就会进入 Skype for Business 会议，并可以根据需要进行共享。

### <a name="interop-versus-native-conversation-threads"></a>互操作与本机对话线程

由于互操作通信不支持本机 Teams 对话的所有功能，Teams 客户端为 Teams 到 Teams 和 Teams 到 Skype for Business 通信维护了单独的对话线程。 这些对话在用户界面上的呈现方式不同。互操作线程可以通过以下方式与常规本地 Teams 线程区分开来:

- 缺乏对多信息文本、文件/屏幕共享的控制，无法添加用户。
- 修改目标用户的图标，显示 Skype for Business 中的 "S"。

这些差异将显示在下面的屏幕截图中:

与用户 G3 测试的本机 Teams-to-Teams 对话

![显示本机 Teams-to-Teams 对话图表](media/teams-upgrade-native-thread.png)

与同一用户 G3 测试互操作对话

![互操作 Teams-to-Teams 对话示意图](media/teams-upgrade-interop-thread.png)

对话线程一旦创建，其类型就不会改变。 创建后，Teams 中的互操作线程将始终路由到目标用户的 Skype for Business 客户端。 本机线程将始终路由到目标用户的 Teams 客户端。  如果收件人用户的模式发生变化，现有的指向该用户的 Teams 线程将不再发挥作用，并且会在该聊天上显示一条带有开始新的本地对话的链接的备注，如下截图所示。

![显示与升级后的 Skype for Business 用户聊天的图表](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>状态

特定用户状态是基于用户通过客户端在服务中的活动。 然后将状态公布给其他用户看。  Skype for Business 和 Teams 是具有独立客户端的独立服务，因此每个服务都有自己的用户状态。   Teams 和 Skype for Business Online 中的状态服务之间也保持同步。  这使得一个服务在需要的时候有可能从另一个服务发布用户的状态。 

状态发布行为取决于用户的模式。 有三个基本情况:

- 如果一个用户处于 TeamsOnly 模式，则无论所有其他用户使用的是哪个客户端，他们都会看到该用户的 Teams 状态。

- 如果一个用户处于任何一种 Skype for Business 模式，则无论所有其他用户使用的是哪个客户端，他们都会看到该用户的 Skype for Business 状态。

- 如果用户处于“并行”模式，则 Skype for Business 和 Teams 中发布的状态是独立的，因此向同一组织内的用户显示的状态将取决于其他用户的客户端。 联合组织中的用户将根据他们的 Skype for Business 活动看到该用户的状态，因为指向“并行”模式用户的联合流量将落在 Skype for Business 中。

例如，假设用户 A 处于“并行”模式。 如果用户 A 在 Teams 中在线，但没有登录 Skype for Business，其他用户将在其 Teams 客户端中看到用户 A 是在线的，但在 Skype for Business 客户端中，他们将看到用户 A 是离线的。 这是特地设计的，因为用户 A 如果不运行客户端，就无法联系到他们。 


### <a name="federation"></a>联合

使用 Skype for Business 从 Teams 到另一个用户的联合需要 Teams 用户在 Skype for Business 中保持在线。 TeamsUpgradePolicy 管理传入的联合聊天和通话的路由。 联合路由行为与同一租户方案相同，但在 Islands 模式下除外。 档收件人处于 Islands 模式时：

- 如果收件人在联合租户中，则从 Teams 发起的聊天和通话会出现在 Skype for Business 中。
- 如果收件人在同一租户中，则从 Teams 发起的聊天和通话会进入 Teams。
- 从 Skype for Business 发起的聊天和通话总是在 Skype for Business 中进行。

联合聊天可以是本机线程，也可以是互操作线程。 请参阅 [互操作与本机对话线程](#interop-versus-native-conversation-threads)。

- 如果接收方和发送方都处于 TeamsOnly 升级模式，对话将是一种本机的聊天体验，其中包括所有富消息和呼叫功能。 如果要了解更多信息，请阅读 [Teams 中外部 (联合) 用户的本机聊天体验](native-chat-for-external-users.md)。 

- 如果对话参与者中的任何一个不处于 TeamsOnly 升级模式下，对话仍然是一个纯文本消息的互操作体验。 用户界面以类似于同租户互操作线程的方式公开联合聊天，只是有一个表明用户来自外部的说明。

有关详细信息，请参阅 [管理 Microsoft Teams 中的外部访问](manage-external-access.md) 和 [Teams 中外部 (联合) 用户的本机聊天体验](native-chat-for-external-users.md)。

### <a name="contacts"></a>联系人

Teams 和 Skype for Business 有单独的联系人列表。 这意味着在一个系统中进行的联系人添加、删除和修改不会同步到另一个系统。 然而，当发生两个特定事件中的任何一个时，Skype for Business 中的联系人会自动复制到 Teams 中: 

- 对于任何 Skype for Business Online 用户来说，他们第一次登录 Teams 时，都将复制 Skype for Business 中的联系人到 Teams 中。  在 Skype for Business Server 中拥有本地账户的用户无法使用此行为。  

- 当用户升级到 TeamsOnly 后 (通过指定 TeamsUpgradePolicy 或通过 Move-CsUser -MoveToTeams)，下次用户登录 Teams 时，Skype for Business 中的现有联系人将与 Teams 中已有的联系人合并。 无论用户从本地还是联机移动到 TeamsOnly，都会发生此行为。 

在这两种情况下，从 Skype for Business 到 Teams 的联系人传输是异步的，因此可能要过几分钟才能在 Teams 中出现联系人。 以上两个事件就是触发副本的原因。  

### <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
