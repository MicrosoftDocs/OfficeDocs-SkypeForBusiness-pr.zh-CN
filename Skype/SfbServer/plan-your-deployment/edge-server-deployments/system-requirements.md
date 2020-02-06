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
description: 摘要：了解 Skype for Business Server 中 Edge 服务器的系统要求。
ms.openlocfilehash: 4ef2feeb2b486bc9be9f4eb59136d74ef542dd31
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803312"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="ff431-103">Skype for Business Server 中的边缘服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="ff431-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="ff431-104">**摘要：** 了解 Skype for Business Server 中 Edge 服务器的系统要求。</span><span class="sxs-lookup"><span data-stu-id="ff431-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="ff431-105">在你的 Skype for Business Server Edge 服务器部署时，这些是你需要对环境本身中的服务器或服务器进行的操作，以及规划环境结构。</span><span class="sxs-lookup"><span data-stu-id="ff431-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="ff431-106">有关拓扑、DNS 证书和其他基础结构问题的详细信息，请查看环境要求文档。</span><span class="sxs-lookup"><span data-stu-id="ff431-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="ff431-107">组件</span><span class="sxs-lookup"><span data-stu-id="ff431-107">Components</span></span>

<span data-ttu-id="ff431-108">当讨论 Edge 服务器环境时，我们将引用在外围网络中部署的大部分组件（这是指在工作组或 Skype for business Server 域结构之外的域中）。</span><span class="sxs-lookup"><span data-stu-id="ff431-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="ff431-109">请记住，这些组件是为了成功部署边缘而需要牢记于胸的组件：</span><span class="sxs-lookup"><span data-stu-id="ff431-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="ff431-110">Edge Servers</span><span class="sxs-lookup"><span data-stu-id="ff431-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="ff431-111">Reverse proxies</span><span class="sxs-lookup"><span data-stu-id="ff431-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="ff431-112">Firewalls</span><span class="sxs-lookup"><span data-stu-id="ff431-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="ff431-113">[Directors](system-requirements.md#Directors)（这类组件是可选的，如果纳入这些组件，它们将位于内部网络中）</span><span class="sxs-lookup"><span data-stu-id="ff431-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="ff431-114">[负载平衡](system-requirements.md#LoadBalancers)器（可以拥有 DNS 负载平衡或硬件负载平衡器（HLB），但对于单个边缘服务器，不需要这样做。</span><span class="sxs-lookup"><span data-stu-id="ff431-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="ff431-115">下面我们更详细地谈论以下每个组件：</span><span class="sxs-lookup"><span data-stu-id="ff431-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="ff431-116">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="ff431-116">Edge Servers</span></span>
<span data-ttu-id="ff431-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="ff431-117"><a name="EdgeServers"> </a></span></span>

<span data-ttu-id="ff431-118">这些是您的外围环境中部署的 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="ff431-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="ff431-119">其角色是向外部用户发送和接收网络流量，以供内部 Skype for Business 服务器部署所提供的服务。</span><span class="sxs-lookup"><span data-stu-id="ff431-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="ff431-120">若要成功执行此操作，每台边缘服务器都将运行：</span><span class="sxs-lookup"><span data-stu-id="ff431-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="ff431-121">**Access Edge 服务**：为出站和入站会话初始协议（SIP）流量提供单个受信任的连接点。</span><span class="sxs-lookup"><span data-stu-id="ff431-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="ff431-122">**网络会议边缘服务**：允许外部用户加入托管在内部 Skype For business 服务器环境中的会议。</span><span class="sxs-lookup"><span data-stu-id="ff431-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="ff431-123">**A/V 边缘服务**：使音频、视频、应用程序共享和文件传输可供外部用户使用。</span><span class="sxs-lookup"><span data-stu-id="ff431-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="ff431-124">**XMPP 代理服务**：接受和发送可扩展消息和状态协议（XMPP）消息，并发送到已配置的 XMPP 联盟合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="ff431-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="ff431-125">已授权的外部用户可以使用你的 Edge 服务器连接到内部 Skype for Business 服务器部署，否则，它们不会为任何人提供对内部网络的其他访问权限。</span><span class="sxs-lookup"><span data-stu-id="ff431-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff431-126">部署边缘服务器以提供适用于已启用的 Skype for Business 客户端和其他边缘服务器（在联合身份验证方案中）的连接。</span><span class="sxs-lookup"><span data-stu-id="ff431-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="ff431-127">不能从其他端点客户端或服务器节点进行连接。</span><span class="sxs-lookup"><span data-stu-id="ff431-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="ff431-128">XMPP 网关服务器可允许与配置的 XMPP 伙伴进行连接。</span><span class="sxs-lookup"><span data-stu-id="ff431-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="ff431-129">但同样，这些伙伴仅限可行的客户端和联盟类型。</span><span class="sxs-lookup"><span data-stu-id="ff431-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="ff431-130">XMPP 网关和代理在 Skype for business Server 2015 中可用，但 Skype for business Server 2019 不再支持。</span><span class="sxs-lookup"><span data-stu-id="ff431-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ff431-131">有关详细信息，请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="ff431-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="ff431-132">反向代理</span><span class="sxs-lookup"><span data-stu-id="ff431-132">Reverse proxies</span></span>
<span data-ttu-id="ff431-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="ff431-133"><a name="ReverseProxies"> </a></span></span>

<span data-ttu-id="ff431-134">反向代理（RP）服务器没有 Skype for business 服务器角色，但是边缘服务器部署的基本组件。</span><span class="sxs-lookup"><span data-stu-id="ff431-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="ff431-135">反向代理允许外部用户：</span><span class="sxs-lookup"><span data-stu-id="ff431-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="ff431-136">使用简单 URL 连接到会议或电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="ff431-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="ff431-137">下载会议内容。</span><span class="sxs-lookup"><span data-stu-id="ff431-137">download meeting content.</span></span>
    
- <span data-ttu-id="ff431-138">展开通讯组。</span><span class="sxs-lookup"><span data-stu-id="ff431-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="ff431-139">获取基于用户的证书，用于基于客户端证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="ff431-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="ff431-140">从通讯簿服务器下载文件，或将查询提交到通讯簿 Web 查询服务。</span><span class="sxs-lookup"><span data-stu-id="ff431-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="ff431-141">获得客户和设备软件的更新。</span><span class="sxs-lookup"><span data-stu-id="ff431-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="ff431-142">对于移动设备：</span><span class="sxs-lookup"><span data-stu-id="ff431-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="ff431-143">它让他们能够自动发现提供移动服务的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ff431-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="ff431-144">它支持从 Office 365 到移动设备的推送通知。</span><span class="sxs-lookup"><span data-stu-id="ff431-144">it enables push notifications from Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="ff431-145">我们可以在[Skype for business 的电话结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)页面上找到当前的反向代理建议。</span><span class="sxs-lookup"><span data-stu-id="ff431-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span> <span data-ttu-id="ff431-146">因此，您的反向代理：</span><span class="sxs-lookup"><span data-stu-id="ff431-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="ff431-147">应能够使用通过公共证书引入环境的传输层安全性 (TLS) 连接到以下对象的已发布外部 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="ff431-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="ff431-148">导演或控制器池</span><span class="sxs-lookup"><span data-stu-id="ff431-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="ff431-149">前端服务器或前端池</span><span class="sxs-lookup"><span data-stu-id="ff431-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="ff431-150">需要能使用加密证书发布内部网站，或者根据需要以未加密的方式发布这些网站。</span><span class="sxs-lookup"><span data-stu-id="ff431-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="ff431-151">应能够使用完全限定域名 (FQDN) 在外部发布内部托管网站。</span><span class="sxs-lookup"><span data-stu-id="ff431-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="ff431-152">需要能发布托管网站的所有内容。</span><span class="sxs-lookup"><span data-stu-id="ff431-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="ff431-153">默认情况下，你可以使用\*\* / \*\*\* 指令，大多数 web 服务器可以识别该指令以表示 "发布 web 服务器上的所有内容"。</span><span class="sxs-lookup"><span data-stu-id="ff431-153">By default, you can use the **/\\**\* directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="ff431-154">您也可以修改指令，例如 \* */Uwca/\\* \* \*，这意味着 "在虚拟目录 Ucwa 下发布所有内容"。</span><span class="sxs-lookup"><span data-stu-id="ff431-154">You can also modify the directive—for example, \*\*/Uwca/\\*\*\*, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="ff431-155">必须与从发布的网站请求内容的客户端建立 TLS 连接。</span><span class="sxs-lookup"><span data-stu-id="ff431-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="ff431-156">必须接受包含使用者替代名称 (SAN) 条目的证书。</span><span class="sxs-lookup"><span data-stu-id="ff431-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="ff431-p108">需要能允许将证书绑定到将通过其解析外部 Web 服务 FQDN 的侦听器或接口。侦听器配置优于接口配置。可在一个接口上配置多个侦听器。</span><span class="sxs-lookup"><span data-stu-id="ff431-p108">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve. Listener configurations are preferable to interfaces. Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="ff431-160">必须允许配置主机头处理。</span><span class="sxs-lookup"><span data-stu-id="ff431-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="ff431-161">通常，发出请求的客户端发送的原始主机标头必须透明地传递，而不是由反向代理进行修改。</span><span class="sxs-lookup"><span data-stu-id="ff431-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="ff431-162">应允许将来自某个外部定义的端口（如 TCP 443）的 TLS 流量桥接至另一个定义的端口（如 TCP 4443）。</span><span class="sxs-lookup"><span data-stu-id="ff431-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="ff431-163">你的反向代理可能会在接收时解密数据包，然后在发送时 reencrypt 数据包。</span><span class="sxs-lookup"><span data-stu-id="ff431-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="ff431-164">应将来自某个端口（如 TCP 80）的未加密 TCP 流量桥接至另一端口（如 TCP 8080）。</span><span class="sxs-lookup"><span data-stu-id="ff431-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="ff431-165">需要允许配置或接受“NTLM 身份验证”、“无身份验证”和“传递身份验证”。</span><span class="sxs-lookup"><span data-stu-id="ff431-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="ff431-166">如果您的反向代理可以满足此列表中的所有需求，您应该可以转到，但请记住上面提供的链接的建议。</span><span class="sxs-lookup"><span data-stu-id="ff431-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="ff431-167">防火墙</span><span class="sxs-lookup"><span data-stu-id="ff431-167">Firewalls</span></span>
<span data-ttu-id="ff431-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="ff431-168"><a name="Firewalls"> </a></span></span>

<span data-ttu-id="ff431-p111">需要将边缘部署放在外部防火墙后面，但是我们建议在边缘环境和内部环境之间设两个防火墙，一个外部，一个内部。我们方案的所有文档都有两个防火墙。我们之所以推荐两道防火墙是因为，这可确保从一个网络边缘到另一个网络边缘的严格路由，并对内部网络实施加倍防火墙保护。</span><span class="sxs-lookup"><span data-stu-id="ff431-p111">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment. All our documentation in our Scenarios will have two firewalls. We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="ff431-172">控制器</span><span class="sxs-lookup"><span data-stu-id="ff431-172">Directors</span></span>
<span data-ttu-id="ff431-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="ff431-173"><a name="Directors"> </a></span></span>

<span data-ttu-id="ff431-174">这是可选角色。</span><span class="sxs-lookup"><span data-stu-id="ff431-174">This is an optional role.</span></span> <span data-ttu-id="ff431-175">它可以是单个服务器，也可以是运行 Director 角色的服务器池。</span><span class="sxs-lookup"><span data-stu-id="ff431-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="ff431-176">它是在内部 Skype for Business 服务器环境中找到的角色。</span><span class="sxs-lookup"><span data-stu-id="ff431-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="ff431-177">Director 是一个内部下一个跃点服务器，它从发送到 Skype for Business 服务器内部服务器的边缘服务器接收入站 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="ff431-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="ff431-178">它对入站请求预先进行身份验证，并将其它们重定向到用户的主池或主服务器。</span><span class="sxs-lookup"><span data-stu-id="ff431-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="ff431-179">此预身份验证可让您丢弃未确定身份的用户帐户的请求。</span><span class="sxs-lookup"><span data-stu-id="ff431-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="ff431-180">为什么这很重要？</span><span class="sxs-lookup"><span data-stu-id="ff431-180">Why does that matter?</span></span> <span data-ttu-id="ff431-181">Director 的一个重要功能是保护标准版服务器和前端服务器或前端池免受恶意流量的攻击，例如拒绝服务（DoS）攻击。</span><span class="sxs-lookup"><span data-stu-id="ff431-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="ff431-182">如果你的网络因外部流量无效而淹没，流量将在 Director 停止。</span><span class="sxs-lookup"><span data-stu-id="ff431-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="ff431-183">负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ff431-183">Load Balancers</span></span>
<span data-ttu-id="ff431-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="ff431-184"><a name="LoadBalancers"> </a></span></span>

<span data-ttu-id="ff431-185">Skype for Business 服务器缩放的合并边缘拓扑针对新部署的 DNS 负载平衡进行了优化，我们建议这样做。</span><span class="sxs-lookup"><span data-stu-id="ff431-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="ff431-186">如果需要高可用性，建议使用硬件负载平衡器来实现一个特定情形：</span><span class="sxs-lookup"><span data-stu-id="ff431-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="ff431-187">Exchange 2013**之前**使用 exchange um 的远程用户的 exchange um。</span><span class="sxs-lookup"><span data-stu-id="ff431-187">Exchange UM for remote users using Exchange UM **prior** to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="ff431-188">必须指出，不能混合使用负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="ff431-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="ff431-189">在您的 Skype for Business 服务器环境中，所有接口都必须使用 DNS 或 HLB。</span><span class="sxs-lookup"><span data-stu-id="ff431-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ff431-190">Skype for business Server 不支持直接服务器返回（DSR） NAT。</span><span class="sxs-lookup"><span data-stu-id="ff431-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="ff431-191">运行 A/V 边缘服务的边缘服务器边缘服务器的硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="ff431-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="ff431-192">对于运行 A/V 边缘服务的任何边缘服务器，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="ff431-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="ff431-193">对内部和外部端口 443 关闭 TCP nagling（Nagling 是将多个小数据包合并成一个大数据包以提高传输效率的过程）。</span><span class="sxs-lookup"><span data-stu-id="ff431-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="ff431-194">对端口范围为 50000 – 59999 的外部端口关闭 TCP nagling。</span><span class="sxs-lookup"><span data-stu-id="ff431-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="ff431-195">不要在内部或外部防火墙上使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="ff431-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="ff431-196">Edge 内部接口必须与 Edge 服务器外部接口位于不同的网络上，并且必须禁用它们之间的路由。</span><span class="sxs-lookup"><span data-stu-id="ff431-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="ff431-197">运行 A/V 边缘服务的任何边缘服务器的外部接口必须使用可公开路由的 IP 地址，并且任何边缘外部 IP 地址上都没有 NAT 或端口转换。</span><span class="sxs-lookup"><span data-stu-id="ff431-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="ff431-198">HLB 要求</span><span class="sxs-lookup"><span data-stu-id="ff431-198">HLB requirements</span></span>

<span data-ttu-id="ff431-199">Skype for Business 服务器没有许多基于 cookie 的相关性要求。</span><span class="sxs-lookup"><span data-stu-id="ff431-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="ff431-200">因此，你无需使用基于 cookie 的持久性，**除非**（这是 skype For business server 2015-特定的 skype for business server），你将在 skype For business server 环境中拥有 Lync Server 2010 前端服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="ff431-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="ff431-201">它们在 Lync Server 2010 推荐的配置方法中需要基于 cookie 的相关性。</span><span class="sxs-lookup"><span data-stu-id="ff431-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff431-202">如果决定为 HLB 开启基于 Cookie 的相关性，那么即使环境不需要，这样做也没有问题。</span><span class="sxs-lookup"><span data-stu-id="ff431-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="ff431-203">如果环境**不**需要基于 Cookie 的相关性：</span><span class="sxs-lookup"><span data-stu-id="ff431-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="ff431-204">在端口443的反向代理发布规则上，将 "**转发主机标题**" 设置为 " **True**"。</span><span class="sxs-lookup"><span data-stu-id="ff431-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="ff431-205">这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="ff431-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="ff431-206">对于**确实**需要基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="ff431-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="ff431-207">在端口443的反向代理发布规则上，将 "**转发主机标题**" 设置为 " **True**"。</span><span class="sxs-lookup"><span data-stu-id="ff431-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="ff431-208">这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="ff431-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="ff431-209">硬件负载平衡器 cookie**不得**标记为 "httpOnly"。</span><span class="sxs-lookup"><span data-stu-id="ff431-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="ff431-210">硬件负载平衡器 cookie**不得**有过期时间。</span><span class="sxs-lookup"><span data-stu-id="ff431-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="ff431-211">硬件负载平衡器 cookie**必须**命名为**MS-WSMAN** （这是 Web 服务预期的值，并且不能更改）。</span><span class="sxs-lookup"><span data-stu-id="ff431-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="ff431-212">硬件负载平衡器 cookie**必须**在每个 http 响应中设置，其中传入的 HTTP 请求没有 cookie，无论同一 TCP 连接上的以前 HTTP 响应是否已获得 cookie。</span><span class="sxs-lookup"><span data-stu-id="ff431-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="ff431-213">如果硬件负载平衡器针对每个 TCP 连接优化 cookie 插入，则**不**能使用该优化。</span><span class="sxs-lookup"><span data-stu-id="ff431-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ff431-214">对于 Skype for business 服务器及其客户端来说，HLB 配置使用源相关性和20分钟 TCP 会话生存期很常见，因为会话状态是通过客户端使用和/或应用程序交互维护的。</span><span class="sxs-lookup"><span data-stu-id="ff431-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="ff431-215">如果部署移动设备，则您的 HLB 必须能对 TCP 会话中的各个请求进行负载平衡（实际上，您需要能基于目标 IP 地址对单个请求进行负载平衡）。</span><span class="sxs-lookup"><span data-stu-id="ff431-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ff431-p121">F5 HLB 有一个名为 OneConnect 的功能。该功能确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的 HLB 供应商支持这同一功能。最新的 iOS 移动应用程序需要 TLS 1.2 版。如果需要了解更多，F5 提供了专门针对这一要求的设置。</span><span class="sxs-lookup"><span data-stu-id="ff431-p121">F5 HLBs have a feature called OneConnect. It ensures that each request within a TCP connection is individually load balanced. If you're deploying mobile devices, ensure your HLB vendor supports the same functionality. The latest iOS mobile apps require TLS version 1.2. If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="ff431-221">以下是（可选）董事和（必需）前端池 Web 服务的 HLB 要求：</span><span class="sxs-lookup"><span data-stu-id="ff431-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="ff431-222">对于内部 Web 服务 Vip，请在 HLB 上设置 Source_addr 持久性（内部端口80、443）。</span><span class="sxs-lookup"><span data-stu-id="ff431-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="ff431-223">对于 Skype for Business 服务器，Source_addr 持久性意味着来自单个 IP 地址的多个连接始终发送到一台服务器，以维护会话状态。</span><span class="sxs-lookup"><span data-stu-id="ff431-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="ff431-224">使用 TCP 空闲超时 1800 秒。</span><span class="sxs-lookup"><span data-stu-id="ff431-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="ff431-225">在反向代理和下一个跃点池的 HLB 之间的防火墙上，创建规则以允许 https：从反向代理到你的 HLB 的端口4443上的流量。</span><span class="sxs-lookup"><span data-stu-id="ff431-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="ff431-226">需要将 HLB 配置为侦听端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="ff431-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="ff431-227">HLB 相关性要求摘要</span><span class="sxs-lookup"><span data-stu-id="ff431-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="ff431-228">**客户端/用户位置**</span><span class="sxs-lookup"><span data-stu-id="ff431-228">**Client/user location**</span></span>|<span data-ttu-id="ff431-229">**外部 Web 服务 FQDN 关联要求**</span><span class="sxs-lookup"><span data-stu-id="ff431-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="ff431-230">**内部 Web 服务 FQDN 相关性要求**</span><span class="sxs-lookup"><span data-stu-id="ff431-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ff431-231">Skype for business Web 应用（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="ff431-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="ff431-232">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="ff431-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="ff431-233">无相关性</span><span class="sxs-lookup"><span data-stu-id="ff431-233">No affinity</span></span>  <br/> |<span data-ttu-id="ff431-234">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="ff431-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="ff431-235">Skype for business Web 应用（仅限外部用户）</span><span class="sxs-lookup"><span data-stu-id="ff431-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="ff431-236">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="ff431-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="ff431-237">无相关性</span><span class="sxs-lookup"><span data-stu-id="ff431-237">No affinity</span></span>  <br/> |<span data-ttu-id="ff431-238">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="ff431-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="ff431-239">Skype for business Web 应用（仅限内部用户）</span><span class="sxs-lookup"><span data-stu-id="ff431-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="ff431-240">移动设备（未部署）</span><span class="sxs-lookup"><span data-stu-id="ff431-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="ff431-241">无相关性</span><span class="sxs-lookup"><span data-stu-id="ff431-241">No affinity</span></span>  <br/> |<span data-ttu-id="ff431-242">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="ff431-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="ff431-243">HLB 的端口监视</span><span class="sxs-lookup"><span data-stu-id="ff431-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="ff431-244">在硬件负载平衡器上定义端口监视，以确定因硬件或通信故障而无法使用特定服务的时间。</span><span class="sxs-lookup"><span data-stu-id="ff431-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="ff431-245">例如，如果前端服务器服务（RTCSRV）因前端服务器或前端池出现故障而停止，则 HLB 监视还应停止接收 Web 服务的流量。</span><span class="sxs-lookup"><span data-stu-id="ff431-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="ff431-246">应在 HLB 上实施端口监视来监视 HLB 外部接口的以下信息：</span><span class="sxs-lookup"><span data-stu-id="ff431-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="ff431-247">**虚拟 IP/端口**</span><span class="sxs-lookup"><span data-stu-id="ff431-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="ff431-248">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="ff431-248">**Node Port**</span></span>|<span data-ttu-id="ff431-249">**节点计算机/监视器**</span><span class="sxs-lookup"><span data-stu-id="ff431-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="ff431-250">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="ff431-250">**Persistence Profile**</span></span>|<span data-ttu-id="ff431-251">**注释**</span><span class="sxs-lookup"><span data-stu-id="ff431-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ff431-252">\<池\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="ff431-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="ff431-253">443</span><span class="sxs-lookup"><span data-stu-id="ff431-253">443</span></span>  <br/> |<span data-ttu-id="ff431-254">4443</span><span class="sxs-lookup"><span data-stu-id="ff431-254">4443</span></span>  <br/> |<span data-ttu-id="ff431-255">前端</span><span class="sxs-lookup"><span data-stu-id="ff431-255">Front End</span></span>  <br/> <span data-ttu-id="ff431-256">5061</span><span class="sxs-lookup"><span data-stu-id="ff431-256">5061</span></span>  <br/> |<span data-ttu-id="ff431-257">无</span><span class="sxs-lookup"><span data-stu-id="ff431-257">None</span></span>  <br/> |<span data-ttu-id="ff431-258">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff431-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="ff431-259">\<池\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="ff431-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="ff431-260">80</span><span class="sxs-lookup"><span data-stu-id="ff431-260">80</span></span>  <br/> |<span data-ttu-id="ff431-261">8080</span><span class="sxs-lookup"><span data-stu-id="ff431-261">8080</span></span>  <br/> |<span data-ttu-id="ff431-262">前端</span><span class="sxs-lookup"><span data-stu-id="ff431-262">Front End</span></span>  <br/> <span data-ttu-id="ff431-263">5061</span><span class="sxs-lookup"><span data-stu-id="ff431-263">5061</span></span>  <br/> |<span data-ttu-id="ff431-264">无</span><span class="sxs-lookup"><span data-stu-id="ff431-264">None</span></span>  <br/> |<span data-ttu-id="ff431-265">HTTP</span><span class="sxs-lookup"><span data-stu-id="ff431-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="ff431-266">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="ff431-266">Hardware and software requirements</span></span>

<span data-ttu-id="ff431-267">我们在 skype for business [server 2015 的整体服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[Skype for business server 2019 文档的系统要求](../../../SfBServer2019/plan/system-requirements.md)中介绍了 Edge 服务器硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="ff431-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="ff431-268">并置</span><span class="sxs-lookup"><span data-stu-id="ff431-268">Collocation</span></span>

<span data-ttu-id="ff431-269">我们已在我们[的 Skype for Business server 文档的拓扑基础知识基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)中介绍了 Edge 服务器 collocation。</span><span class="sxs-lookup"><span data-stu-id="ff431-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

