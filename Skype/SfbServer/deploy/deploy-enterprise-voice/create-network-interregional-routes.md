---
title: 在 Skype for Business Server 2015 中创建网络区域间路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 创建或修改网络 interregional 路由，使用 Skype 中的企业语音呼叫允许控制业务服务器。
ms.openlocfilehash: f9f395325ecf2df35ac43730501603c2fdda9157
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500605"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server-2015"></a><span data-ttu-id="9bc53-103">在 Skype for Business Server 2015 中创建网络区域间路由</span><span class="sxs-lookup"><span data-stu-id="9bc53-103">Create network interregional routes in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9bc53-104">创建或修改网络 interregional 路由，使用 Skype 中的企业语音呼叫允许控制业务服务器。</span><span class="sxs-lookup"><span data-stu-id="9bc53-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="9bc53-105">网络 interregional 路由定义一对网络区域之间的路由。</span><span class="sxs-lookup"><span data-stu-id="9bc53-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="9bc53-106">呼叫允许控制部署中的每对网络区域均需要网络区域间路由。</span><span class="sxs-lookup"><span data-stu-id="9bc53-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="9bc53-107">这样部署中的每个网络区域便能够访问任何其他区域。</span><span class="sxs-lookup"><span data-stu-id="9bc53-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="9bc53-108">虽然区域链接会对区域之间的连接设置带宽限制，但是区域间路由可确定连接从一个区域到另一个区域将遍历的链接路径。</span><span class="sxs-lookup"><span data-stu-id="9bc53-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="9bc53-109">在示例拓扑中，必须为三个区域对中的每一对定义网络区域间路由：北美/EMEA、EMEA/APAC 以及北美/APAC。</span><span class="sxs-lookup"><span data-stu-id="9bc53-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9bc53-110">使用 Skype 业务 Server 命令行管理程序创建网络 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="9bc53-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="9bc53-111">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="9bc53-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9bc53-112">运行**新建 CsNetworkInterRegionRoute** cmdlet 可以定义所需的路由。</span><span class="sxs-lookup"><span data-stu-id="9bc53-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="9bc53-113">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="9bc53-113">For example, run:</span></span>
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="9bc53-114">北美/APAC 的网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="9bc53-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9bc53-115">使用 Skype 业务 Server 控制面板创建网络 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="9bc53-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9bc53-116">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="9bc53-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="9bc53-117">在左侧导航栏中，单击“网络配置”****。</span><span class="sxs-lookup"><span data-stu-id="9bc53-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="9bc53-118">单击“区域路由”**** 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="9bc53-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="9bc53-119">单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="9bc53-119">Click **New**.</span></span>
    
5. <span data-ttu-id="9bc53-120">在“**新建区域路由**”页上，单击“**名称**”，然后键入网络区域间路由的名称。</span><span class="sxs-lookup"><span data-stu-id="9bc53-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="9bc53-121">单击“网络区域 #1”****，然后在列表中单击要路由到网络区域 #2 的网络区域。</span><span class="sxs-lookup"><span data-stu-id="9bc53-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="9bc53-122">单击“网络区域 #2”****，然后在列表中单击要路由到网络区域 #1 的网络区域。</span><span class="sxs-lookup"><span data-stu-id="9bc53-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="9bc53-123">单击“**网络区域链接**”字段旁边的“**添加**”，然后添加将用于网络区域间路由的网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="9bc53-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bc53-p103">如果要为彼此之间没有直接网络区域链接的两个网络区域创建路由，则必须添加所有必要的链接来完成路由。例如，北美/APAC 网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="9bc53-p103">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="9bc53-126">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="9bc53-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="9bc53-127">要为拓扑完成网络区域间路由的创建，请为其他网络区域间路由重复步骤 4 至 步骤 9 的设置。</span><span class="sxs-lookup"><span data-stu-id="9bc53-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9bc53-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bc53-128">See also</span></span>

[<span data-ttu-id="9bc53-129">新 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9bc53-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="9bc53-130">Get-csnetworkinterregionroute</span><span class="sxs-lookup"><span data-stu-id="9bc53-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="9bc53-131">设置 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9bc53-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="9bc53-132">删除 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9bc53-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)