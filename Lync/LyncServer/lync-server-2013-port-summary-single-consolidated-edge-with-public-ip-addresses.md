---
title: 端口摘要 - 使用公用 IP 地址的单一合并边缘
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
ms.openlocfilehash: 7ad4d6dc9b7eda2e476068d5fae4a40d066a0d71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="46ecc-102">Lync Server 2013 中的端口摘要 - 使用公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="46ecc-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46ecc-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="46ecc-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="46ecc-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能非常类似于 Lync Server 2010 中实现的功能。</span><span class="sxs-lookup"><span data-stu-id="46ecc-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="46ecc-105">最显著的相加是针对可扩展消息和状态协议（XMPP）的 TCP 条目的端口**5269** 。</span><span class="sxs-lookup"><span data-stu-id="46ecc-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="46ecc-106">Lync Server 2013 （可选）在 Edge 服务器或边缘池以及前端服务器或前端池中的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="46ecc-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="46ecc-107">在[lync server 2013 中的反向代理](lync-server-2013-scenarios-for-reverse-proxy.md)和在[lync server 2013 部分中规划 SIP、XMPP 联盟和公共即时消息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)的方案中，可以找到反向代理和联合的规划信息。</span><span class="sxs-lookup"><span data-stu-id="46ecc-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="46ecc-108">除了 IPv4，Edge 服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="46ecc-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="46ecc-109">为了清楚起见，方案中仅使用了 IPv4。</span><span class="sxs-lookup"><span data-stu-id="46ecc-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="46ecc-110">**具有公共 IP 寻址的单个统一边缘的企业外围网络**</span><span class="sxs-lookup"><span data-stu-id="46ecc-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="46ecc-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="46ecc-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="46ecc-112">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="46ecc-112">Port and Protocol Details</span></span>

