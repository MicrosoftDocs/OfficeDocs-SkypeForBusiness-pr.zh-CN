---
title: Lync Server 2013：边缘服务器灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cd85a769d021aae6873a50a719a6043ef72f770
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="5899b-102">Lync Server 2013 中的边缘服务器灾难恢复</span><span class="sxs-lookup"><span data-stu-id="5899b-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5899b-103">_**上次修改的主题：** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="5899b-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="5899b-p101">与其他服务器角色一样，为您的边缘服务器提供高可用性的最佳途径是在每个站点的池中部署多台边缘服务器。如果一台边缘服务器停机，池中的其他服务器将继续提供边缘服务。</span><span class="sxs-lookup"><span data-stu-id="5899b-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="5899b-p102">要启用灾难恢复过程，必须在单独的站点部署单独的边缘服务器池。虽然您无需像对前端池那样明确将边缘池组成对，但是拥有多个边缘池仍能在某个完整边缘池出现故障时继续提供可用性。以下各节提供有关边缘服务器各项功能的灾难恢复的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5899b-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="5899b-109">远程访问</span><span class="sxs-lookup"><span data-stu-id="5899b-109">Remote Access</span></span>

<span data-ttu-id="5899b-110">如果您有多个网站，每个站点都有一池的边缘服务器，而一个整个边缘池发生故障，则远程访问服务将继续运行，而无需管理员操作。</span><span class="sxs-lookup"><span data-stu-id="5899b-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="5899b-111">在不同站点中创建边缘池时，不能使用相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5899b-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="5899b-112">每个边缘池都必须具有唯一的 Fqdn （内部和外部）。</span><span class="sxs-lookup"><span data-stu-id="5899b-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="5899b-113">边缘池不使用反向代理发布规则与前端服务器交谈。</span><span class="sxs-lookup"><span data-stu-id="5899b-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="5899b-114">当客户端重新查询远程访问 DNS 服务记录，并且远程用户路由到另一个站点中的边缘服务器时，将发生自动故障转移。</span><span class="sxs-lookup"><span data-stu-id="5899b-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="5899b-115">客户端根据 DNS SRV 记录的优先级尝试每个外部边缘 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5899b-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5899b-116">若要使故障转移正常工作，请确保防火墙允许每个池中的前端服务器与所有边缘服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="5899b-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="5899b-117">联合</span><span class="sxs-lookup"><span data-stu-id="5899b-117">Federation</span></span>

<span data-ttu-id="5899b-118">对于与运行 Lync Server 的其他组织的联盟关系，只要您拥有类似 Geo DNS 的解决方案，入站联合请求将继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="5899b-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="5899b-119">请务必了解，联合身份验证故障转移不会在 SRV 记录中提供优先级故障转移。</span><span class="sxs-lookup"><span data-stu-id="5899b-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="5899b-120">之前提供的解决方案可帮助您为入站联合提供灾难恢复功能。</span><span class="sxs-lookup"><span data-stu-id="5899b-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="5899b-121">出站联盟始终通过组织中的一个已发布边缘池或边缘服务器来设置。</span><span class="sxs-lookup"><span data-stu-id="5899b-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="5899b-122">如果此边缘池已经停机，必须使用拓扑生成器将出站联盟路由改为使用仍在运行的边缘池。</span><span class="sxs-lookup"><span data-stu-id="5899b-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="5899b-123">有关详细信息，请参阅[在 Lync server 2013 中对 Lync server 联合身份验证使用的边缘池故障](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="5899b-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="5899b-124">XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="5899b-124">XMPP Federation</span></span>

<span data-ttu-id="5899b-125">对于 XMPP 联盟，如果被指定为 XMPP 联盟网关的边缘池出现故障，则出站和入站通信都将失败。</span><span class="sxs-lookup"><span data-stu-id="5899b-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="5899b-126">若要使 XMPP 联盟重新工作，必须将 XMPP 联盟改为使用一个不同的边缘池。</span><span class="sxs-lookup"><span data-stu-id="5899b-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="5899b-127">有关详细信息，请参阅[在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="5899b-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="5899b-128">边缘池出故障但前端池仍在运行</span><span class="sxs-lookup"><span data-stu-id="5899b-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="5899b-129">如果一个站点中的一个边缘池出现故障，但该站点中的前端池仍在运行，您需要在这第一个边缘池停机的情况下，将前端池改为使用其他站点上的其他边缘池。</span><span class="sxs-lookup"><span data-stu-id="5899b-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="5899b-130">有关详细信息，请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="5899b-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

