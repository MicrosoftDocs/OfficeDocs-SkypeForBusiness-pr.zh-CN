---
title: 将 Skype for Business Online 升级到 Microsoft 团队 |部署
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 从 Skype for Business Online 升级到团队的注意事项
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
ms.openlocfilehash: 3a9cedd0a169fc43e81dfdc131f98b0a90d9cd9e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836224"
---
![升级旅行图，强调部署和实现](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")

本文是升级过程的部署和实施阶段的一部分。 继续之前，请确认你已完成以下活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [已选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备好你的环境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [准备好您的组织](https://aka.ms/SkypeToTeams-UserReadiness)
- [开展了一个试验](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>从 Skype for Business Online 升级到 Teams

如果已部署了完全部署的 Skype for business Online，并且想要将用户从 Skype for Business 升级到团队，请按照本文中的指南操作。 通过为用户分配适当的共存和升级模式，你可以有选择地或从你的组织选择的升级历程升级用户。

> [!IMPORTANT]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大程度地实现收益并确保你的组织有适当的时间实施升级，我们鼓励你立即开始迁移到 Microsoft 团队。 请记住，成功升级会使技术和用户准备相一致，因此，在您向 Microsoft 团队导航旅行时，请务必利用本指南。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>分配共存和升级模式

你可以通过分配 TeamsUpgradePolicy 的 UpgradeToTeams 实例将你的用户升级到 TeamsOnly 模式，这可以通过使用 Microsoft 团队管理中心或 Skype for business 远程 Windows Powershell 会话来执行。 你可以基于每个用户执行此操作，也可以在租户范围内执行此操作，前提是要在一个步骤中升级整个租户。 

有关详细信息，请参阅[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy：管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一次将所有用户升级到团队

请按照以下步骤一次将所有用户升级到团队。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>步骤1：将更改通知给用户（可选）

1. 在 "Microsoft 团队管理中心" 中，选择 "**组织范围设置** > **团队升级**"。
2. 在 "**共存模式**" 下，更改 "**通知 Skype for business" 用户是否有升级到团队的功能**切换到 **"开**"。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>步骤2：将组织的共存模式设置为 TeamsOnly

1. 在 "Microsoft 团队管理中心" 中，选择 "**组织范围的设置**"。
2. 从 "**共存模式**" 下拉列表中选择 "**仅团队**模式"。

## <a name="upgrade-users-in-stages"></a>分阶段升级用户

如果想要将用户逐步升级到 TeamsOnly，请执行以下步骤。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>步骤1：确定要升级的用户组

组织通常可以选择在用户成功的用户的成功波上升级其组织。  你将首先确定这些用户，以便可以在 Microsoft 团队管理中心轻松搜索它们。 或者，你可能希望使用 PowerShell 更高效地执行此操作。 一旦确定了给定升级 wave 的用户集，请继续执行剩余步骤。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>步骤2：为当前升级浪潮中的用户设置通知（可选）

如果使用的是 Microsoft 团队管理中心，则可以同时为多达20个用户配置 TeamsUpgradePolicy：
1. 在 Microsoft 团队管理中心，选择 "**用户**"，然后找到多达20个应升级的用户的复选框，然后多选。 
2. 选择 listview 左上角的 "**编辑设置**"。 
3. 在右侧的 "**编辑设置**" 窗格中，在 "**团队升级**" 下，"更改**通知 Skype for Business 用户**" 切换到 **"打开"**。 注意：如果 "共存" 模式的值为 "使用组织范围的设置"，你将看不到此开关，因此你需要首先将这些用户的共存模式显式设置为组织的默认值。

或者，你可能会发现使用 PowerShell 一次性为用户组启用通知更容易。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>步骤3：将用户的共存模式设置为 "仅限团队"

准备好升级当前浪潮中的用户以使用团队作为其唯一的应用程序时，将用户的共存模式设置为 "仅限团队"。

如果使用的是 Microsoft 团队管理中心，则可以同时为多达20个用户配置 TeamsUpgradePolicy：
1. 在 Microsoft 团队管理中心，选择 "**用户**"，然后选择最多20个用户的复选框。
2. 选择 listview 左上角的 "**编辑设置**"。
3. 在右侧的 "**编辑设置**" 窗格中，在 "**团队升级**" 部分中，在下拉列表中将 "共存模式" 设置为 "**仅限团队团队**"。

或者，你可能会发现使用 PowerShell 一次性升级用户组更容易。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>步骤4：对连续的用户波形重复步骤1-3

当你验证升级到 "仅团队" 模式并准备好进行扩展时，请重复前面的步骤以将 TeamsOnly 应用于更多用户。  


## <a name="phone-system-and-teams-upgrade"></a>电话系统和团队升级

如果您的 Skype for Business Online 部署包括带有呼叫计划的电话系统，并且 Microsoft 是您的公共交换电话网络（PSTN）提供商，则将用户升级到团队会自动将入站 PSTN 呼叫转到团队。

如果您的 Skype for Business Online 部署包括带有云连接器版本的电话系统，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。
