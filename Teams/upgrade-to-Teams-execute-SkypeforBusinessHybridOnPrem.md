---
title: 将本地 Skype for Business 升级到 Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 了解如何从 Skype for Business 内部部署将你的组织升级到 Microsoft 团队。
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
ms.openlocfilehash: 1981640ab06d00e7895e11c0e15adf7555577908
ms.sourcegitcommit: b23d3d583910aa21a62ea69b554ab614c1ae8079
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648603"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>从本地 Skype for Business 升级到团队

![升级旅行图，强调部署和实现](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")

本文是升级过程的部署和实施阶段的一部分。 继续之前，请确认你已完成以下活动：

-   [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
-   [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
-   [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
-   [已选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [准备好你的环境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [准备好您的组织](https://aka.ms/SkypeToTeams-UserReadiness)
-   [开展了一个试验](https://aka.ms/SkypeToTeams-Pilot)

如果你已部署 Skype for Business 服务器或 Microsoft Lync 本地版，并且你的组织希望升级到团队，请按照本文中的指南操作。 你需要设置与 Microsoft 365 或 Office 365 组织的混合连接，并确定在阶段将用户移动到团队的共存要求。 

> [!IMPORTANT]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大程度地实现收益并确保你的组织有适当的时间实施升级，我们鼓励你立即开始迁移到 Microsoft 团队。 请记住，成功升级会使技术和用户准备相一致，因此，在您向 Microsoft 团队导航旅行时，请务必利用本指南。

## <a name="step-1-configure-hybrid-connectivity"></a>步骤1：配置混合连接 

将本地用户升级到团队的主要先决条件是为您的 Skype for Business Server 内部部署配置混合连接。 

首先阅读 [计划混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)，然后按照[配置混合连接](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)中概述的任务操作。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步骤2：设置过渡的共存模式 (可选) 

Skype for Business 和团队客户端和用户之间的共存和互操作性由团队升级模式定义。  默认情况下，组织处于 "孤岛" 模式，允许用户并排使用团队和 Skype for business 客户端。

对于迁移到团队的组织，TeamsOnly 模式是每个用户的最终目标，但并非所有用户都需要同时分配 TeamsOnly (或任何其他模式) 。

在用户到达 TeamsOnly 模式之前，组织可以选择使用任何 Skype for Business 共存模式，以确保处于 TeamsOnly 模式的用户和尚未使用的用户之间可预测的通信。  Skype for Business 共存模式的用途 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 是为最终用户提供简单、可预测的体验，因为组织从 Skype for Business 过渡到团队。 

当用户处于任何 Skype for Business 模式时，所有传入聊天和通话都将路由到用户的 Skype for business 客户端。 为避免最终用户混淆和确保正确路由，当用户处于任何 Skype for Business 模式时，将禁用团队客户端中的 "调用和聊天" 功能。 同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，将显式禁用团队中的会议计划，并在用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用。

根据你的需求，你可以根据你的组织选择的升级路径分配适当的共存模式。 有关详细信息，请参阅与 Skype for Business 一起使用团队和[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)[的组织的迁移和互操作指南](migration-interop-guidance-for-teams-with-skype.md)。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步骤3：仅将用户从本地 Skype for business 移动到团队

最后，你需要将用户移动到 TeamsOnly 模式。 这可能会涉及一个或两个步骤，具体取决于你的本地环境。  

有关详细信息，请参阅 [在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)以及[将用户从本地移动到团队](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>步骤4：禁用混合以完成到云的迁移

将所有用户从本地迁移到云后，您可以取消本地 Skype for business 部署。 有关详细信息，请参阅[禁用混合以完成到云的迁移](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。


## <a name="phone-system-and-pstn-connectivity-options"></a>电话系统和 PSTN 连接选项

用户处于 TeamsOnly 模式后，支持团队的电话系统。  (如果用户处于 "孤岛" 模式，则只有 Skype for Business 才支持电话系统。 )  

### <a name="pstn-connectivity-options"></a>PSTN 连接选项

当考虑公共交换电话网络 (PSTN) 连接选项时，在从 Skype for Business 从本地迁移到 TeamsOnly 模式时，有两种可能的方案：

- 使用企业语音的 Skype for Business online 中的用户，这些用户将移动到联机并使用 Microsoft 通话计划。 将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并使用) 该用户电话号码的端口与 Microsoft 通话计划或 B 进行协调，) 从可用区域分配新的订户号码。  有关详细信息，请参阅[从本地 Skype For Business 服务器（具有企业语音）到 Microsoft 通话计划](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- 使用企业语音的 Skype for Business online 中的用户，这些用户将移动到联机状态并保持本地 PSTN 连接。 将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并通过将用户迁移到直接路由来协调该用户。 有关详细信息，请参阅[从本地 Skype For Business 服务器（具有企业语音）到直接路由](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。
