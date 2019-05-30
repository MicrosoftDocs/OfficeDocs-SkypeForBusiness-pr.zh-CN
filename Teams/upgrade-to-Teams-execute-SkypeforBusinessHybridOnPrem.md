---
title: 从 Skype for Business 混合或本地部署升级到 Teams - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 从 Skype for Business 混合或内部部署升级到团队的注意事项。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 118bae776f4bb3709d62dea1f384ccaa0707397b
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493976"
---
![升级旅行图, 强调部署和实现](media/upgrade-banner-deployment.png "升级旅程的阶段, 重点介绍部署和实施阶段")

本文是升级过程的部署和实施阶段的一部分。 继续之前, 请确认你已完成以下活动:

-   [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
-   [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
-   [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
-   [已选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [准备好你的环境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [准备好您的组织](https://aka.ms/SkypeToTeams-UserReadiness)
-   [开展了一个试验](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>从 Skype for Business 混合或内部部署升级到团队

如果你已部署 Skype for business 或 Microsoft Lync 本地版, 并且你的组织希望通过使用多个共存模式 (或全部) 升级到团队, 请按照本文中的指南操作。 第一步是设置与 Office 365 租户的混合连接, 然后将用户移动到 Skype for business Online, 并为他们分配适当的共存和升级模式。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步骤 1: 部署混合连接 

将用户升级到团队的关键先决条件是部署混合连接。 这可能涉及为现有 Skype for Business 或 Lync 部署部署新的外部连接, 或者只需配置与你的 Office 365 租户的混合关系。 

有关详细信息, 请参阅 [在 skype for Business 服务器与 skype for Business Online 之间部署混合连接](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。

## <a name="step-2-move-users-to-skype-for-business-online"></a>步骤 2: 将用户移动到 Skype for Business Online 

完成混合设置后, 将用户移动到 Skype for business Online。 

有关详细信息, 请参阅 [将用户从本地移动到 Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>步骤 3: 分配共存和升级模式

将用户移动到 Skype for Business Online 后, 您可以根据组织选择的升级历程为他们分配适当的共存模式。 有关详细信息, 请参阅[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy: 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

> [!NOTE]
> 使用 Skype for business Server 2019 和 Skype for Business Server 2015 的未来累积更新, 你将能够执行步骤 2 (将用户移动到 Skype for business Online) 和步骤 3 (在将用户升级到团队) 中执行一步操作。 在发布 Skype for Business Server 2019 后, 将提供详细信息。

## <a name="phone-system-and-teams-upgrade"></a>电话系统和团队升级

如果你正在将 Skype for Business 混合部署转换为带有呼叫计划的电话系统, Microsoft 将成为您的公共交换电话网络 (PSTN) 提供商, 并假设你已完成电话号码移植-升级你的用户以团队将向团队自动切换入站 PSTN 呼叫。

如果通话计划不可用, 则需要将企业语音部署切换到 Microsoft Phone 系统直接路由。 若要将用户升级到团队, 请参阅[手机系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。
