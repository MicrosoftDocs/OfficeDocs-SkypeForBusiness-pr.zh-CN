---
title: Skype for Business 的负载平衡要求
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 摘要： 查看的负载平衡的企业服务器实现 Skype 之前的注意事项。
ms.openlocfilehash: a7e8e70088c83276c36334c5d9a1e3be1538ca38
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206485"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a><span data-ttu-id="30149-103">Skype for Business 的负载平衡要求</span><span class="sxs-lookup"><span data-stu-id="30149-103">Load balancing requirements for Skype for Business</span></span>
 
<span data-ttu-id="30149-104">**摘要：** 查看的负载平衡的企业服务器实现 Skype 之前的注意事项。</span><span class="sxs-lookup"><span data-stu-id="30149-104">**Summary:** Review the load balancing considerations before implementing Skype for Business Server.</span></span>
  
<span data-ttu-id="30149-105">负载平衡分布在池中的服务器之间的流量。</span><span class="sxs-lookup"><span data-stu-id="30149-105">Load balancing distributes traffic among the servers in a pool.</span></span> <span data-ttu-id="30149-106">如果您有前端池、 中介服务器池或边缘服务器池，需要部署负载平衡的这些池。</span><span class="sxs-lookup"><span data-stu-id="30149-106">If you have Front End pools, Mediation Server pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span>
  
<span data-ttu-id="30149-107">Skype 业务服务器支持的负载平衡的客户端到服务器的通信解决方案的两种类型： 域名系统 (DNS) 负载平衡和硬件负载平衡通常 （缩写为 HLB）。</span><span class="sxs-lookup"><span data-stu-id="30149-107">Skype for Business Server supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing (often abbreviated as HLB).</span></span> <span data-ttu-id="30149-108">DNS 负载平衡提供几个优点包括简化管理、 更高效疑难解答、 和隔离何种业务服务器流量从任何潜在的硬件负载平衡器问题您 Skype 的能力。</span><span class="sxs-lookup"><span data-stu-id="30149-108">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Skype for Business Server traffic from any potential hardware load balancer problems.</span></span>
  
<span data-ttu-id="30149-109">决定为您自己的负载平衡解决方案适合在您部署中，每个池，但请记住以下限制：</span><span class="sxs-lookup"><span data-stu-id="30149-109">Decide for yourself which load balancing solution is appropriate for each pool in your deployment, but keep in mind the following restrictions:</span></span> 
  
- <span data-ttu-id="30149-p103">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能在一个接口上使用 DNS 负载平衡的同时，在另一个接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>
    
- <span data-ttu-id="30149-p104">某些类型的流量需要硬件负载平衡器。例如，HTTP 流量需要硬件平衡负载器而非 DNS 负载平衡。DNS 负载平衡对客户端到服务器的 Web 流量不起作用。</span><span class="sxs-lookup"><span data-stu-id="30149-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>
    
<span data-ttu-id="30149-p105">如果选择对某个池使用 DNS 负载平衡，但仍需对流量（如 HTTP 流量）实现硬件负载平衡器，则会大大简化硬件负载平衡器的管理。例如，配置硬件负载平衡器将更简单，因为它仅管理 HTTP 和 HTTPS 流量，而所有其他协议将由 DNS 负载平衡管理。有关详细信息，请参阅 [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing)。</span><span class="sxs-lookup"><span data-stu-id="30149-p105">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified. For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing. For details, see [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing).</span></span> 
  
<span data-ttu-id="30149-118">对于服务器到服务器通信，Skype 业务服务器使用拓扑感知负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-118">For server-to-server traffic, Skype for Business Server uses topology-aware load balancing.</span></span> <span data-ttu-id="30149-119">服务器阅读要获取在拓扑中，服务器的 Fqdn 的中央管理存储中的已发布的拓扑，并自动将在服务器之间的流量分发。</span><span class="sxs-lookup"><span data-stu-id="30149-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="30149-120">管理员不必设置或管理此类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-120">Administrators do not need to set up or manage this type of load balancing.</span></span> 
  
<span data-ttu-id="30149-p107">如果使用 DNS 负载平衡并且需要阻止至特定计算机的流量，则仅仅删除池 FQDN 中的 IP 地址条目是不够的。您还必须删除计算机的 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="30149-p107">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span> 
  
## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="30149-123">硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="30149-123">Hardware load balancer requirements</span></span>

<span data-ttu-id="30149-124">扩展的业务服务器 Skype 的合并的边缘拓扑进行了优化的主要与其他组织使用 Skype 业务服务器或 Lync Server 联盟的新部署的 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-124">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Skype for Business Server or Lync Server.</span></span> <span data-ttu-id="30149-125">如果任何以下方案需要高可用性，硬件负载平衡器必须使用边缘服务器池上的以下：</span><span class="sxs-lookup"><span data-stu-id="30149-125">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span> 
  
- <span data-ttu-id="30149-126">与使用 Office Communications Server 2007 R2 或 Office Communications Server 2007 的组织建立联盟</span><span class="sxs-lookup"><span data-stu-id="30149-126">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>
    
- <span data-ttu-id="30149-127">Exchange UM sp1 之前 Exchange 2010 UM Exchange 使用的远程用户</span><span class="sxs-lookup"><span data-stu-id="30149-127">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>
    
