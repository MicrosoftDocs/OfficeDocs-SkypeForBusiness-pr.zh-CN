---
title: 端口摘要-使用公用 IP 地址的单一合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f94ac852959ca440f09f8878a17c1e23f7698bd4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="ee964-102">Lync Server 2013 中的端口摘要-具有公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="ee964-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee964-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ee964-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ee964-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。</span><span class="sxs-lookup"><span data-stu-id="ee964-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="ee964-105">最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。</span><span class="sxs-lookup"><span data-stu-id="ee964-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="ee964-106">Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="ee964-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="ee964-107">有关反向代理和联合的规划信息，请参阅[Lync server 2013 中的反向代理方案](lync-server-2013-scenarios-for-reverse-proxy.md)和在[lync server 2013 部分中规划 SIP、XMPP 联合身份验证和公共即时消息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="ee964-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="ee964-108">除 IPv4 外，边缘服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="ee964-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="ee964-109">为了清楚起见，本方案中仅使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="ee964-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="ee964-110">**使用公用 IP 寻址的单一合并边缘的企业外围网络**</span><span class="sxs-lookup"><span data-stu-id="ee964-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="ee964-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="ee964-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ee964-112">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="ee964-112">Port and Protocol Details</span></span>

<span data-ttu-id="ee964-113">我们建议您仅打开支持为其提供外部访问权限的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="ee964-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="ee964-p103">要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图所示。换种方式说就是，即时消息 (IM)、状态、Web 会议、音频/视频 (A/V) 和联盟中涉及发往或来自访问边缘服务的 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="ee964-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="ee964-116">具有公共 IP 地址的单个合并边缘的防火墙摘要：外部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee964-117">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ee964-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ee964-118">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-118">Source IP address</span></span></th>
<th><span data-ttu-id="ee964-119">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-119">Destination IP address</span></span></th>
<th><span data-ttu-id="ee964-120">备注</span><span class="sxs-lookup"><span data-stu-id="ee964-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee964-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ee964-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ee964-122">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-122">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-123">XMPP 代理服务（与访问边缘服务共享 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="ee964-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ee964-124">XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="ee964-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ee964-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ee964-126">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-127">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-127">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-128">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="ee964-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-129">访问/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="ee964-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="ee964-130">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-131">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-131">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-132">通过 TCP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="ee964-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-133">访问/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="ee964-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="ee964-134">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-135">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-135">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-136">通过 UDP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="ee964-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-137">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ee964-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ee964-138">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-138">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-139">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-140">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="ee964-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-141">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee964-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee964-142">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-142">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-143">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-144">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ee964-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-145">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee964-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee964-146">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-147">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-147">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-148">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ee964-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-149">Web 会议/PSOM （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ee964-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ee964-150">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-150">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-151">边缘服务器 Web 会议边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-152">Web 会议媒体</span><span class="sxs-lookup"><span data-stu-id="ee964-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-153">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ee964-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ee964-154">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-155">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-155">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-156">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</span><span class="sxs-lookup"><span data-stu-id="ee964-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-157">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ee964-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ee964-158">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-159">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-159">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-160">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="ee964-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-161">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ee964-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ee964-162">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-162">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-163">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-164">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="ee964-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-165">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ee964-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ee964-166">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-166">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-167">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-168">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="ee964-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-169">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ee964-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ee964-170">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-171">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-171">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-172">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="ee964-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="ee964-173">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</span><span class="sxs-lookup"><span data-stu-id="ee964-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-174">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ee964-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ee964-175">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-175">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-176">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-177">通过 UDP/3478 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="ee964-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-178">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ee964-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ee964-179">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-179">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-180">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-181">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="ee964-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-182">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ee964-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ee964-183">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-184">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-184">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-185">TCP/443 上的候选项的 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="ee964-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="ee964-186">具有公共 IP 地址的单个合并边缘的防火墙摘要：内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee964-187">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ee964-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ee964-188">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-188">Source IP address</span></span></th>
<th><span data-ttu-id="ee964-189">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-189">Destination IP address</span></span></th>
<th><span data-ttu-id="ee964-190">注释</span><span class="sxs-lookup"><span data-stu-id="ee964-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee964-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ee964-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ee964-192">Any （可定义为 Standard Edition server IP、Standard Edition server IP 地址或运行 XMPP 网关服务的池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="ee964-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="ee964-193">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-194">来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="ee964-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee964-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee964-196">Any （可定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="ee964-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="ee964-197">包含内部接口的边缘服务器 IP 或池</span><span class="sxs-lookup"><span data-stu-id="ee964-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-198">出站 SIP 流量（从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）到边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee964-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee964-200">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-201">Any （可定义为控制器、控制器池 IP 地址、前端服务器或前端池地址）</span><span class="sxs-lookup"><span data-stu-id="ee964-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="ee964-202">来自边缘服务器内部接口的入站 SIP 流量（到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="ee964-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="ee964-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="ee964-204">Any （可定义为前端服务器 IP 地址，或在前端池中的每个前端服务器 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="ee964-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="ee964-205">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-206">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="ee964-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="ee964-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="ee964-208">Any （可定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器）</span><span class="sxs-lookup"><span data-stu-id="ee964-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="ee964-209">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-210">使用此边缘服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支机构或 Survivable 分支服务器对 A/V 用户（A/V 身份验证服务）进行身份验证</span><span class="sxs-lookup"><span data-stu-id="ee964-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ee964-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ee964-212">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-212">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-213">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-214">内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="ee964-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ee964-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ee964-216">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-216">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-217">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-218">内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="ee964-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ee964-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ee964-220">Any （可定义为前端服务器 IP 地址或拥有中央管理存储的池）</span><span class="sxs-lookup"><span data-stu-id="ee964-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="ee964-221">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-222">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="ee964-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ee964-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ee964-224">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-224">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-225">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-226">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="ee964-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ee964-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ee964-228">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-228">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-229">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-230">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="ee964-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ee964-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ee964-232">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-232">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-233">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ee964-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ee964-234">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="ee964-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="ee964-235">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="ee964-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee964-236">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ee964-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ee964-237">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-237">Source IP address</span></span></th>
<th><span data-ttu-id="ee964-238">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-238">Destination IP address</span></span></th>
<th><span data-ttu-id="ee964-239">备注</span><span class="sxs-lookup"><span data-stu-id="ee964-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee964-240">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee964-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee964-241">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-242">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-242">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-243">用于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ee964-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="ee964-244">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="ee964-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee964-245">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ee964-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ee964-246">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-246">Source IP address</span></span></th>
<th><span data-ttu-id="ee964-247">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-247">Destination IP address</span></span></th>
<th><span data-ttu-id="ee964-248">备注</span><span class="sxs-lookup"><span data-stu-id="ee964-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee964-249">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee964-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee964-250">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="ee964-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ee964-251">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="ee964-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ee964-252">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ee964-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-253">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee964-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee964-254">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="ee964-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ee964-255">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="ee964-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ee964-256">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ee964-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-257">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ee964-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ee964-258">客户端</span><span class="sxs-lookup"><span data-stu-id="ee964-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="ee964-259">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="ee964-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ee964-260">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="ee964-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-261">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ee964-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ee964-262">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="ee964-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ee964-263">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="ee964-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ee964-264">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="ee964-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-265">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ee964-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ee964-266">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="ee964-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ee964-267">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="ee964-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ee964-268">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ee964-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-269">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ee964-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ee964-270">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="ee964-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ee964-271">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="ee964-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ee964-272">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ee964-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="ee964-273">可扩展消息传递和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="ee964-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee964-274">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ee964-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ee964-275">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="ee964-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="ee964-276">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="ee964-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="ee964-277">注释</span><span class="sxs-lookup"><span data-stu-id="ee964-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee964-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ee964-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ee964-279">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-279">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-280">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-281">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="ee964-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ee964-282">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="ee964-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee964-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ee964-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ee964-284">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ee964-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ee964-285">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-285">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-286">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="ee964-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ee964-287">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="ee964-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee964-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ee964-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ee964-289">任意</span><span class="sxs-lookup"><span data-stu-id="ee964-289">Any</span></span></p></td>
<td><p><span data-ttu-id="ee964-290">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="ee964-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="ee964-291">从前端服务器或前端池上的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="ee964-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

