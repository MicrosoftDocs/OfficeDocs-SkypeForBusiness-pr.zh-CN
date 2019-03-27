---
title: 管理网络区域路由
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络区域路由定义一对网络区域之间的路由。 每对网络区域中您的呼叫允许控制部署需要网络区域路由。
ms.openlocfilehash: 12e8d9072df3affdb6e47b6ddb0452e0ee5982a5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898121"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="90403-104">在 Skype for Business Server 中管理网络区域路由</span><span class="sxs-lookup"><span data-stu-id="90403-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="90403-105">*网络区域路由*定义一对网络区域之间的路由。</span><span class="sxs-lookup"><span data-stu-id="90403-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="90403-106">每对网络区域中您的呼叫允许控制部署需要网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="90403-107">这样部署中的每个网络区域便能够访问任何其他区域。</span><span class="sxs-lookup"><span data-stu-id="90403-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="90403-108">使用本节中此 artilce 以查看、 创建、 修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="90403-109">查看网络区域路由信息</span><span class="sxs-lookup"><span data-stu-id="90403-109">View network region route information</span></span> 

<span data-ttu-id="90403-110">呼叫允许控制 (CAC) 配置中的每个区域都必须具有一种方式访问每个其他区域。</span><span class="sxs-lookup"><span data-stu-id="90403-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="90403-111">虽然区域链接区域之间的连接设置带宽限制，并且还表示物理链路，路由可确定连接从一个区域将遍历到另一个的链接的路径。</span><span class="sxs-lookup"><span data-stu-id="90403-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="90403-112">使用以下过程可以查看现有网络区域路由中 Skype 业务 Server Control Panel 或 Skype 的业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="90403-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="90403-113">若要查看网络区域路由信息 Skype 中的业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="90403-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="90403-114">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="90403-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90403-115">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="90403-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="90403-116">在左侧的导航栏中，单击**网络配置**，然后单击**区域路由**。</span><span class="sxs-lookup"><span data-stu-id="90403-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="90403-117">在**区域路由**页上，单击您想要查看的区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="90403-118">一次只能查看一个区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="90403-119">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90403-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="90403-120">使用 Windows PowerShell Cmdlet 查看网络区域路由信息</span><span class="sxs-lookup"><span data-stu-id="90403-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="90403-121">可以通过使用 Windows PowerShell 和 Get-csnetworkinterregionroute cmdlet 查看网络区域路由信息。</span><span class="sxs-lookup"><span data-stu-id="90403-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="90403-122">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="90403-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="90403-123">若要查看网络区域路由信息</span><span class="sxs-lookup"><span data-stu-id="90403-123">To view network region route information</span></span>

  - <span data-ttu-id="90403-124">若要查看有关所有网络区域路由信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="90403-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="90403-125">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="90403-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="90403-126">有关详细信息，请参阅[Get-csnetworkinterregionroute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="90403-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="90403-127">创建或修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="90403-127">Create or modify network region routes</span></span>

<span data-ttu-id="90403-128">呼叫允许控制 (CAC) 配置中的每个区域都必须具有一种方式访问每个其他区域。</span><span class="sxs-lookup"><span data-stu-id="90403-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="90403-129">虽然区域链接区域之间的连接设置带宽限制，并且还表示物理链路，路由可确定连接从一个区域将遍历到另一个的链接的路径。</span><span class="sxs-lookup"><span data-stu-id="90403-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="90403-130">您可以使用业务 Server Control Panel 的 Skype 配置网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="90403-131">从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="90403-132">使用本主题可创建或修改网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="90403-133">创建网络区域路由</span><span class="sxs-lookup"><span data-stu-id="90403-133">To create a network region route</span></span>

1.  <span data-ttu-id="90403-134">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="90403-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90403-135">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="90403-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="90403-136">在左侧的导航栏中，单击**网络配置**，然后单击**区域路由**。</span><span class="sxs-lookup"><span data-stu-id="90403-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="90403-137">在**区域路由**页上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="90403-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="90403-138">在**新建区域路由**中，键入**名称**字段中的值。</span><span class="sxs-lookup"><span data-stu-id="90403-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="90403-139">此值必须是唯一您 Skype 业务服务器部署中。</span><span class="sxs-lookup"><span data-stu-id="90403-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="90403-140">从**网络区域\#1**下拉列表中，选择要通过此路由进行连接的两个区域之一。</span><span class="sxs-lookup"><span data-stu-id="90403-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="90403-141">从**网络区域\#2**下拉列表中，选择该路由的其他区域。</span><span class="sxs-lookup"><span data-stu-id="90403-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="90403-142">此区域必须不同于网络区域选择的区域\#1。</span><span class="sxs-lookup"><span data-stu-id="90403-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="90403-143">使用**网络区域链接**列表框添加到路由的区域链接。</span><span class="sxs-lookup"><span data-stu-id="90403-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="90403-144">单击**添加**按钮以显示**区域链接**页。</span><span class="sxs-lookup"><span data-stu-id="90403-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="90403-145">单击要添加到该路由，区域链接，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="90403-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="90403-146">继续单击**添加**按钮添加更多链接，或选择一个链接并单击**删除**以删除链接。</span><span class="sxs-lookup"><span data-stu-id="90403-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="90403-147">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="90403-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="90403-148">修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="90403-148">To modify a network region route</span></span>

1.  <span data-ttu-id="90403-149">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="90403-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90403-150">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="90403-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="90403-151">在左侧的导航栏中，单击**网络配置**，然后单击**区域路由**。</span><span class="sxs-lookup"><span data-stu-id="90403-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="90403-152">在**区域路由**页上，单击要修改的区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="90403-153">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90403-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="90403-154">在**编辑区域路由**，可以修改此路由连接的区域以及与此路由关联的区域链接。</span><span class="sxs-lookup"><span data-stu-id="90403-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="90403-155">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="90403-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="90403-156">删除现有网络区域路由</span><span class="sxs-lookup"><span data-stu-id="90403-156">Delete existing network region routes</span></span>

<span data-ttu-id="90403-157">呼叫允许控制 (CAC) 配置中的每个区域都必须具有一种方式访问每个其他区域。</span><span class="sxs-lookup"><span data-stu-id="90403-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="90403-158">虽然区域链接区域之间的连接设置带宽限制，并且还表示物理链路，路由可确定连接从一个区域将遍历到另一个的链接的路径。</span><span class="sxs-lookup"><span data-stu-id="90403-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="90403-159">您可以使用业务 Server Control Panel 的 Skype 配置网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="90403-160">从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="90403-161">使用本主题可删除现有网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="90403-162">删除网络区域路由</span><span class="sxs-lookup"><span data-stu-id="90403-162">To delete a network region route</span></span>

1.  <span data-ttu-id="90403-163">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="90403-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90403-164">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="90403-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="90403-165">在左侧的导航栏中，单击**网络配置**，然后单击**区域路由**。</span><span class="sxs-lookup"><span data-stu-id="90403-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="90403-166">在**区域路由**页上，单击您想要删除的区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="90403-167">您可以一次删除多个区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="90403-168">若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个区域路由。</span><span class="sxs-lookup"><span data-stu-id="90403-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="90403-169">或者，若要选择所有区域路由，**都选择全部**上单击**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="90403-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="90403-170">在**编辑**菜单上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="90403-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="90403-171">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="90403-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="90403-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90403-172">See Also</span></span>

[<span data-ttu-id="90403-173">在 Skype for Business Server 中管理网络区域</span><span class="sxs-lookup"><span data-stu-id="90403-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="90403-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="90403-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="90403-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="90403-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="90403-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="90403-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="90403-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="90403-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
