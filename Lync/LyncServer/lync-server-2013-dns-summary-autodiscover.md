---
title: Lync Server 2013： DNS 摘要-自动发现
description: Lync Server 2013： DNS 摘要-自动发现。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574278"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="1fb23-103">Lync Server 2013 中的 DNS 摘要-自动发现</span><span class="sxs-lookup"><span data-stu-id="1fb23-103">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fb23-104">_**上次修改的主题：** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="1fb23-104">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="1fb23-105">自动发现是一项灵活的服务，因为它将接受通过 HTTP 或 HTTPS 进行的通信。</span><span class="sxs-lookup"><span data-stu-id="1fb23-105">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="1fb23-106">为实现此目的， (DNS) 域名系统，并且必须正确配置承载自动发现服务的服务器所使用的证书。</span><span class="sxs-lookup"><span data-stu-id="1fb23-106">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="1fb23-107">[在 Lync Server 2013 中的证书摘要-自动发现](lync-server-2013-certificate-summary-autodiscover.md)中介绍了证书要求。</span><span class="sxs-lookup"><span data-stu-id="1fb23-107">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1fb23-108">Lync Server 客户端的 DNS 查找逻辑使用特定的解决方案顺序。</span><span class="sxs-lookup"><span data-stu-id="1fb23-108">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="1fb23-109">应始终同时包含 lyncdiscoverinternal.。 &lt;域 &gt; 和 lyncdiscover.。 &lt;&gt;DNS 中的域。</span><span class="sxs-lookup"><span data-stu-id="1fb23-109">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="1fb23-110">不包括 lyncdiscoverinternal.。 &lt;域 &gt; 记录将导致内部客户端无法连接到预期服务或接收错误的自动发现响应。</span><span class="sxs-lookup"><span data-stu-id="1fb23-110">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="1fb23-111">内部 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="1fb23-111">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fb23-112">记录类型</span><span class="sxs-lookup"><span data-stu-id="1fb23-112">Record type</span></span></th>
<th><span data-ttu-id="1fb23-113">主机名</span><span class="sxs-lookup"><span data-stu-id="1fb23-113">Host name</span></span></th>
<th><span data-ttu-id="1fb23-114">解析为</span><span class="sxs-lookup"><span data-stu-id="1fb23-114">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fb23-115">CNAME</span><span class="sxs-lookup"><span data-stu-id="1fb23-115">CNAME</span></span></p></td>
<td><p><span data-ttu-id="1fb23-116">Lyncdiscoverinternal.。 &lt;内部域名&gt;</span><span class="sxs-lookup"><span data-stu-id="1fb23-116">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="1fb23-117">如果你拥有控制器池的内部 Web 服务 FQDN （如果有），或者如果你没有控制器，则为你的前端池。</span><span class="sxs-lookup"><span data-stu-id="1fb23-117">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb23-118"> (主机（如果 IPv6） AAAA) </span><span class="sxs-lookup"><span data-stu-id="1fb23-118">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="1fb23-119">lyncdiscoverinternal.。 &lt;内部域名&gt;</span><span class="sxs-lookup"><span data-stu-id="1fb23-119">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="1fb23-120">内部 Web 服务 IP 地址 (虚拟 IP (VIP) 地址，如果您拥有控制器池的负载平衡器) （如果有），或者如果您没有控制器，则使用前端池。</span><span class="sxs-lookup"><span data-stu-id="1fb23-120">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1fb23-121">您需要创建下列外部 DNS 记录之一：</span><span class="sxs-lookup"><span data-stu-id="1fb23-121">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="1fb23-122">外部 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="1fb23-122">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fb23-123">记录类型</span><span class="sxs-lookup"><span data-stu-id="1fb23-123">Record type</span></span></th>
<th><span data-ttu-id="1fb23-124">主机名</span><span class="sxs-lookup"><span data-stu-id="1fb23-124">Host name</span></span></th>
<th><span data-ttu-id="1fb23-125">解析为</span><span class="sxs-lookup"><span data-stu-id="1fb23-125">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fb23-126">CNAME</span><span class="sxs-lookup"><span data-stu-id="1fb23-126">CNAME</span></span></p></td>
<td><p><span data-ttu-id="1fb23-127">lyncdiscover.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="1fb23-127">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="1fb23-128">如果你拥有控制器池的外部 Web 服务 FQDN （如果有），或者如果你没有控制器，则为你的前端池。</span><span class="sxs-lookup"><span data-stu-id="1fb23-128">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb23-129"> (主机（如果 IPv6） AAAA) </span><span class="sxs-lookup"><span data-stu-id="1fb23-129">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="1fb23-130">lyncdiscover.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="1fb23-130">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="1fb23-131">反向代理的外部或公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1fb23-131">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1fb23-132">外部流量将通过反向代理。</span><span class="sxs-lookup"><span data-stu-id="1fb23-132">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1fb23-133">移动设备客户端不支持来自不同域的多个安全套接字层 (SSL) 证书。</span><span class="sxs-lookup"><span data-stu-id="1fb23-133">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="1fb23-134">因此，不支持通过 HTTPS 对其他域进行 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="1fb23-134">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="1fb23-135">例如，不支持通过 HTTPS 将 lyncdiscover.contoso.com 的 DNS CNAME 记录重定向到 director.contoso.net 地址。</span><span class="sxs-lookup"><span data-stu-id="1fb23-135">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="1fb23-136">在此类拓扑中，移动设备客户端需要对第一个请求使用 HTTP，以便通过 HTTP 解析 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="1fb23-136">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="1fb23-137">之后，后续请求会使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="1fb23-137">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="1fb23-138">若要支持此方案，您需要使用针对端口 80 (HTTP) 的 Web 发布规则配置反向代理。</span><span class="sxs-lookup"><span data-stu-id="1fb23-138">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="1fb23-139">有关详细信息，请参阅在 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中配置反向代理以实现移动性的反向代理</A>中的 "为端口80创建 web 发布规则"。</span><span class="sxs-lookup"><span data-stu-id="1fb23-139">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="1fb23-140">支持通过 HTTPS 对同一域的 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="1fb23-140">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="1fb23-141">在这种情况下，目标域的证书将覆盖源域。</span><span class="sxs-lookup"><span data-stu-id="1fb23-141">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1fb23-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fb23-142">See Also</span></span>


[<span data-ttu-id="1fb23-143">在 Lync Server 2013 中配置反向代理以实现移动功能</span><span class="sxs-lookup"><span data-stu-id="1fb23-143">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="1fb23-144">证书摘要-Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="1fb23-144">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

