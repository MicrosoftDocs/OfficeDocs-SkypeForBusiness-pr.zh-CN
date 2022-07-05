---
title: 将混合部署Skype for Business升级到 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何将组织从Skype for Business混合部署升级到 Microsoft Teams。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615598"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>从Skype for Business混合部署升级到 Teams

![升级过程的阶段，重点是部署和实现阶段。](media/upgrade-banner-deployment.png "升级过程的阶段，重点是部署和实施阶段")

本文是升级过程的部署和实现阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解Skype for Business和 Teams 的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备好环境](./upgrade-prepare-environment.md)
- [准备组织](./upgrade-prepare-organization.md)
- [进行了试点](./pilot-essentials.md)

如果已在本地部署Skype for Business或 Microsoft Lync，并将其配置为与 Microsoft 365 或Office 365组织的混合部署，并且组织希望选择性地升级到 Teams（使用多种共存模式）或全部升级，请遵循本文中的指导。 对于任一升级过程，如果用户尚未在联机) 中驻Skype for Business联机 (，则需要将其移动到联机) ，然后为用户分配适当的共存和升级模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>步骤 1：将用户移动到联机Skype for Business

此步骤适用于当前驻地的用户。 有关将这些用户移动到联机Skype for Business的详细信息，请参阅[将用户从本地移动到 Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>步骤 2：分配共存和升级模式

将用户移到联机Skype for Business后，可以根据组织选择的升级过程为他们分配适当的共存模式。 有关详细信息，请参阅 [“设置共存和升级设置](./setting-your-coexistence-and-upgrade-settings.md) ”和 [“TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)”。

> [!NOTE]
> 通过 Skype for Business Server 2019 和 2015 Skype for Business Server未来的累积更新，你将能够执行步骤 1 (将用户迁移到 Skype for Business Online) ，步骤 2 (单步将用户升级到 Teams) 。 2019 Skype for Business Server发布后，将提供详细信息。

## <a name="phone-system-and-teams-upgrade"></a>电话系统和 Teams 升级

如果使用呼叫计划将Skype for Business混合部署转换为电话系统，Microsoft 将成为 PSTN) 提供商 (公共交换电话网络，并且假设你已完成电话号码移植，则将用户升级到 Teams 将自动将入站 PSTN 呼叫转换为 Teams。

如果通话套餐不可用或你打算使用现有的 PSTN 连接提供程序，则需要将企业语音部署（或使用现有本地部署或云连接器版本的混合语音部署）转换为 Microsoft Phone 系统直接路由。 若要将用户升级到 Teams，请参阅 [电话系统直接路由的其他注意事项](./direct-routing-landing-page.md)。