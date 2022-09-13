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
ms.openlocfilehash: 07d5e443075a80ddad8bda2e490cdd906c3900bf
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657232"
---
# <a name="skype-for-business-online-retirement"></a>Skype for Business Online 停用

2021 年 7 月 31 日，Microsoft 停用了 Skype for Business Online。 2019 年 7 月宣布停用，以便提前两年通知客户计划升级到 Microsoft Teams。 Teams 是 Microsoft 365 中用于通信和协作的核心应用。 停用 Skype for Business Online 后，Microsoft 希望确保客户拥有计划和执行到 Teams 成功升级所需的信息和资源。  Skype 使用者服务不受此停用的影响。 有关 Skype for Business Online 停用的原因的背景信息，请参阅[常见问题解答 - 从Skype for Business升级到 Microsoft Teams](FAQ-journey.yml)。

Microsoft 将于 2022 年 6 月 30 日或之后开始停用 Skype for Business Online 基础结构。 本文包含有关 TeamsOnly 用户已从任何Skype for Business版本升级的组织的指南。


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>具有本地部署Skype for Business Server的组织

Skype for Business Online 停用不会影响对本地部署 Skype for Business Server 和 Lync Server 2013 的支持。 但是，混合客户以及联机和本地用户的混合客户必须升级任何 *联机* 用户。 必须使用 TeamsUpgradePolicy 为任何联机用户分配 TeamsOnly 模式。 Microsoft 正在提供辅助升级，以帮助自动将剩余Skype for Business联机用户升级到 TeamsOnly 模式。 由于此停用，混合组织无需将其 *本地* Skype for Business用户迁移到云。 Microsoft 完全支持混合组织，其中包含 TeamsOnly 用户和本地Skype for Business用户。 具有 Skype for Business Server 或 Lync Server 2013 混合部署的客户应查看 [Skype for Business Online 的停用](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)。

在本地 Active Directory环境中创建新用户时，如果这些用户将同步到 Azure AD，并且你打算为这些用户授予 Teams 许可证，那么 *在为这些用户分配许可证之前*，**必须先在本地Skype for Business部署中启用这些用户，并确保更改已通过 Azure AD 连接同步到云**。  可以使用 Get-CsOnlineUser 验证更改是否已完全同步到云。 如果用户的 HostingProvider= “SRV：”，则更改已同步。  它不应是“sipfed.online.lync.com”。   

## <a name="what-to-expect-post-retirement"></a>退休后会发生什么

云中托管的用户不再可能被分配到 TeamsOnly 以外的模式。 这意味着：

 - 当许可本地Skype for Business Server中未托管的新用户时，无论租户的 TeamsUpgradePolicy 全局策略如何，都会自动为用户分配 TeamsOnly 模式。
 - 在混合组织中，将本地用户迁移到云时，无论是否在云中`Move-CsUser`指定开关，`MoveToTeams`都会自动为用户分配 TeamsOnly 模式。
 - 无法为云中托管的用户分配 TeamsOnly 以外的模式。 联机用户 *不* 使用本地Skype for Business服务器。

客户的剩余用户可能位于 Skype for Business Online 中，但尚未分配 TeamsOnly 模式。 客户应尽快将 TeamsOnly 模式分配给这些用户。 Microsoft 将为不在 TeamsOnly 模式下的Skype for Business联机用户提供辅助升级。 辅助升级体验取决于你的组织是纯在线组织还是具有本地Skype for Business用户的组织。 有关详细信息，请参阅[从 Skype for Business Online 到 Microsoft Teams 的辅助升级](upgrade-assisted.md)。 辅助升级完成后，所有 *联机* 用户都将处于 TeamsOnly 模式。 *任何本地用户都保留在本地，不会成为 TeamsOnly*。

TeamsOnly 模式下的用户在 Teams 中接收传入聊天和呼叫，并在 Teams 中安排会议。 他们无法在联机Skype for Business发起聊天、呼叫或安排会议。 TeamsOnly 用户可以加入他们已拥有或将来接收的Skype for Business会议。 但是，在 Microsoft 删除给定 TeamsOnly 用户的 Skype for Business Online 基础结构后，TeamsOnly 用户只能匿名加入Skype for Business会议。  从 2022 年 6 月 30 日之后开始，新创建的 TeamsOnly 用户将不再使用 Skype for Business Online 基础结构进行预配，因此如果他们被邀请参加Skype for Business会议，则需要匿名加入。


