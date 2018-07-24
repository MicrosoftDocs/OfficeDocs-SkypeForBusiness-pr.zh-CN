---
title: 修补程序或更新业务服务器 Skype 在前端服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 摘要： 了解如何为业务 Server 到 Skype 在前端服务器应用升级或修补程序。
ms.openlocfilehash: 29191192b1dab16b79cc594cc0a7b3b68aaa906f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20972770"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="801a0-103">修补程序或更新业务服务器 Skype 在前端服务器</span><span class="sxs-lookup"><span data-stu-id="801a0-103">Patch or update Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="801a0-104">**摘要：** 了解如何为业务 Server 到 Skype 在前端服务器应用升级或修补程序。</span><span class="sxs-lookup"><span data-stu-id="801a0-104">**Summary:** learn how to apply upgrades or patches to Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="801a0-105">修补程序在前端池中的服务器时，您一次执行因此一台服务器。</span><span class="sxs-lookup"><span data-stu-id="801a0-105">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="801a0-106">对池中的前端服务器应用升级</span><span class="sxs-lookup"><span data-stu-id="801a0-106">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="801a0-107">键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="801a0-107">Type the following cmdlet:</span></span>
    
  ```
  Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
  ```

     <span data-ttu-id="801a0-108">如果此 cmdlet 显示存在任何丢失副本，请运行以下 cmdlet 以恢复池，然后才能应用修补程序。</span><span class="sxs-lookup"><span data-stu-id="801a0-108">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
  ```
  Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
  ```

2. <span data-ttu-id="801a0-109">在要修补的第一台服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="801a0-109">On the first server you want to patch, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="801a0-110">此 cmdlet 将所有服务都移动到其他前端服务器池中，并使此服务器脱机。</span><span class="sxs-lookup"><span data-stu-id="801a0-110">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="801a0-111">为此服务器应用升级或修补。</span><span class="sxs-lookup"><span data-stu-id="801a0-111">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="801a0-112">在升级后的服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="801a0-112">On the upgraded server, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="801a0-113">服务器重新返回服务。</span><span class="sxs-lookup"><span data-stu-id="801a0-113">The server is returned to service.</span></span>
    
5. <span data-ttu-id="801a0-114">对需要升级的每台服务器执行步骤 2-4。</span><span class="sxs-lookup"><span data-stu-id="801a0-114">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    

