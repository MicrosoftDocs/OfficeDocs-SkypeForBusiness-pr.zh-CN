---
title: Lync Server 2013：外部用户访问所需的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895f2d4837eb465f0eead2b70cf1d603504699ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="88395-102">Lync Server 2013 中外部用户访问所需的组件</span><span class="sxs-lookup"><span data-stu-id="88395-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88395-103">_**主题上次修改时间:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="88395-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="88395-104">大多数边缘组件都部署在外围网络中。</span><span class="sxs-lookup"><span data-stu-id="88395-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="88395-105">以下组件构成了外围网络的边缘拓扑。</span><span class="sxs-lookup"><span data-stu-id="88395-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="88395-106">除非另有说明, 组件属于[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)的一部分, 并且位于外围网络中。</span><span class="sxs-lookup"><span data-stu-id="88395-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="88395-107">边缘组件包括下列各项：</span><span class="sxs-lookup"><span data-stu-id="88395-107">Edge components include the following:</span></span>

  - <span data-ttu-id="88395-108">Edge Servers</span><span class="sxs-lookup"><span data-stu-id="88395-108">Edge Servers</span></span>

  - <span data-ttu-id="88395-109">Reverse proxies</span><span class="sxs-lookup"><span data-stu-id="88395-109">Reverse proxies</span></span>

  - <span data-ttu-id="88395-110">Firewalls</span><span class="sxs-lookup"><span data-stu-id="88395-110">Firewalls</span></span>

  - <span data-ttu-id="88395-111">控制器（可选，并且逻辑上位于内部网络中）</span><span class="sxs-lookup"><span data-stu-id="88395-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="88395-112">扩展的边缘拓扑的负载平衡（DNS 负载平衡或硬件负载平衡器）</span><span class="sxs-lookup"><span data-stu-id="88395-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="88395-p102">不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="88395-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="88395-115">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="88395-115">Edge Servers</span></span>

<span data-ttu-id="88395-116">边缘服务器针对由外部用户内部部署提供的服务发送和接收网络流量。</span><span class="sxs-lookup"><span data-stu-id="88395-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="88395-117">边缘服务器运行以下服务:</span><span class="sxs-lookup"><span data-stu-id="88395-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="88395-118">**Access edge 服务**   access edge 服务为出站和入站会话初始协议 (SIP) 流量提供单个受信任的连接点。</span><span class="sxs-lookup"><span data-stu-id="88395-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="88395-119">**网络会议边缘服务**   web 会议 edge 服务允许外部用户加入托管在内部 Lync Server 2013 部署上的会议。</span><span class="sxs-lookup"><span data-stu-id="88395-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="88395-120">**A/v 边缘**   服务 a/v 边缘服务使音频、视频、应用程序共享和文件传输可供外部用户使用。</span><span class="sxs-lookup"><span data-stu-id="88395-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="88395-121">用户可以向包括外部参与者的会议添加音频和视频, 并且他们可以直接使用音频和/或视频与点对点会话中的外部用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="88395-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="88395-122">A/V 边缘服务还提供对桌面共享和文件传输的支持。</span><span class="sxs-lookup"><span data-stu-id="88395-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="88395-123">**XMPP 代理服务**   XMPP 代理服务接受并向已配置 XMPP 联盟合作伙伴发送可扩展消息和状态协议 (XMPP) 消息。</span><span class="sxs-lookup"><span data-stu-id="88395-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="88395-124">授权外部用户可以访问 Edge 服务器, 以便连接到您的内部 Lync Server 2013 部署, 但 Edge 服务器不提供对内部网络的任何其他访问的方法。</span><span class="sxs-lookup"><span data-stu-id="88395-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88395-125">部署边缘服务器以提供适用于已启用的 Lync 客户端和其他 Microsoft Edge 服务器 (如在联盟方案中) 的连接。</span><span class="sxs-lookup"><span data-stu-id="88395-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="88395-126">它们的设计目的不是允许来自其他终结点客户端或服务器类型的连接。</span><span class="sxs-lookup"><span data-stu-id="88395-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="88395-127">可部署 XMPP 网关服务器以允许与已配置的 XMPP 合作伙伴的连接。</span><span class="sxs-lookup"><span data-stu-id="88395-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="88395-128">Edge 服务器和 XMPP 网关只能支持来自这些客户端和联合类型的终结点连接。</span><span class="sxs-lookup"><span data-stu-id="88395-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="88395-129">反向代理</span><span class="sxs-lookup"><span data-stu-id="88395-129">Reverse Proxy</span></span>

