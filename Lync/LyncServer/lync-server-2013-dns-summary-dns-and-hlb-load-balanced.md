---
title: Lync Server 2013： DNS 摘要-DNS 摘要-DNS 和 HLB 负载平衡
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
ms.openlocfilehash: a6a3dc04856e1727c3982864995494cee751f457
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532149"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="5ca15-102">Lync Server 2013 中的 DNS 摘要-DNS 和 HLB 负载平衡</span><span class="sxs-lookup"><span data-stu-id="5ca15-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ca15-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="5ca15-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="5ca15-104">下表包含支持 DNS 负载平衡和硬件负载平衡控制器所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="5ca15-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="5ca15-105">Director 的角色需要类似的 DNS 记录作为前端服务器。</span><span class="sxs-lookup"><span data-stu-id="5ca15-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="5ca15-106">所需的记录数反映在控制器证书所需的主题替代名称中。</span><span class="sxs-lookup"><span data-stu-id="5ca15-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="5ca15-107">与前端服务器不同，控制器池不承载用户帐户或承载移动服务。</span><span class="sxs-lookup"><span data-stu-id="5ca15-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="5ca15-108">使用 DNS 负载平衡和硬件负载平衡器的控制器池所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="5ca15-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ca15-109">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="5ca15-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5ca15-110">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="5ca15-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="5ca15-111">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="5ca15-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="5ca15-112">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="5ca15-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ca15-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5ca15-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5ca15-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5ca15-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5ca15-115">控制器</span><span class="sxs-lookup"><span data-stu-id="5ca15-115">Director</span></span></p></td>
<td><p><span data-ttu-id="5ca15-116">用于复制和服务器到服务器的控制器主机记录</span><span class="sxs-lookup"><span data-stu-id="5ca15-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ca15-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5ca15-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5ca15-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5ca15-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5ca15-119">控制器池</span><span class="sxs-lookup"><span data-stu-id="5ca15-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="5ca15-120">服务器到服务器的 DNS 负载平衡控制器池的主机记录</span><span class="sxs-lookup"><span data-stu-id="5ca15-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ca15-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5ca15-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5ca15-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ca15-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5ca15-123">控制器池</span><span class="sxs-lookup"><span data-stu-id="5ca15-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="5ca15-124">来自边缘服务器的内部接口的入站会话初始协议 (SIP) </span><span class="sxs-lookup"><span data-stu-id="5ca15-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ca15-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5ca15-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5ca15-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ca15-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5ca15-127">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="5ca15-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="5ca15-128">反向代理发布的经过硬件负载平衡的 dialin Web 服务</span><span class="sxs-lookup"><span data-stu-id="5ca15-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ca15-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5ca15-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5ca15-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ca15-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5ca15-131">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="5ca15-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="5ca15-132">反向代理发布的经过硬件负载平衡的 meet Web 服务</span><span class="sxs-lookup"><span data-stu-id="5ca15-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ca15-133">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5ca15-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5ca15-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ca15-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5ca15-135">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="5ca15-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="5ca15-136">由反向代理发布和定义，经过硬件负载平衡的用于控制器池的 Web Ticket 外部 Web 服务</span><span class="sxs-lookup"><span data-stu-id="5ca15-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

