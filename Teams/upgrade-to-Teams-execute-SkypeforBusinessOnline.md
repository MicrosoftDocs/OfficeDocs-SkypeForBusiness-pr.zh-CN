---
title: 从 Skype for Business Online 升级到 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从 Microsoft Teams Online 部署Skype for Business组织。
localization_priority: Normal
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
ms.openlocfilehash: 0c3494ec304722e43b0cbb39d312a656832f9a7cec30654dac8ebb6fefd3e3dc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328907"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>从 Skype for Business Online 升级到 Teams

![升级过程图，强调部署和实施](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")

本文是升级旅程的部署和实施阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解两者共存Skype for Business互操作性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备环境](./upgrade-prepare-environment.md)
- [准备组织](./upgrade-prepare-organization.md)
- [开展试点](./pilot-essentials.md)

如果已完全部署了 Skype for Business Online，并且想要将用户从 Skype for Business 升级到 Teams，请遵循本文中的指导。 可以通过向用户分配适当的共存和升级模式，根据组织选择的升级过程，有选择地或全面升级用户。

> [!IMPORTANT]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大程度地实现权益并确保组织有适当的时间来实施升级，我们鼓励你立即开始Microsoft Teams之旅。 请记住，成功的升级符合技术和用户准备情况，因此，在导航到 Microsoft Teams。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>分配共存和升级模式

可以通过分配 TeamsUpgradePolicy 的 UpgradeToTeams 实例（可以使用 Microsoft Teams 管理中心或 Skype for Business 远程 Windows PowerShell 会话执行）将用户升级到 TeamsOnly 模式。 若要一步升级整个租户，可以按用户或租户范围执行此操作。 

有关详细信息，请参阅 [设置共存和升级设置和](./setting-your-coexistence-and-upgrade-settings.md) [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>将所有用户Teams一次升级

请按照以下步骤将所有用户升级为Teams升级。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>步骤 1：将更改通知用户 (可选) 

1. 在Microsoft Teams管理中心，选择 **"组织范围的设置**"Teams  >  **升级"。**
2. 在 **"共存模式**"下，将"通知 **Skype for Business"通知用户Teams"切换到**"开 **"。**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>步骤 2：为组织将共存模式设置为 TeamsOnly

1. 在Microsoft Teams管理中心，选择 **"组织范围的设置"。**
2. 从 **Teams模式** 下拉列表中选择"仅 **模式**"。

## <a name="upgrade-users-in-stages"></a>分步升级用户

如果要将用户逐渐升级到 TeamsOnly，请按照以下步骤操作。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>步骤 1：确定要升级的用户组

通常，组织可能会选择在用户的成功波次中升级其组织。  首先需要标识这些用户，以便可以轻松在管理中心Microsoft Teams用户。 或者，可能需要使用 PowerShell 更有效地执行此操作。 确定给定升级波次的用户集后，继续执行剩余的步骤。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>步骤 2：在当前升级波次中为用户设置通知 (可选) 

如果使用 Microsoft Teams管理中心，可以一次为最多 20 个用户配置 TeamsUpgradePolicy：
1. 在Microsoft Teams管理中心，选择"用户"，然后查找并多选最多 20 个应升级的用户的复选框。 
2. 选择 **列表** 视图左上角的"编辑设置"。 
3. 在右侧 **"编辑设置"** 窗格中的 **"Teams"下**，将"通知 **用户Skype for Business切换到**"**开"。** 注意：如果共存模式的值是"使用组织范围的设置"，则看不到此开关，因此需要首先将这些用户的共存模式显式设置为组织的任何默认值。

或者，你可能会发现使用 PowerShell 一次为用户组启用通知会更容易。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>步骤 3：将用户的共存模式设置为"仅Teams模式

如果已准备好升级当前波形中的用户以将 Teams 用作其唯一应用程序，请为用户设置"仅Teams模式。

如果使用 Microsoft Teams管理中心，可以一次为最多 20 个用户配置 TeamsUpgradePolicy：
1. 在Microsoft Teams管理中心，选择"用户 **"，然后** 选中最多 20 个用户复选框。
2. 选择 **列表** 视图左上角的"编辑设置"。
3. 在 **右侧"** 编辑设置"窗格的 **Teams"** 升级"部分下，将共存模式Teams下拉列表中的"仅"。

或者，你可能会发现使用 PowerShell 一次升级用户组更容易。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>步骤 4：为连续的用户波形重复步骤 1-3

验证升级到"仅Teams模式并准备好进行扩展时，请重复上述步骤，将 TeamsOnly 应用到更多用户。  


## <a name="phone-system-and-pstn-connectivity-options"></a>电话系统和 PSTN 连接选项

电话系统 TeamsOnly Teams支持使用 Teams。  (如果用户在群岛模式下，电话系统仅支持 Skype for Business.)   

### <a name="pstn-connectivity-options"></a>PSTN 连接选项

在考虑使用 PSTN (公用电话) 时，从 Skype for Business Online 模式迁移到 TeamsOnly 模式时，有两种可能的情况：

- 具有 Microsoft 呼叫Skype for Business Online 中的用户。 升级后，此用户将继续拥有 Microsoft 呼叫计划。 这是最简单的方案，只需几个步骤。 有关详细信息，请参阅[From Skype for Business Online with Microsoft Calling Plans。](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- 使用 Skype for Business Online 的用户，通过本地或云连接器Skype for Business本地语音功能。 用户升级到 Teams需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。  有关详细信息，请参阅从[Skype for Business Online 与本地语音](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)。