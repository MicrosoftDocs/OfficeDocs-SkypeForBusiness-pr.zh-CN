---
title: 从 Skype for Business Online 升级到Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从Skype for Business联机部署将组织升级为Microsoft Teams。
ms.localizationpriority: medium
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
ms.openlocfilehash: 49376910ce9ca0f777533e950600a19bd440c27f
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2022
ms.locfileid: "64846551"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>从 Skype for Business Online 升级到 Teams

![升级旅程关系图，强调部署和实现。](media/upgrade-banner-deployment.png "升级过程的阶段，重点是部署和实施阶段")

本文是升级过程的部署和实现阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解Skype for Business和Teams的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备好环境](./upgrade-prepare-environment.md)
- [准备组织](./upgrade-prepare-organization.md)
- [进行了试点](./pilot-essentials.md)

如果已完全部署 Skype for Business Online，并且想要将用户从Skype for Business升级到Teams，请按照本文中的指导操作。 可以通过向用户分配适当的共存和升级模式，根据组织选择的升级过程，有选择地或全面升级用户。

> [!IMPORTANT]
> Skype for Business在线于2021年7月31日停用。 为了最大程度地实现利益并确保组织有适当的时间实现升级，我们鼓励你今天开始Microsoft Teams。 请记住，成功升级符合技术和用户准备情况，因此，在导航到Microsoft Teams的旅程时，请务必利用此处的指导。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>分配共存和升级模式

可以通过分配 TeamsUpgradePolicy 的 UpgradeToTeams 实例将用户升级到 TeamsOnly 模式，这可以通过使用Microsoft Teams管理中心或Skype for Business远程Windows PowerShell会话来执行。 如果要在一个步骤中升级整个租户，可以按用户或在租户范围内执行此操作。 

有关详细信息，请参阅 [“设置共存和升级设置](./setting-your-coexistence-and-upgrade-settings.md) ”和 [“TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)”。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一次将所有用户升级到Teams

按照以下步骤将所有用户升级为一次Teams。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>步骤 1：通知用户更改 (可选) 

1. 在Microsoft Teams管理中心，选择 **Teams** >  **Teams升级设置**。
2. 在 **“共存”模式** 下，将通知 **Skype for Business用户升级到Teams可** 切换到 **“打开**”。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>步骤 2：为组织将共存模式设置为 TeamsOnly

1. 在Microsoft Teams管理中心，选择 **Teams** >  **Teams升级设置**。
2. 从 **“共存模式**”下拉列表中选择 **“仅Teams** 模式”。

## <a name="upgrade-users-in-stages"></a>分阶段升级用户

如果要逐步将用户升级到 TeamsOnly，请执行以下步骤。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>步骤 1：确定要升级的用户组

通常，组织可能会选择在用户成功浪潮中升级其组织。  你首先需要识别这些用户，以便可以在Microsoft Teams管理中心轻松搜索这些用户。 或者，你可能希望使用 PowerShell 来更有效地执行此操作。 确定给定升级波的用户集后，请继续执行剩余步骤。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>步骤 2：为当前升级波中用户设置通知 (可选) 

如果使用Microsoft Teams管理中心，则可以一次性为最多 20 个用户配置 TeamsUpgradePolicy：
1. 在Microsoft Teams管理中心中，选择 **“用户**”，然后为应升级的最多 20 名用户查找并多选复选框。 
2. 选择列表视图左上角的“ **编辑设置** ”。 
3. 在右侧 **的“编辑设置”** 窗格中，在 **Teams升级** 下，将 **通知Skype for Business用户** 切换为 **“打开**”。 注意：如果共存模式的值为“使用组织范围的设置”，则不会看到此开关，因此需要先将这些用户的共存模式显式设置为组织的任何默认值。

或者，你可能会发现使用 PowerShell 一次性为用户组启用通知会更容易。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>步骤 3：将用户共存模式设置为仅Teams

准备好将当前波中的用户升级为将Teams用作其唯一的应用程序时，请将“共存”模式设置为“仅Teams”。

如果使用Microsoft Teams管理中心，则可以一次性为最多 20 个用户配置 TeamsUpgradePolicy：
1. 在Microsoft Teams管理中心中，选择 **“用户**”，然后选中最多 20 个用户的复选框。
2. 选择列表视图左上角的“ **编辑设置** ”。
3. 在右侧 **的“编辑设置”** 窗格中，**在Teams升级** 部分下，将共存模式设置为仅在下拉列表中 **Teams**。

或者，你可能会发现使用 PowerShell 一次性升级用户组会更容易。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>步骤 4：针对连续的用户波重复步骤 1-3

在验证升级到“仅Teams模式并准备展开”时，请重复前面的步骤，将 TeamsOnly 应用于更多用户。  


## <a name="phone-system-and-pstn-connectivity-options"></a>电话系统和 PSTN 连接选项

用户处于 TeamsOnly 模式后，支持使用Teams电话系统。  (如果用户处于 Islands 模式，电话系统仅支持 Skype for Business.)   

### <a name="pstn-connectivity-options"></a>PSTN 连接选项

考虑公共交换电话网络 (PSTN) 连接选项时，在从 Skype for Business Online 迁移到 TeamsOnly 模式时，有两种可能的情况：

- Skype for Business Online 中的用户，具有 Microsoft 呼叫计划。 升级后，此用户将继续具有 Microsoft 呼叫计划。 这是最简单的方案，只需几个步骤。 有关详细信息，请参阅 [Microsoft 呼叫套餐的“从Skype for Business联机](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)”。

- Skype for Business Online 中的用户，通过本地或云连接器版本Skype for Business具有本地语音功能。 用户升级到Teams需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。  有关详细信息，请参阅[“使用本地语音从 Skype for Business Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)。
