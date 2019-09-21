---
title: Microsoft 团队 |升级、孤岛模式、互操作策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Skype for business 和 Microsoft 团队共存选项以及 Skype for Business 和团队之间的互操作性的详细信息。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 16defcd2cd5a855cbc3713f5a35886bb936c5a45
ms.sourcegitcommit: 299f854bbb73887ba315b09b9adf9ea9ff91e8ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37062968"
---
![升级旅行图，强调项目定义阶段](media/upgrade-banner-project-definition.png "升级旅行的阶段，重点关注项目定义阶段")

本文是你的升级过程的项目定义阶段的一部分，在你创建赞助联盟和项目团队并为你的项目定义范围、目标和构想之后，你完成了一个活动。 继续之前，请确认你已完成以下活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>了解 Microsoft 团队和 Skype for business 共存和互操作性

如果您的组织目前使用 Skype for Business，并且您开始使用多个团队和 Skype for business，或者您开始升级到团队，那么了解这两个应用程序是如何共存、何时以及如何进行互操作，以及如何管理用户的迁移一直到最终从 Skype for Business 升级到团队。

> [!Tip]
> 观看以下会话以了解[共存和互操作性](https://aka.ms/teams-upgrade-coexistence-interop)。
>
> 此外，您可以加入我们的实时交互式研讨会，我们将分享指南、最佳做法和资源，以便开始开始升级规划和实施。
>
> 首先加入[升级](https://aka.ms/SkypeToTeamsPlanning)会话的计划以开始使用。

## <a name="coexistence-of-teams-and-skype-for-business"></a>团队和 Skype for business 的共存

除了协作功能之外，团队还提供聊天、通话和会议功能。 根据你选择的部署团队的方式，这些功能可能与特定用户的 Skype for Business 所提供的功能重叠。 默认模式是与 Skype for Business 一起运行具有这些功能重叠的团队;但是，可以为用户分配几种共存模式（也称为升级模式）之一，以确保这些功能不会与该用户重叠（在这种情况下，团队和 Skype for business 之间有互操作）。 例如，如果您的 Skype for Business 服务器本地资源有复杂的企业语音部署，但希望您的用户尽可能快地体验新式会议，您可能希望[先将会议](meetings-first.md)评估为备用会议路径.

我们建议你查看以下共存模式，以帮助确定哪种路径适合你的组织。

> [!Important]
> 向用户提供新技术或对现有的、熟悉的 Skype for business 环境进行更改，同时为用户带来巨大的新业务好处。 在实施本文中所述的任何更改之前，请花一些时间来评估用户准备情况并实施通信和培训计划。 此外，我们强烈建议你先使用选定的一组用户试验你的计划，然后再在你的组织中实施。

### <a name="islands-mode"></a>孤岛模式

默认情况下，用户可以将 Skype for Business 中的团队作为两个单独的解决方案一起运行，提供类似的和重叠的功能，如状态、聊天、通话和会议。 团队用户还可以利用新的协作功能，如团队和频道、访问 Office 365 中的文件和应用程序。

在此共存模式（名为 "**岛**"）中，每个客户端应用程序都作为单独的岛运行。 Skype for business 与 Skype for Business 交谈，团队与团队进行协作。 用户应始终运行这两个客户端，并且可以在发起通信的客户端中以本机方式进行通信。 因此，无需在**孤岛**模式下实现互操作。

为避免令人困惑或 regressed 的 Skype for business 体验、外部（联合）通信、PSTN 语音服务和语音应用、Office 集成、USB 设备的 HID 控件以及其他一些其他集成将继续由 Skype 处理适用于企业，并且在**孤岛**模式下的团队中不可用。 在**孤岛**模式下，团队不支持电话系统。在此模式下，唯一的企业语音客户端是 Skype for business。

> [!Important]
> 在 "**孤岛**" 模式下，来自联盟用户（组织外部的人员）的所有消息和呼叫都将发送到 Skype for business。 升级到 "**仅限团队**" 模式后，您的组织外部的所有消息和呼叫都将发送给团队。

> [!Tip]
> Skype for Business Online 客户推荐的路径是从默认的**孤岛**模式开始，推动团队在组织中采用饱和，然后快速转到 "**仅团队**" 模式。 在本地和混合客户（尤其是复杂的客户）中，**使用团队协作模式将 Skype For business**部署为一个起点，而不是**孤岛**模式，并通过 skype for business 进行**团队协作和会议**模式（即 "首先会议"），如果需要，和 "**仅限团队**" 模式，而组织准备好采纳团队。

### <a name="skype-for-business-only"></a>仅限 Skype for business

在此共存模式下，用户将保留在 Skype for Business 中，而不是团队-用于聊天、会议和呼叫功能，并且不使用团队和频道团队。 目前可以使用此模式;但是，在当前实现中，团队和频道不会自动为用户关闭。 可通过使用应用权限策略隐藏团队和频道来实现此目的。

此模式可以在启动团队的托管部署之前使用，以防止用户开始使用已建立准备就绪的团队，或作为在适用于 Skype for business 用户的团队会议中启用身份验证参与的方法（前提是用户为团队授权。

### <a name="teams-only"></a>仅限团队


> [!IMPORTANT]
> 如果你在将用户移动到 "**仅团队**" 模式后卸载 Skype for business 客户端，联机状态将在 Outlook 和其他 Office 应用中停止工作。 联机状态在团队中可以正常工作。 解决方法：若要在 Outlook （以及其他 Office 应用）中查看状态，必须安装 Skype for business，即使你是在 "**仅团队**" 模式下运行团队也是如此。 Microsoft 已意识到此问题，正在努力解决问题。


**只有团队**用户（也称为已*升级*用户）可以访问团队中的所有功能。 他们可以保留 Skype for Business 客户端，以便在已由非升级用户或外部团体组织的 Skype for business 上加入会议。 通过使用团队和 Skype for business 之间的互操作性功能，已升级的用户可以继续与仍在使用 Skype for business 的组织中的其他用户通信（前提是这些 Skype for business 用户不在孤岛中）。 **** 模式）。 但是，升级后的用户无法启动 Skype for Business 聊天、通话或会议。

一旦你的组织准备好让部分或所有用户使用团队作为唯一的通信和协作工具，你可以将这些用户升级到 "**仅团队**" 模式。 如果你从**孤岛**模式升级，我们建议你首先让团队在开始升级过程之前饱和整个组织中的团队。 这可避免由于**孤岛**模式不提供互操作而导致的通信方案中断。

有关移动到 "**仅团队**" 模式的其他注意事项，请参阅[仅团队模式注意事项](teams-only-mode-considerations.md)。

![团队确认消息的屏幕截图](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "在用户作为仅团队用户升级后，在特殊模式下运行的 Skype For business 客户端")

### <a name="skype-for-business-with-teams-collaboration"></a>具有团队协作的 Skype for Business

使用此模式可在你的环境中引入团队，同时继续利用 Skype for Business 中的现有投资。 在此模式下，你可以让 Skype for Business 保持不变，以便聊天、通话和会议功能，并添加团队协作功能-团队和频道，在 Office 365 和应用程序中访问文件。 团队通信功能（私人聊天、通话和安排会议）在此模式下默认情况下处于关闭状态。

在本地或混合使用 Skype for business Server 起点的组织，如果他们希望为其用户提供其通信的互操作性和可预测性，则应将此模式视为**孤岛**模式的备用模式，以及具有可预测的日程表，可预测其升级到团队（而不是在**岛**模式下依赖采纳饱和）。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>具有团队协作和会议的 Skype for business，也称为会议优先

除了协作功能外，还可使用此共存模式加速团队会议功能的可用性，使用户能够充分利用出色的团队会议体验-优质创新功能（如设备和翻译或后台模糊处理）和跨所有平台（包括移动设备和浏览器）的卓越用户体验。

在此模式下，与团队和基于频道的对话一起使用团队，用户将使用团队安排和开展会议。 Skype for Business 上的私人聊天和通话保持。 团队和 Skype for business 受益于一系列 "更好地协作" 功能，如状态对、自动保留/unhold 以及在两个应用程序中支持 HID 设备支持。 请注意，如果需要使用应用权限策略，则可以隐藏团队和频道。

此共存模式对于具有企业语音的 Skype for Business 本地部署的组织非常有用，他们很可能需要花费一些时间来升级到团队，并且希望尽快获得高级团队会议。

> [!Note]
> 在除**孤岛**之外的任何共存模式下部署时，团队和 Skype for business 可以进行[互操作](#interoperability-of-teams-and-skype-for-business)，使用户能够与他人聊天和相互通话，并确保在你的组织中进行升级迁移到团队。 共存模式控制互操作性。 接收方的共存模式确定互操作是否可用。 例如，如果接收器处于一种模式下，聊天仅在一台客户端（如团队）中可用，则在发起方使用其他客户端（在此情况下为 Skype for Business）开始聊天时，聊天互操作性通常将可用。 另一方面，如果接收器处于可在两个客户端（即孤岛模式）中提供聊天的模式，则不能对聊天提供互操作。 接收方将在发起聊天的同一客户端中接收消息。 因此，在 "**孤岛**" 模式下正确通信需要团队采用饱和。也就是说，所有用户主动使用和监视这两个客户端。

> [!TIP]
> 若要帮助在 Skype for Business 仍在使用时根据希望在团队中启用的功能确定推荐的升级模式，请利用[skype To 团队升级向导](https://aka.ms/SkypeToTeamsWizard)。

有关共存模式、先决条件和管理的更多详细信息，请参阅使用团队与 Skype for Business 结合使用和[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)[的组织的迁移和互操作指南](https://aka.ms/SkypeToTeams-Interop)。

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|决策点|<ul><li>哪种共存模式最适合你的组织和用户的需要？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|后续步骤|<ul><li>选择升级旅程的最佳方法。</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>团队和 Skype for business 的互操作性

互操作性是团队和 Skype for business 用户在团队和 Skype for business 之间通信的能力。

互操作性由接收方的共存模式（也称为升级模式）控制。 接收器处于**孤岛**模式时，没有互操作性。

### <a name="native-interop-and-interop-escalation"></a>本机互操作和互操作升级

有两种类型的互操作体验：本机和互操作提升。

- 用户当前正在使用的客户端中出现_本机互操作_体验。 一个用户将位于 Skype for Business 客户端，另一个用户位于团队中。 本机互操作体验不会将它们转到另一个客户端进行通信，用户将能够在当前使用的客户端中执行其对话。 本机互操作体验是一对一的聊天和通话。
- _互操作提升_体验意味着，在帮助用户执行高级操作（如共享其桌面）的过程中，客户端有助于创建用户可加入的会议，以便在该会议中继续体验。 将在操作发起人的平台上创建会议。 不在该平台上的用户将收到会议加入链接。 当他们单击此链接时，会将其加入到兼容的客户端（浏览器、web 应用或完整客户端中，具体取决于配置）。 Skype for Business 的互操作性提升需要最近的客户端。 来自团队的互操作性提升现已推出。 两者均受租户中的互操作性体验和联合通信交叉租户支持。

### <a name="native-interop-experiences"></a>本机互操作体验

根据分配给用户的共存模式（如前面所述），可以使用以下本机互操作体验：

Skype for Business 用户可以与团队用户一对一聊天，反之亦然。 互操作性聊天需要通过 "互操作网关"，这是团队云服务的一部分（因此仅在联机状态下才存在）。 互操作聊天为纯文本：不支持格式文本和表情符号。 已通知团队和 Skype for business 中的用户对话是互操作对话。

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business 用户可以与团队用户进行一对一的语音和视频通话，反之亦然。

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 使用 Skype for Business 的本地部署的互操作体验要求本地环境处于 Office 365 Skype for Business 的混合模式中。 有关详细信息，请参阅[迁移和互操作性指南](https://aka.ms/SkypeToTeams-Interop)。

这些互操作体验在以下情况下适用于已分配以下共存模式之一的用户： **skype for business 与团队协作**、**使用团队协作和会议的 skype**for business、skype for business、skype for business **** 仅限企业或**团队**。 在**孤岛**模式下不存在与用户的互操作性。

### <a name="native-interop-experience-limitations"></a>本机互操作体验限制

由于协议和技术之间的差异，因此不能以本机方式支持所有功能。 具体说来，以下功能不可用：

- 标记、格式文本和完整的表情符集不受团队或 Skype for business 支持。 不支持团队聊天中撰写框的其他本机功能。
- 团队和 Skype for business 之间的屏幕共享（桌面或应用共享）本身不受支持。 但是，它通过互操作提升进行支持。
- 团队中的群组聊天（多方对话）只能包括使用团队的参与者。
- Skype for Business 中的多方 IM 对话（群组聊天）只能包括使用 Skype for business 的参与者。 但是，Skype for Business 可通过互操作提升到多方。
- 不支持与团队和 Skype for business 用户进行的多方呼叫（不支持正在进行的对等语音或视频呼叫。
- 不支持来自两方聊天的文件传输，或组聊天中的文件附件（从团队到 Skype for business，反之亦然）。
- Skype for Business 持久聊天没有互操作性。

对于所有这些限制（永久聊天除外），一种可能的解决方法是让一个用户启动会议并邀请其他用户加入会议。

此解决方法是互操作升级的基础。 特别是，对多方的屏幕共享和升级本身不可实现，但它们通过互操作提升进行支持。

### <a name="interop-escalation-experiences"></a>互操作提升体验

互操作性提升包含对与会议的托管升级的本机互操作功能的补充。 无论他们拥有哪种客户，会议都提供丰富的体验供任何人使用。

当团队用户触发互操作提升时，将创建团队会议。 当 Skype for Business 用户触发时，将创建 Skype for business 会议。 在这两种情况下，创建的会议都是 "**立即开会**" 会议，它不会反映在用户的日历中。
 
另一方通过单击该链接，通过互操作聊天和连接接收会议加入链接。 如果 Skype for Business 用户拥有团队帐户，并且被团队用户邀请，他们将加入经过身份验证的会议。 否则，它们将作为匿名参与者加入。 相反，团队用户几乎始终拥有 Skype for business 帐户和 Skype for business 客户端，他们可以使用它们将 Skype for Business 会议作为经过身份验证的参与者加入，但它们也可能作为匿名参与者加入，例如使用 Skype会议应用。

当双方加入会议后，他们可以在会议中执行任何受支持的活动，例如桌面或内容共享、文件共享或传输、添加其他参与者等。

#### <a name="interop-escalation-from-skype-for-business"></a>Skype for Business 中的互操作提升

Skype for Business 中的互操作性和互操作性升级已于7月2019日的 C2R 版本更新。 以前，Skype for business 没有事先意识到远程方在使用团队。 它仅 surmised 在建立会话后收到的信号。

当信号指示响应来自互操作网关（或通过）互操作网关时，它将显示黄色的业务栏（横幅），指示另一方未使用 Skype for Business。 随着我们的服务的发展，这会产生误报，在这种情况下，Skype for Business 用户在连接到云语音邮件服务或其他云语音服务时将看到业务栏，而不是实际的**团队**用户。
 
为了避免这些误报，联机状态服务现在将在另一方是一个**团队仅**是一个团队的实际用户时通知 Skype for business 客户端。 这使 Skype for business 能够意识到它需要在已创建的互操作对话中创建，并且对话窗口特定于互操作。

![使用 Skype for Business 用户创建互操作对话的团队消息的屏幕截图](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

如果 Skype for Business 用户想要共享其桌面，例如，他们将收到一则通知，告知我们我们将启动会议并引导完成步骤。

![团队消息的屏幕截图，用于与团队用户开始会议](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

同时，团队用户接收与会议的链接的传入聊天消息，并引导他们加入会议。

此对 Skype for business 会议的升级适用于租户互操作和互租户联合呼叫和聊天。 它在默认情况下处于打开状态，并且管理员尚未提供任何设置。

#### <a name="interop-escalation-from-teams"></a>来自团队的互操作提升

当团队用户在具有 Skype for Business 用户或跨租户互操作联合的线程中选择 "桌面共享" 按钮时，可从团队的互操作性升级到团队会议。 互操作性提升可通过1:1 聊天对话或从1:1 通话中进行支持。

在 Windows 的团队桌面客户端、适用于 Mac 的团队桌面客户端中以及团队 web 客户端的团队 web 客户端中，在与任何 Skype for Business 客户端版本通信时，该功能受支持。

在互操作性线程和联合身份验证互操作线程中，团队用户现在拥有控件（按钮）来开始内容共享。 当团队用户选择该按钮时，将显示一个附加菜单，通知他们共享内容，需要启动团队会议。

如果用户正在呼叫，则该菜单还会向他们发出警告，团队和 Skype for business 之间的当前通话将在他们加入团队会议时终止。 如果他们选择，他们可以在接受之前向 Skype for business 用户发出警告。

![与 Skype for Business 用户共享会议的团队消息的屏幕截图](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

接受后，他们将加入团队会议;他们必须从会议中的共享送纸器开始共享。
 
同时，Skype for Business 用户将收到一条传入聊天消息，其中包含指向会议的链接，并引导您加入会议。

此向团队会议的升级适用于租户互操作和跨租户联合呼叫和聊天。 它在默认情况下处于打开状态，并且管理员尚未提供任何设置。 但是，如果管理员设置``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy``为``$false``，将对用户关闭该功能。

查看本文后，请参阅[选择升级旅行](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[迁移和互操作性指南](https://aka.ms/SkypeToTeams-Interop)、[与 Skype for business 共存](coexistence-chat-calls-presence.md)，以及为实施[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)更多信息.

## <a name="related-links"></a>相关链接

[视频：管理 SfB 和团队之间的共存和互操作性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
