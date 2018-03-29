---
title: DNS 基础知识
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows 服务器 2016年有内置软件，可以提供 DNS 服务，因此您可能想要查看可用的文档，如 DNS 策略方案指南。 如果您愿意，您可以选择第三方解决方案。
ms.openlocfilehash: df6a693c50b3ca8b61baf0e47e0d019478f3cbf9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="dns-basics"></a><span data-ttu-id="54e56-104">DNS 基础知识</span><span class="sxs-lookup"><span data-stu-id="54e56-104">DNS basics</span></span>
 
<span data-ttu-id="54e56-105">Windows 服务器 2016年有内置软件，可以提供 DNS 服务，因此您可能想要查看可用的文档，如[DNS 策略方案指南](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/dns-policy-scenario-guide)。</span><span class="sxs-lookup"><span data-stu-id="54e56-105">Windows Server 2016 has built-in software that can provide DNS services, so you may want to review the available documentation such as the [DNS Policy Scenario Guide](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/dns-policy-scenario-guide).</span></span> <span data-ttu-id="54e56-106">如果您愿意，您可以选择第三方解决方案。</span><span class="sxs-lookup"><span data-stu-id="54e56-106">You can choose a third-party solution if you prefer.</span></span>
  
<span data-ttu-id="54e56-107">我们建议最好将专用特定服务器以提供 DNS 实现中。</span><span class="sxs-lookup"><span data-stu-id="54e56-107">We recommend that as a best practice you dedicate a specific server in your implementation to provide DNS.</span></span> <span data-ttu-id="54e56-108">您可能有可能将其设置一个专用于一个业务服务器角色，但如果该服务器也是池的一部分，对于业务将出现故障之前 DNS 服务已重新建立了退役无意 Skype Skype 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="54e56-108">You could potentially set it up on one of the servers dedicated to one of the Skype for Business server roles, but if that server was also part of a pool and got decommissioned by accident Skype for Business would malfunction until DNS services were re-established.</span></span>
  
## <a name="dns-records"></a><span data-ttu-id="54e56-109">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="54e56-109">DNS Records</span></span>

<span data-ttu-id="54e56-110">每个映射到 IP 地址的名称 （和可能就在 IPv4 或 IPv6 地址） 存储在 DNS 服务器上的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="54e56-110">Each mapping of a name to an IP address (and that could be an IPv4 or IPv6 address) is stored in a DNS record on the DNS server.</span></span> <span data-ttu-id="54e56-111">名称所述专门作为 FQDN 的 DNS 报表 — — 完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="54e56-111">The name is described in the DNS Report specifically as an FQDN — a Fully Qualified Domain Name.</span></span> <span data-ttu-id="54e56-112">虽然*contoso.com*是一个有效的域名，但它是简写形式*\*。 contoso.com* ，因此，它不明确，可能就可以查阅到域中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="54e56-112">While  *contoso.com*  is a valid domain name, it's shorthand for *\*.contoso.com*  , so it's ambiguous and could possibly refer to any server in the domain.</span></span> <span data-ttu-id="54e56-113">将参考您域中的单个服务器的 FQDN 的示例可能是**meeting01.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="54e56-113">An example of an FQDN that would refer to a single server in your domain might be **meeting01.contoso.com**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="54e56-114">默认情况下，未加入域的计算机的计算机名称是主机名称，而不是完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="54e56-114">By default the computer name of a computer that is not joined to a domain is a host name, and not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="54e56-115">拓扑生成器使用 Fqdn，而不是主机名。</span><span class="sxs-lookup"><span data-stu-id="54e56-115">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="54e56-116">因此，必须在要部署为未加入域的边缘服务器的计算机名称上配置 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="54e56-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="54e56-117">**使用仅标准字符**（包括 A-Z、 a-z、 0-9 和连字符） 时分配给运行 Skype 业务服务器的服务器的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="54e56-117">**Use only standard characters** (including A-Z, a-z, 0-9, and hyphens) when assigning FQDNs to your servers running Skype for Business Server.</span></span> <span data-ttu-id="54e56-118">不要使用 Unicode 字符或下划线字符。</span><span class="sxs-lookup"><span data-stu-id="54e56-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="54e56-119">外部 DNS 和公共 CA 通常不支持在 FQDN 中使用非标准字符（当必须向证书中的 SN 分配 FQDN 时）。</span><span class="sxs-lookup"><span data-stu-id="54e56-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>
  
<span data-ttu-id="54e56-120">除了 IP 地址，FQDN 可以映射到**VIP** — — 一个虚拟 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="54e56-120">In addition to an IP address, the FQDN could map to a **VIP** — A virtual IP address.</span></span> <span data-ttu-id="54e56-121">VIP 是不对应于实际物理网络接口的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="54e56-121">A VIP is an IP address that doesn't correspond to an actual physical network interface.</span></span> <span data-ttu-id="54e56-122">VIP 通常点到池中的服务器执行服务器角色，或对服务器配置的冗余和容错能力。</span><span class="sxs-lookup"><span data-stu-id="54e56-122">A VIP often points to a pool of servers performing a server role, or to a pair of servers configured for redundancy and fault-tolerance.</span></span>
  
<span data-ttu-id="54e56-123">有几种类型的 DNS 记录，在此讨论最相关的那些：</span><span class="sxs-lookup"><span data-stu-id="54e56-123">There are several types of DNS record, the ones that are most relevant to this discussion are:</span></span> 
  
