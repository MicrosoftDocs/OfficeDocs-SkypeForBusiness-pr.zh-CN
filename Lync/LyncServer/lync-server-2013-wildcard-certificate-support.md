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
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="58927-102">Lync Server 2013 中的通配符证书支持</span><span class="sxs-lookup"><span data-stu-id="58927-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58927-103">_**主题上次修改时间：** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="58927-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="58927-104">Lync Server 2013 使用证书提供通信加密和服务器身份身份验证。</span><span class="sxs-lookup"><span data-stu-id="58927-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="58927-105">在某些情况下（例如，通过反向代理的 web 发布），与提供该服务的服务器的完全限定的域名（FQDN）匹配的强主题备用名称（SAN）条目不是必需的。</span><span class="sxs-lookup"><span data-stu-id="58927-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="58927-106">在这些情况下，你可以将证书用于通配符 SAN 条目（通常称为 "通配证书"）以减少从公共证书颁发机构请求的证书的费用，并降低证书的规划过程的复杂性.</span><span class="sxs-lookup"><span data-stu-id="58927-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="58927-107">若要保留统一通信（UC）设备（如桌面电话）的功能，应仔细测试部署的证书，以确保设备在你实现通配符证书后正常工作。</span><span class="sxs-lookup"><span data-stu-id="58927-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="58927-108">不支持通配符条目作为任何角色的主题名称（也称为公用名称或 CN）。</span><span class="sxs-lookup"><span data-stu-id="58927-108">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role.</span></span> <span data-ttu-id="58927-109">在 SAN 中使用通配符条目时，支持以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="58927-109">The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="58927-110">**反向代理。**   对于简单 URL （"满足" 和 "拨入"）发布证书，支持通配符 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="58927-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="58927-111">**反向代理。**   LyncDiscover 发布证书上的 san 条目支持通配符 san 条目。</span><span class="sxs-lookup"><span data-stu-id="58927-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="58927-112">**导演。**   对于简单的 url （"满足" 和 "拨入"）以及用于 LyncDiscover 和 LyncDiscoverInternal web 组件的 SAN 条目，均支持通配符 san 条目。</span><span class="sxs-lookup"><span data-stu-id="58927-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="58927-113">**前端服务器（标准版）和前端池（企业版）。**</span><span class="sxs-lookup"><span data-stu-id="58927-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="58927-114">对于简单 Url （"满足" 和 "拨入"）以及 LyncDiscover 和 LyncDiscoverInternal （前端 web 组件）的 SAN 条目，均支持通配符 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="58927-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="58927-115">**Exchange 统一消息（UM）。**   在作为独立服务器部署时，服务器不使用 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="58927-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="58927-116">**Microsoft Exchange Server 客户端访问服务器。**   SAN 中的通配符条目支持内部和外部客户端。</span><span class="sxs-lookup"><span data-stu-id="58927-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="58927-117">**Exchange 统一消息（UM）和同一台服务器上的 Microsoft Exchange Server 客户端访问服务器。**   支持通配符 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="58927-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="58927-118">本主题中未解决的服务器角色：</span><span class="sxs-lookup"><span data-stu-id="58927-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="58927-119">内部服务器角色（包括但不限于中介服务器、存档和监视服务器、Survivable 分支装置或 Survivable 分支服务器）</span><span class="sxs-lookup"><span data-stu-id="58927-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="58927-120">外部边缘服务器接口</span><span class="sxs-lookup"><span data-stu-id="58927-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="58927-121">内部边缘服务器</span><span class="sxs-lookup"><span data-stu-id="58927-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58927-122">对于内部边缘服务器接口，可以将通配符条目分配给 SAN，并且受支持。</span><span class="sxs-lookup"><span data-stu-id="58927-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="58927-123">不会查询内部边缘服务器上的 SAN，并且通配符 SAN 条目的价值有限。</span><span class="sxs-lookup"><span data-stu-id="58927-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="58927-124">有关证书配置的详细信息（包括在证书中使用通配符），请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="58927-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="58927-125">Lync Server 2013 中内部服务器的证书要求</span><span class="sxs-lookup"><span data-stu-id="58927-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="58927-126">Lync Server 2013 中外部用户访问的证书要求</span><span class="sxs-lookup"><span data-stu-id="58927-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="58927-127">Lync Server 2013 中的证书摘要 - 已进行 DNS 和 HLB 负载平衡</span><span class="sxs-lookup"><span data-stu-id="58927-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="58927-128">Lync Server 2013 中的证书摘要 - 单一控制器</span><span class="sxs-lookup"><span data-stu-id="58927-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="58927-129">Lync Server 2013 中的证书摘要 - 扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="58927-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="58927-130">Lync Server 2013 中的证书摘要 - 反向代理</span><span class="sxs-lookup"><span data-stu-id="58927-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="58927-131">集成本地统一消息与 Lync Server 2013 的指南</span><span class="sxs-lookup"><span data-stu-id="58927-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="58927-132">有关配置 Exchange 证书的详细信息（包括通配符使用），请参阅 Exchange 2013 产品文档。</span><span class="sxs-lookup"><span data-stu-id="58927-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

