---
title: 在 Skype for Business Server 2015 中向网络站点添加位置策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 为业务服务器企业语音 E9-1-1 位置策略分配在 Skype 的网络站点。
ms.openlocfilehash: bf2b8675ebaa14e98f8a362b3a0714037000de95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a><span data-ttu-id="c18ee-103">在 Skype for Business Server 2015 中向网络站点添加位置策略</span><span class="sxs-lookup"><span data-stu-id="c18ee-103">Add a location policy to a network site in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c18ee-104">为业务服务器企业语音 E9-1-1 位置策略分配在 Skype 的网络站点。</span><span class="sxs-lookup"><span data-stu-id="c18ee-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c18ee-105">下面的示例演示如何添加到现有的网络站点[中的业务服务器 2015 Skype 的创建位置策略](create-location-policies.md)中定义的**雷蒙德**位置策略以及如何创建新的网络站点使用**雷蒙德**总部策略。</span><span class="sxs-lookup"><span data-stu-id="c18ee-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server 2015](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="c18ee-106">有关如何使用网络站点的详细信息，请参阅以下 cmdlet 的 Lync 服务器管理外壳程序文档：</span><span class="sxs-lookup"><span data-stu-id="c18ee-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="c18ee-107">**新 CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="c18ee-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="c18ee-108">**获得 CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="c18ee-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="c18ee-109">**一组 CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="c18ee-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="c18ee-110">**删除 CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="c18ee-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="c18ee-111">为现有网络站点分配位置策略</span><span class="sxs-lookup"><span data-stu-id="c18ee-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="c18ee-112">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="c18ee-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c18ee-113">运行以下 cmdlet 以修改现有网络站点。</span><span class="sxs-lookup"><span data-stu-id="c18ee-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="c18ee-114">将带 **Redmond** 标记的位置策略分配给名为 **Redmond** 的现有网络站点。</span><span class="sxs-lookup"><span data-stu-id="c18ee-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="c18ee-115">为新的网络站点分配位置策略</span><span class="sxs-lookup"><span data-stu-id="c18ee-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="c18ee-116">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="c18ee-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c18ee-117">运行以下 cmdlet 以创建新的网络站点。</span><span class="sxs-lookup"><span data-stu-id="c18ee-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="c18ee-118">在网络区域中创建新的网络站点，并分配带 **Redmond** 标记的位置策略。</span><span class="sxs-lookup"><span data-stu-id="c18ee-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


