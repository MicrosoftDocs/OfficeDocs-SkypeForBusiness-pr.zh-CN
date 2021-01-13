---
title: 将 Skype for Business 混合部署升级到 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从 Skype for Business 混合部署将组织升级到 Microsoft Teams。
localization_priority: Normal
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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802342"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>从 Skype for Business 混合部署升级到 Teams

![升级过程阶段，侧重于部署和实施阶段](media/upgrade-banner-deployment.png "升级过程阶段，侧重于部署和实施阶段")

本文是升级旅程的部署和实施阶段的一部分。 在继续之前，请确认已完成以下活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和 Teams 的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备好环境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [为组织做好准备](https://aka.ms/SkypeToTeams-UserReadiness)
- [开展试点](https://aka.ms/SkypeToTeams-Pilot)

如果你已在本地部署 Skype for Business 或 Microsoft Lync，并且已与 Microsoft 365 或 Office 365 组织在混合部署中配置了 Skype for Business 或 Microsoft Lync，并且你的组织希望选择性地升级到 Teams，或者使用多种共存模式或一切功能进行升级，请遵循本文中的指导。 对于任一升级过程，你都需要将用户移动到 Skype for Business Online (如果他们还没有在线家庭) 然后为其分配适当的共存和升级模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>步骤 1：将用户移动到 Skype for Business Online

此步骤适用于当前位于本地的用户。 有关将这些用户移动到 Skype for Business Online 的信息，请参阅"将用户从本地移动到[Skype for Business Online"。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>步骤 2：分配共存和升级模式

将用户移动到 Skype for Business Online 后，你可以根据组织选择的升级旅程为其分配适当的共存模式。 有关详细信息，请参阅 ["设置共存](https://aka.ms/SkypeToTeams-SetCoexistence) 和升级设置"和 [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。

> [!NOTE]
> 使用 Skype for Business Server 2019 和 Skype for Business Server 2015 的未来累积更新，你将能够执行步骤 1 (将用户移动到 Skype for Business Online) ，并且步骤 2 (通过单个步骤将用户升级到 Teams) 。 发布 Skype for Business Server 2019 后，将提供更多信息。

## <a name="phone-system-and-teams-upgrade"></a>手机系统和 Teams 升级

如果你正在使用通话计划将 Skype for Business 混合部署转换到电话系统，并且 Microsoft 将成为你的公共电话交换网 (PSTN) 提供商，并且假设你已完成电话号码转网，将你的用户升级到 Teams 将自动将入站 PSTN 呼叫转换到 Teams。

如果呼叫计划不可用，或者你计划使用现有的 PSTN 连接提供商，则需要将企业语音部署（或使用现有本地部署或 Cloud Connector Edition 的混合语音部署）转换为 Microsoft Phone 系统直接路由。 若要将用户升级到 Teams，请参阅电话系统直接 [路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。
