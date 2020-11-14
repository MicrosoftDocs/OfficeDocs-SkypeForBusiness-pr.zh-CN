---
title: 电话系统直接路由
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
description: 了解有关直接路由的详细信息，如配置、必要的核心部署决策和语音路由注意事项。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c5120f60778879be0978cb80c56daf99e5b5a38
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031818"
---
# <a name="phone-system-direct-routing"></a>电话系统直接路由

你已完成了[入门](get-started-with-teams-quick-start.md)。 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 也许你已将 [会议部署 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。 现在，你已准备好添加云语音工作负载，并且你已决定通过使用电话系统直接路由，将你自己的电话运营商用于公共交换电话网络 (PSTN) 连接。 使用直接路由，可以结合使用电话系统与几乎任何电话运营商。

本文介绍直接路由的核心部署决策，以及你可能希望考虑的基于组织需求的其他注意事项。 您还应阅读 [Microsoft 团队中的云语音](cloud-voice-landing-page.md) ，了解有关 Microsoft 云语音服务的详细信息。

## <a name="learn-more-about-direct-routing"></a>了解有关直接路由的详细信息

以下文章提供了有关配置和使用 "电话系统直接路由" 的详细信息。 配置直接路由需要了解 PSTN 路由设计。 您应阅读所有这些文章，以了解如何规划和配置直接路由：

- [规划直接路由](direct-routing-plan.md) 
- [配置直接路由](direct-routing-configure.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)
- [对直接路由进行监视和故障排除](direct-routing-monitor-and-troubleshoot.md)

此外，你可能需要根据你的要求阅读以下文章：

-  [为多个租户配置会话边界控制器](direct-routing-sbc-multiple-tenants.md)
-  [迁移到直接路由](direct-routing-migrating.md)
-  [采用 PSTN 连接的混合环境中的用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 观看以下会话以了解有关直接路由的详细信息： [在 Microsoft 团队中直接路由](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>核心部署决策

以下是直接路由的核心决策。 

|询问你自己|Action |
| :------------|:-------|
|哪些用户将启用直接路由？ | 有关详细信息，请参阅 [为直接路由服务启用用户](direct-routing-configure.md)。 |
是否有直接路由所需的许可证？ | 有关详细信息，请参阅 [许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a> (SBC) 注意事项的会话边界控制器

通过直接路由，你可以将自己的会话边界控制器 (SBC) 直接连接到电话系统。  有关已验证的 SBCs 的列表，请参阅 [支持的会话边界控制器](direct-routing-border-controllers.md)。

|询问你自己|Action |
|:------------|:-------|
| 我将在哪里以及如何部署 SBCs？ | 有关详细信息，请参阅 [配置直接路由](direct-routing-configure.md) | 
我有多个租户吗？ | 有关详细信息，请参阅 [为多个租户配置会话边框控制器](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>语音路由注意事项

您需要配置电话系统以将呼叫路由到特定的 SBCs。

|询问你自己|Action |
|:------------|:-------|
| 我需要创建哪些语音路由策略、PSTN 使用和语音路由？ | 有关语音路由信息，请参阅 [配置语音路由](direct-routing-configure.md)。
| 哪些用户将分配给我定义的语音路由策略？ | 请参阅 [配置语音路由](direct-routing-configure.md)中的示例。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy 在团队客户端中确保传入呼叫土地

直接路由仅受 Microsoft 团队支持。 要通过直接路由接收 PSTN 呼叫，您需要配置 TeamsUpgradePolicy 以确保在团队中接收传入呼叫。 用户必须位于 "仅团队" 模式下，你可以通过为其分配 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例来执行此操作。 

|询问你自己|Action |
|:------------|:-------|
|团队的唯一模式意味着什么？ | 有关详细信息，请参阅 [与 Skype For business 一起使用团队的组织的迁移和互操作指南](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)。|
|||

## <a name="additional-deployment-considerations"></a>其他部署注意事项

根据组织的需要和配置，您可能需要考虑以下事项：

| 询问你自己| Action |
| :------------|:-------|
| 是否有配置了混合连接的现有 Skype for Business 服务器部署？ |  若要了解如何设置和管理混合环境中的用户帐户，请参阅 [具有 PSTN 连接的混合环境中的用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)。| 
| 您是否正在迁移以直接从呼叫计划或 Skype for business 内部部署环境中路由？ | 若要了解有关从现有环境迁移到直接路由的详细信息，请参阅 [迁移到直接路由](direct-routing-migrating.md)。 |
|||
