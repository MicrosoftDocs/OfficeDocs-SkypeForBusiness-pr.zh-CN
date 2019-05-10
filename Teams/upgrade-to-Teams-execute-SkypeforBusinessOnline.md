---
title: 升级到 Microsoft 团队在线业务 Skype |部署
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 业务 online 从 Skype 升级到团队的注意事项
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc1334e019abadb030199518df15b0dde74dde52
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835332"
---
![升级旅程，重点强调部署阶段和实现阶段](media/upgrade-banner-deployment.png "升级旅程，重点强调部署阶段和实现阶段")

本文是您升级旅程的不同阶段提供部署和实施的一部分。 在继续之前，确认您已完成以下活动：

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [定义您的项目范围](https://aka.ms/SkypetoTeams-Scope)
- [商业和团队理解共存和 Skype 的互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [选择您升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备您的环境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [准备您的组织](https://aka.ms/SkypeToTeams-UserReadiness)
- [执行试验](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>从 Skype for Business Online 升级到 Teams

如果具有完全部署 Skype online 业务，并且希望向工作组从 for Business 的 Skype 升级您的用户，请遵循本文中的指南。 您可以有选择地升级用户或一体化、 基于升级历程的已选择您的组织，通过向用户分配适当的共存和升级的模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>分配的共存和升级模式

您可以通过分配 TeamsUpgradePolicy，可以执行的业务远程 Windows Powershell 会话中使用的 Microsoft 团队管理中心或 Skype 的 UpgradeToTeams 实例升级到 TeamsOnly 模式的用户。 您可以这样做基于每个用户，或在租户范围内如果希望 ugprade 一个步骤中的整个租户。 

有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一次升级到团队的所有用户

按照以下步骤一次将所有用户升级到团队。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>步骤 1： 通知用户的更改 （可选）

1. 在 Microsoft 团队管理中心，选择**组织范围设置** > **团队升级**。
2. **共存模式**下, 到**上**更改的**通知的 Skype 业务用户升级到团队是可用的**开关。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>步骤 2： 将共存模式设置为 TeamsOnly 组织

1. 在 Microsoft 团队管理中心中，选择**组织范围的设置**。
2. 从**共存模式**下拉列表中选择**仅团队**模式。

## <a name="upgrade-users-in-stages"></a>分阶段升级用户

如果您想要在用户逐步升级到 TeamsOnly，请按照以下步骤。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>步骤 1： 确定升级的用户组

通常组织可以选择升级成功随后在其组织的用户。  您需要先确定这些用户，以便您可以方便地搜索联系人在管理中心中的 Microsoft 团队。 此外，您可能想要使用 PowerShell 更有效地执行此操作。 一旦您确定的给定升级波形的用户数，继续执行其余步骤。

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a>步骤 2： 为用户的通知中设置当前 ugprade wave （可选）

如果使用的 Microsoft 团队管理中心，您可以同时为最多 20 个用户配置 TeamsUpgradePolicy:
1. 在 Microsoft 团队管理中心中，选择**用户**和查找和多重选择应升级的最多 20 个用户的复选框。 
2. 在列表视图的左上角中，选择**编辑设置**。 
3. 在右侧，在**升级团队**、 下的**编辑设置**窗格中更改为**上**的**通知业务用户 Skype**交换机。 注意： 如果共存模式的值为"使用组织范围设置"，您将不会看到此开关，因此您将需要首先为这些用户对任何默认值为组织显式设置的共存模式

此外，您会发现它更轻松地为用户同时使用 PowerShell 组启用通知。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>步骤 3： 为用户仅团队的共存模式

当您准备升级中的用户当前波形团队用作其唯一的应用程序时，为用户仅团队的共存模式。

如果使用的 Microsoft 团队管理中心，您可以同时为最多 20 个用户配置 TeamsUpgradePolicy:
1. 在 Microsoft 团队管理中心中，选择**用户**，然后选择最多 20 个用户的复选框。
2. 在列表视图的左上角中，选择**编辑设置**。
3. 在右侧，**团队升级**部分下的**编辑设置**窗格中将共存模式设置为**仅团队**下拉列表中。

此外，您会发现它易于升级的用户同时使用 PowerShell 组。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>步骤 4： 为用户的连续随后重复步骤 1-3

根据您验证升级到团队仅模式，并且已准备好展开，重复前面的步骤将 TeamsOnly 应用于多个用户。  


## <a name="phone-system-and-teams-upgrade"></a>电话系统和团队升级

如果您的业务 Online 部署的 Skype 包括电话系统与调用计划和 Microsoft 是您公用电话交换网 (pstn) 提供商，将用户升级到团队将自动转换到团队呼叫的入站的 PSTN。

如果您的业务 Online 部署的 Skype 包括与云连接器 Edition 的电话系统，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。
