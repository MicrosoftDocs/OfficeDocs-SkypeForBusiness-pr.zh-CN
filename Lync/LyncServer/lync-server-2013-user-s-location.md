---
title: Lync Server 2013：用户的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9754b75b941944a445da33750190b9347aeb9313
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Lync Server 2013 中用户的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-09_

基于位置的路由利用由 E9 使用的 Lync Server 中定义的相同网络区域、网站和子网，以便应用呼叫路由限制以防止 PSTN 免绕过。 用户的位置由用户的 Lync 终结点连接的 IP 子网确定。 每个 IP 子网都与一个网络站点相关联，它们将聚合到由管理员确定的网络区域中。 基于位置的路由基于用户的网络站点强制实施。

基于位置的路由规则是针对每个网络站点应用的，这意味着给定的一组规则将应用于为位于同一网络站点内的基于位置的路由启用的所有终结点。 管理员可以将基于位置的路由应用于需要它的网络站点。

可以在每个网络站点上定义语音路由策略，以定义应由网络站点内的所有用户用于呼叫 PSTN 号码的特殊 PSTN 网关。 当用户位于为基于位置的路由启用的网络站点中时，此类语音路由策略将优先于用户的语音策略所定义的路由，并且它将阻止通过其他 PSTN 网关启用呼叫路由基于位置的路由。 当 Lync 用户发出 PSTN 呼叫时，用户的语音策略确定是否可以授权用户进行呼叫。 如果用户的语音策略允许用户进行呼叫，则基于位置的路由确定呼叫应传出的 PSTN 网关。 基于位置的路由根据用户的位置进行此确定。

用户位置可以通过以下方式进行分类：

  - 用户位于为基于位置的路由启用的已知网络站点，并且其已完成（直接拨入式拨号）号码将在位于同一网络站点（即 office）的 PSTN 网关上终止。 出站呼叫通过用户所在的网络站点的语音路由策略进行路由。 发往用户的传入 PSTN 呼叫将路由到与 PSTN 网关位于相同网络站点中的终结点。

  - 用户所在的已知网络站点不同于 PSTN 网关所在的网络站点。（例如，用户前往另一公司办事处出差。）出站呼叫使用用户所在的网络站点的语音路由策略进行路由。发往用户的传入 PSTN 呼叫不会路由到所在站点与 PSTN 网关不同的终结点，从而防止 PSTN 收费绕路情形。

  - 当用户位于 Lync Server 部署未知的网络网站中时，出站呼叫的路由将基于分配给用户的语音策略，而不是绑定到基于位置的路由限制的 PSTN 网关。 传入 PSTN 呼叫不会路由到位于未知网络站点内的终结点，从而防止 PSTN 收费绕路情形。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中基于位置的路由指南](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

