---
title: Lync Server 2013：移动性技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac74f7e9e85829e500900e03d4b7cfedf89d1e0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="2bf93-102">Lync Server 2013 中的移动性技术要求</span><span class="sxs-lookup"><span data-stu-id="2bf93-102">Technical requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bf93-103">_**主题上次修改时间:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="2bf93-103">_**Topic Last Modified:** 2014-07-24_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="2bf93-104">移动用户遇到需要特殊规划的各种移动应用方案。</span><span class="sxs-lookup"><span data-stu-id="2bf93-104">Mobile users encounter various mobile application scenarios that require special planning.</span></span> <span data-ttu-id="2bf93-105">例如, 通过3G 网络连接时, 某人可能开始使用移动应用程序, 而不是通过3G 网络连接, 然后在工作时切换到公司 Wi-fi 网络, 然后在离开大楼时切换回3G。</span><span class="sxs-lookup"><span data-stu-id="2bf93-105">For example, someone might start using a mobile application while away from work by connecting through the 3G network, then switch to the corporate Wi-Fi network when arriving at work, and then switch back to 3G when leaving the building.</span></span> <span data-ttu-id="2bf93-106">你需要规划你的环境以支持此类网络转换, 并保证一致的用户体验。</span><span class="sxs-lookup"><span data-stu-id="2bf93-106">You need to plan your environment to support such network transitions and guarantee a consistent user experience.</span></span> <span data-ttu-id="2bf93-107">本部分介绍了为支持移动应用程序和自动发现移动资源而必须具备的基础结构要求。</span><span class="sxs-lookup"><span data-stu-id="2bf93-107">This section describes the infrastructure requirements that you must have in order to support mobile applications and automatic discovery of mobility resources.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2bf93-108">虽然移动应用程序也可以连接到其他 Lync Server 2013 服务, 但需要将所有移动应用程序 web 请求发送到相同的外部 web 完全限定的域名 (FQDN) 才会应用于 Lync Server 2013 移动服务。</span><span class="sxs-lookup"><span data-stu-id="2bf93-108">Although mobile applications can also connect to other Lync Server 2013 services, the requirement to send all mobile application web requests to the same external web fully qualified domain name (FQDN) applies only to the Lync Server 2013 Mobility Service.</span></span> <span data-ttu-id="2bf93-109">其他移动服务不需要此配置。</span><span class="sxs-lookup"><span data-stu-id="2bf93-109">Other mobility services do not require this configuration.</span></span>



</div>

<span data-ttu-id="2bf93-110">硬件负载平衡器中的 cookie 相关性要求大大减少, 如果你使用的是使用 Lync Server 2013 发送的 Lync Mobile, 则替换传输控制协议 (TCP) 关系。</span><span class="sxs-lookup"><span data-stu-id="2bf93-110">The requirement for cookie affinity in hardware load balancers is dramatically reduced, and you substitute Transmission Control Protocol (TCP) affinity if you are using the Lync Mobile delivered with Lync Server 2013.</span></span> <span data-ttu-id="2bf93-111">Cookie 相关性仍可使用, 但 web 服务不再需要它。</span><span class="sxs-lookup"><span data-stu-id="2bf93-111">Cookie affinity can still be used, but the web services no longer require it.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2bf93-112">无论来源点位于何处 (内部或外部), 所有移动服务流量都将经历反向代理。</span><span class="sxs-lookup"><span data-stu-id="2bf93-112">All Mobility Service traffic goes through the reverse proxy, regardless of where the origination point is—internal or external.</span></span> <span data-ttu-id="2bf93-113">如果是单个反向代理或反向代理服务器场或提供反向代理功能的设备, 则通过接口 egressing 内部流量并尝试立即进入同一接口时, 可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="2bf93-113">In the case of a single reverse proxy or a farm of reverse proxies, or a device that is providing the reverse proxy function, an issue can arise when the internal traffic is egressing through an interface and attempting to immediately ingress on the same interface.</span></span> <span data-ttu-id="2bf93-114">这通常会导致安全规则被称为 "TCP 数据包欺骗" 或 "仅欺骗"。</span><span class="sxs-lookup"><span data-stu-id="2bf93-114">This often leads to a Security rule violation known as TCP packet spoofing or just spoofing.</span></span> <span data-ttu-id="2bf93-115"><EM>头发钉住</EM>若要使移动正常运行, 必须允许传出和直接输入数据包或数据包。</span><span class="sxs-lookup"><span data-stu-id="2bf93-115"><EM>Hair pinning</EM> (the egress and immediate ingress of a packet or series of packets) must be allowed in order for mobility to function.</span></span> <span data-ttu-id="2bf93-116">解决此问题的一种方法是使用独立于防火墙的反向代理 (应始终在防火墙上强制执行欺骗性的阻止规则, 出于安全目的)。</span><span class="sxs-lookup"><span data-stu-id="2bf93-116">One way to resolve this issue is to use a reverse proxy that is separate from the firewall (the spoofing prevention rule should always be enforced at the firewall, for security purposes).</span></span> <span data-ttu-id="2bf93-117">Hairpin 可以出现在反向代理的外部接口上, 而不是防火墙外部接口。</span><span class="sxs-lookup"><span data-stu-id="2bf93-117">The hairpin can occur at the external interface of the reverse proxy instead of the firewall external interface.</span></span> <span data-ttu-id="2bf93-118">你可以在防火墙上检测欺骗, 并在反向代理服务器上放松规则, 从而允许移动性所需的 hairpin。</span><span class="sxs-lookup"><span data-stu-id="2bf93-118">You detect the spoofing at the firewall, and relax the rule at the reverse proxy, thereby allowing the hairpin that mobility requires.</span></span><BR><span data-ttu-id="2bf93-119">使用域名系统 (DNS) 主机或 CNAME 记录定义 hairpin 行为 (而非防火墙) 的反向代理 (如果可能)。</span><span class="sxs-lookup"><span data-stu-id="2bf93-119">Use the Domain Name System (DNS) host or CNAME records to define the reverse proxy for the hairpin behavior (not the firewall), if at all possible.</span></span>



