---
title: Location-Based Skype for Business Server 中的会议路由
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 规划 Skype for Business Server 企业语音会议基于位置的路由，包括咨询呼叫转接。
ms.openlocfilehash: 744f4b313f7ea458013aa0e45cff37ebbf85068a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825572"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based Skype for Business Server 中的会议路由

规划 Skype for Business Server 企业语音会议基于位置的路由，包括咨询呼叫转接。

Location-Based路由可以基于呼叫中各方的位置限制 VoIP 终结点和 PSTN 终结点之间的呼叫路由。 Location-Based路由功能使您可以对会议Location-Based路由规则，例如 (会议路由规则) PSTN 收费旁路。 应用程序监视活动会议，Location-Based根据参与用户的位置强制实施路由限制。 会议Location-Based路由还允许对涉及 PSTN 终结点的咨询Location-Based路由限制。

路由Location-Based应用程序为 Skype for Business 会议提供了一种防止 PSTN 收费绕过的机制。 应用程序监视活动会议，Location-Based Skype for Business 用户的位置强制实施路由限制。

路由Location-Based应用程序确定是否在满足Location-Based条件时对 Skype for Business 会议强制执行路由：

- 会议组织者已启用"Location-Based路由"。 Location-Based路由限制将仅应用于由启用了路由Location-Based组织的会议。

- 至少有一个会议参与者是 PSTN 终结点。 Location-Based路由限制仅适用于包含 PSTN 终结点的会议。

- 用于将会议桥接到 PSTN 的 PSTN 网关所在的网络站点，以及组织者和参与者所连接的网络站点。

会议Location-Based路由应用程序阻止 Skype for Business 用户和 PSTN 终结点从不同网络站点参与同一会议。 如果会议组织者启用了"Location-Based路由"，则会议应用程序将强制实施以下限制：

- 可以加入 Skype for Business 会议的终结点取决于已加入会议的终结点，当加入的终结点离开且新终结点加入会议时，此限制将进行调整。 如果组织者和参与者从同一网络站点加入 Skype for Business 会议，则允许 PSTN 终结点、来自同一网络站点的另一个参与者、不同网络站点的另一个参与者或未知网络站点的参与者加入。

- 如果组织者和参与者从不同或未知的网络站点加入会议，则如果 PSTN 呼叫从启用了"路由"的 SIP 中继进入，则不允许 PSTN 终结点加入Location-Based会议。

- 如果组织者和参与者都从同一网络站点加入会议，并且有参与者从 PSTN 加入同一会议，则不允许来自不同网络站点的 Skype for Business 终结点加入会议。

下表Location-Based这些会议路由限制。

|用户 () 点参与会议|允许 () 的用户|不允许 () 用户加入会议|
|:-----|:-----|:-----|
|Skype for Business VoIP 客户端 () 单个网络站点进行登录  <br/> |来自相同网络站点的 Skype for Business VoIP 客户端用户  <br/> 不同网络站点的 Skype for Business VoIP 客户端用户  <br/> 来自未知网络站点的 Skype for Business VoIP 客户端用户  <br/> 联盟 Skype for Business VoIP 客户端用户  <br/> 用户从 PSTN 终结点加入  <br/> |无  <br/> |
|Skype for Business VoIP 客户端 () 来自未知网络站点的用户  <br/> |来自任何站点的 Skype for Business VoIP 客户端用户  <br/> 来自未知站点的 Skype for Business VoIP 客户端用户  <br/> 联盟 Skype for Business VoIP 客户端用户  <br/> |用户通过 PSTN 终结点加入  <br/> |
|不同网络站点中的 Skype for Business VoIP 客户端用户  <br/> |来自任何网络站点的 Skype for Business VoIP 客户端用户  <br/> 来自未知网络站点的 Skype for Business VoIP 客户端用户  <br/> 联盟 Skype for Business VoIP 客户端用户  <br/> |用户通过 PSTN 终结点加入  <br/> |
|Skype for Business VoIP 客户端 (来自) 站点的客户端用户和从 PSTN 终结点加入的用户  <br/> |来自相同网络站点的 Skype for Business VoIP 客户端用户  <br/> |不同网络站点的 Skype for Business VoIP 客户端用户  <br/> 来自未知网络站点的 Skype for Business VoIP 客户端用户  <br/> 联盟 Skype for Business VoIP 客户端用户  <br/> |

以下是会议应用程序Location-Based路由的其他特征：

- 如果根据路由限制不允许用户加入Location-Based，则对会议的呼叫将被拒绝，Skype for Business 客户端将报告呼叫未完成或已结束。

