---
title: Lync Server 2013：备份和还原 Lync Server
description: Lync Server 2013：备份和还原 Lync Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1a7024b2264fb895d1562a6da0775f9397644b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543778"
---
# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="4673d-103">备份和还原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4673d-103">Backing up and restoring Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4673d-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4673d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4673d-105">在本节中，您将找到备份 Lync Server 2013 数据的最佳做法，并在遇到故障时将其还原。</span><span class="sxs-lookup"><span data-stu-id="4673d-105">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="4673d-106">这些最佳实践适用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="4673d-106">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="4673d-107">所有类型 (前端服务器、边缘服务器、中介服务器、持久聊天服务器或控制器) 的整个 Lync Server 池或其中一个池中的单个服务器。</span><span class="sxs-lookup"><span data-stu-id="4673d-107">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="4673d-108">中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="4673d-108">The Central Management Server</span></span>

  - <span data-ttu-id="4673d-109">Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="4673d-109">A Standard Edition server</span></span>

  - <span data-ttu-id="4673d-110">企业版后端服务器</span><span class="sxs-lookup"><span data-stu-id="4673d-110">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="4673d-111">文件存储</span><span class="sxs-lookup"><span data-stu-id="4673d-111">A File Store</span></span>

  - <span data-ttu-id="4673d-112">存档数据库、监控数据库或持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="4673d-112">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="4673d-113">本部分不包括有关还原整个网站或开发备用网站的信息。</span><span class="sxs-lookup"><span data-stu-id="4673d-113">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="4673d-114">有关开发具有成对前端池的灾难恢复解决方案的详细信息，请参阅 [在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="4673d-114">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="4673d-115">这是规划灾难恢复的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="4673d-115">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="4673d-116">如果已部署配对的前端池，如果其中一个池发生故障且无法恢复，则可以使用其配对的池中的新的完全限定域名 (FQDN) 还原此池。</span><span class="sxs-lookup"><span data-stu-id="4673d-116">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="4673d-117">有关执行此恢复的步骤的详细信息，请参阅 [在 Lync Server 2013 中对池进行故障转移](lync-server-2013-failing-over-a-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="4673d-117">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="4673d-118">此外，如果您稍后要重新创建属于前端对的故障和不可恢复的池，则可以使用在 [Lync Server 2013 中执行 ABC 前端池故障转移](lync-server-2013-performing-an-abc-front-end-pool-failover.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="4673d-118">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="4673d-119">本文档介绍的方法包括规划阶段的特殊注意事项。</span><span class="sxs-lookup"><span data-stu-id="4673d-119">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="4673d-120">有关详细信息，请参阅为 [Lync Server 2013 建立备份和还原计划](lync-server-2013-establishing-a-backup-and-restoration-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="4673d-120">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4673d-121">本部分内容</span><span class="sxs-lookup"><span data-stu-id="4673d-121">In This Section</span></span>

  - [<span data-ttu-id="4673d-122">准备 Lync Server 2013 备份和还原</span><span class="sxs-lookup"><span data-stu-id="4673d-122">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="4673d-123">在 Lync Server 2013 中备份数据和设置</span><span class="sxs-lookup"><span data-stu-id="4673d-123">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="4673d-124">在 Lync Server 2013 中还原数据和设置</span><span class="sxs-lookup"><span data-stu-id="4673d-124">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="4673d-125">Lync Server 2013 的备份和还原工作表</span><span class="sxs-lookup"><span data-stu-id="4673d-125">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

