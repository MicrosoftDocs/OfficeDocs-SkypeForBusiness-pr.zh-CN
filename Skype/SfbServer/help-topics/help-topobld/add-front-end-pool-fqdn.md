---
title: 添加前端池 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 指定你要创建的前端池的完全限定的域名（FQDN）。 发布包含前端池的拓扑后，无法更改池的 FQDN。 如果需要重命名池，必须删除该池，然后使用新的 FQDN 添加新池。
ms.openlocfilehash: e9e420956656d7bd0217f122844ea222f6bd2b40
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698227"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="4711c-105">添加前端池 FQDN</span><span class="sxs-lookup"><span data-stu-id="4711c-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="4711c-106">指定你要创建的前端池的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="4711c-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="4711c-107">发布包含前端池的拓扑后，无法更改池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4711c-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="4711c-108">如果需要重命名池，必须删除该池，然后使用新的 FQDN 添加新池。</span><span class="sxs-lookup"><span data-stu-id="4711c-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="4711c-109">如果你计划在将来实施前端池，请选择 "**多台计算机池**"。</span><span class="sxs-lookup"><span data-stu-id="4711c-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="4711c-110">即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4711c-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="4711c-111">准备好将更多计算机添加到池中后，必须再次运行拓扑生成器来定义新的池成员、发布新拓扑，然后通过 Skype for Business 服务器部署向导设置新的前端池成员。</span><span class="sxs-lookup"><span data-stu-id="4711c-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="4711c-112">还必须将新的池成员添加到池、域名系统（DNS）负载平衡或硬件负载平衡器的相应负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="4711c-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="4711c-113">在许多情况下，你可以同时使用两个负载平衡系统。</span><span class="sxs-lookup"><span data-stu-id="4711c-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="4711c-114">请确保将新的成员服务器添加到两者中。</span><span class="sxs-lookup"><span data-stu-id="4711c-114">Be sure that you are adding the new member server to both.</span></span> 
  

