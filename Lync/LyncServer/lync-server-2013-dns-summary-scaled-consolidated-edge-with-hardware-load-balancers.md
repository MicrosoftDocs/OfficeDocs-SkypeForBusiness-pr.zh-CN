---
title: DNS 摘要-使用硬件负载平衡器的扩展的合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c45802282c57ebcf80fbc55b030c985fe7d977cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="aedeb-102">Lync Server 2013 中的 DNS 摘要-使用硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="aedeb-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aedeb-103">_**上次修改的主题：** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="aedeb-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="aedeb-104">与证书和端口相比，远程访问 Lync Server 2013 的 DNS 记录要求相当简单。</span><span class="sxs-lookup"><span data-stu-id="aedeb-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="aedeb-105">此外，许多记录是可选的，具体取决于如何配置运行 Lync 2013 的客户端以及是否启用联盟。</span><span class="sxs-lookup"><span data-stu-id="aedeb-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="aedeb-106">有关 Lync 2013 DNS 要求的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aedeb-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="aedeb-107">有关如何配置 Lync 2013 客户端的自动配置的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "自动配置，而不拆分大脑 dns" 部分。</span><span class="sxs-lookup"><span data-stu-id="aedeb-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="aedeb-108">下表包含支持“扩展的合并边缘拓扑（硬件负载已平衡）”图所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="aedeb-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="aedeb-109">请注意，只有 Lync 客户端的自动配置需要某些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="aedeb-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="aedeb-110">如果您计划使用组策略对象（Gpo）来配置 Lync 客户端，则不需要关联的记录。</span><span class="sxs-lookup"><span data-stu-id="aedeb-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="aedeb-111">重要说明：边缘服务器网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="aedeb-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="aedeb-112">若要避免路由问题，请确认边缘服务器中至少有两个网络适配器，并且默认网关仅在与外部接口相关联的网络适配器上设置。</span><span class="sxs-lookup"><span data-stu-id="aedeb-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="aedeb-113">例如，如在 Lync Server 2013 中的扩展的合并边缘方案中，在[使用硬件负载平衡](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)器的扩展合并边缘方案中，默认网关将指向外部防火墙。</span><span class="sxs-lookup"><span data-stu-id="aedeb-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="aedeb-114">您可以在每个边缘服务器中配置两个网络适配器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aedeb-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="aedeb-115">**网络适配器 1（内部接口）**</span><span class="sxs-lookup"><span data-stu-id="aedeb-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="aedeb-116">分配有 172.25.33.10 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="aedeb-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="aedeb-117">无默认网关。</span><span class="sxs-lookup"><span data-stu-id="aedeb-117">No default gateway.</span></span>
    
    <span data-ttu-id="aedeb-118">确保从网络中有一个路由，该网络包含向包含 Lync Server 客户端或运行 Lync Server 的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）的边缘服务器内部接口。</span><span class="sxs-lookup"><span data-stu-id="aedeb-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="aedeb-119">**网络适配器 2（外部接口）**</span><span class="sxs-lookup"><span data-stu-id="aedeb-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="aedeb-120">向此网络适配器分配三个公共 IP 地址，例如 131.107.155.10 for Access Edge service、131.107.155.20 for Web 会议边缘服务、131.107.155.30 for A/V Edge 服务。</span><span class="sxs-lookup"><span data-stu-id="aedeb-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="aedeb-121">分配给边缘服务器的实际外部网络接口的 IP 地址可能取决于所选的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="aedeb-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="aedeb-122">请参阅您的硬件负载平衡器的文档以了解实际 IP 地址要求。</span><span class="sxs-lookup"><span data-stu-id="aedeb-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="aedeb-123">可以为所有三个边缘服务接口使用一个 IP 地址，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="aedeb-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="aedeb-124">尽管这样可以节省 IP 地址，但需要为每个服务使用不同端口号。</span><span class="sxs-lookup"><span data-stu-id="aedeb-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="aedeb-125">默认端口号为 443/TCP，它可确保大多数远程防火墙将允许流量通过。</span><span class="sxs-lookup"><span data-stu-id="aedeb-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="aedeb-126">如果将端口值更改为（例如）访问边缘服务的 5061/TCP，则 Web 会议边缘服务的 444/tcp 和 A/V 边缘服务的 443/TCP 可能会导致远程用户出现问题，在该用户背后的防火墙不允许通过 5061/TCP 和 444/TCP 的流量。</span><span class="sxs-lookup"><span data-stu-id="aedeb-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="aedeb-127">另外，由于能够筛选 IP 地址，因此使用三个不同的 IP 地址更便于排除故障。</span><span class="sxs-lookup"><span data-stu-id="aedeb-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="aedeb-128">访问边缘服务 IP 地址主要是将默认网关设置为面向 Internet 的路由器（131.107.155.1）。</span><span class="sxs-lookup"><span data-stu-id="aedeb-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="aedeb-129">Web 会议边缘服务和 A/V 边缘服务 IP 地址（第二个）。</span><span class="sxs-lookup"><span data-stu-id="aedeb-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="aedeb-130">配置具有两个网络适配器的边缘服务器是两个选项之一。</span><span class="sxs-lookup"><span data-stu-id="aedeb-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="aedeb-131">另一种方法是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。</span><span class="sxs-lookup"><span data-stu-id="aedeb-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="aedeb-132">此选项的主要优点是，每个边缘服务器服务都有不同的网络适配器，并且在需要故障排除时有可能更简单的数据收集</span><span class="sxs-lookup"><span data-stu-id="aedeb-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="aedeb-133">扩展的合并边缘（硬件负载已平衡）所需的 DNS 记录（示例）</span><span class="sxs-lookup"><span data-stu-id="aedeb-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aedeb-134">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="aedeb-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="aedeb-135">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="aedeb-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="aedeb-136">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="aedeb-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="aedeb-137">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="aedeb-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aedeb-138">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="aedeb-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="aedeb-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aedeb-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aedeb-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="aedeb-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="aedeb-141">访问边缘服务外部接口（Contoso）。</span><span class="sxs-lookup"><span data-stu-id="aedeb-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="aedeb-142">根据需要为启用 Lync 的用户的所有 SIP 域重复使用</span><span class="sxs-lookup"><span data-stu-id="aedeb-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aedeb-143">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="aedeb-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="aedeb-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aedeb-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aedeb-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="aedeb-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="aedeb-146">Web 会议边缘服务外部接口</span><span class="sxs-lookup"><span data-stu-id="aedeb-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aedeb-147">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="aedeb-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="aedeb-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aedeb-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aedeb-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="aedeb-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="aedeb-150">A/V 边缘服务外部接口</span><span class="sxs-lookup"><span data-stu-id="aedeb-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aedeb-151">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="aedeb-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="aedeb-152">_sip _tls .com</span><span class="sxs-lookup"><span data-stu-id="aedeb-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aedeb-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aedeb-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aedeb-154">访问边缘服务外部接口。</span><span class="sxs-lookup"><span data-stu-id="aedeb-154">Access Edge service external interface.</span></span> <span data-ttu-id="aedeb-155">将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作是必需的。</span><span class="sxs-lookup"><span data-stu-id="aedeb-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="aedeb-156">根据需要为启用 Lync 的用户的所有 SIP 域重复使用。</span><span class="sxs-lookup"><span data-stu-id="aedeb-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aedeb-157">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="aedeb-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="aedeb-158">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="aedeb-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aedeb-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aedeb-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aedeb-160">SIP 访问边缘服务联合合作伙伴（称为 "允许的 SIP 域"）的自动 DNS 发现所需的外部接口（在以前的版本中称为 "增强联盟"）。</span><span class="sxs-lookup"><span data-stu-id="aedeb-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="aedeb-161">对于启用了 Lync 的用户和使用推送通知服务或 Apple 推送通知服务的 Microsoft Lync 移动客户端的所有 SIP 域，请按需重复执行此操作。</span><span class="sxs-lookup"><span data-stu-id="aedeb-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aedeb-162">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="aedeb-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="aedeb-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="aedeb-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="aedeb-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="aedeb-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="aedeb-165">合并边缘内部接口</span><span class="sxs-lookup"><span data-stu-id="aedeb-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

