---
title: Microsoft 团队 |升级、孤岛模式、互操作策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Skype for business 和 Microsoft 团队共存选项以及 Skype for Business 和团队之间的互操作性的详细信息。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06655b8c43bb912409b2a1c6a42d7509f45bf651
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548794"
---
![升级旅行的阶段, 重点关注项目定义阶段](media/upgrade-banner-project-definition.png "升级旅行的阶段, 重点关注项目定义阶段")

本文是你的升级过程的项目定义阶段的一部分, 在你创建赞助联盟和项目团队并为你的项目定义范围、目标和构想之后, 你完成了一个活动。 继续之前, 请确认你已完成以下活动:

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>了解 Microsoft 团队和 Skype for business 共存和互操作性

如果您的组织目前使用 Skype for business, 并且您打算开始将团队与 Skype for Business 一起使用, 或者您打算开始升级到团队, 那么很重要的一点是了解两个应用程序是如何共存、何时以及如何互操作, 以及如何将用户的迁移一直从 Skype for Business 升级到团队。

> [!Tip]
> 观看以下会话以了解[共存和互操作性](https://aka.ms/teams-upgrade-coexistence-interop)

## <a name="coexistence-of-teams-and-skype-for-business"></a>团队和 Skype for business 的共存

除了协作功能之外, 团队还提供聊天、通话和会议功能。 根据你选择的部署团队的方式, 这些功能将与由特定用户的 Skype for Business 提供的功能重叠。 默认模式是与 Skype for Business 一起运行团队;但是, 可以为用户分配几种共存模式, 以确保这些功能不会与该用户重叠。

我们建议你查看下面讨论的共存模式, 以帮助确定哪种路径适合你的组织。

> [!Important]
> 向用户提供新技术或对现有的、熟悉的 Skype for business 环境进行更改, 同时为用户带来巨大的新业务好处。 在实施本文中所述的任何更改之前, 请花一些时间来评估用户准备情况并实施通信和培训计划。 此外, 我们强烈建议你先使用选定的一组用户试验你的计划, 然后再在你的组织中实施。

### <a name="islands-mode"></a>孤岛模式

默认情况下, 用户可以在 Skype for Business 中运行团队作为两个单独的解决方案, 它们提供类似且重叠的功能, 如聊天、通话和会议。 团队用户还可以利用协作功能, 如团队和频道、访问 Office 365 中的文件和应用程序。

在此共存模式 (名为 "**岛**") 中, 每个客户端应用程序都作为单独的岛运行。 Skype for business 与 Skype for Business 交谈, 团队与团队进行协作。 用户同时运行两个客户端, 并且可以在发起通信的客户端中进行本机通信。 因此, 无需在**孤岛**模式下实现互操作。

> [!Tip]
> Skype for Business Online 客户推荐的路径是从默认的**孤岛**模式开始, 推动组织中的采用饱和, 然后快速转到 "**仅团队**模式"。 在内部部署和混合客户可以通过团队协作模式将即将到来的**Skype for** business 部署为起点, 而不是孤岛, 并且在组织准备**** 采纳足球队.

### <a name="skype-for-business-only"></a>仅限 Skype for business

在此共存模式下, 用户将保留在 Skype for Business 中, 而不是团队-用于聊天、会议和呼叫功能, 并且不使用团队和频道团队。 目前可以使用此模式;但是, 在当前实施团队中, 不会为用户自动关闭形式。 即将推出此功能。 在这种情况下, 管理员可以为需要保留在 Skype for Business 中的任何用户删除团队许可证, 作为其唯一的通信应用程序。

### <a name="teams-only"></a>仅限团队

**只有团队**用户可以使用 Skype for business 客户端加入现有 Skype for business 会议, 或使用未经升级的用户或外部团体组织的 skype for business 上的会议。 通过使用团队和 Skype for business 之间的互操作性功能, 升级后的用户可以继续与组织中的其他用户进行通信;但是, 升级后的用户无法启动 Skype for Business 聊天、通话或会议。

一旦你的组织准备好让部分或所有用户使用团队作为唯一的通信和协作工具, 你可以将这些用户升级到 "**仅团队**" 模式。

有关移动到 "仅团队" 模式的其他注意事项, 请参阅[仅团队模式注意事项](teams-only-mode-considerations.md)。

![团队确认消息的屏幕截图](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "在用户作为仅团队用户升级后, 在特殊模式下运行的 Skype For business 客户端")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>具有团队协作功能的 Skype for Business (此模式即将推出)

使用此模式可在你的环境中引入团队, 同时继续利用 Skype for Business 中的现有投资。 在此模式下, 你可以使用聊天、通话和会议功能让 Skype for business 保持不变, 并且你可以添加团队协作功能-团队和频道, 在 Office 365 和应用程序中访问文件。 在本地或混合使用 Skype for Business server 发起点的组织应使用此模式, 而不是孤岛模式。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>具有团队协作和会议的 Skype for Business (此模式即将推出)

除了协作功能之外, 还可使用此共存模式加速团队会议功能的可用性, 从而使用户能够利用优质的新功能, 如脚本和对浏览器中的会议进行翻译和支持。

在此模式下, 与团队和基于频道的对话一起使用团队, 用户开始使用团队安排和开展会议。 私人聊天、语音和视频通话, 保持在 Skype for Business 上。 此共存模式对于具有企业语音的 Skype for business 本地部署中的用户尤其有用, 用户可能需要花费一些时间来升级到团队, 但想要从上级团队会议中获益。

> [!Note]
> 当在特定共存模式下部署时, 团队和 Skype for business 可以进行[互操作](#interoperability-of-teams-and-skype-for-business), 使用户可以与他人进行聊天, 并确保在升级到团队期间通信在你的组织内保持流畅。 共存模式控制互操作性。 接收方的共存模式确定互操作是否可用。 例如, 如果接收器处于一种模式下, 聊天仅在一台客户端 (如团队) 中可用, 则在发起方使用其他客户端 (在此情况下为 Skype for Business) 开始聊天时, 聊天互操作性通常将可用。 另一方面, 如果接收方处于在两个客户端中都可以使用聊天的模式, 则互操作不会对聊天提供, 并且消息将由发起人在发起聊天的同一客户端接收。

有关共存模式、先决条件和管理的更多详细信息, 请参阅使用团队与 Skype for Business 结合使用和[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)[的组织的迁移和互操作指南](https://aka.ms/SkypeToTeams-Interop)。

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|决策点|<ul><li>哪种共存模式最适合你的组织和用户的需要？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|后续步骤|<ul><li>选择升级旅程的最佳方法。</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>团队和 Skype for business 的互操作性

互操作性是团队和 Skype for business 用户在团队和 Skype for business 之间通信的能力。

### <a name="native-interop-and-interop-escalation"></a>本机互操作和互操作升级

有两种类型的互操作体验: 本机和互操作提升。

- 用户当前正在使用的客户端中出现_本机互操作_体验。 一个用户将位于 Skype for Business 客户端, 另一个用户位于团队中。 本机互操作体验不会将它们转到另一个客户端进行通信, 用户将能够在当前使用的客户端中执行其对话。 本机互操作体验是一对一的聊天和通话。
- _互操作提升_体验意味着, 作为帮助用户执行高级操作 (如共享桌面) 的一部分, 该服务可以帮助创建会议并在该会议中继续体验。 将在操作发起人的平台上创建会议。 不在该平台上的用户将收到会议加入坐标并加入会议 (切换客户端之后)。

### <a name="native-interop-experiences"></a>本机互操作体验

根据分配给用户的共存模式 (如上所述), 可以使用以下本机互操作体验:

- Skype for Business 用户可以与团队用户一对一聊天, 反之亦然。 互操作性聊天需要通过 "互操作网关", 这是团队云服务的一部分 (因此仅在联机状态下才存在)。 互操作聊天为纯文本: 不支持格式文本和表情符号。 已通知团队中的用户对话是互操作对话;将很快提供类似于 Skype for Business 用户的通知。

![来自团队的互操作聊天体验的屏幕截图](media/Interop_chat_experience_from_Teams.png "来自团队的互操作聊天体验")

- Skype for Business 用户可以与团队用户进行一对一的语音和视频通话, 反之亦然。

![来自团队的互操作通话体验的屏幕截图](media/Interop_calling_experience_from_Teams.png "来自团队的互操作通话体验")

> [!Important]
> 使用 Skype for Business 的本地部署的互操作体验要求本地环境处于 Office 365 Skype for Business 的混合模式中。 有关详细信息, 请参阅[迁移和互操作性指南](https://aka.ms/SkypeToTeams-Interop)。

这些互操作体验在以下情况下适用于具有以下共存模式之一的用户: Skype for business**与团队协作**、**使用团队协作和会议的 skype**for business、skype for business、skype for business **** 仅限企业或**团队**。 在孤岛模式下不存在与用户的互操作性。

### <a name="native-interop-experience-limitations"></a>本机互操作体验限制

某些功能不适用于团队和 Skype for business 之间的互操作聊天和互操作通话体验:

- 标记、格式文本和完整的表情符集不受团队或 Skype for business 支持。 不支持团队聊天中撰写框的其他本机功能。
- 团队和 Skype for business 之间的屏幕共享 (桌面或应用共享) 不受支持。
- 团队中的群组聊天 (多方对话) 只能包括使用团队的参与者。
- Skype for Business 中的多方 IM 对话 (群组聊天) 只能包括使用 Skype for business 的参与者。
- 不支持与团队和 Skype for business 用户进行的多方呼叫 (不支持正在进行的对等语音或视频呼叫。
- 不支持来自两方聊天的文件传输, 或组聊天中的文件附件 (从团队到 Skype for business, 反之亦然)。
- Skype for Business 持久聊天没有互操作性。

对于所有这些限制 (永久聊天除外), 一种可能的解决方法是让一个用户启动会议并邀请其他用户加入会议。 此解决方法是互操作升级的基础。

> [!Important]
> 简单的聊天 (IM) 开始的内容可能会快速提升到呼叫或临时会议。 我们了解这些方案对可用性和用户体验至关重要, 并且我们不断发展 Skype for Business 和团队用户之间的互操作体验。 请返回以获取最新信息。

查看本文后, 请参阅[选择升级旅行](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[迁移和互操作性指南](https://aka.ms/SkypeToTeams-Interop)、[与 Skype for business 共存](coexistence-chat-calls-presence.md), 以及为实施[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)更多信息.

## <a name="related-links"></a>相关链接

[视频: 管理 SfB 和团队之间的共存和互操作性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
