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
ms.openlocfilehash: 96bf91dfaf4d231ec64ce1b385983f63b15ee0b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="b5247-102">Lync Server 2013 中的端口摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="b5247-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5247-103">_**上次修改的主题：** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="b5247-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="b5247-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。</span><span class="sxs-lookup"><span data-stu-id="b5247-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="b5247-105">最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。</span><span class="sxs-lookup"><span data-stu-id="b5247-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="b5247-106">Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="b5247-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="b5247-107">除 IPv4 外，边缘服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b5247-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="b5247-108">为了清楚起见，本方案中仅使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="b5247-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="b5247-109">**使用 NAT 的使用专用 IP 地址的扩展合并边缘的企业外围网络**</span><span class="sxs-lookup"><span data-stu-id="b5247-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="b5247-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="b5247-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b5247-111">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="b5247-111">Port and Protocol Details</span></span>

<span data-ttu-id="b5247-112">建议仅打开支持为其提供外部访问的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="b5247-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="b5247-p103">要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。换言之，即时消息 (IM)、状态、Web 会议、音频/视频 (A/V) 和联盟中会涉及在访问边缘服务中接收和发送 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="b5247-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="b5247-115">扩展的合并边缘的防火墙摘要，使用 NAT 的专用 IP 地址进行 DNS 负载平衡：外部接口–节点1和节点2（示例）</span><span class="sxs-lookup"><span data-stu-id="b5247-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5247-116">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b5247-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b5247-117">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-117">Source IP address</span></span></th>
<th><span data-ttu-id="b5247-118">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-118">Destination IP address</span></span></th>
<th><span data-ttu-id="b5247-119">备注</span><span class="sxs-lookup"><span data-stu-id="b5247-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5247-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b5247-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b5247-121">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-121">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-122">XMPP 代理服务（与访问边缘服务共享 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b5247-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b5247-123">XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="b5247-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b5247-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b5247-125">XMPP 代理服务（与访问边缘服务共享 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b5247-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b5247-126">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-126">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-127">XMPP 代理服务向定义的 XMPP 联合中的 XMPP 联系人发送流量</span><span class="sxs-lookup"><span data-stu-id="b5247-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b5247-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b5247-129">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-130">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-130">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-131">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="b5247-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-132">访问/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="b5247-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="b5247-133">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-134">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-134">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-135">通过 TCP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="b5247-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-136">访问/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="b5247-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="b5247-137">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-138">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-138">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-139">通过 UDP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="b5247-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-140">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b5247-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b5247-141">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-141">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-142">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-143">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="b5247-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-144">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b5247-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b5247-145">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-145">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-146">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-147">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b5247-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-148">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b5247-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b5247-149">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-150">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-150">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-151">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b5247-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-152">Web 会议/PSOM （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b5247-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b5247-153">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-153">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-154">边缘服务器 Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-155">Web 会议媒体</span><span class="sxs-lookup"><span data-stu-id="b5247-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-156">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b5247-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b5247-157">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-158">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-158">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-159">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</span><span class="sxs-lookup"><span data-stu-id="b5247-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-160">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b5247-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b5247-161">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-162">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-162">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-163">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="b5247-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-164">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b5247-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b5247-165">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-165">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-166">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-167">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="b5247-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-168">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b5247-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b5247-169">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-169">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-170">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-171">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="b5247-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-172">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b5247-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b5247-173">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-174">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-174">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-175">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="b5247-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="b5247-176">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</span><span class="sxs-lookup"><span data-stu-id="b5247-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-177">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b5247-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b5247-178">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-178">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-179">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-180">通过 UDP/3478 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="b5247-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b5247-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b5247-182">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-182">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-183">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-184">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="b5247-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-185">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b5247-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b5247-186">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-187">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-187">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-188">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="b5247-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="b5247-189">扩展的合并边缘的防火墙摘要，使用 NAT 的专用 IP 地址进行 DNS 负载平衡： Internal Interface – Node 1 和 Node 2 （示例）</span><span class="sxs-lookup"><span data-stu-id="b5247-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5247-190">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b5247-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b5247-191">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-191">Source IP address</span></span></th>
<th><span data-ttu-id="b5247-192">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-192">Destination IP address</span></span></th>
<th><span data-ttu-id="b5247-193">注释</span><span class="sxs-lookup"><span data-stu-id="b5247-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5247-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b5247-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b5247-195">Any （可定义为前端服务器地址，或运行 XMPP 网关服务的前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b5247-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="b5247-196">边缘服务器内部接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b5247-197">来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="b5247-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b5247-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b5247-199">Any （可定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b5247-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b5247-200">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-201">出站 SIP 流量（从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）到边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b5247-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b5247-203">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-204">Any （可定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b5247-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b5247-205">来自边缘服务器内部接口的入站 SIP 流量（到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b5247-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="b5247-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="b5247-207">Any （可定义为前端服务器 IP 地址，或在前端池中的每个前端服务器 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b5247-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="b5247-208">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-209">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="b5247-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="b5247-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="b5247-211">Any （可定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器）</span><span class="sxs-lookup"><span data-stu-id="b5247-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="b5247-212">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-213">使用此边缘服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支机构或 Survivable 分支服务器对 A/V 用户（A/V 身份验证服务）进行身份验证</span><span class="sxs-lookup"><span data-stu-id="b5247-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b5247-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b5247-215">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-215">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-216">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-217">内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="b5247-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b5247-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b5247-219">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-219">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-220">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-221">内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="b5247-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b5247-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b5247-223">Any （可定义为前端服务器 IP 地址或拥有中央管理存储的池）</span><span class="sxs-lookup"><span data-stu-id="b5247-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="b5247-224">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-225">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b5247-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b5247-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b5247-227">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-227">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-228">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-229">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="b5247-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b5247-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b5247-231">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-231">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-232">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-233">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="b5247-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b5247-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b5247-235">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-235">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-236">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="b5247-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b5247-237">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="b5247-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="b5247-238">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="b5247-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5247-239">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b5247-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b5247-240">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-240">Source IP address</span></span></th>
<th><span data-ttu-id="b5247-241">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-241">Destination IP address</span></span></th>
<th><span data-ttu-id="b5247-242">备注</span><span class="sxs-lookup"><span data-stu-id="b5247-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5247-243">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b5247-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b5247-244">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b5247-245">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-245">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-246">用于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b5247-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b5247-247">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="b5247-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5247-248">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b5247-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b5247-249">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-249">Source IP address</span></span></th>
<th><span data-ttu-id="b5247-250">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-250">Destination IP address</span></span></th>
<th><span data-ttu-id="b5247-251">备注</span><span class="sxs-lookup"><span data-stu-id="b5247-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5247-252">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b5247-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b5247-253">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b5247-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b5247-254">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-255">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b5247-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-256">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b5247-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b5247-257">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-258">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b5247-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b5247-259">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b5247-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-260">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b5247-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b5247-261">客户端</span><span class="sxs-lookup"><span data-stu-id="b5247-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="b5247-262">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-263">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="b5247-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-264">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b5247-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b5247-265">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-266">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="b5247-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b5247-267">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="b5247-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b5247-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b5247-269">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-270">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="b5247-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b5247-271">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b5247-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-272">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b5247-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b5247-273">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="b5247-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b5247-274">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b5247-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b5247-275">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b5247-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="b5247-276">可扩展消息传递和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="b5247-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5247-277">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b5247-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b5247-278">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b5247-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="b5247-279">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="b5247-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="b5247-280">注释</span><span class="sxs-lookup"><span data-stu-id="b5247-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5247-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b5247-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b5247-282">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-282">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-283">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b5247-284">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="b5247-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b5247-285">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="b5247-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5247-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b5247-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b5247-287">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b5247-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b5247-288">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-288">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-289">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="b5247-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b5247-290">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="b5247-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5247-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b5247-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b5247-292">任意</span><span class="sxs-lookup"><span data-stu-id="b5247-292">Any</span></span></p></td>
<td><p><span data-ttu-id="b5247-293">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="b5247-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="b5247-294">从前端服务器或前端池上的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="b5247-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

