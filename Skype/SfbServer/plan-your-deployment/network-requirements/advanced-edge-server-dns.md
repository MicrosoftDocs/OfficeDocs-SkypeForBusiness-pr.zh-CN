---
title: Skype for Business Server 的高级边缘服务器 DNS 规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 摘要：查看 Skype for business 服务器部署选项的方案。 无论您是需要单个服务器，还是希望使用 DNS 或 HLB 的服务器池，本主题都应有所帮助。
ms.openlocfilehash: b3893c11e1ce0cfdf9ab0b0452ef0a30a6442ee7
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887759"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a><span data-ttu-id="64b6f-104">Skype for Business Server 的高级边缘服务器 DNS 规划</span><span class="sxs-lookup"><span data-stu-id="64b6f-104">Advanced Edge Server DNS planning for Skype for Business Server</span></span>
 
<span data-ttu-id="64b6f-105">**摘要：** 查看 Skype for business 服务器部署选项的方案。</span><span class="sxs-lookup"><span data-stu-id="64b6f-105">**Summary:** Review scenarios for Skype for Business Server deployment options.</span></span> <span data-ttu-id="64b6f-106">无论您是需要单个服务器，还是希望使用 DNS 或 HLB 的服务器池，本主题都应有所帮助。</span><span class="sxs-lookup"><span data-stu-id="64b6f-106">Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="64b6f-107">当需要为 Skype for business 服务器规划域名系统（DNS）时，有许多因素可能会在你的决策中发挥作用。</span><span class="sxs-lookup"><span data-stu-id="64b6f-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="64b6f-108">如果组织的域结构已经就位，那么这可能就是考虑如何继续的问题。</span><span class="sxs-lookup"><span data-stu-id="64b6f-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="64b6f-109">我们将从下面提供的主题开始：</span><span class="sxs-lookup"><span data-stu-id="64b6f-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="64b6f-110">Walkthrough of Skype for Business clients locating services</span><span class="sxs-lookup"><span data-stu-id="64b6f-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="64b6f-111">Split-brain DNS</span><span class="sxs-lookup"><span data-stu-id="64b6f-111">Split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="64b6f-112">Automatic configuration without split-brain DNS</span><span class="sxs-lookup"><span data-stu-id="64b6f-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="64b6f-113">DNS disaster recovery</span><span class="sxs-lookup"><span data-stu-id="64b6f-113">DNS disaster recovery</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="64b6f-114">DNS load balancing</span><span class="sxs-lookup"><span data-stu-id="64b6f-114">DNS load balancing</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="64b6f-115">Walkthrough of Skype for Business clients locating services</span><span class="sxs-lookup"><span data-stu-id="64b6f-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="64b6f-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="64b6f-116"><a name="WalkthroughOfSkype"> </a></span></span>

