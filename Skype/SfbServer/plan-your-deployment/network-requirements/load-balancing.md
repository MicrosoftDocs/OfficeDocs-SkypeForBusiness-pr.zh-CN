---
title: Skype for Business 的负载平衡要求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 摘要：实施 Skype for Business Server 之前，请查看负载平衡注意事项。
ms.openlocfilehash: 5790ef1ba0d32774ced45be5af257f70fc4cf594
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834372"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a><span data-ttu-id="7638f-103">Skype for Business 的负载平衡要求</span><span class="sxs-lookup"><span data-stu-id="7638f-103">Load balancing requirements for Skype for Business</span></span>
 
<span data-ttu-id="7638f-104">**摘要：** 实施 Skype for Business Server 之前，请查看负载平衡注意事项。</span><span class="sxs-lookup"><span data-stu-id="7638f-104">**Summary:** Review the load balancing considerations before implementing Skype for Business Server.</span></span>
  
<span data-ttu-id="7638f-105">负载平衡在池中的服务器之间分布流量。</span><span class="sxs-lookup"><span data-stu-id="7638f-105">Load balancing distributes traffic among the servers in a pool.</span></span> <span data-ttu-id="7638f-106">如果您有前端池、中介服务器池或边缘服务器池，则需要为这些池部署负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-106">If you have Front End pools, Mediation Server pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span>
  
<span data-ttu-id="7638f-107">Skype for Business Server 支持两种类型的客户端到服务器流量负载平衡解决方案：域名系统 (DNS) 负载平衡和硬件负载平衡 (通常缩写为 HLB) 。</span><span class="sxs-lookup"><span data-stu-id="7638f-107">Skype for Business Server supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing (often abbreviated as HLB).</span></span> <span data-ttu-id="7638f-108">DNS 负载平衡提供了一些优势，包括更简单的管理、更有效的故障排除，以及将 Skype for Business Server 流量与任何潜在的硬件负载平衡器问题隔离在一起的能力。</span><span class="sxs-lookup"><span data-stu-id="7638f-108">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Skype for Business Server traffic from any potential hardware load balancer problems.</span></span>
  
<span data-ttu-id="7638f-109">请自己决定哪个负载平衡解决方案适合部署中的每个池，但请记住以下限制：</span><span class="sxs-lookup"><span data-stu-id="7638f-109">Decide for yourself which load balancing solution is appropriate for each pool in your deployment, but keep in mind the following restrictions:</span></span> 
  
- <span data-ttu-id="7638f-p103">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能在一个接口上使用 DNS 负载平衡的同时，在另一个接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>
    
- <span data-ttu-id="7638f-p104">某些类型的流量需要硬件负载平衡器。例如，HTTP 流量需要硬件平衡负载器而非 DNS 负载平衡。DNS 负载平衡对客户端到服务器的 Web 流量不起作用。</span><span class="sxs-lookup"><span data-stu-id="7638f-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>
    
<span data-ttu-id="7638f-115">如果选择对某个池使用 DNS 负载平衡，但仍需对流量（如 HTTP 流量）使用硬件负载平衡器，则会大大简化硬件负载平衡器的管理。</span><span class="sxs-lookup"><span data-stu-id="7638f-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="7638f-116">例如，配置硬件负载平衡器将更简单，因为它将仅管理 HTTP 和 HTTPS 流量，而所有其他协议都将由 DNS 负载平衡管理。</span><span class="sxs-lookup"><span data-stu-id="7638f-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="7638f-117">有关详细信息，请参阅 [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing)。</span><span class="sxs-lookup"><span data-stu-id="7638f-117">For details, see [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing).</span></span> 
  
<span data-ttu-id="7638f-118">对于服务器到服务器流量，Skype for Business Server 使用拓扑感知负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-118">For server-to-server traffic, Skype for Business Server uses topology-aware load balancing.</span></span> <span data-ttu-id="7638f-119">服务器读取中央管理存储中的已发布拓扑以获取拓扑中服务器的 FQDN，并自动在服务器之间分发流量。</span><span class="sxs-lookup"><span data-stu-id="7638f-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="7638f-120">管理员无需设置或管理这种类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-120">Administrators do not need to set up or manage this type of load balancing.</span></span> 
  
<span data-ttu-id="7638f-121">如果使用 DNS 负载平衡并且需要阻止到特定计算机的流量，则仅从池 FQDN 中删除 IP 地址条目是不够的。</span><span class="sxs-lookup"><span data-stu-id="7638f-121">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="7638f-122">还必须删除计算机的 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="7638f-122">You must remove the DNS entry for the computer as well.</span></span> 
  
## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="7638f-123">硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="7638f-123">Hardware load balancer requirements</span></span>

<span data-ttu-id="7638f-124">Skype for Business Server 扩展的合并边缘拓扑已针对主要使用 Skype for Business Server 或 Lync Server 的其他组织联盟的新部署优化了 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-124">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Skype for Business Server or Lync Server.</span></span> <span data-ttu-id="7638f-125">如果下列任何方案要求高可用性，则必须在边缘服务器池上对以下内容使用硬件负载平衡器：</span><span class="sxs-lookup"><span data-stu-id="7638f-125">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span> 
  
- <span data-ttu-id="7638f-126">使用 Office Communications Server 2007 R2 或 Office Communications Server 2007 与组织联盟</span><span class="sxs-lookup"><span data-stu-id="7638f-126">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>
    
- <span data-ttu-id="7638f-127">Exchange 2010 SP1 之前使用 Exchange UM 的远程用户的 Exchange UM</span><span class="sxs-lookup"><span data-stu-id="7638f-127">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>
    
