---
title: 为直接路由计划基于位置的路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: 了解如何规划 Teams 电话直接路由Location-Based路由。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 354a3ae6ec4fb482b6ba0d5136597438c37acbe2
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727784"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>为直接路由计划基于位置的路由

在某些国家和地区，绕过公用电话交换网 (PSTN) 提供商来降低长途呼叫成本是违法的。 

本文介绍使用Location-Based路由根据地理位置限制 Microsoft Teams 用户的通行费绕过需要了解的内容。 本文仅适用于直接路由。 Location-Based路由不适用于通话套餐或操作员连接。

准备好启用Location-Based路由时，请参阅：

- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)

> [!NOTE]
> 不应使用Location-Based路由基于用户的位置动态路由 PSTN 呼叫。 这样做可能会导致意外结果。

## <a name="overview"></a>概述

Location-Based路由允许根据策略和用户在入站或出站 PSTN 呼叫时的地理位置限制用户的收费绕过。 

Location-Based路由使用为网络区域、站点和子网定义的网络拓扑。 当限制某个位置的收费绕过时，可将该位置的每个 IP 子网和每个 PSTN 网关关联到网络站点。 

在 PSTN 呼叫时，用户的位置由用户的 Teams 终结点连接到的 IP 子网确定。 如果用户在不同站点有多个 Teams 客户端，Location-Based路由将根据 Teams 终结点的位置单独强制实施每个客户端的路由。

有关网络设置的详细信息，请参阅 [Teams 中云语音功能的网络设置](cloud-voice-network-settings.md)。

本文假定网络站点可能处于以下状态之一：

- **已启用** - 使用租户网络子网和站点配置并启用了Location-Based路由的站点。

- **未启用** - 使用租户网络子网和站点配置的站点，但未启用Location-Based路由。

- **未知** - 未使用租户网络子网和站点配置的站点。 通常，此类站点要么是公司网络的内部，但根据设计未配置，要么位于公司网络外部。 在任何情况下，都不为这些站点启用Location-Based路由。 

### <a name="toll-bypass-evaluation-and-outcome"></a>收费旁路评估和结果

使用Location-Based路由时，将评估 Teams 用户与 PSTN 之间的呼叫，以确定是否限制收费绕过。 根据结果，调用将完成或不会完成。 

如果用户启用了Location-Based路由，并且用户位于Location-Based路由限制生效的站点，则会限制该用户的收费绕过。 Teams 使用以下信息确定是否限制通行费绕道： 

- 是否为 Teams 用户启用Location-Based路由，如用户的 Teams 呼叫策略中定义。

- Teams 用户的终结点网络站点位置以及站点是否已启用Location-Based路由。

- 呼叫使用的 PSTN 网关的网络站点位置。

- 呼叫使用的 PSTN 网关是否已为Location-Based路由启用。

- 对于转接方案，PSTN 呼叫的路由基于呼叫转接人员的路由设置，以及呼叫转移到的 Teams 用户的Location-Based路由设置。  

- 对于会议和组呼叫方案，无论其收费绕过限制的 Teams 用户是还是已是呼叫的一部分。

如果通话无法完成，Teams 用户会收到如下通知：

- 对于出站 PSTN 呼叫，呼叫窗口中会显示以下消息：由于组织的设置，不允许呼叫。

- 对于入站 PSTN 呼叫，呼叫根据被调用的 Teams 用户的未接听呼叫转接设置进行路由，通常路由到语音邮件。 如果 Teams 用户未配置未接听的呼叫设置，呼叫将断开连接。

## <a name="apply-location-based-routing"></a>应用Location-Based路由

必须将Location-Based路由应用于以下内容：

