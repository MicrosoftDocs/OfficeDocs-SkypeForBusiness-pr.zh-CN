---
title: Lync Server 2013： DNS 摘要-扩展的控制器池、硬件负载平衡器
description: Lync Server 2013： DNS 摘要-扩展的控制器池、硬件负载平衡器。
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
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555878"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="f1545-103">Lync Server 2013 中的 DNS 摘要-扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="f1545-103">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1545-104">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f1545-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f1545-105">下表列出了支持硬件负载平衡控制器所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="f1545-105">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="f1545-106">Director 的角色需要类似的 DNS 记录作为前端服务器。</span><span class="sxs-lookup"><span data-stu-id="f1545-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="f1545-107">所需的记录数反映在控制器证书所需的主题替代名称中。</span><span class="sxs-lookup"><span data-stu-id="f1545-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="f1545-108">与前端服务器不同，控制器池不承载用户帐户或承载移动服务。</span><span class="sxs-lookup"><span data-stu-id="f1545-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="f1545-109">使用硬件负载平衡器和 DNS 负载平衡的控制器池所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="f1545-109">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1545-110">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="f1545-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f1545-111">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="f1545-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f1545-112">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="f1545-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f1545-113">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="f1545-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1545-114">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f1545-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f1545-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f1545-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f1545-116">控制器</span><span class="sxs-lookup"><span data-stu-id="f1545-116">Director</span></span></p></td>
<td><p><span data-ttu-id="f1545-117">用于复制和服务器到服务器通信的控制器主机记录</span><span class="sxs-lookup"><span data-stu-id="f1545-117">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1545-118">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f1545-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f1545-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f1545-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f1545-120">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f1545-120">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f1545-121">DNS 负载平衡控制器池的主机记录</span><span class="sxs-lookup"><span data-stu-id="f1545-121">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1545-122">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f1545-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f1545-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1545-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f1545-124">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f1545-124">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f1545-125">来自边缘服务器的内部接口的入站会话初始协议 (SIP) </span><span class="sxs-lookup"><span data-stu-id="f1545-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1545-126">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f1545-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f1545-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1545-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f1545-128">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f1545-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f1545-129">反向代理发布的经过硬件负载平衡的 dialin Web 服务</span><span class="sxs-lookup"><span data-stu-id="f1545-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1545-130">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f1545-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f1545-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1545-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f1545-132">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f1545-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f1545-133">反向代理发布的经过硬件负载平衡的 meet Web 服务</span><span class="sxs-lookup"><span data-stu-id="f1545-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1545-134">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f1545-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f1545-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1545-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f1545-136">控制器池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f1545-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f1545-137">由反向代理发布和定义，经过硬件负载平衡的用于控制器池的 Web Ticket 外部 Web 服务</span><span class="sxs-lookup"><span data-stu-id="f1545-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

