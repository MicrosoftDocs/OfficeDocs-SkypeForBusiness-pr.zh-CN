---
title: 迁移多个站点和池
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype 的业务服务器 2019年支持多站点和多池部署。 迁移到 Skype for Business Server 2019 的多个池的过程需要考虑以下事项：
ms.openlocfilehash: 9716df65acfde26c41001bbc252b746ea1bd5241
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028745"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="0d91b-104">迁移多个站点和池</span><span class="sxs-lookup"><span data-stu-id="0d91b-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="0d91b-105">Skype 的业务服务器 2019年支持多站点和多池部署。</span><span class="sxs-lookup"><span data-stu-id="0d91b-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="0d91b-106">迁移到 Skype for Business Server 2019 的多个池的过程需要考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="0d91b-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="0d91b-107">部署后的业务服务器 2019年试点池 Skype，您需要定义业务服务器 2019年池，和用于验证用户的功能的方法将被移动到 Skype 的试生产用户的子集。</span><span class="sxs-lookup"><span data-stu-id="0d91b-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="0d91b-108">例如后将用户移动到试点池，, 验证已由用户的会议策略的业务服务器 2019年移动到 Skype。</span><span class="sxs-lookup"><span data-stu-id="0d91b-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="0d91b-109">部署边缘服务器在试点池中后，您需要验证外部用户可以相互业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="0d91b-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="0d91b-110">持久聊天、 SQL 镜像，和 XMPP 功能是业务服务器 2019年的 Skype 中已弃用和 Skype 作为业务服务器 2019年功能不再可用，但它们可以继续使用在共存环境中如果先前已部署中旧环境。</span><span class="sxs-lookup"><span data-stu-id="0d91b-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="0d91b-111">如果您想要继续使用这些功能，您应计划继续共存环境其中某些用户将保留在旧池。</span><span class="sxs-lookup"><span data-stu-id="0d91b-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="0d91b-112">为业务 Server 2019 边缘服务器切换到试点 Skype 的联盟的路由的边缘服务器后，您需要验证联盟的用户可以相互业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="0d91b-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="0d91b-113">移动所有用户和非用户联系对象后，您需要验证旧池为空。</span><span class="sxs-lookup"><span data-stu-id="0d91b-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="0d91b-114">确认旧池为空后，可以停用该池。</span><span class="sxs-lookup"><span data-stu-id="0d91b-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="0d91b-115">有关如何停用旧旧池和服务器的详细信息，请参阅[第 8 阶段： 停用旧池](phase-8-decommission-legacy-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="0d91b-115">For details about how to deactivate the legacy legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

