---
title: Lync Server 2013：DNS 摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）
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
ms.openlocfilehash: 6a7836a8d9ce998a8de9185de7aeb12eb088f190
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="39aa2-102">Lync Server 2013 中的 DNS 摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="39aa2-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39aa2-103">_**主题上次修改时间：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="39aa2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="39aa2-104">与证书和端口的远程2013访问的 DNS 记录要求相当直接。</span><span class="sxs-lookup"><span data-stu-id="39aa2-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="39aa2-105">此外，许多记录是可选的，具体取决于您配置运行 Lync 2013 的客户端的方式以及是否启用联盟。</span><span class="sxs-lookup"><span data-stu-id="39aa2-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="39aa2-106">有关 Lync 2013 DNS 要求的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39aa2-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="39aa2-107">有关配置 Lync 2013 客户端的自动配置的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)时，请参阅 "没有拆分大脑 Dns 的自动配置" 部分。</span><span class="sxs-lookup"><span data-stu-id="39aa2-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="39aa2-108">下表列出了支持单个统一边缘拓扑图中所示的单个统一边缘拓扑所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="39aa2-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="39aa2-109">请注意，仅当自动配置 Lync 2013 客户端时，才需要某些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="39aa2-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="39aa2-110">如果你计划使用组策略对象（Gpo）配置 Lync 客户端，则不需要关联的记录。</span><span class="sxs-lookup"><span data-stu-id="39aa2-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="39aa2-111">重要提示： Edge 服务器网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="39aa2-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="39aa2-112">为避免路由问题，请验证边缘服务器中是否至少有两个网络适配器，并且是否仅在与外部接口关联的网络适配器上设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="39aa2-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="39aa2-113">例如，如缩放后的合并边缘方案图中所示，在[Lync Server 2013 中使用 NAT 进行 DNS 负载平衡](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)，默认网关将指向外部防火墙。</span><span class="sxs-lookup"><span data-stu-id="39aa2-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="39aa2-114">可以在每个边缘服务器中配置两个网络适配器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="39aa2-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="39aa2-115">**网络适配器 1-节点1（内部接口）**</span><span class="sxs-lookup"><span data-stu-id="39aa2-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="39aa2-116">已分配172.25.33.10 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="39aa2-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="39aa2-117">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="39aa2-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="39aa2-118">请确保从网络中有一个路由，该网络包含指向运行 Lync Server 2013 或 Lync Server 2013 客户端（例如从172.25.33.0 到192.168.10.0）的服务器的任何网络的边缘内部接口。</span><span class="sxs-lookup"><span data-stu-id="39aa2-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="39aa2-119">**网络适配器 1-节点2（内部接口）**</span><span class="sxs-lookup"><span data-stu-id="39aa2-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="39aa2-120">已分配172.25.33.11 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="39aa2-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="39aa2-121">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="39aa2-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="39aa2-122">请确保从网络中有一个路由，该网络包含指向运行 Lync Server 2013 或 Lync Server 2013 客户端（例如从172.25.33.0 到192.168.10.0）的服务器的任何网络的边缘内部接口。</span><span class="sxs-lookup"><span data-stu-id="39aa2-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="39aa2-123">**网络适配器2节点1（外部接口）**</span><span class="sxs-lookup"><span data-stu-id="39aa2-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="39aa2-124">将三个专用 IP 地址分配给此网络适配器，例如10.45.16.10 用于访问边缘，10.45.16.20 用于 Web 会议边缘，10.45.16.30 AV 边缘。</span><span class="sxs-lookup"><span data-stu-id="39aa2-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39aa2-125">虽然不推荐使用所有三个边缘服务接口的单个 IP 地址，但也有可能。</span><span class="sxs-lookup"><span data-stu-id="39aa2-125">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="39aa2-126">虽然这会保存 IP 地址，但它需要每个服务的不同端口号。</span><span class="sxs-lookup"><span data-stu-id="39aa2-126">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="39aa2-127">默认端口号为 443/TCP，这可确保大多数远程防火墙都允许流量。</span><span class="sxs-lookup"><span data-stu-id="39aa2-127">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="39aa2-128">将端口值更改为（例如）访问边缘的 5061/tcp，对于 Web 会议边缘的 444/tcp 和 AV 边缘的 443/TCP 可能会导致远程用户出现问题，在这种情况下，其背后的防火墙不允许通过 5061/TCP 和 444/TCP 的流量。</span><span class="sxs-lookup"><span data-stu-id="39aa2-128">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="39aa2-129">此外，由于能够筛选 IP 地址，三个不同的 IP 地址使疑难解答变得更轻松。</span><span class="sxs-lookup"><span data-stu-id="39aa2-129">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="39aa2-130">访问边缘公共 IP 地址是主要的，将默认网关设置为集成路由器（10.45.16.1）。</span><span class="sxs-lookup"><span data-stu-id="39aa2-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="39aa2-131">Web 会议和 A/V 边缘专用 IP 地址是 Windows Server 中的**Internet 协议版本4（tcp/IPv4）** 和**internet 协议版本6（tcp/IPv6）** 在 Windows Server 中的**本地连接属性**的 "**高级**" 部分中的其他 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="39aa2-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="39aa2-132">**网络适配器2节点2（外部接口）**</span><span class="sxs-lookup"><span data-stu-id="39aa2-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="39aa2-133">将三个专用 IP 地址分配给此网络适配器，例如10.45.16.11 用于访问边缘，10.45.16.21 用于 Web 会议边缘，10.45.16.31 AV 边缘。</span><span class="sxs-lookup"><span data-stu-id="39aa2-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="39aa2-134">访问边缘公共 IP 地址是主要的，将默认网关设置为集成路由器（10.45.16.1）。</span><span class="sxs-lookup"><span data-stu-id="39aa2-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="39aa2-135">Web 会议和 A/V 边缘专用 IP 地址是 Windows Server 中的**Internet 协议版本4（tcp/IPv4）** 和**internet 协议版本6（tcp/IPv6）** 在 Windows Server 中的**本地连接属性**的 "**高级**" 部分中的其他 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="39aa2-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="39aa2-136">配置具有两个网络适配器的 Edge 服务器是两个选项之一。</span><span class="sxs-lookup"><span data-stu-id="39aa2-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="39aa2-137">另一种选择是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。</span><span class="sxs-lookup"><span data-stu-id="39aa2-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="39aa2-138">此选项的主要优点是每个边缘服务器服务有一个不同的网络适配器，并且在需要故障排除时有可能更简洁的数据收集</span><span class="sxs-lookup"><span data-stu-id="39aa2-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="39aa2-139">缩放后的合并边缘、使用 NAT 使用专用 IP 地址的 DNS 负载平衡（示例）所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="39aa2-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39aa2-140">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="39aa2-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="39aa2-141">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="39aa2-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="39aa2-142">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="39aa2-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="39aa2-143">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="39aa2-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39aa2-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="39aa2-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="39aa2-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-146">131.107.155.10 和 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="39aa2-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="39aa2-147">允许启用 Lync 的用户的所有 SIP 域的访问边缘外部接口（Contoso）都有必要重复</span><span class="sxs-lookup"><span data-stu-id="39aa2-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39aa2-148">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="39aa2-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="39aa2-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-150">131.107.155.20 和 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="39aa2-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="39aa2-151">网络会议边缘外部界面</span><span class="sxs-lookup"><span data-stu-id="39aa2-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39aa2-152">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="39aa2-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="39aa2-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-154">131.107.155.30 和 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="39aa2-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="39aa2-155">A/V 边缘外部接口</span><span class="sxs-lookup"><span data-stu-id="39aa2-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39aa2-156">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="39aa2-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="39aa2-157">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-159">访问边缘外部接口。</span><span class="sxs-lookup"><span data-stu-id="39aa2-159">Access Edge external interface.</span></span> <span data-ttu-id="39aa2-160">需要将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作。</span><span class="sxs-lookup"><span data-stu-id="39aa2-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="39aa2-161">根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作。</span><span class="sxs-lookup"><span data-stu-id="39aa2-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39aa2-162">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="39aa2-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="39aa2-163">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-165">SIP 访问边缘外部接口。</span><span class="sxs-lookup"><span data-stu-id="39aa2-165">SIP Access Edge external interface.</span></span> <span data-ttu-id="39aa2-166">对称为 "允许的 SIP 域" 的联盟合作伙伴自动 DNS 发现所必需（在以前版本中称为 "增强联盟"）。</span><span class="sxs-lookup"><span data-stu-id="39aa2-166">Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="39aa2-167">根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</span><span class="sxs-lookup"><span data-stu-id="39aa2-167">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39aa2-168">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="39aa2-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="39aa2-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="39aa2-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="39aa2-170">172.25.33.10 和 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="39aa2-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="39aa2-171">统一边缘内部接口</span><span class="sxs-lookup"><span data-stu-id="39aa2-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="39aa2-172">联盟所需的记录</span><span class="sxs-lookup"><span data-stu-id="39aa2-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39aa2-173">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="39aa2-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="39aa2-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="39aa2-174">FQDN</span></span></th>
<th><span data-ttu-id="39aa2-175">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="39aa2-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="39aa2-176">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="39aa2-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39aa2-177">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="39aa2-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="39aa2-178">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-180">SIP 访问边缘外部接口，将联合身份验证自动 DNS 发现到其他潜在的联合合作伙伴，并称为 "允许的 SIP 域" （在以前的版本中称为增强联盟）。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</span><span class="sxs-lookup"><span data-stu-id="39aa2-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="39aa2-181">移动和推送通知交换所需要此 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="39aa2-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="39aa2-182">DNS 摘要-公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="39aa2-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39aa2-183">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="39aa2-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="39aa2-184">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="39aa2-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="39aa2-185">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="39aa2-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="39aa2-186">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="39aa2-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39aa2-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="39aa2-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="39aa2-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-189">Access Edge 服务界面</span><span class="sxs-lookup"><span data-stu-id="39aa2-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="39aa2-190">允许启用 Lync 的用户的所有 SIP 域的访问边缘外部接口（Contoso）都有必要重复</span><span class="sxs-lookup"><span data-stu-id="39aa2-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="39aa2-191">可扩展消息和状态协议的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="39aa2-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39aa2-192">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="39aa2-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="39aa2-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="39aa2-193">FQDN</span></span></th>
<th><span data-ttu-id="39aa2-194">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="39aa2-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="39aa2-195">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="39aa2-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39aa2-196">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="39aa2-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="39aa2-197">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39aa2-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="39aa2-199">"访问边缘服务" 或 "边缘池" 上的 XMPP 代理外部接口。对于启用了 Lync 的用户，通过全局策略、用户所在的网站策略或应用了用户策略的用户策略，可对所有内部 SIP 域进行必要的操作，并允许使用启用了 Lync 的用户使用 XMPP 联系人。启用 Lync 的用户。</span><span class="sxs-lookup"><span data-stu-id="39aa2-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="39aa2-200">还必须在 XMPP 联盟合作伙伴策略中配置允许的 XMPP 域。</span><span class="sxs-lookup"><span data-stu-id="39aa2-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="39aa2-201">有关其他详细信息，请参阅<strong>另请参阅</strong>中的主题</span><span class="sxs-lookup"><span data-stu-id="39aa2-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39aa2-202">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="39aa2-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="39aa2-203">xmpp.contoso.com （例如）</span><span class="sxs-lookup"><span data-stu-id="39aa2-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="39aa2-204">边缘服务器上的访问边缘服务的 IP 地址或托管 XMPP 代理的边缘池的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="39aa2-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="39aa2-205">指向托管 XMPP 代理服务的访问边缘服务或边缘池。</span><span class="sxs-lookup"><span data-stu-id="39aa2-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="39aa2-206">通常，你创建的 SRV 记录将指向此主机（A 或 AAAA）记录</span><span class="sxs-lookup"><span data-stu-id="39aa2-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

