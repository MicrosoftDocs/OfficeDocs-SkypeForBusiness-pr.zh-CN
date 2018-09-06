---
title: 基于位置的业务服务器路由中 Skype 的会议
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: 规划基于位置的业务 Server 企业语音路由的 Skype 中的会议，包括咨询呼叫传输。
ms.openlocfilehash: 38f43ff2cac0f201861c0ee890034ada886e42b2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23248857"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>基于位置的业务服务器路由中 Skype 的会议

规划基于位置的业务 Server 企业语音路由的 Skype 中的会议，包括咨询呼叫传输。

基于位置的路由，使可以限制的 VoIP 终结点和基于位置的双方呼叫中的 PSTN 终结点之间的呼叫路由。 基于位置的路由会议使您能够强制上基于位置的路由规则阻止 PSTN 会议 （即会议） 免费电话绕过。 应用程序监视的活动会议并强制实施基于位置的路由限制基于用户参与的位置。 此外，会议应用程序基于位置的路由可以涉及 PSTN 终结点的咨询转接到的基于位置的路由限制实施。

基于位置的路由会议应用程序提供对业务会议的 PSTN 收费防护一种机制，绕过 Skype。 应用程序监视活动会议并强制实施基于位置的路由限制基于业务用户参与 Skype 的位置。

基于位置的路由会议应用程序确定是否满足以下条件时强制实施业务会议 Skype 上基于位置的路由：

- 为基于位置的路由启用会议组织者。 基于位置的路由限制将只能应用于会议组织的用户启用了基于位置的路由。

- PSTN 终结点中至少有一名会议参与者。 基于位置的路由限制是仅适用于包括 PSTN 终结点的会议。

- 用于将会议桥接到 PSTN 的 PSTN 网关所在的网络站点以及组织者和参与者用于从中连接的网络站点。

基于位置的路由会议应用程序阻止业务用户和从不同的网络站点到同一个会议的 PSTN 终结点的 Skype 参与。 如果会议组织者启用了基于位置的路由，会议应用程序强制实施以下限制：

- 可以加入业务会议 Skype 的终结点取决于已加入会议的终结点和此限制调整联接终结点离开作为新的终结点加入会议。 如果组织者和参与者加入 Skype 业务从同一个网络站点，然后 PSTN 终结点、 从同一个网络站点的其他参与者、 从不同的网络站点的其他参与者或未知的网络站点从参与者的会议允许加入。

- 如果组织者和参与者从不同或未知的网络站点加入会议，则如果 PSTN 呼叫从启用了基于位置的路由的 SIP 中继传入，将不允许 PSTN 终结点加入会议。

- 如果有参与者加入同一个从 PSTN 会议组织者和参与者所有加入会议的同一个网络站点中，不允许从不同的网络站点的业务终结点的 Skype 加入会议。

下表中总结了这些会议基于位置的路由限制。

| |
|**任意时间点处于会议中的用户**|**允许加入会议的用户**|**不允许加入会议的用户**|
|:-----|:-----|:-----|
|Skype 业务 VoIP 客户端用户从一个网络站点  <br/> |Skype 业务 VoIP 客户端用户从同一个网络站点  <br/> Skype 业务 VoIP 客户端用户从不同的网络站点  <br/> Skype 业务 VoIP 客户端用户从未知的网络站点  <br/> 联盟的 Skype 业务 VoIP 客户端用户  <br/> 从 PSTN 终结点加入的用户  <br/> |无  <br/> |
|Skype 业务 VoIP 客户端用户从未知的网络站点  <br/> |Skype 业务 VoIP 客户端用户从任何网站  <br/> 从未知的网站的业务 VoIP 客户端用户 Skype  <br/> 联盟的 Skype 业务 VoIP 客户端用户  <br/> |通过 PSTN 终结点加入的用户  <br/> |
|Skype 业务 VoIP 客户端用户从不同的网络站点  <br/> |Skype 业务 VoIP 客户端用户从任何网络站点  <br/> Skype 业务 VoIP 客户端用户从未知的网络站点  <br/> 联盟的 Skype 业务 VoIP 客户端用户  <br/> |通过 PSTN 终结点加入的用户  <br/> |
|Skype 业务 VoIP 客户端用户从一个网络站点和用户加入从 PSTN 终结点  <br/> |Skype 业务 VoIP 客户端用户从同一个网络站点  <br/> |Skype 业务 VoIP 客户端用户从不同的网络站点  <br/> Skype 业务 VoIP 客户端用户从未知的网络站点  <br/> 联盟的 Skype 业务 VoIP 客户端用户  <br/> |

下面是基于位置的路由会议应用程序的其他特征：

- 不允许用户加入会议给定基于位置的路由限制、 加入会议呼叫将被拒绝以及业务客户端 Skype 将时报告的呼叫未完成或已结束。

