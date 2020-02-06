---
title: 添加控制器池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定义控制器池 FQDN，请选择将由负载平衡的池中的两个或多个控制器（或单个计算机池）组成的多台计算机池。 还必须键入将用于连接到控制器池或单个控制器的 FQDN 的完全限定的域名（FQDN）。 对于 Director 计算机池，这将是用于硬件负载平衡器的虚拟 IP 或用于 DNS 负载平衡的共享 DNS 条目的域名系统（DNS）条目。
ms.openlocfilehash: 491d50c733314e1811aac38c556a6d4683b6956b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796571"
---
# <a name="add-director-pool"></a><span data-ttu-id="94db5-105">添加控制器池</span><span class="sxs-lookup"><span data-stu-id="94db5-105">Add Director Pool</span></span>
 
<span data-ttu-id="94db5-106">若要**定义控制器池 FQDN**，请选择将由负载平衡的池中的两个或多个控制器（或**单个计算机池**）组成的**多台计算机池**。</span><span class="sxs-lookup"><span data-stu-id="94db5-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="94db5-107">还必须键入将用于连接到控制器池或单个控制器的 FQDN 的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="94db5-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="94db5-108">对于 Director 计算机池，这将是用于硬件负载平衡器的虚拟 IP 或用于 DNS 负载平衡的共享 DNS 条目的域名系统（DNS）条目。</span><span class="sxs-lookup"><span data-stu-id="94db5-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="94db5-109">如果你计划在将来实现控制器池，请选择 "**多台计算机池**"。</span><span class="sxs-lookup"><span data-stu-id="94db5-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="94db5-110">即使池被定义为两台或多台具有负载平衡的计算机，你也可以创建一个单独的计算机池并为该单台计算机创建一个池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="94db5-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="94db5-111">准备好将更多计算机添加到池中后，必须再次运行拓扑生成器来定义新的池成员、发布新拓扑，然后通过 Skype for Business 服务器部署向导设置新的控制器池成员。</span><span class="sxs-lookup"><span data-stu-id="94db5-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="94db5-112">还必须将新的池成员添加到池的相应负载平衡器、域名系统（DNS）负载平衡或硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="94db5-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="94db5-113">在许多情况下，系统会同时使用负载平衡系统。</span><span class="sxs-lookup"><span data-stu-id="94db5-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="94db5-114">请确保将新的成员服务器添加到两者中。</span><span class="sxs-lookup"><span data-stu-id="94db5-114">Be sure that you are adding the new member server to both.</span></span> 
  

