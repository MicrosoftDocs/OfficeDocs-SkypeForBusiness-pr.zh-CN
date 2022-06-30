---
title: 为直接路由计划基于位置的路由
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: 了解如何为 Teams 电话直通路由规划Location-Based路由。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: d282a2cd9588c2e7104b3093d03da082e9cf388b
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562621"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>为直接路由计划基于位置的路由

在一些国家和地区，绕过公共交换电话网络 (PSTN) 提供商来降低长途通话成本是非法的。 

本文介绍使用Location-Based路由来限制 Microsoft Teams 用户基于其地理位置的通行费旁路所需了解的内容。 本文仅适用于直接路由。 Location-Based路由不适用于呼叫计划或运算符连接。

准备好启用Location-Based路由后，请参阅：

- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为Location-Based路由部署网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)

> [!NOTE]
> 不应使用Location-Based路由根据用户的位置动态路由 PSTN 调用。 这样做可能会导致意外的结果。

## <a name="overview"></a>概述

Location-Based路由允许根据策略和用户在入站或出站 PSTN 调用时的地理位置限制用户的通行费旁路。 

Location-Based路由使用你为网络区域、站点和子网定义的网络拓扑。 如果某个位置限制了通行费旁路，则会将该位置的每个 IP 子网和每个 PSTN 网关关联到网络站点。 

在 PSTN 调用时，用户的位置由用户的 Teams 终结点连接到的 IP 子网决定。 如果用户在不同站点上有多个 Teams 客户端，则Location-Based路由会根据 Teams 终结点的位置分别强制执行每个客户端的路由。

有关网络设置的详细信息，请参阅 [Teams 中云语音功能的网络设置](cloud-voice-network-settings.md)。

本文假定网络站点可以处于以下状态之一：

- **已启用** - 使用租户网络子网和站点配置并启用了Location-Based路由的站点。

- **未启用** - 使用租户网络子网和站点配置的站点，但未启用Location-Based路由。

- **未知** - 未使用租户网络子网和站点配置的站点。 通常，此类站点在公司网络内部，但设计上未配置，或在公司网络外部。 在任何情况下，这些站点都未启用Location-Based路由。 

### <a name="toll-bypass-evaluation-and-outcome"></a>通行费旁路评估和结果

使用Location-Based路由时，会评估 Teams 用户与 PSTN 之间的调用以确定是否限制了通行费旁路。 根据结果，调用将或不会完成。 

如果为用户启用了Location-Based路由，并且用户位于Location-Based路由限制生效的站点，则该用户将限制通行费旁路。 Teams 使用以下信息来确定是否限制通行费旁路： 

- Teams 用户是否已启用Location-Based路由，如用户的 Teams 呼叫策略中定义的那样。

- Teams 用户的终结点网络站点位置以及站点是否启用Location-Based路由。

- 呼叫正在使用的 PSTN 网关的网络站点位置。

- 调用使用的 PSTN 网关是否已启用Location-Based路由。

- 对于传输方案，PSTN 呼叫的路由基于传输呼叫的人员的路由设置，以及要将呼叫传输到的 Teams 用户的Location-Based路由设置。  

- 对于会议和组呼叫方案，收费旁路受限的 Teams 用户是调用还是已参与呼叫。

如果呼叫无法完成，Teams 用户将收到如下通知：

- 对于出站 PSTN 调用，呼叫窗口中会显示以下消息：由于组织的设置，不允许呼叫。

- 对于入站 PSTN 调用，调用基于调用的 Teams 用户的未接听呼叫转发设置（通常为语音邮件）进行路由。 如果 Teams 用户未配置未答复的呼叫设置，则调用将断开连接。

## <a name="apply-location-based-routing"></a>应用Location-Based路由

必须将Location-Based路由应用到以下内容：

