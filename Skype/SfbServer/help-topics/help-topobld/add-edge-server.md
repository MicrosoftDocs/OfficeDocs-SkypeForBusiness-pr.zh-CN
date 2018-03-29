---
title: 添加边缘服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。 之前发布的拓扑结构中包括的边缘服务器或边缘服务器池和为业务服务器安装 Skype，您应该已完成部署外部用户访问权限的所有先决条件。 这些系统必备组件的详细信息，请参阅安装的服务器的外围网络中部署文档的准备。
ms.openlocfilehash: 3d377bee22ff33450327e91d4888c3ee419b4195
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server"></a><span data-ttu-id="f662e-105">添加边缘服务器</span><span class="sxs-lookup"><span data-stu-id="f662e-105">Add Edge Server</span></span>
 
<span data-ttu-id="f662e-106">要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="f662e-106">To incorporate an Edge Server or an Edge Server pool into your topology design, you need to specify the fully qualified domain name (FQDN) of the server on which you want to deploy Edge Server or Edge Server pool.</span></span> <span data-ttu-id="f662e-107">之前发布的拓扑结构中包括的边缘服务器或边缘服务器池和为业务服务器安装 Skype，您应该已完成部署外部用户访问权限的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="f662e-107">Prior to publishing a topology that includes the Edge Server or Edge Server pool and installing Skype for Business Server, you should have completed all prerequisites for deploying external user access.</span></span> <span data-ttu-id="f662e-108">有关这些系统必备组件的详细信息，请参阅[准备安装的服务器的外围网络中](http://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)部署文档。</span><span class="sxs-lookup"><span data-stu-id="f662e-108">For details about these prerequisites, see [Preparing for Installation of Servers in the Perimeter Network](http://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) in the Deployment documentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f662e-p103">指定的名称必须与在服务器上配置的计算机名称相同。默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。拓扑生成器使用 FQDN，而不是短名称。必须在要部署为未加入域的边缘服务器或边缘服务器池的计算机名称上配置域名系统 (DNS) 后缀。</span><span class="sxs-lookup"><span data-stu-id="f662e-p103">The name you specify must be identical to the computer name configured on the server. By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN. Topology Builder uses FQDNs, not short names. You must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server or Edge Server pool that is not joined to a domain.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f662e-113">如果计划将来实施边缘服务器池，请选择“**多计算机池**”。</span><span class="sxs-lookup"><span data-stu-id="f662e-113">If you plan to implement an Edge Server pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="f662e-114">即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f662e-114">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="f662e-115">准备好以后向池中添加更多的计算机时，必须再次以定义新的池成员，发布新的拓扑，然后为业务服务器部署向导设置了新的边缘服务器池成员通过 Skype 的拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="f662e-115">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new Edge Server pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f662e-116">还必须向该池的相应负载平衡器（DNS 负载平衡或硬件负载平衡器）添加新的池成员。</span><span class="sxs-lookup"><span data-stu-id="f662e-116">You must also add the new pool member to the appropriate load balancers for the pool, DNS load balancing or hardware load balancers.</span></span> <span data-ttu-id="f662e-117">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="f662e-117">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="f662e-118">您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="f662e-118">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="f662e-119">请确保将新成员服务器添加到相应的负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="f662e-119">Be sure that you are adding the new member server to the appropriate load balancer.</span></span> 
  
<span data-ttu-id="f662e-120">可以在部署初始拓扑时或在部署初始拓扑后添加对外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="f662e-120">You can add support for external user access when you deploy your initial topology, or after you deploy your initial topology.</span></span> <span data-ttu-id="f662e-121">有关添加边缘服务器或向现有拓扑结构的边缘服务器池的详细信息，请参阅[定义边拓扑](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)的边缘服务器部署文档。</span><span class="sxs-lookup"><span data-stu-id="f662e-121">For details about adding Edge Servers or Edge Server pool to an existing topology, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>
  

