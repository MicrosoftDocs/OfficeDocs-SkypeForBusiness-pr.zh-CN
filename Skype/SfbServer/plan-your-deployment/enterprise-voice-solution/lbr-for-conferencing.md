---
title: Location-Based会议路由Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: 为会议规划基于位置的路由Skype for Business Server 企业语音包括咨询呼叫转接。
ms.openlocfilehash: e5f49dfcc798f4871ff9ecc1ed2fec1beacad8e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629524"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based会议路由Skype for Business Server

为会议规划基于位置的路由Skype for Business Server 企业语音包括咨询呼叫转接。

Location-Based路由可以基于呼叫各方的位置限制 VoIP 终结点和 PSTN 终结点之间的呼叫路由。 Location-Based路由功能使您可以对会议Location-Based路由规则，例如 (会议) PSTN 收费绕路情况。 应用程序监视活动会议，Location-Based用户的位置强制执行路由限制。 会议Location-Based路由应用程序还支持对涉及 PSTN 终结点的咨询Location-Based路由限制强制执行。

路由Location-Based应用程序为Skype for Business会议提供了一种防止 PSTN 收费绕路问题的机制。 应用程序监视活动会议，Location-Based用户参与的路由Skype for Business限制。

如果满足Location-Based条件，Location-Based路由会议应用程序确定是否对会议Skype for Business强制实施路由：

- 会议组织者已启用"Location-Based路由"。 Location-Based路由限制将仅应用于由启用了"路由"功能的用户组织的Location-Based会议。

- PSTN 终结点中至少有一个会议参与者。 Location-Based路由限制仅适用于包含 PSTN 终结点的会议。

- 用于将会议桥接到 PSTN 的 PSTN 网关所在的网络站点，以及组织者和参与者从其中连接的网络站点。

会议Location-Based路由应用程序阻止来自不同Skype for Business站点的用户和 PSTN 终结点加入同一会议。 如果会议组织者启用了路由Location-Based，则会议应用程序将强制实施以下限制：

- 可以加入会议Skype for Business取决于已加入会议的终结点，当加入的终结点离开且新终结点加入会议时，此限制将进行调整。 如果组织者和参与者从同一网络站点加入 Skype for Business 会议，则允许 PSTN 终结点、来自同一网络站点的另一个参与者、不同网络站点的另一个参与者或来自未知网络站点的参与者加入。

- 如果组织者和参与者从不同或未知的网络站点加入会议，则如果 PSTN 呼叫从启用了 Location-Based 路由的 SIP 中继进入，则不允许 PSTN 终结点加入会议。

- 如果组织者和参与者都从同一网络站点加入会议，并且有参与者从 PSTN 加入同一会议，则不允许来自不同网络站点的 Skype for Business 终结点加入会议。

下表汇总Location-Based会议路由限制。

|用户 () 点参与会议|允许用户 () 会议的用户|不允许 () 用户加入会议|
|:-----|:-----|:-----|
|Skype for BusinessVoIP 客户端 () 一个网络站点进行连接  <br/> |Skype for Business来自相同网络站点的 VoIP 客户端用户  <br/> Skype for Business不同网络站点中的 VoIP 客户端用户  <br/> Skype for Business来自未知网络站点的 VoIP 客户端用户  <br/> 联盟Skype for Business VoIP 客户端用户  <br/> 从 PSTN 终结点加入的用户  <br/> |无  <br/> |
|Skype for BusinessVoIP 客户端 () 未知网络站点进行连接  <br/> |Skype for Business来自任何站点的 VoIP 客户端用户  <br/> Skype for Business来自未知站点的 VoIP 客户端用户  <br/> 联盟Skype for Business VoIP 客户端用户  <br/> |用户通过 PSTN 终结点加入  <br/> |
|Skype for Business不同网络站点中的 VoIP 客户端用户  <br/> |Skype for Business来自任何网络站点的 VoIP 客户端用户  <br/> Skype for Business来自未知网络站点的 VoIP 客户端用户  <br/> 联盟Skype for Business VoIP 客户端用户  <br/> |用户通过 PSTN 终结点加入  <br/> |
|Skype for BusinessVoIP 客户端 () 来自单个网络站点，而用户从 PSTN 终结点加入  <br/> |Skype for Business来自相同网络站点的 VoIP 客户端用户  <br/> |Skype for Business不同网络站点中的 VoIP 客户端用户  <br/> Skype for Business来自未知网络站点的 VoIP 客户端用户  <br/> 联盟Skype for Business VoIP 客户端用户  <br/> |

以下是会议应用程序Location-Based路由的其他特征：

- 在给定路由限制Location-Based不允许用户加入会议时，将拒绝对会议的呼叫，Skype for Business 客户端将报告呼叫未完成或已结束。

