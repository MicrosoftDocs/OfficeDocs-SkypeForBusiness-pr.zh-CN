---
title: Lync Server 2013： DNS 摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 158dfa2954f331b4dce2407cb3bbee223f8e78ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="5f581-102">Lync Server 2013 中的 DNS 摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="5f581-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f581-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5f581-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="5f581-104">与证书和端口相比，远程访问 Lync Server 2013 的 DNS 记录要求相当简单。</span><span class="sxs-lookup"><span data-stu-id="5f581-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="5f581-105">此外，许多记录是可选的，具体取决于如何配置运行 Lync 2013 的客户端以及是否启用联盟。</span><span class="sxs-lookup"><span data-stu-id="5f581-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="5f581-106">有关 Lync 2013 DNS 要求的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f581-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="5f581-107">有关如何配置 Lync 2013 客户端的自动配置的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "自动配置，而不拆分大脑 dns" 部分。</span><span class="sxs-lookup"><span data-stu-id="5f581-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="5f581-108">下表包含 DNS 记录的摘要，支持单个合并边缘拓扑图中显示的单个合并边缘拓扑时需要这些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="5f581-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="5f581-109">请注意，只有在自动配置 Lync 2013 客户端时，才需要某些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="5f581-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="5f581-110">如果您计划使用组策略对象（Gpo）来配置 Lync 客户端，则不需要关联的记录。</span><span class="sxs-lookup"><span data-stu-id="5f581-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="5f581-111">重要说明：边缘服务器网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="5f581-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="5f581-112">若要避免路由问题，请确认边缘服务器中至少有两个网络适配器，并且默认网关仅在与外部接口相关联的网络适配器上设置。</span><span class="sxs-lookup"><span data-stu-id="5f581-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="5f581-113">例如，如扩展的合并边缘方案图中所示，[扩展的合并边缘（使用 Lync Server 2013 中的 NAT 通过专用 IP 地址进行 DNS 负载平衡](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)），默认网关将指向外部防火墙。</span><span class="sxs-lookup"><span data-stu-id="5f581-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="5f581-114">您可以在每台边缘服务器中配置两个网络适配器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f581-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="5f581-115">**网络适配器 1 - 节点 1（内部接口）**</span><span class="sxs-lookup"><span data-stu-id="5f581-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="5f581-116">分配有 172.25.33.10 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="5f581-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="5f581-117">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="5f581-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="5f581-118">确保从包含边缘内部接口的网络的路由到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="5f581-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="5f581-119">**网络适配器 1 - 节点 2（内部接口）**</span><span class="sxs-lookup"><span data-stu-id="5f581-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="5f581-120">分配有 172.25.33.11 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="5f581-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="5f581-121">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="5f581-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="5f581-122">确保从包含边缘内部接口的网络的路由到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="5f581-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="5f581-123">**网络适配器 2 - 节点 1（外部接口）**</span><span class="sxs-lookup"><span data-stu-id="5f581-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="5f581-124">三个私有 IP 地址将分配到此网络适配器，例如为访问边缘分配 10.45.16.10，为 Web 会议边缘分配 10.45.16.20，为 AV 边缘分配 10.45.16.30。</span><span class="sxs-lookup"><span data-stu-id="5f581-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f581-p104">可以为所有三个边缘服务接口使用一个 IP 地址，但不建议这样做。尽管这样可以节省 IP 地址，但需要为每个服务使用不同端口号。默认端口号为 443/TCP，它可确保大多数远程防火墙会允许流量。对于远程用户（支持这些用户的防火墙不允许 5061/TCP 和 444/TCP 上的流量），为访问边缘将端口值更改为（比如）5061/TCP、为 Web 会议边缘将端口值更改为 444/TCP 以及为 AV 边缘将端口值更改为 443/TCP 可能导致问题。另外，由于能够筛选 IP 地址，因此三个不同的 IP 地址更便于排除故障。</span><span class="sxs-lookup"><span data-stu-id="5f581-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="5f581-130">访问边缘公共 IP 地址是默认网关设置为集成路由器的主要 IP 地址 (10.45.16.1)。</span><span class="sxs-lookup"><span data-stu-id="5f581-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="5f581-131">Web 会议和 A/V 边缘私有 IP 地址是 Windows Server 中“局域网连接属性”\*\*\*\* 的“Internet 协议版本 4 (TCP/IPv4)”\*\*\*\* 和“Internet 协议版本 6 (TCP/IPv6)”\*\*\*\* 属性的“高级”\*\*\*\* 部分中的其他 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5f581-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="5f581-132">**网络适配器 2 - 节点 2（外部接口）**</span><span class="sxs-lookup"><span data-stu-id="5f581-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="5f581-133">三个私有 IP 地址将分配到此网络适配器，例如为访问边缘分配 10.45.16.11，为 Web 会议边缘分配 10.45.16.21，为 AV 边缘分配 10.45.16.31。</span><span class="sxs-lookup"><span data-stu-id="5f581-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="5f581-134">访问边缘公共 IP 地址是默认网关设置为集成路由器的主要 IP 地址 (10.45.16.1)。</span><span class="sxs-lookup"><span data-stu-id="5f581-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="5f581-135">Web 会议和 A/V 边缘私有 IP 地址是 Windows Server 中“局域网连接属性”\*\*\*\* 的“Internet 协议版本 4 (TCP/IPv4)”\*\*\*\* 和“Internet 协议版本 6 (TCP/IPv6)”\*\*\*\* 属性的“高级”\*\*\*\* 部分中的其他 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5f581-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5f581-136">配置具有两个网络适配器的边缘服务器是两个选项之一。</span><span class="sxs-lookup"><span data-stu-id="5f581-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="5f581-137">另一种方法是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。</span><span class="sxs-lookup"><span data-stu-id="5f581-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="5f581-138">此选项的主要优点是，每个边缘服务器服务都有不同的网络适配器，并且在需要故障排除时有可能更简单的数据收集</span><span class="sxs-lookup"><span data-stu-id="5f581-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="5f581-139">扩展的合并边缘、使用 NAT（举例）通过私有 IP 地址实现 DNS 负载平衡所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="5f581-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f581-140">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="5f581-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5f581-141">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="5f581-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="5f581-142">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="5f581-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="5f581-143">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="5f581-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f581-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5f581-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5f581-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f581-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-146">131.107.155.10 和 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="5f581-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="5f581-147">访问边缘外部接口 (Contoso) 根据需要为启用 Lync 的用户的所有 SIP 域重复使用</span><span class="sxs-lookup"><span data-stu-id="5f581-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f581-148">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5f581-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5f581-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f581-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-150">131.107.155.20 和 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="5f581-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="5f581-151">Web 会议边缘外部接口</span><span class="sxs-lookup"><span data-stu-id="5f581-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f581-152">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5f581-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5f581-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f581-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-154">131.107.155.30 和 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="5f581-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="5f581-155">A/V 边缘外部接口</span><span class="sxs-lookup"><span data-stu-id="5f581-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f581-156">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="5f581-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="5f581-157">_sip _tls .com</span><span class="sxs-lookup"><span data-stu-id="5f581-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f581-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-159">访问边缘外部接口。</span><span class="sxs-lookup"><span data-stu-id="5f581-159">Access Edge external interface.</span></span> <span data-ttu-id="5f581-160">将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作是必需的。</span><span class="sxs-lookup"><span data-stu-id="5f581-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="5f581-161">根据需要为启用 Lync 的用户的所有 SIP 域重复使用。</span><span class="sxs-lookup"><span data-stu-id="5f581-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f581-162">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="5f581-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="5f581-163">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="5f581-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f581-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-p107">SIP 访问边缘外部接口。用于实现称为“允许的 SIP 域”的联盟伙伴（在以前版本中称为增强联盟）的自动 DNS 发现。根据需要为启用 Lync 的用户的所有 SIP 域重复使用</span><span class="sxs-lookup"><span data-stu-id="5f581-p107">SIP Access Edge external interface. Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases). Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f581-168">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5f581-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5f581-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5f581-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5f581-170">172.25.33.10 和 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="5f581-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="5f581-171">合并边缘内部接口</span><span class="sxs-lookup"><span data-stu-id="5f581-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="5f581-172">联盟需要的记录</span><span class="sxs-lookup"><span data-stu-id="5f581-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f581-173">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="5f581-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5f581-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="5f581-174">FQDN</span></span></th>
<th><span data-ttu-id="5f581-175">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="5f581-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="5f581-176">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="5f581-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f581-177">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="5f581-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="5f581-178">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="5f581-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f581-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-180">用于实现与其他潜在联盟伙伴的联盟的自动 DNS 发现的 SIP 访问边缘外部接口，称为“允许的 SIP 域”（在以前版本中称为增强联盟）。必要时对带有启用了 Lync 的用户的所有 SIP 域重复</span><span class="sxs-lookup"><span data-stu-id="5f581-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="5f581-181">移动性和推送通知交换所需要此 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="5f581-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="5f581-182">DNS 摘要 - 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="5f581-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f581-183">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="5f581-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5f581-184">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="5f581-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="5f581-185">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="5f581-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="5f581-186">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="5f581-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f581-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5f581-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5f581-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f581-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-189">访问边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="5f581-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5f581-190">访问边缘外部接口 (Contoso)。必要时对带有启用了 Lync 的用户的所有 SIP 域重复</span><span class="sxs-lookup"><span data-stu-id="5f581-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="5f581-191">可扩展消息传递和状态协议的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="5f581-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f581-192">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="5f581-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5f581-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="5f581-193">FQDN</span></span></th>
<th><span data-ttu-id="5f581-194">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="5f581-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="5f581-195">映射目标/注释</span><span class="sxs-lookup"><span data-stu-id="5f581-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f581-196">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="5f581-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="5f581-197">_xmpp-_tcp .com</span><span class="sxs-lookup"><span data-stu-id="5f581-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f581-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5f581-199">访问边缘服务或边缘池上的 XMPP 代理外部接口。根据需要对启用了 Lync 的用户使用通过全局策略、用户所在的网站策略或应用于 XMPP 联系人的外部访问策略的配置，对所有内部 SIP 域重复此操作。启用了 Lync 的用户。</span><span class="sxs-lookup"><span data-stu-id="5f581-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="5f581-200">还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。</span><span class="sxs-lookup"><span data-stu-id="5f581-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="5f581-201">有关其他详细信息，请参阅<strong>另请参阅</strong>主题中的主题</span><span class="sxs-lookup"><span data-stu-id="5f581-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f581-202">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="5f581-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5f581-203">xmpp.contoso.com（举例）</span><span class="sxs-lookup"><span data-stu-id="5f581-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="5f581-204">边缘服务器或边缘池托管 XMPP 代理上的访问边缘服务的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="5f581-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="5f581-205">指向承载 XMPP 代理服务的访问边缘服务或边缘池。</span><span class="sxs-lookup"><span data-stu-id="5f581-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="5f581-206">一般而言，您创建的 SRV 记录将指向此主机（A 或 AAAA）记录</span><span class="sxs-lookup"><span data-stu-id="5f581-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

