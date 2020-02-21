---
title: Lync Server 2013：外部用户访问所需的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca81e26e6a4b634b7b1f861ddfb0e0aedebca23f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="e82ab-102">Lync Server 2013 中的外部用户访问所需的组件</span><span class="sxs-lookup"><span data-stu-id="e82ab-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e82ab-103">_**上次修改的主题：** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="e82ab-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="e82ab-104">大多数边缘组件都部署在外围网络中。</span><span class="sxs-lookup"><span data-stu-id="e82ab-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="e82ab-105">以下组件组成了外围网络的边缘拓扑。</span><span class="sxs-lookup"><span data-stu-id="e82ab-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="e82ab-106">除非另有说明，组件是[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)的一部分，并且位于外围网络中。</span><span class="sxs-lookup"><span data-stu-id="e82ab-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="e82ab-107">边缘组件包括下列各项：</span><span class="sxs-lookup"><span data-stu-id="e82ab-107">Edge components include the following:</span></span>

  - <span data-ttu-id="e82ab-108">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="e82ab-108">Edge Servers</span></span>

  - <span data-ttu-id="e82ab-109">反向代理</span><span class="sxs-lookup"><span data-stu-id="e82ab-109">Reverse proxies</span></span>

  - <span data-ttu-id="e82ab-110">道</span><span class="sxs-lookup"><span data-stu-id="e82ab-110">Firewalls</span></span>

  - <span data-ttu-id="e82ab-111">控制器（可选，并在内部网络中逻辑上）</span><span class="sxs-lookup"><span data-stu-id="e82ab-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="e82ab-112">扩展的边缘拓扑的负载平衡（DNS 负载平衡或硬件负载平衡器）</span><span class="sxs-lookup"><span data-stu-id="e82ab-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e82ab-p102">不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="e82ab-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="e82ab-115">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="e82ab-115">Edge Servers</span></span>

<span data-ttu-id="e82ab-116">边缘服务器发送和接收外部用户由内部部署提供的服务的网络流量。</span><span class="sxs-lookup"><span data-stu-id="e82ab-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="e82ab-117">边缘服务器运行下列服务：</span><span class="sxs-lookup"><span data-stu-id="e82ab-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="e82ab-118">**访问边缘服务**   ： access edge 服务为出站和入站会话初始协议（SIP）流量提供单个受信任的连接点。</span><span class="sxs-lookup"><span data-stu-id="e82ab-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="e82ab-119">**Web 会议边缘服务**   web 会议边缘服务使外部用户能够加入托管在内部 Lync Server 2013 部署上的会议。</span><span class="sxs-lookup"><span data-stu-id="e82ab-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="e82ab-120">**A/v 边缘服务**   a/v 边缘服务使音频、视频、应用程序共享和文件传输可供外部用户使用。</span><span class="sxs-lookup"><span data-stu-id="e82ab-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="e82ab-121">您的用户可以向包含外部参与者的会议添加音频和视频，并且可以在点对点会话中使用音频和/或视频直接与外部用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="e82ab-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="e82ab-122">A/V 边缘服务还提供对桌面共享和文件传输的支持。</span><span class="sxs-lookup"><span data-stu-id="e82ab-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="e82ab-123">**XMPP 代理服务**   XMPP 代理服务接受并发送可扩展消息和状态协议（XMPP）消息，并发送到已配置的 XMPP 联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="e82ab-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="e82ab-124">授权的外部用户可以访问边缘服务器，以便连接到内部 Lync Server 2013 部署，但边缘服务器不提供对内部网络的任何其他访问的方法。</span><span class="sxs-lookup"><span data-stu-id="e82ab-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e82ab-125">部署边缘服务器以提供启用的 Lync 客户端和其他 Microsoft Edge 服务器（如在联合方案中）的连接。</span><span class="sxs-lookup"><span data-stu-id="e82ab-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="e82ab-126">它们的设计不允许来自其他端点客户端或服务器类型的连接。</span><span class="sxs-lookup"><span data-stu-id="e82ab-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="e82ab-127">可以部署 XMPP 网关服务器以允许与配置的 XMPP 合作伙伴之间的连接。</span><span class="sxs-lookup"><span data-stu-id="e82ab-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="e82ab-128">边缘服务器和 XMPP 网关仅支持来自这些客户端和联盟类型的端点连接。</span><span class="sxs-lookup"><span data-stu-id="e82ab-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="e82ab-129">反向代理</span><span class="sxs-lookup"><span data-stu-id="e82ab-129">Reverse Proxy</span></span>

