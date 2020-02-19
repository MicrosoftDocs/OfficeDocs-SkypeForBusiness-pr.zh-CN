---
title: Lync Server 2013 硬件负载平衡器要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ad738824b2ccaa4daf7f67758a970c24cee6a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="58d4d-102">Lync Server 2013 的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="58d4d-102">Hardware load balancer requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58d4d-103">_**上次修改的主题：** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="58d4d-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="58d4d-104">Lync Server 2013 扩展的合并边缘拓扑经过优化，用于新部署的 DNS 负载平衡主要与使用 Lync Server 的其他组织联盟。</span><span class="sxs-lookup"><span data-stu-id="58d4d-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="58d4d-105">如果下列任何方案要求高可用性，则必须在边缘服务器池上对以下内容使用硬件负载平衡器：</span><span class="sxs-lookup"><span data-stu-id="58d4d-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="58d4d-106">与使用 Office 通信服务器 2007 R2 或 Office 通信服务器2007的组织进行联盟</span><span class="sxs-lookup"><span data-stu-id="58d4d-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="58d4d-107">Exchange 2010 之前使用 Exchange UM 的远程用户的 exchange UM （SP1）</span><span class="sxs-lookup"><span data-stu-id="58d4d-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="58d4d-108">与公共 IM 用户的连接</span><span class="sxs-lookup"><span data-stu-id="58d4d-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="58d4d-p102">不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="58d4d-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="58d4d-p103">如果使用硬件负载平衡器，则为内部网络连接部署的负载平衡器必须配置为仅对发往运行访问边缘服务和 A/V 边缘服务的服务器的流量进行负载平衡。它不能对发往内部 Web 会议边缘服务或内部 XMPP 代理服务的流量进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="58d4d-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="58d4d-113">Lync Server 2013 不支持直接服务器返回（DSR） NAT。</span><span class="sxs-lookup"><span data-stu-id="58d4d-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="58d4d-114">若要确定您的硬件负载平衡器是否支持 Lync Server 2013 所需的必要功能，请参阅 at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452)中的 "Lync Server 2010 负载平衡器合作伙伴"。</span><span class="sxs-lookup"><span data-stu-id="58d4d-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="58d4d-115">运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="58d4d-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="58d4d-116">以下是运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求：</span><span class="sxs-lookup"><span data-stu-id="58d4d-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="58d4d-p104">对内部和外部端口 443 关闭 TCP nagling。Nagling 是将若干小数据包整合到单个大数据包以提高传输效率的过程。</span><span class="sxs-lookup"><span data-stu-id="58d4d-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="58d4d-119">对端口范围为 50,000 – 59,999 的外部端口关闭 TCP nagling。</span><span class="sxs-lookup"><span data-stu-id="58d4d-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="58d4d-120">请不要对内部或外部防火墙使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="58d4d-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="58d4d-121">边缘内部接口与边缘服务器外部接口必须位于不同的网络上，且必须禁用它们之间的路由。</span><span class="sxs-lookup"><span data-stu-id="58d4d-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="58d4d-122">运行 A/V 边缘服务的边缘服务器的外部接口必须使用可公开路由的 IP 地址，并且没有任何边缘外部 IP 地址上的 NAT 或端口转换。</span><span class="sxs-lookup"><span data-stu-id="58d4d-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="58d4d-123">硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="58d4d-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="58d4d-124">Lync Server 2013 for Web 服务中的基于 Cookie 的相关性要求大大减少。</span><span class="sxs-lookup"><span data-stu-id="58d4d-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="58d4d-125">如果要部署 Lync Server 2013，并且不会保留任何 Lync Server 2010 前端服务器或前端池，则不需要基于 cookie 的持久性。</span><span class="sxs-lookup"><span data-stu-id="58d4d-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="58d4d-126">但是，如果您将临时或永久保留任何 Lync Server 2010 前端服务器或前端池，您仍将使用基于 cookie 的持久性，因为它是为 Lync Server 2010 部署和配置的。</span><span class="sxs-lookup"><span data-stu-id="58d4d-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58d4d-127"><STRONG>如果您决定使用基于 Cookie 的相关性，但您的部署不需要它</STRONG>，如此做没有任何负面影响。</span><span class="sxs-lookup"><span data-stu-id="58d4d-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="58d4d-128">对于**不使用**基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="58d4d-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="58d4d-129">在端口 4443 的反向代理发布规则上，将“转发主机头”\*\*\*\* 设置为 True。</span><span class="sxs-lookup"><span data-stu-id="58d4d-129">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="58d4d-130">这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="58d4d-130">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="58d4d-131">对于**将使用**基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="58d4d-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="58d4d-p107">在端口 4443 的反向代理发布规则上，将“转发主机头”\*\*\*\* 设置为 True。这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="58d4d-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="58d4d-134">不得将硬件负载平衡器 Cookie 标记为 httpOnly</span><span class="sxs-lookup"><span data-stu-id="58d4d-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="58d4d-135">硬件负载平衡器 Cookie 不得具有过期时间</span><span class="sxs-lookup"><span data-stu-id="58d4d-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="58d4d-136">硬件负载平衡器 Cookie 必须名为 **MS-WSMAN**（这是 Web 服务预期的值，不能更改）</span><span class="sxs-lookup"><span data-stu-id="58d4d-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="58d4d-p108">必须在其传入 HTTP 请求没有 Cookie 的每个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie 都是如此。如果负载平衡器将 Cookie 插入优化为每个 TCP 连接只发生一次，则不得使用该优化</span><span class="sxs-lookup"><span data-stu-id="58d4d-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58d4d-139">典型的硬件负载平衡器配置使用源地址关联和20分钟的 TCP 会话生存期，这对 Lync Server 和 Lync 2013 客户端来说是很好的，因为会话状态是通过客户端使用情况和/或应用程序交互来维护的。</span><span class="sxs-lookup"><span data-stu-id="58d4d-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="58d4d-140">如果部署移动设备，则您的硬件负载平衡器必须能对 TCP 会话中的单个请求进行负载平衡（实际上，您必须能基于目标 IP 地址对单个请求进行负载平衡）。</span><span class="sxs-lookup"><span data-stu-id="58d4d-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="58d4d-p109">F5 硬件负载平衡器具有一个名为 OneConnect 的功能，这可确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的硬件负载平衡器供应商支持这一相同功能。最新的 Apple iOS 移动应用程序要求传输层安全性 (TLS) 1.2 版。F5 提供专门针对这一要求的设置。</span><span class="sxs-lookup"><span data-stu-id="58d4d-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="58d4d-145">有关第三方硬件负载平衡器的详细信息，请参阅<A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="58d4d-145">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="58d4d-146">以下是控制器和前端池 Web 服务的硬件负载平衡器要求：</span><span class="sxs-lookup"><span data-stu-id="58d4d-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="58d4d-147">对于内部 Web 服务 Vip，请设置\_硬件负载平衡器上的源地址暂留（内部端口80，443）。</span><span class="sxs-lookup"><span data-stu-id="58d4d-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="58d4d-148">对于 Lync Server 2013，源\_地址暂留意味着来自单个 IP 地址的多个连接将始终发送到一台服务器，以维护会话状态。</span><span class="sxs-lookup"><span data-stu-id="58d4d-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="58d4d-149">使用 TCP 空闲超时 1800 秒。</span><span class="sxs-lookup"><span data-stu-id="58d4d-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="58d4d-p111">在反向代理和下一个跃点池的硬件负载平衡器之间的防火墙上，创建一条支持端口 4443 上从反向代理到硬件负载平衡器的 HTTPS 流量的规则。必须将硬件负载平衡器配置为侦听端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="58d4d-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="58d4d-152">有关硬件负载平衡器配置的进一步阅读，请<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">在 Lync Server 2013 中查看带硬件负载平衡器的端口摘要-扩展的合并边缘</A>。</span><span class="sxs-lookup"><span data-stu-id="58d4d-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="58d4d-153">硬件负载平衡器关联要求的摘要</span><span class="sxs-lookup"><span data-stu-id="58d4d-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58d4d-154">客户端/用户位置</span><span class="sxs-lookup"><span data-stu-id="58d4d-154">Client/user location</span></span></th>
<th><span data-ttu-id="58d4d-155">外部 Web 服务 FQDN 关联要求</span><span class="sxs-lookup"><span data-stu-id="58d4d-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="58d4d-156">内部 Web 服务 FQDN 关联要求</span><span class="sxs-lookup"><span data-stu-id="58d4d-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58d4d-157">Lync Web App （内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="58d4d-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="58d4d-158">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="58d4d-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="58d4d-159">无相关性</span><span class="sxs-lookup"><span data-stu-id="58d4d-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="58d4d-160">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="58d4d-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58d4d-161">Lync Web App （仅限外部用户）</span><span class="sxs-lookup"><span data-stu-id="58d4d-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="58d4d-162">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="58d4d-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="58d4d-163">无相关性</span><span class="sxs-lookup"><span data-stu-id="58d4d-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="58d4d-164">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="58d4d-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58d4d-165">Lync Web App （仅限内部用户）</span><span class="sxs-lookup"><span data-stu-id="58d4d-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="58d4d-166">移动设备（未部署）</span><span class="sxs-lookup"><span data-stu-id="58d4d-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="58d4d-167">无相关性</span><span class="sxs-lookup"><span data-stu-id="58d4d-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="58d4d-168">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="58d4d-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="58d4d-169">硬件负载平衡器的端口监控</span><span class="sxs-lookup"><span data-stu-id="58d4d-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="58d4d-170">在硬件负载平衡器上定义端口监控来确定特定服务何时由于硬件或通信故障而不再可用。</span><span class="sxs-lookup"><span data-stu-id="58d4d-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="58d4d-171">例如，如果前端服务器服务（RTCSRV）因前端服务器或前端池出现故障而停止，则 HLB 监视还应停止接收 Web 服务上的流量。</span><span class="sxs-lookup"><span data-stu-id="58d4d-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="58d4d-172">可在 HLB 上实施端口监控来监控以下各项：</span><span class="sxs-lookup"><span data-stu-id="58d4d-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="58d4d-173">前端服务器用户池– HLB 内部接口</span><span class="sxs-lookup"><span data-stu-id="58d4d-173">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58d4d-174">虚拟 IP/端口</span><span class="sxs-lookup"><span data-stu-id="58d4d-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="58d4d-175">节点端口</span><span class="sxs-lookup"><span data-stu-id="58d4d-175">Node Port</span></span></th>
<th><span data-ttu-id="58d4d-176">节点计算机/监视器</span><span class="sxs-lookup"><span data-stu-id="58d4d-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="58d4d-177">持久性配置文件</span><span class="sxs-lookup"><span data-stu-id="58d4d-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="58d4d-178">备注</span><span class="sxs-lookup"><span data-stu-id="58d4d-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58d4d-179">&lt;池&gt;web-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="58d4d-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="58d4d-180">443</span><span class="sxs-lookup"><span data-stu-id="58d4d-180">443</span></span></p></td>
<td><p><span data-ttu-id="58d4d-181">443</span><span class="sxs-lookup"><span data-stu-id="58d4d-181">443</span></span></p></td>
<td><p><span data-ttu-id="58d4d-182">前端</span><span class="sxs-lookup"><span data-stu-id="58d4d-182">Front End</span></span></p>
<p><span data-ttu-id="58d4d-183">5061</span><span class="sxs-lookup"><span data-stu-id="58d4d-183">5061</span></span></p></td>
<td><p><span data-ttu-id="58d4d-184">Source</span><span class="sxs-lookup"><span data-stu-id="58d4d-184">Source</span></span></p></td>
<td><p><span data-ttu-id="58d4d-185">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="58d4d-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58d4d-186">&lt;池&gt;web-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="58d4d-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="58d4d-187">80</span><span class="sxs-lookup"><span data-stu-id="58d4d-187">80</span></span></p></td>
<td><p><span data-ttu-id="58d4d-188">80</span><span class="sxs-lookup"><span data-stu-id="58d4d-188">80</span></span></p></td>
<td><p><span data-ttu-id="58d4d-189">前端</span><span class="sxs-lookup"><span data-stu-id="58d4d-189">Front End</span></span></p>
<p><span data-ttu-id="58d4d-190">5061</span><span class="sxs-lookup"><span data-stu-id="58d4d-190">5061</span></span></p></td>
<td><p><span data-ttu-id="58d4d-191">Source</span><span class="sxs-lookup"><span data-stu-id="58d4d-191">Source</span></span></p></td>
<td><p><span data-ttu-id="58d4d-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="58d4d-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="58d4d-193">前端服务器用户池– HLB 外部接口</span><span class="sxs-lookup"><span data-stu-id="58d4d-193">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58d4d-194">虚拟 IP/端口</span><span class="sxs-lookup"><span data-stu-id="58d4d-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="58d4d-195">节点端口</span><span class="sxs-lookup"><span data-stu-id="58d4d-195">Node Port</span></span></th>
<th><span data-ttu-id="58d4d-196">节点计算机/监视器</span><span class="sxs-lookup"><span data-stu-id="58d4d-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="58d4d-197">持久性配置文件</span><span class="sxs-lookup"><span data-stu-id="58d4d-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="58d4d-198">备注</span><span class="sxs-lookup"><span data-stu-id="58d4d-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58d4d-199">&lt;池&gt;web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="58d4d-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="58d4d-200">443</span><span class="sxs-lookup"><span data-stu-id="58d4d-200">443</span></span></p></td>
<td><p><span data-ttu-id="58d4d-201">4443</span><span class="sxs-lookup"><span data-stu-id="58d4d-201">4443</span></span></p></td>
<td><p><span data-ttu-id="58d4d-202">前端</span><span class="sxs-lookup"><span data-stu-id="58d4d-202">Front End</span></span></p>
<p><span data-ttu-id="58d4d-203">5061</span><span class="sxs-lookup"><span data-stu-id="58d4d-203">5061</span></span></p></td>
<td><p><span data-ttu-id="58d4d-204">无</span><span class="sxs-lookup"><span data-stu-id="58d4d-204">None</span></span></p></td>
<td><p><span data-ttu-id="58d4d-205">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="58d4d-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58d4d-206">&lt;池&gt;web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="58d4d-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="58d4d-207">80</span><span class="sxs-lookup"><span data-stu-id="58d4d-207">80</span></span></p></td>
<td><p><span data-ttu-id="58d4d-208">8080</span><span class="sxs-lookup"><span data-stu-id="58d4d-208">8080</span></span></p></td>
<td><p><span data-ttu-id="58d4d-209">前端</span><span class="sxs-lookup"><span data-stu-id="58d4d-209">Front End</span></span></p>
<p><span data-ttu-id="58d4d-210">5061</span><span class="sxs-lookup"><span data-stu-id="58d4d-210">5061</span></span></p></td>
<td><p><span data-ttu-id="58d4d-211">无</span><span class="sxs-lookup"><span data-stu-id="58d4d-211">None</span></span></p></td>
<td><p><span data-ttu-id="58d4d-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="58d4d-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

