---
title: Lync Server 2013：确定 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd8c1c95c3b8ba3671735447f098eca9173111ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="3ef88-102">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="3ef88-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ef88-103">_**主题上次修改时间：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3ef88-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3ef88-104">使用以下流程图确定域名系统 (DNS) 要求。</span><span class="sxs-lookup"><span data-stu-id="3ef88-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="3ef88-105">Lync Server 2013 的累积更新的更改：2月2013的适用位置。</span><span class="sxs-lookup"><span data-stu-id="3ef88-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ef88-106">Microsoft Lync Server 2013 支持使用 IPv6 寻址。</span><span class="sxs-lookup"><span data-stu-id="3ef88-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="3ef88-107">要使用 IPv6 地址，还必须提供 IPv6 DNS 支持和配置 DNS 主机 AAAA（称为“4 A”）记录。</span><span class="sxs-lookup"><span data-stu-id="3ef88-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="3ef88-108">在使用 IPv4 和 IPv6 的部署中，最好为 IPv4 配置和维护 A 记录，并为 IPv6 配置主机 AAAA。</span><span class="sxs-lookup"><span data-stu-id="3ef88-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="3ef88-109">即使您的部署已完全转换为 IPv6，当外部用户仍在使用 IPv4 时，也仍需要 IPv4 DNS 主机记录。</span><span class="sxs-lookup"><span data-stu-id="3ef88-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="3ef88-110">**确定 DNS 要求流程图**</span><span class="sxs-lookup"><span data-stu-id="3ef88-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="3ef88-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="3ef88-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ef88-112">默认情况下，未加入域的计算机的计算机名是主机名，而不是完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="3ef88-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="3ef88-113">拓扑生成器使用 Fqdn，而不是主机名。</span><span class="sxs-lookup"><span data-stu-id="3ef88-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="3ef88-114">因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="3ef88-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="3ef88-115">分配您的 Lync Server、边缘服务器和池的 FQDN 时，<STRONG>只使用标准字符</STRONG>（包括 A–Z、a–z、0–9 和连字符）。</span><span class="sxs-lookup"><span data-stu-id="3ef88-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="3ef88-116">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="3ef88-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="3ef88-117">外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。</span><span class="sxs-lookup"><span data-stu-id="3ef88-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="3ef88-118">有关其他详细信息，请参阅<A href="lync-server-2013-configure-dns-host-records.md">为 Lync Server 2013 配置 DNS 主机记录</A></span><span class="sxs-lookup"><span data-stu-id="3ef88-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="3ef88-119">Lync 客户端如何查找服务</span><span class="sxs-lookup"><span data-stu-id="3ef88-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="3ef88-120">Microsoft Lync 2010、Lync 2013 和 Lync Mobile 与客户在 Lync Server 2013 中查找和访问服务的方式类似。</span><span class="sxs-lookup"><span data-stu-id="3ef88-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="3ef88-121">显著的例外是使用不同服务位置进程的 Lync Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="3ef88-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="3ef88-122">本节详细介绍客户端定位服务的两种方案，第一种为传统方法，使用一系列 SRV 和 A 主机记录，第二种只使用自动发现服务记录。</span><span class="sxs-lookup"><span data-stu-id="3ef88-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="3ef88-123">对桌面客户端的累积更新从 Lync Server 2010 更改所有客户端的 DNS 位置进程，DNS 查询过程将继续，直到返回成功的查询，或者可能的 DNS 记录的列表已用完，最后一个错误将返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="3ef88-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="3ef88-124">对于在 DNS 查找期间除 Lync Windows 应用商店应用**之外**的所有客户端，将按以下顺序查询和返回到客户端的 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="3ef88-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="3ef88-125">lyncdiscoverinternal.\<内部\> Web 服务上的自动发现服务的域 A （主机）记录</span><span class="sxs-lookup"><span data-stu-id="3ef88-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="3ef88-126">lyncdiscover.\<外部\> Web 服务上的自动发现服务的域 A （主机）记录</span><span class="sxs-lookup"><span data-stu-id="3ef88-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="3ef88-127">\_sipinternaltls.\_tcp。\<内部\> TLS 连接的域 SRV （服务定位器）记录</span><span class="sxs-lookup"><span data-stu-id="3ef88-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="3ef88-128">\_sipinternal.\_tcp。\<内部\> TCP 连接的域 SRV （服务定位器）记录（仅在允许 TCP 时执行）</span><span class="sxs-lookup"><span data-stu-id="3ef88-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="3ef88-129">\_sip.\_tls。\<外部\> TLS 连接的域 SRV （服务定位器）记录</span><span class="sxs-lookup"><span data-stu-id="3ef88-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="3ef88-130">sipinternal.\<前端\>池或控制器的域 A （主机）记录，仅在内部网络上可解析</span><span class="sxs-lookup"><span data-stu-id="3ef88-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="3ef88-131">sip.\<用于\>内部网络的前端池或控制器的域 A （主机）记录，或者当客户端为外部客户端时的访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="3ef88-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="3ef88-132">sipexternal.\<当\>客户端为外部客户端时，Access Edge 服务的域 A （主机）记录</span><span class="sxs-lookup"><span data-stu-id="3ef88-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="3ef88-133">Lync Windows 应用商店应用将完全更改该过程，因为它使用两个记录：</span><span class="sxs-lookup"><span data-stu-id="3ef88-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="3ef88-134">lyncdiscoverinternal.\<内部\> Web 服务上的自动发现服务的域 A （主机）记录</span><span class="sxs-lookup"><span data-stu-id="3ef88-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="3ef88-135">lyncdiscover.\<外部\> Web 服务上的自动发现服务的域 A （主机）记录</span><span class="sxs-lookup"><span data-stu-id="3ef88-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="3ef88-136">不回退到其他记录类型。</span><span class="sxs-lookup"><span data-stu-id="3ef88-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="3ef88-137">用于较新客户端和较旧客户端的方法的区别在于，自动发现服务将成为定位所有服务的首选方法。</span><span class="sxs-lookup"><span data-stu-id="3ef88-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="3ef88-138">连接成功后，自动发现服务将返回用户的主池的所有 Web 服务 Url，包括移动服务（称为 Mcx 由在 IIS 中为该服务创建的虚拟目录）、Microsoft Lync Web App 和 Web 计划程序 Url。</span><span class="sxs-lookup"><span data-stu-id="3ef88-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="3ef88-139">但是，内部 Mobility Service URL 和外部 Mobility Service URL 都与外部 Web 服务 FQDN 关联。</span><span class="sxs-lookup"><span data-stu-id="3ef88-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="3ef88-140">因此，不管移动设备是在网络内部还是外部，该设备都始终从外部通过反向代理连接到 Mobility Service。</span><span class="sxs-lookup"><span data-stu-id="3ef88-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="3ef88-141">如果 Lync Server 2013 的累积更新：已安装2月2013，则自动发现服务还返回对 Internal/UCWA、External/UCWA 和 UCWA 的引用。</span><span class="sxs-lookup"><span data-stu-id="3ef88-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="3ef88-142">这些条目是指统一通信 Web API (UCWA) Web 组件。</span><span class="sxs-lookup"><span data-stu-id="3ef88-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="3ef88-143">目前，只使用条目 UCWA，它提供对该 Web 组件 URL 的引用。</span><span class="sxs-lookup"><span data-stu-id="3ef88-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="3ef88-144">UCWA 由 Lync 2013 移动客户端使用，而不是 Lync 2010 移动客户端使用的 Mcx 移动服务。</span><span class="sxs-lookup"><span data-stu-id="3ef88-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ef88-145">创建 SRV 记录时，请务必记住，这些记录必须指向在其中创建了 DNS SRV 记录的同一域中的 DNS A 和 AAAA（如果您使用的是 IPv6 寻址）记录。</span><span class="sxs-lookup"><span data-stu-id="3ef88-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="3ef88-146">例如，如果 SRV 记录在 contoso.com 中，则 A 和 AAAA （如果你使用的是 IPv6 寻址）记录指向的不能在 fabrikam.com 中。</span><span class="sxs-lookup"><span data-stu-id="3ef88-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="3ef88-147">默认配置是使所有移动客户端流量通过外部网站。</span><span class="sxs-lookup"><span data-stu-id="3ef88-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="3ef88-148">您可以修改设置，以便仅返回内部 URL（如果这更符合您的需求）。</span><span class="sxs-lookup"><span data-stu-id="3ef88-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="3ef88-149">在此配置下，仅当用户位于企业网络内部时才能在其移动设备上使用 Lync 移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="3ef88-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="3ef88-150">若要定义此配置，需要使用 <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3ef88-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3ef88-151">虽然移动应用程序也可以连接到其他 Lync Server 2013 服务（如通讯簿服务），但内部移动应用程序 web 请求仅转到移动服务的外部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="3ef88-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="3ef88-152">其他服务请求（如通讯簿请求）不需要此配置。</span><span class="sxs-lookup"><span data-stu-id="3ef88-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="3ef88-p110">移动设备支持手动发现服务。在此情况下，每个用户必须使用整个内部和外部自动发现服务 URI（包括协议和路径）配置移动设备设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ef88-p110">Mobile devices support manual discovery of services. In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="3ef88-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="3ef88-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="3ef88-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root，用于内部访问</span><span class="sxs-lookup"><span data-stu-id="3ef88-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="3ef88-157">建议使用自动发现而非手动发现。</span><span class="sxs-lookup"><span data-stu-id="3ef88-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="3ef88-158">但是，手动设置对解决移动设备连接问题很有用。</span><span class="sxs-lookup"><span data-stu-id="3ef88-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="3ef88-159">配置与 Lync Server 的分裂的 DNS</span><span class="sxs-lookup"><span data-stu-id="3ef88-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="3ef88-p112">拆分式 DNS 以名称编号得名，例如，拆分 DNS 或水平拆分 DNS。它仅仅描述其中具有相同命名空间的两个 DNS 区域（其中一个 DNS 区域仅为内部请求提供服务，而另一个 DNS 区域仅为外部请求提供服务）的 DNS 配置。但是，内部 DNS 所包含的许多 DNS SRV 和 A 记录不包含在外部 DNS 中，反之亦然。如果内部和外部 DNS 中存在相同的 DNS 记录（例如，www.contoso.com），则根据启动 DNS 查询的位置（内部或外部）不同，返回的 IP 地址也将不同。</span><span class="sxs-lookup"><span data-stu-id="3ef88-p112">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS. Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests. However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true. In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ef88-p113">当前，移动性（或者更具体讲，LyncDiscover 和 LyncDiscoverInternal DNS 记录）不支持拆分式 DNS。必须在外部 DNS 服务器上定义 LyncDiscover，在内部 DNS 服务器上定义 LyncDiscoverInternal。</span><span class="sxs-lookup"><span data-stu-id="3ef88-p113">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records. LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="3ef88-166">出于这些主题的目的，将使用术语“拆分式 DNS”。</span><span class="sxs-lookup"><span data-stu-id="3ef88-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="3ef88-167">如果要配置拆分式 DNS，以下内部和外部区域包含每个区域所需的 DNS 记录类型的摘要。</span><span class="sxs-lookup"><span data-stu-id="3ef88-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="3ef88-168">有关详细信息，请参阅[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3ef88-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="3ef88-169">**内部 DNS：**</span><span class="sxs-lookup"><span data-stu-id="3ef88-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="3ef88-170">包含名为 contoso.com 且受其管辖的 DNS 区域</span><span class="sxs-lookup"><span data-stu-id="3ef88-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="3ef88-171">内部 contoso.com 区域包含：</span><span class="sxs-lookup"><span data-stu-id="3ef88-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="3ef88-172">DNS A 和 AAAA （如果使用 IPv6 寻址）和内部 Lync Server 2013 客户端自动配置的 SRV 记录（可选）</span><span class="sxs-lookup"><span data-stu-id="3ef88-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="3ef88-173">DNS A 和 AAAA （如果使用 IPv6 寻址）或用于自动发现 Lync Server 2013 Web 服务的 CNAME 记录（可选）</span><span class="sxs-lookup"><span data-stu-id="3ef88-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="3ef88-174">DNS A 和 AAAA （如果使用 IPv6 寻址）记录的前端池名称、Director 或控制器池名称，以及在企业网络中运行 Lync Server 2013 的所有内部服务器</span><span class="sxs-lookup"><span data-stu-id="3ef88-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="3ef88-175">DNS A 和 AAAA （如果你正在使用 IPv6 寻址）针对外围网络中每个 Lync Server 2013 和 Edge 服务器的边缘内部接口的记录</span><span class="sxs-lookup"><span data-stu-id="3ef88-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="3ef88-176">外围网络中每台反向代理服务器的内部接口的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）记录（仅对反向代理的管理是可选的）</span><span class="sxs-lookup"><span data-stu-id="3ef88-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="3ef88-177">外围网络中的所有 Lync Server 2013 Edge 服务器内部边缘接口使用内部 DNS 区域将查询解析为 contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="3ef88-178">在企业网络中运行 lync Server 2013 和运行 Lync 2013 的客户端的所有服务器指向内部 DNS 服务器，以便将查询解析到 contoso.com 或在每台边缘服务器上使用 HOSTS 文件，并列出 A 和 AAAA （如果使用 IPv6 寻址）记录下一跃点服务器，特别是 Director 或 Director VIP、前端池 VIP 或标准版服务器</span><span class="sxs-lookup"><span data-stu-id="3ef88-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="3ef88-179">**外部 DNS：**</span><span class="sxs-lookup"><span data-stu-id="3ef88-179">**External DNS:**</span></span>

  - <span data-ttu-id="3ef88-180">包含名为 contoso.com 且受其管辖的 DNS 区域</span><span class="sxs-lookup"><span data-stu-id="3ef88-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="3ef88-181">外部 contoso.com 区域包含：</span><span class="sxs-lookup"><span data-stu-id="3ef88-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="3ef88-182">DNS A 和 AAAA （如果使用 IPv6 寻址）和 Lync Server 2013 客户端自动配置的 SRV 记录（可选）</span><span class="sxs-lookup"><span data-stu-id="3ef88-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="3ef88-183">DNS A 和 AAAA （如果使用 IPv6 寻址）或 CNAME 记录，用于自动发现 Lync Server 2013 Web 服务以与移动版一起使用</span><span class="sxs-lookup"><span data-stu-id="3ef88-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="3ef88-184">DNS A 和 AAAA （如果正在使用 IPv6 寻址）和适用于外围网络中每个 Lync Server 2013、Edge 服务器或硬件负载平衡器虚拟 IP （VIP）的边缘外部接口的 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="3ef88-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="3ef88-185">外围网络中反向代理服务器的外部接口的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）记录或反向代理服务器池的 VIP</span><span class="sxs-lookup"><span data-stu-id="3ef88-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="3ef88-186">没有拆分式 DNS 时的自动配置</span><span class="sxs-lookup"><span data-stu-id="3ef88-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="3ef88-187">如果内部 DNS 区域包含\_sipinternaltls，则使用 "分裂" DNS，登录内部的 Lync Server 2013 用户可以利用自动配置。\_正在使用的每个 SIP 域的 tcp SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="3ef88-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="3ef88-188">但是，如果您不使用分裂的 DNS，则运行 Lync 的客户端的内部自动配置将不起作用，除非实施本部分后面部分中所述的解决方法之一。</span><span class="sxs-lookup"><span data-stu-id="3ef88-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="3ef88-189">这是因为 Lync Server 2013 要求用户的 SIP URI 与为自动配置指定的前端池的域匹配。</span><span class="sxs-lookup"><span data-stu-id="3ef88-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="3ef88-190">这也是早期版本的 Communicator 的情况。</span><span class="sxs-lookup"><span data-stu-id="3ef88-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="3ef88-191">例如，如果正在使用两个 SIP 域，则需要以下 DNS 服务 (SRV) 记录：</span><span class="sxs-lookup"><span data-stu-id="3ef88-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="3ef88-192">如果用户使用 bob@contoso.com 登录，由于用户的 SIP 域 (contoso.com) 与自动配置前端池的域相匹配，因此，以下 SRV 记录将用于自动配置：</span><span class="sxs-lookup"><span data-stu-id="3ef88-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="3ef88-193">\_sipinternaltls.\_tcp.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3ef88-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="3ef88-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="3ef88-195">如果用户使用 alice@fabrikam.com 登录，则以下 DNS SRV 记录将用于第二个 SIP 域的自动配置。</span><span class="sxs-lookup"><span data-stu-id="3ef88-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="3ef88-196">\_sipinternaltls.\_tcp.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="3ef88-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="3ef88-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="3ef88-198">与此相对，如果用户使用 tim@litwareinc.com 登录，则以下 DNS SRV 记录不会用于自动配置，因为客户端的 SIP 域 (litwareinc.com) 与池所在的域 (fabrikam.com) 不匹配：</span><span class="sxs-lookup"><span data-stu-id="3ef88-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="3ef88-199">\_sipinternaltls.\_tcp.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="3ef88-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="3ef88-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="3ef88-201">如果运行 Lync 的客户端需要 "自动配置"，请选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="3ef88-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="3ef88-202">**组策略对象**   使用组策略对象（gpo）填充正确的服务器值。</span><span class="sxs-lookup"><span data-stu-id="3ef88-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ef88-203">此选项不会启用自动配置，但可以自动化手动配置的过程，因此，使用这种方法时不需要与自动配置关联的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="3ef88-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="3ef88-204">**匹配的内部区域**   在内部 DNS 中创建与外部 dns 区域匹配的区域（例如 contoso.com），并创建 DNS a 和 AAAA （如果你使用的是用于自动配置的 Lync Server 2013 池）的 dns a 和 AAAA （如果你使用的是 IPv6 寻址）记录。</span><span class="sxs-lookup"><span data-stu-id="3ef88-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="3ef88-205">例如，如果用户托管在 pool01.contoso.net 上，但在 bob@contoso.com 中登录 Lync，请创建名为 contoso.com 的内部 DNS 区域，并在其中创建一个名为的内部 DNS 区域（如果使用 IPv6 寻址）记录，请创建 pool01.contoso.com 的 DNS A 和 AAAA。</span><span class="sxs-lookup"><span data-stu-id="3ef88-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="3ef88-206">**固定点内部区域**   如果在内部 DNS 中创建整个区域不是一个选项，则可以创建与自动配置所需的 SRV 记录相对应的 pin 点（即专用）区域，并使用 dnscmd 填充这些区域。</span><span class="sxs-lookup"><span data-stu-id="3ef88-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="3ef88-207">Dnscmd 是必需的，因为 DNS 用户界面不支持创建固定点区域。</span><span class="sxs-lookup"><span data-stu-id="3ef88-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="3ef88-208">例如，如果 SIP 域为 contoso.com，并且你有一个名为 pool01 的前端池，该池包含两个前端服务器，则你需要内部 DNS 中的以下 pin 点区域和记录：</span><span class="sxs-lookup"><span data-stu-id="3ef88-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="3ef88-209">如果环境中包含第二个 SIP 域（例如，fabrikam.com），则内部 DNS 中需要以下精确区域和 A 记录：</span><span class="sxs-lookup"><span data-stu-id="3ef88-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="3ef88-210">前端池 FQDN 出现两次，但两次的 IP 地址不同。</span><span class="sxs-lookup"><span data-stu-id="3ef88-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="3ef88-211">这是因为使用了 DNS 负载平衡，但如果使用硬件负载平衡，则只有一个前端池条目。</span><span class="sxs-lookup"><span data-stu-id="3ef88-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="3ef88-212">并且，前端池 FQDN 值因 contoso.com 示例和 fabrikam.com 示例的不同而变化，但 IP 地址保持不变。</span><span class="sxs-lookup"><span data-stu-id="3ef88-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="3ef88-213">这是因为用户从任一 SIP 域登录，所以使用相同的前端池进行自动配置。</span><span class="sxs-lookup"><span data-stu-id="3ef88-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="3ef88-214">有关详细信息，请参阅 DMTF 博客文章 "Communicator 自动配置和分裂的 DNS" [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)。</span><span class="sxs-lookup"><span data-stu-id="3ef88-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ef88-215">每个博客的内容及其 URL 如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="3ef88-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="3ef88-216">为灾难恢复配置域名系统 (DNS)</span><span class="sxs-lookup"><span data-stu-id="3ef88-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="3ef88-217">若要将 DNS 配置为将 Lync Server 2013 Web 流量重定向到你的灾难恢复和故障转移网站，你必须使用支持 GeoDNS 的 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="3ef88-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="3ef88-218">你可以设置 Web 的 DNS 记录以支持灾难恢复，因此即使一个完整的前端池停机，使用 Web 服务的功能仍继续。</span><span class="sxs-lookup"><span data-stu-id="3ef88-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="3ef88-219">此灾难恢复功能支持自动发现 (Lyncdiscover URL)、会议和拨入式简单 URL。</span><span class="sxs-lookup"><span data-stu-id="3ef88-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="3ef88-p123">您可以在 GeoDNS 提供程序上为 Web 服务的内部和外部解决方案定义和配置其他 DNS 主机（如果使用的是 IPv6 地址，则为 A 和 AAAA）记录。以下详细信息假定池已配对，地理位置分散，且 GeoDNS 支持的提供程序使用循环 DNS 或被配置为使用 Pool1 作为主池，并且在发生通信丢失或硬件失败时故障转移到 Pool2。</span><span class="sxs-lookup"><span data-stu-id="3ef88-p123">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider. The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ef88-222">GeoDNS 记录（示例）</span><span class="sxs-lookup"><span data-stu-id="3ef88-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="3ef88-223">池记录（示例）</span><span class="sxs-lookup"><span data-stu-id="3ef88-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="3ef88-224">CNAME 记录（示例）</span><span class="sxs-lookup"><span data-stu-id="3ef88-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="3ef88-225">DNS 设置（选择一个选项）</span><span class="sxs-lookup"><span data-stu-id="3ef88-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ef88-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-229">Pool1InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-230">Pool2InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-231">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="3ef88-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="3ef88-232">使用主映像，如果失败则连接到辅助</span><span class="sxs-lookup"><span data-stu-id="3ef88-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ef88-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-236">Pool1ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-237">Pool2ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-238">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="3ef88-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="3ef88-239">使用主映像，如果失败则连接到辅助</span><span class="sxs-lookup"><span data-stu-id="3ef88-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ef88-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-243">Pool1InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-244">Pool2InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-245">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="3ef88-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="3ef88-246">使用主映像，如果失败则连接到辅助</span><span class="sxs-lookup"><span data-stu-id="3ef88-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ef88-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-250">Pool1ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-251">Pool2ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-252">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="3ef88-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="3ef88-253">使用主映像，如果失败则连接到辅助</span><span class="sxs-lookup"><span data-stu-id="3ef88-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ef88-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-257">Pool1InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-258">Pool2InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-259">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="3ef88-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="3ef88-260">使用主映像，如果失败则连接到辅助</span><span class="sxs-lookup"><span data-stu-id="3ef88-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ef88-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-264">Pool1ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-265">Pool2ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-266">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="3ef88-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="3ef88-267">使用主映像，如果失败则连接到辅助</span><span class="sxs-lookup"><span data-stu-id="3ef88-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ef88-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-271">Pool1InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-272">Pool2InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-273">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="3ef88-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="3ef88-274">使用主映像，如果失败则连接到辅助</span><span class="sxs-lookup"><span data-stu-id="3ef88-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ef88-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3ef88-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-278">Pool1ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="3ef88-279">Pool2ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</span><span class="sxs-lookup"><span data-stu-id="3ef88-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3ef88-280">在池之间启用循环</span><span class="sxs-lookup"><span data-stu-id="3ef88-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="3ef88-281">使用主映像，如果失败则连接到辅助</span><span class="sxs-lookup"><span data-stu-id="3ef88-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="3ef88-282">DNS Load Balancing</span><span class="sxs-lookup"><span data-stu-id="3ef88-282">DNS Load Balancing</span></span>

