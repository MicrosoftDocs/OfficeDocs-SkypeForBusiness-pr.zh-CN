---
title: 'Lync Server 2013: DNS 摘要-自动发现'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e303ebecc42f03197f6502296c8a2708e97ebf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="2141d-102">DNS 摘要-Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="2141d-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2141d-103">_**主题上次修改时间:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="2141d-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="2141d-104">自动发现是一种灵活的服务, 它将通过 HTTP 或 HTTPS 接受通信。</span><span class="sxs-lookup"><span data-stu-id="2141d-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="2141d-105">若要实现此目的, 必须正确配置托管自动发现服务的服务器所使用的域名系统 (DNS) 和证书。</span><span class="sxs-lookup"><span data-stu-id="2141d-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="2141d-106">证书要求在 "[证书摘要-Lync Server 2013 中的自动发现](lync-server-2013-certificate-summary-autodiscover.md)" 中介绍。</span><span class="sxs-lookup"><span data-stu-id="2141d-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2141d-107">Lync Server 客户端的 DNS 查找逻辑使用特定的解决方案顺序。</span><span class="sxs-lookup"><span data-stu-id="2141d-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="2141d-108">你应始终同时包含 lyncdiscoverinternal。&lt;域&gt;和 lyncdiscover。&lt;您&gt;的 DNS 中的域。</span><span class="sxs-lookup"><span data-stu-id="2141d-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="2141d-109">不包括 lyncdiscoverinternal。&lt;域&gt;记录将导致内部客户端无法连接到预期服务或接收不正确的自动发现响应。</span><span class="sxs-lookup"><span data-stu-id="2141d-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="2141d-110">内部 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2141d-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2141d-111">记录类型</span><span class="sxs-lookup"><span data-stu-id="2141d-111">Record type</span></span></th>
<th><span data-ttu-id="2141d-112">主机名</span><span class="sxs-lookup"><span data-stu-id="2141d-112">Host name</span></span></th>
<th><span data-ttu-id="2141d-113">解析为</span><span class="sxs-lookup"><span data-stu-id="2141d-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2141d-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="2141d-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="2141d-115">Lyncdiscoverinternal.&lt;内部域名&gt;</span><span class="sxs-lookup"><span data-stu-id="2141d-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="2141d-116">如果你有控制器池的内部 Web 服务 FQDN, 或者如果你没有 Director, 则为你的前端池。</span><span class="sxs-lookup"><span data-stu-id="2141d-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2141d-117">A (主机, 如果是 IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="2141d-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="2141d-118">lyncdiscoverinternal.&lt;内部域名&gt;</span><span class="sxs-lookup"><span data-stu-id="2141d-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="2141d-119">如果你有控制器池的内部 Web 服务 IP 地址 (VIP) 地址 (如果你有一个负载平衡器), 或者你的前端池 (如果你没有 Director), 请使用该地址。</span><span class="sxs-lookup"><span data-stu-id="2141d-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2141d-120">您需要创建下列外部 DNS 记录之一:</span><span class="sxs-lookup"><span data-stu-id="2141d-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="2141d-121">外部 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2141d-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2141d-122">记录类型</span><span class="sxs-lookup"><span data-stu-id="2141d-122">Record type</span></span></th>
<th><span data-ttu-id="2141d-123">主机名</span><span class="sxs-lookup"><span data-stu-id="2141d-123">Host name</span></span></th>
<th><span data-ttu-id="2141d-124">解析为</span><span class="sxs-lookup"><span data-stu-id="2141d-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2141d-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="2141d-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="2141d-126">lyncdiscover.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="2141d-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="2141d-127">如果你有控制器池的外部 Web 服务 FQDN, 或者如果你没有 Director, 则为你的前端池。</span><span class="sxs-lookup"><span data-stu-id="2141d-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2141d-128">A (主机, 如果是 IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="2141d-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="2141d-129">lyncdiscover.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="2141d-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="2141d-130">反向代理的外部或公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2141d-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2141d-131">外部流量通过反向代理。</span><span class="sxs-lookup"><span data-stu-id="2141d-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2141d-132">移动设备客户端不支持来自不同域的多个安全套接字层 (SSL) 证书。</span><span class="sxs-lookup"><span data-stu-id="2141d-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="2141d-133">因此, 不支持通过 HTTPS 对不同域进行 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="2141d-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="2141d-134">例如, 不支持通过 HTTPS 重定向到 director.contoso.net 地址的 lyncdiscover.contoso.com 的 DNS CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="2141d-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="2141d-135">在此类拓扑中, 移动设备客户端需要对第一个请求使用 HTTP, 以便 CNAME 重定向通过 HTTP 进行解析。</span><span class="sxs-lookup"><span data-stu-id="2141d-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="2141d-136">随后的请求将使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="2141d-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="2141d-137">若要支持此方案, 你需要使用端口 80 (HTTP) 的 web 发布规则配置反向代理。</span><span class="sxs-lookup"><span data-stu-id="2141d-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="2141d-138">有关详细信息, 请参阅在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中配置反向代理</A>中的 "为端口80创建 web 发布规则"。</span><span class="sxs-lookup"><span data-stu-id="2141d-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="2141d-139">通过 HTTPS 支持到同一域的 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="2141d-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="2141d-140">在这种情况下, 目标域的证书覆盖了始发域。</span><span class="sxs-lookup"><span data-stu-id="2141d-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2141d-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2141d-141">See Also</span></span>


[<span data-ttu-id="2141d-142">在 Lync Server 2013 中配置反向代理以实现移动功能</span><span class="sxs-lookup"><span data-stu-id="2141d-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="2141d-143">证书摘要-Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="2141d-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

