---
title: Lync Server 2013：基于位置的路由的技术注意事项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e672e35771ec3cc4ecbd3655af350231f1583b52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中基于位置的路由的技术注意事项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-09_

在规划基于位置的路由时，应考虑对以下方案的影响。

<div>

## <a name="disaster-recovery"></a>灾难恢复

在将主池故障转移到备份池以及将正常操作还原到主池的过程中，在灾难和恢复过程中始终强制实施基于位置的路由。

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

配置基于位置的路由会影响规划与 Survivable 分支设备关联的网关的部署位置。 与您的 SBA 关联的网关必须位于与您的 Survivable 分支装置相同的网络站点中;否则，如果配置基于位置的路由，则不允许驻留在 Survivable 分支设备上的用户发出出站呼叫。 当您的 Survivable 分支设备与中心站点之间的 WAN 连接关闭时，基于位置的路由限制仍将强制实施。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

