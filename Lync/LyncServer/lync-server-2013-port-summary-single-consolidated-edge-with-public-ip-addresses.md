---
title: 端口摘要-使用公用 IP 地址的单一合并边缘
description: 端口摘要-使用公用 IP 地址的单一合并边缘。
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
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566398"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="ced28-103">Lync Server 2013 中的端口摘要-具有公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="ced28-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ced28-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ced28-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ced28-105">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。</span><span class="sxs-lookup"><span data-stu-id="ced28-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="ced28-106">最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。</span><span class="sxs-lookup"><span data-stu-id="ced28-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="ced28-107">Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="ced28-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="ced28-108">有关反向代理和联合的规划信息，请参阅 [Lync server 2013 中的反向代理方案](lync-server-2013-scenarios-for-reverse-proxy.md) 和在 [lync server 2013 部分中规划 SIP、XMPP 联合身份验证和公共即时消息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) 。</span><span class="sxs-lookup"><span data-stu-id="ced28-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="ced28-109">除 IPv4 外，边缘服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="ced28-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="ced28-110">为了清楚起见，本方案中仅使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="ced28-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="ced28-111">**使用公用 IP 寻址的单一合并边缘的企业外围网络**</span><span class="sxs-lookup"><span data-stu-id="ced28-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="ced28-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="ced28-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ced28-113">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="ced28-113">Port and Protocol Details</span></span>

