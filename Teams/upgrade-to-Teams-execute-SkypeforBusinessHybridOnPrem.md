---
title: 从 Skype for Business 混合或本地部署升级到 Teams - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 从业务混合或本地部署 Skype 升级到团队的注意事项。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fd4e78149dfaee58e85b9969062f324e90b7e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930810"
---
![升级旅程，重点强调部署阶段和实现阶段](media/upgrade-banner-deployment.png "升级旅程，重点强调部署阶段和实现阶段")

本文是您升级旅程的不同阶段提供部署和实施的一部分。 在继续之前，确认您已完成以下活动：

-   [登记项目利益干系人](upgrade-enlist-stakeholders.md)
-   [定义您的项目范围](https://aka.ms/SkypetoTeams-Scope)
-   [商业和团队理解共存和 Skype 的互操作性](https://aka.ms/SkypeToTeams-Coexist)
-   [选择您升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [准备您的环境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [准备您的组织](https://aka.ms/SkypeToTeams-UserReadiness)
-   [执行试验](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>从业务混合或本地部署 Skype 升级到团队

请遵循本文中的指南，如果您已经部署了 for Business 的 Skype 或 Microsoft Lync 本地和贵组织希望如何升级到团队也有选择地 — 通过使用多个共存模式 — 或一体化。 第一步是设置混合连接性与 Office 365 租户，然后您将用户移至 Skype 业务 online 和将其分配适当的共存和升级模式。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步骤 1： 部署混合连接性 

将用户升级到团队的主要先决条件是部署混合连接性。 这样做可能会为您现有的 Skype 业务或 Lync 部署新的外部连接或只使用 Office 365 租户配置混合关系。 

有关详细信息，请参阅 [部署之间 Skype 业务服务器和 Skype 业务 online 的混合连接](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。

## <a name="step-2-move-users-to-skype-for-business-online"></a>步骤 2： 将用户移动到业务 online Skype 

在您完成混合安装程序后，将用户移至 Skype 中，为业务 Online。 

有关详细信息，请参阅 [移动用户从本地到业务 online Skype](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>步骤 3： 分配共存并升级模式

您已为业务 Online 到 Skype 移动用户后，您可以将其分配基于您的组织已选择升级旅程的相应共存模式。 有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

> [!NOTE]
> 与业务服务器 2019年和未来的业务服务器 2015 Skype 的累积更新的 Skype，您将能够单步执行 （将用户移动到 Skype 业务 online） 的步骤 2 和步骤 3 （向工作组的升级用户）。 发布的业务服务器 2019 Skype 之后，将提供详细信息。

## <a name="phone-system-and-teams-upgrade"></a>电话系统和团队升级

如果您正在转换到与调用计划的电话系统的业务混合部署您 Skype 和 Microsoft 将您的公用电话交换网 (pstn) 提供商 — 和假定您已完成电话号码移植 — 升级到您的用户团队，将自动转换为入站的 PSTN 呼叫到团队。

如果调用计划不可用，则需要转换为 Microsoft 电话系统直接路由企业语音部署。 若要向工作组升级您的用户，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。
