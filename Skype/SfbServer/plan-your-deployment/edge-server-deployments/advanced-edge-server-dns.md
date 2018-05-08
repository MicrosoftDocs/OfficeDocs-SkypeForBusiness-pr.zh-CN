---
title: 高级边缘服务器的 DNS 规划的 Skype 业务服务器 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 摘要： 查看的 Skype 方案业务服务器 2015年部署选项。 是否希望一台服务器或首选 DNS 或 HLB 的服务器池，应帮助本主题。
ms.openlocfilehash: 575bbacfa58f52197d50b335942909dc8748a965
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server-2015"></a><span data-ttu-id="db29e-104">高级边缘服务器的 DNS 规划的 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="db29e-104">Advanced Edge Server DNS planning for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="db29e-p102">**摘要：**回顾 Skype for Business Server 2015 部署选项的方案。无论你想要单服务器，还是偏好采用 DNS 或 HLB 的服务器池，本主题都应该有帮助。</span><span class="sxs-lookup"><span data-stu-id="db29e-p102">**Summary:** Review scenarios for Skype for Business Server 2015 deployment options. Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="db29e-107">当谈到的 Skype 域名系统 (DNS) 规划业务服务器 2015年时，有大量的可能播放到您的决定因素。</span><span class="sxs-lookup"><span data-stu-id="db29e-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server 2015, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="db29e-108">如果组织的域结构已经就位，那么这可能就是考虑如何继续的问题。</span><span class="sxs-lookup"><span data-stu-id="db29e-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="db29e-109">我们将从下面提供的主题开始：</span><span class="sxs-lookup"><span data-stu-id="db29e-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="db29e-110">Walkthrough of Skype for Business clients locating services</span><span class="sxs-lookup"><span data-stu-id="db29e-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="db29e-111">Split-brain DNS</span><span class="sxs-lookup"><span data-stu-id="db29e-111">Split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="db29e-112">Automatic configuration without split-brain DNS</span><span class="sxs-lookup"><span data-stu-id="db29e-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="db29e-113">DNS disaster recovery</span><span class="sxs-lookup"><span data-stu-id="db29e-113">DNS disaster recovery</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="db29e-114">DNS load balancing</span><span class="sxs-lookup"><span data-stu-id="db29e-114">DNS load balancing</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="db29e-115">Walkthrough of Skype for Business clients locating services</span><span class="sxs-lookup"><span data-stu-id="db29e-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="db29e-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="db29e-116"></span></span>

