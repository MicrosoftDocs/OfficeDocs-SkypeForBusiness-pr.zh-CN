---
title: 端口摘要 - 使用硬件负载平衡器的扩展的合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="55bec-102">Lync Server 2013 中的端口摘要 - 使用硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="55bec-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55bec-103">_**主题上次修改时间:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="55bec-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="55bec-104">此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能非常类似于 Lync Server 2010 中实现的功能。</span><span class="sxs-lookup"><span data-stu-id="55bec-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="55bec-105">最显著的相加是针对可扩展消息和状态协议 (XMPP) 的 TCP 条目的端口**5269** 。</span><span class="sxs-lookup"><span data-stu-id="55bec-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="55bec-106">Lync Server 2013 (可选) 在 Edge 服务器或边缘池以及前端服务器或前端池中的 XMPP 网关服务器上部署 XMPP 代理。</span><span class="sxs-lookup"><span data-stu-id="55bec-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="55bec-107">除了 IPv4, Edge 服务器现在还支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="55bec-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="55bec-108">为了清楚起见, 方案中仅使用了 IPv4。</span><span class="sxs-lookup"><span data-stu-id="55bec-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="55bec-109">**使用硬件负载平衡缩放的合并边缘**</span><span class="sxs-lookup"><span data-stu-id="55bec-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="55bec-110">![边缘服务器外围网络端口和协议](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "边缘服务器外围网络端口和协议")</span><span class="sxs-lookup"><span data-stu-id="55bec-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="55bec-111">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="55bec-111">Port and Protocol Details</span></span>