- 如果 PSTN 终结点通过未启用 Location-Based Location-Based 路由的中继加入会议，则无论其状态如何，都将不会限制通过 Location-Based 路由加入会议。

- 通过未将呼叫输出到 PSTN 的 SIP 中继连接到中介服务器的 PBX 系统将具有与位于定义 SIP 中继的同一网络站点中的 Skype for Business 用户相同的强制。 例如，PSTN 终结点将能够与 PBX 用户和 Skype for Business（如果他们位于同一网络站点）加入会议;否则，如果 PBX 用户位于与用户不同的网络站点中，则不允许 PSTN Skype for Business会议。

> [!NOTE]
> 使用 Skype for Business累积更新 4 时，应观察下表中的行为：

|用户|其他方|操作|结果|
|:-----|:-----|:-----|:-----|
|Skype for Business移动  <br/> |PSTN  <br/> |Skype for Business移动位于 PSTN 呼叫中。 Skype for Business然后，移动将呼叫升级为 CAA 自动助理 (会议) 。  <br/> |呼叫被阻止，并出现相应的错误消息。  <br/> |
|Skype for Business移动  <br/> |Skype for Business客户端或联盟用户  <br/> |客户端或联盟用户正在与移动Skype for Business路由Location-Based进行 VoIP 呼叫，并且任一方升级至 CAA。  <br/> |升级呼叫被阻止，并包含相应的错误消息。  <br/> |

## <a name="consultative-call-transfers"></a>咨询呼叫转接

除了强制执行Location-Based路由到 Skype for Business 会议之外，Location-Based 会议路由应用程序还强制执行对发至 PSTN 终结点的咨询呼叫转接的 Location-Based 路由限制。 咨询呼叫转接是在双方之间建立的呼叫，其中一方将呼叫转接给新用户。 例如，PSTN 终结点呼叫用户 A (Skype for Business被叫方) 。 用户 A 确定 PSTN 用户应转发到用户 B， (Skype for Business用户) 。 用户 A 将呼叫与 PSTN 用户一起放在保持状态，并呼叫用户 B。用户 B 同意与 PSTN 用户交谈。 用户 A 将呼叫保持转接到用户 B。

**咨询呼叫转接呼叫流**

![会议图表的基于位置的路由](../../media/LocationBasedRoutingForConferencing.jpg)

启用 Location-Based 路由的用户启动 PSTN 终结点 (的咨询呼叫转移（如上图) 所示）时，这将创建两个活动呼叫，一个呼叫在 PSTN 用户和 Skype for Business 用户 A 之间，另一个呼叫在 Skype for Business 用户 A 和 Skype for Business 用户 B 之间。Location-Based 会议应用程序将强制执行以下行为：

- 如果路由 PSTN 呼叫的 SIP 中继有权将 PSTN 呼叫重新路由到 Skype for Business 用户 B (（即转接目标) ）所在的网络站点，则允许呼叫转接;否则，咨询呼叫转接将被阻止。 此授权基于转接方的位置与将活动呼叫路由到 PSTN 终结点的 SIP 中继位于同一网络站点中。

- 如果路由入站 PSTN 呼叫的 SIP 中继无权将呼叫路由到转接方 (Skype for Business 用户 B) 所在的网络站点，或转接方位于未知网络站点，则咨询呼叫将转接到 PSTN 终结点 (即呼叫转接目标) 将被阻止。

下表介绍了 Location-Based路由应用程序如何对咨询呼叫Location-Based应用路由限制。 尽管 PBX 终结点不直接与网络站点关联，但可以为 PBX 连接到的 SIP 中继分配网络站点。 因此，PBX 终结点可以间接与网络站点关联。


|呼叫转接方的网络站点|呼叫转接目标的网络站点|行为|
|:-----|:-----|:-----|
|PSTN 终结点  <br/> |Skype for Business网络站点中的用户 (，即站点 1)   <br/> |将允许咨询转接  <br/> |
|PSTN 终结点  <br/> |Skype for Business站点（即站点 2 (）中的用户)   <br/> |将不允许咨询转接  <br/> |
|PSTN 终结点  <br/> |Skype for Business未知网络站点中的用户  <br/> |将不允许咨询转接  <br/> |
|PSTN 终结点  <br/> |联盟Skype for Business用户  <br/> |将不允许咨询转接  <br/> |
|PSTN 终结点  <br/> |同一站点中的 PBX (，即站点 1)   <br/> |将允许咨询转接  <br/> |
|PSTN 终结点  <br/> |不同站点（即站点 2 (）中的 PBX)   <br/> |将不允许咨询转接  <br/> |
|同一站点中的 PBX (，即站点 1)   <br/> |PSTN 终结点  <br/> |将允许咨询转接  <br/> |
|不同站点（即站点 2 (）中的 PBX)   <br/> |PSTN 终结点  <br/> |将不允许咨询转接  <br/> |
|任何站点中的 PBX 终结点  <br/> |Skype for Business网络站点中的用户 (，即站点 1)   <br/> |将允许咨询转接  <br/> |
|任何站点中的 PBX 终结点  <br/> |Skype for Business站点（即站点 2） (站点 2 中的用户)   <br/> |将允许咨询转接  <br/> |
|任何站点中的 PBX 终结点  <br/> |Skype for Business未知网络站点中的用户  <br/> |将允许咨询转接  <br/> |
|任何站点中的 PBX 终结点  <br/> |联盟Skype for Business用户  <br/> |将允许咨询转接  <br/> |

