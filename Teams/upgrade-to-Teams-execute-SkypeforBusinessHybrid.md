---
title: 升级到 Microsoft 团队业务混合部署的 Skype |PSTN
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 从业务混合部署的 Skype 升级到团队的注意事项。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e27e36a26115acf23536edb896066d6bc78daa4e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464809"
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

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>从业务混合部署的 Skype 升级到团队

请遵循本文中的指南，如果您已经部署了 for Business 的 Skype 或 Microsoft Lync 的本地和其配置为与 Office 365 租户，混合部署中，您的组织希望在升级到团队也有选择地 — 通过使用多个共存模式 — 或一体化。 对于任一升级旅程，您需要将用户移动到 Skype 业务 online （如果它们不已联机驻留），然后将其分配适当的共存和升级的模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>步骤 1： 将用户移动到业务 online Skype

此步骤应用于当前驻留在内部部署的用户。 有关业务 online 将这些用户移动到 Skype 的详细信息，请参阅[移动用户从本地-到业务 online Skype](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>步骤 2： 分配共存并升级模式

您已为业务 Online 到 Skype 移动用户后，您可以将其分配基于您的组织已选择升级旅程的相应共存模式。 有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

> [!NOTE]
> 与业务服务器 2019年和未来的业务服务器 2015 Skype 的累积更新的 Skype，您将能够单步执行 （将用户移动到 Skype 业务 online） 的步骤 1 和步骤 2 （向工作组的升级用户）。 发布的业务服务器 2019 Skype 之后，将提供详细信息。

## <a name="phone-system-and-teams-upgrade"></a>电话系统和团队升级

如果您正在转换到与调用计划的电话系统的业务混合部署您 Skype 和 Microsoft 将您的公用电话交换网 (pstn) 提供商 — 和假定您已完成电话号码移植 — 升级到您的用户团队，将自动转换为入站的 PSTN 呼叫到团队。

如果调用计划不可用或您打算使用您现有的 PSTN 连接的提供程序，您需要转换企业语音部署，或使用您现有的混合语音部署本地部署或云连接器 Edition — 到Microsoft 电话系统直接路由。 若要向工作组升级您的用户，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。
