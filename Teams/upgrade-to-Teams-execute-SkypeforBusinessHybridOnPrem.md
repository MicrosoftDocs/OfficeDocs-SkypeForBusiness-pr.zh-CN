---
title: 在本地Skype for Business升级到 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 了解如何从本地部署Microsoft Teams组织Skype for Business升级。
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
ms.openlocfilehash: d5ad5bc82771a3a8f020600a48848a074b88aec4
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299057"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>从Skype for Business本地升级到 Teams

![升级过程图，强调部署和实施。](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")

本文是升级旅程的部署和实施阶段的一部分。 在继续之前，请确认已经完成了以下活动:

-   [登记项目利益干系人](upgrade-enlist-stakeholders.md)
-   [请确定项目范围](./upgrade-define-project-scope.md)
-   [了解两者共存Skype for Business互操作性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [准备环境](./upgrade-prepare-environment.md)
-   [为组织做好准备](./upgrade-prepare-organization.md)
-   [开展试点](./pilot-essentials.md)

如果您已在本地Skype for Business Server Microsoft Lync Server，并且您的组织想要升级到 Teams，请按照本文中的指导操作。 必须设置与组织之间的混合Microsoft 365连接，如计划 Skype for Business Server 与 [Teams。](/skypeforbusiness/hybrid/plan-hybrid-connectivity)

在开始之前，还应在本文的[Skype for Business Server查看](#important-considerations-for-organizations-with-skype-for-business-server-on-premises)组织的重要注意事项。

> [!IMPORTANT]
> Skype for Business Online 于 2021 年 7 月 31 日停用。 为了最大程度地实现权益并确保组织有适当的时间来实施升级，我们鼓励你立即开始Microsoft Teams之旅。 请记住，成功的升级符合技术和用户准备情况，因此，在导航到 Microsoft Teams。

## <a name="step-1-configure-hybrid-connectivity"></a>步骤 1：配置混合连接 

将本地用户升级到 Teams的主要先决条件是为本地部署Skype for Business Server混合连接。 

首先阅读 ["规划混合](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json)连接"，然后按照配置混合连接 [中概述的任务操作](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步骤 2：设置过渡共存模式 (可选) 

客户端和用户之间的共存Skype for Business互操作性Teams共存模式[定义](migration-interop-guidance-for-teams-with-skype.md)。 混合组织默认采用群岛模式。 岛屿模式允许用户并行使用Teams Skype for Business客户端。 组织可以选择性地使用其他共存模式，为最终用户提供可预测的体验，因为组织从Skype for Business到Teams。 组织为本地用户使用的任何模式，当这些用户从本地移动到云时，他们将成为 TeamsOnly (并且不能具有任何其他模式) 。  只要用户仍在使用 Skype for Business Server，就可以为其分配 TeamsOnly 外的任何模式。 如果需要，可以将 TeamsOnly 用户移回本地，这使它们能够接收租户的 TeamsUpgradePolicy 全局策略。

当用户位于任何聊天Skype for Business时，所有传入聊天和呼叫将路由到用户的Skype for Business客户端。 为了避免最终用户混淆并确保正确的路由，为分配了任何 Skype for Business 模式的用户禁用 Teams 客户端中的呼叫 *和聊天功能*。 当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，将禁用 Teams 中的会议计划，当用户处于 SfBWithTeamsCollabAndMeetings 模式时，会启用会议计划。

根据要求，可以基于组织选择的升级路径分配适当的共存模式。 有关详细信息，请参阅迁移和[互操作性指南](migration-interop-guidance-for-teams-with-skype.md)，了解将 Teams与Skype for Business一起使用和设置[共存和升级设置的组织](./setting-your-coexistence-and-upgrade-settings.md)。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步骤 3：将Skype for Business从本地移动到Teams

Microsoft 最近简化了将用户移到 TeamsOnly 的过程。 无论使用哪个版本的 Skype for Business Server 或 Lync Server 2013，此过程现在都是一个步骤。 有关详细信息，请参阅 [在本地](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)和云之间移动用户和将用户从本地移到[Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。 

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>步骤 4：通过禁用混合部署和解除本地部署，完成到云的Skype for Business

将所有用户从本地移动到云后，可以解除本地部署Skype for Business部署。 有关详细信息，请参阅[取消本地Skype for Business环境](/skypeforbusiness/hybrid/decommission-on-prem-overview)。


## <a name="phone-system-and-pstn-connectivity-options"></a>电话系统 PSTN 连接选项

电话系统 TeamsOnly Teams支持使用 Teams。  (如果用户在群岛模式下，电话系统仅支持 Skype for Business.)  

### <a name="pstn-connectivity-options"></a>PSTN 连接选项

考虑使用 PSTN (公用电话 (PSTN) 连接选项时，从本地 Skype for Business 切换到 TeamsOnly 模式时，有两种可能的情况：

- 在本地Skype for Business用户企业语音，该用户将移动到联机状态，使用 Microsoft 呼叫计划。 将该用户迁移到 Teams 需要将用户的本地 Skype for Business 帐户移动到云，并将该帐户与 A) 用户电话号码的端口转移到 Microsoft 呼叫计划或 B) 从可用区域分配新的订阅者号码协调。  有关详细信息，请参阅[从本地Skype for Business Server，使用 企业语音，到 Microsoft 呼叫计划](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- 在本地使用 Skype for Business 的用户企业语音，该用户将移动到联机并保留本地 PSTN 连接。 将该用户迁移到 Teams需要将用户的本地 Skype for Business 帐户移动到云，并协调该移动以及将用户迁移到直接路由。 有关详细信息，请参阅[从本地Skype for Business Server，使用 企业语音，到直接路由](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>在本地部署Skype for Business Server组织的重要注意事项

- 设置Skype for Business混合是迁移到 TeamsOnly 模式的先决条件。 本地用户无需混合Skype for Business Server即可在Teams模式下使用云。 但是，如果不使用 [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)（需要混合连接）将用户移动到云，则不能过渡到 TeamsOnly 模式。 有关详细信息，请参阅 [配置混合连接](/skypeforbusiness/hybrid/configure-hybrid-connectivity)。 即将停用 Skype for Business Online 不会更改此要求。 若要让组织从Skype for Business Server迁移Teams，它们仍然必须使用同一工具集来设置和配置混合，与停用前 *完全相同*。

- 若要将本地用户移到云，请使用 `Move-CsUser` 本地管理工具。 不再需要指定开关， `-MoveToTeams` 将用户从本地直接移动到 TeamsOnly。 系统会自动为用户分配 TeamsOnly 模式，其本地会议会自动转换为Teams会议 - `-MoveToTeams` 无论是否指定了开关。

- 如果组织Skype for Business Server尚未配置混合连接，但仍要使用 Teams，若要管理 Teams 功能，必须使用具有 .onmicrosoft.com 域的管理帐户。 如果没有混合连接，管理工具无法识别本地域。 

- Teams本地 (Skype for Business 帐户的用户（即，他们尚未使用 Move-CsUser) 移动到云中）不能与任何 Skype for Business 用户互操作，也不能与外部用户联合。 只有在将用户移动到云且是 TeamsOnly 用户后，此功能才可用。 

- 如果有任何用户在本地Skype for Business帐户，或者对于本地部署仍具有 lyncdiscover DNS 记录，则不能分配租户级别的 TeamsOnly 模式。 必须先使用 将具有本地 Skype for Business 帐户的所有用户移到云`Move-CsUser`中。 然后按照禁用混合中所述的步骤完成 [到](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)云的迁移，包括删除 DNS 条目。 `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`如果检测到 lyncdiscover DNS 记录指向其他位置，则租户级别Office 365。

- 必须确保用户使用正确的属性Azure AD正确同步Skype for Business同步。 这些属性都是前缀"msRTCSIP-"。 如果用户未正确同步到Azure AD，Teams中的管理工具将无法管理这些用户。  (例如，除非正确同步这些属性，否则无法将 Teams 策略分配给本地用户。) 有关详细信息，请参阅为 [Teams 和 Skype for Business 配置 Azure AD 连接](/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- 若要在混合组织中创建新的 TeamsOnly，必须先在本地 *Skype for Business Server* 中启用该用户，然后使用 Move-CsUser 将用户从本地移动到云。  首先在本地创建用户可确保任何其他剩余的本地Skype for Business用户能够路由到新创建的用户。 *所有用户都* 联机后，不再需要先在本地启用用户。

- 如果要在本地用户的 Skype for Business客户端中显示通知，则必须在本地工具集使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 参数与本地用户相关。  本地用户从 TeamsUpgradePolicy 的在线实例接收其模式。 请参阅 [Grant-CsTeamsUpgradePolicy 中的说明](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)。 

>[!NOTE]
> 2019 年 9 月 3 日之后创建的任何新租户将创建为 TeamsOnly 租户，除非组织已在本地部署 Skype for Business Server。 Microsoft 使用 DNS 记录来标识本地Skype for Business Server组织。 有关详细信息，请参阅对混合 [本地组织的 DNS 影响](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid)。 

- 以下文章介绍重要的升级概念和共存行为：
    - [Teams和Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