<span data-ttu-id="64b6f-117">Skype for business 客户端与以前版本的 Lync 客户端类似于他们在 Skype for Business 服务器中查找和访问服务的方式。</span><span class="sxs-lookup"><span data-stu-id="64b6f-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server.</span></span> <span data-ttu-id="64b6f-118">本节详述服务查找过程。</span><span class="sxs-lookup"><span data-stu-id="64b6f-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="64b6f-119">lyncdiscoverinternal.\<域\></span><span class="sxs-lookup"><span data-stu-id="64b6f-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="64b6f-120">*这是内部 Web 服务上自动发现服务的 A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="64b6f-121">lyncdiscover.\<域\></span><span class="sxs-lookup"><span data-stu-id="64b6f-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="64b6f-122">*这是外部 Web 服务上自动发现服务的 A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="64b6f-123">_sipinternaltls _tcp。\<域\></span><span class="sxs-lookup"><span data-stu-id="64b6f-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="64b6f-124">*这是内部 TLS 连接的 SRV 记录。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="64b6f-125">_sip _tls。\<域\></span><span class="sxs-lookup"><span data-stu-id="64b6f-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="64b6f-126">*这是外部 TLS 连接的 SRV 记录。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="64b6f-127">sipinternal.\<域\></span><span class="sxs-lookup"><span data-stu-id="64b6f-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="64b6f-128">*这是前端池或控制器的主机记录，仅可在内部网络上解析。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="64b6f-129">sip.\<域\></span><span class="sxs-lookup"><span data-stu-id="64b6f-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="64b6f-130">*这是前端池或控制器的主机记录，仅可在内部网络上解析。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="64b6f-131">sipexternal.\<域\></span><span class="sxs-lookup"><span data-stu-id="64b6f-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="64b6f-132">*这是当客户端为外部客户端时，用于访问边缘服务的主机记录。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="64b6f-133">自动发现服务总是受人欢迎，因为这是服务定位的首选方法，其他方法为回退方法。</span><span class="sxs-lookup"><span data-stu-id="64b6f-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64b6f-p105">创建 SRV 记录时，请务必记住，这些记录需要指向要在其中创建 DNS SRV 记录的同一域中的 DNS A（如果使用 IPv6 寻址，则还有 AAAA）。例如，如果 SRV 记录位于 contoso.com，则其所指向的 A（和 AAAA）记录不能在 fabrikam.com 中。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p105">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created. For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="64b6f-p106">如果倾向于这样做，可以设置移动设备进行手动服务发现。如果这正是你想做的，那么每个用户需要为其移动设备的设置配置内部和外部自动发现服务的完整 URI，包括协议和路径，具体如下：</span><span class="sxs-lookup"><span data-stu-id="64b6f-p106">If you're inclined to do it, you can set your mobile device up for manual discovery of services. If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="64b6f-138">对于外部访问： https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="64b6f-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="64b6f-139">对于内部访问： https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="64b6f-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="64b6f-p107">我们建议使用自动发现，而不是手动发现。但是如果你要执行某种故障排除或测试，那么手动设置可能很有帮助。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p107">We do recommend you use automatic discovery as opposed to manual discovery. But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="64b6f-142">拆分式 DNS</span><span class="sxs-lookup"><span data-stu-id="64b6f-142">Split-brain DNS</span></span>
<span data-ttu-id="64b6f-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="64b6f-143"><a name="SplitBrainDNS"> </a></span></span>

<span data-ttu-id="64b6f-p108">这是一种两个 DNS 区域有相同命名空间的 DNS 配置。第一个 DNS 区域处理内部请求，而第二个 DNS 区域处理外部请求。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p108">This is a DNS configuration where you have two DNS zones with the same namespace. The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="64b6f-p109">为什么公司会这样做？他们可能需要内外使用相同的命名空间，但是当然，这会导致很多 DNS SRV 和 A 记录在这个区域或那个区域是唯一的，在有重复的情况下，与这些记录关联的 IP 地址将是唯一的。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p109">Why would a company do this? They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="64b6f-148">这带来了一些难题。</span><span class="sxs-lookup"><span data-stu-id="64b6f-148">This presents some challenges.</span></span> <span data-ttu-id="64b6f-149">最重要的是，**不支持**移动性的分裂 DNS。</span><span class="sxs-lookup"><span data-stu-id="64b6f-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="64b6f-150">这是因为 LyncDiscover 和 LyncDiscoverInternal DNS 记录（LyncDiscover 必须定义在外部 DNS 服务器上，而 LyncDiscoverInternal 必须定义在内部 DNS 服务器上）。</span><span class="sxs-lookup"><span data-stu-id="64b6f-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="64b6f-151">我们将在此处列出内部和外部区域的 DNS 记录，但你可以在 "边缘服务器环境要求" 部分中找到详细示例。</span><span class="sxs-lookup"><span data-stu-id="64b6f-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="64b6f-152">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="64b6f-152">Internal DNS</span></span>

