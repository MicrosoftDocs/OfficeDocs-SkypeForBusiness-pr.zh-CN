---
title: Lync Server 2013： DNS 摘要-反向代理
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
ms.openlocfilehash: a5f79437c5253365e4333e7cd064883bba968a54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="53ab0-102">Lync Server 2013 中的 DNS 摘要-反向代理</span><span class="sxs-lookup"><span data-stu-id="53ab0-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53ab0-103">_**上次修改的主题：** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="53ab0-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="53ab0-104">可以在反向代理中配置两个网络适配器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="53ab0-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="53ab0-105">反向代理网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="53ab0-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="53ab0-106">**网络适配器 1（内部接口）** 示例</span><span class="sxs-lookup"><span data-stu-id="53ab0-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="53ab0-107">分配有 172.25.33.40 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="53ab0-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="53ab0-108">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="53ab0-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="53ab0-109">确保从包含反向代理内部接口的网络到包含 Lync Server 前端池服务器的任何网络的路由（例如，从172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="53ab0-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="53ab0-110">**网络适配器 2（外部接口）** 示例</span><span class="sxs-lookup"><span data-stu-id="53ab0-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="53ab0-111">至少为此网络适配器分配了一个公用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="53ab0-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="53ab0-p101">定义网关以指向外围中的路由器或集成防火墙。（在方案示例中为 10.45.16.1）</span><span class="sxs-lookup"><span data-stu-id="53ab0-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="53ab0-114">反向代理所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="53ab0-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53ab0-115">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="53ab0-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="53ab0-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="53ab0-116">FQDN</span></span></th>
<th><span data-ttu-id="53ab0-117">IP 地址</span><span class="sxs-lookup"><span data-stu-id="53ab0-117">IP address</span></span></th>
<th><span data-ttu-id="53ab0-118">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="53ab0-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53ab0-119">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="53ab0-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="53ab0-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="53ab0-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="53ab0-121">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="53ab0-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="53ab0-p102">来自内部部署的外部 Web 服务。可以为将使用此反向代理且已定义外部 Web 服务的任何 SIP 域的所有池和各个服务器定义和创建附加记录。</span><span class="sxs-lookup"><span data-stu-id="53ab0-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53ab0-124">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="53ab0-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="53ab0-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="53ab0-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="53ab0-126">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="53ab0-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="53ab0-127">部署中的控制器或控制器池的外部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="53ab0-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="53ab0-128">您可以定义任意多个控制器，因为有不同的控制器，这些控制器可能与其他 SIP 域相关联。</span><span class="sxs-lookup"><span data-stu-id="53ab0-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="53ab0-129">定义和发布控制器的 DNS 记录不是前端池或控制器决策。</span><span class="sxs-lookup"><span data-stu-id="53ab0-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="53ab0-130">如果您使用的是控制器，则必须定义并发布 Director 和前端池外部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="53ab0-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="53ab0-131">如果在拓扑中定义了特定的流量类型（用于身份验证和其他使用），则会先将其发送给控制器。</span><span class="sxs-lookup"><span data-stu-id="53ab0-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53ab0-132">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="53ab0-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="53ab0-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="53ab0-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="53ab0-134">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="53ab0-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="53ab0-135">在外部发布的电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="53ab0-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53ab0-136">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="53ab0-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="53ab0-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="53ab0-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="53ab0-138">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="53ab0-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="53ab0-139">在外部发布的会议</span><span class="sxs-lookup"><span data-stu-id="53ab0-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53ab0-140">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="53ab0-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="53ab0-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="53ab0-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="53ab0-142">为 Office Web Apps Server 分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="53ab0-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="53ab0-143">Office Web Apps Server 在内部部署或在外围部署，并已发布用于外部客户端访问</span><span class="sxs-lookup"><span data-stu-id="53ab0-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53ab0-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="53ab0-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="53ab0-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="53ab0-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="53ab0-146">为外部发布的资源分配的侦听器</span><span class="sxs-lookup"><span data-stu-id="53ab0-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="53ab0-147">Lync 发现外部发布的自动发现的外部记录，包括移动性、Microsoft Lync Web App 和计划程序 Web 应用</span><span class="sxs-lookup"><span data-stu-id="53ab0-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