<span data-ttu-id="88395-130">以下情况需要反向代理:</span><span class="sxs-lookup"><span data-stu-id="88395-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="88395-131">允许用户使用简单 Url 连接到会议或拨入式会议</span><span class="sxs-lookup"><span data-stu-id="88395-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="88395-132">允许外部用户下载会议内容</span><span class="sxs-lookup"><span data-stu-id="88395-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="88395-133">使外部用户能够展开通讯组</span><span class="sxs-lookup"><span data-stu-id="88395-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="88395-134">允许用户为基于客户端证书的身份验证获取基于用户的证书</span><span class="sxs-lookup"><span data-stu-id="88395-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="88395-135">允许远程用户从通讯簿服务器下载文件, 或将查询提交到通讯簿 Web 查询服务</span><span class="sxs-lookup"><span data-stu-id="88395-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="88395-136">使远程用户能够获取客户端和设备软件的更新</span><span class="sxs-lookup"><span data-stu-id="88395-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="88395-137">使移动设备能够自动发现前端服务器, 提供移动服务</span><span class="sxs-lookup"><span data-stu-id="88395-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="88395-138">从 Office 365 或 Apple 推送通知服务启用移动设备的推送通知</span><span class="sxs-lookup"><span data-stu-id="88395-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="88395-139">有关与反向代理和反向代理必须满足的要求相关的其他信息, 请参阅[Lync Server 2013 中反向代理的配置要求](lync-server-2013-configuration-requirements-for-reverse-proxy.md)中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88395-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88395-140">外部用户不需要与你的组织的虚拟专用网络 (VPN) 连接, 即可使用 Lync Server 2013 参与通信。</span><span class="sxs-lookup"><span data-stu-id="88395-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="88395-141">如果你已在组织中实现 VPN 技术, 并且你的用户使用的是 Lync 的 VPN, 则媒体流量 (如视频会议) 可能会受到不利影响。</span><span class="sxs-lookup"><span data-stu-id="88395-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="88395-142">你应该考虑为媒体流量提供一种方法来直接连接到 AV 边缘服务并绕过 VPN。</span><span class="sxs-lookup"><span data-stu-id="88395-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="88395-143">有关详细信息, 请参阅 NextHop 博客文章 "启用 Lync 媒体绕过 VPN 隧道" <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>。</span><span class="sxs-lookup"><span data-stu-id="88395-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="88395-144">防火墙</span><span class="sxs-lookup"><span data-stu-id="88395-144">Firewall</span></span>

<span data-ttu-id="88395-145">你可以仅使用外部防火墙或外部防火墙和内部防火墙部署 edge 拓扑。</span><span class="sxs-lookup"><span data-stu-id="88395-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="88395-146">方案体系结构包括两个防火墙。</span><span class="sxs-lookup"><span data-stu-id="88395-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="88395-147">使用两个防火墙是推荐的方法, 因为它确保严格地从一个网络边缘路由到另一个网络边缘, 并通过两个级别的防火墙保护内部部署。</span><span class="sxs-lookup"><span data-stu-id="88395-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="88395-148">控制器</span><span class="sxs-lookup"><span data-stu-id="88395-148">Director</span></span>

<span data-ttu-id="88395-149">Director 是 Lync Server 2013 中的一个独立的可选服务器角色, 它不会家庭用户帐户, 也不能提供状态或会议服务。</span><span class="sxs-lookup"><span data-stu-id="88395-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="88395-150">它充当一个内部下一个跃点服务器, 边缘服务器将入站 SIP 流量路由到内部服务器。</span><span class="sxs-lookup"><span data-stu-id="88395-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="88395-151">Director preauthenticates 入站请求并将其重定向到用户的主池或服务器。</span><span class="sxs-lookup"><span data-stu-id="88395-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="88395-152">通过在 Director 上 preauthenticating, 你可以丢弃对部署未知的用户帐户请求。</span><span class="sxs-lookup"><span data-stu-id="88395-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="88395-153">控制器可帮助将企业版前端池中的标准版服务器和前端服务器与恶意流量 (如拒绝服务 (DoS) 攻击) 隔离。</span><span class="sxs-lookup"><span data-stu-id="88395-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="88395-154">如果网络被此类攻击中的无效外部通信所淹没, 则流量将在 Director 处结束。</span><span class="sxs-lookup"><span data-stu-id="88395-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="88395-155">有关使用控制器的详细信息, 请参阅[Lync Server 2013 中的 Director 的方案](lync-server-2013-scenarios-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="88395-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88395-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88395-156">See Also</span></span>


[<span data-ttu-id="88395-157">Lync Server 2013 的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="88395-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

