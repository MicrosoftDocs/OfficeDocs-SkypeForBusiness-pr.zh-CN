---
title: Lync Server 2013：规划自动发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 990e58dc01171001e896b03e5a32fc8175c93b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="5f0c6-102">在 Lync Server 2013 中规划自动发现</span><span class="sxs-lookup"><span data-stu-id="5f0c6-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f0c6-103">_**上次修改的主题：** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="5f0c6-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="5f0c6-104">在 Lync Server 2010 的累积更新中为 Lync Server 引入了自动发现：11月2011。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="5f0c6-105">此初始的自动发现实现的主要目的是为 Lync Mobile 提供一种定位移动服务（Mcx）的方法。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="5f0c6-106">Lync Server 2013 中的自动发现服务现在是所有客户端用来查找服务器和用户服务的一项服务。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="5f0c6-107">Microsoft Lync Server 2013 自动发现服务在控制器和前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5f0c6-108">有关自动发现和向客户端传递内容的技术方面的更多了解，请参阅<A href="lync-server-2013-understanding-autodiscover.md">了解 Lync Server 2013 中的自动发现</A>。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="5f0c6-109">移动仍然是一个不同的方案，移动服务仍需要进行一些特殊规划。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="5f0c6-110">有关其他详细信息，请参阅<A href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中规划移动</A>功能。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="5f0c6-111">如果在 Lync Server 2010 中引入了自动发现，则需要进行一些威胁，以便实施需要对现有服务器部署进行潜在证书更改的服务。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="5f0c6-112">自动发现可用于 HTTPS 的端口 TCP 443 或通过端口 TCP 80 for HTTP。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="5f0c6-113">如果做出了使用 HTTPS 的决定，则需要重新颁发反向代理、控制器和前端服务器上的证书，以便满足所需`lyncdiscover.<domain>`的和`lyncdiscoverinternal.<domain>` DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="5f0c6-114">如果决定使用 HTTP，可以通过使用 DNS CNAME （或别名）记录来使用证书上的现有名称来避免重新颁发证书。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="5f0c6-115">使用 HTTP 是指未加密初始通信。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="5f0c6-116">由于 Lync Server 2013 使用所有客户端的自动发现，因此主要方案是以独占方式使用 HTTPS，并使用 lyncdiscover. 创建证书。\<作为\>反向代理、控制器和前端服务器配置的一部分的域。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="5f0c6-117">如果要将自动发现实现从 Lync Server 2010 的已升级部署，则可能需要使用 HTTP 以避免重新颁发证书。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="5f0c6-118">以下各节提供了这两种方案的指南。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f0c6-119">外部 web 服务发布规则所使用的证书上的 "主题备用名称" 列表必须包含<EM>lyncdiscover.&lt; 。组织&gt; </EM>中每个 SIP 域的 sipdomain 条目。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="5f0c6-120">有关控制器、前端服务器和反向代理所需的主题替代名称条目的详细信息，请参阅<A href="lync-server-2013-certificate-summary-autodiscover.md">Lync Server 2013 中的证书摘要-自动发现</A>。</span><span class="sxs-lookup"><span data-stu-id="5f0c6-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f0c6-121">本部分内容</span><span class="sxs-lookup"><span data-stu-id="5f0c6-121">In This Section</span></span>

  - [<span data-ttu-id="5f0c6-122">证书摘要-Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="5f0c6-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="5f0c6-123">Lync Server 2013 中的端口摘要-自动发现</span><span class="sxs-lookup"><span data-stu-id="5f0c6-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="5f0c6-124">Lync Server 2013 中的 DNS 摘要-自动发现</span><span class="sxs-lookup"><span data-stu-id="5f0c6-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="5f0c6-125">Lync Server 2013 中的混合和拆分域自动发现</span><span class="sxs-lookup"><span data-stu-id="5f0c6-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