- <span data-ttu-id="64b6f-153">包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。</span><span class="sxs-lookup"><span data-stu-id="64b6f-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="64b6f-154">这个内部 contoso.com 包含：</span><span class="sxs-lookup"><span data-stu-id="64b6f-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="64b6f-155">DNS A 和 AAAA （如果正在使用 IPv6 寻址）你的前端池、控制器池或控制器池名称的记录，以及组织网络中运行 Skype for Business 服务器的所有内部服务器。</span><span class="sxs-lookup"><span data-stu-id="64b6f-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server in your organization's network.</span></span>
    
  - <span data-ttu-id="64b6f-156">DNS A 和 AAAA （如果你正在为外围网络中的每个 Skype for Business Server Edge 服务器使用 IPv6 寻址）记录。</span><span class="sxs-lookup"><span data-stu-id="64b6f-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="64b6f-157">DNS A 和 AAAA （如果你正在使用 IPv6 寻址）你的外围网络中每个反向代理服务器的内部接口的记录（这对于对反向代理的管理是**可选**的）。</span><span class="sxs-lookup"><span data-stu-id="64b6f-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="64b6f-158">DNS A 和 AAAA （如果正在使用 IPv6 寻址）和用于内部 Skype for Business 服务器客户端自动配置的 SRV 记录（**可选**）。</span><span class="sxs-lookup"><span data-stu-id="64b6f-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="64b6f-159">DNS A 和 AAAA （如果你使用 IPv6 寻址）或用于自动发现 Skype for business Server Web 服务的 CNAME 记录（**可选**）。</span><span class="sxs-lookup"><span data-stu-id="64b6f-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="64b6f-160">您的外围网络中的所有 Skype for Business 服务器内部边缘接口都使用此内部 DNS 区域将查询解析到 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="64b6f-160">All your Skype for Business Server internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="64b6f-161">运行 Skype for Business 服务器的所有服务器以及运行企业网络中 Skype for business 服务器的客户端，指向内部 DNS 服务器以将查询解析到 contoso.com，或者使用每台边缘服务器上的主机文件和列表 A 和 AAAA （如果使用的是IPv6 寻址）下一个跃点服务器（专用于 Director 或 Director pool VIP、前端池 VIP 或标准版服务器）的记录。</span><span class="sxs-lookup"><span data-stu-id="64b6f-161">All servers running Skype for Business Server, and clients running Skype for Business Server in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="64b6f-162">外部 DNS</span><span class="sxs-lookup"><span data-stu-id="64b6f-162">External DNS</span></span>

- <span data-ttu-id="64b6f-163">包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。</span><span class="sxs-lookup"><span data-stu-id="64b6f-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="64b6f-164">此外部 contoso.com 包含：</span><span class="sxs-lookup"><span data-stu-id="64b6f-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="64b6f-165">DNS A 和 AAAA （如果正在使用 IPv6 寻址）或 CNAME 记录，用于自动发现 Skype for business Server web 服务。</span><span class="sxs-lookup"><span data-stu-id="64b6f-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server web services.</span></span> <span data-ttu-id="64b6f-166">这供移动使用。</span><span class="sxs-lookup"><span data-stu-id="64b6f-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="64b6f-167">DNS A 和 AAAA （如果正在使用 IPv6 寻址）和适用于外围网络中每个 Skype for Business 服务器边缘服务器或硬件负载平衡（HLB） VIP 的边缘外部接口的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="64b6f-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="64b6f-168">DNS A 和 AAAA （如果你正在使用 IPv6 寻址）和针对反向代理服务器的外部接口的 SRV 记录，或者是在外围网络中（反向代理服务器的 VIP）的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="64b6f-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="64b6f-169">DNS A 和 AAAA （如果您使用的是 IPv6 寻址）和 Skype for business 服务器客户端自动配置的 SRV 记录（**可选**）。</span><span class="sxs-lookup"><span data-stu-id="64b6f-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration ( **optional** ).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="64b6f-170">没有拆分式 DNS 时的自动配置</span><span class="sxs-lookup"><span data-stu-id="64b6f-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="64b6f-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="64b6f-171"><a name="NoSplitBrainDNS"> </a></span></span>

