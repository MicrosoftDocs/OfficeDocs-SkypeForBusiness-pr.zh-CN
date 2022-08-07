---
title: 直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 了解具有直接路由的 Teams 电话系统。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff97fc683acd693f867126661c9bf90550ebbe5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269917"
---
# <a name="direct-routing"></a>直接路由

你已完成了[入门](get-started-with-teams-quick-start.md)。 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 也许你已 [部署会议&会议](deploy-meetings-microsoft-teams-landing-page.md)。 现在，你已准备好添加语音工作负载，并决定使用自己的电话运营商进行公共交换电话网络 (PSTN) 通过直接路由使用电话系统进行连接。 使用直接路由，可以结合使用电话系统与几乎任何电话运营商。

本文介绍直接路由的核心部署决策，以及可能需要根据组织需求考虑的其他注意事项。 还应阅读 [“计划语音解决方案](cloud-voice-landing-page.md) ”，了解有关 Microsoft 语音产品/服务的详细信息。

## <a name="learn-more-about-direct-routing"></a>详细了解直接路由

以下文章提供了有关配置和使用直接路由的详细信息。 配置直接路由需要了解 PSTN 路由设计。 应阅读所有这些文章，了解如何规划和配置直接路由：

- [规划直接路由](direct-routing-plan.md) 
- [配置直接路由](direct-routing-configure.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)
- [对直接路由进行监视和故障排除](direct-routing-monitor-and-troubleshoot.md)

此外，你可能希望阅读以下文章，具体取决于你的要求：

-  [为多个租户配置会话边界控制器](direct-routing-sbc-multiple-tenants.md)
-  [迁移到直接路由](direct-routing-migrating.md)
-  [采用 PSTN 连接的混合环境中的用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 观看以下会话，详细了解直接路由： [Microsoft Teams 中的直接路由](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>核心部署决策

这些是直接路由需要考虑的核心决策。 

|询问你自己|操作 |
| :------------|:-------|
|我将为哪些用户启用直接路由？ | 有关详细信息，请参阅 [为直接路由服务启用用户](direct-routing-configure.md)。 |
我有直接路由所需的许可证吗？ | 有关详细信息，请参阅 [许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>会话边界控制器 (SBC) 注意事项

通过直接路由，可将自己的会话边框控制器 (SBC) 直接连接到电话系统。 有关已认证 SBC 的列表，请参阅 [支持的会话边框控制器](direct-routing-border-controllers.md)。

|询问你自己|操作 |
|:------------|:-------|
| 在何处以及如何部署 SBC？ | 有关详细信息，请参阅 [配置直接路由](direct-routing-configure.md) | 
我有多个租户吗？ | 有关详细信息，请参阅 [为多个租户配置会话边框控制器](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>语音路由注意事项

需要将电话系统配置为将呼叫路由到特定 SBC。

|询问你自己|操作 |
|:------------|:-------|
| 需要创建哪些语音路由策略、PSTN 使用情况和语音路由？ | 有关语音路由信息，请参阅 [配置语音路由](direct-routing-configure.md)。
| 哪些用户将被分配到我定义的语音路由策略？ | 请参阅“ [配置语音路由](direct-routing-configure.md)”中的示例。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy 确保传入呼叫在 Teams 客户端中降落

直接路由仅支持 Microsoft Teams。 若要通过直接路由接收 PSTN 呼叫，需要配置 TeamsUpgradePolicy 以确保在 Teams 中接收传入呼叫。 用户必须处于 TeamsOnly 模式，可以通过向其分配 TeamsUpgradePolicy 的“UpgradeToTeams”实例来完成此操作。 

|询问你自己|操作 |
|:------------|:-------|
|TeamsOnly 模式意味着什么？ | 有关详细信息，请参阅[使用 Teams 和 Skype for Business 的组织迁移和互操作性指南](./migration-interop-guidance-for-teams-with-skype.md)。|
|||


