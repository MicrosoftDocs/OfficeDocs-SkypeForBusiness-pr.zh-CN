---
title: Lync Server 2013;创建网络 interregion 路由
description: Lync Server 2013;创建网络 interregion 路由。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 44c8c62a86f7cfb6ca5b1148dc097c1d7786ad29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546048"
---
# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="a54f2-103">在 Lync Server 2013 中创建网络 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="a54f2-103">Create network interregion routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a54f2-104">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a54f2-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a54f2-p101">“网络区域间路由”\*\* 定义一对网络区域之间的路由。呼叫允许控制部署中的每对网络区域均需要网络区域间路由。这样部署中的每个网络区域便能够访问任何其他区域。</span><span class="sxs-lookup"><span data-stu-id="a54f2-p101">A *network interregion route* defines the route between a pair of network regions. Each pair of network regions in your call admission control deployment requires a network interregion route. This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="a54f2-108">虽然区域链接会对区域之间的连接设置带宽限制，但是区域间路由可确定连接从一个区域到另一个区域将遍历的链接路径。</span><span class="sxs-lookup"><span data-stu-id="a54f2-108">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="a54f2-109">有关使用网络 interregion 路由的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a54f2-109">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a54f2-110">新 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a54f2-110">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="a54f2-111">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a54f2-111">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="a54f2-112">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a54f2-112">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="a54f2-113">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a54f2-113">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="a54f2-114">在示例拓扑中，必须为三个区域对中的每一对定义网络区域间路由：北美/EMEA、EMEA/APAC 以及北美/APAC。</span><span class="sxs-lookup"><span data-stu-id="a54f2-114">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="a54f2-115">使用 Lync Server 命令行管理程序创建网络 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="a54f2-115">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="a54f2-116">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a54f2-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a54f2-117">运行 **New-CsNetworkInterRegionRoute** cmdlet 来定义所需路由。</span><span class="sxs-lookup"><span data-stu-id="a54f2-117">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="a54f2-118">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="a54f2-118">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="a54f2-119">北美/APAC 的网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="a54f2-119">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="a54f2-120">使用 Lync Server 控制面板创建网络 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="a54f2-120">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a54f2-121">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a54f2-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a54f2-122">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="a54f2-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a54f2-123">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a54f2-123">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a54f2-124">单击“区域路由”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="a54f2-124">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="a54f2-125">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a54f2-125">Click **New**.</span></span>

5.  <span data-ttu-id="a54f2-126">在“新建区域路由”\*\*\*\* 页上，单击“名称”\*\*\*\*，然后键入网络区域间路由的名称。</span><span class="sxs-lookup"><span data-stu-id="a54f2-126">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="a54f2-127">单击 " **网络区域 \# 1**"，然后在列表中单击要路由到 "网络区域 2" 的网络区域 \# 。</span><span class="sxs-lookup"><span data-stu-id="a54f2-127">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="a54f2-128">单击 " **网络区域 \# 2**"，然后在列表中单击要路由到 "网络区域 1" 的网络区域 \# 。</span><span class="sxs-lookup"><span data-stu-id="a54f2-128">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="a54f2-129">单击“网络区域链接”\*\*\*\* 字段旁边的“添加”\*\*\*\*，然后添加将用于网络区域间路由的网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="a54f2-129">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="a54f2-p104">如果要为彼此之间没有直接网络区域链接的两个网络区域创建路由，则必须添加所有必要的链接来完成路由。例如，北美/APAC 网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="a54f2-p104">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="a54f2-132">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a54f2-132">Click **Commit**.</span></span>

10. <span data-ttu-id="a54f2-133">要为拓扑完成网络区域间路由的创建，请为其他网络区域间路由重复步骤 4 至 步骤 9 的设置。</span><span class="sxs-lookup"><span data-stu-id="a54f2-133">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

