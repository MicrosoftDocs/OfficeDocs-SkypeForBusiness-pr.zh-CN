---
title: DNS 基础知识
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有可提供 DNS 服务的内置软件, 因此你可能需要查看 "DNS 策略方案指南" 等可用文档。 如果愿意, 您可以选择第三方解决方案。
ms.openlocfilehash: c1084a756a79ebcf15b8e99eef049690b5dcd9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297272"
---
# <a name="dns-basics"></a><span data-ttu-id="c2528-104">DNS 基础知识</span><span class="sxs-lookup"><span data-stu-id="c2528-104">DNS basics</span></span>
 
<span data-ttu-id="c2528-105">Windows Server 2016 具有可提供 DNS 服务的内置软件, 因此你可能需要查看 " [Dns 策略方案指南](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)" 等可用文档。</span><span class="sxs-lookup"><span data-stu-id="c2528-105">Windows Server 2016 has built-in software that can provide DNS services, so you may want to review the available documentation such as the [DNS Policy Scenario Guide](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide).</span></span> <span data-ttu-id="c2528-106">如果愿意, 您可以选择第三方解决方案。</span><span class="sxs-lookup"><span data-stu-id="c2528-106">You can choose a third-party solution if you prefer.</span></span>
  
<span data-ttu-id="c2528-107">我们建议, 最佳做法是在你的实现中专用特定服务器以提供 DNS。</span><span class="sxs-lookup"><span data-stu-id="c2528-107">We recommend that as a best practice you dedicate a specific server in your implementation to provide DNS.</span></span> <span data-ttu-id="c2528-108">您可能会在专用于其中一个 Skype for Business 服务器角色的服务器之一上设置它, 但如果该服务器也是某个池的一部分, 而在重新建立 DNS 服务之前, 您的 Skype for business 取消授权将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="c2528-108">You could potentially set it up on one of the servers dedicated to one of the Skype for Business server roles, but if that server was also part of a pool and got decommissioned by accident Skype for Business would malfunction until DNS services were re-established.</span></span>
  
## <a name="dns-records"></a><span data-ttu-id="c2528-109">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c2528-109">DNS Records</span></span>

<span data-ttu-id="c2528-110">每个名称到 IP 地址 (也可以是 IPv4 或 IPv6 地址) 的映射都存储在 DNS 服务器上的 DNS 记录中。</span><span class="sxs-lookup"><span data-stu-id="c2528-110">Each mapping of a name to an IP address (and that could be an IPv4 or IPv6 address) is stored in a DNS record on the DNS server.</span></span> <span data-ttu-id="c2528-111">该名称在 DNS 报告中描述为 FQDN (完全限定的域名)。</span><span class="sxs-lookup"><span data-stu-id="c2528-111">The name is described in the DNS Report specifically as an FQDN — a Fully Qualified Domain Name.</span></span> <span data-ttu-id="c2528-112">虽然*contoso.com*是有效的\* \*\* 域名, 但它是 contoso.com 的简写, 因此它不明确, 并且可能会引用域中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="c2528-112">While  *contoso.com*  is a valid domain name, it's shorthand for *\*.contoso.com*  , so it's ambiguous and could possibly refer to any server in the domain.</span></span> <span data-ttu-id="c2528-113">在您的域中引用单个服务器的 FQDN 的示例可能是**meeting01.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="c2528-113">An example of an FQDN that would refer to a single server in your domain might be **meeting01.contoso.com**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c2528-114">默认情况下，未加入域的计算机的计算机名称是主机名称，而不是完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="c2528-114">By default the computer name of a computer that is not joined to a domain is a host name, and not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="c2528-115">拓扑生成器使用 Fqdn, 而不是主机名。</span><span class="sxs-lookup"><span data-stu-id="c2528-115">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="c2528-116">因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="c2528-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="c2528-117">**仅使用标准字符**(包括 A-z、A-z、0-9 和连字符) 在运行 Skype for Business 服务器的服务器上分配 Fqdn 时。</span><span class="sxs-lookup"><span data-stu-id="c2528-117">**Use only standard characters** (including A-Z, a-z, 0-9, and hyphens) when assigning FQDNs to your servers running Skype for Business Server.</span></span> <span data-ttu-id="c2528-118">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="c2528-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="c2528-119">外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。</span><span class="sxs-lookup"><span data-stu-id="c2528-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>
  
<span data-ttu-id="c2528-120">除了 IP 地址, FQDN 还可以映射到**VIP** (虚拟 IP 地址)。</span><span class="sxs-lookup"><span data-stu-id="c2528-120">In addition to an IP address, the FQDN could map to a **VIP** — A virtual IP address.</span></span> <span data-ttu-id="c2528-121">VIP 是不对应于实际物理网络接口的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c2528-121">A VIP is an IP address that doesn't correspond to an actual physical network interface.</span></span> <span data-ttu-id="c2528-122">VIP 通常指向执行服务器角色的服务器池, 或者指向配置为冗余和容错的一对服务器。</span><span class="sxs-lookup"><span data-stu-id="c2528-122">A VIP often points to a pool of servers performing a server role, or to a pair of servers configured for redundancy and fault-tolerance.</span></span>
  
<span data-ttu-id="c2528-123">有多种类型的 DNS 记录, 与本讨论最相关的 DNS 记录包括:</span><span class="sxs-lookup"><span data-stu-id="c2528-123">There are several types of DNS record, the ones that are most relevant to this discussion are:</span></span> 
  
