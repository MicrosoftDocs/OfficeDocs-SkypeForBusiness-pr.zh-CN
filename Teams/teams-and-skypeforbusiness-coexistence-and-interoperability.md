---
title: 了解 Microsoft Teams 和 Skype for Business 共存和互操作性
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Business 和 Microsoft Teams 共存选项的详细信息，以及 Skype for Business 和 Teams 之间的最终互操作性。
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
ms.openlocfilehash: adefa7a7ca948363f3d331c4500619e81bbc1ea8
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460602"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>了解 Microsoft Teams 和 Skype for Business 共存和互操作性

![升级过程图，强调项目定义阶段](media/upgrade-banner-project-definition.png "升级旅程的阶段，强调项目定义阶段")

本文是升级过程的项目定义阶段的一部分。 创建赞助联盟和项目团队并定义项目的范围、目标和计划后完成。 在继续之前，请确认已完成以下活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [定义项目范围](https://aka.ms/SkypetoTeams-Scope)

如果你的组织现在使用 Skype for Business，并且你开始将 Teams 与 Skype for Business 一起使用，或者你开始升级到 Teams，则了解这两个应用程序如何共存、它们何时以及如何互操作，以及如何管理用户从 Skype for Business 到 Teams 的最终升级，这一点非常重要。

> [!Tip]
> 观看以下会话，了解 [共存和互操作性](https://aka.ms/teams-upgrade-coexistence-interop)。
>
> 此外，你可以与我们一起参加实时交互式研讨会，我们将分享指导、最佳做法和资源，旨在开始升级规划和实施。
>
> 首先 [加入"计划升级](https://aka.ms/SkypeToTeamsPlanning) 会话"以开始。

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Teams 和 Skype for Business 的共存概述

以下部分介绍决定升级到 Teams 时可用的共存模式，以及每个模式提供的功能。 此外，还介绍了 Skype-for-Business 客户端 (用户与 Teams 客户端上的用户之间发生的互操作) 互操作性，以及所选的共存模式对互操作的影响。

 Teams 提供协作功能、聊天、通话和会议功能。 根据你选择部署 Teams 的方式，这些功能可能会与 Skype for Business 为给定用户提供的功能重叠。 默认模式是运行功能重叠的 Teams 和 Skype for Business。 但是，可以为用户分配多个共存模式 (也称为升级模式) 之一，这些模式旨在确保这些功能不会与该用户 (重叠，在这种情况下，Teams 和 Skype for Business 之间的互操作性可用于) 。 例如，如果你拥有具有复杂 企业语音 部署的重要 Skype for Business Server 本地资产，但希望用户尽快享受现代会议，你可能希望将"会议第一"评估为备用[](meetings-first.md)路径。

建议查看以下共存模式，帮助确定适合组织的路径。

> [!Important]
> 引入新技术或对现有熟悉的 Skype for Business 环境进行更改，同时提供出色的新业务优势，可能会给用户造成干扰。 在实施本文中概述的任何更改之前，请花些时间评估用户准备情况并实施通信和培训计划。 此外，我们强烈建议在在整个组织中实施计划之前，先与选定的一组用户一起试点计划。

### <a name="islands-mode"></a>群岛模式

默认情况下，用户可以将 Teams 与 Skype for Business 一起作为提供类似和重叠功能的两个独立解决方案运行。 这些功能包括状态、聊天、呼叫和会议。 Teams 用户还可以利用新的协作功能，例如团队和频道、访问 Microsoft 365 或 Office 365 中的文件以及应用程序。

在此名为 **"** 群岛"的共存模式下，每个客户端应用程序都作为单独的岛屿运行。 Skype for Business 与 Skype for Business 交谈，Teams 与 Teams 交谈。 用户应会一切运行这两个客户端，并且可以在启动通信的客户端中以本机方式进行通信。 因此，在群岛模式下不需要 **互操作性** 。

为了避免令人困惑或回归的 Skype for Business 体验，Skype for Business 会处理以下未在 Teams **Islands** 模式下处理的集成：

- 外部 (联合) 通信。
- PSTN 语音服务和语音应用程序，Office 集成。
- USB 设备的 HID 控件。
- 其他几个集成。  

在群岛模式下，Teams 不支持 **电话** 系统。 **群岛** 模式不支持 skype for Business 企业语音客户端。

> [!Important]
> 在 **群岛** 模式下，来自联合用户的所有消息和呼叫 (组织外部) 发送到 Skype for Business。 升级到"仅 **Teams"** 模式后，来自组织外部的所有消息和呼叫将传递到 Teams。

> [!Tip]
> Skype for Business Online 客户建议的路径是先使用默认 **群岛** 模式，推动组织中 Teams 的采用饱和，然后快速转移到 **Teams Only** 模式。 本地和混合客户（尤其是复杂的客户）可能受益于将 **Skype for Business** 与 Teams 协作模式（而不是岛屿模式）部署为起点，从该模式到 Teams 协作和会议模式 (即会议第一个) （如果适用）的 Skype **for Business，** 以及组织准备好采用 Teams 时到 **Teams** Only 模式。

### <a name="teams-only"></a>仅 Teams

仅 **Teams** 用户 (升级 *的用户*) 有权访问 Teams 中的所有功能。 他们可以保留 Skype for Business 客户端以加入由未升级的用户或外部方组织的 Skype for Business 会议。 升级后的用户可以继续使用 Teams 与 Skype for Business (之间的互操作性功能与组织中仍在使用 Skype for Business 的其他用户进行通信 (只要 Skype for Business 用户不处于群岛模式) 。 但是，升级后的用户无法启动 Skype for Business 聊天、通话或会议。

组织准备好让部分或所有用户使用 Teams 作为唯一的通信和协作工具后，即可将这些用户升级到 **"仅 Teams"** 模式。 如果要从群岛模式升级，我们建议在开始升级过程之前，先使整个组织的 Teams 采用饱和。 这种采用可避免由于群岛模式未提供互操作性而中断的通信方案。

在 **Teams Only** 模式下，Teams 是 SIP/Tel 协议的默认应用。 Teams 将处理 Outlook 中用户联系人卡片中用于呼叫或聊天的链接。

有关迁移到 Teams Only 模式的额外 **注意事项**，请参阅 ["仅 Teams 模式注意事项"。](teams-only-mode-considerations.md)

![Teams 确认消息的屏幕截图](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "将用户升级为仅 Teams 用户后以特殊模式运行的 Skype for Business 客户端")

### <a name="skype-for-business-only"></a>仅 Skype for Business

在此共存模式下，用户仍使用 Skype for Business（而不是 Teams）进行聊天、会议以及通话功能，并且不会将 Teams 用于团队和频道。 此模式目前可用;但是，在当前实现中，不会自动为用户关闭团队和频道。 这可以通过使用应用设置策略隐藏团队和文件实现。

在开始 Teams 的托管部署之前，可以使用此模式，以防止用户在做好构建准备之前开始使用 Teams。 此模式也是一种为 Skype for Business 用户启用经过身份验证的 Teams 会议参与的方式，但用户已获得 Teams 许可。

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business 与 Teams 协作

使用此模式在你的环境中引入 Teams，同时继续使用 Skype for Business 中的现有投资。 让 Skype for Business 在聊天、通话和会议功能方面保持不变。 添加 Teams 协作功能：

- 团队和频道。
- 访问 Microsoft 365 或 Office 365 中的文件。
- 应用程序。 Teams 通信功能 - 私人聊天、通话和安排会议。

在此模式下，Teams 私人聊天、通话和安排会议默认关闭。

如果以本地或混合版 Skype for Business Server 为起点的组织希望为用户提供通信的互操作性和可预测性，并且具有可预测的升级到 Teams (的时间线，而不是依赖于群岛模式) 中的采用饱和，则组织应考虑采用此模式作为群岛模式的替代模式。 

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business 与 Teams 协作和会议，也称为会议第一

使用此共存模式可加快组织中 Teams 会议与协作功能的可用性。 共存模式允许用户利用出色的 Teams 会议体验：

- 优质。
- 听录和翻译。
- 背景模糊。
- 在所有平台（包括移动设备和浏览器）上提供卓越的用户体验。

除了在此模式下使用 Teams 进行基于团队和频道的对话外，用户还将使用 Teams 安排和召开会议。 私人聊天和通话仍保留在 Skype for Business 上。 Teams 和 Skype for Business 受益于一系列"更好的协作"功能，例如状态对帐、自动保留/取消保留，以及跨这两个应用程序的 HID 设备支持。 如果需要，可以隐藏团队和频道，使用应用设置策略。

此共存模式特别适用于使用 Skype for Business 本地部署企业语音。 这些组织可能需要一些时间升级到 Teams，并想要尽快从高级 Teams 会议中获益。

> [!TIP]
> 若要根据你在 Skype for Business 仍在使用时在 Teams 中启用的功能帮助确定建议的升级模式，请利用 [Skype 到 Teams](https://aka.ms/SkypeToTeamsWizard)升级向导。

有关共存模式、先决条件和管理详细信息，请参阅将 Teams 与 [Skype for Business](https://aka.ms/SkypeToTeams-Interop) 一起用于组织的迁移和互操作性指南，以及设置共存和 [升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)。

|"决策点"图标 |图标定义 |说明 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|决策点|<ul><li>哪种共存 () 最适合组织和用户的需求？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|后续步骤|<ul><li>选择升级过程的最佳方法。</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 和 Skype for Business 的互操作性

互操作性是同一组织中 Teams 和 Skype for Business 用户跨 Teams 和 Skype for Business 进行通信的能力。

互操作性受共存模式约束 (也称为接收方的) 模式。 接收器在群岛模式下时 **没有互操作性。**

> [!Note]
> 在除群岛以外的任何共存模式下部署时，Teams 和 Skype for [](#interoperability-of-teams-and-skype-for-business)Business 可以互操作，使用户能够相互聊天和呼叫，并确保在升级到 Teams 期间，整个组织的通信保持流畅。 共存模式控制互操作性。 接收方的共存模式决定了互操作性是否可用。 例如，如果接收方在一个客户端中聊天仅在一个客户端中可用 (例如 Teams) ，则通常提供聊天互操作性，以防发起程序使用另一个客户端 (在这种情况下，Skype for Business) 启动聊天。 另一方面，如果接收方在两个客户端和岛屿模式 (都可用聊天) ，则互操作性将不适用于聊天。 接收方将在发起程序启动聊天的同一客户端中接收消息。 因此，在群岛模式下进行 **适当的** 通信需要 Teams 采用饱和;也就是说，所有用户都主动使用和监视这两个客户端。

> [!Note]
> **若要获得最新的共存体验，客户端版本必须是用户的 Office 部署通道中的最新可用客户端。**

#### <a name="native-interop-and-interop-escalation"></a>本机互操作和互操作升级

有两种类型的互操作体验：本机升级和互操作升级。

- 用户 _当前使用的_ 客户端中会发生本机互操作体验。 一个用户将在 Skype for Business 客户端中，另一个用户在 Teams 中。 本机互操作体验不会将它们带到另一个客户端进行通信。 用户能够在他们当前使用的客户端中执行其对话。 本机互操作体验是一对一聊天和通话。
- 互 _升级_ 体验意味着，作为帮助用户执行高级操作 (（例如共享其桌面) ）的一部分，客户端有助于创建用户可以加入的会议以继续该会议的体验。 会议是在操作发起程序平台上创建的。 不位于该平台上的用户将收到会议加入链接。 单击此链接时，他们将在兼容的客户端中加入会议 (浏览器、Web 应用或完整客户端，具体取决于配置) 。 从 Skype for Business 进行互操作升级需要最近的客户端。 Teams 的互操作升级现已可用。 租户内互操作性体验和跨租户联合通信支持这两者。

#### <a name="native-interop-experiences"></a>本机互操作体验

根据为用户分配的共存模式 (如前面所述) ，提供以下本机互操作体验：

Skype for Business 用户可以与 Teams 用户进行一对一聊天，反之亦然。 互操作聊天需要经过属于 Teams 云服务门户的互操作网关 (因此仅存在于联机) 。 互操作聊天是纯文本：不支持富文本和图释。 Teams 和 Skype for Business 中的用户将收到对话是互操作对话的通知。

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business 用户可以向 Teams 用户进行一对一语音和视频通话，Teams 用户可以执行相同的调用。

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 使用 Skype for Business 本地部署实现互操作体验需要本地环境与 Microsoft 365 或 Office 365 Skype for Business 采用混合模式。 有关详细信息，请参阅 [迁移和互操作性指南](https://aka.ms/SkypeToTeams-Interop)。

这些互操作体验适用于分配了以下共存模式之一的用户和用户之间：Teams 协作的 **Skype for Business、Teams** 协作和会议的 **Skype for Business、****仅 Skype for Business** 或 **仅 Teams。** 在群岛模式下，用户没有 **互操作性** 。

#### <a name="native-interop-experience-limitations"></a>本机互操作体验限制

由于协议和技术的差异，无法原生支持所有功能。 具体而言，以下功能不可用：

- Teams 或 Skype for Business 不支持 Markdown、富文本和完整图释集。 Teams 聊天中撰写框的其他本机功能不受支持。
- 本机不支持 (Teams) Skype for Business 之间的桌面或应用共享屏幕共享。 但是，通过互操作升级支持它。
- Teams 中 (群对话) 群组聊天只能包括使用 Teams 的参与者。
- Skype for Business (群组聊天) 即时消息对话只能包括使用 Skype for Business 的参与者。 但是，可从 Skype for Business 向多方进行互升级。
- 不支持将正在进行的对等语音或视频呼叫升级到涉及 Teams 和 Skype for Business 用户的多方呼叫。
- 不支持将两方聊天的文件传输或群组聊天中的文件附件从 Teams 转移到 Skype for Business，反之亦然。
- Skype for Business 持久聊天没有互操作性。

对于所有这些限制 (持久聊天) ，一种可能的解决方法是让一个用户启动会议并邀请其他用户加入会议。

此解决方法是互操作升级的基础。 具体而言，屏幕共享和升级到多个部分在本机无法实现，但通过互操作升级支持。

#### <a name="interop-escalation-experiences"></a>互操作升级体验

互操作升级包括使用托管的会议升级来补充本机互操作功能。 会议为任何人提供丰富的体验，无论他们拥有哪个客户端。

当 Teams 用户触发互操作升级时，将创建一个 Teams 会议。 当 Skype for Business 用户触发时，将创建 Skype for Business 会议。 在这两种情况下，创建的会议 **都是"现在** 开会"会议，不会反映在用户的日历中。

另一方通过互聊天接收会议加入链接，并通过单击该链接加入。 如果 Skype for Business 用户具有 Teams 帐户并且受 Teams 用户邀请，他们将加入经过身份验证的会议。 否则，他们将以匿名参与者身份加入。 相反，Teams 用户几乎总是拥有 Skype for Business 帐户和 Skype for Business 客户端，他们可以使用该帐户以经过身份验证的参与者身份加入 Skype for Business 会议，但他们也可能以匿名参与者身份加入，例如使用 Skype 会议应用。

当参与方加入会议后，他们可以执行会议中支持的任何活动，例如桌面或内容共享、文件共享或传输、添加其他参与者等。

#### <a name="interop-escalation-from-skype-for-business"></a>从 Skype for Business 进行互操作升级

Skype for Business 的互操作和互升级在 2019 年 7 月内部版本（每月 C2R）中进行了更新。 以前，Skype for Business 没有提前意识到远程聚会正在使用 Teams。 它仅从建立会话后收到的信号中推测出。

当信号指示响应来自 (或) 互操作网关时，它将显示黄色业务栏 (横幅) 指示另一方未使用 Skype for Business。 随着我们服务的演进，这导致误报，其中 Skype for Business 用户在连接到云语音邮件服务或其他云语音服务时会看到业务栏，而不是实际的 **仅 Teams 用户** 。

为了防止这些误报，当另一方是"仅 **Teams"** 实际用户时，状态服务现在通知 Skype for Business 客户端。 这使 Skype for Business 能够知道，需要先创建互操作对话，然后创建特定于互操作的对话窗口。

![用于创建与 Skype for Business 用户的互操作对话的 Teams 消息的屏幕截图](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

例如，如果 Skype for Business 用户想要共享其桌面，将通知他们我们将启动一个会议并引导完成这些步骤。

![Teams 消息的屏幕截图，显示开始与 Teams 用户的会议](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

同时，Teams 用户将收到包含会议链接的传入聊天消息，并引导其加入。

此升级为 Skype for Business 会议适用于租户内互操作和跨租户联合呼叫和聊天。 它默认为打开状态，并且管理员无需设置任何设置。

#### <a name="interop-escalation-from-teams"></a>Teams 的互操作升级

Teams 用户在与 Skype for Business 用户或跨租户互操作联合线程的租户内互操作线程中选择桌面共享按钮时，现在可以从 Teams 互升级到 Teams 会议。 1 对 1 聊天聊天或 1：1 通话支持互操作升级。

支持内容共享的浏览器上的 Teams 桌面客户端、适用于 Mac 的 Teams 桌面客户端和 Teams Web 客户端支持此功能，同时与任何 Skype for Business 客户端版本通信。

在互操作性线程和联合互操作性线程中，Teams 用户现在具有用于启动内容 (按钮) 控件。 当 Teams 用户选择该按钮时，他们将看到一个附加菜单，通知他们共享内容，他们需要启动 Teams 会议。

如果用户在通话中，菜单还会警告他们 Teams 和 Skype for Business 之间的当前通话将在他们进入 Teams 会议时终止。 如果他们选择，他们可以在接受 Skype for Business 用户之前发出警告。

![用于与 Skype for Business 用户共享会议的团队消息的屏幕截图](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

接受后，他们将进入 Teams 会议;他们必须从会议中的共享托盘开始共享。

同时，Skype for Business 用户将收到一条传入的聊天消息以及指向会议的链接，并引导其加入。

此升级为 Teams 会议适用于租户内互操作和跨租户联合呼叫和聊天。 它默认为打开状态，并且管理员无需设置任何设置。 但是，如果管理员将其设置到 .，则用户已关闭 ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` 它 ``$false`` 。

查看本文后，请参阅"选择[升级](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)过程、迁移和[互操作性](https://aka.ms/SkypeToTeams-Interop)指南"、与[Skype for Business](coexistence-chat-calls-presence.md)共存，[](https://aka.ms/SkypeToTeams-SetCoexistence)以及设置共存和升级设置，了解实现详细信息。 我们还建议观看以下视频[：视频：管理 SfB](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)和 Teams 之间的共存和互操作性

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Teams 和 Skype for Business 共存的技术详细信息

以下部分汇总了在同一组织中同时运行 Teams 和 Skype for Business 客户端时可能遇到的行为，无论使用哪种模式和升级方法：

- [会议](#meetings)
- [互操作性](#interoperability)
- [互操作与本机聊天线程](#interop-versus-native-conversation-threads)
- [状态](#presence)
- [联合身份验证](#federation)
- [联系人](#contacts)

### <a name="meetings"></a>会议

无论用户的模式如何，用户始终可以加入受邀参加的任何类型的会议，无论是 Skype for Business 还是 Teams。  但是，用户必须使用与会议类型匹配的相应客户端加入会议：

- 如果会议是 Teams 会议，则所有参与者 (TeamsOnly、Islands 还是 Skype for Business 用户) 使用 Teams 客户端加入会议。 如果未安装 Teams，用户在尝试加入会议时将被定向到 Web。

- 如果会议是 Skype for Business 会议，则所有参与者 (TeamsOnly、Islands 或 Skype for Business 用户) Skype for Business 客户端加入会议。 如果未安装 Skype for Business 客户端，用户将被定向到 Web 以通过 Skype 会议应用加入。

组织会议时，安排的会议类型基于组织者的模式，如下表所示：

| 组织者模式    |      行为 |
| :------------------ | :---------------- |
| TeamsOnly、SfbWithTeamsCollabAndMeetings |    Teams 中安排的所有会议。 Skype for Business 加载项在 Outlook 中不可用。 | 
| SfbWithTeamsCollab、SfbOnly   | Skype for Business 中安排的所有会议。 Teams 加载项在 Outlook 中不可用。 | 
| 孤岛 | 默认情况下，可以在 Skype for Business 或 Teams 中安排会议。 这两个加载项在 Outlook 中均可用。 但是，可以选择性地要求群岛中的用户始终通过分配具有 PreferredMeetingProviderForIslandsMode=Teams 的 TeamsMeetingPolicy 实例，在 Teams 中安排会议。| 


### <a name="interoperability"></a>互操作性

如上所述，在 [Teams](#interoperability-of-teams-and-skype-for-business)和 Skype for Business 的互操作性中，Teams 支持在某些情况下与 Skype for Business 互操作。 互操作通信是指 Skype for Business 用户与 Teams 用户之间的聊天或通话。  只能在两个用户之间实现互操作通信;不支持多方聊天/呼叫或添加其他用户。

当以下每一项都成立时，将创建两个用户之间的互聊天或通话：

- 一个用户正在使用 Teams，另一个用户使用 Skype for Business。

- 初始通信的接收者模式不是群岛 (否则，如果两个用户位于同一组织) 通信将位于同一客户端中。 在联合方案中，发送用户使用的是 Teams，收件人不采用 TeamsOnly 模式。 

- Teams 用户没有本地的 Skype for Business 帐户。

在互操作通信中，聊天是纯文本的。 此外，互操作聊天本身无法进行文件共享和 *屏幕共享*。 但是，互操作对话中的用户可以通过在互操作聊天内创建按需会议轻松实现文件和/或屏幕共享，如下所述：

- 如果 Teams 用户尝试共享其屏幕，将自动创建一个按需 Teams 会议，并且该会议的邀请链接将发送到 Skype for Business 用户的客户端。 单击链接后，Skype for Business 用户将打开 Teams 并加入会议。 这两个用户现在都参加 Teams 会议，并可以根据需要共享。

- 如果 Skype for Business 用户从 2018 年或以后使用客户端并尝试共享任何内容，则会自动创建按需 Skype for Business 会议，并且该会议的邀请链接将发送到 Teams 用户的客户端。 单击该链接后，Teams 用户将尝试加入 Skype for Business 会议。 如果 Teams 用户已安装 Skype for Business 客户端，它将打开，并且提示用户 (（如果尚未登录) ）。  如果 Teams 用户未安装 Skype for Business 客户端，系统会提示用户使用 Web 版本。 两个用户登录后，他们将参加 Skype for Business 会议，并可以根据需要共享。

### <a name="interop-versus-native-conversation-threads"></a>互操作与本机聊天线程

由于互操作通信不支持本机 Teams 对话的所有功能，因此 Teams 客户端为 Teams 到 Teams 和 Teams 到 Skype for Business 通信维护单独的会话线程。 这些对话在用户界面中的呈现方式不同：互操作线程可通过以下方式与常规本机 Teams 线程进行区分：

- 缺少对富文本、文件/屏幕共享的控件，无法添加用户。
- 对目标用户的图标的修改，显示 Skype for Business 的"S"。

以下屏幕截图显示了这些差异：

与用户 G3 测试的本机 Teams 到 Teams 对话

![显示本机 Teams 到 Teams 对话的图表](media/teams-upgrade-native-thread.png)

使用同一个用户 G3 测试的互操作聊天

![显示 Teams 到 Teams 对话互操作示意图](media/teams-upgrade-interop-thread.png)

创建会话线程后，其类型永远不会更改。 创建后，Teams 中的互操作线程将始终路由到目标用户的 Skype for Business 客户端。 本机线程将始终路由到目标用户的 Teams 客户端。  如果收件人用户的模式发生更改，该用户的现有 Teams 线程将不再工作，该聊天上会显示一条注释，并包含用于启动新本机对话的链接，如以下屏幕截图所示。

![显示与已升级的 Skype for Business 用户聊天的示意图](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>状态

给定用户的存在基于用户通过客户端在服务中的活动。 然后发布状态，供其他用户查看。  Skype for Business 和 Teams 是具有单独客户端的单独服务，因此每个服务都有自己的用户状态。   Teams 和 Skype for Business Online 中的状态服务之间也有同步。  这允许一个服务根据需要从另一个服务中发布用户。 

状态发布行为基于用户的模式。 有三个基本情况：

- 如果用户在 TeamsOnly 模式下，则所有其他用户都会看到该用户的 Teams 状态，无论他们使用哪个客户端。

- 如果用户采用任何 Skype for Business 模式，则无论该用户使用哪个客户端，所有其他用户都会看到该用户的 Skype for Business 状态。

- 如果用户在群岛模式下，Skype for Business 和 Teams 中发布的状态是独立的，因此向同一组织内的用户显示的存在将取决于其他用户的客户端。 联盟组织的用户将基于其 Skype for Business 活动看到该用户的存在，因为到群岛模式用户的联合流量进入 Skype for Business。

例如，假设用户 A 在群岛模式下。 如果用户 A 在 Teams 中处于活动状态，但没有登录到 Skype for Business，其他用户将看到用户 A 从 Teams 客户端处于活动状态，但在其 Skype for Business 客户端中，他们将用户 A 视为脱机。 这是设计使的，因为如果用户未运行客户端，则无法访问用户 A。 


### <a name="federation"></a>联合身份验证

使用 Skype for Business 从 Teams 联合到其他用户需要 Teams 用户在 Skype for Business 中在线进行家庭。 TeamsUpgradePolicy 控制传入的联合聊天和呼叫的路由。 联合路由行为与同租户方案相同，在群岛模式下除外。 当收件人位于群岛模式时：

- 如果收件人在联合租户中，则从 Teams 发起的聊天和呼叫将登陆 Skype for Business。
- 如果收件人位于同一租户中，则从 Teams 发起的聊天和呼叫将登陆 Teams。
- 从 Skype for Business 发起的聊天和通话始终位于 Skype for Business 中。

联合聊天可以是本机线程或互操作线程。 请参阅 [互操作与本机聊天线程](#interop-versus-native-conversation-threads)。

- 如果接收方和发送方都同时在 TeamsOnly 升级模式下，则聊天将是一种本机聊天体验，其中包含所有丰富的消息传送和呼叫功能。 若要了解有关详细信息，请阅读 Teams 中 ([用户) 本机聊天体验](native-chat-for-external-users.md)。 

- 如果任一对话参与者未处于 TeamsOnly 升级模式，则对话仍具有纯文本消息的互操作体验。 用户界面以与同租户互操作线程类似的方式公开联合聊天，不过有一条说明指出用户是外部用户。

有关详细信息，请参阅 ["管理 Microsoft Teams](manage-external-access.md) 中的外部访问"和 Teams 中外部用户 ([联合) 本机聊天体验](native-chat-for-external-users.md)。

### <a name="contacts"></a>联系人

Teams 和 Skype for Business 有单独的联系人列表。 这意味着，在一个系统中所做的接触添加、删除和修改不会同步到另一个系统。 但是，当发生两个特定事件之一时，来自 Skype for Business 的联系人会自动复制到 Teams： 

- 任何 Skype for Business Online 用户首次登录 Teams 时，Skype for Business 中的联系人都将复制到 Teams。  此行为不适用于在 Skype for Business Server 中具有本地帐户的用户。  

- 通过分配 TeamsUpgradePolicy 或 Move-CsUser -MoveToTeams) 将用户升级到 TeamsOnly (后，用户下次登录 Teams 时，Skype for Business 中的现有联系人将与 Teams 中的现有联系人合并。 无论用户的 Skype for Business 帐户是在本地还是联机，都会发生此行为。 

在这两种情况下，将联系人从 Skype for Business 转移到 Teams 是异步的，因此可能需要几分钟时间，联系人才能显示在 Teams 中。 上面的两个事件是触发复制的事件。  

### <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[在 Skype for Business Server 与 Microsoft 365 或 Office 365 之间配置混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
