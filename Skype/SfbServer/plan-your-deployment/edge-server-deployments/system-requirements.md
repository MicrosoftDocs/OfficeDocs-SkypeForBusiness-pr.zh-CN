---
title: Skype for Business Server 2015 的边缘服务器系统要求
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 摘要： 了解在 Skype 的边缘服务器业务服务器的系统要求。
ms.openlocfilehash: d4d195d07b13ccfc294054a811cbd6735b2431cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-system-requirements-in-skype-for-business-server-2015"></a><span data-ttu-id="b8cf7-103">Skype for Business Server 2015 的边缘服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="b8cf7-103">Edge Server system requirements in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b8cf7-104">**摘要：**了解如何在 Skype 的边缘服务器业务服务器的系统要求。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="b8cf7-105">到您 Skype 业务服务器边缘服务器部署时，这些是您需要为服务器或服务器本身，以及规划环境结构在环境中所做的事情。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="b8cf7-106">有关拓扑、DNS 证书和其他基础结构问题的详细信息，请查看环境要求文档。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="b8cf7-107">组件</span><span class="sxs-lookup"><span data-stu-id="b8cf7-107">Components</span></span>

<span data-ttu-id="b8cf7-108">在讨论边缘服务器环境时，我们引用，大多数情况下，部署在外围网络 （即是说它是在工作组或域之外您 Skype 业务服务器域结构） 的组件。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="b8cf7-109">请记住，这些组件是为了成功部署边缘而需要牢记于胸的组件：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="b8cf7-110">Edge Servers</span><span class="sxs-lookup"><span data-stu-id="b8cf7-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="b8cf7-111">Reverse proxies</span><span class="sxs-lookup"><span data-stu-id="b8cf7-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="b8cf7-112">Firewalls</span><span class="sxs-lookup"><span data-stu-id="b8cf7-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="b8cf7-113">[Directors](system-requirements.md#Directors)（这类组件是可选的，如果纳入这些组件，它们将位于内部网络中）</span><span class="sxs-lookup"><span data-stu-id="b8cf7-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="b8cf7-114">[负载平衡器](system-requirements.md#LoadBalancers)（可以有 DNS 负载平衡或硬件负载平衡器 (HLB)，但单个边缘服务器，这不需要）</span><span class="sxs-lookup"><span data-stu-id="b8cf7-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="b8cf7-115">下面我们更详细地谈论以下每个组件：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="b8cf7-116">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b8cf7-116">Edge Servers</span></span>
<span data-ttu-id="b8cf7-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="b8cf7-117"></span></span>

<span data-ttu-id="b8cf7-118">这些都是业务服务器部署在外围环境的 Skype。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="b8cf7-119">其作用是发送和接收业务服务器部署您内部 Skype 所提供的服务的外部用户的网络流量。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="b8cf7-120">若要成功执行此操作，每个边缘服务器运行：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="b8cf7-121">**访问边缘服务**： 为出站和入站会话启动协议 (SIP) 通信提供单一的受信任连接点。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="b8cf7-122">**Web 会议边缘服务**： 使外部用户可以加入您的企业服务器环境的内部 Skype 上承载的会议。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="b8cf7-123">**A / V 边缘服务**： 将音频、 视频、 应用程序共享和文件传输提供给外部用户。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="b8cf7-124">**XMPP 代理服务**： 接受，并与配置的 XMPP 联合伙伴发送消息和状态的可扩展协议 (XMPP) 消息。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="b8cf7-125">授权的外部用户可以使用边缘服务器连接到您内部 Skype 业务服务器部署中，但它们否则，为所有人提供其他访问您的内部网络。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8cf7-126">部署边缘服务器提供的业务客户端连接已启用 Skype 和其他边缘服务器 （在联合方案）。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="b8cf7-127">不能从其他端点客户端或服务器节点进行连接。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="b8cf7-128">XMPP 网关服务器可允许与配置的 XMPP 伙伴进行连接。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="b8cf7-129">但同样，这些伙伴仅限可行的客户端和联盟类型。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-129">But again, those are the only client and federation types that will work.</span></span> 
  
### <a name="reverse-proxies"></a><span data-ttu-id="b8cf7-130">反向代理</span><span class="sxs-lookup"><span data-stu-id="b8cf7-130">Reverse proxies</span></span>
<span data-ttu-id="b8cf7-131"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="b8cf7-131"></span></span>

<span data-ttu-id="b8cf7-132">(RP) 的反向代理服务器已没有 Skype 业务服务器角色，但边缘服务器部署的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-132">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="b8cf7-133">反向代理服务器允许外部用户：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-133">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="b8cf7-134">使用简单 URL 连接到会议或电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-134">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="b8cf7-135">下载会议内容。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-135">download meeting content.</span></span>
    
- <span data-ttu-id="b8cf7-136">展开通讯组。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-136">expand distribution groups.</span></span>
    
- <span data-ttu-id="b8cf7-137">获取基于用户的证书，用于基于客户端证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="b8cf7-137">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="b8cf7-138">从通讯簿服务器，或提交到地址簿 Web 查询服务的查询，请下载文件。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-138">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="b8cf7-139">获得客户和设备软件的更新。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-139">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="b8cf7-140">对于移动设备：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-140">And for mobile devices:</span></span>
  
- <span data-ttu-id="b8cf7-141">它可以让它们自动发现前端服务器提供移动服务。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-141">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="b8cf7-142">它使从 Office 365 到移动设备的推式通知。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-142">it enables push notifications from Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="b8cf7-143">[对于业务的 Skype 电话基础架构](https://technet.microsoft.com/en-us/office/dn947483)页上找不到我们当前反向代理的建议。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-143">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://technet.microsoft.com/en-us/office/dn947483) page.</span></span> <span data-ttu-id="b8cf7-144">因此您的反向代理服务器：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-144">So your reverse proxy:</span></span>
  
- <span data-ttu-id="b8cf7-145">应能够使用通过公共证书引入环境的传输层安全性 (TLS) 连接到以下对象的已发布外部 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-145">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="b8cf7-146">总监或总监池</span><span class="sxs-lookup"><span data-stu-id="b8cf7-146">Director or Director pool</span></span>
    
  - <span data-ttu-id="b8cf7-147">前端服务器或前端池</span><span class="sxs-lookup"><span data-stu-id="b8cf7-147">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="b8cf7-148">需要能使用加密证书发布内部网站，或者根据需要以未加密的方式发布这些网站。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-148">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="b8cf7-149">应能够使用完全限定域名 (FQDN) 在外部发布内部托管网站。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-149">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="b8cf7-150">需要能发布托管网站的所有内容。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-150">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="b8cf7-151">默认情况下，您可以使用**/**指令，大多数 web 服务器识别是指"发布的 web 服务器上的所有内容"。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-151">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="b8cf7-152">您还可以修改指令 — — 例如， **/Uwca/\***，这意味着"发布 Ucwa 的虚拟目录下的所有内容。"</span><span class="sxs-lookup"><span data-stu-id="b8cf7-152">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="b8cf7-153">必须与从发布的网站请求内容的客户端建立 TLS 连接。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-153">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="b8cf7-154">必须接受包含使用者替代名称 (SAN) 条目的证书。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-154">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="b8cf7-p107">需要能允许将证书绑定到将通过其解析外部 Web 服务 FQDN 的侦听器或接口。侦听器配置优于接口配置。可在一个接口上配置多个侦听器。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-p107">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve. Listener configurations are preferable to interfaces. Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="b8cf7-158">必须允许配置主机头处理。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-158">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="b8cf7-159">通常情况下，原始主机头发送请求的客户端必须以透明的方式，传递而不是修改的反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-159">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="b8cf7-160">应允许将来自某个外部定义的端口（如 TCP 443）的 TLS 流量桥接至另一个定义的端口（如 TCP 4443）。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-160">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="b8cf7-161">反向代理服务器可以解密数据包在收据上的，然后重新加密发送该数据包。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-161">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="b8cf7-162">应将来自某个端口（如 TCP 80）的未加密 TCP 流量桥接至另一端口（如 TCP 8080）。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-162">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="b8cf7-163">需要允许配置或接受“NTLM 身份验证”、“无身份验证”和“传递身份验证”。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-163">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="b8cf7-164">如果您的反向代理服务器可以解决此列表中的所有需求，应该很好，但请记住我们的建议在上面提供的链接。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-164">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="b8cf7-165">防火墙</span><span class="sxs-lookup"><span data-stu-id="b8cf7-165">Firewalls</span></span>
<span data-ttu-id="b8cf7-166"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="b8cf7-166"></span></span>

<span data-ttu-id="b8cf7-p110">需要将边缘部署放在外部防火墙后面，但是我们建议在边缘环境和内部环境之间设两个防火墙，一个外部，一个内部。我们方案的所有文档都有两个防火墙。我们之所以推荐两道防火墙是因为，这可确保从一个网络边缘到另一个网络边缘的严格路由，并对内部网络实施加倍防火墙保护。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-p110">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment. All our documentation in our Scenarios will have two firewalls. We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="b8cf7-170">控制器</span><span class="sxs-lookup"><span data-stu-id="b8cf7-170">Directors</span></span>
<span data-ttu-id="b8cf7-171"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="b8cf7-171"></span></span>

<span data-ttu-id="b8cf7-172">这是可选角色。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-172">This is an optional role.</span></span> <span data-ttu-id="b8cf7-173">它可以是一台服务器或池的运行主管角色的服务器。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-173">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="b8cf7-174">它是在内部 Skype 业务服务器环境中找到一个角色。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-174">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="b8cf7-175">控制器是内部下一个跃点服务器接收从边缘服务器发送到 Skype 业务服务器的内部服务器的入站的 SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-175">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="b8cf7-176">它对入站请求预先进行身份验证，并将其它们重定向到用户的主池或主服务器。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-176">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="b8cf7-177">此预身份验证可让您丢弃未确定身份的用户帐户的请求。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-177">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="b8cf7-178">为什么这很重要？</span><span class="sxs-lookup"><span data-stu-id="b8cf7-178">Why does that matter?</span></span> <span data-ttu-id="b8cf7-179">导演的重要功能是为了防止恶意通信量，如拒绝服务 (DoS) 攻击的标准版服务器和前端服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-179">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="b8cf7-180">如果您的网络被淹没无效的外部通信，通信停止处主任。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-180">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="b8cf7-181">负载平衡器</span><span class="sxs-lookup"><span data-stu-id="b8cf7-181">Load Balancers</span></span>
<span data-ttu-id="b8cf7-182"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="b8cf7-182"></span></span>

<span data-ttu-id="b8cf7-183">Skype 业务服务器 2015 缩放合并边缘拓扑优化 DNS 负载平衡的新部署，并建议这样做。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-183">The Skype for Business Server 2015 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="b8cf7-184">如果需要高可用性，我们建议使用一种特定情形的硬件负载平衡：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-184">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="b8cf7-185">交换 UM 的远程用户使用 Exchange UM**事先**交换 2013年。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-185">Exchange UM for remote users using Exchange UM **prior** to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b8cf7-186">必须指出，不能混合使用负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-186">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="b8cf7-187">在您 Skype 业务服务器环境中的所有接口必须都使用 DNS 或 HLB。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-187">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b8cf7-188">直接服务器返回 (DSR) NAT 不支持为 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-188">Direct server return (DSR) NAT isn't supported for Skype for Business Server 2015.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="b8cf7-189">硬件负载平衡器要求服务器边缘，边缘服务器运行 A / V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="b8cf7-189">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="b8cf7-190">任何边缘服务器运行 A / V 边缘服务，这些都是要求：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-190">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="b8cf7-191">对内部和外部端口 443 关闭 TCP nagling（Nagling 是将多个小数据包合并成一个大数据包以提高传输效率的过程）。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-191">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="b8cf7-192">对端口范围为 50000 – 59999 的外部端口关闭 TCP nagling。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-192">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="b8cf7-193">不要在内部或外部防火墙上使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-193">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="b8cf7-194">边缘内部接口必须比您边缘服务器的外部接口，不同的网络上，并且必须禁用它们之间路由。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-194">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="b8cf7-195">运行的任何边缘服务器的外部接口 / V 边缘服务必须使用公用路由的 IP 地址和没有 NAT 或端口上任何边缘外部 IP 地址的翻译。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-195">The external interface of any Edge Server running the A/V Edge service must use publically routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="b8cf7-196">HLB 要求</span><span class="sxs-lookup"><span data-stu-id="b8cf7-196">HLB requirements</span></span>

<span data-ttu-id="b8cf7-197">使用 Lync Server 2013，业务服务器 2015年的 Skype 不会有大量的基于 cookie 的相似性要求。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-197">As with Lync Server 2013, Skype for Business Server 2015 doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="b8cf7-198">因此，您不需要使用基于 cookie 持久性**除非**您将需要在您的企业服务器环境的 Skype 的 Lync Server 2010 前结束服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-198">So you don't need to use a cookie-based persistence **unless** you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="b8cf7-199">他们将需要基于 cookie 的配置方法建议使用 Lync Server 2010 中的相似性。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-199">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8cf7-200">如果决定为 HLB 开启基于 Cookie 的相关性，那么即使环境不需要，这样做也没有问题。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-200">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="b8cf7-201">如果环境**不**需要基于 Cookie 的相关性：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-201">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="b8cf7-202">在端口 443 的反向代理服务器发布规则，将设置为**True**的**前向主机标头**。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-202">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="b8cf7-203">这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-203">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="b8cf7-204">对于**确实**需要基于 Cookie 的相关性的部署：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-204">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="b8cf7-205">在端口 443 的反向代理服务器发布规则，将设置为**True**的**前向主机标头**。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-205">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="b8cf7-206">这可确保转发原始 URL。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-206">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="b8cf7-207">硬件负载平衡器 cookie**不**会标记为 httpOnly。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-207">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="b8cf7-208">硬件负载平衡器 cookie**不必须**有截止时间。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-208">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="b8cf7-209">硬件负载平衡器 cookie**必须**命名为**MS WSMAN** （这是所期望的 Web 服务，并且不能更改的值）。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-209">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="b8cf7-210">硬件负载平衡器 cookie**必须**在传入的 HTTP 请求没有 cookie，而不考虑以前的 HTTP 响应该相同的 TCP 连接上是否有引起了 cookie 的每个 HTTP 响应中设置。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-210">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="b8cf7-211">如果您的硬件负载平衡器优化 cookie 插入仅发生后该优化**必须不**使用每个 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-211">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b8cf7-212">它是典型的 HLB 配置为使用源相关性和 20 分钟 TCP 会话生存期，这是相当不错的 Skype 业务服务器 2015年和其客户端，因为通过客户端使用情况和/或应用程序交互，即可保持会话状态。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-212">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server 2015 and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="b8cf7-213">如果部署移动设备，则您的 HLB 必须能对 TCP 会话中的各个请求进行负载平衡（实际上，您需要能基于目标 IP 地址对单个请求进行负载平衡）。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-213">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b8cf7-p120">F5 HLB 有一个名为 OneConnect 的功能。该功能确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的 HLB 供应商支持这同一功能。最新的 iOS 移动应用程序需要 TLS 1.2 版。如果需要了解更多，F5 提供了专门针对这一要求的设置。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-p120">F5 HLBs have a feature called OneConnect. It ensures that each request within a TCP connection is individually load balanced. If you're deploying mobile devices, ensure your HLB vendor supports the same functionality. The latest iOS mobile apps require TLS version 1.2. If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="b8cf7-219">这里是 HLB 要求的控制器 （可选） 和 （必选） 前端池 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-219">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="b8cf7-220">为内部的 Web 服务 Vip，设置您 HLB Source_addr 持久性 （内部端口 80、 443）。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-220">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="b8cf7-221">对于业务服务器 2015年的 Skype，Source_addr 持久性意味着来自单个 IP 地址的多个连接始终发送到一台服务器，以维护会话状态。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-221">For Skype for Business Server 2015, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="b8cf7-222">使用 TCP 空闲超时 1800 秒。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-222">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="b8cf7-223">反向代理服务器和您下一个跃点池 HLB 之间的防火墙，在创建一个规则来允许 https： 端口 4443，从您 HLB 为您反向代理服务器上的流量。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-223">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="b8cf7-224">需要将 HLB 配置为侦听端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-224">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="b8cf7-225">HLB 相关性要求摘要</span><span class="sxs-lookup"><span data-stu-id="b8cf7-225">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="b8cf7-226">**Client/user location**</span><span class="sxs-lookup"><span data-stu-id="b8cf7-226">**Client/user location**</span></span>|<span data-ttu-id="b8cf7-227">**外部 web 服务 FQDN 关联需求**</span><span class="sxs-lookup"><span data-stu-id="b8cf7-227">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="b8cf7-228">**内部 web 服务 FQSN 仿射性需求**</span><span class="sxs-lookup"><span data-stu-id="b8cf7-228">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b8cf7-229">Skype 业务 Web 应用程序 （内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="b8cf7-229">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="b8cf7-230">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="b8cf7-230">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="b8cf7-231">无相关性</span><span class="sxs-lookup"><span data-stu-id="b8cf7-231">No affinity</span></span>  <br/> |<span data-ttu-id="b8cf7-232">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="b8cf7-232">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="b8cf7-233">Skype 业务 Web 应用程序 （仅适用于外部用户）</span><span class="sxs-lookup"><span data-stu-id="b8cf7-233">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="b8cf7-234">移动设备（内部和外部用户）</span><span class="sxs-lookup"><span data-stu-id="b8cf7-234">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="b8cf7-235">无相关性</span><span class="sxs-lookup"><span data-stu-id="b8cf7-235">No affinity</span></span>  <br/> |<span data-ttu-id="b8cf7-236">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="b8cf7-236">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="b8cf7-237">Skype 业务 Web 应用程序 （仅适用于内部用户）</span><span class="sxs-lookup"><span data-stu-id="b8cf7-237">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="b8cf7-238">移动设备（未部署）</span><span class="sxs-lookup"><span data-stu-id="b8cf7-238">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="b8cf7-239">无相关性</span><span class="sxs-lookup"><span data-stu-id="b8cf7-239">No affinity</span></span>  <br/> |<span data-ttu-id="b8cf7-240">源地址相关性</span><span class="sxs-lookup"><span data-stu-id="b8cf7-240">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="b8cf7-241">HLB 的端口监视</span><span class="sxs-lookup"><span data-stu-id="b8cf7-241">Port monitoring for HLBs</span></span>

<span data-ttu-id="b8cf7-242">您定义端口监视上硬件负载平衡器以确定特定服务何时不再可用，由于硬件或通信故障。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-242">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="b8cf7-243">例如，如果前端服务器服务 (RTCSRV) 停止因为前端服务器或前端池失败，HLB 监视也应该停止接收对 Web 服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-243">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="b8cf7-244">应在 HLB 上实施端口监视来监视 HLB 外部接口的以下信息：</span><span class="sxs-lookup"><span data-stu-id="b8cf7-244">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="b8cf7-245">**虚拟的 IP 端口**</span><span class="sxs-lookup"><span data-stu-id="b8cf7-245">**Virtual IP/Port**</span></span>|<span data-ttu-id="b8cf7-246">**节点端口**</span><span class="sxs-lookup"><span data-stu-id="b8cf7-246">**Node Port**</span></span>|<span data-ttu-id="b8cf7-247">**节点机/监视器**</span><span class="sxs-lookup"><span data-stu-id="b8cf7-247">**Node Machine/Monitor**</span></span>|<span data-ttu-id="b8cf7-248">**持久性配置文件**</span><span class="sxs-lookup"><span data-stu-id="b8cf7-248">**Persistence Profile**</span></span>|<span data-ttu-id="b8cf7-249">**说明**</span><span class="sxs-lookup"><span data-stu-id="b8cf7-249">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8cf7-250">\<池\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="b8cf7-250">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="b8cf7-251">443</span><span class="sxs-lookup"><span data-stu-id="b8cf7-251">443</span></span>  <br/> |<span data-ttu-id="b8cf7-252">4443</span><span class="sxs-lookup"><span data-stu-id="b8cf7-252">4443</span></span>  <br/> |<span data-ttu-id="b8cf7-253">前端</span><span class="sxs-lookup"><span data-stu-id="b8cf7-253">Front End</span></span>  <br/> <span data-ttu-id="b8cf7-254">5061</span><span class="sxs-lookup"><span data-stu-id="b8cf7-254">5061</span></span>  <br/> |<span data-ttu-id="b8cf7-255">无</span><span class="sxs-lookup"><span data-stu-id="b8cf7-255">None</span></span>  <br/> |<span data-ttu-id="b8cf7-256">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b8cf7-256">HTTPS</span></span>  <br/> |
|<span data-ttu-id="b8cf7-257">\<pool\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="b8cf7-257">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="b8cf7-258">80</span><span class="sxs-lookup"><span data-stu-id="b8cf7-258">80</span></span>  <br/> |<span data-ttu-id="b8cf7-259">8080</span><span class="sxs-lookup"><span data-stu-id="b8cf7-259">8080</span></span>  <br/> |<span data-ttu-id="b8cf7-260">前端</span><span class="sxs-lookup"><span data-stu-id="b8cf7-260">Front End</span></span>  <br/> <span data-ttu-id="b8cf7-261">5061</span><span class="sxs-lookup"><span data-stu-id="b8cf7-261">5061</span></span>  <br/> |<span data-ttu-id="b8cf7-262">无</span><span class="sxs-lookup"><span data-stu-id="b8cf7-262">None</span></span>  <br/> |<span data-ttu-id="b8cf7-263">HTTP</span><span class="sxs-lookup"><span data-stu-id="b8cf7-263">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="b8cf7-264">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="b8cf7-264">Hardware and software requirements</span></span>

<span data-ttu-id="b8cf7-265">我们已经在我们总[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)文档介绍边缘服务器硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-265">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="b8cf7-266">并置</span><span class="sxs-lookup"><span data-stu-id="b8cf7-266">Collocation</span></span>

<span data-ttu-id="b8cf7-267">我们已经在我们的[业务服务器 2015年的 Skype 的拓扑结构基础](../../plan-your-deployment/topology-basics/topology-basics.md)文档介绍边缘服务器配置。</span><span class="sxs-lookup"><span data-stu-id="b8cf7-267">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

