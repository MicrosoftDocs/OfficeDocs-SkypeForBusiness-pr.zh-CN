---
title: Lync Server 2013：端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2095df7ebd68265d135a8b174ce2d1d3ae76ca5d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="8e034-102">Lync Server 2013 中的端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8e034-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e034-103">_**主题上次修改时间:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="8e034-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="8e034-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能非常类似于 Lync Server 2010 中实现的功能。</span><span class="sxs-lookup"><span data-stu-id="8e034-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="8e034-105">最显著的相加是针对可扩展消息和状态协议 (XMPP) 的 TCP 条目的端口**5269** 。</span><span class="sxs-lookup"><span data-stu-id="8e034-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="8e034-106">Lync Server 2013 (可选) 在 Edge 服务器或边缘池以及前端服务器或前端池中的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="8e034-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="8e034-107">除了 IPv4, Edge 服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="8e034-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="8e034-108">为了清楚起见, 方案中仅使用了 IPv4。</span><span class="sxs-lookup"><span data-stu-id="8e034-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="8e034-109">**用于缩放合并边缘的企业外围网络, 具有公共 IP 地址的 DNS 负载平衡**</span><span class="sxs-lookup"><span data-stu-id="8e034-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="8e034-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="8e034-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="8e034-111">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="8e034-111">Port and Protocol Details</span></span>

