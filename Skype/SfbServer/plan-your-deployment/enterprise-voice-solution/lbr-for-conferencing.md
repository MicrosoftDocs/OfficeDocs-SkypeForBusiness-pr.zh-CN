---
title: Skype for Business Server 中的会议的基于位置的路由
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
description: 为 Skype for business Server Enterprise Voice 中的会议规划基于位置的路由，包括咨询呼叫转移。
ms.openlocfilehash: decfe8117b3b47c5de4db8a7d0963eca587d0da1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42130175"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Skype for Business Server 中的会议的基于位置的路由

为 Skype for business Server Enterprise Voice 中的会议规划基于位置的路由，包括咨询呼叫转移。

基于位置的路由使您可以根据呼叫中各方的位置限制 VoIP 终结点和 PSTN 终结点之间的呼叫路由。 通过基于位置的会议路由，可以在会议（即会议）上强制实施基于位置的路由规则，以防止 PSTN 收费旁路。 应用程序监视活动会议，并根据参与用户的位置强制实施基于位置的路由限制。 会议应用程序的基于位置的路由此外，还允许将基于位置的路由限制强制转换为涉及 PSTN 终结点的咨询转移。

基于位置的路由会议应用程序向 Skype for business 会议提供了阻止 PSTN 收费旁路的机制。 该应用程序监视活动会议，并根据参加会议的 Skype for Business 用户的位置强制实施基于位置的路由限制。

如果满足以下条件，则基于位置的路由会议应用程序将确定是否在 Skype for Business 会议上强制实施基于位置的路由：

- 会议组织者启用了基于位置的路由。 基于位置的路由限制将仅应用于由启用了基于位置的路由的用户组织的会议。

- 至少有一个会议参与者是 PSTN 终结点。 基于位置的路由限制仅适用于包含 PSTN 终结点的会议。

- PSTN 网关用于将会议桥接到 PSTN 的网络站点，以及组织者和参与者从中连接的网络站点。

会议应用程序的基于位置的路由可阻止将 Skype for Business 用户和 PSTN 终结点从不同的网络站点加入同一会议。 如果为会议的组织者启用了基于位置的路由，会议应用程序将强制实施以下限制：

- 可以加入 Skype for Business 会议的终结点取决于已加入会议的终结点，并且此限制将作为联接的终结点保留，并将新的终结点加入会议进行调整。 如果组织者和参与者从同一个网络站点加入 Skype for Business 会议，则 PSTN 终结点、同一网络站点中的另一个参与者、来自不同网络站点的其他参与者或来自未知网络站点的参与者允许加入。

- 如果组织者和参与者从不同或未知网络站点加入会议，则不允许 PSTN 终结点加入会议（如果 PSTN 呼叫 ingresses 来自 SIP 中继启用基于位置的路由）。

- 如果组织者和参与者都从同一个网络站点加入会议，并且有参与者加入来自 PSTN 的同一会议，则不允许来自不同网络站点的 Skype for Business 终结点加入会议。

下表汇总了这些基于会议位置的路由限制。

| |

|**在任意给定时刻会议中的用户**|**允许加入会议的用户**|**不允许用户加入会议**|
|:-----|:-----|:-----|
|来自单个网络站点的 Skype for Business VoIP 客户端用户  <br/> |来自相同网络站点的 Skype for Business VoIP 客户端用户  <br/> 来自不同网络站点的 Skype for Business VoIP 客户端用户  <br/> 来自未知网络站点的 Skype for Business VoIP 客户端用户  <br/> 联合 Skype for Business VoIP 客户端用户  <br/> 从 PSTN 终结点加入的用户  <br/> |无  <br/> |
|来自未知网络站点的 Skype for Business VoIP 客户端用户  <br/> |来自任何网站的 Skype for Business VoIP 客户端用户  <br/> 来自未知网站的 Skype for business VoIP 客户端用户  <br/> 联合 Skype for Business VoIP 客户端用户  <br/> |通过 PSTN 终结点加入的用户  <br/> |
|来自不同网络站点的 Skype for Business VoIP 客户端用户  <br/> |来自任何网络站点的 Skype for Business VoIP 客户端用户  <br/> 来自未知网络站点的 Skype for Business VoIP 客户端用户  <br/> 联合 Skype for Business VoIP 客户端用户  <br/> |通过 PSTN 终结点加入的用户  <br/> |
|来自单个网络站点和从 PSTN 终结点加入的用户的 Skype for Business VoIP 客户端用户  <br/> |来自相同网络站点的 Skype for Business VoIP 客户端用户  <br/> |来自不同网络站点的 Skype for Business VoIP 客户端用户  <br/> 来自未知网络站点的 Skype for Business VoIP 客户端用户  <br/> 联合 Skype for Business VoIP 客户端用户  <br/> |

以下是会议应用程序的基于位置的路由的其他特征：

- 如果不允许用户加入会议给定的基于位置的路由限制，则对会议的呼叫将被拒绝，并且 Skype for Business 客户端将报告呼叫未完成或已结束。