</div>

<span data-ttu-id="2bf93-120">Lync Server 2013 支持 Lync 2010 移动版和 Lync 2013 移动客户端的移动服务。</span><span class="sxs-lookup"><span data-stu-id="2bf93-120">Lync Server 2013 supports mobility services for Lync 2010 Mobile and Lync 2013 mobile clients.</span></span> <span data-ttu-id="2bf93-121">两个客户端都使用 Lync Server 2013 自动发现服务来查找其移动入口点, 但其使用的移动服务有所不同。</span><span class="sxs-lookup"><span data-stu-id="2bf93-121">Both clients use the Lync Server 2013 Autodiscover Service to find its mobility entry point, but differ on which mobility service they use.</span></span> <span data-ttu-id="2bf93-122">Lync 2010 Mobile 使用名为*Mcx*的移动服务, 该服务由 Lync Server 2010 的累积更新引入:11 月2011。</span><span class="sxs-lookup"><span data-stu-id="2bf93-122">Lync 2010 Mobile uses the Mobility Service known as *Mcx*, introduced with the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="2bf93-123">Lync 2013 移动客户端将统一通信 Web API (或*UCWA*) 用作其移动服务提供商。</span><span class="sxs-lookup"><span data-stu-id="2bf93-123">Lync 2013 mobile clients use the Unified Communications Web API, or *UCWA*, as their mobility service provider.</span></span>

<div>

## <a name="internal-and-external-dns-configuration"></a><span data-ttu-id="2bf93-124">内部和外部 DNS 配置</span><span class="sxs-lookup"><span data-stu-id="2bf93-124">Internal and External DNS Configuration</span></span>

<span data-ttu-id="2bf93-125">移动服务 Mcx (使用 Lync Server 2010:11 月2011的累积更新引入) 和 UCWA (在 Lync Server 2013 的累积更新中引入: 2 月 2013) 以同样的方式使用 DNS。</span><span class="sxs-lookup"><span data-stu-id="2bf93-125">The Mobility Services Mcx (introduced with the Cumulative Update for Lync Server 2010: November 2011) and UCWA (introduced in the Cumulative Updates for Lync Server 2013: February 2013) use DNS in the same way.</span></span>

