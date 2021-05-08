---
title: 为直接路由计划基于位置的路由
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: 了解如何规划直接Location-Based路由。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: f05049cdc181aef72f9ed018f20cd8d2e3264909
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822922"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>为直接路由计划基于位置的路由

## <a name="overview-of-location-based-routing"></a>路由Location-Based概述

在某些国家和地区，绕过 PSTN 公用电话交换网 (PSTN) 降低远程呼叫成本非法。 本文介绍如何使用"Location-Based路由"根据用户的地理位置Microsoft Teams用户免验证通行费。 本文仅适用于直接电话系统路由。

下面将概述如何Location-Based路由和指南，以帮助你进行规划。 准备好应用和启用路由Location-Based，请参阅：

- [部署网络路由Location-Based设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)

> [!NOTE]
> Location-Based高级或 DoD 部署Microsoft 365 政府社区云 (GCC) 路由不可用。

Location-Based路由是一项功能，可用于在入站或出站 PSTN 呼叫时根据策略和用户的地理位置限制通行费绕过。 Location-Based路由旨在提供一种机制来防止收费绕过。 它不应用作基于用户位置动态路由 PSTN 呼叫的机制，否则可能会导致意外后果。

为Teams用户启用Location-Based时，以下规则适用：

- 若要进行出站 PSTN 呼叫，下列其中一项必须为 true：
    - 用户的终结点位于启用了 Location-Based 路由的网络站点中，并通过为 Location-Based 路由启用的相应网关调用出口。 
    - 用户的终结点位于未启用 Location-Based 路由的网络站点中，并通过未为 Location-Based 路由启用的网关调用出口。

    出站呼叫在任何其他方案中都不允许。

- 要接收入站 PSTN 呼叫，用户的应答终结点必须位于呼叫通过为 Location-Based 路由启用的网关的同一网络站点中。 在任何其他方案中（例如，如果用户正在漫游）中，不允许呼叫，并且被路由到用户的呼叫转发设置 (语音邮件) 。
- 若要将 PSTN 呼叫Teams用户，目标用户的终结点必须与发起传输的用户位于同一网络站点中。 任何其他方案都不允许传输。 
- 若要将Teams转接到 PSTN，呼叫必须通过与初始呼叫方位于同一网络站点的启用了 Location-Based 路由的网关进行转移。 任何其他方案都不允许传输。

Location-Based路由使用的网络区域、站点和子网定义与Skype for Business Server相同。 当针对一个位置限制通行费绕过时，管理员将该位置的每个 IP 子网和每个 PSTN 网关关联到网络站点。 用户的位置由 PSTN 呼叫时用户Teams终结点连接到的 IP 子网确定。 用户可能有多个位于Teams客户端，在这种情况下，Location-Based路由会根据其终结点的位置单独强制实施每个客户端的路由。 

