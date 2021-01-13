---
title: 添加控制器池
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: 要“定义控制器池 FQDN”，请选择“多计算机池”（在负载平衡池中包含两个或更多控制器）或“单计算机池”。 还必须在 FQDN (键入将用于连接到控制器池) 或单个控制器的 FQDN 的完全限定域名。 对于控制器计算机池，该完全限定的域名可以是硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享 DNS 条目。
ms.openlocfilehash: 611692c9491fa197594e5d16038665997809853e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828902"
---
# <a name="add-director-pool"></a><span data-ttu-id="7722b-105">添加控制器池</span><span class="sxs-lookup"><span data-stu-id="7722b-105">Add Director Pool</span></span>
 
<span data-ttu-id="7722b-106">要“定义控制器池 FQDN”，请选择“多计算机池”（在负载平衡池中包含两个或更多控制器）或“单计算机池”。</span><span class="sxs-lookup"><span data-stu-id="7722b-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="7722b-107">还必须在 FQDN (键入将用于连接到控制器池) 或单个控制器的 FQDN 的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="7722b-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="7722b-108">对于控制器计算机池，该完全限定的域名可以是硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="7722b-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="7722b-109">如果计划将来实施控制器池，请选择“多计算机池”。</span><span class="sxs-lookup"><span data-stu-id="7722b-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="7722b-110">即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7722b-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="7722b-111">以后准备好向池中添加更多计算机时，必须再次运行拓扑生成器以定义新的池成员，发布新拓扑，然后通过 Skype for Business Server 部署向导设置新的控制器池成员。</span><span class="sxs-lookup"><span data-stu-id="7722b-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="7722b-112">还必须向该池的相应负载平衡器（域名系统 (DNS) 负载平衡或硬件负载平衡器）添加新的池成员。</span><span class="sxs-lookup"><span data-stu-id="7722b-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="7722b-113">多数情况下，会同时部署这两种负载平衡系统。</span><span class="sxs-lookup"><span data-stu-id="7722b-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="7722b-114">请确保向这两者均添加新的成员服务器。</span><span class="sxs-lookup"><span data-stu-id="7722b-114">Be sure that you are adding the new member server to both.</span></span> 
  

