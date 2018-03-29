---
title: 在 Skype for Business Server 2015 中添加或删除前端服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要： 了解如何添加或删除在 Skype 业务服务器的前端服务器。
ms.openlocfilehash: aed52becf5d4cc97307f9788a81f8d6563d1d25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="5eefa-103">在 Skype for Business Server 2015 中添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="5eefa-103">Add or remove a Front End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5eefa-104">**摘要：**了解如何添加或删除在 Skype 业务服务器的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="5eefa-104">**Summary:** Learn how to add or remove Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="5eefa-105">当您将前端服务器添加到库中，或从池中删除前端服务器时，然后需要重新启动该池。</span><span class="sxs-lookup"><span data-stu-id="5eefa-105">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5eefa-p101">当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="5eefa-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="5eefa-109">您可以使用以下过程添加或删除前端服务器时。</span><span class="sxs-lookup"><span data-stu-id="5eefa-109">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5eefa-110">如果将新服务器添加到池，请将您的新池服务器更新为与池中的现有服务器相同的累积更新级别。</span><span class="sxs-lookup"><span data-stu-id="5eefa-110">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="5eefa-111">若要添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="5eefa-111">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="5eefa-112">如果要删除所有前端服务器，请首先停止与这些服务器的新连接。</span><span class="sxs-lookup"><span data-stu-id="5eefa-112">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="5eefa-113">为此，您可以使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5eefa-113">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="5eefa-114">打开拓扑生成器以及添加或移除所需的服务器。</span><span class="sxs-lookup"><span data-stu-id="5eefa-114">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="5eefa-115">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="5eefa-115">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5eefa-p103">当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="5eefa-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
4. <span data-ttu-id="5eefa-119">如果您更改了服务器的数量在前端池中任一下列方式，然后通过键入以下 cmdlet 复位与池： 重置-CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="5eefa-119">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="5eefa-120">2 到任意</span><span class="sxs-lookup"><span data-stu-id="5eefa-120">2 to any</span></span>
    
     - <span data-ttu-id="5eefa-121">任意到 2</span><span class="sxs-lookup"><span data-stu-id="5eefa-121">Any to 2</span></span>
    
     - <span data-ttu-id="5eefa-122">3 到任意</span><span class="sxs-lookup"><span data-stu-id="5eefa-122">3 to any</span></span>
    
     - <span data-ttu-id="5eefa-123">任意到 3</span><span class="sxs-lookup"><span data-stu-id="5eefa-123">Any to 3</span></span>
    
5. <span data-ttu-id="5eefa-124">键入以下 cmdlet 以重新启动该池</span><span class="sxs-lookup"><span data-stu-id="5eefa-124">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```


