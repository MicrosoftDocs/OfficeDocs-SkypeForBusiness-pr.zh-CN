---
title: Skype for Business Online 停用
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 了解 Skype for Business Online 的停用计划，以及 Microsoft 如何帮助客户迁移到 Teams。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6c18871756c8081b7013666d98d1599cfec4117f
ms.sourcegitcommit: b635f3765498ae23f535a33fa9ffea5068eecb14
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2022
ms.locfileid: "63463735"
---
# <a name="skype-for-business-online-retirement"></a>Skype for Business Online 停用

2021 年 7 月 31 日，Microsoft 停用了 Skype for Business Online。 2019 年 7 月宣布停用，以提前两年通知客户计划升级Microsoft Teams。 Teams是应用程序中通信和协作的核心Microsoft 365。 随着 Skype for Business Online 的停用，Microsoft 希望确保客户拥有所需的信息和资源，以计划并执行成功升级到 Teams。  Skype使用者服务不受此停用的影响。

## <a name="why-is-skype-for-business-online-retiring"></a>为什么 Skype for Business Online 停用？

自其简介Skype for Business，Skype for Business Online 已成为全球数百万用户的重要工具。 通过将即时消息、呼叫和视频相结合，Skype for Business Online 为业务通信建立了新的可能性。 Teams是该愿景的下一章。 

Microsoft Teams的功能超出了 Skype for Business Online 的功能。 持续进行的平台创新与开发Teams用户受益于更丰富的性能、功能、灵活性和安全性。 通过将以下功能组合到单个体验中，Teams新的工作方式：

- 聊天
- 视频
- 通话
- 文档协作
- 应用程序集成

Teams升级不仅仅是升级 Skype for Business Online。 它是一个功能强大的工具，可让学校和组织变得更灵活，并提高关键工作流的效率。 在 Forrester 白皮书 forrester[™](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/sites/2/2019/04/Total-Economic-Impact-Microsoft-Teams.pdf?rtc=1)（Teams）的"总体经济影响"中详细了解 Microsoft Teams。

有关联机停用Skype for Business，请参阅[常见问题解答 - 从 Skype for Business 升级到 Microsoft Teams](FAQ-journey.yml)。

## <a name="organizations-with-skype-for-business-online"></a>使用 Skype for Business Online 的组织

Microsoft 提供辅助升级过程，帮助组织将剩余的用户Skype for Business Online 用户Teams迁移。 Teams商业和Microsoft 365计划Enterprise，现有许可投资会一Teams。 现在 Skype for Business Online 中作为优质工作负荷的功能将继续在 Teams 中作为优质工作负荷。 例如，如果你独立购买了音频会议，或者作为 E5 的一部分Skype for Business，音频会议将在 Teams 中启用。

## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>在本地部署 Skype for Business Server

停用 Skype for Business Online 不会影响对 Skype for Business Server 和 Lync Server 2013 本地部署的支持。 但是，混合使用联机和本地用户混合的混合客户必须升级任何 *联机* 用户。 必须使用 TeamsUpgradePolicy Teams这些联机用户分配"仅"模式。 Microsoft 提供辅助升级，以帮助自动将剩余的 Skype for Business Online 用户升级到Teams模式。 由于此 *停用，混合* Skype for Business用户无需将其本地用户移到云中。 Microsoft 完全支持混合使用混合混合Teams仅用户和本地Skype for Business用户。 使用混合部署 Skype for Business Server 或 Lync Server 2013 的客户应查看即将停用 [Skype for Business Online 的影响](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)。

## <a name="what-to-expect-post-retirement"></a>停用后预期结果

不再能够为云中的用户分配 TeamsOnly 模式。 这意味着：
 - 向新用户 (（本地 Skype for Business Server) 中的用户除外）时，无论租户的 TeamsUpgradePolicy 全局策略如何，系统都会自动为用户分配 TeamsOnly 模式。
 - 在混合组织中，将本地用户移动到云时，系统会自动为用户分配 TeamsOnly `MoveToTeams` `Move-CsUser`模式 (用户，这些模式与在 .) 中是否指定了开关有关) 
 - 不能为托管在云 (（例如，不使用本地 Skype for Business 服务器）) 分配除"仅"Teams模式。

客户可能拥有其用户群体的剩余部分，这些部分位于 Skype for Business Online 中，并且尚未分配为Teams模式。  客户应Teams这些用户分配"仅"模式。  此外，Microsoft 将为未在"仅Skype for Business联机"Teams辅助升级。  辅助升级体验取决于组织是纯在线组织，还是具有本地用户Skype for Business的组织。  有关详细信息，请参阅从联机到Skype for Business[辅助Microsoft Teams](upgrade-assisted.md)。

辅助升级完成后，所有 *联机* 用户将进入"仅Teams模式。 "仅Teams模式的用户接收传入聊天和呼叫Teams，还可以在 Teams 中安排会议。 他们无法在 Skype for Business Online 中发起聊天或通话或Skype for Business会议。  但是，Teams用户Skype for Business他们已有或将来收到的会议。 最后 *，本地存储的任何用户* 都保留在本地，并且不会Teams。


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft 如何帮助客户升级到 Teams

强烈建议立即开始从 Skype for Business Online Teams升级。

利用可用的资源来帮助规划部署和Teams部署和升级Skype for Business：

- [Teams部署和升级文档](upgrade-start-here.md) - IT 管理员的免费技术指南。

- [Teams计划](./upgrade-workshops-landing-page.yml)研讨会 - 免费的交互式升级规划研讨会，你将在这里获得指导、最佳做法和资源，以帮助你规划和实施升级到 Teams。

- [协助从 Skype for Business Online 升级到 Microsoft Teams](upgrade-assisted.md) - 自动化程序，可帮助你将 Skype for Business Online 用户升级到 Teams。

- [FastTrack计划Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams计划可用的部署帮助。

- [Teams培训](./instructor-led-training-teams-landing-page.yml) - 免费在线培训课程，旨在帮助组织通过实时培训Teams。

- [Teams技术](./chalk-talks-landing-page.yml)研讨会 - IT 专业人员和决策者的免费在线研讨会，这些在线研讨会介绍了有关主要方案Teams。

- [Microsoft 合作伙伴](https://www.microsoft.com/solution-providers/home) - Microsoft 解决方案提供商可帮助你充分利用Teams。

- [Microsoft Teams博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) - Teams新功能、采用和使用资源、Teams设备以及与其他业务应用程序集成的新闻。

如果你是当前在线客户Skype for Business，请立即开始规划升级到 Teams。 我们很高兴你能够体验其强大的通信和协作功能，我们一直致力于帮助。




