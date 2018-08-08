---
title: 业务服务器添加到网络站点中 Skype 位置策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 为业务 Server 企业语音给 Skype 中的网络站点分配 E9-1-1 位置策略。
ms.openlocfilehash: 862b6d91371199fe3f9380acf7e2898539153f28
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979823"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="12a6f-103">业务服务器添加到网络站点中 Skype 位置策略</span><span class="sxs-lookup"><span data-stu-id="12a6f-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="12a6f-104">为业务 Server 企业语音给 Skype 中的网络站点分配 E9-1-1 位置策略。</span><span class="sxs-lookup"><span data-stu-id="12a6f-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="12a6f-105">下面的示例演示如何添加到现有网络站点[中的业务服务器 Skype 的创建位置策略](create-location-policies.md)中定义的**Redmond**位置策略以及如何创建新的网络站点使用**雷德蒙德**位置策略。</span><span class="sxs-lookup"><span data-stu-id="12a6f-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="12a6f-106">有关使用网络站点的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="12a6f-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="12a6f-107">**新可**</span><span class="sxs-lookup"><span data-stu-id="12a6f-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="12a6f-108">**Get-csnetworksite**</span><span class="sxs-lookup"><span data-stu-id="12a6f-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="12a6f-109">**Set-csnetworksite**</span><span class="sxs-lookup"><span data-stu-id="12a6f-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="12a6f-110">**删除可**</span><span class="sxs-lookup"><span data-stu-id="12a6f-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="12a6f-111">为现有网络站点分配位置策略</span><span class="sxs-lookup"><span data-stu-id="12a6f-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="12a6f-112">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="12a6f-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="12a6f-113">运行以下 cmdlet 以修改现有网络站点。</span><span class="sxs-lookup"><span data-stu-id="12a6f-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="12a6f-114">将带 **Redmond** 标记的位置策略分配给名为 **Redmond** 的现有网络站点。</span><span class="sxs-lookup"><span data-stu-id="12a6f-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="12a6f-115">为新的网络站点分配位置策略</span><span class="sxs-lookup"><span data-stu-id="12a6f-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="12a6f-116">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="12a6f-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="12a6f-117">运行以下 cmdlet 以创建新的网络站点。</span><span class="sxs-lookup"><span data-stu-id="12a6f-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="12a6f-118">在网络区域中创建新的网络站点，并分配带 **Redmond** 标记的位置策略。</span><span class="sxs-lookup"><span data-stu-id="12a6f-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


