---
title: 将 Skype for business 混合部署升级到团队
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从 Skype for Business 混合部署将组织升级到 Microsoft 团队。
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
ms.openlocfilehash: 72786dc2ef5cefe7c3c87c5a376cc01d93a2c22c
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940512"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>从 Skype for Business 混合部署升级到团队

![升级旅程的阶段，重点介绍部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")

本文是升级过程的部署和实施阶段的一部分。 继续之前，请确认你已完成以下活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [已选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备好你的环境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [准备好您的组织](https://aka.ms/SkypeToTeams-UserReadiness)
- [开展了一个试验](https://aka.ms/SkypeToTeams-Pilot)

如果你已在本地部署 Skype for business 或 Microsoft Lync，并在与你的 Microsoft 365 或 Office 365 组织进行混合部署中配置它，并且你的组织希望通过使用多种共存模式（或多功能）升级到团队，请按照本文中的指南操作。 对于升级旅程，你需要将你的用户移动到 Skype for business Online (（如果他们尚未处于联机状态) ），然后为他们分配适当的共存和升级模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>步骤1：将用户移动到 Skype for business Online

此步骤适用于当前驻留在本地的用户。 有关将这些用户移动到 Skype for business Online 的详细信息，请参阅 [将用户从本地移动到 skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>步骤2：分配共存和升级模式

将用户移动到 Skype for Business Online 后，您可以根据组织选择的升级历程为他们分配适当的共存模式。 有关详细信息，请参阅 [设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence) 和 [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。

> [!NOTE]
> 使用 Skype for Business Server 2019 和 Skype for Business Server 2015 的未来累积更新，你将能够执行步骤 1 (将用户移动到 Skype for business Online) 和步骤 2 (将用户升级到团队) 单个步骤。 在发布 Skype for Business Server 2019 后，将提供详细信息。

## <a name="phone-system-and-teams-upgrade"></a>电话系统和团队升级

如果你正在将 Skype for Business 混合部署转换为带有呼叫计划的电话系统，Microsoft 将成为您的公共交换电话网络 (PSTN) 提供商，并假定你已完成电话号码移植-将你的用户升级到团队会自动将入站 PSTN 呼叫转到团队。

如果通话计划不可用或你打算使用现有的 PSTN 连接提供程序，则需要将你的企业语音部署（或使用现有本地部署或云连接器版本的混合语音部署）转换为 Microsoft Phone 系统直接路由。 若要将用户升级到团队，请参阅 [手机系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。