<span data-ttu-id="db29e-117">Skype 业务客户端在类似于早期版本的 Lync 客户端如何查找和访问业务服务器 2015 Skype 中的服务。</span><span class="sxs-lookup"><span data-stu-id="db29e-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server 2015.</span></span> <span data-ttu-id="db29e-118">本节详述服务查找过程。</span><span class="sxs-lookup"><span data-stu-id="db29e-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="db29e-119">lyncdiscoverinternal。\<域\></span><span class="sxs-lookup"><span data-stu-id="db29e-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="db29e-120">*这是内部 Web 服务上自动发现服务的 A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="db29e-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="db29e-121">lyncdiscover。\<域\></span><span class="sxs-lookup"><span data-stu-id="db29e-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="db29e-122">*这是外部 Web 服务上自动发现服务的 A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="db29e-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="db29e-123">_sipinternaltls._tcp。\<域\></span><span class="sxs-lookup"><span data-stu-id="db29e-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="db29e-124">*这是内部 TLS 连接的 SRV 记录。*</span><span class="sxs-lookup"><span data-stu-id="db29e-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="db29e-125">_sip._tls。\<域\></span><span class="sxs-lookup"><span data-stu-id="db29e-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="db29e-126">*这是外部 TLS 连接的 SRV 记录。*</span><span class="sxs-lookup"><span data-stu-id="db29e-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="db29e-127">sipinternal。\<域\></span><span class="sxs-lookup"><span data-stu-id="db29e-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="db29e-128">*这是前端池或控制器，仅在内部网络上进行解析 A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="db29e-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="db29e-129">sip。\<域\></span><span class="sxs-lookup"><span data-stu-id="db29e-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="db29e-130">*这是前端池或控制器，仅在内部网络上进行解析 A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="db29e-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="db29e-131">sipexternal。\<域\></span><span class="sxs-lookup"><span data-stu-id="db29e-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="db29e-132">*外部客户端时，这是访问边缘服务中，A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="db29e-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="db29e-133">自动发现服务总是受人欢迎，因为这是服务定位的首选方法，其他方法为回退方法。</span><span class="sxs-lookup"><span data-stu-id="db29e-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db29e-p105">创建 SRV 记录时，请务必记住，这些记录需要指向要在其中创建 DNS SRV 记录的同一域中的 DNS A（如果使用 IPv6 寻址，则还有 AAAA）。例如，如果 SRV 记录位于 contoso.com，则其所指向的 A（和 AAAA）记录不能在 fabrikam.com 中。</span><span class="sxs-lookup"><span data-stu-id="db29e-p105">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created. For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="db29e-p106">如果倾向于这样做，可以设置移动设备进行手动服务发现。如果这正是你想做的，那么每个用户需要为其移动设备的设置配置内部和外部自动发现服务的完整 URI，包括协议和路径，具体如下：</span><span class="sxs-lookup"><span data-stu-id="db29e-p106">If you're inclined to do it, you can set your mobile device up for manual discovery of services. If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="db29e-138">用于外部访问： https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="db29e-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="db29e-139">用于内部访问： https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="db29e-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="db29e-p107">我们建议使用自动发现，而不是手动发现。但是如果你要执行某种故障排除或测试，那么手动设置可能很有帮助。</span><span class="sxs-lookup"><span data-stu-id="db29e-p107">We do recommend you use automatic discovery as opposed to manual discovery. But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="db29e-142">拆分式 DNS</span><span class="sxs-lookup"><span data-stu-id="db29e-142">Split-brain DNS</span></span>
<span data-ttu-id="db29e-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="db29e-143"></span></span>

<span data-ttu-id="db29e-p108">这是一种两个 DNS 区域有相同命名空间的 DNS 配置。第一个 DNS 区域处理内部请求，而第二个 DNS 区域处理外部请求。</span><span class="sxs-lookup"><span data-stu-id="db29e-p108">This is a DNS configuration where you have two DNS zones with the same namespace. The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="db29e-p109">为什么公司会这样做？他们可能需要内外使用相同的命名空间，但是当然，这会导致很多 DNS SRV 和 A 记录在这个区域或那个区域是唯一的，在有重复的情况下，与这些记录关联的 IP 地址将是唯一的。</span><span class="sxs-lookup"><span data-stu-id="db29e-p109">Why would a company do this? They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="db29e-148">这带来了一些难题。</span><span class="sxs-lookup"><span data-stu-id="db29e-148">This presents some challenges.</span></span> <span data-ttu-id="db29e-149">最重要的是拆分式 DNS 是**不支持**移动。</span><span class="sxs-lookup"><span data-stu-id="db29e-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="db29e-150">这是因为 LyncDiscover 和 LyncDiscoverInternal DNS 记录（LyncDiscover 必须定义在外部 DNS 服务器上，而 LyncDiscoverInternal 必须定义在内部 DNS 服务器上）。</span><span class="sxs-lookup"><span data-stu-id="db29e-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="db29e-151">我们将列表的内部和外部区域此处的 DNS 记录，但您可以找到详细的示例的边缘服务器环境的要求一节。</span><span class="sxs-lookup"><span data-stu-id="db29e-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="db29e-152">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="db29e-152">Internal DNS</span></span>

