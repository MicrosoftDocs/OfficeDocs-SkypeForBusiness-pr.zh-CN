---
title: 规划基于位置的路由Skype for Business
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
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: 规划基于位置的路由，Skype for Business Server 企业语音同时响铃和委派的交互，以及支持基于位置的路由方案。
ms.openlocfilehash: 64757f389278dbb5899146ea4fd0f4e201311127
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013746"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>规划基于位置的路由Skype for Business

规划基于位置的路由，Skype for Business Server 企业语音同时响铃和委派的交互，以及支持基于位置的路由方案。

Location-Based路由可以基于呼叫各方的位置限制 VoIP 终结点和 PSTN 终结点之间的呼叫路由。 Location-Based路由是一项呼叫管理功能，用于控制呼叫路由方式Skype for Business Server。 它强制执行呼叫授权规则，以确定是否可以基于呼叫者的地理位置将呼叫路由Skype for Business PBX 或 PSTN 终结点。

Location-Based路由引入了一组新规则，可修改国家/和国际 PSTN 呼叫的路由，以防止收费绕路问题。 Location-Based路由提供了将这些规则范围设定为仅特定区域、特定网关或特定用户集的灵活性。

以下方案说明了路由可以强制实施Location-Based类型的限制：

- Egress 呼叫 - Location-Based 路由可以强制传出呼叫进入 PSTN 网关，该网关位于呼叫者所在的同一区域，以防止 PSTN 收费绕路，从而阻止呼叫进入位于与呼叫者位于不同地区的 PSTN 网关。

- 传入呼叫 - Location-Based如果路由传入呼叫的 PSTN 网关与被呼叫的 Skype for Business 用户不在同一区域，则路由路由可以阻止传入 PSTN 呼叫响铃 Skype for Business 终结点。

