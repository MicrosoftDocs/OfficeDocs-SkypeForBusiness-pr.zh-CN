---
title: 添加前端池 FQDN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: 指定要创建的前端池的完全限定域名 (FQDN)。发布包含前端池的拓扑后，就无法更改该池的 FQDN。如果需要重命名池，必须先删除该池，然后添加具有新 FQDN 的新池。
ms.openlocfilehash: 7b0b14ab9b8cb450a80872cedf61e6f24da91dc2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811652"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="ef38f-105">添加前端池 FQDN</span><span class="sxs-lookup"><span data-stu-id="ef38f-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="ef38f-p102">指定要创建的前端池的完全限定域名 (FQDN)。发布包含前端池的拓扑后，就无法更改该池的 FQDN。如果需要重命名池，必须先删除该池，然后添加具有新 FQDN 的新池。</span><span class="sxs-lookup"><span data-stu-id="ef38f-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="ef38f-109">如果计划将来实施前端池，请选择 **“多个计算机池”**。</span><span class="sxs-lookup"><span data-stu-id="ef38f-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="ef38f-110">即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单个计算机的池并为该单个计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ef38f-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="ef38f-111">以后准备好向池中添加更多计算机时，必须再次运行拓扑生成器以定义新的池成员，发布新拓扑，然后通过 Skype for Business Server 部署向导设置新的前端池成员。</span><span class="sxs-lookup"><span data-stu-id="ef38f-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="ef38f-112">还必须向该池的相应负载平衡器（域名系统 (DNS) 负载平衡或硬件负载平衡器）添加新的池成员。</span><span class="sxs-lookup"><span data-stu-id="ef38f-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="ef38f-113">多数情况下，会同时部署这两种负载平衡系统。</span><span class="sxs-lookup"><span data-stu-id="ef38f-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="ef38f-114">请确保向这两者均添加新的成员服务器。</span><span class="sxs-lookup"><span data-stu-id="ef38f-114">Be sure that you are adding the new member server to both.</span></span> 
  

