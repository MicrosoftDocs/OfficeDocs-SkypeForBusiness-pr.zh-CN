---
title: Lync Server 2013： DNS 摘要-扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 448cbb0834c8ad7dee983fd6dcd56922cbb030d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="6cd82-102">Lync Server 2013 中的 DNS 摘要-扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="6cd82-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cd82-103">_**上次修改的主题：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="6cd82-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="6cd82-104">与证书和端口相比，远程访问 Lync Server 2013 的 DNS 记录要求相当简单。</span><span class="sxs-lookup"><span data-stu-id="6cd82-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="6cd82-105">此外，许多记录是可选的，具体取决于如何配置运行 Lync 2013 的客户端以及是否启用联盟。</span><span class="sxs-lookup"><span data-stu-id="6cd82-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="6cd82-106">有关 Lync 2013 DNS 要求的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6cd82-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="6cd82-107">有关如何配置 Lync 2013 客户端的自动配置的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "自动配置，而不拆分大脑 dns" 部分。</span><span class="sxs-lookup"><span data-stu-id="6cd82-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="6cd82-108">下表包含 DNS 记录的摘要，支持单个合并边缘拓扑图中显示的单个合并边缘拓扑时需要这些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="6cd82-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="6cd82-109">请注意，只有在自动配置 Lync 2013 客户端时，才需要某些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="6cd82-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="6cd82-110">如果您计划使用组策略对象（Gpo）来配置 Lync 客户端，则不需要关联的记录。</span><span class="sxs-lookup"><span data-stu-id="6cd82-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="6cd82-111">重要说明：边缘服务器网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="6cd82-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="6cd82-112">若要避免路由问题，请确认边缘服务器中至少有两个网络适配器，并且默认网关仅在与外部接口相关联的网络适配器上设置。</span><span class="sxs-lookup"><span data-stu-id="6cd82-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="6cd82-113">例如，如扩展合并边缘的扩展合并边缘方案中所示[，在 Lync Server 2013 中使用公用 IP 地址进行 DNS 负载平衡](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)，默认网关将指向外部防火墙。</span><span class="sxs-lookup"><span data-stu-id="6cd82-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="6cd82-114">您可以在每台边缘服务器中配置两个网络适配器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6cd82-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="6cd82-115">**网络适配器 1 - 节点 1（内部接口）**</span><span class="sxs-lookup"><span data-stu-id="6cd82-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="6cd82-116">分配有 172.25.33.10 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="6cd82-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="6cd82-117">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="6cd82-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="6cd82-118">确保从包含边缘内部接口的网络的路由到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="6cd82-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="6cd82-119">**网络适配器 1 - 节点 2（内部接口）**</span><span class="sxs-lookup"><span data-stu-id="6cd82-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="6cd82-120">分配有 172.25.33.11 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="6cd82-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="6cd82-121">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="6cd82-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="6cd82-122">确保从包含边缘内部接口的网络的路由到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="6cd82-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="6cd82-123">**网络适配器 2 - 节点 1（外部接口）**</span><span class="sxs-lookup"><span data-stu-id="6cd82-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="6cd82-124">向此网络适配器分配了三个专用 IP 地址，例如 131.107.155.10 for Access Edge service、131.107.155.20 for Web 会议边缘服务、131.107.155.30 for A/V Edge 服务。</span><span class="sxs-lookup"><span data-stu-id="6cd82-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="6cd82-125">访问边缘服务公用 IP 地址是主要的，默认网关设置为公用路由器（131.107.155.1）。</span><span class="sxs-lookup"><span data-stu-id="6cd82-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="6cd82-126">Web 会议边缘服务和 A/V 边缘服务专用 IP 地址是 Windows Server 中的**本地区域连接属性**的**internet 协议版本4（tcp/IPv4）** 和**INTERNET 协议版本6（tcp/IPv6）** 属性的 "**高级**" 部分中的其他 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6cd82-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6cd82-127">可以为所有三个边缘服务接口使用一个 IP 地址，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="6cd82-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="6cd82-128">尽管这样可以节省 IP 地址，但需要为每个服务使用不同端口号。</span><span class="sxs-lookup"><span data-stu-id="6cd82-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="6cd82-129">默认端口号为 443/TCP，它可确保大多数远程防火墙将允许流量通过。</span><span class="sxs-lookup"><span data-stu-id="6cd82-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="6cd82-130">如果将端口值更改为（例如）访问边缘服务的 5061/TCP，则 Web 会议边缘服务的 444/tcp 和 A/V 边缘服务的 443/TCP 可能会导致远程用户出现问题，在该用户背后的防火墙不允许通过 5061/TCP 和 444/TCP 的流量。</span><span class="sxs-lookup"><span data-stu-id="6cd82-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="6cd82-131">另外，由于能够筛选 IP 地址，因此使用三个不同的 IP 地址更便于排除故障。</span><span class="sxs-lookup"><span data-stu-id="6cd82-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="6cd82-132">**网络适配器 2 - 节点 2（外部接口）**</span><span class="sxs-lookup"><span data-stu-id="6cd82-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="6cd82-133">向此网络适配器分配了三个专用 IP 地址，例如 131.107.155.11 for Access Edge service、131.107.155.21 for Web 会议边缘服务、131.107.155.31 for A/V Edge 服务。</span><span class="sxs-lookup"><span data-stu-id="6cd82-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="6cd82-134">访问边缘服务公用 IP 地址是主要的，默认网关设置为公用路由器（131.107.155.1）。</span><span class="sxs-lookup"><span data-stu-id="6cd82-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="6cd82-135">Web 会议边缘服务和 A/V 边缘服务专用 IP 地址是 Windows Server 中的**本地区域连接属性**的**internet 协议版本4（tcp/IPv4）** 和**INTERNET 协议版本6（tcp/IPv6）** 属性的 "**高级**" 部分中的其他 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6cd82-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6cd82-136">配置具有两个网络适配器的边缘服务器是两个选项之一。</span><span class="sxs-lookup"><span data-stu-id="6cd82-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="6cd82-137">另一种方法是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。</span><span class="sxs-lookup"><span data-stu-id="6cd82-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="6cd82-138">此选项的主要优点是，每个边缘服务器服务都有不同的网络适配器，并且在需要故障排除时有可能更简单的数据收集</span><span class="sxs-lookup"><span data-stu-id="6cd82-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="6cd82-139">扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）所需的 DNS 记录（示例）</span><span class="sxs-lookup"><span data-stu-id="6cd82-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cd82-140">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="6cd82-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="6cd82-141">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="6cd82-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="6cd82-142">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="6cd82-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="6cd82-143">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="6cd82-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cd82-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="6cd82-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6cd82-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cd82-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-146">131.107.155.10 和 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="6cd82-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="6cd82-147">访问边缘服务外部接口（Contoso）根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</span><span class="sxs-lookup"><span data-stu-id="6cd82-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd82-148">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="6cd82-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6cd82-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cd82-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-150">131.107.155.20 和 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="6cd82-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="6cd82-151">Web 会议边缘服务外部接口</span><span class="sxs-lookup"><span data-stu-id="6cd82-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd82-152">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="6cd82-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6cd82-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cd82-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-154">131.107.155.30 和 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="6cd82-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="6cd82-155">A/V 边缘服务外部接口</span><span class="sxs-lookup"><span data-stu-id="6cd82-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd82-156">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="6cd82-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="6cd82-157">_sip _tls .com</span><span class="sxs-lookup"><span data-stu-id="6cd82-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cd82-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-159">访问边缘服务外部接口。</span><span class="sxs-lookup"><span data-stu-id="6cd82-159">Access Edge service external interface.</span></span> <span data-ttu-id="6cd82-160">将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作是必需的。</span><span class="sxs-lookup"><span data-stu-id="6cd82-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="6cd82-161">根据需要为启用 Lync 的用户的所有 SIP 域重复使用。</span><span class="sxs-lookup"><span data-stu-id="6cd82-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd82-162">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="6cd82-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="6cd82-163">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="6cd82-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cd82-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-165">访问边缘服务外部接口，联合合作伙伴（称为 "允许的 SIP 域"）的自动 DNS 发现需要此外部接口（在以前的版本中称为 "增强联盟"）。</span><span class="sxs-lookup"><span data-stu-id="6cd82-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="6cd82-166">根据需要为启用 Lync 的用户的所有 SIP 域重复使用</span><span class="sxs-lookup"><span data-stu-id="6cd82-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd82-167">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="6cd82-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6cd82-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6cd82-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6cd82-169">172.25.33.10 和 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="6cd82-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="6cd82-170">合并边缘内部接口</span><span class="sxs-lookup"><span data-stu-id="6cd82-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="6cd82-171">联盟需要的记录</span><span class="sxs-lookup"><span data-stu-id="6cd82-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cd82-172">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="6cd82-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="6cd82-173">FQDN</span><span class="sxs-lookup"><span data-stu-id="6cd82-173">FQDN</span></span></th>
<th><span data-ttu-id="6cd82-174">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="6cd82-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="6cd82-175">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="6cd82-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cd82-176">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="6cd82-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="6cd82-177">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="6cd82-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cd82-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-179">SIP 访问边缘服务外部接口，对其他潜在联合合作伙伴的联合身份验证的自动 DNS 发现是必需的，也称为 "允许的 SIP 域" （在以前的版本中称为 "增强联盟"）。</span><span class="sxs-lookup"><span data-stu-id="6cd82-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="6cd82-180">对于启用了 Lync 的用户和使用推送通知服务或 Apple 推送通知服务的 Microsoft Lync 移动客户端的所有 SIP 域，请按需重复执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6cd82-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="6cd82-181">可扩展消息传递和状态协议的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="6cd82-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cd82-182">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="6cd82-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="6cd82-183">FQDN</span><span class="sxs-lookup"><span data-stu-id="6cd82-183">FQDN</span></span></th>
<th><span data-ttu-id="6cd82-184">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="6cd82-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="6cd82-185">映射目标/注释</span><span class="sxs-lookup"><span data-stu-id="6cd82-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cd82-186">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="6cd82-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="6cd82-187">_xmpp-_tcp .com</span><span class="sxs-lookup"><span data-stu-id="6cd82-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cd82-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6cd82-189">访问边缘服务或边缘池上的 XMPP 代理外部接口。根据需要对启用了 Lync 的用户使用通过全局策略、用户所在的网站策略或应用于 XMPP 联系人的外部访问策略的配置，对所有内部 SIP 域重复此操作。启用了 Lync 的用户。</span><span class="sxs-lookup"><span data-stu-id="6cd82-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="6cd82-190">还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。</span><span class="sxs-lookup"><span data-stu-id="6cd82-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="6cd82-191">有关其他详细信息，请参阅<strong>另请参阅</strong>主题中的主题</span><span class="sxs-lookup"><span data-stu-id="6cd82-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd82-192">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="6cd82-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6cd82-193">xmpp.contoso.com（举例）</span><span class="sxs-lookup"><span data-stu-id="6cd82-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="6cd82-194">边缘服务器或边缘池托管 XMPP 代理上的访问边缘服务的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="6cd82-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="6cd82-195">指向承载 XMPP 代理服务的访问边缘服务或边缘池。</span><span class="sxs-lookup"><span data-stu-id="6cd82-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="6cd82-196">一般而言，您创建的 SRV 记录将指向此主机（A 或 AAAA）记录</span><span class="sxs-lookup"><span data-stu-id="6cd82-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

