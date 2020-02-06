---
title: Skype for Business 服务器中用于会议的基于位置的路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: 在 Skype for business Server Enterprise Voice 中规划会议基于位置的路由（包括咨询呼叫传输）。
ms.openlocfilehash: d03bab835556bf0cea4dffb33bcfbcc48ba7fa42
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802842"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Skype for Business 服务器中用于会议的基于位置的路由

在 Skype for business Server Enterprise Voice 中规划会议基于位置的路由（包括咨询呼叫传输）。

基于位置的路由使您能够根据呼叫中各方的位置限制 VoIP 终结点和 PSTN 终结点之间的通话路由。 用于会议的基于位置的路由使你能够在会议（即会议）上强制实施基于位置的路由规则，以防止 PSTN 免绕过。 应用程序监视活动会议，并根据参与用户的位置强制执行基于位置的路由限制。 另外，针对会议应用程序的基于位置的路由还允许将基于位置的路由限制强制转换为涉及 PSTN 终结点的咨询式转移。

基于位置的路由会议应用程序向 Skype for business 会议提供阻止 PSTN 免绕过的机制。 应用程序监控活动会议，并根据参与的 Skype for Business 用户的位置强制实施基于位置的路由限制。

基于位置的路由会议应用程序确定满足以下条件时是否要在 Skype for Business 会议上强制执行基于位置的路由：

- 会议组织者已启用基于位置的路由。 基于位置的路由限制将仅应用于启用了基于位置的路由的用户组织的会议。

- PSTN 终结点中至少有一名会议参与者。 基于位置的路由限制仅适用于包含 PSTN 终结点的会议。

- 用于将会议桥接到 PSTN 的 PSTN 网关所在的网络站点以及组织者和参与者用于从中连接的网络站点。

会议应用程序基于位置的路由可防止将 Skype for Business 用户和 PSTN 终结点从不同的网络站点加入到同一会议。 如果为基于位置的路由启用了会议组织者，则会议应用程序会强制执行以下限制：

- 可以加入 Skype for Business 会议的终结点取决于已加入会议的终结点，并且此限制将按联接终结点进行调整，并且新终结点加入会议。 如果组织者和参与者从同一网络网站加入 Skype for Business 会议，则 PSTN 终结点、来自同一网络网站的另一位参与者、来自不同网络网站或来自未知网络网站的参与者的另一位参与者允许加入。

- 如果组织者和参与者从不同或未知的网络站点加入会议，则如果 PSTN 呼叫从启用了基于位置的路由的 SIP 中继传入，将不允许 PSTN 终结点加入会议。

- 如果组织者和参与者都从同一网络网站加入会议，并且有参与者加入来自 PSTN 的同一会议，则不允许来自不同网络网站的 Skype for business 终结点加入会议。

下表汇总了这些基于会议位置的路由限制。

| |

|**任意时间点处于会议中的用户**|**允许加入会议的用户**|**不允许加入会议的用户**|
|:-----|:-----|:-----|
|来自单个网络网站的 Skype for business VoIP 客户端用户  <br/> |来自同一网络网站的 Skype for business VoIP 客户端用户  <br/> 来自不同网络网站的 Skype for business VoIP 客户端用户  <br/> 来自未知网络网站的 Skype for business VoIP 客户端用户  <br/> 联合 Skype for Business VoIP 客户端用户  <br/> 从 PSTN 终结点加入的用户  <br/> |无  <br/> |
|来自未知网络网站的 Skype for business VoIP 客户端用户  <br/> |来自任何网站的 Skype for business VoIP 客户端用户  <br/> 来自未知网站的 Skype for business VoIP 客户端用户  <br/> 联合 Skype for Business VoIP 客户端用户  <br/> |通过 PSTN 终结点加入的用户  <br/> |
|来自不同网络网站的 Skype for business VoIP 客户端用户  <br/> |来自任何网络网站的 Skype for business VoIP 客户端用户  <br/> 来自未知网络网站的 Skype for business VoIP 客户端用户  <br/> 联合 Skype for Business VoIP 客户端用户  <br/> |通过 PSTN 终结点加入的用户  <br/> |
|来自单个网络站点和从 PSTN 终结点加入的用户的 Skype for Business VoIP 客户端用户  <br/> |来自同一网络网站的 Skype for business VoIP 客户端用户  <br/> |来自不同网络网站的 Skype for business VoIP 客户端用户  <br/> 来自未知网络网站的 Skype for business VoIP 客户端用户  <br/> 联合 Skype for Business VoIP 客户端用户  <br/> |

以下是适用于会议应用程序的基于位置的路由的其他特性：

- 当用户在给定基于位置的路由限制的情况下，不允许用户加入会议时，对会议的呼叫将被拒绝，并且 Skype for Business 客户端将报告呼叫未完成或已结束。

