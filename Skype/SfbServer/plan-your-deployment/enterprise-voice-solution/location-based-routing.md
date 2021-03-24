---
title: Plan for Location-Based Routing in Skype for Business
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
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: 在 Skype for Business Server 企业语音中规划基于位置的路由，包括与同时响铃和委派的交互，以及支持基于位置的路由方案。
ms.openlocfilehash: 99a76d3cda40bb1fdc71bdffc7f6c896c96c5cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101478"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Plan for Location-Based Routing in Skype for Business

在 Skype for Business Server 企业语音中规划基于位置的路由，包括与同时响铃和委派的交互，以及支持基于位置的路由方案。

Location-Based路由可以基于呼叫各方的位置限制 VoIP 终结点和 PSTN 终结点之间的呼叫路由。 Location-Based路由是一项呼叫管理功能，用于控制 Skype for Business Server 如何路由呼叫。 它强制执行呼叫授权规则，以确定是否可以基于 Skype for Business 呼叫者的地理位置将呼叫路由到 PBX 或 PSTN 终结点。

Location-Based路由引入了一组新规则，可修改国家/和国际 PSTN 呼叫的路由，以防止收费绕路问题。 Location-Based路由可以灵活地将这些规则的范围设定为特定区域、特定网关或仅特定的一组用户。

以下方案演示了路由可以强制实施Location-Based类型的限制：

- 出口呼叫 - Location-Based 路由可以强制传出呼叫进入 PSTN 网关，该网关位于呼叫者所在的同一区域，用于阻止 PSTN 收费绕路，从而阻止呼叫进入与呼叫者位于不同地区的 PSTN 网关。

- 传入呼叫 - Location-Based如果路由传入呼叫的 PSTN 网关与被叫 Skype for Business 用户不在同一区域，则路由路由可以阻止传入 PSTN 呼叫拨打 Skype for Business 终结点。

- 未知区域 - Location-Based 路由限制位于不确定位置（即从 Internet 连接或位于未知区域 () ）的用户的传入和传出 PSTN 呼叫。

- 国际区域 - Location-Based如果找不到用户位置的本地网关，则路由将强制通过国际 PSTN 网关路由传出呼叫。

## <a name="guidance-for-where-to-apply-location-based-routing"></a>应用路由Location-Based指南

Location-Based在用户的终结点网络站点位置或 PSTN 网关的网络站点位置应用基于情况路由。 本主题提供有关如何应用Location-Based路由的指南。

### <a name="applying-location-based-routing-at-the-users-location"></a>在Location-Based位置应用路由

Location-Based路由利用 E9-1-1、CAC 和媒体旁路使用 Skype for Business Server 中定义的相同网络区域、站点和子网应用呼叫路由限制，以防止 PSTN 收费绕路。 用户的位置由用户的 Skype for Business 终结点的 IP 子网 (连接) IP 子网。 每个 IP 子网都与一个网络站点关联，网络站点聚合到管理员定义的网络区域。 Location-Based基于用户的网络站点强制执行路由。

Location-Based路由规则基于每个网络站点应用，这意味着给定的一组规则将应用于为位于同一网络站点内的 Location-Based 路由启用的所有终结点。 管理员可以将Location-Based路由应用于需要它的网络站点。

可以基于每个网络站点定义语音路由策略，以定义特定 PSTN 网关，网络站点中的所有用户都应使用该网关呼叫 PSTN 电话号码。 当用户位于启用了 Location-Based 路由的网络站点中时，此类语音路由策略将优先于用户的语音策略定义的路由，并且它将阻止通过启用了 Location-Based 路由的其他 PSTN 网关路由呼叫。 当 Skype for Business 用户发出 PSTN 呼叫时，用户的语音策略将确定用户是否可以获得发出呼叫的授权。 如果用户的语音策略允许用户发出呼叫，则路由Location-Based确定呼叫应从哪个 PSTN 网关发出。 Location-Based路由根据用户的位置做出此决定。

用户位置可以按以下方式分类：

- 用户位于启用了 Location-Based 路由的已知网络站点中，其 DID (外线直拨拨号) 号码终止于位于相同网络站点 (即 office) 中的 PSTN 网关上。 出站呼叫的路由是通过用户所在的网络站点的语音路由策略。 传入到用户的 PSTN 呼叫将路由到与 PSTN 网关位于同一网络站点中的终结点。

