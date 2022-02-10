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
- m365initiative-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 了解如何Teams 电话系统直接路由。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fe723ee8347ea96c87cb0a9e85f7794c5e50e01
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518704"
---
# <a name="direct-routing"></a>直接路由

你已完成了[入门](get-started-with-teams-quick-start.md)。 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 也许你已部署 [会议&会议](deploy-meetings-microsoft-teams-landing-page.md)。 现在，你已准备好添加语音工作负荷，并且你已决定使用自己的电话运营商进行公用电话交换电话网络 (PSTN) 连接，将 电话系统 与直接路由一起使用。 使用直接路由，可以结合使用电话系统与几乎任何电话运营商。

本文介绍直接路由的核心部署决策，以及可能需要根据组织需求考虑的其他注意事项。 还应阅读 [规划语音解决方案](cloud-voice-landing-page.md) ，了解有关 Microsoft 语音产品/服务详细信息。

## <a name="learn-more-about-direct-routing"></a>详细了解直接路由

以下文章提供有关配置和使用直接路由的信息。 配置直接路由需要了解 PSTN 路由设计。 应阅读以下所有文章，了解如何计划和配置直接路由：

- [规划直接路由](direct-routing-plan.md) 
- [配置直接路由](direct-routing-configure.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)
- [对直接路由进行监视和故障排除](direct-routing-monitor-and-troubleshoot.md)

此外，可能需要阅读以下文章，具体取决于要求：

-  [为多个租户配置会话边界控制器](direct-routing-sbc-multiple-tenants.md)
-  [迁移到直接路由](direct-routing-migrating.md)
-  [采用 PSTN 连接的混合环境中的用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 观看以下会话，详细了解直接路由：[直接路由Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>核心部署决策

这些是直接路由要考虑的核心决策。 

|询问你自己|Action |
| :------------|:-------|
|我将为哪些用户启用直接路由？ | 有关详细信息，请参阅 [为用户启用直接路由服务](direct-routing-configure.md)。 |
我是否拥有直接路由所需的许可证？ | 有关详细信息，请参阅 [许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>会话边界控制器 (SBC) 注意事项

使用直接路由，可将自己的会话边界控制器 (SBC) 直接连接到电话系统。 有关认证 SDC 的列表，请参阅 [支持的会话边界控制器](direct-routing-border-controllers.md)。

|询问你自己|Action |
|:------------|:-------|
| 在何处以及如何部署 SDC？ | 有关详细信息，请参阅 [配置直接路由](direct-routing-configure.md) | 
是否有多个租户？ | 有关详细信息，请参阅 [为多个租户配置会话边界控制器](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>语音路由注意事项

需要配置一个电话系统将调用路由到特定 SDC。

|询问你自己|Action |
|:------------|:-------|
| 需要创建哪些语音路由策略、PSTN 使用情况和语音路由？ | 有关语音路由信息，请参阅 [配置语音路由](direct-routing-configure.md)。
| 将哪些用户分配到我定义的语音路由策略？ | 请参阅配置语音 [路由中的示例](direct-routing-configure.md)。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>确保传入呼叫使用 TeamsUpgradePolicy Teams客户端

直接路由仅支持Microsoft Teams。 若要通过直接路由接收 PSTN 呼叫，需要配置 TeamsUpgradePolicy 以确保在 Teams。 用户必须进入 TeamsOnly 模式，为此，可以通过为用户分配 TeamsUpgradePolicy 的"UpgradeToTeams"实例。 

|询问你自己|Action |
|:------------|:-------|
|TeamsOnly 模式意味着什么？ | 有关详细信息，请参阅将 Teams 与 Skype for Business 一起用于组织的[迁移和互操作性Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)。|
|||