- 使用基于位置的路由 enforcements 加入会议的 PSTN 终结点不会受到限制，即使终结点通过不支持基于位置的路由的主干进行联接，也不会限制加入会议的状态。

- 通过 SIP 主干连接到中介服务器的 PBX 系统不会向 PSTN 传出呼叫，其 enforcements 与在定义 SIP 主干的同一网络站点中的 Skype for business 用户具有相同的。 例如，PSTN 终结点将能够使用 PBX 用户和 Skype for business 用户加入会议（如果它们位于同一网络网站上）;否则，如果 PBX 用户与 Skype for Business 用户位于不同的网络站点，则不允许 PSTN 终结点加入会议。

> [!NOTE]
> 有了 Skype for Business 累积更新 4，将会观察到下表中的行为：

|**User**|**其他方**|**操作**|**结果**|
|:-----|:-----|:-----|:-----|
|Skype for Business 移动  <br/> |PSTN  <br/> |Skype for Business 移动进行 PSTN 通话。Skype for Business 移动然后将通话升级为会议自动助理 (CAA)。  <br/> |呼叫被阻止，并显示相应的错误消息。  <br/> |
|Skype for Business 移动  <br/> |Skype for Business 客户端或联盟用户  <br/> |客户端或联盟用户位于基于 Skype for business 移动位置的 VoIP 呼叫，并且其中一个参与方升级到 CAA。  <br/> |升级呼叫被阻止，并显示相应的错误消息。  <br/> |

## <a name="consultative-call-transfers"></a>咨询呼叫转接

除了强制执行基于位置的 Skype for Business 会议时，会议应用程序的基于位置的路由会强制执行对 PSTN 终结点的向 PSTN 终结点发送的基于位置的路由限制。 咨询式呼叫转移是在双方将呼叫转移到新用户之间建立的呼叫。 例如，PSTN 终结点呼叫用户 A （Skype for Business 呼叫者）。 用户 A 确定应将 PSTN 用户转发给用户 B （Skype for Business 用户）。 用户 A 将呼叫与 PSTN 用户保持通话状态，然后呼叫用户 B。用户 B 同意与 PSTN 用户交谈。 用户 A 将呼叫转接至用户 B。

**咨询呼叫转接呼叫流**

![会议的基于位置的路由图示](../../media/LocationBasedRoutingForConferencing.jpg)

如果启用了基于位置的路由的用户启动 PSTN 终结点的咨询式呼叫转移（如上图所示），这将创建两个活动呼叫、PSTN 用户和 Skype for business 用户 A 之间的一个通话以及 Skype for business 的另一个通话商业用户 A 和 Skype for business 用户 B。以下行为由适用于会议应用程序的基于位置的路由强制执行：

- 如果对 PSTN 呼叫的 SIP 中继路由有权将 PSTN 呼叫重新路由到使用 Skype for Business 用户 B （即传输目标）的网络站点，则将允许呼叫转移;否则，将阻止咨询呼叫转接。 此授权是基于已转移的参与方的位置执行的，该位置与将活动呼叫路由到 PSTN 终结点的 SIP 干线位于同一网络站点。

- 如果 SIP 中继路由入站 PSTN 呼叫无权将呼叫路由到已转移方（Skype for Business 用户 B）所在的网络站点，或者转移方位于未知的网络站点，则咨询呼叫转移到PSTN 终结点（即呼叫转移目标）将被阻止。

下表介绍了针对咨询式呼叫转移的会议应用程序基于位置的路由应用如何应用基于位置的路由限制。 尽管 PBX 终结点并非直接与某个网络站点关联，但可以为 PBX 连接到的 SIP 中继分配一个网络站点。 因此，PBX 终结点可以间接与网络站点关联。


|**呼叫被转接方的网络站点**|**呼叫转接目标的网络站点**|**行为**|
|:-----|:-----|:-----|
|PSTN 终结点  <br/> |同一网络网站中的 Skype for business 用户（即站点1）  <br/> |咨询转接将被允许  <br/> |
|PSTN 终结点  <br/> |不同网络站点中的 Skype for business 用户（即站点2）  <br/> |咨询转接将被禁止  <br/> |
|PSTN 终结点  <br/> |未知网络网站中的 Skype for business 用户  <br/> |咨询转接将被禁止  <br/> |
|PSTN 终结点  <br/> |联合 Skype for Business 用户  <br/> |咨询转接将被禁止  <br/> |
|PSTN 终结点  <br/> |PBX 终结点位于相同站点（即站点 1）  <br/> |咨询转接将被允许  <br/> |
|PSTN 终结点  <br/> |PBX 终结点位于不同站点（即站点 2）  <br/> |咨询转接将被禁止  <br/> |
|PBX 终结点位于相同站点（即站点 1）  <br/> |PSTN 终结点  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于不同站点（即站点 2）  <br/> |PSTN 终结点  <br/> |咨询转接将被禁止  <br/> |
|PBX 终结点位于任意站点  <br/> |同一网络网站中的 Skype for business 用户（即站点1）  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于任意站点  <br/> |不同网络站点中的 Skype for business 用户（即站点2）  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于任意站点  <br/> |未知网络网站中的 Skype for business 用户  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于任意站点  <br/> |联合 Skype for Business 用户  <br/> |咨询转接将被允许  <br/> |

