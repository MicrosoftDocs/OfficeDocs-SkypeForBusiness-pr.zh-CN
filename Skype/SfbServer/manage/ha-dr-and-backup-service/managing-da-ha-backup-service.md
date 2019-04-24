---
title: 管理灾难恢复、 高可用性和备份服务
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解有关灾难恢复操作以及维护同步配对前端池中数据备份服务的过程。
ms.openlocfilehash: 103e0aa274e40fd997981bd6de595ceca089b710
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199824"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="aa042-103">管理 Skype 的业务 Server 灾难恢复、 高可用性和备份服务</span><span class="sxs-lookup"><span data-stu-id="aa042-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="aa042-104">本节包含灾难恢复操作以及维护同步配对前端池中数据备份服务的过程。</span><span class="sxs-lookup"><span data-stu-id="aa042-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="aa042-105">灾难恢复过程，故障转移和故障回复，是手动。</span><span class="sxs-lookup"><span data-stu-id="aa042-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="aa042-106">如果没有灾难，管理员必须手动调用故障转移过程。</span><span class="sxs-lookup"><span data-stu-id="aa042-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="aa042-107">这同样适用于故障回复后修复池。</span><span class="sxs-lookup"><span data-stu-id="aa042-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="aa042-108">本节中的灾难恢复过程假定以下几点：</span><span class="sxs-lookup"><span data-stu-id="aa042-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="aa042-109">您必须部署已配对前端池，位于不同网站[规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="aa042-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="aa042-110">备份服务已在这些配对的池，以使它们保持同步运行。</span><span class="sxs-lookup"><span data-stu-id="aa042-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="aa042-111">如果在任一池中承载中央管理存储，它是两者之一的承载活动主控形状这些池和承载备用的其他池配对池上安装和运行。</span><span class="sxs-lookup"><span data-stu-id="aa042-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa042-112">在下面的过程中， *PoolFQDN*参数是指受灾难的池的 FQDN，从正在重定向不受影响用户的池。</span><span class="sxs-lookup"><span data-stu-id="aa042-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="aa042-113">为一组相同的受影响的用户，它引用到相同的池故障转移和故障回复 cmdlet （即，首先驻留故障转移前的用户的池） 中。</span><span class="sxs-lookup"><span data-stu-id="aa042-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="aa042-114">例如，假定所有用户都驻留在 P1 已故障转移到备份池，P2 池中案例。</span><span class="sxs-lookup"><span data-stu-id="aa042-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="aa042-115">如果管理员希望将当前 P2 P1 中处理由提供服务的所有用户都移动，管理员必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="aa042-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="aa042-116">失败备份所有用户最初驻留在从 P2 到 P1 P1 使用故障回复 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa042-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="aa042-117">在这种情况下，则*PoolFQDN*为 P1 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="aa042-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="aa042-118">故障转移所有用户最初驻留在 P2 到 P1 使用故障转移 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa042-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="aa042-119">在这种情况下，则 PoolFQDN 为 P2 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="aa042-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="aa042-120">如果更高版本，管理员希望故障回复这些 P2 用户回复到 P2，则 PoolFQDN 为 P2 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="aa042-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="aa042-121">请注意步骤 2 以保持池完整性之前必须执行的步骤 1 上面。</span><span class="sxs-lookup"><span data-stu-id="aa042-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="aa042-122">如果您尝试步骤 2 之前步骤 1，则第 2 步 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="aa042-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="aa042-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa042-123">See Also</span></span>

[<span data-ttu-id="aa042-124">规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="aa042-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