- <span data-ttu-id="7638f-128">与公共 IM 用户的连接</span><span class="sxs-lookup"><span data-stu-id="7638f-128">Connectivity to public IM users</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="7638f-p109">不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-p109">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7638f-p110">如果使用硬件负载平衡器，则为内部网络连接部署的负载平衡器必须配置为仅对发往运行访问边缘服务和 A/V 边缘服务的服务器的流量进行负载平衡。它不能对发往内部 Web 会议边缘服务或内部 XMPP 代理服务的流量进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-p110">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7638f-133">Skype for Business Server (NAT) 返回直接服务器。</span><span class="sxs-lookup"><span data-stu-id="7638f-133">The direct server return (DSR) NAT is not supported with Skype for Business Server.</span></span> 
  
<span data-ttu-id="7638f-134">若要确定硬件负载平衡器是否支持 Skype for Business Server 所需的必要功能，请参阅 [Skype for Business 的基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="7638f-134">To determine whether your hardware load balancer supports the necessary features required by Skype for Business Server, see [Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="7638f-135">运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="7638f-135">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="7638f-136">以下是运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求：</span><span class="sxs-lookup"><span data-stu-id="7638f-136">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>
  
- <span data-ttu-id="7638f-p111">对内部和外部端口 443 关闭 TCP nagling。Nagling 是将若干小数据包整合到单个大数据包以提高传输效率的过程。</span><span class="sxs-lookup"><span data-stu-id="7638f-p111">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>
    
- <span data-ttu-id="7638f-139">关闭外部端口范围为 50，000 - 59，999 的 TCP 对接。</span><span class="sxs-lookup"><span data-stu-id="7638f-139">Turn off TCP nagling for external port range 50,000 - 59,999.</span></span> 
    
- <span data-ttu-id="7638f-140">请不要对内部或外部防火墙使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="7638f-140">Do not use NAT on the internal or external firewall.</span></span> 
    
- <span data-ttu-id="7638f-141">边缘内部接口与边缘服务器外部接口必须位于不同的网络上，且必须禁用它们之间的路由。</span><span class="sxs-lookup"><span data-stu-id="7638f-141">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span> 
    
- <span data-ttu-id="7638f-142">运行 A/V 边缘服务的边缘服务器的外部接口必须使用可公开路由的 IP 地址，并且任何边缘外部 IP 地址上都不得进行 NAT 或端口转换。</span><span class="sxs-lookup"><span data-stu-id="7638f-142">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span> 
    
- <span data-ttu-id="7638f-143">负载平衡器不得更改客户端的源地址。</span><span class="sxs-lookup"><span data-stu-id="7638f-143">The load balancer must not change the source address of the client.</span></span>
    
### <a name="other-hardware-load-balancer-requirements"></a><span data-ttu-id="7638f-144">其他硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="7638f-144">Other Hardware Load Balancer requirements</span></span>

<span data-ttu-id="7638f-145">Skype for Business Server 中针对 Web 服务的基于 Cookie 的关联要求大大减少。</span><span class="sxs-lookup"><span data-stu-id="7638f-145">Cookie-based affinity requirements are greatly reduced in Skype for Business Server for Web services.</span></span> <span data-ttu-id="7638f-146">如果要部署 Skype for Business Server 并且不会保留任何 Lync Server 2010 前端服务器或前端池，则不需要基于 Cookie 的持久性。</span><span class="sxs-lookup"><span data-stu-id="7638f-146">If you are deploying Skype for Business Server and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="7638f-147">但是，如果您暂时或永久保留任何 Lync Server 2010 前端服务器或前端池，则仍使用基于 Cookie 的持久性，因为它已针对 Lync Server 2010 进行部署和配置。</span><span class="sxs-lookup"><span data-stu-id="7638f-147">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7638f-148">**如果您决定使用基于 Cookie 的相关性，但您的部署不需要它**，如此做没有任何负面影响。</span><span class="sxs-lookup"><span data-stu-id="7638f-148">**If you decide to use cookie-based affinity even though your deployment does not require it**, there is no negative impact to doing so.</span></span> 
  
<span data-ttu-id="7638f-149">对于 **不使用** 基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="7638f-149">For deployments that **will not use** cookie-based affinity:</span></span>
  
- <span data-ttu-id="7638f-p113">在端口 4443 的反向代理发布规则上，将“转发主机头”设置为 True。这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="7638f-p113">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>
    
<span data-ttu-id="7638f-152">对于 **将使用** 基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="7638f-152">For deployments that **will use** cookie-based affinity:</span></span>
  
- <span data-ttu-id="7638f-p114">在端口 4443 的反向代理发布规则上，将“转发主机头”设置为 True。这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="7638f-p114">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>
    
- <span data-ttu-id="7638f-155">不得将硬件负载平衡器 Cookie 标记为 httpOnly</span><span class="sxs-lookup"><span data-stu-id="7638f-155">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>
    
- <span data-ttu-id="7638f-156">硬件负载平衡器 Cookie 不得具有过期时间</span><span class="sxs-lookup"><span data-stu-id="7638f-156">Hardware load balancer cookie MUST NOT have an expiration time</span></span>
    
- <span data-ttu-id="7638f-157">硬件负载平衡器 Cookie 必须名为 **MS-WSMAN**（这是 Web 服务预期的值，不能更改）</span><span class="sxs-lookup"><span data-stu-id="7638f-157">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>
    
- <span data-ttu-id="7638f-p115">必须在其传入 HTTP 请求没有 Cookie 的每个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie 都是如此。如果负载平衡器将 Cookie 插入优化为每个 TCP 连接只发生一次，则不得使用该优化</span><span class="sxs-lookup"><span data-stu-id="7638f-p115">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>
    
> [!NOTE]
> <span data-ttu-id="7638f-160">典型的硬件负载平衡器配置使用源地址相关性和 20 分钟的 TCP 会话生存期，这适用于 Lync Server 和 Lync 2013 客户端，因为会话状态通过客户端使用和/或应用程序交互进行维护。</span><span class="sxs-lookup"><span data-stu-id="7638f-160">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span> 
  
<span data-ttu-id="7638f-161">如果部署移动设备，则您的硬件负载平衡器必须能对 TCP 会话中的单个请求进行负载平衡（实际上，您必须能基于目标 IP 地址对单个请求进行负载平衡）。</span><span class="sxs-lookup"><span data-stu-id="7638f-161">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7638f-162">如果要部署移动设备，则硬件负载平衡器必须能够在 TCP 连接内单独平衡每个请求的负载。</span><span class="sxs-lookup"><span data-stu-id="7638f-162">If you are deploying mobile devices, your hardware load balancer must be able to individually load balance each request within a TCP connection.</span></span> <span data-ttu-id="7638f-163">最新的 Apple iOS 移动应用程序要求传输层安全性 (TLS) 1.2 版。</span><span class="sxs-lookup"><span data-stu-id="7638f-163">The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="7638f-164">有关第三方硬件负载平衡器的详细信息，请参阅 [Skype for Business 的基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="7638f-164">For details on third party hardware load balancers, see [Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span>  
  
<span data-ttu-id="7638f-165">以下是控制器和前端池 Web 服务的硬件负载平衡器要求：</span><span class="sxs-lookup"><span data-stu-id="7638f-165">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>
  
- <span data-ttu-id="7638f-166">对于内部 Web 服务 VIP，在硬件负载平衡器上设置 Source_addr 持久性（内部端口 80 和 443）。</span><span class="sxs-lookup"><span data-stu-id="7638f-166">For internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="7638f-167">对于 Skype for Business Server，Source_addr持久性意味着始终将来自单个 IP 地址的多个连接发送到一台服务器以保持会话状态。</span><span class="sxs-lookup"><span data-stu-id="7638f-167">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>
    
- <span data-ttu-id="7638f-168">使用 TCP 空闲超时 1800 秒。</span><span class="sxs-lookup"><span data-stu-id="7638f-168">Use TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="7638f-169">在反向代理和下一个跃点池的硬件负载平衡器之间的防火墙上，创建一个规则以允许端口 4443 上的 https：流量从反向代理到硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="7638f-169">On the firewall between the reverse proxy and the next hop pool's hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer.</span></span> <span data-ttu-id="7638f-170">必须将硬件负载平衡器配置为侦听端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="7638f-170">The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="7638f-171">硬件负载平衡器关联要求的摘要</span><span class="sxs-lookup"><span data-stu-id="7638f-171">Summary of Hardware Load Balancer Affinity Requirements</span></span>

|<span data-ttu-id="7638f-172">**客户端/用户位置**</span><span class="sxs-lookup"><span data-stu-id="7638f-172">**Client/user location**</span></span>|<span data-ttu-id="7638f-173">**外部 Web 服务 FQDN 关联要求**</span><span class="sxs-lookup"><span data-stu-id="7638f-173">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="7638f-174">**内部 Web 服务 FQDN 关联要求**</span><span class="sxs-lookup"><span data-stu-id="7638f-174">**Internal web services FQDN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7638f-175">Lync Web App (内部和外部) </span><span class="sxs-lookup"><span data-stu-id="7638f-175">Lync Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="7638f-176">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="7638f-176">Mobile device (internal and external users)</span></span>  <br/> |<span data-ttu-id="7638f-177">无相关性</span><span class="sxs-lookup"><span data-stu-id="7638f-177">No affinity</span></span>  <br/> |<span data-ttu-id="7638f-178">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="7638f-178">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="7638f-179">Lync Web App (外部用户) </span><span class="sxs-lookup"><span data-stu-id="7638f-179">Lync Web App (external users only)</span></span>  <br/> <span data-ttu-id="7638f-180">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="7638f-180">Mobile device (internal and external users)</span></span>  <br/> |<span data-ttu-id="7638f-181">无相关性</span><span class="sxs-lookup"><span data-stu-id="7638f-181">No affinity</span></span>  <br/> |<span data-ttu-id="7638f-182">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="7638f-182">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="7638f-183">Lync Web App (内部用户) </span><span class="sxs-lookup"><span data-stu-id="7638f-183">Lync Web App (internal users only)</span></span>  <br/> <span data-ttu-id="7638f-184">移动设备（未部署）</span><span class="sxs-lookup"><span data-stu-id="7638f-184">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="7638f-185">无相关性</span><span class="sxs-lookup"><span data-stu-id="7638f-185">No affinity</span></span>  <br/> |<span data-ttu-id="7638f-186">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="7638f-186">Source address affinity</span></span>  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="7638f-187">硬件负载平衡器的端口监控</span><span class="sxs-lookup"><span data-stu-id="7638f-187">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="7638f-188">在硬件负载平衡器上定义端口监控来确定特定服务何时由于硬件或通信故障而不再可用。</span><span class="sxs-lookup"><span data-stu-id="7638f-188">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="7638f-189">例如，如果前端服务器服务 (RTCSRV) 由于前端服务器或前端池失败而停止，则 HLB 监控还应停止接收 Web 服务上的流量。</span><span class="sxs-lookup"><span data-stu-id="7638f-189">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="7638f-190">可在 HLB 上实施端口监控来监控以下各项：</span><span class="sxs-lookup"><span data-stu-id="7638f-190">You implement port monitoring on the HLB to monitor the following:</span></span>
  
<span data-ttu-id="7638f-191">**前端服务器用户池 - HLB 内部接口**</span><span class="sxs-lookup"><span data-stu-id="7638f-191">**Front End Server User Pool - HLB Internal Interface**</span></span>

|<span data-ttu-id="7638f-192">**虚拟 IP/端口**</span><span class="sxs-lookup"><span data-stu-id="7638f-192">**Virtual IP/Port**</span></span>|<span data-ttu-id="7638f-193">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="7638f-193">**Node Port**</span></span>|<span data-ttu-id="7638f-194">**节点计算机/监视器**</span><span class="sxs-lookup"><span data-stu-id="7638f-194">**Node Machine/Monitor**</span></span>|<span data-ttu-id="7638f-195">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="7638f-195">**Persistence Profile**</span></span>|<span data-ttu-id="7638f-196">**备注**</span><span class="sxs-lookup"><span data-stu-id="7638f-196">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7638f-197">\<pool\>web-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="7638f-197">\<pool\>web-int_mco_443_vs</span></span>  <br/> <span data-ttu-id="7638f-198">443</span><span class="sxs-lookup"><span data-stu-id="7638f-198">443</span></span>  <br/> |<span data-ttu-id="7638f-199">443</span><span class="sxs-lookup"><span data-stu-id="7638f-199">443</span></span>  <br/> |<span data-ttu-id="7638f-200">前端</span><span class="sxs-lookup"><span data-stu-id="7638f-200">Front End</span></span>  <br/> <span data-ttu-id="7638f-201">5061</span><span class="sxs-lookup"><span data-stu-id="7638f-201">5061</span></span>  <br/> |<span data-ttu-id="7638f-202">Source</span><span class="sxs-lookup"><span data-stu-id="7638f-202">Source</span></span>  <br/> |<span data-ttu-id="7638f-203">HTTPS</span><span class="sxs-lookup"><span data-stu-id="7638f-203">HTTPS</span></span>  <br/> |
|<span data-ttu-id="7638f-204">\<pool\>web-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="7638f-204">\<pool\>web-int_mco_80_vs</span></span>  <br/> <span data-ttu-id="7638f-205">80</span><span class="sxs-lookup"><span data-stu-id="7638f-205">80</span></span>  <br/> |<span data-ttu-id="7638f-206">80</span><span class="sxs-lookup"><span data-stu-id="7638f-206">80</span></span>  <br/> |<span data-ttu-id="7638f-207">前端</span><span class="sxs-lookup"><span data-stu-id="7638f-207">Front End</span></span>  <br/> <span data-ttu-id="7638f-208">5061</span><span class="sxs-lookup"><span data-stu-id="7638f-208">5061</span></span>  <br/> |<span data-ttu-id="7638f-209">Source</span><span class="sxs-lookup"><span data-stu-id="7638f-209">Source</span></span>  <br/> |<span data-ttu-id="7638f-210">HTTP</span><span class="sxs-lookup"><span data-stu-id="7638f-210">HTTP</span></span>  <br/> |
   
<span data-ttu-id="7638f-211">**前端服务器用户池 - HLB 外部接口**</span><span class="sxs-lookup"><span data-stu-id="7638f-211">**Front End Server User Pool - HLB External Interface**</span></span>

|<span data-ttu-id="7638f-212">**虚拟 IP/端口**</span><span class="sxs-lookup"><span data-stu-id="7638f-212">**Virtual IP/Port**</span></span>|<span data-ttu-id="7638f-213">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="7638f-213">**Node Port**</span></span>|<span data-ttu-id="7638f-214">**节点计算机/监视器**</span><span class="sxs-lookup"><span data-stu-id="7638f-214">**Node Machine/Monitor**</span></span>|<span data-ttu-id="7638f-215">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="7638f-215">**Persistence Profile**</span></span>|<span data-ttu-id="7638f-216">**备注**</span><span class="sxs-lookup"><span data-stu-id="7638f-216">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7638f-217">\<pool\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="7638f-217">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="7638f-218">443</span><span class="sxs-lookup"><span data-stu-id="7638f-218">443</span></span>  <br/> |<span data-ttu-id="7638f-219">4443</span><span class="sxs-lookup"><span data-stu-id="7638f-219">4443</span></span>  <br/> |<span data-ttu-id="7638f-220">前端</span><span class="sxs-lookup"><span data-stu-id="7638f-220">Front End</span></span>  <br/> <span data-ttu-id="7638f-221">5061</span><span class="sxs-lookup"><span data-stu-id="7638f-221">5061</span></span>  <br/> |<span data-ttu-id="7638f-222">无</span><span class="sxs-lookup"><span data-stu-id="7638f-222">None</span></span>  <br/> |<span data-ttu-id="7638f-223">HTTPS</span><span class="sxs-lookup"><span data-stu-id="7638f-223">HTTPS</span></span>  <br/> |
|<span data-ttu-id="7638f-224">\<pool\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="7638f-224">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="7638f-225">80</span><span class="sxs-lookup"><span data-stu-id="7638f-225">80</span></span>  <br/> |<span data-ttu-id="7638f-226">8080</span><span class="sxs-lookup"><span data-stu-id="7638f-226">8080</span></span>  <br/> |<span data-ttu-id="7638f-227">前端</span><span class="sxs-lookup"><span data-stu-id="7638f-227">Front End</span></span>  <br/> <span data-ttu-id="7638f-228">5061</span><span class="sxs-lookup"><span data-stu-id="7638f-228">5061</span></span>  <br/> |<span data-ttu-id="7638f-229">无</span><span class="sxs-lookup"><span data-stu-id="7638f-229">None</span></span>  <br/> |<span data-ttu-id="7638f-230">HTTP</span><span class="sxs-lookup"><span data-stu-id="7638f-230">HTTP</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="7638f-231">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="7638f-231">DNS Load Balancing</span></span>
<span data-ttu-id="7638f-232"><a name="BKMK_DNSLoadBalancing"> </a></span><span class="sxs-lookup"><span data-stu-id="7638f-232"><a name="BKMK_DNSLoadBalancing"> </a></span></span>

<span data-ttu-id="7638f-233">Skype for Business Server 支持 DNS 负载平衡，这是一种可大大减少网络上负载平衡的管理开销的软件解决方案。</span><span class="sxs-lookup"><span data-stu-id="7638f-233">Skype for Business Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="7638f-234">DNS 负载平衡可平衡 Skype for Business Server 特有的网络流量，例如 SIP 流量和媒体流量。</span><span class="sxs-lookup"><span data-stu-id="7638f-234">DNS load balancing balances the network traffic that is unique to Skype for Business Server, such as SIP traffic and media traffic.</span></span>
  
<span data-ttu-id="7638f-235">如果部署 DNS 负载平衡，将最大程度地减少组织的硬件负载平衡器管理开销。</span><span class="sxs-lookup"><span data-stu-id="7638f-235">If you deploy DNS load balancing, your organization's administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="7638f-236">此外，还可以免除解决 SIP 流量负载平衡器配置错误相关问题的复杂过程。</span><span class="sxs-lookup"><span data-stu-id="7638f-236">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="7638f-237">您还可以阻止服务器连接以使服务器脱机。</span><span class="sxs-lookup"><span data-stu-id="7638f-237">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="7638f-238">同时，DNS 负载平衡还可确保硬件负载平衡器问题不会影响 SIP 流量的元素，例如基本呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="7638f-238">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="7638f-239">下图显示了一个同时包括内部和外部 DNS 负载平衡的示例：</span><span class="sxs-lookup"><span data-stu-id="7638f-239">The following diagram shows an example that includes both internal and external DNS load balancing:</span></span> 
  
<span data-ttu-id="7638f-240">**使用公用 IPv4 地址的边缘网络图**</span><span class="sxs-lookup"><span data-stu-id="7638f-240">**Edge network diagram using Public IPv4 addresses**</span></span>

![DNS 网络图示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
<span data-ttu-id="7638f-242">与为所有类型的流量使用硬件负载平衡器相比，使用 DNS 负载平衡还可以降低您购买硬件负载平衡器的成本。</span><span class="sxs-lookup"><span data-stu-id="7638f-242">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="7638f-243">你应该使用已通过与 Skype for Business Server 的互操作性资格测试的负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="7638f-243">You should use load balancers that have passed interoperability qualification testing with Skype for Business Server.</span></span> <span data-ttu-id="7638f-244">有关负载平衡器互操作性测试的详细信息，请参阅[Lync Server 2010 Load Balancer Partners。](https://go.microsoft.com/fwlink/p/?linkId=202452)</span><span class="sxs-lookup"><span data-stu-id="7638f-244">For details about load balancer interoperability testing, see [Lync Server 2010 Load Balancer Partners](https://go.microsoft.com/fwlink/p/?linkId=202452).</span></span> <span data-ttu-id="7638f-245">内容适用于 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="7638f-245">The content there applies to Skype for Business Server.</span></span>
  
<span data-ttu-id="7638f-246">前端池、边缘服务器池、控制器池和独立的中介服务器池都支持 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-246">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>
  
<span data-ttu-id="7638f-247">DNS 负载平衡通常在应用程序级别实现。</span><span class="sxs-lookup"><span data-stu-id="7638f-247">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="7638f-248">应用程序 (例如，运行 Skype for Business) 的客户端，如果对池完全限定域名 (FQDN) 使用) 记录查询，则通过连接到从 DNS A 和 AAAA (返回的 IP 地址之一来尝试连接到池中的服务器。</span><span class="sxs-lookup"><span data-stu-id="7638f-248">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span> 
  
<span data-ttu-id="7638f-249">例如，如果名为 pool01.contoso.com 的池中有三台前端服务器，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="7638f-249">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>
  
- <span data-ttu-id="7638f-250">运行 Skype for Business 的客户端查询 DNS pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7638f-250">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="7638f-251">查询返回三个 IP 地址，并按如下 (按以下顺序进行缓存) ：</span><span class="sxs-lookup"><span data-stu-id="7638f-251">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="7638f-252">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="7638f-252">pool01.contoso.com 192.168.10.90</span></span>
    
    <span data-ttu-id="7638f-253">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="7638f-253">pool01.contoso.com 192.168.10.91</span></span>
    
    <span data-ttu-id="7638f-254">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="7638f-254">pool01.contoso.com 192.168.10.92</span></span>
    
- <span data-ttu-id="7638f-255">客户端尝试建立与其中一个 IP 地址 (TCP) 协议。</span><span class="sxs-lookup"><span data-stu-id="7638f-255">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="7638f-256">如果失败，客户端将尝试缓存中的下一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7638f-256">If that fails, the client tries the next IP address in the cache.</span></span>
    
- <span data-ttu-id="7638f-257">如果 TCP 连接成功，客户端将协商 TLS 以连接到主注册器pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7638f-257">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="7638f-258">如果客户端在未成功连接的情况下尝试所有缓存的条目，将通知用户当前没有运行 Skype for Business Server 的服务器可用。</span><span class="sxs-lookup"><span data-stu-id="7638f-258">If the client tries all cached entries without a successful connection, the user is notified that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7638f-259">基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR) 它通常通过依赖 DNS 来提供与池中服务器对应的不同 IP 地址顺序来引用负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-259">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="7638f-260">通常 DNS RR 仅启用负载分布，但不启用故障转移。</span><span class="sxs-lookup"><span data-stu-id="7638f-260">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="7638f-261">例如，如果连接到 DNS A 和 AAAA 返回的一个 IP 地址 (如果使用 IPv6 寻址查询失败) 连接将失败。</span><span class="sxs-lookup"><span data-stu-id="7638f-261">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="7638f-262">因此，DNS 轮循机制本身不如基于 DNS 的负载平衡可靠。</span><span class="sxs-lookup"><span data-stu-id="7638f-262">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="7638f-263">可以将 DNS 轮循机制与 DNS 负载平衡结合使用。</span><span class="sxs-lookup"><span data-stu-id="7638f-263">You can use DNS round robin in conjunction with DNS load balancing.</span></span> 
  
<span data-ttu-id="7638f-264">DNS 负载平衡用于以下各项：</span><span class="sxs-lookup"><span data-stu-id="7638f-264">DNS load balancing is used for the following:</span></span>
  
- <span data-ttu-id="7638f-265">对边缘服务器的服务器到服务器 SIP 进行负载平衡</span><span class="sxs-lookup"><span data-stu-id="7638f-265">Load balancing server-to-server SIP to the Edge Servers</span></span>
    
- <span data-ttu-id="7638f-266">负载平衡统一通信应用程序服务 (作为) 应用程序（如会议自动助理、响应组和呼叫呼叫应答）</span><span class="sxs-lookup"><span data-stu-id="7638f-266">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>
    
- <span data-ttu-id="7638f-267">阻止与 从而阻止与 一 ("排出"的新连接) </span><span class="sxs-lookup"><span data-stu-id="7638f-267">Preventing new connections to UCAS applications (also known as "draining")</span></span>
    
- <span data-ttu-id="7638f-268">在客户端和边缘服务器之间实现所有客户端到服务器流量的负载平衡</span><span class="sxs-lookup"><span data-stu-id="7638f-268">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>
    
<span data-ttu-id="7638f-269">DNS 负载平衡不能用于以下各项：</span><span class="sxs-lookup"><span data-stu-id="7638f-269">DNS load balancing cannot be used for the following:</span></span>
  
- <span data-ttu-id="7638f-270">到控制器或前端服务器的客户端到服务器 Web 流量</span><span class="sxs-lookup"><span data-stu-id="7638f-270">Client-to-server web traffic to Director or Front End Servers</span></span>
    
<span data-ttu-id="7638f-271">DNS 负载平衡和联合流量：</span><span class="sxs-lookup"><span data-stu-id="7638f-271">DNS load balancing and federated traffic:</span></span>
  
<span data-ttu-id="7638f-272">如果 DNS SRV 查询返回了多个 DNS 记录，则访问边缘服务始终选取具有最低数字优先级和最高数字权重的 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="7638f-272">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="7638f-273">Internet 工程任务组文档"用于指定服务位置的 DNS RR (DNS SRV) " [RFC 2782，DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) 指定如果定义了多个 DNS SRV 记录，则首先使用优先级，然后使用权重。</span><span class="sxs-lookup"><span data-stu-id="7638f-273">The Internet Engineering Task Force document "A DNS RR for specifying the location of services (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="7638f-274">例如，DNS SRV 记录 A 的权重为 20，优先级为 40，DNS SRV 记录 B 的权重为 10，优先级为 50。</span><span class="sxs-lookup"><span data-stu-id="7638f-274">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="7638f-275">将选择优先级为 40 的 DNS SRV 记录 A。</span><span class="sxs-lookup"><span data-stu-id="7638f-275">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="7638f-276">以下规则适用于 DNS SRV 记录选择：</span><span class="sxs-lookup"><span data-stu-id="7638f-276">The following rules apply to DNS SRV record selection:</span></span>
  
- <span data-ttu-id="7638f-277">首先考虑优先级。</span><span class="sxs-lookup"><span data-stu-id="7638f-277">Priority is considered first.</span></span> <span data-ttu-id="7638f-278">客户端必须尝试联系 DNS SRV 记录定义的目标主机，该目标主机的编号优先级最低。</span><span class="sxs-lookup"><span data-stu-id="7638f-278">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="7638f-279">应按权重字段定义的顺序尝试具有相同优先级的目标。</span><span class="sxs-lookup"><span data-stu-id="7638f-279">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>
    
- <span data-ttu-id="7638f-280">权重字段指定优先级相同的条目的相对权重。</span><span class="sxs-lookup"><span data-stu-id="7638f-280">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="7638f-281">较大权重的选定概率应成比例提高。</span><span class="sxs-lookup"><span data-stu-id="7638f-281">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="7638f-282">当没有任何服务器选择时，DNS 管理员应使用权重 0。</span><span class="sxs-lookup"><span data-stu-id="7638f-282">DNS administrators SHOULD use Weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="7638f-283">如果记录包含大于 0 的权重，则选择权重为 0 的记录的可能性应该很小。</span><span class="sxs-lookup"><span data-stu-id="7638f-283">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>
    
<span data-ttu-id="7638f-284">如果返回多个优先级和权重相同的 DNS SRV 记录，访问边缘服务将选择首先从 DNS 服务器收到的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="7638f-284">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="7638f-285">前端池和控制器池中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="7638f-285">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="7638f-p130">您可以使用 DNS 负载平衡来平衡前端池和控制器池中的 SIP 流量。部署 DNS 负载平衡后，仍需要对这些池使用硬件负载平衡器，但仅用于客户端到服务器的 HTTPS 流量。硬件负载平衡器用于通过端口 443 和 80 从客户端传入的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="7638f-p130">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> 
  
<span data-ttu-id="7638f-289">尽管这些池中仍需要硬件负载平衡器，但这些负载平衡器的安装和管理主要用于硬件负载平衡器管理员熟悉的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="7638f-289">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="7638f-290">支持旧客户端和服务器并对其进行 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="7638f-290">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="7638f-291">DNS 负载平衡仅支持运行 Skype for Business Server 或 Lync Server 2010 的服务器以及 Lync 2013 和 Skype for Business 客户端的自动故障转移。</span><span class="sxs-lookup"><span data-stu-id="7638f-291">DNS load balancing supports automatic failover only for servers running Skype for Business Server or Lync Server 2010, and for Lync 2013 and Skype for Business clients.</span></span> <span data-ttu-id="7638f-292">早期版本的客户端和 Office Communications Server 仍可连接到运行 DNS 负载平衡的池，但如果它们无法连接到 DNS 负载平衡引用的第一台服务器，则它们无法故障转移到池中的另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="7638f-292">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span> 
  
<span data-ttu-id="7638f-293">此外，如果使用的是 Exchange UM，则必须至少使用 Exchange 2010 SP1 才能获得对 Skype for Business Server DNS 负载平衡的支持。</span><span class="sxs-lookup"><span data-stu-id="7638f-293">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Skype for Business Server DNS load balancing.</span></span> <span data-ttu-id="7638f-294">如果使用早期版本的 Exchange，则用户将不会具有这些 Exchange UM 方案的故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="7638f-294">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>
  
- <span data-ttu-id="7638f-295">在手机上播放企业语音邮件</span><span class="sxs-lookup"><span data-stu-id="7638f-295">Playing their Enterprise voicemail on their phone</span></span>
    
- <span data-ttu-id="7638f-296">转接来自 Exchange UM 自动助理的呼叫</span><span class="sxs-lookup"><span data-stu-id="7638f-296">Transferring calls from an Exchange UM Auto Attendant</span></span>
    
<span data-ttu-id="7638f-297">其他所有 Exchange UM 方案将正常工作。</span><span class="sxs-lookup"><span data-stu-id="7638f-297">All other Exchange UM scenarios will work properly.</span></span>
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="7638f-298">在前端池和控制器池中部署 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="7638f-298">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>
<span data-ttu-id="7638f-299"><a name="BK_FE_Dir"> </a></span><span class="sxs-lookup"><span data-stu-id="7638f-299"><a name="BK_FE_Dir"> </a></span></span>

<span data-ttu-id="7638f-300">在前端池和控制器池中部署 DNS 负载平衡时，需要使用 FQDN 和 DNS 记录执行一些额外步骤。</span><span class="sxs-lookup"><span data-stu-id="7638f-300">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>
  
- <span data-ttu-id="7638f-301">使用 DNS 负载平衡的池必须具有两个 FQDN：DNS 负载平衡 (（如 pool01.contoso.com) ）使用的常规池 FQDN，并解析为池中服务器的物理 IP;池的 Web 服务 (例如 web01.contoso.com) 的另一个 FQDN（解析为池的虚拟 IP 地址）。</span><span class="sxs-lookup"><span data-stu-id="7638f-301">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool's Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span> 
    
    <span data-ttu-id="7638f-302">在拓扑生成器中，如果要为池部署 DNS 负载平衡，若要为池的 Web 服务创建此额外的 FQDN，您必须选中"覆盖内部 Web 服务池 **FQDN"** 复选框，并键入"为此池指定 **Web** 服务 URL"页中的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7638f-302">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool's Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>
    
- <span data-ttu-id="7638f-p133">要支持 DNS 负载平衡使用的 FQDN，必须设置 DNS，以便将池 FQDN（例如 pool01.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。您应该仅包含当前部署的服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7638f-p133">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="7638f-305">如果您具有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7638f-305">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="7638f-306">例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 **pool01.contoso.com，** 则不能将 pool01.contoso.com **用于另** 一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7638f-306">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="7638f-307">如果还要部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7638f-307">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="7638f-308">如果决定使用自定义的 FQDN 覆盖内部 Web 服务，则每个 FQDN 都必须与任何其他前端池、控制器或控制器池是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7638f-308">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
### <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="7638f-309">边缘服务器池中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="7638f-309">DNS Load Balancing on Edge Server Pools</span></span>
<span data-ttu-id="7638f-310"><a name="BK_Edge"> </a></span><span class="sxs-lookup"><span data-stu-id="7638f-310"><a name="BK_Edge"> </a></span></span>

<span data-ttu-id="7638f-p135">您可以在边缘服务器池中部署 DNS 负载平衡。如果要进行部署，则必须了解以下注意事项。</span><span class="sxs-lookup"><span data-stu-id="7638f-p135">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>
  
<span data-ttu-id="7638f-313">在边缘服务器中使用 DNS 负载平衡会导致以下方案中丧失故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="7638f-313">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>
  
- <span data-ttu-id="7638f-314">与运行 Lync Server 2010 之前发布的 Skype for Business Server 版本的组织联盟。</span><span class="sxs-lookup"><span data-stu-id="7638f-314">Federation with organizations that are running versions of Skype for Business Server released prior to Lync Server 2010.</span></span>
    
- <span data-ttu-id="7638f-315">除了基于 XMPP 的提供商和服务器（如 Google Talk）（当前唯一受支持的 XMPP 合作伙伴）之外，与公共即时消息 (IM) 服务 AOL 和 Yahoo！的用户交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="7638f-315">Instant message exchange with users of public instant messaging (IM) services AOL and Yahoo!, in addition to XMPP-based providers and servers, such as Google Talk, currently the only supported XMPP partner.</span></span>
    
<span data-ttu-id="7638f-316">只要池中的所有边缘服务器都在运行，这些方案就会正常工作；但是如果某台边缘服务器不可用，则发送到该服务器的对这些方案的所有请求都将失败，而不会路由到其他边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="7638f-316">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>
  
 <span data-ttu-id="7638f-317">如果使用的是 Exchange UM，则必须至少使用 Exchange 2013 才能在边缘上获取对 Skype for Business Server DNS 负载平衡的支持。</span><span class="sxs-lookup"><span data-stu-id="7638f-317">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Skype for Business Server DNS load balancing on Edge.</span></span> <span data-ttu-id="7638f-318">如果使用早期版本的 Exchange，则远程用户将不会具有这些 Exchange UM 方案的故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="7638f-318">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>
  
- <span data-ttu-id="7638f-319">在手机上播放企业语音邮件</span><span class="sxs-lookup"><span data-stu-id="7638f-319">Playing their Enterprise voicemail on their phone</span></span>
    
- <span data-ttu-id="7638f-320">转接来自 Exchange UM 自动助理的呼叫</span><span class="sxs-lookup"><span data-stu-id="7638f-320">Transferring calls from an Exchange UM Auto Attendant</span></span>
    
<span data-ttu-id="7638f-321">其他所有 Exchange UM 方案将正常工作。</span><span class="sxs-lookup"><span data-stu-id="7638f-321">All other Exchange UM scenarios will work properly.</span></span>
  
<span data-ttu-id="7638f-p137">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-p137">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="7638f-324">在边缘服务器池中部署 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="7638f-324">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="7638f-325">要在边缘服务器池的外部接口上部署 DNS 负载平衡，需要具有以下 DNS 条目：</span><span class="sxs-lookup"><span data-stu-id="7638f-325">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>
  
- <span data-ttu-id="7638f-326">对于访问边缘服务，池中每台服务器都需要一个条目。</span><span class="sxs-lookup"><span data-stu-id="7638f-326">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="7638f-327">每个条目都必须解析访问边缘服务的 FQDN (例如，sip.contoso.com) 解析为池中其中一台边缘服务器上访问边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7638f-327">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>
    
- <span data-ttu-id="7638f-328">对于 Web 会议边缘服务，池中每台服务器都需要一个条目。</span><span class="sxs-lookup"><span data-stu-id="7638f-328">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="7638f-329">每个条目都必须将 Web 会议边缘服务的 FQDN (例如，webconf.contoso.com) 解析为池中其中一台边缘服务器的 Web 会议边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7638f-329">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>
    
- <span data-ttu-id="7638f-330">对于音频/视频边缘服务，池中每台服务器都需要一个条目。</span><span class="sxs-lookup"><span data-stu-id="7638f-330">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="7638f-331">每个条目都必须解析音频/视频边缘服务的 FQDN (例如，av.contoso.com) 解析为池中其中一台边缘服务器的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7638f-331">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>
    
<span data-ttu-id="7638f-332">要在边缘服务器池的内部接口上部署 DNS 负载平衡，必须添加一条将此边缘服务器池的内部 FQDN 解析为该池中每台服务器的 IP 地址的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="7638f-332">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="7638f-333">在中介服务器池中使用 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="7638f-333">Using DNS Load Balancing on Mediation Server Pools</span></span>
<span data-ttu-id="7638f-334"><a name="BK_Mediation"> </a></span><span class="sxs-lookup"><span data-stu-id="7638f-334"><a name="BK_Mediation"> </a></span></span>

<span data-ttu-id="7638f-p141">可以在独立的中介服务器池上使用 DNS 负载平衡。所有 SIP 和媒体流量都通过 DNS 负载平衡进行平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-p141">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>
  
<span data-ttu-id="7638f-337">要在中介服务器池中部署 DNS 负载平衡，必须设置 DNS，以便将池 FQDN（例如 mediationpool1.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。</span><span class="sxs-lookup"><span data-stu-id="7638f-337">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="7638f-338">使用 DNS 负载平衡阻止到服务器的流量</span><span class="sxs-lookup"><span data-stu-id="7638f-338">Blocking Traffic to a Server With DNS Load Balancing</span></span>
<span data-ttu-id="7638f-339"><a name="BK_Mediation"> </a></span><span class="sxs-lookup"><span data-stu-id="7638f-339"><a name="BK_Mediation"> </a></span></span>

<span data-ttu-id="7638f-340">如果使用 DNS 负载平衡并且需要阻止到特定计算机的流量，则仅从池 FQDN 中删除 IP 地址条目是不够的。</span><span class="sxs-lookup"><span data-stu-id="7638f-340">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="7638f-341">还必须删除计算机的 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="7638f-341">You must remove the DNS entry for the computer as well.</span></span> 
  
<span data-ttu-id="7638f-342">请注意，对于服务器到服务器的流量，Skype for Business Server 使用拓扑感知负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7638f-342">Note that for server-to-server traffic, Skype for Business Server uses topology-aware load balancing.</span></span> <span data-ttu-id="7638f-343">服务器读取中央管理存储中的已发布拓扑以获取拓扑中服务器的 FQDN，并自动在服务器之间分发流量。</span><span class="sxs-lookup"><span data-stu-id="7638f-343">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="7638f-344">若要阻止服务器接收服务器到服务器的流量，必须从拓扑中删除服务器。</span><span class="sxs-lookup"><span data-stu-id="7638f-344">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span> 
  