- [用户](#apply-location-based-routing-at-the-user-location)
- [网络站点](#apply-location-based-routing-at-the-network-site)
- [PSTN 网关](#apply-location-based-routing-at-the-pstn-gateway)

请记住以下最佳做法：

- 必须为与网关关联的 PSTN 网关和网络站点启用Location-Based路由。

- 若要通过启用了Location-Based路由的 PSTN 网关发出呼叫，还必须为用户启用Location-Based路由。

- 若要允许启用Location-Based路由的用户从未知网络站点发出出站 PSTN 呼叫，必须满足以下条件：

  - 呼叫需要从为Location-Based路由启用的 PSTN 网关传出。
  - 必须将 PSTN 网关配置为将 GatewayLbrEnabledUserOverride 标志设置为 True。


### <a name="apply-location-based-routing-at-the-user-location"></a>在用户位置应用Location-Based路由

收费绕过限制控制用户可以拨打和接收 PSTN 呼叫的条件，以及可以使用的 PSTN 网关。 

如果用户受到收费绕过限制，则必须为该用户启用Location-Based路由。 启用的用户位于启用了Location-Based路由的站点时，用户必须通过同时连接到站点并启用Location-Based路由的网关进行呼叫。 

Location-Based路由的工作原理是基于用户的 Teams 终结点的 IP 地址确定用户的当前位置，并相应地应用规则。 启用Location-Based路由的用户的位置可按如下方式分类： 

- **用户位于与分配了 DID 的 PSTN 网关关联的启用了路由Location-Based站点。**<br>在此方案中，用户位于启用了Location-Based路由的配置网络站点中，并且用户的直接向内拨号 (DID) 号码在同一网络站点中的 PSTN 网关上终止。 例如，用户位于其办公室。 

- **用户位于另一个启用了路由Location-Based的站点上，该站点未关联到分配了 DID 的 PSTN 网关。**<br>在此方案中，用户位于已启用Location-Based路由的已配置网络站点中，并且该站点与分配了用户的 DID 号码的 PSTN 网关不关联。 例如，用户前往另一个办公室。  

- **用户位于未启用Location-Based路由的内部站点。** <br>在此方案中，用户位于未启用Location-Based路由的已配置网络站点中。 

- **用户位于未知站点。** 
    - 用户位于未定义为网络站点的内部网络中。 
    - 用户位于内部网络外部。 例如，用户在家中或咖啡店的 Internet 上。 

### <a name="apply-location-based-routing-at-the-network-site"></a>在网络站点上应用Location-Based路由 

启用Location-Based路由的用户漫游时，为Location-Based路由启用的网络站点将帮助确定要使用的网关。 例如：

- 如果启用了Location-Based路由的用户漫游到启用了Location-Based路由的站点，则只有为该站点上启用了Location-Based路由的 PSTN 网关可用于出站呼叫。 

- 如果启用了Location-Based路由的用户漫游到未启用Location-Based路由的站点，则任何未启用Location-Based路由的网关都可用于出站呼叫。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>在 PSTN 网关上应用Location-Based路由  

若要在 PSTN 网关上应用Location-Based路由，必须执行以下操作：

- 为Location-Based路由启用网关。  (必须为网关启用Location-Based路由，以确保未启用 Location-Based Routing 的用户无法使用它们。) 

- 将网络站点分配到网关。

然后，系统确定是否允许给定站点中的给定用户使用网关。 

此外，如果将 GatewayLbrEnabledUserOverride 设置为 True，则未知站点中启用了基于位置的路由的用户（例如，在家工作的用户）可以进行出站 PSTN 呼叫。


## <a name="restriction-rules"></a>限制规则

限制规则取决于是否为 Teams 用户启用了Location-Based路由。

### <a name="user-is-enabled-for-location-based-routing"></a>用户已启用Location-Based路由

为用户启用Location-Based路由时，以下情况适用：

- **若要进行出站 PSTN 呼叫**，必须满足以下条件之一：

  - 用户的终结点位于启用了Location-Based路由的站点上，并通过同一站点中启用了Location-Based路由的 PSTN 网关调用出口。  

  - 用户的终结点位于未知站点，并通过为Location-Based路由启用的 PSTN 网关调用出口。 PSTN 网关配置为 GatewayLbrEnabledUserOverride 参数设置为 True。

  - 用户的终结点位于未启用Location-Based路由的站点上，并通过未启用Location-Based路由的 PSTN 网关调用出口。

- **若要接收入站 PSTN 呼叫**，必须满足以下条件之一： 

   - 用户的应答终结点和通过的 PSTN 网关必须位于为Location-Based路由启用的同一站点。 必须为 PSTN 网关启用Location-Based路由。

   - 用户的应答终结点和通过的 PSTN 网关必须位于未启用Location-Based路由的同一站点。 不能为Location-Based路由启用 PSTN 网关。   (此方案涉及通过另一个 PSTN 网关将传入 PSTN 呼叫重新路由到入口，而不是通常用于对用户的电话号码进行传入呼叫的网关。) 

   - 在任何其他方案中（例如，如果用户正在漫游），则不允许呼叫，并且将路由到用户的未接听呼叫转接设置， (通常为语音邮件) 。  
   
- **对于 1：1 Teams VoIP 呼叫和转接到 PSTN**，请注意以下事项：

  - 呼叫的路由（即，用于传出呼叫的 PSTN 网关）基于转移呼叫的用户的路由设置。

  - 是否允许传输取决于以下各项：
  
    - 要传输到 PSTN 的用户的Location-Based路由设置。
    - 终结点网络站点位置。
    - 是否为Location-Based路由启用位置。

    如果被转移的用户能够使用相同的 PSTN 网关在其当前位置进行 PSTN 呼叫，则允许转移。

- **对于传入或传出 PSTN 呼叫并转接到另一个 Teams 用户**，是否允许转移取决于以下情况：

   - 接收已转移呼叫的用户的路由设置。 
   - 终结点网络站点位置。
   - 是否为Location-Based路由启用位置。

   如果接收转接呼叫的人员能够使用正在进行的 PSTN 呼叫使用的 PSTN 网关在其当前位置发出或接收该 PSTN 呼叫，则允许转接。


### <a name="user-is-not-enabled-for-location-based-routing"></a>用户未启用Location-Based路由

当 Teams 用户未启用Location-Based路由时，所有与该用户之间的呼叫都必须通过未启用Location-Based路由的 PSTN 网关进行路由。 通过启用Location-Based路由的 PSTN 网关路由到此类用户的入站呼叫将路由到用户的未接听呼叫转接设置 (通常为语音邮件) 。

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>入站和出站呼叫的决策流

下图显示了入站和出站调用的决策流。

**入站呼叫**

![显示入站呼叫的 LBR 的关系图](media/lbr-routing-inbound1.png "显示Location-Based路由方案的关系图")

**出站调用**

![显示出站调用的 LBR 的关系图](media/lbr-routing-outbound1.png "显示Location-Based路由方案的关系图")


## <a name="scenarios-for-location-based-routing"></a>基于位置的路由的方案

本部分介绍使用Location-Based路由限制收费绕过的不同方案。 这些方案比较了未启用Location-Based路由的用户与启用了Location-Based路由的用户的呼叫路由方式。

- [Teams 用户向 PSTN 发出出站呼叫](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams 用户从 PSTN 接收入站呼叫](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams 用户将呼叫转接或转接到另一个 Teams 用户](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams 用户将呼叫转接或转接到 PSTN 终结点](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同时响铃](#simultaneous-ringing)
- [委派](#delegation)

下图显示了Location-Based路由在每个方案中启用的限制。 为Location-Based路由启用的用户、网络站点和网关有一个边界。 使用关系图作为指南来帮助你了解Location-Based路由在每个方案中的工作原理。  

![显示Location-Based路由方案的关系图。](media/lbr-direct-routing.png "显示Location-Based路由方案的关系图")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams 用户向 PSTN 发出出站呼叫

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用Location-Based路由

未启用Location-Based路由的用户可以通过其分配的语音路由策略，使用未启用Location-Based路由的任何站点的任何网关进行出站呼叫。 但是，如果为网关启用了Location-Based路由，则用户无法通过网关进行出站呼叫，即使该网关已分配给其语音路由策略。 如果用户漫游到启用了Location-Based路由的站点，他们只能通过未启用Location-Based路由的普通路由网关进行呼叫。
 
#### <a name="user-enabled-for-location-based-routing"></a>用户已启用Location-Based路由

相比之下，为启用Location-Based路由的用户的出站呼叫路由受用户终结点的网络位置的影响。 下表显示了Location-Based路由如何影响 User1 的出站呼叫路由，具体取决于 User1 的位置。 

|User1 终结点位置  |User1 的出站呼叫路由  |
|---------|---------|
|为用户分配 DID 的同一站点，为站点启用了Location-Based路由 (Site1)       |根据用户的语音路由策略，通过已启用 Location-Based 路由 (GW1) 的网关路由的呼叫         |
|为站点启用Location-Based路由 (Site2)     |根据用户的语音路由策略，通过已启用Location-Based路由 (GW2) 的网关路由的呼叫        |
|与分配用户 DID 的站点不同，未为站点启用Location-Based路由 (Site3)   |根据用户的语音路由策略，通过网关路由的呼叫，该网关未启用Location-Based路由的站点上未启用Location-Based路由 (GW3)        |
|未知的内部网络 (Location4)     |  除非网关将 GatewayLbrEnabledUserOverride 设置为 True，否则不允许 PSTN 呼叫       |
|未知的外部网络 (Location5)     | 除非网关将 GatewayLbrEnabledUserOverride 设置为 True，否则不允许 PSTN 呼叫       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams 用户从 PSTN 接收入站呼叫

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用Location-Based路由

未启用Location-Based路由的用户可以接收来自网关的入站呼叫，该呼叫未启用其分配的 DID 号码入口的Location-Based路由。 如果用户漫游到未启用Location-Based路由的站点，他们仍可以通过其普通 PSTN 网关接收呼叫。
  
#### <a name="user-enabled-for-location-based-routing"></a>用户已启用Location-Based路由

相比之下，启用Location-Based路由的用户只能接收来自 PSTN 网关的入站呼叫，当他们位于同一站点时，他们的 DID 被分配到。 下表显示了 User1 移动到不同网络位置时 User1 如何接收入站呼叫。 如果呼叫未路由到用户的终结点，则会转到用户的未接听呼叫转接设置（如果配置了这些设置）。 通常，呼叫会转发到语音邮件。  

|User1 终结点位置  |路由到 User1 的入站呼叫  |
|---------|---------|
|与分配用户 DID 的站点相同，为站点启用了Location-Based路由 (Site1)    | 在 Site1 中路由到 User1 终结点的调用        |
|为站点启用Location-Based路由 (Site2)     | 未路由到 Site2 中的终结点的调用        |
|与分配用户 DID 的站点不同，未为站点启用Location-Based路由 (Site3)     | 未路由到 Site3 中的终结点的调用        |
|未知的内部网络 (Location4)    | 未路由到 Location4 中的终结点的调用        |
|未知的外部网络 (Location5)      | 未路由到 Location5 中的终结点的调用        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams 用户将呼叫转接或转接到另一个 Teams 用户

当涉及 PSTN 终结点时，Location-Based路由会分析是否为一个或两个用户启用了Location-Based路由，并确定应根据两个终结点的位置转移或转接呼叫。 
 
呼叫转移要求发起用户接听呼叫，而呼叫转接不需要接听初始呼叫。 即使 User1 不在接收入站呼叫的位置，也可以转接呼叫 (查看 [Teams 用户从 PSTN 部分接收入站呼叫](#teams-user-receives-an-inbound-call-from-the-pstn) 的表) ，如果 User1 无法接收入站呼叫，则无法转移呼叫。 

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用Location-Based路由

未启用Location-Based路由的用户可以将 PSTN 呼叫转移或转接到未启用Location-Based路由的其他用户。 启用Location-Based路由的用户通常位于Location-Based为 PSTN 呼叫启用路由的网关。 因此，不允许未启用的用户将 PSTN 呼叫转接或转接到启用了Location-Based路由的用户。 例外是启用Location-Based路由的用户漫游到未启用Location-Based路由的站点。 在此方案中，允许传输的呼叫。  

同样，未启用Location-Based路由的用户只能接收来自另一个未启用Location-Based路由的用户的转接或转接 PSTN 呼叫。 

#### <a name="user-enabled-for-location-based-routing"></a>用户已启用Location-Based路由

仅当目标用户启用了Location-Based路由并且位于同一站点时，才允许从启用了Location-Based路由的网关转移和转发入站 PSTN 呼叫。 否则，不允许转移和转接呼叫。 

下表显示是否允许呼叫转接和呼叫转接，具体取决于目标用户的位置。 在此表中，位于 Site1 中的 User1 启动转移或转发给其他 Teams 用户，这些用户也启用了Location-Based路由，并且位于不同位置。  

|目标用户终结点位置|User1 启动呼叫转移 |User1 启动呼叫转接|
|---------|---------|---------|
|与发起方 (User2) 相同的网络站点|允许|允许|
|不同的网络站点、为 Location-Based 路由启用的站点 (User3) |不允许|不允许|
|不同网络站点，站点未启用Location-Based路由 (User4) |不允许|不允许|
|未知的内部网络 (User5) | 不允许|不允许|
|未知的外部网络 (User6) | 不允许|不允许|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams 用户将呼叫转接或转接到 PSTN 终结点

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用Location-Based路由

- 允许将 PSTN 呼叫转接和转接到另一个 PSTN 号码。 

- 将入站 VOIP 呼叫转接和转发到 PSTN 必须遵循呼叫者的收费绕过限制。 

    - 如果未为调用方启用Location-Based路由，则可以将其转移到任何未启用Location-Based路由的 PSTN 网关。
    - 如果调用方启用了Location-Based路由，则只能将其传输到位于同一网络站点的启用了Location-Based路由的网关。 

#### <a name="user-enabled-for-location-based-routing"></a>用户已启用Location-Based路由

- 将 PSTN 呼叫转接和转接到另一个 PSTN 号码时，必须路由到与入站呼叫到达的同一Location-Based已启用路由的网关。

- 将入站 VOIP 呼叫转接和转发到 PSTN 必须同时遵守呼叫方和被呼叫用户的收费绕过限制。 

    - 如果未为调用方启用Location-Based路由，则可以将其转移到任何未启用Location-Based路由的 PSTN 网关。

    - 如果调用方启用了Location-Based路由，则只能将其传输到位于同一网络站点的启用了Location-Based路由的网关。
 
下表显示了Location-Based路由如何影响从 Site1 上启用Location-Based路由的 User1 到不同位置将呼叫转接到 PSTN 终结点的用户的 VOIP 呼叫路由。  

|用户发起呼叫转移或转接  |传输或转发到 PSTN  |
|---------|---------|
|同一网络站点、为 Location-Based 路由启用的站点 (User2)    |仅当基于 User2 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫         |
|不同的网络站点、为 Location-Based 路由启用的站点 (User3)     |仅当基于 User3 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫 |
|不同网络站点，站点未启用Location-Based路由 (User4)     |仅当基于 User4 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫          |
|未知的内部网络 (User5)      |仅当基于 User5 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫          |
|未知的外部网络 (User6)    |仅当基于 User6 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫          |

### <a name="simultaneous-ringing"></a>同时响铃

启用Location-Based路由的用户收到呼叫并同时启用了响铃时，Location-Based路由将分析呼叫方的位置和被调用方终结点，以确定是否应路由呼叫。 同时响铃遵循呼叫转接和转接相同的Location-Based规则。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>另一个 Teams 用户同时响铃

下表显示了Location-Based路由是否允许同时为 User1 拨打不同用户的入站 PSTN 呼叫。

|目标用户终结点位置|同时环  |
|---------|---------|
|与发起方 (User2) 相同的网络站点   |允许         |
|为 Location-Based 路由启用了不同的漫游网络站点 (User3)    |不允许         |
|未为Location-Based路由启用漫游网络站点 (User4)    |不允许        |
|未知的内部网络 (User5)     | 不允许        |
|未知的外部网络 (User6)     |不允许        |
|目标用户是 PSTN 号码    |只能根据 User1 的语音路由策略，通过 Site1 Location-Based已启用路由的 Gateway1 来路由呼叫      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>同时响铃到 PSTN 终结点

下表显示了从位于 Site1 的已启用 Location-Based 路由的 User1 到同时响铃设置为 PSTN 号码的不同位置的用户的入站 VoIP 呼叫Location-Based路由行为。 

|调用的用户终结点位置  |同时响铃目标是 PSTN 终结点 |
|---------|---------|
|同一网络站点、为 Location-Based 路由启用的站点 (User2)     |仅当基于 User2 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫        |
|为 Location-Based 路由启用的不同网络站点 (User3)     |仅当基于 User3 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫         |
|不同网络站点未为 Location-Based 路由启用 (User4)     |仅当基于 User4 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫          |
|未知的内部网络 (User5)     |仅当基于 User5 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫          |
|未知的外部网络 (User6)    |仅当基于 User6 的语音路由策略的计算路由导致通过 Site1 上启用了Location-Based路由的 Gateway1 的路由时，才允许生成的 PSTN 呼叫          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>通过语音应用 (自动助理或呼叫队列) 

允许来自已启用路由Location-Based网关的入站 PSTN 呼叫连接到自动助理或呼叫队列。 

如果启用了Location-Based路由的用户位于来自入站 PSTN 呼叫的同一站点，则支持这些应用程序接收这些应用程序的入站呼叫转接。 若要在这些方案中支持本地媒体优化和媒体旁路，必须将呼叫队列配置为传输模式 (会议模式 = OFF) 。
 
语音应用传输允许呼叫转接和同时响铃给用户和 PSTN。 完成对目标的调用受前面列出的相同Location-Based路由规则的约束。  
 
还允许转发到语音邮件。  

### <a name="delegation"></a>委派

Teams 用户可以选择可以代表他们拨打和接听呼叫的代理人。 Teams 中的委派功能受Location-Based路由影响，如下所示： 

- 对于代表委托人从Location-Based已启用路由的委托的出站调用，应用相同的规则。 呼叫路由基于代理人的呼叫授权策略、语音路由策略和位置。 有关详细信息，请参阅 [Teams 用户向 PSTN 发出出站呼叫](#teams-user-places-an-outbound-call-to-the-pstn)。 

- 对于对委托器的入站 PSTN 呼叫，适用于呼叫转接或同时响铃给其他用户的相同Location-Based路由规则也适用于代理人。 有关详细信息，请参阅 [Teams 用户转接呼叫或转接呼叫到另一个 Teams 用户](#teams-user-transfers-or-forwards-call-to-another-teams-user)、 [Teams 用户转接呼叫或转接 PSTN 终结点](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)和 [同时响铃](#simultaneous-ringing)。 当委托将 PSTN 终结点设置为同时响铃目标时，将使用委托的语音路由策略将呼叫路由到 PSTN。 

- 对于委派，Microsoft 建议委托人和关联的委托位于同一网络站点中。 

## <a name="other-planning-considerations"></a>其他规划考虑事项

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>本地Location-Based路由部署的更改

不再使用网络站点语音路由策略。 相反，我们使用用户的语音路由策略。 若要允许用户漫游到其他站点，语音路由策略必须包括漫游站点的网关。 

### <a name="technical-considerations-for-location-based-routing"></a>基于位置的路由的技术注意事项

支持 IPv4 和 IPv6 子网，但在检查匹配项时，IPv6 优先。

### <a name="client-support-for-location-based-routing"></a>客户端对Location-Based路由的支持

支持以下 Teams 客户端：
- Windows 和 Mac)  (Teams 桌面客户端
-  (iOS 和 Android) 的 Teams 移动客户端
- Teams IP 电话

不支持 Teams Web 客户端和Skype for Business客户端。

### <a name="capabilities-not-supported-by-location-based-routing"></a>基于位置的路由不支持的功能

Location-Based路由不适用于以下类型的交互。 在以下方案中，当 Teams 终结点与 PSTN 终结点交互时，不会强制实施Location-Based路由： 

- 通过呼叫寄存对 PSTN 呼叫进行呼叫寄存或检索 

- 本地Skype for Business用户或Skype for Business Online 用户呼叫 Teams 用户  

### <a name="location-based-routing-for-conferencing"></a>会议Location-Based路由

在 PSTN 呼叫上没有音频会议许可证的情况下启用Location-Based路由的用户不允许与其他用户或 PSTN 号码启动会议。 允许连接到自动助理或呼叫队列。

如果用户具有音频会议许可证，则用户必须与相关用户启动会议，并通过会议网桥呼叫 PSTN 以启动电话会议。 如果用户已在 PSTN 呼叫中，他们可以使用会议网桥将呼叫升级为呼叫，从而将其他用户或 PSTN 号码添加到呼叫中。

在由没有音频会议许可证的用户发起的电话会议中，如果会议呼叫中至少有一个启用Location-Based路由的用户，则不允许添加 PSTN 参与者。 如果在邀请任何启用Location-Based路由的参与者加入呼叫之前，至少有一个 PSTN 参与者是或已加入此类电话会议，则无法将启用路由的此类Location-Based参与者添加到呼叫中。

如果启用Location-Based路由的用户正在从未启用Location-Based路由的内部站点加入电话会议，则不会强制执行上述段落中的限制。 

不得与印度的任何电话设备一起部署音频会议的网络会议。

不允许 PSTN 呼叫上启用Location-Based路由的用户将该呼叫与另一个呼叫合并。 不支持以下各项：录制 PSTN 呼叫和 PSTN 呼叫的符合性记录。

### <a name="media-bypass-requirement-for-location-based-routing"></a>Location-Based路由的媒体旁路要求

如果要在印度部署Location-Based路由，则还需要配置媒体旁路。 若要了解详细信息，请参阅 [使用直接路由规划媒体旁路](direct-routing-plan-media-bypass.md) 和 [直接路由的本地媒体优化](direct-routing-media-optimization.md)。

### <a name="direct-voice-over-ip-voip"></a>通过 IP 的直接语音 (VoIP) 

直接语音通过 IP (VoIP) 不得与任何电话设备一起部署在印度。


## <a name="related-articles"></a>相关文章

- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [Teams 中云语音功能的网络设置](cloud-voice-network-settings.md)
