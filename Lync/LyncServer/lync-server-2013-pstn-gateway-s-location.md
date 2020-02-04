---
title: Lync Server 2013：PSTN 网关的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d15589f37b18015f91e3717e19415d5ade6b6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013 中 PSTN 网关的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-09_

通过 PSTN 网关和 Pbx 路由的通话可能需要基于位置的路由限制，具体取决于此类系统的位置。 基于位置的路由可以按每个干线的粒度来启用。

基于位置的路由在主干上启用时引入以下规则集：

  - 在每个主干基础上启用基于位置的路由时，在该主干上定义的规则将仅应用于通过该主干路由的呼叫。

  - 为了防止 PSTN tolls 绕过从网络站点（PSTN 网关所在的网络站点不同）的网络站点进行调用的位置，基于位置的路由引入了网络站点与给定主干的关联。 这定义了允许呼叫路由到给定中继的网络站点。

可以通过以下两种方式为基于位置的路由启用中继：

  - 为中继定义将呼叫发出到 PSTN 的 PSTN 网关。此类型的中继路由的传入呼叫只能路由到位于与中继相同的网络站点中的终结点。

  - 主干是针对中介服务器对等方定义的，它不会向在静态位置（即 PBX 手机）中使用旧式电话的 PSTN 和服务用户传出呼叫。 对于此特殊配置，此类型的中继路由的传入呼叫将视为来自与中继相同的网络站点。 来自 PBX 用户的呼叫将与与主干的同一网络站点中的 Lync 用户具有相同的基于位置的路由强制。 如果位于单独网络站点的两个 PBX 系统通过 Lync Server 连接，基于位置的路由将允许从一个网络站点中的一个 PBX 终结点路由到另一个网络站点中的另一个 PBX 终结点。 此方案不会被基于位置的路由阻止。 除了此方案以及与同一位置的 Lync 用户类似的情况下，连接到具有此配置的中介服务器对等的终结点将能够在不将调用路由到 PSTN （i）的其他中介服务器对等上进行或接收呼叫。e. 连接到其他 PBX 的终结点，与中介服务器对等关联的网络站点无关。 所有入站呼叫、出站呼叫、呼叫转接和涉及 PSTN 终结点的转接将根据基于位置的路由，仅使用定义为本中介服务器对等的本地的 PSTN 网关。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中基于位置的路由指南](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

