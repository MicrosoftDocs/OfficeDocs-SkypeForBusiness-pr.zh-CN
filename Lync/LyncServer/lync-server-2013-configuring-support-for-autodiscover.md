---
title: 'Lync Server 2013: 配置自动发现的支持'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb83156d319db96a4c6ed79768193a24e5cc3e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="89643-102">在 Lync Server 2013 中配置自动发现支持</span><span class="sxs-lookup"><span data-stu-id="89643-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89643-103">_**主题上次修改时间:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="89643-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="89643-104">Lync Server web 服务**自动发现服务**首先在 Lync Server 2010 累积更新中显示:11 月2011。</span><span class="sxs-lookup"><span data-stu-id="89643-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="89643-105">此更新附带了 Lync 移动客户端的初始版本。</span><span class="sxs-lookup"><span data-stu-id="89643-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="89643-106">自动发现服务公开了移动服务, 称为 Mcx 服务。</span><span class="sxs-lookup"><span data-stu-id="89643-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="89643-107">自动发现服务用作所有客户端请求提供哪些服务和功能的相关信息的单个位置, 以及如何联系 sevices –通过完全限定的域名或 web 统一资源定位器参考。</span><span class="sxs-lookup"><span data-stu-id="89643-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="89643-108">自动发现公开了许多功能, 并且每个客户端将基于客户端可以使用的功能发出请求。</span><span class="sxs-lookup"><span data-stu-id="89643-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="89643-109">例如, 桌面 Lync 2013 客户端将使用 autodiscvoer 确定外部 web 服务, 但不会使用移动 (Mcx) 服务。</span><span class="sxs-lookup"><span data-stu-id="89643-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="89643-110">若要正确定义和启用客户端以使用它们可用的功能, 则应定义允许客户有效查找和使用自动发现条目的方案。</span><span class="sxs-lookup"><span data-stu-id="89643-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="89643-111">若要使用 autodoscover, 你的部署要求反向代理发布 Lync Server web 服务、DNS 记录配置为解析 Lync Server 自动发现服务和 Lync Server web 服务的 DNS 查询以及证书服务已针对你的特定方案正确配置。</span><span class="sxs-lookup"><span data-stu-id="89643-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="89643-112">有关自动发现请求/响应中的元素的技术详细信息, 请参阅<A href="lync-server-2013-understanding-autodiscover.md">了解 Lync Server 2013 中的自动发现</A>。</span><span class="sxs-lookup"><span data-stu-id="89643-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="89643-113">以下信息和表根据方案定义需要实现哪些配置 (如果有) 才能提供自动发现服务的完整和有效使用。</span><span class="sxs-lookup"><span data-stu-id="89643-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="89643-114">以下主题中的信息特定于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="89643-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="89643-115">如果你正在寻找有关如何规划 Lync Server 2010 的移动的指南, 请参阅[http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113)。</span><span class="sxs-lookup"><span data-stu-id="89643-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="89643-116">若要部署 Lync Server 2010 的移动版, 请参阅[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="89643-116">To deploy Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="89643-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="89643-117">In This Section</span></span>

  - [<span data-ttu-id="89643-118">在 Lync Server 2013 中配置自动发现的 DNS</span><span class="sxs-lookup"><span data-stu-id="89643-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="89643-119">在 Lync Server 2013 中配置自动发现的证书</span><span class="sxs-lookup"><span data-stu-id="89643-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="89643-120">在 Lync Server 2013 中配置自动发现的反向代理</span><span class="sxs-lookup"><span data-stu-id="89643-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="89643-121">在 Lync Server 2013 中为混合部署配置自动发现</span><span class="sxs-lookup"><span data-stu-id="89643-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

