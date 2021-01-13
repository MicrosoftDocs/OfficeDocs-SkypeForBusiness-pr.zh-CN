---
title: Skype for Business Server 的高级边缘服务器 DNS 规划
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：查看 Skype for Business Server 部署选项的方案。 无论是希望使用单个服务器还是首选具有 DNS 或 HLB 的服务器池，本主题都应有所帮助。
ms.openlocfilehash: 5a41baac30f3bf6a1e20ae34db009dae0cec40af
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825322"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a><span data-ttu-id="753b3-104">Skype for Business Server 的高级边缘服务器 DNS 规划</span><span class="sxs-lookup"><span data-stu-id="753b3-104">Advanced Edge Server DNS planning for Skype for Business Server</span></span>
 
<span data-ttu-id="753b3-105">**摘要：** 查看 Skype for Business Server 部署选项的方案。</span><span class="sxs-lookup"><span data-stu-id="753b3-105">**Summary:** Review scenarios for Skype for Business Server deployment options.</span></span> <span data-ttu-id="753b3-106">无论是希望使用单个服务器还是首选具有 DNS 或 HLB 的服务器池，本主题都应有所帮助。</span><span class="sxs-lookup"><span data-stu-id="753b3-106">Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="753b3-107">在规划 Skype for Business Server 的域名系统 (DNS) 时，你的决策可能会涉及许多因素。</span><span class="sxs-lookup"><span data-stu-id="753b3-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="753b3-108">如果组织的域结构已就位，这可能就是查看如何继续操作的问题。</span><span class="sxs-lookup"><span data-stu-id="753b3-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="753b3-109">我们将从以下主题开始：</span><span class="sxs-lookup"><span data-stu-id="753b3-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="753b3-110">Skype for Business 客户端定位服务的演练</span><span class="sxs-lookup"><span data-stu-id="753b3-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="753b3-111">拆分式 DNS</span><span class="sxs-lookup"><span data-stu-id="753b3-111">Split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="753b3-112">无拆分式 DNS 的自动配置</span><span class="sxs-lookup"><span data-stu-id="753b3-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="753b3-113">DNS 灾难恢复</span><span class="sxs-lookup"><span data-stu-id="753b3-113">DNS disaster recovery</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="753b3-114">DNS load balancing － DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="753b3-114">DNS load balancing</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="753b3-115">Skype for Business 客户端定位服务的演练</span><span class="sxs-lookup"><span data-stu-id="753b3-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="753b3-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="753b3-116"><a name="WalkthroughOfSkype"> </a></span></span>

