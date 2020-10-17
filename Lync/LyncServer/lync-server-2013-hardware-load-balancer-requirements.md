---
title: Lync Server 2013 硬件负载平衡器要求
description: Lync Server 2013 硬件负载平衡器要求。
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
ms.openlocfilehash: 69cbf79c1fd7551dfd428c23ed22c924d0805c43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552918"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="e8d1c-103">Lync Server 2013 的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="e8d1c-103">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8d1c-104">_**上次修改的主题：** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="e8d1c-104">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="e8d1c-105">Lync Server 2013 扩展的合并边缘拓扑经过优化，用于新部署的 DNS 负载平衡主要与使用 Lync Server 的其他组织联盟。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-105">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="e8d1c-106">如果下列任何方案要求高可用性，则必须在边缘服务器池上对以下内容使用硬件负载平衡器：</span><span class="sxs-lookup"><span data-stu-id="e8d1c-106">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="e8d1c-107">与使用 Office 通信服务器 2007 R2 或 Office 通信服务器2007的组织进行联盟</span><span class="sxs-lookup"><span data-stu-id="e8d1c-107">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="e8d1c-108">Exchange 2010 之前使用 Exchange UM 的远程用户的 exchange UM （SP1）</span><span class="sxs-lookup"><span data-stu-id="e8d1c-108">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="e8d1c-109">与公共 IM 用户的连接</span><span class="sxs-lookup"><span data-stu-id="e8d1c-109">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e8d1c-p102">不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e8d1c-p103">如果使用硬件负载平衡器，则为内部网络连接部署的负载平衡器必须配置为仅对发往运行访问边缘服务和 A/V 边缘服务的服务器的流量进行负载平衡。它不能对发往内部 Web 会议边缘服务或内部 XMPP 代理服务的流量进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e8d1c-114">Lync Server 2013 不支持直接服务器返回 (DSR) NAT。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-114">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="e8d1c-115">若要确定您的硬件负载平衡器是否支持 Lync Server 2013 所需的必要功能，请参阅 at 中的 "Lync Server 2010 负载平衡器合作伙伴" [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) 。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-115">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="e8d1c-116">运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="e8d1c-116">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="e8d1c-117">以下是运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求：</span><span class="sxs-lookup"><span data-stu-id="e8d1c-117">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="e8d1c-p104">对内部和外部端口 443 关闭 TCP nagling。Nagling 是将若干小数据包整合到单个大数据包以提高传输效率的过程。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="e8d1c-120">对端口范围为 50,000 – 59,999 的外部端口关闭 TCP nagling。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-120">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="e8d1c-121">请不要对内部或外部防火墙使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-121">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="e8d1c-122">边缘内部接口与边缘服务器外部接口必须位于不同的网络上，且必须禁用它们之间的路由。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-122">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="e8d1c-123">运行 A/V 边缘服务的边缘服务器的外部接口必须使用可公开路由的 IP 地址，并且没有任何边缘外部 IP 地址上的 NAT 或端口转换。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-123">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="e8d1c-124">硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="e8d1c-124">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="e8d1c-125">Lync Server 2013 for Web 服务中的基于 Cookie 的相关性要求大大减少。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-125">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="e8d1c-126">如果要部署 Lync Server 2013，并且不会保留任何 Lync Server 2010 前端服务器或前端池，则不需要基于 cookie 的持久性。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-126">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="e8d1c-127">但是，如果您将临时或永久保留任何 Lync Server 2010 前端服务器或前端池，您仍将使用基于 cookie 的持久性，因为它是为 Lync Server 2010 部署和配置的。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-127">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8d1c-128"><STRONG>如果您决定使用基于 Cookie 的相关性，但您的部署不需要它</STRONG>，如此做没有任何负面影响。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-128"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="e8d1c-129">对于**不使用**基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="e8d1c-129">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="e8d1c-p106">在端口 4443 的反向代理发布规则上，将“转发主机头”\*\*\*\* 设置为 True。这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-p106">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="e8d1c-132">对于**将使用**基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="e8d1c-132">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="e8d1c-p107">在端口 4443 的反向代理发布规则上，将“转发主机头”\*\*\*\* 设置为 True。这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="e8d1c-135">不得将硬件负载平衡器 Cookie 标记为 httpOnly</span><span class="sxs-lookup"><span data-stu-id="e8d1c-135">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="e8d1c-136">硬件负载平衡器 Cookie 不得具有过期时间</span><span class="sxs-lookup"><span data-stu-id="e8d1c-136">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="e8d1c-137">硬件负载平衡器 Cookie 必须名为 **MS-WSMAN**（这是 Web 服务预期的值，不能更改）</span><span class="sxs-lookup"><span data-stu-id="e8d1c-137">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="e8d1c-p108">必须在其传入 HTTP 请求没有 Cookie 的每个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie 都是如此。如果负载平衡器将 Cookie 插入优化为每个 TCP 连接只发生一次，则不得使用该优化</span><span class="sxs-lookup"><span data-stu-id="e8d1c-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8d1c-140">典型的硬件负载平衡器配置使用源地址关联和20分钟的 TCP 会话生存期，这对 Lync Server 和 Lync 2013 客户端来说是很好的，因为会话状态是通过客户端使用情况和/或应用程序交互来维护的。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-140">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="e8d1c-141">如果部署移动设备，则您的硬件负载平衡器必须能对 TCP 会话中的单个请求进行负载平衡（实际上，您必须能基于目标 IP 地址对单个请求进行负载平衡）。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-141">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e8d1c-p109">F5 硬件负载平衡器具有一个名为 OneConnect 的功能，这可确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的硬件负载平衡器供应商支持这一相同功能。最新的 Apple iOS 移动应用程序要求传输层安全性 (TLS) 1.2 版。F5 提供专门针对这一要求的设置。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="e8d1c-146">有关第三方硬件负载平衡器的详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="e8d1c-146">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="e8d1c-147">以下是控制器和前端池 Web 服务的硬件负载平衡器要求：</span><span class="sxs-lookup"><span data-stu-id="e8d1c-147">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="e8d1c-148">对于内部 Web 服务 Vip，请设置 \_ 硬件负载平衡器上的源地址持久性 (内部端口80、443) 。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-148">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="e8d1c-149">对于 Lync Server 2013，源 \_ 地址暂留意味着来自单个 IP 地址的多个连接将始终发送到一台服务器，以维护会话状态。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-149">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="e8d1c-150">使用 TCP 空闲超时 1800 秒。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-150">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="e8d1c-p111">在反向代理和下一个跃点池的硬件负载平衡器之间的防火墙上，创建一条支持端口 4443 上从反向代理到硬件负载平衡器的 HTTPS 流量的规则。必须将硬件负载平衡器配置为侦听端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e8d1c-153">有关硬件负载平衡器配置的进一步阅读，请 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">在 Lync Server 2013 中查看带硬件负载平衡器的端口摘要-扩展的合并边缘</A>。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-153">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="e8d1c-154">硬件负载平衡器关联要求的摘要</span><span class="sxs-lookup"><span data-stu-id="e8d1c-154">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8d1c-155">客户端/用户位置</span><span class="sxs-lookup"><span data-stu-id="e8d1c-155">Client/user location</span></span></th>
<th><span data-ttu-id="e8d1c-156">外部 Web 服务 FQDN 关联要求</span><span class="sxs-lookup"><span data-stu-id="e8d1c-156">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="e8d1c-157">内部 Web 服务 FQDN 关联要求</span><span class="sxs-lookup"><span data-stu-id="e8d1c-157">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8d1c-158">Lync Web App (内部和外部用户) </span><span class="sxs-lookup"><span data-stu-id="e8d1c-158">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="e8d1c-159">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="e8d1c-159">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-160">无相关性</span><span class="sxs-lookup"><span data-stu-id="e8d1c-160">No affinity</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-161">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="e8d1c-161">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8d1c-162">仅 (外部用户) 的 Lync Web App</span><span class="sxs-lookup"><span data-stu-id="e8d1c-162">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="e8d1c-163">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="e8d1c-163">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-164">无相关性</span><span class="sxs-lookup"><span data-stu-id="e8d1c-164">No affinity</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-165">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="e8d1c-165">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8d1c-166">Lync Web App (仅限内部用户) </span><span class="sxs-lookup"><span data-stu-id="e8d1c-166">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="e8d1c-167">移动设备（未部署）</span><span class="sxs-lookup"><span data-stu-id="e8d1c-167">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-168">无相关性</span><span class="sxs-lookup"><span data-stu-id="e8d1c-168">No affinity</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-169">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="e8d1c-169">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="e8d1c-170">硬件负载平衡器的端口监控</span><span class="sxs-lookup"><span data-stu-id="e8d1c-170">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="e8d1c-171">在硬件负载平衡器上定义端口监控来确定特定服务何时由于硬件或通信故障而不再可用。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-171">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="e8d1c-172">例如，如果前端服务器服务 (RTCSRV) 因前端服务器或前端池发生故障而停止，则 HLB 监视还应停止接收 Web 服务的流量。</span><span class="sxs-lookup"><span data-stu-id="e8d1c-172">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="e8d1c-173">可在 HLB 上实施端口监控来监控以下各项：</span><span class="sxs-lookup"><span data-stu-id="e8d1c-173">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="e8d1c-174">前端服务器用户池– HLB 内部接口</span><span class="sxs-lookup"><span data-stu-id="e8d1c-174">Front End Server User Pool – HLB Internal Interface</span></span>

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
<th><span data-ttu-id="e8d1c-175">虚拟 IP/端口</span><span class="sxs-lookup"><span data-stu-id="e8d1c-175">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="e8d1c-176">节点端口</span><span class="sxs-lookup"><span data-stu-id="e8d1c-176">Node Port</span></span></th>
<th><span data-ttu-id="e8d1c-177">节点计算机/监视器</span><span class="sxs-lookup"><span data-stu-id="e8d1c-177">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="e8d1c-178">持久性配置文件</span><span class="sxs-lookup"><span data-stu-id="e8d1c-178">Persistence Profile</span></span></th>
<th><span data-ttu-id="e8d1c-179">注释</span><span class="sxs-lookup"><span data-stu-id="e8d1c-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8d1c-180">&lt;池 &gt; web-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="e8d1c-180">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="e8d1c-181">443</span><span class="sxs-lookup"><span data-stu-id="e8d1c-181">443</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-182">443</span><span class="sxs-lookup"><span data-stu-id="e8d1c-182">443</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-183">前端</span><span class="sxs-lookup"><span data-stu-id="e8d1c-183">Front End</span></span></p>
<p><span data-ttu-id="e8d1c-184">5061</span><span class="sxs-lookup"><span data-stu-id="e8d1c-184">5061</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-185">Source</span><span class="sxs-lookup"><span data-stu-id="e8d1c-185">Source</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-186">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8d1c-186">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8d1c-187">&lt;池 &gt; web-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="e8d1c-187">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="e8d1c-188">80</span><span class="sxs-lookup"><span data-stu-id="e8d1c-188">80</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-189">80</span><span class="sxs-lookup"><span data-stu-id="e8d1c-189">80</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-190">前端</span><span class="sxs-lookup"><span data-stu-id="e8d1c-190">Front End</span></span></p>
<p><span data-ttu-id="e8d1c-191">5061</span><span class="sxs-lookup"><span data-stu-id="e8d1c-191">5061</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-192">Source</span><span class="sxs-lookup"><span data-stu-id="e8d1c-192">Source</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-193">HTTP</span><span class="sxs-lookup"><span data-stu-id="e8d1c-193">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="e8d1c-194">前端服务器用户池– HLB 外部接口</span><span class="sxs-lookup"><span data-stu-id="e8d1c-194">Front End Server User Pool – HLB External Interface</span></span>

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
<th><span data-ttu-id="e8d1c-195">虚拟 IP/端口</span><span class="sxs-lookup"><span data-stu-id="e8d1c-195">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="e8d1c-196">节点端口</span><span class="sxs-lookup"><span data-stu-id="e8d1c-196">Node Port</span></span></th>
<th><span data-ttu-id="e8d1c-197">节点计算机/监视器</span><span class="sxs-lookup"><span data-stu-id="e8d1c-197">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="e8d1c-198">持久性配置文件</span><span class="sxs-lookup"><span data-stu-id="e8d1c-198">Persistence Profile</span></span></th>
<th><span data-ttu-id="e8d1c-199">注释</span><span class="sxs-lookup"><span data-stu-id="e8d1c-199">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8d1c-200">&lt;池 &gt; web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="e8d1c-200">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="e8d1c-201">443</span><span class="sxs-lookup"><span data-stu-id="e8d1c-201">443</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-202">4443</span><span class="sxs-lookup"><span data-stu-id="e8d1c-202">4443</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-203">前端</span><span class="sxs-lookup"><span data-stu-id="e8d1c-203">Front End</span></span></p>
<p><span data-ttu-id="e8d1c-204">5061</span><span class="sxs-lookup"><span data-stu-id="e8d1c-204">5061</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-205">无</span><span class="sxs-lookup"><span data-stu-id="e8d1c-205">None</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-206">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8d1c-206">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8d1c-207">&lt;池 &gt; web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="e8d1c-207">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="e8d1c-208">80</span><span class="sxs-lookup"><span data-stu-id="e8d1c-208">80</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-209">8080</span><span class="sxs-lookup"><span data-stu-id="e8d1c-209">8080</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-210">前端</span><span class="sxs-lookup"><span data-stu-id="e8d1c-210">Front End</span></span></p>
<p><span data-ttu-id="e8d1c-211">5061</span><span class="sxs-lookup"><span data-stu-id="e8d1c-211">5061</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-212">无</span><span class="sxs-lookup"><span data-stu-id="e8d1c-212">None</span></span></p></td>
<td><p><span data-ttu-id="e8d1c-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="e8d1c-213">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

