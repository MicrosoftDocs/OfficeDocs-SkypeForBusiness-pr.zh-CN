---
title: 为直接路由计划基于位置的路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: 了解如何为直接路由规划基于位置的路由。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c3d5f4eb0cd63dd252d5fcc01bff21f8643a788
ms.sourcegitcommit: ebdad71a8d393466e33a2fdc8606d882a6007588
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280271"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>为直接路由计划基于位置的路由

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>基于位置的路由概述

在某些国家和地区，绕过公共交换电话网络（PSTN）提供商以减少长途通话成本是非法的。 本文介绍了如何使用基于位置的路由，根据其地理位置限制 Microsoft 团队用户进行收费跳过。 本文仅适用于 "电话系统直接路由"。

在这里，你将大致了解基于位置的路由和指南，以帮助你进行规划。 准备好应用和启用基于位置的路由时，请参阅：
- [部署基于位置的路由的网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)

基于位置的路由功能允许您在入站或出站 PSTN 呼叫时限制基于策略和用户地理位置的收费跳过。 

当团队用户启用基于位置的路由时，以下内容适用：
- 要发出出站 PSTN 呼叫，必须满足以下条件之一：
    - 用户终结点位于启用了基于位置的路由的网络网站中，并通过针对基于位置的路由启用的相应网关呼叫传出。 
    - 用户终结点位于未启用基于位置的路由的网络网站中，并且通过未启用基于位置的路由的网关呼叫传出。

    任何其他方案中都不允许出站呼叫。

- 若要接收入站 PSTN 呼叫，用户的应答终结点必须位于呼叫 ingresses 通过启用了基于位置的路由的网关的同一网络站点中。 在任何其他方案（如用户是漫游的情况）中，不允许呼叫，并将路由到用户的呼叫转接设置（通常为语音邮件）。
- 若要将 PSTN 呼叫转移到另一个团队用户，目标用户的终结点必须与发起传输的用户位于同一网络站点。 任何其他方案中都不允许传输。 
- 若要将其他团队用户转移到 PSTN，必须通过与初始呼叫者位于同一网络站点的基于位置的支持路由的网关转移呼叫。 任何其他方案中都不允许传输。

基于位置的路由使用 Skype for Business 服务器使用的相同网络区域、站点和子网定义。 如果限制了某个位置的收费旁路，管理员会将该位置的每个 IP 子网和每个 PSTN 网关关联到一个网络站点。 用户的位置由用户的团队终结点在 PSTN 呼叫时连接到的 IP 子网确定。 用户可能有多个团队客户端位于不同的网站，在这种情况下，基于位置的路由会根据其终结点的位置单独强制执行每个客户端的路由。 

若要熟悉本文中使用的一些网络术语，请参阅[团队中的云语音功能的网络设置](cloud-voice-network-settings.md)。

## <a name="apply-location-based-routing"></a>应用基于位置的路由

您必须将基于位置的路由应用到用户、网络站点和 PSTN 网关。  

### <a name="apply-location-based-routing-at-the-user-location"></a>在用户位置应用基于位置的路由

正如前面所述，基于位置的路由仅适用于设置直接路由的用户。 基于位置的路由不适用于为通话计划设置的用户。 如果用户位于 "收费旁路限制" 下，则必须为其启用基于位置的路由，这样就可以控制他们可以拨打和接收 PSTN 呼叫的条件以及可以使用的 PSTN 网关。 如果启用了基于位置的路由的用户位于为基于位置的路由启用的网站上，则用户必须通过连接到该网站的基于位置的路由网关进行呼叫。 

基于位置的路由通过基于用户的团队终结点的 IP 地址确定用户的当前位置，并相应地应用规则来进行工作。 可通过以下方式对启用了基于位置的路由的用户的位置进行分类： 
- **用户位于与分配了其所在的 PSTN 网关相同的基于位置的启用路由的网站上。**<br>在此方案中，用户位于为基于位置的路由启用的已知网络站点中，用户的直接向内拨号（已有）号码将在同一网络站点中的 PSTN 网关处终止。 例如，用户位于其办公室。 
- **用户位于其他基于位置的启用路由的站点，该站点未关联到 PSTN 网关（已分配它们的位置）。**<br>在此方案中，用户位于为基于位置的路由启用的已知网络站点中，并且该站点未与用户的已分配的 PSTN 网关相关联。 例如，用户将传播到另一个 office。  
- **用户位于不支持基于位置的路由的内部站点。** <br>在此方案中，用户位于不支持基于位置的路由的已知内部网络站点。 
- **用户位于未知网站。** 
    - 用户位于未定义为网络站点的内部网络中。 
    - 用户位于内部网络外部。 例如，用户在家中或在咖啡店中使用 Internet。 

