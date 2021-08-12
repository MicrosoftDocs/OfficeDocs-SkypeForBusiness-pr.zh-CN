---
title: 电话中建立系统直接Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 了解直接路由配置、必要的核心部署决策和语音路由注意事项。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55676d855d3e15c3f767203da981a4fae241f3128a270f5656d770a229f00059
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848067"
---
# <a name="phone-system-direct-routing"></a>电话系统直接路由

你已完成了[入门](get-started-with-teams-quick-start.md)。 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 也许你已部署会议[&会议。](deploy-meetings-microsoft-teams-landing-page.md) 现在，你已准备好添加云语音工作负荷，并且你已决定使用自己的电话运营商进行公共电话交换网 (PSTN) 连接，电话系统直接路由。 使用直接路由，可以结合使用电话系统与几乎任何电话运营商。

本文介绍直接路由的核心部署决策，以及可能需要根据组织需求考虑的其他注意事项。 还应阅读[云语音Microsoft Teams](cloud-voice-landing-page.md)了解有关 Microsoft 云语音产品/服务的信息。

## <a name="learn-more-about-direct-routing"></a>详细了解直接路由

以下文章提供有关配置和使用直接路由电话系统详细信息。 配置直接路由需要了解 PSTN 路由设计。 应阅读以下所有文章，了解如何计划和配置直接路由：

- [规划直接路由](direct-routing-plan.md) 
- [配置直接路由](direct-routing-configure.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)
- [对直接路由进行监视和故障排除](direct-routing-monitor-and-troubleshoot.md)

此外，可能需要阅读以下文章，具体取决于要求：

-  [为多个租户配置会话边界控制器](direct-routing-sbc-multiple-tenants.md)
-  [迁移到直接路由](direct-routing-migrating.md)
-  [采用 PSTN 连接的混合环境中的用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 观看以下会话，详细了解直接路由：直接[路由Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>核心部署决策

这些是直接路由要考虑的核心决策。 

|询问你自己|操作 |
| :------------|:-------|
|我将为哪些用户启用直接路由？ | 有关详细信息，请参阅 [为直接路由服务启用用户](direct-routing-configure.md)。 |
我是否拥有直接路由所需的许可证？ | 有关详细信息，请参阅 [许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>会话边界控制器 (SBC) 注意事项

使用直接路由，可将自己的会话边界控制器 (SBC) 直接连接到电话系统。  有关经过认证的 SDC 的列表，请参阅 [支持的会话边界控制器](direct-routing-border-controllers.md)。

|询问你自己|操作 |
|:------------|:-------|
| 在何处以及如何部署 SDC？ | 有关详细信息，请参阅 [配置直接路由](direct-routing-configure.md) | 
是否有多个租户？ | 有关详细信息，请参阅 [为多个租户配置会话边界控制器](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>语音路由注意事项

需要配置一个电话系统将调用路由到特定的 SDC。

|询问你自己|操作 |
|:------------|:-------|
| 需要创建哪些语音路由策略、PSTN 使用情况和语音路由？ | 有关语音路由信息，请参阅 [配置语音路由](direct-routing-configure.md)。
| 将哪些用户分配到我定义的语音路由策略？ | 请参阅配置语音 [路由中的示例](direct-routing-configure.md)。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>确保传入呼叫使用 TeamsUpgradePolicy Teams客户端

直接路由仅支持Microsoft Teams。 若要通过直接路由接收 PSTN 呼叫，需要配置 TeamsUpgradePolicy 以确保在 Teams。 用户必须进入Teams模式，为此，可以通过为用户分配 TeamsUpgradePolicy 的"UpgradeToTeams"实例。 

|询问你自己|操作 |
|:------------|:-------|
|"仅Teams模式"意味着什么？ | 有关详细信息，请参阅[迁移和互操作性指南，](./migration-interop-guidance-for-teams-with-skype.md)了解将 Teams 与 Skype for Business 一Skype for Business。|
|||

## <a name="additional-deployment-considerations"></a>其他部署注意事项

根据组织的需求和配置，可以考虑以下事项：

| 询问你自己| 操作 |
| :------------|:-------|
| 是否具有已配置Skype for Business Server连接的现有部署？ |  若要了解如何预配和管理混合环境中用户帐户，请参阅具有 [PSTN 连接的混合环境中用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)。| 
| 你是从调用计划还是从本地环境Skype for Business直接路由？ | 若要详细了解如何从现有环境迁移到直接路由，请参阅 [迁移到直接路由](direct-routing-migrating.md)。 |
|||