<span data-ttu-id="e82ab-130">反向代理是实现以下功能所必需的：</span><span class="sxs-lookup"><span data-stu-id="e82ab-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="e82ab-131">允许用户使用简单 URL 连接到会议或电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="e82ab-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="e82ab-132">允许外部用户下载会议内容</span><span class="sxs-lookup"><span data-stu-id="e82ab-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="e82ab-133">允许外部用户扩展通讯组</span><span class="sxs-lookup"><span data-stu-id="e82ab-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="e82ab-134">允许用户获取基于用户的证书以便进行基于客户端证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="e82ab-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="e82ab-135">允许远程用户从通讯簿服务器下载文件，或者向通讯簿 Web 查询服务提交查询</span><span class="sxs-lookup"><span data-stu-id="e82ab-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="e82ab-136">允许远程用户获取客户端和设备软件的更新</span><span class="sxs-lookup"><span data-stu-id="e82ab-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="e82ab-137">允许移动设备自动发现提供 Mobility Service 的前端服务器</span><span class="sxs-lookup"><span data-stu-id="e82ab-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="e82ab-138">允许通过 Office 365 或 Apple 推送通知服务向移动设备发送推送通知</span><span class="sxs-lookup"><span data-stu-id="e82ab-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="e82ab-139">有关与反向代理和反向代理必须满足的要求相关的其他信息，请参阅[Lync Server 2013 中反向代理的配置要求](lync-server-2013-configuration-requirements-for-reverse-proxy.md)中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e82ab-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e82ab-140">外部用户不需要与您的组织的虚拟专用网络（VPN）连接即可参与使用 Lync Server 2013 的通信。</span><span class="sxs-lookup"><span data-stu-id="e82ab-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="e82ab-141">如果您在组织中实施了 VPN 技术，并且您的用户使用的是 Lync 的 VPN，媒体流量（如视频会议）可能会受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="e82ab-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="e82ab-142">应考虑为媒体通信提供直接连接到 AV 边缘服务的方法，并绕过 VPN。</span><span class="sxs-lookup"><span data-stu-id="e82ab-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="e82ab-143">有关详细信息，请参阅 NextHop 博客文章 "启用 Lync Media 绕过 VPN 隧道" <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>。</span><span class="sxs-lookup"><span data-stu-id="e82ab-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="e82ab-144">Firewall</span><span class="sxs-lookup"><span data-stu-id="e82ab-144">Firewall</span></span>

<span data-ttu-id="e82ab-145">可以在仅有外部防火墙的情况下部署边缘拓扑，也可以在外部防火墙和内部防火墙兼有的情况下部署边缘拓扑。</span><span class="sxs-lookup"><span data-stu-id="e82ab-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="e82ab-146">方案体系结构包括两个防火墙。</span><span class="sxs-lookup"><span data-stu-id="e82ab-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="e82ab-147">建议的方法是使用两道防火墙，因为这样可确保从一个网络边缘严格路由到另一网络边缘，并使内部部署享有两层防火墙的保护。</span><span class="sxs-lookup"><span data-stu-id="e82ab-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="e82ab-148">控制器</span><span class="sxs-lookup"><span data-stu-id="e82ab-148">Director</span></span>

<span data-ttu-id="e82ab-149">Director 是 Lync Server 2013 中的一个单独的可选服务器角色，它不会家庭用户帐户，也不提供状态或会议服务。</span><span class="sxs-lookup"><span data-stu-id="e82ab-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="e82ab-150">它充当内部下一个跃点服务器，边缘服务器将入站 SIP 流量路由到内部服务器。</span><span class="sxs-lookup"><span data-stu-id="e82ab-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="e82ab-151">Director 对入站请求，并将其重定向到用户的主池或服务器。</span><span class="sxs-lookup"><span data-stu-id="e82ab-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="e82ab-152">通过在 Director 的 preauthenticating，您可以从用户帐户中删除部署无法识别的请求。</span><span class="sxs-lookup"><span data-stu-id="e82ab-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="e82ab-153">控制器可帮助将 Enterprise Edition 前端池中的 Standard Edition 服务器和前端服务器与恶意流量（如拒绝服务（DoS）攻击）隔离。</span><span class="sxs-lookup"><span data-stu-id="e82ab-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="e82ab-154">如果网络在此类攻击中遇到无效的外部通信，则流量将在 Director 处结束。</span><span class="sxs-lookup"><span data-stu-id="e82ab-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="e82ab-155">有关使用控制器的详细信息，请参阅[Lync Server 2013 中的控制器方案](lync-server-2013-scenarios-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="e82ab-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e82ab-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e82ab-156">See Also</span></span>


[<span data-ttu-id="e82ab-157">Lync Server 2013 的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="e82ab-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

