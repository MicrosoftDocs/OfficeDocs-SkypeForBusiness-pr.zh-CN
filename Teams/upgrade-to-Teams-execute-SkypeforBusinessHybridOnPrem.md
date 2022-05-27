---
title: 将本地Skype for Business升级到Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 了解如何从本地部署Skype for Business将组织升级到Microsoft Teams。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4b233978b9f9edf0aabbdfb8f9b24ff55a234cc
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681363"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>从本地Skype for Business升级到Teams

![升级旅程关系图，强调部署和实现。](media/upgrade-banner-deployment.png "升级过程的阶段，重点是部署和实施阶段")

本文是升级过程的部署和实现阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解Skype for Business和Teams的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备好环境](./upgrade-prepare-environment.md)
- [准备组织](./upgrade-prepare-organization.md)
- [进行了试点](./pilot-essentials.md)

如果已在本地部署Skype for Business Server或 Microsoft Lync Server，并且组织希望升级到Teams，请遵循本文中的指导。 必须与Microsoft 365组织建立混合连接，如[计划Skype for Business Server与Teams之间的混合连接](/skypeforbusiness/hybrid/plan-hybrid-connectivity)中所述。

在开始之前，还应在本文后面查看[具有本地Skype for Business Server的组织的重要注意事项](#important-considerations-for-organizations-with-skype-for-business-server-on-premises)。

> [!IMPORTANT]
> Skype for Business在线于2021年7月31日停用。 为了最大程度地实现利益并确保组织有适当的时间实现升级，我们鼓励你今天开始Microsoft Teams。 请记住，成功升级符合技术和用户准备情况，因此，在导航到Microsoft Teams时，请务必利用此指南。

## <a name="step-1-configure-hybrid-connectivity"></a>步骤 1：配置混合连接

将本地用户升级到Teams的关键先决条件是为Skype for Business Server本地部署配置混合连接。

"开始"菜单读取[计划混合连接](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json)，然后按照配置[混合连接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)中概述的任务进行操作。

## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步骤 2： (可选) 设置过渡共存模式

Skype for Business和Teams客户端与用户之间的共存和互操作性由[共存模式](migration-interop-guidance-for-teams-with-skype.md)定义。 混合组织默认处于 Islands 模式。 “岛屿”模式允许用户并排使用Teams和Skype for Business客户端。 当组织从Skype for Business过渡到Teams时，组织可以选择使用其他共存模式为最终用户提供可预测的体验。 无论组织对其本地用户使用何种模式，当这些用户从本地迁移到云时，它们都会成为 TeamsOnly (，并且无法) 任何其他模式。  只要用户仍在使用Skype for Business Server，就可以为用户分配除 TeamsOnly 以外的任何模式。 如果需要，TeamsOnly 用户可以移回本地，这将导致他们收到租户的 TeamsUpgradePolicy 全局策略。

当用户处于任何Skype for Business模式时，所有传入聊天和呼叫都会路由到用户的Skype for Business客户端。 为了避免最终用户混淆并确保正确的路由，Teams客户端中的呼叫和聊天功能 *对于分配了任何Skype for Business模式的用户* 是禁用的。 当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，将禁用Teams中的会议计划，并在用户处于 SfBWithTeamsCollabAndMeetings 模式时 *启用*。

根据要求，可以根据组织选择的升级路径分配适当的共存模式。 有关详细信息，请参阅组织[使用Teams以及Skype for Business](migration-interop-guidance-for-teams-with-skype.md)和[设置共存和升级设置的迁移和](./setting-your-coexistence-and-upgrade-settings.md)互操作性指南。

## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步骤 3：将用户从本地Skype for Business移动到仅Teams

Microsoft 最近简化了将用户移动到 TeamsOnly 的过程。 此过程现在是单个步骤，无论使用的是哪个版本的 Skype for Business Server 或 Lync Server 2013。 有关详细信息，请参阅[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)，[并将用户从本地移动到Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>步骤 4：通过禁用混合和解除本地Skype for Business完成到云的迁移

将所有用户从本地移动到云后，可以解除本地Skype for Business部署。 有关详细信息，请参阅[解除本地Skype for Business环境的授权](/skypeforbusiness/hybrid/decommission-on-prem-overview)。

## <a name="phone-system-and-pstn-connectivity-options"></a>电话系统和 PSTN 连接选项

用户处于 TeamsOnly 模式后，支持使用Teams电话系统。  (如果用户处于 Islands 模式，电话系统仅支持 Skype for Business.) 

### <a name="pstn-connectivity-options"></a>PSTN 连接选项

考虑公共交换电话网络 (PSTN) 连接选项时，从本地Skype for Business移动到 TeamsOnly 模式时，有两种可能的情况：

- Skype for Business本地企业语音的用户，他们将转到联机并使用 Microsoft 呼叫计划。 将此用户迁移到Teams需要将用户的本地Skype for Business帐户移动到云中，并使用 A) 该用户电话号码的端口协调移动到 Microsoft 呼叫计划，或者 B) 从可用区域分配新的订阅者号码。  有关详细信息，请参阅[从本地Skype for Business Server和企业语音到 Microsoft 呼叫计划](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- Skype for Business本地企业语音用户，他们将转到联机并保持本地 PSTN 连接。 将此用户迁移到Teams需要将用户的本地Skype for Business帐户移动到云，并协调用户迁移到直接路由的操作。 有关详细信息，请参阅[从本地Skype for Business Server和企业语音到直接路由](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。

## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>本地Skype for Business Server组织的重要注意事项

- 设置Skype for Business混合是迁移到 TeamsOnly 模式的先决条件。 本地Skype for Business Server用户可以在没有混合的 Islands 模式下使用Teams。 但是，如果不使用需要混合连接的 [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) 将用户移到云，则无法转换到 TeamsOnly 模式。 有关详细信息，请参阅 [配置混合连接](/skypeforbusiness/hybrid/configure-hybrid-connectivity)。 即将停用 Skype for Business Online 不会改变此要求。 若要使组织从Skype for Business Server迁移到Teams，它们仍必须使用相同的工具集（*与停用前一样*）设置和配置混合。

- 若要将本地用户移动到云，请在本地管理工具中使用 `Move-CsUser` 。 不再需要指定 `-MoveToTeams` 将用户直接从本地移动到 TeamsOnly 的开关。 用户会自动分配 TeamsOnly 模式，并且其本地会议会自动转换为Teams会议，而不管是否指定了`-MoveToTeams`开关。

- 如果组织已Skype for Business Server，但尚未配置混合连接，但仍希望使用Teams，若要管理Teams功能，必须使用具有 .onmicrosoft.com 域的管理帐户。 如果没有混合连接，管理工具将无法识别本地域。

- Teams拥有本地Skype for Business帐户的用户 (，他们尚未使用 Move-CsUser 移动到云) 无法与任何Skype for Business用户互操作，也不能与外部用户联合。 仅当用户移动到云并成为 TeamsOnly 用户后，此功能才可用。

- 如果有任何用户在本地拥有Skype for Business帐户，或者仍具有本地部署的 lyncdiscover DNS 记录，则无法在租户级别分配 TeamsOnly 模式。 必须首先使用`Move-CsUser`本地Skype for Business帐户将所有用户移动到云。 然后按照禁用混合中所述的步骤 [完成到云的迁移](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)，其中包括删除 DNS 条目。 `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`如果检测到指向Office 365以外的位置的 lyncdiscover DNS 记录，则不会在租户级别工作。

- 必须确保用户正确同步到具有正确Skype for Business属性的 Azure AD。 这些属性都是带有“msRTCSIP-”的前缀。 如果用户未正确同步到 Azure AD，Teams中的管理工具将无法管理这些用户。  (例如，除非正确同步这些属性，否则无法将Teams策略分配给本地用户。) 有关详细信息，请参阅为[Teams和Skype for Business配置 Azure AD 连接](/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- 若要在混合组织中创建新的 TeamsOnly，*必须先在本地Skype for Business Server中启用用户*，然后使用 Move-CsUser 将用户从本地移动到云。  首先在本地创建用户可确保任何其他剩余的本地Skype for Business用户能够路由到新创建的用户。 *所有用户* 联机后，就不再需要先在本地启用用户。

- 如果要在Skype for Business客户端中为本地用户显示通知，则必须在本地工具集中使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 参数与本地用户相关。  本地用户从 TeamsUpgradePolicy 的联机实例接收其模式。 请参阅 [Grant-CsTeamsUpgradePolicy 中的](/powershell/module/skype/grant-csteamsupgradepolicy)说明。

> [!NOTE]
> 2019 年 9 月 3 日之后创建的任何新租户都创建为 TeamsOnly 租户，除非组织已部署本地Skype for Business Server。 Microsoft 使用 DNS 记录标识本地Skype for Business Server组织。 有关详细信息，请参阅 [DNS 对成为混合的本地组织的影响](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid)。

- 以下文章介绍了重要的升级概念和共存行为：
  - [Teams和Skype for Business共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
  - [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
  - [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
