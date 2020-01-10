---
title: 在 Skype for Business 服务器中创建网络 interregional 路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 创建或修改网络 interregional 路由，这些路由由 Skype for Business Server 中的 "企业语音呼叫许可控制" 使用。
ms.openlocfilehash: 6d9517796b2f418c39873850ee596a5effdba4e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001752"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="095a7-103">在 Skype for Business 服务器中创建网络 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="095a7-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="095a7-104">创建或修改网络 interregional 路由，这些路由由 Skype for Business Server 中的 "企业语音呼叫许可控制" 使用。</span><span class="sxs-lookup"><span data-stu-id="095a7-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="095a7-105">网络区域间路由定义一对网络区域之间的路由。</span><span class="sxs-lookup"><span data-stu-id="095a7-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="095a7-106">呼叫允许控制部署中的每对网络区域均需要网络区域间路由。</span><span class="sxs-lookup"><span data-stu-id="095a7-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="095a7-107">这样部署中的每个网络区域便能够访问任何其他区域。</span><span class="sxs-lookup"><span data-stu-id="095a7-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="095a7-108">虽然区域链接会对区域之间的连接设置带宽限制，但是区域间路由可确定连接从一个区域到另一个区域将遍历的链接路径。</span><span class="sxs-lookup"><span data-stu-id="095a7-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="095a7-109">在示例拓扑中，必须为三个区域对中的每一对定义网络区域间路由：北美/EMEA、EMEA/APAC 以及北美/APAC。</span><span class="sxs-lookup"><span data-stu-id="095a7-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="095a7-110">使用 Skype for Business Server 命令行管理程序创建网络 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="095a7-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="095a7-111">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="095a7-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="095a7-112">运行 **New-CsNetworkInterRegionRoute** cmdlet 来定义所需路由。</span><span class="sxs-lookup"><span data-stu-id="095a7-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="095a7-113">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="095a7-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="095a7-114">北美/APAC 的网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="095a7-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="095a7-115">使用 Skype for Business 服务器控制面板创建网络 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="095a7-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="095a7-116">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="095a7-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="095a7-117">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="095a7-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="095a7-118">单击“区域路由”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="095a7-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="095a7-119">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="095a7-119">Click **New**.</span></span>
    
5. <span data-ttu-id="095a7-120">在“**新建区域路由**”页上，单击“**名称**”，然后键入网络区域间路由的名称。</span><span class="sxs-lookup"><span data-stu-id="095a7-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="095a7-121">单击“网络区域 #1”\*\*\*\*，然后在列表中单击要路由到网络区域 #2 的网络区域。</span><span class="sxs-lookup"><span data-stu-id="095a7-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="095a7-122">单击“网络区域 #2”\*\*\*\*，然后在列表中单击要路由到网络区域 #1 的网络区域。</span><span class="sxs-lookup"><span data-stu-id="095a7-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="095a7-123">单击“**网络区域链接**”字段旁边的“**添加**”，然后添加将用于网络区域间路由的网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="095a7-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="095a7-p103">如果要为彼此之间没有直接网络区域链接的两个网络区域创建路由，则必须添加所有必要的链接来完成路由。例如，北美/APAC 网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="095a7-p103">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="095a7-126">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="095a7-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="095a7-127">要为拓扑完成网络区域间路由的创建，请为其他网络区域间路由重复步骤 4 至 步骤 9 的设置。</span><span class="sxs-lookup"><span data-stu-id="095a7-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="095a7-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="095a7-128">See also</span></span>

[<span data-ttu-id="095a7-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="095a7-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="095a7-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="095a7-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="095a7-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="095a7-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="095a7-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="095a7-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
