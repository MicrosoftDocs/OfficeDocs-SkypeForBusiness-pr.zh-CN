---
title: Lync Server 2013：DNS 摘要 - 反向代理
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
ms.openlocfilehash: ae4834ce608f6726403e8742a4d506b173309b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="10f37-102">Lync Server 2013 中的 DNS 摘要 - 反向代理</span><span class="sxs-lookup"><span data-stu-id="10f37-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10f37-103">_**主题上次修改时间：** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="10f37-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="10f37-104">您在反向代理服务器中配置两个网络适配器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="10f37-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="10f37-105">反向代理网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="10f37-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="10f37-106">**网络适配器1（内部接口）** 示例</span><span class="sxs-lookup"><span data-stu-id="10f37-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="10f37-107">已分配172.25.33.40 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="10f37-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="10f37-108">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="10f37-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="10f37-109">确保存在从网络到包含 Lync Server 前端池服务器（例如从172.25.33.0 到192.168.10.0）的反向代理内部接口的路由。</span><span class="sxs-lookup"><span data-stu-id="10f37-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="10f37-110">**网络适配器2（外部接口）** 示例</span><span class="sxs-lookup"><span data-stu-id="10f37-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="10f37-111">至少有一个公共 IP 地址分配给此网络适配器。</span><span class="sxs-lookup"><span data-stu-id="10f37-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="10f37-112">网关定义为指向外部外围设备中的路由器或集成防火墙。</span><span class="sxs-lookup"><span data-stu-id="10f37-112">Gateway is defined to point to the router or integrated firewall in your outer perimeter.</span></span> <span data-ttu-id="10f37-113">（10.45.16.1 在方案示例中）</span><span class="sxs-lookup"><span data-stu-id="10f37-113">(10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="10f37-114">反向代理所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="10f37-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10f37-115">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="10f37-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="10f37-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="10f37-116">FQDN</span></span></th>
<th><span data-ttu-id="10f37-117">IP 地址</span><span class="sxs-lookup"><span data-stu-id="10f37-117">IP address</span></span></th>
<th><span data-ttu-id="10f37-118">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="10f37-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10f37-119">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="10f37-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="10f37-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10f37-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10f37-121">分配给外部已发布资源的侦听器</span><span class="sxs-lookup"><span data-stu-id="10f37-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="10f37-122">内部部署中的外部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="10f37-122">External web services from the internal deployment.</span></span> <span data-ttu-id="10f37-123">对于将使用此反向代理的任何 SIP 域，可以为所有池和单个服务器定义和创建其他记录，并且已定义外部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="10f37-123">Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10f37-124">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="10f37-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="10f37-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10f37-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10f37-126">分配给外部已发布资源的侦听器</span><span class="sxs-lookup"><span data-stu-id="10f37-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="10f37-127">部署中的控制器或控制器池的外部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="10f37-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="10f37-128">你可以定义任意多个控制器，因为不同的控制器可能与其他 SIP 域相关联。</span><span class="sxs-lookup"><span data-stu-id="10f37-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="10f37-129">定义和发布控制器的 DNS 记录既不是前端池，也不是控制器决策。</span><span class="sxs-lookup"><span data-stu-id="10f37-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="10f37-130">如果您使用的是董事，则必须定义和发布 Director 和前端池外部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="10f37-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="10f37-131">特定流量类型（用于身份验证和其他使用）将首先发送给 Director，前提是它在拓扑中定义。</span><span class="sxs-lookup"><span data-stu-id="10f37-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10f37-132">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="10f37-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="10f37-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10f37-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10f37-134">分配给外部已发布资源的侦听器</span><span class="sxs-lookup"><span data-stu-id="10f37-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="10f37-135">外部发布的电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="10f37-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10f37-136">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="10f37-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="10f37-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10f37-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10f37-138">分配给外部已发布资源的侦听器</span><span class="sxs-lookup"><span data-stu-id="10f37-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="10f37-139">外部发布的会议</span><span class="sxs-lookup"><span data-stu-id="10f37-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10f37-140">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="10f37-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="10f37-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10f37-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10f37-142">已分配 Office Web Apps 服务器侦听器</span><span class="sxs-lookup"><span data-stu-id="10f37-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="10f37-143">Office Web Apps 服务器内部部署或在外围部署，并且已发布外部客户端访问</span><span class="sxs-lookup"><span data-stu-id="10f37-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10f37-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="10f37-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="10f37-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10f37-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="10f37-146">分配给外部已发布资源的侦听器</span><span class="sxs-lookup"><span data-stu-id="10f37-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="10f37-147">Lync 发现外部发布的自动发现的外部记录，包括移动性、Microsoft Lync Web App 和计划程序 Web 应用</span><span class="sxs-lookup"><span data-stu-id="10f37-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

