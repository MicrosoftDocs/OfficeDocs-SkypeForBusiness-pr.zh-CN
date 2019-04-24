---
title: DNS 基础知识
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有内置可以提供 DNS 服务，因此您可能想要查看可用的文档，如 DNS 策略方案指南的软件。 如果您愿意，您可以选择第三方解决方案。
ms.openlocfilehash: 2ba20c6aabd296f13ea5e84053d140123097f114
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213891"
---
# <a name="dns-basics"></a><span data-ttu-id="ec383-104">DNS 基础知识</span><span class="sxs-lookup"><span data-stu-id="ec383-104">DNS basics</span></span>
 
<span data-ttu-id="ec383-105">Windows Server 2016 具有内置可以提供 DNS 服务，因此您可能想要查看可用的文档，如[DNS 策略方案指南](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)的软件。</span><span class="sxs-lookup"><span data-stu-id="ec383-105">Windows Server 2016 has built-in software that can provide DNS services, so you may want to review the available documentation such as the [DNS Policy Scenario Guide](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide).</span></span> <span data-ttu-id="ec383-106">如果您愿意，您可以选择第三方解决方案。</span><span class="sxs-lookup"><span data-stu-id="ec383-106">You can choose a third-party solution if you prefer.</span></span>
  
<span data-ttu-id="ec383-107">建议的最佳做法是将专用特定服务器实现提供 DNS 中。</span><span class="sxs-lookup"><span data-stu-id="ec383-107">We recommend that as a best practice you dedicate a specific server in your implementation to provide DNS.</span></span> <span data-ttu-id="ec383-108">您无法可能将其设置在一台服务器专用于业务服务器角色，但如果该服务器也是池的一部分，并获得停用无意 Skype 的业务会出现故障，直到 DNS 服务已重新建立 Skype 之一。</span><span class="sxs-lookup"><span data-stu-id="ec383-108">You could potentially set it up on one of the servers dedicated to one of the Skype for Business server roles, but if that server was also part of a pool and got decommissioned by accident Skype for Business would malfunction until DNS services were re-established.</span></span>
  
## <a name="dns-records"></a><span data-ttu-id="ec383-109">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="ec383-109">DNS Records</span></span>

<span data-ttu-id="ec383-110">每个映射的 IP 地址的名称 （和可能的 IPv4 或 IPv6 地址） 存储在 DNS 服务器上的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="ec383-110">Each mapping of a name to an IP address (and that could be an IPv4 or IPv6 address) is stored in a DNS record on the DNS server.</span></span> <span data-ttu-id="ec383-111">名称所述明确标注为 FQDN DNS 报告 — 完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="ec383-111">The name is described in the DNS Report specifically as an FQDN — a Fully Qualified Domain Name.</span></span> <span data-ttu-id="ec383-112">一个有效域名*contoso.com*时，它是简写*\*。 contoso.com* ，因此它不明确而无法可能引用域中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="ec383-112">While  *contoso.com*  is a valid domain name, it's shorthand for *\*.contoso.com*  , so it's ambiguous and could possibly refer to any server in the domain.</span></span> <span data-ttu-id="ec383-113">将引用您的域中的单个服务器的 FQDN 的示例可能**meeting01.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="ec383-113">An example of an FQDN that would refer to a single server in your domain might be **meeting01.contoso.com**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ec383-114">默认情况下，未加入域的计算机的计算机名称是主机名称，而不是完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ec383-114">By default the computer name of a computer that is not joined to a domain is a host name, and not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="ec383-115">拓扑生成器使用 Fqdn，而不是主机名称。</span><span class="sxs-lookup"><span data-stu-id="ec383-115">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="ec383-116">因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="ec383-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="ec383-117">**使用仅标准字符**（包括 A-Z、 a-z、 0-9 和连字符） 时分配到您的业务服务器运行 Skype 的服务器的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="ec383-117">**Use only standard characters** (including A-Z, a-z, 0-9, and hyphens) when assigning FQDNs to your servers running Skype for Business Server.</span></span> <span data-ttu-id="ec383-118">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="ec383-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="ec383-119">外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。</span><span class="sxs-lookup"><span data-stu-id="ec383-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>
  
<span data-ttu-id="ec383-120">除了 IP 地址、 FQDN 可以映射到**VIP** — 一个虚拟 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ec383-120">In addition to an IP address, the FQDN could map to a **VIP** — A virtual IP address.</span></span> <span data-ttu-id="ec383-121">VIP 是不对应于实际的物理网络接口的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ec383-121">A VIP is an IP address that doesn't correspond to an actual physical network interface.</span></span> <span data-ttu-id="ec383-122">VIP 通常指向池服务器执行服务器角色，或指向一对的服务器配置为冗余和容错能力。</span><span class="sxs-lookup"><span data-stu-id="ec383-122">A VIP often points to a pool of servers performing a server role, or to a pair of servers configured for redundancy and fault-tolerance.</span></span>
  
<span data-ttu-id="ec383-123">有几种类型的 DNS 记录，此次讨论中与最相关的那些是：</span><span class="sxs-lookup"><span data-stu-id="ec383-123">There are several types of DNS record, the ones that are most relevant to this discussion are:</span></span> 
  
