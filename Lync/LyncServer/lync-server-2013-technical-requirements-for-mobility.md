---
title: Lync Server 2013：移动性技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb4c1eacf48940822ddb26ac41f238ccdb4452dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="7c8fb-102">Lync Server 2013 中的移动性技术要求</span><span class="sxs-lookup"><span data-stu-id="7c8fb-102">Technical requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c8fb-103">_**上次修改的主题：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="7c8fb-103">_**Topic Last Modified:** 2014-07-24_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="7c8fb-104">移动用户会遇到各种需要特殊规划的移动应用程序方案。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-104">Mobile users encounter various mobile application scenarios that require special planning.</span></span> <span data-ttu-id="7c8fb-105">例如，通过3G 网络连接时，某人可能会开始使用移动应用程序，然后在工作到达时切换到公司 Wi-fi 网络，然后在离开大楼时切换回3G。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-105">For example, someone might start using a mobile application while away from work by connecting through the 3G network, then switch to the corporate Wi-Fi network when arriving at work, and then switch back to 3G when leaving the building.</span></span> <span data-ttu-id="7c8fb-106">您需要规划您的环境以支持此类网络转换并确保实现一致的用户体验。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-106">You need to plan your environment to support such network transitions and guarantee a consistent user experience.</span></span> <span data-ttu-id="7c8fb-107">本节介绍了为支持移动应用程序和自动发现移动资源而必须具备的基础结构要求。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-107">This section describes the infrastructure requirements that you must have in order to support mobile applications and automatic discovery of mobility resources.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c8fb-108">尽管移动应用程序也可以连接到其他 Lync Server 2013 服务，但将所有移动应用程序 web 请求发送到相同外部 web 完全限定的域名（FQDN）的要求仅适用于 Lync Server 2013 移动服务。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-108">Although mobile applications can also connect to other Lync Server 2013 services, the requirement to send all mobile application web requests to the same external web fully qualified domain name (FQDN) applies only to the Lync Server 2013 Mobility Service.</span></span> <span data-ttu-id="7c8fb-109">其他移动服务不需要此配置。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-109">Other mobility services do not require this configuration.</span></span>



</div>

<span data-ttu-id="7c8fb-110">硬件负载平衡器中的 cookie 关联要求大大减少，如果使用 lync Mobile 提供的 Lync Server 2013，则替换了传输控制协议（TCP）关联。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-110">The requirement for cookie affinity in hardware load balancers is dramatically reduced, and you substitute Transmission Control Protocol (TCP) affinity if you are using the Lync Mobile delivered with Lync Server 2013.</span></span> <span data-ttu-id="7c8fb-111">Cookie 相关性仍然可以使用，但 web 服务不再需要它。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-111">Cookie affinity can still be used, but the web services no longer require it.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7c8fb-112">所有移动服务流量都通过反向代理，而不管来源点是内部还是外部。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-112">All Mobility Service traffic goes through the reverse proxy, regardless of where the origination point is—internal or external.</span></span> <span data-ttu-id="7c8fb-113">如果是单个反向代理或反向代理服务器场或提供反向代理功能的设备，则通过接口附近内部流量并尝试立即进入同一接口时，可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-113">In the case of a single reverse proxy or a farm of reverse proxies, or a device that is providing the reverse proxy function, an issue can arise when the internal traffic is egressing through an interface and attempting to immediately ingress on the same interface.</span></span> <span data-ttu-id="7c8fb-114">这通常会导致违反 TCP 数据包欺骗或仅哄骗的安全规则。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-114">This often leads to a Security rule violation known as TCP packet spoofing or just spoofing.</span></span> <span data-ttu-id="7c8fb-115">若要使移动功能正常工作，必须允许使用<EM>头发钉住</EM>（数据包或数据包系列的出口和直接入站）。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-115"><EM>Hair pinning</EM> (the egress and immediate ingress of a packet or series of packets) must be allowed in order for mobility to function.</span></span> <span data-ttu-id="7c8fb-116">解决此问题的一种方法是使用独立于防火墙的反向代理（哄骗预防规则应始终在防火墙上强制实施，出于安全目的）。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-116">One way to resolve this issue is to use a reverse proxy that is separate from the firewall (the spoofing prevention rule should always be enforced at the firewall, for security purposes).</span></span> <span data-ttu-id="7c8fb-117">发夹可以在反向代理的外部接口（而不是防火墙外部接口）发生。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-117">The hairpin can occur at the external interface of the reverse proxy instead of the firewall external interface.</span></span> <span data-ttu-id="7c8fb-118">在防火墙中检测到欺骗，并在反向代理中放松该规则，从而允许移动性所需的发夹。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-118">You detect the spoofing at the firewall, and relax the rule at the reverse proxy, thereby allowing the hairpin that mobility requires.</span></span><BR><span data-ttu-id="7c8fb-119">使用域名系统（DNS）主机或 CNAME 记录为发夹行为（而不是防火墙）定义反向代理（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-119">Use the Domain Name System (DNS) host or CNAME records to define the reverse proxy for the hairpin behavior (not the firewall), if at all possible.</span></span>



