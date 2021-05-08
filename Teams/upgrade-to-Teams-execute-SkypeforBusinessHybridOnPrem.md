---
title: 在本地Skype for Business升级到 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 了解如何从本地部署Microsoft Teams升级Skype for Business升级。
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
ms.openlocfilehash: c45770258d452c3f84c707a51812d2e336ce48ee
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282169"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>从Skype for Business本地升级到 Teams

![升级过程图，强调部署和实施](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")

本文是升级旅程的部署和实施阶段的一部分。 在继续之前，请确认已经完成了以下活动:

-   [登记项目利益干系人](upgrade-enlist-stakeholders.md)
-   [请确定项目范围](./upgrade-define-project-scope.md)
-   [了解两者共存Skype for Business互操作性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [准备环境](./upgrade-prepare-environment.md)
-   [准备组织](./upgrade-prepare-organization.md)
-   [开展试点](./pilot-essentials.md)

如果您已在本地Skype for Business Server Microsoft Lync，并且您的组织想要升级到 Teams，请按照本文中的指导操作。 需要设置与组织或Microsoft 365 Office 365的混合连接，并确定在将用户分Teams共存要求。

在开始之前，IT 专业人员和管理员应查看本文稍后在本地Skype for Business Server[组织](#important-considerations-for-organizations-with-skype-for-business-server-on-premises)的重要注意事项。

> [!IMPORTANT]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大程度地实现权益并确保组织有适当的时间来实施升级，我们鼓励你立即开始Microsoft Teams之旅。 请记住，成功的升级符合技术和用户准备情况，因此，在导航到 Microsoft Teams。

## <a name="step-1-configure-hybrid-connectivity"></a>步骤 1：配置混合连接 

将本地用户升级到 Teams的主要先决条件是为本地部署Skype for Business Server混合连接。 

首先阅读规划 [混合连接](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) ，然后按照配置混合连接 [中概述的任务操作](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步骤 2：设置过渡共存模式 (可选) 

客户端和用户之间的Skype for Business Teams互操作性由升级模式Teams定义。  默认情况下，组织采用"群岛"模式，允许用户并行使用Teams Skype for Business客户端。

对于迁移到 Teams 的组织，TeamsOnly 模式是每个用户的最终目标- 尽管并非所有用户都需要同时分配 TeamsOnly (或其他) 模式。

在用户进入 TeamsOnly 模式之前，组织可以选择性地使用任何 Skype for Business 共存模式，以确保 TeamsOnly 模式下的用户与尚未登录的用户之间的通信可预测。  Skype for Business 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在组织从 Skype for Business 过渡到 Teams 时为最终用户提供简单且可预测的体验。 

当用户在任何聊天模式下Skype for Business，所有传入的聊天和呼叫将路由到用户的Skype for Business客户端。 为了避免最终用户混淆并确保正确的路由，当用户处于任何聊天模式时，Teams客户端中的呼叫和聊天Skype for Business禁用。 同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，显式禁用 Teams 中的会议计划，当用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用会议计划。

根据要求，可以基于组织选择的升级路径分配适当的共存模式。 有关详细信息，请参阅[将](migration-interop-guidance-for-teams-with-skype.md)Teams 与 Skype for Business 和设置共存和升级设置 一同使用的组织的迁移和互操作性[指南](./setting-your-coexistence-and-upgrade-settings.md)。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步骤 3：将用户Skype for Business本地移动到Teams用户

最终，需要将用户移动到 TeamsOnly 模式。 这可能涉及一个或两个步骤，具体取决于本地环境。  

有关详细信息，请参阅 [在本地](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)和云之间移动用户和将用户从本地[移动到 Teams。](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>步骤 4：禁用混合以完成到云的迁移

将所有用户从本地移动到云后，可以解除本地部署Skype for Business部署。 有关详细信息，请参阅 [禁用混合以完成到云的迁移](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。


## <a name="phone-system-and-pstn-connectivity-options"></a>电话系统和 PSTN 连接选项

电话系统 TeamsOnly Teams支持使用 Teams。  (如果用户在群岛模式下，电话系统仅支持 Skype for Business.)  

### <a name="pstn-connectivity-options"></a>PSTN 连接选项

在考虑使用 PSTN (公用电话) 时，从本地 Skype for Business 切换到 TeamsOnly 模式时，有两种可能的情况：

- 在本地使用 Skype for Business 的用户企业语音，该用户将移动到联机状态，使用 Microsoft 呼叫计划。 将该用户迁移到 Teams 需要将用户的本地 Skype for Business 帐户移动到云，并将该帐户与 A) 用户电话号码的端口转移到 Microsoft 呼叫计划或 B) 从可用区域分配新的订阅者号码协调。  有关详细信息，请参阅[从本地Skype for Business Server，使用 企业语音，到 Microsoft 呼叫计划](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- 在本地使用 Skype for Business的用户企业语音，该用户将移动到联机并保留本地 PSTN 连接。 将该用户迁移到 Teams需要将用户的本地 Skype for Business 帐户移动到云，并协调该移动，同时将用户迁移到直接路由。 有关详细信息，请参阅从[本地Skype for Business Server，使用 企业语音，到直接路由](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>在本地部署Skype for Business Server组织的重要注意事项

- 以下文章介绍重要的升级概念和共存行为：
    - [Teams 和 Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

- 设置Skype for Business混合是迁移到 TeamsOnly 模式的先决条件。 虽然可以在不混合的情况下在群岛模式下使用 Teams，但除非使用[Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) 将用户从 Skype for Business 本地移动到 Skype for Business Online (，才能过渡到 TeamsOnly 模式。 有关详细信息，请参阅 [配置混合连接](/skypeforbusiness/hybrid/configure-hybrid-connectivity)。

- 如果组织Skype for Business Server尚未配置混合连接，但仍想使用 Teams 管理 Teams 功能，则必须使用具有 .onmicrosoft.com 域的管理帐户。 

- Teams本地 Skype for Business (帐户（即，他们尚未使用 Move-CsUser) 移动到云中）的用户不能与任何 Skype for Business 用户互操作，也不能与外部用户联合。 只有在将用户移动到位于群岛模式或 TeamsOnly 用户 (云环境后，此功能才) 。 

- 如果有任何用户在本地Skype for Business帐户，则不能在租户级别分配 TeamsOnly 模式。 必须先使用 将具有本地 Skype for Business 帐户的所有用户移到云，然后禁用混合以 `Move-CsUser` [完成到云的迁移](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`如果检测到 lyncdiscover DNS 记录指向其他位置，则租户级别Office 365。

- 必须确保用户使用正确的属性正确同步到 Azure AD Skype for Business属性。 这些属性都是前缀"msRTCSIP-"。 如果用户未正确同步到 Azure AD，Teams管理这些用户。  (例如，除非正确同步这些属性，否则无法将 Teams 策略分配给本地用户。) 有关详细信息，请参阅为 Teams 和 Skype for Business 配置[Azure AD 连接。](/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- 若要在混合组织中创建新的 TeamsOnly 或 Skype for Business Online 用户，必须先在本地 *Skype for Business Server* 中启用该用户，然后使用 Move-CsUser 将用户从本地移动到云。  首先在本地创建用户可确保任何其他剩余的本地Skype for Business用户能够路由到新创建的用户。 所有用户都联机后，不再需要先在本地启用用户。

- 当用户从本地移动到云时，由该用户组织的会议将迁移到 Skype for Business Online 或 Teams -具体取决于是否指定了 -MoveToTeams 开关。

- 如果要在本地用户的 Skype for Business客户端中显示通知，则必须在本地工具集使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 参数与本地用户相关。  本地用户从 TeamsUpgradePolicy 的在线实例接收其模式。 请参阅 [Grant-CsTeamsUpgradePolicy 中的说明](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)。 

>[!NOTE]
> 2019 年 9 月 3 日之后创建的任何新租户将创建为 TeamsOnly 租户，除非组织已在本地部署 Skype for Business Server。 Microsoft 使用 DNS 记录来标识本地Skype for Business Server组织。 如果组织具有本地 Skype for Business Server没有公共 DNS 条目，则需要致电 Microsoft 支持部门，将新租户降级。 

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)