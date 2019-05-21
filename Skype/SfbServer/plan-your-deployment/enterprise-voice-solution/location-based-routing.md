---
title: 在 Skype for Business 中规划基于位置的路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: 在 Skype for Business Server Enterprise Voice 中规划基于位置的路由, 包括与同时拨打和委派的交互, 以及基于位置的路由支持的方案。
ms.openlocfilehash: 8c6ce8467c48231ebcab706874e70341ba431fd8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276745"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>在 Skype for Business 中规划基于位置的路由

在 Skype for Business Server Enterprise Voice 中规划基于位置的路由, 包括与同时拨打和委派的交互, 以及基于位置的路由支持的方案。

基于位置的路由使您能够根据呼叫中各方的位置限制 VoIP 终结点和 PSTN 终结点之间的通话路由。 基于位置的路由是一种呼叫管理功能, 用于控制 Skype for Business 服务器如何路由呼叫。 根据 Skype for Business 呼叫者所在的地理位置, 它会强制执行呼叫授权规则, 以确定是否可以将呼叫路由到 PBX 或 PSTN 终结点。

基于位置的路由引入了一组新规则，它们可修改国内和国际 PSTN 呼叫的路由以防止收费绕路情形。使用基于位置的路由可灵活地将这些规则限定为仅特定区域、特定网关或特定用户集。

以下方案说明了基于位置的主要路由可强制执行的主要类型:

- 外出呼叫-基于位置的路由可将传出呼叫强制传出到 PSTN 网关, 该 PSTN 网关位于与呼叫者阻止 PSTN 免绕过的同一区域中, 从而阻止呼叫与呼叫方位于不同区域的 PSTN 网关的出口。

- 进入呼叫-基于位置的路由可以阻止传入 PSTN 呼叫拨打 Skype for business 终结点, 前提是该传入呼叫与称为 Skype for business 用户不在同一地区。

- 未知区域-基于位置的路由对位于不确定位置 (即从 Internet 连接的远程用户或位于未知区域) 的用户限制传入和传出 PSTN 呼叫。

- 国际区域-基于位置的路由通过国际 PSTN 网关 (如果找不到用户位置的本地网关) 强制路由传出呼叫。

## <a name="guidance-for-where-to-apply-location-based-routing"></a>有关在何处应用基于位置的路由的指南

基于位置的路由可应用于用户的终结点网络网站位置或 PSTN 网关的网络网站位置。 本主题提供有关如何应用基于位置的路由的指南。

### <a name="applying-location-based-routing-at-the-users-location"></a>在用户的位置应用基于位置的路由

基于位置的路由利用由 E9 使用的 Skype for Business 服务器中定义的相同网络区域、网站和子网, 从而应用呼叫路由限制以防止 PSTN 免绕过。 用户的位置由用户的 Skype for Business 终结点连接的 IP 子网确定。 每个 IP 子网都与一个网络站点相关联，它们将聚合到由管理员确定的网络区域中。 基于位置的路由根据用户的网络网站实施。

基于位置的路由规则是针对每个网络站点应用的, 这意味着给定的一组规则将应用于为位于同一网络站点内的基于位置的路由启用的所有终结点。 管理员可以将基于位置的路由应用于需要它的网络站点。

可以在每个网络站点上定义语音路由策略，以定义应由网络站点内的所有用户用于呼叫 PSTN 号码的特殊 PSTN 网关。 当用户位于为基于位置的路由启用的网络站点中时, 此类语音路由策略将优先于用户的语音策略所定义的路由, 并且它将阻止通过其他 PSTN 网关启用呼叫路由基于位置的路由。 当 Skype for Business 用户发出 PSTN 呼叫时, 用户的语音策略确定是否可以授权用户进行呼叫。 如果用户的语音策略允许用户进行呼叫, 则基于位置的路由确定呼叫应传出的 PSTN 网关。 基于位置的路由根据用户的位置进行此确定。

用户位置可以通过以下方式进行分类：

- 用户位于为基于位置的路由启用的已知网络站点, 并且其已完成 (直接拨入式拨号) 号码将在位于同一网络站点 (即 office) 的 PSTN 网关上终止。 出站呼叫通过用户所在的网络站点的语音路由策略进行路由。 发往用户的传入 PSTN 呼叫将路由到与 PSTN 网关位于相同网络站点中的终结点。

- 用户所在的已知网络站点不同于 PSTN 网关所在的网络站点。（例如，用户前往另一公司办事处出差。）出站呼叫使用用户所在的网络站点的语音路由策略进行路由。发往用户的传入 PSTN 呼叫不会路由到所在站点与 PSTN 网关不同的终结点，从而防止 PSTN 收费绕路情形。

