---
title: Lync Server 2013：前端池的 DNS 要求
description: Lync Server 2013：前端池的 DNS 要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c0369e82bd8ed2ea63e2156728b41f9942b0148
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574318"
---
# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="a4ac0-103">Lync Server 2013 中前端池的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="a4ac0-103">DNS requirements for Front End pools in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4ac0-104">_**上次修改的主题：** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="a4ac0-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="a4ac0-105">本节介绍部署前端池所需的域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-105">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="a4ac0-106">前端池的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="a4ac0-106">DNS Records for Front End Pools</span></span>

<span data-ttu-id="a4ac0-107">下表指定了 Lync Server 2013 前端池部署的 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-107">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="a4ac0-108">前端池的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="a4ac0-108">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4ac0-109">部署方案</span><span class="sxs-lookup"><span data-stu-id="a4ac0-109">Deployment scenario</span></span></th>
<th><span data-ttu-id="a4ac0-110">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="a4ac0-110">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4ac0-111">带有多个前端服务器和一个硬件负载平衡器的前端池（该池上是否也部署了 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="a4ac0-111">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-112">在同时使用 DNS 负载平衡和硬件负载平衡器时，您需要主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-112">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="a4ac0-113">为 DNS 负载平衡创建将解析前端池的完全限定域名 (FQDN) 的内部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-113">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="a4ac0-114">为内部 Web 服务创建针对负载平衡器的虚拟 IP (VIP) 地址的内部主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-114">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="a4ac0-115">您必须使用拓扑生成器中定义的内部 Web 服务名称。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-115">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="a4ac0-116">例如，如果同时使用 DNS 负载平衡和硬件负载平衡，则会为池内的每个前端服务器提供一个记录，以实现 DNS 负载平衡，将内部 Web 服务的 A 记录用于指向硬件负载平衡器的虚拟 IP：</span><span class="sxs-lookup"><span data-stu-id="a4ac0-116">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="a4ac0-117">DNS 负载平衡：   Pool01.contoso.net   池的 IP 地址   10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="a4ac0-117">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="a4ac0-118">每个前端服务器也将具有不同的 A 记录：</span><span class="sxs-lookup"><span data-stu-id="a4ac0-118">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="a4ac0-119">FE01.contoso.net 10.10.10。1</span><span class="sxs-lookup"><span data-stu-id="a4ac0-119">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="a4ac0-120">FE02.contoso.net 10.10.10。2</span><span class="sxs-lookup"><span data-stu-id="a4ac0-120">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="a4ac0-121">FE03.contoso.net 10.10.10。3</span><span class="sxs-lookup"><span data-stu-id="a4ac0-121">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="a4ac0-122">FE04.contoso.net 10.10.10。4</span><span class="sxs-lookup"><span data-stu-id="a4ac0-122">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="a4ac0-123">硬件负载平衡：   WebInternal.contoso.net    HLB VIP 的 IP 地址   192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="a4ac0-123">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="a4ac0-p102">除 HTTP/HTTPS 流量之外的所有流量都将使用 Pool01.contoso.net 记录。HTTP/HTTPS 流量将使用定义的内部 Web 服务地址 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="a4ac0-p102">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record. HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac0-126">部署了 DNS 负载平衡的前端池</span><span class="sxs-lookup"><span data-stu-id="a4ac0-126">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-p103">将池的 FQDN 解析为池中每个服务器的 IP 地址的一组内部 A 记录。池中的每个服务器都必须有一个 A 记录。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-p103">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool. There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac0-129">部署了 DNS 负载平衡的前端池</span><span class="sxs-lookup"><span data-stu-id="a4ac0-129">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-130">将池中每个服务器的 FQDN 解析为该服务器的 IP 地址的一组内部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-130">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="a4ac0-131">有关详细信息，请参阅规划文档中的 <a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013 中的 DNS 负载平衡</a> 。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-131">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac0-132">具有一个前端服务器和一个专用后端数据库、但没有负载平衡器的前端池</span><span class="sxs-lookup"><span data-stu-id="a4ac0-132">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-133">将前端池的 FQDN 解析为单个 Enterprise Edition 前端服务器的 IP 地址的内部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-133">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac0-134">自动客户端登录</span><span class="sxs-lookup"><span data-stu-id="a4ac0-134">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-135">对于每个受支持的 SIP 域，_sipinternaltls 的 SRV 记录。 _tcp c0/>&gt;通过端口5061的域映射到前端池的 FQDN，该前端池会对登录的客户端请求进行身份验证和重定向。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-135">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="a4ac0-136">有关详细信息，请参阅 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自动客户端登录的 DNS 要求</a>。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-136">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac0-137">统一通信 (UC) 设备发现设备更新 Web 服务</span><span class="sxs-lookup"><span data-stu-id="a4ac0-137">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-138">一个名为为 ucupdates-r2.-r2 的内部 A 记录。 &lt;&gt;解析为承载设备更新 Web 服务的前端池的 IP 地址的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-138">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="a4ac0-139">在打开了 UC 设备但用户从未登录到该设备的情况下，该设备通过此 A 记录可以发现承载设备更新 Web 服务的前端池并获得更新。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-139">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="a4ac0-140">否则，该设备在用户首次登录时通过带内设置获得此信息。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-140">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="a4ac0-141">如果您已在 Lync Server 2010 中部署了设备更新 Web 服务，则您已使用名称为 ucupdates-r2. 创建了一个内部 A 记录。 &lt;SIP 域 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-141">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="a4ac0-142">对于 Microsoft Office 通信服务器 2007 R2，必须创建一个名为为 ucupdates-r2.-R2 的附加 DNS A 记录。 &lt;SIP 域 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-142">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac0-143">支持 HTTP 流量的反向代理</span><span class="sxs-lookup"><span data-stu-id="a4ac0-143">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-144">将外部 Web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-144">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="a4ac0-145">客户端和 UC 设备使用此记录连接到反向代理。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-145">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="a4ac0-146">有关详细信息，请参阅规划文档中的 <a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a> 。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-146">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a4ac0-147">下表显示了内部 Web 场 FQDN 所需的 DNS 记录的示例。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-147">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="a4ac0-148">内部 Web 场 FQDN 的 DNS 记录示例</span><span class="sxs-lookup"><span data-stu-id="a4ac0-148">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4ac0-149">内部 Web 场 FQDN</span><span class="sxs-lookup"><span data-stu-id="a4ac0-149">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="a4ac0-150">池 FQDN</span><span class="sxs-lookup"><span data-stu-id="a4ac0-150">Pool FQDN</span></span></th>
<th><span data-ttu-id="a4ac0-151">DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="a4ac0-151">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4ac0-152">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4ac0-152">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-153">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4ac0-153">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-154">ee-pool.contoso.com 的 DNS A 记录，将解析为前端服务器使用的负载平衡器的 VIP 地址。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-154">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="a4ac0-155">webcon.contoso.com 的 DNS A 记录，将解析为前端服务器使用的负载平衡器的 VIP 地址。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-155">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac0-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4ac0-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-157">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4ac0-157">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a4ac0-158">ee-pool.contoso.com 的 DNS A 记录，将解析为前端池中 Enterprise Edition 前端服务器所使用的负载平衡器的虚拟 IP (VIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-158">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="a4ac0-159">请注意，如果您正对该池使用 DNS 负载平衡，则前端池和内部 Web 场不会有相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a4ac0-159">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

