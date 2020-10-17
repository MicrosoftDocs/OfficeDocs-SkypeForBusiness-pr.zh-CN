---
title: Lync Server 2013：配置自动发现支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3893ddd2282fd6abdfff716207f99102d09fac31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507539"
---
# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="71b1b-102">在 Lync Server 2013 中配置自动发现支持</span><span class="sxs-lookup"><span data-stu-id="71b1b-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71b1b-103">_**上次修改的主题：** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="71b1b-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="71b1b-104">Lync Server web services **自动发现服务** 首先显示在 Lync Server 2010 累积更新中：11月2011。</span><span class="sxs-lookup"><span data-stu-id="71b1b-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="71b1b-105">此更新伴随 Lync 移动客户端的初始版本。</span><span class="sxs-lookup"><span data-stu-id="71b1b-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="71b1b-106">自动发现服务公开了移动服务，称为 Mcx 服务。</span><span class="sxs-lookup"><span data-stu-id="71b1b-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="71b1b-107">自动发现服务充当所有客户端的单个位置，以请求提供哪些服务和功能可用的信息，以及如何通过完全限定的域名或 web 统一资源定位器引用来联系 sevices –。</span><span class="sxs-lookup"><span data-stu-id="71b1b-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="71b1b-108">自动发现将公开许多功能，每个客户端将根据客户端可以使用的功能发出请求。</span><span class="sxs-lookup"><span data-stu-id="71b1b-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="71b1b-109">例如，桌面 Lync 2013 客户端将使用 autodiscvoer 来确定外部 web 服务，但不会使用移动 (Mcx) 服务。</span><span class="sxs-lookup"><span data-stu-id="71b1b-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="71b1b-110">若要正确定义和启用客户端以使用其可用的功能，则应定义允许客户端有效查找和使用自动发现项的方案。</span><span class="sxs-lookup"><span data-stu-id="71b1b-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="71b1b-111">若要使用 autodoscover，您的部署要求反向代理发布 Lync Server web 服务，并将 DNS 记录配置为解析 Lync Server 自动发现服务和 Lync Server web 服务的 DNS 查询，并为您的特定方案正确配置证书服务。</span><span class="sxs-lookup"><span data-stu-id="71b1b-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="71b1b-112">有关自动发现请求/响应中的元素的技术详细信息，请参阅 <A href="lync-server-2013-understanding-autodiscover.md">了解 Lync Server 2013 中的自动发现</A>。</span><span class="sxs-lookup"><span data-stu-id="71b1b-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="71b1b-113">下面的信息和表根据应用场景定义了哪些配置 (如果需要实现什么) 才能提供自动发现服务的完整和有效使用。</span><span class="sxs-lookup"><span data-stu-id="71b1b-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="71b1b-114">以下主题中的信息特定于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="71b1b-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="71b1b-115">如果你正在寻找有关如何规划 Lync Server 2010 移动性的指南，请参阅 [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113) 。</span><span class="sxs-lookup"><span data-stu-id="71b1b-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="71b1b-116">若要部署 Lync Server 2010 的移动功能，请参阅 [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="71b1b-116">To deploy Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="71b1b-117">本部分内容</span><span class="sxs-lookup"><span data-stu-id="71b1b-117">In This Section</span></span>

  - [<span data-ttu-id="71b1b-118">在 Lync Server 2013 中配置用于自动发现的 DNS</span><span class="sxs-lookup"><span data-stu-id="71b1b-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="71b1b-119">在 Lync Server 2013 中配置自动发现的证书</span><span class="sxs-lookup"><span data-stu-id="71b1b-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="71b1b-120">在 Lync Server 2013 中为自动发现配置反向代理</span><span class="sxs-lookup"><span data-stu-id="71b1b-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="71b1b-121">在 Lync Server 2013 中配置自动发现以实现混合部署</span><span class="sxs-lookup"><span data-stu-id="71b1b-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