- 如果 PSTN 终结点通过未启用 Location-Based 路由的中继加入会议，则无论其状态如何，加入具有 Location-Based 路由强制的会议的 PSTN 终结点Location-Based加入会议。

- 通过未将呼叫输出到 PSTN 的 SIP 中继连接到中介服务器的 PBX 系统将具有与位于定义 SIP 中继的相同网络站点中的 Skype for Business 用户相同的强制。 例如，PSTN 终结点将能够与 PBX 用户和 Skype for Business 用户加入会议（如果他们位于同一网络站点）;否则，如果 PBX 用户位于与 Skype for Business 用户不同的网络站点中，则不允许 PSTN 终结点加入会议。

> [!NOTE]
> 对于 Skype for Business 累积更新 4，应观察下表中的行为：

|用户|其他方|操作|结果|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile 正在进行 PSTN 呼叫。 Skype for Business Mobile 随后将呼叫上报给 CAA 自动助理 (会议) 。  <br/> |呼叫被阻止，并出现相应的错误消息。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business 客户端或联盟用户  <br/> |客户端或联盟用户正在与 Skype for Business Mobile Location-Based路由用户进行 VoIP 呼叫，并且任一方将升级至 CAA。  <br/> |升级呼叫被阻止，并出现相应的错误消息。  <br/> |

## <a name="consultative-call-transfers"></a>咨询呼叫转接

除了强制执行Location-Based路由到 Skype for Business 会议外，Location-Based 会议路由应用程序还对发至 PSTN 终结点的咨询呼叫转接强制实施 Location-Based 路由限制。 咨询呼叫转接是在双方之间建立的呼叫，其中一方将呼叫转接给新用户。 例如，PSTN 终结点呼叫用户 A (Skype for Business 被叫方) 。 用户 A 确定 PSTN 用户应转发到用户 B (Skype for Business) 。 用户 A 将 PSTN 用户的呼叫放在保留状态，并呼叫用户 B。用户 B 同意与 PSTN 用户交谈。 用户 A 将呼叫保持转接到用户 B。

**咨询呼叫转接呼叫流**

![会议图表的基于位置的路由](../../media/LocationBasedRoutingForConferencing.jpg)

启用 Location-Based 路由的用户启动 PSTN 终结点的咨询呼叫转接（如上图 () 所示）时，这将创建两个活动呼叫，一个呼叫在 PSTN 用户和 Skype for Business 用户 A 之间，另一个在 Skype for Business 用户 A 和 Skype for Business 用户 B 之间。以下行为由 Location-Based Routing for Conferencing 应用程序强制执行：

- 如果路由 PSTN 呼叫的 SIP 中继有权将 PSTN 呼叫重新路由到 Skype for Business 用户 B (即转接目标) 所在的网络站点，则允许呼叫转接;否则，咨询呼叫转接将被阻止。 此授权基于转接方的位置与将活动呼叫路由到 PSTN 终结点的 SIP 中继位于同一网络站点中。

- 如果路由入站 PSTN 呼叫的 SIP 中继无权将呼叫路由到转接方 (Skype for Business 用户 B) 所在的网络站点，或转接方位于未知网络站点，则咨询呼叫转接到 PSTN 终结点 (即呼叫转接目标) 将被阻止。

下表介绍了如何Location-Based咨询呼叫转接的Location-Based路由应用程序应用路由限制。 尽管 PBX 终结点未与网络站点直接关联，但可以为 PBX 连接到的 SIP 中继分配网络站点。 因此，PBX 终结点可以间接与网络站点关联。


|呼叫转接方的网络站点|呼叫转移目标的网络站点|行为|
|:-----|:-----|:-----|
|PSTN 终结点  <br/> |同一网络站点中的 Skype for Business (即站点 1)   <br/> |将允许咨询转接  <br/> |
|PSTN 终结点  <br/> |不同网络站点（即站点 2 (）中的 Skype for Business)   <br/> |将不允许咨询转接  <br/> |
|PSTN 终结点  <br/> |未知网络站点中的 Skype for Business 用户  <br/> |将不允许咨询转接  <br/> |
|PSTN 终结点  <br/> |联盟 Skype for Business 用户  <br/> |将不允许咨询转接  <br/> |
|PSTN 终结点  <br/> |同一站点中的 PBX (即站点 1)   <br/> |将允许咨询转接  <br/> |
|PSTN 终结点  <br/> |不同站点（即站点 2 (）中的 PBX)   <br/> |将不允许咨询转接  <br/> |
|同一站点中的 PBX (即站点 1)   <br/> |PSTN 终结点  <br/> |将允许咨询转接  <br/> |
|不同站点（即站点 2 (）中的 PBX)   <br/> |PSTN 终结点  <br/> |将不允许咨询转接  <br/> |
|任何站点中的 PBX 终结点  <br/> |同一网络站点中的 Skype for Business (即站点 1)   <br/> |将允许咨询转接  <br/> |
|任何站点中的 PBX 终结点  <br/> |不同网络站点（即站点 2 (）中的 Skype for Business)   <br/> |将允许咨询转接  <br/> |
|任何站点中的 PBX 终结点  <br/> |未知网络站点中的 Skype for Business 用户  <br/> |将允许咨询转接  <br/> |
|任何站点中的 PBX 终结点  <br/> |联盟 Skype for Business 用户  <br/> |将允许咨询转接  <br/> |