<span data-ttu-id="64b6f-172">如果不使用 "分裂大脑" DNS，则运行 Skype for Business 的客户的内部自动配置将不起作用，除非你使用我们的其中一种解决方法。</span><span class="sxs-lookup"><span data-stu-id="64b6f-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="64b6f-173">为什么会不起作用？</span><span class="sxs-lookup"><span data-stu-id="64b6f-173">Why not?</span></span> <span data-ttu-id="64b6f-174">由于 Skype for Business 服务器要求用户的 SIP URI 与为自动配置指定的前端池的域匹配。</span><span class="sxs-lookup"><span data-stu-id="64b6f-174">Because Skype for Business Server requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="64b6f-175">此操作未从早期版本的 Lync Server 更改。</span><span class="sxs-lookup"><span data-stu-id="64b6f-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="64b6f-176">所以，如果正在使用两个 SIP 域，那么需要以下 DNS SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="64b6f-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="64b6f-p113">_sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-p113">_sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="64b6f-179">*如果用户以 bob@contoso.com 的形式登录，此记录将适用于自动配置，因为用户的 SIP 域与前端池（contoso.com）的域相匹配。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-179">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="64b6f-180">_sipinternaltls._tcp.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="64b6f-180">_sipinternaltls._tcp.fabrikam.com.</span></span> <span data-ttu-id="64b6f-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="64b6f-182">*如果用户以 alice@fabrikam.com 的形式登录，则该记录将可用于自动配置第二个域，因为 SIP 域匹配该域的前端池。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-182">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="64b6f-183">再举此例，下面的记录不起作用：</span><span class="sxs-lookup"><span data-stu-id="64b6f-183">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="64b6f-p115">_sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-p115">_sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="64b6f-186">*作为 tim@litwareinc.com 登录的用户对自动配置不起作用，因为该用户的 SIP 域 (litwareinc.com) 与池中的域 (fabrikam.com) 不匹配。*</span><span class="sxs-lookup"><span data-stu-id="64b6f-186">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="64b6f-187">现在，我们知道，如果你需要对 Skype for Business 客户端的自动要求而不使用分裂的 DNS，则可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="64b6f-187">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="64b6f-188">**组策略对象**</span><span class="sxs-lookup"><span data-stu-id="64b6f-188">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="64b6f-189">可使用组策略对象 (GPO) 填充正确的服务器值。</span><span class="sxs-lookup"><span data-stu-id="64b6f-189">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="64b6f-p116">此选项不会启用自动配置，但可以自动化手动配置。如果使用此方法，则不需要与自动配置关联的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p116">This option doesn't enable automatic configuration, but it does automate manual configuration. If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="64b6f-192">**匹配内部区域**</span><span class="sxs-lookup"><span data-stu-id="64b6f-192">**Matching internal zone**</span></span>
    
    <span data-ttu-id="64b6f-193">你需要在内部 DNS 中创建一个与你的外部 DNS 区域（例如，contoso.com）匹配的区域，然后创建 DNS A （如果使用 IPv6 寻址，则为 AAAA）与用于自动的 Skype for business 服务器池相对应的记录配置.</span><span class="sxs-lookup"><span data-stu-id="64b6f-193">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="64b6f-194">例如，如果你有一个用户驻留在 pool01.contoso.net 上，但登录 Skype for business 的 bob@contoso.com，请创建名为 contoso.com 的内部 DNS 区域，并在其中创建一个名为 pool01.contoso.com 的 DNS A （如果使用 IPv6 寻址的 AAAA）记录。</span><span class="sxs-lookup"><span data-stu-id="64b6f-194">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="64b6f-195">**精确内部区域**</span><span class="sxs-lookup"><span data-stu-id="64b6f-195">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="64b6f-p117">如果在内部 DNS 中创建整个区域不适合你，你可以创建与自动配置所需要的 SRV 记录对应的精确（专用）区域，并使用 dnscmd.exe 填充这些区域。由于 DNS 用户界面不支持创建精确内部区域，因此需要 Dnscmd.exe。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p117">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe. Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="64b6f-198">例如，如果你的 SIP 域是 contoso.com，而你有一个名为 pool01 的前端池，其中包含两个前端服务器，则你需要在内部 DNS 中具有以下 pin 点区域和记录：</span><span class="sxs-lookup"><span data-stu-id="64b6f-198">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="64b6f-p118">环境中可能还有第二个 SIP 域。这种情况下，内部 DNS 中需要以下精确区域和 A 记录：</span><span class="sxs-lookup"><span data-stu-id="64b6f-p118">You may have a second SIP domain in your environment. In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> <span data-ttu-id="64b6f-201">你将看到前端池 FQDN 出现两次，但具有两个不同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="64b6f-201">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="64b6f-202">这是因为使用了 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="64b6f-202">That's because DNS load balancing is used.</span></span> <span data-ttu-id="64b6f-203">如果使用 HLB，则只能有一个前端池条目。</span><span class="sxs-lookup"><span data-stu-id="64b6f-203">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="64b6f-204">此外，前端池 FQDN 值在 contoso.com 和 fabrikam.com 示例之间更改，但 IP 地址保持不变。</span><span class="sxs-lookup"><span data-stu-id="64b6f-204">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="64b6f-205">这是因为从任一 SIP 域登录的用户都将使用相同的前端池进行自动配置。</span><span class="sxs-lookup"><span data-stu-id="64b6f-205">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="64b6f-206">DNS 灾难恢复</span><span class="sxs-lookup"><span data-stu-id="64b6f-206">DNS disaster recovery</span></span>
