---
title: DNS 基础
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有可提供 DNS 服务的内置软件，因此您可能需要查看可用的文档，如 DNS 策略方案指南。 如果需要，可以选择第三方解决方案。
ms.openlocfilehash: dc60bab84220cad306deee408a6a09fc16df5a10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825582"
---
# <a name="dns-basics"></a><span data-ttu-id="7f7cd-104">DNS 基础</span><span class="sxs-lookup"><span data-stu-id="7f7cd-104">DNS basics</span></span>
 
<span data-ttu-id="7f7cd-105">Windows Server 2016 具有可提供 DNS 服务的内置软件，因此您可能需要查看可用的文档，如 [DNS 策略方案指南](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-105">Windows Server 2016 has built-in software that can provide DNS services, so you may want to review the available documentation such as the [DNS Policy Scenario Guide](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide).</span></span> <span data-ttu-id="7f7cd-106">如果需要，可以选择第三方解决方案。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-106">You can choose a third-party solution if you prefer.</span></span>
  
<span data-ttu-id="7f7cd-107">建议最佳做法是，在你的实现中专门使用特定服务器来提供 DNS。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-107">We recommend that as a best practice you dedicate a specific server in your implementation to provide DNS.</span></span> <span data-ttu-id="7f7cd-108">你可能在专用于其中一个 Skype for Business 服务器角色的服务器上设置它，但如果该服务器也是池的一部分并且因意外的 Skype for Business 停用，那么在重新建立 DNS 服务之前，Skype for Business 将发生故障。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-108">You could potentially set it up on one of the servers dedicated to one of the Skype for Business server roles, but if that server was also part of a pool and got decommissioned by accident Skype for Business would malfunction until DNS services were re-established.</span></span>
  
## <a name="dns-records"></a><span data-ttu-id="7f7cd-109">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="7f7cd-109">DNS Records</span></span>

<span data-ttu-id="7f7cd-110">名称到 IP 地址的每个 (可以是 IPv4 或 IPv6 地址) 存储在 DNS 服务器的 DNS 记录中。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-110">Each mapping of a name to an IP address (and that could be an IPv4 or IPv6 address) is stored in a DNS record on the DNS server.</span></span> <span data-ttu-id="7f7cd-111">该名称在 DNS 报告中专门描述为 FQDN— 一个完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-111">The name is described in the DNS Report specifically as an FQDN — a Fully Qualified Domain Name.</span></span> <span data-ttu-id="7f7cd-112">虽然 *contoso.com* 域名，但它是 *\* .contoso.com* 的简写，因此不明确，可能指域中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-112">While  *contoso.com*  is a valid domain name, it's shorthand for *\*.contoso.com*  , so it's ambiguous and could possibly refer to any server in the domain.</span></span> <span data-ttu-id="7f7cd-113">引用域中的单台服务器的 FQDN 示例可能 **meeting01.contoso.com。**</span><span class="sxs-lookup"><span data-stu-id="7f7cd-113">An example of an FQDN that would refer to a single server in your domain might be **meeting01.contoso.com**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7f7cd-114">默认情况下，未加入域的计算机的计算机名称是主机名，而不是 FQDN (完全限定) 。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-114">By default the computer name of a computer that is not joined to a domain is a host name, and not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="7f7cd-115">拓扑生成器使用 FQDN，而不是主机名。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-115">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="7f7cd-116">因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="7f7cd-117">向运行 Skype for Business **Server** 的服务器 (FQDN 时，请仅使用标准字符) 包括 A-Z、a-z、0-9 和连字符。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-117">**Use only standard characters** (including A-Z, a-z, 0-9, and hyphens) when assigning FQDNs to your servers running Skype for Business Server.</span></span> <span data-ttu-id="7f7cd-118">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="7f7cd-119">外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>
  
<span data-ttu-id="7f7cd-120">除了 IP 地址之外，FQDN 还可以映射到 **VIP—** 一个虚拟 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-120">In addition to an IP address, the FQDN could map to a **VIP** — A virtual IP address.</span></span> <span data-ttu-id="7f7cd-121">VIP 是一个与实际物理网络接口不对应的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-121">A VIP is an IP address that doesn't correspond to an actual physical network interface.</span></span> <span data-ttu-id="7f7cd-122">VIP 通常指向执行服务器角色的服务器池，或指向配置为冗余和容错的一对服务器。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-122">A VIP often points to a pool of servers performing a server role, or to a pair of servers configured for redundancy and fault-tolerance.</span></span>
  
<span data-ttu-id="7f7cd-123">有几种 DNS 记录类型，与此讨论最相关的记录有：</span><span class="sxs-lookup"><span data-stu-id="7f7cd-123">There are several types of DNS record, the ones that are most relevant to this discussion are:</span></span> 
  
- <span data-ttu-id="7f7cd-124">**A** — 地址记录或主机记录，返回 32 位 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-124">**A** — an Address record or Host record, Returns a 32-bit IPv4 address.</span></span> <span data-ttu-id="7f7cd-125">最常用于将主机名映射到主机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-125">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="7f7cd-126">**AAAA** — IPv6 地址记录。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-126">**AAAA** — an IPv6 address record.</span></span> <span data-ttu-id="7f7cd-127">返回 128 位 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-127">Returns a 128-bit IPv6 address.</span></span> <span data-ttu-id="7f7cd-128">最常用于将主机名映射到主机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-128">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="7f7cd-129">**CNAME** — 规范名称记录。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-129">**CNAME** — a Canonical name record.</span></span> <span data-ttu-id="7f7cd-130">这会将一个名称解析为另一个名称：DNS 查找将重试具有新名称的查找。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-130">This resolves one name to another: the DNS lookup will retry the lookup with the new name.</span></span>
    
- <span data-ttu-id="7f7cd-131">**SRV** - SRV 记录 (SRV 记录) 指定在 (端口和 IP 组合上访问) 服务器上进程的服务记录。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-131">**SRV** — a Service record (SRV record) specifies a service (a process on a server) that is accessed on a specific port and IP combination.</span></span> <span data-ttu-id="7f7cd-132">需要服务记录的服务的名称是固定的，除了使它们成为 SIP 域的一部分之外，无法自定义它们。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-132">The names of services requiring a service record are fixed, and can't be customized beyond making them part of your SIP domain.</span></span> <span data-ttu-id="7f7cd-133">某些用户服务使用简单 URL。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-133">Some user services use Simple URLs.</span></span> <span data-ttu-id="7f7cd-134">SRV 记录必须指向同一 SIP 域中的位置，因此，如果有多个域，则给定服务需要多个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-134">An SRV record must point to a location in the same SIP domain, so if you have multiple domains you'll need multiple SRV records for a given service.</span></span>
    
## <a name="how-to-choose-a-sip-domain-name"></a><span data-ttu-id="7f7cd-135">如何选择 SIP 域名</span><span class="sxs-lookup"><span data-stu-id="7f7cd-135">How to choose a SIP domain name</span></span>
<span data-ttu-id="7f7cd-136"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="7f7cd-136"><a name="BK_NameSIP"> </a></span></span>

<span data-ttu-id="7f7cd-137">组织的 SIP 域名通常与向用户提供的电子邮件地址一致。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-137">An organization's SIP domain name usually aligns with the email addresses given to its users.</span></span> <span data-ttu-id="7f7cd-138">如果贵组织的用户具有类似 Brown@contoso.com 的电子邮件地址，则使用 contoso.com 域名的组织的首选只是 \<sip-domain\> contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-138">If a user in your organization would have an email address like Brown@contoso.com, the preferred \<sip-domain\> for an organization with the contoso.com domain name is simply contoso.com.</span></span>
  
### <a name="multiple-sip-domains"></a><span data-ttu-id="7f7cd-139">多个 SIP 域</span><span class="sxs-lookup"><span data-stu-id="7f7cd-139">Multiple SIP domains</span></span>

 <span data-ttu-id="7f7cd-140">在某些情况下，您的组织可能需要多个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-140">Your organization might in some cases need several SIP domains.</span></span> <span data-ttu-id="7f7cd-141">例如，如果Fabrikam.com用户contoso.com，可能需要创建 Skype for Business Server 识别并接受其连接的新 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-141">As an example, if Fabrikam.com was acquired by contoso.com, you might need to create a new SIP domain that Skype for Business Server recognizes and will accept connection from.</span></span> <span data-ttu-id="7f7cd-142">当您这样做时，您需要创建一组使用 contoso.com 的其他所有 DNS 记录，其中显示 Fabrikam 请求的发送位置的新 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-142">When you do this, you'd need to create an additional set of all the DNS records that use contoso.com, with new FQDNs that show where to send requests for Fabrikam.</span></span>
  
## <a name="dns-load-balancing"></a><span data-ttu-id="7f7cd-143">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="7f7cd-143">DNS Load Balancing</span></span>
<span data-ttu-id="7f7cd-144"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="7f7cd-144"><a name="BK_NameSIP"> </a></span></span>

<span data-ttu-id="7f7cd-145">您可以使用 DNS 在设置为服务器池的几个服务器之间共享流量负载。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-145">You can use DNS to share traffic load among several servers that are set up as a server pool.</span></span> <span data-ttu-id="7f7cd-146">为此，您需要为池的 FQDN 创建多个 A 记录，每条记录都指向池中节点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-146">To do this, you would create several A records for the pool's FQDN, each of which points to the IP address of a node in the pool.</span></span>
  
<span data-ttu-id="7f7cd-147">有关 [负载平衡的其他](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) 讨论，请参阅 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7f7cd-147">See [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) for additional discussions of load balancing.</span></span>
  