- 使用基于位置的路由之后加入会议的 PSTN 终结点如果终结点通过未启用基于位置的路由的中继进行联接，则不会限制加入会议的会议。

- 通过 SIP 中继连接到中介服务器的 PBX 系统不会对 PSTN 进行传出呼叫，与在定义 SIP 中继的同一网络站点中的 Skype for Business 用户具有相同的之后。 例如，PSTN 终结点将能够加入具有 PBX 用户和 Skype for business 用户（如果它们位于同一网络站点中）的会议;否则，如果 PBX 用户位于与 Skype for Business 用户不同的网络站点中，则不允许 PSTN 终结点加入会议。

> [!NOTE]
> 使用 Skype for Business 累积更新4，应遵循下表中的行为：

|**用户**|**其他方**|**操作**|**结果**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile 位于 PSTN 呼叫中。 Skype for Business 移动然后将呼叫升级到会议自动助理（CAA）。  <br/> |呼叫被阻止，并提供相应的错误消息。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business 客户端或联合用户  <br/> |客户端或联盟用户位于基于 Skype for Business 移动位置的 VoIP 呼叫，并且每一方都要升级到 CAA。  <br/> |升级呼叫被阻止，并提供相应的错误消息。  <br/> |

## <a name="consultative-call-transfers"></a>咨询呼叫转移

除了强制对 Skype for business 会议进行基于位置的路由，会议应用程序的基于位置的路由在咨询呼叫转移时强制实施基于位置的路由限制，以向 PSTN 终结点进行出口。 咨询呼叫转接是在双方将呼叫转移到新用户之间建立的呼叫。 例如，PSTN 终结点呼叫用户 A （Skype for Business 呼叫者）。 用户 A 确定 PSTN 用户应转发到用户 B （Skype for Business 用户）。 用户 A 将呼叫与 PSTN 用户置于保留状态，并呼叫用户 B。用户 B 同意与 PSTN 用户对话。 用户 A 将呼叫（保留）转移到用户 B。

**咨询呼叫转接呼叫流**

![会议图的基于位置的路由](../../media/LocationBasedRoutingForConferencing.jpg)

当启用基于位置的路由的用户启动 PSTN 终结点的咨询呼叫转移（如上图所示）时，这将创建两个活动呼叫、PSTN 用户和 Skype for business 用户 A 之间的一次呼叫以及 Skype for business 之间的另一个呼叫商业用户 A 和 Skype for Business 用户 B。以下行为由会议应用程序的基于位置的路由强制实施：

- 如果对 PSTN 呼叫的 SIP 中继路由有权将 PSTN 呼叫重新路由到网络站点（其中 Skype for Business 用户 B （即传输目标）所在的网络站点），则将允许呼叫转移;否则，将阻止咨询呼叫转移。 此授权根据被转移方在与将活动呼叫路由到 PSTN 终结点的 SIP 中继位于同一网络站点中的位置进行。

- 如果 SIP 中继路由未授权入站 PSTN 呼叫将呼叫路由到传输方（Skype for Business 用户 B）所在的网络站点，或者转移方位于未知网络站点中，则咨询呼叫转移到PSTN 终结点（即呼叫转移目标）将被阻止。

下表介绍了会议应用程序的基于位置的路由限制是如何应用于咨询呼叫转移的基于位置的路由限制。 虽然 PBX 终结点不与网络站点直接关联，但 PBX 的 SIP 中继可分配给网络站点。 因此，PBX 终结点可以与网络站点间接关联。


|**呼叫转移方的网络站点**|**呼叫转接目标的网络站点**|**行为**|
|:-----|:-----|:-----|
|PSTN 终结点  <br/> |同一网络站点中的 Skype for Business 用户（例如，站点1）  <br/> |将允许咨询转移  <br/> |
|PSTN 终结点  <br/> |不同网络站点（即站点2）中的 Skype for Business 用户  <br/> |将不允许咨询转移  <br/> |
|PSTN 终结点  <br/> |未知网络站点中的 Skype for Business 用户  <br/> |将不允许咨询转移  <br/> |
|PSTN 终结点  <br/> |联合 Skype for Business 用户  <br/> |将不允许咨询转移  <br/> |
|PSTN 终结点  <br/> |同一站点中的 PBX 终结点（例如，site 1）  <br/> |将允许咨询转移  <br/> |
|PSTN 终结点  <br/> |不同站点中的 PBX 终结点（即 site 2）  <br/> |将不允许咨询转移  <br/> |
|同一站点中的 PBX 终结点（例如，site 1）  <br/> |PSTN 终结点  <br/> |将允许咨询转移  <br/> |
|不同站点中的 PBX 终结点（即 site 2）  <br/> |PSTN 终结点  <br/> |将不允许咨询转移  <br/> |
|任何站点中的 PBX 终结点  <br/> |同一网络站点中的 Skype for Business 用户（例如，站点1）  <br/> |将允许咨询转移  <br/> |
|任何站点中的 PBX 终结点  <br/> |不同网络站点（即站点2）中的 Skype for Business 用户  <br/> |将允许咨询转移  <br/> |
|任何站点中的 PBX 终结点  <br/> |未知网络站点中的 Skype for Business 用户  <br/> |将允许咨询转移  <br/> |
|任何站点中的 PBX 终结点  <br/> |联合 Skype for Business 用户  <br/> |将允许咨询转移  <br/> |

