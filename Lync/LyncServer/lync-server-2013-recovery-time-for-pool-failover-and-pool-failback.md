---
title: Lync Server 2013 池故障转移和池故障回复的恢复时间
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1221d145951b4f780638cc2681f6d6cff822a4e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512019"
---
# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="3c3a5-102">Lync Server 2013 中池故障转移和池故障回复的恢复时间</span><span class="sxs-lookup"><span data-stu-id="3c3a5-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c3a5-103">_**上次修改的主题：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="3c3a5-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="3c3a5-p101">对于池故障转移和池故障回复，恢复时间目标 (RTO) 的工程目标为 30 分钟。这是管理员确定存在灾难并启动故障转移过程之后，故障转移发生所需的时间。此时间不包括管理员评估情况并作出决策所需的时间，也不包括用户在故障转移完成后再次登录所需的时间。</span><span class="sxs-lookup"><span data-stu-id="3c3a5-p101">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes. This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures. It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="3c3a5-107">对于池故障转移和池故障回复，恢复点目标 (RPO) 的工程目标为 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="3c3a5-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="3c3a5-108">这表示测量可能因灾难、因备份服务的复制延迟丢失的数据的时间。</span><span class="sxs-lookup"><span data-stu-id="3c3a5-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="3c3a5-109">例如，如果池在 10:00 A.M. 停止，RPO 为30分钟，则在 9:30 A.M. 之间写入到池的数据</span><span class="sxs-lookup"><span data-stu-id="3c3a5-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="3c3a5-110">而10:00 可能尚未复制到备份池，并且将丢失。</span><span class="sxs-lookup"><span data-stu-id="3c3a5-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="3c3a5-111">本文档中的所有 RTO 和 RPO 数字均假定两个数据中心位于同一在两个网站间具有高速度、低延迟传输的世界区域中。</span><span class="sxs-lookup"><span data-stu-id="3c3a5-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="3c3a5-112">对于在数据复制中没有积压工作的预定义用户模型，为40000并发活动用户和200000用户启用了与 Lync 相关的池的度量值。</span><span class="sxs-lookup"><span data-stu-id="3c3a5-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="3c3a5-113">这些数字可能根据测试和验证性能发生改变。</span><span class="sxs-lookup"><span data-stu-id="3c3a5-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

