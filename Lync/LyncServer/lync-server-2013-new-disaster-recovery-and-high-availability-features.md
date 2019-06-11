---
title: Lync Server 2013：新的灾难恢复和高可用性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93e2265d401c6dca16f5c00c339fbdc893aba0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Lync Server 2013 中新的灾难恢复和高可用性功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-20_

与 Lync Server 2010 中一样, Lync Server 2013 的主高可用性 (HA) 方案基于服务器冗余 (通过池划分)。 如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。 这适用于前端服务器、边缘服务器、中介服务器和控制器。

Lync Server 2013 通过使你能够对位于两个数据中心的前端池进行配对来添加新的灾难恢复措施。 如果其中一个配对的池出现故障, 则管理员可以将该池中的用户故障转移到该池中的另一个池, 以便提供服务的延续。 此功能不需要昂贵的网络或硬件解决方案, 例如存储网络或共享磁盘。

Lync Server 2013 还添加了后端服务器高可用性。 这是一个可选拓扑, 你可以在其中部署前端池的两个后端服务器, 并为在后端服务器上运行的所有 Lync 数据库设置同步 SQL 镜像。 你可以选择是否为镜像部署见证。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