- <span data-ttu-id="db29e-153">包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。</span><span class="sxs-lookup"><span data-stu-id="db29e-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="db29e-154">这个内部 contoso.com 包含：</span><span class="sxs-lookup"><span data-stu-id="db29e-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="db29e-155">DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 记录前端池、 控制器池或控制器池名称和组织的网络中运行业务服务器 2015 Skype 的所有内部服务器。</span><span class="sxs-lookup"><span data-stu-id="db29e-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server 2015 in your organization's network.</span></span>
    
  - <span data-ttu-id="db29e-156">DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 记录您的边缘内部接口的每个 Skype 业务服务器 2015年边缘服务器的外围网络中。</span><span class="sxs-lookup"><span data-stu-id="db29e-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server 2015 Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="db29e-157">（这是**可选**的反向代理的管理） 外围网络中每台反向代理服务器的内部接口的 DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 记录。</span><span class="sxs-lookup"><span data-stu-id="db29e-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="db29e-158">DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 和 SRV 记录内部 Skype 业务服务器 2015年客户端自动配置 （它是**可选**的）。</span><span class="sxs-lookup"><span data-stu-id="db29e-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server 2015 client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="db29e-159">DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 或 CNAME 记录的自动发现的 Skype Business Server 2015 Web services （这是**可选**的）。</span><span class="sxs-lookup"><span data-stu-id="db29e-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server 2015 Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="db29e-160">您的业务服务器 2015年外围网络中的内部边缘接口的所有 Skype 可都用于解决对 contoso.com 的查询此内部 DNS 区域。</span><span class="sxs-lookup"><span data-stu-id="db29e-160">All your Skype for Business Server 2015 internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="db29e-161">业务服务器 2015年和企业网络中运行业务服务器 2015 Skype 的客户端运行 Skype 的所有服务器都指向内部 DNS 服务器，以解决对 contoso.com 的查询或他们 （如果使用的每台边缘服务器和列表 A 和 AAAA 上的主机文件您正在使用 IPv6 寻址） 记录 （特别是对于控制器或控制器池 VIP、 Front End 池 VIP 或 Standard Edition server） 的下一个跃点服务器。</span><span class="sxs-lookup"><span data-stu-id="db29e-161">All servers running Skype for Business Server 2015, and clients running Skype for Business Server 2015 in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="db29e-162">外部 DNS</span><span class="sxs-lookup"><span data-stu-id="db29e-162">External DNS</span></span>

- <span data-ttu-id="db29e-163">包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。</span><span class="sxs-lookup"><span data-stu-id="db29e-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="db29e-164">此外部 contoso.com 包含：</span><span class="sxs-lookup"><span data-stu-id="db29e-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="db29e-165">DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 或 CNAME 记录的自动发现的 Skype 业务服务器 2015 web 服务。</span><span class="sxs-lookup"><span data-stu-id="db29e-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server 2015 web services.</span></span> <span data-ttu-id="db29e-166">这是用于移动。</span><span class="sxs-lookup"><span data-stu-id="db29e-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="db29e-167">DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 和 SRV 记录的边缘外部接口的每个 Skype 业务 Server 2015 边缘服务器或硬件负载平衡 (HLB) VIP 外围网络中。</span><span class="sxs-lookup"><span data-stu-id="db29e-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server 2015 Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="db29e-168">DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 和 SRV 记录的外部接口 (VIP 的反向代理服务器池)，反向代理服务器的外围网络中。</span><span class="sxs-lookup"><span data-stu-id="db29e-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="db29e-169">DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 和 SRV 记录的 Skype 业务服务器 2015年客户端自动配置 （**可选**）。</span><span class="sxs-lookup"><span data-stu-id="db29e-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server 2015 client autoconfiguration ( **optional** ).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="db29e-170">没有拆分式 DNS 时的自动配置</span><span class="sxs-lookup"><span data-stu-id="db29e-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="db29e-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="db29e-171"></span></span>

