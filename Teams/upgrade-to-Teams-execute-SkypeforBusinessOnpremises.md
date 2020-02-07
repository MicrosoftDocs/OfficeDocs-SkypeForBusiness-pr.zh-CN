---
title: 将本地 Skype for business 升级到 Microsoft 团队 |部署 |Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 从 Skype for Business 内部部署升级到团队的注意事项。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e2bcd48abb34ad3b8e18b780708e588ad9d0276
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836214"
---
![升级旅程的阶段，重点介绍部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")

本文是升级过程的部署和实施阶段的一部分。 继续之前，请确认你已完成以下活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [已选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备好你的环境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [准备好您的组织](https://aka.ms/SkypeToTeams-UserReadiness)
- [开展了一个试验](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>从 Skype for Business 内部部署升级到团队

如果你已部署 Skype for business 或 Microsoft Lync 本地版，并且你的组织希望通过使用多个共存模式（或全部）升级到 Microsoft 团队，请按照本文中的指南操作。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步骤1：部署混合连接

将用户升级到团队的关键先决条件是部署混合连接。

有关详细信息，请参阅[在 skype for Business 服务器与 skype for Business Online 之间部署混合连接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>步骤2：为你的组织实施所选升级旅程

完成混合设置后，您可以计划将用户移动到 Office 365。

有关详细信息，请参阅：

- [TeamsUpgradePolicy：管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

- [将用户从本地移动到 Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="phone-system-and-teams-upgrade"></a>电话系统和团队升级

从本地电话系统过渡到团队将允许你利用手机系统直接路由（"直接路由"）或 Microsoft 提供的适用于 Office 365 的呼叫计划。

如果您不使用 Office 365 中的通话计划，则您需要将企业语音部署切换到手机系统直接路由，作为您的团队升级的一部分。

有关详细信息，请参阅[手机系统直接路由的其他注意事项](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)。 如果您计划在 Office 365 中使用呼叫计划，请参阅我们关于将[电话号码转移到团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)的指南。