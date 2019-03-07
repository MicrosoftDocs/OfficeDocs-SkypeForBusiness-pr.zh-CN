---
title: Microsoft 团队 |升级，群岛模式互操作性策略，只
author: lsomi
ms.author: lsomi
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Skype 的业务和 Microsoft 团队共存选项和 Skype for Business 和团队之间的互操作性的详细信息。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bd9f3deeabed9f024179499f4515ae4d12f444b
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465033"
---
![升级旅程，重点强调项目定义阶段的阶段](media/upgrade-banner-project-definition.png "升级旅程，重点强调项目定义阶段的阶段")

本文是您升级旅程的项目定义阶段的一部分，创建赞助 coalition 和项目工作组并为您的项目定义范围、 目标和远景后完成活动。 在继续之前，确认您已完成以下活动：

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [定义您的项目范围](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>了解 Microsoft 团队和 Skype 的业务共存及互操作性

如果您的组织使用 Skype for Business 今天并且打算开始 for Business 使用旁 Skype 团队 — 或您打算开始升级到团队 — 务必要了解如何两个应用程序共存，当和如何实现它们互操作，以及如何为从业务向工作组的 Skype 一直到其最终升级管理用户的迁移。

> [!Tip]
> 观看下面的会话了解[共存及互操作性](https://aka.ms/teams-upgrade-coexistence-interop)

## <a name="coexistence-of-teams-and-skype-for-business"></a>团队和 Skype 共存 for Business

协作功能，除了团队提供了聊天、 电话和会议功能。 根据您选择如何部署团队，这些功能将由 for Business 的 Skype 分发给定用户的功能与重叠。 默认模式是运行旁 for Business; Skype 的团队但是，可将用户分配多个旨在确保该用户不相互重叠这些功能的共存模式之一。

我们建议您查看可帮助确定适合您的组织的路径如下所述的共存模式。

> [!Important]
> 引入新技术或对您现有，且与熟悉的 Skype 业务环境进行更改，同时还提供了很多新业务好处，可以为用户中断。 需要评估用户准备和实现通信和培训计划实现的任何更改按照本文之前的时间。 此外，我们强烈建议您实现您的组织内之前与一组选定用户的试用计划。

### <a name="islands-mode"></a>群岛模式

默认情况下，用户可以作为两个单独的解决方案，提供类似且重叠的功能，例如，聊天、 电话和会议运行旁 for Business 的 Skype 的团队。 团队用户还可以充分利用协作功能，如团队和通道、 对 Office 365 中的文件的访问和应用程序。

在此共存模式，调用**群岛**，每个客户端应用程序运行作为单独岛。 业务交谈 for Business 和团队的 Skype 的 Skype 交谈团队。 用户运行这两个客户端，从中启动通信客户端中本机通信。 因此，没有需要在**群岛**模式下的互操作性。

> [!Tip]
> Skype 业务联机客户推荐路径是开头的默认**群岛**模式、 驱动器组织中采用饱和度，然后快速移到**团队仅**模式。 在部署和混合客户可从组织准备采用时为起始点而不是群岛，并从该处到**团队仅**模式的进度部署即将开始的**Skype for Business 使用团队协作**模式团队。

### <a name="skype-for-business-only"></a>Skype for Business 仅

在此共存模式中，用户保留在 for Business 的 Skype — 不团队 — for 聊天、 会议和呼叫功能，以及它们不为团队和通道使用团队。 此模式为今天; 可用但是，在当前实现团队形式是不为用户自动关闭。 此功能是即将开始的。 在此期间，管理员可以删除任何用户需要作为其唯一的通信应用程序的业务的 Skype 随时了解最新的工作组许可证。

### <a name="teams-only"></a>仅团队

**团队仅**用户只能使用业务客户端 Skype 加入现有 Skype 业务会议或 for Business 的 Skype 上具有已按未升级的用户或外部组织的会议。 已升级的用户可以继续与组织中仍在使用 Skype for Business 使用适用于业务; 之间团队和 Skype 的互操作性功能的其他用户通信但是，已升级的用户无法启动业务聊天、 通话或会议的 Skype。

只要您的组织可供使用团队作为其唯一的沟通和协作工具的部分或全部用户，您可以升级到**团队仅**模式的这些用户。

有关移动到团队仅模式的其他注意事项，请参阅[仅团队模式注意事项](teams-only-mode-considerations.md)。

![Skype 以特殊模式用户升级为仅团队用户之后运行的业务客户端](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype 以特殊模式用户升级为仅团队用户之后运行的业务客户端")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>Skype for Business 使用团队协作 （此模式为即将发布）

使用此模式时继续利用您现有的投资 Skype for Business 中您的环境中引入团队。 在此模式中，您保持不变与聊天、 电话和会议功能的业务的 Skype 并将其添加团队协作功能 — 团队和通道，访问到 Office 365 和应用程序中的文件。 起始点的 Skype 业务服务器上部署或混合的组织应使用此模式，而不是群岛模式。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>Skype for Business with 团队协作和会议 （此模式为即将发布）

使用此共存模式来加快小组会议中您的组织，除了其协作功能的功能，使用户能够利用很好的质量，如转录的新功能的可用性和翻译，并在浏览器中的会议的支持。

使用团队团队和基于通道 – 在此模式中的对话，以及用户开始使用团队能够安排和管理其会议。 专用聊天和语音和视频呼叫，将保留在 for Business 的 Skype。 特别有用的业务的本地部署企业语音，用户很可能需要一些时间才能升级到团队，但希望受益于出色的团队会议的用户的 Skype 此共存模式。

> [!Note]
> 当部署特定共存模式中，工作组和 for Business 的 Skype 可以[互操作](#interoperability-of-teams-and-skype-for-business)，使用户能够与聊天和其他，呼叫和确保通信保持整个组织期间向工作组您升级旅程液量。 共存模式调控互操作性。 接收方的共存模式决定是否将提供的互操作性。 例如，如果接收者位于在其中聊天只是一个客户端 （说，团队） 中提供的模式，聊天互操作性通常可在发起者 （在本例中为 for Business 的 Skype） 使用其他客户端启动聊天的情况下。 另一方面，如果接收者位于聊天这两个客户端中提供的模式，互操作性不能再聊天 — 且由发起者在其中启动聊天同一客户端中接收方接收邮件。

有关共存模式、 先决条件，以及管理的详细信息，请参阅[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](https://aka.ms/SkypeToTeams-Interop)和[设置您共存并升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)。

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>最佳的共存模式适合您的组织和用户需求？</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>选择您升级旅程的最佳方法。</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>团队和 for Business 的 Skype 的互操作性

互操作性是能够个团队和 Skype 的同一组织中的企业用户团队和 for Business 的 Skype 间通信。

### <a name="native-interop-and-interop-escalation"></a>本机互操作性和互操作性升级

有两种类型的互操作的体验： 本机和互操作性升级。

- 用户当前正在使用的客户端中发生的_本机互操作_体验。 对于业务客户端，团队中其他 Skype 中将一个用户。 本机互操作性体验不会执行其到另一个客户端进行通信，用户将能够进行客户端他们当前正在使用中的其对话。 本机互操作的体验是一对一聊天和调用。
- _互操作性升级_体验表示作为帮助用户执行高级 （如共享其桌面） 操作的一部分，该服务可方便的会议创建，并在继续该会议中体验。 操作的发起方平台上创建会议。 不在该平台收到会议的用户加入坐标和加入会议 （之后切换客户端）。

### <a name="native-interop-experiences"></a>本机互操作体验

根据分配给用户 （如上所述） 的共存模式，提供了以下本机互操作的体验：

- 适用于业务用户的 Skype 可以一对一聊天，与团队用户，反之亦然。 互操作性聊天需要通过属于的团队云服务 （并因此仅存在于联机） 的互操作性网关。 互操作性聊天是纯文本： 富文本和图释不受支持。 通知团队中的用户的对话的互操作的对话;很快将提供 Skype 业务用户的类似通知。

![互操作聊天从团队体验](media/Interop_chat_experience_from_Teams.png "互操作聊天从团队体验")

- Skype 的企业用户可以进行一对一语音和视频呼叫的团队用户，反之亦然。

![互操作调用从团队体验](media/Interop_calling_experience_from_Teams.png "互操作调用从团队体验")

> [!Important]
> 在本地部署的 for Business 的 Skype 的互操作性体验需要在本地环境处于 for Business 的 Office 365 Skype 混合模式。 有关详细信息，请参阅[迁移和互操作性指南](https://aka.ms/SkypeToTeams-Interop)。

这些互操作的体验是提供给，并且用户拥有分配以下共存模式之一之间： **Skype for Business 使用团队协作**， **Business 团队协作和会议的 Skype**， **Skype 的仅业务**，或**仅团队**。 在群岛模式中对用户没有互操作性。

### <a name="native-interop-experience-limitations"></a>本机互操作性体验限制

某些功能不可用的互操作性聊天和团队之间 for Business 的 Skype 的互操作调用体验：

- 减价、 富文本和完整的图释集不支持从工作组或业务的 Skype。 不支持团队聊天中撰写框其他本机功能。
- 不支持团队和 for Business 的 Skype 之间共享 （桌面或应用程序共享） 的屏幕。
- 团队中的组聊天 （多方对话） 只能包含使用团队参与者。
- Skype for Business 中的多个方 IM 对话 （群聊） 只能包含 for Business 使用 Skype 的参与者。
- 升级正在进行的对等语音或视频呼叫涉及的业务用户的工作组和 Skype 的多方呼叫不受支持。
- 文件传输的两方聊天，或在群聊，从团队 Skype for Business 文件附件 —，反之亦然 — 不受支持。
- 与业务持久聊天的 Skype 没有互操作性。

有关所有这些限制 （除外持久聊天），一个可能的解决方法是一个用户开始会议并邀请其他用户加入它。 此解决方法是互操作性升级的基础。

> [!Important]
> 什么开始简单聊天 (IM) 可能快速升级到呼叫或临时会议。 我们了解这些方案至关重要的可用性和用户体验，以及我们正在不断发展之间的业务和团队的用户的 Skype 的互操作性体验。 重新检查的最新信息。

阅读本文后，请参阅[选择您升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[迁移和互操作性指南](https://aka.ms/SkypeToTeams-Interop)、[与 for Business 的 Skype 共存](coexistence-chat-calls-presence.md)，和[设置您共存并升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)实现详细信息。

## <a name="related-links"></a>相关的链接

[视频： 管理共存和 SfB 和团队之间的互操作性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)