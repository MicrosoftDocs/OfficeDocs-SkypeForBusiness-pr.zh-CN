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
ms.openlocfilehash: dcd2148a3f939bd8799b7b3f8b86118359936b7c
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783901"
---
# <a name="skype-for-business-online-retirement"></a>Skype for Business Online 停用

2021 年 7 月 31 日，Microsoft 停用了 Skype for Business Online。 2019 年 7 月宣布停用，以提前两年通知客户计划升级Microsoft Teams。 Teams是应用程序中通信和协作的核心Microsoft 365。 随着 Skype for Business Online 的停用，Microsoft 希望确保客户拥有所需的信息和资源，以计划并执行成功升级到 Teams。  Skype使用者服务不受此停用的影响。 有关停用 Skype for Business Online 的背景信息，请参阅[常见问题解答 - 从 Skype for Business 升级到 Microsoft Teams](FAQ-journey.yml)。

Microsoft 将在 2022 年 6 月 30 Skype for Business之后停用联机基础结构。 本文包含针对 TeamsOnly 用户从任何版本升级的组织的Skype for Business。


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>在本地部署 Skype for Business Server

停用 Skype for Business Online 不会影响对 Skype for Business Server 和 Lync Server 2013 本地部署的支持。 但是，混合使用联机和本地用户混合的混合客户必须升级任何 *联机* 用户。 必须使用 TeamsUpgradePolicy 为任何联机用户分配 TeamsOnly 模式。 Microsoft 提供辅助升级，以帮助自动将剩余的 Skype for Business Online 用户升级到 TeamsOnly 模式。 由于此 *停用，混合* Skype for Business用户无需将其本地用户移到云中。 Microsoft 完全支持混合使用 TeamsOnly 用户和本地用户混合的混合Skype for Business组织。 使用混合部署 Skype for Business Server Lync Server 2013 的客户应查看停用 [Skype for Business Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)。

## <a name="what-to-expect-post-retirement"></a>停用后预期结果

不再为云中的用户分配 TeamsOnly 模式。 这意味着：

 - 为不在本地 Skype for Business Server 中的新用户授权时，无论租户的 TeamsUpgradePolicy 全局策略如何，都会自动为用户分配 TeamsOnly 模式。
 - 在混合组织中，将本地托管的用户移动到云时，会自动为用户分配 TeamsOnly `MoveToTeams` 模式，而不考虑是否在 中指定了开关 `Move-CsUser`。
 - 不能为托管在云中的用户分配 TeamsOnly 模式。 联机用户 *不在本地* Skype for Business服务器。

客户可能拥有在 Skype for Business Online 中且尚未分配 TeamsOnly 模式的剩余用户。 客户应尽快为这些用户分配 TeamsOnly 模式。 Microsoft 将为不在 TeamsOnly 模式下Skype for Business Online 用户提供辅助升级。 辅助升级体验取决于组织是纯在线组织，还是具有本地用户Skype for Business的组织。 有关详细信息，请参阅从联机到Skype for Business[辅助Microsoft Teams](upgrade-assisted.md)。

辅助升级完成后，所有 *联机* 用户将进入 TeamsOnly 模式。 TeamsOnly 模式下的用户接收传入的聊天和呼叫Teams，还可以在 Teams 中安排会议。 他们无法启动聊天或通话或在 Skype for Business Online 中安排会议。  但是，TeamsOnly 用户可以加入Skype for Business已经或将来收到的会议。 最后 *，任何本地用户* 都保留在本地，不会成为 TeamsOnly。

## <a name="actions-to-take-before-june-30-2022"></a>2022 年 6 月 30 日之前要采取的操作
现已Skype for Business Online，Microsoft 将于 2022 年 6 月 30 日之前开始停用支持基础结构。  对于使用 TeamsOnly 用户从任何版本升级Skype for Business组织，如果以下任一情况适用，则需要采取措施：

- 如果你有任何 TeamsOnly 用户，这些用户之前在 Skype for Business 中具有联系人，并且自升级后尚未登录  Teams登录。
- 如果有任何 TeamsOnly 用户Skype for Business升级到 TeamsOnly 之前组织的在线会议。

如果上述任一情况适用于组织，则必须在 2022 年 6 月 30 日前采取措施，如下所述：

 - **Skype for Business联机** 联系人：将用户升级到 TeamsOnly 模式后，该用户首次登录到 Teams 时，该用户的 Skype for Business Online 帐户中的任何现有联系人都将迁移到 Teams。 Microsoft 删除 Skype for Business Online 基础结构后，你不能再迁移尚未登录到 Teams *的用户的联系人。* 若要将联系人从 Skype for Business 迁移到 Teams，Microsoft 建议以前Skype for Business的所有用户在 2022 年 6 月 30 Teams至少登录一次。

 - **Skype for Business联机会议**：组织升级到 TeamsOnly 后，用户以会议Teams会议。 在某些情况下，TeamsOnly 用户可能Skype for Business之前组织的联机会议。 目前，升级后的 TeamsOnly 用户和任何受邀与会者可以使用其Skype for Business客户端加入这些Skype for Business联机会议。 但是，在 Microsoft 删除Skype for Business TeamsOnly 用户的联机基础结构后，该用户组织的Skype for Business Online 会议将不再存在。 组织者和任何与会者将无法加入这些会议。 如果 TeamsOnly 组织的用户Skype for Business在线会议的剩余时间，Microsoft 建议他们重新安排这些会议，Teams会议。 或者，管理员可以使用会议迁移[服务](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet)将这些会议转换为Teams会议。 在任一情况下，请于 2022 年 6 月 30 日完成这些操作。  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft 如何帮助客户升级到 Teams

强烈建议立即开始从 Skype for Business Online Teams升级。 利用可用的资源来帮助规划部署和Teams部署和升级Skype for Business：

- [Teams部署和升级文档](upgrade-start-here.md) - IT 管理员的免费技术指南。

- [Teams计划](./upgrade-workshops-landing-page.yml)研讨会 - 免费的交互式升级规划研讨会，你将在这里获得指导、最佳做法和资源，以帮助你规划和实施升级到 Teams。

- [协助从 Skype for Business Online 升级到 Microsoft Teams](upgrade-assisted.md) - 自动化程序，可帮助你将 Skype for Business Online 用户升级到 Teams。

- [FastTrack计划Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams计划可用的部署帮助。

- [Teams培训](./instructor-led-training-teams-landing-page.yml) - 免费在线培训课程，旨在帮助组织通过实时培训Teams。

- [Teams技术](./chalk-talks-landing-page.yml)研讨会 - IT 专业人员和决策者的免费在线研讨会，这些在线研讨会介绍了有关主要方案Teams。

- [Microsoft 合作伙伴](https://www.microsoft.com/solution-providers/home) - Microsoft 解决方案提供商可帮助你充分利用Teams。

- [Microsoft Teams博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) - Teams新功能、采用和使用资源、Teams设备以及与其他业务应用程序集成的新闻。

如果你是当前在线客户Skype for Business，请立即开始规划升级到 Teams。 我们很高兴你能够体验其强大的通信和协作功能，我们一直致力于帮助。  有关联机停用Skype for Business，请参阅[常见问题解答 - 从 Skype for Business 升级到 Microsoft Teams](FAQ-journey.yml)。





