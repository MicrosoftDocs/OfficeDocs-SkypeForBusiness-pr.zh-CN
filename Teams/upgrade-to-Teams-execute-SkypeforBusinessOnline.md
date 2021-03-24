---
title: 从 Skype for Business Online 升级到 Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从 Skype for Business Online 部署将组织升级到 Microsoft Teams。
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
ms.openlocfilehash: 65b00f8e56792164ed2aa0b8240d0d131a7bdbcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104008"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>从 Skype for Business Online 升级到 Teams

![升级过程图，强调部署和实施](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")

本文是升级旅程的部署和实施阶段的一部分。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解 Skype for Business 和 Teams 的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备环境](./upgrade-prepare-environment.md)
- [准备组织](./upgrade-prepare-organization.md)
- [开展试点](./pilot-essentials.md)

如果你已完全部署了 Skype for Business Online 并且想要将用户从 Skype for Business 升级到 Teams，请按照本文中的指导操作。 可以通过向用户分配适当的共存和升级模式，根据组织选择的升级过程，有选择地或全面升级用户。

> [!IMPORTANT]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大程度地实现权益并确保组织有适当的时间来实施升级，我们鼓励你立即开始 Microsoft Teams 之旅。 请记住，成功的升级符合技术和用户准备情况，因此，在导航到 Microsoft Teams 旅程时，请务必参考此处的指南。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>分配共存和升级模式

可以通过分配 TeamsUpgradePolicy 的 UpgradeToTeams 实例（可以使用 Microsoft Teams 管理中心或 Skype for Business 远程 Windows PowerShell 会话执行）将用户升级到 TeamsOnly 模式。 若要一步升级整个租户，可以按用户或租户范围执行此操作。 

有关详细信息，请参阅 [设置共存和升级设置和](./setting-your-coexistence-and-upgrade-settings.md) [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一次将所有用户升级到 Teams

按照以下步骤一次将所有用户升级到 Teams。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>步骤 1：将更改通知用户 (可选) 

1. 在 Microsoft Teams 管理中心中，选择 **"组织范围的设置**  >  **""Teams 升级"。**
2. 在 **"共存模式"** 下，将"通知 Skype for Business 用户，可升级到 **Teams"切换** 为"**开"。**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>步骤 2：为组织将共存模式设置为 TeamsOnly

1. 在 Microsoft Teams 管理中心中，选择 **"组织范围的设置"。**
2. 从 **"共存模式** " **下拉列表中选择"仅** Teams 模式"。

## <a name="upgrade-users-in-stages"></a>分步升级用户

如果要将用户逐渐升级到 TeamsOnly，请按照以下步骤操作。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>步骤 1：确定要升级的用户组

通常，组织可能会选择在用户的成功波次中升级其组织。  首先需要识别这些用户，以便可以轻松在 Microsoft Teams 管理中心中搜索他们。 或者，可能需要使用 PowerShell 更有效地执行此操作。 确定给定升级波次的用户集后，继续执行剩余的步骤。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>步骤 2：在当前升级波次中为用户设置通知 (可选) 

如果使用 Microsoft Teams 管理中心，可以一次为最多 20 个用户配置 TeamsUpgradePolicy：
1. 在 Microsoft Teams 管理中心中，选择"用户"，然后查找并多选最多 20 个应升级的用户的复选框。 
2. 选择 **列表** 视图左上角的"编辑设置"。 
3. 在右侧 **"编辑设置"** 窗格中的 **"Teams 升级"** 下，将"通知 **Skype for Business** 用户"切换到"**开"。** 注意：如果共存模式的值是"使用组织范围的设置"，则看不到此开关，因此需要首先将这些用户的共存模式显式设置为组织的任何默认值。

或者，你可能会发现使用 PowerShell 一次为用户组启用通知会更容易。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>步骤 3：将用户的共存模式设置为"仅 Teams"

如果已准备好升级当前波形中的用户以将 Teams 用作其唯一应用程序，请为用户设置"仅 Teams"共存模式。

如果使用 Microsoft Teams 管理中心，可以一次为最多 20 个用户配置 TeamsUpgradePolicy：
1. 在 Microsoft Teams 管理中心中，选择" **用户"，** 然后选中最多 20 个用户复选框。
2. 选择 **列表** 视图左上角的"编辑设置"。
3. 在 **右侧"** 编辑设置"窗格中的 **"Teams** 升级"部分下，在下拉列表中将共存模式设置为" **仅** Teams"。

或者，你可能会发现使用 PowerShell 一次升级用户组更容易。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>步骤 4：为连续的用户波形重复步骤 1-3

验证升级到"仅 Teams"模式并准备好进行扩展时，请重复上述步骤，将 TeamsOnly 应用到更多用户。  


## <a name="phone-system-and-pstn-connectivity-options"></a>电话系统和 PSTN 连接选项

在用户进入 TeamsOnly 模式后，支持 Teams 手机系统。  (如果用户在群岛模式下，则电话系统仅支持 Skype for Business.)   

### <a name="pstn-connectivity-options"></a>PSTN 连接选项

在考虑使用 PSTN (公用电话) 时，从 Skype for Business Online 切换到 TeamsOnly 模式时，有两种可能的情况：

- Skype for Business Online 中的用户，具有 Microsoft 呼叫计划。 升级后，此用户将继续拥有 Microsoft 呼叫计划。 这是最简单的方案，只需几个步骤。 有关详细信息，请参阅通过[Microsoft 呼叫计划从 Skype for Business Online。](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- Skype for Business Online 中的用户，通过本地 Skype for Business 或 Cloud Connector Edition 提供本地语音功能。 用户升级到 Teams 需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。  有关详细信息，请参阅使用本地语音[从 Skype for Business Online。](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)