</div>

<span data-ttu-id="7c8fb-120">Lync Server 2013 支持 Lync 2010 移动和 Lync 2013 移动客户端的移动服务。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-120">Lync Server 2013 supports mobility services for Lync 2010 Mobile and Lync 2013 mobile clients.</span></span> <span data-ttu-id="7c8fb-121">这两个客户端都使用 Lync Server 2013 自动发现服务来查找其移动入口点，但在其使用的移动服务上有所不同。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-121">Both clients use the Lync Server 2013 Autodiscover Service to find its mobility entry point, but differ on which mobility service they use.</span></span> <span data-ttu-id="7c8fb-122">Lync 2010 Mobile 使用移动服务（称为 " *Mcx*"），随 Lync Server 2010 的累积更新引入：11月2011。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-122">Lync 2010 Mobile uses the Mobility Service known as *Mcx*, introduced with the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="7c8fb-123">Lync 2013 移动客户端使用统一通信 Web API 或*UCWA*作为其移动服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-123">Lync 2013 mobile clients use the Unified Communications Web API, or *UCWA*, as their mobility service provider.</span></span>

<div>

## <a name="internal-and-external-dns-configuration"></a><span data-ttu-id="7c8fb-124">内部和外部 DNS 配置</span><span class="sxs-lookup"><span data-stu-id="7c8fb-124">Internal and External DNS Configuration</span></span>

<span data-ttu-id="7c8fb-125">移动服务 Mcx （随 Lync Server 2010：11月2011的累积更新引入）和 UCWA （在 Lync Server 2013 的累积更新中引入：二月份2013）以相同的方式使用 DNS。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-125">The Mobility Services Mcx (introduced with the Cumulative Update for Lync Server 2010: November 2011) and UCWA (introduced in the Cumulative Updates for Lync Server 2013: February 2013) use DNS in the same way.</span></span>

