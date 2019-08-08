---
title: Microsoft 团队从 Skype for Business 升级 |模式、共存
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen, bjwhalen
description: Skype for business 和 Microsoft 团队共存选项和模式的详细信息, 以及通过示例方案将慷慨升级到来自 Skype for Business 的团队。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7509d0f3d6e3e557f6b7ccd388f7b9b340705bba
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236165"
---
![升级旅行图, 强调部署和实现](media/upgrade-banner-deployment.png "升级旅程的阶段, 重点介绍部署和实施阶段")

本文是升级过程的部署和实施阶段的一部分。 继续之前, 请确认你已完成以下活动:

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>选择从 Skype for Business 到团队的升级旅程

作为现有的 Skype for Business 客户, 您对团队的完全过渡可能需要一段时间。 但是, 你现在可以通过让你的用户与 Skype for Business 一起使用团队, 开始实现团队的价值。 假设两个应用之间存在一些重叠的功能, 我们建议你查看可用的共存和升级模式, 以帮助确定适合你的组织的路径。 例如, 你可以选择在不具有互操作性的两个解决方案上启用所有工作负荷。 或者, 你可以决定管理用户体验, 方法是逐步引入团队功能或面向用户组选择功能, 直到你的组织准备好将每个人升级到团队。 使用试点结果帮助评估适合您的组织的升级旅程。

> [!IMPORTANT]
> Skype for Business Online 将于2021年7月31日停用, 之后将不再可访问或支持。 为了最大程度地实现收益并确保你的组织有适当的时间实施升级, 我们鼓励你立即开始迁移到 Microsoft 团队。

本文概述了各种模式, 使你能够管理 Skype for Business 和团队的哪些形式可供你的用户使用。 与任何部署一样, 我们强烈建议你在将组织升级到团队之前使用选定的一组用户[试验你的预定计划](pilot-essentials.md)。 请记住, 新技术的引入会使用户中断。 在实施此处所述的任何模式之前, 请花一些时间来评估用户准备情况并实施通信和培训计划。

