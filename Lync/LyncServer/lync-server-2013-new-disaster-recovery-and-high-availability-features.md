---
title: Lync Server 2013：新的灾难恢复和高可用性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33a9039c65d059042d9eb93c9d5437a00ebff266
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512559"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Lync Server 2013 中的新的灾难恢复和高可用性功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-20_

与 Lync Server 2010 中一样，Lync Server 2013 的主要高可用性 (HA) 方案基于通过池进行的服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。 这适用于前端服务器、边缘服务器、中介服务器和控制器。

Lync Server 2013 通过使您能够对位于两个数据中心的前端池进行配对，从而添加了新的灾难恢复措施。 如果其中一个配对池不可用，则管理员可将该池中的用户故障转移到配对中的其他池，以继续提供服务。 此功能无需昂贵的网络或硬件解决方案，如存储网络或共享磁盘。

Lync Server 2013 还添加了后端服务器高可用性。 这是一个可选拓扑，可在其中为前端池部署两台后端服务器，并为在后端服务器上运行的所有 Lync 数据库设置同步的 SQL 镜像。 您可选择是否为镜像部署见证。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