## <a name="requirements"></a>要求

会议应用程序基于位置的路由需要在拓扑中的所有前端池和标准版服务器上部署 Skype for business 服务器或 Lync Server 2013 累积更新2。 如果你的拓扑中的某些服务器上未安装这些服务器版本，基于位置的路由限制不能完全强加于会议和咨询式呼叫转移。

下表标识了支持基于位置的路由的服务器角色和版本的组合。


|**前端池版本**|**中介服务器版本**|**支持**|
|:-----|:-----|:-----|
|Skype for Business 服务器或 Lync Server 2013 累积更新2  <br/> |Skype for Business 服务器或 Lync Server 2013 累积更新2  <br/> |是  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2013 累积更新 1  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累积更新 1  <br/> |任意  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任意  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任意  <br/> |否  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>针对会议的基于位置的路由的配置

会议应用程序基于位置的路由取决于基于位置的路由的配置。 主要配置如下：

- 加入会议的参与者的位置基于其网络站点进行确定。 必须在 Skype for Business Server 中定义网络网站及其关联的网络子网，才能强制执行基于位置的路由。

- 若要强制使用基于位置的会议路由，必须为 Skype for Business 参与者启用基于位置的路由。

- 若要强制使用基于位置的 PSTN 终结点路由加入会议，则必须为基于位置的路由配置用于连接 PSTN 终结点的 SIP 中继。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>为会议启用基于位置的路由

默认情况下，会议应用程序的基于位置的路由已被禁用。 在启用此应用程序之前，您需要确定要为该应用程序分配的适当优先级。 若要确定此优先级，请在 Skype for Business Server Management Shell 中运行以下 cmdlet：

CsServerApplication-Identity 服务：注册机构：<Pool FQDN>在此 cmdlet 中， \<池 FQDN\>是启用会议应用程序的基于位置的路由的池。

此 cmdlet 将返回由 Skype for Business 服务器托管的应用程序的列表，以及每个应用程序的优先级值。 需要为会议应用程序的基于位置的路由分配一个比 "UdcAgent" 应用程序更大的优先级值，并小于 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 应用程序。 我们建议你为会议应用程序分配基于位置的路由，该优先级值比 "UdcAgent" 应用程序的优先级值高一个点。

例如，如果 "UdcAgent" 应用程序的优先级值为 "2"，则 "DefaultRouting" 应用程序的优先级值为 "8"，"ExumRouting" 应用程序的优先级值为 "9"，"OutboundRouting" 应用程序的优先级值为 "10"，然后你应该为会议应用程序分配基于位置的路由，优先级值为 "3"。 这样做将按以下顺序对应用程序的优先级进行排序：其他应用程序（优先级：0到1），"UdcAgent" （优先级：2），基于位置的路由会议应用程序（优先级：3），其他应用程序（优先级：4到8），"DefaultRouting "（优先级：9），" ExumRouting "（优先级：10）和" OutboundRouting "（优先级：11）。

找到针对会议应用程序基于位置的路由的正确优先级值后，为每个前端池或标准版服务器键入以下 cmdlet，以便为基于位置的路由启用家庭用户：

CsServerApplication-Identity 服务：注册机构：`<Pool FQDN`>/Lbrouting-启用优先级\<的应用\>程序优先级已启用 $true 关键 $true Uri<http://www.microsoft.com/LCS/LBRouting> 

例如：

New-CsServerApplication-Identity 服务:Registrar:LS2013CU2LBRPool/LBRouting-启用优先级3的 $true 关键 $true-Urihttp://www.microsoft.com/LCS/LBRouting 

使用此 cmdlet 后，重启池中的所有前端服务器或启用了基于位置的路由应用程序的标准版服务器。

> [!IMPORTANT]
> 在重新启动适用的池或标准版服务器中的所有前端服务器之前，不会强制执行基于位置的路由 enforcements 到会议或咨询式传输。 如果您设置了在上述 cmdlet 中 **$true**的**关键**，您的 Skype for business 服务器服务将立即重新启动。 如果您不希望这些服务立即重新启动，**请将**CsServerApplication **$false**设置为 "立即更新"，然后在重新启动服务后使用 "**设置**" 更改为 **$true**的**关键**。

一旦已成功启用基于位置的会议应用程序的路由，并且所有适用的服务器都已重新启动，则将监视所有由 Skype for business 用户组织的支持基于位置的路由的所有会议，以防止PSTN 免绕过


