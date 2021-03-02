---
title: 将本地 Skype for Business 升级到 Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 了解如何将组织从 Skype for Business 本地部署升级到 Microsoft Teams。
localization_priority: Normal
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
ms.openlocfilehash: 7bd7d2fad4e4c35a26bcbb435caba5898dd54534
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397547"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>从本地 Skype for Business 升级到 Teams

![升级过程图，强调部署和实施](media/upgrade-banner-deployment.png "升级旅程的阶段，强调部署和实施阶段")

本文是升级过程部署和实施阶段的一部分。 在继续之前，请确认已完成以下活动：

-   [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
-   [定义项目范围](https://aka.ms/SkypetoTeams-Scope)
-   [了解 Skype for Business 和 Teams 的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
-   [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [准备环境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [为组织做好准备](https://aka.ms/SkypeToTeams-UserReadiness)
-   [进行试点](https://aka.ms/SkypeToTeams-Pilot)

如果你已在本地部署了 Skype for Business Server 或 Microsoft Lync，并且你的组织想要升级到 Teams，请按照本文中的指导操作。 需要设置与 Microsoft 365 或 Office 365 组织的混合连接，并确定分阶段将用户迁移到 Teams 时需满足的共存要求。

在开始之前，IT 专业人员和管理员应查看本文稍后在本地使用 [Skype for Business Server](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) 的组织的重要注意事项。

> [!IMPORTANT]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大限度地实现权益并确保组织有适当的时间来实施升级，我们建议你立即开始 Microsoft Teams 之旅。 请记住，成功的升级符合技术和用户准备情况，因此在导航到 Microsoft Teams 旅程时，请务必利用此处的指导。

## <a name="step-1-configure-hybrid-connectivity"></a>步骤 1：配置混合连接 

将本地用户升级到 Teams 的关键先决条件是配置 Skype for Business Server 本地部署的混合连接。 

首先阅读 ["规划混合连接"，](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 然后按照"配置混合连接 ["中概述的任务操作](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步骤 2：设置过渡共存模式 (可选) 

Skype for Business 与 Teams 客户端与用户之间的共存和互操作性由 Teams 升级模式定义。  默认情况下，组织采用群岛模式，允许用户并排使用 Teams 和 Skype for Business 客户端。

对于迁移到 Teams 的组织，TeamsOnly 模式是每个用户的最终目标 -尽管并非所有用户都需要同时分配 TeamsOnly (或其他) 模式。

在用户进入 TeamsOnly 模式之前，组织可以选择性地使用任何 Skype for Business 共存模式，以确保 TeamsOnly 模式下的用户与尚未进入 TeamsOnly 模式的用户之间的通信可预测。  Skype for Business 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在组织从 Skype for Business 过渡到 Teams 时为最终用户提供简单且可预测的体验。 

当用户在任何 Skype for Business 模式下时，所有传入聊天和呼叫将路由到用户的 Skype for Business 客户端。 为了避免最终用户混淆并确保正确的路由，当用户处于任何 Skype for Business 模式时，Teams 客户端中的呼叫和聊天功能将被禁用。 同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，明确禁用 Teams 中的会议计划，当用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用。

根据要求，你可以根据组织选择的升级路径分配适当的共存模式。 有关详细信息，请参阅将 [Teams](migration-interop-guidance-for-teams-with-skype.md) 与 Skype for Business 一同使用的组织迁移和互操作性指南，以及 [设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步骤 3：将用户从本地 Skype for Business 移到仅 Teams

最终，需要将用户移动到 TeamsOnly 模式。 这可能涉及一两个步骤，具体取决于本地环境。  

有关详细信息，请参阅 ["在本地](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)和云之间移动用户"和"将用户从本地移到[Teams"。](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>步骤 4：禁用混合以完成到云的迁移

将所有用户从本地移动到云后，可以解除本地 Skype for Business 部署。 有关详细信息，请参阅["禁用混合以完成迁移到云"。](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>电话系统和 PSTN 连接选项

在用户进入 TeamsOnly 模式后，支持使用 Teams 的电话系统。  (如果用户在群岛模式下，则电话系统仅支持 Skype for Business.)  

### <a name="pstn-connectivity-options"></a>PSTN 连接选项

在考虑公共电话交换网 (PSTN) 连接选项时，从本地 Skype for Business 迁移到 TeamsOnly 模式时，有两种可能的情况：

- 在本地使用 Skype for Business 的用户企业语音，该用户将移动到联机状态，使用 Microsoft 呼叫计划。 将该用户迁移到 Teams 需要将用户本地 Skype for Business 帐户移动到云，并配合 A) 将该用户的电话号码的端口移动到 Microsoft 呼叫计划，或者 B) 从可用区域分配新的订阅者号码。  有关详细信息，请参阅从 [本地 Skype for Business Server（带 企业语音）到 Microsoft 呼叫计划](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- 本地 Skype for Business 中具有 企业语音 的用户，该用户将移动到联机并保留本地 PSTN 连接。 将该用户迁移到 Teams 需要将用户本地 Skype for Business 帐户移动到云，并协调用户迁移到直接路由。 有关详细信息，请参阅"从 [本地 Skype for Business Server（带企业语音）到直接路由](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>使用本地 Skype for Business Server 的组织的重要注意事项

- 以下文章介绍重要的升级概念和共存行为：
    - [Teams 和 Skype for Business 共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

- 设置 Skype for Business 混合是迁移到 TeamsOnly 模式的先决条件。 虽然可以在不带混合模式的群岛模式下使用 Teams，但除非使用 [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) 将用户从本地 Skype for Business 移动到 Skype for Business Online (，才能过渡到 TeamsOnly) 。 有关详细信息，请参阅"配置[混合连接"。](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- 如果你的组织具有 Skype for Business Server，并且你尚未配置混合连接，但你仍希望使用 Teams 来管理 Teams 功能，则必须使用具有 .onmicrosoft.com 域的管理帐户。 

- 拥有本地 (Skype for Business 帐户的 Teams 用户（即，他们尚未使用 Move-CsUser) 移动到云中）不能与任何 Skype for Business 用户互操作，也不能与外部用户联合。 只有在将用户移动到以群岛模式或 TeamsOnly 用户 (云环境后，此功能才) 。 

- 如果有任何用户在本地拥有 Skype for Business 帐户，则不能在租户级别分配 TeamsOnly 模式。 必须先使用本地 Skype for Business 帐户将所有用户移到云，然后禁用混合以 `Move-CsUser` [完成到云的迁移](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` 如果检测到指向 Office 365 外部位置的 lyncdiscover DNS 记录，该记录在租户级别将不起作用。

- 必须确保使用正确的 Skype for Business 属性将用户正确同步到 Azure AD。 这些属性都是带"msRTCSIP-"的前缀。 如果用户未正确同步到 Azure AD，Teams 中的管理工具将无法管理这些用户。  (例如，除非正确同步这些属性，否则无法将 Teams 策略分配给本地用户。) 有关详细信息，请参阅"为 Teams 和 Skype for Business 配置 Azure [AD Connect"。](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- 若要在混合组织中创建新的 TeamsOnly 或 Skype for Business Online 用户，必须先在本地 *Skype for Business Server* 中启用该用户，然后使用 Move-CsUser 将用户从本地移动到云。  首先在本地创建用户可确保任何其他剩余的本地 Skype for Business 用户能够路由到新创建的用户。 所有用户联机移动后，不再需要先在本地启用用户。

- 当用户从本地移动到云时，由该用户组织的会议将迁移到 Skype for Business Online 或 Teams-具体取决于是否指定了 -MoveToTeams 开关。

- 如果要在本地用户的 Skype for Business 客户端中显示通知，则必须在本地工具集中使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 参数与本地用户相关。  本地用户从 TeamsUpgradePolicy 的在线实例接收其模式。 请参阅 [Grant-CsTeamsUpgradePolicy 中的说明](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)。 

>[!NOTE]
> 2019 年 9 月 3 日之后创建的任何新租户将创建为 TeamsOnly 租户，除非组织已在本地部署 Skype for Business Server。 Microsoft 使用 DNS 记录来标识本地 Skype for Business Server 组织。 如果你的组织具有本地 Skype for Business Server，但没有公共 DNS 条目，则需要致电 Microsoft 支持部门，将新租户降级。 

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[在 Skype for Business Server 与 Microsoft 365 或 Office 365 之间配置混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)