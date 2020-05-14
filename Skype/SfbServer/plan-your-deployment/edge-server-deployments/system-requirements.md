---
title: Skype for Business Server 中的边缘服务器系统要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 摘要：了解 Skype for Business Server 中的边缘服务器的系统要求。
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221022"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="b234b-103">Skype for Business Server 中的边缘服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="b234b-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="b234b-104">**摘要：** 了解 Skype for Business Server 中的边缘服务器的系统要求。</span><span class="sxs-lookup"><span data-stu-id="b234b-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="b234b-105">在你的 Skype for Business Server Edge 服务器部署时，需要执行这些操作，才能针对环境本身中的服务器或服务器，以及规划环境结构。</span><span class="sxs-lookup"><span data-stu-id="b234b-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="b234b-106">有关拓扑、DNS、证书和其他基础结构问题的详细信息，请参阅环境要求文档。</span><span class="sxs-lookup"><span data-stu-id="b234b-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="b234b-107">组件</span><span class="sxs-lookup"><span data-stu-id="b234b-107">Components</span></span>

<span data-ttu-id="b234b-108">在讨论边缘服务器环境时，我们正在引用大多数在外围网络中部署的组件（这是指在工作组或位于 Skype for business Server 域之外的域中）。</span><span class="sxs-lookup"><span data-stu-id="b234b-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="b234b-109">请记住，以下是您在成功部署 Edge 时需要记住的组件：</span><span class="sxs-lookup"><span data-stu-id="b234b-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="b234b-110">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b234b-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="b234b-111">反向代理</span><span class="sxs-lookup"><span data-stu-id="b234b-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="b234b-112">道</span><span class="sxs-lookup"><span data-stu-id="b234b-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="b234b-113">[控制器](system-requirements.md#Directors)（这些是可选的，如果包含，它们将位于内部网络中）</span><span class="sxs-lookup"><span data-stu-id="b234b-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="b234b-114">[负载平衡](system-requirements.md#LoadBalancers)器（可以具有 DNS 负载平衡或硬件负载平衡器（HLB），但对于单个边缘服务器，不需要这样做。</span><span class="sxs-lookup"><span data-stu-id="b234b-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="b234b-115">下面详细介绍了每个选项：</span><span class="sxs-lookup"><span data-stu-id="b234b-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="b234b-116">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b234b-116">Edge Servers</span></span>
<span data-ttu-id="b234b-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="b234b-117"><a name="EdgeServers"> </a></span></span>

<span data-ttu-id="b234b-118">这些是部署在你的外围环境中的 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="b234b-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="b234b-119">其角色是向外部用户发送和接收由内部 Skype for Business Server 部署提供的服务的网络通信。</span><span class="sxs-lookup"><span data-stu-id="b234b-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="b234b-120">若要成功执行此操作，每台边缘服务器都将运行：</span><span class="sxs-lookup"><span data-stu-id="b234b-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="b234b-121">**访问边缘服务**：为出站和入站会话初始协议（SIP）流量提供单个受信任的连接点。</span><span class="sxs-lookup"><span data-stu-id="b234b-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="b234b-122">**Web 会议边缘服务**：允许外部用户加入托管在内部 Skype For business Server 环境中的会议。</span><span class="sxs-lookup"><span data-stu-id="b234b-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="b234b-123">**A/V 边缘服务**：使音频、视频、应用程序共享和文件传输可供外部用户使用。</span><span class="sxs-lookup"><span data-stu-id="b234b-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="b234b-124">**XMPP 代理服务**：接受并发送来自已配置的 XMPP 联盟伙伴的可扩展消息和状态协议（XMPP）消息。</span><span class="sxs-lookup"><span data-stu-id="b234b-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="b234b-125">已授权的外部用户可以使用边缘服务器连接到内部 Skype for Business Server 部署，否则，不会为任何人提供对内部网络的其他访问权限。</span><span class="sxs-lookup"><span data-stu-id="b234b-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b234b-126">部署边缘服务器以提供启用的 Skype for Business 客户端和其他边缘服务器（在联合身份验证方案中）的连接。</span><span class="sxs-lookup"><span data-stu-id="b234b-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="b234b-127">无法从其他终结点客户端或服务器类型进行连接。</span><span class="sxs-lookup"><span data-stu-id="b234b-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="b234b-128">XMPP 网关服务器可以允许与已配置的 XMPP 合作伙伴的连接。</span><span class="sxs-lookup"><span data-stu-id="b234b-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="b234b-129">但同样，这些是唯一可以使用的客户端和联合类型。</span><span class="sxs-lookup"><span data-stu-id="b234b-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="b234b-130">XMPP 网关和代理在 Skype for business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="b234b-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b234b-131">有关详细信息，请参阅[迁移 XMPP 联合](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="b234b-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="b234b-132">反向代理</span><span class="sxs-lookup"><span data-stu-id="b234b-132">Reverse proxies</span></span>
<span data-ttu-id="b234b-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="b234b-133"><a name="ReverseProxies"> </a></span></span>

<span data-ttu-id="b234b-134">反向代理（RP）服务器没有 Skype for Business Server 角色，但它是边缘服务器部署的基本组件。</span><span class="sxs-lookup"><span data-stu-id="b234b-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="b234b-135">反向代理允许外部用户执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b234b-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="b234b-136">使用简单 Url 连接到会议或电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="b234b-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="b234b-137">下载会议内容。</span><span class="sxs-lookup"><span data-stu-id="b234b-137">download meeting content.</span></span>
    
- <span data-ttu-id="b234b-138">展开 "通讯组"。</span><span class="sxs-lookup"><span data-stu-id="b234b-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="b234b-139">获取基于用户的证书以用于基于客户端证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="b234b-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="b234b-140">从通讯簿服务器下载文件，或将查询提交到通讯簿 Web 查询服务。</span><span class="sxs-lookup"><span data-stu-id="b234b-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="b234b-141">获取客户端和设备软件的更新。</span><span class="sxs-lookup"><span data-stu-id="b234b-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="b234b-142">对于移动设备：</span><span class="sxs-lookup"><span data-stu-id="b234b-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="b234b-143">它让他们能够自动发现提供移动服务的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="b234b-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="b234b-144">它支持从 Microsoft 365 或 Office 365 推送到移动设备的推送通知。</span><span class="sxs-lookup"><span data-stu-id="b234b-144">it enables push notifications from Microsoft 365 or Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="b234b-145">我们可以在[Skype for business 的电话基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)页上找到我们当前的反向代理建议。</span><span class="sxs-lookup"><span data-stu-id="b234b-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span> <span data-ttu-id="b234b-146">因此，你的反向代理：</span><span class="sxs-lookup"><span data-stu-id="b234b-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="b234b-147">应能够使用通过公共证书引入的环境中引入的传输层安全性（TLS），以连接到的发布的外部 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="b234b-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="b234b-148">控制器或控制器池</span><span class="sxs-lookup"><span data-stu-id="b234b-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="b234b-149">前端服务器或前端池</span><span class="sxs-lookup"><span data-stu-id="b234b-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="b234b-150">需要能够使用证书进行加密来发布内部网站，或在需要时通过未加密的方式发布这些网站。</span><span class="sxs-lookup"><span data-stu-id="b234b-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="b234b-151">应能够使用完全限定的域名（FQDN）在外部发布内部托管的网站。</span><span class="sxs-lookup"><span data-stu-id="b234b-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="b234b-152">需要能够发布托管网站的所有内容。</span><span class="sxs-lookup"><span data-stu-id="b234b-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="b234b-153">默认情况下，可以使用 **/\\** \* 指令，大多数 web 服务器都可以识别该指令，以表示 "发布 web 服务器上的所有内容"。</span><span class="sxs-lookup"><span data-stu-id="b234b-153">By default, you can use the **/\\**\* directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="b234b-154">您还可以修改指令（例如，\* \*/Uwca/ \\ \* \* \*），这意味着 "在虚拟目录 Ucwa 下发布所有内容"。</span><span class="sxs-lookup"><span data-stu-id="b234b-154">You can also modify the directive—for example, \*\*/Uwca/\\*\*\*, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="b234b-155">必须需要与从已发布网站请求内容的客户端进行 TLS 连接。</span><span class="sxs-lookup"><span data-stu-id="b234b-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="b234b-156">必须接受具有使用者可选名称（SAN）项的证书。</span><span class="sxs-lookup"><span data-stu-id="b234b-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="b234b-157">需要能够允许将证书绑定到外部 web 服务 FQDN 将解析的侦听器或接口。</span><span class="sxs-lookup"><span data-stu-id="b234b-157">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="b234b-158">侦听器配置优于接口。</span><span class="sxs-lookup"><span data-stu-id="b234b-158">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="b234b-159">可以在单个接口上配置多个侦听器。</span><span class="sxs-lookup"><span data-stu-id="b234b-159">Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="b234b-160">必须允许配置主机标头处理。</span><span class="sxs-lookup"><span data-stu-id="b234b-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="b234b-161">通常，发出请求的客户端发送的原始主机标头必须透明地传递，而不是由反向代理进行修改。</span><span class="sxs-lookup"><span data-stu-id="b234b-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="b234b-162">应允许将 TLS 流量从一个外部定义的端口（例如，TCP 443）桥接到另一个定义的端口（例如，TCP 4443）。</span><span class="sxs-lookup"><span data-stu-id="b234b-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="b234b-163">反向代理可能会在接收时对数据包进行解密，然后在发送时重新加密数据包。</span><span class="sxs-lookup"><span data-stu-id="b234b-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="b234b-164">应允许将未加密的 TCP 流量从一个端口桥接（例如，TCP 80）到另一个端口（例如，TCP 8080）。</span><span class="sxs-lookup"><span data-stu-id="b234b-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="b234b-165">需要允许配置或接受 NTLM 身份验证、无身份验证和传递身份验证。</span><span class="sxs-lookup"><span data-stu-id="b234b-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="b234b-166">如果反向代理可以满足此列表中的所有需求，则应转到，但请记住上面提供的链接中的建议。</span><span class="sxs-lookup"><span data-stu-id="b234b-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="b234b-167">道</span><span class="sxs-lookup"><span data-stu-id="b234b-167">Firewalls</span></span>
<span data-ttu-id="b234b-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="b234b-168"><a name="Firewalls"> </a></span></span>

<span data-ttu-id="b234b-169">您需要将边缘部署置于外部防火墙后面，但我们建议在边缘环境和内部环境之间使用两个防火墙（一个外部）和一个内部防火墙。</span><span class="sxs-lookup"><span data-stu-id="b234b-169">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment.</span></span> <span data-ttu-id="b234b-170">我们的应用场景中的所有文档都有两个防火墙。</span><span class="sxs-lookup"><span data-stu-id="b234b-170">All our documentation in our Scenarios will have two firewalls.</span></span> <span data-ttu-id="b234b-171">我们建议采用两个防火墙，因为它可确保严格地从一个网络边缘路由到另一个，并将内部网络的防火墙保护加倍。</span><span class="sxs-lookup"><span data-stu-id="b234b-171">We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="b234b-172">控制器</span><span class="sxs-lookup"><span data-stu-id="b234b-172">Directors</span></span>
<span data-ttu-id="b234b-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="b234b-173"><a name="Directors"> </a></span></span>

<span data-ttu-id="b234b-174">这是可选角色。</span><span class="sxs-lookup"><span data-stu-id="b234b-174">This is an optional role.</span></span> <span data-ttu-id="b234b-175">它可以是单个服务器，也可以是运行控制器角色的服务器池。</span><span class="sxs-lookup"><span data-stu-id="b234b-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="b234b-176">它是内置 Skype for Business Server 环境中的角色。</span><span class="sxs-lookup"><span data-stu-id="b234b-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="b234b-177">Director 是一个内部的下一个跃点服务器，它接收来自发往 Skype for Business Server 内部服务器的边缘服务器的入站 SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="b234b-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="b234b-178">它对入站请求，并将其重定向到用户的主池或服务器。</span><span class="sxs-lookup"><span data-stu-id="b234b-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="b234b-179">此预身份验证允许您删除未识别的用户帐户请求。</span><span class="sxs-lookup"><span data-stu-id="b234b-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="b234b-180">为什么要这么做呢？</span><span class="sxs-lookup"><span data-stu-id="b234b-180">Why does that matter?</span></span> <span data-ttu-id="b234b-181">Director 的一个重要功能是保护 Standard Edition 服务器和前端服务器或前端池免遭恶意流量（如拒绝服务（DoS）攻击）。</span><span class="sxs-lookup"><span data-stu-id="b234b-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="b234b-182">如果你的网络充斥了无效的外部流量，则流量将在控制器处停止。</span><span class="sxs-lookup"><span data-stu-id="b234b-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="b234b-183">负载平衡器</span><span class="sxs-lookup"><span data-stu-id="b234b-183">Load Balancers</span></span>
<span data-ttu-id="b234b-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="b234b-184"><a name="LoadBalancers"> </a></span></span>

<span data-ttu-id="b234b-185">Skype for Business Server 扩展的合并边缘拓扑已针对新部署的 DNS 负载平衡进行了优化，我们建议这样做。</span><span class="sxs-lookup"><span data-stu-id="b234b-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="b234b-186">如果需要高可用性，建议使用硬件负载平衡器来实现一种特定情况：</span><span class="sxs-lookup"><span data-stu-id="b234b-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="b234b-187">Exchange 2013**之前**使用 exchange um 的远程用户的 exchange um。</span><span class="sxs-lookup"><span data-stu-id="b234b-187">Exchange UM for remote users using Exchange UM **prior** to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b234b-188">需要注意的重要一点是，不能混合使用负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="b234b-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="b234b-189">在 Skype for Business Server 环境中，所有接口都必须使用 DNS 或 HLB。</span><span class="sxs-lookup"><span data-stu-id="b234b-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b234b-190">Skype for business Server 不支持直接服务器返回（DSR） NAT。</span><span class="sxs-lookup"><span data-stu-id="b234b-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="b234b-191">边缘服务器的硬件负载平衡器要求运行 A/V 边缘服务的边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b234b-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="b234b-192">对于运行 A/V 边缘服务的任何边缘服务器，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="b234b-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="b234b-193">对内部和外部端口443关闭 TCP nagling （nagling 是将几个小型数据包合并成一个较大的数据包以提高传输效率的过程）。</span><span class="sxs-lookup"><span data-stu-id="b234b-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="b234b-194">对于外部端口范围 50000-59999，请关闭 TCP nagling。</span><span class="sxs-lookup"><span data-stu-id="b234b-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="b234b-195">请勿在内部或外部防火墙上使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="b234b-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="b234b-196">您的边缘内部接口必须位于与边缘服务器外部接口不同的网络上，并且必须禁用它们之间的路由。</span><span class="sxs-lookup"><span data-stu-id="b234b-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="b234b-197">运行 A/V 边缘服务的任何边缘服务器的外部接口都必须使用可公开路由的 IP 地址，并且不会在任何边缘外部 IP 地址上进行 NAT 或端口转换。</span><span class="sxs-lookup"><span data-stu-id="b234b-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="b234b-198">HLB 要求</span><span class="sxs-lookup"><span data-stu-id="b234b-198">HLB requirements</span></span>

<span data-ttu-id="b234b-199">Skype for Business Server 不具有很多基于 cookie 的相关性要求。</span><span class="sxs-lookup"><span data-stu-id="b234b-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="b234b-200">因此，您不需要使用基于 cookie 的持久性，**除非**（且这是 skype For business server 2015 专用的）您的 skype For business server 环境中将包含 Lync Server 2010 前端服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="b234b-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="b234b-201">在为 Lync Server 2010 推荐的配置方法中，它们需要基于 cookie 的相关性。</span><span class="sxs-lookup"><span data-stu-id="b234b-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b234b-202">如果您决定为您的 HLB 启用基于 cookie 的相关性，则即使您的环境不需要，也不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="b234b-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="b234b-203">如果您的环境**不**需要基于 cookie 的相关性：</span><span class="sxs-lookup"><span data-stu-id="b234b-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="b234b-204">在端口443的反向代理发布规则上，将 "**转发主机头**" 设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="b234b-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="b234b-205">这将确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="b234b-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="b234b-206">对于**确实**需要基于 cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="b234b-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="b234b-207">在端口443的反向代理发布规则上，将 "**转发主机头**" 设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="b234b-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="b234b-208">这将确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="b234b-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="b234b-209">硬件负载平衡器 cookie**不得**标记为 "httpOnly"。</span><span class="sxs-lookup"><span data-stu-id="b234b-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="b234b-210">硬件负载平衡器 cookie**不得**具有过期时间。</span><span class="sxs-lookup"><span data-stu-id="b234b-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="b234b-211">硬件负载平衡器 cookie**必须**命名为**MS-WSMAN** （这是 Web 服务预期的值，并且不能更改）。</span><span class="sxs-lookup"><span data-stu-id="b234b-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="b234b-212">必须在传入的 HTTP 请求没有 cookie 的每个 HTTP 响应中设置硬件负载平衡器 cookie，而**不**考虑该 TCP 连接上以前的 http 响应是否已获得 cookie。</span><span class="sxs-lookup"><span data-stu-id="b234b-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="b234b-213">如果您的硬件负载平衡器将 cookie 插入优化为每个 TCP 连接只发生一次，则**不得**使用该优化。</span><span class="sxs-lookup"><span data-stu-id="b234b-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b234b-214">通常情况下，HLB 配置使用源相关性和20分钟 TCP 会话生存期（适用于 Skype for business Server 及其客户端），因为会话状态是通过客户端使用和/或应用程序交互来维护的。</span><span class="sxs-lookup"><span data-stu-id="b234b-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="b234b-215">如果要部署移动设备，HLB 必须能够在 TCP 会话中对单个请求进行负载平衡（实际上，您需要能够根据目标 IP 地址对单个请求进行负载平衡）。</span><span class="sxs-lookup"><span data-stu-id="b234b-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b234b-216">F5 Hlb 具有称为 "OneConnect" 的功能。</span><span class="sxs-lookup"><span data-stu-id="b234b-216">F5 HLBs have a feature called OneConnect.</span></span> <span data-ttu-id="b234b-217">它确保 TCP 连接中的每个请求都单独进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="b234b-217">It ensures that each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="b234b-218">如果要部署移动设备，请确保您的 HLB 供应商支持相同的功能。</span><span class="sxs-lookup"><span data-stu-id="b234b-218">If you're deploying mobile devices, ensure your HLB vendor supports the same functionality.</span></span> <span data-ttu-id="b234b-219">最新的 iOS 移动应用需要 TLS 版本1.2。</span><span class="sxs-lookup"><span data-stu-id="b234b-219">The latest iOS mobile apps require TLS version 1.2.</span></span> <span data-ttu-id="b234b-220">如果需要了解详细信息，按 F5 可为此提供特定的设置。</span><span class="sxs-lookup"><span data-stu-id="b234b-220">If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="b234b-221">以下是（可选） Director 和（必需）前端池 Web 服务的 HLB 要求：</span><span class="sxs-lookup"><span data-stu-id="b234b-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="b234b-222">对于内部 Web 服务 Vip，请在 HLB 上设置 Source_addr 持久性（内部端口80、443）。</span><span class="sxs-lookup"><span data-stu-id="b234b-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="b234b-223">对于 Skype for Business Server，Source_addr 暂留意味着来自单个 IP 地址的多个连接将始终发送到一台服务器，以维护会话状态。</span><span class="sxs-lookup"><span data-stu-id="b234b-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="b234b-224">使用1800秒的 TCP 空闲超时。</span><span class="sxs-lookup"><span data-stu-id="b234b-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="b234b-225">在反向代理与下一个跃点池的 HLB 之间的防火墙上，创建一个规则，以允许从您的反向代理到您的 HLB 的端口4443上的 https：流量。</span><span class="sxs-lookup"><span data-stu-id="b234b-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="b234b-226">您的 HLB 需要配置为侦听端口80、443和4443。</span><span class="sxs-lookup"><span data-stu-id="b234b-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="b234b-227">HLB 相关性要求摘要</span><span class="sxs-lookup"><span data-stu-id="b234b-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="b234b-228">**客户端/用户位置**</span><span class="sxs-lookup"><span data-stu-id="b234b-228">**Client/user location**</span></span>|<span data-ttu-id="b234b-229">**外部 Web 服务 FQDN 关联要求**</span><span class="sxs-lookup"><span data-stu-id="b234b-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="b234b-230">**内部 web 服务 FQDN 相关性要求**</span><span class="sxs-lookup"><span data-stu-id="b234b-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b234b-231">Skype for Business Web 应用程序（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="b234b-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="b234b-232">移动设备（内部和外部用户</span><span class="sxs-lookup"><span data-stu-id="b234b-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="b234b-233">无相关性</span><span class="sxs-lookup"><span data-stu-id="b234b-233">No affinity</span></span>  <br/> |<span data-ttu-id="b234b-234">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="b234b-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="b234b-235">Skype for Business Web 应用程序（仅限外部用户）</span><span class="sxs-lookup"><span data-stu-id="b234b-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="b234b-236">移动设备（内部和外部用户</span><span class="sxs-lookup"><span data-stu-id="b234b-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="b234b-237">无相关性</span><span class="sxs-lookup"><span data-stu-id="b234b-237">No affinity</span></span>  <br/> |<span data-ttu-id="b234b-238">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="b234b-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="b234b-239">Skype for Business Web 应用程序（仅限内部用户）</span><span class="sxs-lookup"><span data-stu-id="b234b-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="b234b-240">移动设备（未部署）</span><span class="sxs-lookup"><span data-stu-id="b234b-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="b234b-241">无相关性</span><span class="sxs-lookup"><span data-stu-id="b234b-241">No affinity</span></span>  <br/> |<span data-ttu-id="b234b-242">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="b234b-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="b234b-243">Hlb 的端口监视</span><span class="sxs-lookup"><span data-stu-id="b234b-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="b234b-244">您可以在硬件负载平衡器上定义端口监控，以确定特定服务何时不再可用，因为硬件或通信故障。</span><span class="sxs-lookup"><span data-stu-id="b234b-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="b234b-245">例如，如果前端服务器服务（RTCSRV）因前端服务器或前端池出现故障而停止，则 HLB 监视还应停止接收 Web 服务上的流量。</span><span class="sxs-lookup"><span data-stu-id="b234b-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="b234b-246">应在 HLB 上实现端口监控，以监视 HLB 外部接口的以下内容：</span><span class="sxs-lookup"><span data-stu-id="b234b-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="b234b-247">**虚拟 IP/端口**</span><span class="sxs-lookup"><span data-stu-id="b234b-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="b234b-248">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="b234b-248">**Node Port**</span></span>|<span data-ttu-id="b234b-249">**节点计算机/监视器**</span><span class="sxs-lookup"><span data-stu-id="b234b-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="b234b-250">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="b234b-250">**Persistence Profile**</span></span>|<span data-ttu-id="b234b-251">**Notes**</span><span class="sxs-lookup"><span data-stu-id="b234b-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b234b-252">\<池 \> web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="b234b-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="b234b-253">443</span><span class="sxs-lookup"><span data-stu-id="b234b-253">443</span></span>  <br/> |<span data-ttu-id="b234b-254">4443</span><span class="sxs-lookup"><span data-stu-id="b234b-254">4443</span></span>  <br/> |<span data-ttu-id="b234b-255">前端</span><span class="sxs-lookup"><span data-stu-id="b234b-255">Front End</span></span>  <br/> <span data-ttu-id="b234b-256">5061</span><span class="sxs-lookup"><span data-stu-id="b234b-256">5061</span></span>  <br/> |<span data-ttu-id="b234b-257">无</span><span class="sxs-lookup"><span data-stu-id="b234b-257">None</span></span>  <br/> |<span data-ttu-id="b234b-258">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="b234b-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="b234b-259">\<池 \> web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="b234b-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="b234b-260">80</span><span class="sxs-lookup"><span data-stu-id="b234b-260">80</span></span>  <br/> |<span data-ttu-id="b234b-261">8080</span><span class="sxs-lookup"><span data-stu-id="b234b-261">8080</span></span>  <br/> |<span data-ttu-id="b234b-262">前端</span><span class="sxs-lookup"><span data-stu-id="b234b-262">Front End</span></span>  <br/> <span data-ttu-id="b234b-263">5061</span><span class="sxs-lookup"><span data-stu-id="b234b-263">5061</span></span>  <br/> |<span data-ttu-id="b234b-264">无</span><span class="sxs-lookup"><span data-stu-id="b234b-264">None</span></span>  <br/> |<span data-ttu-id="b234b-265">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="b234b-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="b234b-266">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="b234b-266">Hardware and software requirements</span></span>

<span data-ttu-id="b234b-267">我们在 Skype for business [server 2015 的总体服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[Skype for business server 2019 文档的系统要求](../../../SfBServer2019/plan/system-requirements.md)中介绍了边缘服务器硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="b234b-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="b234b-268">并置</span><span class="sxs-lookup"><span data-stu-id="b234b-268">Collocation</span></span>

<span data-ttu-id="b234b-269">我们在[拓扑基础知识 For Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md)文档中介绍了边缘服务器并置。</span><span class="sxs-lookup"><span data-stu-id="b234b-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