- 用户位于与 PSTN 网关所在的网络站点不同的已知网络站点中。  (例如，用户前往另一个公司办事处) 。 出站呼叫的路由将采用用户所在的网络站点的语音路由策略。 传入到用户的 PSTN 呼叫不会路由到位于与 PSTN 网关不同的站点中的终结点，以防止 PSTN 收费绕路情况。

- 当用户位于 Skype for Business Server 部署未知的网络站点中时，出站呼叫的路由将基于分配给用户的语音策略到未绑定到 Location-Based 路由限制的 PSTN 网关。 传入 PSTN 呼叫不会路由到位于未知网络站点中的终结点，以防止 PSTN 收费绕路情况。

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>在Location-Based位置应用路由路由

通过 PSTN 网关和 PBX 路由的呼叫可能需要Location-Based路由限制，具体取决于此类系统的位置。 Location-Based可以按每个中继的粒度启用路由。

Location-Based在中继上启用时，路由将引入以下规则集：

- 当Location-Based中继启用路由时，该中继上定义的规则将仅应用于通过该中继路由的呼叫。

- 为防止 PSTN 收费绕路情况，即呼叫来自与 PSTN 网关所在的网络站点不同的网络站点，Location-Based Routing 引入了网络站点与给定中继的关联。 这将定义允许将呼叫路由到给定中继的网络站点。

可以通过两种方式为路由Location-Based中继：

- 为将呼叫输出到 PSTN 的 PSTN 网关定义中继。 此类型的中继路由的传入呼叫将仅路由到位于与中继相同的网络站点内的终结点。

- 为中介服务器对等方定义中继，该对等方不会将呼叫输出到 PSTN，并且为静态位置（例如 PBX 电话）中具有旧电话 (用户提供服务) 。 对于此特定配置，此类型的中继路由的所有传入呼叫均被视为来自与中继相同的网络站点。 来自 PBX 用户的呼叫将Location-Based中继位于同一网络站点中的 Skype for Business 用户执行路由。 如果位于不同网络站点中的两个 PBX 系统通过 Skype for Business Server 连接，Location-Based 路由将允许从一个网络站点中的一个 PBX 终结点路由到另一个网络站点中的另一个 PBX 终结点。 此方案不会被路由Location-Based阻止。 除此方案外，与位于相同位置的 Skype for Business 用户类似，连接到具有此配置的中介服务器对等方终结点将能够拨打或接收其他中介服务器对等方向 PSTN (即连接到不同 PBX) 的终结点的呼叫，无论中介服务器对等方已关联到哪个网络站点。 涉及 PSTN 终结点的所有入站呼叫、出站呼叫、呼叫转移和呼叫转接将受基于位置的路由的限制，以使用定义为此类中介服务器对等方本地的 PSTN 网关。

## <a name="scenarios-for-location-based-routing"></a>路由Location-Based方案

Location-Based路由在下列方案中路由呼叫时，路由将应用以下一般规则。

### <a name="outgoing-calls"></a>传出呼叫

启用了路由路由的用户的出Location-Based呼叫的路由受用户终结点的网络位置影响。 下表说明了路由Location-Based路由如何影响出站呼叫的路由，具体取决于呼叫者的终结点的位置。

**向 PSTN 发出出站呼叫的呼叫者**

||**位于启用了路由路由的网络站点中的Location-Based终结点**|**位于未知网络站点或未启用网络路由的用户Location-Based终结点**|
|:-----|:-----|:-----|
|出站呼叫的授权  <br/> |根据用户的语音策略授权呼叫  <br/> |根据用户的语音策略授权呼叫  <br/> |
|出站呼叫路由  <br/> |根据网络站点的语音路由策略路由呼叫  <br/> |呼叫根据用户的语音策略进行路由，并且仅通过未启用路由路由Location-Based中继 (路由)   <br/> |

### <a name="incoming-calls"></a>传入呼叫

向启用了路由路由Location-Based传入呼叫的路由取决于用户终结点的位置。 传入呼叫的路由以下列方式受到影响。 如果用户向启用了路由的 Location-Based 网络站点中的终结点发送传入呼叫，并且该终结点与 PSTN 网关位于同一网络站点中，将路由该呼叫。 如果用户对位于启用了路由的 Location-Based 网络站点中的终结点有传入呼叫，并且该终结点位于与 PSTN 网关不同的网络站点中，则将不会路由该呼叫。 如果用户没有与发出传入呼叫的 PSTN 网关位于同一网络站点中的终结点，则传入呼叫将直接路由到用户的语音邮件，并且未接来电通知将发送给被叫方。

