---
title: Lync Server 2013;创建网络 interregion 路由
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: be1c28450708660e2322144802c81d5458ded6da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "34821815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="f4765-102">在 Lync Server 2013 中创建网络 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="f4765-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4765-103">_**主题上次修改时间:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f4765-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f4765-104">*网络 interregion 路线*定义了一对网络区域之间的路线。</span><span class="sxs-lookup"><span data-stu-id="f4765-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="f4765-105">您的呼叫许可控制部署中的每对网络区域都需要网络 interregion 路线。</span><span class="sxs-lookup"><span data-stu-id="f4765-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="f4765-106">这样部署中的每个网络区域便能够访问任何其他区域。</span><span class="sxs-lookup"><span data-stu-id="f4765-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="f4765-107">虽然区域链接为区域之间的连接设置带宽限制, 但 interregion 路由决定了连接将从一个区域遍历到另一个区域的链接路径。</span><span class="sxs-lookup"><span data-stu-id="f4765-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="f4765-108">有关使用网络 interregion 路由的详细信息, 请参阅以下 cmdlet 的 Lync Server Management Shell 文档:</span><span class="sxs-lookup"><span data-stu-id="f4765-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="f4765-109">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f4765-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="f4765-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f4765-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="f4765-111">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f4765-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="f4765-112">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f4765-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="f4765-113">在示例拓扑中, 必须为三个地区对中的每一对定义网络 interregion 路由: 北美洲/EMEA、EMEA/APAC 和北美/APAC。</span><span class="sxs-lookup"><span data-stu-id="f4765-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="f4765-114">使用 Lync Server 命令行管理程序创建网络 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="f4765-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f4765-115">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f4765-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f4765-116">运行 **New-CsNetworkInterRegionRoute** cmdlet 来定义所需路由。</span><span class="sxs-lookup"><span data-stu-id="f4765-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="f4765-117">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="f4765-117">For example, run:</span></span>
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="f4765-118">北美/APAC 网络 interregion 路由需要两个网络区域链接, 因为它们之间没有直接的网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="f4765-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="f4765-119">使用 Lync Server "控制面板" 创建网络 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="f4765-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f4765-120">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f4765-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f4765-121">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f4765-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="f4765-122">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f4765-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="f4765-123">单击“区域路由”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="f4765-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="f4765-124">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f4765-124">Click **New**.</span></span>

5.  <span data-ttu-id="f4765-125">在 "**新建区域路由**" 页面上, 单击 "**名称**", 然后键入网络 interregion 路由的名称。</span><span class="sxs-lookup"><span data-stu-id="f4765-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="f4765-126">单击 "**网络\#区域 1**", 然后在列表中单击要路由到 "网络区域\#2" 的网络区域。</span><span class="sxs-lookup"><span data-stu-id="f4765-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="f4765-127">单击 "**网络\#区域 2**", 然后在列表中单击要路由到 "网络区域\#1" 的网络区域。</span><span class="sxs-lookup"><span data-stu-id="f4765-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="f4765-128">单击 "**网络区域链接**" 字段旁边的 "**添加**", 然后添加将在网络 interregion 路由中使用的网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="f4765-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="f4765-129">如果要为彼此之间没有直接网络区域链接的两个网络区域创建路由，则必须添加所有必要的链接来完成路由。</span><span class="sxs-lookup"><span data-stu-id="f4765-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="f4765-130">例如, 北美/APAC 网络 interregion 路由需要两个网络区域链接, 因为它们之间没有直接的网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="f4765-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="f4765-131">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f4765-131">Click **Commit**.</span></span>

10. <span data-ttu-id="f4765-132">若要完成为拓扑创建网络 interregion 路由, 请使用其他网络 interregion 路由的设置重复步骤4到步骤9。</span><span class="sxs-lookup"><span data-stu-id="f4765-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

