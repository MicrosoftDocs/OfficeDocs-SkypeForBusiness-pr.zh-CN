---
title: 添加 A / V MCU 池
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 所有企业版前端服务器的中心站点没有并入 A / V 会议服务可以使用相同的独立 A / V 会议池。 对于每个 A / V 会议池，必须指定完全限定的域名称 (FQDN) 的池和是否会有一个 A / V 会议服务器或多个负载平衡 A / V 会议服务器。
ms.openlocfilehash: d1712829030836446c06a2e335c424d51a19e466
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="1dd90-104">添加 A / V MCU 池</span><span class="sxs-lookup"><span data-stu-id="1dd90-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="1dd90-105">所有企业版前端服务器的中心站点没有并入 A / V 会议服务可以使用相同的独立 A / V 会议池。</span><span class="sxs-lookup"><span data-stu-id="1dd90-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="1dd90-106">对于每个 A / V 会议池，必须指定完全限定的域名称 (FQDN) 的池和是否会有一个 A / V 会议服务器或多个负载平衡 A / V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="1dd90-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1dd90-107">不能将单服务器池转换到多服务器池。</span><span class="sxs-lookup"><span data-stu-id="1dd90-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="1dd90-108">如果您以后决定您的组织需要一个多服务器池，您必须删除该单服务器池，，然后添加多个服务器池。</span><span class="sxs-lookup"><span data-stu-id="1dd90-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="1dd90-109">如果您计划如何实现 A / V 会议池以后，选择**多个计算机池**。</span><span class="sxs-lookup"><span data-stu-id="1dd90-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="1dd90-110">即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1dd90-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="1dd90-111">当准备好以后向池中添加更多的计算机时，您必须拓扑生成器再次以定义新的池成员发布新的拓扑，然后设置了新的 / V 会议池成员通过 Skype 业务服务器部署向导。</span><span class="sxs-lookup"><span data-stu-id="1dd90-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="1dd90-112">A / V 会议服务器池都是唯一的因为它们不需要加载平衡器来创建池。</span><span class="sxs-lookup"><span data-stu-id="1dd90-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="1dd90-113">A / V 会议池内部负载平衡，并不需要额外的硬件。</span><span class="sxs-lookup"><span data-stu-id="1dd90-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

