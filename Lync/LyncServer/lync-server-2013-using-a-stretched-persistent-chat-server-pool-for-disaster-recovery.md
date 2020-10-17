---
title: 使用拉伸的持久聊天服务器池进行灾难恢复
description: 使用延伸的持久聊天服务器池进行灾难恢复。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b83a7226f7b9a49a2676b6222505f53247bd5abf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548538"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="0128e-103">在 Lync Server 2013 中使用延伸的持久聊天服务器池进行灾难恢复</span><span class="sxs-lookup"><span data-stu-id="0128e-103">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0128e-104">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0128e-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0128e-105">持久聊天服务器的灾难恢复解决方案建立在延伸的持久聊天服务器池之上。</span><span class="sxs-lookup"><span data-stu-id="0128e-105">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="0128e-106">这类似于 Lync Server 2010 中的大都市站点恢复能力;但是，不要求对扩展虚拟局域网 (VLAN) 。</span><span class="sxs-lookup"><span data-stu-id="0128e-106">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="0128e-107">通过拉伸持久聊天服务器池，实际上是在拓扑中以逻辑方式配置一个池，但实际上是将池中的服务器放在两个不同的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="0128e-107">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="0128e-108">以相同的方式为数据库配置 SQL Server 镜像，并在同一数据中心中部署数据库和镜像。</span><span class="sxs-lookup"><span data-stu-id="0128e-108">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="0128e-109">需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。</span><span class="sxs-lookup"><span data-stu-id="0128e-109">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="0128e-110">这是在灾难恢复期间用于故障转移的备份数据库。</span><span class="sxs-lookup"><span data-stu-id="0128e-110">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="0128e-111">有关如何配置 SQL Server 镜像以实现高可用性的详细信息，请参阅 [Lync server 2013 中的 SQL server 镜像](lync-server-2013-sql-server-mirroring.md)。</span><span class="sxs-lookup"><span data-stu-id="0128e-111">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="0128e-112">有关故障转移数据库以实现灾难恢复的详细信息，请参阅 [在 Lync server 2013 中为持久聊天服务器主数据库设置 Sql Server 日志传送](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) ，并在 [lync server 2013 中的主镜像和日志传送辅助数据库之间设置 Sql server 日志传送](lync-server-2013-set-up-log-shipping-secondary-database.md)。</span><span class="sxs-lookup"><span data-stu-id="0128e-112">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