- <span data-ttu-id="30149-128">与公共 IM 用户的连接</span><span class="sxs-lookup"><span data-stu-id="30149-128">Connectivity to public IM users</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="30149-p109">不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-p109">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="30149-p110">如果使用硬件负载平衡器，则为内部网络连接部署的负载平衡器必须配置为仅对发往运行访问边缘服务和 A/V 边缘服务的服务器的流量进行负载平衡。它不能对发往内部 Web 会议边缘服务或内部 XMPP 代理服务的流量进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-p110">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="30149-133">直接服务器返回 (DSR) NAT 不支持与 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-133">The direct server return (DSR) NAT is not supported with Skype for Business Server.</span></span> 
  
<span data-ttu-id="30149-134">若要确定您的硬件负载平衡器是否支持所需的 Skype 业务服务器所需的功能，请参阅[for Business 的 Skype 的基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="30149-134">To determine whether your hardware load balancer supports the necessary features required by Skype for Business Server, see [Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="30149-135">运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="30149-135">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="30149-136">下面是运行 A 的边缘服务器的硬件负载平衡器要求 / V 边缘服务：</span><span class="sxs-lookup"><span data-stu-id="30149-136">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>
  
- <span data-ttu-id="30149-p111">对内部和外部端口 443 关闭 TCP nagling。Nagling 是将若干小数据包整合到单个大数据包以提高传输效率的过程。</span><span class="sxs-lookup"><span data-stu-id="30149-p111">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>
    
- <span data-ttu-id="30149-139">关闭外部端口范围 50000-59999 TCP nagling。</span><span class="sxs-lookup"><span data-stu-id="30149-139">Turn off TCP nagling for external port range 50,000 - 59,999.</span></span> 
    
- <span data-ttu-id="30149-140">请不要对内部或外部防火墙使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="30149-140">Do not use NAT on the internal or external firewall.</span></span> 
    
- <span data-ttu-id="30149-141">边缘内部接口必须位于不同网络边缘服务器外部接口上，且必须禁用它们之间的路由。</span><span class="sxs-lookup"><span data-stu-id="30149-141">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span> 
    
- <span data-ttu-id="30149-142">外部接口的边缘服务器运行 A / V 边缘服务必须使用公共可路由 IP 地址和 NAT 或端口上的任何边缘外部 IP 地址的转换。</span><span class="sxs-lookup"><span data-stu-id="30149-142">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span> 
    
- <span data-ttu-id="30149-143">负载平衡器不得更改客户端的源地址。</span><span class="sxs-lookup"><span data-stu-id="30149-143">The load balancer must not change the source address of the client.</span></span>
    
### <a name="other-hardware-load-balancer-requirements"></a><span data-ttu-id="30149-144">其他硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="30149-144">Other Hardware Load Balancer requirements</span></span>

<span data-ttu-id="30149-145">基于 cookie 的相关性要求将会显著降低中 Skype 业务服务器 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="30149-145">Cookie-based affinity requirements are greatly reduced in Skype for Business Server for Web services.</span></span> <span data-ttu-id="30149-146">如果您部署 Skype 业务服务器，并将不会保留的所有 Lync Server 2010 前端服务器或前端池，则不需要基于 cookie 的持久性。</span><span class="sxs-lookup"><span data-stu-id="30149-146">If you are deploying Skype for Business Server and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="30149-147">但是，如果将临时或永久保留的所有 Lync Server 2010 前端服务器或前端池，您仍使用基于 cookie 的持久性，它为部署和 Lync Server 2010 的配置。</span><span class="sxs-lookup"><span data-stu-id="30149-147">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="30149-148">**如果您决定使用基于 Cookie 的相关性，但您的部署不需要它**，如此做没有任何负面影响。</span><span class="sxs-lookup"><span data-stu-id="30149-148">**If you decide to use cookie-based affinity even though your deployment does not require it**, there is no negative impact to doing so.</span></span> 
  
<span data-ttu-id="30149-149">对于 **不使用**基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="30149-149">For deployments that **will not use** cookie-based affinity:</span></span>
  
- <span data-ttu-id="30149-150">在端口 4443 的反向代理发布规则上，将“**转发主机头**”设置为 True。</span><span class="sxs-lookup"><span data-stu-id="30149-150">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="30149-151">这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="30149-151">This will ensure that the original URL is forwarded.</span></span>
    
<span data-ttu-id="30149-152">对于**将使用**基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="30149-152">For deployments that **will use** cookie-based affinity:</span></span>
  
- <span data-ttu-id="30149-p114">在端口 4443 的反向代理发布规则上，将“**转发主机头**”设置为 True。这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="30149-p114">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>
    
- <span data-ttu-id="30149-155">不得将硬件负载平衡器 Cookie 标记为 httpOnly</span><span class="sxs-lookup"><span data-stu-id="30149-155">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>
    
- <span data-ttu-id="30149-156">硬件负载平衡器 Cookie 不得具有过期时间</span><span class="sxs-lookup"><span data-stu-id="30149-156">Hardware load balancer cookie MUST NOT have an expiration time</span></span>
    
- <span data-ttu-id="30149-157">硬件负载平衡器 Cookie 必须名为 **MS-WSMAN**（这是 Web 服务预期的值，不能更改）</span><span class="sxs-lookup"><span data-stu-id="30149-157">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>
    
- <span data-ttu-id="30149-p115">必须在其传入 HTTP 请求没有 Cookie 的每个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie 都是如此。如果负载平衡器将 Cookie 插入优化为每个 TCP 连接只发生一次，则不得使用该优化</span><span class="sxs-lookup"><span data-stu-id="30149-p115">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>
    
> [!NOTE]
> <span data-ttu-id="30149-160">典型的硬件负载平衡器配置使用源地址相关性和 20 分钟 TCP 会话生存期，因为会话状态维护通过客户端使用这对于 Lync Server 和 Lync 2013 客户端和/或和应用程序交互。</span><span class="sxs-lookup"><span data-stu-id="30149-160">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span> 
  
<span data-ttu-id="30149-161">如果部署移动设备，则您的硬件负载平衡器必须能对 TCP 会话中的单个请求进行负载平衡（实际上，您必须能基于目标 IP 地址对单个请求进行负载平衡）。</span><span class="sxs-lookup"><span data-stu-id="30149-161">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="30149-162">如果您正在部署移动设备，硬件负载平衡器必须能够单独负载平衡的 TCP 连接中的每个请求。</span><span class="sxs-lookup"><span data-stu-id="30149-162">If you are deploying mobile devices, your hardware load balancer must be able to individually load balance each request within a TCP connection.</span></span> <span data-ttu-id="30149-163">最新的 Apple iOS 移动应用程序要求传输层安全性 (TLS) 1.2 版。</span><span class="sxs-lookup"><span data-stu-id="30149-163">The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="30149-164">有关第三方硬件负载平衡器的详细信息，请参阅[for Business 的 Skype 的基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="30149-164">For details on third party hardware load balancers, see [Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span>  
  
<span data-ttu-id="30149-165">以下是控制器和前端池 Web 服务的硬件负载平衡器要求：</span><span class="sxs-lookup"><span data-stu-id="30149-165">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>
  
- <span data-ttu-id="30149-166">对于内部 Web 服务 VIP，在硬件负载平衡器上设置 Source_addr 持久性（内部端口 80 和 443）。</span><span class="sxs-lookup"><span data-stu-id="30149-166">For internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="30149-167">对于业务服务器 Skype，Source_addr 持久性意味着，来自单个 IP 地址的多个连接始终发送到一台服务器来维护会话状态。</span><span class="sxs-lookup"><span data-stu-id="30149-167">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>
    
- <span data-ttu-id="30149-168">使用 TCP 空闲超时 1800 秒。</span><span class="sxs-lookup"><span data-stu-id="30149-168">Use TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="30149-169">在反向代理和下一个跃点池的硬件负载平衡器之间防火墙中，创建一个规则来允许 https： 通信端口 4443 上，从反向代理的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="30149-169">On the firewall between the reverse proxy and the next hop pool's hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer.</span></span> <span data-ttu-id="30149-170">必须将硬件负载平衡器配置为侦听端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="30149-170">The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="30149-171">硬件负载平衡器关联要求的摘要</span><span class="sxs-lookup"><span data-stu-id="30149-171">Summary of Hardware Load Balancer Affinity Requirements</span></span>

|<span data-ttu-id="30149-172">**客户端/用户位置**</span><span class="sxs-lookup"><span data-stu-id="30149-172">**Client/user location**</span></span>|<span data-ttu-id="30149-173">**外部 Web 服务 FQDN 关联要求**</span><span class="sxs-lookup"><span data-stu-id="30149-173">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="30149-174">**内部 Web 服务 FQDN 关联要求**</span><span class="sxs-lookup"><span data-stu-id="30149-174">**Internal web services FQDN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="30149-175">Lync Web App （内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="30149-175">Lync Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="30149-176">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="30149-176">Mobile device (internal and external users)</span></span>  <br/> |<span data-ttu-id="30149-177">无相关性</span><span class="sxs-lookup"><span data-stu-id="30149-177">No affinity</span></span>  <br/> |<span data-ttu-id="30149-178">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="30149-178">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="30149-179">Lync Web App （仅外部用户）</span><span class="sxs-lookup"><span data-stu-id="30149-179">Lync Web App (external users only)</span></span>  <br/> <span data-ttu-id="30149-180">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="30149-180">Mobile device (internal and external users)</span></span>  <br/> |<span data-ttu-id="30149-181">无相关性</span><span class="sxs-lookup"><span data-stu-id="30149-181">No affinity</span></span>  <br/> |<span data-ttu-id="30149-182">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="30149-182">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="30149-183">Lync Web App （仅内部用户）</span><span class="sxs-lookup"><span data-stu-id="30149-183">Lync Web App (internal users only)</span></span>  <br/> <span data-ttu-id="30149-184">移动设备（未部署）</span><span class="sxs-lookup"><span data-stu-id="30149-184">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="30149-185">无相关性</span><span class="sxs-lookup"><span data-stu-id="30149-185">No affinity</span></span>  <br/> |<span data-ttu-id="30149-186">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="30149-186">Source address affinity</span></span>  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="30149-187">硬件负载平衡器的端口监控</span><span class="sxs-lookup"><span data-stu-id="30149-187">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="30149-188">在硬件负载平衡器上定义端口监控来确定特定服务何时由于硬件或通信故障而不再可用。</span><span class="sxs-lookup"><span data-stu-id="30149-188">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="30149-189">例如，如果前端服务器服务 (RTCSRV) 停止因为前端服务器或前端池失败，HLB 监控还应该停止接收通信，在 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="30149-189">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="30149-190">可在 HLB 上实施端口监控来监控以下各项：</span><span class="sxs-lookup"><span data-stu-id="30149-190">You implement port monitoring on the HLB to monitor the following:</span></span>
  
<span data-ttu-id="30149-191">**前端服务器用户池 HLB 内部接口**</span><span class="sxs-lookup"><span data-stu-id="30149-191">**Front End Server User Pool - HLB Internal Interface**</span></span>

|<span data-ttu-id="30149-192">**虚拟 IP/端口**</span><span class="sxs-lookup"><span data-stu-id="30149-192">**Virtual IP/Port**</span></span>|<span data-ttu-id="30149-193">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="30149-193">**Node Port**</span></span>|<span data-ttu-id="30149-194">**节点计算机/监视器**</span><span class="sxs-lookup"><span data-stu-id="30149-194">**Node Machine/Monitor**</span></span>|<span data-ttu-id="30149-195">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="30149-195">**Persistence Profile**</span></span>|<span data-ttu-id="30149-196">**注释**</span><span class="sxs-lookup"><span data-stu-id="30149-196">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="30149-197">\<池\>web int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="30149-197">\<pool\>web-int_mco_443_vs</span></span>  <br/> <span data-ttu-id="30149-198">443</span><span class="sxs-lookup"><span data-stu-id="30149-198">443</span></span>  <br/> |<span data-ttu-id="30149-199">443</span><span class="sxs-lookup"><span data-stu-id="30149-199">443</span></span>  <br/> |<span data-ttu-id="30149-200">前端</span><span class="sxs-lookup"><span data-stu-id="30149-200">Front End</span></span>  <br/> <span data-ttu-id="30149-201">5061</span><span class="sxs-lookup"><span data-stu-id="30149-201">5061</span></span>  <br/> |<span data-ttu-id="30149-202">源</span><span class="sxs-lookup"><span data-stu-id="30149-202">Source</span></span>  <br/> |<span data-ttu-id="30149-203">HTTPS</span><span class="sxs-lookup"><span data-stu-id="30149-203">HTTPS</span></span>  <br/> |
|<span data-ttu-id="30149-204">\<池\>web int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="30149-204">\<pool\>web-int_mco_80_vs</span></span>  <br/> <span data-ttu-id="30149-205">80</span><span class="sxs-lookup"><span data-stu-id="30149-205">80</span></span>  <br/> |<span data-ttu-id="30149-206">80</span><span class="sxs-lookup"><span data-stu-id="30149-206">80</span></span>  <br/> |<span data-ttu-id="30149-207">前端</span><span class="sxs-lookup"><span data-stu-id="30149-207">Front End</span></span>  <br/> <span data-ttu-id="30149-208">5061</span><span class="sxs-lookup"><span data-stu-id="30149-208">5061</span></span>  <br/> |<span data-ttu-id="30149-209">源</span><span class="sxs-lookup"><span data-stu-id="30149-209">Source</span></span>  <br/> |<span data-ttu-id="30149-210">HTTP</span><span class="sxs-lookup"><span data-stu-id="30149-210">HTTP</span></span>  <br/> |
   
<span data-ttu-id="30149-211">**前端服务器用户池 HLB 外部接口**</span><span class="sxs-lookup"><span data-stu-id="30149-211">**Front End Server User Pool - HLB External Interface**</span></span>

|<span data-ttu-id="30149-212">**虚拟 IP/端口**</span><span class="sxs-lookup"><span data-stu-id="30149-212">**Virtual IP/Port**</span></span>|<span data-ttu-id="30149-213">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="30149-213">**Node Port**</span></span>|<span data-ttu-id="30149-214">**节点计算机/监视器**</span><span class="sxs-lookup"><span data-stu-id="30149-214">**Node Machine/Monitor**</span></span>|<span data-ttu-id="30149-215">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="30149-215">**Persistence Profile**</span></span>|<span data-ttu-id="30149-216">**注释**</span><span class="sxs-lookup"><span data-stu-id="30149-216">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="30149-217">\<池\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="30149-217">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="30149-218">443</span><span class="sxs-lookup"><span data-stu-id="30149-218">443</span></span>  <br/> |<span data-ttu-id="30149-219">端口 4443</span><span class="sxs-lookup"><span data-stu-id="30149-219">4443</span></span>  <br/> |<span data-ttu-id="30149-220">前端</span><span class="sxs-lookup"><span data-stu-id="30149-220">Front End</span></span>  <br/> <span data-ttu-id="30149-221">5061</span><span class="sxs-lookup"><span data-stu-id="30149-221">5061</span></span>  <br/> |<span data-ttu-id="30149-222">无</span><span class="sxs-lookup"><span data-stu-id="30149-222">None</span></span>  <br/> |<span data-ttu-id="30149-223">HTTPS</span><span class="sxs-lookup"><span data-stu-id="30149-223">HTTPS</span></span>  <br/> |
|<span data-ttu-id="30149-224">\<池\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="30149-224">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="30149-225">80</span><span class="sxs-lookup"><span data-stu-id="30149-225">80</span></span>  <br/> |<span data-ttu-id="30149-226">8080</span><span class="sxs-lookup"><span data-stu-id="30149-226">8080</span></span>  <br/> |<span data-ttu-id="30149-227">前端</span><span class="sxs-lookup"><span data-stu-id="30149-227">Front End</span></span>  <br/> <span data-ttu-id="30149-228">5061</span><span class="sxs-lookup"><span data-stu-id="30149-228">5061</span></span>  <br/> |<span data-ttu-id="30149-229">无</span><span class="sxs-lookup"><span data-stu-id="30149-229">None</span></span>  <br/> |<span data-ttu-id="30149-230">HTTP</span><span class="sxs-lookup"><span data-stu-id="30149-230">HTTP</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="30149-231">DNS Load Balancing</span><span class="sxs-lookup"><span data-stu-id="30149-231">DNS Load Balancing</span></span>
<span data-ttu-id="30149-232"><a name="BKMK_DNSLoadBalancing"> </a></span><span class="sxs-lookup"><span data-stu-id="30149-232"></span></span>

<span data-ttu-id="30149-233">Skype 业务服务器启用 DNS 负载平衡，可以大幅降低负载平衡在您的网络管理开销的软件解决方案。</span><span class="sxs-lookup"><span data-stu-id="30149-233">Skype for Business Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="30149-234">DNS 负载平衡平衡是唯一的 Skype 的企业服务器，例如 SIP 流量和媒体流量的网络流量。</span><span class="sxs-lookup"><span data-stu-id="30149-234">DNS load balancing balances the network traffic that is unique to Skype for Business Server, such as SIP traffic and media traffic.</span></span>
  
<span data-ttu-id="30149-235">如果您部署 DNS 负载平衡，就可以最贵组织的管理开销的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="30149-235">If you deploy DNS load balancing, your organization's administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="30149-236">此外，将消除复杂故障排除与错误配置的 SIP 流量的负载平衡器的相关的问题。</span><span class="sxs-lookup"><span data-stu-id="30149-236">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="30149-237">以便您可以使服务器脱机，您还可以阻止服务器连接。</span><span class="sxs-lookup"><span data-stu-id="30149-237">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="30149-238">DNS 负载平衡还可以确保硬件负载平衡器问题不会影响如基本呼叫路由的 SIP 通信的元素。</span><span class="sxs-lookup"><span data-stu-id="30149-238">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="30149-239">下图显示了示例同时包含内部和外部 DNS 负载平衡：</span><span class="sxs-lookup"><span data-stu-id="30149-239">The following diagram shows an example that includes both internal and external DNS load balancing:</span></span> 
  
<span data-ttu-id="30149-240">**使用公共 IPv4 地址边缘网络图**</span><span class="sxs-lookup"><span data-stu-id="30149-240">**Edge network diagram using Public IPv4 addresses**</span></span>

![DNS 网络图表示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
<span data-ttu-id="30149-242">如果您使用 DNS 负载平衡，您可能还能够购买比所有类型的通信使用硬件负载平衡器的成本较低的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="30149-242">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="30149-243">您应使用过去 Business Server 测试与 Skype 的互操作性认证的负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="30149-243">You should use load balancers that have passed interoperability qualification testing with Skype for Business Server.</span></span> <span data-ttu-id="30149-244">有关负载平衡器的互操作性测试的详细信息，请参阅[Lync Server 2010 负载平衡器合作伙伴](https://go.microsoft.com/fwlink/p/?linkId=202452)。</span><span class="sxs-lookup"><span data-stu-id="30149-244">For details about load balancer interoperability testing, see [Lync Server 2010 Load Balancer Partners](https://go.microsoft.com/fwlink/p/?linkId=202452).</span></span> <span data-ttu-id="30149-245">为业务 Server 适用于 Skype 中存在的内容。</span><span class="sxs-lookup"><span data-stu-id="30149-245">The content there applies to Skype for Business Server.</span></span>
  
<span data-ttu-id="30149-246">前端池、 边缘服务器池、 控制器池和独立的中介服务器池的情况下，都支持 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-246">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>
  
<span data-ttu-id="30149-247">通常在应用程序级别实现 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-247">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="30149-248">应用程序 （例如，客户端运行 for Business 的 Skype），尝试连接到一个从返回的 IP 地址连接到池中的服务器的 DNS A 和 AAAA （如果使用 IPv6 寻址） 记录查询池完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="30149-248">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span> 
  
<span data-ttu-id="30149-249">例如，如果名为 pool01.contoso.com 的池中有三台前端服务器，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="30149-249">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>
  
- <span data-ttu-id="30149-250">运行 for Business 的 Skype 的客户端 DNS 查询 pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="30149-250">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="30149-251">查询将返回三个 IP 地址，并将其缓存，如下所示 （不一定是按此顺序）：</span><span class="sxs-lookup"><span data-stu-id="30149-251">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="30149-252">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="30149-252">pool01.contoso.com 192.168.10.90</span></span>
    
    <span data-ttu-id="30149-253">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="30149-253">pool01.contoso.com 192.168.10.91</span></span>
    
    <span data-ttu-id="30149-254">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="30149-254">pool01.contoso.com 192.168.10.92</span></span>
    
- <span data-ttu-id="30149-255">客户端尝试建立与一个 IP 地址的传输控制协议 (TCP) 连接。</span><span class="sxs-lookup"><span data-stu-id="30149-255">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="30149-256">如果失败，客户端尝试了缓存中的下一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="30149-256">If that fails, the client tries the next IP address in the cache.</span></span>
    
- <span data-ttu-id="30149-257">如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。</span><span class="sxs-lookup"><span data-stu-id="30149-257">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="30149-258">如果客户端尝试了所有缓存的条目不成功连接的情况下，则通知用户当前没有服务器运行 Business Server Skype 此时都已可用。</span><span class="sxs-lookup"><span data-stu-id="30149-258">If the client tries all cached entries without a successful connection, the user is notified that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="30149-259">基于 DNS 负载平衡是不同于 DNS 轮循机制 (DNS RR) 这通常是指负载平衡依靠 DNS 提供不同的顺序的 IP 地址对应于在池中的服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-259">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="30149-260">通常 DNS RR 仅启用负载分布，但不启用故障转移。</span><span class="sxs-lookup"><span data-stu-id="30149-260">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="30149-261">例如，如果为一个 IP 地址连接返回的 DNS A 和 AAAA （如果您使用的 IPv6 寻址） 查询失败，连接将失败。</span><span class="sxs-lookup"><span data-stu-id="30149-261">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="30149-262">因此，DNS 轮循机制本身是比基于 DNS 负载平衡不可靠。</span><span class="sxs-lookup"><span data-stu-id="30149-262">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="30149-263">您可以使用 DNS 轮循机制结合 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-263">You can use DNS round robin in conjunction with DNS load balancing.</span></span> 
  
<span data-ttu-id="30149-264">以下情况下使用 DNS 负载平衡：</span><span class="sxs-lookup"><span data-stu-id="30149-264">DNS load balancing is used for the following:</span></span>
  
- <span data-ttu-id="30149-265">负载平衡边缘服务器的服务器到服务器 SIP</span><span class="sxs-lookup"><span data-stu-id="30149-265">Load balancing server-to-server SIP to the Edge Servers</span></span>
    
- <span data-ttu-id="30149-266">负载平衡统一通信应用程序服务 (UCAS) 应用程序，如会议自动助理、 响应组和呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="30149-266">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>
    
- <span data-ttu-id="30149-267">阻止到 UCAS 应用程序 （也称为"排出"） 的新连接</span><span class="sxs-lookup"><span data-stu-id="30149-267">Preventing new connections to UCAS applications (also known as "draining")</span></span>
    
- <span data-ttu-id="30149-268">客户端和边缘服务器之间的所有客户端到服务器流量进行负载平衡</span><span class="sxs-lookup"><span data-stu-id="30149-268">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>
    
<span data-ttu-id="30149-269">以下，不能使用 DNS 负载平衡：</span><span class="sxs-lookup"><span data-stu-id="30149-269">DNS load balancing cannot be used for the following:</span></span>
  
- <span data-ttu-id="30149-270">至控制器或前端服务器的客户端到服务器的 web 流量</span><span class="sxs-lookup"><span data-stu-id="30149-270">Client-to-server web traffic to Director or Front End Servers</span></span>
    
<span data-ttu-id="30149-271">DNS 负载平衡和联盟流量：</span><span class="sxs-lookup"><span data-stu-id="30149-271">DNS load balancing and federated traffic:</span></span>
  
<span data-ttu-id="30149-272">如果 DNS SRV 查询返回多个 DNS 记录，则在访问边缘服务将始终选择 DNS SRV 记录使用的数字优先级最低和最大数字权重。</span><span class="sxs-lookup"><span data-stu-id="30149-272">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="30149-273">Internet 工程任务组文档"以指定的服务 (DNS SRV) 位置 DNS RR" [RFC 2782、 DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt)指定是否有多个 DNS SRV 记录定义，首先使用优先级、 然后重量。</span><span class="sxs-lookup"><span data-stu-id="30149-273">The Internet Engineering Task Force document "A DNS RR for specifying the location of services (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="30149-274">例如 DNS SRV 记录 A 具有 20 个权重和 40 和 DNS SRV 记录 B 的优先级具有的权重为 10 和优先级为 50。</span><span class="sxs-lookup"><span data-stu-id="30149-274">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="30149-275">DNS SRV 记录的优先级 40 将被选中。</span><span class="sxs-lookup"><span data-stu-id="30149-275">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="30149-276">以下规则适用于 DNS SRV 记录所选内容：</span><span class="sxs-lookup"><span data-stu-id="30149-276">The following rules apply to DNS SRV record selection:</span></span>
  
- <span data-ttu-id="30149-277">首先考虑优先级。</span><span class="sxs-lookup"><span data-stu-id="30149-277">Priority is considered first.</span></span> <span data-ttu-id="30149-278">客户端必须尝试联系目标主机定义通过它可以到达最低的编号优先级的 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="30149-278">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="30149-279">具有相同优先级的目标应尝试定义权重字段顺序。</span><span class="sxs-lookup"><span data-stu-id="30149-279">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>
    
- <span data-ttu-id="30149-280">权重字段指定具有相同优先级的相对权重，条目。</span><span class="sxs-lookup"><span data-stu-id="30149-280">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="30149-281">较大的权重，应注意的选择的按比例较高的概率。</span><span class="sxs-lookup"><span data-stu-id="30149-281">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="30149-282">没有选择任何服务器进行时，DNS 管理员应使用权重 0。</span><span class="sxs-lookup"><span data-stu-id="30149-282">DNS administrators SHOULD use Weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="30149-283">包含权重大于 0 的记录，如果存在与权重 0 的记录应有选择非常小机会。</span><span class="sxs-lookup"><span data-stu-id="30149-283">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>
    
<span data-ttu-id="30149-284">如果返回了优先级和权重的多个 DNS SRV 记录，访问边缘服务将选择首先从 DNS 服务器收到的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="30149-284">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="30149-285">DNS 负载平衡的前端池和控制器池</span><span class="sxs-lookup"><span data-stu-id="30149-285">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="30149-286">您可以使用 DNS 负载平衡的前端池和控制器池的 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="30149-286">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools.</span></span> <span data-ttu-id="30149-287">使用 DNS 负载平衡部署，您仍需要为这些池，但仅限于客户端到服务器的 HTTPS 通信也使用硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="30149-287">With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic.</span></span> <span data-ttu-id="30149-288">硬件负载平衡器是通过端口 443 和 80 用于来自客户端的 HTTPS 通信。</span><span class="sxs-lookup"><span data-stu-id="30149-288">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> 
  
<span data-ttu-id="30149-289">尽管这些池中仍需要硬件负载平衡器，其安装和管理将主要用于硬件负载平衡器管理员熟悉的 HTTPS 通信。</span><span class="sxs-lookup"><span data-stu-id="30149-289">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="30149-290">DNS 负载平衡和支持旧客户端和服务器</span><span class="sxs-lookup"><span data-stu-id="30149-290">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="30149-291">DNS 负载平衡支持自动故障转移只有业务客户端运行 Skype 业务服务器或 Lync Server 2010 和 Lync 2013 和 Skype 的服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-291">DNS load balancing supports automatic failover only for servers running Skype for Business Server or Lync Server 2010, and for Lync 2013 and Skype for Business clients.</span></span> <span data-ttu-id="30149-292">客户端和 Office Communications Server 的早期版本仍然可以连接到池运行 DNS 负载平衡，但如果不能进行连接到第一台服务器的 DNS 负载平衡引用给，他们不能故障转移到池中的另一台服务器.</span><span class="sxs-lookup"><span data-stu-id="30149-292">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span> 
  
<span data-ttu-id="30149-293">此外，如果您使用 Exchange UM，您必须使用 Exchange 2010 SP1 的最少的 Skype 支持获得业务服务器 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-293">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Skype for Business Server DNS load balancing.</span></span> <span data-ttu-id="30149-294">如果使用早期版本的 Exchange，用户不会这些 Exchange UM 方案的故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="30149-294">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>
  
- <span data-ttu-id="30149-295">其电话上播放他们企业的语音邮件</span><span class="sxs-lookup"><span data-stu-id="30149-295">Playing their Enterprise voicemail on their phone</span></span>
    
- <span data-ttu-id="30149-296">从 Exchange UM 自动助理转接呼叫</span><span class="sxs-lookup"><span data-stu-id="30149-296">Transferring calls from an Exchange UM Auto Attendant</span></span>
    
<span data-ttu-id="30149-297">所有其他 Exchange UM 方案将正常工作。</span><span class="sxs-lookup"><span data-stu-id="30149-297">All other Exchange UM scenarios will work properly.</span></span>
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="30149-298">部署 DNS 负载平衡前端池和控制器池</span><span class="sxs-lookup"><span data-stu-id="30149-298">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>
<span data-ttu-id="30149-299"><a name="BK_FE_Dir"> </a></span><span class="sxs-lookup"><span data-stu-id="30149-299"></span></span>

<span data-ttu-id="30149-300">正在部署 DNS 负载平衡的前端池和控制器池要求您执行一些处理 Fqdn 和 DNS 记录的额外步骤。</span><span class="sxs-lookup"><span data-stu-id="30149-300">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>
  
- <span data-ttu-id="30149-301">使用 DNS 负载平衡池必须具有两个 Fqdn： 正则池 FQDN 由 DNS 负载平衡 （如 pool01.contoso.com)，和解析为池中的服务器的物理 Ip 和 FQDN 另一个池的 Web 服务 （如web01.contoso.com)，它解析为池的虚拟 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="30149-301">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool's Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span> 
    
    <span data-ttu-id="30149-302">在拓扑生成器中，如果您想要部署 DNS 负载平衡池，要创建此额外的池的 Web 服务 FQDN 必须选择**覆盖内部 Web 服务池 FQDN**复选框并键入 FQDN，在**指定 Web 服务 Url此池**页。</span><span class="sxs-lookup"><span data-stu-id="30149-302">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool's Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>
    
- <span data-ttu-id="30149-303">若要支持使用 DNS 负载平衡的 FQDN，必须设置 DNS （如 pool01.contoso.com) 将池 FQDN 解析为池中的所有服务器的 IP 地址 （例如，192.168.1.1、 192.168.1.2，等等）。</span><span class="sxs-lookup"><span data-stu-id="30149-303">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="30149-304">您应仅当前部署的服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="30149-304">You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="30149-305">如果您有多个前端池或前端服务器的外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="30149-305">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="30149-306">例如，如果您定义的外部 Web 服务的前端服务器的 FQDN 为**pool01.contoso.com**，不能使用**pool01.contoso.com** ，另一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-306">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="30149-307">如果还要部署控制器、 外部 Web 服务 FQDN 定义任何控制器或控制器池必须不同于任何其他控制器池以及任何前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-307">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="30149-308">如果决定覆盖内部 web 服务与自定义的 FQDN，每个 FQDN 必须是唯一的任何其他前端池、 控制器或控制器池。</span><span class="sxs-lookup"><span data-stu-id="30149-308">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
### <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="30149-309">DNS 负载平衡边缘服务器池</span><span class="sxs-lookup"><span data-stu-id="30149-309">DNS Load Balancing on Edge Server Pools</span></span>
<span data-ttu-id="30149-310"><a name="BK_Edge"> </a></span><span class="sxs-lookup"><span data-stu-id="30149-310"></span></span>

<span data-ttu-id="30149-311">您可以部署 DNS 负载平衡边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="30149-311">You can deploy DNS load balancing on Edge Server pools.</span></span> <span data-ttu-id="30149-312">否则，您必须了解一些注意事项。</span><span class="sxs-lookup"><span data-stu-id="30149-312">If you do, you must be aware of some considerations.</span></span>
  
<span data-ttu-id="30149-313">使用 DNS 负载平衡边缘服务器上将导致以下方案中丧失故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="30149-313">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>
  
- <span data-ttu-id="30149-314">与之前 Lync Server 2010 的业务服务器运行的 Skype 版本的组织建立联盟。</span><span class="sxs-lookup"><span data-stu-id="30149-314">Federation with organizations that are running versions of Skype for Business Server released prior to Lync Server 2010.</span></span>
    
- <span data-ttu-id="30149-315">与公共即时消息 (IM) 服务 AOL 和 yahoo ！，除了基于 XMPP 的提供程序和服务器，如 Google Talk 当前只支持 XMPP 伙伴的用户的即时消息交换。</span><span class="sxs-lookup"><span data-stu-id="30149-315">Instant message exchange with users of public instant messaging (IM) services AOL and Yahoo!, in addition to XMPP-based providers and servers, such as Google Talk, currently the only supported XMPP partner.</span></span>
    
<span data-ttu-id="30149-316">这些方案起作用，只要在池中的所有边缘服务器启动并正在运行，但如果一台边缘服务器不可用，向其发送这些方案任何请求将失败，而不是传送到另一台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-316">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>
  
 <span data-ttu-id="30149-317">如果您使用 Exchange UM，您必须使用 Exchange 2013 的最少的 Skype 支持获得业务服务器 DNS 负载平衡的边缘。</span><span class="sxs-lookup"><span data-stu-id="30149-317">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Skype for Business Server DNS load balancing on Edge.</span></span> <span data-ttu-id="30149-318">如果使用早期版本的 Exchange，远程用户不会这些 Exchange UM 方案的故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="30149-318">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>
  
- <span data-ttu-id="30149-319">其电话上播放他们企业的语音邮件</span><span class="sxs-lookup"><span data-stu-id="30149-319">Playing their Enterprise voicemail on their phone</span></span>
    
- <span data-ttu-id="30149-320">从 Exchange UM 自动助理转接呼叫</span><span class="sxs-lookup"><span data-stu-id="30149-320">Transferring calls from an Exchange UM Auto Attendant</span></span>
    
<span data-ttu-id="30149-321">所有其他 Exchange UM 方案将正常工作。</span><span class="sxs-lookup"><span data-stu-id="30149-321">All other Exchange UM scenarios will work properly.</span></span>
  
<span data-ttu-id="30149-322">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-322">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="30149-323">您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-323">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="30149-324">部署 DNS 负载平衡边缘服务器池中</span><span class="sxs-lookup"><span data-stu-id="30149-324">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="30149-325">若要部署 DNS 负载平衡边缘服务器池的外部接口上，您需要以下 DNS 条目：</span><span class="sxs-lookup"><span data-stu-id="30149-325">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>
  
- <span data-ttu-id="30149-326">对于访问边缘服务，您需要一个条目的池中每台服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-326">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="30149-327">每个条目必须解析为上一台边缘服务器池中的访问边缘服务的 IP 地址 (例如，sip.contoso.com) 的访问边缘服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="30149-327">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>
    
- <span data-ttu-id="30149-328">对于 Web 会议边缘服务，您需要一个条目的池中每台服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-328">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="30149-329">每个条目必须解析为上一台边缘服务器池中的 Web 会议边缘服务的 IP 地址 (例如，webconf.contoso.com) Web 会议边缘服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="30149-329">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>
    
- <span data-ttu-id="30149-330">对于音频/视频边缘服务，您需要一个条目的池中每台服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-330">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="30149-331">每个条目必须音频/视频边缘服务 (例如，av.contoso.com) 将 FQDN 解析为的 IP 地址的 A / V 边缘服务上一台边缘服务器池中。</span><span class="sxs-lookup"><span data-stu-id="30149-331">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>
    
<span data-ttu-id="30149-332">若要部署 DNS 负载平衡边缘服务器池的内部接口上，您必须添加一个 DNS A 记录，边缘服务器池的内部 FQDN 解析为池中的每台服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="30149-332">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="30149-333">使用 DNS 负载平衡中介服务器池</span><span class="sxs-lookup"><span data-stu-id="30149-333">Using DNS Load Balancing on Mediation Server Pools</span></span>
<span data-ttu-id="30149-334"><a name="BK_Mediation"> </a></span><span class="sxs-lookup"><span data-stu-id="30149-334"></span></span>

<span data-ttu-id="30149-335">您可以使用 DNS 负载平衡在独立的中介服务器池上。</span><span class="sxs-lookup"><span data-stu-id="30149-335">You can use DNS load balancing on stand-alone Mediation Server pools.</span></span> <span data-ttu-id="30149-336">所有的 SIP 和媒体流量平衡由 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-336">All SIP and media traffic is balanced by DNS load balancing.</span></span>
  
<span data-ttu-id="30149-337">若要部署 DNS 负载平衡中介服务器池，必须设置 DNS 以将池 FQDN (例如，mediationpool1.contoso.com) 解析为池中的所有服务器的 IP 地址 （例如，192.168.1.1、 192.168.1.2，等等）。</span><span class="sxs-lookup"><span data-stu-id="30149-337">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="30149-338">阻止到带有 DNS 负载平衡服务器的流量</span><span class="sxs-lookup"><span data-stu-id="30149-338">Blocking Traffic to a Server With DNS Load Balancing</span></span>
<span data-ttu-id="30149-339"><a name="BK_Mediation"> </a></span><span class="sxs-lookup"><span data-stu-id="30149-339"></span></span>

<span data-ttu-id="30149-p142">如果使用 DNS 负载平衡并且需要阻止至特定计算机的流量，则仅仅删除池 FQDN 中的 IP 地址条目是不够的。您还必须删除计算机的 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="30149-p142">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span> 
  
<span data-ttu-id="30149-342">请注意，对于服务器到服务器通信，业务服务器 Skype 使用可识别拓扑的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="30149-342">Note that for server-to-server traffic, Skype for Business Server uses topology-aware load balancing.</span></span> <span data-ttu-id="30149-343">服务器阅读要获取在拓扑中，服务器的 Fqdn 的中央管理存储中的已发布的拓扑，并自动将在服务器之间的流量分发。</span><span class="sxs-lookup"><span data-stu-id="30149-343">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="30149-344">若要阻止从接收服务器到服务器通信的服务器，必须从拓扑中删除服务器。</span><span class="sxs-lookup"><span data-stu-id="30149-344">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span> 
  

