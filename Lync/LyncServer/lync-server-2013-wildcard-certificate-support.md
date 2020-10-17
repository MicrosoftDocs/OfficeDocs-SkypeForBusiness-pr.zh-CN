---
title: Lync Server 2013 通配符证书支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d639ba422bde7b936bd58ff58abae47ea365bb70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508519"
---
# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="a21c8-102">Lync Server 2013 中的通配符证书支持</span><span class="sxs-lookup"><span data-stu-id="a21c8-102">Wildcard certificate support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a21c8-103">_**上次修改的主题：** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="a21c8-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="a21c8-104">Lync Server 2013 使用证书提供通信加密和服务器身份身份验证。</span><span class="sxs-lookup"><span data-stu-id="a21c8-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="a21c8-105">在某些情况下，如通过反向代理的 Web 发布，不需要使用与提供服务的服务器的完全限定域名 (FQDN) 匹配的强主题备用名称 (SAN) 项。</span><span class="sxs-lookup"><span data-stu-id="a21c8-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="a21c8-106">在这些情况下，可以使用具有通配符 SAN 项（通常称为“通配符证书”）的证书来减少从公共证书颁发机构请求证书的成本，并降低证书规划流程的复杂性。</span><span class="sxs-lookup"><span data-stu-id="a21c8-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a21c8-107">若要保留统一通信 (UC) 设备（例如，桌面电话）的功能，您应该小心测试已部署的证书，确保设备在实施通配符证书后可以正常运行。</span><span class="sxs-lookup"><span data-stu-id="a21c8-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="a21c8-p102">不支持使用通配符项作为任何角色的主题名称（也称为公用名或 CN）。使用 SAN 中的通配符项时支持以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="a21c8-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="a21c8-110">**反向代理。**    通配符 SAN 条目受简单 URL 支持， () 发布证书的符合和拨出。</span><span class="sxs-lookup"><span data-stu-id="a21c8-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="a21c8-111">**反向代理。**    对于发布证书上的 Lyncdiscover. 的 SAN 条目，支持通配符 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="a21c8-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="a21c8-112">**导演。**    通配符 SAN 条目受简单 Url 支持， () 和在控制器 web 组件中拨入和 Lyncdiscoverinternal. 的 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="a21c8-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="a21c8-113">**前端服务器 (Standard Edition) 和前端池 (Enterprise Edition) 。**</span><span class="sxs-lookup"><span data-stu-id="a21c8-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="a21c8-114">通配符 SAN 条目受简单 Url 支持， () 和为前端 web 组件中的 Lyncdiscover. 和 Lyncdiscoverinternal. 的 SAN 条目进行和拨入。</span><span class="sxs-lookup"><span data-stu-id="a21c8-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="a21c8-115">**Exchange 统一消息 (UM) 。**    在作为独立服务器部署时，服务器不使用 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="a21c8-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="a21c8-116">**Microsoft Exchange Server 客户端访问服务器。**    SAN 中的通配符条目支持内部和外部客户端。</span><span class="sxs-lookup"><span data-stu-id="a21c8-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="a21c8-117">**Exchange 统一消息 (UM) 和同一台服务器上的 Microsoft Exchange Server 客户端访问服务器。**    支持通配符 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="a21c8-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="a21c8-118">该主题中未提到的服务器角色：</span><span class="sxs-lookup"><span data-stu-id="a21c8-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="a21c8-119">内部服务器角色 (包括但不限于中介服务器、存档和监控服务器、Survivable 分支设备或 Survivable 分支服务器) </span><span class="sxs-lookup"><span data-stu-id="a21c8-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="a21c8-120">外部边缘服务器接口</span><span class="sxs-lookup"><span data-stu-id="a21c8-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="a21c8-121">内部边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a21c8-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a21c8-122">对于内部边缘服务器接口，可以将通配符项分配给 SAN 并支持它。</span><span class="sxs-lookup"><span data-stu-id="a21c8-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="a21c8-123">不会查询内部边缘服务器上的 SAN，并且通配符 SAN 条目的值有限。</span><span class="sxs-lookup"><span data-stu-id="a21c8-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="a21c8-124">有关证书配置的详细信息（包括证书中的通配符使用），请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a21c8-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="a21c8-125">Lync Server 2013 中的内部服务器的证书要求</span><span class="sxs-lookup"><span data-stu-id="a21c8-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="a21c8-126">Lync Server 2013 中的外部用户访问的证书要求</span><span class="sxs-lookup"><span data-stu-id="a21c8-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="a21c8-127">Lync Server 2013 中的证书摘要-DNS 和 HLB 负载平衡</span><span class="sxs-lookup"><span data-stu-id="a21c8-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="a21c8-128">证书摘要-Lync Server 2013 中的单个控制器</span><span class="sxs-lookup"><span data-stu-id="a21c8-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="a21c8-129">Lync Server 2013 中的证书摘要-扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="a21c8-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="a21c8-130">Lync Server 2013 中的证书摘要-反向代理</span><span class="sxs-lookup"><span data-stu-id="a21c8-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="a21c8-131">集成本地统一消息和 Lync Server 2013 的准则</span><span class="sxs-lookup"><span data-stu-id="a21c8-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="a21c8-132">有关为 Exchange 配置证书的详细信息，包括通配符的使用，请参阅 Exchange 2013 产品文档。</span><span class="sxs-lookup"><span data-stu-id="a21c8-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

