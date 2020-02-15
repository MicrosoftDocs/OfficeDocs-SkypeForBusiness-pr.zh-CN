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
ms.openlocfilehash: 4daeb3ea88570afaf9fc90c0e252466be67ed192
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="7ef80-102">在 Lync Server 2013 中规划前端池配对</span><span class="sxs-lookup"><span data-stu-id="7ef80-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ef80-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7ef80-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7ef80-104">为了在 Lync Server 2013 中获取最佳的灾难恢复能力，请跨两个地理位置分散的网站部署前端池的对。</span><span class="sxs-lookup"><span data-stu-id="7ef80-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="7ef80-105">每个站点包含一个前端池，该池与另一个站点中的相应前端池配对。</span><span class="sxs-lookup"><span data-stu-id="7ef80-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="7ef80-106">这两个站点都处于活动状态，并且 Lync Server 备份服务提供实时数据复制以保持池同步。</span><span class="sxs-lookup"><span data-stu-id="7ef80-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="7ef80-107">备份服务是 Lync Server 2013 中的一项新功能，旨在支持灾难恢复解决方案。</span><span class="sxs-lookup"><span data-stu-id="7ef80-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="7ef80-108">当您将该前端池与另一个前端池配对时，会将该服务安装到该池上。</span><span class="sxs-lookup"><span data-stu-id="7ef80-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="7ef80-p102">如果某个站点中的池失败，则您可以将用户从该前端池故障转移到另一个站点中的池，然后可向两个池中的所有用户提供服务。出于容量规划目的，每个池应设计为在发生灾难时处理两个池中所有用户的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="7ef80-p102">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools. For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7ef80-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="7ef80-111">In This Section</span></span>

  - [<span data-ttu-id="7ef80-112">Lync Server 2013 的受支持的池配对选项和最佳做法</span><span class="sxs-lookup"><span data-stu-id="7ef80-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="7ef80-113">Lync Server 2013 中的备份注册器关系</span><span class="sxs-lookup"><span data-stu-id="7ef80-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="7ef80-114">Lync Server 2013 中池故障转移和池故障回复的恢复时间</span><span class="sxs-lookup"><span data-stu-id="7ef80-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="7ef80-115">Lync Server 2013 中的中央管理存储故障转移</span><span class="sxs-lookup"><span data-stu-id="7ef80-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="7ef80-116">Lync Server 2013 中的前端池配对数据安全性</span><span class="sxs-lookup"><span data-stu-id="7ef80-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

