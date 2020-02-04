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
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中基于位置的路由的技术注意事项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-09_

规划基于位置的路由时，应考虑对以下方案的影响。

<div>

## <a name="disaster-recovery"></a>灾难恢复

在将主池故障转移到备份池以及将正常操作还原到主池的过程中，在灾难和恢复过程中始终强制执行基于位置的路由。

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

配置基于位置的路由会影响你部署与 Survivable 分支机构相关联的网关的位置的规划。 与你的 SBA 关联的网关必须与 Survivable 分支装置位于同一网络站点;否则，如果配置基于位置的路由，则不允许驻留在 Survivable 分支设备上的用户进行出站呼叫。 当 Survivable 分支设备和中心网站之间的 WAN 连接关闭时，基于位置的路由限制将保持强制实施。

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

