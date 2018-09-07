---
title: 从联机业务的 Skype 升级到团队的 Microsoft 团队
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 业务 online 从 Skype 升级到团队的注意事项
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8102c9b4a19b78f41fda0518a04cf5525f364c47
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851130"
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


# <a name="upgrade-from-skype-for-business-online-to-teams"></a>从联机业务的 Skype 升级到团队

如果具有完全部署 Skype online 业务，并且希望向工作组从 for Business 的 Skype 升级您的用户，请遵循本文中的指南。 您可以有选择地升级用户或一体化、 基于升级历程的已选择您的组织，通过向用户分配适当的共存和升级的模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>分配的共存和升级模式

升级到团队可以通过分配 TeamsUpgradePolicy，可以使用的 Microsoft 团队 Skype Business Admin Center 或 Skype 业务远程 Windows Powershell 会话执行的 TeamsOnly 模式来实现。

有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

## <a name="phone-system-and-teams-upgrade"></a>电话系统和团队升级

如果您的业务 Online 部署的 Skype 包括电话系统与调用计划和 Microsoft 是您公用电话交换网 (pstn) 提供商，将用户升级到团队将自动转换到团队呼叫的入站的 PSTN。

如果您的业务 Online 部署的 Skype 包括与云连接器 Edition 的电话系统，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。