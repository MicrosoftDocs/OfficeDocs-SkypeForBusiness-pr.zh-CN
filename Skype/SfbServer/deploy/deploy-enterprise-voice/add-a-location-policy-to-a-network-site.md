---
title: 在 Skype for Business Server 中向网络站点添加位置策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 将 E9-1-1 位置策略分配给 Skype for Business Server 企业语音。
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804272"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="5e93e-103">在 Skype for Business Server 中向网络站点添加位置策略</span><span class="sxs-lookup"><span data-stu-id="5e93e-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="5e93e-104">将 E9-1-1 位置策略分配给 Skype for Business Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="5e93e-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="5e93e-105">以下示例显示如何将 [Skype for Business Server](create-location-policies.md)中的"创建位置策略"中定义的 **Redmond** 位置策略添加到现有网络站点，以及如何创建使用 **Redmond** 位置策略的新网络站点。</span><span class="sxs-lookup"><span data-stu-id="5e93e-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="5e93e-106">有关使用网络站点的详细信息，请参阅以下 cmdlet 的 Lync Server 命令行管理程序文档：</span><span class="sxs-lookup"><span data-stu-id="5e93e-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="5e93e-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="5e93e-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="5e93e-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="5e93e-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="5e93e-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="5e93e-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="5e93e-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="5e93e-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="5e93e-111">为现有网络站点分配位置策略</span><span class="sxs-lookup"><span data-stu-id="5e93e-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="5e93e-112">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="5e93e-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5e93e-113">运行以下 cmdlet 以修改现有网络站点。</span><span class="sxs-lookup"><span data-stu-id="5e93e-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="5e93e-114">将 **Redmond** 标记的位置策略分配给名为 **Redmond 的现有网络站点**。</span><span class="sxs-lookup"><span data-stu-id="5e93e-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="5e93e-115">为新的网络站点分配位置策略</span><span class="sxs-lookup"><span data-stu-id="5e93e-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="5e93e-116">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="5e93e-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5e93e-117">运行以下 cmdlet 以创建新的网络站点。</span><span class="sxs-lookup"><span data-stu-id="5e93e-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="5e93e-118">在网络区域中创建新的网络站点，并分配 **Redmond** 带标记的位置策略。</span><span class="sxs-lookup"><span data-stu-id="5e93e-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


