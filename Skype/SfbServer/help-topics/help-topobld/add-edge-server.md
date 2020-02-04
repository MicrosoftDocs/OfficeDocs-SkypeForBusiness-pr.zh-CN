---
title: 添加边缘服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。 在发布包含 Edge 服务器或边缘服务器池以及安装 Skype for Business 服务器的拓扑之前，应完成部署外部用户访问的所有先决条件。 有关这些先决条件的详细信息，请参阅部署文档中的Preparing for Installation of Servers in the Perimeter Network。
ms.openlocfilehash: 3433f5dac67d0e02fb8e8552e205092a51082cc6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698337"
---
# <a name="add-edge-server"></a><span data-ttu-id="3d6fe-105">添加边缘服务器</span><span class="sxs-lookup"><span data-stu-id="3d6fe-105">Add Edge Server</span></span>

<span data-ttu-id="3d6fe-106">要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-106">To incorporate an Edge Server or an Edge Server pool into your topology design, you need to specify the fully qualified domain name (FQDN) of the server on which you want to deploy Edge Server or Edge Server pool.</span></span> <span data-ttu-id="3d6fe-107">在发布包含 Edge 服务器或边缘服务器池以及安装 Skype for Business 服务器的拓扑之前，应完成部署外部用户访问的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-107">Prior to publishing a topology that includes the Edge Server or Edge Server pool and installing Skype for Business Server, you should have completed all prerequisites for deploying external user access.</span></span> <span data-ttu-id="3d6fe-108">有关这些先决条件的详细信息，请参阅部署文档中的[Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-108">For details about these prerequisites, see [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d6fe-p103">指定的名称必须与在服务器上配置的计算机名称相同。默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。拓扑生成器使用 FQDN，而不是短名称。必须在要部署为未加入域的边缘服务器或边缘服务器池的计算机名称上配置域名系统 (DNS) 后缀。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-p103">The name you specify must be identical to the computer name configured on the server. By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN. Topology Builder uses FQDNs, not short names. You must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server or Edge Server pool that is not joined to a domain.</span></span>

> [!TIP]
> <span data-ttu-id="3d6fe-113">如果计划将来实施边缘服务器池，请选择“**多计算机池**”。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-113">If you plan to implement an Edge Server pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="3d6fe-114">即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-114">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="3d6fe-115">当你准备好将更多计算机添加到池中时，你必须再次使用拓扑生成器来定义新的池成员、发布新拓扑，然后通过 Skype for Business 服务器部署向导设置新的 Edge 服务器池成员。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-115">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new Edge Server pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="3d6fe-116">还必须向该池的相应负载平衡器（DNS 负载平衡或硬件负载平衡器）添加新的池成员。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-116">You must also add the new pool member to the appropriate load balancers for the pool, DNS load balancing or hardware load balancers.</span></span> <span data-ttu-id="3d6fe-117">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-117">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="3d6fe-118">您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-118">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="3d6fe-119">请确保将新成员服务器添加到相应的负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-119">Be sure that you are adding the new member server to the appropriate load balancer.</span></span>

<span data-ttu-id="3d6fe-p105">可以在部署初始拓扑时或在部署初始拓扑后添加对外部用户访问的支持。有关向现有拓扑中添加边缘服务器或边缘服务器池的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3d6fe-p105">You can add support for external user access when you deploy your initial topology, or after you deploy your initial topology. For details about adding Edge Servers or Edge Server pool to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


