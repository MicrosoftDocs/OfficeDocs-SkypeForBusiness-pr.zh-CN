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
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 668e44b66b08b16a04e730c43dbbe02a9edea4fe
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754628"
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

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>从联机业务的 Skype 升级到团队

如果具有完全部署 Skype online 业务，并且希望向工作组从 for Business 的 Skype 升级您的用户，请遵循本文中的指南。 您可以有选择地升级用户或一体化、 基于升级历程的已选择您的组织，通过向用户分配适当的共存和升级的模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>分配的共存和升级模式

您可以通过分配 TeamsUpgradePolicy，可以执行的业务远程 Windows Powershell 会话中使用的 Microsoft 团队管理中心或 Skype 的 TeamsOnly 模式升级团队用户。

有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一次升级到团队的所有用户

按照以下步骤一次将所有用户升级到团队。

### <a name="step-1-notify-the-users-of-the-change"></a>步骤 1： 通知用户的更改

1. 在 Microsoft 团队管理中心，选择**组织范围设置** > **团队升级**。
2. **共存模式**下, 到**上**更改的**通知的 Skype 业务用户升级到团队是可用的**开关。

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a>步骤 2： 为用户设置的共存模式

1. 在 Microsoft 团队管理中心中，选择**组织范围的设置**。
2. 从**共存模式**下拉列表中选择**仅团队**模式。

## <a name="upgrade-users-in-stages"></a>分阶段升级用户

如果您想要为团队中逐步升级您的用户，请按照以下步骤。

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a>步骤 1： 创建您升级的用户群体

用户群体是将同时移至仅团队模式的用户的组。

创建您的用户群体 （将链接添加到用户选择页）

### <a name="step-2-set-the-user-mode-to-islands"></a>步骤 2： 将用户模式下设置为群岛

1. 在 Microsoft 团队管理中心中，选择**用户**，然后选择用户群体。
2. **升级团队**、 旁边选择**编辑**。
3. 在**工作组升级**窗格的**共存模式**下，从下拉列表中选择**群岛**。

### <a name="step-3-set-notification-for-the-user-optional"></a>步骤 3： 为用户的通知 （可选）

1. 在 Microsoft 团队管理中心中，选择**用户**，然后选择用户群体。
2. **升级团队**、 旁边选择**编辑**。
3. 在**工作组升级**窗格的**共存模式**下，更改为**上**的**通知业务用户 Skype**开关。

### <a name="step-4-set-the-user-mode-to-teams-only"></a>步骤 4： 将用户模式下设置为仅团队

当您准备升级团队用作其唯一的应用程序的用户时，为团队仅用户的共存模式。

1. 在 Microsoft 团队管理中心中，选择**用户**，然后选择用户群体。
2. **升级团队**、 旁边选择**编辑**。
3. 在**工作组升级**窗格的**共存模式**下，从下拉列表中选择**仅团队**。

## <a name="phone-system-and-teams-upgrade"></a>电话系统和团队升级

如果您的业务 Online 部署的 Skype 包括电话系统与调用计划和 Microsoft 是您公用电话交换网 (pstn) 提供商，将用户升级到团队将自动转换到团队呼叫的入站的 PSTN。

如果您的业务 Online 部署的 Skype 包括与云连接器 Edition 的电话系统，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。