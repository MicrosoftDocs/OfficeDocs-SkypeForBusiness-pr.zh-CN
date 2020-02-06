---
title: 迁移多个站点和池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business 服务器2019支持多站点和多池部署。 将多个池迁移到 Skype for business 服务器2019的过程需要考虑以下事项：
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813440"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="f64b1-104">迁移多个站点和池</span><span class="sxs-lookup"><span data-stu-id="f64b1-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="f64b1-105">Skype for Business 服务器2019支持多站点和多池部署。</span><span class="sxs-lookup"><span data-stu-id="f64b1-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="f64b1-106">将多个池迁移到 Skype for business 服务器2019的过程需要考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="f64b1-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="f64b1-107">部署 Skype for Business Server 2019 试验池后，你需要定义将被移动到 Skype for business Server 2019 池的试点用户的子集，以及用于验证用户功能的方法。</span><span class="sxs-lookup"><span data-stu-id="f64b1-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="f64b1-108">例如，将用户移动到试验池后，请验证用户的会议策略是否已移动到 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="f64b1-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="f64b1-109">在试验池中部署边缘服务器之后，你需要验证外部用户是否可以与 Skype for Business Server 2019 池通信。</span><span class="sxs-lookup"><span data-stu-id="f64b1-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="f64b1-110">Skype for business Server 2019 中已弃用持续式聊天、SQL 镜像和 XMPP 功能，并且不再以 Skype for business Server 2019 功能的形式提供，但它们可以在共存环境中继续使用（如果它们以前部署在旧版环境。</span><span class="sxs-lookup"><span data-stu-id="f64b1-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="f64b1-111">如果你希望继续使用这些功能，你应该计划继续使用一个共存环境，其中某些用户将保留在旧版池中。</span><span class="sxs-lookup"><span data-stu-id="f64b1-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="f64b1-112">将联盟路由的边缘服务器转换为试点 Skype for business Server 2019 Edge 服务器之后，你需要验证联盟用户是否可以与 Skype for business Server 2019 池通信。</span><span class="sxs-lookup"><span data-stu-id="f64b1-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="f64b1-113">移动所有用户和非用户联系人对象后，需要验证旧版池是否为空。</span><span class="sxs-lookup"><span data-stu-id="f64b1-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="f64b1-114">验证旧版池是否为空后，您可以停用该池。</span><span class="sxs-lookup"><span data-stu-id="f64b1-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="f64b1-115">有关如何停用旧版池和服务器的详细信息，请参阅[第8阶段：解除旧版池](phase-8-decommission-legacy-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="f64b1-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

