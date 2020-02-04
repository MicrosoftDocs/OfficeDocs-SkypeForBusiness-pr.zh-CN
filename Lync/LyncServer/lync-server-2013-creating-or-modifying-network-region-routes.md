---
title: Lync Server 2013：创建或修改网络区域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="45848-102">在 Lync Server 2013 中创建或修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="45848-102">Creating or modifying network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45848-103">_**主题上次修改时间：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="45848-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="45848-104">呼叫许可控制（CAC）配置中的每个区域都必须有某种方式才能访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="45848-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="45848-105">虽然区域链接为区域之间的连接设置带宽限制，同时也表示物理链接，但路由决定了连接从一个地区到另一个地区的链接路径。</span><span class="sxs-lookup"><span data-stu-id="45848-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="45848-106">您可以使用 Lync Server "控制面板" 配置网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="45848-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="45848-107">从 Lync Server 控制面板中，你可以创建、修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="45848-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="45848-108">使用本主题创建或修改网络区域路线。</span><span class="sxs-lookup"><span data-stu-id="45848-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="45848-109">有关删除现有网络区域路由的详细信息，请参阅[在 Lync Server 2013 中删除现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="45848-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="45848-110">创建网络区域路由</span><span class="sxs-lookup"><span data-stu-id="45848-110">To create a network region route</span></span>

1.  <span data-ttu-id="45848-111">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="45848-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="45848-112">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="45848-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="45848-113">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="45848-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="45848-114">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域路由**"。</span><span class="sxs-lookup"><span data-stu-id="45848-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="45848-115">在 "**区域路由**" 页面上，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="45848-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="45848-116">在 "**新区域路由**" 中，在 "**名称**" 字段中键入值。</span><span class="sxs-lookup"><span data-stu-id="45848-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45848-117">此值在 Microsoft Lync Server 2013 部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="45848-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="45848-118">从 "**网络区域\#1** " 下拉列表中，选择两个要通过此路由连接的区域之一。</span><span class="sxs-lookup"><span data-stu-id="45848-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="45848-119">从 "**网络区域\#2** " 下拉列表中，选择此路由的其他区域。</span><span class="sxs-lookup"><span data-stu-id="45848-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="45848-120">此区域必须与为 "网络区域\#1" 选择的区域不同。</span><span class="sxs-lookup"><span data-stu-id="45848-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="45848-121">使用 "**网络区域链接**" 列表框将区域链接添加到路由。</span><span class="sxs-lookup"><span data-stu-id="45848-121">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="45848-122">单击 "**添加**" 按钮以显示 "**区域链接**" 页面。</span><span class="sxs-lookup"><span data-stu-id="45848-122">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="45848-123">单击要添加到此路由的区域链接，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="45848-123">Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45848-124">继续单击 "<STRONG>添加</STRONG>" 按钮以添加更多链接，或选择一个链接，然后单击 "<STRONG>删除</STRONG>" 以删除链接。</span><span class="sxs-lookup"><span data-stu-id="45848-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="45848-125">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="45848-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="45848-126">修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="45848-126">To modify a network region route</span></span>

1.  <span data-ttu-id="45848-127">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="45848-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="45848-128">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="45848-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="45848-129">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="45848-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="45848-130">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域路由**"。</span><span class="sxs-lookup"><span data-stu-id="45848-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="45848-131">在 "**区域路由**" 页面上，单击要修改的区域路由。</span><span class="sxs-lookup"><span data-stu-id="45848-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="45848-132">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45848-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="45848-133">在 "**编辑区域" 路由**中，可以修改此路由所联接的区域和与该路由关联的区域链接。</span><span class="sxs-lookup"><span data-stu-id="45848-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="45848-134">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="45848-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="45848-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45848-135">See Also</span></span>


[<span data-ttu-id="45848-136">删除 Lync Server 2013 中的现有网络区域路由</span><span class="sxs-lookup"><span data-stu-id="45848-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

