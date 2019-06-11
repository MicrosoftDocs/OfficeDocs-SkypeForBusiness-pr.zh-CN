---
title: Lync Server 2013：控制器方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for the Director
ms:assetid: d2cf384a-0860-4779-80ce-cba2543be322
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398908(v=OCS.15)
ms:contentKeyID: 48185419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba35647e8ecc0cfa59d5c7c6b5c32b07bedf95e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="f287e-102">Lync Server 2013 中的控制器方案</span><span class="sxs-lookup"><span data-stu-id="f287e-102">Scenarios for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f287e-103">_**主题上次修改时间:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f287e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f287e-104">Director 是运行 Microsoft Lync Server 2013 通信软件的服务器, 可对用户请求进行身份验证, 但不会在家任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f287e-104">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="f287e-105">Director 还托管类似于前端服务器的 web 服务, 并将验证 web 票证请求并提供其他服务。</span><span class="sxs-lookup"><span data-stu-id="f287e-105">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f287e-106">如果你部署控制器, 则必须通过反向代理以及前端服务器的 web 服务从外部发布 Director web 服务。</span><span class="sxs-lookup"><span data-stu-id="f287e-106">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="f287e-107">下面的主题介绍了可能的控制器拓扑的规划流程。</span><span class="sxs-lookup"><span data-stu-id="f287e-107">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f287e-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="f287e-108">In This Section</span></span>

  - [<span data-ttu-id="f287e-109">Lync Server 2013 中的控制器概述</span><span class="sxs-lookup"><span data-stu-id="f287e-109">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="f287e-110">Lync Server 2013 中控制器所需的组件</span><span class="sxs-lookup"><span data-stu-id="f287e-110">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="f287e-111">Lync Server 2013 中控制器的软硬件要求</span><span class="sxs-lookup"><span data-stu-id="f287e-111">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="f287e-112">Lync Server 2013 中的单一控制器</span><span class="sxs-lookup"><span data-stu-id="f287e-112">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="f287e-113">Lync Server 2013 中扩展的控制器池</span><span class="sxs-lookup"><span data-stu-id="f287e-113">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f287e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f287e-114">See Also</span></span>


[<span data-ttu-id="f287e-115">Lync Server 2013 中支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="f287e-115">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="f287e-116">Lync Server 2013 的服务器硬件平台</span><span class="sxs-lookup"><span data-stu-id="f287e-116">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

