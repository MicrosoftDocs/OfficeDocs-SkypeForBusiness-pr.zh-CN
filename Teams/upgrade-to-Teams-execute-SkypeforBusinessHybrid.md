---
title: 将Skype for Business混合部署升级到 Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何将组织升级为Microsoft Teams混合Skype for Business部署。
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
ms.openlocfilehash: ef173755673cf22ece6c3f8325b2d0392092c1eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840654"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>从混合Skype for Business升级到 Teams

![升级旅程的阶段，侧重于部署和实施阶段。](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")

本文是升级旅程的部署和实施阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解两者共存Skype for Business互操作性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备环境](./upgrade-prepare-environment.md)
- [为组织做好准备](./upgrade-prepare-organization.md)
- [开展试点](./pilot-essentials.md)

如果已在本地部署 Skype for Business 或 Microsoft Lync，并且已将其配置为与 Microsoft 365 或 Office 365 组织的混合部署中，并且您的组织希望选择性地升级到 Teams，或者使用多个共存模式，或者全部升级，请按照本文中的指导操作。 对于任一升级过程，需要将用户移动到 Skype for Business Online (（如果他们还没有联机) 然后为其分配适当的共存和升级模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>步骤 1：将用户移动到 Skype for Business Online

此步骤适用于当前位于本地的用户。 有关将这些用户移动到 Skype for Business Online，请参阅将用户从本地移动到[Skype for Business Online。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>步骤 2：分配共存和升级模式

将用户移动到 Skype for Business Online 后，可基于组织选择的升级过程为其分配适当的共存模式。 有关详细信息，请参阅 [设置共存和升级设置和](./setting-your-coexistence-and-upgrade-settings.md) [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。

> [!NOTE]
> 使用 Skype for Business Server 2019 和 Skype for Business Server 2015 的未来累积更新，您将能够执行步骤 1 (将用户移动到 Skype for Business Online) 和步骤 2 (将用户升级到 Teams) 单步。 2019 年 Skype for Business Server发布后，将提供详细信息。

## <a name="phone-system-and-teams-upgrade"></a>电话系统Teams升级

如果你使用呼叫计划将 Skype for Business 混合部署转换到 电话系统，并且 Microsoft 将成为你的公共电话交换网 (PSTN) 提供商，并且假定你已完成电话号码转网，将你的用户升级到 Teams 将自动将入站 PSTN 呼叫转换到 Teams。

如果呼叫计划不可用，或者你打算使用现有的 PSTN 连接提供商，则需要将企业语音部署（或使用现有本地部署或 Cloud Connector Edition 的混合语音部署）转换为 Microsoft 电话 系统直接路由。 若要将用户升级到 Teams，请参阅直接路由的其他电话系统[注意事项](./direct-routing-landing-page.md)。