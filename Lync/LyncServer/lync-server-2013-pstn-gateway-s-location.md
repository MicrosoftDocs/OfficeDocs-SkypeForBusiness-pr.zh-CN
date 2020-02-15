---
title: Lync Server 2013： PSTN 网关的位置
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
ms.openlocfilehash: b3ff0e3ea426a8f3aa053b057b616148a42ad409
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 网关的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-09_

通过 PSTN 网关和 Pbx 路由的呼叫可能需要基于位置的路由限制，具体取决于此类系统的位置。 可以基于每个中继的粒度启用基于位置的路由。

基于位置的路由在中继上启用时引入了以下一组规则：

  - 在每个中继基础上启用基于位置的路由时，在该中继上定义的规则将仅应用于通过该中继路由的呼叫。

  - 为了防止 PSTN 费绕过 PSTN 网关所在的网络站点之外的网络站点进行呼叫，基于位置的路由引入了网络站点与给定中继的关联。 这将定义允许呼叫路由到给定中继的网络站点。

可以通过两种方式为基于位置的路由启用中继：

  - 为发出对 PSTN 的呼叫的 PSTN 网关定义中继。 由这种类型的中继路由的传入呼叫将仅路由到与中继位于同一网络站点内的终结点。

  - 中继是为中介服务器对等方定义的，它不会向 PSTN 和服务用户提供静态位置（即 PBX 电话）中的旧版电话的传出呼叫。 对于此特定配置，由这种类型的中继路由的所有传入呼叫都将被视为来自与中继相同的网络站点。 来自 PBX 用户的呼叫将与与中继位于同一网络站点的 Lync 用户具有相同的基于位置的路由强制实施。 如果位于不同网络站点的两个 PBX 系统通过 Lync Server 连接，基于位置的路由将允许从一个网络站点中的一个 PBX 终结点路由到其他网络站点中的另一个 PBX 终结点。 此方案不会被基于位置的路由阻止。 除了此方案和相同位置中的 Lync 用户的类似方式之外，与此配置连接到中介服务器对等方的终结点可以在不将呼叫路由到 PSTN （i）的其他中介服务器对等方发出或接收呼叫。e. 连接到不同 PBX 的终结点），而不管中介服务器对等端与之关联的网络站点。 涉及 PSTN 终结点的所有入站呼叫、出站呼叫、呼叫转移和呼叫转接将受基于位置的路由的制约，仅使用定义为此中介服务器对等的本地的 PSTN 网关。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中基于位置的路由指南](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