若要熟悉本文中使用的一些网络术语，请参阅中云语音[功能的网络Teams。](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>应用Location-Based路由

必须将路由Location-Based用户、网络站点和 PSTN 网关。  

### <a name="apply-location-based-routing-at-the-user-location"></a>在Location-Based位置应用路由

如前所述，Location-Based路由仅适用于为直接路由设置的用户。 Location-Based路由不适用于为呼叫计划设置的用户。 如果用户受到收费Location-Based，则必须为用户启用"呼叫路由"，该限制控制他们可以拨打和接听 PSTN 呼叫的条件以及可以使用的 PSTN 网关。 当启用了 Location-Based 路由的用户位于启用了 Location-Based 路由的站点时，用户必须通过连接到站点的已启用 Location-Based 路由的网关进行调用。 

Location-Based路由的工作原理是基于用户终结点的 IP 地址确定用户的当前位置Teams并相应地应用规则。 可以按以下方式对启用了 Location-Based 路由的用户的位置进行分类： 
- **用户位于与分配了 DID 的 PSTN Location-Based启用路由的同一站点。**<br>在此方案中，用户位于启用了 Location-Based 路由的已知网络站点中，用户的直接向内拨号 (DID) 号码在同一网络站点的 PSTN 网关上终止。 例如，用户位于其办公室。 
- **用户位于与分配了 DID 的 PSTN Location-Based启用路由的站点不同。**<br>在此方案中，用户位于已启用 Location-Based 路由的已知网络站点中，并且该网站未与分配用户 DID 编号的 PSTN 网关相关联。 例如，用户前往另一个办公室。  
- **用户位于未启用路由路由Location-Based站点。** <br>在此方案中，用户位于未启用路由路由的已知内部Location-Based站点。 
- **用户位于未知站点。** 
    - 用户位于未定义为网络站点的内部网络中。 
    - 用户位于内部网络外部。 例如，用户位于家庭或咖啡店的 Internet 上。 

### <a name="apply-location-based-routing-at-the-network-site"></a>在Location-Based应用路由 
必须启用网络站点Location-Based路由，以帮助确定在漫游时要路由Location-Based路由的用户的网关。 如果启用了 Location-Based 路由的用户漫游到启用了 Location-Based 路由的网站，则只有该网站中启用了 Location-Based 路由的 PSTN 网关才能用于出站呼叫。 如果启用了 Location-Based 路由的用户漫游到未启用 Location-Based 路由的站点，则未为 Location-Based 路由启用的任何网关都可以用于出站呼叫。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>在 PSTN Location-Based应用路由 

网关与网站相关联，以确定启用了路由Location-Based用户在拨打或接收 PSTN 呼叫时可以位于何处。 必须为网关启用Location-Based路由，以确保它受收费绕过限制，并且不能由未启用"Location-Based路由"的用户使用。 同一网关可能关联到多个站点，可以配置为为 Location-Based 路由启用，或者根据站点Location-Based路由启用网关。

## <a name="scenarios-for-location-based-routing"></a>基于位置的路由的方案

本部分介绍使用 Location-Based 路由限制通行费绕过的不同方案，并将未启用 Location-Based 路由的用户的呼叫路由方式与启用了 Location-Based 路由的用户进行比较。

- [Teams向 PSTN 发送出站呼叫](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams PSTN 收到入站呼叫](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams将呼叫转接或转接给另一个Teams用户](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams将呼叫转接到 PSTN 终结点](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同时响铃](#simultaneous-ringing)
- [委派](#delegation)

下图显示了每种方案中Location-Based路由启用的限制。 为路由启用的用户、网络站点和Location-Based周围具有边框。 使用图表作为指南，帮助了解Location-Based路由的工作原理。  

![显示路由方案Location-Based示意图](media/lbr-direct-routing.png "显示路由方案Location-Based示意图")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams向 PSTN 发送出站呼叫

#### <a name="user-not-enabled-for-location-based-routing"></a>未为用户启用Location-Based路由

未启用语音路由Location-Based可以在未通过其分配的语音路由策略启用 Location-Based 路由的任何站点上使用任何网关进行出站呼叫。 但是，如果为网关启用了Location-Based路由，则用户无法通过网关进行出站呼叫，即使该网关已分配给其语音路由策略。 如果用户漫游到启用了 Location-Based 路由的站点，则他们只能通过其未为 Location-Based 路由启用的正常路由网关进行调用。
 
#### <a name="user-enabled-for-location-based-routing"></a>为用户启用Location-Based路由
相比之下，为启用了路由路由Location-Based用户的出站调用路由受用户终结点的网络位置影响。 下表显示了路由Location-Based用户 1 的出站调用路由，具体取决于用户 1 的位置。 

|User1 终结点位置  |User1 的出站调用路由  |
|---------|---------|
|分配了用户的 DID 的同一站点，为 Site1 Location-Based路由 (启用)       |通过基于用户的语音路由策略Location-Based Site1 (GW1) 路由的网关路由的呼叫         |
|与分配用户的 DID 的网站不同，为 Site2 Location-Based路由 (启用)     |基于用户的语音路由策略，通过Location-Based GW2 (GW2) 路由的网关进行路由的呼叫        |
|与分配用户 DID 的站点不同，未为 Site3 Location-Based路由 (启用)   |通过未根据用户的语音路由策略为 Location-Based 路由 (GW3) 启用的站点中未启用 Location-Based 路由的网关进行路由的呼叫       |
|Location4 (未知)     |  不允许 PSTN 呼叫       |
|Location5 (未知)     | 不允许 PSTN 呼叫        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams PSTN 收到入站呼叫

#### <a name="user-not-enabled-for-location-based-routing"></a>未为用户启用Location-Based路由

未启用 Location-Based 路由的用户可以从未为其分配 DID 编号入口的 Location-Based 路由启用的网关接收入站呼叫。 如果用户漫游到未启用路由路由Location-Based，他们仍可通过其普通 PSTN 网关接收呼叫。
  
#### <a name="user-enabled-for-location-based-routing"></a>为用户启用Location-Based路由

相比之下，为路由启用Location-Based只能从 PSTN 网关接收来自 PSTN 网关的入站呼叫，当这些用户位于同一站点时，其 DID 将分配到该网关。 下表显示了 User1 在 User1 移动到不同的网络位置时如何接收入站呼叫。 如果呼叫未路由到用户的终结点，它将转到用户的呼叫转发设置（如果已配置设置）。 通常，这是语音邮件。  

|User1 终结点位置  |将入站调用路由到 User1  |
|---------|---------|
|与分配用户的 DID 的站点相同，为 Site1 Location-Based路由 (启用)    | 路由到 Site1 中 User1 终结点的调用        |
|与分配用户的 DID 的网站不同，为 Site2 Location-Based路由 (启用)     | 未路由到 Site2 中的终结点的调用        |
|与分配用户 DID 的站点不同，未为 Site3 Location-Based路由 (启用)     | 未路由到 Site3 中的终结点的调用        |
|Location4 (未知)    | 未路由到 Location4 中的终结点的调用        |
|Location5 (未知)      | 未路由到 Location5 中的终结点的调用        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams将呼叫转接或转接给另一个Teams用户

当涉及 PSTN 终结点时，Location-Based路由会分析是否为一个或两个用户启用了 Location-Based 路由，并确定是否应该根据这两个终结点的位置转移或转接呼叫。 
 
呼叫转接要求发起用户接听呼叫，而呼叫转接不需要应答初始呼叫。 这意味着，即使 User1 不在接收入站呼叫的位置 (也可以转接呼叫 (请参阅 Teams 用户从[PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)部分接收入站呼叫的表) 并且如果用户 1 无法接收入站呼叫，则不能转移呼叫。 

#### <a name="user-not-enabled-for-location-based-routing"></a>未为用户启用Location-Based路由

未启用自动路由Location-Based可以将 PSTN 呼叫转接或转发给未启用路由路由Location-Based呼叫。 通常不允许用户将 PSTN 呼叫转接或转发给启用了 Location-Based 路由的用户，因为启用 Location-Based 路由的用户通常只允许在启用 Location-Based 路由的网关上共同进行 PSTN 呼叫。 例外情况是启用Location-Based路由的用户漫游到未为路由启用Location-Based站点。 在此方案中，允许转接的呼叫。  

同样，未启用路由Location-Based只能接收未启用路由的另一用户的转接或转发 PSTN Location-Based呼叫。 

#### <a name="user-enabled-for-location-based-routing"></a>为用户启用Location-Based路由

通常，只有当目标用户启用了 Location-Based 路由并位于同一站点时，才允许从启用了 Location-Based 路由的网关转移和转发入站 PSTN 呼叫。 否则，不允许转移和转接呼叫。 

下表显示了是否允许呼叫转接和呼叫转接，具体取决于目标用户的位置。 在此表中，位于 Site1 中的 User1 启动传输或转发到其他 Teams 用户，这些用户也启用了 Location-Based 路由，并且这些用户位于不同的位置。  

|目标用户终结点位置|User1 启动呼叫转接 |User1 启动呼叫转发|
|---------|---------|---------|
|与 User2 (发起程序) |允许|允许|
|不同的网络站点、为用户 3 Location-Based路由 (站点) |不允许|不允许|
|不同的网络站点，未为 Location-Based User4 (启用) |不允许|不允许|
|User5 (未知) | 不允许|不允许|
|User6 (未知) | 不允许|不允许|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams将呼叫转接到 PSTN 终结点

#### <a name="user-not-enabled-for-location-based-routing"></a>未为用户启用Location-Based路由

- 允许将 PSTN 呼叫转移和转接到另一个 PSTN 号码。 
- 将入站 VOIP 呼叫转移和转接到 PSTN 时，必须遵守呼叫者的收费绕过限制。 
    - 如果未为呼叫方启用Location-Based路由，可以将呼叫者转移到未为路由启用Location-Based PSTN 网关。
    - 如果调用方启用了 Location-Based路由，则只能将其传输到位于同一网络Location-Based已启用路由的网关。 

#### <a name="user-enabled-for-location-based-routing"></a>为用户启用Location-Based路由

- 必须将 PSTN 呼叫的入站转接和转发到另一个 PSTN 号码Location-Based入站呼叫到达的已启用路由的网关。 
- 将入站 VOIP 呼叫转移和转接到 PSTN 时，必须同时遵守呼叫方和被呼叫用户的收费绕过限制。 
    - 如果未为呼叫方启用Location-Based路由，可以将呼叫者转移到未为路由启用Location-Based PSTN 网关。
    - 如果调用方启用了 Location-Based路由，则只能将其传输到位于同一网络Location-Based已启用路由的网关。
 
下表显示了路由Location-Based将 VOIP 呼叫从 Site1 中的 User1 路由到将呼叫转接或转接到 PSTN 终结点的不同位置的用户。  

|用户发起呼叫转接或转接  |转移到 PSTN  |转发到 PSTN  |
|---------|---------|---------|
|同一网络站点，为用户 2 Location-Based路由 (启用)    |基于 User2 的语音路由策略，Location-Based站点 1 中启用路由的 Gateway1 路由呼叫转移         |根据 User2 的语音路由Location-Based，呼叫转发只能通过 Site1 上已启用路由的 Gateway1 进行路由         |
|不同的网络站点、为用户 3 Location-Based路由 (站点)     |基于 User3 的语音路由策略，Location-Based站点 1 上启用路由的 Gateway1 路由呼叫转移         |呼叫转发只能根据用户 3 的语音路由Location-Based在 Site1 中通过已启用路由的 Gateway1 进行路由         |
|不同的网络站点，未为 Location-Based User4 (启用)     |基于 User4 的语音路由策略，Location-Based站点 1 中已启用路由的 Gateway1 路由呼叫转移         |基于 User4 的语音路由策略，Location-Based站点 1 中已启用路由的 Gateway1 路由呼叫转发         |
|User5 (未知)      |呼叫转接只能根据用户 5 的语音路由Location-Based在 Site1 中通过已启用路由的 Gateway1 进行路由         |呼叫转发只能根据用户 5 的语音路由Location-Based在 Site1 中通过已启用路由的 Gateway1 进行路由         |
|User6 (未知)    |根据 User6 的语音路由策略，Location-Based站点 1 上启用路由的 Gateway1 路由呼叫转移        |根据 User6 的语音路由策略，Location-Based站点 1 中已启用路由的 Gateway1 路由呼叫转发         |

### <a name="simultaneous-ringing"></a>同时响铃

当启用了 Location-Based 路由的用户收到呼叫并已启用同时响铃时，Location-Based 路由将分析呼叫方的位置和被调用方终结点，确定是否应路由呼叫。 同时拨打遵循与呼叫Location-Based相同的规则。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>同时为另一个Teams响铃

下表显示了用户Location-Based用户 1 的入站 PSTN 呼叫是否允许同时拨打不同的用户。

|目标用户终结点位置|同时响铃  |
|---------|---------|
|与 User2 (发起程序)    |允许         |
|为用户 3 路由路由Location-Based启用 (漫游)    |不允许         |
|未为用户 4 Location-Based路由 (漫游)    |不允许        |
|User5 (未知)     | 不允许        |
|User6 (未知)     |不允许        |
|目标用户是 PSTN 号码    |基于 User1 的语音路由策略，Location-Based站点 1 上已启用路由的 Gateway1 路由呼叫      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>同时响铃到 PSTN 终结点

下表显示了 Location-Based从位于站点 1 的 User1 到不同位置的用户（同时拨打设置为 PSTN 号码）的入站 VOIP 呼叫的路由行为。 

|调用的用户终结点位置  |同时响铃目标是 PSTN 终结点 |
|---------|---------|
|同一网络站点，为用户 2 Location-Based路由 (启用)     |基于 User2 的语音路由策略，Location-Based站点 1 上的路由网关1 路由呼叫       |
|为 User3 Location-Based路由 (启用)     |基于 User3 的语音路由策略，Location-Based站点 1 上的路由网关1 路由呼叫        |
|未为 User4 路由Location-Based启用 (站点)     |基于 User4 的语音路由策略，Location-Based站点 1 上的路由网关1 路由呼叫         |
|User5 (未知)     |根据用户 5 的语音路由Location-Based，只能通过 Site1 上的路由网关1 路由呼叫         |
|User6 (未知)    |基于 User6 的语音路由策略，Location-Based站点 1 上的路由网关1 路由呼叫         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>通过语音应用呼叫或 (自动助理呼叫队列呼叫) 

允许来自已启用路由Location-Based网关的入站 PSTN 呼叫连接到自动助理或呼叫队列。 启用自动Location-Based路由的用户只能位于入站 PSTN 呼叫源自的同一站点时，才能接收来自这些应用程序的入站呼叫转移。 
 
语音应用传输允许呼叫转接和同时拨打用户和 PSTN。 完成目标调用时，需要遵守Location-Based路由规则。  
 
还允许转发到语音邮件。  

### <a name="delegation"></a>委派

Teams用户可以选择可以代表他们拨打和接听呼叫的代理人。 服务中的委派Teams受Location-Based路由的影响，如下所示： 
- 对于来自已启用路由Location-Based代理的出站调用，适用相同的规则。 呼叫路由基于代理的呼叫授权策略、语音路由策略和位置。 有关详细信息，请参阅[Teams向 PSTN](#teams-user-places-an-outbound-call-to-the-pstn)发送出站呼叫。 
- 对于向代理人的入站 PSTN 呼叫，Location-Based呼叫转发或同时拨打给其他用户的相同路由规则也适用于代理人。 有关详细信息，请参阅Teams转接[](#teams-user-transfers-or-forwards-call-to-another-teams-user)或转接给另一 Teams 用户的呼叫、Teams将呼叫转接或转接到[PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)终结点和[同时拨打](#simultaneous-ringing)。 当代理人将 PSTN 终结点设置为同时拨打目标时，代理的语音路由策略用于将呼叫路由到 PSTN。 
- 对于委派，建议委派方和关联的代理人位于同一网络站点中。 

## <a name="other-planning-considerations"></a>其他规划考虑事项

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>从本地路由部署Location-Based更改

不再使用网络站点语音路由策略。 相反，我们使用用户的语音路由策略。 这意味着，要允许用户漫游到其他站点，语音路由策略必须包含漫游站点网关。 

### <a name="technical-considerations-for-location-based-routing"></a>基于位置的路由的技术注意事项

支持 IPv4 和 IPv6 子网，但在检查匹配时，IPv6 优先。

### <a name="client-support-for-location-based-routing"></a>客户端对路由Location-Based支持

支持Teams客户端：
- Teams桌面客户端 (Windows Mac) 
- Teams iOS 和 Android (移动客户端) 
- TeamsIP 电话

不支持Teams Web 客户端Skype for Business客户端。

### <a name="capabilities-not-supported-by-location-based-routing"></a>基于位置的路由不支持的功能

Location-Based路由不适用于以下类型的交互。 Location-Based以下情况中，当终结点与 PSTN Teams交互时，不强制使用路由： 
- 通过呼叫寄存对 PSTN 呼叫进行呼叫寄存或检索 
- 本地用户Skype for Business或 Skype for Business Online 用户Teams用户  

### <a name="location-based-routing-for-conferencing"></a>Location-Based会议路由

不允许Location-Based PSTN 呼叫的已启用路由的用户启动与其他用户或 PSTN 号码的会议。 允许连接到自动助理或呼叫队列。 如果用户具有会议许可证，用户必须启动与相关用户的会议，并通过会议网桥呼叫 PSTN 以开始电话会议。  

### <a name="media-bypass-requirement-for-location-based-routing"></a>媒体旁路要求Location-Based路由

如果正在印度部署Location-Based路由，则还需要配置媒体旁路。 有关详细信息，请参阅使用直接路由规划 [媒体](direct-routing-plan-media-bypass.md) 绕过和直接路由 [的本地媒体优化](direct-routing-media-optimization.md)。

### <a name="direct-voice-over-ip-voip"></a>通过 IP 直接语音 (VoIP) 

不得使用任何 (设备) VoIP 直接语音。

## <a name="next-steps"></a>后续步骤

转到配置[路由的网络Location-Based。](location-based-routing-configure-network-settings.md)

## <a name="related-topics"></a>相关主题

- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [云语音功能的网络设置Teams](cloud-voice-network-settings.md)
