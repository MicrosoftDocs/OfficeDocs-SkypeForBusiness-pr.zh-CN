---
title: Lync Server 2013 中央管理存储故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b320b3313f37a1912b909d018bbe37de5a997be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="22883-102">Lync Server 2013 中的中央管理存储故障转移</span><span class="sxs-lookup"><span data-stu-id="22883-102">Central Management store failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22883-103">_**主题上次修改时间:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="22883-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="22883-104">中央管理存储包含有关 Lync 2013 部署中的服务器和服务的配置数据。</span><span class="sxs-lookup"><span data-stu-id="22883-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="22883-105">它提供了定义、设置、维护、管理、描述和操作 Lync 2013 部署所需的数据的可靠、schematized 的存储。</span><span class="sxs-lookup"><span data-stu-id="22883-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="22883-106">它还会验证数据，以确保配置的一致性。</span><span class="sxs-lookup"><span data-stu-id="22883-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="22883-107">每个 Lync 部署都包括一个中央管理存储, 该存储由一个前端池的后端服务器托管。</span><span class="sxs-lookup"><span data-stu-id="22883-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="22883-108">建立包含托管中央管理存储的池的池配对时, 将在备份池中设置备份中央管理存储数据库, 并在两个池中安装中央管理存储服务。</span><span class="sxs-lookup"><span data-stu-id="22883-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="22883-109">在任何时间点, 两个中央管理存储数据库之一是活动主机, 另一个是备用主机。</span><span class="sxs-lookup"><span data-stu-id="22883-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="22883-110">备份服务将内容从活动主机复制到待机。</span><span class="sxs-lookup"><span data-stu-id="22883-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="22883-111">在涉及托管中央管理存储的池的池故障转移过程中, 管理员必须先故障转移中央管理存储, 然后才能在前端池进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="22883-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="22883-112">修复灾难后，无需对中央管理存储进行故障回复。</span><span class="sxs-lookup"><span data-stu-id="22883-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="22883-113">修复后, 原始备份池中的中央管理存储可以保留为活动主机。</span><span class="sxs-lookup"><span data-stu-id="22883-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="22883-114">中央管理存储故障转移的恢复时间目标 (RTO) 和恢复点目标 (RPO) 的工程目标均为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="22883-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