## <a name="requirements"></a>Requirements

会议应用程序的基于位置的路由要求在拓扑中的所有前端池和 Standard Edition 服务器上都部署 Skype for Business Server 或 Lync Server 2013 累积更新2。 如果拓扑中的某些服务器上未安装这些服务器版本，则不能在会议和咨询呼叫转移上完全强制实施基于位置的路由限制。

下表标识了支持基于位置的路由的服务器角色和版本的组合。


|**前端池版本**|**中介服务器版本**|**支持**|
|:-----|:-----|:-----|
|Skype for Business Server 或 Lync Server 2013 累积更新2  <br/> |Skype for Business Server 或 Lync Server 2013 累积更新2  <br/> |是  <br/> |
|Lync Server 2013 累积更新2  <br/> |Lync Server 2013 累积更新1  <br/> |否  <br/> |
|Lync Server 2013 累积更新2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累积更新2  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累积更新1  <br/> |任意  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任意  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任意  <br/> |否  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>会议的基于位置的路由的配置

会议应用程序的基于位置的路由取决于基于位置的路由的配置。 主要配置如下所示：

- 加入会议的参与者的位置根据其网络网站确定。 必须在 Skype for Business Server 中定义网络站点及其关联的网络子网，才能强制实施基于位置的路由。

- 若要强制进行会议的基于位置的路由，必须为 Skype for Business 参与者启用基于位置的路由。

- 若要强制对 PSTN 终结点进行基于位置的路由加入会议，必须为用于连接 PSTN 终结点的 SIP 中继配置基于位置的路由。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>为会议启用基于位置的路由

默认情况下，将禁用会议应用程序的基于位置的路由。 在启用此应用程序之前，您需要确定要分配给应用程序的正确优先级。 若要确定此优先级，请在 Skype for Business Server 命令行管理程序中运行以下 cmdlet：

CsServerApplication-Identity Service：注册器：<Pool FQDN>在此 cmdlet 中， \<池 FQDN\>是要在其中启用会议应用程序的基于位置的路由的池。

此 cmdlet 将返回由 Skype for Business Server 托管的应用程序的列表以及每个应用程序的优先级值。 需要为会议应用程序的基于位置的路由分配比 "UdcAgent" 应用程序更大的优先级值，而不是 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 应用程序。 我们建议您为会议应用程序分配基于位置的路由，优先级值大于 "UdcAgent" 应用程序的优先级值的一个点。

例如，如果 "UdcAgent" 应用程序的优先级值为 "2"，则 "DefaultRouting" 应用程序的优先级值为 "8"，"ExumRouting" 应用程序的优先级值为 "9"，而 "OutboundRouting" 应用程序的优先级值为 "10"，则您应该为会议应用程序分配基于位置的路由，优先级值为 "3"。 这样做会按以下顺序放置应用程序的优先级：其他应用程序（优先级：0到1）、"UdcAgent" （优先级：2）、基于位置的路由会议应用程序（优先级：4）、其他应用程序（优先级：4到8）、"DefaultRouting "（优先级：9）、" ExumRouting "（优先级：10）和" OutboundRouting "（优先级：11）。

在为会议应用程序的基于位置的路由找到正确的优先级值之后，为每个前端池或 Standard Edition 服务器键入以下 cmdlet，以便为基于位置的路由启用了家庭用户：

CsServerApplication-Identity Service：注册器：`<Pool FQDN`>/Lbrouting-优先级\<应用程序优先级\>已启用 $true 关键 $true-Uri<https://www.microsoft.com/LCS/LBRouting> 

例如：

CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool/LBRouting-已启用优先级3的 $true-关键 $true-Urihttps://www.microsoft.com/LCS/LBRouting 

使用此 cmdlet 之后，请重新启动池中的所有前端服务器或启用了会议应用程序的基于位置的路由的 Standard Edition 服务器。

> [!IMPORTANT]
> 在重新启动适用的池中的所有前端服务器或 Standard Edition 服务器之前，将不会强制执行基于位置的路由之后或咨询转移。 如果对上述 cmdlet 中的 **$true** **进行设置，** 则会立即重新启动 Skype for business Server 服务。 如果您不希望这些服务立即重新启动，请将**关键**设置为 "现在 **$false** "，然后使用**CsServerApplication**更改为 "**关键**"，以便在以后重新启动服务后 **$true** 。

一旦成功启用了会议应用程序的基于位置的路由，并重新启动了所有适用的服务器，则会监视所有由 Skype for Business 用户组织的已启用了基于位置的路由的会议，以防止PSTN 收费旁路