- <span data-ttu-id="ec383-124">**A** -地址记录或主机记录返回 32 位 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="ec383-124">**A** — an Address record or Host record, Returns a 32-bit IPv4 address.</span></span> <span data-ttu-id="ec383-125">最常用于映射到主机的 IP 地址的主机名。</span><span class="sxs-lookup"><span data-stu-id="ec383-125">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="ec383-126">**AAAA** — IPv6 地址记录。</span><span class="sxs-lookup"><span data-stu-id="ec383-126">**AAAA** — an IPv6 address record.</span></span> <span data-ttu-id="ec383-127">返回一个 128 位 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="ec383-127">Returns a 128-bit IPv6 address.</span></span> <span data-ttu-id="ec383-128">最常用于映射到主机的 IP 地址的主机名。</span><span class="sxs-lookup"><span data-stu-id="ec383-128">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="ec383-129">**CNAME** — 规范名称记录。</span><span class="sxs-lookup"><span data-stu-id="ec383-129">**CNAME** — a Canonical name record.</span></span> <span data-ttu-id="ec383-130">这解析到另一个名称： DNS 查找将重试查找使用新名称。</span><span class="sxs-lookup"><span data-stu-id="ec383-130">This resolves one name to another: the DNS lookup will retry the lookup with the new name.</span></span>
    
- <span data-ttu-id="ec383-131">**SRV** -服务记录 （SRV 记录） 指定访问特定端口和 IP 组合的服务 （此过程的服务器上）。</span><span class="sxs-lookup"><span data-stu-id="ec383-131">**SRV** — a Service record (SRV record) specifies a service (a process on a server) that is accessed on a specific port and IP combination.</span></span> <span data-ttu-id="ec383-132">需要服务记录的服务的名称固定的而且不能超出进行自定义您的 SIP 域的一部分。</span><span class="sxs-lookup"><span data-stu-id="ec383-132">The names of services requiring a service record are fixed, and can't be customized beyond making them part of your SIP domain.</span></span> <span data-ttu-id="ec383-133">某些用户服务使用简单 Url。</span><span class="sxs-lookup"><span data-stu-id="ec383-133">Some user services use Simple URLs.</span></span> <span data-ttu-id="ec383-134">如果您有多个域的给定的服务，您将需要多个 SRV 记录以便 SRV 记录必须指向中的相同的 SIP 域的位置。</span><span class="sxs-lookup"><span data-stu-id="ec383-134">An SRV record must point to a location in the same SIP domain, so if you have multiple domains you'll need multiple SRV records for a given service.</span></span>
    
## <a name="how-to-choose-a-sip-domain-name"></a><span data-ttu-id="ec383-135">如何选择 SIP 域名称</span><span class="sxs-lookup"><span data-stu-id="ec383-135">How to choose a SIP domain name</span></span>
<span data-ttu-id="ec383-136"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="ec383-136"></span></span>

<span data-ttu-id="ec383-137">组织的 SIP 域名通常与分配给用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ec383-137">An organization's SIP domain name usually aligns with the email addresses given to its users.</span></span> <span data-ttu-id="ec383-138">如果您的组织中用户应具有类似 Brown@contoso.com，首选的电子邮件地址\<sip 域\>具有 contoso.com 域的组织的名称是只需 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="ec383-138">If a user in your organization would have an email address like Brown@contoso.com, the preferred \<sip-domain\> for an organization with the contoso.com domain name is simply contoso.com.</span></span>
  
### <a name="multiple-sip-domains"></a><span data-ttu-id="ec383-139">多个 SIP 域</span><span class="sxs-lookup"><span data-stu-id="ec383-139">Multiple SIP domains</span></span>

 <span data-ttu-id="ec383-140">您的组织在某些情况下可能需要多个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="ec383-140">Your organization might in some cases need several SIP domains.</span></span> <span data-ttu-id="ec383-141">例如，如果 Fabrikam.com 被收购的 contoso.com，您可能需要创建一个新的 SIP 域的业务服务器 Skype 识别和将接受来自连接。</span><span class="sxs-lookup"><span data-stu-id="ec383-141">As an example, if Fabrikam.com was acquired by contoso.com, you might need to create a new SIP domain that Skype for Business Server recognizes and will accept connection from.</span></span> <span data-ttu-id="ec383-142">执行此操作，您将需要创建一组额外的 contoso.com，使用新的显示位置以将请求发送的 Fabrikam 的 Fqdn 的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="ec383-142">When you do this, you'd need to create an additional set of all the DNS records that use contoso.com, with new FQDNs that show where to send requests for Fabrikam.</span></span>
  
## <a name="dns-load-balancing"></a><span data-ttu-id="ec383-143">DNS Load Balancing</span><span class="sxs-lookup"><span data-stu-id="ec383-143">DNS Load Balancing</span></span>
<span data-ttu-id="ec383-144"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="ec383-144"></span></span>

<span data-ttu-id="ec383-145">您可以使用 DNS 共享为服务器池设置的多个服务器之间的流量负载。</span><span class="sxs-lookup"><span data-stu-id="ec383-145">You can use DNS to share traffic load among several servers that are set up as a server pool.</span></span> <span data-ttu-id="ec383-146">若要执行此操作，您将创建几个 A 记录的池的 FQDN，其中每个指向池中的节点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ec383-146">To do this, you would create several A records for the pool's FQDN, each of which points to the IP address of a node in the pool.</span></span>
  
<span data-ttu-id="ec383-147">有关负载平衡的详细讨论，请参阅[DNS 负载平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)。</span><span class="sxs-lookup"><span data-stu-id="ec383-147">See [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) for additional discussions of load balancing.</span></span>
  

