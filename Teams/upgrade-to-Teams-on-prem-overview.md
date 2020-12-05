---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578395"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>从 Skype for Business 升级到 &mdash; IT 管理员的团队

## <a name="overview"></a>概述

从 Skype for Business 升级到团队时，某些组织需要由其 IT 部门计划和管理的渐进式推出。 本部分中的文章主要适用于大型组织中的 IT 管理员。 这些组织通常位于本地，但它们也可能是大型 Skype for Business Online 组织。 阅读这些文章之前，请务必阅读 [团队升级](upgrade-start-here.md) 和 [升级框架](upgrade-framework.md)入门。


以下文章将指导你完成组织的升级过程： 

- [升级方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [用于管理升级的工具](upgrade-to-teams-on-prem-tools.md)
- [具有 Skype for business 内部部署的组织的其他注意事项](upgrade-to-teams-on-prem-considerations.md)
- [实现升级](upgrade-to-teams-on-prem-implement.md)
- [ (PSTN) 注意事项的公共交换电话网络](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，以下文章介绍了重要的升级概念和共存行为：

- [团队和 Skype for business 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>这些文章使用 "Skype for business Online"、"本地 Skype for business 服务器" 和 "Skype for business" 术语。 后一术语既指联机版本，也是本地版本。

开始之前，请注意，已迁移到团队的用户不再使用 Skype for business 客户端，除非加入 Skype for business 中托管的会议。  所有传入聊天和呼叫用户团队客户端中的土地，无论发件人是使用团队还是 Skype for business。 由迁移用户组织的任何新会议将计划为团队会议。 如果用户尝试使用 Skype for Business 客户端，将阻止启动聊天和通话。  但是，用户可以 (，并且必须) 仍使用 Skype for Business 客户端加入受邀的 Skype for business 会议。  (在2017之前发运的旧版 Skype for business 客户端不接受 TeamsUpgradePolicy。 请确保您使用的是最新的 Skype for Business 客户端。 ) 
 
使用 [模式](migration-interop-guidance-for-teams-with-skype.md)概念（ [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的属性）管理用户对团队的过渡。 按照上述说明迁移到团队的用户处于 "TeamsOnly" 模式。  对于迁移到团队的组织，最终目标是将所有用户移到 TeamsOnly 模式。

>[!NOTE]
>拥有 Skype for business 本地帐户的用户不能 TeamsOnly。 虽然这些用户可以 [在孤岛模式下使用团队](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)，但这不会提供可在 TeamsOnly 模式下使用的整套团队功能。 若要使这些用户 TeamsOnly，必须使用本地 Skype for business Server 工具将其移动到云 `Move-CsUser` 。

还行。 让我们开始吧。  第一步是了解 [可用的升级方法](upgrade-to-teams-on-prem-upgrade-methods.md)。







   

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