<span data-ttu-id="ced28-114">我们建议您仅打开支持为其提供外部访问权限的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="ced28-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="ced28-p103">要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图所示。换种方式说就是，即时消息 (IM)、状态、Web 会议、音频/视频 (A/V) 和联盟中涉及发往或来自访问边缘服务的 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="ced28-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="ced28-117">具有公共 IP 地址的单个合并边缘的防火墙摘要：外部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ced28-118">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ced28-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ced28-119">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-119">Source IP address</span></span></th>
<th><span data-ttu-id="ced28-120">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-120">Destination IP address</span></span></th>
<th><span data-ttu-id="ced28-121">注释</span><span class="sxs-lookup"><span data-stu-id="ced28-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ced28-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ced28-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ced28-123">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-123">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-124">XMPP 代理服务 (与访问边缘服务共享 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="ced28-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ced28-125">XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="ced28-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-126">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ced28-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ced28-127">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-128">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-128">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-129">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="ced28-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-130">访问/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="ced28-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="ced28-131">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-132">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-132">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-133">通过 TCP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="ced28-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-134">访问/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="ced28-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="ced28-135">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-136">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-136">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-137">通过 UDP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="ced28-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-138">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="ced28-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ced28-139">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-139">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-140">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-141">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="ced28-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-142">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ced28-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ced28-143">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-143">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-144">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-145">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ced28-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-146">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ced28-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ced28-147">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-148">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-148">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-149">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ced28-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-150">Web 会议/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="ced28-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ced28-151">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-151">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-152">边缘服务器 Web 会议边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-153">Web 会议媒体</span><span class="sxs-lookup"><span data-stu-id="ced28-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-154">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ced28-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ced28-155">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-156">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-156">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-157">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</span><span class="sxs-lookup"><span data-stu-id="ced28-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-158">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ced28-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ced28-159">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-160">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-160">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-161">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="ced28-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-162">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ced28-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ced28-163">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-163">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-164">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-165">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="ced28-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-166">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ced28-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ced28-167">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-167">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-168">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-169">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="ced28-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-170">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ced28-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ced28-171">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-172">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-172">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-173">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="ced28-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="ced28-174">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</span><span class="sxs-lookup"><span data-stu-id="ced28-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-175">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ced28-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ced28-176">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-176">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-177">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-178">通过 UDP/3478 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="ced28-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-179">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ced28-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ced28-180">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-180">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-181">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-182">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="ced28-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-183">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ced28-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ced28-184">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-185">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-185">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-186">TCP/443 上的候选项的 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="ced28-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="ced28-187">具有公共 IP 地址的单个合并边缘的防火墙摘要：内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ced28-188">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ced28-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ced28-189">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-189">Source IP address</span></span></th>
<th><span data-ttu-id="ced28-190">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-190">Destination IP address</span></span></th>
<th><span data-ttu-id="ced28-191">Comments</span><span class="sxs-lookup"><span data-stu-id="ced28-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ced28-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ced28-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ced28-193">可以将任何 (定义为 Standard Edition server IP、Standard Edition server IP 地址或运行 XMPP 网关服务的池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="ced28-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="ced28-194">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-195">来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="ced28-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ced28-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ced28-197">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="ced28-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="ced28-198">包含内部接口的边缘服务器 IP 或池</span><span class="sxs-lookup"><span data-stu-id="ced28-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-199">从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 到边缘服务器内部接口的出站 SIP 流量 (</span><span class="sxs-lookup"><span data-stu-id="ced28-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ced28-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ced28-201">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-202">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池地址) </span><span class="sxs-lookup"><span data-stu-id="ced28-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="ced28-203">入站 SIP 流量 (到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 从边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="ced28-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="ced28-205">可以将任何 (定义为前端服务器 IP 地址，或在前端池中的每个前端服务器 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="ced28-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="ced28-206">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-207">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="ced28-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="ced28-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="ced28-209">可以将任何 (定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器) </span><span class="sxs-lookup"><span data-stu-id="ced28-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="ced28-210">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-211">A/V 身份验证服务 (A/v 身份验证服务) 从前端服务器或前端池 IP 地址或使用此边缘服务器的任何 Survivable 分支装置或 Survivable 分支服务器进行身份验证</span><span class="sxs-lookup"><span data-stu-id="ced28-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-212">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ced28-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ced28-213">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-213">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-214">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-215">内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="ced28-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-216">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ced28-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ced28-217">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-217">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-218">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-219">内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="ced28-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ced28-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ced28-221">可以将任何 (定义为前端服务器 IP 地址或包含中央管理存储的池) </span><span class="sxs-lookup"><span data-stu-id="ced28-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="ced28-222">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-223">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="ced28-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ced28-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ced28-225">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-225">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-226">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-227">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="ced28-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ced28-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ced28-229">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-229">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-230">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-231">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="ced28-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ced28-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ced28-233">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-233">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-234">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="ced28-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ced28-235">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="ced28-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="ced28-236">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="ced28-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ced28-237">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ced28-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ced28-238">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-238">Source IP address</span></span></th>
<th><span data-ttu-id="ced28-239">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-239">Destination IP address</span></span></th>
<th><span data-ttu-id="ced28-240">注释</span><span class="sxs-lookup"><span data-stu-id="ced28-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ced28-241">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ced28-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ced28-242">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-243">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-243">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-244">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ced28-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="ced28-245">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="ced28-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ced28-246">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ced28-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ced28-247">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-247">Source IP address</span></span></th>
<th><span data-ttu-id="ced28-248">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-248">Destination IP address</span></span></th>
<th><span data-ttu-id="ced28-249">注释</span><span class="sxs-lookup"><span data-stu-id="ced28-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ced28-250">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ced28-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ced28-251">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="ced28-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ced28-252">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="ced28-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ced28-253">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ced28-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-254">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ced28-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ced28-255">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="ced28-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ced28-256">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="ced28-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ced28-257">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ced28-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-258">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="ced28-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ced28-259">客户端</span><span class="sxs-lookup"><span data-stu-id="ced28-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="ced28-260">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="ced28-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ced28-261">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="ced28-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-262">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ced28-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ced28-263">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="ced28-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ced28-264">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="ced28-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ced28-265">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="ced28-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-266">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ced28-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ced28-267">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="ced28-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ced28-268">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="ced28-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ced28-269">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ced28-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-270">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ced28-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ced28-271">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="ced28-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ced28-272">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="ced28-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ced28-273">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="ced28-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="ced28-274">可扩展消息传递和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="ced28-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ced28-275">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="ced28-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ced28-276">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="ced28-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="ced28-277">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="ced28-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="ced28-278">Comments</span><span class="sxs-lookup"><span data-stu-id="ced28-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ced28-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ced28-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ced28-280">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-280">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-281">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-282">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="ced28-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ced28-283">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="ced28-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ced28-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ced28-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ced28-285">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ced28-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ced28-286">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-286">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-287">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="ced28-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ced28-288">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="ced28-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ced28-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ced28-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ced28-290">任何</span><span class="sxs-lookup"><span data-stu-id="ced28-290">Any</span></span></p></td>
<td><p><span data-ttu-id="ced28-291">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="ced28-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="ced28-292">从前端服务器或前端池上的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="ced28-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