<span data-ttu-id="8e034-112">建议你仅打开支持你为其提供外部访问的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="8e034-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="8e034-113">若要使远程访问适用于任何 edge 服务, 必须确保 SIP 流量可以双向排列, 如入站/出站边缘流量图中所示。</span><span class="sxs-lookup"><span data-stu-id="8e034-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="8e034-114">另一种方法是, 在即时消息 (IM)、状态、web 会议、音频/视频 (A/V) 和联合身份验证中涉及到和发送来自访问边缘服务的 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="8e034-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="8e034-115">用于缩放后的合并边缘的防火墙摘要、具有公共 IP 地址的 DNS 负载平衡: 外部接口-节点1和节点 2 (示例)</span><span class="sxs-lookup"><span data-stu-id="8e034-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e034-116">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="8e034-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8e034-117">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-117">Source IP address</span></span></th>
<th><span data-ttu-id="8e034-118">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-118">Destination IP address</span></span></th>
<th><span data-ttu-id="8e034-119">备注</span><span class="sxs-lookup"><span data-stu-id="8e034-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e034-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8e034-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8e034-121">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-121">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-122">XMPP 代理服务 (使用 Access Edge 服务共享 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="8e034-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="8e034-123">XMPP 代理服务接受来自定义的 XMPP 联合的 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="8e034-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="8e034-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="8e034-125">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-126">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-126">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-127">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="8e034-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="8e034-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="8e034-129">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-130">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-130">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-131">通过 TCP 进行 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="8e034-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="8e034-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="8e034-133">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-134">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-134">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-135">通过 UDP 进行 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="8e034-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-136">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8e034-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8e034-137">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-137">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-138">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-139">用于外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="8e034-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-140">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8e034-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8e034-141">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-141">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-142">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-143">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="8e034-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-144">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8e034-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8e034-145">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-146">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-146">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-147">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="8e034-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-148">网络会议/PSOM (TLS) TCP/443</span><span class="sxs-lookup"><span data-stu-id="8e034-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8e034-149">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-149">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-150">Edge 服务器 Web 会议边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-151">网络会议媒体</span><span class="sxs-lookup"><span data-stu-id="8e034-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8e034-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8e034-153">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-154">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-154">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-155">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟所必需。</span><span class="sxs-lookup"><span data-stu-id="8e034-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8e034-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8e034-157">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-158">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-158">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-159">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所必需。</span><span class="sxs-lookup"><span data-stu-id="8e034-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8e034-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8e034-161">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-161">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-162">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-163">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</span><span class="sxs-lookup"><span data-stu-id="8e034-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8e034-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8e034-165">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-165">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-166">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-167">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</span><span class="sxs-lookup"><span data-stu-id="8e034-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8e034-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8e034-169">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-170">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-170">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-171">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="8e034-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="8e034-172">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟, 以及在公司内部部署了多个边缘池的情况下, 也是必需的。</span><span class="sxs-lookup"><span data-stu-id="8e034-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8e034-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8e034-174">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-174">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-175">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-176">通过 UDP/3478 对候选人的 STUN 进行协商/启用</span><span class="sxs-lookup"><span data-stu-id="8e034-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8e034-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8e034-178">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-178">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-179">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-180">在 TCP/443 上 STUN/打开候选人的协商</span><span class="sxs-lookup"><span data-stu-id="8e034-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8e034-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8e034-182">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="8e034-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8e034-183">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-183">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-184">在 TCP/443 上 STUN/打开候选人的协商</span><span class="sxs-lookup"><span data-stu-id="8e034-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="8e034-185">用于缩放后的合并边缘的防火墙摘要、具有公共 IP 地址的 DNS 负载平衡: 内部接口-节点1和节点 2 (示例)</span><span class="sxs-lookup"><span data-stu-id="8e034-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e034-186">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="8e034-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8e034-187">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-187">Source IP address</span></span></th>
<th><span data-ttu-id="8e034-188">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-188">Destination IP address</span></span></th>
<th><span data-ttu-id="8e034-189">备注</span><span class="sxs-lookup"><span data-stu-id="8e034-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e034-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8e034-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8e034-191">任何 (可以定义为前端服务器地址, 或运行 XMPP 网关服务的前端池 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="8e034-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="8e034-192">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-193">来自前端服务器或前端池运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="8e034-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8e034-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8e034-195">任何 (可以定义为 Director、Director pool IP 地址、前端服务器或前端池 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="8e034-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="8e034-196">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-197">出站 SIP 流量 (从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 到边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8e034-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8e034-199">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-200">任何 (可以定义为 Director、Director pool IP 地址、前端服务器或前端池 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="8e034-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="8e034-201">来自边缘服务器内部接口的入站 SIP 流量 (到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="8e034-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="8e034-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="8e034-203">任何 (可以定义为前端服务器 IP 地址, 或前端池中的每个前端服务器 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="8e034-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="8e034-204">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-205">从前端服务器或每台前端服务器 (如果在池中) 到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="8e034-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="8e034-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="8e034-207">任何 (可以定义为前端服务器 IP 地址或前端池 IP 地址, 或使用此 Edge 服务器的任何 Survivable 分支装置或 Survivable 分支服务器)</span><span class="sxs-lookup"><span data-stu-id="8e034-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="8e034-208">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-209">使用此 Edge 服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支装置或 Survivable 分支服务器身份验证 A/V 用户 (A/V 身份验证服务) 的身份验证</span><span class="sxs-lookup"><span data-stu-id="8e034-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8e034-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8e034-211">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-211">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-212">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-213">内部和外部用户之间的/V 媒体传输的首选路径, Survivable 分支装置或 Survivable 分支服务器</span><span class="sxs-lookup"><span data-stu-id="8e034-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8e034-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8e034-215">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-215">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-216">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-217">内部和外部用户、Survivable 分支装置或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信, 则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="8e034-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="8e034-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="8e034-219">任何 (可以定义为前端服务器 IP 地址或拥有中央管理存储的池)</span><span class="sxs-lookup"><span data-stu-id="8e034-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="8e034-220">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-221">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="8e034-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="8e034-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="8e034-223">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-223">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-224">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-225">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="8e034-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="8e034-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="8e034-227">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-227">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-228">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-229">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="8e034-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="8e034-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="8e034-231">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-231">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-232">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="8e034-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8e034-233">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="8e034-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="8e034-234">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="8e034-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e034-235">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="8e034-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8e034-236">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-236">Source IP address</span></span></th>
<th><span data-ttu-id="8e034-237">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-237">Destination IP address</span></span></th>
<th><span data-ttu-id="8e034-238">备注</span><span class="sxs-lookup"><span data-stu-id="8e034-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e034-239">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8e034-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8e034-240">Access Edge 服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-241">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-241">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-242">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="8e034-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="8e034-243">防火墙摘要-公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="8e034-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e034-244">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="8e034-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8e034-245">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-245">Source IP address</span></span></th>
<th><span data-ttu-id="8e034-246">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-246">Destination IP address</span></span></th>
<th><span data-ttu-id="8e034-247">备注</span><span class="sxs-lookup"><span data-stu-id="8e034-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e034-248">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8e034-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8e034-249">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="8e034-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8e034-250">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="8e034-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8e034-251">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="8e034-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-252">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8e034-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8e034-253">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="8e034-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8e034-254">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="8e034-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8e034-255">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="8e034-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-256">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8e034-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8e034-257">客户端</span><span class="sxs-lookup"><span data-stu-id="8e034-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="8e034-258">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="8e034-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8e034-259">用于外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="8e034-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8e034-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8e034-261">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="8e034-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8e034-262">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="8e034-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8e034-263">如果配置了公用 IM 连接, 则用于带有 Windows Live Messenger 的 A/V 会话。</span><span class="sxs-lookup"><span data-stu-id="8e034-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8e034-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8e034-265">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="8e034-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8e034-266">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="8e034-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8e034-267">与 Windows Live Messenger 的公共即时消息连接所必需</span><span class="sxs-lookup"><span data-stu-id="8e034-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8e034-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8e034-269">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="8e034-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8e034-270">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="8e034-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8e034-271">与 Windows Live Messenger 的公共即时消息连接所必需</span><span class="sxs-lookup"><span data-stu-id="8e034-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="8e034-272">可扩展消息和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="8e034-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e034-273">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="8e034-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8e034-274">源 (IP 地址)</span><span class="sxs-lookup"><span data-stu-id="8e034-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="8e034-275">目标 (IP 地址)</span><span class="sxs-lookup"><span data-stu-id="8e034-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="8e034-276">备注</span><span class="sxs-lookup"><span data-stu-id="8e034-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e034-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8e034-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8e034-278">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-278">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-279">Edge 服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-280">适用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="8e034-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8e034-281">允许与联盟 XMPP 合作伙伴的 Edge 服务器 XMPP 代理通信</span><span class="sxs-lookup"><span data-stu-id="8e034-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e034-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8e034-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8e034-283">Edge 服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8e034-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8e034-284">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-284">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-285">适用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="8e034-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8e034-286">允许从 Edge 服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="8e034-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e034-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8e034-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8e034-288">任意</span><span class="sxs-lookup"><span data-stu-id="8e034-288">Any</span></span></p></td>
<td><p><span data-ttu-id="8e034-289">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="8e034-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="8e034-290">从前端服务器或前端池中的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="8e034-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

