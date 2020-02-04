---
title: DNS 摘要 - 单一合并边缘（使用 NAT 通过专用 IP 地址进行）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3276219fb4c2227cde75cf9a5d3a47616c03336d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="1196a-102">Lync Server 2013 中的 DNS 摘要 - 单一合并边缘（使用 NAT 通过专用 IP 地址进行）</span><span class="sxs-lookup"><span data-stu-id="1196a-102">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1196a-103">_**主题上次修改时间：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="1196a-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="1196a-104">与证书和端口的远程2013访问的 DNS 记录要求相当直接。</span><span class="sxs-lookup"><span data-stu-id="1196a-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="1196a-105">此外，许多记录是可选的，具体取决于您配置运行 Lync 2013 的客户端的方式以及是否启用联盟。</span><span class="sxs-lookup"><span data-stu-id="1196a-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="1196a-106">有关 Lync 2013 DNS 要求的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1196a-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1196a-107">有关运行 Lync 2013 的客户端的自动配置的详细信息（如果未配置分裂大脑 DNS），请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "没有分裂的 dns 所需的自动配置"。</span><span class="sxs-lookup"><span data-stu-id="1196a-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1196a-108">下表列出了支持单个统一边缘拓扑图中所示的单个统一边缘拓扑所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="1196a-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="1196a-109">请注意，只有在自动配置 Lync 2013 和 Lync 2010 客户端时，才需要某些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="1196a-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="1196a-110">如果你计划使用组策略对象（Gpo）配置 Lync 客户端，则不需要关联的自动配置记录。</span><span class="sxs-lookup"><span data-stu-id="1196a-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="1196a-111">重要提示： Edge 服务器网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="1196a-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="1196a-112">为避免路由问题，请验证边缘服务器中是否至少有两个网络适配器，并且是否仅在与外部接口关联的网络适配器上设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="1196a-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="1196a-113">例如，如单个统一边缘拓扑图中所示，在[Lync Server 2013 中具有专用 IP 地址和 NAT](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)的单个统一边缘拓扑图中，默认网关将指向外部防火墙（10.45.16.1）。</span><span class="sxs-lookup"><span data-stu-id="1196a-113">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="1196a-114">你可以在 Edge 服务器中配置两个网络适配器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1196a-114">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="1196a-115">**网络适配器1（内部接口）**</span><span class="sxs-lookup"><span data-stu-id="1196a-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="1196a-116">已分配172.25.33.10 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="1196a-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="1196a-117">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="1196a-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="1196a-118">请确保从网络中有一个路由，该网络包含指向运行 Lync Server 2013 或 Lync Server 2013 客户端（例如从172.25.33.0 到192.168.10.0）的服务器的任何网络的边缘内部接口。</span><span class="sxs-lookup"><span data-stu-id="1196a-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="1196a-119">**网络适配器2（外部接口）**</span><span class="sxs-lookup"><span data-stu-id="1196a-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="1196a-120">将三个专用 IP 地址分配给此网络适配器，例如10.45.16.10 用于访问边缘，10.45.16.20 用于 Web 会议边缘，10.45.16.30 AV 边缘</span><span class="sxs-lookup"><span data-stu-id="1196a-120">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1196a-121">虽然不推荐使用所有三个边缘服务接口的单个 IP 地址，但也有可能。</span><span class="sxs-lookup"><span data-stu-id="1196a-121">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="1196a-122">虽然这会保存 IP 地址，但它需要每个服务的不同端口号。</span><span class="sxs-lookup"><span data-stu-id="1196a-122">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="1196a-123">默认端口号为 443/TCP，这可确保大多数远程防火墙都允许流量。</span><span class="sxs-lookup"><span data-stu-id="1196a-123">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="1196a-124">将端口值更改为（例如）访问边缘的 5061/tcp，对于 Web 会议边缘的 444/tcp 和 AV 边缘的 443/TCP 可能会导致远程用户出现问题，在这种情况下，其背后的防火墙不允许通过 5061/TCP 和 444/TCP 的流量。</span><span class="sxs-lookup"><span data-stu-id="1196a-124">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="1196a-125">此外，由于能够筛选 IP 地址，三个不同的 IP 地址使疑难解答变得更轻松。</span><span class="sxs-lookup"><span data-stu-id="1196a-125">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="1196a-126">访问边缘 IP 地址是将默认网关设置为集成路由器（10.45.16.1）的主要地址。</span><span class="sxs-lookup"><span data-stu-id="1196a-126">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="1196a-127">辅助网络会议和 A/V 边缘 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1196a-127">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="1196a-128">配置具有两个网络适配器的 Edge 服务器是两个选项之一。</span><span class="sxs-lookup"><span data-stu-id="1196a-128">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="1196a-129">另一种选择是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。</span><span class="sxs-lookup"><span data-stu-id="1196a-129">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="1196a-130">此选项的主要优点是每个边缘服务器服务有一个不同的网络适配器，并且在需要故障排除时有可能更简洁的数据收集</span><span class="sxs-lookup"><span data-stu-id="1196a-130">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="1196a-131">使用 NAT 的专用 IP 地址的单个统一边缘所需的 DNS 记录（示例）</span><span class="sxs-lookup"><span data-stu-id="1196a-131">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1196a-132">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="1196a-132">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1196a-133">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="1196a-133">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1196a-134">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="1196a-134">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1196a-135">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="1196a-135">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1196a-136">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1196a-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1196a-137">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-137">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-138">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="1196a-138">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="1196a-139">允许启用 Lync 的用户的所有 SIP 域的访问边缘外部接口（Contoso）都有必要重复</span><span class="sxs-lookup"><span data-stu-id="1196a-139">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1196a-140">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1196a-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1196a-141">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-141">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-142">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="1196a-142">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="1196a-143">网络会议边缘外部界面</span><span class="sxs-lookup"><span data-stu-id="1196a-143">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1196a-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1196a-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1196a-145">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-145">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-146">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="1196a-146">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="1196a-147">A/V 边缘外部接口</span><span class="sxs-lookup"><span data-stu-id="1196a-147">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1196a-148">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="1196a-148">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="1196a-149">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-149">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-150">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-150">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-151">访问边缘外部接口。</span><span class="sxs-lookup"><span data-stu-id="1196a-151">Access Edge external interface.</span></span> <span data-ttu-id="1196a-152">需要将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作。</span><span class="sxs-lookup"><span data-stu-id="1196a-152">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="1196a-153">根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作。</span><span class="sxs-lookup"><span data-stu-id="1196a-153">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1196a-154">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="1196a-154">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="1196a-155">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-155">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-156">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-156">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-157">SIP 访问边缘外部接口，用于自动 DNS 发现称为 "允许的 SIP 域" 的联盟伙伴（在以前的版本中称为 "增强联盟"）。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</span><span class="sxs-lookup"><span data-stu-id="1196a-157">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1196a-158">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1196a-158">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1196a-159">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1196a-159">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1196a-160">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="1196a-160">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="1196a-161">统一边缘内部接口</span><span class="sxs-lookup"><span data-stu-id="1196a-161">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="1196a-162">使用<EM>.net</EM>扩展或<EM>.com</EM>扩展名显示上表中列出的记录，以突出显示要在不使用分裂的 DNS 时需要驻留的区域。</span><span class="sxs-lookup"><span data-stu-id="1196a-162">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="1196a-163">如果您使用的是分裂的 DNS，则所有记录都将位于同一个<EM>.com</EM>区域中，唯一的区别是它们位于内部还是外部 DNS 区域版本中。</span><span class="sxs-lookup"><span data-stu-id="1196a-163">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="1196a-164">有关详细信息，请参阅<A href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</A>中的 "分裂大脑 dns"。</span><span class="sxs-lookup"><span data-stu-id="1196a-164">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="1196a-165">联盟所需的记录</span><span class="sxs-lookup"><span data-stu-id="1196a-165">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1196a-166">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="1196a-166">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1196a-167">FQDN</span><span class="sxs-lookup"><span data-stu-id="1196a-167">FQDN</span></span></th>
<th><span data-ttu-id="1196a-168">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="1196a-168">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="1196a-169">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="1196a-169">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1196a-170">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="1196a-170">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="1196a-171">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-171">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-172">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-172">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-173">SIP 访问边缘外部接口，将联合身份验证自动 DNS 发现到其他潜在的联合合作伙伴，并称为 "允许的 SIP 域" （在以前的版本中称为增强联盟）。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</span><span class="sxs-lookup"><span data-stu-id="1196a-173">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="1196a-174">移动和推送通知交换所需要此 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="1196a-174">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="1196a-175">可扩展消息和状态协议的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="1196a-175">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1196a-176">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="1196a-176">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1196a-177">FQDN</span><span class="sxs-lookup"><span data-stu-id="1196a-177">FQDN</span></span></th>
<th><span data-ttu-id="1196a-178">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="1196a-178">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="1196a-179">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="1196a-179">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1196a-180">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="1196a-180">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="1196a-181">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-181">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-182">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1196a-182">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1196a-183">"访问边缘服务" 或 "边缘池" 上的 XMPP 代理外部接口。对于启用了 Lync 的用户，通过全局策略、用户所在的网站策略或应用了用户策略的用户策略，可对所有内部 SIP 域进行必要的操作，并允许使用启用了 Lync 的用户使用 XMPP 联系人。启用 Lync 的用户。</span><span class="sxs-lookup"><span data-stu-id="1196a-183">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="1196a-184">还必须在 XMPP 联盟合作伙伴策略中配置允许的 XMPP 域。</span><span class="sxs-lookup"><span data-stu-id="1196a-184">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="1196a-185">有关其他详细信息，请参阅<strong>另请参阅</strong>中的主题</span><span class="sxs-lookup"><span data-stu-id="1196a-185">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1196a-186">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1196a-186">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1196a-187">xmpp.contoso.com （例如）</span><span class="sxs-lookup"><span data-stu-id="1196a-187">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="1196a-188">边缘服务器上的访问边缘服务的 IP 地址或托管 XMPP 代理的边缘池的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="1196a-188">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="1196a-189">指向托管 XMPP 代理服务的访问边缘服务或边缘池。</span><span class="sxs-lookup"><span data-stu-id="1196a-189">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="1196a-190">通常，你创建的 SRV 记录将指向此主机（A 或 AAAA）记录</span><span class="sxs-lookup"><span data-stu-id="1196a-190">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

