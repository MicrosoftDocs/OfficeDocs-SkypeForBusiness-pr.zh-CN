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
ms.openlocfilehash: 4a5aaa4628a92174aca39579c5f2e6a8e4f31987
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533999"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="d0680-102">Lync Server 2013 中的端口摘要-使用 NAT 的具有专用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="d0680-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0680-103">_**上次修改的主题：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="d0680-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="d0680-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。</span><span class="sxs-lookup"><span data-stu-id="d0680-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="d0680-105">最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。</span><span class="sxs-lookup"><span data-stu-id="d0680-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="d0680-106">Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="d0680-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="d0680-107">除 IPv4 外，边缘服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="d0680-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="d0680-108">为了清楚起见，本方案中仅使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="d0680-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="d0680-109">**具有使用 NAT 的专用 IP 寻址的单个合并边缘服务器的网络外围**</span><span class="sxs-lookup"><span data-stu-id="d0680-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="d0680-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="d0680-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="d0680-111">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="d0680-111">Port and Protocol Details</span></span>

<span data-ttu-id="d0680-112">我们建议您仅打开支持为其提供外部访问权限的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="d0680-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="d0680-113">要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。</span><span class="sxs-lookup"><span data-stu-id="d0680-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="d0680-114">另一种方法，在即时消息 (IM) 、状态、web 会议、音频/视频 (A/V) 和联合身份验证中，与来自访问边缘服务的 SIP 消息涉及。</span><span class="sxs-lookup"><span data-stu-id="d0680-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="d0680-115">具有使用 NAT 的专用 IP 地址的单一合并边缘的防火墙摘要：外部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0680-116">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="d0680-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d0680-117">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-117">Source IP address</span></span></th>
<th><span data-ttu-id="d0680-118">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-118">Destination IP address</span></span></th>
<th><span data-ttu-id="d0680-119">注释</span><span class="sxs-lookup"><span data-stu-id="d0680-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0680-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d0680-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d0680-121">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-121">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-122">XMPP 代理服务 (与访问边缘服务共享 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="d0680-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="d0680-123">XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="d0680-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="d0680-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="d0680-125">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-126">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-126">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-127">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="d0680-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-128">访问/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="d0680-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="d0680-129">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-130">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-130">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-131">通过 TCP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="d0680-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-132">访问/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="d0680-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="d0680-133">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-134">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-134">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-135">通过 UDP 的 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="d0680-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-136">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="d0680-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d0680-137">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-137">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-138">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-139">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="d0680-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-140">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d0680-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d0680-141">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-141">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-142">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-143">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="d0680-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-144">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d0680-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d0680-145">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-146">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-146">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-147">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="d0680-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-148">Web 会议/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="d0680-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d0680-149">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-149">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-150">边缘服务器 Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-151">Web 会议媒体</span><span class="sxs-lookup"><span data-stu-id="d0680-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d0680-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d0680-153">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-154">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-154">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-155">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</span><span class="sxs-lookup"><span data-stu-id="d0680-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d0680-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d0680-157">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-158">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-158">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-159">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</span><span class="sxs-lookup"><span data-stu-id="d0680-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d0680-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d0680-161">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-161">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-162">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-163">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="d0680-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d0680-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d0680-165">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-165">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-166">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-167">仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</span><span class="sxs-lookup"><span data-stu-id="d0680-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d0680-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d0680-169">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-170">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-170">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-171">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="d0680-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="d0680-172">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</span><span class="sxs-lookup"><span data-stu-id="d0680-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d0680-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d0680-174">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-174">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-175">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-176">通过 UDP/3478 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="d0680-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d0680-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d0680-178">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-178">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-179">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-180">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="d0680-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d0680-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d0680-182">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-183">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-183">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-184">通过 TCP/443 进行的候选项 STUN/TURN 协商</span><span class="sxs-lookup"><span data-stu-id="d0680-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="d0680-185">具有使用 NAT 的专用 IP 地址的单一合并边缘的防火墙摘要： Internal 接口</span><span class="sxs-lookup"><span data-stu-id="d0680-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0680-186">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="d0680-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d0680-187">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-187">Source IP address</span></span></th>
<th><span data-ttu-id="d0680-188">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-188">Destination IP address</span></span></th>
<th><span data-ttu-id="d0680-189">Comments</span><span class="sxs-lookup"><span data-stu-id="d0680-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0680-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d0680-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d0680-191">可以将任何 (定义为 Standard Edition server IP、Standard Edition server IP 地址或运行 XMPP 网关服务的池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="d0680-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="d0680-192">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-193">来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="d0680-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d0680-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d0680-195">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="d0680-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="d0680-196">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-197">从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 到边缘服务器内部接口的出站 SIP 流量 (</span><span class="sxs-lookup"><span data-stu-id="d0680-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d0680-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d0680-199">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-200">可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="d0680-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="d0680-201">入站 SIP 流量 (到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 从边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="d0680-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="d0680-203">可以将任何 (定义为前端服务器 IP 地址，或在前端池中的每个前端服务器 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="d0680-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="d0680-204">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-205">从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</span><span class="sxs-lookup"><span data-stu-id="d0680-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="d0680-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="d0680-207">可以将任何 (定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器) </span><span class="sxs-lookup"><span data-stu-id="d0680-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="d0680-208">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-209">A/V 身份验证服务 (A/v 身份验证服务) 从前端服务器或前端池 IP 地址或使用此边缘服务器的任何 Survivable 分支装置或 Survivable 分支服务器进行身份验证</span><span class="sxs-lookup"><span data-stu-id="d0680-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d0680-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d0680-211">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-211">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-212">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-213">内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="d0680-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d0680-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d0680-215">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-215">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-216">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-217">内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="d0680-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="d0680-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="d0680-219">可以将任何 (定义为前端服务器 IP 地址或包含中央管理存储的池) </span><span class="sxs-lookup"><span data-stu-id="d0680-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="d0680-220">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-221">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d0680-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="d0680-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="d0680-223">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-223">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-224">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-225">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="d0680-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="d0680-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="d0680-227">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-227">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-228">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-229">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="d0680-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="d0680-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="d0680-231">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-231">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-232">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d0680-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d0680-233">使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</span><span class="sxs-lookup"><span data-stu-id="d0680-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="d0680-234">联盟的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="d0680-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0680-235">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="d0680-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d0680-236">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-236">Source IP address</span></span></th>
<th><span data-ttu-id="d0680-237">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-237">Destination IP address</span></span></th>
<th><span data-ttu-id="d0680-238">注释</span><span class="sxs-lookup"><span data-stu-id="d0680-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0680-239">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d0680-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d0680-240">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d0680-241">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-241">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-242">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="d0680-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="d0680-243">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="d0680-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0680-244">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="d0680-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d0680-245">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-245">Source IP address</span></span></th>
<th><span data-ttu-id="d0680-246">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-246">Destination IP address</span></span></th>
<th><span data-ttu-id="d0680-247">注释</span><span class="sxs-lookup"><span data-stu-id="d0680-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0680-248">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d0680-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d0680-249">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="d0680-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d0680-250">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-251">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="d0680-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-252">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d0680-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d0680-253">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-254">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="d0680-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d0680-255">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="d0680-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-256">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="d0680-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d0680-257">客户端</span><span class="sxs-lookup"><span data-stu-id="d0680-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="d0680-258">边缘服务器访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-259">外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="d0680-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d0680-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d0680-261">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-262">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="d0680-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d0680-263">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="d0680-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d0680-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d0680-265">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-266">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="d0680-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d0680-267">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="d0680-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d0680-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d0680-269">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="d0680-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d0680-270">边缘服务器 A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d0680-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d0680-271">需要与 Windows Live Messenger 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="d0680-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d0680-272">可扩展消息传递和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="d0680-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0680-273">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="d0680-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d0680-274">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="d0680-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="d0680-275">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="d0680-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="d0680-276">Comments</span><span class="sxs-lookup"><span data-stu-id="d0680-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0680-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d0680-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d0680-278">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-278">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-279">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d0680-280">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="d0680-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d0680-281">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="d0680-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0680-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d0680-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d0680-283">边缘服务器访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d0680-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d0680-284">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-284">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-285">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="d0680-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d0680-286">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="d0680-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0680-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d0680-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d0680-288">任何</span><span class="sxs-lookup"><span data-stu-id="d0680-288">Any</span></span></p></td>
<td><p><span data-ttu-id="d0680-289">每个内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="d0680-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="d0680-290">从前端服务器或前端池上的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="d0680-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