<span data-ttu-id="55bec-112">建议你仅打开支持你为其提供外部访问的功能所需的端口。</span><span class="sxs-lookup"><span data-stu-id="55bec-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="55bec-113">若要使远程访问适用于任何 edge 服务, 必须确保 SIP 流量可以双向排列, 如入站/出站边缘流量图中所示。</span><span class="sxs-lookup"><span data-stu-id="55bec-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="55bec-114">另一种方法是, 在即时消息 (IM)、状态、web 会议、音频/视频 (A/V) 和联合身份验证中涉及到和发送来自访问边缘服务的 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="55bec-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="55bec-115">用于缩放后的合并边缘的防火墙摘要, 硬件负载平衡: 外部接口-节点1和节点 2 (示例)</span><span class="sxs-lookup"><span data-stu-id="55bec-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55bec-116">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="55bec-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="55bec-117">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-117">Source IP address</span></span></th>
<th><span data-ttu-id="55bec-118">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-118">Destination IP address</span></span></th>
<th><span data-ttu-id="55bec-119">备注</span><span class="sxs-lookup"><span data-stu-id="55bec-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55bec-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="55bec-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="55bec-121">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-122">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-122">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-123">证书吊销/CRL 检查和检索</span><span class="sxs-lookup"><span data-stu-id="55bec-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="55bec-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="55bec-125">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-126">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-126">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-127">通过 TCP 进行 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="55bec-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="55bec-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="55bec-129">边缘服务器访问边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-130">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-130">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-131">通过 UDP 进行 DNS 查询</span><span class="sxs-lookup"><span data-stu-id="55bec-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-132">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="55bec-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="55bec-133">Edge 服务器 A/V 边缘服务 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-134">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-134">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-135">与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟所必需。</span><span class="sxs-lookup"><span data-stu-id="55bec-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-136">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="55bec-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="55bec-137">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-138">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-138">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-139">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所必需。</span><span class="sxs-lookup"><span data-stu-id="55bec-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-140">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="55bec-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="55bec-141">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-141">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-142">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-143">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</span><span class="sxs-lookup"><span data-stu-id="55bec-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-144">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="55bec-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="55bec-145">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-145">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-146">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-147">仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</span><span class="sxs-lookup"><span data-stu-id="55bec-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-148">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55bec-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55bec-149">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-150">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-150">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-151">3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="55bec-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="55bec-152">对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟, 以及在公司内部部署了多个边缘池的情况下, 也是必需的。</span><span class="sxs-lookup"><span data-stu-id="55bec-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-153">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55bec-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55bec-154">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-154">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-155">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-156">通过 UDP/3478 对候选人的 STUN 进行协商/启用</span><span class="sxs-lookup"><span data-stu-id="55bec-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-157">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55bec-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55bec-158">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-158">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-159">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-160">在 TCP/443 上 STUN/打开候选人的协商</span><span class="sxs-lookup"><span data-stu-id="55bec-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-161">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55bec-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55bec-162">Edge 服务器 A/V 边缘服务公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-163">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-163">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-164">在 TCP/443 上 STUN/打开候选人的协商</span><span class="sxs-lookup"><span data-stu-id="55bec-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="55bec-165">用于缩放后的合并边缘的防火墙摘要, 硬件负载平衡: 内部接口节点1和节点2</span><span class="sxs-lookup"><span data-stu-id="55bec-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55bec-166">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="55bec-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="55bec-167">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-167">Source IP address</span></span></th>
<th><span data-ttu-id="55bec-168">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-168">Destination IP address</span></span></th>
<th><span data-ttu-id="55bec-169">备注</span><span class="sxs-lookup"><span data-stu-id="55bec-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55bec-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="55bec-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="55bec-171">任何 (可以定义为前端服务器地址, 或运行 XMPP 网关服务的前端池虚拟 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="55bec-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="55bec-172">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="55bec-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-173">来自前端服务器或前端池运行的 XMPP 网关服务的出站 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="55bec-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="55bec-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="55bec-175">任何 (可以定义为拥有中央管理存储的前端服务器服务器 IP 或池)</span><span class="sxs-lookup"><span data-stu-id="55bec-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="55bec-176">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="55bec-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-177">将中央管理存储中的更改复制到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="55bec-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="55bec-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="55bec-179">任何 (可以定义为 Director IP、前端服务器 IP 或池虚拟 IP)</span><span class="sxs-lookup"><span data-stu-id="55bec-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="55bec-180">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="55bec-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-181">从内部部署到内部边缘服务器接口的网络会议流量</span><span class="sxs-lookup"><span data-stu-id="55bec-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55bec-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55bec-183">任何 (可以定义为 Director IP、前端服务器 IP 或池虚拟 IP)</span><span class="sxs-lookup"><span data-stu-id="55bec-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="55bec-184">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="55bec-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-185">内部和外部用户之间的/V 媒体传输的首选路径, Survivable 分支装置或 Survivable 分支服务器</span><span class="sxs-lookup"><span data-stu-id="55bec-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55bec-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55bec-187">任何 (可以定义为 Director IP、前端服务器 IP 或池虚拟 IP)</span><span class="sxs-lookup"><span data-stu-id="55bec-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="55bec-188">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="55bec-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-189">内部和外部用户、Survivable 分支装置或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信, 则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="55bec-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="55bec-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="55bec-191">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-191">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-192">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="55bec-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-193">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="55bec-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="55bec-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="55bec-195">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-195">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-196">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="55bec-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-197">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="55bec-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="55bec-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="55bec-199">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-199">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-200">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="55bec-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-201">使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器</span><span class="sxs-lookup"><span data-stu-id="55bec-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="55bec-202">硬件负载平衡器在部署以提供 Lync 服务器的可用性和负载平衡时有特定的要求。</span><span class="sxs-lookup"><span data-stu-id="55bec-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="55bec-203">这些要求在下图和表中定义。</span><span class="sxs-lookup"><span data-stu-id="55bec-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="55bec-204">第三方供应商可能对此处定义的要求使用不同的术语。</span><span class="sxs-lookup"><span data-stu-id="55bec-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="55bec-205">需要将 Lync Server 的要求映射到硬件负载平衡器供应商提供的功能和配置选项。</span><span class="sxs-lookup"><span data-stu-id="55bec-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="55bec-206">配置硬件负载平衡器时, 请考虑以下要求:</span><span class="sxs-lookup"><span data-stu-id="55bec-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="55bec-207">可在硬件负载平衡器 (HLB) 上为 Access Edge 服务和 Web 会议边缘服务配置源网络地址转换 (SNAT)</span><span class="sxs-lookup"><span data-stu-id="55bec-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="55bec-208">不能在 A/V 边缘服务上配置 SNAT-A/V 边缘服务必须用真实的服务器地址 (而不是 HLB 虚拟 IP (VIP)) 响应, 以便使用中继 NAT (STUN)/traversal 简单遍历 NAT over NAT (),/federation 转动 (FTURN) 才能正常工作</span><span class="sxs-lookup"><span data-stu-id="55bec-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="55bec-209">如果客户端向 HLB 发送请求, 则该响应必须从 HLB VIP 返回</span><span class="sxs-lookup"><span data-stu-id="55bec-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="55bec-210">如果客户端向边缘发送请求, 则响应必须从边缘 IP 返回</span><span class="sxs-lookup"><span data-stu-id="55bec-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="55bec-211">公共 IP 地址在每个服务器接口和 HLB 的 Vip 上使用, 并且您的公共 IP 地址要求是 N + 1, 其中包含每个真实服务器接口的公共 IP 地址, 以及每个 HLB VIP 的一个公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="55bec-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="55bec-212">如果池中有2台边缘服务器, 这将产生9个公共 IP 地址, 其中3用于 HLB Vip, 另一个用于每个边缘服务器接口 (共6台服务器)</span><span class="sxs-lookup"><span data-stu-id="55bec-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="55bec-213">对于 Access Edge 服务和 Web 会议边缘服务 (并在 HLB 上使用 NAT), 该 VIP 会将源 IP 地址从客户端更改为其自己的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="55bec-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="55bec-214">服务器接口将寄信人地址寻址到 VIP, VIP 从服务器接口 IP 地址更改源地址, 并将该数据包发送到客户端</span><span class="sxs-lookup"><span data-stu-id="55bec-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="55bec-215">对于 A/V 边缘服务, VIP 不得更改源 IP 地址, 而真正的服务器地址将直接返回到客户端-你无法在 HLB 上配置用于 AV 流量的 NAT</span><span class="sxs-lookup"><span data-stu-id="55bec-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="55bec-216">如果客户端向 HLB VIP 发送请求, 则响应必须从 HLB VIP 返回</span><span class="sxs-lookup"><span data-stu-id="55bec-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="55bec-217">如果客户端向边缘 IP 发送请求, 则响应必须从边缘 IP 返回</span><span class="sxs-lookup"><span data-stu-id="55bec-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="55bec-218">对于 AV, 外部防火墙将保留所有数据包的真实服务器公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="55bec-219">客户端到 A/V 边缘服务通信一经建立, 就是真正的服务器, 而不是 HLB</span><span class="sxs-lookup"><span data-stu-id="55bec-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="55bec-220">内部边缘到内部服务器和客户端必须路由, 并且为托管服务器或客户端的所有内部网络设置持久路由</span><span class="sxs-lookup"><span data-stu-id="55bec-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="55bec-221">HLB Access Edge 服务 VIP 将用作每个 Edge 服务器接口的默认网关</span><span class="sxs-lookup"><span data-stu-id="55bec-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="55bec-222">有关 NAT 规划和功能的详细信息, 请参阅<A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 的硬件负载平衡器要求</A>。</span><span class="sxs-lookup"><span data-stu-id="55bec-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="55bec-223">![边缘服务器端口和协议详细信息](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "边缘服务器端口和协议详细信息")</span><span class="sxs-lookup"><span data-stu-id="55bec-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="55bec-224">缩放后的合并边缘所需的外部端口设置, 硬件负载平衡: 外部接口虚拟 IPs</span><span class="sxs-lookup"><span data-stu-id="55bec-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55bec-225">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="55bec-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="55bec-226">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-226">Source IP address</span></span></th>
<th><span data-ttu-id="55bec-227">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-227">Destination IP address</span></span></th>
<th><span data-ttu-id="55bec-228">备注</span><span class="sxs-lookup"><span data-stu-id="55bec-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55bec-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="55bec-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="55bec-230">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-230">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-231">XMPP 代理服务 (使用 Access Edge 服务共享 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="55bec-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="55bec-232">XMPP 代理服务接受来自定义的 XMPP 联合的 XMPP 联系人的流量</span><span class="sxs-lookup"><span data-stu-id="55bec-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="55bec-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="55bec-234">XMPP 代理服务 (使用 Access Edge 服务共享 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="55bec-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="55bec-235">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-235">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-236">XMPP 代理服务将流量发送到定义的 XMPP 联合体中的 XMPP 联系人</span><span class="sxs-lookup"><span data-stu-id="55bec-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-237">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55bec-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55bec-238">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-238">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-239">Access Edge 服务公共 VIP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-240">用于外部用户访问的客户端到服务器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="55bec-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-241">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55bec-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55bec-242">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-242">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-243">Access Edge 服务公共 VIP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-244">使用 SIP 的 SIP 信号、联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="55bec-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-245">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55bec-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55bec-246">Access Edge 服务公共 VIP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-247">联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="55bec-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="55bec-248">使用 SIP 的 SIP 信号、联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="55bec-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-249">Web 会议/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55bec-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55bec-250">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-250">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-251">Edge 服务器 Web 会议 Edge 服务公共 VIP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-252">网络会议媒体</span><span class="sxs-lookup"><span data-stu-id="55bec-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-253">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55bec-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55bec-254">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-254">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-255">Edge 服务器 A/V 边缘服务公共 VIP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-256">通过 UDP/3478 对候选人的 STUN 进行协商/启用</span><span class="sxs-lookup"><span data-stu-id="55bec-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-257">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55bec-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55bec-258">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-258">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-259">Edge 服务器 A/V 边缘服务公共 VIP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="55bec-260">在 TCP/443 上 STUN/打开候选人的协商</span><span class="sxs-lookup"><span data-stu-id="55bec-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="55bec-261">用于缩放后的合并边缘的防火墙摘要, 硬件负载平衡: 内部接口虚拟 IPs</span><span class="sxs-lookup"><span data-stu-id="55bec-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55bec-262">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="55bec-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="55bec-263">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-263">Source IP address</span></span></th>
<th><span data-ttu-id="55bec-264">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="55bec-264">Destination IP address</span></span></th>
<th><span data-ttu-id="55bec-265">备注</span><span class="sxs-lookup"><span data-stu-id="55bec-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55bec-266">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55bec-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55bec-267">任何 (可以定义为 Director、Director pool 虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="55bec-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="55bec-268">Edge 服务器内部 VIP 接口</span><span class="sxs-lookup"><span data-stu-id="55bec-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-269">出站 SIP 流量 (从控制器、控制器池虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址) 到内部边缘 VIP</span><span class="sxs-lookup"><span data-stu-id="55bec-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-270">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="55bec-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="55bec-271">Edge 服务器内部 VIP 接口</span><span class="sxs-lookup"><span data-stu-id="55bec-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-272">任何 (可以定义为 Director、Director pool 虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="55bec-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="55bec-273">来自边缘服务器内部接口的入站 SIP 流量 (到控制器、控制器池虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址)</span><span class="sxs-lookup"><span data-stu-id="55bec-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="55bec-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="55bec-275">任何 (可以定义为前端服务器 IP 地址或前端池 IP 地址, 或使用此 Edge 服务器的任何 Survivable 分支装置或 Survivable 分支服务器)</span><span class="sxs-lookup"><span data-stu-id="55bec-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="55bec-276">Edge 服务器内部 VIP 接口</span><span class="sxs-lookup"><span data-stu-id="55bec-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-277">使用此 Edge 服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支装置或 Survivable 分支服务器身份验证 A/V 用户 (A/V 身份验证服务) 的身份验证</span><span class="sxs-lookup"><span data-stu-id="55bec-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="55bec-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="55bec-279">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-279">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-280">Edge 服务器内部 VIP 接口</span><span class="sxs-lookup"><span data-stu-id="55bec-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-281">内部和外部用户之间的 A/V 媒体传输的首选路径</span><span class="sxs-lookup"><span data-stu-id="55bec-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55bec-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55bec-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55bec-283">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-283">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-284">Edge 服务器内部 VIP 接口</span><span class="sxs-lookup"><span data-stu-id="55bec-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-285">内部和外部用户之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信, 则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="55bec-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55bec-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="55bec-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="55bec-287">Edge 服务器内部 VIP 接口</span><span class="sxs-lookup"><span data-stu-id="55bec-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="55bec-288">任意</span><span class="sxs-lookup"><span data-stu-id="55bec-288">Any</span></span></p></td>
<td><p><span data-ttu-id="55bec-289">内部和外部用户之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信, 则使用 TCP 进行文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="55bec-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

