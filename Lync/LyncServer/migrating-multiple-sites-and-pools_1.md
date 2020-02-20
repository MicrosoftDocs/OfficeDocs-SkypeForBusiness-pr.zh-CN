---
title: 迁移多个站点和池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf8de79830dab0b85bd5346da24cf3c4222ed696
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="ccfb3-102">迁移多个站点和池</span><span class="sxs-lookup"><span data-stu-id="ccfb3-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccfb3-103">_**上次修改的主题：** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="ccfb3-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="ccfb3-104">Lync Server 2013 支持多站点部署和多池部署。</span><span class="sxs-lookup"><span data-stu-id="ccfb3-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="ccfb3-105">将多个池从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013 的过程需要以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="ccfb3-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="ccfb3-106">部署 Lync Server 2013 引导池之后，需要定义将移动到 Lync Server 2013 池的试点用户的子集，以及用于验证用户功能的方法。</span><span class="sxs-lookup"><span data-stu-id="ccfb3-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="ccfb3-107">在引导池中部署边缘服务器之后，需要验证外部用户是否可以与 Lync Server 2013 池通信。</span><span class="sxs-lookup"><span data-stu-id="ccfb3-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="ccfb3-108">将来自 Office 通信服务器 2007 R2 边缘服务器的联盟路由转换为试点 Lync Server 2013 边缘服务器后，需要验证联合用户是否可以与 Lync Server 2013 池通信。</span><span class="sxs-lookup"><span data-stu-id="ccfb3-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="ccfb3-109">移动所有用户和非用户联系人对象之后，需要验证 Office 通信服务器 2007 R2 池是否为空。</span><span class="sxs-lookup"><span data-stu-id="ccfb3-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="ccfb3-110">验证 Office 通信服务器 2007 R2 池是否为空之后，您可以停用池。</span><span class="sxs-lookup"><span data-stu-id="ccfb3-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="ccfb3-111">有关如何停用旧版 Office 通信服务器 2007 R2 池和服务器的详细信息，请参阅[阶段10：停止旧版网站](phase-10-decommission-legacy-site.md)。</span><span class="sxs-lookup"><span data-stu-id="ccfb3-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