- <span data-ttu-id="c2528-124">**A** -地址记录或主机记录返回32位的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="c2528-124">**A** — an Address record or Host record, Returns a 32-bit IPv4 address.</span></span> <span data-ttu-id="c2528-125">最常用于将主机名映射到主机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c2528-125">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="c2528-126">**AAAA** -IPv6 地址记录。</span><span class="sxs-lookup"><span data-stu-id="c2528-126">**AAAA** — an IPv6 address record.</span></span> <span data-ttu-id="c2528-127">返回128位 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="c2528-127">Returns a 128-bit IPv6 address.</span></span> <span data-ttu-id="c2528-128">最常用于将主机名映射到主机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c2528-128">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="c2528-129">**CNAME** -规范名称记录。</span><span class="sxs-lookup"><span data-stu-id="c2528-129">**CNAME** — a Canonical name record.</span></span> <span data-ttu-id="c2528-130">这会将一个名称解析为另一个名称: DNS 查找将重试具有新名称的查找。</span><span class="sxs-lookup"><span data-stu-id="c2528-130">This resolves one name to another: the DNS lookup will retry the lookup with the new name.</span></span>
    
- <span data-ttu-id="c2528-131">**SRV** —服务记录 (srv 记录) 指定在特定端口和 IP 组合上访问的服务 (服务器上的进程)。</span><span class="sxs-lookup"><span data-stu-id="c2528-131">**SRV** — a Service record (SRV record) specifies a service (a process on a server) that is accessed on a specific port and IP combination.</span></span> <span data-ttu-id="c2528-132">需要服务记录的服务的名称是固定的, 并且不能进行自定义, 而不是使其成为您的 SIP 域的一部分。</span><span class="sxs-lookup"><span data-stu-id="c2528-132">The names of services requiring a service record are fixed, and can't be customized beyond making them part of your SIP domain.</span></span> <span data-ttu-id="c2528-133">某些用户服务使用简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="c2528-133">Some user services use Simple URLs.</span></span> <span data-ttu-id="c2528-134">SRV 记录必须指向同一 SIP 域中的某个位置, 因此如果你有多个域, 则给定服务需要多个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="c2528-134">An SRV record must point to a location in the same SIP domain, so if you have multiple domains you'll need multiple SRV records for a given service.</span></span>
    
## <a name="how-to-choose-a-sip-domain-name"></a><span data-ttu-id="c2528-135">如何选择 SIP 域名</span><span class="sxs-lookup"><span data-stu-id="c2528-135">How to choose a SIP domain name</span></span>
<span data-ttu-id="c2528-136"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="c2528-136"></span></span>

<span data-ttu-id="c2528-137">组织的 SIP 域名通常与为其用户提供的电子邮件地址对齐。</span><span class="sxs-lookup"><span data-stu-id="c2528-137">An organization's SIP domain name usually aligns with the email addresses given to its users.</span></span> <span data-ttu-id="c2528-138">如果组织中的用户具有类似 Brown@contoso.com 的电子邮件地址, 则具有 contoso.com \<域名的组织\>的首选 sip 域只是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c2528-138">If a user in your organization would have an email address like Brown@contoso.com, the preferred \<sip-domain\> for an organization with the contoso.com domain name is simply contoso.com.</span></span>
  
### <a name="multiple-sip-domains"></a><span data-ttu-id="c2528-139">多个 SIP 域</span><span class="sxs-lookup"><span data-stu-id="c2528-139">Multiple SIP domains</span></span>

 <span data-ttu-id="c2528-140">在某些情况下, 您的组织可能需要多个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="c2528-140">Your organization might in some cases need several SIP domains.</span></span> <span data-ttu-id="c2528-141">例如, 如果 contoso.com 获取了 Fabrikam.com, 你可能需要创建一个新的 SIP 域, 以便 Skype for Business 服务器识别并将接受来自的连接。</span><span class="sxs-lookup"><span data-stu-id="c2528-141">As an example, if Fabrikam.com was acquired by contoso.com, you might need to create a new SIP domain that Skype for Business Server recognizes and will accept connection from.</span></span> <span data-ttu-id="c2528-142">执行此操作时, 你需要创建一个使用 contoso.com 的所有 DNS 记录的附加集, 其中显示了在何处发送 Fabrikam 请求的新 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="c2528-142">When you do this, you'd need to create an additional set of all the DNS records that use contoso.com, with new FQDNs that show where to send requests for Fabrikam.</span></span>
  
## <a name="dns-load-balancing"></a><span data-ttu-id="c2528-143">DNS Load Balancing</span><span class="sxs-lookup"><span data-stu-id="c2528-143">DNS Load Balancing</span></span>
<span data-ttu-id="c2528-144"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="c2528-144"></span></span>

<span data-ttu-id="c2528-145">可以使用 DNS 在设置为服务器池的多个服务器之间共享流量负载。</span><span class="sxs-lookup"><span data-stu-id="c2528-145">You can use DNS to share traffic load among several servers that are set up as a server pool.</span></span> <span data-ttu-id="c2528-146">为此, 你将为池的 FQDN 创建几条记录, 每个记录指向池中的一个节点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c2528-146">To do this, you would create several A records for the pool's FQDN, each of which points to the IP address of a node in the pool.</span></span>
  
<span data-ttu-id="c2528-147">有关负载平衡的其他讨论, 请参阅[DNS 负载平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)。</span><span class="sxs-lookup"><span data-stu-id="c2528-147">See [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) for additional discussions of load balancing.</span></span>
  