<span data-ttu-id="64b6f-207"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="64b6f-207"><a name="DNSDR"> </a></span></span>

<span data-ttu-id="64b6f-208">若要将 DNS 配置为将 Skype for Business 服务器 web 流量重定向到灾难恢复（DR）和故障转移站点，需要使用支持 GeoDNS 的 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="64b6f-208">To configure DNS to redirect Skype for Business Server web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="64b6f-209">你可以将 DNS 记录设置为支持灾难恢复，以便使用 web 服务的功能即使在一个完整的前端池停止时也会继续。</span><span class="sxs-lookup"><span data-stu-id="64b6f-209">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="64b6f-210">此 DR 功能支持自动发现、会议和拨入式简单 URL。</span><span class="sxs-lookup"><span data-stu-id="64b6f-210">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="64b6f-p122">你可以在 GeoDNS 提供商处定义和配置用于 Web 服务的内部和外部解析额外的 DNS 主机 A（如果使用 IPv6，则为 AAAA）记录。以下详细信息假定池已配对，地理位置分散，且提供商支持的 GeoDNS **要么**使用循环 DNS，**要么**配置为使用 Pool1 作为主池，并且在发生通信丢失或电源故障时故障转移到 Pool2。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p122">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider. The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="64b6f-213">下表中的所有 DNS 记录均为示例。</span><span class="sxs-lookup"><span data-stu-id="64b6f-213">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="64b6f-214">**GeoDNS 记录**</span><span class="sxs-lookup"><span data-stu-id="64b6f-214">**GeoDNS record**</span></span>|<span data-ttu-id="64b6f-215">**池记录**</span><span class="sxs-lookup"><span data-stu-id="64b6f-215">**Pool records**</span></span>|<span data-ttu-id="64b6f-216">**CNAME 记录**</span><span class="sxs-lookup"><span data-stu-id="64b6f-216">**CNAME records**</span></span>|<span data-ttu-id="64b6f-217">**DNS 设置（选择一个选项）**</span><span class="sxs-lookup"><span data-stu-id="64b6f-217">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="64b6f-218">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-218">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-219">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-219">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-220">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-220">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-221">Pool1InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-221">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-222">Pool2InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-222">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-223">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="64b6f-223">Round Robin between pools</span></span>  <br/> <span data-ttu-id="64b6f-224">**或者**</span><span class="sxs-lookup"><span data-stu-id="64b6f-224">**OR**</span></span> <br/> <span data-ttu-id="64b6f-225">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="64b6f-225">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="64b6f-226">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-226">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-227">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-227">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-228">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-228">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-229">Pool1ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-229">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-230">Pool2ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-230">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-231">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="64b6f-231">Round Robin between pools</span></span>  <br/> <span data-ttu-id="64b6f-232">**或者**</span><span class="sxs-lookup"><span data-stu-id="64b6f-232">**OR**</span></span> <br/> <span data-ttu-id="64b6f-233">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="64b6f-233">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="64b6f-234">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-234">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-235">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-235">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-236">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-236">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-237">Pool1InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-237">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-238">Pool2InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-238">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-239">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="64b6f-239">Round Robin between pools</span></span>  <br/> <span data-ttu-id="64b6f-240">**或者**</span><span class="sxs-lookup"><span data-stu-id="64b6f-240">**OR**</span></span> <br/> <span data-ttu-id="64b6f-241">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="64b6f-241">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="64b6f-242">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-242">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-243">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-243">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-244">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-244">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-245">Pool1ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-245">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-246">Pool2ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-246">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-247">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="64b6f-247">Round Robin between pools</span></span>  <br/> <span data-ttu-id="64b6f-248">**或者**</span><span class="sxs-lookup"><span data-stu-id="64b6f-248">**OR**</span></span> <br/> <span data-ttu-id="64b6f-249">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="64b6f-249">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="64b6f-250">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-250">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-251">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-251">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-252">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-252">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-253">Pool1InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-253">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-254">Pool2InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-254">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-255">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="64b6f-255">Round Robin between pools</span></span>  <br/> <span data-ttu-id="64b6f-256">**或者**</span><span class="sxs-lookup"><span data-stu-id="64b6f-256">**OR**</span></span> <br/> <span data-ttu-id="64b6f-257">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="64b6f-257">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="64b6f-258">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-258">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-259">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-259">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-260">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-260">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-261">Pool1ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-261">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-262">Pool2ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-262">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-263">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="64b6f-263">Round Robin between pools</span></span>  <br/> <span data-ttu-id="64b6f-264">**或者**</span><span class="sxs-lookup"><span data-stu-id="64b6f-264">**OR**</span></span> <br/> <span data-ttu-id="64b6f-265">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="64b6f-265">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="64b6f-266">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-266">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-267">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-267">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-268">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-268">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-269">Pool1InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-269">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-270">Pool2InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-270">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-271">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="64b6f-271">Round Robin between pools</span></span>  <br/> <span data-ttu-id="64b6f-272">**或者**</span><span class="sxs-lookup"><span data-stu-id="64b6f-272">**OR**</span></span> <br/> <span data-ttu-id="64b6f-273">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="64b6f-273">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="64b6f-274">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-274">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-275">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-275">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-276">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-276">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-277">Pool1ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-277">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="64b6f-278">Pool2ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="64b6f-278">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-279">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="64b6f-279">Round Robin between pools</span></span>  <br/> <span data-ttu-id="64b6f-280">**或者**</span><span class="sxs-lookup"><span data-stu-id="64b6f-280">**OR**</span></span> <br/> <span data-ttu-id="64b6f-281">使用主池，发生故障时连接到副池</span><span class="sxs-lookup"><span data-stu-id="64b6f-281">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="64b6f-282">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="64b6f-282">DNS load balancing</span></span>
<span data-ttu-id="64b6f-283"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="64b6f-283"><a name="DNSLB"> </a></span></span>

