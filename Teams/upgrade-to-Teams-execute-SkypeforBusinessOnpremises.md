---
title: 将本地 Skype for Business 升级到 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何将组织从 Skype for Business 本地部署过渡到 Microsoft Teams。
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115550"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>从 Skype for Business 本地部署升级到 Teams

![升级旅程的阶段，着重强调部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")

本文是升级旅程的部署和实施阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解 Skype for Business 和 Teams 的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备环境](./upgrade-prepare-environment.md)
- [准备组织](./upgrade-prepare-organization.md)
- [开展试点](./pilot-essentials.md)

如果你已在本地部署 Skype for Business 或 Microsoft Lync，并且你的组织想要选择性地升级到 Microsoft Teams（通过使用多种共存模式）或一切功能，请按照本文中的指导操作。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步骤 1：部署混合连接

将用户升级到 Teams 的关键先决条件是部署混合连接。

有关详细信息，请参阅在 Skype for Business Server 和 [Skype for Business Online 之间部署混合连接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>步骤 2：为组织实施所选的升级过程

完成混合设置后，可以计划将用户移动到 Microsoft 365 或 Office 365。

有关详细信息，请参阅：

- [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。

- [将用户从本地移动到 Skype for Business Online。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>手机系统和 Teams 升级

从本地电话系统转换到 Teams 将允许你利用电话系统直接路由 ("直接路由") 或 Microsoft 提供的适用于 Microsoft 365 或 Office 365 的呼叫计划。

如果不使用呼叫计划，则需要在升级到 Teams 期间，将企业语音部署转换为电话系统直接路由。

有关详细信息，请参阅 [电话系统直接路由的其他注意事项](./direct-routing-landing-page.md)。 如果你计划使用通话套餐，请参阅我们的指南，将你的电话号码转移到[Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)