<span data-ttu-id="46ecc-113">我们建议你仅打开支持你为其提供外部访问的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="46ecc-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="46ecc-114">若要使远程访问适用于任何 edge 服务，必须确保 SIP 流量能够流过 bidirectionally，如入站/出站边缘流量图所示。</span><span class="sxs-lookup"><span data-stu-id="46ecc-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="46ecc-115">另一种方法是，在即时消息（IM）、状态、web 会议、音频/视频（A/V）和联合身份验证中涉及到和发送来自访问边缘服务的 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="46ecc-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="46ecc-116">具有公共 IP 地址的单个统一边缘的防火墙摘要：外部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ecc-117">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="46ecc-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46ecc-118">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-118">Source IP address</span></span></th>
<th><span data-ttu-id="46ecc-119">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-119">Destination IP address</span></span></th>
<th><span data-ttu-id="46ecc-120">备注</span><span class="sxs-lookup"><span data-stu-id="46ecc-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="46ecc-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="46ecc-122">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-122">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-123">XMPP 代理服务（使用 Access Edge 服务共享 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="46ecc-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="46ecc-124">XMPP 代理服务接受来自定义的 XMPP 联合的 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="46ecc-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="46ecc-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="46ecc-126">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-127">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-127">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-128">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="46ecc-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="46ecc-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="46ecc-130">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-131">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-131">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-132">通过 TCP 进行 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="46ecc-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="46ecc-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="46ecc-134">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-135">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-135">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-136">通过 UDP 进行 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="46ecc-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-137">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46ecc-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46ecc-138">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-138">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-139">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-140">用于外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="46ecc-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-141">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46ecc-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46ecc-142">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-142">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-143">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-144">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="46ecc-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-145">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46ecc-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46ecc-146">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-147">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-147">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-148">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="46ecc-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-149">Web 会议/PSOM （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46ecc-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46ecc-150">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-150">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-151">Edge 服务器 Web 会议边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-152">网络会议媒体</span><span class="sxs-lookup"><span data-stu-id="46ecc-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-153">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="46ecc-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46ecc-154">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-155">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-155">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-156">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟所必需。</span><span class="sxs-lookup"><span data-stu-id="46ecc-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-157">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="46ecc-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46ecc-158">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-159">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-159">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-160">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</span><span class="sxs-lookup"><span data-stu-id="46ecc-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-161">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="46ecc-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46ecc-162">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-162">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-163">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-164">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所必需。</span><span class="sxs-lookup"><span data-stu-id="46ecc-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-165">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="46ecc-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46ecc-166">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-166">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-167">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-168">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所必需。</span><span class="sxs-lookup"><span data-stu-id="46ecc-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-169">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46ecc-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46ecc-170">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-171">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-171">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-172">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="46ecc-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="46ecc-173">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司内部部署了多个边缘池的情况下，也是必需的。</span><span class="sxs-lookup"><span data-stu-id="46ecc-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-174">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46ecc-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46ecc-175">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-175">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-176">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-177">通过 UDP/3478 对候选人的 STUN 进行协商/启用</span><span class="sxs-lookup"><span data-stu-id="46ecc-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-178">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46ecc-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46ecc-179">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-179">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-180">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-181">在 TCP/443 上 STUN/打开候选人的协商</span><span class="sxs-lookup"><span data-stu-id="46ecc-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-182">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46ecc-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46ecc-183">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-184">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-184">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-185">在 TCP/443 上 STUN/打开候选人的协商</span><span class="sxs-lookup"><span data-stu-id="46ecc-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="46ecc-186">具有公共 IP 地址的单个统一边缘的防火墙摘要：内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ecc-187">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="46ecc-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46ecc-188">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-188">Source IP address</span></span></th>
<th><span data-ttu-id="46ecc-189">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-189">Destination IP address</span></span></th>
<th><span data-ttu-id="46ecc-190">备注</span><span class="sxs-lookup"><span data-stu-id="46ecc-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="46ecc-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="46ecc-192">任何（可以定义为运行 XMPP 网关服务的标准版服务器 IP、标准版服务器 IP 地址或池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="46ecc-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="46ecc-193">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-194">来自前端服务器或前端池运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="46ecc-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46ecc-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46ecc-196">任何（可以定义为 Director、Director pool IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="46ecc-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="46ecc-197">包含内部接口的边缘服务器 IP 或池</span><span class="sxs-lookup"><span data-stu-id="46ecc-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-198">出站 SIP 流量（从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）到边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46ecc-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46ecc-200">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-201">任何（可以定义为 Director、Director pool IP 地址、前端服务器或前端池地址）</span><span class="sxs-lookup"><span data-stu-id="46ecc-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="46ecc-202">来自边缘服务器内部接口的入站 SIP 流量（到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="46ecc-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="46ecc-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="46ecc-204">任何（可以定义为前端服务器 IP 地址，或前端池中的每个前端服务器 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="46ecc-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="46ecc-205">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-206">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="46ecc-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="46ecc-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="46ecc-208">任何（可以定义为前端服务器 IP 地址或前端池 IP 地址，或使用此 Edge 服务器的任何 Survivable 分支装置或 Survivable 分支服务器）</span><span class="sxs-lookup"><span data-stu-id="46ecc-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="46ecc-209">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-210">使用此 Edge 服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支装置或 Survivable 分支服务器身份验证 A/V 用户（A/V 身份验证服务）的身份验证</span><span class="sxs-lookup"><span data-stu-id="46ecc-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46ecc-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46ecc-212">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-212">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-213">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-214">内部和外部用户之间的/V 媒体传输的首选路径，Survivable 分支装置或 Survivable 分支服务器</span><span class="sxs-lookup"><span data-stu-id="46ecc-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46ecc-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46ecc-216">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-216">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-217">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-218">内部和外部用户、Survivable 分支装置或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="46ecc-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="46ecc-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="46ecc-220">任何（可以定义为前端服务器 IP 地址或拥有中央管理存储的池）</span><span class="sxs-lookup"><span data-stu-id="46ecc-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="46ecc-221">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-222">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="46ecc-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="46ecc-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="46ecc-224">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-224">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-225">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-226">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="46ecc-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="46ecc-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="46ecc-228">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-228">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-229">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-230">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="46ecc-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="46ecc-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="46ecc-232">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-232">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-233">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="46ecc-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46ecc-234">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="46ecc-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="46ecc-235">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="46ecc-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ecc-236">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="46ecc-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46ecc-237">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-237">Source IP address</span></span></th>
<th><span data-ttu-id="46ecc-238">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-238">Destination IP address</span></span></th>
<th><span data-ttu-id="46ecc-239">备注</span><span class="sxs-lookup"><span data-stu-id="46ecc-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-240">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46ecc-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46ecc-241">Access Edge 服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-242">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-242">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-243">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="46ecc-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="46ecc-244">防火墙摘要-公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="46ecc-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ecc-245">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="46ecc-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46ecc-246">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-246">Source IP address</span></span></th>
<th><span data-ttu-id="46ecc-247">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-247">Destination IP address</span></span></th>
<th><span data-ttu-id="46ecc-248">备注</span><span class="sxs-lookup"><span data-stu-id="46ecc-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-249">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46ecc-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46ecc-250">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="46ecc-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="46ecc-251">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="46ecc-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="46ecc-252">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="46ecc-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-253">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46ecc-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46ecc-254">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="46ecc-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="46ecc-255">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="46ecc-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="46ecc-256">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="46ecc-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-257">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46ecc-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46ecc-258">客户端</span><span class="sxs-lookup"><span data-stu-id="46ecc-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="46ecc-259">Edge 服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="46ecc-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="46ecc-260">用于外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="46ecc-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-261">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="46ecc-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46ecc-262">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="46ecc-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="46ecc-263">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="46ecc-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="46ecc-264">如果配置了公用 IM 连接，则用于带有 Windows Live Messenger 的 A/V 会话。</span><span class="sxs-lookup"><span data-stu-id="46ecc-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-265">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46ecc-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46ecc-266">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="46ecc-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="46ecc-267">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="46ecc-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="46ecc-268">与 Windows Live Messenger 的公共即时消息连接所必需</span><span class="sxs-lookup"><span data-stu-id="46ecc-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-269">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46ecc-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46ecc-270">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="46ecc-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="46ecc-271">Edge 服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="46ecc-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="46ecc-272">与 Windows Live Messenger 的公共即时消息连接所必需</span><span class="sxs-lookup"><span data-stu-id="46ecc-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="46ecc-273">可扩展消息和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="46ecc-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ecc-274">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="46ecc-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46ecc-275">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="46ecc-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="46ecc-276">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="46ecc-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="46ecc-277">备注</span><span class="sxs-lookup"><span data-stu-id="46ecc-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="46ecc-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="46ecc-279">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-279">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-280">Edge 服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-281">适用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="46ecc-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="46ecc-282">允许与联盟 XMPP 合作伙伴的 Edge 服务器 XMPP 代理通信</span><span class="sxs-lookup"><span data-stu-id="46ecc-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ecc-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="46ecc-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="46ecc-284">Edge 服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="46ecc-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="46ecc-285">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-285">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-286">适用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="46ecc-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="46ecc-287">允许从 Edge 服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="46ecc-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ecc-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="46ecc-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="46ecc-289">任意</span><span class="sxs-lookup"><span data-stu-id="46ecc-289">Any</span></span></p></td>
<td><p><span data-ttu-id="46ecc-290">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="46ecc-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="46ecc-291">从前端服务器或前端池中的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="46ecc-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

