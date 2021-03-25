---
title: Skype for Business Server 中的边缘服务器系统要求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：了解 Skype for Business Server 中边缘服务器的系统要求。
ms.openlocfilehash: d5003a265a53c3603892133077a961f54c974401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112738"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="3b815-103">Skype for Business Server 中的边缘服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="3b815-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="3b815-104">**摘要：** 了解 Skype for Business Server 中边缘服务器的系统要求。</span><span class="sxs-lookup"><span data-stu-id="3b815-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="3b815-105">对于 Skype for Business Server 边缘服务器部署，需要针对环境本身的一个或多个服务器执行这些操作，以及规划环境结构。</span><span class="sxs-lookup"><span data-stu-id="3b815-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="3b815-106">有关拓扑、DNS、证书和其他基础结构问题的信息，请查看环境要求文档。</span><span class="sxs-lookup"><span data-stu-id="3b815-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="3b815-107">组件</span><span class="sxs-lookup"><span data-stu-id="3b815-107">Components</span></span>

<span data-ttu-id="3b815-108">讨论边缘服务器环境时，我们主要引用在外围网络 (中部署的组件，即位于工作组或 Skype for Business Server 域结构) 外部的域中。</span><span class="sxs-lookup"><span data-stu-id="3b815-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="3b815-109">请记住，这些组件是成功部署边缘时需要记住的组件：</span><span class="sxs-lookup"><span data-stu-id="3b815-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="3b815-110">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="3b815-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="3b815-111">逆向代理</span><span class="sxs-lookup"><span data-stu-id="3b815-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="3b815-112">防火墙</span><span class="sxs-lookup"><span data-stu-id="3b815-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="3b815-113">[ (](system-requirements.md#Directors) 这些控制器是可选的，如果包含它们，它们将位于内部网络) </span><span class="sxs-lookup"><span data-stu-id="3b815-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="3b815-114">[负载平衡](system-requirements.md#LoadBalancers) 器 (可以具有 DNS 负载平衡或硬件负载平衡器 (HLB) ，但对于单个边缘服务器，这不是) </span><span class="sxs-lookup"><span data-stu-id="3b815-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="3b815-115">下面我们详细介绍了其中每一项：</span><span class="sxs-lookup"><span data-stu-id="3b815-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="3b815-116">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="3b815-116">Edge Servers</span></span>
<span data-ttu-id="3b815-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="3b815-117"><a name="EdgeServers"> </a></span></span>

<span data-ttu-id="3b815-118">这些是部署在外围环境的 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="3b815-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="3b815-119">他们的角色是向外部用户发送和接收由内部 Skype for Business Server 部署提供的服务的网络流量。</span><span class="sxs-lookup"><span data-stu-id="3b815-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="3b815-120">要成功执行这一操作，每台边缘服务器将运行：</span><span class="sxs-lookup"><span data-stu-id="3b815-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="3b815-121">**访问边缘服务**：为出站和入站会话初始协议提供单一的受信任连接点 (SIP) 流量。</span><span class="sxs-lookup"><span data-stu-id="3b815-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="3b815-122">**Web 会议边缘服务**：允许外部用户加入在内部 Skype for Business Server 环境中托管的会议。</span><span class="sxs-lookup"><span data-stu-id="3b815-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="3b815-123">**A/V 边缘服务**：使音频、视频、应用程序共享和文件传输对外部用户可用。</span><span class="sxs-lookup"><span data-stu-id="3b815-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="3b815-124">**XMPP 代理** 服务：接受 XMPP 联盟伙伴 (和发送) XMPP 联盟伙伴的可扩展消息传递和状态协议。</span><span class="sxs-lookup"><span data-stu-id="3b815-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="3b815-125">授权的外部用户可以使用边缘服务器连接到内部 Skype for Business Server 部署，但在其他情况下，他们不会为任何人提供对内部网络的其他访问。</span><span class="sxs-lookup"><span data-stu-id="3b815-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b815-126">边缘服务器部署为启用的 Skype for Business 客户端和其他边缘服务器提供连接， (联盟方案中) 。</span><span class="sxs-lookup"><span data-stu-id="3b815-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="3b815-127">无法从其他终端客户端或服务器类型进行连接。</span><span class="sxs-lookup"><span data-stu-id="3b815-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="3b815-128">XMPP 网关服务器可以允许与配置的 XMPP 合作伙伴建立连接。</span><span class="sxs-lookup"><span data-stu-id="3b815-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="3b815-129">但同样，这些类型是唯一能工作的客户端和联盟类型。</span><span class="sxs-lookup"><span data-stu-id="3b815-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="3b815-130">XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="3b815-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3b815-131">有关详细信息 [，请参阅迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。</span><span class="sxs-lookup"><span data-stu-id="3b815-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="3b815-132">逆向代理</span><span class="sxs-lookup"><span data-stu-id="3b815-132">Reverse proxies</span></span>
<span data-ttu-id="3b815-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="3b815-133"><a name="ReverseProxies"> </a></span></span>

<span data-ttu-id="3b815-134">反向代理 (RP) 服务器没有 Skype for Business Server 角色，但是边缘服务器部署的重要组件。</span><span class="sxs-lookup"><span data-stu-id="3b815-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="3b815-135">反向代理允许外部用户：</span><span class="sxs-lookup"><span data-stu-id="3b815-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="3b815-136">使用简单 URL 连接到会议或电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="3b815-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="3b815-137">下载会议内容。</span><span class="sxs-lookup"><span data-stu-id="3b815-137">download meeting content.</span></span>
    
- <span data-ttu-id="3b815-138">展开通讯组。</span><span class="sxs-lookup"><span data-stu-id="3b815-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="3b815-139">为基于客户端证书的身份验证获取基于用户的证书</span><span class="sxs-lookup"><span data-stu-id="3b815-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="3b815-140">从通讯簿服务器下载文件，或将查询提交到通讯簿 Web 查询服务。</span><span class="sxs-lookup"><span data-stu-id="3b815-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="3b815-141">获取客户端和设备软件的更新。</span><span class="sxs-lookup"><span data-stu-id="3b815-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="3b815-142">对于移动设备：</span><span class="sxs-lookup"><span data-stu-id="3b815-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="3b815-143">它允许他们自动发现提供移动服务的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="3b815-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="3b815-144">它支持从 Microsoft 365 或 Office 365 向移动设备发送推送通知。</span><span class="sxs-lookup"><span data-stu-id="3b815-144">it enables push notifications from Microsoft 365 or Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="3b815-145">我们的当前反向代理建议可在 Skype for [Business](../../../SfbPartnerCertification/certification/infra-gateways.md) 电话基础结构页面上找到。</span><span class="sxs-lookup"><span data-stu-id="3b815-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md) page.</span></span> <span data-ttu-id="3b815-146">因此反向代理：</span><span class="sxs-lookup"><span data-stu-id="3b815-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="3b815-147">应该能够使用传输层安全性 (TLS) 通过公共证书引入环境，以连接到以下已发布的外部 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="3b815-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="3b815-148">控制器或控制器池</span><span class="sxs-lookup"><span data-stu-id="3b815-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="3b815-149">前端服务器或前端池</span><span class="sxs-lookup"><span data-stu-id="3b815-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="3b815-150">需要能够使用加密证书发布内部网站，或者根据需要通过未加密的方式发布它们。</span><span class="sxs-lookup"><span data-stu-id="3b815-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="3b815-151">应该能够使用 FQDN 中的完全限定域名在外部发布 (托管) 。</span><span class="sxs-lookup"><span data-stu-id="3b815-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="3b815-152">需要能够发布托管网站的所有内容。</span><span class="sxs-lookup"><span data-stu-id="3b815-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="3b815-153">默认情况下，您可以使用 _指令，该指令被大多数 Web 服务器识别为表示"在 Web 服务器上 **/\\** 发布所有内容"。</span><span class="sxs-lookup"><span data-stu-id="3b815-153">By default, you can use the **/\\** _ directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="3b815-154">您还可以修改指令（例如 ，_\*/Uwca/ \*\*\*，这意味着"发布虚拟目录 \\ Ucwa 下的所有内容"。</span><span class="sxs-lookup"><span data-stu-id="3b815-154">You can also modify the directive—for example, _\*/Uwca/\\*\*\*, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="3b815-155">必须与从已发布网站请求内容的客户端建立 TLS 连接。</span><span class="sxs-lookup"><span data-stu-id="3b815-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="3b815-156">必须接受主题备用名称为 SAN (条目) 证书。</span><span class="sxs-lookup"><span data-stu-id="3b815-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="3b815-157">需要能够允许将证书绑定到外部 Web 服务 FQDN 将通过其解析的侦听器或接口。</span><span class="sxs-lookup"><span data-stu-id="3b815-157">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="3b815-158">侦听器配置比接口更可取。</span><span class="sxs-lookup"><span data-stu-id="3b815-158">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="3b815-159">可以在单个接口上配置许多侦听器。</span><span class="sxs-lookup"><span data-stu-id="3b815-159">Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="3b815-160">必须允许配置主机头处理。</span><span class="sxs-lookup"><span data-stu-id="3b815-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="3b815-161">通常，请求客户端发送的原始主机头必须以透明方式传递，而不是由反向代理修改。</span><span class="sxs-lookup"><span data-stu-id="3b815-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="3b815-162">应允许将 TLS 流量从一个外部定义的端口 (例如 TCP 443) 桥接到另一个定义的端口 (例如 TCP 4443) 。</span><span class="sxs-lookup"><span data-stu-id="3b815-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="3b815-163">反向代理可能在接收时解密数据包，然后在发送时重新加密数据包。</span><span class="sxs-lookup"><span data-stu-id="3b815-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="3b815-164">应允许将未加密的 TCP 流量从一个端口 (例如 TCP 80) 桥接到另一个端口 (例如 TCP 8080) 。</span><span class="sxs-lookup"><span data-stu-id="3b815-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="3b815-165">需要允许配置或接受 NTLM 身份验证、无身份验证和传递身份验证。</span><span class="sxs-lookup"><span data-stu-id="3b815-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="3b815-166">如果反向代理可以满足此列表中的所有需求，你应该可以继续操作，但请记住我们上面提供的链接中的建议。</span><span class="sxs-lookup"><span data-stu-id="3b815-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="3b815-167">防火墙</span><span class="sxs-lookup"><span data-stu-id="3b815-167">Firewalls</span></span>
<span data-ttu-id="3b815-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="3b815-168"><a name="Firewalls"> </a></span></span>

<span data-ttu-id="3b815-169">需要将边缘部署置于外部防火墙之后，但我们建议在边缘环境和内部环境之间设置两个防火墙，一个外部防火墙和一个内部防火墙。</span><span class="sxs-lookup"><span data-stu-id="3b815-169">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment.</span></span> <span data-ttu-id="3b815-170">方案的所有文档都有两个防火墙。</span><span class="sxs-lookup"><span data-stu-id="3b815-170">All our documentation in our Scenarios will have two firewalls.</span></span> <span data-ttu-id="3b815-171">我们建议使用两个防火墙，因为它可确保从一个网络边缘到另一个网络边缘的严格路由，并针对内部网络将防火墙保护增加一倍。</span><span class="sxs-lookup"><span data-stu-id="3b815-171">We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="3b815-172">控制器</span><span class="sxs-lookup"><span data-stu-id="3b815-172">Directors</span></span>
<span data-ttu-id="3b815-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="3b815-173"><a name="Directors"> </a></span></span>

<span data-ttu-id="3b815-174">这是可选角色。</span><span class="sxs-lookup"><span data-stu-id="3b815-174">This is an optional role.</span></span> <span data-ttu-id="3b815-175">它可以是单个服务器或运行控制器角色的服务器池。</span><span class="sxs-lookup"><span data-stu-id="3b815-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="3b815-176">这是在内部 Skype for Business Server 环境中找到的角色。</span><span class="sxs-lookup"><span data-stu-id="3b815-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="3b815-177">控制器是内部的下一个跃点服务器，它接收来自发往 Skype for Business Server 内部服务器的边缘服务器的入站 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="3b815-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="3b815-178">它会预授权入站请求，并重定向到用户主池或服务器。</span><span class="sxs-lookup"><span data-stu-id="3b815-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="3b815-179">此预身份验证允许你删除无法识别的用户帐户请求。</span><span class="sxs-lookup"><span data-stu-id="3b815-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="3b815-180">为什么这很重要？</span><span class="sxs-lookup"><span data-stu-id="3b815-180">Why does that matter?</span></span> <span data-ttu-id="3b815-181">控制器的一个重要功能是保护 Standard Edition 服务器和前端服务器或前端池免受恶意流量的攻击，例如拒绝服务 (DoS) 攻击。</span><span class="sxs-lookup"><span data-stu-id="3b815-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="3b815-182">如果网络被无效外部流量淹没，流量将停止在控制器上。</span><span class="sxs-lookup"><span data-stu-id="3b815-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="3b815-183">负载均衡器</span><span class="sxs-lookup"><span data-stu-id="3b815-183">Load Balancers</span></span>
<span data-ttu-id="3b815-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="3b815-184"><a name="LoadBalancers"> </a></span></span>

<span data-ttu-id="3b815-185">Skype for Business Server 扩展的合并边缘拓扑已针对新部署的 DNS 负载平衡进行了优化，建议这样做。</span><span class="sxs-lookup"><span data-stu-id="3b815-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="3b815-186">如果您需要高可用性，我们建议针对一种特定情况使用硬件负载平衡器：</span><span class="sxs-lookup"><span data-stu-id="3b815-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="3b815-187">Exchange 2013 之前使用 Exchange UM **的远程用户的** Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="3b815-187">Exchange UM for remote users using Exchange UM **prior** to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="3b815-188">值得注意的是，不能混合使用负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="3b815-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="3b815-189">在 Skype for Business Server 环境中，所有接口都必须使用 DNS 或 HLB。</span><span class="sxs-lookup"><span data-stu-id="3b815-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3b815-190">Skype for Business Server 不支持 (直接服务器) DSR 或 NAT。</span><span class="sxs-lookup"><span data-stu-id="3b815-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="3b815-191">运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="3b815-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="3b815-192">对于运行 A/V 边缘服务的任何边缘服务器，有以下要求：</span><span class="sxs-lookup"><span data-stu-id="3b815-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="3b815-193">关闭内部和外部端口 443 (tcp nagling 是一个将多个小数据包合并到单个较大数据包中以更有效地传输) 。</span><span class="sxs-lookup"><span data-stu-id="3b815-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="3b815-194">关闭外部端口范围 50000 - 59999 的 TCP nagling。</span><span class="sxs-lookup"><span data-stu-id="3b815-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="3b815-195">请勿在内部或外部防火墙上使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="3b815-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="3b815-196">边缘内部接口必须位于与边缘服务器外部接口不同的网络上，并且必须禁用它们之间的路由。</span><span class="sxs-lookup"><span data-stu-id="3b815-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="3b815-197">运行 A/V 边缘服务的任何边缘服务器的外部接口都必须使用可公开路由的 IP 地址，并且不能在任何边缘外部 IP 地址上进行 NAT 或端口转换。</span><span class="sxs-lookup"><span data-stu-id="3b815-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="3b815-198">HLB 要求</span><span class="sxs-lookup"><span data-stu-id="3b815-198">HLB requirements</span></span>

<span data-ttu-id="3b815-199">Skype for Business Server 没有很多基于 Cookie 的关联要求。</span><span class="sxs-lookup"><span data-stu-id="3b815-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="3b815-200">因此，无需使用基于 Cookie 的持久性，除非 **(且** 这是特定于 Skype for Business Server 2015 的) 你将在 Skype for Business Server 环境中拥有 Lync Server 2010 前端服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="3b815-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="3b815-201">它们将需要 Lync Server 2010 推荐的配置方法中基于 Cookie 的关联。</span><span class="sxs-lookup"><span data-stu-id="3b815-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b815-202">如果决定为 HLB 启用基于 Cookie 的关联，则这样做不会出现问题，即使您的环境不需要它。</span><span class="sxs-lookup"><span data-stu-id="3b815-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="3b815-203">如果你的环境 **不需要基于** Cookie 的关联：</span><span class="sxs-lookup"><span data-stu-id="3b815-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="3b815-204">在端口 443 的反向代理发布规则上，将 **"转发主机头"设置为\*\*\*\*"True"。**</span><span class="sxs-lookup"><span data-stu-id="3b815-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="3b815-205">这将确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="3b815-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="3b815-206">对于需要基于 **Cookie** 的关联部署的部署：</span><span class="sxs-lookup"><span data-stu-id="3b815-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="3b815-207">在端口 443 的反向代理发布规则上，将 **"转发主机头"设置为\*\*\*\*"True"。**</span><span class="sxs-lookup"><span data-stu-id="3b815-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="3b815-208">这将确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="3b815-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="3b815-209">硬件负载平衡器 Cookie **不得标记为** httpOnly。</span><span class="sxs-lookup"><span data-stu-id="3b815-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="3b815-210">硬件负载平衡器 Cookie **不得具有** 过期时间。</span><span class="sxs-lookup"><span data-stu-id="3b815-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="3b815-211">硬件负载平衡器 **cookie** 必须命名为 **MS-WSMAN** (这是 Web 服务期望的值，并且不能) 。</span><span class="sxs-lookup"><span data-stu-id="3b815-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="3b815-212">必须在传入 HTTP 请求没有 Cookie 的每一个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie。</span><span class="sxs-lookup"><span data-stu-id="3b815-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="3b815-213">如果硬件负载平衡器将 Cookie 插入优化为每个 TCP 连接仅发生一次，则不得 **使用** 该优化。</span><span class="sxs-lookup"><span data-stu-id="3b815-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3b815-214">HLB 配置通常使用源相关性和 20 分钟的 TCP 会话生存期，这适用于 Skype for Business Server 及其客户端，因为会话状态通过客户端使用和/或应用程序交互进行维护。</span><span class="sxs-lookup"><span data-stu-id="3b815-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="3b815-215">如果要部署移动设备，则 HLB 必须能够在有效 TCP 会话 (中对单个请求进行负载平衡，您需要能够基于目标 IP 地址) 对单个请求进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="3b815-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3b815-216">F5 HLB 具有一个称为 OneConnect 的功能。</span><span class="sxs-lookup"><span data-stu-id="3b815-216">F5 HLBs have a feature called OneConnect.</span></span> <span data-ttu-id="3b815-217">它确保 TCP 连接内的每个请求都单独进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="3b815-217">It ensures that each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="3b815-218">如果要部署移动设备，请确保您的 HLB 供应商支持相同的功能。</span><span class="sxs-lookup"><span data-stu-id="3b815-218">If you're deploying mobile devices, ensure your HLB vendor supports the same functionality.</span></span> <span data-ttu-id="3b815-219">最新的 iOS 移动应用需要 TLS 版本 1.2。</span><span class="sxs-lookup"><span data-stu-id="3b815-219">The latest iOS mobile apps require TLS version 1.2.</span></span> <span data-ttu-id="3b815-220">如果需要了解更多信息，F5 会为此提供特定设置。</span><span class="sxs-lookup"><span data-stu-id="3b815-220">If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="3b815-221">以下是前端池 Web 服务中 (控制器) 所需的 (HLB) HLB 要求：</span><span class="sxs-lookup"><span data-stu-id="3b815-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="3b815-222">对于内部 Web 服务 IP，Source_addr HLB (端口 80，443) 持久性。</span><span class="sxs-lookup"><span data-stu-id="3b815-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="3b815-223">对于 Skype for Business Server，Source_addr持久性意味着始终向一台服务器发送来自单个 IP 地址的多个连接，以维持会话状态。</span><span class="sxs-lookup"><span data-stu-id="3b815-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="3b815-224">使用 TCP 空闲超时 1800 秒。</span><span class="sxs-lookup"><span data-stu-id="3b815-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="3b815-225">在反向代理和下一个跃点池的 HLB 之间的防火墙上，创建一个规则以允许端口 4443 上的 https：流量从反向代理到 HLB。</span><span class="sxs-lookup"><span data-stu-id="3b815-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="3b815-226">HLB 需要配置为侦听端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="3b815-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="3b815-227">HLB 相关性要求摘要</span><span class="sxs-lookup"><span data-stu-id="3b815-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="3b815-228">**客户端/用户位置**</span><span class="sxs-lookup"><span data-stu-id="3b815-228">**Client/user location**</span></span>|<span data-ttu-id="3b815-229">**外部 Web 服务 FQDN 关联要求**</span><span class="sxs-lookup"><span data-stu-id="3b815-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="3b815-230">**内部 Web 服务 FQSN 相关性要求**</span><span class="sxs-lookup"><span data-stu-id="3b815-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b815-231">Skype for Business Web App (内部和外部用户) </span><span class="sxs-lookup"><span data-stu-id="3b815-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="3b815-232">移动设备 (内部和外部用户</span><span class="sxs-lookup"><span data-stu-id="3b815-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="3b815-233">无相关性</span><span class="sxs-lookup"><span data-stu-id="3b815-233">No affinity</span></span>  <br/> |<span data-ttu-id="3b815-234">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="3b815-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="3b815-235">Skype for Business Web App (外部用户) </span><span class="sxs-lookup"><span data-stu-id="3b815-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="3b815-236">移动设备 (内部和外部用户</span><span class="sxs-lookup"><span data-stu-id="3b815-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="3b815-237">无相关性</span><span class="sxs-lookup"><span data-stu-id="3b815-237">No affinity</span></span>  <br/> |<span data-ttu-id="3b815-238">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="3b815-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="3b815-239">Skype for Business Web App (内部用户) </span><span class="sxs-lookup"><span data-stu-id="3b815-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="3b815-240">移动设备（未部署）</span><span class="sxs-lookup"><span data-stu-id="3b815-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="3b815-241">无相关性</span><span class="sxs-lookup"><span data-stu-id="3b815-241">No affinity</span></span>  <br/> |<span data-ttu-id="3b815-242">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="3b815-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="3b815-243">HLB 的端口监控</span><span class="sxs-lookup"><span data-stu-id="3b815-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="3b815-244">在硬件负载平衡器上定义端口监控，以确定特定服务何时因硬件或通信故障而不再可用。</span><span class="sxs-lookup"><span data-stu-id="3b815-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="3b815-245">例如，如果前端服务器服务 (RTCSRV) 由于前端服务器或前端池出现故障而停止，则 HLB 监控也应停止接收 Web 服务上的流量。</span><span class="sxs-lookup"><span data-stu-id="3b815-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="3b815-246">应在 HLB 上实现端口监控，以监视 HLB 外部接口的以下内容：</span><span class="sxs-lookup"><span data-stu-id="3b815-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="3b815-247">**虚拟 IP/端口**</span><span class="sxs-lookup"><span data-stu-id="3b815-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="3b815-248">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="3b815-248">**Node Port**</span></span>|<span data-ttu-id="3b815-249">**节点计算机/监视器**</span><span class="sxs-lookup"><span data-stu-id="3b815-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="3b815-250">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="3b815-250">**Persistence Profile**</span></span>|<span data-ttu-id="3b815-251">**备注**</span><span class="sxs-lookup"><span data-stu-id="3b815-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b815-252">\<pool\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="3b815-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="3b815-253">443</span><span class="sxs-lookup"><span data-stu-id="3b815-253">443</span></span>  <br/> |<span data-ttu-id="3b815-254">4443</span><span class="sxs-lookup"><span data-stu-id="3b815-254">4443</span></span>  <br/> |<span data-ttu-id="3b815-255">前端</span><span class="sxs-lookup"><span data-stu-id="3b815-255">Front End</span></span>  <br/> <span data-ttu-id="3b815-256">5061</span><span class="sxs-lookup"><span data-stu-id="3b815-256">5061</span></span>  <br/> |<span data-ttu-id="3b815-257">无</span><span class="sxs-lookup"><span data-stu-id="3b815-257">None</span></span>  <br/> |<span data-ttu-id="3b815-258">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3b815-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="3b815-259">\<pool\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="3b815-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="3b815-260">80</span><span class="sxs-lookup"><span data-stu-id="3b815-260">80</span></span>  <br/> |<span data-ttu-id="3b815-261">8080</span><span class="sxs-lookup"><span data-stu-id="3b815-261">8080</span></span>  <br/> |<span data-ttu-id="3b815-262">前端</span><span class="sxs-lookup"><span data-stu-id="3b815-262">Front End</span></span>  <br/> <span data-ttu-id="3b815-263">5061</span><span class="sxs-lookup"><span data-stu-id="3b815-263">5061</span></span>  <br/> |<span data-ttu-id="3b815-264">无</span><span class="sxs-lookup"><span data-stu-id="3b815-264">None</span></span>  <br/> |<span data-ttu-id="3b815-265">HTTP</span><span class="sxs-lookup"><span data-stu-id="3b815-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="3b815-266">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="3b815-266">Hardware and software requirements</span></span>

<span data-ttu-id="3b815-267">我们在 Skype [for Business Server 2015 的总体服务器要求和 Skype for Business Server 2019](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 的系统要求文档中介绍了  [边缘服务器](../../../SfBServer2019/plan/system-requirements.md) 硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="3b815-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="3b815-268">并置</span><span class="sxs-lookup"><span data-stu-id="3b815-268">Collocation</span></span>

<span data-ttu-id="3b815-269">我们在 [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) 文档中介绍了边缘服务器并置。</span><span class="sxs-lookup"><span data-stu-id="3b815-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
