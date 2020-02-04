---
title: Lync Server 2013：前端池的 DNS 要求
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
ms.openlocfilehash: 4b763f9b01e070fc434dae997bc1e2da68dcbc26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="40186-102">Lync Server 2013 中前端池的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="40186-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40186-103">_**主题上次修改时间：** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="40186-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="40186-104">本节介绍部署前端池所需的域名系统（DNS）记录。</span><span class="sxs-lookup"><span data-stu-id="40186-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="40186-105">前端池的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="40186-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="40186-106">下表指定了 Lync Server 2013 前端池部署的 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="40186-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="40186-107">前端池的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="40186-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40186-108">部署方案</span><span class="sxs-lookup"><span data-stu-id="40186-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="40186-109">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="40186-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40186-110">具有多个前端服务器和硬件负载平衡器（无论是否还在该池中部署了 DNS 负载平衡）的前端池</span><span class="sxs-lookup"><span data-stu-id="40186-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="40186-111">同时使用 DNS 负载平衡和硬件负载平衡器时，你需要托管（A）条记录。</span><span class="sxs-lookup"><span data-stu-id="40186-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="40186-112">创建一个内部 A 记录，用于解析用于 DNS 负载平衡的前端池的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="40186-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="40186-113">为内部 Web 服务创建内部主机（A）记录以使用负载平衡器的虚拟 IP （VIP）地址。</span><span class="sxs-lookup"><span data-stu-id="40186-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="40186-114">你必须使用拓扑生成器中定义的内部 Web 服务名称。</span><span class="sxs-lookup"><span data-stu-id="40186-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="40186-115">例如，如果你同时使用 DNS 负载平衡和硬件负载平衡，你将在一个池中为 DNS 负载平衡的池中的每个前端服务器提供一个记录，并提供指向硬件负载平衡器的虚拟 IP 的内部 Web 服务的 A 记录:</span><span class="sxs-lookup"><span data-stu-id="40186-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="40186-116">DNS 负载平衡： Pool01.contoso.net 的 IP 地址池10.10.10。5</span><span class="sxs-lookup"><span data-stu-id="40186-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="40186-117">每个前端服务器还将具有不同的 A 记录：</span><span class="sxs-lookup"><span data-stu-id="40186-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="40186-118">FE01.contoso.net 10.10.10。1</span><span class="sxs-lookup"><span data-stu-id="40186-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="40186-119">FE02.contoso.net 10.10.10。2</span><span class="sxs-lookup"><span data-stu-id="40186-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="40186-120">FE03.contoso.net 10.10.10。3</span><span class="sxs-lookup"><span data-stu-id="40186-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="40186-121">FE04.contoso.net 10.10.10。4</span><span class="sxs-lookup"><span data-stu-id="40186-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="40186-122">硬件负载平衡： WebInternal.contoso.net HLB VIP 192.168.10.5 的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="40186-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="40186-123">除 HTTP/HTTPS 流量之外的所有通信都将使用 Pool01.contoso.net 记录。</span><span class="sxs-lookup"><span data-stu-id="40186-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="40186-124">HTTP/HTTPS 流量将使用已定义的内部 Web 服务地址192.168.10。5</span><span class="sxs-lookup"><span data-stu-id="40186-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40186-125">部署了 DNS 负载平衡的前端池</span><span class="sxs-lookup"><span data-stu-id="40186-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="40186-126">一组内部 A 记录，用于将池的 FQDN 解析为池中每台服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="40186-126">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool.</span></span> <span data-ttu-id="40186-127">池中每台服务器必须有一条记录。</span><span class="sxs-lookup"><span data-stu-id="40186-127">There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40186-128">部署了 DNS 负载平衡的前端池</span><span class="sxs-lookup"><span data-stu-id="40186-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="40186-129">一组内部 A 记录，用于将池中的每个服务器的 FQDN 解析为该服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="40186-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="40186-130">有关详细信息，请参阅规划文档中<a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013 中的 "DNS 负载平衡</a>"。</span><span class="sxs-lookup"><span data-stu-id="40186-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40186-131">带有单个前端服务器和专用后端数据库但没有负载平衡器的前端池</span><span class="sxs-lookup"><span data-stu-id="40186-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="40186-132">一个内部 A 记录，可将前端池的 FQDN 解析为单个企业版前端服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="40186-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40186-133">自动客户端登录</span><span class="sxs-lookup"><span data-stu-id="40186-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="40186-134">对于每个受支持的 SIP 域，_sipinternaltls 的 SRV 记录。 _tcp。&lt;通过&gt;端口5061的域映射到用于对登录的客户端请求进行身份验证和重定向的前端池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="40186-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="40186-135">有关详细信息，请参阅<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自动客户端登录 DNS 要求</a>。</span><span class="sxs-lookup"><span data-stu-id="40186-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40186-136">通过统一通信（UC）设备进行的设备更新 Web 服务发现</span><span class="sxs-lookup"><span data-stu-id="40186-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="40186-137">名为 ucupdates-r2 的内部 A 记录。&lt;SIP 域&gt; ，可解析为托管设备更新 Web 服务的前端池的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="40186-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="40186-138">在 UC 设备处于打开状态但用户从未登录到设备的情况下，A 记录允许设备发现前端池托管设备更新 Web 服务并获取更新。</span><span class="sxs-lookup"><span data-stu-id="40186-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="40186-139">否则，设备会在用户第一次登录时通过带内预配获取此信息。</span><span class="sxs-lookup"><span data-stu-id="40186-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="40186-140">如果您在 Lync Server 2010 中已有设备更新 Web 服务的现有部署，则您已使用名称 ucupdates 创建了一个内部 A 记录。&lt;SIP 域&gt;。</span><span class="sxs-lookup"><span data-stu-id="40186-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="40186-141">对于 Microsoft Office 通信服务器 2007 R2，必须创建一个名为 ucupdates-R2 的附加 DNS A 记录。&lt;SIP 域&gt;。</span><span class="sxs-lookup"><span data-stu-id="40186-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40186-142">支持 HTTP 流量的反向代理</span><span class="sxs-lookup"><span data-stu-id="40186-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="40186-143">将外部 web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="40186-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="40186-144">客户端和 UC 设备使用此记录连接到反向代理。</span><span class="sxs-lookup"><span data-stu-id="40186-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="40186-145">有关详细信息，请参阅在规划文档中<a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a>。</span><span class="sxs-lookup"><span data-stu-id="40186-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="40186-146">下表显示内部 web 场 FQDN 所需的 DNS 记录的示例。</span><span class="sxs-lookup"><span data-stu-id="40186-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="40186-147">内部 Web 场 FQDN 的 DNS 记录示例</span><span class="sxs-lookup"><span data-stu-id="40186-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40186-148">内部 web 场 FQDN</span><span class="sxs-lookup"><span data-stu-id="40186-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="40186-149">池 FQDN</span><span class="sxs-lookup"><span data-stu-id="40186-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="40186-150">DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="40186-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40186-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40186-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="40186-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40186-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="40186-153">Ee-pool.contoso.com 的 DNS A 记录，它解析为前端服务器使用的负载平衡器的 VIP 地址。</span><span class="sxs-lookup"><span data-stu-id="40186-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="40186-154">用于解析为前端服务器使用的负载平衡器的 VIP 地址的 webcon.contoso.com 的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="40186-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40186-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40186-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="40186-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40186-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="40186-157">Ee-pool.contoso.com 的 DNS A 记录，用于解析为前端池中的企业版前端服务器使用的负载平衡器的虚拟 IP （VIP）地址。</span><span class="sxs-lookup"><span data-stu-id="40186-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="40186-158">请注意，如果在此池中使用 DNS 负载平衡，则您的前端池和内部 web 场不能具有相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="40186-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

