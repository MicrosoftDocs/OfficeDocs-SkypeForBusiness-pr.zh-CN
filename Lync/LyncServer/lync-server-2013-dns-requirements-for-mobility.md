---
title: Lync Server 2013：移动性的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0201a9e8870a1b7d8cc579eb270ca67c929cae5d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="87f23-102">具有 Lync Server 2013 的移动性的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="87f23-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87f23-103">_**上次修改的主题：** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="87f23-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="87f23-104">在部署 Lync Server 2013 移动功能时，可以使用 Microsoft Lync Server 2013 自动发现服务中提供的新 Url，也可以使用现有的 Web 服务 Url。</span><span class="sxs-lookup"><span data-stu-id="87f23-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="87f23-105">如果您使用现有的 Url，则用户需要在其移动设备设置中手动输入 Url。</span><span class="sxs-lookup"><span data-stu-id="87f23-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="87f23-106">此选项通常用于故障排除。</span><span class="sxs-lookup"><span data-stu-id="87f23-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="87f23-107">使用新 Url 时，移动客户端可以自动发现 Lync Server 2013 资源。</span><span class="sxs-lookup"><span data-stu-id="87f23-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="87f23-108">当您支持自动发现时，您需要添加新的域名系统（DNS）记录。</span><span class="sxs-lookup"><span data-stu-id="87f23-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="87f23-109">本节介绍了自动发现所需的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="87f23-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="87f23-110">若要支持自动发现，您需要为每个 SIP 域创建以下 DNS 记录：</span><span class="sxs-lookup"><span data-stu-id="87f23-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="87f23-111">支持从组织网络内部进行连接的移动用户的内部 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="87f23-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="87f23-112">支持从 Internet 进行连接的移动用户的外部或公共 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="87f23-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="87f23-113">应无法从网络外部对内部自动发现 URL 进行寻址。</span><span class="sxs-lookup"><span data-stu-id="87f23-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="87f23-114">应无法从网络内部对外部自动发现 URL 进行寻址。</span><span class="sxs-lookup"><span data-stu-id="87f23-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="87f23-115">但是，如果您无法满足外部 URL 的此要求，则移动客户端功能不应受到影响。</span><span class="sxs-lookup"><span data-stu-id="87f23-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="87f23-116">DNS 记录可以是 CNAME 记录或 A（主机）记录。</span><span class="sxs-lookup"><span data-stu-id="87f23-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="87f23-117">**内部 DNS 记录**</span><span class="sxs-lookup"><span data-stu-id="87f23-117">**Internal DNS records**</span></span>

<span data-ttu-id="87f23-118">您需要创建以下内部 DNS 记录之一：</span><span class="sxs-lookup"><span data-stu-id="87f23-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87f23-119">记录类型</span><span class="sxs-lookup"><span data-stu-id="87f23-119">Record type</span></span></th>
<th><span data-ttu-id="87f23-120">主机名或 SRV 定义</span><span class="sxs-lookup"><span data-stu-id="87f23-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="87f23-121">解析为</span><span class="sxs-lookup"><span data-stu-id="87f23-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87f23-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="87f23-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="87f23-123">lyncdiscoverinternal..&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="87f23-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="87f23-124">如果你拥有控制器池的内部 Web 服务完全限定域名（FQDN）（如果有），或者对于你的前端池，如果你没有控制器，则为该域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="87f23-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87f23-125">A（主机）</span><span class="sxs-lookup"><span data-stu-id="87f23-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="87f23-126">lyncdiscoverinternal..&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="87f23-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="87f23-127">如果你拥有控制器池的内部 Web 服务 IP 地址（虚拟 IP （VIP）地址）（如果你有一个或多个前端池）（如果你没有控制器），则为该地址（VIP）地址）。</span><span class="sxs-lookup"><span data-stu-id="87f23-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87f23-128">**外部 DNS 记录**</span><span class="sxs-lookup"><span data-stu-id="87f23-128">**External DNS records**</span></span>

<span data-ttu-id="87f23-129">您需要创建下列外部 DNS 记录之一：</span><span class="sxs-lookup"><span data-stu-id="87f23-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87f23-130">记录类型</span><span class="sxs-lookup"><span data-stu-id="87f23-130">Record type</span></span></th>
<th><span data-ttu-id="87f23-131">主机名</span><span class="sxs-lookup"><span data-stu-id="87f23-131">Host name</span></span></th>
<th><span data-ttu-id="87f23-132">解析为</span><span class="sxs-lookup"><span data-stu-id="87f23-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87f23-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="87f23-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="87f23-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="87f23-134">lyncdiscover.</span></span> <span data-ttu-id="87f23-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="87f23-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="87f23-136">如果你拥有控制器池的外部 Web 服务 FQDN （如果有），或者如果你没有控制器，则为你的前端池</span><span class="sxs-lookup"><span data-stu-id="87f23-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87f23-137">A（主机）</span><span class="sxs-lookup"><span data-stu-id="87f23-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="87f23-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="87f23-138">lyncdiscover.</span></span> <span data-ttu-id="87f23-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="87f23-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="87f23-140">反向代理的外部或公共 IP 地址（如果使用负载平衡器，则为 VIP 地址）</span><span class="sxs-lookup"><span data-stu-id="87f23-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87f23-141">SRV</span><span class="sxs-lookup"><span data-stu-id="87f23-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="87f23-142">_sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="87f23-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="87f23-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="87f23-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="87f23-144">解析为访问边缘服务的主机（A 或 AAAA）记录</span><span class="sxs-lookup"><span data-stu-id="87f23-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="87f23-145">若要支持推送通知服务和 Apple 推送通知服务，请为拥有 Microsoft Lync 移动客户端的每个 SIP 域创建一个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="87f23-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="87f23-146">此要求仅适用于基于 Apple 或 Microsoft 的移动设备上的 Microsoft Lync 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="87f23-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="87f23-147">Andriod 和 Nokia Symbian 设备不使用推送通知。</span><span class="sxs-lookup"><span data-stu-id="87f23-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="87f23-148">Lyncdiscover. 也称为自动发现，流量通过反向代理。</span><span class="sxs-lookup"><span data-stu-id="87f23-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="87f23-149">SRV 记录指向通过访问边缘服务解析的记录。</span><span class="sxs-lookup"><span data-stu-id="87f23-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

