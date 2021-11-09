---
title: 将本地 Skype for Business 升级到 Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何将组织从本地Microsoft Teams转换为Skype for Business部署。
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
ms.openlocfilehash: b6d8c95b34345bd6ea6203abbb099c7071c9db60
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846015"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>从 Skype for Business 本地部署升级到 Teams

![升级旅程的阶段，侧重于部署和实施阶段。](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")

本文是升级旅程的部署和实施阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解两者共存Skype for Business互操作性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备环境](./upgrade-prepare-environment.md)
- [为组织做好准备](./upgrade-prepare-organization.md)
- [开展试点](./pilot-essentials.md)

如果已在本地部署 Skype for Business 或 Microsoft Lync，并且您的组织希望选择性地升级到 Microsoft Teams，或者使用多个共存模式，或全部升级，请按照本文中的指导操作。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步骤 1：部署混合连接

将用户升级到 Teams的主要先决条件是部署混合连接。

有关详细信息，请参阅在 Skype for Business Server 与[Skype for Business Online 之间部署混合连接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>步骤 2：为组织实施所选的升级过程

完成混合设置后，可以计划将用户移动到 Microsoft 365 或 Office 365。

有关详细信息，请参阅：

- [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。

- [将用户从本地移动到 Skype for Business Online。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>电话系统Teams升级

从本地电话系统转换到 Teams 将允许你利用 电话系统 直接路由 ("直接路由") 或 Microsoft 提供的 Microsoft 365 或 Office 365 呼叫计划。

如果不使用呼叫计划，则需要在升级到 电话系统 过程中将企业语音部署电话系统直接路由Teams。

有关详细信息，请参阅直接[路由的其他电话系统注意事项](./direct-routing-landing-page.md)。 如果你计划使用呼叫计划，请参阅我们的指南，将你的电话号码转移到[Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)