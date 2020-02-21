---
title: 端口摘要-使用 NAT 的具有专用 IP 地址的单一合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 870732df847d589ebb24751977babc8182d79a3f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="11bae-102">Lync Server 2013 中的端口摘要-使用 NAT 的具有专用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="11bae-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11bae-103">_**上次修改的主题：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="11bae-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="11bae-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。</span><span class="sxs-lookup"><span data-stu-id="11bae-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="11bae-105">最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。</span><span class="sxs-lookup"><span data-stu-id="11bae-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="11bae-106">Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="11bae-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="11bae-107">除 IPv4 外，边缘服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="11bae-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="11bae-108">为了清楚起见，本方案中仅使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="11bae-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="11bae-109">**具有使用 NAT 的专用 IP 寻址的单个合并边缘服务器的网络外围**</span><span class="sxs-lookup"><span data-stu-id="11bae-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="11bae-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="11bae-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="11bae-111">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="11bae-111">Port and Protocol Details</span></span>

<span data-ttu-id="11bae-112">我们建议您仅打开支持为其提供外部访问权限的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="11bae-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="11bae-113">要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。</span><span class="sxs-lookup"><span data-stu-id="11bae-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="11bae-114">另一种方法是，即时消息（IM）、状态、web 会议、音频/视频（A/V）和联合身份验证发件人和来自访问边缘服务的 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="11bae-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="11bae-115">具有使用 NAT 的专用 IP 地址的单一合并边缘的防火墙摘要：外部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11bae-116">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="11bae-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11bae-117">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-117">Source IP address</span></span></th>
<th><span data-ttu-id="11bae-118">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-118">Destination IP address</span></span></th>
<th><span data-ttu-id="11bae-119">备注</span><span class="sxs-lookup"><span data-stu-id="11bae-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11bae-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="11bae-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="11bae-121">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-121">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-122">XMPP 代理服务（与访问边缘服务共享 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="11bae-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="11bae-123">XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="11bae-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="11bae-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="11bae-125">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-126">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-126">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-127">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="11bae-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-128">访问/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="11bae-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="11bae-129">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-130">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-130">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-131">通过 TCP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="11bae-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-132">访问/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="11bae-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="11bae-133">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-134">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-134">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-135">通过 UDP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="11bae-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-136">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11bae-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11bae-137">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-137">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-138">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-139">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="11bae-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-140">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11bae-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11bae-141">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-141">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-142">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-143">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="11bae-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-144">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11bae-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11bae-145">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-146">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-146">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-147">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="11bae-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-148">Web 会议/PSOM （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11bae-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11bae-149">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-149">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-150">边缘服务器 Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-151">Web 会议媒体</span><span class="sxs-lookup"><span data-stu-id="11bae-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="11bae-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11bae-153">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-154">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-154">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-155">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</span><span class="sxs-lookup"><span data-stu-id="11bae-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="11bae-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11bae-157">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-158">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-158">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-159">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="11bae-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="11bae-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11bae-161">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-161">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-162">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-163">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="11bae-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="11bae-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11bae-165">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-165">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-166">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-167">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="11bae-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11bae-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11bae-169">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-170">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-170">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-171">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="11bae-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="11bae-172">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</span><span class="sxs-lookup"><span data-stu-id="11bae-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11bae-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11bae-174">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-174">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-175">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-176">通过 UDP/3478 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="11bae-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11bae-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11bae-178">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-178">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-179">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-180">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="11bae-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11bae-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11bae-182">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-183">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-183">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-184">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="11bae-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="11bae-185">具有使用 NAT 的专用 IP 地址的单一合并边缘的防火墙摘要： Internal 接口</span><span class="sxs-lookup"><span data-stu-id="11bae-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11bae-186">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="11bae-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11bae-187">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-187">Source IP address</span></span></th>
<th><span data-ttu-id="11bae-188">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-188">Destination IP address</span></span></th>
<th><span data-ttu-id="11bae-189">注释</span><span class="sxs-lookup"><span data-stu-id="11bae-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11bae-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="11bae-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="11bae-191">Any （可定义为 Standard Edition server IP、Standard Edition server IP 地址或运行 XMPP 网关服务的池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="11bae-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="11bae-192">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-193">来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="11bae-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11bae-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11bae-195">Any （可定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="11bae-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="11bae-196">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-197">出站 SIP 流量（从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）到边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11bae-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11bae-199">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-200">Any （可定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="11bae-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="11bae-201">来自边缘服务器内部接口的入站 SIP 流量（到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="11bae-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="11bae-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="11bae-203">Any （可定义为前端服务器 IP 地址，或在前端池中的每个前端服务器 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="11bae-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="11bae-204">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-205">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="11bae-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="11bae-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="11bae-207">Any （可定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器）</span><span class="sxs-lookup"><span data-stu-id="11bae-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="11bae-208">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-209">使用此边缘服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支机构或 Survivable 分支服务器对 A/V 用户（A/V 身份验证服务）进行身份验证</span><span class="sxs-lookup"><span data-stu-id="11bae-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11bae-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11bae-211">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-211">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-212">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-213">内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="11bae-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11bae-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11bae-215">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-215">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-216">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-217">内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="11bae-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="11bae-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="11bae-219">Any （可定义为前端服务器 IP 地址或拥有中央管理存储的池）</span><span class="sxs-lookup"><span data-stu-id="11bae-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="11bae-220">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-221">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="11bae-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="11bae-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="11bae-223">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-223">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-224">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-225">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="11bae-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="11bae-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="11bae-227">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-227">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-228">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-229">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="11bae-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="11bae-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="11bae-231">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-231">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-232">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="11bae-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11bae-233">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="11bae-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="11bae-234">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="11bae-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11bae-235">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="11bae-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11bae-236">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-236">Source IP address</span></span></th>
<th><span data-ttu-id="11bae-237">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-237">Destination IP address</span></span></th>
<th><span data-ttu-id="11bae-238">备注</span><span class="sxs-lookup"><span data-stu-id="11bae-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11bae-239">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11bae-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11bae-240">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="11bae-241">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-241">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-242">用于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="11bae-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="11bae-243">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="11bae-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11bae-244">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="11bae-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11bae-245">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-245">Source IP address</span></span></th>
<th><span data-ttu-id="11bae-246">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-246">Destination IP address</span></span></th>
<th><span data-ttu-id="11bae-247">备注</span><span class="sxs-lookup"><span data-stu-id="11bae-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11bae-248">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11bae-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11bae-249">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="11bae-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="11bae-250">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-251">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="11bae-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-252">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11bae-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11bae-253">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-254">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="11bae-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="11bae-255">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="11bae-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-256">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11bae-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11bae-257">客户端</span><span class="sxs-lookup"><span data-stu-id="11bae-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="11bae-258">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-259">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="11bae-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="11bae-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11bae-261">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-262">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="11bae-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="11bae-263">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="11bae-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11bae-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11bae-265">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-266">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="11bae-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="11bae-267">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="11bae-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11bae-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11bae-269">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="11bae-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="11bae-270">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="11bae-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11bae-271">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="11bae-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="11bae-272">可扩展消息传递和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="11bae-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11bae-273">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="11bae-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11bae-274">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="11bae-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="11bae-275">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="11bae-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="11bae-276">注释</span><span class="sxs-lookup"><span data-stu-id="11bae-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11bae-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="11bae-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="11bae-278">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-278">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-279">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="11bae-280">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="11bae-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="11bae-281">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="11bae-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bae-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="11bae-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="11bae-283">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11bae-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="11bae-284">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-284">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-285">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="11bae-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="11bae-286">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="11bae-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bae-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="11bae-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="11bae-288">任意</span><span class="sxs-lookup"><span data-stu-id="11bae-288">Any</span></span></p></td>
<td><p><span data-ttu-id="11bae-289">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="11bae-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="11bae-290">从前端服务器或前端池上的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="11bae-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