- 当用户位于 Skype for Business 服务器部署未知的网络网站中时, 出站呼叫的路由将基于为用户分配给未绑定到基于位置的路由限制的 PSTN 网关的语音策略。 传入 PSTN 呼叫不会路由到位于未知网络站点内的终结点，从而防止 PSTN 收费绕路情形。

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>在 PSTN 网关的位置应用基于位置的路由

通过 PSTN 网关和 Pbx 路由的通话可能需要基于位置的路由限制, 具体取决于此类系统的位置。 基于位置的路由可以按每个干线的粒度来启用。

基于位置的路由在主干上启用时引入以下规则集:

- 在每个主干基础上启用基于位置的路由时, 在该主干上定义的规则将仅应用于通过该主干路由的呼叫。

- 为了防止 PSTN tolls 绕过从网络站点 (PSTN 网关所在的网络站点不同) 的网络站点进行调用的位置, 基于位置的路由引入了网络站点与给定主干的关联。 这定义了允许呼叫路由到给定中继的网络站点。

可以通过以下两种方式为基于位置的路由启用中继:

- 为中继定义将呼叫发出到 PSTN 的 PSTN 网关。此类型的中继路由的传入呼叫只能路由到位于与中继相同的网络站点中的终结点。

- 主干是针对中介服务器对等方定义的, 它不会向在静态位置 (即 PBX 手机) 中使用旧式电话的 PSTN 和服务用户传出呼叫。 对于此特殊配置，此类型的中继路由的传入呼叫将视为来自与中继相同的网络站点。 来自 PBX 用户的呼叫将与与主干所在的同一网络站点中的 Skype for business 用户具有相同的基于位置的路由强制。 如果位于单独网络站点的两个 PBX 系统通过 Skype for Business 服务器连接, 基于位置的路由将允许从一个网络站点中的一个 PBX 终结点路由到另一个网络站点中的另一个 PBX 终结点。 此方案不会被基于位置的路由阻止。 除了此方案以及与同一位置的 Skype for business 用户类似的情况下, 连接到具有此配置的中介服务器对等的终结点将能够在不路由呼叫 t 的其他中介服务器对等上进行或接收呼叫o PSTN (即连接到其他 PBX 的终结点) 与中介服务器对等关联的网络站点无关。 所有入站呼叫、出站呼叫、呼叫转接和涉及 PSTN 终结点的转接将根据基于位置的路由, 仅使用定义为本中介服务器对等的本地的 PSTN 网关。

## <a name="scenarios-for-location-based-routing"></a>基于位置的路由的方案

当在以下方案中路由呼叫时，基于位置的路由应用以下常规规则。

### <a name="outgoing-calls"></a>传出呼叫

对启用了基于位置的路由的用户的出站呼叫的路由受用户终结点的网络位置的影响。 下表说明了基于位置的路由如何影响出站呼叫路由, 具体取决于呼叫者终结点的位置。

**向 PSTN 发出出站呼叫的呼叫者**

||**位于启用了基于位置的路由的网络站点中的用户终结点**|**位于未知网络站点或者未启用基于位置的路由的网络站点中的用户终结点**|
|:-----|:-----|:-----|
|出站呼叫授权  <br/> |根据用户的语音政策, 呼叫已获得授权  <br/> |根据用户的语音政策, 呼叫已获得授权  <br/> |
|出站呼叫路由  <br/> |根据网络站点的语音路由策略路由呼叫  <br/> |呼叫将根据用户的语音策略进行路由, 并且只能通过中继 (如果有) 启用。  <br/> |

### <a name="incoming-calls"></a>传入呼叫

将传入呼叫路由到启用基于位置的路由的用户取决于用户终结点的位置。 传入呼叫的路由通过以下方式受到影响。 如果用户对位于基于位置的启用路由的网络站点中的终结点进行传入呼叫, 并且终结点与 PSTN 网关位于同一网络站点, 则将路由呼叫。 如果用户对位于基于位置的启用路由的网络站点中的终结点进行传入呼叫, 并且终结点所在的网络站点与 PSTN 网关不同, 则不会路由呼叫。 当用户在与传入呼叫来自的 PSTN 网关所在的网络站点中没有终结点时, 传入呼叫将直接路由到用户的语音邮件, 并且将向呼叫方发送未接来电通知。

将继续强制执行为基于位置的路由启用的用户的呼叫转接设置, 但是呼叫转移将受到用户基于位置的路由限制。

