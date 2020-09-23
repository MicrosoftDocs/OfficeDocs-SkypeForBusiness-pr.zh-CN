---
title: 添加 A/V MCU 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 中央站点中没有并置的 A/V 会议服务的所有 Enterprise Edition 前端服务器可使用相同的独立 A/V 会议池。对于每个 A/V 会议池，必须为其指定完全限定域名 (FQDN)，并指定该池将具有单台 A/V 会议服务器还是多台负载平衡的 A/V 会议服务器。
ms.openlocfilehash: e38bcf5efa065ef2f9b53a5df47f6a56eafbe29a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217473"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="7771e-104">添加 A/V MCU 池</span><span class="sxs-lookup"><span data-stu-id="7771e-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="7771e-p102">中央站点中没有并置的 A/V 会议服务的所有 Enterprise Edition 前端服务器可使用相同的独立 A/V 会议池。对于每个 A/V 会议池，必须为其指定完全限定域名 (FQDN)，并指定该池将具有单台 A/V 会议服务器还是多台负载平衡的 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="7771e-p102">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool. For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7771e-p103">无法将单个服务器的池转换为多个服务器的池。如果以后确定组织需要多个服务器的池，则必须先删除单个服务器的池，然后添加多个服务器的池。</span><span class="sxs-lookup"><span data-stu-id="7771e-p103">You cannot convert a single-server pool to a multiple-server pool. If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="7771e-109">如果计划将来实施 A/V 会议池，请选择“多个计算机池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7771e-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="7771e-110">即使将池定义为具有两个或更多负载平衡的计算机，仍可以创建单一计算机池并为该单一计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7771e-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="7771e-111">当您准备好将更多计算机添加到池时，您必须再次使用拓扑生成器来定义新的池成员，发布新的拓扑，然后通过 Skype for Business Server 部署向导设置新的 A/V 会议池成员。</span><span class="sxs-lookup"><span data-stu-id="7771e-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="7771e-112">A/V 会议服务器池是唯一的，因此无需负载平衡器就可以创建池。</span><span class="sxs-lookup"><span data-stu-id="7771e-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="7771e-113">A/V 会议池内部可进行负载平衡，无需其他硬件。</span><span class="sxs-lookup"><span data-stu-id="7771e-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