- 加入会议使用基于位置的路由执行进行不会受到限制加入会议而不考虑其状态，如果没有为基于位置的路由启用中继通过加入终结点 PSTN 终结点。

- PBX 系统通过不出口到 PSTN 的呼叫的 SIP 中继连接到中介服务器不会具有相同的业务用户作为 Skype 的执行进行位于同一个网络站点定义 SIP 中继的位置。 例如，PSTN 终结点都将能够加入会议与 PBX 用户和业务用户 Skype，如果它们位于相同的网络站点;否则，PSTN 终结点，不将允许如果 PBX 用户是在不同的网络站点比 Skype 业务用户加入会议。

> [!NOTE]
> 有了 Skype for Business 累积更新 4，将会观察到下表中的行为：

|**用户**|**其他方**|**操作**|**结果**|
|:-----|:-----|:-----|:-----|
|Skype for Business 移动  <br/> |PSTN  <br/> |Skype for Business 移动进行 PSTN 通话。Skype for Business 移动然后将通话升级为会议自动助理 (CAA)。  <br/> |呼叫被阻止，并显示相应的错误消息。  <br/> |
|Skype for Business 移动  <br/> |Skype for Business 客户端或联盟用户  <br/> |在客户端或联盟用户位于 Business Mobile Location-Based 路由用户 Skype VoIP 呼叫和知情提升到 CAA。  <br/> |升级呼叫被阻止，并显示相应的错误消息。  <br/> |

## <a name="consultative-call-transfers"></a>咨询呼叫转接

除了业务会议强制实施到 Skype 基于位置的路由，会议应用程序基于位置的路由强制执行基于位置的路由至 PSTN 终结点的出口咨询呼叫传输限制。 咨询呼叫传输是其中的一方将呼叫转接给新用户的双方之间建立的呼叫。 例如，PSTN 终结点呼叫用户 (Skype 业务被叫方的)。 用户 A 确定的 PSTN 用户应转发到用户 B (Skype 业务用户)。 将呼叫置于保持状态的 PSTN 用户和呼叫用户 B 与同意与 PSTN 用户的用户的位置。 用户 A 将暂挂呼叫转移到用户 b。

**咨询呼叫转接呼叫流**

![会议的基于位置的路由图示](../../media/LocationBasedRoutingForConferencing.jpg)

如果用户启用了基于位置的路由启动咨询呼叫传输 PSTN 终结点 （如上图所示），这将创建两个活动通话，一次调用之间的 PSTN 用户和 Skype 业务用户 A，，之间的 Skype 另一个由会议应用程序基于位置的路由强制执行业务用户 A 和 Skype 的业务用户 B 以下行为：

- 如果 SIP 中继路由 PSTN 呼叫有权重新路由到网络站点其中业务用户 B （即传输目标） 的 Skype 是位于、，则将允许转接呼叫; PSTN 呼叫否则，将阻止咨询呼叫转接。 此授权为执行基于是活动呼叫路由至 PSTN 终结点的 SIP 中继的同一网络站点中的已转移的方的位置。

- 如果将入站的 PSTN 呼叫路由的 SIP 中继未被授权呼叫路由到网络站点传输的方 (Skype 业务用户 B) 位于或转移的方位于未知的网络站点的位置，咨询呼叫转接到PSTN 终结点 （即呼叫转移目标） 将被阻止。

下表介绍基于位置的路由限制所应用的咨询呼叫转移的会议应用程序基于位置的路由。 尽管 PBX 终结点并非直接与某个网络站点关联，但可以为 PBX 连接到的 SIP 中继分配一个网络站点。 因此，PBX 终结点可以间接与网络站点关联。


|**呼叫被转接方的网络站点**|**呼叫转接目标的网络站点**|**行为**|
|:-----|:-----|:-----|
|PSTN 终结点  <br/> |同一个网络站点 （即网站 1） 中的业务用户的 Skype  <br/> |咨询转接将被允许  <br/> |
|PSTN 终结点  <br/> |不同的网络站点 （即站点 2） 中的业务用户的 Skype  <br/> |咨询转接将被禁止  <br/> |
|PSTN 终结点  <br/> |未知的网络站点中的业务用户的 Skype  <br/> |咨询转接将被禁止  <br/> |
|PSTN 终结点  <br/> |业务用户的联盟的 Skype  <br/> |咨询转接将被禁止  <br/> |
|PSTN 终结点  <br/> |PBX 终结点位于相同站点（即站点 1）  <br/> |咨询转接将被允许  <br/> |
|PSTN 终结点  <br/> |PBX 终结点位于不同站点（即站点 2）  <br/> |咨询转接将被禁止  <br/> |
|PBX 终结点位于相同站点（即站点 1）  <br/> |PSTN 终结点  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于不同站点（即站点 2）  <br/> |PSTN 终结点  <br/> |咨询转接将被禁止  <br/> |
|PBX 终结点位于任意站点  <br/> |同一个网络站点 （即网站 1） 中的业务用户的 Skype  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于任意站点  <br/> |不同的网络站点 （即站点 2） 中的业务用户的 Skype  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于任意站点  <br/> |未知的网络站点中的业务用户的 Skype  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于任意站点  <br/> |业务用户的联盟的 Skype  <br/> |咨询转接将被允许  <br/> |

