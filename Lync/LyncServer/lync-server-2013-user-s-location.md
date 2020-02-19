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
ms.openlocfilehash: d18ef5092f0506951dd9b431c6a44945b87b7f92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Lync Server 2013 中的用户位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-09_

基于位置的路由利用了在 Lync Server 中定义的、由 E9-1-1、CAC 和媒体旁路使用的相同网络区域、站点和子网，以应用呼叫路由限制以防止 PSTN 收费旁路。 用户的位置由用户的 Lync 终结点的连接的 IP 子网决定。 每个 IP 子网都与一个网络站点相关联，该站点聚合到由管理员定义的网络区域中。 基于位置的路由根据用户的网络站点强制实施。

基于位置的路由规则是按每个网络站点应用的，这意味着一组给定的规则将应用于为位于同一网络站点中的基于位置的路由启用的所有终结点。 管理员可以将基于位置的路由应用到需要它的网络站点。

可以在每个网络站点上定义语音路由策略，以定义应由位于网络站点中的所有用户用来呼叫 PSTN 电话号码的特定 PSTN 网关。 当用户位于启用了基于位置的路由的网络站点中时，此类语音路由策略将优先于由用户语音策略定义的路由，并且它将阻止通过其他已启用的 PSTN 网关路由呼叫基于位置的路由。 当 Lync 用户发出 PSTN 呼叫时，用户的语音策略将确定是否可以授权用户发出呼叫。 如果用户的语音策略允许用户发出呼叫，则基于位置的路由将确定呼叫应传出的 PSTN 网关。 基于位置的路由根据用户的位置做出此决定。

可以通过以下方式对用户位置进行分类：

  - 用户所在的已知网络站点启用了基于位置的路由，而其执行的（直接向内拨号）号码在位于同一网络站点（即 office）的 PSTN 网关上终止。 出站呼叫的路由将通过用户所在的网络站点的语音路由策略。 对用户的传入 PSTN 呼叫将路由到位于与 PSTN 网关相同的网络站点中的终结点。

  - 用户位于与 PSTN 网关所在的网络站点不同的已知网络站点中。 （即，向另一个公司办公室旅行的用户）。 出站呼叫的路由将使用用户所在的网络站点的语音路由策略。 对用户的传入 PSTN 呼叫不会路由到位于与 PSTN 网关不同的其他站点的终结点，从而防止 PSTN 收费绕过。

  - 当用户位于 Lync Server 部署无法识别的网络站点中时，出站呼叫的路由将基于为用户分配的语音策略，而不是绑定到基于位置的路由限制的 PSTN 网关。 传入 PSTN 呼叫不会路由到位于未知网络站点中的终结点，从而防止 PSTN 收费绕过。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中基于位置的路由指南](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