<span data-ttu-id="7c8fb-126">当您使用自动发现时，移动设备将使用 DNS 查找资源。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-126">When you use Automatic Discovery, mobile devices use DNS to locate resources.</span></span> <span data-ttu-id="7c8fb-127">在 DNS 查找过程中，首先尝试连接到与内部 DNS 记录（lyncdiscoverinternal.）相关联的 FQDN。\<内部域名称\>）。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-127">During the DNS lookup, a connection is first attempted to the FQDN that is associated with the internal DNS record (lyncdiscoverinternal.\<internal domain name\>).</span></span> <span data-ttu-id="7c8fb-128">如果无法使用内部 DNS 记录建立连接，则使用外部 DNS 记录（lyncdiscover.）尝试连接。\<sipdomain\>）。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-128">If a connection cannot be made by using the internal DNS record, a connection is attempted by using the external DNS record (lyncdiscover.\<sipdomain\>).</span></span> <span data-ttu-id="7c8fb-129">网络内部的移动设备会连接到内部自动发现服务 URL，而网络外部的移动设备会连接到外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-129">A mobile device that is internal to the network connects to the internal Autodiscover Service URL, and a mobile device that is external to the network connects to the external Autodiscover Service URL.</span></span> <span data-ttu-id="7c8fb-130">外部自动发现请求会经历反向代理。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-130">External Autodiscover requests go through the reverse proxy.</span></span> <span data-ttu-id="7c8fb-131">Lync Server 2013 自动发现服务返回用户主池的所有 Web 服务 Url，包括移动服务（Mcx 和 UCWA） Url。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-131">The Lync Server 2013 Autodiscover Service returns all Web Services URLs for the user's home pool, including the Mobility Service (Mcx and UCWA) URLs.</span></span> <span data-ttu-id="7c8fb-132">但是，内部 Mobility Service URL 和外部 Mobility Service URL 都与外部 Web 服务 FQDN 关联。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-132">However, both the internal Mobility Service URL and the external Mobility Service URL are associated with the external Web Services FQDN.</span></span> <span data-ttu-id="7c8fb-133">因此，无论移动设备是在网络内部还是外部，设备都将始终通过反向代理从外部连接到 Lync Server 2013 移动服务。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-133">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Lync Server 2013 Mobility Service externally through the reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c8fb-134">您的部署可以由多个不同的命名空间组成，以供内部和外部使用，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-134">It is important to understand that your deployment can consist of multiple distinct namespaces for internal and external use.</span></span> <span data-ttu-id="7c8fb-135">您的 SIP 域名可能不同于内部部署域名称。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-135">Your SIP domain name may be different than the internal deployment domain name.</span></span> <span data-ttu-id="7c8fb-136">例如，您的 SIP 域可能是<STRONG>contoso.com</STRONG>，而内部部署可能是<STRONG>contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-136">For example, your SIP domain may be <STRONG>contoso.com</STRONG>, while your internal deployment may be <STRONG>contoso.net</STRONG>.</span></span> <span data-ttu-id="7c8fb-137">登录到 Lync Server 的用户将使用 SIP 域名，如<STRONG>john@contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-137">Users who log in to Lync Server will use the SIP domain name, such as <STRONG>john@contoso.com</STRONG>.</span></span> <span data-ttu-id="7c8fb-138">在将外部 web 服务（在拓扑生成器中定义为<STRONG>外部 web 服务</STRONG>）寻址时，域名和 SIP 域名将保持一致，如 DNS 中所定义。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-138">When addressing the external web services (defined in Topology Builder as <STRONG>External web services</STRONG>), the domain name and the SIP domain name will be consistent, as defined in DNS.</span></span> <span data-ttu-id="7c8fb-139">在为内部 web 服务（在拓扑生成器中定义为<STRONG>内部 web 服务</STRONG>）寻址时，内部 web 服务的默认名称将是前端服务器、前端池、控制器或控制器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-139">When addressing the internal Web services (defined in Topology Builder as <STRONG>Internal web services</STRONG>), the default name of the internal web services will be the FQDN of the Front End Server, Front End pool, Director, or Director pool.</span></span> <span data-ttu-id="7c8fb-140">你可以选择替代内部 web 服务名称。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-140">You have the option to override the internal web services name.</span></span> <span data-ttu-id="7c8fb-141">应使用内部 web 服务的内部域名（而不是 SIP 域名），并定义 DNS 主机 A （或 IPv6、AAAA）记录以反映覆盖的名称。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-141">You should use the internal domain name (and not the SIP domain name) for internal web services and define the DNS host A (or, for IPv6, AAAA) record to reflect the overridden name.</span></span> <span data-ttu-id="7c8fb-142">例如，默认的内部 web 服务 FQDN 可能为<STRONG>pool01.contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-142">For example, the default internal web services FQDN may be <STRONG>pool01.contoso.net</STRONG>.</span></span> <span data-ttu-id="7c8fb-143">重写的内部 web 服务 FQDN 可能是<STRONG>webpool.contoso.net</STRONG>的。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-143">An overridden internal web services FQDN may be <STRONG>webpool.contoso.net</STRONG>.</span></span> <span data-ttu-id="7c8fb-144">以这种方式定义 web 服务有助于确保服务的内部和外部位置（而不是使用它们的用户的位置）遵守。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-144">Defining the web services in this way helps to ensure that the internal and external locality of the services—and not the locality of the user who is using them—is observed.</span></span><BR><span data-ttu-id="7c8fb-145">但是，由于 web 服务是在拓扑生成器中定义的，并且可以重写内部 web 服务名称，因此只要生成的 web 服务名称、用于验证它的证书以及用于定义它的 DNS 记录，它们就是一致的。您可以定义包含您所需的任何域名（包括 SIP 域名）的内部 web 服务。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-145">However, because the web services are defined in Topology Builder and the internal web services name can be overridden, as long as the resulting web services name, the certificate that validates it, and the DNS records that define it, are consistent, you can define the internal web services with any domain name—including the SIP domain name—that you want.</span></span> <span data-ttu-id="7c8fb-146">最终，名称到 IP 地址的解析由 DNS 主机记录和一致的命名空间确定。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-146">Ultimately, the resolution for the name to the IP address is determined by DNS host records and a consistent namespace.</span></span><BR><span data-ttu-id="7c8fb-147">出于本主题和示例的目的，内部域名用于说明拓扑和 DNS 定义。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-147">For the purposes of this topic and the examples, the internal domain name is used to illustrate the topology and the DNS definitions.</span></span>



