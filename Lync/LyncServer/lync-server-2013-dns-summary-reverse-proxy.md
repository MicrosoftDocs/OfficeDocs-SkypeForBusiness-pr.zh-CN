---
title: Lync Server 2013： DNS 摘要-反向代理
description: Lync Server 2013： DNS 摘要-反向代理。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2d806893786a11317be1eff9bfdc08c9230bf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544788"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="2f791-103">Lync Server 2013 中的 DNS 摘要-反向代理</span><span class="sxs-lookup"><span data-stu-id="2f791-103">DNS summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f791-104">_**上次修改的主题：** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="2f791-104">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="2f791-105">可以在反向代理中配置两个网络适配器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2f791-105">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="2f791-106">反向代理网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="2f791-106">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="2f791-107">**网络适配器 1（内部接口）** 示例</span><span class="sxs-lookup"><span data-stu-id="2f791-107">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="2f791-108">分配有 172.25.33.40 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="2f791-108">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="2f791-109">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="2f791-109">No default gateway is defined.</span></span>
    
    <span data-ttu-id="2f791-110">确保有一个从包含反向代理内部接口的网络到包含 Lync Server 前端池服务器的任何网络的路由 (例如，从172.25.33.0 到 192.168.10.0) 。</span><span class="sxs-lookup"><span data-stu-id="2f791-110">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="2f791-111">**网络适配器 2（外部接口）** 示例</span><span class="sxs-lookup"><span data-stu-id="2f791-111">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="2f791-112">至少为此网络适配器分配了一个公用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2f791-112">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="2f791-p101">定义网关以指向外围中的路由器或集成防火墙。（在方案示例中为 10.45.16.1）</span><span class="sxs-lookup"><span data-stu-id="2f791-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="2f791-115">反向代理所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2f791-115">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f791-116">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="2f791-116">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2f791-117">FQDN</span><span class="sxs-lookup"><span data-stu-id="2f791-117">FQDN</span></span></th>
<th><span data-ttu-id="2f791-118">IP 地址</span><span class="sxs-lookup"><span data-stu-id="2f791-118">IP address</span></span></th>
<th><span data-ttu-id="2f791-119">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="2f791-119">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f791-120">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2f791-120">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2f791-121">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f791-121">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f791-122">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="2f791-122">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2f791-p102">来自内部部署的外部 Web 服务。可以为将使用此反向代理且已定义外部 Web 服务的任何 SIP 域的所有池和各个服务器定义和创建附加记录。</span><span class="sxs-lookup"><span data-stu-id="2f791-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f791-125">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2f791-125">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2f791-126">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f791-126">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f791-127">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="2f791-127">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2f791-128">部署中的控制器或控制器池的外部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="2f791-128">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="2f791-129">您可以定义任意多个控制器，因为有不同的控制器，这些控制器可能与其他 SIP 域相关联。</span><span class="sxs-lookup"><span data-stu-id="2f791-129">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="2f791-130">定义和发布控制器的 DNS 记录不是前端池或控制器决策。</span><span class="sxs-lookup"><span data-stu-id="2f791-130">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="2f791-131">如果您使用的是控制器，则必须定义并发布 Director 和前端池外部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="2f791-131">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="2f791-132">若要将特定的流量类型 (用于身份验证和其他使用) 将首先发送到控制器，前提是它是在拓扑中定义的。</span><span class="sxs-lookup"><span data-stu-id="2f791-132">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f791-133">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2f791-133">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2f791-134">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f791-134">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f791-135">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="2f791-135">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2f791-136">在外部发布的电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="2f791-136">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f791-137">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2f791-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2f791-138">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f791-138">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f791-139">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="2f791-139">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2f791-140">在外部发布的会议</span><span class="sxs-lookup"><span data-stu-id="2f791-140">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f791-141">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2f791-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2f791-142">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f791-142">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f791-143">为 Office Web Apps Server 分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="2f791-143">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="2f791-144">Office Web Apps Server 在内部部署或在外围部署，并已发布用于外部客户端访问</span><span class="sxs-lookup"><span data-stu-id="2f791-144">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f791-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2f791-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2f791-146">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f791-146">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f791-147">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="2f791-147">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2f791-148">Lync 发现外部发布的自动发现的外部记录，包括移动性、Microsoft Lync Web App 和计划程序 Web 应用</span><span class="sxs-lookup"><span data-stu-id="2f791-148">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