## <a name="requirements"></a>要求

会议Location-Based路由应用程序要求在拓扑的所有 Front-End 池和 Standard Edition 服务器上部署 Skype for Business Server 或 Lync Server 2013 累积更新 2。 如果未在拓扑中的某些服务器上安装这些服务器版本，Location-Based会议转接和咨询呼叫转接完全强制实施路由限制。

下表标识了支持路由的服务器角色和版本Location-Based组合。


|Front-End 池版本|中介服务器版本|支持|
|:-----|:-----|:-----|
|Skype for Business Server Lync Server 2013 累积更新 2  <br/> |Skype for Business Server Lync Server 2013 累积更新 2  <br/> |是  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2013 累积更新 1  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累积更新 1  <br/> |任何  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任何  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任何  <br/> |否  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>会议Location-Based路由的配置

会议Location-Based路由依赖于会议路由Location-Based配置。 主要配置如下：

- 加入会议的参与者的位置取决于其网络站点。 网络站点及其关联的网络子网必须在 Skype for Business Server中定义，以便强制实施Location-Based路由。

- 若要强制Location-Based路由会议，Skype for Business必须启用会议Location-Based路由。

- 若要Location-Based PSTN 终结点加入会议的路由，必须为 PSTN 终结点配置用于连接 PSTN 终结点的 SIP 中继Location-Based路由。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>启用Location-Based路由

默认情况下Location-Based会议应用程序的默认路由。 在启用此应用程序之前，需要确定为应用程序分配适当的优先级。 若要确定此优先级，在命令行管理程序中Skype for Business Server cmdlet：

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

在此 cmdlet 中，是启用会议Location-Based路由 \<Pool FQDN\> 的池。

此 cmdlet 将返回由 Skype for Business Server 托管的应用程序的列表以及每个应用程序的优先级值。 会议Location-Based路由需要分配一个大于"UdcAgent"应用程序且小于"DefaultRouting"、"ExumRouting"和"OutboundRouting"应用程序的优先级值。 建议您为会议Location-Based路由应用程序分配优先级值，该值比"UdcAgent"应用程序的优先级值高一个点。

例如，如果"UdcAgent"应用程序的优先级值为"2"，则"DefaultRouting"应用程序的优先级值为"8"，则"ExumRouting"应用程序的优先级值为"9"，而"OutboundRouting"应用程序的优先级值为"10"，则应该为 Location-Based Routing for Conferencing 应用程序分配优先级值"3"。 这样做将按以下顺序放置应用程序的优先级：其他应用程序 (优先级：0 到 1) ，"UdcAgent" (优先级：2) ， Location-Based 路由会议应用程序 (优先级：3) ，其他应用程序 (优先级：4 到 8) ，"DefaultRouting" (优先级：9) ，"ExumRouting" (优先级：10) ，"OutboundRouting" (优先级：11) 。

找到"会议路由"应用程序的 Location-Based 路由的正确优先级值后，为每台 Front-End 池或 Standard Edition Server 键入以下 cmdlet，这些 cmdlet 用于为启用了 Location-Based 路由的用户：

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

例如：

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

使用此 cmdlet 后，重新启动池中的所有前端服务器或启用了会议Standard Edition路由的 Location-Based 服务器。

> [!IMPORTANT]
> Location-Based池或 Standard Edition 服务器的所有前端服务器重新启动后，才会强制将路由强制路由到会议或咨询转接。 如果将 **-Critical** **$true** 上述 cmdlet 中，Skype for Business Server服务将立即重新启动。 如果您不希望这些服务立即重新启动，请现在将 **-Critical** 设置为 **$false，** 然后在服务重新启动后使用 **Set-CsServerApplication** 将 **-Critical** 更改为 **$true。**

成功启用 Location-Based Routing for Conferencing 应用程序并重新启动所有适用的服务器后，将监视由启用了 Location-Based 路由的 Skype for Business 用户组织的所有会议，以防止 PSTN 收费绕路情况


