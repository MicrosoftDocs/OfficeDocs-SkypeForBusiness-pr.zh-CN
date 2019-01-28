---
title: 电话系统直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: 直接路由登陆页面
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c2e225090c6d58db2184113dd43995847f9409
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595364"
---
# <a name="phone-system-direct-routing"></a>电话系统直接路由

您已完成[开始](get-started-with-teams-quick-start.md)。 您已推出团队[聊天、 工作组、 通道和 & 应用程序](deploy-chat-teams-channels-microsoft-teams-landing-page.md)与您的组织内。 也许您已经部署了[会议 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。 现在已准备好添加云语音工作负荷，并已决定要使用电话系统直接路由电话运营商用于公共公用电话交换网 (PSTN) 连接。 直接路由中，您可以使用电话系统与几乎任何电话运营商。

本文介绍数据直接路由以及其他注意事项核心部署决策可能想要配置，根据组织的需要。  有关 Microsoft 云语音产品的详细信息，您还应阅读[Microsoft 团队中的云语音功能](cloud-voice-landing-page.md)。

## <a name="learn-more-about-direct-routing"></a>了解有关直接路由的详细信息


下面的文章提供有关配置和使用电话系统直接路由的详细信息。 配置直接路由需要了解 PSTN 路由设计。 您应阅读这些文章以了解如何规划和配置直接路由中的所有：

- [规划直接路由](direct-routing-plan.md) 
- [配置直接路由](direct-routing-configure.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)
- [监视和故障排除直接路由](direct-routing-monitor-and-troubleshoot.md)

此外，您可能想要阅读以下文章根据您的要求：

-  [为多个租户配置会话边界控制器](direct-routing-sbc-multiple-tenants.md)
-  [迁移到直接路由](direct-routing-migrating.md)
-  [采用 PSTN 连接的混合环境中的用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 观看下面的会话，若要了解有关直接路由的详细信息： [Microsoft 团队中直接路由](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>核心部署决策

这些是要考虑的直接路由中的核心决策。 


|问自己|操作 |
| :------------|:-------|
|哪些用户将启用直接路由？ | 有关详细信息，请参阅[启用直接路由服务的用户](direct-routing-configure.md#enable-users-for-direct-routing-service)。 |
我的直接路由中有所需的许可证？ | 有关详细信息，请参阅[授权和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>会话边界控制器 (SBC) 注意事项

使用直接路由时，您自己的会话边界控制器 (SBC) 直接连接到电话系统。  认证的 Sbc 的列表，请参阅[支持的会话边界控制器](direct-routing-border-controllers.md)。

|问自己|操作 |
|:------------|:-------|
| 在何处以及如何将部署 SBCs？ | 有关详细信息，请参阅[配置直接路由](direct-routing-configure.md) | 
我有多个租户？ | 有关详细信息，请参阅[配置多个租户的会话边界控制器](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>语音路由的注意事项

您需要配置电话系统，以将呼叫路由至特定的 Sbc。

|问自己|操作 |
|:------------|:-------|
| 我需要创建哪些语音路由策略、 PSTN 用法和语音路由？ | 语音路由的信息，请参阅[配置语音路由](direct-routing-configure.md#configure-voice-routing)。
| 将分配给我定义语音路由策略的用户？ | 请参阅[配置语音路由](direct-routing-configure.md#configure-voice-routing)中的示例。 |
|||

### <a name="calling-and-interop-policies"></a>调用和互操作性策略

与 Microsoft 团队才支持直接路由。 若要发起或接收直接路由通过 PSTN 呼叫，您需要配置所需的策略，以确保团队中收到传入呼叫。 您可以配置用户设置为其首选的客户端的呼叫的团队通过配置用户仅团队模式或通过分配 TeamsCallingPolicy 和 TeamsInteropPolicy 配置为首选调用客户端的团队。

|问自己|操作 |
|:------------|:-------|
|如何将设置为首选客户端的呼叫的团队？ | 有关详细信息，请参阅[设置为首选的 Microsoft 团队呼叫的用户的客户端](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)。|
|||

## <a name="additional-deployment-considerations"></a>其他部署注意事项

您可能要考虑以下内容，根据组织的需求和配置：

| 问自己| 操作 |
| :------------|:-------|
| 您必须现有 Skype 业务服务器部署配置的混合连接？ |  了解如何设置混合环境中的用户帐户和管理，请参阅[使用 PSTN 连接的混合环境中的用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)。| 
| 您即将迁移到直接路由从调用规划或从企业内部部署环境 Skype？ | 若要了解有关从现有环境迁移到直接路由的详细信息，请参阅[迁移到直接路由](direct-routing-migrating.md)。 |
|||
