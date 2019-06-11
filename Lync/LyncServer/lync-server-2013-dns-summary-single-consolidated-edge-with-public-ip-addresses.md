---
title: DNS 摘要 - 使用公用 IP 地址的单一合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50aae14309e55919eb3f65560cd7cd0e7f1b1283
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="610b3-102">Lync Server 2013 中的证书摘要 - 使用公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="610b3-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="610b3-103">_**主题上次修改时间:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="610b3-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="610b3-104">与证书和端口的远程2013访问的 DNS 记录要求相当直接。</span><span class="sxs-lookup"><span data-stu-id="610b3-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="610b3-105">此外, 许多记录是可选的, 具体取决于您配置运行 Lync 2013 的客户端的方式以及是否启用联盟。</span><span class="sxs-lookup"><span data-stu-id="610b3-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="610b3-106">有关 Lync 2013 DNS 要求的详细信息, 请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="610b3-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="610b3-107">有关运行 Lync 2013 的客户端的自动配置的详细信息 (如果未配置分裂大脑 DNS), 请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "没有分裂的 dns 所需的自动配置"。</span><span class="sxs-lookup"><span data-stu-id="610b3-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="610b3-108">下表列出了支持单个统一边缘拓扑图中所示的单个统一边缘拓扑所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="610b3-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="610b3-109">请注意, 只有在自动配置 Lync 2013 和 Lync 2010 客户端时, 才需要某些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="610b3-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="610b3-110">如果你计划使用组策略对象 (Gpo) 配置 Lync 客户端, 则不需要关联的自动配置记录。</span><span class="sxs-lookup"><span data-stu-id="610b3-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="610b3-111">重要提示: Edge 服务器网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="610b3-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="610b3-112">为避免路由问题, 请验证边缘服务器中是否至少有两个网络适配器, 并且是否仅在与外部接口关联的网络适配器上设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="610b3-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="610b3-113">例如, 如在[Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)中具有公共 ip 地址的单个统一边缘拓扑图中显示的单个统一边缘拓扑中, 默认网关将指向 Internet 外围的外部路由器或可提供公共 IP 地址的防火墙。</span><span class="sxs-lookup"><span data-stu-id="610b3-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="610b3-114">Edge 服务器接口的网络关系是路由关系, 而不是 NAT 关系。</span><span class="sxs-lookup"><span data-stu-id="610b3-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="610b3-115">你可以在 Edge 服务器中配置两个网络适配器, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="610b3-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="610b3-116">**网络适配器 1 (内部接口)**</span><span class="sxs-lookup"><span data-stu-id="610b3-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="610b3-117">已分配172.25.33.10 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="610b3-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="610b3-118">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="610b3-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="610b3-119">请确保从网络中有一个路由, 该网络包含指向运行 Lync Server 2013 或 Lync Server 2013 客户端 (例如从172.25.33.0 到 192.168.10.0) 的服务器的任何网络的边缘内部接口。</span><span class="sxs-lookup"><span data-stu-id="610b3-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="610b3-120">**网络适配器 2 (外部接口)**</span><span class="sxs-lookup"><span data-stu-id="610b3-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="610b3-121">将三个公共 IP 地址分配给此网络适配器, 例如131.107.155.10 用于访问边缘, 131.107.155.20 用于 Web 会议边缘, 131.107.155.30 AV 边缘。</span><span class="sxs-lookup"><span data-stu-id="610b3-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="610b3-122">虽然不推荐使用所有三个边缘服务接口的单个 IP 地址, 但也有可能。</span><span class="sxs-lookup"><span data-stu-id="610b3-122">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="610b3-123">虽然这会保存 IP 地址, 但它需要每个服务的不同端口号。</span><span class="sxs-lookup"><span data-stu-id="610b3-123">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="610b3-124">默认端口号为 443/TCP, 这可确保大多数远程防火墙都允许流量。</span><span class="sxs-lookup"><span data-stu-id="610b3-124">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="610b3-125">将端口值更改为 (例如) 访问边缘的 5061/tcp, 对于 Web 会议边缘的 444/tcp 和 AV 边缘的 443/TCP 可能会导致远程用户出现问题, 在这种情况下, 其背后的防火墙不允许通过 5061/TCP 和 444/TCP 的流量。</span><span class="sxs-lookup"><span data-stu-id="610b3-125">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="610b3-126">此外, 由于能够筛选 IP 地址, 三个不同的 IP 地址使疑难解答变得更轻松。</span><span class="sxs-lookup"><span data-stu-id="610b3-126">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="610b3-127">访问边缘公共 IP 地址是主要的, 将默认网关设置为公共路由器 (131.107.155.1)。</span><span class="sxs-lookup"><span data-stu-id="610b3-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="610b3-128">Web 会议和 A/V 边缘公共 IP 地址是**Internet 协议版本 4 (tcp/IPv4)** 和**internet 协议版本 6 (tcp/IPv6)** 在本地区域的属性的 "**高级**" 部分中的附加 ip 地址\*\*\*\* Windows Server 中的连接属性。</span><span class="sxs-lookup"><span data-stu-id="610b3-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="610b3-129">配置具有两个网络适配器的 Edge 服务器是两个选项之一。</span><span class="sxs-lookup"><span data-stu-id="610b3-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="610b3-130">另一种选择是将一个网络适配器用于内部端, 将三个网络适配器用于边缘服务器的外部端。</span><span class="sxs-lookup"><span data-stu-id="610b3-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="610b3-131">此选项的主要优点是每个边缘服务器服务有一个不同的网络适配器, 并且在需要故障排除时有可能更简洁的数据收集</span><span class="sxs-lookup"><span data-stu-id="610b3-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="610b3-132">具有公共 IP 地址的单个统一边缘所需的 DNS 记录 (示例)</span><span class="sxs-lookup"><span data-stu-id="610b3-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="610b3-133">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="610b3-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="610b3-134">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="610b3-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="610b3-135">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="610b3-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="610b3-136">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="610b3-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="610b3-137">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="610b3-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="610b3-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="610b3-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="610b3-140">允许启用 Lync 的用户的所有 SIP 域的访问边缘外部接口 (Contoso) 都有必要重复</span><span class="sxs-lookup"><span data-stu-id="610b3-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="610b3-141">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="610b3-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="610b3-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="610b3-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="610b3-144">网络会议边缘外部界面</span><span class="sxs-lookup"><span data-stu-id="610b3-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="610b3-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="610b3-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="610b3-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="610b3-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="610b3-148">A/V 边缘外部接口</span><span class="sxs-lookup"><span data-stu-id="610b3-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="610b3-149">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="610b3-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="610b3-150">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-152">访问边缘外部接口。</span><span class="sxs-lookup"><span data-stu-id="610b3-152">Access Edge external interface.</span></span> <span data-ttu-id="610b3-153">需要将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作。</span><span class="sxs-lookup"><span data-stu-id="610b3-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="610b3-154">根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作。</span><span class="sxs-lookup"><span data-stu-id="610b3-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="610b3-155">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="610b3-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="610b3-156">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-158">SIP 访问边缘外部接口, 用于自动 DNS 发现称为 "允许的 SIP 域" 的联盟伙伴 (在以前的版本中称为 "增强联盟")。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</span><span class="sxs-lookup"><span data-stu-id="610b3-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="610b3-159">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="610b3-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="610b3-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="610b3-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="610b3-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="610b3-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="610b3-162">统一边缘内部接口</span><span class="sxs-lookup"><span data-stu-id="610b3-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="610b3-163">使用<EM>.net</EM>扩展或<EM>.com</EM>扩展名显示上表中列出的记录, 以突出显示要在不使用分裂的 DNS 时需要驻留的区域。</span><span class="sxs-lookup"><span data-stu-id="610b3-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="610b3-164">如果使用的是分裂大脑 DNS, 则所有记录将位于同一区域中, 唯一的区别是它们是否位于内部或外部版本中。</span><span class="sxs-lookup"><span data-stu-id="610b3-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="610b3-165">有关详细信息, 请参阅<A href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</A>中的 "分裂大脑 dns"。</span><span class="sxs-lookup"><span data-stu-id="610b3-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="610b3-166">联盟所需的记录</span><span class="sxs-lookup"><span data-stu-id="610b3-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="610b3-167">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="610b3-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="610b3-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="610b3-168">FQDN</span></span></th>
<th><span data-ttu-id="610b3-169">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="610b3-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="610b3-170">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="610b3-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="610b3-171">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="610b3-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="610b3-172">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-174">SIP 访问边缘外部接口, 将联合身份验证自动 DNS 发现到其他潜在的联合合作伙伴, 并称为 "允许的 SIP 域" (在以前的版本中称为增强联盟)。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</span><span class="sxs-lookup"><span data-stu-id="610b3-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="610b3-175">移动和推送通知交换所需要此 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="610b3-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="610b3-176">可扩展消息和状态协议的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="610b3-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="610b3-177">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="610b3-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="610b3-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="610b3-178">FQDN</span></span></th>
<th><span data-ttu-id="610b3-179">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="610b3-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="610b3-180">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="610b3-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="610b3-181">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="610b3-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="610b3-182">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="610b3-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="610b3-184">"访问边缘服务" 或 "边缘池" 上的 XMPP 代理外部接口。对于启用了 Lync 的用户, 通过全局策略、用户所在的网站策略或应用了用户策略的用户策略, 可对所有内部 SIP 域进行必要的操作, 并允许使用启用了 Lync 的用户使用 XMPP 联系人。启用 Lync 的用户。</span><span class="sxs-lookup"><span data-stu-id="610b3-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="610b3-185">还必须在 XMPP 联盟合作伙伴策略中配置允许的 XMPP 域。</span><span class="sxs-lookup"><span data-stu-id="610b3-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="610b3-186">有关其他详细信息, 请参阅<strong>另请参阅</strong>中的主题</span><span class="sxs-lookup"><span data-stu-id="610b3-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="610b3-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="610b3-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="610b3-188">xmpp.contoso.com (例如)</span><span class="sxs-lookup"><span data-stu-id="610b3-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="610b3-189">边缘服务器上的访问边缘服务的 IP 地址或托管 XMPP 代理的边缘池的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="610b3-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="610b3-190">指向托管 XMPP 代理服务的访问边缘服务或边缘池。</span><span class="sxs-lookup"><span data-stu-id="610b3-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="610b3-191">通常, 你创建的 SRV 记录将指向此主机 (A 或 AAAA) 记录</span><span class="sxs-lookup"><span data-stu-id="610b3-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

