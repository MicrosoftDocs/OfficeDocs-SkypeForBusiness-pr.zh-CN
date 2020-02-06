---
title: 管理网络区域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 网络区域路由定义一对网络区域之间的路线。 呼叫许可控制部署中的每对网络区域都需要网络区域路线。
ms.openlocfilehash: 5e0c099b8c461873b96963c721d835f1ccdf4705
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817491"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="1c55c-104">在 Skype for Business Server 中管理网络区域路由</span><span class="sxs-lookup"><span data-stu-id="1c55c-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="1c55c-105">*网络区域路由*定义一对网络区域之间的路线。</span><span class="sxs-lookup"><span data-stu-id="1c55c-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="1c55c-106">呼叫许可控制部署中的每对网络区域都需要网络区域路线。</span><span class="sxs-lookup"><span data-stu-id="1c55c-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="1c55c-107">这样部署中的每个网络区域便能够访问任何其他区域。</span><span class="sxs-lookup"><span data-stu-id="1c55c-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="1c55c-108">使用此 artilce 中的过程查看、创建、修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="1c55c-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="1c55c-109">查看网络区域路线信息</span><span class="sxs-lookup"><span data-stu-id="1c55c-109">View network region route information</span></span> 

<span data-ttu-id="1c55c-110">呼叫许可控制（CAC）配置中的每个区域都必须有某种方式才能访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="1c55c-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="1c55c-111">虽然区域链接为区域之间的连接设置带宽限制，同时也表示物理链接，但路由决定了连接从一个地区到另一个地区的链接路径。</span><span class="sxs-lookup"><span data-stu-id="1c55c-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="1c55c-112">使用以下过程可查看 Skype for business Server 控制面板或 Skype for business Server Management Shell 中的现有网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="1c55c-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="1c55c-113">在 "Skype for Business 服务器" 控制面板中查看网络区域路线信息</span><span class="sxs-lookup"><span data-stu-id="1c55c-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1c55c-114">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1c55c-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c55c-115">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="1c55c-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1c55c-116">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域路由**"。</span><span class="sxs-lookup"><span data-stu-id="1c55c-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="1c55c-117">在 "**区域路线**" 页面上，单击要查看的地区路线。</span><span class="sxs-lookup"><span data-stu-id="1c55c-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="1c55c-118">一次只能查看一个区域路线。</span><span class="sxs-lookup"><span data-stu-id="1c55c-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="1c55c-119">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c55c-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1c55c-120">使用 Windows PowerShell Cmdlet 查看网络区域路由信息</span><span class="sxs-lookup"><span data-stu-id="1c55c-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1c55c-121">可以使用 Windows PowerShell 和 CsNetworkInterRegionRoute cmdlet 查看网络区域路线信息。</span><span class="sxs-lookup"><span data-stu-id="1c55c-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="1c55c-122">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="1c55c-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="1c55c-123">查看网络区域路线信息</span><span class="sxs-lookup"><span data-stu-id="1c55c-123">To view network region route information</span></span>

  - <span data-ttu-id="1c55c-124">若要查看有关所有网络区域路由的信息，请在 Skype for Business Server 命令行管理器中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="1c55c-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="1c55c-125">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="1c55c-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="1c55c-126">有关详细信息，请参阅[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="1c55c-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="1c55c-127">创建或修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="1c55c-127">Create or modify network region routes</span></span>

<span data-ttu-id="1c55c-128">呼叫许可控制（CAC）配置中的每个区域都必须有某种方式才能访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="1c55c-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="1c55c-129">虽然区域链接为区域之间的连接设置带宽限制，同时也表示物理链接，但路由决定了连接从一个地区到另一个地区的链接路径。</span><span class="sxs-lookup"><span data-stu-id="1c55c-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="1c55c-130">您可以使用 Skype for Business 服务器控制面板配置网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="1c55c-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="1c55c-131">从 "Skype for Business 服务器" 控制面板中，您可以创建、修改或删除网络区域路线。</span><span class="sxs-lookup"><span data-stu-id="1c55c-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="1c55c-132">使用本主题创建或修改网络区域路线。</span><span class="sxs-lookup"><span data-stu-id="1c55c-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="1c55c-133">创建网络区域路由</span><span class="sxs-lookup"><span data-stu-id="1c55c-133">To create a network region route</span></span>

1.  <span data-ttu-id="1c55c-134">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1c55c-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c55c-135">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="1c55c-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1c55c-136">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域路由**"。</span><span class="sxs-lookup"><span data-stu-id="1c55c-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="1c55c-137">在 "**区域路由**" 页面上，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="1c55c-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="1c55c-138">在 "**新区域路由**" 中，在 "**名称**" 字段中键入值。</span><span class="sxs-lookup"><span data-stu-id="1c55c-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="1c55c-139">此值在 Skype for Business 服务器部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1c55c-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="1c55c-140">从 "**网络区域\#1** " 下拉列表中，选择两个要通过此路由连接的区域之一。</span><span class="sxs-lookup"><span data-stu-id="1c55c-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="1c55c-141">从 "**网络区域\#2** " 下拉列表中，选择此路由的其他区域。</span><span class="sxs-lookup"><span data-stu-id="1c55c-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="1c55c-142">此区域必须与为 "网络区域\#1" 选择的区域不同。</span><span class="sxs-lookup"><span data-stu-id="1c55c-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="1c55c-143">使用 "**网络区域链接**" 列表框将区域链接添加到路由。</span><span class="sxs-lookup"><span data-stu-id="1c55c-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="1c55c-144">单击 "**添加**" 按钮以显示 "**区域链接**" 页面。</span><span class="sxs-lookup"><span data-stu-id="1c55c-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="1c55c-145">单击要添加到此路由的区域链接，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1c55c-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="1c55c-146">继续单击 "**添加**" 按钮以添加更多链接，或选择一个链接，然后单击 "**删除**" 以删除链接。</span><span class="sxs-lookup"><span data-stu-id="1c55c-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="1c55c-147">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1c55c-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="1c55c-148">修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="1c55c-148">To modify a network region route</span></span>

1.  <span data-ttu-id="1c55c-149">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1c55c-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c55c-150">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="1c55c-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1c55c-151">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域路由**"。</span><span class="sxs-lookup"><span data-stu-id="1c55c-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="1c55c-152">在 "**区域路由**" 页面上，单击要修改的区域路由。</span><span class="sxs-lookup"><span data-stu-id="1c55c-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="1c55c-153">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c55c-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1c55c-154">在 "**编辑区域" 路由**中，可以修改此路由所联接的区域和与该路由关联的区域链接。</span><span class="sxs-lookup"><span data-stu-id="1c55c-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="1c55c-155">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1c55c-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="1c55c-156">删除现有网络区域路由</span><span class="sxs-lookup"><span data-stu-id="1c55c-156">Delete existing network region routes</span></span>

<span data-ttu-id="1c55c-157">呼叫许可控制（CAC）配置中的每个区域都必须有某种方式才能访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="1c55c-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="1c55c-158">虽然区域链接为区域之间的连接设置带宽限制，同时也表示物理链接，但路由决定了连接从一个地区到另一个地区的链接路径。</span><span class="sxs-lookup"><span data-stu-id="1c55c-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="1c55c-159">您可以使用 Skype for Business 服务器控制面板配置网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="1c55c-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="1c55c-160">从 "Skype for Business 服务器" 控制面板中，您可以创建、修改或删除网络区域路线。</span><span class="sxs-lookup"><span data-stu-id="1c55c-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="1c55c-161">使用本主题删除现有网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="1c55c-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="1c55c-162">删除网络区域路由</span><span class="sxs-lookup"><span data-stu-id="1c55c-162">To delete a network region route</span></span>

1.  <span data-ttu-id="1c55c-163">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1c55c-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c55c-164">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="1c55c-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1c55c-165">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域路由**"。</span><span class="sxs-lookup"><span data-stu-id="1c55c-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="1c55c-166">在 "**区域路由**" 页面上，单击要删除的区域路由。</span><span class="sxs-lookup"><span data-stu-id="1c55c-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="1c55c-167">您可以一次删除多个区域路线。</span><span class="sxs-lookup"><span data-stu-id="1c55c-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="1c55c-168">若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个区域路由。</span><span class="sxs-lookup"><span data-stu-id="1c55c-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="1c55c-169">或者，若要选择所有区域路由，请单击 "**编辑**" 菜单上的 "**全选**"。</span><span class="sxs-lookup"><span data-stu-id="1c55c-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="1c55c-170">在 "**编辑**" 菜单上，单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="1c55c-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="1c55c-171">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1c55c-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="1c55c-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c55c-172">See Also</span></span>

[<span data-ttu-id="1c55c-173">在 Skype for Business Server 中管理网络区域</span><span class="sxs-lookup"><span data-stu-id="1c55c-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="1c55c-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1c55c-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="1c55c-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1c55c-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="1c55c-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1c55c-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="1c55c-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1c55c-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
