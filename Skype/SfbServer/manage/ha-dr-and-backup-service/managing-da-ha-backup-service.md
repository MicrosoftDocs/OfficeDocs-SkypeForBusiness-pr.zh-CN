---
title: 管理灾难恢复、高可用性和备份服务
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解灾难恢复操作的过程, 以及维护备份服务, 该过程将同步成对前端池内的数据。
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303896"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="c1efc-103">管理 Skype for Business Server 灾难恢复、高可用性和备份服务</span><span class="sxs-lookup"><span data-stu-id="c1efc-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="c1efc-104">本部分包含灾难恢复操作的过程, 以及用于维护备份服务的过程, 该过程将同步成对前端池内的数据。</span><span class="sxs-lookup"><span data-stu-id="c1efc-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="c1efc-105">灾难恢复过程 (故障转移和回切) 是手动的。</span><span class="sxs-lookup"><span data-stu-id="c1efc-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="c1efc-106">如果发生灾难, 管理员必须手动调用故障转移过程。</span><span class="sxs-lookup"><span data-stu-id="c1efc-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="c1efc-107">修复完池后, 故障回复也同样适用。</span><span class="sxs-lookup"><span data-stu-id="c1efc-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="c1efc-108">本部分中的灾难恢复过程假定以下情况:</span><span class="sxs-lookup"><span data-stu-id="c1efc-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="c1efc-109">你的部署具有成对的前端池, 位于不同的网站中, 如[高可用性和灾难恢复计划](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="c1efc-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="c1efc-110">备份服务已在这些配对的池上运行, 以使其保持同步。</span><span class="sxs-lookup"><span data-stu-id="c1efc-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="c1efc-111">如果中央管理存储托管在任一池中, 则会在这两个配对的池上安装和运行它, 其中一个托管活动主机的池和另一个托管备用池的池。</span><span class="sxs-lookup"><span data-stu-id="c1efc-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1efc-112">在以下过程中, *PoolFQDN*参数是指受灾难影响的池的 FQDN, 而不是对受影响的用户进行重定向的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c1efc-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="c1efc-113">对于同一组受影响的用户, 它指的是故障转移和故障回复 cmdlet 中的同一池 (即, 在故障转移之前首先驻留用户的池)。</span><span class="sxs-lookup"><span data-stu-id="c1efc-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="c1efc-114">例如, 假设驻留在池 P1 上的所有用户都已故障转移到备份池 P2 的情况。</span><span class="sxs-lookup"><span data-stu-id="c1efc-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="c1efc-115">如果管理员想要移动当前由 P2 服务的所有用户以供 P1 处理, 管理员必须执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="c1efc-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="c1efc-116">使用故障回复 cmdlet, 将原来位于 P1 中的所有用户从 P2 切换回 P1。</span><span class="sxs-lookup"><span data-stu-id="c1efc-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="c1efc-117">在此情况下, *PoolFQDN*为 P1's FQDN。</span><span class="sxs-lookup"><span data-stu-id="c1efc-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="c1efc-118">使用故障转移 cmdlet, 将所有最初驻留在 P2 上的用户故障转移到 P1。</span><span class="sxs-lookup"><span data-stu-id="c1efc-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="c1efc-119">在此情况下, PoolFQDN 为 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="c1efc-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="c1efc-120">如果管理员稍后希望将这些 P2 用户故障回复回 P2, 则 PoolFQDN 为 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="c1efc-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="c1efc-121">请注意, 上面的步骤1必须在步骤2之前执行, 以保留池完整性。</span><span class="sxs-lookup"><span data-stu-id="c1efc-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="c1efc-122">如果你在步骤1之前尝试步骤 2, 则步骤 2 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="c1efc-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="c1efc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1efc-123">See Also</span></span>

[<span data-ttu-id="c1efc-124">规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="c1efc-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
