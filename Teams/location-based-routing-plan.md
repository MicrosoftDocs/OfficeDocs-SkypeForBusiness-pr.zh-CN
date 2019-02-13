---
title: 为直接路由计划基于位置的路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.service: msteams
ms.reviewer: roykuntz
search.appverid: MET150
description: 了解如何规划基于位置的路由直接路由。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8faf0f70b509a851b8365bea5ce4a69a57f198d1
ms.sourcegitcommit: 09c2094104ee055cb1cb047a5fab8f9fd02b123e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "29967453"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>为直接路由计划基于位置的路由

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>基于位置的路由的概述

在某些国家/地区和区域中，是非法的绕过的公共公用电话交换网 (PSTN) 提供程序，以降低长途呼叫成本。 本文介绍如何使用基于位置的路由限制收费电话的 Microsoft 团队用户根据其地理位置的绕过。 本文仅适用于电话系统直接路由。

此处，您将获取基于位置的路由和指南可帮助您为其规划的概述。 当您准备好应用并启用基于位置的路由时，请参阅：
- [部署基于位置的路由的网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)

基于位置的路由是允许您限制的入站或出站 PSTN 呼叫时，基于策略和用户的地理位置的收费电话绕过功能。 

如果团队用户启用了基于位置的路由，适用于以下情况：
- 若要使出站 PSTN 呼叫，必须满足下列选项之一：
    - 用户的终结点位于启用相应启用基于位置的路由的网关通过基于位置的路由和呼叫的出口网络站点。 
    - 用户的终结点位于未启用基于位置的路由，并调用出口通过未启用基于位置的路由的网关的网络站点。

    任何其他方案中不允许出站呼叫。

- 若要接收的入站的 PSTN 呼叫，用户应答终结点必须位于同一个网络站点其中通过启用基于位置的路由的网关呼叫 ingresses。 在任何其他方案中，例如，如果用户漫游，呼叫不允许和路由到用户的呼叫转接设置 （通常语音邮件）。
- PSTN 呼叫转接到另一个团队用户，目标用户的终结点必须位于中启动转接的用户的同一网络站点。 传输不允许任何其他方案中。 
- 要转接到 PSTN 的另一小组用户，必须通过启用的基于位置的路由网关位于同一个网络站点初始的呼叫者转接呼叫。 传输不允许任何其他方案中。

基于位置的路由使用 Skype 业务服务器使用的同一网络区域、 网站和子网定义。 收费绕过位置限制后，管理员将每个 IP 子网并与网络站点的位置的每个 PSTN 网关相关联。 用户的位置取决于用户的工作组终结点时的 PSTN 呼叫连接到的 IP 子网。 用户可能拥有多个团队客户端位于不同网站，在这种情况下基于位置的路由强制执行每个客户端的单独路由根据其终结点的位置。 

若要获取熟悉一些使用本文中的网络术语，请参阅[基于位置的路由术语](location-based-routing-terminology.md)。

## <a name="apply-location-based-routing"></a>应用基于位置的路由

您必须向用户、 网络站点和 PSTN 网关应用基于位置的路由。  

### <a name="apply-location-based-routing-at-the-user-location"></a>应用的用户位置基于位置的路由

如前所述，基于位置的路由仅适用于直接路由的设置的用户。 用户调用规划为设置不适用于基于位置的路由。 如果在收费绕过限制，用于控制在其中他们可以发起和接收 PSTN 呼叫和可用的 PSTN 网关的条件下，用户必须启用基于位置的路由。 时为基于位置的路由启用的用户位于网站的已启用基于位置的路由，用户必须进行呼叫通过连接到的网站启用基于位置的路由网关。 

基于位置的路由的工作方式是确定用户的当前位置根据用户的工作组终结点的 IP 地址和相应应用规则。 可以按以下方式分类为基于位置的路由启用的用户的位置： 
- **用户位于同一个基于位置的路由启用的网站关联到 PSTN 网关分配其 DID 位置。**<br>在此方案中，用户位于启用基于位置的路由和用户的外线直拨拨号 (DID) 号码位于相同的网络站点的 PSTN 网关终止已知的网络站点。 例如，用户是其办公室。 
- **用户位于不同基于位置的路由启用关联的网站不到 PSTN 网关分配其 DID 位置。**<br>在此方案中，用户位于启用基于位置的路由，已知的网络站点，该网站未与 PSTN 网关相关联的分配用户的 DID 号码的位置。 例如，用户转移到另一个 office。  
- **用户位于未启用基于位置的路由的内部站点。** <br>在此方案中，用户位于已知的内部网络站点的未启用基于位置的路由。 
- **用户位于未知的网站。** 
    - 用户位于内部未定义为网络站点的内部网络。 
    - 用户位于内部网络之外。 例如，用户属于在家中或在咖啡馆 Internet。 