将继续强制实施启用了 Location-Based Routing 的用户的呼叫转发设置，但是，转发的呼叫将受Location-Based路由限制的限制。

下表说明了呼叫Location-Based路由如何影响入站呼叫的路由，具体取决于被叫方终结点的位置。 PSTN 网关的网络站点已启用路由Location-Based，Location-Based路由仅允许将 PSTN 呼叫路由到同一网络站点内的终结点。

**从 PSTN 接收入站呼叫的被叫方**

||**与 PSTN 网关位于同一网络站点中的被叫方终结点**|**被叫方终结点与 PSTN 网关不在同一网络站点中**|**被叫方终结点位于未知网络站点或未启用Location-Based路由**|
|:-----|:-----|:-----|:-----|
|入站 PSTN 呼叫的路由  <br/> |传入呼叫将路由到被叫方终结点  <br/> |传入呼叫未路由到被叫方终结点  <br/> |传入呼叫未路由到被叫方终结点  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>呼叫转移和呼叫转接

当涉及 PSTN 终结点时，Location-Based 路由将分析呼叫者终结点的位置以及将呼叫转接到 (即转接目标) 的终结点。 Location-Based路由根据两个终结点的位置确定是否应转接呼叫。

下表说明了使用 PSTN 终结点进行呼叫时 Skype for Business 用户的方案，Skype for Business 用户将呼叫转接到另一个 Skype for Business 用户。 根据被叫方终结点的网络站点位置，Location-Based路由会影响呼叫转接的路由。

**发起呼叫转接**

|**发起呼叫转接的用户**|**目标终结点与发起呼叫转接的用户位于相同的网络站点中**|**目标终结点与发起呼叫转接的用户位于不同的网络站点中**|**目标终结点位于未知网络站点中，或网络站点未启用Location-Based路由**|
|:-----|:-----|:-----|:-----|
|Skype for Business 用户  <br/> |允许呼叫转接  <br/> |不允许呼叫转接  <br/> |不允许呼叫转接  <br/> |

例如：使用 PSTN 终结点的呼叫中的 Skype for Business 用户将呼叫转接到同一网络站点中的另一个 Skype for Business 用户。 在这种情况下，允许呼叫转移。

下表说明了 Skype for Business 用户在与另一个 Skype for Business 用户的呼叫中的情况，其中一个用户将呼叫转接到 PSTN 终结点。 根据呼叫转接到的用户的位置，下表详细说明了路由Location-Based呼叫有何影响。

**呼叫转接到 PSTN 终结点**

|**呼叫转接终结点目标**|**相同网络站点中的 Skype for Business 用户**|**不同网络站点中的 Skype for Business 用户**|**未知网络站点或网络站点中未启用路由路由的一个或两个 Skype for Business Location-Based用户**|
|:-----|:-----|:-----|:-----|
|PSTN 终结点  <br/> |转接用户的站点语音路由策略允许的呼叫转接  <br/> |转接用户的站点语音路由策略允许的呼叫转接  <br/> |转接用户的语音策略所允许的呼叫转接仅通过未启用 Location-Based 路由的中继  <br/> |

例如：与位于同一网络站点中的另一 Skype for Business 用户的呼叫中的 Skype for Business 用户将呼叫转接到 PSTN 终结点，允许呼叫转移。

### <a name="simultaneous-ringing"></a>同时响铃

当被叫方启用了同时响铃时，Location-Based路由将分析呼叫方的位置和被叫方终结点，以确定是否应该路由呼叫。

下表说明配置了同时响铃的用户，同时响铃目标为相同网络站点、不同网络站点或未知网络站点中的用户。

****

|**传入 PSTN 呼叫**|**与被叫方位于同一网络站点中**|**位于与被叫方不同的网络站点中**|**位于未知网络站点中或未启用Location-Based路由**|
|:-----|:-----|:-----|:-----|
|Skype for Business 用户  <br/> |允许同时响铃  <br/> |不允许同时响铃  <br/> |不允许同时响铃  <br/> |

