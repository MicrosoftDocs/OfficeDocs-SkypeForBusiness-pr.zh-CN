---
title: 添加控制器池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定义控制器池 FQDN，选择将包含两个或多个控制器负载平衡池中的多个计算机池或单计算机池。 您还必须键入的完全限定的域名 (FQDN) 将用于连接到控制器池或单个控制器的 FQDN。 对于控制器计算机的池，这将为硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享的 DNS 条目。
ms.openlocfilehash: f659b45fd758d07b9cf96b59b57654bb8cf2fd28
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879312"
---
# <a name="add-director-pool"></a><span data-ttu-id="33339-105">添加控制器池</span><span class="sxs-lookup"><span data-stu-id="33339-105">Add Director Pool</span></span>
 
<span data-ttu-id="33339-106">要在**定义控制器池 FQDN**中，选择是将包含两个或多个控制器负载平衡池中的**多个计算机池**或**单计算机池**。</span><span class="sxs-lookup"><span data-stu-id="33339-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="33339-107">您还必须键入的完全限定的域名 (FQDN) 将用于连接到控制器池或单个控制器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="33339-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="33339-108">对于控制器计算机的池，这将为硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享的 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="33339-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="33339-109">如果您计划将来实现控制器池，选择**多计算机池**。</span><span class="sxs-lookup"><span data-stu-id="33339-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="33339-110">即使池中定义为两个或多台计算机的负载平衡，您可以创建单计算机池，并创建单个计算机池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="33339-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="33339-111">当您准备好以后向池中添加更多计算机时，您必须运行拓扑生成器再次以定义新的池成员和发布新拓扑，然后设置业务 Server 部署向导 Skype 通过新的控制器池成员。</span><span class="sxs-lookup"><span data-stu-id="33339-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="33339-112">您还必须将新的池成员添加到适当的负载平衡器的池的域名系统 (DNS) 负载平衡，或硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="33339-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="33339-113">在许多情况下，您将具有两个负载平衡就地系统。</span><span class="sxs-lookup"><span data-stu-id="33339-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="33339-114">确保到这两个中添加新的成员服务器。</span><span class="sxs-lookup"><span data-stu-id="33339-114">Be sure that you are adding the new member server to both.</span></span> 
  

