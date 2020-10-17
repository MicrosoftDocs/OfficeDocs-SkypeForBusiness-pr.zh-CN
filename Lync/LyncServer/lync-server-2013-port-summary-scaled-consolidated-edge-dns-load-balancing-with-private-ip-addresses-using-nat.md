---
title: Lync Server 2013：端口摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）
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
ms.openlocfilehash: ff1cb9d559d3d6824882a87aaa4d45ad7254c276
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534139"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="b4faf-102">Lync Server 2013 中的端口摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="b4faf-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4faf-103">_**上次修改的主题：** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="b4faf-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="b4faf-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。</span><span class="sxs-lookup"><span data-stu-id="b4faf-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="b4faf-105">最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。</span><span class="sxs-lookup"><span data-stu-id="b4faf-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="b4faf-106">Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="b4faf-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="b4faf-107">除 IPv4 外，边缘服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b4faf-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="b4faf-108">为了清楚起见，本方案中仅使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="b4faf-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="b4faf-109">**使用 NAT 的使用专用 IP 地址的扩展合并边缘的企业外围网络**</span><span class="sxs-lookup"><span data-stu-id="b4faf-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="b4faf-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="b4faf-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b4faf-111">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="b4faf-111">Port and Protocol Details</span></span>

<span data-ttu-id="b4faf-112">建议仅打开支持为其提供外部访问的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="b4faf-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="b4faf-p103">要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。换言之，即时消息 (IM)、状态、Web 会议、音频/视频 (A/V) 和联盟中会涉及在访问边缘服务中接收和发送 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="b4faf-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="b4faf-115">扩展的合并边缘的防火墙摘要、使用 NAT 的专用 IP 地址进行 DNS 负载平衡：外部接口–节点1和节点 2 (示例) </span><span class="sxs-lookup"><span data-stu-id="b4faf-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4faf-116">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b4faf-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b4faf-117">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-117">Source IP address</span></span></th>
<th><span data-ttu-id="b4faf-118">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-118">Destination IP address</span></span></th>
<th><span data-ttu-id="b4faf-119">注释</span><span class="sxs-lookup"><span data-stu-id="b4faf-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b4faf-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b4faf-121">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-121">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-122">XMPP 代理服务 (与访问边缘服务共享 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="b4faf-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b4faf-123">XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="b4faf-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b4faf-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b4faf-125">XMPP 代理服务 (与访问边缘服务共享 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="b4faf-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b4faf-126">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-126">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-127">XMPP 代理服务向定义的 XMPP 联合中的 XMPP 联系人发送流量</span><span class="sxs-lookup"><span data-stu-id="b4faf-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b4faf-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b4faf-129">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-130">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-130">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-131">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="b4faf-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-132">访问/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="b4faf-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="b4faf-133">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-134">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-134">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-135">通过 TCP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="b4faf-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-136">访问/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="b4faf-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="b4faf-137">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-138">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-138">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-139">通过 UDP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="b4faf-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-140">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="b4faf-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b4faf-141">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-141">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-142">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-143">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="b4faf-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-144">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b4faf-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b4faf-145">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-145">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-146">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-147">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b4faf-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-148">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b4faf-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b4faf-149">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-150">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-150">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-151">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b4faf-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-152">Web 会议/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="b4faf-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b4faf-153">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-153">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-154">边缘服务器 Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-155">Web 会议媒体</span><span class="sxs-lookup"><span data-stu-id="b4faf-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-156">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b4faf-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b4faf-157">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-158">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-158">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-159">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</span><span class="sxs-lookup"><span data-stu-id="b4faf-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-160">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b4faf-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b4faf-161">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-162">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-162">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-163">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="b4faf-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-164">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b4faf-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b4faf-165">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-165">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-166">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-167">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="b4faf-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-168">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b4faf-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b4faf-169">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-169">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-170">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-171">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="b4faf-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-172">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b4faf-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b4faf-173">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-174">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-174">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-175">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="b4faf-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="b4faf-176">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</span><span class="sxs-lookup"><span data-stu-id="b4faf-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-177">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b4faf-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b4faf-178">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-178">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-179">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-180">通过 UDP/3478 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="b4faf-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b4faf-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b4faf-182">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-182">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-183">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-184">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="b4faf-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-185">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b4faf-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b4faf-186">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-187">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-187">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-188">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="b4faf-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="b4faf-189">扩展的合并边缘的防火墙摘要、使用 NAT 的专用 IP 地址进行 DNS 负载平衡： Internal 接口– Node 1 和 Node 2 (示例) </span><span class="sxs-lookup"><span data-stu-id="b4faf-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4faf-190">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b4faf-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b4faf-191">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-191">Source IP address</span></span></th>
<th><span data-ttu-id="b4faf-192">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-192">Destination IP address</span></span></th>
<th><span data-ttu-id="b4faf-193">Comments</span><span class="sxs-lookup"><span data-stu-id="b4faf-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b4faf-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b4faf-195">可以将任何 (定义为前端服务器地址，也可以将前端池 IP 地址定义为运行 XMPP 网关服务的前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="b4faf-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="b4faf-196">边缘服务器内部接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b4faf-197">来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="b4faf-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b4faf-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b4faf-199">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="b4faf-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b4faf-200">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-201">从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 到边缘服务器内部接口的出站 SIP 流量 (</span><span class="sxs-lookup"><span data-stu-id="b4faf-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b4faf-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b4faf-203">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-204">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="b4faf-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b4faf-205">入站 SIP 流量 (到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 从边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="b4faf-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="b4faf-207">可以将任何 (定义为前端服务器 IP 地址，或在前端池中的每个前端服务器 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="b4faf-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="b4faf-208">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-209">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="b4faf-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="b4faf-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="b4faf-211">可以将任何 (定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器) </span><span class="sxs-lookup"><span data-stu-id="b4faf-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="b4faf-212">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-213">A/V 身份验证服务 (A/v 身份验证服务) 从前端服务器或前端池 IP 地址或使用此边缘服务器的任何 Survivable 分支装置或 Survivable 分支服务器进行身份验证</span><span class="sxs-lookup"><span data-stu-id="b4faf-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b4faf-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b4faf-215">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-215">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-216">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-217">内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="b4faf-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b4faf-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b4faf-219">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-219">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-220">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-221">内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="b4faf-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b4faf-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b4faf-223">可以将任何 (定义为前端服务器 IP 地址或包含中央管理存储的池) </span><span class="sxs-lookup"><span data-stu-id="b4faf-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="b4faf-224">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-225">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b4faf-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b4faf-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b4faf-227">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-227">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-228">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-229">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="b4faf-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b4faf-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b4faf-231">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-231">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-232">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-233">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="b4faf-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b4faf-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b4faf-235">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-235">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-236">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b4faf-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b4faf-237">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="b4faf-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="b4faf-238">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="b4faf-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4faf-239">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b4faf-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b4faf-240">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-240">Source IP address</span></span></th>
<th><span data-ttu-id="b4faf-241">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-241">Destination IP address</span></span></th>
<th><span data-ttu-id="b4faf-242">注释</span><span class="sxs-lookup"><span data-stu-id="b4faf-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-243">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b4faf-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b4faf-244">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b4faf-245">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-245">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-246">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b4faf-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b4faf-247">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="b4faf-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4faf-248">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b4faf-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b4faf-249">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-249">Source IP address</span></span></th>
<th><span data-ttu-id="b4faf-250">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-250">Destination IP address</span></span></th>
<th><span data-ttu-id="b4faf-251">注释</span><span class="sxs-lookup"><span data-stu-id="b4faf-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-252">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b4faf-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b4faf-253">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b4faf-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b4faf-254">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-255">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b4faf-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-256">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b4faf-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b4faf-257">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-258">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b4faf-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b4faf-259">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b4faf-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-260">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="b4faf-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b4faf-261">客户端</span><span class="sxs-lookup"><span data-stu-id="b4faf-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="b4faf-262">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-263">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="b4faf-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-264">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b4faf-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b4faf-265">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-266">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="b4faf-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b4faf-267">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="b4faf-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b4faf-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b4faf-269">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-270">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="b4faf-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b4faf-271">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b4faf-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-272">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b4faf-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b4faf-273">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="b4faf-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b4faf-274">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4faf-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b4faf-275">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b4faf-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="b4faf-276">可扩展消息传递和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="b4faf-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4faf-277">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b4faf-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b4faf-278">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b4faf-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="b4faf-279">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b4faf-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="b4faf-280">Comments</span><span class="sxs-lookup"><span data-stu-id="b4faf-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b4faf-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b4faf-282">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-282">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-283">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b4faf-284">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="b4faf-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b4faf-285">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="b4faf-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4faf-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b4faf-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b4faf-287">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b4faf-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b4faf-288">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-288">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-289">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="b4faf-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b4faf-290">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="b4faf-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4faf-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b4faf-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b4faf-292">任何</span><span class="sxs-lookup"><span data-stu-id="b4faf-292">Any</span></span></p></td>
<td><p><span data-ttu-id="b4faf-293">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="b4faf-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="b4faf-294">从前端服务器或前端池上的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="b4faf-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