### <a name="apply-location-based-routing-at-the-network-site"></a>在网络站点应用基于位置的路由 
必须为基于位置的路由启用网络站点，以帮助确定在漫游时为基于位置的路由启用用户路由的网关。 如果启用了基于位置的路由的用户漫游到为基于位置的路由启用的网站，则仅在该网站上启用基于位置的路由的 PSTN 网关才可用于出站呼叫。 如果启用了基于位置的路由的用户漫游到未启用基于位置的路由的网站，则没有为基于位置的路由启用的任何网关均可用于出站呼叫。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>在 PSTN 网关上应用基于位置的路由 

网关与网站相关联，以确定在其进行或接收 PSTN 呼叫时，可以使用基于位置的路由的用户所在的位置。 必须为基于位置的路由启用网关，以确保其位于 "收费回避" 限制下，并且不能由没有启用基于位置的路由的用户使用。 同一个网关可能与多个网站相关联，并且可以配置为启用基于位置的路由或不启用基于位置的路由，具体取决于网站。

## <a name="scenarios-for-location-based-routing"></a>基于位置的路由的方案

本部分介绍了通过基于位置的路由来限制免收长途电话的不同方案，以及如何为没有启用基于位置路由的用户的基于位置的路由的用户路由呼叫。

- [团队用户将出站呼叫置于 PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [团队用户从 PSTN 接收入站呼叫](#teams-user-receives-an-inbound-call-from-the-pstn)
- [团队用户将呼叫转移或转发给另一个团队用户](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [团队用户将呼叫转移或转发到 PSTN 终结点](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同时响铃](#simultaneous-ringing)
- [委派](#delegation)

下图显示了每个方案中基于位置的路由启用的限制。 为基于位置的路由启用的用户、网络站点和网关在其周围有边框。 将图表用作指南，帮助你了解基于位置的路由在每个方案中的工作方式。  

![显示基于位置的路由的方案的图表](media/lbr-direct-routing.png "显示基于位置的路由的方案的图表")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>团队用户将出站呼叫置于 PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用基于位置的路由

未启用基于位置的路由的用户可以使用任何网站上的任何网关进行出站呼叫，而不是通过其分配的语音路由策略启用基于位置的路由。 但是，如果为基于位置的路由启用了网关，则用户不能通过网关发出出站呼叫，即使已将其分配给其语音路由策略也是如此。 如果用户漫游到启用了基于位置的路由的网站，则他们只能通过其不支持基于位置的路由的常规路由网关进行呼叫。
 
#### <a name="user-enabled-for-location-based-routing"></a>用户启用了基于位置的路由
比较而言，对启用了基于位置的路由的用户的出站呼叫的路由受用户终结点的网络位置的影响。 下表显示了基于位置的路由如何影响对 User1 的出站调用的路由，具体取决于 User1 的位置。 

|User1 终结点位置  |对 User1 的出站呼叫进行路由  |
|---------|---------|
|分配了用户的同一网站，为基于位置的路由启用了网站（Site1）      |通过基于用户的语音路由策略在 Site1 上启用的基于位置的路由（GW1）的呼叫通过网关进行路由         |
|与用户所分配的位置不同的网站，为基于位置的路由启用网站（Site2）    |根据用户的语音路由策略，呼叫通过网关在漫游 Site2 上启用的基于位置的路由（GW2）进行路由        |
|与用户所分配的位置不同的网站，不为基于位置的路由启用网站（Site3）  |在未启用基于位置的路由（GW3）的站点上通过未启用基于位置的路由（基于用户的语音路由策略）而未启用的呼叫路由网关       |
|未知内部网络（Location4）    |  不允许 PSTN 呼叫       |
|未知外部网络（Location5）    | 不允许 PSTN 呼叫        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>团队用户从 PSTN 接收入站呼叫

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用基于位置的路由

未启用基于位置的路由的用户可以接收来自未启用其分配的基于位置的路由的网关的入站呼叫。 ingresses。 如果用户漫游到未启用基于位置的路由的网站，他们仍然可以通过其正常的 PSTN 网关接收呼叫。
  
#### <a name="user-enabled-for-location-based-routing"></a>用户启用了基于位置的路由

相比之下，为基于位置的路由启用的用户只能从 PSTN 网关接收来自 PSTN 网关的入站呼叫，这些呼叫是在位于同一站点时分配的。 下表显示了当 User1 移动到不同网络位置时，User1 如何接收入站呼叫。 如果呼叫未路由到用户的终结点，则它将转到用户的呼叫转接设置（如果设置已配置）。 通常，这是语音邮件。  

|User1 终结点位置  |将入站呼叫路由到 User1  |
|---------|---------|
|与用户所分配的位置相同的网站，为基于位置的路由启用网站（Site1）   | 在 Site1 中路由到 User1's 终结点的通话        |
|与用户所分配的位置不同的网站，为基于位置的路由启用网站（Site2）    | 在 Site2 中未路由到终结点的调用        |
|与用户所分配的位置不同的网站，不为基于位置的路由启用网站（Site3）    | 在 Site3 中未路由到终结点的调用        |
|未知内部网络（Location4）   | 在 Location4 中未路由到终结点的调用        |
|未知外部网络（Location5）     | 在 Location5 中未路由到终结点的调用        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>团队用户将呼叫转移或转发给另一个团队用户

当涉及 PSTN 终结点时，基于位置的路由会分析是否为基于位置的路由启用一个或两个用户，并确定是否应转移或转发呼叫，具体取决于两个终结点的位置。 
 
呼叫转接要求启动用户接听呼叫时，呼叫转移不需要应答初始呼叫。 这意味着即使 User1 不在某个位置即可接收入站呼叫（请参阅[团队用户从 PSTN 部分接收入站调用](#teams-user-receives-an-inbound-call-from-the-pstn)的位置），也可以转移呼叫，并且如果 user1 无法接收入站呼叫，则无法转移呼叫。 

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用基于位置的路由

未启用基于位置的路由的用户可以将 PSTN 呼叫转移或转发到未启用基于位置的路由的其他用户。 用户通常不允许用户将 PSTN 呼叫转移或转发到启用了基于位置的路由的用户，因为基于位置的路由用户通常仅在基于位置的支持路由的连接网关（适用于 PSTN 呼叫）之间共存。 例外情况是，启用基于位置的路由用户漫游到未启用基于位置的路由的网站。 在此方案中，允许转移的通话。  

同样，没有为基于位置的路由启用的用户只能接收来自另一个未启用位置路由的用户的转移或转发 PSTN 呼叫。 

#### <a name="user-enabled-for-location-based-routing"></a>用户启用了基于位置的路由

通常，仅当目标用户已启用基于位置的路由并位于同一网站时，才允许从启用基于位置的路由的网关转移和转发入站 PSTN 呼叫。 否则，不允许转移和转发呼叫。 

下表显示了是否允许呼叫转接和呼叫转移，具体取决于目标用户的位置。 在此表中，位于 Site1 中的 User1 启动传输或转发给其他团队用户，这些用户也启用了基于位置的路由和位于不同位置的人员。  

|目标用户终结点位置|User1 启动呼叫转移 |User1 发起呼叫转发|
|---------|---------|---------|
|与发起方（网络2）相同的网络站点|有|有|
|不同的网络站点，为基于位置的路由启用了站点（User3）|不允许|不允许|
|不同的网络站点，没有为基于位置的路由启用网站（User4）|不允许|不允许|
|未知内部网络（User5）| 不允许|不允许|
|未知外部网络（User6）| 不允许|不允许|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>团队用户将呼叫转移或转发到 PSTN 终结点

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用基于位置的路由

- 允许将 PSTN 呼叫转移和转发到另一个 PSTN 号码。 
- 将入站 VOIP 呼叫转移和转发到 PSTN 必须遵守呼叫者的收费绕过限制。 
    - 如果呼叫者未启用基于位置的路由，则可以将其转移到未启用基于位置的路由的任何 PSTN 网关。
    - 如果呼叫者启用了基于位置的路由，则只能将其转移到位于同一网络站点的基于位置的路由启用的网关。 

#### <a name="user-enabled-for-location-based-routing"></a>用户启用了基于位置的路由

- 将 PSTN 呼叫转移和转发到另一个 PSTN 号码的情况必须路由到已启用入站呼叫的基于位置的基于路由的网关。 
- 转移和转发到 PSTN 的入站 VOIP 呼叫必须同时接受呼叫方和呼叫用户的收费绕过限制。 
    - 如果呼叫者未启用基于位置的路由，则可以将其转移到未启用基于位置的路由的任何 PSTN 网关。
    - 如果呼叫者启用了基于位置的路由，则只能将其转移到位于同一网络站点的基于位置的路由启用的网关。
 
下表显示了基于位置的路由如何影响来自 User1 的从 Site1 到不同位置的 VOIP 呼叫的路由，这些用户将呼叫转移或转发到 PSTN 终结点。  

|用户启动呼叫转移或转发  |转接至 PSTN  |转发到 PSTN  |
|---------|---------|---------|
|同一网络站点，为基于位置的路由启用站点（服务2）   |呼叫转移只能通过基于位置的 Gateway1 在 Site1 上启用基于位置的路由，并基于 User2's 的语音路由策略来进行路由         |根据 User2's 语音路由策略，呼叫转接只能通过基于位置启用的 Gateway1 在 Site1 上路由         |
|不同的网络站点，为基于位置的路由启用了站点（User3）    |呼叫转移只能通过基于位置的 Gateway1 在 Site1 上启用基于位置的路由，并基于 User3's 的语音路由策略来进行路由         |呼叫转接只能通过基于位置的 Gateway1 在 Site1 上启用基于位置的路由，并基于 User3's 的语音路由策略来进行路由         |
|不同的网络站点，没有为基于位置的路由启用网站（User4）    |呼叫转移只能通过基于位置的 Gateway1 在 Site1 上启用基于位置的路由，并基于 User4's 的语音路由策略来进行路由         |呼叫转接只能通过基于位置的 Gateway1 在 Site1 上启用基于位置的路由，并基于 User4's 的语音路由策略来进行路由         |
|未知内部网络（User5）     |呼叫转移只能通过基于位置的 Gateway1 在 Site1 上启用基于位置的路由，并基于 User5's 的语音路由策略来进行路由         |呼叫转接只能通过基于位置的 Gateway1 在 Site1 上启用基于位置的路由，并基于 User5's 的语音路由策略来进行路由         |
|未知外部网络（User6）   |呼叫转移只能通过基于位置的 Gateway1 在 Site1 上启用基于位置的路由，并基于 User6's 的语音路由策略来进行路由        |呼叫转接只能通过基于位置的 Gateway1 在 Site1 上启用基于位置的路由，并基于 User6's 的语音路由策略来进行路由         |

### <a name="simultaneous-ringing"></a>同时响铃

如果启用了基于位置的路由的用户收到呼叫且同时启用了同时拨打，则基于位置的路由会分析呼叫方的位置和被呼叫方的终结点，以确定是否应路由呼叫。 同时拨打的规则与呼叫转移和转发的基于位置的规则相同。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>同时拨打另一个团队用户

下表显示了对于 User1 的入站 PSTN 呼叫，基于位置的路由是否允许不同用户同时拨打到不同用户。

|目标用户终结点位置|同时拨打  |
|---------|---------|
|与发起方（网络2）相同的网络站点   |有         |
|为基于位置的路由启用了不同的漫游网络网站（User3）   |不允许         |
|没有为基于位置的路由（User4）启用漫游网络网站   |不允许        |
|未知内部网络（User5）    | 不允许        |
|未知外部网络（User6）    |不允许        |
|目标用户是 PSTN 号码    |呼叫只能通过基于位置的路由启用 Gateway1 at Site1，基于 User1's 的语音路由策略进行路由      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>同时拨打 PSTN 终结点

下表显示了从 Site1 到不同位置的入站 VOIP 呼叫的入站 VOIP 呼叫的基于位置的路由行为，同时拨打设置为 PSTN 号码的不同位置的用户。 

|名为用户终结点位置  |同时拨打的目标为 PSTN 终结点 |
|---------|---------|
|同一网络站点，为基于位置的路由启用站点（服务2）    |呼叫只能通过基于位置的路由 Gateway1 在 Site1 上进行路由，基于 User2's 的语音路由策略       |
|为基于位置的路由启用了不同的网络站点（User3）    |呼叫只能通过基于位置的路由 Gateway1 在 Site1 上进行路由，基于 User3's 的语音路由策略        |
|没有为基于位置的路由（User4）启用不同的网络站点    |呼叫只能通过基于位置的路由 Gateway1 在 Site1 上进行路由，基于 User4's 的语音路由策略         |
|未知内部网络（User5）    |呼叫只能通过基于位置的路由 Gateway1 在 Site1 上进行路由，基于 User5's 的语音路由策略         |
|未知外部网络（User6）   |呼叫只能通过基于位置的路由 Gateway1 在 Site1 上进行路由，基于 User6's 的语音路由策略         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>通过语音应用进行入站呼叫（自动助理或呼叫队列）

允许来自基于位置的启用路由的网关的入站 PSTN 呼叫连接到自动助理或呼叫队列。 如果用户位于与入站 PSTN 呼叫来自同一站点的同一站点，则启用基于位置的路由的用户只能接收来自这些应用程序的入站呼叫转移。 
 
语音应用传输允许呼叫转接和同时拨打用户和 PSTN。 完成对目标的调用取决于前面列出的基于位置的路由规则。  
 
还允许转发到语音邮件。  

### <a name="delegation"></a>委派

团队用户可以选择代表自己进行呼叫和接听呼叫的代理人。 团队中的委派功能受基于位置的路由影响，如下所示： 
- 对于代表委托人进行通话的基于位置的路由启用委派的出站呼叫，应用相同的规则。 呼叫路由基于代理人的呼叫授权策略、语音路由策略和位置。 有关详细信息，请参阅[团队用户将出站呼叫放置到 PSTN](#teams-user-places-an-outbound-call-to-the-pstn)。 
- 对于入站 PSTN 呼叫委托人进行通话，用于呼叫转接或同时拨打给其他用户的基于位置的路由规则也适用于代理人。 有关详细信息，请参阅[团队用户将呼叫转移或转发给另一个团队用户](#teams-user-transfers-or-forwards-call-to-another-teams-user)，[团队用户将呼叫转移或转移到 PSTN 终结点](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)，[同时拨打](#simultaneous-ringing)。 当代理人将 PSTN 终结点设置为同时拨打的目标时，将使用该代理的语音路由策略将呼叫路由到 PSTN。 
- 对于委派，建议委托人进行通话和关联的委派位于同一网络站点。 

## <a name="other-planning-considerations"></a>其他规划考虑事项

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>基于本地位置的路由部署的更改

不再使用网络站点语音路由策略。 而是使用用户的语音路由策略。 这意味着，若要允许用户漫游到其他网站，语音路由策略必须包含漫游网站的网关。 

### <a name="technical-considerations-for-location-based-routing"></a>基于位置的路由的技术注意事项

支持 IPv4 和 IPv6 子网，但是在检查匹配项时，IPv6 优先。

### <a name="client-support-for-location-based-routing"></a>基于位置的路由的客户端支持

支持以下团队客户端：
- 团队桌面客户端（Windows 和 Mac）
- 团队移动客户端（iOS 和 Android）
- 团队 IP 电话

不支持团队 web 客户端和 Skype for Business 客户端。

### <a name="capabilities-not-supported-by-location-based-routing"></a>基于位置的路由不支持的功能

基于位置的路由不适用于以下类型的交互。 当团队终结点在以下情况下与 PSTN 终结点交互时，不会强制执行基于位置的路由： 
- 通过呼叫寄存对 PSTN 呼叫进行呼叫寄存或检索 
- 本地 Skype for Business 用户或 Skype for business Online 用户呼叫团队用户  

### <a name="location-based-routing-for-conferencing"></a>会议的基于位置的路由

不允许在 PSTN 呼叫上启用基于位置的路由用户与其他用户或 PSTN 号码开始会议。 允许连接到自动助理或呼叫队列。 如果用户拥有会议许可证，则用户必须启动与相关用户的会议并通过会议桥呼叫 PSTN 才能开始电话会议。  

### <a name="media-bypass-requirement-for-location-based-routing"></a>基于位置的路由的媒体绕过要求

如果要在印度中部署基于位置的路由，则还需要配置 "绕过媒体"。 若要了解详细信息，请参阅[使用直接路由规划媒体旁路](direct-routing-plan-media-bypass.md)。

## <a name="next-steps"></a>后续步骤

转到为[基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)。

## <a name="related-topics"></a>相关主题

- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [团队中云语音功能的网络设置](cloud-voice-network-settings.md)
