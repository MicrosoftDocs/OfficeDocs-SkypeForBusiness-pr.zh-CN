---
title: 添加 A/V MCU 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: 所有 Enterprise Edition 前端服务器的中央站点没有并置的 A / V 会议服务可以使用相同的独立 A / V 会议池。 每个 a / V 会议池，必须指定完全限定的域名 (FQDN) 的池以及是否将具有单个 A / V 会议服务器或多个负载平衡 A / V 会议服务器。
ms.openlocfilehash: f88476165ce6affe23e9e5cbb33e03a997c04971
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202301"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="c3194-104">添加 A/V MCU 池</span><span class="sxs-lookup"><span data-stu-id="c3194-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="c3194-105">所有 Enterprise Edition 前端服务器的中央站点没有并置的 A / V 会议服务可以使用相同的独立 A / V 会议池。</span><span class="sxs-lookup"><span data-stu-id="c3194-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="c3194-106">每个 a / V 会议池，必须指定完全限定的域名 (FQDN) 的池以及是否将具有单个 A / V 会议服务器或多个负载平衡 A / V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="c3194-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c3194-107">您不能将单服务器池转换为多服务器池。</span><span class="sxs-lookup"><span data-stu-id="c3194-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="c3194-108">如果您以后决定您的组织需要多服务器池，必须删除单服务器池，并将多服务器池。</span><span class="sxs-lookup"><span data-stu-id="c3194-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="c3194-109">如果您打算实现 A / V 会议池将来，选择**多个计算机池**。</span><span class="sxs-lookup"><span data-stu-id="c3194-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="c3194-110">即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c3194-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="c3194-111">当您准备好以后向池中添加更多计算机时，您必须拓扑生成器再次以定义新的池成员和发布新拓扑，然后设置新的 A / V 会议池成员通过 Skype 的业务 Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="c3194-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="c3194-112">A / V 会议服务器池都是唯一的它们不需要加载平衡器来创建池。</span><span class="sxs-lookup"><span data-stu-id="c3194-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="c3194-113">A / V 会议池内部负载平衡和不需要额外的硬件。</span><span class="sxs-lookup"><span data-stu-id="c3194-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