下表说明了基于位置的路由如何影响传入呼叫的路由, 具体取决于被调用方终结点的位置。 PSTN 网关的网络站点为基于位置的路由启用, 并且基于位置的路由仅允许对同一网络站点内终结点的 PSTN 呼叫路由。

**从 PSTN 接收入站呼叫的被呼叫者**

||**被呼叫方的终结点位于与 PSTN 网关相同的网络站点中**|**被调用方的终结点不位于与 PSTN 网关相同的网络站点中**|**被调用方的终结点位于未知的网络站点中, 或者没有为基于位置的路由启用**|
|:-----|:-----|:-----|:-----|
|入站 PSTN 呼叫的路由  <br/> |传入呼叫将路由到被呼叫方的终结点  <br/> |传入呼叫未路由到被呼叫方的终结点  <br/> |传入呼叫未路由到被呼叫方的终结点  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>呼叫转移和呼叫转接

当涉及 PSTN 终结点时, 基于位置的路由会分析 calle 终结点的位置以及呼叫将被转移或转发到的终结点 (例如, 传输/转发目标)。 基于位置的路由确定是否应根据两个终结点的位置来转移或转发呼叫。

下表说明了使用 PSTN 终结点进行呼叫的 Skype for business 用户的方案, 并且 Skype for Business 用户将呼叫转移到另一个 Skype for Business 用户。 根据 transferee 终结点的网络站点位置, 基于位置的路由会影响呼叫转移或转发的路由。

**发起呼叫转接**

|**发起呼叫转接的用户**|**目标终结点位于与发起呼叫转接的用户相同的网络站点中**|**目标终结点位于与发起呼叫转接的用户不同的网络站点中**|**目标终结点位于未知的网络网站中, 或者没有为基于位置的路由启用网络网站**|
|:-----|:-----|:-----|:-----|
|Skype for Business 用户  <br/> |允许呼叫转接  <br/> |不允许呼叫转接  <br/> |不允许呼叫转接  <br/> |

例如: 与 PSTN 终结点通话的 Skype for Business 用户将呼叫转移到位于同一网络站点中的另一个 Skype for Business 用户。 在这种情况下，允许进行呼叫转接。

下表介绍了与另一个 Skype for Business 用户进行的通话中的 Skype for business 用户的方案, 其中一个用户将呼叫转移到 PSTN 终结点。 根据呼叫转接至的用户的位置，表格详细介绍了基于位置的路由如何影响呼叫。

**呼叫转接至 PSTN 终结点**

|**呼叫转接终结点目标**|**同一网络网站中的 Skype for business 用户**|**不同网络站点中的 Skype for business 用户**|**未知网络网站中的一个或两个 Skype for Business 用户或不支持基于位置的路由的网络网站**|
|:-----|:-----|:-----|:-----|
|PSTN 终结点  <br/> |已转移用户的网站语音路由策略允许呼叫转接或转移  <br/> |已转移用户的网站语音路由策略允许呼叫转接或转移  <br/> |转移的用户语音策略允许的呼叫转移或转移仅通过中继未启用基于位置的路由  <br/> |

例如: 与同一网络站点中的其他 Skype for business 用户进行通话的 Skype for business 用户将呼叫转移到 PSTN 终结点, 并允许呼叫转移。

### <a name="simultaneous-ringing"></a>同时响铃

当被呼叫方启用同时震铃时, 基于位置的路由会分析呼叫方的位置和被呼叫方的终结点, 以确定是否应路由呼叫。

下表说明配置了同时响铃的用户，同时响铃目标是位于相同网络站点中的用户、位于不同网络站点中的用户或者位于未知网络站点中的用户。

****

|**传入 PSTN 呼叫**|**位于与被呼叫者相同的网络站点中**|**位于与被呼叫者不同的网络站点中**|**位于未知网络网站中, 或者未启用基于位置的路由**|
|:-----|:-----|:-----|:-----|
|Skype for Business 用户  <br/> |允许同时响铃  <br/> |不允许同时响铃  <br/> |不允许同时响铃  <br/> |

下表说明了来自 Skype for Business 用户 (即 Skype for business 呼叫者) 的呼叫, 该用户位于同一网络站点、不同网络站点或来自未知网络站点。 被呼叫者将 PSTN 终结点（如移动电话）配置为同时响铃目标。 在此方案中, 基于位置的路由将确定是否应将呼叫路由到被呼叫方的同时环目标 (即手机)。

****

