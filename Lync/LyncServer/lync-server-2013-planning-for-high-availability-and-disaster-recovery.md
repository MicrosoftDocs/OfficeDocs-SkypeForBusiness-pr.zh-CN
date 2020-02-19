---
title: Lync Server 2013：规划高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ba7e58f29bb4e54972804fbe338c2e1345e91e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中规划高可用性和灾难恢复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-31_

与 Lync Server 2010 中一样，Lync Server 2013 中大多数服务器角色的主要高可用性方案都基于通过池进行的服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。 这适用于前端服务器、边缘服务器、中介服务器和控制器。

Lync Server 2013 为前端池添加了新的灾难恢复措施，具体方法是将服务器的地理位置 dispersement 引入两个数据中心，以在一个整体池或站点停机时提供服务的延续。

Lync Server 2013 还通过支持针对后端数据库的同步 SQL 镜像，从而增强了后端服务器高可用性。

本节对这些主要的高可用性和灾难恢复功能进行了说明，还介绍了为其他服务器角色实现高可用性和灾难恢复所需执行的步骤。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的前端池灾难恢复](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Lync Server 2013 中的边缘服务器灾难恢复](lync-server-2013-edge-server-disaster-recovery.md)

  - [在 Lync Server 2013 中规划企业语音恢复能力](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Lync Server 2013 中用于灾难恢复的呼叫管理功能](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [在 Lync Server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 大都市站点恢复能力](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