<span data-ttu-id="db29e-172">如果不使用拆分式 DNS，内部自动配置运行 for Business 的 Skype 的客户端不会起作用，除非您使用我们在这里有解决方法之一。</span><span class="sxs-lookup"><span data-stu-id="db29e-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="db29e-173">为什么不进行合计？</span><span class="sxs-lookup"><span data-stu-id="db29e-173">Why not?</span></span> <span data-ttu-id="db29e-174">因为业务服务器 2015年的 Skype 需要用户的 SIP URI 匹配指定用于自动配置的前端池的域。</span><span class="sxs-lookup"><span data-stu-id="db29e-174">Because Skype for Business Server 2015 requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="db29e-175">此尚未更改从早期版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="db29e-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="db29e-176">所以，如果正在使用两个 SIP 域，那么需要以下 DNS SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="db29e-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="db29e-177">_sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-177">_sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="db29e-178">*如果一个用户登录为 bob@contoso.com，此记录将适合自动配置，如前端池 (contoso.com) 的域用户的 SIP 域匹配。*</span><span class="sxs-lookup"><span data-stu-id="db29e-178">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="db29e-179">_sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="db29e-179">_sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="db29e-180">*如果用户为 alice@fabrikam.com 登录，此记录将自动配置的第二个域，再次中工作，这因为的 SIP 域匹配该域的前端池。*</span><span class="sxs-lookup"><span data-stu-id="db29e-180">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="db29e-181">再举此例，下面的记录不起作用：</span><span class="sxs-lookup"><span data-stu-id="db29e-181">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="db29e-182">_sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="db29e-182">_sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="db29e-183">*作为 tim@litwareinc.com 登录的用户对自动配置不起作用，因为该用户的 SIP 域 (litwareinc.com) 与池中的域 (fabrikam.com) 不匹配。*</span><span class="sxs-lookup"><span data-stu-id="db29e-183">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="db29e-184">因此，既然我们知道所有，如果您需要为您 Skype 业务没有拆分式 DNS 的客户端的自动要求，必须这些选项：</span><span class="sxs-lookup"><span data-stu-id="db29e-184">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="db29e-185">**组策略对象**</span><span class="sxs-lookup"><span data-stu-id="db29e-185">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="db29e-186">可使用组策略对象 (GPO) 填充正确的服务器值。</span><span class="sxs-lookup"><span data-stu-id="db29e-186">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="db29e-p113">此选项不会启用自动配置，但可以自动化手动配置。如果使用此方法，则不需要与自动配置关联的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="db29e-p113">This option doesn't enable automatic configuration, but it does automate manual configuration. If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="db29e-189">**匹配内部区域**</span><span class="sxs-lookup"><span data-stu-id="db29e-189">**Matching internal zone**</span></span>
    
    <span data-ttu-id="db29e-190">您需要创建匹配外部 DNS 区域 (例如，contoso.com)，在内部 dns 区域，然后创建 DNS A （和 AAAA 如果您使用的 IPv6 寻址） 记录对应于业务服务器 2015年池用于自动 Skype配置。</span><span class="sxs-lookup"><span data-stu-id="db29e-190">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server 2015 pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="db29e-191">例如，如果您有用户驻留在 pool01.contoso.net，但迹象到 Skype 的业务作为 bob@contoso.com，创建名为 contoso.com，内部 DNS 区域，您需要在其中创建 DNS A （和 AAAA 如果正在使用 IPv6 寻址） 记录pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="db29e-191">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="db29e-192">**精确内部区域**</span><span class="sxs-lookup"><span data-stu-id="db29e-192">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="db29e-p114">如果在内部 DNS 中创建整个区域不适合你，你可以创建与自动配置所需要的 SRV 记录对应的精确（专用）区域，并使用 dnscmd.exe 填充这些区域。由于 DNS 用户界面不支持创建精确内部区域，因此需要 Dnscmd.exe。</span><span class="sxs-lookup"><span data-stu-id="db29e-p114">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe. Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="db29e-195">例如，如果您的 SIP 域是 contoso.com，并且必须调用包含两个前端服务器的 pool01 前端池，将需要在您的内部 DNS 中的以下精确区域和 A 记录：</span><span class="sxs-lookup"><span data-stu-id="db29e-195">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="db29e-p115">环境中可能还有第二个 SIP 域。这种情况下，内部 DNS 中需要以下精确区域和 A 记录：</span><span class="sxs-lookup"><span data-stu-id="db29e-p115">You may have a second SIP domain in your environment. In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> <span data-ttu-id="db29e-198">您将看到前端池 FQDN 出现两次，但有两个不同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="db29e-198">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="db29e-199">这是因为使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="db29e-199">That's because DNS load balancing is used.</span></span> <span data-ttu-id="db29e-200">如果使用 HLB 时，才会一个前端池项。</span><span class="sxs-lookup"><span data-stu-id="db29e-200">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="db29e-201">此外，前端池 FQDN 值之间 contoso.com 和 fabrikam.com 示例中，更改但的 IP 地址保持不变。</span><span class="sxs-lookup"><span data-stu-id="db29e-201">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="db29e-202">这是因为正在登录从任一 SIP 域的用户将自动配置为使用相同的前端池。</span><span class="sxs-lookup"><span data-stu-id="db29e-202">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="db29e-203">DNS 灾难恢复</span><span class="sxs-lookup"><span data-stu-id="db29e-203">DNS disaster recovery</span></span>