<span data-ttu-id="2bf93-126">使用自动发现时, 移动设备使用 DNS 查找资源。</span><span class="sxs-lookup"><span data-stu-id="2bf93-126">When you use Automatic Discovery, mobile devices use DNS to locate resources.</span></span> <span data-ttu-id="2bf93-127">在 DNS 查找过程中, 首先尝试连接到与内部 DNS 记录 (lyncdiscoverinternal) 相关联的 FQDN。\<内部域名\>)。</span><span class="sxs-lookup"><span data-stu-id="2bf93-127">During the DNS lookup, a connection is first attempted to the FQDN that is associated with the internal DNS record (lyncdiscoverinternal.\<internal domain name\>).</span></span> <span data-ttu-id="2bf93-128">如果使用内部 DNS 记录无法建立连接, 则使用外部 DNS 记录 (lyncdiscover) 尝试连接。\<sipdomain\>)。</span><span class="sxs-lookup"><span data-stu-id="2bf93-128">If a connection cannot be made by using the internal DNS record, a connection is attempted by using the external DNS record (lyncdiscover.\<sipdomain\>).</span></span> <span data-ttu-id="2bf93-129">网络内部的移动设备连接到内部自动发现服务 URL, 并且网络外部的移动设备连接到外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="2bf93-129">A mobile device that is internal to the network connects to the internal Autodiscover Service URL, and a mobile device that is external to the network connects to the external Autodiscover Service URL.</span></span> <span data-ttu-id="2bf93-130">外部自动发现请求经过反向代理。</span><span class="sxs-lookup"><span data-stu-id="2bf93-130">External Autodiscover requests go through the reverse proxy.</span></span> <span data-ttu-id="2bf93-131">Lync Server 2013 自动发现服务返回用户的主池的所有 Web 服务 Url, 包括移动服务 (Mcx 和 UCWA) Url。</span><span class="sxs-lookup"><span data-stu-id="2bf93-131">The Lync Server 2013 Autodiscover Service returns all Web Services URLs for the user's home pool, including the Mobility Service (Mcx and UCWA) URLs.</span></span> <span data-ttu-id="2bf93-132">但是, 内部移动服务 URL 和外部移动服务 URL 均与外部 Web 服务 FQDN 相关联。</span><span class="sxs-lookup"><span data-stu-id="2bf93-132">However, both the internal Mobility Service URL and the external Mobility Service URL are associated with the external Web Services FQDN.</span></span> <span data-ttu-id="2bf93-133">因此, 无论移动设备是网络内部还是外部设备, 设备都将始终通过反向代理连接到外部的 Lync Server 2013 移动服务。</span><span class="sxs-lookup"><span data-stu-id="2bf93-133">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Lync Server 2013 Mobility Service externally through the reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2bf93-134">了解你的部署可以包含多个不同的命名空间以供内部和外部使用, 这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="2bf93-134">It is important to understand that your deployment can consist of multiple distinct namespaces for internal and external use.</span></span> <span data-ttu-id="2bf93-135">您的 SIP 域名可能与内部部署域名不同。</span><span class="sxs-lookup"><span data-stu-id="2bf93-135">Your SIP domain name may be different than the internal deployment domain name.</span></span> <span data-ttu-id="2bf93-136">例如, 你的 SIP 域可能是<STRONG>contoso.com</STRONG>, 而内部部署可能是<STRONG>contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2bf93-136">For example, your SIP domain may be <STRONG>contoso.com</STRONG>, while your internal deployment may be <STRONG>contoso.net</STRONG>.</span></span> <span data-ttu-id="2bf93-137">登录 Lync Server 的用户将使用 SIP 域名, 例如<STRONG>john@contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2bf93-137">Users who log in to Lync Server will use the SIP domain name, such as <STRONG>john@contoso.com</STRONG>.</span></span> <span data-ttu-id="2bf93-138">当为外部 web 服务 (在拓扑生成器中定义为<STRONG>外部 web 服务</STRONG>) 寻址时, 域名和 SIP 域名将保持一致, 如 DNS 中所定义。</span><span class="sxs-lookup"><span data-stu-id="2bf93-138">When addressing the external web services (defined in Topology Builder as <STRONG>External web services</STRONG>), the domain name and the SIP domain name will be consistent, as defined in DNS.</span></span> <span data-ttu-id="2bf93-139">当寻址内部 Web 服务 (在拓扑生成器中定义为<STRONG>内部 web 服务</STRONG>) 时, 内部 web 服务的默认名称将是前端服务器、前端池、控制器或控制器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2bf93-139">When addressing the internal Web services (defined in Topology Builder as <STRONG>Internal web services</STRONG>), the default name of the internal web services will be the FQDN of the Front End Server, Front End pool, Director, or Director pool.</span></span> <span data-ttu-id="2bf93-140">你可以选择替代内部 web 服务名称。</span><span class="sxs-lookup"><span data-stu-id="2bf93-140">You have the option to override the internal web services name.</span></span> <span data-ttu-id="2bf93-141">你应该为内部 web 服务使用内部域名 (而不是 SIP 域名), 并定义 DNS 主机 A (或 IPv6、AAAA) 记录以反映替代名称。</span><span class="sxs-lookup"><span data-stu-id="2bf93-141">You should use the internal domain name (and not the SIP domain name) for internal web services and define the DNS host A (or, for IPv6, AAAA) record to reflect the overridden name.</span></span> <span data-ttu-id="2bf93-142">例如, 默认内部 web 服务 FQDN 可能为<STRONG>pool01.contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2bf93-142">For example, the default internal web services FQDN may be <STRONG>pool01.contoso.net</STRONG>.</span></span> <span data-ttu-id="2bf93-143">已覆盖内部 web 服务 FQDN 可能为<STRONG>webpool.contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2bf93-143">An overridden internal web services FQDN may be <STRONG>webpool.contoso.net</STRONG>.</span></span> <span data-ttu-id="2bf93-144">以这种方式定义 web 服务有助于确保服务的内部和外部位置 (而不是使用它们的用户的位置) 被遵守。</span><span class="sxs-lookup"><span data-stu-id="2bf93-144">Defining the web services in this way helps to ensure that the internal and external locality of the services—and not the locality of the user who is using them—is observed.</span></span><BR><span data-ttu-id="2bf93-145">但是, 由于 web 服务在拓扑生成器中定义且内部 web 服务名称可以被重写, 因此只要生成的 web 服务名称、验证它的证书以及定义它的 DNS 记录是一致的, 您就可以定义包含你所需的任何域名 (包括 SIP 域名) 的内部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="2bf93-145">However, because the web services are defined in Topology Builder and the internal web services name can be overridden, as long as the resulting web services name, the certificate that validates it, and the DNS records that define it, are consistent, you can define the internal web services with any domain name—including the SIP domain name—that you want.</span></span> <span data-ttu-id="2bf93-146">最终, 名称到 IP 地址的解析由 DNS 主机记录和一致的命名空间确定。</span><span class="sxs-lookup"><span data-stu-id="2bf93-146">Ultimately, the resolution for the name to the IP address is determined by DNS host records and a consistent namespace.</span></span><BR><span data-ttu-id="2bf93-147">出于本主题和示例的目的, 内部域名用于说明拓扑和 DNS 定义。</span><span class="sxs-lookup"><span data-stu-id="2bf93-147">For the purposes of this topic and the examples, the internal domain name is used to illustrate the topology and the DNS definitions.</span></span>