下表说明了来自 Skype for Business 用户的呼叫 (即 Skype for Business 呼叫者) 在同一网络站点中、在不同网络站点中或来自未知网络站点。 被叫方具有 PSTN 终结点 (例如，) 配置为同时响铃目标。 在此方案中，Location-Based路由将确定是否应该将呼叫路由到同时响铃目标 (即被叫) 的移动电话。

****

|**同时响铃目标**|**与被叫方位于同一网络站点中**|**位于与被叫方不同的网络站点中**|**位于未知网络站点中或未启用Location-Based路由**|
|:-----|:-----|:-----|:-----|
|PSTN 终结点  <br/> |通过呼叫者的站点语音路由策略允许同时响铃  <br/> |通过呼叫者的站点语音路由策略允许同时响铃  <br/> |通过呼叫者的语音策略允许同时响铃到未启用呼叫路由的中继Location-Based响  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Skype for Business 累积更新 4

使用累积更新 4，你将看到以下内容：

- Location-Based路由将继续通过语音策略启用，包括 Skype for Business 移动客户端。

- Skype for Business 移动客户端的呼叫行为将基于它们是否启用了 Location-Based 路由和通信客户端。 这设计为静态，但在某些情况下，可能会努力将 Skype for Business 移动客户端与本地 PSTN 网关关联，并允许某些行为（如升级）

- 无论使用何种操作系统，Skype for Business 移动客户端都应具有相同的功能。

下表将演练累积更新 4 后一些方案：

|**基于位置的路由用户**|**其他方**|**操作**|**结果**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile 接收传入的 PSTN 呼叫。  <br/> |呼叫通过"通过工位呼叫" (CvW) 路由，而不是通过 VoIP 进行路由。  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile 进行传出 PSTN 呼叫。  <br/> |呼叫通过 CvW 而不是 VoIP 进行路由。  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile 正在进行 PSTN 呼叫。 然后，Skype for Business Mobile 将呼叫升级为其他用户或联系人。  <br/> |如果用户或联系人位于 PSTN 网关通道的本地，则通过 VoIP 路由呼叫。  <br/> 如果用户或联系人与 PSTN 网关通道是远程的，则通过 CvW 路由呼叫。  <br/> 如果无法通过 PSTN 访问目标用户，则呼叫将失败。  <br/> 如果目标联系人是 CAA 自动助理 (会议) ，将阻止呼叫。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business 客户端或联盟用户  <br/> |Skype for Business Mobile 向另一个 Skype for Business 客户端或联盟用户发起语音呼叫。  <br/> |呼叫通过 VoIP 完成。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business 客户端或联盟用户  <br/> | Skype for Business 客户端或联盟用户向 Skype for Business Mobile Location-Based路由用户发起语音呼叫。 <br/> |呼叫通过 VoIP 完成。  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business 客户端或联盟用户  <br/> |Skype for Business 客户端或联盟用户正在与 Skype for Business Mobile 用户进行 VoIP 呼叫。 任一方升级为其他 Skype for Business 或联盟用户。  <br/> |呼叫通过 VoIP 完成。  <br/> |
|Skype for Business Mobile  <br/> |联合用户  <br/> |联盟用户正在与 Skype for Business Mobile Location-Based进行语音呼叫;Skype for Business 移动方升级至 PSTN 用户。  <br/> |呼叫被阻止。  <br/> |
|Skype for Business Mobile  <br/> |联合用户  <br/> |联盟用户正在与 Skype for Business Mobile Location-Based路由用户进行 VoIP 呼叫;任一方升级至 CAA 联系人。  <br/> |升级的呼叫被阻止，并包含相应的错误消息。  <br/> |
|Skype for Business Mobile  <br/> |联合用户  <br/> |联盟用户正在与 Skype for Business Mobile Location-Based 路由用户进行 VoIP 呼叫，联盟用户升级至 PSTN 用户。  <br/> |将允许或禁止升级，Location-Based联盟用户的路由。 Skype for Business Mobile Location-Based 路由用户的应用程序不执行任何操作。  <br/> |

### <a name="delegation"></a>委派

Skype for Business 中的委派功能受以下Location-Based路由的影响：

- 当启用了 Location-Based 路由的代理人代表经理发出呼叫时，代理的语音策略将用于授权呼叫，并且代理人的站点语音路由策略将用于路由呼叫

- 对于呼叫经理的传入 PSTN 呼叫，适用于呼叫转接或同时响铃的相同规则将适用，如呼叫转接和同时响铃主题中所述。