### <a name="apply-location-based-routing-at-the-network-site"></a>应用基于位置的网络站点的路由 
基于位置的路由，可帮助确定路由基于位置的路由启用用户漫游时的网关必须为启用网络站点。 如果启用了基于位置的路由用户漫游到启用基于位置的路由的网站，仅为适应该站点的基于位置的路由启用的 PSTN 网关才能可用于出站呼叫。 为基于位置的路由启用的用户漫游到没有为基于位置的路由启用的网站，如果没有为基于位置的路由启用任何网关可用于出站呼叫。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>应用在 PSTN 网关基于位置的路由 

网关相关联以确定其中的基于位置的路由启用的用户可以在发起或接收的 PSTN 呼叫时所在的网站。 网关必须为启用基于位置的路由，以确保它是在收费绕过限制下，并不能由用户未启用基于位置的路由。 同一个网关可能与多个站点关联，可配置为启用基于位置的路由或未启用基于位置的路由，具体取决于网站。 

## <a name="scenarios-for-location-based-routing"></a>基于位置的路由的方案

本节介绍了使用基于位置的路由限制收费绕过的不同方案，并比较的未启用基于位置的路由与为基于位置的路由启用的用户的用户路由呼叫的方式。

- [团队用户发起出站 pstn 呼叫](#teams-user-places-an-outbound-call-to-the-pstn)
- [团队用户收到来自 PSTN 的入站的呼叫](#teams-user-receives-an-inbound-call-from-the-pstn)
- [团队用户传输或转发到另一个团队用户的呼叫](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [团队用户传输或转发到 PSTN 终结点的呼叫](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同时响铃](#simultaneous-ringing)
- [委派](#delegation)

下图显示了由每个方案中基于位置的路由启用的限制。 用户、 网络站点和启用基于位置的路由的网关有边框。 使用图作为指南可帮助您了解每个方案中如何基于位置的路由工作原理。  

![图表显示基于位置的路由方案](media/lbr-direct-routing.png "图表显示基于位置的路由方案")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>团队用户发起出站 pstn 呼叫

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用基于位置的路由

基于位置的路由未启用的用户可以在没有为其分配的语音路由策略通过基于位置的路由启用的任何网站上使用任何网关的出站呼叫。 但是，如果网关启用了基于位置的路由，用户不能通过网关的出站呼叫即使它已分配给语音路由策略。 如果用户漫游的网站上启用基于位置的路由，他们可以仅发起通过基于位置的路由未启用其正常路由网关的呼叫。
 
#### <a name="user-enabled-for-location-based-routing"></a>为基于位置的路由启用的用户
相比之下，用于基于位置的路由启用的用户的出站呼叫路由受影响用户的终结点的网络位置。 下表显示了如何基于位置的路由影响的 User1，具体取决于 User1 的位置的出站呼叫路由。 

|User1 终结点位置  |为 User1 的出站呼叫路由  |
|---------|---------|
|分配用户的 DID 位置，同一站点的站点启用基于位置的路由 (Site1)      |呼叫路由通过在 Site1，基于用户的语音路由策略启用基于位置的路由 (GW1) 的网关         |
|与其中分配用户的 DID，网站启用基于位置的路由 (Site2) 不同站点    |通过在漫游 Site2 的基于位置的路由 (GW2) 启用的网关路由的呼叫基于用户的语音路由策略        |
|与其中分配用户的 DID，未启用基于位置的路由 (Site3) 的网站不同的站点  |呼叫路由通过未启用了未启用基于位置的路由 (GW3)，基于用户的语音路由策略的站点上基于位置的路由的网关       |
|未知的内部网络 (Location4)    |  PSTN 呼叫不允许       |
|未知的外部网络 (Location5)    | PSTN 呼叫不允许        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>团队用户收到来自 PSTN 的入站的呼叫

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用基于位置的路由

基于位置的路由未启用的用户可以从未启用从中其分配给未数字 ingresses 的基于位置的路由的网关接收的入站的呼叫。 如果到没有为基于位置的路由启用网站漫游用户，他们仍可以接收通过其正常的 PSTN 网关的呼叫。
  
#### <a name="user-enabled-for-location-based-routing"></a>为基于位置的路由启用的用户

相比之下，基于位置的路由已启用的用户可以仅接收来自这些文件位于同一网站时，将其 DID 分配给 PSTN 网关的入站的调用。 下表显示当 User1 移到不同的网络位置 User1 接收入站的呼叫的方式。 如果呼叫未路由到用户的终结点，它转到用户的呼叫转移设置，如果配置了这些设置。 通常，这是语音邮件。  

|User1 终结点位置  |为 User1 的入站呼叫的路由  |
|---------|---------|
|同一站点其中分配用户的 DID，网站启用基于位置的路由 (Site1)   | 呼叫路由至 Site1 中的 User1 的终结点        |
|与其中分配用户的 DID，网站启用基于位置的路由 (Site2) 不同站点    | 呼叫未传送给 Site2 中的终结点        |
|与其中分配用户的 DID，未启用基于位置的路由 (Site3) 的网站不同的站点    | 呼叫未传送给 Site3 中的终结点        |
|未知的内部网络 (Location4)   | 呼叫未传送给 Location4 中的终结点        |
|未知的外部网络 (Location5)     | 呼叫未传送给 Location5 中的终结点        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>团队用户传输或转发到另一个团队用户的呼叫

当涉及 PSTN 终结点时，基于位置的路由分析是否为基于位置的路由启用了一个或两个用户，并确定是否应传输或根据两个终结点位置转接呼叫。 
 
转接呼叫，要求发起用户选取建立呼叫时呼叫转接不需要初始接听电话。 这意味着可以将呼叫转接即使 User1 不在一个位置来接收入站呼叫 （请参阅[团队用户收到来自 PSTN 的入站的呼叫](#teams-user-receives-an-inbound-call-from-the-pstn)节中的表） 和无法转接呼叫，如果 User1 无法接收入站的呼叫。 

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用基于位置的路由

基于位置的路由未启用的用户可以传输或向其他用户未启用基于位置的路由的正向 PSTN 呼叫。 用户通常不能传输或转接 PSTN 呼叫，因为基于位置的路由启用用户为基于位置的路由启用的用户通常只允许将共同位于基于位置的路由启用了 PSTN 的网关呼叫。 基于位置的路由启用位置的网站的没有为基于位置的路由启用的用户之间漫游时除外。 在此方案中，允许将呼叫转接。  

同样，基于位置的路由未启用的用户可以仅接收复制或转发来自另一个用户未启用基于位置的路由 PSTN 呼叫。 

#### <a name="user-enabled-for-location-based-routing"></a>为基于位置的路由启用的用户

通常，转接和转移从启用基于位置的路由的网关的入站的 PSTN 呼叫，才允许使用目标用户启用基于位置的路由，并位于同一站点。 否则，不允许转接和转移呼叫。 

下表显示是否允许呼叫转接和呼叫转移，具体取决于目标用户的位置。 在此表中，User1，位于 Site1，启动传输或转接到其他团队用户，用户还启用了基于位置的路由，并且用户位于不同的位置。  

|目标用户终结点位置|User1 启动转接呼叫 |User1 启动转接呼叫|
|---------|---------|---------|
|为发起者 (User2) 的同一个网络站点|允许|允许|
|不同的网络站点，网站启用基于位置的路由 (User3)|不允许|不允许|
|不同的网络站点，未启用基于位置的路由 (User4) 的网站|不允许|不允许|
|未知的内部网络 (User5)| 不允许|不允许|
|未知的外部网络 (User6)| 不允许|不允许|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>团队用户传输或转发到 PSTN 终结点的呼叫

#### <a name="user-not-enabled-for-location-based-routing"></a>用户未启用基于位置的路由

- 允许传输与 PSTN 呼叫转移到其他 PSTN 号码。 
- 转接和转移到 PSTN 的入站的 VOIP 呼叫必须遵守呼叫者的收费电话绕过限制。 
    - 如果呼叫者未启用基于位置的路由，它们可以转接到没有为基于位置的路由启用任何 PSTN 网关。
    - 如果呼叫者启用了基于位置的路由，他们只能将转移到启用的基于位置的路由网关位于同一个网络站点。 

#### <a name="user-enabled-for-location-based-routing"></a>为基于位置的路由启用的用户

- 转接和转移入站 PSTN 呼叫到其他 PSTN 号码必须路由出入站的呼叫到达同一个基于位置的路由启用网关。 
- 转接和转移入站的 VOIP 到 PSTN 的呼叫必须接受两个呼叫者呼叫的用户的收费电话绕过的限制。 
    - 如果呼叫者未启用基于位置的路由，它们可以转接到没有为基于位置的路由启用任何 PSTN 网关。
    - 如果呼叫者启用了基于位置的路由，它们是只能将转移到启用的基于位置的路由网关位于同一个网络站点。
 
下表显示了如何基于位置的路由影响到不同的位置传输或将呼叫转接至 PSTN 终结点中的用户在 Site1 User1 的 VOIP 呼叫的路由。  

|用户启动呼叫转接或转发  |转接到 PSTN  |转接到 PSTN  |
|---------|---------|---------|
|同一个网络站点，网站启用基于位置的路由 (User2)   |呼叫转接只能通过基于位置的路由路由启用 Gateway1 在 Site1，基于 User2 的语音路由策略         |仅通过基于位置的路由路由的呼叫转接可以启用 Gateway1 在 Site1，基于 User2 的语音路由策略         |
|不同的网络站点，网站启用基于位置的路由 (User3)    |呼叫转接只能通过基于位置的路由路由启用 Gateway1 在 Site1，基于 User3 的语音路由策略         |转接呼叫可以仅通过基于位置的路由进行路由启用 Gateway1 在 Site1，基于 User3 的语音路由策略         |
|不同的网络站点，未启用基于位置的路由 (User4) 的网站    |呼叫转接只能通过基于位置的路由路由启用 Gateway1 在 Site1，基于 User4 的语音路由策略         |转接呼叫可以仅通过基于位置的路由进行路由启用 Gateway1 在 Site1，基于 User4 的语音路由策略         |
|未知的内部网络 (User5)     |呼叫转接只能通过基于位置的路由路由启用 Gateway1 在 Site1，基于 User5 的语音路由策略         |转接呼叫可以仅通过基于位置的路由进行路由启用 Gateway1 在 Site1，基于 User5 的语音路由策略         |
|未知的外部网络 (User6)   |呼叫转接只能通过基于位置的路由路由启用 Gateway1 在 Site1，基于 User6 的语音路由策略        |转接呼叫可以仅通过基于位置的路由进行路由启用 Gateway1 在 Site1，基于 User6 的语音路由策略         |

### <a name="simultaneous-ringing"></a>同时响铃

当为基于位置的路由启用的用户接收呼叫并已启用同时响铃时，基于位置的路由分析呼叫方的位置，以确定是否应将呼叫路由呼叫方的终结点。 呼叫转接和转发，同时响铃遵循相同的基于位置的规则。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>同时拨打另一个团队用户

下表显示了基于位置的路由是否允许同时响铃到不同的用户的入站 PSTN 呼叫 user1。

|目标用户终结点位置|同时响铃  |
|---------|---------|
|为发起者 (User2) 的同一个网络站点   |允许         |
|为基于位置的路由 (User3) 启用的不同漫游的网络站点   |不允许         |
|基于位置的路由 (User4) 未启用漫游的网络站点   |不允许        |
|未知的内部网络 (User5)    | 不允许        |
|未知的外部网络 (User6)    |不允许        |
|目标用户是 PSTN 号码    |呼叫可以仅通过基于位置的路由路由启用 Gateway1 在 Site1，基于 User1 的语音路由策略      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>同时响铃到 PSTN 的终结点

下表显示了基于位置的路由行为来自 User1 在 Site1 分布到不同的位置中的用户的设置为 PSTN 号码的同时响铃的入站 VOIP 呼叫。 

|呼叫的用户终结点位置  |同时拨打目标是 PSTN 终结点 |
|---------|---------|
|同一个网络站点，网站启用基于位置的路由 (User2)    |呼叫可以仅为路由通过在 Site1，基于 User2 的语音路由策略基于位置的路由 Gateway1       |
|为基于位置的路由 (User3) 启用的不同的网络站点    |仅可以通过在 Site1，基于 User3 的语音路由策略基于位置的路由 Gateway1 路由呼叫        |
|基于位置的路由 (User4) 未启用的不同的网络站点    |仅可以通过在 Site1，基于 User4 的语音路由策略基于位置的路由 Gateway1 路由呼叫         |
|未知的内部网络 (User5)    |仅可以通过在 Site1，基于 User5 的语音路由策略基于位置的路由 Gateway1 路由呼叫         |
|未知的外部网络 (User6)   |仅可以通过在 Site1，基于 User6 的语音路由策略基于位置的路由 Gateway1 路由呼叫         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>入站呼叫通过语音应用程序 （自动助理或呼叫的队列）

允许来自启用的基于位置的路由网关的入站的 PSTN 呼叫连接到自动助理或呼叫的队列。 基于位置的路由已启用的用户可以仅入站的呼叫转移从这些应用程序时会收到这些文件位于同一站点入站的 PSTN 呼叫不是来自。 
 
呼叫转接和同时响铃给用户和 PSTN 被允许语音应用程序传输。 完成对目标调用受制于前面列出的相同基于位置的路由规则。  
 
此外允许转接到语音邮件。  

### <a name="delegation"></a>委派

团队用户可以选择代理人可以发起和接收代表其拨打的呼叫。 团队中的委派功能受到了基于位置的路由，如下所示： 
- 为从基于位置的路由启用代理人代表 delegator 的出站呼叫，应该应用相同的规则。 呼叫路由基于代理的呼叫授权策略、 语音路由策略和位置。 有关详细信息，请参阅[团队用户发起出站 pstn 呼叫](#teams-user-places-an-outbound-call-to-the-pstn)。 
- 到 delegator 的入站 PSTN 呼叫，相同的基于位置的路由规则适用于呼叫转接或同时拨打给其他用户也适用于代理人。 有关详细信息，请参阅[团队用户传输或转发到另一个团队用户的呼叫](#teams-user-transfers-or-forwards-call-to-another-teams-user)、[团队用户传输或转发到 PSTN 终结点的呼叫](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)，和[同时响铃](#simultaneous-ringing)。 时代理人将 PSTN 终结点设置为同时拨打目标，语音路由策略的代理人将用于将呼叫路由到 PSTN。 
- 为委派，建议在相同的网络站点位于 delegator 和关联的委托。 

## <a name="other-planning-considerations"></a>其他规划考虑事项

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>从内部部署基于位置的路由部署的更改

网络站点语音路由策略已不再使用。 相反，我们使用用户的语音路由策略。 这意味着，以允许用户漫游到其他网站，语音路由策略必须包含漫游网站的网关。 

### <a name="technical-considerations-for-location-based-routing"></a>基于位置的路由的技术注意事项

支持 IPv4 和 IPv6 的子网，但是，IPv6 优先时检查的匹配项。 IPv6 支持当前正在进行，可通过常规可用性 (GA) 的基于位置的路由。 

### <a name="client-support-for-location-based-routing"></a>基于位置的路由的客户端支持

支持以下团队客户端：
- 团队桌面客户端 （Windows 和 Mac）
- 团队移动客户端 （iOS 和 Android）
- 团队 IP 电话

不支持的工作组 web 客户端和 Skype 业务客户端。

### <a name="capabilities-not-supported-by-location-based-routing"></a>基于位置的路由不支持的功能

基于位置的路由不适用于以下类型的交互。 当团队终结点交互 PSTN 终结点在下列情况下，不强制执行基于位置的路由： 
- 通过呼叫寄存对 PSTN 呼叫进行呼叫寄存或检索 
- 业务用户的本地 Skype 或业务联机用户 Skype 调用团队用户  

### <a name="location-based-routing-for-conferencing"></a>基于位置的路由会议

不允许在 PSTN 呼叫基于位置的路由启用用户开始会议与另一个用户或 PSTN 号码。 允许连接到自动助理或呼叫的队列。 如果用户具有会议许可证，用户必须与相关的用户开始会议并呼叫启动电话会议的会议桥通过 PSTN。  

## <a name="next-steps"></a>后续步骤
转到[基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)。

### <a name="related-topics"></a>相关主题
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [基于位置的路由术语](location-based-routing-terminology.md)