<span data-ttu-id="db29e-204"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="db29e-204"></span></span>

<span data-ttu-id="db29e-205">若要配置 DNS 以将 Skype 重定向到您的灾难恢复 （灾难恢复） 和故障转移网站的业务服务器 2015 web 通信，您需要使用支持 GeoDNS DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="db29e-205">To configure DNS to redirect Skype for Business Server 2015 web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="db29e-206">您可以设置 DNS 记录以支持灾难恢复，以便使用 web 服务的功能继续即使一个整个前端池不可用。</span><span class="sxs-lookup"><span data-stu-id="db29e-206">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="db29e-207">此 DR 功能支持自动发现、会议和拨入式简单 URL。</span><span class="sxs-lookup"><span data-stu-id="db29e-207">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="db29e-p119">你可以在 GeoDNS 提供商处定义和配置用于 Web 服务的内部和外部解析额外的 DNS 主机 A（如果使用 IPv6，则为 AAAA）记录。以下详细信息假定池已配对，地理位置分散，且提供商支持的 GeoDNS **要么**使用循环 DNS，**要么**配置为使用 Pool1 作为主池，并且在发生通信丢失或电源故障时故障转移到 Pool2。</span><span class="sxs-lookup"><span data-stu-id="db29e-p119">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider. The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="db29e-210">下表中的所有 DNS 记录均为示例。</span><span class="sxs-lookup"><span data-stu-id="db29e-210">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="db29e-211">**GeoDNS 记录**</span><span class="sxs-lookup"><span data-stu-id="db29e-211">**GeoDNS record**</span></span>|<span data-ttu-id="db29e-212">**池记录**</span><span class="sxs-lookup"><span data-stu-id="db29e-212">**Pool records**</span></span>|<span data-ttu-id="db29e-213">**CNAME 记录**</span><span class="sxs-lookup"><span data-stu-id="db29e-213">**CNAME records**</span></span>|<span data-ttu-id="db29e-214">**DNS 设置 （选择一个选项）**</span><span class="sxs-lookup"><span data-stu-id="db29e-214">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="db29e-215">开会 int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-215">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-216">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-216">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-217">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-217">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-218">Pool1InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-218">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-219">Pool2InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-219">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-220">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="db29e-220">Round Robin between pools</span></span>  <br/> <span data-ttu-id="db29e-221">**或者**</span><span class="sxs-lookup"><span data-stu-id="db29e-221">**OR**</span></span> <br/> <span data-ttu-id="db29e-222">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="db29e-222">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="db29e-223">开会 ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-223">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-224">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-224">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-225">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-225">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-226">Pool1ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-226">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-227">Pool2ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-227">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-228">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="db29e-228">Round Robin between pools</span></span>  <br/> <span data-ttu-id="db29e-229">**或者**</span><span class="sxs-lookup"><span data-stu-id="db29e-229">**OR**</span></span> <br/> <span data-ttu-id="db29e-230">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="db29e-230">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="db29e-231">Dialin int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-231">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-232">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-232">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-233">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-233">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-234">Pool1InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-234">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-235">Pool2InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-235">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-236">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="db29e-236">Round Robin between pools</span></span>  <br/> <span data-ttu-id="db29e-237">**或者**</span><span class="sxs-lookup"><span data-stu-id="db29e-237">**OR**</span></span> <br/> <span data-ttu-id="db29e-238">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="db29e-238">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="db29e-239">Dialin ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-239">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-240">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-240">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-241">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-241">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-242">Pool1ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-242">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-243">Pool2ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-243">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-244">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="db29e-244">Round Robin between pools</span></span>  <br/> <span data-ttu-id="db29e-245">**或者**</span><span class="sxs-lookup"><span data-stu-id="db29e-245">**OR**</span></span> <br/> <span data-ttu-id="db29e-246">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="db29e-246">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="db29e-247">Lyncdiscoverint int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-247">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-248">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-248">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-249">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-249">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-250">Pool1InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-250">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-251">Pool2InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-251">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-252">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="db29e-252">Round Robin between pools</span></span>  <br/> <span data-ttu-id="db29e-253">**或者**</span><span class="sxs-lookup"><span data-stu-id="db29e-253">**OR**</span></span> <br/> <span data-ttu-id="db29e-254">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="db29e-254">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="db29e-255">Lyncdiscover ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-255">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-256">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-256">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-257">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-257">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-258">Pool1ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-258">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-259">Pool2ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-259">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-260">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="db29e-260">Round Robin between pools</span></span>  <br/> <span data-ttu-id="db29e-261">**或者**</span><span class="sxs-lookup"><span data-stu-id="db29e-261">**OR**</span></span> <br/> <span data-ttu-id="db29e-262">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="db29e-262">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="db29e-263">计划程序 int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-263">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-264">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-264">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-265">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-265">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-266">Pool1InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-266">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-267">Pool2InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-267">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-268">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="db29e-268">Round Robin between pools</span></span>  <br/> <span data-ttu-id="db29e-269">**或者**</span><span class="sxs-lookup"><span data-stu-id="db29e-269">**OR**</span></span> <br/> <span data-ttu-id="db29e-270">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="db29e-270">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="db29e-271">计划程序 ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-271">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-272">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-272">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-273">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-273">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-274">Pool1ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-274">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="db29e-275">Pool2ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="db29e-275">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-276">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="db29e-276">Round Robin between pools</span></span>  <br/> <span data-ttu-id="db29e-277">**或者**</span><span class="sxs-lookup"><span data-stu-id="db29e-277">**OR**</span></span> <br/> <span data-ttu-id="db29e-278">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="db29e-278">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="db29e-279">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="db29e-279">DNS load balancing</span></span>
<span data-ttu-id="db29e-280"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="db29e-280"></span></span>