</div>

<span data-ttu-id="7c8fb-148">下图说明了在使用内部和外部 DNS 配置时移动服务和自动发现服务的移动应用程序 web 请求流。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-148">The following diagram illustrates the flow of mobile application web requests for the Mobility Service and for the Autodiscover Service when using an internal and external DNS configuration.</span></span>

<span data-ttu-id="7c8fb-149">**使用自动发现的移动服务流**</span><span class="sxs-lookup"><span data-stu-id="7c8fb-149">**Mobility service flow using AutoDiscover**</span></span>

<span data-ttu-id="7c8fb-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span><span class="sxs-lookup"><span data-stu-id="7c8fb-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c8fb-151">该图说明了通用 web 服务。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-151">The diagram illustrates generic web services.</span></span> <span data-ttu-id="7c8fb-152">名为 "移动性" 的虚拟目录描述了移动服务 Mcx 和/或 UCWA。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-152">A virtual directory named Mobility depicts the Mobility services Mcx and/or UCWA.</span></span> <span data-ttu-id="7c8fb-153">如果尚未应用 Lync Server 2013 的累积更新：2月2013，则您的内部和外部 Web 服务上可能有也可能没有定义虚拟目录 Ucwa。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-153">If you have not applied the Cumulative Updates for Lync Server 2013: February 2013, you may or may not have the virtual directory Ucwa defined on your internal and external Web services.</span></span> <span data-ttu-id="7c8fb-154">您将拥有一个虚拟目录自动发现，并且您可能有一个虚拟目录 Mcx。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-154">You will have a virtual directory Autodiscover, and you may have a virtual directory Mcx.</span></span><BR><span data-ttu-id="7c8fb-155">无论您部署了何种移动服务技术，自动发现和服务发现的工作方式都是相同的。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-155">Autodiscover and the discovery of services work the same way, regardless of the mobility services technology that you have deployed.</span></span>



</div>

