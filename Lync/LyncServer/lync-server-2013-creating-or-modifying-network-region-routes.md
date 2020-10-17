---
title: Lync Server 2013：创建或修改网络区域路由
description: Lync Server 2013：创建或修改网络区域路由。
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
ms.openlocfilehash: 89106c905419778776ea16341f247027d49f1195
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544088"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="6fcff-103">在 Lync Server 2013 中创建或修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="6fcff-103">Creating or modifying network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fcff-104">_**上次修改的主题：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="6fcff-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="6fcff-105">呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="6fcff-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="6fcff-106">虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。</span><span class="sxs-lookup"><span data-stu-id="6fcff-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="6fcff-107">您可以使用 Lync Server 控制面板配置网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="6fcff-107">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="6fcff-108">从 Lync Server 控制面板中，您可以创建、修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="6fcff-108">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="6fcff-109">使用本主题创建或修改网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="6fcff-109">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="6fcff-110">有关删除现有网络区域路由的详细信息，请参阅 [在 Lync Server 2013 中删除现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="6fcff-110">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="6fcff-111">创建网络区域路由</span><span class="sxs-lookup"><span data-stu-id="6fcff-111">To create a network region route</span></span>

1.  <span data-ttu-id="6fcff-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6fcff-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6fcff-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="6fcff-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6fcff-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="6fcff-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6fcff-115">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“区域路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6fcff-115">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="6fcff-116">在“区域路由”\*\*\*\* 页上，单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6fcff-116">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="6fcff-117">在“新建区域路由”\*\*\*\* 的“名称”\*\*\*\* 字段中键入值。</span><span class="sxs-lookup"><span data-stu-id="6fcff-117">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6fcff-118">此值在 Microsoft Lync Server 2013 部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6fcff-118">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="6fcff-119">从 " **网络区域 \# 1** " 下拉列表中，选择两个要通过此路由连接的区域之一。</span><span class="sxs-lookup"><span data-stu-id="6fcff-119">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="6fcff-120">从 " **网络区域 \# 2** " 下拉列表中，选择此路由的其他区域。</span><span class="sxs-lookup"><span data-stu-id="6fcff-120">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="6fcff-121">此区域必须不同于为网络区域1选择的区域 \# 。</span><span class="sxs-lookup"><span data-stu-id="6fcff-121">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="6fcff-p104">使用“网络区域链接”\*\*\*\* 列表框向路由添加区域链接。单击“添加”\*\*\*\* 按钮以显示“区域链接”\*\*\*\* 页面。单击某个区域链接将其添加到此路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6fcff-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6fcff-125">继续单击“添加”<STRONG></STRONG>按钮添加更多链接，还可选择某个链接，然后单击“删除”<STRONG></STRONG>删除该链接。</span><span class="sxs-lookup"><span data-stu-id="6fcff-125">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="6fcff-126">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6fcff-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="6fcff-127">修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="6fcff-127">To modify a network region route</span></span>

1.  <span data-ttu-id="6fcff-128">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6fcff-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6fcff-129">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="6fcff-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6fcff-130">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="6fcff-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6fcff-131">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“区域路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6fcff-131">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="6fcff-132">在“区域路由”\*\*\*\* 页上，单击要修改的区域路由。</span><span class="sxs-lookup"><span data-stu-id="6fcff-132">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="6fcff-133">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6fcff-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="6fcff-134">在“编辑区域路由”\*\*\*\* 中，可以修改此路由连接的区域以及与此路由关联的区域链接。</span><span class="sxs-lookup"><span data-stu-id="6fcff-134">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="6fcff-135">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6fcff-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fcff-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6fcff-136">See Also</span></span>


[<span data-ttu-id="6fcff-137">在 Lync Server 2013 中删除现有网络区域路由</span><span class="sxs-lookup"><span data-stu-id="6fcff-137">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