<span data-ttu-id="753b3-117">Skype for Business 客户端在如何查找和访问 Skype for Business Server 中的服务方面与早期版本的 Lync 客户端类似。</span><span class="sxs-lookup"><span data-stu-id="753b3-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server.</span></span> <span data-ttu-id="753b3-118">本节详细介绍服务器位置过程。</span><span class="sxs-lookup"><span data-stu-id="753b3-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="753b3-119">lyncdiscoverinternal。\<domain\></span><span class="sxs-lookup"><span data-stu-id="753b3-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="753b3-120">*这是内部 Web 服务上的自动发现服务的 A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="753b3-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="753b3-121">lyncdiscover。\<domain\></span><span class="sxs-lookup"><span data-stu-id="753b3-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="753b3-122">*这是外部 Web 服务上的自动发现服务的 A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="753b3-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="753b3-123">_sipinternaltls._tcp。\<domain\></span><span class="sxs-lookup"><span data-stu-id="753b3-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="753b3-124">*这是内部 TLS 连接的 SRV 记录。*</span><span class="sxs-lookup"><span data-stu-id="753b3-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="753b3-125">_sip._tls。\<domain\></span><span class="sxs-lookup"><span data-stu-id="753b3-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="753b3-126">*这是外部 TLS 连接的 SRV 记录。*</span><span class="sxs-lookup"><span data-stu-id="753b3-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="753b3-127">sipinternal。\<domain\></span><span class="sxs-lookup"><span data-stu-id="753b3-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="753b3-128">*这是前端池或控制器的 A 主机记录，只能在内部网络上进行解说。*</span><span class="sxs-lookup"><span data-stu-id="753b3-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="753b3-129">sip。\<domain\></span><span class="sxs-lookup"><span data-stu-id="753b3-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="753b3-130">*这是前端池或控制器的 A 主机记录，只能在内部网络上进行解说。*</span><span class="sxs-lookup"><span data-stu-id="753b3-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="753b3-131">sipexternal。\<domain\></span><span class="sxs-lookup"><span data-stu-id="753b3-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="753b3-132">*当客户端位于外部时，这是访问边缘服务的 A 主机记录。*</span><span class="sxs-lookup"><span data-stu-id="753b3-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="753b3-133">自动发现服务始终受支持，因为这是服务位置的首选方法，其他方法为回退方法。</span><span class="sxs-lookup"><span data-stu-id="753b3-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="753b3-134">创建 SRV 记录时，必须记住，如果你正在创建 DNS SRV 记录的同一域中使用 IPv6 寻址) ，它们需要指向 DNS A (和 AAAA。</span><span class="sxs-lookup"><span data-stu-id="753b3-134">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created.</span></span> <span data-ttu-id="753b3-135">例如，如果 SRV 记录在 contoso.com 中，则它 (A) 和 AAAA 记录不能fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="753b3-135">For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="753b3-136">如果你倾向于这样做，你可以将移动设备设置为手动发现服务。</span><span class="sxs-lookup"><span data-stu-id="753b3-136">If you're inclined to do it, you can set your mobile device up for manual discovery of services.</span></span> <span data-ttu-id="753b3-137">如果你希望这样做，每个用户都需要使用完整的内部和外部自动发现服务 URI（包括协议和路径）配置其移动设备设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="753b3-137">If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="753b3-138">对于外部访问：https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="753b3-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="753b3-139">对于内部访问：https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="753b3-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="753b3-140">我们建议你使用自动发现，而不是手动发现。</span><span class="sxs-lookup"><span data-stu-id="753b3-140">We do recommend you use automatic discovery as opposed to manual discovery.</span></span> <span data-ttu-id="753b3-141">但是，如果你要执行一些故障排除或测试，手动设置可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="753b3-141">But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="753b3-142">拆分式 DNS</span><span class="sxs-lookup"><span data-stu-id="753b3-142">Split-brain DNS</span></span>
<span data-ttu-id="753b3-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="753b3-143"><a name="SplitBrainDNS"> </a></span></span>

<span data-ttu-id="753b3-144">这是一个 DNS 配置，其中两个 DNS 区域具有相同的命名空间。</span><span class="sxs-lookup"><span data-stu-id="753b3-144">This is a DNS configuration where you have two DNS zones with the same namespace.</span></span> <span data-ttu-id="753b3-145">第一个 DNS 区域处理内部请求，第二个 DNS 区域处理外部请求。</span><span class="sxs-lookup"><span data-stu-id="753b3-145">The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="753b3-146">为什么公司会这样做？</span><span class="sxs-lookup"><span data-stu-id="753b3-146">Why would a company do this?</span></span> <span data-ttu-id="753b3-147">它们可能需要在内部和外部使用相同的命名空间，但当然，这可能会导致许多 DNS SRV 和 A 记录对一个区域或另一个区域是唯一的，如果重复，则与这些记录关联的 IP 地址将是唯一的。</span><span class="sxs-lookup"><span data-stu-id="753b3-147">They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="753b3-148">这带来了一些挑战。</span><span class="sxs-lookup"><span data-stu-id="753b3-148">This presents some challenges.</span></span> <span data-ttu-id="753b3-149">最重要的是，移动功能不支持拆分式 DNS。 </span><span class="sxs-lookup"><span data-stu-id="753b3-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="753b3-150">这是因为 LyncDiscover 和 LyncDiscoverInternal DNS 记录 (LyncDiscover 必须定义在外部 DNS 服务器上，而 LyncDiscoverInternal 必须定义在内部 DNS 服务器上) 。</span><span class="sxs-lookup"><span data-stu-id="753b3-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="753b3-151">我们将在此处列出内部和外部区域 DNS 记录，但您可以在边缘服务器环境要求部分找到详细示例。</span><span class="sxs-lookup"><span data-stu-id="753b3-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="753b3-152">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="753b3-152">Internal DNS</span></span>