## <a name="requirements"></a>要求

会议Location-Based路由要求在拓扑中所有 Front-End 池和 Standard Edition Server 上部署 Skype for Business Server 或 Lync Server 2013 累积更新 2。 如果未在拓扑中的某些服务器上安装这些服务器版本，Location-Based对会议和咨询呼叫转接完全强制实施路由限制。

下表标识了支持路由的服务器角色和Location-Based的组合。


|Front-End池版本|中介服务器版本|支持|
|:-----|:-----|:-----|
|Skype for Business Server 或 Lync Server 2013 累积更新 2  <br/> |Skype for Business Server 或 Lync Server 2013 累积更新 2  <br/> |是  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2013 累积更新 1  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累积更新 1  <br/> |任何  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任何  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任何  <br/> |否  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>会议Location-Based路由的配置

会议Location-Based路由依赖于会议路由Location-Based配置。 主要配置如下：

- 加入会议的参与者的位置基于其网络站点确定。 必须在 Skype for Business Server 中定义网络站点及其关联的网络子网，才能强制执行Location-Based路由。

- 若要强制执行Location-Based路由，必须为 Skype for Business 参与者启用Location-Based路由。

- 若要强制执行Location-Based PSTN 终结点路由，必须为 PSTN 路由配置用于连接 PSTN 终结点的 SIP 中继Location-Based路由。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>为会议Location-Based路由

默认情况下Location-Based会议应用程序的默认路由。 在启用此应用程序之前，需要确定为应用程序分配正确的优先级。 若要确定此优先级，请运行 Skype for Business Server 命令行管理程序 中的以下 cmdlet：

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

在此 cmdlet 中，是启用会议Location-Based路由 \<Pool FQDN\> 的池。

此 cmdlet 将返回 Skype for Business Server 托管的应用程序的列表以及每个应用程序的优先级值。 会议Location-Based路由需要分配一个大于"UdcAgent"应用程序且小于"DefaultRouting"、"ExumRouting"和"OutboundRouting"应用程序的优先级值。 建议您为会议Location-Based路由分配优先级值，该值比"UdcAgent"应用程序的优先级值高一个点。

例如，如果"UdcAgent"应用程序的优先级值为"2"，则"DefaultRouting"应用程序的优先级值为"8"，"ExumRouting"应用程序的优先级值为"9"，而"OutboundRouting"应用程序的优先级值为"10"，则应该为 Location-Based Routing for Conferencing 应用程序分配优先级值"3"。 这样做将按以下顺序放置应用程序的优先级：其他应用程序 (优先级：0 到 1) ，"UdcAgent" (优先级：2) ， Location-Based 路由会议应用程序 (优先级：3) ，其他应用程序 (优先级：4 到 8) ，"DefaultRouting" (优先级：9) ，"ExumRouting" (优先级：10) ，"OutboundRouting" (优先级：11) 。

找到适用于会议应用程序的 Location-Based 路由的正确优先级值后，请针对每个 Front-End 池或 Standard Edition Server 键入以下 cmdlet，该池或 Standard Edition Server 为启用了 Location-Based 路由的用户提供以下 cmdlet：

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

例如：

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

使用此 cmdlet 后，重新启动池中的所有前端服务器或启用了会议Location-Based路由的 Standard Edition Servers。

> [!IMPORTANT]
> Location-Based池或 Standard Edition Servers 中所有前端服务器重新启动后，才会强制将强制路由到会议或咨询转接。 如果你将 **-Critical** 设置为 **$true** cmdlet，你的 Skype for Business Server 服务将立即重新启动。 如果您不希望这些服务立即重新启动，请现在将 **-Critical** 设置为 **$false，** 然后在重新启动服务后使用 **Set-CsServerApplication** 将 **-Critical** 更改为 **$true。**

成功启用Location-Based路由会议应用程序并重新启动所有适用的服务器后，将监视启用了 Location-Based 路由的 Skype for Business 用户组织的所有会议，以防止 PSTN 收费绕路


