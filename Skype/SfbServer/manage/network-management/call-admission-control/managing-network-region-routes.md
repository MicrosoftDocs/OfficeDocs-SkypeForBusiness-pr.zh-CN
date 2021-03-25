---
title: 管理网络区域路由
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 网络区域路由 定义一对网络区域之间的路由。 呼叫允许控制部署中的每对网络区域均需要网络区域路由。
ms.openlocfilehash: c91f46ff45dd50f638cdb4f256fb93f2d33781ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118551"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="73ecb-104">在 Skype for Business Server 中管理网络区域路由</span><span class="sxs-lookup"><span data-stu-id="73ecb-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="73ecb-105">*网络区域路由* 定义一对网络区域之间的路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="73ecb-106">呼叫允许控制部署中的每对网络区域均需要网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="73ecb-107">这样部署中的每个网络区域便能够访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="73ecb-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="73ecb-108">使用本文中的过程可查看、创建、修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="73ecb-109">查看网络区域路由信息</span><span class="sxs-lookup"><span data-stu-id="73ecb-109">View network region route information</span></span> 

<span data-ttu-id="73ecb-110">呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="73ecb-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="73ecb-111">虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。</span><span class="sxs-lookup"><span data-stu-id="73ecb-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="73ecb-112">使用以下过程在 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序 中查看现有网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="73ecb-113">在 Skype for Business Server 控制面板中查看网络区域路由信息</span><span class="sxs-lookup"><span data-stu-id="73ecb-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="73ecb-114">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="73ecb-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73ecb-115">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="73ecb-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="73ecb-116">在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **路由"。**</span><span class="sxs-lookup"><span data-stu-id="73ecb-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="73ecb-117">在“区域路由”页上，单击要查看的区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="73ecb-118">您一次只能查看一个区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="73ecb-119">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="73ecb-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="73ecb-120">使用 Cmdlet 查看网络区域Windows PowerShell信息</span><span class="sxs-lookup"><span data-stu-id="73ecb-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="73ecb-121">网络区域路由信息可以通过使用 Windows PowerShell 和 Get-CsNetworkInterRegionRoute cmdlet 进行查看。</span><span class="sxs-lookup"><span data-stu-id="73ecb-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="73ecb-122">可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="73ecb-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="73ecb-123">查看网络区域路由信息</span><span class="sxs-lookup"><span data-stu-id="73ecb-123">To view network region route information</span></span>

  - <span data-ttu-id="73ecb-124">若要查看有关所有网络区域路由的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="73ecb-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="73ecb-125">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="73ecb-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="73ecb-126">有关详细信息，请参阅 [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="73ecb-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="73ecb-127">创建或修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="73ecb-127">Create or modify network region routes</span></span>

<span data-ttu-id="73ecb-128">呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="73ecb-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="73ecb-129">虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。</span><span class="sxs-lookup"><span data-stu-id="73ecb-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="73ecb-130">可以使用 Skype for Business Server 控制面板配置网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="73ecb-131">从 Skype for Business Server 控制面板中，可以创建、修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="73ecb-132">使用本主题创建或修改网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="73ecb-133">创建网络区域路由</span><span class="sxs-lookup"><span data-stu-id="73ecb-133">To create a network region route</span></span>

1.  <span data-ttu-id="73ecb-134">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="73ecb-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73ecb-135">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="73ecb-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="73ecb-136">在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **路由"。**</span><span class="sxs-lookup"><span data-stu-id="73ecb-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="73ecb-137">在“区域路由”页上，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="73ecb-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="73ecb-138">在“新建区域路由”的“名称”字段中键入值。</span><span class="sxs-lookup"><span data-stu-id="73ecb-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="73ecb-139">此值在 Skype for Business Server 部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="73ecb-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="73ecb-140">从" **网络区域 \# 1"** 下拉列表中，选择要通过此路由连接的两个区域之一。</span><span class="sxs-lookup"><span data-stu-id="73ecb-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="73ecb-141">从 **"网络区域 \# 2"** 下拉列表中，为此路由选择另一区域。</span><span class="sxs-lookup"><span data-stu-id="73ecb-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="73ecb-142">此区域必须与为网络区域 1 所选的区域 \# 不同。</span><span class="sxs-lookup"><span data-stu-id="73ecb-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="73ecb-p107">使用“网络区域链接”列表框向路由添加区域链接。单击“添加”按钮以显示“区域链接”页面。单击某个区域链接将其添加到此路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="73ecb-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="73ecb-146">继续单击“添加”按钮添加更多链接，还可选择某个链接，然后单击“删除”删除该链接。</span><span class="sxs-lookup"><span data-stu-id="73ecb-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="73ecb-147">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="73ecb-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="73ecb-148">修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="73ecb-148">To modify a network region route</span></span>

1.  <span data-ttu-id="73ecb-149">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="73ecb-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73ecb-150">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="73ecb-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="73ecb-151">在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **路由"。**</span><span class="sxs-lookup"><span data-stu-id="73ecb-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="73ecb-152">在“区域路由”页上，单击要修改的区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="73ecb-153">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="73ecb-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="73ecb-154">在“编辑区域路由”中，可以修改此路由连接的区域以及与此路由关联的区域链接。</span><span class="sxs-lookup"><span data-stu-id="73ecb-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="73ecb-155">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="73ecb-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="73ecb-156">删除现有网络区域路由</span><span class="sxs-lookup"><span data-stu-id="73ecb-156">Delete existing network region routes</span></span>

<span data-ttu-id="73ecb-157">呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="73ecb-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="73ecb-158">虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。</span><span class="sxs-lookup"><span data-stu-id="73ecb-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="73ecb-159">可以使用 Skype for Business Server 控制面板配置网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="73ecb-160">从 Skype for Business Server 控制面板中，可以创建、修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="73ecb-161">使用本主题可删除现有网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="73ecb-162">删除网络区域路由</span><span class="sxs-lookup"><span data-stu-id="73ecb-162">To delete a network region route</span></span>

1.  <span data-ttu-id="73ecb-163">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="73ecb-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73ecb-164">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="73ecb-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="73ecb-165">在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **路由"。**</span><span class="sxs-lookup"><span data-stu-id="73ecb-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="73ecb-166">在“区域路由”页上，单击要删除的区域路由。</span><span class="sxs-lookup"><span data-stu-id="73ecb-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="73ecb-p109">可一次性删除多个区域路由。要执行此操作，请按住 Ctrl 键，同时选择多个区域路由。或者，要选择全部区域路由，请单击“编辑”菜单中的“全选”。</span><span class="sxs-lookup"><span data-stu-id="73ecb-p109">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="73ecb-170">在“编辑”菜单上，单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="73ecb-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="73ecb-171">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="73ecb-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="73ecb-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73ecb-172">See Also</span></span>

[<span data-ttu-id="73ecb-173">在 Skype for Business Server 中管理网络区域</span><span class="sxs-lookup"><span data-stu-id="73ecb-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="73ecb-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="73ecb-174">New-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="73ecb-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="73ecb-175">Set-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="73ecb-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="73ecb-176">Remove-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="73ecb-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="73ecb-177">Get-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Get-CsNetworkInterRegionRoute)