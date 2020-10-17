---
title: 迁移多个站点和池
description: 迁移多个站点和池。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7efaa6f038286ff9138e631f23da88bb445e20f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543248"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="0bc58-103">迁移多个站点和池</span><span class="sxs-lookup"><span data-stu-id="0bc58-103">Migrating multiple sites and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bc58-104">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="0bc58-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="0bc58-105">Lync Server 2013 支持多站点部署和多池部署。</span><span class="sxs-lookup"><span data-stu-id="0bc58-105">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="0bc58-106">将多个池从 Lync Server 2010 迁移到 Lync Server 2013 的过程需要以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="0bc58-106">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="0bc58-107">部署 Lync Server 2013 引导池之后，需要定义将移动到 Lync Server 2013 池的试点用户的子集，以及用于验证用户功能的方法。</span><span class="sxs-lookup"><span data-stu-id="0bc58-107">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="0bc58-108">例如，在将用户移动到引导池之后，请验证用户的会议策略是否已移动到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="0bc58-108">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="0bc58-109">在引导池中部署边缘服务器之后，需要验证外部用户是否可以与 Lync Server 2013 池通信。</span><span class="sxs-lookup"><span data-stu-id="0bc58-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="0bc58-110">将来自 Lync Server 2010 边缘服务器的联盟路由转换为试点 Lync Server 2013 边缘服务器后，需要验证联合用户是否可以与 Lync Server 2013 池通信。</span><span class="sxs-lookup"><span data-stu-id="0bc58-110">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="0bc58-111">移动所有用户和非用户联系人对象之后，需要验证 Lync Server 2010 池是否为空。</span><span class="sxs-lookup"><span data-stu-id="0bc58-111">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="0bc58-112">在验证 Lync Server 2010 池是否为空之后，您可以停用该池。</span><span class="sxs-lookup"><span data-stu-id="0bc58-112">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="0bc58-113">有关如何停用旧版 Lync Server 2010 池和服务器的详细信息，请参阅 [第8阶段：停止旧版池](phase-8-decommission-legacy-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="0bc58-113">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

