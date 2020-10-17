---
title: Lync Server 2013：端口摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）
description: Lync Server 2013：端口摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0402b6682e86e5edf263fca78dfbe0f8fa070b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563938"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="4a2a3-103">Lync Server 2013 中的端口摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="4a2a3-103">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a2a3-104">_**上次修改的主题：** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="4a2a3-104">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="4a2a3-105">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="4a2a3-106">最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="4a2a3-107">Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="4a2a3-108">除 IPv4 外，边缘服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="4a2a3-109">为了清楚起见，本方案中仅使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="4a2a3-110">**使用 NAT 的使用专用 IP 地址的扩展合并边缘的企业外围网络**</span><span class="sxs-lookup"><span data-stu-id="4a2a3-110">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="4a2a3-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="4a2a3-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="4a2a3-112">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="4a2a3-112">Port and Protocol Details</span></span>

<span data-ttu-id="4a2a3-113">建议仅打开支持为其提供外部访问的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="4a2a3-p103">要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。换言之，即时消息 (IM)、状态、Web 会议、音频/视频 (A/V) 和联盟中会涉及在访问边缘服务中接收和发送 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="4a2a3-116">扩展的合并边缘的防火墙摘要、使用 NAT 的专用 IP 地址进行 DNS 负载平衡：外部接口–节点1和节点 2 (示例) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a2a3-117">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4a2a3-118">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-118">Source IP address</span></span></th>
<th><span data-ttu-id="4a2a3-119">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-119">Destination IP address</span></span></th>
<th><span data-ttu-id="4a2a3-120">注释</span><span class="sxs-lookup"><span data-stu-id="4a2a3-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4a2a3-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-122">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-122">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-123">XMPP 代理服务 (与访问边缘服务共享 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-124">XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="4a2a3-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-125">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4a2a3-125">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-126">XMPP 代理服务 (与访问边缘服务共享 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-126">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-127">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-127">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-128">XMPP 代理服务向定义的 XMPP 联合中的 XMPP 联系人发送流量</span><span class="sxs-lookup"><span data-stu-id="4a2a3-128">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-129">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="4a2a3-129">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-130">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-131">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-131">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-132">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="4a2a3-132">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-133">访问/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="4a2a3-133">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-134">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-135">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-135">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-136">通过 TCP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="4a2a3-136">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-137">访问/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="4a2a3-137">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-138">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-139">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-139">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-140">通过 UDP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="4a2a3-140">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-141">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="4a2a3-141">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-142">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-142">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-143">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-144">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="4a2a3-144">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-145">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4a2a3-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-146">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-146">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-147">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-147">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-148">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="4a2a3-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-149">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4a2a3-149">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-150">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-150">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-151">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-151">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-152">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="4a2a3-152">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-153">Web 会议/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="4a2a3-153">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-154">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-154">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-155">边缘服务器 Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-155">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-156">Web 会议媒体</span><span class="sxs-lookup"><span data-stu-id="4a2a3-156">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-157">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="4a2a3-157">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-158">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-159">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-159">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-160">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-160">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-161">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="4a2a3-161">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-162">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-163">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-163">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-164">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-165">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="4a2a3-165">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-166">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-166">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-167">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-168">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="4a2a3-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-169">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="4a2a3-169">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-170">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-170">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-171">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-171">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-172">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="4a2a3-172">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4a2a3-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-174">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-174">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-175">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-175">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-176">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-176">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="4a2a3-177">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-177">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-178">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4a2a3-178">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-179">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-179">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-180">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-181">通过 UDP/3478 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="4a2a3-181">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-182">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4a2a3-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-183">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-183">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-184">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-184">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-185">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="4a2a3-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-186">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4a2a3-186">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-187">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-187">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-188">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-188">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-189">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="4a2a3-189">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="4a2a3-190">扩展的合并边缘的防火墙摘要、使用 NAT 的专用 IP 地址进行 DNS 负载平衡： Internal 接口– Node 1 和 Node 2 (示例) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-190">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a2a3-191">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-191">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4a2a3-192">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-192">Source IP address</span></span></th>
<th><span data-ttu-id="4a2a3-193">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-193">Destination IP address</span></span></th>
<th><span data-ttu-id="4a2a3-194">Comments</span><span class="sxs-lookup"><span data-stu-id="4a2a3-194">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-195">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="4a2a3-195">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-196">可以将任何 (定义为前端服务器地址，也可以将前端池 IP 地址定义为运行 XMPP 网关服务的前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-196">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-197">边缘服务器内部接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-197">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-198">来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="4a2a3-198">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4a2a3-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-200">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-201">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-202">从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 到边缘服务器内部接口的出站 SIP 流量 (</span><span class="sxs-lookup"><span data-stu-id="4a2a3-202">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-203">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4a2a3-203">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-204">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-205">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-205">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-206">入站 SIP 流量 (到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 从边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-206">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-207">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="4a2a3-207">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-208">可以将任何 (定义为前端服务器 IP 地址，或在前端池中的每个前端服务器 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-208">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-209">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-210">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="4a2a3-210">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-211">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="4a2a3-211">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-212">可以将任何 (定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-212">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-213">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-214">A/V 身份验证服务 (A/v 身份验证服务) 从前端服务器或前端池 IP 地址或使用此边缘服务器的任何 Survivable 分支装置或 Survivable 分支服务器进行身份验证</span><span class="sxs-lookup"><span data-stu-id="4a2a3-214">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-215">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4a2a3-215">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-216">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-216">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-217">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-218">内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="4a2a3-218">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-219">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4a2a3-219">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-220">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-220">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-221">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-222">内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="4a2a3-222">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-223">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="4a2a3-223">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-224">可以将任何 (定义为前端服务器 IP 地址或包含中央管理存储的池) </span><span class="sxs-lookup"><span data-stu-id="4a2a3-224">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-225">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-226">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="4a2a3-226">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-227">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="4a2a3-227">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-228">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-228">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-229">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-230">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="4a2a3-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-231">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="4a2a3-231">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-232">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-232">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-233">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-234">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="4a2a3-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-235">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="4a2a3-235">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-236">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-236">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-237">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-237">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-238">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="4a2a3-238">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="4a2a3-239">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="4a2a3-239">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a2a3-240">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-240">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4a2a3-241">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-241">Source IP address</span></span></th>
<th><span data-ttu-id="4a2a3-242">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-242">Destination IP address</span></span></th>
<th><span data-ttu-id="4a2a3-243">注释</span><span class="sxs-lookup"><span data-stu-id="4a2a3-243">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-244">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4a2a3-244">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-245">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-245">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-246">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-246">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-247">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="4a2a3-247">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="4a2a3-248">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="4a2a3-248">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a2a3-249">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-249">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4a2a3-250">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-250">Source IP address</span></span></th>
<th><span data-ttu-id="4a2a3-251">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-251">Destination IP address</span></span></th>
<th><span data-ttu-id="4a2a3-252">注释</span><span class="sxs-lookup"><span data-stu-id="4a2a3-252">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-253">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4a2a3-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-254">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="4a2a3-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-255">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-256">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="4a2a3-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-257">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4a2a3-257">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-258">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-259">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="4a2a3-259">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-260">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="4a2a3-260">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-261">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="4a2a3-261">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-262">客户端</span><span class="sxs-lookup"><span data-stu-id="4a2a3-262">Clients</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-263">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-263">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-264">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="4a2a3-264">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-265">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="4a2a3-265">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-266">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-267">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="4a2a3-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-268">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-268">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-269">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4a2a3-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-270">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-271">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="4a2a3-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-272">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="4a2a3-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-273">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4a2a3-273">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-274">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="4a2a3-274">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-275">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="4a2a3-275">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-276">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="4a2a3-276">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="4a2a3-277">可扩展消息传递和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="4a2a3-277">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a2a3-278">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="4a2a3-278">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4a2a3-279">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="4a2a3-279">Source (IP address)</span></span></th>
<th><span data-ttu-id="4a2a3-280">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="4a2a3-280">Destination (IP address)</span></span></th>
<th><span data-ttu-id="4a2a3-281">Comments</span><span class="sxs-lookup"><span data-stu-id="4a2a3-281">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4a2a3-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-283">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-283">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-284">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-285">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4a2a3-286">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="4a2a3-286">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a2a3-287">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4a2a3-287">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-288">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4a2a3-288">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-289">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-289">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-290">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="4a2a3-290">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4a2a3-291">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="4a2a3-291">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a2a3-292">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="4a2a3-292">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-293">任何</span><span class="sxs-lookup"><span data-stu-id="4a2a3-293">Any</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-294">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="4a2a3-294">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="4a2a3-295">从前端服务器或前端池上的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="4a2a3-295">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