|**同时响铃目标**|**位于与被呼叫者相同的网络站点中**|**位于与被呼叫者不同的网络站点中**|**位于未知网络网站中, 或者未启用基于位置的路由**|
|:-----|:-----|:-----|:-----|
|PSTN 终结点  <br/> |通过呼叫者的站点语音路由策略允许同时拨打  <br/> |通过呼叫者的站点语音路由策略允许同时拨打  <br/> |通过呼叫者的语音策略允许同时拨打, 可同时拨打基于位置的布线的中继  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Skype for Business 累积更新 4

通过累积更新 4，你将看到以下结果：

- 基于位置的路由将通过语音策略继续启用, 包括 Skype for Business 移动客户端。

- Skype for business 移动客户端的呼叫行为取决于它们是否启用了基于位置的路由和通信客户端。 这设计为静态，但有些情况下，可能会尽力将 Skype for Business 移动客户端与本地 PSTN 网关关联并允许某些行为（如升级）

- 无论你使用哪个操作系统，Skype for Business 移动客户端的功能都应该相同。

下表将指导你完成累积更新 4 之后的一些方案：

|**基于位置的路由用户**|**其他方**|**操作**|**结果**|
|:-----|:-----|:-----|:-----|
|Skype for Business 移动  <br/> |PSTN  <br/> |Skype for Business Mobile 接收 PSTN 来电。  <br/> |该呼叫使用通过工号拨号 (CvW) 而不是 VoIP 路由。  <br/> |
|Skype for Business 移动  <br/> |PSTN  <br/> |Skype for business Mobile 进行出局 PSTN 呼叫。  <br/> |该呼叫通过 CvW 而不是 VoIP 路由。  <br/> |
|Skype for Business 移动  <br/> |PSTN  <br/> |Skype for Business 移动进行 PSTN 通话。 Skype for business Mobile 将呼叫升级到另一个用户或联系人。  <br/> |如果用户或联系人在 PSTN 网关线路本地，则通过 VoIP 路由呼叫。  <br/> 如果用户或联系人距离 PSTN 网关线路很遥远，则通过 CvW 路由呼叫。  <br/> 如果通过 PSTN 无法访问目标用户，则呼叫失败。  <br/> 如果目标联系人是会议自动助理 (CAA)，则阻止该呼叫。  <br/> |
|Skype for Business 移动  <br/> |Skype for Business 客户端或联合用户  <br/> |Skype for Business Mobile 开始向其他 Skype for Business 客户端或联盟用户发出语音呼叫。  <br/> |该呼叫通过 VoIP 完成。  <br/> |
|Skype for Business 移动  <br/> |Skype for Business 客户端或联合用户  <br/> | Skype for business 客户端或联合用户开始对基于 Skype for business 移动位置的路由用户进行语音呼叫。 <br/> |该呼叫通过 VoIP 完成。  <br/> |
|Skype for Business 移动  <br/> |Skype for Business 客户端或联合用户  <br/> |Skype for business 客户端或联盟用户是对 Skype for business 移动用户的 VoIP 呼叫。 任何一方向其他 Skype for Business 或联盟用户进行升级。  <br/> |该呼叫通过 VoIP 完成。  <br/> |
|Skype for Business 移动  <br/> |联合用户  <br/> |联盟用户在基于 Skype for business 移动位置的路由用户上进行语音呼叫;Skype for Business 移动方升级到 PSTN 用户。  <br/> |呼叫被阻止。  <br/> |
|Skype for Business 移动  <br/> |联合用户  <br/> |联盟用户是基于 Skype for business 移动位置的 VoIP 呼叫, 后者是基于 Skype for business 的路由用户。任何一方向 CAA 联系人进行升级。  <br/> |升级呼叫被阻止，并显示相应的错误消息。  <br/> |
|Skype for Business 移动  <br/> |联合用户  <br/> |联盟用户是基于 Skype for business 移动位置的路由用户的 VoIP 呼叫, 而联盟用户则升级到 PSTN 用户。  <br/> |根据联盟用户的基于位置的路由, 将允许或禁止升级。 基于 Skype for Business 移动位置的路由用户应用程序不执行任何操作。  <br/> |

### <a name="delegation"></a>委派

Skype for Business 中的委派功能受基于位置的路由以下列方式受到影响:

- 当为基于位置的路由启用代理人代表经理呼叫时, 代理人的语音政策将用于授权呼叫, 代理人的网站语音路由策略将用于路由呼叫

- 对于打给经理的传入 PSTN 呼叫，适用于呼叫转接或同时响铃的相同规则将按照呼叫转接和同时响铃主题所述进行应用。

- 当代理人将 PSTN 终结点设置为同时拨打的电话时, 对于对管理器的传入呼叫, 将使用与传入主干相关联的站点的语音路由策略将呼叫路由到代理人的 PSTN 终结点。

