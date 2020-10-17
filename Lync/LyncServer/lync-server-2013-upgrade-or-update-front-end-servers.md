---
title: Lync Server 2013：升级或更新前端服务器
description: Lync Server 2013：升级或更新前端服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5340ca5549aeff51b275798572573b2c9f017644
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569918"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="e5619-103">在 Lync Server 2013 中升级或更新前端服务器</span><span class="sxs-lookup"><span data-stu-id="e5619-103">Upgrade or update Front End Servers in Lync Server 2013</span></span>

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5619-104">_**上次修改的主题：** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="e5619-104">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="e5619-105">企业版池中的前端服务器被组织为 *升级域*。</span><span class="sxs-lookup"><span data-stu-id="e5619-105">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="e5619-106">这些是池中的前端服务器的子集。</span><span class="sxs-lookup"><span data-stu-id="e5619-106">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="e5619-107">升级域由拓扑生成器自动创建。</span><span class="sxs-lookup"><span data-stu-id="e5619-107">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="e5619-108">升级服务器时，必须一次升级域。</span><span class="sxs-lookup"><span data-stu-id="e5619-108">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="e5619-109">将每台服务器放在一个升级域中，将其升级，然后重新启动它，然后再转到另一个升级域。</span><span class="sxs-lookup"><span data-stu-id="e5619-109">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="e5619-110">请务必跟踪到目前为止升级了哪些升级域和服务器。</span><span class="sxs-lookup"><span data-stu-id="e5619-110">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="e5619-111">升级每个服务器时，请使用以下流程图图。</span><span class="sxs-lookup"><span data-stu-id="e5619-111">Use the following flowchart diagram when upgrading each server.</span></span>

![升级或更新前端服务器](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="e5619-113">将升级应用到池中的前端服务器</span><span class="sxs-lookup"><span data-stu-id="e5619-113">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="e5619-114">在池中的前端服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e5619-114">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="e5619-115">**CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="e5619-115">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="e5619-116">如果 *PoolUpgradeState* 的值正 **忙**，请等待10分钟，然后再次尝试 **CsPoolUpgradeReadinessState** 。</span><span class="sxs-lookup"><span data-stu-id="e5619-116">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="e5619-117">如果在每次尝试之间等待10分钟后又至少看到了3次**繁忙**，或者如果您看到**PoolUpgradeState**的**InsufficientActiveFrontEnds**的任何结果，则该池存在问题。</span><span class="sxs-lookup"><span data-stu-id="e5619-117">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="e5619-118">如果该池与灾难恢复拓扑中的另一个前端池配对，则应将池故障转移到备份池，然后更新该池中的服务器。</span><span class="sxs-lookup"><span data-stu-id="e5619-118">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="e5619-119">有关详细信息，请参阅 [在 Lync Server 2013 中故障转移池](lync-server-2013-failing-over-a-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="e5619-119">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="e5619-120">如果 *PoolUpgradeState* 的值为 **Ready**，请转至步骤 2。</span><span class="sxs-lookup"><span data-stu-id="e5619-120">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="e5619-121">**CsPoolUpgradeReadinessState** cmdlet 还会返回有关池中每个升级域的信息，以及每个升级域中的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e5619-121">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="e5619-122">如果包含要升级的一个或一台服务器的升级域的 **ReadyforUpgrade** 值为 **True** ，则现在可以安全地升级这些服务器。</span><span class="sxs-lookup"><span data-stu-id="e5619-122">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="e5619-123">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e5619-123">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="e5619-124">使用 cmdlet 停止与要升级的前端服务器的新连接 `Stop-CsWindowsService -Graceful -Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="e5619-124">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e5619-125">如果在计划的服务器停机期间执行这些服务器升级，则可以在不使用 "-<STRONG>宽容</STRONG>" 参数的情况下运行此 cmdlet，如下所示： <STRONG>start-cswindowsservice</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="e5619-125">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="e5619-126">这将立即关闭服务，而无需等待要填充的所有现有服务请求。</span><span class="sxs-lookup"><span data-stu-id="e5619-126">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="e5619-127">升级与此升级域关联的服务器。</span><span class="sxs-lookup"><span data-stu-id="e5619-127">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="e5619-128">重新启动服务器，并确保它们接受新的连接。</span><span class="sxs-lookup"><span data-stu-id="e5619-128">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="e5619-129">对池中的每个其他升级域重复步骤1和步骤2，直到所有前端服务器都已升级。</span><span class="sxs-lookup"><span data-stu-id="e5619-129">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

