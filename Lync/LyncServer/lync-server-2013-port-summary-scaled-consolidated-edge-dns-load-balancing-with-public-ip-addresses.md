---
title: Lync Server 2013：端口摘要-扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5318f418c2bbd0876999aedcb33b559c5572b20a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534119"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="66866-102">Lync Server 2013 中的端口摘要-扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="66866-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66866-103">_**上次修改的主题：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="66866-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="66866-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。</span><span class="sxs-lookup"><span data-stu-id="66866-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="66866-105">最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。</span><span class="sxs-lookup"><span data-stu-id="66866-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="66866-106">Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="66866-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="66866-107">除 IPv4 外，边缘服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="66866-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="66866-108">为了清楚起见，本方案中仅使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="66866-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="66866-109">**用于扩展合并边缘的企业外围网络（使用公用 IP 地址进行 DNS 负载平衡）**</span><span class="sxs-lookup"><span data-stu-id="66866-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="66866-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="66866-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="66866-111">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="66866-111">Port and Protocol Details</span></span>

<span data-ttu-id="66866-112">建议仅打开支持为其提供外部访问的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="66866-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="66866-p103">要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。换言之，即时消息 (IM)、状态、Web 会议、音频/视频 (A/V) 和联盟中会涉及在访问边缘服务中接收和发送 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="66866-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="66866-115">扩展的合并边缘的防火墙摘要、使用公用 IP 地址的 DNS 负载平衡：外部接口–节点1和节点 2 (示例) </span><span class="sxs-lookup"><span data-stu-id="66866-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66866-116">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="66866-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="66866-117">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-117">Source IP address</span></span></th>
<th><span data-ttu-id="66866-118">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-118">Destination IP address</span></span></th>
<th><span data-ttu-id="66866-119">注释</span><span class="sxs-lookup"><span data-stu-id="66866-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66866-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="66866-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="66866-121">任何</span><span class="sxs-lookup"><span data-stu-id="66866-121">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-122">XMPP 代理服务 (与访问边缘服务共享 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="66866-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="66866-123">XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="66866-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="66866-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="66866-125">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-126">任何</span><span class="sxs-lookup"><span data-stu-id="66866-126">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-127">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="66866-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-128">访问/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="66866-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="66866-129">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-130">任何</span><span class="sxs-lookup"><span data-stu-id="66866-130">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-131">通过 TCP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="66866-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-132">访问/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="66866-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="66866-133">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-134">任何</span><span class="sxs-lookup"><span data-stu-id="66866-134">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-135">通过 UDP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="66866-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-136">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="66866-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="66866-137">任何</span><span class="sxs-lookup"><span data-stu-id="66866-137">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-138">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-139">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="66866-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-140">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="66866-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="66866-141">任何</span><span class="sxs-lookup"><span data-stu-id="66866-141">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-142">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-143">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="66866-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-144">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="66866-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="66866-145">边缘服务器访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-146">任何</span><span class="sxs-lookup"><span data-stu-id="66866-146">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-147">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="66866-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-148">Web 会议/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="66866-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="66866-149">任何</span><span class="sxs-lookup"><span data-stu-id="66866-149">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-150">边缘服务器 Web 会议边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-151">Web 会议媒体</span><span class="sxs-lookup"><span data-stu-id="66866-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="66866-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="66866-153">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-154">任何</span><span class="sxs-lookup"><span data-stu-id="66866-154">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-155">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</span><span class="sxs-lookup"><span data-stu-id="66866-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="66866-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="66866-157">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-158">任何</span><span class="sxs-lookup"><span data-stu-id="66866-158">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-159">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="66866-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="66866-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="66866-161">任何</span><span class="sxs-lookup"><span data-stu-id="66866-161">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-162">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-163">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="66866-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="66866-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="66866-165">任何</span><span class="sxs-lookup"><span data-stu-id="66866-165">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-166">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-167">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="66866-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="66866-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="66866-169">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-170">任何</span><span class="sxs-lookup"><span data-stu-id="66866-170">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-171">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="66866-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="66866-172">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</span><span class="sxs-lookup"><span data-stu-id="66866-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="66866-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="66866-174">任何</span><span class="sxs-lookup"><span data-stu-id="66866-174">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-175">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-176">通过 UDP/3478 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="66866-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="66866-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="66866-178">任何</span><span class="sxs-lookup"><span data-stu-id="66866-178">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-179">边缘服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-180">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="66866-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="66866-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="66866-182">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="66866-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="66866-183">任何</span><span class="sxs-lookup"><span data-stu-id="66866-183">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-184">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="66866-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="66866-185">使用公共 IP 地址的扩展的合并边缘（DNS 负载平衡）的防火墙摘要：外部接口 – 节点 1 和节点 2（示例）</span><span class="sxs-lookup"><span data-stu-id="66866-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66866-186">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="66866-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="66866-187">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-187">Source IP address</span></span></th>
<th><span data-ttu-id="66866-188">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-188">Destination IP address</span></span></th>
<th><span data-ttu-id="66866-189">Comments</span><span class="sxs-lookup"><span data-stu-id="66866-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66866-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="66866-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="66866-191">可以将任何 (定义为前端服务器地址，也可以将前端池 IP 地址定义为运行 XMPP 网关服务的前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="66866-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="66866-192">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-193">来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="66866-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="66866-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="66866-195">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="66866-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="66866-196">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-197">从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 到边缘服务器内部接口的出站 SIP 流量 (</span><span class="sxs-lookup"><span data-stu-id="66866-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="66866-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="66866-199">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-200">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="66866-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="66866-201">入站 SIP 流量 (到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 从边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="66866-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="66866-203">可以将任何 (定义为前端服务器 IP 地址，或在前端池中的每个前端服务器 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="66866-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="66866-204">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-205">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="66866-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="66866-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="66866-207">可以将任何 (定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器) </span><span class="sxs-lookup"><span data-stu-id="66866-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="66866-208">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-209">A/V 身份验证服务 (A/v 身份验证服务) 从前端服务器或前端池 IP 地址或使用此边缘服务器的任何 Survivable 分支装置或 Survivable 分支服务器进行身份验证</span><span class="sxs-lookup"><span data-stu-id="66866-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="66866-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="66866-211">任何</span><span class="sxs-lookup"><span data-stu-id="66866-211">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-212">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-213">内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="66866-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="66866-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="66866-215">任何</span><span class="sxs-lookup"><span data-stu-id="66866-215">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-216">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-217">内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="66866-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="66866-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="66866-219">可以将任何 (定义为前端服务器 IP 地址或包含中央管理存储的池) </span><span class="sxs-lookup"><span data-stu-id="66866-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="66866-220">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-221">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="66866-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="66866-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="66866-223">任何</span><span class="sxs-lookup"><span data-stu-id="66866-223">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-224">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-225">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="66866-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="66866-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="66866-227">任何</span><span class="sxs-lookup"><span data-stu-id="66866-227">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-228">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-229">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="66866-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="66866-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="66866-231">任何</span><span class="sxs-lookup"><span data-stu-id="66866-231">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-232">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="66866-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="66866-233">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="66866-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="66866-234">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="66866-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66866-235">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="66866-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="66866-236">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-236">Source IP address</span></span></th>
<th><span data-ttu-id="66866-237">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-237">Destination IP address</span></span></th>
<th><span data-ttu-id="66866-238">注释</span><span class="sxs-lookup"><span data-stu-id="66866-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66866-239">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="66866-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="66866-240">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-241">任何</span><span class="sxs-lookup"><span data-stu-id="66866-241">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-242">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="66866-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="66866-243">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="66866-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66866-244">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="66866-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="66866-245">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-245">Source IP address</span></span></th>
<th><span data-ttu-id="66866-246">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-246">Destination IP address</span></span></th>
<th><span data-ttu-id="66866-247">注释</span><span class="sxs-lookup"><span data-stu-id="66866-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66866-248">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="66866-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="66866-249">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="66866-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="66866-250">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="66866-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="66866-251">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="66866-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-252">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="66866-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="66866-253">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="66866-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="66866-254">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="66866-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="66866-255">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="66866-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-256">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="66866-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="66866-257">客户端</span><span class="sxs-lookup"><span data-stu-id="66866-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="66866-258">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="66866-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="66866-259">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="66866-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="66866-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="66866-261">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="66866-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="66866-262">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="66866-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="66866-263">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="66866-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="66866-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="66866-265">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="66866-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="66866-266">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="66866-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="66866-267">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="66866-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="66866-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="66866-269">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="66866-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="66866-270">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="66866-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="66866-271">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="66866-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="66866-272">可扩展消息传递和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="66866-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66866-273">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="66866-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="66866-274">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="66866-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="66866-275">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="66866-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="66866-276">Comments</span><span class="sxs-lookup"><span data-stu-id="66866-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66866-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="66866-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="66866-278">任何</span><span class="sxs-lookup"><span data-stu-id="66866-278">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-279">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-280">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="66866-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="66866-281">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="66866-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66866-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="66866-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="66866-283">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66866-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="66866-284">任何</span><span class="sxs-lookup"><span data-stu-id="66866-284">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-285">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="66866-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="66866-286">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="66866-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66866-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="66866-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="66866-288">任何</span><span class="sxs-lookup"><span data-stu-id="66866-288">Any</span></span></p></td>
<td><p><span data-ttu-id="66866-289">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="66866-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="66866-290">从前端服务器或前端池上的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="66866-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

