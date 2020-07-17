---
title: 迁移多个站点和池
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 支持多站点部署和多池部署。 将多个池迁移到 Skype for business Server 2019 的过程需要以下注意事项：
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752654"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="957de-104">迁移多个站点和池</span><span class="sxs-lookup"><span data-stu-id="957de-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="957de-105">Skype for Business Server 2019 支持多站点部署和多池部署。</span><span class="sxs-lookup"><span data-stu-id="957de-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="957de-106">将多个池迁移到 Skype for business Server 2019 的过程需要以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="957de-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="957de-107">部署 Skype for Business Server 2019 试点池之后，需要定义将移动到 Skype for Business Server 2019 池的试点用户的子集，以及用于验证用户功能的方法。</span><span class="sxs-lookup"><span data-stu-id="957de-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="957de-108">例如，在将用户移动到引导池之后，验证用户的会议策略是否已移动到 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="957de-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="957de-109">在引导池中部署边缘服务器之后，需要验证外部用户是否可以与 Skype for Business Server 2019 池通信。</span><span class="sxs-lookup"><span data-stu-id="957de-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="957de-110">Skype for Business Server 2019 中已弃用持久聊天、SQL 镜像和 XMPP 功能，并且不再作为 Skype for business Server 2019 功能提供，但它们可以在共存环境中继续进行（如果它们之前已部署在旧环境中）。</span><span class="sxs-lookup"><span data-stu-id="957de-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="957de-111">如果要继续使用这些功能，则应计划继续使用共存环境，其中某些用户将保留在旧版池中。</span><span class="sxs-lookup"><span data-stu-id="957de-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="957de-112">将联合路由的边缘服务器转换为试点 Skype for business Server 2019 边缘服务器后，需要验证联合用户是否可以与 Skype for business Server 2019 池通信。</span><span class="sxs-lookup"><span data-stu-id="957de-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="957de-113">移动所有用户和非用户联系人对象之后，需要验证旧版池是否为空。</span><span class="sxs-lookup"><span data-stu-id="957de-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="957de-114">验证旧版池是否为空之后，您可以停用池。</span><span class="sxs-lookup"><span data-stu-id="957de-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="957de-115">有关如何停用旧版池和服务器的详细信息，请参阅[第8阶段：停止旧版池](phase-8-decommission-legacy-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="957de-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

