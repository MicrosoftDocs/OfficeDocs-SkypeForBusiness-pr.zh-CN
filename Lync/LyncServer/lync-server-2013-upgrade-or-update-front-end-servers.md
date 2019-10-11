---
title: Lync Server 2013：升级或更新前端服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e4edb5ea009960fe0456f266a428431049f542b
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="7c083-102">Upgrade or update Front End Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c083-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c083-103">_**主题上次修改时间：** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="7c083-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="7c083-104">企业版池中的前端服务器组织为*升级域*。</span><span class="sxs-lookup"><span data-stu-id="7c083-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="7c083-105">这些是池中的前端服务器的子集。</span><span class="sxs-lookup"><span data-stu-id="7c083-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="7c083-106">升级域由拓扑生成器自动创建。</span><span class="sxs-lookup"><span data-stu-id="7c083-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="7c083-107">升级服务器时，必须一次升级域。</span><span class="sxs-lookup"><span data-stu-id="7c083-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="7c083-108">将每台服务器放在一个升级域中，升级它，然后重新启动它，然后再转到另一个升级域。</span><span class="sxs-lookup"><span data-stu-id="7c083-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="7c083-109">请务必跟踪目前升级的升级域和服务器。</span><span class="sxs-lookup"><span data-stu-id="7c083-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="7c083-110">升级每台服务器时，请使用以下流程图图。</span><span class="sxs-lookup"><span data-stu-id="7c083-110">Use the following flowchart diagram when upgrading each server.</span></span>

<span data-ttu-id="7c083-111">:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="升级或更新前端服务器":::</span><span class="sxs-lookup"><span data-stu-id="7c083-111">:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="Upgrade or Update Front End Servers":::</span></span>

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="7c083-112">对池中的前端服务器应用升级</span><span class="sxs-lookup"><span data-stu-id="7c083-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="7c083-113">在池中的前端服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7c083-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="7c083-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="7c083-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="7c083-115">如果*PoolUpgradeState*的值为 "**忙碌**"，请等待10分钟，然后再次尝试**获取 CsPoolUpgradeReadinessState** 。</span><span class="sxs-lookup"><span data-stu-id="7c083-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="7c083-116">如果在每次尝试之间等待10分钟，或者如果你看到 PoolUpgradeState 的**InsufficientActiveFrontEnds**的任何结果，则至少出现三次 "**忙碌**"，或者如果你看到的任何结果 **，** 则该池存在问题。</span><span class="sxs-lookup"><span data-stu-id="7c083-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="7c083-117">如果此池与灾难恢复拓扑中的另一个前端池配对，则应将池故障转移到备份池，然后更新此池中的服务器。</span><span class="sxs-lookup"><span data-stu-id="7c083-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="7c083-118">有关详细信息，请参阅[在 Lync Server 2013 中故障转移池](lync-server-2013-failing-over-a-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="7c083-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="7c083-119">如果*PoolUpgradeState*的值已**准备就绪**，请转到步骤2。</span><span class="sxs-lookup"><span data-stu-id="7c083-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="7c083-120">**CsPoolUpgradeReadinessState** cmdlet 还会返回有关池中的每个升级域的信息，以及每个升级域中的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7c083-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="7c083-121">如果包含要升级的一个或一些服务器的升级域的**ReadyforUpgrade**值为**True** ，则现在可以安全地升级这些服务器。</span><span class="sxs-lookup"><span data-stu-id="7c083-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="7c083-122">若要执行此操作，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7c083-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="7c083-123">通过使用`Stop-CsWindowsService -Graceful -Verbose` cmdlet 停止与即将升级的前端服务器的新连接。</span><span class="sxs-lookup"><span data-stu-id="7c083-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7c083-124">如果在计划的服务器停机期间执行这些服务器升级，则可以运行此 cmdlet 而不使用 "-<STRONG>宽容</STRONG>" 参数，如下所示： <STRONG>Stop-CsWindowsService</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7c083-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="7c083-125">这将立即关闭服务，而无需等待已填写的所有现有服务请求。</span><span class="sxs-lookup"><span data-stu-id="7c083-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="7c083-126">升级与此升级域相关联的服务器。</span><span class="sxs-lookup"><span data-stu-id="7c083-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="7c083-127">重新启动服务器，确保他们接受新的连接。</span><span class="sxs-lookup"><span data-stu-id="7c083-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="7c083-128">对池中的每个升级域重复步骤1和2，直到升级了所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7c083-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