- <span data-ttu-id="753b3-153">包含名为 (的 DNS 区域，) contoso.com具有权威性的 DNS 区域。</span><span class="sxs-lookup"><span data-stu-id="753b3-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="753b3-154">此内部contoso.com包含：</span><span class="sxs-lookup"><span data-stu-id="753b3-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="753b3-155">如果对前端池、控制器池或控制器池名称以及组织网络中运行 Skype for Business Server 的所有内部服务器使用 IPv6 寻址) 记录，则 DNS A 和 AAAA (。</span><span class="sxs-lookup"><span data-stu-id="753b3-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server in your organization's network.</span></span>
    
  - <span data-ttu-id="753b3-156">如果为外围网络 (每台 Skype for Business Server 边缘服务器的边缘内部接口使用 IPv6 寻址) 记录，则 DNS A 和 AAAA 支持。</span><span class="sxs-lookup"><span data-stu-id="753b3-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="753b3-157">如果将 IPv6 寻址) 记录用于外围网络 (中每个反向代理服务器的内部接口，则 DNS A 和 AAA (A (对于反向代理服务管理) 。</span><span class="sxs-lookup"><span data-stu-id="753b3-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="753b3-158">如果将 IPv6 寻址) 和 SRV 记录用于内部 Skype for Business Server 客户端自动配置，则 DNS A 和 AAA  (A (可选) 。</span><span class="sxs-lookup"><span data-stu-id="753b3-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="753b3-159">如果使用 IPv6 寻址) 或 CNAME 记录自动发现 Skype for Business Server Web Services (（可选）) ，则 DNS A 和 AAA (A **) 。**</span><span class="sxs-lookup"><span data-stu-id="753b3-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="753b3-160">外围网络内的所有 Skype for Business Server 内部边缘接口都使用此内部 DNS 区域解析对contoso.com。</span><span class="sxs-lookup"><span data-stu-id="753b3-160">All your Skype for Business Server internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="753b3-161">运行 Skype for Business Server 的所有服务器以及企业网络中运行 Skype for Business Server 的客户端指向内部 DNS 服务器，以将查询解析为 contoso.com，或者，如果你为下一跃点服务器 (（专门针对控制器或控制器池 VIP、前端池 VIP 或 Standard Edition Server () ）使用 IPv6 寻址) 记录，则这些服务器会在每个边缘服务器上使用主机文件并列出 A 和 AAAA) 。</span><span class="sxs-lookup"><span data-stu-id="753b3-161">All servers running Skype for Business Server, and clients running Skype for Business Server in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="753b3-162">外部 DNS</span><span class="sxs-lookup"><span data-stu-id="753b3-162">External DNS</span></span>

