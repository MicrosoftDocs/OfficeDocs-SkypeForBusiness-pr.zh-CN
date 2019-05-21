---
title: 添加 A/V MCU 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 没有 collocated A/V 会议服务的中心网站的所有企业版前端服务器都可以使用相同的独立 A/V 会议池。 对于每个 A/V 会议池, 你必须为该池指定完全限定的域名 (FQDN), 以及它将仅具有单个 A/V 会议服务器还是具有多个负载平衡的 A/V 会议服务器。
ms.openlocfilehash: b854e7ecaeed13bd7df15c3ac0439323f3deb311
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304994"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="8839e-104">添加 A/V MCU 池</span><span class="sxs-lookup"><span data-stu-id="8839e-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="8839e-105">没有 collocated A/V 会议服务的中心网站的所有企业版前端服务器都可以使用相同的独立 A/V 会议池。</span><span class="sxs-lookup"><span data-stu-id="8839e-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="8839e-106">对于每个 A/V 会议池, 你必须为该池指定完全限定的域名 (FQDN), 以及它将仅具有单个 A/V 会议服务器还是具有多个负载平衡的 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="8839e-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8839e-107">不能将单个服务器池转换为多服务器池。</span><span class="sxs-lookup"><span data-stu-id="8839e-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="8839e-108">如果稍后确定你的组织需要多服务器池, 则必须删除单服务器池, 然后添加多服务器池。</span><span class="sxs-lookup"><span data-stu-id="8839e-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="8839e-109">如果你计划在将来实现 A/V 会议池, 请选择 "**多台计算机池**"。</span><span class="sxs-lookup"><span data-stu-id="8839e-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="8839e-110">即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8839e-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="8839e-111">当你准备好将更多计算机添加到池中时, 你必须再次使用拓扑生成器来定义新的池成员、发布新拓扑, 然后通过 Skype for Business 服务器部署向导设置新的 A/V 会议池成员。</span><span class="sxs-lookup"><span data-stu-id="8839e-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="8839e-112">A/V 会议服务器池是唯一的, 因为它们不需要负载平衡器即可创建池。</span><span class="sxs-lookup"><span data-stu-id="8839e-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="8839e-113">A/V 会议池内部负载平衡, 并且不需要其他硬件。</span><span class="sxs-lookup"><span data-stu-id="8839e-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

