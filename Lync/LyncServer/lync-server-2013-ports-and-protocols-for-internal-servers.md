---
title: Lync Server 2013：内部服务器的端口和协议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="ccfe5-102">Lync Server 2013 中内部服务器的端口和协议</span><span class="sxs-lookup"><span data-stu-id="ccfe5-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccfe5-103">_**主题上次修改时间：** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="ccfe5-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="ccfe5-104">本部分概述了 Lync Server 部署中的服务器、负载平衡器和客户端使用的端口和协议。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ccfe5-105">Lync 和 Communicator 客户参与一次通信时，通常称为对等。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="ccfe5-106">从技术上讲，两个客户在一次对话中进行通信，中间有即时消息 multipoint control 单元（IMMCU）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="ccfe5-107">IMMCU 是前端服务器的组件。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="ccfe5-108">将 IMMCU 放入所需的通信工作流中，可使呼叫详细记录和前端服务器启用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="ccfe5-109">通信来自客户端上的动态源端口到前端服务器端口 TLS/TCP/5061 （假设使用了推荐的传输层安全性）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="ccfe5-110">根据设计，仅当 Lync Server 和 IMMCU 处于活动状态且可用时，才能使用对等通信（以及多方 IM）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ccfe5-111">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="ccfe5-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ccfe5-112">在服务器上启动 Lync Server 服务之前，Windows 防火墙必须运行，因为这是 Lync 服务器在防火墙中打开所需端口的时候。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="ccfe5-113">有关 edge 组件的防火墙配置的详细信息，请参阅[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="ccfe5-114">下表依据每个内部服务器角色列出了需要打开的端口。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="ccfe5-115">所需服务器端口（根据服务器角色）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-115">Required Server Ports (by Server Role)</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccfe5-116">服务器角色</span><span class="sxs-lookup"><span data-stu-id="ccfe5-116">Server role</span></span></th>
<th><span data-ttu-id="ccfe5-117">服务名称</span><span class="sxs-lookup"><span data-stu-id="ccfe5-117">Service name</span></span></th>
<th><span data-ttu-id="ccfe5-118">端口</span><span class="sxs-lookup"><span data-stu-id="ccfe5-118">Port</span></span></th>
<th><span data-ttu-id="ccfe5-119">协议</span><span class="sxs-lookup"><span data-stu-id="ccfe5-119">Protocol</span></span></th>
<th><span data-ttu-id="ccfe5-120">备注</span><span class="sxs-lookup"><span data-stu-id="ccfe5-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-121">所有服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-122">SQL 浏览器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-123">1434</span><span class="sxs-lookup"><span data-stu-id="ccfe5-123">1434</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-124">UDP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-125">中央管理存储数据库的本地复制副本的 SQL 浏览器。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-126">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-127">Lync Server 前端服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-128">5060</span><span class="sxs-lookup"><span data-stu-id="ccfe5-128">5060</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-129">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-130">（可选）Standard Edition Server 和前端服务器用于静态路由到受信任服务，例如，远程呼叫控制服务器。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-131">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-132">Lync Server 前端服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-133">5061</span><span class="sxs-lookup"><span data-stu-id="ccfe5-133">5061</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-135">Standard Edition Server 和前端池用于在服务器 (MTLS) 之间进行所有的内部 SIP 通信、在服务器和客户端 (TLS) 之间进行 SIP 通信，以及在前端服务器和中介服务器 (MTLS) 之间进行 SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="ccfe5-136">也用于与监视服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-137">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-138">Lync Server 前端服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-139">444</span><span class="sxs-lookup"><span data-stu-id="ccfe5-139">444</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-140">HTTPS</span></span></p>
<p><span data-ttu-id="ccfe5-141">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-142">用于焦点（管理会议状态的 Lync 服务器组件）和单个服务器之间的 HTTPS 通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="ccfe5-143">此端口还用于 Survivable 分支装置和前端服务器之间的 TCP 通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-144">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-145">Lync Server 前端服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-146">135</span><span class="sxs-lookup"><span data-stu-id="ccfe5-146">135</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-147">DCOM 和远程过程调用 (RPC)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-148">用于基于 DCOM 的操作，例如，移动用户、用户复制程序同步和通讯簿同步。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-149">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-150">Lync Server IM 会议服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-151">5062</span><span class="sxs-lookup"><span data-stu-id="ccfe5-151">5062</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-152">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-153">用于即时消息 (IM) 会议的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-154">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-155">Lync Server Web 会议服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-156">8057</span><span class="sxs-lookup"><span data-stu-id="ccfe5-156">8057</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-158">用于侦听来自客户端的持续性共享对象模型 (PSOM) 连接。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-159">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-160">Lync Server Web 会议兼容性服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-161">8058</span><span class="sxs-lookup"><span data-stu-id="ccfe5-161">8058</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-163">用于从 Live Meeting 客户端和早期版本的 Lync Server 中侦听永久共享对象模型（PSOM）连接。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-164">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-165">Lync Server 音频/视频会议服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-166">5063</span><span class="sxs-lookup"><span data-stu-id="ccfe5-166">5063</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-167">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-168">用于音频/视频 (A/V) 会议的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-169">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-170">Lync Server 音频/视频会议服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="ccfe5-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-173">用于视频会议的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-174">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-175">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-176">80</span><span class="sxs-lookup"><span data-stu-id="ccfe5-176">80</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-178">用于未使用 HTTPS 时从前端服务器到 Web 场 FQDN（IIS Web 组件使用的 URL）的通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-179">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-180">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-181">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-181">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-183">用于从前端服务器到 Web 场 FQDN（IIS Web 组件使用的 URL）的通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-184">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-185">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-186">8080</span><span class="sxs-lookup"><span data-stu-id="ccfe5-186">8080</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-187">TCP 和 HTTP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-188">用于 Web 组件供外部访问。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-189">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-190">Web 服务器组件</span><span class="sxs-lookup"><span data-stu-id="ccfe5-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-191">4443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-191">4443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-193">HTTPS（从反向代理）和 HTTPS 前端池间通信，用于自动发现登录。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-194">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-195">Web 服务器组件</span><span class="sxs-lookup"><span data-stu-id="ccfe5-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-196">8060</span><span class="sxs-lookup"><span data-stu-id="ccfe5-196">8060</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-198">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-199">Web 服务器组件</span><span class="sxs-lookup"><span data-stu-id="ccfe5-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-200">8061</span><span class="sxs-lookup"><span data-stu-id="ccfe5-200">8061</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-202">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-203">Mobility Service 组件</span><span class="sxs-lookup"><span data-stu-id="ccfe5-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-204">5086</span><span class="sxs-lookup"><span data-stu-id="ccfe5-204">5086</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-206">Mobility Service 内部过程所使用的 SIP 端口。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-207">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-208">Mobility Service 组件</span><span class="sxs-lookup"><span data-stu-id="ccfe5-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-209">5087</span><span class="sxs-lookup"><span data-stu-id="ccfe5-209">5087</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-211">Mobility Service 内部过程所使用的 SIP 端口。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-212">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-213">Mobility Service 组件</span><span class="sxs-lookup"><span data-stu-id="ccfe5-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-214">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-214">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-216">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-217">Lync Server 会议助理服务（电话拨入式会议）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-218">5064</span><span class="sxs-lookup"><span data-stu-id="ccfe5-218">5064</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-219">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-220">用于电话拨入式会议的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-221">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-222">Lync Server 会议助理服务（电话拨入式会议）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-223">5072</span><span class="sxs-lookup"><span data-stu-id="ccfe5-223">5072</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-224">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-225">用于对助理（拨入式会议）的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-226">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-227">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-228">5070</span><span class="sxs-lookup"><span data-stu-id="ccfe5-228">5070</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-229">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-230">中介服务器用于从前端服务器到中介服务器的传入请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-231">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-232">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-233">5067</span><span class="sxs-lookup"><span data-stu-id="ccfe5-233">5067</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-235">用于从 PSTN 网关到中介服务器的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-236">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-237">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-238">5068</span><span class="sxs-lookup"><span data-stu-id="ccfe5-238">5068</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-239">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-240">用于从 PSTN 网关到中介服务器的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-241">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-242">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-243">5081</span><span class="sxs-lookup"><span data-stu-id="ccfe5-243">5081</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-244">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-245">用于从中介服务器到 PSTN 网关的传出 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-246">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-247">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-248">5082</span><span class="sxs-lookup"><span data-stu-id="ccfe5-248">5082</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-250">用于从中介服务器到 PSTN 网关的传出 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-251">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-252">Lync Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-253">5065</span><span class="sxs-lookup"><span data-stu-id="ccfe5-253">5065</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-254">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-255">用于应用程序共享的传入 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-256">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-257">Lync Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="ccfe5-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-259">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-260">用于应用程序共享的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-261">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-262">Lync Server 会议公告服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-263">5073</span><span class="sxs-lookup"><span data-stu-id="ccfe5-263">5073</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-264">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-265">用于 Lync Server 会议公告服务的传入 SIP 请求（即电话拨入式会议）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-266">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-267">Lync Server 呼叫寄存服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-268">5075</span><span class="sxs-lookup"><span data-stu-id="ccfe5-268">5075</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-269">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-270">用于呼叫寄存应用程序的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-271">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-272">Lync Server 音频测试服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-273">5076</span><span class="sxs-lookup"><span data-stu-id="ccfe5-273">5076</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-274">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-275">用于音频测试服务的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-276">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-277">不适用</span><span class="sxs-lookup"><span data-stu-id="ccfe5-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-278">5066</span><span class="sxs-lookup"><span data-stu-id="ccfe5-278">5066</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-279">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-280">用于出站增强型 9-1-1 (E9-1-1) 网关。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-281">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-282">Lync Server 响应组服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-283">5071</span><span class="sxs-lookup"><span data-stu-id="ccfe5-283">5071</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-284">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-285">用于响应组应用程序的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-286">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-287">Lync Server 响应组服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-288">8404</span><span class="sxs-lookup"><span data-stu-id="ccfe5-288">8404</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-290">用于响应组应用程序的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-291">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-292">Lync Server 带宽策略服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-293">5080</span><span class="sxs-lookup"><span data-stu-id="ccfe5-293">5080</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-294">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-295">用于通过带宽策略服务对 A/V 边缘 TURN 流量进行呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-296">前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-297">Lync Server 带宽策略服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-298">448</span><span class="sxs-lookup"><span data-stu-id="ccfe5-298">448</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-299">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-300">由 Lync Server 带宽策略服务用于呼叫许可控制。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-301">中央管理存储所在的前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-302">Lync Server 主复制程序代理服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-303">445</span><span class="sxs-lookup"><span data-stu-id="ccfe5-303">445</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-304">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-305">用于将配置数据从中央管理存储推送到运行 Lync Server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-306">所有服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-307">SQL 浏览器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-308">1434</span><span class="sxs-lookup"><span data-stu-id="ccfe5-308">1434</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-309">UDP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-310">本地 SQL Server 实例中中央管理存储数据的本地复制副本的 SQL 浏览器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-311">所有内部服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-312">各种</span><span class="sxs-lookup"><span data-stu-id="ccfe5-312">Various</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="ccfe5-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-315">用于所有内部服务器上的音频会议的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="ccfe5-316">由终止音频的所有服务器使用：前端服务器（适用于 Lync Server 会议助理服务、Lync Server 会议公告服务和 Lync Server 音频/视频会议服务）和中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-317">Office Web Apps Servers</span><span class="sxs-lookup"><span data-stu-id="ccfe5-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccfe5-318">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccfe5-319">由 Lync Server 2013 用于连接到 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-320">控制器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-321">Lync Server 前端服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-322">5060</span><span class="sxs-lookup"><span data-stu-id="ccfe5-322">5060</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-323">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-324">（可选）用于静态路由到受信任服务，例如，远程呼叫控制服务器。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-325">控制器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-326">Lync Server 前端服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-327">444</span><span class="sxs-lookup"><span data-stu-id="ccfe5-327">444</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-328">HTTPS</span></span></p>
<p><span data-ttu-id="ccfe5-329">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-330">前端与控制器之间的服务器间通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="ccfe5-331">此外，客户端证书发布（到前端服务器）或验证客户端证书是否已发布。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-332">控制器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-333">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-334">80</span><span class="sxs-lookup"><span data-stu-id="ccfe5-334">80</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-335">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-p105">用于从控制器到 Web 场 FQDN（IIS Web 组件使用的 URL）的初始通信。在常规操作中，将使用端口 443 和协议类型 TCP 切换到 HTTPS 通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-338">控制器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-339">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-340">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-340">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-342">用于从控制器到 Web 场 FQDN（IIS Web 组件使用的 URL）之间的通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-343">控制器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-344">Lync Server 前端服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-345">5061</span><span class="sxs-lookup"><span data-stu-id="ccfe5-345">5061</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-346">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-347">用于服务器之间的内部通信和客户端连接。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-348">中介服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-349">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-350">5070</span><span class="sxs-lookup"><span data-stu-id="ccfe5-350">5070</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-351">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-352">中介服务器用于来自前端服务器的传入请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-353">中介服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-354">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-355">5067</span><span class="sxs-lookup"><span data-stu-id="ccfe5-355">5067</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-357">用于来自 PSTN 网关的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-358">中介服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-359">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-360">5068</span><span class="sxs-lookup"><span data-stu-id="ccfe5-360">5068</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-361">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-362">用于来自 PSTN 网关的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-363">中介服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-364">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-365">5070</span><span class="sxs-lookup"><span data-stu-id="ccfe5-365">5070</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-367">用于来自前端服务器的 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-368">持久聊天前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-369">持久聊天 SIP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-370">5041</span><span class="sxs-lookup"><span data-stu-id="ccfe5-370">5041</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-372">持久聊天前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-373">持久聊天 Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-374">881</span><span class="sxs-lookup"><span data-stu-id="ccfe5-374">881</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-375">TCP (TLS) 和 TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-376">持久聊天前端服务器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-377">持久聊天文件传输服务</span><span class="sxs-lookup"><span data-stu-id="ccfe5-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-378">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-378">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ccfe5-380">某些远程呼叫控制方案需要前端服务器或控制器与 PBX 之间的 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="ccfe5-381">虽然 Lync Server 不再使用 TCP 端口5060，但在远程呼叫控制部署期间，你创建了一个受信任的服务器配置，该配置将 RCC 线路服务器 FQDN 与前端服务器或控制器用于连接到 PBX 系统的 TCP 端口相关联。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="ccfe5-382">有关详细信息，请参阅 Lync Server Management Shell 文档中的<STRONG>CsTrustedApplicationComputer</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="ccfe5-383">对于仅使用硬件负载平衡（不是 DNS 负载平衡）的池，下表显示了需要打开硬件负载平衡器的端口。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="ccfe5-384">仅使用硬件负载平衡时的硬件负载平衡器端口</span><span class="sxs-lookup"><span data-stu-id="ccfe5-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccfe5-385">负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-385">Load Balancer</span></span></th>
<th><span data-ttu-id="ccfe5-386">端口</span><span class="sxs-lookup"><span data-stu-id="ccfe5-386">Port</span></span></th>
<th><span data-ttu-id="ccfe5-387">协议</span><span class="sxs-lookup"><span data-stu-id="ccfe5-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-388">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-389">5061</span><span class="sxs-lookup"><span data-stu-id="ccfe5-389">5061</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-391">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-392">444</span><span class="sxs-lookup"><span data-stu-id="ccfe5-392">444</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-394">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-395">135</span><span class="sxs-lookup"><span data-stu-id="ccfe5-395">135</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-396">DCOM 和远程过程调用 (RPC)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-397">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-398">80</span><span class="sxs-lookup"><span data-stu-id="ccfe5-398">80</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-400">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-401">8080</span><span class="sxs-lookup"><span data-stu-id="ccfe5-401">8080</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-402">TCP - 从前端服务器中进行的客户端和设备根证书检索 – NTLM 授权的客户端和设备</span><span class="sxs-lookup"><span data-stu-id="ccfe5-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-403">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-404">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-404">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-406">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-407">4443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-407">4443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-408">HTTPS（来自反向代理）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-409">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-410">5072</span><span class="sxs-lookup"><span data-stu-id="ccfe5-410">5072</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-411">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-412">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-413">5073</span><span class="sxs-lookup"><span data-stu-id="ccfe5-413">5073</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-414">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-415">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-416">5075</span><span class="sxs-lookup"><span data-stu-id="ccfe5-416">5075</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-417">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-418">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-419">5076</span><span class="sxs-lookup"><span data-stu-id="ccfe5-419">5076</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-420">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-421">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-422">5071</span><span class="sxs-lookup"><span data-stu-id="ccfe5-422">5071</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-423">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-424">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-425">5080</span><span class="sxs-lookup"><span data-stu-id="ccfe5-425">5080</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-426">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-427">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-428">448</span><span class="sxs-lookup"><span data-stu-id="ccfe5-428">448</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-429">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-430">中介服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-431">5070</span><span class="sxs-lookup"><span data-stu-id="ccfe5-431">5070</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-432">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-433">前端服务器负载平衡器（如果池也运行中介服务器）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-434">5070</span><span class="sxs-lookup"><span data-stu-id="ccfe5-434">5070</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-435">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-436">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-437">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-437">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-439">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-440">444</span><span class="sxs-lookup"><span data-stu-id="ccfe5-440">444</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-442">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-443">5061</span><span class="sxs-lookup"><span data-stu-id="ccfe5-443">5061</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-444">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-445">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-446">4443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-446">4443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-447">HTTPS（来自反向代理）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ccfe5-p107">使用 DNS 负载平衡的前端池和控制器池还必须部署硬件负载平衡器。下表显示了需要在这些硬件负载平衡器上打开的端口。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="ccfe5-450">使用 DNS 负载平衡时的硬件负载平衡器端口</span><span class="sxs-lookup"><span data-stu-id="ccfe5-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccfe5-451">负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-451">Load Balancer</span></span></th>
<th><span data-ttu-id="ccfe5-452">端口</span><span class="sxs-lookup"><span data-stu-id="ccfe5-452">Port</span></span></th>
<th><span data-ttu-id="ccfe5-453">协议</span><span class="sxs-lookup"><span data-stu-id="ccfe5-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-454">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-455">80</span><span class="sxs-lookup"><span data-stu-id="ccfe5-455">80</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-457">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-458">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-458">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-460">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-461">8080</span><span class="sxs-lookup"><span data-stu-id="ccfe5-461">8080</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-462">TCP - 从前端服务器中进行的客户端和设备根证书检索 – NTLM 授权的客户端和设备</span><span class="sxs-lookup"><span data-stu-id="ccfe5-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-463">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-464">4443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-464">4443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-465">HTTPS（来自反向代理）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-466">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-467">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-467">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ccfe5-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-469">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ccfe5-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-470">4443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-470">4443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-471">HTTPS（来自反向代理）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="ccfe5-472">所需客户端端口</span><span class="sxs-lookup"><span data-stu-id="ccfe5-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccfe5-473">组件</span><span class="sxs-lookup"><span data-stu-id="ccfe5-473">Component</span></span></th>
<th><span data-ttu-id="ccfe5-474">端口</span><span class="sxs-lookup"><span data-stu-id="ccfe5-474">Port</span></span></th>
<th><span data-ttu-id="ccfe5-475">协议</span><span class="sxs-lookup"><span data-stu-id="ccfe5-475">Protocol</span></span></th>
<th><span data-ttu-id="ccfe5-476">备注</span><span class="sxs-lookup"><span data-stu-id="ccfe5-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-477">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-478">67/68</span><span class="sxs-lookup"><span data-stu-id="ccfe5-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-480">由 Lync Server 用于查找注册机构 FQDN （即，如果 DNS SRV 失败，并且未配置手动设置）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-481">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-482">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-482">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-484">用于外部用户访问的客户端到服务器 SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-485">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-486">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-486">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-488">用于外部用户访问 Web 会议会话。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-489">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-490">443</span><span class="sxs-lookup"><span data-stu-id="ccfe5-490">443</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-492">用于外部用户访问 A/V 会话和媒体 (TCP)。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-493">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-494">3478</span><span class="sxs-lookup"><span data-stu-id="ccfe5-494">3478</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-496">用于外部用户访问 A/V 会话和媒体 (UDP)。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-497">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-498">5061</span><span class="sxs-lookup"><span data-stu-id="ccfe5-498">5061</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ccfe5-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-500">用于外部用户访问的客户端到服务器 SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-501">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="ccfe5-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-503">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-504">用于 Lync 客户端和以前的客户端（Microsoft Office 通信服务器 2007 R2、Microsoft Office 通信服务器2007和实时通信服务器2005）之间的文件传输。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-505">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ccfe5-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-508">音频端口范围（最少需要 20 个端口）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-509">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ccfe5-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-512">视频端口范围（最少需要 20 个端口）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-513">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ccfe5-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-515">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-516">对等文件传输（对于会议文件传输，客户端使用 PSOM）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfe5-517">客户端</span><span class="sxs-lookup"><span data-stu-id="ccfe5-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ccfe5-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-519">TCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-520">应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfe5-521">Aastra 6721ip 公用区域电话</span><span class="sxs-lookup"><span data-stu-id="ccfe5-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="ccfe5-522">Aastra 6725ip 桌面电话</span><span class="sxs-lookup"><span data-stu-id="ccfe5-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="ccfe5-523">HP 4110 IP Phone（公用区域电话）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="ccfe5-524">HP 4120 IP Phone（桌面电话）</span><span class="sxs-lookup"><span data-stu-id="ccfe5-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="ccfe5-525">Polycom CX500 IP 公用区域电话</span><span class="sxs-lookup"><span data-stu-id="ccfe5-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="ccfe5-526">Polycom CX600 IP 桌面电话</span><span class="sxs-lookup"><span data-stu-id="ccfe5-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="ccfe5-527">Polycom CX700 IP 桌面电话</span><span class="sxs-lookup"><span data-stu-id="ccfe5-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="ccfe5-528">Polycom CX3000 IP 会议电话</span><span class="sxs-lookup"><span data-stu-id="ccfe5-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-529">67/68</span><span class="sxs-lookup"><span data-stu-id="ccfe5-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="ccfe5-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="ccfe5-531">由列出的设备用于查找 Lync 服务器证书、配置 FQDN 和注册机构 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ccfe5-532">**\*** 若要为这些媒体类型配置特定端口，请使用 CsConferencingConfiguration cmdlet （ClientMediaPortRangeEnabled、ClientMediaPort 和 ClientMediaPortRange 参数）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ccfe5-533">为 Lync 客户端设置的程序在客户端计算机上自动创建所需的操作系统防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ccfe5-534">在客户端必须遍历组织的防火墙的任何方案中，都需要用于外部用户访问的端口（例如，由其他组织承载的任何外部通信或会议）。</span><span class="sxs-lookup"><span data-stu-id="ccfe5-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

