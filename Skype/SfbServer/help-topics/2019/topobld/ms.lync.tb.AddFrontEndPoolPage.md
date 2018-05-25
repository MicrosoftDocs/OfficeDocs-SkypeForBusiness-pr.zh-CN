---
title: 添加前端池 FQDN
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 指定要创建的前端池的完全限定的域名 (FQDN)。 发布包含前端池的拓扑之后，无法更改池的 FQDN。 如果您需要重命名一个池，您必须删除池，然后添加新的 FQDN 与新池。
ms.openlocfilehash: 73fce35786cdce2a39ebf2981b59a500991112f0
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="eda91-105">添加前端池 FQDN</span><span class="sxs-lookup"><span data-stu-id="eda91-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="eda91-106">指定要创建的前端池的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="eda91-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="eda91-107">发布包含前端池的拓扑之后，无法更改池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="eda91-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="eda91-108">如果您需要重命名一个池，您必须删除池，然后添加新的 FQDN 与新池。</span><span class="sxs-lookup"><span data-stu-id="eda91-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="eda91-109">如果您计划将来实现前端池，选择**多计算机池**。</span><span class="sxs-lookup"><span data-stu-id="eda91-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="eda91-110">即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="eda91-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="eda91-111">当您准备好以后向池中添加更多计算机时，您必须运行拓扑生成器再次以定义新的池成员和发布新拓扑，然后设置 Skype 通过新的前端池成员的业务 Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="eda91-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="eda91-112">您还必须将新池成员添加到适当的负载平衡器的池、 域名系统 (DNS) 负载平衡或硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="eda91-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="eda91-113">在许多情况下，您必须同时负载平衡就地系统。</span><span class="sxs-lookup"><span data-stu-id="eda91-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="eda91-114">确保到这两个中添加新的成员服务器。</span><span class="sxs-lookup"><span data-stu-id="eda91-114">Be sure that you are adding the new member server to both.</span></span> 
  