</div>

<span data-ttu-id="2bf93-148">下图显示了在使用内部和外部 DNS 配置时移动服务和自动发现服务的移动应用程序 web 请求的流程。</span><span class="sxs-lookup"><span data-stu-id="2bf93-148">The following diagram illustrates the flow of mobile application web requests for the Mobility Service and for the Autodiscover Service when using an internal and external DNS configuration.</span></span>

<span data-ttu-id="2bf93-149">**使用自动发现的移动服务流程**</span><span class="sxs-lookup"><span data-stu-id="2bf93-149">**Mobility service flow using AutoDiscover**</span></span>

<span data-ttu-id="2bf93-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span><span class="sxs-lookup"><span data-stu-id="2bf93-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2bf93-151">图表显示了通用 web 服务。</span><span class="sxs-lookup"><span data-stu-id="2bf93-151">The diagram illustrates generic web services.</span></span> <span data-ttu-id="2bf93-152">名为 "移动" 的虚拟目录描述了移动服务 Mcx 和/或 UCWA。</span><span class="sxs-lookup"><span data-stu-id="2bf93-152">A virtual directory named Mobility depicts the Mobility services Mcx and/or UCWA.</span></span> <span data-ttu-id="2bf93-153">如果尚未应用 Lync Server 2013 的累积更新: 2 月 2013, 则你的内部和外部 Web 服务上可能有也可能没有定义虚拟目录 Ucwa。</span><span class="sxs-lookup"><span data-stu-id="2bf93-153">If you have not applied the Cumulative Updates for Lync Server 2013: February 2013, you may or may not have the virtual directory Ucwa defined on your internal and external Web services.</span></span> <span data-ttu-id="2bf93-154">你将拥有虚拟目录自动发现, 并且你可能具有虚拟目录 Mcx。</span><span class="sxs-lookup"><span data-stu-id="2bf93-154">You will have a virtual directory Autodiscover, and you may have a virtual directory Mcx.</span></span><BR><span data-ttu-id="2bf93-155">无论您部署了何种移动服务技术, 自动发现和服务的发现的工作方式都相同。</span><span class="sxs-lookup"><span data-stu-id="2bf93-155">Autodiscover and the discovery of services work the same way, regardless of the mobility services technology that you have deployed.</span></span>



</div>

