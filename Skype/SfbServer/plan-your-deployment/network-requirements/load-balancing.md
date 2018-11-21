---
title: Skype for Business 的负载平衡要求
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
ms.openlocfilehash: 9c0153d9b366731a85070c42ed11ea1a061ee409
ms.sourcegitcommit: ff0c4bef4d4cbc71d51fce941aff63739a0016e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2018
ms.locfileid: "26626189"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a><span data-ttu-id="46c56-103">Skype for Business 的负载平衡要求</span><span class="sxs-lookup"><span data-stu-id="46c56-103">Load balancing requirements for Skype for Business</span></span>
 
<span data-ttu-id="46c56-104">**摘要：** 查看的负载平衡的企业服务器实现 Skype 之前的注意事项。</span><span class="sxs-lookup"><span data-stu-id="46c56-104">**Summary:** Review the load balancing considerations before implementing Skype for Business Server.</span></span>
  
<span data-ttu-id="46c56-105">负载平衡分布在池中的服务器之间的流量。</span><span class="sxs-lookup"><span data-stu-id="46c56-105">Load balancing distributes traffic among the servers in a pool.</span></span> <span data-ttu-id="46c56-106">如果您有前端池、 中介服务器池或边缘服务器池，需要部署负载平衡的这些池。</span><span class="sxs-lookup"><span data-stu-id="46c56-106">If you have Front End pools, Mediation Server pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span>
  
<span data-ttu-id="46c56-107">Skype 业务服务器支持的负载平衡的客户端到服务器的通信解决方案的两种类型： 域名系统 (DNS) 负载平衡和硬件负载平衡通常 （缩写为 HLB）。</span><span class="sxs-lookup"><span data-stu-id="46c56-107">Skype for Business Server supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing (often abbreviated as HLB).</span></span> <span data-ttu-id="46c56-108">DNS 负载平衡提供几个优点包括简化管理、 更高效疑难解答、 和隔离何种业务服务器流量从任何潜在的硬件负载平衡器问题您 Skype 的能力。</span><span class="sxs-lookup"><span data-stu-id="46c56-108">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Skype for Business Server traffic from any potential hardware load balancer problems.</span></span>
  
<span data-ttu-id="46c56-109">决定为您自己的负载平衡解决方案适合在您部署中，每个池，但请记住以下限制：</span><span class="sxs-lookup"><span data-stu-id="46c56-109">Decide for yourself which load balancing solution is appropriate for each pool in your deployment, but keep in mind the following restrictions:</span></span> 
  
- <span data-ttu-id="46c56-p103">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能在一个接口上使用 DNS 负载平衡的同时，在另一个接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>
    
- <span data-ttu-id="46c56-p104">某些类型的流量需要硬件负载平衡器。例如，HTTP 流量需要硬件平衡负载器而非 DNS 负载平衡。DNS 负载平衡对客户端到服务器的 Web 流量不起作用。</span><span class="sxs-lookup"><span data-stu-id="46c56-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>
    
<span data-ttu-id="46c56-p105">如果选择对某个池使用 DNS 负载平衡，但仍需对流量（如 HTTP 流量）实现硬件负载平衡器，则会大大简化硬件负载平衡器的管理。例如，配置硬件负载平衡器将更简单，因为它仅管理 HTTP 和 HTTPS 流量，而所有其他协议将由 DNS 负载平衡管理。有关详细信息，请参阅 [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing)。</span><span class="sxs-lookup"><span data-stu-id="46c56-p105">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified. For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing. For details, see [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing).</span></span> 
  
<span data-ttu-id="46c56-118">对于服务器到服务器通信，Skype 业务服务器使用拓扑感知负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-118">For server-to-server traffic, Skype for Business Server uses topology-aware load balancing.</span></span> <span data-ttu-id="46c56-119">服务器阅读要获取在拓扑中，服务器的 Fqdn 的中央管理存储中的已发布的拓扑，并自动将在服务器之间的流量分发。</span><span class="sxs-lookup"><span data-stu-id="46c56-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="46c56-120">管理员不必设置或管理此类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-120">Administrators do not need to set up or manage this type of load balancing.</span></span> 
  
<span data-ttu-id="46c56-p107">如果使用 DNS 负载平衡并且需要阻止至特定计算机的流量，则仅仅删除池 FQDN 中的 IP 地址条目是不够的。您还必须删除计算机的 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="46c56-p107">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span> 
  
## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="46c56-123">硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="46c56-123">Hardware load balancer requirements</span></span>

<span data-ttu-id="46c56-124">扩展的业务服务器 Skype 的合并的边缘拓扑进行了优化的主要与其他组织使用 Skype 业务服务器或 Lync Server 联盟的新部署的 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-124">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Skype for Business Server or Lync Server.</span></span> <span data-ttu-id="46c56-125">如果任何以下方案需要高可用性，硬件负载平衡器必须使用边缘服务器池上的以下：</span><span class="sxs-lookup"><span data-stu-id="46c56-125">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span> 
  
- <span data-ttu-id="46c56-126">与使用 Office Communications Server 2007 R2 或 Office Communications Server 2007 的组织建立联盟</span><span class="sxs-lookup"><span data-stu-id="46c56-126">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>
    
- <span data-ttu-id="46c56-127">Exchange UM sp1 之前 Exchange 2010 UM Exchange 使用的远程用户</span><span class="sxs-lookup"><span data-stu-id="46c56-127">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>
    
