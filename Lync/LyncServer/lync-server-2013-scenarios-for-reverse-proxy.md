---
title: Lync Server 2013：反向代理方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1621e8bb0241e82f9f4678d4fe39a4f66f6bcf9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="04077-102">Lync Server 2013 中的反向代理方案</span><span class="sxs-lookup"><span data-stu-id="04077-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04077-103">_**主题上次修改时间:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="04077-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="04077-104">Lync Server 2013 中需要 "反向代理", 以便提供对服务和资源的访问权限, 例如会议和电话拨入式简单 Url、通讯簿、会议内容、通讯组列表扩展、移动服务等。</span><span class="sxs-lookup"><span data-stu-id="04077-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="04077-105">Lync Server 2013 中的典型反向代理方案是允许外部客户端 (例如, 桌面客户端或 Lync Web App 客户端) 访问 Director 或前端服务器外部 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="04077-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="04077-106">**反向代理和外部 web 服务**</span><span class="sxs-lookup"><span data-stu-id="04077-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="04077-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="04077-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="04077-108">在计划阶段, 在 Lync Server 2013 部署中定义反向代理的要求。</span><span class="sxs-lookup"><span data-stu-id="04077-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="04077-109">反向代理启用以下外部客户端的功能访问:</span><span class="sxs-lookup"><span data-stu-id="04077-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="04077-110">Microsoft Lync 2013 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="04077-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="04077-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="04077-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="04077-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="04077-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="04077-113">Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="04077-113">Lync Windows Store app</span></span>

<span data-ttu-id="04077-114">规划 Lync Server 2013 部署时, 将 Lync Server 2013 的实际要求映射到反向代理功能。</span><span class="sxs-lookup"><span data-stu-id="04077-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="04077-115">外部客户端将连接到端口 TCP 443 上的反向代理, 并且将使用安全套接字层 (SSL) 或传输层安全 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="04077-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="04077-116">Microsoft Lync 移动客户端可以连接到 TCP 80, 但仅在执行与 Lync 探索服务的初始连接时, 并且管理员已配置了正确的域名系统 (DNS) CNAME (或别名) 记录, 并接受此将不会加密通信。</span><span class="sxs-lookup"><span data-stu-id="04077-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="04077-117">Lync Server 2013 外部 web 服务 (部署在前端服务器和/或控制器上) 期望通过端口 TCP 4443 上的反向代理建立连接, 并且预期连接将是 SSL/TLS。</span><span class="sxs-lookup"><span data-stu-id="04077-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="04077-118">用于外部 web 服务的建议默认侦听端口为 HTTP 流量的 TCP 8080, 而 TCP 流量为 TCP 4443。</span><span class="sxs-lookup"><span data-stu-id="04077-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="04077-119">拓扑生成器提供了一种替代默认设置和定义你自己的外部 web 服务侦听端口的机会。</span><span class="sxs-lookup"><span data-stu-id="04077-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="04077-120">请务必注意, 反向代理与外部 web 服务进行通信, 并且外部客户端与反向代理通信。</span><span class="sxs-lookup"><span data-stu-id="04077-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="04077-121">外部客户端与端口 TCP 443 上的反向代理通信, 但你可以重新定义反向代理与的外部 web 服务进行通信的端口。</span><span class="sxs-lookup"><span data-stu-id="04077-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="04077-122">拓扑生成器中用于替代 web 服务的默认侦听端口的选项使你能够解决基础结构中可能出现的侦听端口冲突。</span><span class="sxs-lookup"><span data-stu-id="04077-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="04077-123">Lync Server 2013 外部 web 服务需要来自客户端的未修改的主机标头来标识客户端尝试使用的服务和 web 服务器目录。</span><span class="sxs-lookup"><span data-stu-id="04077-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="04077-124">请求应类似于来自反向代理的请求</span><span class="sxs-lookup"><span data-stu-id="04077-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="04077-125">外部 web 服务使用已定义的 web 服务器虚拟目录 (vDir), 这些虚拟目录提供向客户端提供的服务。</span><span class="sxs-lookup"><span data-stu-id="04077-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="04077-126">特定的外部身份 web 服务包括:</span><span class="sxs-lookup"><span data-stu-id="04077-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="04077-127">网络会议会议的 "会面" vDir</span><span class="sxs-lookup"><span data-stu-id="04077-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="04077-128">手机接入和电话会议的 "拨入" vDir</span><span class="sxs-lookup"><span data-stu-id="04077-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="04077-129">Lync Windows 应用商店应用、Lync Mobile 和桌面客户端 Lync 2013 的 "自动发现" vDir。</span><span class="sxs-lookup"><span data-stu-id="04077-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="04077-130">Lync Server 2013 中的自动发现由 DNS 名称 "lyncdiscover" 识别</span><span class="sxs-lookup"><span data-stu-id="04077-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="04077-131">未定义的服务由外部客户端通过直接调用外部 web 服务来访问。</span><span class="sxs-lookup"><span data-stu-id="04077-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="04077-132">例如, 通讯组扩展 (DLX) 和通讯簿服务 (ABS) 通过直接调用外部 web 服务和关联的 vDirs 来访问。</span><span class="sxs-lookup"><span data-stu-id="04077-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="04077-133">客户端知道 vDir 的实际路径, 并基于此信息构造一个统一的记录定位器 (URL)。</span><span class="sxs-lookup"><span data-stu-id="04077-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="04077-134">客户端将使用类似于的 URL 访问通讯簿服务`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="04077-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="04077-135">会议已定义并配置为 Lync Server 拓扑的一部分时的 Office Web Apps 服务器</span><span class="sxs-lookup"><span data-stu-id="04077-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="04077-136">Office Web Apps 服务器是单独的角色服务器, 未配置为外部 Web 服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="04077-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="04077-137">此服务器为客户端访问单独发布。</span><span class="sxs-lookup"><span data-stu-id="04077-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="04077-138">为每个服务定义 SSL 桥接。</span><span class="sxs-lookup"><span data-stu-id="04077-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="04077-139">将外部端口 TCP 443 映射到 TCP 4443 的外部 web 服务端口。</span><span class="sxs-lookup"><span data-stu-id="04077-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="04077-140">对于未加密的 HTTP, 端口 TCP 80 映射到外部 web 服务端口 TCP 8080</span><span class="sxs-lookup"><span data-stu-id="04077-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="04077-141">计划反向代理侦听器以发布 web 服务器资源</span><span class="sxs-lookup"><span data-stu-id="04077-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="04077-142">根据将提供的服务请求和配置反向代理的证书。</span><span class="sxs-lookup"><span data-stu-id="04077-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="04077-143">如果配置了正确的主题备用名称, 则该证书可以由反向代理服务器上的所有已配置侦听器共享</span><span class="sxs-lookup"><span data-stu-id="04077-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="04077-144">可用于计划反向代理部署的资源:</span><span class="sxs-lookup"><span data-stu-id="04077-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="04077-145">Lync Server 2013 中的数据收集</span><span class="sxs-lookup"><span data-stu-id="04077-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="04077-146">Lync Server 2013 中的证书摘要 - 反向代理</span><span class="sxs-lookup"><span data-stu-id="04077-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="04077-147">Lync Server 2013 中的端口摘要 - 反向代理</span><span class="sxs-lookup"><span data-stu-id="04077-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="04077-148">Lync Server 2013 中的 DNS 摘要 - 反向代理</span><span class="sxs-lookup"><span data-stu-id="04077-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