- <span data-ttu-id="54e56-124">**A** — 地址记录或主机记录返回 32 位 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="54e56-124">**A** — an Address record or Host record, Returns a 32-bit IPv4 address.</span></span> <span data-ttu-id="54e56-125">通常用于将主机名映射到 IP 地址的主机。</span><span class="sxs-lookup"><span data-stu-id="54e56-125">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="54e56-126">**AAAA** — IPv6 地址记录。</span><span class="sxs-lookup"><span data-stu-id="54e56-126">**AAAA** — an IPv6 address record.</span></span> <span data-ttu-id="54e56-127">返回一个 128 位的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="54e56-127">Returns a 128-bit IPv6 address.</span></span> <span data-ttu-id="54e56-128">通常用于将主机名映射到 IP 地址的主机。</span><span class="sxs-lookup"><span data-stu-id="54e56-128">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="54e56-129">**CNAME** — 规范名称记录。</span><span class="sxs-lookup"><span data-stu-id="54e56-129">**CNAME** — a Canonical name record.</span></span> <span data-ttu-id="54e56-130">这到另一个解析一个名称： DNS 查找将重试以新名称查找。</span><span class="sxs-lookup"><span data-stu-id="54e56-130">This resolves one name to another: the DNS lookup will retry the lookup with the new name.</span></span>
    
- <span data-ttu-id="54e56-131">**SRV** — 服务记录 （SRV 记录） 指定访问特定的端口和 IP 组合的服务 （在服务器上的进程）。</span><span class="sxs-lookup"><span data-stu-id="54e56-131">**SRV** — a Service record (SRV record) specifies a service (a process on a server) that is accessed on a specific port and IP combination.</span></span> <span data-ttu-id="54e56-132">要求服务记录的服务的名称固定的并不能自定义之外，使它们成为您的 SIP 域的一部分。</span><span class="sxs-lookup"><span data-stu-id="54e56-132">The names of services requiring a service record are fixed, and can't be customized beyond making them part of your SIP domain.</span></span> <span data-ttu-id="54e56-133">一些用户服务使用简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="54e56-133">Some user services use Simple URLs.</span></span> <span data-ttu-id="54e56-134">因此，如果您有多个域需要多个 SRV 记录给定服务的 SRV 记录必须指向相同的 SIP 域中的某个位置。</span><span class="sxs-lookup"><span data-stu-id="54e56-134">An SRV record must point to a location in the same SIP domain, so if you have multiple domains you'll need multiple SRV records for a given service.</span></span>
    
## <a name="how-to-choose-a-sip-domain-name"></a><span data-ttu-id="54e56-135">如何选择一个 SIP 域的名称</span><span class="sxs-lookup"><span data-stu-id="54e56-135">How to choose a SIP domain name</span></span>
<span data-ttu-id="54e56-136"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="54e56-136"></span></span>

<span data-ttu-id="54e56-137">组织的 SIP 域的名称通常与提供给其用户的电子邮件地址相符。</span><span class="sxs-lookup"><span data-stu-id="54e56-137">An organization's SIP domain name usually aligns with the email addresses given to its users.</span></span> <span data-ttu-id="54e56-138">如果您的组织中的用户将具有类似 Brown@contoso.com，首选电子邮件地址\<sip 域\>contoso.com 域的组织名称是简单 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="54e56-138">If a user in your organization would have an email address like Brown@contoso.com, the preferred \<sip-domain\> for an organization with the contoso.com domain name is simply contoso.com.</span></span>
  
### <a name="multiple-sip-domains"></a><span data-ttu-id="54e56-139">多个 SIP 域</span><span class="sxs-lookup"><span data-stu-id="54e56-139">Multiple SIP domains</span></span>

 <span data-ttu-id="54e56-140">您的组织在某些情况下可能需要多个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="54e56-140">Your organization might in some cases need several SIP domains.</span></span> <span data-ttu-id="54e56-141">举一个例子，如果 Fabrikam.com 获取 contoso.com，您可能需要创建一个新的 SIP 域，Skype 业务服务器识别并将接受连接。</span><span class="sxs-lookup"><span data-stu-id="54e56-141">As an example, if Fabrikam.com was acquired by contoso.com, you might need to create a new SIP domain that Skype for Business Server recognizes and will accept connection from.</span></span> <span data-ttu-id="54e56-142">当您执行此操作时，您需要创建一组额外的 contoso.com，使用显示的发送请求的位置的新 Fqdn 的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="54e56-142">When you do this, you'd need to create an additional set of all the DNS records that use contoso.com, with new FQDNs that show where to send requests for Fabrikam.</span></span>
  
## <a name="dns-load-balancing"></a><span data-ttu-id="54e56-143">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="54e56-143">DNS Load Balancing</span></span>
<span data-ttu-id="54e56-144"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="54e56-144"></span></span>

<span data-ttu-id="54e56-145">您可以使用 DNS 来共享设置为服务器池的多个服务器之间的通信负载。</span><span class="sxs-lookup"><span data-stu-id="54e56-145">You can use DNS to share traffic load among several servers that are set up as a server pool.</span></span> <span data-ttu-id="54e56-146">为了做到这一点，您需要创建几个 A 记录为该池的 FQDN，其中的每个点到池中的节点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="54e56-146">To do this, you would create several A records for the pool's FQDN, each of which points to the IP address of a node in the pool.</span></span>
  
<span data-ttu-id="54e56-147">有关负载平衡的详细讨论，请参阅[DNS 负载平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)。</span><span class="sxs-lookup"><span data-stu-id="54e56-147">See [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) for additional discussions of load balancing.</span></span>
  