- <span data-ttu-id="753b3-163">包含名为 (的 DNS 区域，) contoso.com具有权威性的 DNS 区域。</span><span class="sxs-lookup"><span data-stu-id="753b3-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="753b3-164">此外部contoso.com包含：</span><span class="sxs-lookup"><span data-stu-id="753b3-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="753b3-165">如果使用 IPv6 寻址) 或 CNAME 记录，则 DNS A 和 AAAA (自动发现 Skype for Business Server Web 服务。</span><span class="sxs-lookup"><span data-stu-id="753b3-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server web services.</span></span> <span data-ttu-id="753b3-166">这适用于移动功能。</span><span class="sxs-lookup"><span data-stu-id="753b3-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="753b3-167">如果对外围网络中每个 Skype for Business Server 边缘服务器的边缘外部接口或硬件负载平衡 (HLB) VIP 使用 IPv6 寻址) 和 SRV 记录，则 DNS A 和 AAAA (。</span><span class="sxs-lookup"><span data-stu-id="753b3-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="753b3-168">如果对反向代理服务器的外部接口使用 IPv6 寻址) 和 SRV 记录，或在外围网络中为反向代理服务器) 池使用 (VIP，则 DNS A 和 AAA (A) 。</span><span class="sxs-lookup"><span data-stu-id="753b3-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="753b3-169">如果为 Skype for Business Server 客户端自动配置使用 IPv6 寻址) 和 SRV 记录，则 DNS A 和 AAA (A (**可选) 。**</span><span class="sxs-lookup"><span data-stu-id="753b3-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration ( **optional** ).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="753b3-170">无拆分式 DNS 的自动配置</span><span class="sxs-lookup"><span data-stu-id="753b3-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="753b3-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="753b3-171"><a name="NoSplitBrainDNS"> </a></span></span>

<span data-ttu-id="753b3-172">如果不使用拆分式 DNS，运行 Skype for Business 的客户端的内部自动配置将不起作用，除非你使用的是我们在此处使用的解决方法之一。</span><span class="sxs-lookup"><span data-stu-id="753b3-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="753b3-173">这是为什么？</span><span class="sxs-lookup"><span data-stu-id="753b3-173">Why not?</span></span> <span data-ttu-id="753b3-174">由于 Skype for Business Server 要求用户的 SIP URI 与为自动配置指定的前端池的域相匹配。</span><span class="sxs-lookup"><span data-stu-id="753b3-174">Because Skype for Business Server requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="753b3-175">这一点与早期版本的 Lync Server 没有变化。</span><span class="sxs-lookup"><span data-stu-id="753b3-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="753b3-176">因此，如果你有两个 SIP 域在使用，则需要以下 DNS SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="753b3-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="753b3-177">_sipinternaltls._tcp.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="753b3-177">_sipinternaltls._tcp.contoso.com.</span></span> <span data-ttu-id="753b3-178">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-178">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="753b3-179">*如果用户以 bob@contoso.com 登录，则此记录适用于自动配置，因为用户的 SIP 域与前端池的域 (contoso.com) 。*</span><span class="sxs-lookup"><span data-stu-id="753b3-179">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="753b3-180">_sipinternaltls._tcp.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="753b3-180">_sipinternaltls._tcp.fabrikam.com.</span></span> <span data-ttu-id="753b3-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="753b3-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="753b3-182">*如果用户以 alice@fabrikam.com 登录，则此记录将再次用于第二个域的自动配置，因为 SIP 域与该域的前端池匹配。*</span><span class="sxs-lookup"><span data-stu-id="753b3-182">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="753b3-183">若要进一步说明示例，此操作将不起作用：</span><span class="sxs-lookup"><span data-stu-id="753b3-183">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="753b3-184">_sipinternaltls._tcp.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="753b3-184">_sipinternaltls._tcp.litwareinc.com.</span></span> <span data-ttu-id="753b3-185">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="753b3-185">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="753b3-186">*用户以 tim@litwareinc.com 登录无法进行自动配置，因为用户的 SIP 域 (litwareinc.com) 与池中的域不匹配 (fabrikam.com) 。*</span><span class="sxs-lookup"><span data-stu-id="753b3-186">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="753b3-187">既然我们知道这一切，如果你需要自动要求 Skype for Business 客户端而不使用拆分式 DNS，你拥有以下选项：</span><span class="sxs-lookup"><span data-stu-id="753b3-187">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="753b3-188">**组策略对象**</span><span class="sxs-lookup"><span data-stu-id="753b3-188">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="753b3-189">可以使用组策略对象 (GPO) 填充正确的服务器值。</span><span class="sxs-lookup"><span data-stu-id="753b3-189">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="753b3-190">此选项不启用自动配置，但它确实可以自动执行手动配置。</span><span class="sxs-lookup"><span data-stu-id="753b3-190">This option doesn't enable automatic configuration, but it does automate manual configuration.</span></span> <span data-ttu-id="753b3-191">如果使用此方法，则不需要与自动配置关联的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="753b3-191">If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="753b3-192">**匹配内部区域**</span><span class="sxs-lookup"><span data-stu-id="753b3-192">**Matching internal zone**</span></span>
    
    <span data-ttu-id="753b3-193">你需要在内部 DNS 中创建一个与外部 DNS 区域 (相匹配的区域，例如 contoso.com) ，如果你使用的是与用于自动配置的 Skype for Business Server 池相对应的 IPv6 寻址) 记录，则需要创建 DNS A (和 AAAA。</span><span class="sxs-lookup"><span data-stu-id="753b3-193">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="753b3-194">例如，如果你的用户托管在 pool01.contoso.net 上，但以 bob@contoso.com 登录 Skype for Business，请创建名为 contoso.com 的内部 DNS 区域，如果 pool01.contoso.com 使用 IPv) 6 寻址记录，则需要在内部创建 DNS A (和 AAAA。</span><span class="sxs-lookup"><span data-stu-id="753b3-194">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="753b3-195">**固定点内部区域**</span><span class="sxs-lookup"><span data-stu-id="753b3-195">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="753b3-196">如果无法选择在内部 DNS 中创建整个区域，可以创建与自动配置所需的 SRV 记录相对应的 pin-point (专用) 区域，并使用 dnscmd.exe 填充这些区域。</span><span class="sxs-lookup"><span data-stu-id="753b3-196">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="753b3-197">Dnscmd.exe，因为 DNS 用户界面不支持创建 pin-point 区域。</span><span class="sxs-lookup"><span data-stu-id="753b3-197">Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="753b3-198">例如，如果您的 SIP 域是 contoso.com，并且您的前端池名为 pool01，其中包含两台前端服务器，则需要内部 DNS 中的以下 pin-point 区域和 A 记录：</span><span class="sxs-lookup"><span data-stu-id="753b3-198">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="753b3-199">环境中可能有第二个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="753b3-199">You may have a second SIP domain in your environment.</span></span> <span data-ttu-id="753b3-200">在这种情况下，内部 DNS 中需要以下 pin-point 区域和 A 记录：</span><span class="sxs-lookup"><span data-stu-id="753b3-200">In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
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
> <span data-ttu-id="753b3-201">你将看到前端池 FQDN 出现两次，但显示两个不同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="753b3-201">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="753b3-202">这是因为使用了 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="753b3-202">That's because DNS load balancing is used.</span></span> <span data-ttu-id="753b3-203">如果使用 HLB，则只有一个前端池条目。</span><span class="sxs-lookup"><span data-stu-id="753b3-203">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="753b3-204">此外，前端池 FQDN 值在contoso.com和fabrikam.com更改，但 IP 地址保持不变。</span><span class="sxs-lookup"><span data-stu-id="753b3-204">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="753b3-205">这是因为从任一 SIP 域登录的用户将使用相同的前端池进行自动配置。</span><span class="sxs-lookup"><span data-stu-id="753b3-205">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="753b3-206">DNS 灾难恢复</span><span class="sxs-lookup"><span data-stu-id="753b3-206">DNS disaster recovery</span></span>
<span data-ttu-id="753b3-207"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="753b3-207"><a name="DNSDR"> </a></span></span>

<span data-ttu-id="753b3-208">若要将 DNS 配置为将 Skype for Business Server Web 流量重定向到灾难恢复 (DR) 和故障转移站点，您需要使用支持 GeoDNS 的 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="753b3-208">To configure DNS to redirect Skype for Business Server web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="753b3-209">您可以将 DNS 记录设置为支持灾难恢复，以便即使整个前端池关闭，使用 Web 服务的功能也将继续。</span><span class="sxs-lookup"><span data-stu-id="753b3-209">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="753b3-210">此 DR 功能支持自动发现、开会和拨入简单 URL。</span><span class="sxs-lookup"><span data-stu-id="753b3-210">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="753b3-211">如果对 GeoDNS 提供程序的 Web 服务内部和外部解析使用 IPv6) 记录，则定义和配置其他 DNS 主机 A (AAAA。</span><span class="sxs-lookup"><span data-stu-id="753b3-211">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider.</span></span> <span data-ttu-id="753b3-212">以下详细信息假定配对池，地理位置分散，且提供程序支持的 GeoDNS 具有循环 **DNS** 或配置为使用 Pool1 作为主池，当出现任何通信丢失或电源故障时，将故障情况故障恢复至 Pool2。</span><span class="sxs-lookup"><span data-stu-id="753b3-212">The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="753b3-213">此表中的所有 DNS 记录都是示例。</span><span class="sxs-lookup"><span data-stu-id="753b3-213">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="753b3-214">**GeoDNS 记录**</span><span class="sxs-lookup"><span data-stu-id="753b3-214">**GeoDNS record**</span></span>|<span data-ttu-id="753b3-215">**池记录**</span><span class="sxs-lookup"><span data-stu-id="753b3-215">**Pool records**</span></span>|<span data-ttu-id="753b3-216">**CNAME 记录**</span><span class="sxs-lookup"><span data-stu-id="753b3-216">**CNAME records**</span></span>|<span data-ttu-id="753b3-217">**DNS 设置 (选择一个选项)**</span><span class="sxs-lookup"><span data-stu-id="753b3-217">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="753b3-218">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-218">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-219">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-219">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-220">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-220">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-221">Meet.contoso.com别名Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-221">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-222">Meet.contoso.com别名Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-222">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-223">池之间的循环</span><span class="sxs-lookup"><span data-stu-id="753b3-223">Round Robin between pools</span></span>  <br/> <span data-ttu-id="753b3-224">**或**</span><span class="sxs-lookup"><span data-stu-id="753b3-224">**OR**</span></span> <br/> <span data-ttu-id="753b3-225">使用主连接，如果出现故障，则连接到辅助服务器</span><span class="sxs-lookup"><span data-stu-id="753b3-225">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="753b3-226">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-226">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-227">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-227">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-228">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-228">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-229">Meet.contoso.com别名Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-229">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-230">Meet.contoso.com别名Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-230">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-231">池之间的循环</span><span class="sxs-lookup"><span data-stu-id="753b3-231">Round Robin between pools</span></span>  <br/> <span data-ttu-id="753b3-232">**或**</span><span class="sxs-lookup"><span data-stu-id="753b3-232">**OR**</span></span> <br/> <span data-ttu-id="753b3-233">使用主连接，如果出现故障，则连接到辅助服务器</span><span class="sxs-lookup"><span data-stu-id="753b3-233">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="753b3-234">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-234">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-235">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-235">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-236">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-236">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-237">Dialin.contoso.com别名Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-237">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-238">Dialin.contoso.com别名Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-238">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-239">池之间的循环</span><span class="sxs-lookup"><span data-stu-id="753b3-239">Round Robin between pools</span></span>  <br/> <span data-ttu-id="753b3-240">**或**</span><span class="sxs-lookup"><span data-stu-id="753b3-240">**OR**</span></span> <br/> <span data-ttu-id="753b3-241">使用主连接，如果出现故障，则连接到辅助服务器</span><span class="sxs-lookup"><span data-stu-id="753b3-241">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="753b3-242">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-242">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-243">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-243">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-244">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-244">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-245">Dialin.contoso.com别名Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-245">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-246">Dialin.contoso.com别名Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-246">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-247">池之间的循环</span><span class="sxs-lookup"><span data-stu-id="753b3-247">Round Robin between pools</span></span>  <br/> <span data-ttu-id="753b3-248">**或**</span><span class="sxs-lookup"><span data-stu-id="753b3-248">**OR**</span></span> <br/> <span data-ttu-id="753b3-249">使用主连接，如果出现故障，则连接到辅助服务器</span><span class="sxs-lookup"><span data-stu-id="753b3-249">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="753b3-250">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-250">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-251">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-251">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-252">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-252">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-253">Lyncdiscoverinternal.contoso.com别名Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-253">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-254">Lyncdiscoverinternal.contoso.com别名Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-254">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-255">池之间的循环</span><span class="sxs-lookup"><span data-stu-id="753b3-255">Round Robin between pools</span></span>  <br/> <span data-ttu-id="753b3-256">**或**</span><span class="sxs-lookup"><span data-stu-id="753b3-256">**OR**</span></span> <br/> <span data-ttu-id="753b3-257">使用主连接，如果出现故障，则连接到辅助服务器</span><span class="sxs-lookup"><span data-stu-id="753b3-257">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="753b3-258">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-258">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-259">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-259">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-260">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-260">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-261">Lyncdiscover.contoso.com别名Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-261">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-262">Lyncdiscover.contoso.com别名Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-262">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-263">池之间的循环</span><span class="sxs-lookup"><span data-stu-id="753b3-263">Round Robin between pools</span></span>  <br/> <span data-ttu-id="753b3-264">**或**</span><span class="sxs-lookup"><span data-stu-id="753b3-264">**OR**</span></span> <br/> <span data-ttu-id="753b3-265">使用主连接，如果出现故障，则连接到辅助服务器</span><span class="sxs-lookup"><span data-stu-id="753b3-265">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="753b3-266">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-266">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-267">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-267">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-268">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-268">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-269">Scheduler.contoso.com别名Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-269">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-270">Scheduler.contoso.com别名Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-270">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-271">池之间的循环</span><span class="sxs-lookup"><span data-stu-id="753b3-271">Round Robin between pools</span></span>  <br/> <span data-ttu-id="753b3-272">**或**</span><span class="sxs-lookup"><span data-stu-id="753b3-272">**OR**</span></span> <br/> <span data-ttu-id="753b3-273">使用主连接，如果出现故障，则连接到辅助服务器</span><span class="sxs-lookup"><span data-stu-id="753b3-273">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="753b3-274">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-274">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-275">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-275">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-276">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-276">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-277">Scheduler.contoso.com别名Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-277">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="753b3-278">Scheduler.contoso.com别名Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-278">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-279">池之间的循环</span><span class="sxs-lookup"><span data-stu-id="753b3-279">Round Robin between pools</span></span>  <br/> <span data-ttu-id="753b3-280">**或**</span><span class="sxs-lookup"><span data-stu-id="753b3-280">**OR**</span></span> <br/> <span data-ttu-id="753b3-281">使用主连接，如果出现故障，则连接到辅助服务器</span><span class="sxs-lookup"><span data-stu-id="753b3-281">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="753b3-282">DNS load balancing － DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="753b3-282">DNS load balancing</span></span>
<span data-ttu-id="753b3-283"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="753b3-283"><a name="DNSLB"> </a></span></span>

<span data-ttu-id="753b3-284">DNS 负载平衡通常在应用程序级别实现。</span><span class="sxs-lookup"><span data-stu-id="753b3-284">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="753b3-285">应用程序 (例如，运行 Skype for Business) 的客户端，如果对池 FQDN 使用) 记录查询，则通过连接到从 DNS A 和 AAAA (返回的 IP 地址之一来尝试连接到池中的服务器。</span><span class="sxs-lookup"><span data-stu-id="753b3-285">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="753b3-286">例如，如果名为 pool01.contoso.com 的池中有三台前端服务器，则会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="753b3-286">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="753b3-287">运行 Skype for Business 的客户端查询 DNS pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="753b3-287">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="753b3-288">查询将返回三个 IP 地址，并按以下 (顺序缓存它们) ：</span><span class="sxs-lookup"><span data-stu-id="753b3-288">The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="753b3-289">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-289">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-290">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="753b3-290">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="753b3-291">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-291">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-292">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="753b3-292">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="753b3-293">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="753b3-293">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="753b3-294">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="753b3-294">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="753b3-295">客户端尝试建立到其中一个 IP 地址的 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="753b3-295">The client tries to establish a TCP connection to one of the IP addresses.</span></span> <span data-ttu-id="753b3-296">如果失败，它将尝试从该列表缓存下一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="753b3-296">If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="753b3-297">如果 TCP 连接成功，客户端将协商 TLS 以连接到主注册器pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="753b3-297">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="753b3-298">如果客户端在未成功连接的情况下尝试所有缓存条目，则用户将收到一条通知，指出当前没有运行 Skype for Business Server 的服务器可用。</span><span class="sxs-lookup"><span data-stu-id="753b3-298">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="753b3-299">基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR) ，DNS RR) 通常通过依赖 DNS 为池中的服务器提供不同的 IP 地址顺序来引用负载平衡。</span><span class="sxs-lookup"><span data-stu-id="753b3-299">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool.</span></span> <span data-ttu-id="753b3-300">通常，DNS RR 支持负载分布，但不允许您启用故障转移。</span><span class="sxs-lookup"><span data-stu-id="753b3-300">Typically, DNS RR enables load distribution, but it won't allow you to enable failover.</span></span> <span data-ttu-id="753b3-301">例如，如果与在 IPv6 方案中由 DNS A (或 AAAA 返回的一个 IP 地址的连接失败) 该连接将失败。</span><span class="sxs-lookup"><span data-stu-id="753b3-301">For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail.</span></span> <span data-ttu-id="753b3-302">这使得 DNS RR 的可靠性低于基于 DNS 的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="753b3-302">That makes DNS RR less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="753b3-303">如果需要，您仍可以将 DNS RR 与基于 DNS 的负载平衡结合使用。</span><span class="sxs-lookup"><span data-stu-id="753b3-303">You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="753b3-304">DNS 负载平衡用于：</span><span class="sxs-lookup"><span data-stu-id="753b3-304">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="753b3-305">将服务器到服务器 SIP 负载平衡到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="753b3-305">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="753b3-306">负载平衡统一通信应用程序服务 (作为 还) 应用程序，如会议自动助理、响应组和呼叫呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="753b3-306">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="753b3-307">阻止与 一些 (应用程序的新连接，也称为排出) 。</span><span class="sxs-lookup"><span data-stu-id="753b3-307">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="753b3-308">负载平衡客户端和边缘服务器之间的所有客户端到服务器流量。</span><span class="sxs-lookup"><span data-stu-id="753b3-308">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="753b3-309">DNS 负载平衡不能用于：</span><span class="sxs-lookup"><span data-stu-id="753b3-309">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="753b3-310">到前端服务器或控制器的客户端到服务器 Web 流量。</span><span class="sxs-lookup"><span data-stu-id="753b3-310">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="753b3-311">为了进一步深入了解查询返回多组 DNS 记录时如何选择 DNS SRV 记录，访问边缘服务始终选取数字优先级最低的记录，如果需要分线，则选择数字权重最高的记录。</span><span class="sxs-lookup"><span data-stu-id="753b3-311">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="753b3-312">这与 [Internet 工程任务组文档一致](https://www.ietf.org/rfc/rfc2782.txt)。</span><span class="sxs-lookup"><span data-stu-id="753b3-312">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="753b3-313">因此，例如，如果第一条 DNS SRV 记录的权重为 20，优先级为 40，而第二条 DNS SRV 记录的权重为 10，优先级为 50，则选择第一条记录，因为它的优先级较低，为 40。</span><span class="sxs-lookup"><span data-stu-id="753b3-313">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40.</span></span> <span data-ttu-id="753b3-314">优先级始终优先，这是客户端首先面向的主机。</span><span class="sxs-lookup"><span data-stu-id="753b3-314">Priority always goes first, and that's the host that a client will target first.</span></span> <span data-ttu-id="753b3-315">如果存在两个优先级相同的目标，如何？</span><span class="sxs-lookup"><span data-stu-id="753b3-315">What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="753b3-316">在这种情况下，需要考虑权重。</span><span class="sxs-lookup"><span data-stu-id="753b3-316">In that case, weight comes into consideration.</span></span> <span data-ttu-id="753b3-317">在这种情况下，应给较大的权重赋予较高的选择概率。</span><span class="sxs-lookup"><span data-stu-id="753b3-317">Larger weights should be given a high probability, in this circumstance, of being selected.</span></span> <span data-ttu-id="753b3-318">当没有任何服务器选择时，DNS 管理员应使用权重 0。</span><span class="sxs-lookup"><span data-stu-id="753b3-318">DNS administrators should use weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="753b3-319">当存在权重大于 0 的记录时，权重为 0 的记录被选中的可能性很小。</span><span class="sxs-lookup"><span data-stu-id="753b3-319">In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="753b3-320">那么，如果返回的 DNS SRV 记录优先级和权重相等，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="753b3-320">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="753b3-321">在这种情况下，访问边缘服务将选择它首先从 DNS 服务器获取的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="753b3-321">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