- 对于委派, 建议经理和他的相关联的代理人通常位于同一网络站点。

## <a name="other-planning-considerations"></a>其他规划考虑事项

规划基于位置的路由时, 应考虑对以下方案的影响。

### <a name="disaster-recovery"></a>灾难恢复

在将主池故障转移到备份池以及将正常操作还原到主池的过程中, 在灾难和恢复过程中始终强制执行基于位置的路由。

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

配置基于位置的路由会影响你部署与 Survivable 分支机构相关联的网关的位置的规划。 与你的 SBA 关联的网关必须与 Survivable 分支装置位于同一网络站点;否则, 如果配置基于位置的路由, 则不允许驻留在 Survivable 分支设备上的用户进行出站呼叫。 当 Survivable 分支设备和中心网站之间的 WAN 连接关闭时, 基于位置的路由限制将保持强制实施。

## <a name="client-and-server-support-for-location-based-routing"></a>基于位置的路由的客户端和服务器支持

基于位置的路由由 Skype for Business 服务器强制执行。 Skype for business 服务器可以标识用户从公司网络中连接的网络站点。 由于远程用户位于企业网络外，其位置将被视为未知。

### <a name="server-support"></a>服务器支持

基于位置的路由要求在给定拓扑中的所有前端池和标准版服务器上部署 Skype for business 服务器或 Lync Server 2013 CU1。 如果未安装这些版本的服务器, 则不能完全强制使用基于位置的路由限制。

下表标识了基于位置的路由支持的服务器角色和版本的组合。

****

|**池版本**|**中介服务器版本**|**支持**|
|:-----|:-----|:-----|
|Skype for business 服务器或 Lync Server 2013 2 2013 月累积更新  <br/> |Skype for business 服务器或 Lync Server 2013 2 2013 月累积更新  <br/> |支持  <br/> |
|Skype for business 服务器或 Lync Server 2013 2 2013 月累积更新  <br/> |Lync Server 2013  <br/> |不支持  <br/> |
|Skype for business 服务器或 Lync Server 2013 2 2013 月累积更新  <br/> |Lync Server 2010  <br/> |不支持  <br/> |
|Skype for business 服务器或 Lync Server 2013 2 2013 月累积更新  <br/> |Office Communications Server 2007 R2  <br/> |不支持  <br/> |
|Lync Server 2013  <br/> |任意  <br/> |不支持  <br/> |
|Lync Server 2010  <br/> |任意  <br/> |不支持  <br/> |
|Office Communications Server 2007 R2  <br/> |任意  <br/> |不支持  <br/> |

### <a name="client-support"></a>客户端支持

下表标识了基于位置的路由支持的客户端。

****

|**客户端类型**|**支持**|**详细信息**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |支持  <br/> ||
|Lync 2013  <br/> |支持  <br/> ||
|Lync 2010  <br/> |支持  <br/> ||
|Office Communicator 2007 R2  <br/> |不支持  <br/> ||
|Lync Phone Edition  <br/> |支持  <br/> ||
|Lync Attendant  <br/> |支持  <br/> ||
|适用于 Windows 8 的 Lync  <br/> |不支持  <br/> ||
|Lync Mobile 2013  <br/> |不支持  <br/> |如果启用了基于位置的路由的用户使用, 则必须为 Lync Mobile 2013 客户端禁用 VoIP。  <br/> |
|Lync Mobile 2010  <br/> |支持  <br/> ||

> [!NOTE]
> 若要对 Skype for business 客户端禁用 VoIP, 请为启用了基于位置的路由的所有用户的设置 (IP 音频/视频) 分配移动策略。 有关移动策略的详细信息，请参阅 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。

## <a name="capabilities-not-supported-by-location-based-routing"></a>基于位置的路由不支持的功能

基于位置的路由不适用于以下类型的交互。 当 Skype for Business 终结点使用这些功能与 PSTN 终结点交互时, 不强制执行基于位置的路由。

- PSTN 电话拨入式会议

- 通过响应组的传入和传出 PSTN 呼叫

- 通过呼叫寄存对 PSTN 呼叫进行呼叫寄存或检索

- 到公告服务的传入 PSTN 呼叫

- 通过组内呼叫应答检索的传入 PSTN 呼叫

若要对下表中的交互类型强制使用基于位置的路由规则, 必须为会议启用基于位置的路由:

- PSTN 电话拨出式会议

- 从点对点音频对话升级到涉及 PSTN 终结点的音频会议

- 涉及 PSTN 终结点的咨询转接

若要为会议启用基于位置的路由, 请参阅[会议的基于位置的路由](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx)。


