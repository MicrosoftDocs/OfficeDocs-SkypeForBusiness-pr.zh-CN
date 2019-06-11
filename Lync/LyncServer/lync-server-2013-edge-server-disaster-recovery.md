---
title: Lync Server 2013：边缘服务器灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="af532-102">Lync Server 2013 中的边缘服务器灾难恢复</span><span class="sxs-lookup"><span data-stu-id="af532-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af532-103">_**主题上次修改时间:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="af532-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="af532-104">与其他服务器角色一样, 为 Edge 服务器提供高可用性的最佳方式是在每个网站的池中部署多台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="af532-104">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site.</span></span> <span data-ttu-id="af532-105">如果一台边缘服务器出现故障, 则池中的其他服务器将继续提供 Edge 服务。</span><span class="sxs-lookup"><span data-stu-id="af532-105">If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="af532-106">若要启用灾难恢复过程, 必须在单独的网站上部署单独的 Edge 服务器池。</span><span class="sxs-lookup"><span data-stu-id="af532-106">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites.</span></span> <span data-ttu-id="af532-107">你无需将边缘池与前端池一起进行显式配对, 但如果一个整个边缘池停机, 则具有多个边缘池的功能仍可提供。</span><span class="sxs-lookup"><span data-stu-id="af532-107">You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down.</span></span> <span data-ttu-id="af532-108">以下部分提供了有关边缘服务器的各种功能的灾难恢复的详细信息。</span><span class="sxs-lookup"><span data-stu-id="af532-108">The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="af532-109">远程访问</span><span class="sxs-lookup"><span data-stu-id="af532-109">Remote Access</span></span>

<span data-ttu-id="af532-110">如果你有多个网站, 每个网站都有一个边缘服务器池, 一个整个边缘池出现故障, 则远程访问服务将继续运行, 而不需要管理员操作。</span><span class="sxs-lookup"><span data-stu-id="af532-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="af532-111">在不同的网站中创建边缘池时, 无法使用相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="af532-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="af532-112">每个 Edge 池必须具有唯一的 Fqdn (内部和外部)。</span><span class="sxs-lookup"><span data-stu-id="af532-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="af532-113">边缘池不使用反向代理发布规则与前端服务器交谈。</span><span class="sxs-lookup"><span data-stu-id="af532-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="af532-114">当客户端重新查询远程访问 DNS 服务记录, 并且远程用户路由到另一个站点中的边缘服务器时, 将发生自动故障转移。</span><span class="sxs-lookup"><span data-stu-id="af532-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="af532-115">客户根据 DNS SRV 记录的优先级尝试每个外部边缘 FQDN。</span><span class="sxs-lookup"><span data-stu-id="af532-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af532-116">若要使故障转移顺利工作, 请确保防火墙允许每个池中的前端服务器与所有边缘服务器通信。</span><span class="sxs-lookup"><span data-stu-id="af532-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="af532-117">联合身份验证</span><span class="sxs-lookup"><span data-stu-id="af532-117">Federation</span></span>

<span data-ttu-id="af532-118">对于其他运行 Lync Server 的组织的联盟关系, 只要你有类似于 Geo DNS 的解决方案, 入站联合请求将继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="af532-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="af532-119">请务必了解, 联合身份验证故障转移不会提供 SRV 记录中优先级的故障转移。</span><span class="sxs-lookup"><span data-stu-id="af532-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="af532-120">以前提供的解决方案可帮助你提供入站联合身份验证的灾难恢复功能。</span><span class="sxs-lookup"><span data-stu-id="af532-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="af532-121">出站联盟始终在组织中的一个已发布的 Edge 池或边缘服务器上设置。</span><span class="sxs-lookup"><span data-stu-id="af532-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="af532-122">如果此边缘池已关闭, 则必须使用拓扑生成器将出站联盟路由以使用仍在运行的边缘池。</span><span class="sxs-lookup"><span data-stu-id="af532-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="af532-123">有关详细信息, 请参阅[在 lync server 2013 中针对 Lync server 联合使用的边缘池故障](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="af532-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="af532-124">XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="af532-124">XMPP Federation</span></span>

<span data-ttu-id="af532-125">对于 XMPP 联合身份验证, 如果指定为 XMPP 联合网关的边缘池已关闭, 则出站流量和入站流量都将失败。</span><span class="sxs-lookup"><span data-stu-id="af532-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="af532-126">若要使 XMPP 联合身份验证再次运行, 必须将 XMPP 联盟更改为使用其他边缘池。</span><span class="sxs-lookup"><span data-stu-id="af532-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="af532-127">有关详细信息, 请参阅[在 Lync Server 2013 中用于 XMPP 联合身份验证的边缘池故障](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="af532-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="af532-128">Edge 池失败, 但前端池仍在运行</span><span class="sxs-lookup"><span data-stu-id="af532-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="af532-129">如果某个边缘池在网站上失败, 但该网站上的前端池仍在运行, 则需要更改前端池以在另一个网站上使用不同的边缘池, 而第一个边缘池已关闭。</span><span class="sxs-lookup"><span data-stu-id="af532-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="af532-130">有关详细信息, 请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="af532-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