<span data-ttu-id="7c8fb-p110">若要同时支持企业网络内部和外部的移动用户，内部和外部 Web FQDN 必须满足某些先决条件。此外，您可能需要满足其他要求，具体取决于您选择用来实现以下各项的功能：</span><span class="sxs-lookup"><span data-stu-id="7c8fb-p110">To support mobile users from both inside and outside the corporate network, your internal and external web FQDNs must meet some prerequisites. In addition, you may need to meet other requirements, depending on the features you choose to implement:</span></span>

  - <span data-ttu-id="7c8fb-158">用于自动发现的新 DNS、CNAME 或 A （主机，如果是 IPv6、AAAA）记录。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-158">New DNS, CNAME or A (host, if IPv6, AAAA) records, for automatic discovery.</span></span>

  - <span data-ttu-id="7c8fb-159">新的防火墙规则（如果要通过 Wlan 网络支持推送通知）。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-159">New firewall rule, if you want to support push notifications through your Wi-Fi network.</span></span>

  - <span data-ttu-id="7c8fb-160">内部服务器证书上的使用者替代名称和反向代理证书（用于自动发现）。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-160">Subject alternative names on internal server certificates and reverse proxy certificates, for automatic discovery.</span></span>

  - <span data-ttu-id="7c8fb-161">前端服务器硬件负载平衡器配置更改源关联。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-161">Front End Server hardware load balancer configuration changes source affinity.</span></span>

<span data-ttu-id="7c8fb-162">您的拓扑必须满足以下要求才能支持移动服务和自动发现服务：</span><span class="sxs-lookup"><span data-stu-id="7c8fb-162">Your topology must meet the following requirements to support the Mobility Service and the Autodiscover Service:</span></span>

  - <span data-ttu-id="7c8fb-163">前端池内部 web FQDN 必须与前端池外部 web FQDN 不同。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-163">The Front End pool internal web FQDN must be distinct from the Front End pool external web FQDN.</span></span>

  - <span data-ttu-id="7c8fb-164">内部 Web FQDN 必须仅解析为企业网络地址且仅能从企业网络内部进行访问。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-164">The internal web FQDN must only resolve to and be accessible from inside the corporate network.</span></span>

  - <span data-ttu-id="7c8fb-165">外部 web FQDN 必须仅解析到并可从 Internet 访问。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-165">The external web FQDN must only resolve to and be accessible from the Internet.</span></span>

  - <span data-ttu-id="7c8fb-p111">对于企业网络内部的用户，必须将 Mobility Service URL 寻址到外部 Web FQDN。此要求针对的是 Mobility Service 且仅适用于此 URL。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-p111">For a user who is inside the corporate network, the Mobility Service URL must be addressed to the external web FQDN. This requirement is for the Mobility Service and applies only to this URL.</span></span>

  - <span data-ttu-id="7c8fb-168">对于公司网络外部的用户，该请求必须转到前端池或控制器的外部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-168">For a user who is outside the corporate network, the request must go to the external web FQDN of the Front End pool or Director.</span></span>

<span data-ttu-id="7c8fb-169">如果您支持自动发现，则需要为每个 SIP 域创建以下 DNS 记录：</span><span class="sxs-lookup"><span data-stu-id="7c8fb-169">If you support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="7c8fb-170">支持从组织网络内部进行连接的移动用户的内部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-170">An internal DNS record to support mobile users who connect from within your organization's network.</span></span>

  - <span data-ttu-id="7c8fb-171">支持从 Internet 进行连接的移动用户的外部或公共 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-171">An external, or public, DNS record to support mobile users who connect from the Internet.</span></span>

<span data-ttu-id="7c8fb-172">应无法从网络外部对内部自动发现 URL 进行寻址。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-172">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="7c8fb-173">应无法从网络内部对外部自动发现 URL 进行寻址。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-173">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="7c8fb-174">但是，如果您无法满足外部 URL 的此要求，则可能不会影响移动客户端的功能，因为最初总是会尝试内部 URL。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-174">However, if you cannot meet this requirement for the external URL, mobile client functionally will probably not be affected, because the internal URL is always tried first.</span></span>