- [用户](#apply-location-based-routing-at-the-user-location)
- [网络站点](#apply-location-based-routing-at-the-network-site)
- [PSTN 网关](#apply-location-based-routing-at-the-pstn-gateway)

请记住以下最佳做法：

- 必须同时为与网关关联的 PSTN 网关和网络站点启用Location-Based路由。

- 若要通过启用Location-Based路由的 PSTN 网关进行调用，还必须为用户启用Location-Based路由。

- 若要允许启用Location-Based路由的用户从未知网络站点发出出站 PSTN 调用，必须为以下内容：

  - 调用需要从启用了Location-Based路由的 PSTN 网关传出。
  - 必须将 PSTN 网关配置为将 GatewayLbrEnabledUserOverride 设置为 True 的标志。


### <a name="apply-location-based-routing-at-the-user-location"></a>在用户位置应用Location-Based路由

通行费旁路限制控制用户可以发出和接收 PSTN 调用的条件以及可使用的 PSTN 网关。 

如果用户受到收费旁路限制，则必须为该用户启用Location-Based路由。 当启用的用户位于启用了Location-Based路由的站点时，用户必须通过既连接到站点又已启用Location-Based路由的网关进行调用。 

Location-Based路由的工作原理是根据用户 Teams 终结点的 IP 地址确定用户的当前位置，并相应地应用规则。 为Location-Based路由启用的用户的位置可按如下所示进行分类： 

- **用户位于与分配其 DID 的 PSTN 网关关联的已启用路由Location-Based站点。**<br>在此方案中，用户位于已为Location-Based路由启用的已配置网络站点中，并且用户的直接向内拨号 (DID) 号码会在同一网络站点中的 PSTN 网关上终止。 例如，用户在其办公室。 

- **用户位于另一个启用了路由Location-Based站点，该站点未关联到分配其 DID 的 PSTN 网关。**<br>在此方案中，用户位于已为Location-Based路由启用的已配置网络站点中，并且该站点未与分配用户 DID 号码的 PSTN 网关关联。 例如，用户将转到另一个办公室。  

- **用户位于未启用Location-Based路由的内部站点。** <br>在此方案中，用户位于未启用Location-Based路由的已配置网络站点中。 

- **用户位于未知站点。** 
    - 用户位于未定义为网络站点的内部网络中。 
    - 用户位于内部网络外部。 例如，用户在家中或咖啡店的 Internet 上。 

### <a name="apply-location-based-routing-at-the-network-site"></a>在网络站点应用Location-Based路由 

当启用了Location-Based路由的用户漫游时，启用了Location-Based路由的网络站点将有助于确定要使用的网关。 例如：

- 如果启用了Location-Based路由的用户漫游到启用了Location-Based路由的站点，则只有启用了该站点Location-Based路由的 PSTN 网关才能用于出站调用。 

- 如果启用了Location-Based路由的用户漫游到未启用Location-Based路由的站点，则任何未启用Location-Based路由的网关都可以用于出站调用。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>在 PSTN 网关应用Location-Based路由  

若要在 PSTN 网关应用Location-Based路由，必须执行以下操作：

- 为Location-Based路由启用网关。  (必须为Location-Based路由启用网关，以确保未启用Location-Based路由的用户无法使用这些网关。) 

- 将网络站点分配给网关。

然后，系统确定是否允许给定站点中的给定用户使用网关。 

此外，如果将 GatewayLbrEnabledUserOverride 设置为 True，则在未知站点中启用了基于位置的路由的用户（例如，在家工作的用户）可以进行出站 PSTN 调用。


## <a name="restriction-rules"></a>限制规则

限制规则取决于 Teams 用户是否已启用Location-Based路由。

### <a name="user-is-enabled-for-location-based-routing"></a>用户已启用Location-Based路由

为用户启用Location-Based路由时，适用以下各项：

- **若要进行出站 PSTN 调用**，必须满足以下条件之一：

  - 用户的终结点位于启用了Location-Based路由的站点，并通过启用了同一站点中Location-Based路由的 PSTN 网关调用出口。  

  - 用户的终结点位于未知站点，通过启用了Location-Based路由的 PSTN 网关调用出口。 PSTN 网关配置为 GatewayLbrEnabledUserOverride 参数设置为 True。

  - 用户的终结点位于未启用Location-Based路由的站点，并通过未启用Location-Based路由的 PSTN 网关调用出口。

- **若要接收入站 PSTN 呼叫**，必须满足以下条件之一： 

   - 用户的应答终结点和调用入口通过的 PSTN 网关必须位于启用Location-Based路由的同一站点。 必须为Location-Based路由启用 PSTN 网关。

   - 用户的应答终结点和呼叫入口通过的 PSTN 网关必须位于未启用Location-Based路由的同一站点。 不得为Location-Based路由启用 PSTN 网关。   (此方案涉及通过另一个 PSTN 网关将传入的 PSTN 呼叫重新路由到入口，而不是通常用于对用户电话号码进行传入呼叫的网关。) 

   - 在任何其他情况下，例如，如果用户正在漫游，则不允许呼叫，并且会路由到用户未接听的呼叫转接设置， (通常语音邮件) 。  
   
- **对于 1：1 Teams VoIP 调用并转移到 PSTN**，请注意以下事项：

  - 呼叫的路由（即要从其发出呼叫的 PSTN 网关）基于用户传输呼叫的路由设置。

  - 是否允许传输基于以下内容：
  
    - 要传输到 PSTN 的用户的Location-Based路由设置。
    - 终结点网络站点位置。
    - 是否为Location-Based路由启用了该位置。

    如果正在传输的用户能够使用同一 PSTN 网关在其当前位置进行 PSTN 调用，则允许传输。

- **对于传入或传出的 PSTN 呼叫并传输到另一个 Teams 用户**，是否允许传输取决于以下内容：

   - 接收传输呼叫的用户的路由设置。 
   - 终结点网络站点位置。
   - 是否为Location-Based路由启用了该位置。

   如果接收传输呼叫的人员能够使用正在进行的 PSTN 呼叫使用的 PSTN 网关在其当前位置拨打或接收该 PSTN 呼叫，则允许传输。


### <a name="user-is-not-enabled-for-location-based-routing"></a>未为用户启用Location-Based路由

如果未为 Teams 用户启用Location-Based路由，则该用户的所有调用都必须通过未为Location-Based路由启用的 PSTN 网关路由。 通过启用了Location-Based路由的 PSTN 网关路由到此类用户的入站呼叫将路由到用户未接听的呼叫转接设置 (通常是语音邮件) 。

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>入站和出站调用的决策流

下图显示了入站和出站调用的决策流。

**入站调用**

![显示入站调用的 LBR 的示意图](media/lbr-routing-inbound1.png "显示Location-Based路由方案的示意图")

**出站调用**

![显示出站调用的 LBR 的示意图](media/lbr-routing-outbound1.png "显示Location-Based路由方案的示意图")


## <a name="scenarios-for-location-based-routing"></a>基于位置的路由的方案

本部分介绍使用Location-Based路由限制通行费旁路的不同方案。 这些方案比较了未启用Location-Based路由的用户与启用了Location-Based路由的用户的呼叫路由方式。

- [Teams 用户向 PSTN 发出出站调用](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams 用户从 PSTN 接收入站呼叫](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams 用户转移或转发对另一个 Teams 用户的调用](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams 用户传输或转发对 PSTN 终结点的调用](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同时响铃](#simultaneous-ringing)
- [委派](#delegation)

下图显示了在每个方案中通过Location-Based路由启用的限制。 为Location-Based路由启用的用户、网络站点和网关周围有边框。 使用该图作为指南，帮助你了解Location-Based路由在每个方案中的工作原理。  

![显示Location-Based路由方案的示意图。](media/lbr-direct-routing.png "显示Location-Based路由方案的示意图")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams 用户向 PSTN 发出出站调用

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用Location-Based路由

未启用Location-Based路由的用户可以使用任何未启用的网关进行出站呼叫，这些网关未通过分配的语音路由策略Location-Based路由。 但是，如果为网关启用了Location-Based路由，则用户无法通过网关进行出站呼叫，即使该网关已分配到其语音路由策略。 如果用户漫游到启用了Location-Based路由的站点，则只能通过未启用Location-Based路由的正常路由网关进行调用。
 
#### <a name="user-enabled-for-location-based-routing"></a>为Location-Based路由启用的用户

相比之下，启用了Location-Based路由的用户的出站调用路由受用户终结点的网络位置的影响。 下表显示了Location-Based路由如何影响 User1 的出站调用路由，具体取决于 User1 的位置。 

|User1 终结点位置  |用户 1 的出站调用路由  |
|---------|---------|
|分配用户的 DID 的同一站点，为站点 1 (Location-Based路由启用站点)       |基于用户的语音路由策略，通过在 Site1 中启用Location-Based路由 (GW1) 的网关进行呼叫路由         |
|与分配用户的 DID 的站点不同，站点已启用Location-Based路由 (Site2)     |基于用户的语音路由策略，通过网关进行呼叫路由，该网关已启用 Location-Based 路由 (GW2) 漫游站点 2        |
|与分配用户的 DID 的站点不同，站点未启用Location-Based路由 (Site3)   |基于用户的语音路由策略，通过未启用Location-Based路由的网关进行呼叫路由，该网关未启用Location-Based路由 (GW3)        |
|未知的内部网络 (Location4)     |  除非网关将 GatewayLbrEnabledUserOverride 设置为 True，否则不允许 PSTN 调用       |
|未知的外部网络 (Location5)     | 除非网关将 GatewayLbrEnabledUserOverride 设置为 True，否则不允许 PSTN 调用       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams 用户从 PSTN 接收入站呼叫

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用Location-Based路由

未启用Location-Based路由的用户可以从未启用其分配的 DID 号码流入的Location-Based路由的网关接收入站呼叫。 如果用户漫游到未启用Location-Based路由的站点，他们仍然可以通过其正常的 PSTN 网关接收呼叫。
  
#### <a name="user-enabled-for-location-based-routing"></a>为Location-Based路由启用的用户

相比之下，为Location-Based路由启用的用户只能从其 DID 分配到的 PSTN 网关接收来自其位于同一站点的入站呼叫。 下表显示了 User1 移动到不同网络位置时 User1 如何接收入站呼叫。 如果调用未路由到用户的终结点，则会转到用户未答复的呼叫转发设置（如果配置了设置）。 通常，呼叫会转发到语音邮件。  

|User1 终结点位置  |将入站调用路由到 User1  |
|---------|---------|
|与分配用户的 DID 的站点相同，站点已启用Location-Based路由 (Site1)    | 路由到 Site1 中 User1 终结点的调用        |
|与分配用户的 DID 的站点不同，站点已启用Location-Based路由 (Site2)     | 未路由到 Site2 中的终结点的调用        |
|与分配用户的 DID 的站点不同，站点未启用Location-Based路由 (Site3)     | 未路由到 Site3 中的终结点的调用        |
|未知的内部网络 (Location4)    | 未路由到 Location4 中的终结点的调用        |
|未知的外部网络 (Location5)      | 未路由到 Location5 中的终结点的调用        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams 用户转移或转发对另一个 Teams 用户的调用

涉及 PSTN 终结点时，Location-Based路由会分析是否为一个或两个用户启用了Location-Based路由，并根据两个终结点的位置确定是否应传输或转发调用。 
 
呼叫传输要求发起用户接听呼叫，而呼叫转接不需要应答初始调用。 即使 User1 不在接收入站呼叫的位置，也可以转发呼叫， (看到 [Teams 用户中的表从 PSTN 部分接收入站呼叫](#teams-user-receives-an-inbound-call-from-the-pstn)) 如果 User1 无法接收入站呼叫，则无法传输呼叫。 

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用Location-Based路由

未启用Location-Based路由的用户可以将 PSTN 调用传输或转发给未启用Location-Based路由的其他用户。 启用Location-Based路由的用户通常共置在启用了路由的网关Location-Based PSTN 调用。 因此，不允许未启用的用户将 PSTN 调用转移或转发给启用了Location-Based路由的用户。 例外情况是，启用了Location-Based路由的用户漫游到未启用Location-Based路由的站点。 在此方案中，允许传输的调用。  

同样，未启用Location-Based路由的用户只能从未启用Location-Based路由的其他用户接收传输或转发 PSTN 呼叫。 

#### <a name="user-enabled-for-location-based-routing"></a>为Location-Based路由启用的用户

仅当目标用户启用了Location-Based路由并位于同一站点时，才允许从已启用Location-Based路由的网关传输和转发入站 PSTN 调用。 否则，不允许传输和转发调用。 

下表显示是否允许呼叫转接和呼叫传输，具体取决于目标用户的位置。 在此表中，位于 Site1 中的 User1 启动传输或转发给其他 Teams 用户，这些用户也已启用Location-Based路由，并且位于不同位置。  

|目标用户终结点位置|User1 启动呼叫传输 |User1 启动呼叫转发|
|---------|---------|---------|
|与发起程序 (User2) 相同的网络站点|允许|允许|
|不同的网络站点，站点启用了Location-Based路由 (User3) |不允许|不允许|
|不同的网络站点，站点未启用Location-Based路由 (User4) |不允许|不允许|
|未知的内部网络 (User5) | 不允许|不允许|
|未知外部网络 (User6) | 不允许|不允许|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams 用户传输或转发对 PSTN 终结点的调用

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用Location-Based路由

- 允许将 PSTN 调用传输到另一个 PSTN 号码并将其转发。 

- 将入站 VOIP 调用传输和转发到 PSTN 必须遵守调用方的通行费旁路限制。 

    - 如果调用方未启用Location-Based路由，则可以将其传输到未为Location-Based路由启用的任何 PSTN 网关。
    - 如果调用方已启用Location-Based路由，则只能将其传输到位于同一网络站点的已启用Location-Based路由网关。 

#### <a name="user-enabled-for-location-based-routing"></a>为Location-Based路由启用的用户

- 必须将 PSTN 调用传入和转发到另一个 PSTN 号码，Location-Based启用路由的网关与入站调用到达的网关相同。

- 将入站 VOIP 调用传输和转发到 PSTN 必须同时遵守调用方和调用用户的通行费旁路限制。 

    - 如果调用方未启用Location-Based路由，则可以将其传输到未为Location-Based路由启用的任何 PSTN 网关。

    - 如果调用方启用了Location-Based路由，则只能将其传输到位于同一网络站点的已启用Location-Based路由网关。
 
下表显示了Location-Based路由如何影响 VOIP 调用从 Site1 中启用Location-Based路由的 User1 路由到不同位置的用户，这些用户将调用传输或转发到 PSTN 终结点。  

|发起呼叫传输或转发的用户  |传输或转发到 PSTN  |
|---------|---------|
|同一网络站点，用于Location-Based路由 (User2)    |仅当基于 User2 语音路由策略的计算路由导致路由通过站点 1 启用了路由的 Gateway1 Location-Based路由时，才允许生成的 PSTN 调用         |
|不同的网络站点，站点启用了Location-Based路由 (User3)     |仅当基于 User3 语音路由策略的计算路由导致路由通过站点 1 中启用了Location-Based路由的 Gateway1 时，才允许生成的 PSTN 调用 |
|不同的网络站点，站点未启用Location-Based路由 (User4)     |仅当基于 User4 语音路由策略的计算路由导致路由在 Site1 中启用了Location-Based路由的 Gateway1 时，才允许生成的 PSTN 调用          |
|未知的内部网络 (User5)      |仅当基于 User5 语音路由策略的计算路由导致路由通过 Site1 中启用了Location-Based路由的 Gateway1 时，才允许生成的 PSTN 调用          |
|未知外部网络 (User6)    |仅当基于 User6 语音路由策略的计算路由导致路由通过站点 1 启用了路由的 Gateway1 Location-Based路由时，才允许生成的 PSTN 调用          |

### <a name="simultaneous-ringing"></a>同时响铃

当启用了Location-Based路由的用户收到呼叫并同时启用了呼叫时，Location-Based路由会分析调用方的位置和调用方的终结点，以确定是否应路由呼叫。 同时响铃遵循与调用传输和转发相同的Location-Based规则。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>另一个 Teams 用户同时响铃

下表显示了Location-Based路由是否允许为 User1 的入站 PSTN 调用同时向不同用户响铃。

|目标用户终结点位置|同时环  |
|---------|---------|
|与发起程序 (User2) 相同的网络站点   |允许         |
|为Location-Based路由 (User3 启用了不同的漫游网络站点)    |不允许         |
|漫游网络站点未启用Location-Based路由 (User4)    |不允许        |
|未知的内部网络 (User5)     | 不允许        |
|未知外部网络 (User6)     |不允许        |
|目标用户是 PSTN 号码    |只能根据 User1 的语音路由策略，通过 Site1 中启用了路由的 Gateway1 Location-Based路由呼叫      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>同时响铃到 PSTN 终结点

下表显示了站点 1 中启用了 Location-Based Routing User1 的入站 VoIP 调用的Location-Based路由行为，这些用户位于不同位置，同时将通道设置为 PSTN 号码。 

|调用用户终结点位置  |同时环目标为 PSTN 终结点 |
|---------|---------|
|同一网络站点，用于Location-Based路由 (User2)     |仅当基于 User2 语音路由策略的计算路由导致路由通过站点 1 启用了路由的 Gateway1 Location-Based路由时，才允许生成的 PSTN 调用        |
|为用户 3 (Location-Based路由启用了不同的网络站点)     |仅当基于 User3 语音路由策略的计算路由导致路由通过站点 1 中启用了Location-Based路由的 Gateway1 时，才允许生成的 PSTN 调用         |
|不同网络站点未启用Location-Based路由 (User4)     |仅当基于 User4 语音路由策略的计算路由导致路由在 Site1 中启用了Location-Based路由的 Gateway1 时，才允许生成的 PSTN 调用          |
|未知的内部网络 (User5)     |仅当基于 User5 语音路由策略的计算路由导致路由通过 Site1 中启用了Location-Based路由的 Gateway1 时，才允许生成的 PSTN 调用          |
|未知外部网络 (User6)    |仅当基于 User6 语音路由策略的计算路由导致路由通过站点 1 启用了路由的 Gateway1 Location-Based路由时，才允许生成的 PSTN 调用          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>通过语音应用 (自动助理或呼叫队列) 进行入站呼叫

允许从启用了路由Location-Based网关的入站 PSTN 调用连接到自动助理或呼叫队列。 

启用了Location-Based路由的用户在位于入站 PSTN 呼叫源自的同一站点时，支持接收这些应用程序的入站呼叫传输。
 
语音应用传输允许呼叫转接和同时拨打用户和 PSTN。 完成对目标的调用需要遵循前面列出的相同Location-Based路由规则。  
 
还允许转发到语音邮件。  

### <a name="delegation"></a>委派

Teams 用户可以选择代表其发出和接听呼叫的代表。 Teams 中的委派功能受Location-Based路由的影响，如下所示： 

- 对于代表委托人从启用了Location-Based路由委托的出站调用，适用相同的规则。 呼叫路由基于委托的呼叫授权策略、语音路由策略和位置。 有关详细信息，请参阅 [Teams 用户对 PSTN 进行出站调用](#teams-user-places-an-outbound-call-to-the-pstn)。 

- 对于委托者的入站 PSTN 调用，适用于呼叫转接或同时向其他用户发出呼叫的相同Location-Based路由规则也适用于委托。 有关详细信息，请参阅 [Teams 用户转移或转发对另一个 Teams 用户的调用](#teams-user-transfers-or-forwards-call-to-another-teams-user)、 [Teams 用户传输或转发对 PSTN 终结点的调用](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)，以及 [同时响铃](#simultaneous-ringing)。 当委托将 PSTN 终结点设置为同时响铃目标时，委托的语音路由策略用于将调用路由到 PSTN。 

- 对于委派，Microsoft 建议委派人和关联委托位于同一网络站点中。 

## <a name="other-planning-considerations"></a>其他规划考虑事项

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>本地路由部署Location-Based更改

不再使用网络站点语音路由策略。 相反，我们使用用户的语音路由策略。 若要允许用户漫游到其他网站，语音路由策略必须包括漫游网站的网关。 

### <a name="technical-considerations-for-location-based-routing"></a>基于位置的路由的技术注意事项

支持 IPv4 和 IPv6 子网，但是，在检查匹配项时，IPv6 优先。

### <a name="client-support-for-location-based-routing"></a>客户端对Location-Based路由的支持

支持以下 Teams 客户端：
- Windows 和 Mac (Teams 桌面客户端) 
-  (iOS 和 Android) 的 Teams 移动客户端
- Teams IP 电话

不支持 Teams Web 客户端和Skype for Business客户端。

### <a name="capabilities-not-supported-by-location-based-routing"></a>基于位置的路由不支持的功能

Location-Based路由不适用于以下类型的交互。 在以下情况下，当 Teams 终结点与 PSTN 终结点交互时，不会强制执行Location-Based路由： 

- 通过呼叫寄存对 PSTN 呼叫进行呼叫寄存或检索 

- 本地Skype for Business用户或Skype for Business联机用户调用 Teams 用户  

### <a name="location-based-routing-for-conferencing"></a>Location-Based会议路由

不允许在 PSTN 呼叫中启用Location-Based路由的用户使用其他用户或 PSTN 号码开始会议。 允许连接到自动助理或呼叫队列。

如果用户有音频会议许可证，则用户必须与相关用户启动会议，并通过会议网桥调用 PSTN 以启动电话会议。

在没有音频会议许可证的用户发起的电话会议上，如果电话会议中至少有一个或至少已启用路由 Location-Based的用户，则不允许添加 PSTN 参与者。 如果在邀请任何启用了 Location-Based路由的参与者加入呼叫之前，至少有一个 PSTN 参与者是或是此类电话会议的一部分，则无法将启用路由的参与者添加到呼叫中Location-Based。

如果启用了Location-Based路由的用户从未启用Location-Based路由的内部站点加入电话会议，则不会强制执行上述段落中的限制。 

不得使用印度的任何电话设备部署音频会议的网络会议。


### <a name="media-bypass-requirement-for-location-based-routing"></a>Location-Based路由的媒体旁路要求

如果要在印度部署Location-Based路由，则还需要配置媒体旁路。 若要了解详细信息，请参阅 [使用直接路由](direct-routing-plan-media-bypass.md) 和 [本地媒体优化进行直接路由](direct-routing-media-optimization.md)的媒体旁路计划。

### <a name="direct-voice-over-ip-voip"></a>通过 IP 直接语音 (VoIP) 

不能使用任何电话设备在印度部署直接语音 (VoIP) 。


## <a name="related-articles"></a>相关文章

- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [Teams 中云语音功能的网络设置](cloud-voice-network-settings.md)