> [!TIP]
> 加入我们的现场互动式研讨会, 我们将分享指导、最佳做法和资源, 旨在开始升级规划和实施。
>
>首先加入[升级](https://aka.ms/SkypeToTeamsPlanning)会话的计划以开始使用。


## <a name="upgrade-journey-building-blocks"></a>升级旅程构建基块

若要正式准备您的组织以供团队旅行, 您需要开始规划升级方案, 最终让您的组织完全接纳团队作为您的唯一的通信和协作解决方案。

为帮助指导制定决策过程, 请熟悉各种模式、概念和与从 Skype for Business 升级到团队相关的术语。 有关详细信息, 请参阅[Microsoft 团队和 Skype for business 共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)

如果某些用户已准备好仅使用团队进行日常通信和协作需求, 则可以通过为团队启用 "**仅限团队**" 模式来开始将这些用户升级到团队。

如果不能让整个组织移动到团队, 则可以在 "**孤岛**" 共存模式下通过 "试用团队" 和 "Skype for business" 开始。 作为其他共存模式 (即**使用团队协作**和 skype for Business 与**团队协作和会议**的 skype for business), 我们将在未来几个月内逐渐获得完整的功能, 您也可以从完全首先将团队用作组协作解决方案, 同时将 Skype for business 作为组织的统一通信解决方案。 对于使用 Skype for Business 服务器 (本地或混合版) 的客户, 以及有大量复杂的客户, 其轨迹将包括很长的共存期, 这是 Microsoft 推荐的用于使用 Skype for Business 服务器的客户的路径。

![从 Skype For business 升级到团队的升级构建基块的屏幕截图](media/upgrade_journeys_building_block.png "从 skype For business 升级构建基块的屏幕截图, 由使用 "团队协作&ndash;" 模式的 skype for Business、使用团队协作和会议模式的 skype For business、孤岛模式、"仅限团队" 模式和 Skype for business 组成仅&ndash;业务模式。")

下表比较了共存和升级模式。

|众 |状况 |推荐使用 |最终 |一些 |
|---|---|---|---|---|
|群岛 |较小或更简单的 Skype for business 部署<br><br>能够更快地管理一些短期的复杂性, 更快地迁移到团队 |尽快转到完整的团队体验<br><br>开展团队的概念证明 (PoC)<br><br>适用于采用 Skype for Business Online 的组织的推荐升级途径 |操作简单<br><br>所有功能的最丰富的团队体验 |需要进行良好的用户通信以避免混乱和推动团队使用<br><br>退出策略要求用户在开始升级到 "仅团队" 阶段之前拥有完全采纳的团队<br><br>在孤岛模式下没有用户互操作;当用户的 Skype for Business 帐户在本地托管时, 也没有来自团队的联盟|
|具有团队协作的 Skype for Business |使用团队尚未满足的要求进行 Skype for business 部署 (例如, 高级合规性)<br><br>长期需要和/或 Skype for business 承诺|快速开始团队开始, 首先关注组协作<br><br>希望立即在 Skype for Business 上保留所有统一通信工作负荷<br><br>建议用作组织开始从本地 (或混合) Skype for business 开始进行旅行的起点|团队和 Skype for business 之间没有重叠的功能<br><br>即时消息聊天和会议安排将驻留在 Skype for Business 中 (绑定到通话)<br><br>仅与团队中的用户进行互操作|
|具有团队协作和会议的 Skype for business |通过大量使用企业语音和要求的 Skype for business 部署, 团队通话尚不满足这些要求<br><br>长期需要和/或 Skype for business 承诺<br><br>可能使用的是第三方会议服务|快速开始团队发展, 超越组协作<br><br>改善用户的会议体验<br><br>建议用于需要在准备好进行完全升级 (通常是由于企业内部部署的企业语音) 之前利用团队会议的本地组织。 |没有重叠的功能<br><br>团队的出色会议。 功能路线图、UX 和跨平台、质量和可靠性<br><br>在 Skype for Business 和团队之间 "更好地协作" 体验<br><br>团队中的互操作性用户。|即时消息和聊天将驻留在 Skype for Business 中 (绑定到通话)|
|仅限团队 |团队仅为所有用户最终的目标。<br><br>某些用户需要保留在 Skype for Business 上<br><br>您正在将 skype for business Online 用户升级到团队, 同时在 Skype for business 服务器上保持 Skype for business 本地用户<br><br>你可能已经在孤岛模式下部署了用户, 并且已准备好注销用户组的 Skype for Business |减少 Skype for Business (本地服务器操作、外包合同等) 的可变成本<br><br>尽快转到完整的团队体验, 至少对于某些用户|通过仅向 Skype for Business 中的用户提供一个客户端来限制用户混乱, 使用团队协作与 skype for business 进行协作, 使用团队协作和会议与 Skype for business 进行协作|互操作性仅支持 Skype for Business 和团队之间的基本聊天和通话, 以及用于桌面共享和多方聊天和通话的互操作性升级方案|
|仅限 Skype for business |某些用户需要保留在 Skype for Business 上<br><br>|通过仅提供一个客户端来限制用户混乱<br><br>用户仍可参与受邀参加的团队会议|继续满足目前只能由 Skype for business 满足的业务要求<br><br>仅与团队中的用户进行互操作|互操作性仅支持 Skype for Business 和团队之间的基本聊天和通话, 以及用于桌面共享和多方聊天和通话的互操作性升级方案|

> [!TIP]
> 若要帮助在 Skype for Business 仍在使用时根据希望在团队中启用的功能确定推荐的升级模式, 请利用[skype To 团队升级向导](https://aka.ms/SkypeToTeamsWizard)。

## <a name="upgrade-journeys"></a>升级慷慨

你可以采用多种方法从 Skype for Business (联机或本地) 升级到团队:

- 在直接升级过程中, 你首先在**孤岛**模式下部署团队和 Skype for business, 作为评估和提前采纳的一部分, 然后将你的用户升级到**仅限团队**模式, 从而使 skype for business 快速淘汰组织中所有用户的环境。 这是为 Skype 商业版客户推荐的旅程, 除非他们担心他们的用户不会与使用两个工具来执行相同操作 (聊天、通话、会议安排) 的干扰。
- 逐步升级会将特定的共存和升级模式提供给特定用户组 (也称为*群体*), 具体取决于其通信和协作要求。 随着时间的推移, 整个组织只能集中到使用团队, 并最终取代 Skype for Business。 但是, 如果您的组织有引人注目的商业理由来保留 Skype for business (例如, 依赖于基于统一通信托管 API (UCMA) 的解决方案), 该解决方案与业务线应用程序集成, 或者有道德的留言板解决方案目前仅适用于 Skype for business 或复杂的企业语音部署, 只需花费时间升级到**团队**, 您就可以将部分用户升级到 "**仅团队**" 模式, 同时将 Skype for business 用户保留在其中一个部分用户填充的共存模式。 逐步升级旅程是一种推荐的方法, 用于从使用团队协作模式的 Skype for Business 开始使用 Skype for Business, 并在要求用户满足时从 "仅团队" 模式移动到 "仅团队" 模式 (可能是通过具有团队协作和会议共存模式的 Skype for Business。

> [!IMPORTANT]
> 对于这两种类型的升级, 如果你的组织当前仅是 Skype for business 内部部署部署, 则在将用户升级到 "**仅团队**" 模式之前, 你需要开始计划以实施 skype for business 混合。 这还有助于促进与团队的互操作。

> [!NOTE]
> "**仅限团队**" 模式要求属于 cohorts 的用户托管在 skype For business Online 中, 并且您需要使用 Skype For business online 部署和 skype For business Online 租户之间的混合关系来简化Skype for Business 和团队之间的互操作性。 在升级到 "**仅限团队**" 模式之前, 必须为属于 cohorts 的用户完成 "移动到 Skype For business Online"。 Skype for business Server 2019 和具有 CU8 更新的 Skype for Business Server 2015 可以通过管理到 Skype for business Online 的迁移并在一个步骤中将用户升级到 "**仅团队**" 模式来简化将本地用户升级到团队的机制。.

### <a name="direct-upgrade-journey"></a>直接升级旅程

直接升级旅程如下图所示。

![直接升级旅程的屏幕截图](media/upgrade_journey_direct_upgrade.png "直接升级旅程的屏幕截图。所有用户最初都以孤岛模式使用团队, 然后切换到 \"仅团队\" 模式, 并将整个组织的结束状态升级到团队。")

团队将部署到组织中的所有用户, 并在 "**孤岛**" 模式下配置。 当你的组织确定团队准备好满足你的所有通信和协作需求时, 请通知用户并将其升级到 "**仅团队**" 模式。 此时, 可以从环境中停用 Skype for business。

### <a name="gradual-upgrade-journey"></a>逐步升级旅程

下图阐释了逐步升级旅程的示例。

![逐步升级旅程的图解示例](media/upgrade_journey_gradual_upgrade.png "在逐步升级过程中, cohorts 用户最初在孤岛模式下使用团队进行评估, 然后在各种升级模式下使用 Skype for business。某些 cohorts 切换到仅限团队模式, 而一组用户与具有团队协作和会议模式的 Skype for Business 保持一致。")

团队在以**孤岛**模式部署到组织中, 以便对不同的用户组进行评估, 然后移动到不同的共存和升级模式。 例如, 可以为 "**孤岛**" 模式启用一组用户, 这种用户可以**使用团队协作和会议模式为 skype for** business 启用另一个组, 而第三组用户最初可能会启用与团队的 skype for business 的用户**仅协作**模式。

随着时间的推移, 用户组可以升级到 "**仅团队**" 模式, 后跟组织的其余部分。 最终, 整个组织将随时准备停用 Skype for business, 并仅使用团队进行通信和协作, 或者, 如果业务要求规定为特定组保留 Skype for business (大多数用户位于组织只能使用团队。 <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul> 哪些升级旅程适用于组织的业务需求？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>后续步骤</td><td><ul> 确定你的当前部署模型、使用案例方案以及你的组织的关键注意事项将通知迁移到最适合你的组织的团队。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul> 哪种升级方案适用于您的组织？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul> 根据消息、会议和通话业务要求, 确定组织的升级旅程的日程表。<br><br> 确定完成升级旅行所需的额外工作。<br><br></ul></td></tr>
</table>

为你的组织选择最佳升级旅行后, 请[向团队执行升级](https://aka.ms/SkypeToTeams-Upgrade)。