- 未知区域 - Location-Based 路由限制位于未确定位置（即从 Internet 连接或位于未知区域) ）的用户的传入和传出 PST (N 呼叫。

- 国际区域 - Location-Based如果找不到用户位置的本地网关，则路由将强制通过国际 PSTN 网关路由传出呼叫。

## <a name="guidance-for-where-to-apply-location-based-routing"></a>应用路由Location-Based指南

Location-Based路由可以应用于用户的终结点网络站点位置或 PSTN 网关的网络站点位置。 本主题提供有关如何应用Location-Based路由的指南。

### <a name="applying-location-based-routing-at-the-users-location"></a>在Location-Based位置应用路由

Location-Based路由利用 E9-1-1、CAC 和媒体旁路使用的 Skype for Business Server 中定义的相同网络区域、站点和子网应用呼叫路由限制，以防止 PSTN 收费绕路。 用户的位置由用户的 Skype for Business 终结点的 IP 子网 (连接) IP 子网。 每个 IP 子网都与一个网络站点关联，网络站点聚合到管理员定义的网络区域。 Location-Based基于用户的网络站点强制执行路由。

Location-Based路由规则基于每个网络站点应用，这意味着给定的一组规则将应用于为位于同一网络站点内的 Location-Based Routing 启用的所有终结点。 管理员可以将Location-Based路由应用于需要它的网络站点。

可以基于每个网络站点定义语音路由策略，以定义特定 PSTN 网关，网络站点中的所有用户都应使用该网关呼叫 PSTN 电话号码。 当用户位于启用了 Location-Based 路由的网络站点中时，此类语音路由策略将优先于用户的语音策略定义的路由，并且它将阻止通过启用了 Location-Based 路由的其他 PSTN 网关路由呼叫。 当用户Skype for Business PSTN 呼叫时，用户的语音策略将确定用户是否可以获得发出呼叫的授权。 如果用户的语音策略允许用户发出呼叫，则路由Location-Based确定呼叫应从哪个 PSTN 网关发出。 Location-Based路由根据用户的位置做出此决定。

用户位置可以按以下方式分类：

- 用户位于启用了 Location-Based 路由的已知网络站点中，其 DID (外线直拨拨号) 号码终止于位于相同网络站点 (即 office) 中的 PSTN 网关上。 出站呼叫的路由是通过用户所在的网络站点的语音路由策略。 传入到用户的 PSTN 呼叫将路由到与 PSTN 网关位于同一网络站点中的终结点。

- 用户位于与 PSTN 网关所在的网络站点不同的已知网络站点中。  (，即用户前往另一个公司办事处) 。 出站呼叫的路由将采用用户所在的网络站点的语音路由策略。 传入到用户的 PSTN 呼叫不会路由到位于与 PSTN 网关不同的站点中的终结点，以防止 PSTN 收费绕路情况。

- 当用户位于 Skype for Business Server 部署未知的网络站点中时，出站呼叫的路由将基于分配给用户的语音策略到未绑定到 Location-Based 路由限制的 PSTN 网关。 传入 PSTN 呼叫不会路由到位于未知网络站点中的终结点，以防止 PSTN 收费绕路情况。

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>应用Location-Based PSTN 网关位置的路由

通过 PSTN 网关和 PBX 路由的呼叫可能需要Location-Based路由限制，具体取决于此类系统的位置。 Location-Based可以按每个中继的粒度启用路由。

Location-Based在中继上启用时，路由将引入以下规则集：

- 当Location-Based中继启用路由时，该中继上定义的规则将仅应用于通过该中继路由的呼叫。

- 为防止 PSTN 收费绕路情况，即呼叫来自与 PSTN 网关所在的网络站点不同的网络站点，Location-Based Routing 引入了网络站点与给定中继的关联。 这将定义允许将呼叫路由到给定中继的网络站点。

可以通过两种方式为Location-Based启用中继：

- 为将呼叫输出到 PSTN 的 PSTN 网关定义中继。 此类型的中继路由的传入呼叫将仅路由到位于与中继相同的网络站点内的终结点。

- 中继为中介服务器对等方定义，该对等方不会将呼叫输出到 PSTN，并且为静态位置（例如 PBX 电话）中具有旧电话 (的用户提供服务) 。 对于此特定配置，此类型的中继路由的所有传入呼叫均被视为来自与中继相同的网络站点。 来自 PBX 用户的呼叫将Location-Based中继Skype for Business位于同一网络站点中的用户执行路由。 如果位于不同网络站点中的两个 PBX 系统通过 Skype for Business Server 进行连接，Location-Based 路由将允许从一个网络站点中的一个 PBX 终结点路由到另一个网络站点中的另一个 PBX 终结点。 此方案不会被路由Location-Based阻止。 除此方案外，与同一位置的 Skype for Business 用户类似，连接到具有此配置的中介服务器对等方终结点将能够拨打或接收其他中介服务器对等方向 PSTN (即连接到不同 PBX) 的终结点，无论中介服务器对等方位于哪个网络站点关联。 涉及 PSTN 终结点的所有入站呼叫、出站呼叫、呼叫转移和呼叫转接将受基于位置的路由的限制，以使用定义为此类中介服务器对等方本地的 PSTN 网关。

## <a name="scenarios-for-location-based-routing"></a>路由Location-Based方案

Location-Based路由在下列方案中路由呼叫时，将应用以下一般规则。

### <a name="outgoing-calls"></a>传出呼叫

启用了路由路由的用户的出Location-Based呼叫的路由受用户终结点的网络位置影响。 下表说明了路由Location-Based路由如何影响出站呼叫的路由，具体取决于呼叫者的终结点的位置。

**向 PSTN 发出出站呼叫的呼叫者**

|&nbsp;|位于启用了路由路由的网络站点中的Location-Based终结点|位于未知网络站点或未启用网络路由的用户Location-Based终结点|
|:-----|:-----|:-----|
|出站呼叫的授权   |根据用户的语音策略授权呼叫   |根据用户的语音策略授权呼叫   |
|出站呼叫路由   |根据网络站点的语音路由策略路由呼叫   |呼叫根据用户的语音策略进行路由，并且仅通过未启用路由Location-Based中继 (路由)    |

### <a name="incoming-calls"></a>传入呼叫

向启用了路由路由Location-Based传入呼叫的路由取决于用户终结点的位置。 传入呼叫的路由以下列方式受到影响。 如果用户对位于启用了 Location-Based 路由的网络站点中的终结点有传入呼叫，并且该终结点与 PSTN 网关位于同一网络站点中，将路由该呼叫。 如果用户对位于启用了 Location-Based 路由的网络站点中的终结点有传入呼叫，并且该终结点位于与 PSTN 网关不同的网络站点中，则将不会路由该呼叫。 如果用户没有与发出传入呼叫的 PSTN 网关位于同一网络站点中的终结点，则传入呼叫将直接路由到用户的语音邮件，并且未接来电通知将发送给被叫方。

将继续强制实施启用了 Location-Based Routing 的用户的呼叫转发设置，但是，转发的呼叫将受Location-Based路由限制的限制。

下表说明了呼叫Location-Based路由如何影响入站呼叫的路由，具体取决于被叫方终结点的位置。 PSTN 网关的网络站点已启用路由Location-Based，Location-Based路由仅允许将 PSTN 呼叫路由到同一网络站点内的终结点。

**从 PSTN 接收入站呼叫的被叫方**

|&nbsp;|与 PSTN 网关位于同一网络站点中的被叫方终结点|被叫方终结点与 PSTN 网关不在同一网络站点中|被叫方终结点位于未知网络站点中或未启用Location-Based路由|
|:-----|:-----|:-----|:-----|
|入站 PSTN 呼叫的路由   |传入呼叫将路由到被叫方终结点   |传入呼叫未路由到被叫方终结点   |传入呼叫未路由到被叫方终结点   |

### <a name="call-transfers-and-call-forwarding"></a>呼叫转移和呼叫转接

当涉及 PSTN 终结点时，Location-Based 路由将分析呼叫者终结点的位置，以及将呼叫转接到 (即转接目标) 的终结点。 Location-Based路由根据两个终结点的位置确定是否应转接呼叫。

下表说明了 PSTN 终结点Skype for Business呼叫中呼叫用户的情况，Skype for Business用户将呼叫转接给另一Skype for Business用户。 根据被叫方终结点的网络站点位置，Location-Based路由会影响呼叫转接的路由。

**发起呼叫转接**

|发起呼叫转接的用户|目标终结点与发起呼叫转接的用户位于相同的网络站点中|目标终结点与发起呼叫转接的用户位于不同的网络站点中|目标终结点位于未知网络站点中，或网络站点未启用Location-Based路由
|:-----|:-----|:-----|:-----|
|Skype for Business用户   |允许呼叫转接   |不允许呼叫转接   |不允许呼叫转接   |

例如：Skype for Business PSTN 终结点的呼叫中的用户将呼叫转接到Skype for Business网络站点中的另一个呼叫用户。 在这种情况下，允许呼叫转移。

下表演示了在呼叫Skype for Business用户与另一个 Skype for Business 用户进行呼叫，其中一个用户将呼叫转接到 PSTN 终结点的方案。 根据呼叫转接到的用户的位置，下表详细说明了路由Location-Based呼叫有何影响。

**呼叫转接到 PSTN 终结点**

|呼叫转接终结点目标|Skype for Business网络站点中的用户|Skype for Business网络站点中的用户|未启用Skype for Business路由的未知网络站点或网络站点中的一个或多个Location-Based用户|
|:-----|:-----|:-----|:-----|
|PSTN 终结点   |转接用户的站点语音路由策略允许的呼叫转接   |转接用户的站点语音路由策略允许的呼叫转接   |转接用户的语音策略仅允许通过未启用呼叫路由的中继进行呼叫转接Location-Based转接   |

例如：Skype for Business同一网络站点中的另一个 Skype for Business 用户在呼叫中将呼叫转接到 PSTN 终结点，允许呼叫转移。

### <a name="simultaneous-ringing"></a>同时响铃

当被叫方启用了同时响铃时，Location-Based路由将分析呼叫方的位置和被叫方终结点，以确定是否应该路由呼叫。

下表说明了配置了同时响铃的用户，同时响铃目标为相同网络站点、不同网络站点或未知网络站点中的用户。

****

|传入 PSTN 呼叫|与被叫方位于同一网络站点中|位于与被叫方不同的网络站点中|位于未知网络站点中或未启用Location-Based路由|
|:-----|:-----|:-----|:-----|
|Skype for Business用户   |允许同时响铃   |不允许同时响铃   |不允许同时响铃   |

下表说明了来自 Skype for Business 用户的呼叫 (即 Skype for Business 呼叫者) 在同一网络站点、不同网络站点中或来自未知网络站点。 被叫方具有 PSTN 终结点 (即，) 配置为同时响铃目标。 在此方案中，Location-Based路由将确定是否应该将呼叫路由到同时响铃目标 (即被叫) 的移动电话。

****

|同时响铃目标|与被叫方位于同一网络站点中|位于与被叫方不同的网络站点中|位于未知网络站点中或未启用Location-Based路由|
|:-----|:-----|:-----|:-----|
|PSTN 终结点   |通过呼叫者的站点语音路由策略允许同时响铃   |通过呼叫者的站点语音路由策略允许同时响铃   |通过呼叫者的语音策略允许同时响铃到未启用路由Location-Based中继   |

### <a name="skype-for-business-cumulative-update-4"></a>Skype for Business累积更新 4

使用累积更新 4，你将看到以下内容：

- Location-Based路由将继续通过语音策略启用，包括Skype for Business客户端。

- 移动Skype for Business的呼叫行为将基于它们是否启用了 Location-Based 路由和通信客户端。 这设计为静态，但在某些情况下，可能会努力将 Skype for Business 移动客户端与本地 PSTN 网关关联，并允许某些行为（如升级）

- 无论使用何种操作系统，Skype for Business移动客户端都应具有相同的功能。

下表将分步说明累积更新 4 后的一些方案：

|Location-Based路由用户|其他方|Action|结果|
|:-----|:-----|:-----|:-----|
|Skype for Business移动   |PSTN   |Skype for Business移动接收传入 PSTN 呼叫。   |呼叫通过"通过工位呼叫" (CvW) 路由，而不是通过 VoIP 路由。   |
|Skype for Business移动   |PSTN   |Skype for Business移动进行传出 PSTN 呼叫。   |呼叫通过 CvW 而不是 VoIP 进行路由。   |
|Skype for Business移动   |PSTN   |Skype for Business移动位于 PSTN 呼叫中。 Skype for Business然后，移动将呼叫升级为其他用户或联系人。   |如果用户或联系人位于 PSTN 网关通道的本地，则通过 VoIP 路由呼叫。  <br/> 如果用户或联系人与 PSTN 网关通道是远程的，则通过 CvW 路由呼叫。  <br/> 如果无法通过 PSTN 访问目标用户，则呼叫将失败。  <br/> 如果目标联系人是 CAA 自动助理 (会议) ，将阻止呼叫。   |
|Skype for Business移动   |Skype for Business客户端或联盟用户   |移动Skype for Business向另一个客户端或联盟Skype for Business发起语音呼叫。   |呼叫通过 VoIP 完成。   |
|Skype for Business移动   |Skype for Business客户端或联盟用户   | Skype for Business客户端或联盟用户向移动Skype for Business路由Location-Based发起语音呼叫。  |呼叫通过 VoIP 完成。   |
|Skype for Business移动   |Skype for Business客户端或联盟用户   |客户端Skype for Business联盟用户正在对移动用户进行 VoIP Skype for Business呼叫。 任一方升级为Skype for Business联盟用户。   |呼叫通过 VoIP 完成。   |
|Skype for Business移动   |联合用户   |联盟用户正在与移动Skype for Business路由Location-Based进行语音呼叫;Skype for Business方升级至 PSTN 用户。   |呼叫被阻止。   |
|Skype for Business移动   |联合用户   |联盟用户正在与移动Skype for Business路由用户进行 VoIP Location-Based呼叫;任一方升级至 CAA 联系人。   |升级的呼叫被阻止，并包含相应的错误消息。   |
|Skype for Business移动   |联合用户   |联盟用户正在与 Skype for Business Mobile Location-Based 路由用户进行 VoIP 呼叫，联盟用户升级至 PSTN 用户。   |将允许或禁止升级，Location-Based联盟用户的路由。 Skype for Business移动Location-Based路由用户的应用程序不执行任何操作。   |

### <a name="delegation"></a>委派

以下方式Skype for Business路由Location-Based中的委派功能：

- 当启用了 Location-Based 路由的代理人代表经理发出呼叫时，代理的语音策略用于授权呼叫，并且代理人的站点语音路由策略将用于路由呼叫

- 对于呼叫经理的传入 PSTN 呼叫，适用于呼叫转接或同时响铃的相同规则将适用，如呼叫转接和同时响铃主题中所述。

- 当代理将 PSTN 终结点设置为同时响铃目标时，对于呼叫经理的传入呼叫，与传入中继关联的站点的语音路由策略将用于将呼叫路由到代理人的 PSTN 终结点。

- 对于委派，建议经理及其关联的代理人通常位于同一网络站点中。

## <a name="other-planning-considerations"></a>其他规划注意事项

规划Location-Based路由时，应考虑对以下方案的影响。

### <a name="disaster-recovery"></a>灾难恢复

在从主池故障转移到备份池期间，以及将正常操作还原到主池时，在灾难恢复过程中Location-Based始终强制实施路由。

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

配置Location-Based路由会影响规划与 Survivable Branch 设备关联的网关的部署位置。 与 SBA 关联的网关必须位于与 Survivable Branch Appliance 相同的网络站点中;否则，如果配置了路由，则不允许 Survivable Branch Appliance 上Location-Based出站呼叫。 当 Survivable Branch Appliance 和中央站点之间的 WAN 连接关闭时，Location-Based路由限制仍然强制实施。

## <a name="client-and-server-support-for-location-based-routing"></a>客户端和服务器对路由Location-Based支持

Location-Based路由由 Skype for Business Server。 Skype for Business Server标识用户从企业网络内部进行连接的网络站点。 由于远程用户位于企业网络外部，因此他们的位置被视为未知。

### <a name="server-support"></a>服务器支持

Location-Based路由要求Skype for Business Server拓扑中所有前端池和 Standard Edition服务器上部署 Lync Server 2013 CU1。 如果未安装这些版本的服务器，则不能完全强制实施基于位置的路由限制。

下表标识了支持路由的服务器角色和版本Location-Based组合。

****

|池版本|中介服务器版本|支持|
|:-----|:-----|:-----|
|Skype for Business Server或 Lync Server 2013 2013 年 2 月累积更新   |Skype for Business Server或 Lync Server 2013 2013 年 2 月累积更新   |是   |
|Skype for Business Server或 Lync Server 2013 2013 年 2 月累积更新   |Lync Server 2013   |否   |
|Skype for Business Server或 Lync Server 2013 2013 年 2 月累积更新   |Lync Server 2010   |否   |
|Skype for Business Server或 Lync Server 2013 2013 年 2 月累积更新   |Office Communications Server 2007 R2   |否   |
|Lync Server 2013   |任意   |否   |
|Lync Server 2010   |任意   |否   |
|Office Communications Server 2007 R2   |任意   |否   |

### <a name="client-support"></a>客户端支持

下表标识了路由Location-Based客户端。

****

|客户端类型|支持|详细信息|
|:-----|:-----|:-----|
|Skype for Business   |是   ||
|Lync 2013   |是   ||
|Lync 2010   |是   ||
|Office Communicator 2007 R2   |否   ||
|Lync Phone Edition   |是   ||
|Lync Attendant   |是   ||
|Lync for Windows 8   |否   ||
|Lync Mobile 2013   |否   |如果启用了路由的用户使用 Lync Mobile 2013 客户端，则必须Location-Based VoIP。   |
|Lync Mobile 2010   |是   ||

> [!NOTE]
> 若要禁用 Skype for Business 客户端的 VoIP，请为启用了"Location-Based 路由的所有用户分配一个禁用 IP 音频/视频设置的移动策略。 有关移动策略的更多详细信息，请参阅 [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)。

## <a name="capabilities-not-supported-by-location-based-routing"></a>路由不支持Location-Based功能

Location-Based路由不适用于以下类型的交互。 Location-Based使用这些功能与 PSTN Skype for Business时，不强制使用路由。

- PSTN 拨入会议

- 通过响应组传入和传出 PSTN 呼叫

- 通过呼叫管理来呼叫呼叫的 PSTN 呼叫的呼叫管理或检索

- 传入到通知服务的 PSTN 呼叫

- 通过组内呼叫接听检索到的传入 PSTN 呼叫

若要Location-Based路由规则强制遵循以下列表中的交互类型，必须启用Location-Based路由：

- 从会议拨出的 PSTN

- 从点对点音频对话升级至涉及 PSTN 终结点的会议

- 涉及 PSTN 终结点的咨询转接

若要启用Location-Based路由，请参阅会议基于 [位置的路由](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing)。