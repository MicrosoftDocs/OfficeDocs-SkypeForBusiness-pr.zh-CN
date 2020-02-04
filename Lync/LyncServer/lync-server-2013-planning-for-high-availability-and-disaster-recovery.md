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
ms.openlocfilehash: 79abf8b98252f3b05b899a9840e7a9c9a2e8096c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中规划高可用性和灾难恢复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-10-31_

与在 Lync Server 2010 中一样，Lync Server 2013 中大多数服务器角色的主高可用性方案都基于服务器冗余（通过池划分）。 如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。 这适用于前端服务器、边缘服务器、中介服务器和控制器。

Lync Server 2013 通过将服务器的地理 dispersement 引入两个数据中心来为前端池添加新的灾难恢复措施，以便在一个整个池或网站停机时提供服务的延续。

Lync Server 2013 还支持后端数据库的同步 SQL 镜像，从而增强了后端服务器高可用性。

本部分介绍这些主要的高可用性和灾难恢复功能，还介绍了为其他服务器角色执行高可用性和灾难恢复时可以采取的步骤。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的前端池灾难恢复](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Lync Server 2013 中的边缘服务器灾难恢复](lync-server-2013-edge-server-disaster-recovery.md)

  - [在 Lync Server 2013 中规划企业语音恢复能力](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Lync Server 2013 中实现灾难恢复的呼叫管理功能](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [在 Lync Server 2013 中为持久聊天服务器配置高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 都市站点恢复能力](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