<span data-ttu-id="7c8fb-175">DNS 记录可以是 CNAME 记录，也可以是（主机，如果是 IPv6，AAAA）记录。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-175">The DNS records can be either CNAME records or A (host, if IPv6, AAAA) records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c8fb-176">移动设备客户端不支持来自不同域的多个安全套接字层 (SSL) 证书。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-176">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="7c8fb-177">因此，不支持通过 HTTPS 对其他域进行 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-177">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="7c8fb-178">例如，不支持通过 HTTPS 将 lyncdiscover.contoso.com 的 DNS CNAME 记录重定向到 director.contoso.net 地址。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-178">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="7c8fb-179">在此类拓扑中，移动设备客户端需要对第一个请求使用 HTTP，以便通过 HTTP 解析 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-179">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="7c8fb-180">之后，后续请求会使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-180">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="7c8fb-181">若要支持此方案，您需要使用针对端口 80 (HTTP) 的 Web 发布规则配置反向代理。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-181">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="7c8fb-182">有关详细信息，请参阅在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中配置反向代理以实现移动性的反向代理</A>中的 "为端口80创建 web 发布规则"。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-182">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="7c8fb-183">支持通过 HTTPS 对同一域的 CNAME 重定向。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-183">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="7c8fb-184">在这种情况下，目标域的证书将覆盖源域。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-184">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<span data-ttu-id="7c8fb-185">有关您的方案所需的 DNS 记录的详细信息，请参阅[Lync Server 2013 中的 dns 摘要-自动发现](lync-server-2013-dns-summary-autodiscover.md)。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-185">For details about the DNS records required for your scenario, see [DNS summary - Autodiscover in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="port-and-firewall-requirements"></a><span data-ttu-id="7c8fb-186">端口和防火墙要求</span><span class="sxs-lookup"><span data-stu-id="7c8fb-186">Port and Firewall Requirements</span></span>

<span data-ttu-id="7c8fb-187">如果您支持推送通知并希望 Apple 移动设备通过 Wi-Fi 网络接收推送通知，则还需要在您的企业 Wi-Fi 网络上打开端口 5223。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-187">If you support push notifications and want Apple mobile devices to receive push notifications over your Wi-Fi network, you also need to open port 5223 on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="7c8fb-188">端口 5223 是一个由 Apple 推送通知服务 (APNS) 使用的出站 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-188">Port 5223 is an outbound TCP port used by the Apple Push Notification Service (APNS).</span></span> <span data-ttu-id="7c8fb-189">移动设备启动连接。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-189">The mobile device initiates the connection.</span></span> <span data-ttu-id="7c8fb-190">有关详细信息， [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629)请参阅。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-190">For details, see [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) .</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7c8fb-191">使用 Lync 2013 移动客户端的 Apple 设备不需要推送通知。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-191">An Apple device using the Lync 2013 Mobile client does not require push notifications.</span></span>



</div>

<span data-ttu-id="7c8fb-192">请注意，如果用户驻留在 Survivable 分支设备（SBA）上，则需要以下端口：</span><span class="sxs-lookup"><span data-stu-id="7c8fb-192">Note that if a user is homed on a Survivable Branch Appliance (SBA) then the following ports are required:</span></span>

  - <span data-ttu-id="7c8fb-193">UcwaSipExternalListeningPort 需要端口5088</span><span class="sxs-lookup"><span data-stu-id="7c8fb-193">UcwaSipExternalListeningPort requires port 5088</span></span>

  - <span data-ttu-id="7c8fb-194">UcwaSipPrimaryListeningPort 需要端口5089</span><span class="sxs-lookup"><span data-stu-id="7c8fb-194">UcwaSipPrimaryListeningPort requires port 5089</span></span>

<span data-ttu-id="7c8fb-195">有关自动发现的端口和协议要求的其他详细信息和指导，请参阅[Lync Server 2013 中的端口摘要-自动发现](lync-server-2013-port-summary-autodiscover.md)。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-195">For additional details and guidance on port and protocol requirements for Autodiscover, see [Port summary - Autodiscover in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="certificate-requirements"></a><span data-ttu-id="7c8fb-196">证书要求</span><span class="sxs-lookup"><span data-stu-id="7c8fb-196">Certificate Requirements</span></span>

<span data-ttu-id="7c8fb-197">如果您支持 Lync 移动客户端的自动发现，则需要修改证书上的使用者替代名称列表以支持来自该移动客户端的安全连接。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-197">If you support automatic discovery for Lync mobile clients, you need to modify the subject alternative name lists on certificates to support secure connections from the mobile clients.</span></span> <span data-ttu-id="7c8fb-198">对于运行自动发现服务的每台前端服务器和控制器，您需要请求和分配新证书，并为每个前端服务器和控制器添加此部分中介绍的使用者可选名称条目。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-198">You need to request and assign new certificates, adding the subject alternative name entries described in this section, for each Front End Server and Director that runs the Autodiscover Service.</span></span> <span data-ttu-id="7c8fb-199">建议的方法同样是修改反向代理的证书上的使用者替代名称列表。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-199">The recommended approach is to also modify the subject alternative names lists on certificates for your reverse proxies.</span></span> <span data-ttu-id="7c8fb-200">您需要为组织中的每个 SIP 域添加使用者替代名称条目。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-200">You need to add subject alternative name entries for every SIP domain in your organization.</span></span>

<span data-ttu-id="7c8fb-201">使用内部证书颁发结构重新颁发证书通常是一个简单的过程，但向反向代理所使用的公共证书中添加多个使用者替代名称条目的成本很高。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-201">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="7c8fb-202">如果您具有多个 SIP 域（这会导致添加使用者替代名称的成本很高），则可以将反向代理配置为在使用 HTTP 的端口 80（而非使用 HTTPS 的端口 443，这是默认配置）上发出初始自动发现服务请求。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-202">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to make the initial Autodiscover Service request over port 80 using HTTP, instead of port 443 using HTTPS (the default configuration).</span></span> <span data-ttu-id="7c8fb-203">然后，将该请求重定向到控制器或前端池上的端口8080。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-203">The request is then redirected to port 8080 on the Director or Front End pool.</span></span> <span data-ttu-id="7c8fb-204">当您在端口 80 上发布初始自动发现服务请求时，您无需更改反向代理的证书，因为该请求使用的是 HTTP 而非 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-204">When you publish the initial Autodiscover Service request on port 80, you do not need to change certificates for the reverse proxy, because the request uses HTTP rather than HTTPS.</span></span> <span data-ttu-id="7c8fb-205">此方法受支持，但我们不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-205">This approach is supported, but we do not recommend it.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="7c8fb-206">Internet Information Services (IIS) 要求</span><span class="sxs-lookup"><span data-stu-id="7c8fb-206">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="7c8fb-207">建议使用 IIS 7.5、IIS 8.0 或 IIS 8.5 进行移动。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-207">We recommend that you use IIS 7.5, IIS 8.0, or IIS 8.5 for mobility.</span></span> <span data-ttu-id="7c8fb-208">移动服务安装程序在 ASP.NET 中设置标志以提高性能。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-208">The Mobility Service installer sets flags in ASP.NET to improve performance.</span></span> <span data-ttu-id="7c8fb-209">默认情况下，IIS 7.5 安装在 Windows server 2008 R2 上，IIS 8.0 安装在 windows Server 2012 上，而 IIS 8.5 安装在 Windows server 2012 R2 上。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-209">IIS 7.5 is installed by default on Windows Server 2008 R2, IIS 8.0 is installed on Windows Server 2012, and IIS 8.5 is installed on Windows Server 2012 R2.</span></span> <span data-ttu-id="7c8fb-210">移动服务安装程序会自动更改 ASP.NET 设置。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-210">The Mobility Service installer automatically changes the ASP.NET settings.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="7c8fb-211">硬件负载平衡器要求</span><span class="sxs-lookup"><span data-stu-id="7c8fb-211">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="7c8fb-212">在支持前端池的硬件负载平衡器上，必须为源配置 Web 服务流量的外部 Web 服务虚拟 Ip （Vip）。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-212">On the hardware load balancer that is supporting the Front End pool, the external Web Services virtual IPs (VIPs) for Web Services traffic must be configured for source.</span></span> <span data-ttu-id="7c8fb-213">源关联有助于确保将来自单个客户端的多个连接发送到一台服务器，以维护会话状态。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-213">Source affinity helps to ensure that multiple connections from a single client are sent to one server to maintain session state.</span></span> <span data-ttu-id="7c8fb-214">有关相关性要求的详细信息，请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-214">For details about affinity requirements, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<span data-ttu-id="7c8fb-215">如果计划仅通过内部 Wlan 网络支持 Lync 移动客户端，则应为源配置内部 Web 服务 VIP，如外部 Web 服务 Vip 所述。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-215">If you plan to support Lync mobile clients only over your internal Wi-Fi network, you should configure the internal Web Services VIPS for source as described for external Web Services VIPs.</span></span> <span data-ttu-id="7c8fb-216">在这种情况下，应将\_源地址（或 TCP）关联用于硬件负载平衡器上的内部 Web 服务 vip。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-216">In this situation, you should use source\_addr (or TCP) affinity for the internal Web Services VIPs on the hardware load balancer.</span></span> <span data-ttu-id="7c8fb-217">有关详细信息，请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-217">For details, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="7c8fb-218">反向代理要求</span><span class="sxs-lookup"><span data-stu-id="7c8fb-218">Reverse Proxy Requirements</span></span>

<span data-ttu-id="7c8fb-219">如果您支持 Lync 移动客户端的自动发现，则需要更新当前发布规则，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7c8fb-219">If you support automatic discovery for Lync mobile clients, you need to update the current publishing rule as follows:</span></span>

  - <span data-ttu-id="7c8fb-220">如果您决定在反向代理证书上更新 "主题备用名称" 列表并对初始自动发现服务请求使用 HTTPS，则必须更新 lyncdiscover. 的 web 发布规则。\<sipdomain\>。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-220">If you decide to update the subject alternative names lists on the reverse proxy certificates and use HTTPS for the initial Autodiscover Service request, you must update the web publishing rule for lyncdiscover.\<sipdomain\>.</span></span> <span data-ttu-id="7c8fb-221">通常情况下，这与前端池上的外部 Web 服务 URL 的发布规则结合在一起。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-221">Typically, this is combined with the publishing rule for the external Web Services URL on the Front End pool.</span></span>

  - <span data-ttu-id="7c8fb-222">如果您决定对初始自动发现服务请求使用 HTTP，以便不需要更新反向代理证书上的 "主题备用名称" 列表，则必须为 "端口 HTTP/TCP 80" 创建一个新的 web 发布规则（如果尚不存在）。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-222">If you decide to use HTTP for the initial Autodiscover Service request so that you do not need to update the subject alternative names list on the reverse proxy certificates, you must create a new web publishing rule for port HTTP/TCP 80, if one does not already exist.</span></span> <span data-ttu-id="7c8fb-223">如果 HTTP/TCP 80 的规则已存在，则可以将该规则更新为包含 lyncdiscover.。\<sipdomain\>条目。</span><span class="sxs-lookup"><span data-stu-id="7c8fb-223">If a rule for HTTP/TCP 80 does already exist, you can update that rule to include the lyncdiscover.\<sipdomain\> entry.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

