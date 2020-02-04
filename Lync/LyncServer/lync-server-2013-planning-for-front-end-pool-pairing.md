---
title: Lync Server 2013：规划前端池配对
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85f6e19f3aa74c09a522e737d1223095f17d7c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="bf262-102">在 Lync Server 2013 中规划前端池配对</span><span class="sxs-lookup"><span data-stu-id="bf262-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf262-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bf262-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bf262-104">为了获得 Lync Server 2013 中的最佳灾难恢复能力，请跨两个地理位置分散的网站部署前端池对。</span><span class="sxs-lookup"><span data-stu-id="bf262-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="bf262-105">每个网站都包含一个与另一个网站中的对应前端池配对的前端池。</span><span class="sxs-lookup"><span data-stu-id="bf262-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="bf262-106">两个网站都处于活动状态，并且 Lync Server 备份服务提供实时数据复制以保持池同步。</span><span class="sxs-lookup"><span data-stu-id="bf262-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="bf262-107">备份服务是 Lync Server 2013 中的一项新功能，旨在支持灾难恢复解决方案。</span><span class="sxs-lookup"><span data-stu-id="bf262-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="bf262-108">当您将池与另一个前端池配对时，它将安装在前端池。</span><span class="sxs-lookup"><span data-stu-id="bf262-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="bf262-109">如果某个网站中的池出现故障，则可以将用户从该池中故障转移到另一个网站中的池，然后在两个池中的所有用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="bf262-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="bf262-110">对于容量规划，每个池都应设计为在发生灾难时处理两个池中所有用户的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="bf262-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bf262-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="bf262-111">In This Section</span></span>

  - [<span data-ttu-id="bf262-112">支持 Lync Server 2013 的池配对选项和最佳做法</span><span class="sxs-lookup"><span data-stu-id="bf262-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="bf262-113">Lync Server 2013 中的备份注册器关系</span><span class="sxs-lookup"><span data-stu-id="bf262-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="bf262-114">Lync Server 2013 中的池故障转移和池故障回复的恢复时间</span><span class="sxs-lookup"><span data-stu-id="bf262-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="bf262-115">Lync Server 2013 中的中央管理存储故障转移</span><span class="sxs-lookup"><span data-stu-id="bf262-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="bf262-116">Lync Server 2013 中的前端池配对数据安全</span><span class="sxs-lookup"><span data-stu-id="bf262-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