<span data-ttu-id="64b6f-284">通常在应用程序级别实现 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="64b6f-284">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="64b6f-285">应用程序（例如，运行 Skype for Business 的客户端）通过连接到池 FQDN 的 DNS A 和 AAAA （如果使用 IPv6 寻址）记录查询来连接到池中的某个 IP 地址，尝试连接到池中的服务器。</span><span class="sxs-lookup"><span data-stu-id="64b6f-285">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="64b6f-286">例如，如果一个名为 pool01.contoso.com 的池中有三个前端服务器，则会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="64b6f-286">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="64b6f-287">运行 Skype for business 的 pool01.contoso.com 的客户端查询 DNS。</span><span class="sxs-lookup"><span data-stu-id="64b6f-287">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="64b6f-288">此查询将返回三个 IP 地址并如下方式缓存它们（按某种顺序）：</span><span class="sxs-lookup"><span data-stu-id="64b6f-288">The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="64b6f-289">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-289">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-290">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="64b6f-290">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="64b6f-291">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-291">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-292">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="64b6f-292">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="64b6f-293">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64b6f-293">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="64b6f-294">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="64b6f-294">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="64b6f-p125">客户端将尝试建立与其中一个 IP 地址的 TCP 连接。如果失败，则客户端会尝试该列表中它所缓存的下一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p125">The client tries to establish a TCP connection to one of the IP addresses. If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="64b6f-297">如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。</span><span class="sxs-lookup"><span data-stu-id="64b6f-297">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="64b6f-298">如果客户在未成功连接的情况下尝试所有缓存的条目，用户此时将收到一条通知，表明当前没有运行 Skype for business 服务器的服务器可用。</span><span class="sxs-lookup"><span data-stu-id="64b6f-298">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="64b6f-p126">基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR)，后者通常是指依靠 DNS 来提供与池中服务器对应的不同顺序的 IP 地址来进行负载平衡。通常 DNS RR 启用负载分配，但不允许启用故障转移。例如，如果无法连接到由 DNS A 和 AAAA（如果使用 IPv6 寻址）查询返回的某个 IP 地址，则连接失败。这使得，DNS RR 的可靠性不如基于 DNS 的负载平衡。如果需要，可以将 DNS RR 与基于 DNS 的负载平衡结合使用。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p126">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool. Typically, DNS RR enables load distribution, but it won't allow you to enable failover. For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail. That makes DNS RR less reliable than DNS-based load balancing. You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="64b6f-304">DNS 负载平衡可用来：</span><span class="sxs-lookup"><span data-stu-id="64b6f-304">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="64b6f-305">将服务器到服务器 SIP 的负载平衡到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="64b6f-305">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="64b6f-306">对统一通信应用程序服务 (UCAS) 应用程序（如会议自动助理、响应组和呼叫寄存）进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="64b6f-306">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="64b6f-307">阻止到 UCAS 应用程序的新连接（也称为排出）。</span><span class="sxs-lookup"><span data-stu-id="64b6f-307">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="64b6f-308">在客户端和边缘服务器之间对所有客户端到服务器的通信进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="64b6f-308">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="64b6f-309">DNS 负载平衡不可用于：</span><span class="sxs-lookup"><span data-stu-id="64b6f-309">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="64b6f-310">与您的前端服务器或 Director 的客户端到服务器 web 流量。</span><span class="sxs-lookup"><span data-stu-id="64b6f-310">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="64b6f-311">若要更深入地了解查询返回 mutiple DNS 记录时如何选择 DNS SRV 记录，Access Edge 服务始终使用最低的数值优先级选择记录，并且如果需要断字符，则使用最高的数字权重。</span><span class="sxs-lookup"><span data-stu-id="64b6f-311">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="64b6f-312">这与[Internet 工程任务组文档](https://www.ietf.org/rfc/rfc2782.txt)一致。</span><span class="sxs-lookup"><span data-stu-id="64b6f-312">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="64b6f-p128">例如，如果第一条 DNS SRV 记录权重为 20，优先级为 40，而第二条 DNS SRV 记录权重为 10，优先级为 50，则选择第一条记录，因为其优先级 40 更低。优先级总是最先进行比较，这是客户端首先要找的主机。优先级总是最先比较，这是首先成为客户端目标的主机。如果两个目标优先级相同该怎么办？</span><span class="sxs-lookup"><span data-stu-id="64b6f-p128">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40. Priority always goes first, and that's the host that a client will target first. What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="64b6f-p129">这种情况下，要考虑权重。优先级相同时，权重越大，被选中的可能性越大。当不作任何服务器选择时，DNS 管理员应使用权重 0。存在权重大于 0 的记录时，权重为 0 的记录被选中的机会极小。</span><span class="sxs-lookup"><span data-stu-id="64b6f-p129">In that case, weight comes into consideration. Larger weights should be given a high probability, in this circumstance, of being selected. DNS administrators should use weight 0 when there isn't any server selection to do. In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="64b6f-320">那么，如果返回了优先级和权重都相同的多个 DNS SRV 记录，那又该怎么办呢？</span><span class="sxs-lookup"><span data-stu-id="64b6f-320">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="64b6f-321">在这种情况下，Access Edge 服务将选择它首先从 DNS 服务器获取的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="64b6f-321">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