## <a name="actions-to-take-before-june-30-2022"></a>要在 2022 年 6 月 30 日之前执行的操作
现在，Skype for Business Online 已停用，Microsoft 将于 2022 年 6 月 30 日开始停用支持基础结构。  对于具有从任何版本的 Skype for Business 升级的 TeamsOnly 用户的任何组织，如果以下任一情况适用，则需要采取措施：

- 如果有任何 TeamsOnly 用户在 Skype for Business 中具有联系人，*并且* 自升级后尚未登录到 Teams。
- 如果有任何 TeamsOnly 用户在升级到 TeamsOnly 之前仍Skype for Business他们组织的联机会议。

如果其中任一情况适用于你的组织，则必须在 2022 年 6 月 30 日之前采取行动，如下所述：

 - **Skype for Business联机联系人：** 用户升级到 TeamsOnly 模式后，用户首次登录 Teams 时，该用户Skype for Business联机帐户中的任何现有联系人都将迁移到 Teams。 Microsoft 删除Skype for Business联机基础结构后，你不能再 *为尚未登录 Teams 的用户* 迁移联系人。 若要将联系人从Skype for Business迁移到 Teams，Microsoft 建议以前Skype for Business的所有用户至少在 2022 年 6 月 30 日之前登录一次 Teams。

 - **Skype for Business联机会议：** 将组织升级到 TeamsOnly 后，用户将创建所有新会议作为 Teams 会议。 在某些情况下，TeamsOnly 用户可能仍拥有之前组织的Skype for Business联机会议。 目前，升级的 TeamsOnly 用户和任何受邀与会者都可以使用其Skype for Business客户端加入这些Skype for Business联机会议。 但是，在 Microsoft 删除给定 TeamsOnly 用户的 Skype for Business Online 基础结构后，该用户只能匿名加入 Skype for business 会议，并且 *该用户组织的* 剩余Skype for Business联机会议将不再存在。 组织者和任何与会者将无法参加这些会议。 如果 TeamsOnly 组织中的用户拥有他们组织的剩余Skype for Business联机会议，Microsoft 建议将这些会议重新安排为 Teams 会议。 或者，管理员可以使用 [会议迁移服务](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) 将这些会议转换为 Teams 会议。 在任一情况下，请在 2022 年 6 月 30 日之前完成这些操作。  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft 如何帮助客户升级到 Teams

我们强烈建议你今天开始从 Skype for Business Online 升级到 Teams。 利用可用的资源，从Skype for Business规划 Teams 部署和升级：

- [Teams 部署和升级文档](upgrade-start-here.md) – 面向 IT 管理员的免费技术指南。

- [Teams 升级规划研讨会](./upgrade-workshops-landing-page.yml) - 免费的交互式升级规划研讨会，你将在其中收到指导、最佳做法和资源，旨在帮助你规划和实施到 Teams 的升级。

- [从 Skype for Business Online 到 Microsoft Teams 的辅助升级](upgrade-assisted.md) – 自动化计划，可帮助你将Skype for Business联机用户升级到 Teams。

- [FastTrack for Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – 适用于符合条件的计划的 Teams 部署协助。

- [Teams 实时培训](./instructor-led-training-teams-landing-page.yml) - 免费在线培训课程，旨在让组织通过 Teams 启动和运行。

- [Teams 粉笔演讲](./chalk-talks-landing-page.yml) - 面向 IT 专业人员和决策者的免费在线研讨会，介绍 Teams 中关键方案的最佳做法。

- [Microsoft 合作伙伴](https://www.microsoft.com/solution-providers/home) - Microsoft 解决方案提供商可以帮助你充分利用 Teams。

- [Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) - Teams 新闻，介绍新功能、采用和使用资源、Teams 设备以及与其他业务应用程序的集成。

如果你是当前Skype for Business联机客户，请立即开始计划升级到 Teams。 我们很高兴你体验其强大的沟通和协作功能，并致力于一路提供帮助。  有关Skype for Business联机停用的详细信息，请参阅[常见问题解答 - 从Skype for Business升级到 Microsoft Teams](FAQ-journey.yml)。





