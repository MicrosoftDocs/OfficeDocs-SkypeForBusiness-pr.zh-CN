---
title: Lync Server 2013：端口摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）
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
ms.openlocfilehash: 20071cba55551a42ea6406723bb1f9ed55853afa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="cf2a5-102">Lync Server 2013 中的端口摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf2a5-103">_**主题上次修改时间：** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="cf2a5-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="cf2a5-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能非常类似于 Lync Server 2010 中实现的功能。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="cf2a5-105">最显著的相加是针对可扩展消息和状态协议（XMPP）的 TCP 条目的端口**5269** 。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="cf2a5-106">Lync Server 2013 （可选）在 Edge 服务器或边缘池以及前端服务器或前端池中的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="cf2a5-107">除了 IPv4，Edge 服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="cf2a5-108">为了清楚起见，方案中仅使用了 IPv4。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="cf2a5-109">**使用 NAT 使用专用 IP 地址缩放合并边缘的企业外围网络**</span><span class="sxs-lookup"><span data-stu-id="cf2a5-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="cf2a5-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="cf2a5-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="cf2a5-111">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="cf2a5-111">Port and Protocol Details</span></span>

<span data-ttu-id="cf2a5-112">建议你仅打开支持你为其提供外部访问的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="cf2a5-113">若要使远程访问适用于任何 edge 服务，必须确保 SIP 流量可以双向排列，如入站/出站边缘流量图中所示。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="cf2a5-114">另一种方法是，在即时消息（IM）、状态、web 会议、音频/视频（A/V）和联合身份验证中涉及到和发送来自访问边缘服务的 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="cf2a5-115">用于缩放后的合并边缘的防火墙摘要、使用 NAT 的专用 IP 地址的 DNS 负载平衡：外部接口-节点1和节点2（示例）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf2a5-116">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf2a5-117">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-117">Source IP address</span></span></th>
<th><span data-ttu-id="cf2a5-118">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-118">Destination IP address</span></span></th>
<th><span data-ttu-id="cf2a5-119">备注</span><span class="sxs-lookup"><span data-stu-id="cf2a5-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf2a5-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-121">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-121">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-122">XMPP 代理服务（使用 Access Edge 服务共享 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-123">XMPP 代理服务接受来自定义的 XMPP 联合的 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="cf2a5-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf2a5-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-125">XMPP 代理服务（使用 Access Edge 服务共享 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-126">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-126">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-127">XMPP 代理服务将流量发送到定义的 XMPP 联合体中的 XMPP 联系人</span><span class="sxs-lookup"><span data-stu-id="cf2a5-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="cf2a5-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-129">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-130">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-130">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-131">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="cf2a5-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="cf2a5-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-133">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-134">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-134">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-135">通过 TCP 进行 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="cf2a5-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="cf2a5-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-137">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-138">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-138">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-139">通过 UDP 进行 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="cf2a5-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-140">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf2a5-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-141">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-141">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-142">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-143">用于外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="cf2a5-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-144">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf2a5-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-145">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-145">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-146">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-147">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="cf2a5-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-148">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf2a5-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-149">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-150">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-150">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-151">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="cf2a5-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-152">Web 会议/PSOM （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf2a5-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-153">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-153">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-154">Edge 服务器 Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-155">网络会议媒体</span><span class="sxs-lookup"><span data-stu-id="cf2a5-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-156">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf2a5-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-157">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-158">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-158">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-159">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟所必需。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-160">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf2a5-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-161">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-162">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-162">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-163">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所必需。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-164">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf2a5-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-165">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-165">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-166">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-167">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</span><span class="sxs-lookup"><span data-stu-id="cf2a5-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-168">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf2a5-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-169">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-169">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-170">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-171">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</span><span class="sxs-lookup"><span data-stu-id="cf2a5-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-172">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf2a5-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-173">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-174">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-174">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-175">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="cf2a5-176">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司内部部署了多个边缘池的情况下，也是必需的。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-177">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf2a5-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-178">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-178">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-179">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-180">通过 UDP/3478 对候选人的 STUN 进行协商/启用</span><span class="sxs-lookup"><span data-stu-id="cf2a5-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf2a5-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-182">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-182">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-183">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-184">在 TCP/443 上 STUN/打开候选人的协商</span><span class="sxs-lookup"><span data-stu-id="cf2a5-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-185">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf2a5-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-186">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-187">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-187">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-188">在 TCP/443 上 STUN/打开候选人的协商</span><span class="sxs-lookup"><span data-stu-id="cf2a5-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="cf2a5-189">用于缩放后的合并边缘的防火墙摘要、使用 NAT 的专用 IP 地址的 DNS 负载平衡：内部接口-节点1和节点2（示例）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf2a5-190">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf2a5-191">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-191">Source IP address</span></span></th>
<th><span data-ttu-id="cf2a5-192">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-192">Destination IP address</span></span></th>
<th><span data-ttu-id="cf2a5-193">备注</span><span class="sxs-lookup"><span data-stu-id="cf2a5-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="cf2a5-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-195">任何（可以定义为前端服务器地址，或运行 XMPP 网关服务的前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-196">边缘服务器内部接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-197">来自前端服务器或前端池运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="cf2a5-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf2a5-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-199">任何（可以定义为 Director、Director pool IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-200">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-201">出站 SIP 流量（从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）到边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf2a5-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-203">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-204">任何（可以定义为 Director、Director pool IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-205">来自边缘服务器内部接口的入站 SIP 流量（到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="cf2a5-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-207">任何（可以定义为前端服务器 IP 地址，或前端池中的每个前端服务器 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-208">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-209">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="cf2a5-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="cf2a5-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-211">任何（可以定义为前端服务器 IP 地址或前端池 IP 地址，或使用此 Edge 服务器的任何 Survivable 分支装置或 Survivable 分支服务器）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-212">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-213">使用此 Edge 服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支装置或 Survivable 分支服务器身份验证 A/V 用户（A/V 身份验证服务）的身份验证</span><span class="sxs-lookup"><span data-stu-id="cf2a5-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf2a5-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-215">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-215">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-216">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-217">内部和外部用户之间的/V 媒体传输的首选路径，Survivable 分支装置或 Survivable 分支服务器</span><span class="sxs-lookup"><span data-stu-id="cf2a5-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf2a5-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-219">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-219">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-220">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-221">内部和外部用户、Survivable 分支装置或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="cf2a5-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="cf2a5-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-223">任何（可以定义为前端服务器 IP 地址或拥有中央管理存储的池）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-224">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-225">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="cf2a5-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="cf2a5-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-227">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-227">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-228">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-229">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="cf2a5-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="cf2a5-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-231">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-231">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-232">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-233">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="cf2a5-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="cf2a5-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-235">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-235">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-236">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-237">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="cf2a5-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="cf2a5-238">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="cf2a5-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf2a5-239">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf2a5-240">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-240">Source IP address</span></span></th>
<th><span data-ttu-id="cf2a5-241">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-241">Destination IP address</span></span></th>
<th><span data-ttu-id="cf2a5-242">备注</span><span class="sxs-lookup"><span data-stu-id="cf2a5-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-243">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf2a5-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-244">Access Edge 服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-245">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-245">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-246">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="cf2a5-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="cf2a5-247">防火墙摘要-公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="cf2a5-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf2a5-248">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf2a5-249">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-249">Source IP address</span></span></th>
<th><span data-ttu-id="cf2a5-250">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-250">Destination IP address</span></span></th>
<th><span data-ttu-id="cf2a5-251">备注</span><span class="sxs-lookup"><span data-stu-id="cf2a5-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-252">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf2a5-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-253">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="cf2a5-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-254">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-255">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="cf2a5-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-256">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf2a5-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-257">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-258">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="cf2a5-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-259">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="cf2a5-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-260">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf2a5-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-261">客户端</span><span class="sxs-lookup"><span data-stu-id="cf2a5-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-262">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-263">用于外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="cf2a5-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-264">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf2a5-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-265">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-266">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="cf2a5-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-267">如果配置了公用 IM 连接，则用于带有 Windows Live Messenger 的 A/V 会话。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf2a5-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-269">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-270">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="cf2a5-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-271">与 Windows Live Messenger 的公共即时消息连接所必需</span><span class="sxs-lookup"><span data-stu-id="cf2a5-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-272">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf2a5-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-273">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="cf2a5-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-274">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="cf2a5-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-275">与 Windows Live Messenger 的公共即时消息连接所必需</span><span class="sxs-lookup"><span data-stu-id="cf2a5-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="cf2a5-276">可扩展消息和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="cf2a5-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf2a5-277">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="cf2a5-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf2a5-278">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="cf2a5-279">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="cf2a5-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="cf2a5-280">备注</span><span class="sxs-lookup"><span data-stu-id="cf2a5-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf2a5-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-282">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-282">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-283">Edge 服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-284">适用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cf2a5-285">允许与联盟 XMPP 合作伙伴的 Edge 服务器 XMPP 代理通信</span><span class="sxs-lookup"><span data-stu-id="cf2a5-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf2a5-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf2a5-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-287">Edge 服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cf2a5-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-288">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-288">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-289">适用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="cf2a5-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cf2a5-290">允许从 Edge 服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="cf2a5-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf2a5-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="cf2a5-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-292">任意</span><span class="sxs-lookup"><span data-stu-id="cf2a5-292">Any</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-293">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="cf2a5-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="cf2a5-294">从前端服务器或前端池中的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="cf2a5-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

