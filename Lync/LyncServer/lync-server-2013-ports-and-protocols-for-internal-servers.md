---
title: Lync Server 2013：内部服务器的端口和协议
description: Lync Server 2013：内部服务器的端口和协议。
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
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566349"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="14d41-103">Lync Server 2013 中内部服务器的端口和协议</span><span class="sxs-lookup"><span data-stu-id="14d41-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14d41-104">_**上次修改的主题：** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="14d41-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="14d41-105">本节总结了 Lync Server 部署中的服务器、负载平衡器和客户端使用的端口和协议。</span><span class="sxs-lookup"><span data-stu-id="14d41-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="14d41-106">Lync 和 Communicator 客户端参与一次通信时，通常称为对等。</span><span class="sxs-lookup"><span data-stu-id="14d41-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="14d41-107">从技术上讲，两个客户端在一次对话中进行通信，即时消息 multipoint 控制单位 (IMMCU) 在中间。</span><span class="sxs-lookup"><span data-stu-id="14d41-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="14d41-108">IMMCU 是前端服务器的组件。</span><span class="sxs-lookup"><span data-stu-id="14d41-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="14d41-109">将 IMMCU 置于所需的通信工作流中可允许呼叫详细记录和前端服务器启用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="14d41-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="14d41-110">通信是从客户端上的动态源端口到前端服务器端口 TLS/TCP/5061 (，假定使用的是建议的传输层安全性) 。</span><span class="sxs-lookup"><span data-stu-id="14d41-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="14d41-111">根据设计，只有在 Lync Server 和 IMMCU 处于活动状态且可用时，才能使用对等通信 (以及多方 IM) 。</span><span class="sxs-lookup"><span data-stu-id="14d41-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="14d41-112">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="14d41-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14d41-113">在服务器上启动 Lync Server 服务之前，必须运行 Windows 防火墙，这是因为当 Lync Server 在防火墙中打开所需端口时。</span><span class="sxs-lookup"><span data-stu-id="14d41-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="14d41-114">有关边缘组件的防火墙配置的详细信息，请参阅 [确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="14d41-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="14d41-115">下表依据每个内部服务器角色列出了需要打开的端口。</span><span class="sxs-lookup"><span data-stu-id="14d41-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="14d41-116">所需服务器端口（根据服务器角色）</span><span class="sxs-lookup"><span data-stu-id="14d41-116">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="14d41-117">服务器角色</span><span class="sxs-lookup"><span data-stu-id="14d41-117">Server role</span></span></th>
<th><span data-ttu-id="14d41-118">服务名称</span><span class="sxs-lookup"><span data-stu-id="14d41-118">Service name</span></span></th>
<th><span data-ttu-id="14d41-119">端口</span><span class="sxs-lookup"><span data-stu-id="14d41-119">Port</span></span></th>
<th><span data-ttu-id="14d41-120">协议</span><span class="sxs-lookup"><span data-stu-id="14d41-120">Protocol</span></span></th>
<th><span data-ttu-id="14d41-121">注释</span><span class="sxs-lookup"><span data-stu-id="14d41-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14d41-122">所有服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-123">SQL 浏览器</span><span class="sxs-lookup"><span data-stu-id="14d41-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="14d41-124">1434</span><span class="sxs-lookup"><span data-stu-id="14d41-124">1434</span></span></p></td>
<td><p><span data-ttu-id="14d41-125">UDP</span><span class="sxs-lookup"><span data-stu-id="14d41-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="14d41-126">用于中央管理存储数据库的本地复制副本的 SQL 浏览器。</span><span class="sxs-lookup"><span data-stu-id="14d41-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-127">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-128">Lync Server Front-End 服务</span><span class="sxs-lookup"><span data-stu-id="14d41-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="14d41-129">5060</span><span class="sxs-lookup"><span data-stu-id="14d41-129">5060</span></span></p></td>
<td><p><span data-ttu-id="14d41-130">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-131">（可选）Standard Edition Server 和前端服务器用于静态路由到受信任服务，例如，远程呼叫控制服务器。</span><span class="sxs-lookup"><span data-stu-id="14d41-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-132">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-133">Lync Server Front-End 服务</span><span class="sxs-lookup"><span data-stu-id="14d41-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="14d41-134">5061</span><span class="sxs-lookup"><span data-stu-id="14d41-134">5061</span></span></p></td>
<td><p><span data-ttu-id="14d41-135">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-p102">Standard Edition Server 和前端池用于在服务器 (MTLS) 之间进行所有的内部 SIP 通信、在服务器和客户端 (TLS) 之间进行 SIP 通信，以及在前端服务器和中介服务器 (MTLS) 之间进行 SIP 通信。还用于与监控服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="14d41-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-138">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-139">Lync Server Front-End 服务</span><span class="sxs-lookup"><span data-stu-id="14d41-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="14d41-140">444</span><span class="sxs-lookup"><span data-stu-id="14d41-140">444</span></span></p></td>
<td><p><span data-ttu-id="14d41-141">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-141">HTTPS</span></span></p>
<p><span data-ttu-id="14d41-142">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-143">用于管理会议状态的 (Lync Server 组件的焦点之间的 HTTPS 通信) 和各个服务器。</span><span class="sxs-lookup"><span data-stu-id="14d41-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="14d41-144">此端口还用于 Survivable 分支机构和前端服务器之间的 TCP 通信。</span><span class="sxs-lookup"><span data-stu-id="14d41-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-145">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-146">Lync Server Front-End 服务</span><span class="sxs-lookup"><span data-stu-id="14d41-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="14d41-147">135</span><span class="sxs-lookup"><span data-stu-id="14d41-147">135</span></span></p></td>
<td><p><span data-ttu-id="14d41-148">DCOM 和远程过程调用 (RPC)</span><span class="sxs-lookup"><span data-stu-id="14d41-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="14d41-149">用于基于 DCOM 的操作，例如，移动用户、用户复制程序同步和通讯簿同步。</span><span class="sxs-lookup"><span data-stu-id="14d41-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-150">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-151">Lync Server IM 会议服务</span><span class="sxs-lookup"><span data-stu-id="14d41-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="14d41-152">5062</span><span class="sxs-lookup"><span data-stu-id="14d41-152">5062</span></span></p></td>
<td><p><span data-ttu-id="14d41-153">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-154">用于即时消息 (IM) 会议的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-155">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-156">Lync Server Web 会议服务</span><span class="sxs-lookup"><span data-stu-id="14d41-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="14d41-157">8057</span><span class="sxs-lookup"><span data-stu-id="14d41-157">8057</span></span></p></td>
<td><p><span data-ttu-id="14d41-158">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-159">用于侦听来自客户端的持续性共享对象模型 (PSOM) 连接。</span><span class="sxs-lookup"><span data-stu-id="14d41-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-160">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-161">Lync Server Web 会议兼容性服务</span><span class="sxs-lookup"><span data-stu-id="14d41-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="14d41-162">8058</span><span class="sxs-lookup"><span data-stu-id="14d41-162">8058</span></span></p></td>
<td><p><span data-ttu-id="14d41-163">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-164">用于侦听永久共享对象模型 (PSOM) 来自 Live Meeting 客户端和早期版本的 Lync Server 的连接。</span><span class="sxs-lookup"><span data-stu-id="14d41-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-165">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-166">Lync Server 音频/视频会议服务</span><span class="sxs-lookup"><span data-stu-id="14d41-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="14d41-167">5063</span><span class="sxs-lookup"><span data-stu-id="14d41-167">5063</span></span></p></td>
<td><p><span data-ttu-id="14d41-168">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-169">用于音频/视频 (A/V) 会议的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-170">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-171">Lync Server 音频/视频会议服务</span><span class="sxs-lookup"><span data-stu-id="14d41-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="14d41-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="14d41-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="14d41-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="14d41-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="14d41-174">用于视频会议的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="14d41-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-175">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-176">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="14d41-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="14d41-177">80</span><span class="sxs-lookup"><span data-stu-id="14d41-177">80</span></span></p></td>
<td><p><span data-ttu-id="14d41-178">HTTP</span><span class="sxs-lookup"><span data-stu-id="14d41-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="14d41-179">用于未使用 HTTPS 时从前端服务器到 Web 场 FQDN（IIS Web 组件使用的 URL）的通信。</span><span class="sxs-lookup"><span data-stu-id="14d41-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-180">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-181">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="14d41-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="14d41-182">443</span><span class="sxs-lookup"><span data-stu-id="14d41-182">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-183">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="14d41-184">用于从前端服务器到 Web 场 FQDN（IIS Web 组件使用的 URL）的通信。</span><span class="sxs-lookup"><span data-stu-id="14d41-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-185">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-186">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="14d41-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="14d41-187">8080</span><span class="sxs-lookup"><span data-stu-id="14d41-187">8080</span></span></p></td>
<td><p><span data-ttu-id="14d41-188">TCP 和 HTTP</span><span class="sxs-lookup"><span data-stu-id="14d41-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="14d41-189">供用于外部访问的 web 组件使用。</span><span class="sxs-lookup"><span data-stu-id="14d41-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-190">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-191">Web 服务器组件</span><span class="sxs-lookup"><span data-stu-id="14d41-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="14d41-192">4443</span><span class="sxs-lookup"><span data-stu-id="14d41-192">4443</span></span></p></td>
<td><p><span data-ttu-id="14d41-193">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="14d41-194">HTTPS (从反向代理) 和 HTTPS 前端池之间的通信，用于自动发现登录。</span><span class="sxs-lookup"><span data-stu-id="14d41-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-195">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-196">Web 服务器组件</span><span class="sxs-lookup"><span data-stu-id="14d41-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="14d41-197">8060</span><span class="sxs-lookup"><span data-stu-id="14d41-197">8060</span></span></p></td>
<td><p><span data-ttu-id="14d41-198">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-199">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-200">Web 服务器组件</span><span class="sxs-lookup"><span data-stu-id="14d41-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="14d41-201">8061</span><span class="sxs-lookup"><span data-stu-id="14d41-201">8061</span></span></p></td>
<td><p><span data-ttu-id="14d41-202">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-203">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-204">移动服务组件</span><span class="sxs-lookup"><span data-stu-id="14d41-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="14d41-205">5086</span><span class="sxs-lookup"><span data-stu-id="14d41-205">5086</span></span></p></td>
<td><p><span data-ttu-id="14d41-206">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-207">移动服务内部进程使用的 SIP 端口</span><span class="sxs-lookup"><span data-stu-id="14d41-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-208">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-209">移动服务组件</span><span class="sxs-lookup"><span data-stu-id="14d41-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="14d41-210">5087</span><span class="sxs-lookup"><span data-stu-id="14d41-210">5087</span></span></p></td>
<td><p><span data-ttu-id="14d41-211">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-212">移动服务内部进程使用的 SIP 端口</span><span class="sxs-lookup"><span data-stu-id="14d41-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-213">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-214">移动服务组件</span><span class="sxs-lookup"><span data-stu-id="14d41-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="14d41-215">443</span><span class="sxs-lookup"><span data-stu-id="14d41-215">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-216">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-217">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-218">Lync Server 会议助理服务 (电话拨入式会议) </span><span class="sxs-lookup"><span data-stu-id="14d41-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="14d41-219">5064</span><span class="sxs-lookup"><span data-stu-id="14d41-219">5064</span></span></p></td>
<td><p><span data-ttu-id="14d41-220">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-221">用于电话拨入式会议的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-222">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-223">Lync Server 会议助理服务 (电话拨入式会议) </span><span class="sxs-lookup"><span data-stu-id="14d41-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="14d41-224">5072</span><span class="sxs-lookup"><span data-stu-id="14d41-224">5072</span></span></p></td>
<td><p><span data-ttu-id="14d41-225">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-226">用于会议) 中的助理的传入 SIP 请求 (电话拨入式。</span><span class="sxs-lookup"><span data-stu-id="14d41-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-227">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="14d41-228">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="14d41-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="14d41-229">5070</span><span class="sxs-lookup"><span data-stu-id="14d41-229">5070</span></span></p></td>
<td><p><span data-ttu-id="14d41-230">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-231">中介服务器用于从前端服务器到中介服务器的传入请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-232">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="14d41-233">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="14d41-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="14d41-234">5067</span><span class="sxs-lookup"><span data-stu-id="14d41-234">5067</span></span></p></td>
<td><p><span data-ttu-id="14d41-235">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-236">用于从 PSTN 网关到中介服务器的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-237">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="14d41-238">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="14d41-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="14d41-239">5068</span><span class="sxs-lookup"><span data-stu-id="14d41-239">5068</span></span></p></td>
<td><p><span data-ttu-id="14d41-240">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-241">用于从 PSTN 网关到中介服务器的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-242">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="14d41-243">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="14d41-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="14d41-244">5081</span><span class="sxs-lookup"><span data-stu-id="14d41-244">5081</span></span></p></td>
<td><p><span data-ttu-id="14d41-245">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-246">用于从中介服务器到 PSTN 网关的传出 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-247">也运行并置中介服务器的前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="14d41-248">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="14d41-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="14d41-249">5082</span><span class="sxs-lookup"><span data-stu-id="14d41-249">5082</span></span></p></td>
<td><p><span data-ttu-id="14d41-250">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-251">用于从中介服务器到 PSTN 网关的传出 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-252">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-253">Lync Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="14d41-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="14d41-254">5065</span><span class="sxs-lookup"><span data-stu-id="14d41-254">5065</span></span></p></td>
<td><p><span data-ttu-id="14d41-255">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-256">用于应用程序共享的传入 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-257">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-258">Lync Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="14d41-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="14d41-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="14d41-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="14d41-260">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-261">用于应用程序共享的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="14d41-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-262">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-263">Lync Server 会议通知服务</span><span class="sxs-lookup"><span data-stu-id="14d41-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="14d41-264">5073</span><span class="sxs-lookup"><span data-stu-id="14d41-264">5073</span></span></p></td>
<td><p><span data-ttu-id="14d41-265">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-266">用于 Lync Server 会议通知服务 (的传入 SIP 请求，即，电话拨入式会议) 。</span><span class="sxs-lookup"><span data-stu-id="14d41-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-267">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-268">Lync Server 呼叫寄存服务</span><span class="sxs-lookup"><span data-stu-id="14d41-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="14d41-269">5075</span><span class="sxs-lookup"><span data-stu-id="14d41-269">5075</span></span></p></td>
<td><p><span data-ttu-id="14d41-270">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-271">用于呼叫寄存应用程序的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-272">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-273">Lync Server 音频测试服务</span><span class="sxs-lookup"><span data-stu-id="14d41-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="14d41-274">5076</span><span class="sxs-lookup"><span data-stu-id="14d41-274">5076</span></span></p></td>
<td><p><span data-ttu-id="14d41-275">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-276">用于音频测试服务的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-277">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-278">不适用</span><span class="sxs-lookup"><span data-stu-id="14d41-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="14d41-279">5066</span><span class="sxs-lookup"><span data-stu-id="14d41-279">5066</span></span></p></td>
<td><p><span data-ttu-id="14d41-280">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-281">用于出站增强型 9-1-1 (E9-1-1) 网关。</span><span class="sxs-lookup"><span data-stu-id="14d41-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-282">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-283">Lync Server 响应组服务</span><span class="sxs-lookup"><span data-stu-id="14d41-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="14d41-284">5071</span><span class="sxs-lookup"><span data-stu-id="14d41-284">5071</span></span></p></td>
<td><p><span data-ttu-id="14d41-285">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-286">用于响应组应用程序的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-287">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-288">Lync Server 响应组服务</span><span class="sxs-lookup"><span data-stu-id="14d41-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="14d41-289">8404</span><span class="sxs-lookup"><span data-stu-id="14d41-289">8404</span></span></p></td>
<td><p><span data-ttu-id="14d41-290">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-291">用于响应组应用程序的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-292">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-293">Lync Server 带宽策略服务</span><span class="sxs-lookup"><span data-stu-id="14d41-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="14d41-294">5080</span><span class="sxs-lookup"><span data-stu-id="14d41-294">5080</span></span></p></td>
<td><p><span data-ttu-id="14d41-295">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-296">用于通过带宽策略服务对 A/V 边缘 TURN 流量进行呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="14d41-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-297">前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-298">Lync Server 带宽策略服务</span><span class="sxs-lookup"><span data-stu-id="14d41-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="14d41-299">448</span><span class="sxs-lookup"><span data-stu-id="14d41-299">448</span></span></p></td>
<td><p><span data-ttu-id="14d41-300">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-301">用于 Lync Server 带宽策略服务的呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="14d41-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-302">中央管理存储所在的前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="14d41-303">Lync Server 主复制程序代理服务</span><span class="sxs-lookup"><span data-stu-id="14d41-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="14d41-304">445</span><span class="sxs-lookup"><span data-stu-id="14d41-304">445</span></span></p></td>
<td><p><span data-ttu-id="14d41-305">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-306">用于将配置数据从中央管理存储推送到运行 Lync Server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="14d41-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-307">所有服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-308">SQL 浏览器</span><span class="sxs-lookup"><span data-stu-id="14d41-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="14d41-309">1434</span><span class="sxs-lookup"><span data-stu-id="14d41-309">1434</span></span></p></td>
<td><p><span data-ttu-id="14d41-310">UDP</span><span class="sxs-lookup"><span data-stu-id="14d41-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="14d41-311">本地 SQL Server 实例中的中央管理存储数据的本地复制副本的 SQL 浏览器</span><span class="sxs-lookup"><span data-stu-id="14d41-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-312">所有内部服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-313">各种</span><span class="sxs-lookup"><span data-stu-id="14d41-313">Various</span></span></p></td>
<td><p><span data-ttu-id="14d41-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="14d41-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="14d41-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="14d41-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="14d41-316">用于所有内部服务器上的音频会议的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="14d41-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="14d41-317">由终止音频的所有服务器使用：前端服务器 (Lync Server 会议助理服务、Lync Server 会议通知服务和 Lync Server 音频/视频会议服务) 和中介服务器。</span><span class="sxs-lookup"><span data-stu-id="14d41-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-318">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="14d41-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14d41-319">443</span><span class="sxs-lookup"><span data-stu-id="14d41-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14d41-320">由 Lync Server 2013 用于连接到 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="14d41-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-321">控制器</span><span class="sxs-lookup"><span data-stu-id="14d41-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="14d41-322">Lync Server Front-End 服务</span><span class="sxs-lookup"><span data-stu-id="14d41-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="14d41-323">5060</span><span class="sxs-lookup"><span data-stu-id="14d41-323">5060</span></span></p></td>
<td><p><span data-ttu-id="14d41-324">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-325">（可选）用于静态路由到受信任服务，例如，远程呼叫控制服务器。</span><span class="sxs-lookup"><span data-stu-id="14d41-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-326">控制器</span><span class="sxs-lookup"><span data-stu-id="14d41-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="14d41-327">Lync Server Front-End 服务</span><span class="sxs-lookup"><span data-stu-id="14d41-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="14d41-328">444</span><span class="sxs-lookup"><span data-stu-id="14d41-328">444</span></span></p></td>
<td><p><span data-ttu-id="14d41-329">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-329">HTTPS</span></span></p>
<p><span data-ttu-id="14d41-330">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-331">前端和控制器之间的服务器间通信。</span><span class="sxs-lookup"><span data-stu-id="14d41-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="14d41-332">此外，客户端证书 (发布到前端服务器) 或验证客户端证书是否已发布。</span><span class="sxs-lookup"><span data-stu-id="14d41-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-333">控制器</span><span class="sxs-lookup"><span data-stu-id="14d41-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="14d41-334">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="14d41-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="14d41-335">80</span><span class="sxs-lookup"><span data-stu-id="14d41-335">80</span></span></p></td>
<td><p><span data-ttu-id="14d41-336">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-p105">用于从控制器到 Web 场 FQDN（IIS Web 组件使用的 URL）的初始通信。在常规操作中，将使用端口 443 和协议类型 TCP 切换到 HTTPS 通信。</span><span class="sxs-lookup"><span data-stu-id="14d41-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-339">控制器</span><span class="sxs-lookup"><span data-stu-id="14d41-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="14d41-340">Lync Server Web 兼容性服务</span><span class="sxs-lookup"><span data-stu-id="14d41-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="14d41-341">443</span><span class="sxs-lookup"><span data-stu-id="14d41-341">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-342">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="14d41-343">用于从控制器到 Web 场 FQDN（IIS Web 组件使用的 URL）之间的通信。</span><span class="sxs-lookup"><span data-stu-id="14d41-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-344">控制器</span><span class="sxs-lookup"><span data-stu-id="14d41-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="14d41-345">Lync Server Front-End 服务</span><span class="sxs-lookup"><span data-stu-id="14d41-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="14d41-346">5061</span><span class="sxs-lookup"><span data-stu-id="14d41-346">5061</span></span></p></td>
<td><p><span data-ttu-id="14d41-347">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-348">用于服务器之间的内部通信和客户端连接。</span><span class="sxs-lookup"><span data-stu-id="14d41-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-349">中介服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-350">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="14d41-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="14d41-351">5070</span><span class="sxs-lookup"><span data-stu-id="14d41-351">5070</span></span></p></td>
<td><p><span data-ttu-id="14d41-352">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-353">中介服务器用于来自前端服务器的传入请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-354">中介服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-355">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="14d41-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="14d41-356">5067</span><span class="sxs-lookup"><span data-stu-id="14d41-356">5067</span></span></p></td>
<td><p><span data-ttu-id="14d41-357">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-358">用于来自 PSTN 网关的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-359">中介服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-360">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="14d41-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="14d41-361">5068</span><span class="sxs-lookup"><span data-stu-id="14d41-361">5068</span></span></p></td>
<td><p><span data-ttu-id="14d41-362">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-363">用于来自 PSTN 网关的传入 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-364">中介服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="14d41-365">Lync Server 中介服务</span><span class="sxs-lookup"><span data-stu-id="14d41-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="14d41-366">5070</span><span class="sxs-lookup"><span data-stu-id="14d41-366">5070</span></span></p></td>
<td><p><span data-ttu-id="14d41-367">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-368">用于来自前端服务器的 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="14d41-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-369">持久聊天前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="14d41-370">持久聊天 SIP</span><span class="sxs-lookup"><span data-stu-id="14d41-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="14d41-371">5041</span><span class="sxs-lookup"><span data-stu-id="14d41-371">5041</span></span></p></td>
<td><p><span data-ttu-id="14d41-372">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-373">持久聊天前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="14d41-374"> (WCF) 的持久聊天 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="14d41-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="14d41-375">881</span><span class="sxs-lookup"><span data-stu-id="14d41-375">881</span></span></p></td>
<td><p><span data-ttu-id="14d41-376">TCP (TLS) 和 TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="14d41-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-377">持久聊天前端服务器</span><span class="sxs-lookup"><span data-stu-id="14d41-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="14d41-378">持久聊天文件传输服务</span><span class="sxs-lookup"><span data-stu-id="14d41-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="14d41-379">443</span><span class="sxs-lookup"><span data-stu-id="14d41-379">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-380">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="14d41-381">某些远程呼叫控制方案需要前端服务器或控制器与 PBX 之间的 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="14d41-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="14d41-382">尽管 Lync Server 不再使用 TCP 端口5060，但在远程呼叫控制部署期间，您可以创建一个受信任的服务器配置，该配置将 RCC 线路服务器 FQDN 与前端服务器或控制器用于连接 PBX 系统的 TCP 端口相关联。</span><span class="sxs-lookup"><span data-stu-id="14d41-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="14d41-383">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="14d41-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="14d41-384">对于仅使用硬件负载平衡（不是 DNS 负载平衡）的池，下表显示了需要打开硬件负载平衡器的端口。</span><span class="sxs-lookup"><span data-stu-id="14d41-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="14d41-385">仅使用硬件负载平衡时的硬件负载平衡器端口</span><span class="sxs-lookup"><span data-stu-id="14d41-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14d41-386">负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-386">Load Balancer</span></span></th>
<th><span data-ttu-id="14d41-387">端口</span><span class="sxs-lookup"><span data-stu-id="14d41-387">Port</span></span></th>
<th><span data-ttu-id="14d41-388">协议</span><span class="sxs-lookup"><span data-stu-id="14d41-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14d41-389">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-390">5061</span><span class="sxs-lookup"><span data-stu-id="14d41-390">5061</span></span></p></td>
<td><p><span data-ttu-id="14d41-391">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-392">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-393">444</span><span class="sxs-lookup"><span data-stu-id="14d41-393">444</span></span></p></td>
<td><p><span data-ttu-id="14d41-394">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-395">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-396">135</span><span class="sxs-lookup"><span data-stu-id="14d41-396">135</span></span></p></td>
<td><p><span data-ttu-id="14d41-397">DCOM 和远程过程调用 (RPC)</span><span class="sxs-lookup"><span data-stu-id="14d41-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-398">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-399">80</span><span class="sxs-lookup"><span data-stu-id="14d41-399">80</span></span></p></td>
<td><p><span data-ttu-id="14d41-400">HTTP</span><span class="sxs-lookup"><span data-stu-id="14d41-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-401">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-402">8080</span><span class="sxs-lookup"><span data-stu-id="14d41-402">8080</span></span></p></td>
<td><p><span data-ttu-id="14d41-403">TCP - 从前端服务器中进行的客户端和设备根证书检索 – NTLM 授权的客户端和设备</span><span class="sxs-lookup"><span data-stu-id="14d41-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-404">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-405">443</span><span class="sxs-lookup"><span data-stu-id="14d41-405">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-406">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-407">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-408">4443</span><span class="sxs-lookup"><span data-stu-id="14d41-408">4443</span></span></p></td>
<td><p><span data-ttu-id="14d41-409">HTTPS（来自反向代理）</span><span class="sxs-lookup"><span data-stu-id="14d41-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-410">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-411">5072</span><span class="sxs-lookup"><span data-stu-id="14d41-411">5072</span></span></p></td>
<td><p><span data-ttu-id="14d41-412">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-413">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-414">5073</span><span class="sxs-lookup"><span data-stu-id="14d41-414">5073</span></span></p></td>
<td><p><span data-ttu-id="14d41-415">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-416">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-417">5075</span><span class="sxs-lookup"><span data-stu-id="14d41-417">5075</span></span></p></td>
<td><p><span data-ttu-id="14d41-418">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-419">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-420">5076</span><span class="sxs-lookup"><span data-stu-id="14d41-420">5076</span></span></p></td>
<td><p><span data-ttu-id="14d41-421">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-422">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-423">5071</span><span class="sxs-lookup"><span data-stu-id="14d41-423">5071</span></span></p></td>
<td><p><span data-ttu-id="14d41-424">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-425">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-426">5080</span><span class="sxs-lookup"><span data-stu-id="14d41-426">5080</span></span></p></td>
<td><p><span data-ttu-id="14d41-427">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-428">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-429">448</span><span class="sxs-lookup"><span data-stu-id="14d41-429">448</span></span></p></td>
<td><p><span data-ttu-id="14d41-430">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-431">中介服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-432">5070</span><span class="sxs-lookup"><span data-stu-id="14d41-432">5070</span></span></p></td>
<td><p><span data-ttu-id="14d41-433">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-434">前端服务器负载平衡器 (如果池也运行中介服务器) </span><span class="sxs-lookup"><span data-stu-id="14d41-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="14d41-435">5070</span><span class="sxs-lookup"><span data-stu-id="14d41-435">5070</span></span></p></td>
<td><p><span data-ttu-id="14d41-436">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-437">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-438">443</span><span class="sxs-lookup"><span data-stu-id="14d41-438">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-439">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-440">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-441">444</span><span class="sxs-lookup"><span data-stu-id="14d41-441">444</span></span></p></td>
<td><p><span data-ttu-id="14d41-442">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-443">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-444">5061</span><span class="sxs-lookup"><span data-stu-id="14d41-444">5061</span></span></p></td>
<td><p><span data-ttu-id="14d41-445">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-446">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-447">4443</span><span class="sxs-lookup"><span data-stu-id="14d41-447">4443</span></span></p></td>
<td><p><span data-ttu-id="14d41-448">HTTPS（来自反向代理）</span><span class="sxs-lookup"><span data-stu-id="14d41-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="14d41-p107">使用 DNS 负载平衡的前端池和控制器池还必须部署硬件负载平衡器。下表显示了需要在这些硬件负载平衡器上打开的端口。</span><span class="sxs-lookup"><span data-stu-id="14d41-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="14d41-451">使用 DNS 负载平衡时的硬件负载平衡器端口</span><span class="sxs-lookup"><span data-stu-id="14d41-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14d41-452">负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-452">Load Balancer</span></span></th>
<th><span data-ttu-id="14d41-453">端口</span><span class="sxs-lookup"><span data-stu-id="14d41-453">Port</span></span></th>
<th><span data-ttu-id="14d41-454">协议</span><span class="sxs-lookup"><span data-stu-id="14d41-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14d41-455">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-456">80</span><span class="sxs-lookup"><span data-stu-id="14d41-456">80</span></span></p></td>
<td><p><span data-ttu-id="14d41-457">HTTP</span><span class="sxs-lookup"><span data-stu-id="14d41-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-458">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-459">443</span><span class="sxs-lookup"><span data-stu-id="14d41-459">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-460">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-461">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-462">8080</span><span class="sxs-lookup"><span data-stu-id="14d41-462">8080</span></span></p></td>
<td><p><span data-ttu-id="14d41-463">TCP - 从前端服务器中进行的客户端和设备根证书检索 – NTLM 授权的客户端和设备</span><span class="sxs-lookup"><span data-stu-id="14d41-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-464">前端服务器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-465">4443</span><span class="sxs-lookup"><span data-stu-id="14d41-465">4443</span></span></p></td>
<td><p><span data-ttu-id="14d41-466">HTTPS（来自反向代理）</span><span class="sxs-lookup"><span data-stu-id="14d41-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-467">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-468">443</span><span class="sxs-lookup"><span data-stu-id="14d41-468">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-469">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="14d41-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-470">控制器负载平衡器</span><span class="sxs-lookup"><span data-stu-id="14d41-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="14d41-471">4443</span><span class="sxs-lookup"><span data-stu-id="14d41-471">4443</span></span></p></td>
<td><p><span data-ttu-id="14d41-472">HTTPS（来自反向代理）</span><span class="sxs-lookup"><span data-stu-id="14d41-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="14d41-473">所需客户端端口</span><span class="sxs-lookup"><span data-stu-id="14d41-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14d41-474">组件</span><span class="sxs-lookup"><span data-stu-id="14d41-474">Component</span></span></th>
<th><span data-ttu-id="14d41-475">端口</span><span class="sxs-lookup"><span data-stu-id="14d41-475">Port</span></span></th>
<th><span data-ttu-id="14d41-476">协议</span><span class="sxs-lookup"><span data-stu-id="14d41-476">Protocol</span></span></th>
<th><span data-ttu-id="14d41-477">注释</span><span class="sxs-lookup"><span data-stu-id="14d41-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14d41-478">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-479">67/68</span><span class="sxs-lookup"><span data-stu-id="14d41-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="14d41-480">LDHCP</span><span class="sxs-lookup"><span data-stu-id="14d41-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-481">由 Lync Server 用来查找注册器 FQDN (即，如果 DNS SRV 失败且未) 配置手动设置。</span><span class="sxs-lookup"><span data-stu-id="14d41-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-482">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-483">443</span><span class="sxs-lookup"><span data-stu-id="14d41-483">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-484">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-485">用于外部用户访问的客户端到服务器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="14d41-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-486">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-487">443</span><span class="sxs-lookup"><span data-stu-id="14d41-487">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-488">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-489">用于外部用户访问 Web 会议会话。</span><span class="sxs-lookup"><span data-stu-id="14d41-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-490">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-491">443</span><span class="sxs-lookup"><span data-stu-id="14d41-491">443</span></span></p></td>
<td><p><span data-ttu-id="14d41-492">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="14d41-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="14d41-493">用于外部用户访问 A/V 会话和媒体 (TCP)</span><span class="sxs-lookup"><span data-stu-id="14d41-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-494">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-495">3478</span><span class="sxs-lookup"><span data-stu-id="14d41-495">3478</span></span></p></td>
<td><p><span data-ttu-id="14d41-496">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="14d41-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="14d41-497">用于外部用户访问 A/V 会话和媒体 (UDP) </span><span class="sxs-lookup"><span data-stu-id="14d41-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-498">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-499">5061</span><span class="sxs-lookup"><span data-stu-id="14d41-499">5061</span></span></p></td>
<td><p><span data-ttu-id="14d41-500">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="14d41-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="14d41-501">用于外部用户访问的客户端到服务器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="14d41-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-502">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="14d41-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="14d41-504">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-505">用于在 Lync 客户端和以前的客户端之间进行文件传输 (Microsoft Office 通信 Server 2007 R2、Microsoft Office 通信服务器2007和 Live 通信服务器 2005) 的客户端。</span><span class="sxs-lookup"><span data-stu-id="14d41-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-506">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="14d41-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="14d41-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="14d41-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="14d41-509">音频端口范围（最少需要 20 个端口）</span><span class="sxs-lookup"><span data-stu-id="14d41-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-510">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="14d41-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="14d41-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="14d41-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="14d41-513">视频端口范围（最少需要 20 个端口）。</span><span class="sxs-lookup"><span data-stu-id="14d41-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-514">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="14d41-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="14d41-516">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-517">对等文件传输（对于会议文件传输，客户端使用 PSOM）。</span><span class="sxs-lookup"><span data-stu-id="14d41-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d41-518">客户端</span><span class="sxs-lookup"><span data-stu-id="14d41-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="14d41-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="14d41-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="14d41-520">TCP</span><span class="sxs-lookup"><span data-stu-id="14d41-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-521">应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="14d41-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d41-522">Aastra 6721ip 公用区域电话</span><span class="sxs-lookup"><span data-stu-id="14d41-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="14d41-523">Aastra 6725ip 桌面电话</span><span class="sxs-lookup"><span data-stu-id="14d41-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="14d41-524">HP 4110 IP Phone（公用区域电话）</span><span class="sxs-lookup"><span data-stu-id="14d41-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="14d41-525">HP 4120 IP Phone（桌面电话）</span><span class="sxs-lookup"><span data-stu-id="14d41-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="14d41-526">Polycom CX500 IP 公用区域电话</span><span class="sxs-lookup"><span data-stu-id="14d41-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="14d41-527">Polycom CX600 IP 桌面电话</span><span class="sxs-lookup"><span data-stu-id="14d41-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="14d41-528">Polycom CX700 IP 桌面电话</span><span class="sxs-lookup"><span data-stu-id="14d41-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="14d41-529">Polycom CX3000 IP 会议电话</span><span class="sxs-lookup"><span data-stu-id="14d41-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="14d41-530">67/68</span><span class="sxs-lookup"><span data-stu-id="14d41-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="14d41-531">LDHCP</span><span class="sxs-lookup"><span data-stu-id="14d41-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="14d41-532">由列出的设备用来查找 Lync Server 证书、设置 FQDN 和注册器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="14d41-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="14d41-533">**\*** 若要配置这些媒体类型的特定端口，请使用 CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled、ClientMediaPort 和 ClientMediaPortRange 参数) 。</span><span class="sxs-lookup"><span data-stu-id="14d41-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14d41-534">为 Lync 客户端设置的程序会自动在客户端计算机上创建所需的操作系统防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="14d41-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="14d41-535">在客户端必须遍历组织的防火墙的任何方案中，都需要用于外部用户访问的端口（例如，由其他组织承载的任何外部通信或会议）。</span><span class="sxs-lookup"><span data-stu-id="14d41-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

