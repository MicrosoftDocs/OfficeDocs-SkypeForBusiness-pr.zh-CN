---
title: 将本地 Skype for Business 升级到 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何将组织从本地部署Skype for Business转换为 Microsoft Teams。
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
ms.openlocfilehash: 7b06134a0fe0f72e8dc9c01b4faa85c67a6063f3
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615438"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>从Skype for Business本地部署升级到 Teams

![升级过程的阶段，重点是部署和实现阶段。](media/upgrade-banner-deployment.png "升级过程的阶段，重点是部署和实施阶段")

本文是升级过程的“部署和实现”阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解Skype for Business和 Teams 的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备好环境](./upgrade-prepare-environment.md)
- [准备组织](./upgrade-prepare-organization.md)
- [进行了试点](./pilot-essentials.md)

如果已在本地部署Skype for Business或 Microsoft Lync，并且组织希望选择性地升级到 Microsoft Teams（使用多种共存模式）或全入，请遵循本文中的指导。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步骤 1：部署混合连接

将用户升级到 Teams 的关键先决条件是部署混合连接。

有关详细信息，请参阅[在 Skype for Business Server 和 Skype for Business Online 之间部署混合连接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>步骤 2：为组织实现所选升级过程

完成混合设置后，可以计划将用户移动到 Microsoft 365 或Office 365。

有关详细信息，请参阅：

- [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。

- [将用户从本地移动到 Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="phone-system-and-teams-upgrade"></a>电话系统和 Teams 升级

从本地电话系统过渡到 Teams 将允许你利用电话系统直接路由 (“直接路由”) 或 Microsoft 提供的适用于 Microsoft 365 或Office 365的呼叫计划。

如果不使用呼叫计划，则需要将企业语音部署转换为电话系统直接路由，作为升级到 Teams 的一部分。

有关详细信息，请参阅 [电话系统直接路由的其他注意事项](./direct-routing-landing-page.md)。 如果计划使用通话套餐，请参阅我们有关 [将电话号码传输到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 的指南。