- 当代理人将 PSTN 终结点设置为同时响铃目标时，对于呼叫经理的传入呼叫，与传入中继关联的站点的语音路由策略将用于将呼叫路由到代理人的 PSTN 终结点。

- 对于委派，建议经理及其关联的代理人通常位于同一网络站点中。

## <a name="other-planning-considerations"></a>其他规划注意事项

规划Location-Based路由时，应考虑对以下方案的影响。

### <a name="disaster-recovery"></a>灾难恢复

在从主池故障转移到备份池期间，以及将正常操作还原到主池时，在灾难恢复过程中Location-Based始终强制实施路由。

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

配置Location-Based路由会影响规划与 Survivable Branch 设备关联的网关的部署位置。 与 SBA 关联的网关必须位于与 Survivable Branch Appliance 相同的网络站点中;否则，如果配置了路由，则不允许 Survivable Branch Appliance 上Location-Based出站呼叫。 当 Survivable Branch Appliance 和中央站点之间的 WAN 连接关闭时，Location-Based路由限制仍然强制实施。

## <a name="client-and-server-support-for-location-based-routing"></a>客户端和服务器对路由Location-Based支持

Location-Based路由由 Skype for Business Server 强制执行。 Skype for Business Server 可以标识用户从企业网络内部进行连接的网络站点。 由于远程用户位于企业网络外部，因此他们的位置被视为未知。

### <a name="server-support"></a>服务器支持

Location-Based路由要求在给定拓扑的所有前端池和 Standard Edition 服务器上部署 Skype for Business Server 或 Lync Server 2013 CU1。 如果未安装这些版本的服务器，则不能完全强制实施基于位置的路由限制。

下表标识了支持路由的服务器角色和版本Location-Based组合。

****

|**池版本**|**中介服务器版本**|**支持**|
|:-----|:-----|:-----|
|Skype for Business Server 或 Lync Server 2013 2013 年 2 月累积更新  <br/> |Skype for Business Server 或 Lync Server 2013 2013 年 2 月累积更新  <br/> |是  <br/> |
|Skype for Business Server 或 Lync Server 2013 2013 年 2 月累积更新  <br/> |Lync Server 2013  <br/> |否  <br/> |
|Skype for Business Server 或 Lync Server 2013 2013 年 2 月累积更新  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Skype for Business Server 或 Lync Server 2013 2013 年 2 月累积更新  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013  <br/> |任意  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任意  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任意  <br/> |否  <br/> |

### <a name="client-support"></a>客户端支持

下表标识了路由Location-Based客户端。

****

|**客户端类型**|**支持**|**Details**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |是  <br/> ||
|Lync 2013  <br/> |是  <br/> ||
|Lync 2010  <br/> |是  <br/> ||
|Office Communicator 2007 R2  <br/> |否  <br/> ||
|Lync Phone Edition  <br/> |是  <br/> ||
|Lync Attendant  <br/> |是  <br/> ||
|Lync for Windows 8  <br/> |否  <br/> ||
|Lync Mobile 2013  <br/> |否  <br/> |如果启用了路由的用户使用 Lync Mobile 2013 客户端，则必须Location-Based VoIP。  <br/> |
|Lync Mobile 2010  <br/> |是  <br/> ||

> [!NOTE]
> 若要禁用 Skype for Business 客户端的 VoIP，请为启用了语音路由的所有用户分配一个移动策略（IP 音频/视频Location-Based禁用）。 有关移动策略的更多详细信息，请参阅[New-CsMobilityPolicy。](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)

## <a name="capabilities-not-supported-by-location-based-routing"></a>路由不支持Location-Based功能

Location-Based路由不适用于以下类型的交互。 Location-Based Skype for Business 终结点使用这些功能与 PSTN 终结点交互时，不强制使用路由。

- PSTN 拨入会议

- 通过响应组传入和传出 PSTN 呼叫

- 通过呼叫管理来呼叫呼叫的 PSTN 呼叫的呼叫管理或检索

- 传入到通知服务的 PSTN 呼叫

- 通过组内呼叫接听检索到的传入 PSTN 呼叫

若要Location-Based中的交互类型强制实施路由规则，必须启用Location-Based路由：

- 从会议拨出的 PSTN

- 从点对点音频对话升级至涉及 PSTN 终结点的会议

- 涉及 PSTN 终结点的咨询转接

若要启用Location-Based路由，请参阅会议基于 [位置的路由](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing)。