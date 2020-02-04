---
title: Lync Server 2013：DNS 摘要 - 扩展的控制器池、硬件负载平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="e9682-102">Lync Server 2013 中的 DNS 摘要 - 扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="e9682-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9682-103">_**主题上次修改时间：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e9682-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e9682-104">下表包含支持硬件负载平衡控制器所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="e9682-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="e9682-105">Director 的角色需要类似的 DNS 记录作为前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e9682-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="e9682-106">所需的记录数反映在 Director 证书所需的主题备用名称中。</span><span class="sxs-lookup"><span data-stu-id="e9682-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="e9682-107">与前端服务器不同，控制器池不托管用户帐户或托管移动服务。</span><span class="sxs-lookup"><span data-stu-id="e9682-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="e9682-108">使用硬件负载平衡器和 DNS 负载平衡的控制器池所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="e9682-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9682-109">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="e9682-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e9682-110">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="e9682-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="e9682-111">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="e9682-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="e9682-112">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="e9682-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9682-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e9682-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e9682-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e9682-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="e9682-115">控制器</span><span class="sxs-lookup"><span data-stu-id="e9682-115">Director</span></span></p></td>
<td><p><span data-ttu-id="e9682-116">用于复制的控制器主机记录和服务器到服务器的通信</span><span class="sxs-lookup"><span data-stu-id="e9682-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9682-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e9682-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e9682-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e9682-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="e9682-119">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="e9682-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e9682-120">用于 DNS 负载平衡控制器池的主机记录</span><span class="sxs-lookup"><span data-stu-id="e9682-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9682-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e9682-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e9682-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9682-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e9682-123">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="e9682-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e9682-124">来自边缘服务器的内部接口的入站会话初始协议（SIP）</span><span class="sxs-lookup"><span data-stu-id="e9682-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9682-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e9682-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e9682-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9682-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e9682-127">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="e9682-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e9682-128">从反向代理的硬件负载平衡发布的拨入 web 服务</span><span class="sxs-lookup"><span data-stu-id="e9682-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9682-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e9682-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e9682-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9682-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e9682-131">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="e9682-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e9682-132">硬件负载平衡已发布在反向代理中满足 web 服务</span><span class="sxs-lookup"><span data-stu-id="e9682-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9682-133">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e9682-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e9682-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9682-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e9682-135">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="e9682-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e9682-136">通过 "反向代理 Web 票" 发布和定义的硬件负载平衡控制器池的外部 web 服务</span><span class="sxs-lookup"><span data-stu-id="e9682-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

