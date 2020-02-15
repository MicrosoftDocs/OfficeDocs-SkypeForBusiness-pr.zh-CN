---
title: DNS 摘要-使用公用 IP 地址的单一合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d78bcb5733b2630ad69ebc7686885625ce6ed13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="22b8f-102">Lync Server 2013 中的 DNS 摘要-使用公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="22b8f-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22b8f-103">_**上次修改的主题：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="22b8f-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="22b8f-104">与证书和端口相比，远程访问 Lync Server 2013 的 DNS 记录要求相当简单。</span><span class="sxs-lookup"><span data-stu-id="22b8f-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="22b8f-105">此外，许多记录是可选的，具体取决于如何配置运行 Lync 2013 的客户端以及是否启用联盟。</span><span class="sxs-lookup"><span data-stu-id="22b8f-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="22b8f-106">有关 Lync 2013 DNS 要求的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22b8f-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="22b8f-107">若要详细了解如何自动配置运行 Lync 2013 的客户端，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "自动配置而不拆分大脑 dns"。</span><span class="sxs-lookup"><span data-stu-id="22b8f-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="22b8f-108">下表包含 DNS 记录的摘要，支持单个合并边缘拓扑图中显示的单个合并边缘拓扑时需要这些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="22b8f-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="22b8f-109">请注意，只有在自动配置 Lync 2013 和 Lync 2010 客户端时，才需要某些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="22b8f-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="22b8f-110">如果您计划使用组策略对象（Gpo）来配置 Lync 客户端，则不需要关联的自动配置记录。</span><span class="sxs-lookup"><span data-stu-id="22b8f-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="22b8f-111">重要说明：边缘服务器网络适配器要求</span><span class="sxs-lookup"><span data-stu-id="22b8f-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="22b8f-112">若要避免路由问题，请确认边缘服务器中至少有两个网络适配器，并且默认网关仅在与外部接口相关联的网络适配器上设置。</span><span class="sxs-lookup"><span data-stu-id="22b8f-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="22b8f-113">例如，如在具有公共 IP 地址的单一合并边缘拓扑中，在[Lync Server 2013 中使用公用 ip 地址](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)的单一合并边缘拓扑图中所示，默认网关将指向 Internet 外围的外部路由器或可提供公用 ip 地址的防火墙。</span><span class="sxs-lookup"><span data-stu-id="22b8f-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="22b8f-114">边缘服务器接口的网络关系是路由关系，而不是 NAT 关系。</span><span class="sxs-lookup"><span data-stu-id="22b8f-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="22b8f-115">您可以在边缘服务器中配置两个网络适配器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22b8f-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="22b8f-116">**网络适配器 1（内部接口）**</span><span class="sxs-lookup"><span data-stu-id="22b8f-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="22b8f-117">分配有 172.25.33.10 的内部接口。</span><span class="sxs-lookup"><span data-stu-id="22b8f-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="22b8f-118">未定义默认网关。</span><span class="sxs-lookup"><span data-stu-id="22b8f-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="22b8f-119">确保从包含边缘内部接口的网络的路由到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="22b8f-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="22b8f-120">**网络适配器 2（外部接口）**</span><span class="sxs-lookup"><span data-stu-id="22b8f-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="22b8f-121">三个公共 IP 地址将分配到此网络适配器，例如为访问边缘分配 131.107.155.10，为 Web 会议边缘分配 131.107.155.20，为 AV 边缘分配 131.107.155.30。</span><span class="sxs-lookup"><span data-stu-id="22b8f-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="22b8f-p104">可以为所有三个边缘服务接口使用一个 IP 地址，但不建议这样做。尽管这样可以节省 IP 地址，但需要为每个服务使用不同端口号。默认端口号为 443/TCP，它可确保大多数远程防火墙将允许流量通过。对于远程用户（支持这些用户的防火墙不允许 5061/TCP 和 444/TCP 上的流量通过），为访问边缘将端口值更改为（比如）5061/TCP、为 Web 会议边缘将端口值更改为 444/TCP 以及为 AV 边缘将端口值更改为 443/TCP 可能导致问题。另外，由于能够筛选 IP 地址，因此使用三个不同的 IP 地址更便于排除故障。</span><span class="sxs-lookup"><span data-stu-id="22b8f-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="22b8f-127">访问边缘公共 IP 地址是默认网关设置为公共路由器的主要 IP 地址 (131.107.155.1)。</span><span class="sxs-lookup"><span data-stu-id="22b8f-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="22b8f-128">Web 会议和 A/V 边缘公共 IP 地址是 Windows Server 中**本地区域连接属性**的 **Internet 协议版本 4 (TCP/IPv4)** 和 **Internet 协议版本 6 (TCP/IPv6)** 属性的**高级** 部分中的其他 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22b8f-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="22b8f-129">配置具有两个网络适配器的边缘服务器是两个选项之一。</span><span class="sxs-lookup"><span data-stu-id="22b8f-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="22b8f-130">另一种方法是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。</span><span class="sxs-lookup"><span data-stu-id="22b8f-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="22b8f-131">此选项的主要优点是，每个边缘服务器服务都有不同的网络适配器，并且在需要故障排除时有可能更简单的数据收集</span><span class="sxs-lookup"><span data-stu-id="22b8f-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="22b8f-132">单个合并边缘所需的 DNS 记录和公共 IP 地址（示例）</span><span class="sxs-lookup"><span data-stu-id="22b8f-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22b8f-133">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="22b8f-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="22b8f-134">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="22b8f-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="22b8f-135">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="22b8f-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="22b8f-136">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="22b8f-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22b8f-137">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="22b8f-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="22b8f-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22b8f-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="22b8f-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="22b8f-140">访问边缘外部接口 (Contoso) 根据需要为启用 Lync 的用户的所有 SIP 域重复使用</span><span class="sxs-lookup"><span data-stu-id="22b8f-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22b8f-141">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="22b8f-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="22b8f-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22b8f-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="22b8f-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="22b8f-144">Web 会议边缘外部接口</span><span class="sxs-lookup"><span data-stu-id="22b8f-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22b8f-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="22b8f-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="22b8f-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22b8f-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="22b8f-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="22b8f-148">A/V 边缘外部接口</span><span class="sxs-lookup"><span data-stu-id="22b8f-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22b8f-149">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="22b8f-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="22b8f-150">_sip _tls .com</span><span class="sxs-lookup"><span data-stu-id="22b8f-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22b8f-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-152">访问边缘外部接口。</span><span class="sxs-lookup"><span data-stu-id="22b8f-152">Access Edge external interface.</span></span> <span data-ttu-id="22b8f-153">将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作是必需的。</span><span class="sxs-lookup"><span data-stu-id="22b8f-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="22b8f-154">根据需要为启用 Lync 的用户的所有 SIP 域重复使用。</span><span class="sxs-lookup"><span data-stu-id="22b8f-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22b8f-155">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="22b8f-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="22b8f-156">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="22b8f-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22b8f-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-158">SIP 访问边缘外部接口用于实现称为“允许的 SIP 域”的联盟伙伴（在以前版本中称为增强联盟）的自动 DNS 发现。根据需要为启用 Lync 的用户的所有 SIP 域重复使用</span><span class="sxs-lookup"><span data-stu-id="22b8f-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22b8f-159">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="22b8f-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="22b8f-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="22b8f-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="22b8f-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="22b8f-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="22b8f-162">合并边缘内部接口</span><span class="sxs-lookup"><span data-stu-id="22b8f-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="22b8f-163">上表中列出的记录以 <EM>.net</EM> 扩展名或 <EM>.com</EM> 扩展名显示，以便在未使用裂脑 DNS 时突出显示需要驻留这些记录的区域。</span><span class="sxs-lookup"><span data-stu-id="22b8f-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="22b8f-164">如果使用裂脑 DNS，则所有记录将位于同一区域中，唯一的区别在于它们是位于内部版本还是外部版本。</span><span class="sxs-lookup"><span data-stu-id="22b8f-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="22b8f-165">有关详细信息，请参阅<A href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</A>中的 "裂脑 dns"。</span><span class="sxs-lookup"><span data-stu-id="22b8f-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="22b8f-166">联盟所需的记录</span><span class="sxs-lookup"><span data-stu-id="22b8f-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22b8f-167">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="22b8f-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="22b8f-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="22b8f-168">FQDN</span></span></th>
<th><span data-ttu-id="22b8f-169">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="22b8f-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="22b8f-170">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="22b8f-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22b8f-171">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="22b8f-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="22b8f-172">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="22b8f-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22b8f-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-174">用于实现与其他潜在联盟伙伴的联盟的自动 DNS 发现的 SIP 访问边缘外部接口，称为“允许的 SIP 域”（在以前版本中称为增强联盟）。必要时对带有启用了 Lync 的用户的所有 SIP 域重复</span><span class="sxs-lookup"><span data-stu-id="22b8f-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="22b8f-175">移动性和推送通知交换所需要此 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="22b8f-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="22b8f-176">可扩展消息传递和状态协议的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="22b8f-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22b8f-177">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="22b8f-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="22b8f-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="22b8f-178">FQDN</span></span></th>
<th><span data-ttu-id="22b8f-179">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="22b8f-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="22b8f-180">映射目标/注释</span><span class="sxs-lookup"><span data-stu-id="22b8f-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22b8f-181">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="22b8f-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="22b8f-182">_xmpp-_tcp .com</span><span class="sxs-lookup"><span data-stu-id="22b8f-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="22b8f-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="22b8f-184">访问边缘服务或边缘池上的 XMPP 代理外部接口。根据需要对启用了 Lync 的用户使用通过全局策略、用户所在的网站策略或应用于 XMPP 联系人的外部访问策略的配置，对所有内部 SIP 域重复此操作。启用了 Lync 的用户。</span><span class="sxs-lookup"><span data-stu-id="22b8f-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="22b8f-185">还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。</span><span class="sxs-lookup"><span data-stu-id="22b8f-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="22b8f-186">有关其他详细信息，请参阅<strong>另请参阅</strong>主题中的主题</span><span class="sxs-lookup"><span data-stu-id="22b8f-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22b8f-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="22b8f-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="22b8f-188">xmpp.contoso.com（举例）</span><span class="sxs-lookup"><span data-stu-id="22b8f-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="22b8f-189">边缘服务器或边缘池托管 XMPP 代理上的访问边缘服务的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="22b8f-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="22b8f-190">指向承载 XMPP 代理服务的访问边缘服务或边缘池。</span><span class="sxs-lookup"><span data-stu-id="22b8f-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="22b8f-191">一般而言，您创建的 SRV 记录将指向此主机（A 或 AAAA）记录</span><span class="sxs-lookup"><span data-stu-id="22b8f-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

