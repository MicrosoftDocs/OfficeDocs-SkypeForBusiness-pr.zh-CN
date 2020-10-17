---
title: 配置持久聊天服务器以实现高可用性和灾难恢复
description: 配置持久聊天服务器以实现高可用性和灾难恢复。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13935f2ec690deb7f896c13d185680ce1122a892
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544828"
---
# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="32ee6-103">在 Lync Server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="32ee6-103">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32ee6-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="32ee6-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="32ee6-105">Lync Server 2013、持久聊天服务器服务使用 *延伸池* 配置进行灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="32ee6-105">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="32ee6-106">延伸池是一个池，它具有在两个物理数据中心之间分布但位于单个逻辑 Lync 服务器站点内的计算机。</span><span class="sxs-lookup"><span data-stu-id="32ee6-106">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="32ee6-107">本部分内容</span><span class="sxs-lookup"><span data-stu-id="32ee6-107">In This Section</span></span>

  - [<span data-ttu-id="32ee6-108">Lync Server 2013 中持久聊天服务器所需的资源</span><span class="sxs-lookup"><span data-stu-id="32ee6-108">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="32ee6-109">使用拓扑生成器在 Lync Server 2013 中配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="32ee6-109">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="32ee6-110">在 Lync Server 2013 中使用延伸的持久聊天服务器池进行灾难恢复</span><span class="sxs-lookup"><span data-stu-id="32ee6-110">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="32ee6-111">Lync Server 2013 中的 SQL Server 镜像</span><span class="sxs-lookup"><span data-stu-id="32ee6-111">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="32ee6-112">在 Lync Server 2013 中为持久聊天服务器主数据库设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="32ee6-112">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="32ee6-113">在 Lync Server 2013 中的主镜像和日志传送辅助数据库之间设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="32ee6-113">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

