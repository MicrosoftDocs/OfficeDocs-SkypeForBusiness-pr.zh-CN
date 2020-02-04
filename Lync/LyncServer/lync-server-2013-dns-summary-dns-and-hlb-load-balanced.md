---
title: Lync Server 2013：DNS 摘要 - 已进行 DNS 和 HLB 负载平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5b84ccab2b3074662016a19c5f0a51d0cb70405
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="88bbd-102">Lync Server 2013 中的 DNS 摘要 - 已进行 DNS 和 HLB 负载平衡</span><span class="sxs-lookup"><span data-stu-id="88bbd-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88bbd-103">_**主题上次修改时间：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="88bbd-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="88bbd-104">下表包含支持 DNS 负载平衡和硬件负载平衡控制器所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="88bbd-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="88bbd-105">Director 的角色需要类似的 DNS 记录作为前端服务器。</span><span class="sxs-lookup"><span data-stu-id="88bbd-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="88bbd-106">所需的记录数反映在 Director 证书所需的主题备用名称中。</span><span class="sxs-lookup"><span data-stu-id="88bbd-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="88bbd-107">与前端服务器不同，控制器池不托管用户帐户或托管移动服务。</span><span class="sxs-lookup"><span data-stu-id="88bbd-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="88bbd-108">使用 DNS 负载平衡和硬件负载平衡器的控制器池所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="88bbd-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88bbd-109">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="88bbd-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="88bbd-110">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="88bbd-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="88bbd-111">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="88bbd-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="88bbd-112">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="88bbd-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88bbd-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="88bbd-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88bbd-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="88bbd-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="88bbd-115">控制器</span><span class="sxs-lookup"><span data-stu-id="88bbd-115">Director</span></span></p></td>
<td><p><span data-ttu-id="88bbd-116">用于复制和服务器到服务器的控制器主机记录</span><span class="sxs-lookup"><span data-stu-id="88bbd-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88bbd-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="88bbd-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88bbd-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="88bbd-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="88bbd-119">控制器池</span><span class="sxs-lookup"><span data-stu-id="88bbd-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="88bbd-120">服务器到服务器的 DNS 负载平衡控制器池的主机记录</span><span class="sxs-lookup"><span data-stu-id="88bbd-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88bbd-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="88bbd-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88bbd-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88bbd-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88bbd-123">控制器池</span><span class="sxs-lookup"><span data-stu-id="88bbd-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="88bbd-124">来自边缘服务器的内部接口的入站会话初始协议（SIP）</span><span class="sxs-lookup"><span data-stu-id="88bbd-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88bbd-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="88bbd-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88bbd-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88bbd-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88bbd-127">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="88bbd-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="88bbd-128">从反向代理的硬件负载平衡发布的拨入 web 服务</span><span class="sxs-lookup"><span data-stu-id="88bbd-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88bbd-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="88bbd-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88bbd-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88bbd-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88bbd-131">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="88bbd-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="88bbd-132">硬件负载平衡已发布在反向代理中满足 web 服务</span><span class="sxs-lookup"><span data-stu-id="88bbd-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88bbd-133">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="88bbd-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88bbd-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88bbd-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88bbd-135">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="88bbd-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="88bbd-136">通过 "反向代理 Web 票" 发布和定义的硬件负载平衡控制器池的外部 web 服务</span><span class="sxs-lookup"><span data-stu-id="88bbd-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

