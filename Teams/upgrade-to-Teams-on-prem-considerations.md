---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
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
ms.openlocfilehash: e16e651004148645789f5e8e55df6fbbfa1dea9c
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955909"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>针对 IT 管理员在本地 Skype for business 服务器的组织的升级注意事项 &mdash;

本文介绍本地 Skype for business Server 的组织的其他注意事项。 本文是介绍 IT 管理员的升级概念和实现的第四个。  

- [概述](upgrade-to-teams-on-prem-overview.md)
- [升级方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [用于管理升级的工具](upgrade-to-teams-on-prem-tools.md)
-  (本文) 的**具有 Skype For business 内部部署的组织的其他注意事项**
- [实施升级](upgrade-to-teams-on-prem-implement.md)
- [ (PSTN) 注意事项的公共交换电话网络](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，以下文章介绍了重要的升级概念和共存行为：

- [团队和 Skype for business 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>适用于本地 Skype for business 服务器的组织的注意事项

- 设置 Skype for business 混合是迁移到 TeamsOnly 模式的先决条件。 虽然在不带混合的孤岛模式下可以使用团队，但在用户从本地 Skype for business Online (移动到 Skype for business Online 时，无法进行切换，直到使用 [move-csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) 。 有关详细信息，请参阅 [配置混合连接](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)。

- 如果你的组织具有 Skype for business 服务器，但尚未配置混合连接，但你仍希望使用团队来管理团队功能，则必须使用具有 onmicrosoft.com 域的管理帐户。 

- 具有本地 Skype for Business 帐户的团队用户 (也就是说，他们尚未使用移动 Move-csuser) 移动到云，无法与任何 Skype for Business 用户进行互操作，也不能与外部用户联盟。 此功能仅在用户被移动到云 (在 "孤岛" 模式下或 TeamsOnly 用户) 时才可用。 

- 如果你拥有本地 Skype for Business 帐户的任何用户，则不能在租户级别分配 TeamsOnly 模式，除非你将其他模式显式分配给具有本地 Skype for Business 帐户的所有用户。 

- 你必须确保你的用户与正确的 Skype for Business 属性正确同步到 Azure AD。 这些属性都是带有 "msRTCSIP-" 的所有前缀。 如果用户未正确地与 Azure AD 同步，团队中的管理工具将无法管理这些用户。  (例如，你将无法向本地用户分配团队策略，除非你正确同步这些属性。 ) 有关详细信息，请参阅 [配置团队和 Skype for business 的 AZURE AD 连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- 若要在混合组织中创建新的 TeamsOnly 或 Skype for business Online 用户， *必须先在本地 Skype for Business Server 中启用用户*，然后使用 move-csuser 将用户从本地移动到云。  首先在本地创建用户可确保其他任何其他本地 Skype for business 用户能够路由到新创建的用户。 在所有用户都已联机移动后，不再需要先在本地启用用户。

- 当用户从本地移动到云时，按该用户组织的会议将迁移到 Skype for business Online 或团队中，具体取决于是否指定了-MoveToTeams 开关。

- 如果你想要在本地用户的 Skype for Business 客户端中显示通知，则必须在本地工具集中使用 TeamsUpgradePolicy。 仅 NotifySfbUsers 参数对于本地用户是相关的。  本地用户从 TeamsUpgradePolicy 的联机实例接收其模式。 请参阅 [授权 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中的备注。 

>[!NOTE]
> 2019在年9月3日之后创建的任何新租户均创建为 TeamsOnly 租户，除非该组织已有 Skype for Business Server 的内部部署。 Microsoft 使用 DNS 记录来标识本地 Skype for Business 服务器组织。 如果您的组织具有本地 Skype for Business 服务器，但没有公共 DNS 条目，则您需要致电 Microsoft 支持部门以使新租户降级。 



















## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