<span data-ttu-id="db29e-281">通常在应用程序级别实现 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="db29e-281">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="db29e-282">应用程序 （例如，客户端运行 for Business 的 Skype），尝试连接到一个从返回的 IP 地址连接到池中的服务器的 DNS A 和 AAAA （如果使用 IPv6 寻址） 记录的池 FQDN 的查询。</span><span class="sxs-lookup"><span data-stu-id="db29e-282">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="db29e-283">例如，如果名为 pool01.contoso.com 的池中有三个前端服务器，以下会发生：</span><span class="sxs-lookup"><span data-stu-id="db29e-283">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="db29e-284">运行 for Business 的 Skype 的客户端 DNS 查询 pool01.contoso.com。查询返回三个 IP 地址，并将其缓存，如下所示 （在某些顺序）：</span><span class="sxs-lookup"><span data-stu-id="db29e-284">Clients running Skype for Business query DNS for pool01.contoso.com. The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="db29e-285">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-285">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-286">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="db29e-286">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="db29e-287">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-287">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-288">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="db29e-288">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="db29e-289">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db29e-289">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="db29e-290">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="db29e-290">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="db29e-p121">客户端将尝试建立与其中一个 IP 地址的 TCP 连接。如果失败，则客户端会尝试该列表中它所缓存的下一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="db29e-p121">The client tries to establish a TCP connection to one of the IP addresses. If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="db29e-293">如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。</span><span class="sxs-lookup"><span data-stu-id="db29e-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="db29e-294">如果客户端尝试了所有缓存的条目不成功连接的情况下，用户将收到通知，任何服务器运行业务服务器 2015 Skype 此时都已可用。</span><span class="sxs-lookup"><span data-stu-id="db29e-294">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server 2015 are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="db29e-p122">基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR)，后者通常是指依靠 DNS 来提供与池中服务器对应的不同顺序的 IP 地址来进行负载平衡。通常 DNS RR 启用负载分配，但不允许启用故障转移。例如，如果无法连接到由 DNS A 和 AAAA（如果使用 IPv6 寻址）查询返回的某个 IP 地址，则连接失败。这使得，DNS RR 的可靠性不如基于 DNS 的负载平衡。如果需要，可以将 DNS RR 与基于 DNS 的负载平衡结合使用。</span><span class="sxs-lookup"><span data-stu-id="db29e-p122">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool. Typically, DNS RR enables load distribution, but it won't allow you to enable failover. For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail. That makes DNS RR less reliable than DNS-based load balancing. You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="db29e-300">DNS 负载平衡可用来：</span><span class="sxs-lookup"><span data-stu-id="db29e-300">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="db29e-301">负载平衡服务器到服务器到边缘服务器的 SIP。</span><span class="sxs-lookup"><span data-stu-id="db29e-301">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="db29e-302">对统一通信应用程序服务 (UCAS) 应用程序（如会议自动助理、响应组和呼叫寄存）进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="db29e-302">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="db29e-303">阻止到 UCAS 应用程序的新连接（也称为排出）。</span><span class="sxs-lookup"><span data-stu-id="db29e-303">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="db29e-304">负载平衡客户端和边缘服务器之间的所有客户端到服务器通信。</span><span class="sxs-lookup"><span data-stu-id="db29e-304">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="db29e-305">DNS 负载平衡不可用于：</span><span class="sxs-lookup"><span data-stu-id="db29e-305">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="db29e-306">客户端到服务器的 web 前端服务器或控制器的流量。</span><span class="sxs-lookup"><span data-stu-id="db29e-306">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="db29e-307">继续更深入的 DNS SRV 记录如何选择当多 DNS 记录返回查询，访问边缘服务始终选择数字优先级最低记录时，断开裁判是否需要，可使用的最大数字权重。</span><span class="sxs-lookup"><span data-stu-id="db29e-307">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="db29e-308">这是与[Internet 工程任务组文档](https://www.ietf.org/rfc/rfc2782.txt)一致。</span><span class="sxs-lookup"><span data-stu-id="db29e-308">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="db29e-p124">例如，如果第一条 DNS SRV 记录权重为 20，优先级为 40，而第二条 DNS SRV 记录权重为 10，优先级为 50，则选择第一条记录，因为其优先级 40 更低。优先级总是最先进行比较，这是客户端首先要找的主机。优先级总是最先比较，这是首先成为客户端目标的主机。如果两个目标优先级相同该怎么办？</span><span class="sxs-lookup"><span data-stu-id="db29e-p124">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40. Priority always goes first, and that's the host that a client will target first. What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="db29e-p125">这种情况下，要考虑权重。优先级相同时，权重越大，被选中的可能性越大。当不作任何服务器选择时，DNS 管理员应使用权重 0。存在权重大于 0 的记录时，权重为 0 的记录被选中的机会极小。</span><span class="sxs-lookup"><span data-stu-id="db29e-p125">In that case, weight comes into consideration. Larger weights should be given a high probability, in this circumstance, of being selected. DNS administrators should use weight 0 when there isn't any server selection to do. In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="db29e-316">那么，如果返回了优先级和权重都相同的多个 DNS SRV 记录，那又该怎么办呢？</span><span class="sxs-lookup"><span data-stu-id="db29e-316">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="db29e-317">在这种情况下在访问边缘服务将选择它获得 DNS 服务器从第一个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="db29e-317">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