<span data-ttu-id="3ef88-283">DNS 负载平衡通常在应用程序级别实现。</span><span class="sxs-lookup"><span data-stu-id="3ef88-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="3ef88-284">应用程序（例如，运行 Lync 的客户端）通过连接到池完全限定的域名（FQDN）的 DNS A 和 AAAA （如果使用 IPv6 寻址）记录查询来连接到池中的某个服务器，尝试连接到池中的服务器。</span><span class="sxs-lookup"><span data-stu-id="3ef88-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="3ef88-285">例如，如果一个名为 pool01.contoso.com 的池中有三个前端服务器，则将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="3ef88-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="3ef88-286">运行 Lync 的 pool01.contoso.com 查询 DNS 的客户端。</span><span class="sxs-lookup"><span data-stu-id="3ef88-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="3ef88-287">该查询返回三个 IP 地址并将其缓存，如下所示（不必按此顺序）：</span><span class="sxs-lookup"><span data-stu-id="3ef88-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="3ef88-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="3ef88-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="3ef88-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="3ef88-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="3ef88-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="3ef88-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="3ef88-291">客户端尝试建立与其中一个 IP 地址的传输控制协议（TCP）连接。</span><span class="sxs-lookup"><span data-stu-id="3ef88-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="3ef88-292">如果此操作失败，客户端将尝试缓存中的下一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3ef88-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="3ef88-293">如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。</span><span class="sxs-lookup"><span data-stu-id="3ef88-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="3ef88-294">如果客户在未成功连接的情况下尝试所有缓存的条目，则系统将通知用户目前没有运行 Lync Server 2013 的服务器。</span><span class="sxs-lookup"><span data-stu-id="3ef88-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ef88-295">基于 DNS 的负载平衡不同于 DNS 循环（DNS RR），它通常指的是负载平衡，具体取决于 DNS 以提供与池中的服务器对应的不同 IP 地址顺序。</span><span class="sxs-lookup"><span data-stu-id="3ef88-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="3ef88-296">通常，DNS RR 仅支持负载分配，但不支持故障转移。</span><span class="sxs-lookup"><span data-stu-id="3ef88-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="3ef88-297">例如，如果连接到 DNS A 和 AAAA 返回的一个 IP 地址（如果使用的是 IPv6 寻址）查询失败，连接将失败。</span><span class="sxs-lookup"><span data-stu-id="3ef88-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="3ef88-298">因此，DNS 循环复用本身比基于 DNS 的负载平衡的可靠性更低。</span><span class="sxs-lookup"><span data-stu-id="3ef88-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="3ef88-299">你可以将 DNS 循环与 DNS 负载平衡结合使用。</span><span class="sxs-lookup"><span data-stu-id="3ef88-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="3ef88-300">DNS 负载平衡用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="3ef88-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="3ef88-301">将服务器到服务器 SIP 负载平衡到边缘服务器</span><span class="sxs-lookup"><span data-stu-id="3ef88-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="3ef88-302">负载平衡统一通信应用程序服务（UCAS）应用程序，如会议自动助理、响应组和呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="3ef88-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="3ef88-303">阻止新连接 UCAS 应用程序（也称为 "排出"）</span><span class="sxs-lookup"><span data-stu-id="3ef88-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="3ef88-304">负载平衡客户端和边缘服务器之间的所有客户端到服务器流量</span><span class="sxs-lookup"><span data-stu-id="3ef88-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="3ef88-305">无法将 DNS 负载平衡用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="3ef88-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="3ef88-306">客户端到服务器 web 流量到控制器或前端服务器</span><span class="sxs-lookup"><span data-stu-id="3ef88-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="3ef88-307">DNS 负载平衡和联合通信：</span><span class="sxs-lookup"><span data-stu-id="3ef88-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="3ef88-308">如果 DNS SRV 查询返回多个 DNS 记录，则 Access Edge 服务始终使用最小的数值优先级和最高的数字权重来选取 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="3ef88-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="3ef88-309">Internet 工程任务组文档 "用于指定服务位置的 DNS RR （DNS SRV）" <http://www.ietf.org/rfc/rfc2782.txt>指定如果定义了多个 DNS SRV 记录，将首先使用 "优先级"，然后按 "重量"。</span><span class="sxs-lookup"><span data-stu-id="3ef88-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="3ef88-310">例如，DNS SRV 记录 A 的权重为20，优先级为40，DNS SRV 记录 B 的权重为10，优先级为50。</span><span class="sxs-lookup"><span data-stu-id="3ef88-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="3ef88-311">将选择优先级为40的 DNS SRV 记录 A。</span><span class="sxs-lookup"><span data-stu-id="3ef88-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="3ef88-312">以下规则适用于 DNS SRV 记录选择：</span><span class="sxs-lookup"><span data-stu-id="3ef88-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="3ef88-313">首先考虑优先级。</span><span class="sxs-lookup"><span data-stu-id="3ef88-313">Priority is considered first.</span></span> <span data-ttu-id="3ef88-314">客户端必须尝试联系由 DNS SRV 记录定义的目标主机，该目标主机可以访问的最低优先级。</span><span class="sxs-lookup"><span data-stu-id="3ef88-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="3ef88-315">应按照权重字段定义的顺序尝试具有相同优先级的目标。</span><span class="sxs-lookup"><span data-stu-id="3ef88-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="3ef88-316">"权重" 域为具有相同优先级的条目指定相对权重。</span><span class="sxs-lookup"><span data-stu-id="3ef88-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="3ef88-317">应按比例增加所选的概率。</span><span class="sxs-lookup"><span data-stu-id="3ef88-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="3ef88-318">当没有任何服务器选择要执行时，DNS 管理员应使用权重0。</span><span class="sxs-lookup"><span data-stu-id="3ef88-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="3ef88-319">如果记录包含的权重大于0，则权重为0的记录应具有非常小的选择机会。</span><span class="sxs-lookup"><span data-stu-id="3ef88-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="3ef88-320">如果返回具有相同优先级和权重的多个 DNS SRV 记录，则 Access Edge 服务将选择首先从 DNS 服务器接收的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="3ef88-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