<span data-ttu-id="2bf93-156">为了支持来自公司网络内部和外部的移动用户, 内部和外部 web Fqdn 必须满足某些先决条件。</span><span class="sxs-lookup"><span data-stu-id="2bf93-156">To support mobile users from both inside and outside the corporate network, your internal and external web FQDNs must meet some prerequisites.</span></span> <span data-ttu-id="2bf93-157">此外, 你可能需要满足其他要求, 具体取决于你选择要实现的功能:</span><span class="sxs-lookup"><span data-stu-id="2bf93-157">In addition, you may need to meet other requirements, depending on the features you choose to implement:</span></span>

  - <span data-ttu-id="2bf93-158">新的 DNS、CNAME 或 A (host, if IPv6, AAAA) 记录, 用于自动发现。</span><span class="sxs-lookup"><span data-stu-id="2bf93-158">New DNS, CNAME or A (host, if IPv6, AAAA) records, for automatic discovery.</span></span>

  - <span data-ttu-id="2bf93-159">新防火墙规则（如果希望通过 Wi-Fi 网络支持推送通知）。</span><span class="sxs-lookup"><span data-stu-id="2bf93-159">New firewall rule, if you want to support push notifications through your Wi-Fi network.</span></span>

  - <span data-ttu-id="2bf93-160">内部服务器证书上的使用者备用名称和反向代理证书, 用于自动发现。</span><span class="sxs-lookup"><span data-stu-id="2bf93-160">Subject alternative names on internal server certificates and reverse proxy certificates, for automatic discovery.</span></span>

  - <span data-ttu-id="2bf93-161">前端服务器硬件负载平衡器配置更改了源关联。</span><span class="sxs-lookup"><span data-stu-id="2bf93-161">Front End Server hardware load balancer configuration changes source affinity.</span></span>

<span data-ttu-id="2bf93-162">拓扑必须满足以下要求才能支持移动服务和自动发现服务:</span><span class="sxs-lookup"><span data-stu-id="2bf93-162">Your topology must meet the following requirements to support the Mobility Service and the Autodiscover Service:</span></span>

  - <span data-ttu-id="2bf93-163">前端池内部 web FQDN 必须与前端池外部 web FQDN 不同。</span><span class="sxs-lookup"><span data-stu-id="2bf93-163">The Front End pool internal web FQDN must be distinct from the Front End pool external web FQDN.</span></span>

  - <span data-ttu-id="2bf93-164">内部 web FQDN 必须仅解析到企业网络内部并可访问。</span><span class="sxs-lookup"><span data-stu-id="2bf93-164">The internal web FQDN must only resolve to and be accessible from inside the corporate network.</span></span>

  - <span data-ttu-id="2bf93-165">外部 web FQDN 必须仅解析到并可从 Internet 访问。</span><span class="sxs-lookup"><span data-stu-id="2bf93-165">The external web FQDN must only resolve to and be accessible from the Internet.</span></span>

  - <span data-ttu-id="2bf93-166">对于位于企业网络内部的用户, 移动服务 URL 必须寻址到外部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="2bf93-166">For a user who is inside the corporate network, the Mobility Service URL must be addressed to the external web FQDN.</span></span> <span data-ttu-id="2bf93-167">此要求适用于移动服务, 并且仅适用于此 URL。</span><span class="sxs-lookup"><span data-stu-id="2bf93-167">This requirement is for the Mobility Service and applies only to this URL.</span></span>

  - <span data-ttu-id="2bf93-168">对于公司网络外部的用户, 请求必须转到前端池或控制器的外部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="2bf93-168">For a user who is outside the corporate network, the request must go to the external web FQDN of the Front End pool or Director.</span></span>

<span data-ttu-id="2bf93-169">如果你支持自动发现, 你需要为每个 SIP 域创建以下 DNS 记录:</span><span class="sxs-lookup"><span data-stu-id="2bf93-169">If you support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="2bf93-170">一个内部 DNS 记录, 用于支持从你的组织的网络中连接的移动用户。</span><span class="sxs-lookup"><span data-stu-id="2bf93-170">An internal DNS record to support mobile users who connect from within your organization's network.</span></span>

  - <span data-ttu-id="2bf93-171">支持从 Internet 连接的移动用户的外部 DNS 记录或公共 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="2bf93-171">An external, or public, DNS record to support mobile users who connect from the Internet.</span></span>