- <span data-ttu-id="46c56-128">与公共 IM 用户的连接</span><span class="sxs-lookup"><span data-stu-id="46c56-128">Connectivity to public IM users</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="46c56-p109">不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-p109">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="46c56-p110">如果使用硬件负载平衡器，则为内部网络连接部署的负载平衡器必须配置为仅对发往运行访问边缘服务和 A/V 边缘服务的服务器的流量进行负载平衡。它不能对发往内部 Web 会议边缘服务或内部 XMPP 代理服务的流量进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-p110">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="46c56-133">直接服务器返回 (DSR) NAT 不支持与 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="46c56-133">The direct server return (DSR) NAT is not supported with Skype for Business Server.</span></span> 
  
<span data-ttu-id="46c56-134">若要确定您的硬件负载平衡器是否支持所需的 Skype 业务服务器所需的功能，请参阅[for Business 的 Skype 的基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="46c56-134">To determine whether your hardware load balancer supports the necessary features required by Skype for Business Server, see [Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="46c56-135">运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="46c56-135">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="46c56-136">下面是运行 A 的边缘服务器的硬件负载平衡器要求 / V 边缘服务：</span><span class="sxs-lookup"><span data-stu-id="46c56-136">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>
  
- <span data-ttu-id="46c56-p111">对内部和外部端口 443 关闭 TCP nagling。Nagling 是将若干小数据包整合到单个大数据包以提高传输效率的过程。</span><span class="sxs-lookup"><span data-stu-id="46c56-p111">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>
    
- <span data-ttu-id="46c56-139">关闭外部端口范围 50000-59999 TCP nagling。</span><span class="sxs-lookup"><span data-stu-id="46c56-139">Turn off TCP nagling for external port range 50,000 - 59,999.</span></span> 
    
- <span data-ttu-id="46c56-140">请不要对内部或外部防火墙使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="46c56-140">Do not use NAT on the internal or external firewall.</span></span> 
    
- <span data-ttu-id="46c56-141">边缘内部接口必须位于不同网络边缘服务器外部接口上，且必须禁用它们之间的路由。</span><span class="sxs-lookup"><span data-stu-id="46c56-141">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span> 
    
- <span data-ttu-id="46c56-142">外部接口的边缘服务器运行 A / V 边缘服务必须使用公共可路由 IP 地址和 NAT 或端口上的任何边缘外部 IP 地址的转换。</span><span class="sxs-lookup"><span data-stu-id="46c56-142">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span> 
    
- <span data-ttu-id="46c56-143">负载平衡器不得更改客户端的源地址。</span><span class="sxs-lookup"><span data-stu-id="46c56-143">The load balancer must not change the source address of the client.</span></span>
    
### <a name="other-hardware-load-balancer-requirements"></a><span data-ttu-id="46c56-144">其他硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="46c56-144">Other Hardware Load Balancer requirements</span></span>

<span data-ttu-id="46c56-145">基于 cookie 的相关性要求将会显著降低中 Skype 业务服务器 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="46c56-145">Cookie-based affinity requirements are greatly reduced in Skype for Business Server for Web services.</span></span> <span data-ttu-id="46c56-146">如果您部署 Skype 业务服务器，并将不会保留的所有 Lync Server 2010 前端服务器或前端池，则不需要基于 cookie 的持久性。</span><span class="sxs-lookup"><span data-stu-id="46c56-146">If you are deploying Skype for Business Server and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="46c56-147">但是，如果将临时或永久保留的所有 Lync Server 2010 前端服务器或前端池，您仍使用基于 cookie 的持久性，它为部署和 Lync Server 2010 的配置。</span><span class="sxs-lookup"><span data-stu-id="46c56-147">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="46c56-148">**如果您决定使用基于 Cookie 的相关性，但您的部署不需要它**，如此做没有任何负面影响。</span><span class="sxs-lookup"><span data-stu-id="46c56-148">**If you decide to use cookie-based affinity even though your deployment does not require it**, there is no negative impact to doing so.</span></span> 
  
<span data-ttu-id="46c56-149">对于 **不使用**基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="46c56-149">For deployments that **will not use** cookie-based affinity:</span></span>
  
- <span data-ttu-id="46c56-p113">在端口 4443 的反向代理发布规则上，将“**转发主机头**”设置为 True。这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="46c56-p113">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>
    
<span data-ttu-id="46c56-152">对于**将使用**基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="46c56-152">For deployments that **will use** cookie-based affinity:</span></span>
  
- <span data-ttu-id="46c56-p114">在端口 4443 的反向代理发布规则上，将“**转发主机头**”设置为 True。这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="46c56-p114">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>
    
- <span data-ttu-id="46c56-155">不得将硬件负载平衡器 Cookie 标记为 httpOnly</span><span class="sxs-lookup"><span data-stu-id="46c56-155">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>
    
- <span data-ttu-id="46c56-156">硬件负载平衡器 Cookie 不得具有过期时间</span><span class="sxs-lookup"><span data-stu-id="46c56-156">Hardware load balancer cookie MUST NOT have an expiration time</span></span>
    
- <span data-ttu-id="46c56-157">硬件负载平衡器 Cookie 必须名为 **MS-WSMAN**（这是 Web 服务预期的值，不能更改）</span><span class="sxs-lookup"><span data-stu-id="46c56-157">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>
    
- <span data-ttu-id="46c56-p115">必须在其传入 HTTP 请求没有 Cookie 的每个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie 都是如此。如果负载平衡器将 Cookie 插入优化为每个 TCP 连接只发生一次，则不得使用该优化</span><span class="sxs-lookup"><span data-stu-id="46c56-p115">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>
    
> [!NOTE]
> <span data-ttu-id="46c56-160">典型的硬件负载平衡器配置使用源地址相关性和 20 分钟 TCP 会话生存期，因为会话状态维护通过客户端使用这对于 Lync Server 和 Lync 2013 客户端和/或和应用程序交互。</span><span class="sxs-lookup"><span data-stu-id="46c56-160">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span> 
  
<span data-ttu-id="46c56-161">如果部署移动设备，则您的硬件负载平衡器必须能对 TCP 会话中的单个请求进行负载平衡（实际上，您必须能基于目标 IP 地址对单个请求进行负载平衡）。</span><span class="sxs-lookup"><span data-stu-id="46c56-161">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="46c56-p116">F5 硬件负载平衡器具有一个名为 OneConnect 的功能，这可确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的硬件负载平衡器供应商支持这一相同功能。最新的 Apple iOS 移动应用程序要求传输层安全性 (TLS) 1.2 版。F5 提供专门针对这一要求的设置。</span><span class="sxs-lookup"><span data-stu-id="46c56-p116">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="46c56-166">有关第三方硬件负载平衡器的详细信息，请参阅 [Skype for Business 的基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="46c56-166">For details on third party hardware load balancers, see [Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span>  
  
<span data-ttu-id="46c56-167">以下是控制器和前端池 Web 服务的硬件负载平衡器要求：</span><span class="sxs-lookup"><span data-stu-id="46c56-167">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>
  
- <span data-ttu-id="46c56-168">对于内部 Web 服务 VIP，在硬件负载平衡器上设置 Source_addr 持久性（内部端口 80 和 443）。</span><span class="sxs-lookup"><span data-stu-id="46c56-168">For internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="46c56-169">对于业务服务器 Skype，Source_addr 持久性意味着，来自单个 IP 地址的多个连接始终发送到一台服务器来维护会话状态。</span><span class="sxs-lookup"><span data-stu-id="46c56-169">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>
    
- <span data-ttu-id="46c56-170">使用 TCP 空闲超时 1800 秒。</span><span class="sxs-lookup"><span data-stu-id="46c56-170">Use TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="46c56-171">在反向代理和下一个跃点池的硬件负载平衡器之间防火墙中，创建一个规则来允许 https： 通信端口 4443 上，从反向代理的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="46c56-171">On the firewall between the reverse proxy and the next hop pool's hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer.</span></span> <span data-ttu-id="46c56-172">必须将硬件负载平衡器配置为侦听端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="46c56-172">The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="46c56-173">硬件负载平衡器关联要求的摘要</span><span class="sxs-lookup"><span data-stu-id="46c56-173">Summary of Hardware Load Balancer Affinity Requirements</span></span>

|<span data-ttu-id="46c56-174">**客户端/用户位置**</span><span class="sxs-lookup"><span data-stu-id="46c56-174">**Client/user location**</span></span>|<span data-ttu-id="46c56-175">**外部 Web 服务 FQDN 关联要求**</span><span class="sxs-lookup"><span data-stu-id="46c56-175">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="46c56-176">**内部 Web 服务 FQDN 关联要求**</span><span class="sxs-lookup"><span data-stu-id="46c56-176">**Internal web services FQDN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46c56-177">Lync Web App （内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="46c56-177">Lync Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="46c56-178">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="46c56-178">Mobile device (internal and external users)</span></span>  <br/> |<span data-ttu-id="46c56-179">无相关性</span><span class="sxs-lookup"><span data-stu-id="46c56-179">No affinity</span></span>  <br/> |<span data-ttu-id="46c56-180">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="46c56-180">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="46c56-181">Lync Web App （仅外部用户）</span><span class="sxs-lookup"><span data-stu-id="46c56-181">Lync Web App (external users only)</span></span>  <br/> <span data-ttu-id="46c56-182">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="46c56-182">Mobile device (internal and external users)</span></span>  <br/> |<span data-ttu-id="46c56-183">无相关性</span><span class="sxs-lookup"><span data-stu-id="46c56-183">No affinity</span></span>  <br/> |<span data-ttu-id="46c56-184">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="46c56-184">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="46c56-185">Lync Web App （仅内部用户）</span><span class="sxs-lookup"><span data-stu-id="46c56-185">Lync Web App (internal users only)</span></span>  <br/> <span data-ttu-id="46c56-186">移动设备（未部署）</span><span class="sxs-lookup"><span data-stu-id="46c56-186">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="46c56-187">无相关性</span><span class="sxs-lookup"><span data-stu-id="46c56-187">No affinity</span></span>  <br/> |<span data-ttu-id="46c56-188">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="46c56-188">Source address affinity</span></span>  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="46c56-189">硬件负载平衡器的端口监控</span><span class="sxs-lookup"><span data-stu-id="46c56-189">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="46c56-190">在硬件负载平衡器上定义端口监控来确定特定服务何时由于硬件或通信故障而不再可用。</span><span class="sxs-lookup"><span data-stu-id="46c56-190">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="46c56-191">例如，如果前端服务器服务 (RTCSRV) 停止因为前端服务器或前端池失败，HLB 监控还应该停止接收通信，在 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="46c56-191">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="46c56-192">可在 HLB 上实施端口监控来监控以下各项：</span><span class="sxs-lookup"><span data-stu-id="46c56-192">You implement port monitoring on the HLB to monitor the following:</span></span>
  
<span data-ttu-id="46c56-193">**前端服务器用户池 HLB 内部接口**</span><span class="sxs-lookup"><span data-stu-id="46c56-193">**Front End Server User Pool - HLB Internal Interface**</span></span>

|<span data-ttu-id="46c56-194">**虚拟 IP/端口**</span><span class="sxs-lookup"><span data-stu-id="46c56-194">**Virtual IP/Port**</span></span>|<span data-ttu-id="46c56-195">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="46c56-195">**Node Port**</span></span>|<span data-ttu-id="46c56-196">**节点计算机/监视器**</span><span class="sxs-lookup"><span data-stu-id="46c56-196">**Node Machine/Monitor**</span></span>|<span data-ttu-id="46c56-197">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="46c56-197">**Persistence Profile**</span></span>|<span data-ttu-id="46c56-198">**说明**</span><span class="sxs-lookup"><span data-stu-id="46c56-198">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46c56-199">\<池\>web int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="46c56-199">\<pool\>web-int_mco_443_vs</span></span>  <br/> <span data-ttu-id="46c56-200">443</span><span class="sxs-lookup"><span data-stu-id="46c56-200">443</span></span>  <br/> |<span data-ttu-id="46c56-201">443</span><span class="sxs-lookup"><span data-stu-id="46c56-201">443</span></span>  <br/> |<span data-ttu-id="46c56-202">前端</span><span class="sxs-lookup"><span data-stu-id="46c56-202">Front End</span></span>  <br/> <span data-ttu-id="46c56-203">5061</span><span class="sxs-lookup"><span data-stu-id="46c56-203">5061</span></span>  <br/> |<span data-ttu-id="46c56-204">源</span><span class="sxs-lookup"><span data-stu-id="46c56-204">Source</span></span>  <br/> |<span data-ttu-id="46c56-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="46c56-205">HTTPS</span></span>  <br/> |
|<span data-ttu-id="46c56-206">\<池\>web int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="46c56-206">\<pool\>web-int_mco_80_vs</span></span>  <br/> <span data-ttu-id="46c56-207">80</span><span class="sxs-lookup"><span data-stu-id="46c56-207">80</span></span>  <br/> |<span data-ttu-id="46c56-208">80</span><span class="sxs-lookup"><span data-stu-id="46c56-208">80</span></span>  <br/> |<span data-ttu-id="46c56-209">前端</span><span class="sxs-lookup"><span data-stu-id="46c56-209">Front End</span></span>  <br/> <span data-ttu-id="46c56-210">5061</span><span class="sxs-lookup"><span data-stu-id="46c56-210">5061</span></span>  <br/> |<span data-ttu-id="46c56-211">源</span><span class="sxs-lookup"><span data-stu-id="46c56-211">Source</span></span>  <br/> |<span data-ttu-id="46c56-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="46c56-212">HTTP</span></span>  <br/> |
   
<span data-ttu-id="46c56-213">**前端服务器用户池 HLB 外部接口**</span><span class="sxs-lookup"><span data-stu-id="46c56-213">**Front End Server User Pool - HLB External Interface**</span></span>

|<span data-ttu-id="46c56-214">**虚拟 IP/端口**</span><span class="sxs-lookup"><span data-stu-id="46c56-214">**Virtual IP/Port**</span></span>|<span data-ttu-id="46c56-215">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="46c56-215">**Node Port**</span></span>|<span data-ttu-id="46c56-216">**节点计算机/监视器**</span><span class="sxs-lookup"><span data-stu-id="46c56-216">**Node Machine/Monitor**</span></span>|<span data-ttu-id="46c56-217">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="46c56-217">**Persistence Profile**</span></span>|<span data-ttu-id="46c56-218">**说明**</span><span class="sxs-lookup"><span data-stu-id="46c56-218">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46c56-219">\<池\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="46c56-219">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="46c56-220">443</span><span class="sxs-lookup"><span data-stu-id="46c56-220">443</span></span>  <br/> |<span data-ttu-id="46c56-221">端口 4443</span><span class="sxs-lookup"><span data-stu-id="46c56-221">4443</span></span>  <br/> |<span data-ttu-id="46c56-222">前端</span><span class="sxs-lookup"><span data-stu-id="46c56-222">Front End</span></span>  <br/> <span data-ttu-id="46c56-223">5061</span><span class="sxs-lookup"><span data-stu-id="46c56-223">5061</span></span>  <br/> |<span data-ttu-id="46c56-224">无</span><span class="sxs-lookup"><span data-stu-id="46c56-224">None</span></span>  <br/> |<span data-ttu-id="46c56-225">HTTPS</span><span class="sxs-lookup"><span data-stu-id="46c56-225">HTTPS</span></span>  <br/> |
|<span data-ttu-id="46c56-226">\<池\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="46c56-226">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="46c56-227">80</span><span class="sxs-lookup"><span data-stu-id="46c56-227">80</span></span>  <br/> |<span data-ttu-id="46c56-228">8080</span><span class="sxs-lookup"><span data-stu-id="46c56-228">8080</span></span>  <br/> |<span data-ttu-id="46c56-229">前端</span><span class="sxs-lookup"><span data-stu-id="46c56-229">Front End</span></span>  <br/> <span data-ttu-id="46c56-230">5061</span><span class="sxs-lookup"><span data-stu-id="46c56-230">5061</span></span>  <br/> |<span data-ttu-id="46c56-231">无</span><span class="sxs-lookup"><span data-stu-id="46c56-231">None</span></span>  <br/> |<span data-ttu-id="46c56-232">HTTP</span><span class="sxs-lookup"><span data-stu-id="46c56-232">HTTP</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="46c56-233">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-233">DNS Load Balancing</span></span>
<span data-ttu-id="46c56-234"><a name="BKMK_DNSLoadBalancing"> </a></span><span class="sxs-lookup"><span data-stu-id="46c56-234"></span></span>

<span data-ttu-id="46c56-235">Skype 业务服务器启用 DNS 负载平衡，可以大幅降低负载平衡在您的网络管理开销的软件解决方案。</span><span class="sxs-lookup"><span data-stu-id="46c56-235">Skype for Business Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="46c56-236">DNS 负载平衡平衡是唯一的 Skype 的企业服务器，例如 SIP 流量和媒体流量的网络流量。</span><span class="sxs-lookup"><span data-stu-id="46c56-236">DNS load balancing balances the network traffic that is unique to Skype for Business Server, such as SIP traffic and media traffic.</span></span>
  
<span data-ttu-id="46c56-237">如果您部署 DNS 负载平衡，就可以最贵组织的管理开销的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="46c56-237">If you deploy DNS load balancing, your organization's administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="46c56-238">此外，还可以免除解决 SIP 流量负载平衡器配置错误相关问题的复杂过程。</span><span class="sxs-lookup"><span data-stu-id="46c56-238">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="46c56-239">您还可以阻止服务器连接以使服务器脱机。</span><span class="sxs-lookup"><span data-stu-id="46c56-239">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="46c56-240">同时，DNS 负载平衡还可确保硬件负载平衡器问题不会影响 SIP 流量的元素，例如基本呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="46c56-240">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="46c56-241">下图显示了示例同时包含内部和外部 DNS 负载平衡：</span><span class="sxs-lookup"><span data-stu-id="46c56-241">The following diagram shows an example that includes both internal and external DNS load balancing:</span></span> 
  
<span data-ttu-id="46c56-242">**使用公共 IPv4 地址边缘网络图**</span><span class="sxs-lookup"><span data-stu-id="46c56-242">**Edge network diagram using Public IPv4 addresses**</span></span>

![DNS 网络图表示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
<span data-ttu-id="46c56-244">与为所有类型的流量使用硬件负载平衡器相比，使用 DNS 负载平衡还可以降低您购买硬件负载平衡器的成本。</span><span class="sxs-lookup"><span data-stu-id="46c56-244">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="46c56-245">您应使用过去 Business Server 测试与 Skype 的互操作性认证的负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="46c56-245">You should use load balancers that have passed interoperability qualification testing with Skype for Business Server.</span></span> <span data-ttu-id="46c56-246">有关负载平衡器的互操作性测试的详细信息，请参阅[Lync Server 2010 负载平衡器合作伙伴](https://go.microsoft.com/fwlink/p/?linkId=202452)。</span><span class="sxs-lookup"><span data-stu-id="46c56-246">For details about load balancer interoperability testing, see [Lync Server 2010 Load Balancer Partners](https://go.microsoft.com/fwlink/p/?linkId=202452).</span></span> <span data-ttu-id="46c56-247">为业务 Server 适用于 Skype 中存在的内容。</span><span class="sxs-lookup"><span data-stu-id="46c56-247">The content there applies to Skype for Business Server.</span></span>
  
<span data-ttu-id="46c56-248">前端池、边缘服务器池、控制器池和独立的中介服务器池都支持 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-248">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>
  
<span data-ttu-id="46c56-249">通常在应用程序级别实现 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-249">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="46c56-250">应用程序 （例如，客户端运行 for Business 的 Skype），尝试连接到一个从返回的 IP 地址连接到池中的服务器的 DNS A 和 AAAA （如果使用 IPv6 寻址） 记录查询池完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="46c56-250">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span> 
  
<span data-ttu-id="46c56-251">例如，如果名为 pool01.contoso.com 的池中有三台前端服务器，则会发生以下情形：</span><span class="sxs-lookup"><span data-stu-id="46c56-251">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>
  
- <span data-ttu-id="46c56-252">运行 for Business 的 Skype 的客户端 DNS 查询 pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="46c56-252">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="46c56-253">此查询将返回三个 IP 地址并将其按如下方式进行缓存（不需要按此顺序）：</span><span class="sxs-lookup"><span data-stu-id="46c56-253">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="46c56-254">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="46c56-254">pool01.contoso.com 192.168.10.90</span></span>
    
    <span data-ttu-id="46c56-255">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="46c56-255">pool01.contoso.com 192.168.10.91</span></span>
    
    <span data-ttu-id="46c56-256">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="46c56-256">pool01.contoso.com 192.168.10.92</span></span>
    
- <span data-ttu-id="46c56-p125">客户端将尝试建立到其中一个 IP 地址的传输控制协议 (TCP) 连接。如果失败，则客户端会尝试缓存中的下一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="46c56-p125">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses. If that fails, the client tries the next IP address in the cache.</span></span>
    
- <span data-ttu-id="46c56-259">如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。</span><span class="sxs-lookup"><span data-stu-id="46c56-259">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="46c56-260">如果客户端尝试了所有缓存的条目不成功连接的情况下，则通知用户当前没有服务器运行 Business Server Skype 此时都已可用。</span><span class="sxs-lookup"><span data-stu-id="46c56-260">If the client tries all cached entries without a successful connection, the user is notified that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="46c56-p126">基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR)，后者通常是指依靠 DNS 提供与池中服务器对应的不同顺序的 IP 地址来进行负载平衡。通常 DNS RR 只启用负载分配，而不启用故障转移。例如，如果到由 DNS A 和 AAAA（如果使用的是 IPv6 寻址）查询返回的一个 IP 地址的连接失败，则连接失败。因此，DNS 循环自身的可靠性低于基于 DNS 的负载平衡。您可以将 DNS 循环与 DNS 负载平衡结合使用。</span><span class="sxs-lookup"><span data-stu-id="46c56-p126">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool. Typically DNS RR only enables load distribution, but does not enable failover. For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails. Therefore, DNS round robin by itself is less reliable than DNS-based load balancing. You can use DNS round robin in conjunction with DNS load balancing.</span></span> 
  
<span data-ttu-id="46c56-266">DNS 负载平衡用于以下方面：</span><span class="sxs-lookup"><span data-stu-id="46c56-266">DNS load balancing is used for the following:</span></span>
  
- <span data-ttu-id="46c56-267">对至边缘服务器的服务器到服务器 SIP 进行负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-267">Load balancing server-to-server SIP to the Edge Servers</span></span>
    
- <span data-ttu-id="46c56-268">对统一通信应用程序服务 (UCAS) 应用程序（如会议自动助理、响应组和呼叫寄存）进行负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-268">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>
    
- <span data-ttu-id="46c56-269">阻止到 UCAS 应用程序的新连接（也称为“排出”）</span><span class="sxs-lookup"><span data-stu-id="46c56-269">Preventing new connections to UCAS applications (also known as "draining")</span></span>
    
- <span data-ttu-id="46c56-270">对客户端和边缘服务器之间的所有客户端到服务器的流量进行负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-270">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>
    
<span data-ttu-id="46c56-271">DNS 负载平衡不能用于以下方面：</span><span class="sxs-lookup"><span data-stu-id="46c56-271">DNS load balancing cannot be used for the following:</span></span>
  
- <span data-ttu-id="46c56-272">客户端到服务器至控制器或前端服务器的 Web 流量</span><span class="sxs-lookup"><span data-stu-id="46c56-272">Client-to-server web traffic to Director or Front End Servers</span></span>
    
<span data-ttu-id="46c56-273">DNS 负载平衡和联盟流量：</span><span class="sxs-lookup"><span data-stu-id="46c56-273">DNS load balancing and federated traffic:</span></span>
  
<span data-ttu-id="46c56-274">如果一个 DNS SRV 查询返回了多个 DNS 记录，则访问边缘服务始终以最低数值优先级与最高数值权重拾取 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="46c56-274">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="46c56-275">Internet 工程任务组文档"以指定的服务 (DNS SRV) 位置 DNS RR" [RFC 2782、 DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt)指定是否有多个 DNS SRV 记录定义，首先使用优先级、 然后重量。</span><span class="sxs-lookup"><span data-stu-id="46c56-275">The Internet Engineering Task Force document "A DNS RR for specifying the location of services (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="46c56-276">例如 DNS SRV 记录 A 权重为 20，优先级为 40，而 DNS SRV 记录 B 权重为 10，优先级为 50。</span><span class="sxs-lookup"><span data-stu-id="46c56-276">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="46c56-277">优先级为 40 的 DNS SRV 记录 A 将被选中。</span><span class="sxs-lookup"><span data-stu-id="46c56-277">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="46c56-278">下列规则适用于 DNS SRV 记录选择：</span><span class="sxs-lookup"><span data-stu-id="46c56-278">The following rules apply to DNS SRV record selection:</span></span>
  
- <span data-ttu-id="46c56-p128">首先考虑优先级。客户端必须尝试联系它可访问的由具有最低编号优先级的 DNS SRV 记录定义的目标主机。应按权重字段定义的顺序尝试具有相同优先级的目标。</span><span class="sxs-lookup"><span data-stu-id="46c56-p128">Priority is considered first. A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach. Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>
    
- <span data-ttu-id="46c56-282">权重字段指定具有相同优先级的条目的相对权重。</span><span class="sxs-lookup"><span data-stu-id="46c56-282">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="46c56-283">权重越大，应赋予的被选中可能性相应越高。</span><span class="sxs-lookup"><span data-stu-id="46c56-283">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="46c56-284">没有选择任何服务器进行时，DNS 管理员应使用权重 0。</span><span class="sxs-lookup"><span data-stu-id="46c56-284">DNS administrators SHOULD use Weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="46c56-285">相对于包含大于 0 的权重的记录，权重为 0 的记录应具有非常小的被选中机会。</span><span class="sxs-lookup"><span data-stu-id="46c56-285">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>
    
<span data-ttu-id="46c56-286">如果返回了优先级和权重都相同的多个 DNS SRV 记录，则访问边缘服务将选择首先从 DNS 服务器收到的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="46c56-286">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="46c56-287">前端池和控制器池中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-287">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="46c56-p130">您可以使用 DNS 负载平衡来平衡前端池和控制器池中的 SIP 流量。部署 DNS 负载平衡后，仍需要对这些池使用硬件负载平衡器，但仅用于客户端到服务器的 HTTPS 流量。硬件负载平衡器用于通过端口 443 和 80 从客户端传入的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="46c56-p130">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> 
  
<span data-ttu-id="46c56-291">尽管这些池中仍需要硬件负载平衡器，但这些负载平衡器的安装和管理主要用于硬件负载平衡器管理员熟悉的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="46c56-291">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="46c56-292">支持旧客户端和服务器并对其进行 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-292">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="46c56-293">DNS 负载平衡支持自动故障转移只有业务客户端运行 Skype 业务服务器或 Lync Server 2010 和 Lync 2013 和 Skype 的服务器。</span><span class="sxs-lookup"><span data-stu-id="46c56-293">DNS load balancing supports automatic failover only for servers running Skype for Business Server or Lync Server 2010, and for Lync 2013 and Skype for Business clients.</span></span> <span data-ttu-id="46c56-294">客户端和 Office Communications Server 的早期版本仍然可以连接到池运行 DNS 负载平衡，但如果不能进行连接到第一台服务器的 DNS 负载平衡引用给，他们不能故障转移到池中的另一台服务器.</span><span class="sxs-lookup"><span data-stu-id="46c56-294">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span> 
  
<span data-ttu-id="46c56-295">此外，如果您使用 Exchange UM，您必须使用 Exchange 2010 SP1 的最少的 Skype 支持获得业务服务器 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-295">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Skype for Business Server DNS load balancing.</span></span> <span data-ttu-id="46c56-296">如果使用较早版本的 Exchange，则在以下 Exchange UM 方案中无法为您的用户提供故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="46c56-296">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>
  
- <span data-ttu-id="46c56-297">在其电话上播放企业语音邮件</span><span class="sxs-lookup"><span data-stu-id="46c56-297">Playing their Enterprise voicemail on their phone</span></span>
    
- <span data-ttu-id="46c56-298">转接来自 Exchange UM 自动助理的呼叫</span><span class="sxs-lookup"><span data-stu-id="46c56-298">Transferring calls from an Exchange UM Auto Attendant</span></span>
    
<span data-ttu-id="46c56-299">其他所有 Exchange UM 方案将正常工作。</span><span class="sxs-lookup"><span data-stu-id="46c56-299">All other Exchange UM scenarios will work properly.</span></span>
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="46c56-300">在前端池和控制器池中部署 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-300">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>
<span data-ttu-id="46c56-301"><a name="BK_FE_Dir"> </a></span><span class="sxs-lookup"><span data-stu-id="46c56-301"></span></span>

<span data-ttu-id="46c56-302">在前端池和控制器池中部署 DNS 负载平衡时，需要使用 FQDN 和 DNS 记录执行一些额外步骤。</span><span class="sxs-lookup"><span data-stu-id="46c56-302">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>
  
- <span data-ttu-id="46c56-303">使用 DNS 负载平衡池必须具有两个 Fqdn： 正则池 FQDN 由 DNS 负载平衡 （如 pool01.contoso.com)，和解析为池中的服务器的物理 Ip 和 FQDN 另一个池的 Web 服务 （如web01.contoso.com)，它解析为池的虚拟 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="46c56-303">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool's Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span> 
    
    <span data-ttu-id="46c56-304">在拓扑生成器中，如果您想要部署 DNS 负载平衡池，要创建此额外的池的 Web 服务 FQDN 必须选择**覆盖内部 Web 服务池 FQDN**复选框并键入 FQDN，在**指定 Web 服务 Url此池**页。</span><span class="sxs-lookup"><span data-stu-id="46c56-304">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool's Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>
    
- <span data-ttu-id="46c56-p133">要支持 DNS 负载平衡使用的 FQDN，必须设置 DNS，以便将池 FQDN（例如 pool01.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。您应该仅包含当前部署的服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="46c56-p133">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="46c56-307">如果您有多个前端池或前端服务器的外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="46c56-307">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="46c56-308">例如，如果您定义的外部 Web 服务的前端服务器的 FQDN 为**pool01.contoso.com**，不能使用**pool01.contoso.com** ，另一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="46c56-308">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="46c56-309">如果还要部署控制器、 外部 Web 服务 FQDN 定义任何控制器或控制器池必须不同于任何其他控制器池以及任何前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="46c56-309">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="46c56-310">如果决定覆盖内部 web 服务与自定义的 FQDN，每个 FQDN 必须是唯一的任何其他前端池、 控制器或控制器池。</span><span class="sxs-lookup"><span data-stu-id="46c56-310">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
### <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="46c56-311">边缘服务器池中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-311">DNS Load Balancing on Edge Server Pools</span></span>
<span data-ttu-id="46c56-312"><a name="BK_Edge"> </a></span><span class="sxs-lookup"><span data-stu-id="46c56-312"></span></span>

<span data-ttu-id="46c56-p135">您可以在边缘服务器池中部署 DNS 负载平衡。如果要进行部署，则必须了解以下注意事项。</span><span class="sxs-lookup"><span data-stu-id="46c56-p135">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>
  
<span data-ttu-id="46c56-315">在边缘服务器中使用 DNS 负载平衡会导致以下方案中丧失故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="46c56-315">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>
  
- <span data-ttu-id="46c56-316">与之前 Lync Server 2010 的业务服务器运行的 Skype 版本的组织建立联盟。</span><span class="sxs-lookup"><span data-stu-id="46c56-316">Federation with organizations that are running versions of Skype for Business Server released prior to Lync Server 2010.</span></span>
    
- <span data-ttu-id="46c56-317">与公共即时消息 (IM) 服务 AOL 和 yahoo ！，除了基于 XMPP 的提供程序和服务器，如 Google Talk 当前只支持 XMPP 伙伴的用户的即时消息交换。</span><span class="sxs-lookup"><span data-stu-id="46c56-317">Instant message exchange with users of public instant messaging (IM) services AOL and Yahoo!, in addition to XMPP-based providers and servers, such as Google Talk, currently the only supported XMPP partner.</span></span>
    
<span data-ttu-id="46c56-318">只要池中的所有边缘服务器都在运行，这些方案就会正常工作；但是如果某台边缘服务器不可用，则发送到该服务器的对这些方案的所有请求都将失败，而不会路由到其他边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="46c56-318">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>
  
 <span data-ttu-id="46c56-319">如果您使用 Exchange UM，您必须使用 Exchange 2013 的最少的 Skype 支持获得业务服务器 DNS 负载平衡的边缘。</span><span class="sxs-lookup"><span data-stu-id="46c56-319">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Skype for Business Server DNS load balancing on Edge.</span></span> <span data-ttu-id="46c56-320">如果使用较早版本的 Exchange，则在以下 Exchange UM 方案中无法为您的远程用户提供故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="46c56-320">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>
  
- <span data-ttu-id="46c56-321">在其电话上播放企业语音邮件</span><span class="sxs-lookup"><span data-stu-id="46c56-321">Playing their Enterprise voicemail on their phone</span></span>
    
- <span data-ttu-id="46c56-322">转接来自 Exchange UM 自动助理的呼叫</span><span class="sxs-lookup"><span data-stu-id="46c56-322">Transferring calls from an Exchange UM Auto Attendant</span></span>
    
<span data-ttu-id="46c56-323">其他所有 Exchange UM 方案将正常工作。</span><span class="sxs-lookup"><span data-stu-id="46c56-323">All other Exchange UM scenarios will work properly.</span></span>
  
<span data-ttu-id="46c56-p137">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-p137">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="46c56-326">在边缘服务器池中部署 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-326">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="46c56-327">要在边缘服务器池的外部接口上部署 DNS 负载平衡，需要具有以下 DNS 条目：</span><span class="sxs-lookup"><span data-stu-id="46c56-327">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>
  
- <span data-ttu-id="46c56-p138">对于访问边缘服务，池中的每台服务器都需要有一个条目。每个条目必须将访问边缘服务的 FQDN（例如 sip.contoso.com）解析为该池中某台边缘服务器上访问边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="46c56-p138">For the Access Edge service, you need one entry for each server in the pool. Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>
    
- <span data-ttu-id="46c56-p139">对于 Web 会议边缘服务，池中的每台服务器都需要有一个条目。每个条目必须将 Web 会议边缘服务的 FQDN（例如 webconf.contoso.com）解析为该池中某台边缘服务器上 Web 会议边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="46c56-p139">For the Web Conferencing Edge service, you need one entry for each server in the pool. Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>
    
- <span data-ttu-id="46c56-332">对于音频/视频边缘服务，池中的每台服务器都需要有一个条目。</span><span class="sxs-lookup"><span data-stu-id="46c56-332">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="46c56-333">每个条目必须音频/视频边缘服务 (例如，av.contoso.com) 将 FQDN 解析为的 IP 地址的 A / V 边缘服务上一台边缘服务器池中。</span><span class="sxs-lookup"><span data-stu-id="46c56-333">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>
    
<span data-ttu-id="46c56-334">要在边缘服务器池的内部接口上部署 DNS 负载平衡，必须添加一条将此边缘服务器池的内部 FQDN 解析为该池中每台服务器的 IP 地址的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="46c56-334">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="46c56-335">在中介服务器池中使用 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="46c56-335">Using DNS Load Balancing on Mediation Server Pools</span></span>
<span data-ttu-id="46c56-336"><a name="BK_Mediation"> </a></span><span class="sxs-lookup"><span data-stu-id="46c56-336"></span></span>

<span data-ttu-id="46c56-p141">可以在独立的中介服务器池上使用 DNS 负载平衡。所有 SIP 和媒体流量都通过 DNS 负载平衡进行平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-p141">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>
  
<span data-ttu-id="46c56-339">要在中介服务器池中部署 DNS 负载平衡，必须设置 DNS，以便将池 FQDN（例如 mediationpool1.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。</span><span class="sxs-lookup"><span data-stu-id="46c56-339">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="46c56-340">使用 DNS 负载平衡阻止到服务器的流量</span><span class="sxs-lookup"><span data-stu-id="46c56-340">Blocking Traffic to a Server With DNS Load Balancing</span></span>
<span data-ttu-id="46c56-341"><a name="BK_Mediation"> </a></span><span class="sxs-lookup"><span data-stu-id="46c56-341"></span></span>

<span data-ttu-id="46c56-p142">如果使用 DNS 负载平衡并且需要阻止至特定计算机的流量，则仅仅删除池 FQDN 中的 IP 地址条目是不够的。您还必须删除计算机的 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="46c56-p142">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span> 
  
<span data-ttu-id="46c56-344">请注意，对于服务器到服务器通信，业务服务器 Skype 使用可识别拓扑的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="46c56-344">Note that for server-to-server traffic, Skype for Business Server uses topology-aware load balancing.</span></span> <span data-ttu-id="46c56-345">服务器阅读要获取在拓扑中，服务器的 Fqdn 的中央管理存储中的已发布的拓扑，并自动将在服务器之间的流量分发。</span><span class="sxs-lookup"><span data-stu-id="46c56-345">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="46c56-346">若要阻止服务器接收服务器到服务器的流量，则必须从拓扑中删除服务器。</span><span class="sxs-lookup"><span data-stu-id="46c56-346">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span> 
  