## <a name="requirements"></a>要求

基于位置的应用程序需要 Skype 业务服务器或 Lync Server 2013 累积更新 2年部署在所有前端池和 Standard Edition 拓扑中的服务器上的会议的路由。 如果您的拓扑中的某些服务器上未安装这些服务器版本，基于位置的路由限制不能完全在会议上强制并咨询呼叫传输。

下表标识服务器角色和支持基于位置的路由的版本的组合。


|**前端池版本**|**中介服务器版本**|**支持**|
|:-----|:-----|:-----|
|Skype 业务服务器或 Lync Server 2013 累积更新 2  <br/> |Skype 业务服务器或 Lync Server 2013 累积更新 2  <br/> |是  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2013 累积更新 1  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累积更新 1  <br/> |任意  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任意  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任意  <br/> |否  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>基于位置的路由会议的配置

基于位置的路由会议应用程序依赖的基于位置的路由配置。 主要配置如下：

- 加入会议的参与者的位置基于其网络站点进行确定。 网络站点和其关联的网络子网必须以强制实施基于位置的路由定义 Skype 业务服务器中。

- 强制实施会议的基于位置的路由，Skype 业务参与者必须启用基于位置的路由。

- 若要强制加入会议的 PSTN 终结点的基于位置的路由，必须为基于位置的路由配置用来连接的 PSTN 终结点的 SIP 中继。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>启用的会议中基于位置的路由

基于位置的路由，默认情况下禁用应用程序的会议。 在启用此应用程序之前，您需要确定要为该应用程序分配的适当优先级。 若要确定此优先级，Skype 中为 Business Server 命令行管理程序运行以下 cmdlet:

Get-csserverapplication-Identity Service: Registrar:<Pool FQDN>中此 cmdlet，\<池 FQDN\>是在其中启用会议应用程序基于位置的路由池。

此 cmdlet 将返回由 Skype 承载业务服务器和优先级值，其中每台应用程序的列表。 会议应用程序基于位置的路由需要分配优先级值大于"UdcAgent"应用程序和小于"DefaultRouting"、"ExumRouting"和"OutboundRouting"应用程序。 我们建议您在是一个点更高的优先级值比"UdcAgent"应用程序的优先级值分配的会议应用程序基于位置的路由。

如果"UdcAgent"应用程序具有"2"的优先级值，例如，"DefaultRouting"应用程序具有优先级值"8"、"ExumRouting"应用程序的优先级值为"9"和"OutboundRouting"应用程序具有的优先级值是"10"，然后您应分配的会议应用程序基于位置的路由优先级值为"3"。 这样可以按以下顺序将应用程序的优先级： 其他应用程序 (优先级： 0 到 1)，"UdcAgent"(优先级： 2)，基于位置的路由会议应用程序 (优先级： 3)，其他应用程序 (优先级： 4 至 8)，"DefaultRouting"(优先级： 9)，"ExumRouting"(优先级： 10) 和"OutboundRouting"(优先级： 11)。

您的会议应用程序基于位置的路由找到正确的优先级值后，键入以下 cmdlet 为家庭用户启用基于位置的路由每个前端池或 Standard Edition Server:

New-csserverapplication-Identity Service: Registrar:<Pool FQDN>/LBRouting-优先级<Application Priority>-启用 $true-关键 $true Urihttps://www.microsoft.com/LCS/LBRoutingFor示例：

New-csserverapplication-Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-优先级 3-启用的 $true-关键 $true Urihttps://www.microsoft.com/LCS/LBRoutingAfter使用此 cmdlet，重新启动所有前端服务器池或 Standard Edition Server 位置已启用的会议应用程序的基于位置的路由。

> [!IMPORTANT]
> 基于位置的路由执行进行到会议或咨询转接不强制实现直到所有前端服务器中适用的池或 Standard Edition Server 随即会重新启动。 如果您设置 **-关键**到上述 cmdlet 中 **$true** ，您的业务服务器服务的 Skype 将立即重新启动。 如果您不希望立即重新启动这些服务，设置 **-关键** **$false**为，然后使用**集 CsServerApplication**更改到 **-关键**到更高版本、 **$true**已重新启动服务后。

已成功启用会议应用程序基于位置的路由并适用的所有服务器已重新都启动后，将监视启用基于位置的路由的业务用户的组织的 Skype 的所有会议以防止绕过 PSTN 收费电话