<span data-ttu-id="2bf93-172">内部自动发现 URL 不应从您的网络外部寻址。</span><span class="sxs-lookup"><span data-stu-id="2bf93-172">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="2bf93-173">外部自动发现 URL 不应从你的网络中寻址。</span><span class="sxs-lookup"><span data-stu-id="2bf93-173">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="2bf93-174">但是, 如果您无法满足外部 URL 的此要求, 则移动客户端功能可能不会受到影响, 因为内部 URL 总是首先尝试。</span><span class="sxs-lookup"><span data-stu-id="2bf93-174">However, if you cannot meet this requirement for the external URL, mobile client functionally will probably not be affected, because the internal URL is always tried first.</span></span>

<span data-ttu-id="2bf93-175">DNS 记录可以是 CNAME 记录, 也可以是 A (host, if IPv6、AAAA) 记录。</span><span class="sxs-lookup"><span data-stu-id="2bf93-175">The DNS records can be either CNAME records or A (host, if IPv6, AAAA) records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2bf93-176">移动设备客户端不支持来自不同域的多个安全套接字层 (SSL) 证书。</span><span class="sxs-lookup"><span data-stu-id="2bf93-176">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="2bf93-177">因此, 不支持通过 HTTPS 对不同域进行 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="2bf93-177">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="2bf93-178">例如, 不支持通过 HTTPS 重定向到 director.contoso.net 地址的 lyncdiscover.contoso.com 的 DNS CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="2bf93-178">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="2bf93-179">在此类拓扑中, 移动设备客户端需要对第一个请求使用 HTTP, 以便 CNAME 重定向通过 HTTP 进行解析。</span><span class="sxs-lookup"><span data-stu-id="2bf93-179">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="2bf93-180">随后的请求将使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="2bf93-180">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="2bf93-181">若要支持此方案, 你需要使用端口 80 (HTTP) 的 web 发布规则配置反向代理。</span><span class="sxs-lookup"><span data-stu-id="2bf93-181">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="2bf93-182">有关详细信息, 请参阅在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中配置反向代理</A>中的 "为端口80创建 web 发布规则"。</span><span class="sxs-lookup"><span data-stu-id="2bf93-182">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="2bf93-183">通过 HTTPS 支持到同一域的 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="2bf93-183">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="2bf93-184">在这种情况下, 目标域的证书覆盖了始发域。</span><span class="sxs-lookup"><span data-stu-id="2bf93-184">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<span data-ttu-id="2bf93-185">有关你的方案所需的 DNS 记录的详细信息, 请参阅[在 Lync Server 2013 中的 dns 摘要自动发现](lync-server-2013-dns-summary-autodiscover.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf93-185">For details about the DNS records required for your scenario, see [DNS summary - Autodiscover in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="port-and-firewall-requirements"></a><span data-ttu-id="2bf93-186">端口和防火墙要求</span><span class="sxs-lookup"><span data-stu-id="2bf93-186">Port and Firewall Requirements</span></span>

<span data-ttu-id="2bf93-187">如果你支持推送通知, 并且希望 Apple 移动设备通过 Wi-fi 网络接收推送通知, 你还需要在企业 Wi-fi 网络上打开端口5223。</span><span class="sxs-lookup"><span data-stu-id="2bf93-187">If you support push notifications and want Apple mobile devices to receive push notifications over your Wi-Fi network, you also need to open port 5223 on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="2bf93-188">端口5223是 Apple 推送通知服务 (APNS) 使用的出站 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="2bf93-188">Port 5223 is an outbound TCP port used by the Apple Push Notification Service (APNS).</span></span> <span data-ttu-id="2bf93-189">移动设备将启动连接。</span><span class="sxs-lookup"><span data-stu-id="2bf93-189">The mobile device initiates the connection.</span></span> <span data-ttu-id="2bf93-190">有关详细信息, [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629)请参阅。</span><span class="sxs-lookup"><span data-stu-id="2bf93-190">For details, see [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) .</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2bf93-191">使用 Lync 2013 移动客户端的 Apple 设备不需要推送通知。</span><span class="sxs-lookup"><span data-stu-id="2bf93-191">An Apple device using the Lync 2013 Mobile client does not require push notifications.</span></span>



</div>

<span data-ttu-id="2bf93-192">请注意, 如果用户托管在 Survivable 分支装置 (SBA) 上, 则需要以下端口:</span><span class="sxs-lookup"><span data-stu-id="2bf93-192">Note that if a user is homed on a Survivable Branch Appliance (SBA) then the following ports are required:</span></span>

  - <span data-ttu-id="2bf93-193">UcwaSipExternalListeningPort 需要端口5088</span><span class="sxs-lookup"><span data-stu-id="2bf93-193">UcwaSipExternalListeningPort requires port 5088</span></span>

  - <span data-ttu-id="2bf93-194">UcwaSipPrimaryListeningPort 需要端口5089</span><span class="sxs-lookup"><span data-stu-id="2bf93-194">UcwaSipPrimaryListeningPort requires port 5089</span></span>

<span data-ttu-id="2bf93-195">有关自动发现的端口和协议要求的其他详细信息和指导, 请参阅[在 Lync Server 2013 中自动发现的端口摘要](lync-server-2013-port-summary-autodiscover.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf93-195">For additional details and guidance on port and protocol requirements for Autodiscover, see [Port summary - Autodiscover in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="certificate-requirements"></a><span data-ttu-id="2bf93-196">证书要求</span><span class="sxs-lookup"><span data-stu-id="2bf93-196">Certificate Requirements</span></span>

<span data-ttu-id="2bf93-197">如果你支持 Lync 移动客户端的自动发现, 你需要修改证书上的使用者备用名称列表以支持来自移动客户端的安全连接。</span><span class="sxs-lookup"><span data-stu-id="2bf93-197">If you support automatic discovery for Lync mobile clients, you need to modify the subject alternative name lists on certificates to support secure connections from the mobile clients.</span></span> <span data-ttu-id="2bf93-198">对于运行自动发现服务的每个前端服务器和控制器, 你需要请求和分配新证书, 并为每个前端服务器和控制器添加本部分中所述的主题备用名称条目。</span><span class="sxs-lookup"><span data-stu-id="2bf93-198">You need to request and assign new certificates, adding the subject alternative name entries described in this section, for each Front End Server and Director that runs the Autodiscover Service.</span></span> <span data-ttu-id="2bf93-199">建议的方法也是在反向代理证书上修改 "主题备用名称" 列表。</span><span class="sxs-lookup"><span data-stu-id="2bf93-199">The recommended approach is to also modify the subject alternative names lists on certificates for your reverse proxies.</span></span> <span data-ttu-id="2bf93-200">您需要为组织中的每个 SIP 域添加主题备用名称条目。</span><span class="sxs-lookup"><span data-stu-id="2bf93-200">You need to add subject alternative name entries for every SIP domain in your organization.</span></span>

<span data-ttu-id="2bf93-201">通过使用内部证书颁发机构重新发起证书通常是一个简单的过程, 但向反向代理使用的公共证书添加多个主题备用名称条目可能会很高。</span><span class="sxs-lookup"><span data-stu-id="2bf93-201">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="2bf93-202">如果您有多个 SIP 域, 增加了使用者备用名称的费用, 则可以通过使用 HTTP 配置反向代理以通过端口80进行初始自动发现服务请求, 而不是使用 HTTPS (默认配置) 的端口443。</span><span class="sxs-lookup"><span data-stu-id="2bf93-202">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to make the initial Autodiscover Service request over port 80 using HTTP, instead of port 443 using HTTPS (the default configuration).</span></span> <span data-ttu-id="2bf93-203">然后, 该请求将被重定向到 Director 或前端池中的端口8080。</span><span class="sxs-lookup"><span data-stu-id="2bf93-203">The request is then redirected to port 8080 on the Director or Front End pool.</span></span> <span data-ttu-id="2bf93-204">在端口80上发布初始自动发现服务请求时, 不需要更改反向代理的证书, 因为该请求使用 HTTP 而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="2bf93-204">When you publish the initial Autodiscover Service request on port 80, you do not need to change certificates for the reverse proxy, because the request uses HTTP rather than HTTPS.</span></span> <span data-ttu-id="2bf93-205">此方法受支持, 但我们不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="2bf93-205">This approach is supported, but we do not recommend it.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="2bf93-206">Internet Information Services (IIS) 要求</span><span class="sxs-lookup"><span data-stu-id="2bf93-206">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="2bf93-207">我们建议你使用 IIS 7.5、IIS 8.0 或 IIS 8.5 进行移动。</span><span class="sxs-lookup"><span data-stu-id="2bf93-207">We recommend that you use IIS 7.5, IIS 8.0, or IIS 8.5 for mobility.</span></span> <span data-ttu-id="2bf93-208">移动服务安装程序在 ASP.NET 中设置标志以提高性能。</span><span class="sxs-lookup"><span data-stu-id="2bf93-208">The Mobility Service installer sets flags in ASP.NET to improve performance.</span></span> <span data-ttu-id="2bf93-209">默认情况下, IIS 7.5 安装在 Windows server 2008 R2 上, IIS 8.0 安装在 windows Server 2012 上, 而 IIS 8.5 安装在 Windows Server 2012 R2 上。</span><span class="sxs-lookup"><span data-stu-id="2bf93-209">IIS 7.5 is installed by default on Windows Server 2008 R2, IIS 8.0 is installed on Windows Server 2012, and IIS 8.5 is installed on Windows Server 2012 R2.</span></span> <span data-ttu-id="2bf93-210">移动服务安装程序会自动更改 ASP.NET 设置。</span><span class="sxs-lookup"><span data-stu-id="2bf93-210">The Mobility Service installer automatically changes the ASP.NET settings.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="2bf93-211">硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="2bf93-211">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="2bf93-212">在支持前端池的硬件负载平衡器上, 必须为源配置外部 Web 服务虚拟 IPs (Vip) 用于 Web 服务流量。</span><span class="sxs-lookup"><span data-stu-id="2bf93-212">On the hardware load balancer that is supporting the Front End pool, the external Web Services virtual IPs (VIPs) for Web Services traffic must be configured for source.</span></span> <span data-ttu-id="2bf93-213">源相关性有助于确保将单个客户端的多个连接发送到一台服务器以维护会话状态。</span><span class="sxs-lookup"><span data-stu-id="2bf93-213">Source affinity helps to ensure that multiple connections from a single client are sent to one server to maintain session state.</span></span> <span data-ttu-id="2bf93-214">有关相关性要求的详细信息, 请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf93-214">For details about affinity requirements, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<span data-ttu-id="2bf93-215">如果你计划仅在你的内部 Wlan 网络上支持 Lync 移动客户端, 你应该为源配置内部 Web 服务 VIP, 如外部 Web 服务 Vip 所述。</span><span class="sxs-lookup"><span data-stu-id="2bf93-215">If you plan to support Lync mobile clients only over your internal Wi-Fi network, you should configure the internal Web Services VIPS for source as described for external Web Services VIPs.</span></span> <span data-ttu-id="2bf93-216">在这种情况下, 你应该\_对硬件负载平衡器上的内部 Web 服务 vip 使用源地址 (或 TCP) 关联。</span><span class="sxs-lookup"><span data-stu-id="2bf93-216">In this situation, you should use source\_addr (or TCP) affinity for the internal Web Services VIPs on the hardware load balancer.</span></span> <span data-ttu-id="2bf93-217">有关详细信息, 请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf93-217">For details, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="2bf93-218">反向代理要求</span><span class="sxs-lookup"><span data-stu-id="2bf93-218">Reverse Proxy Requirements</span></span>

<span data-ttu-id="2bf93-219">如果你支持 Lync 移动客户端的自动发现, 你需要更新当前发布规则, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="2bf93-219">If you support automatic discovery for Lync mobile clients, you need to update the current publishing rule as follows:</span></span>

  - <span data-ttu-id="2bf93-220">如果你决定在反向代理证书上更新 "主题备用名称" 列表, 并对初始自动发现服务请求使用 HTTPS, 则必须更新 lyncdiscover 的 web 发布规则。\<sipdomain\>。</span><span class="sxs-lookup"><span data-stu-id="2bf93-220">If you decide to update the subject alternative names lists on the reverse proxy certificates and use HTTPS for the initial Autodiscover Service request, you must update the web publishing rule for lyncdiscover.\<sipdomain\>.</span></span> <span data-ttu-id="2bf93-221">通常, 此功能与前端池中的外部 Web 服务 URL 的发布规则相结合。</span><span class="sxs-lookup"><span data-stu-id="2bf93-221">Typically, this is combined with the publishing rule for the external Web Services URL on the Front End pool.</span></span>

  - <span data-ttu-id="2bf93-222">如果你决定将 HTTP 用于初始自动发现服务请求, 以便你不需要更新反向代理证书上的 "主题备用名称" 列表, 则必须为端口 HTTP/TCP 80 创建新的 web 发布规则 (如果尚不存在)。</span><span class="sxs-lookup"><span data-stu-id="2bf93-222">If you decide to use HTTP for the initial Autodiscover Service request so that you do not need to update the subject alternative names list on the reverse proxy certificates, you must create a new web publishing rule for port HTTP/TCP 80, if one does not already exist.</span></span> <span data-ttu-id="2bf93-223">如果 HTTP/TCP 80 的规则已存在, 则可以将该规则更新为包含 lyncdiscover。\<sipdomain\>条目。</span><span class="sxs-lookup"><span data-stu-id="2bf93-223">If a rule for HTTP/TCP 80 does already exist, you can update that rule to include the lyncdiscover.\<sipdomain\> entry.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

