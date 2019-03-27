---
title: 链接网络区域
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '您可以配置呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。 '
ms.openlocfilehash: 4ea6ddcc72d2cadea32608288d1db93ba8505aee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884682"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="62353-103">在 Skype for Business Server 中链接网络区域</span><span class="sxs-lookup"><span data-stu-id="62353-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="62353-104">您可以配置呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。</span><span class="sxs-lookup"><span data-stu-id="62353-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="62353-105">使用本文中的部分以查看 newtwork 区域链接信息或者配置或删除网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="62353-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="62353-106">查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="62353-106">View network region link information</span></span> 

<span data-ttu-id="62353-107">您可以查看作为呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。</span><span class="sxs-lookup"><span data-stu-id="62353-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="62353-108">在网络中的区域链接通过物理广域网 (wan) 连接。</span><span class="sxs-lookup"><span data-stu-id="62353-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="62353-109">您可以使用业务 Server Control Panel 的 Skype 查看两个网络区域之间的现有链接。</span><span class="sxs-lookup"><span data-stu-id="62353-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="62353-110">若要查看网络区域链接 Skype 中的业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="62353-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="62353-111">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="62353-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62353-112">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="62353-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="62353-113">在左侧的导航栏中，单击**网络配置**，然后单击**区域链接**。</span><span class="sxs-lookup"><span data-stu-id="62353-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="62353-114">在**区域链接**页上，单击您想要查看的区域链接。</span><span class="sxs-lookup"><span data-stu-id="62353-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="62353-115">您只能查看一个区域链接信息一次。</span><span class="sxs-lookup"><span data-stu-id="62353-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="62353-116">从**编辑**菜单上，选择**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="62353-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="62353-117">使用 Windows PowerShell cmdlet 查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="62353-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="62353-118">您可以使用 Windows PowerShell 和**Get-csnetworkregionlink** cmdlet 查看网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="62353-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="62353-119">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62353-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="62353-120">若要查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="62353-120">To view network region link information</span></span>

  - <span data-ttu-id="62353-121">若要查看有关所有网络区域链接的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="62353-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="62353-122">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="62353-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="62353-123">有关详细信息，请参阅[Get-csnetworkregionlink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。</span><span class="sxs-lookup"><span data-stu-id="62353-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="62353-124">配置网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62353-124">Configure network region links</span></span> 

<span data-ttu-id="62353-125">您可以配置呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。</span><span class="sxs-lookup"><span data-stu-id="62353-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="62353-126">在网络中的区域链接通过物理广域网 (wan) 连接。</span><span class="sxs-lookup"><span data-stu-id="62353-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="62353-127">可以使用业务 Server Control Panel 的 Skype 定义两个网络区域之间的链接和这些区域之间的音频和视频连接设置带宽限制。</span><span class="sxs-lookup"><span data-stu-id="62353-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="62353-128">创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62353-128">To create a network region link</span></span>

1.  <span data-ttu-id="62353-129">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="62353-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62353-130">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="62353-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="62353-131">在左侧的导航栏中，单击**网络配置**，然后单击**区域链接**。</span><span class="sxs-lookup"><span data-stu-id="62353-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="62353-132">在**区域链接**页上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="62353-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="62353-133">在**新建区域链接**中，键入**名称**字段中的值。</span><span class="sxs-lookup"><span data-stu-id="62353-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="62353-134">此值必须是唯一您 Skype 业务服务器部署中。</span><span class="sxs-lookup"><span data-stu-id="62353-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="62353-135">从**网络区域\#1**下拉列表中，选择要链接的两个区域之一。</span><span class="sxs-lookup"><span data-stu-id="62353-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="62353-136">从**网络区域\#2**下拉列表中，选择要链接的其他区域。</span><span class="sxs-lookup"><span data-stu-id="62353-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="62353-137">此区域必须不同于网络区域选择的区域\#1。</span><span class="sxs-lookup"><span data-stu-id="62353-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="62353-138">（可选）如果您想要在这些区域之间的音频或视频呼叫设置带宽限制，请从**带宽策略**下拉列表中选择带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="62353-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="62353-139">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="62353-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="62353-140">修改网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62353-140">To modify a network region link</span></span>

1.  <span data-ttu-id="62353-141">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="62353-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62353-142">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="62353-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="62353-143">在左侧的导航栏中，单击**网络配置**，然后单击**区域链接**。</span><span class="sxs-lookup"><span data-stu-id="62353-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="62353-144">在**区域链接**页上，单击要修改的区域链接。</span><span class="sxs-lookup"><span data-stu-id="62353-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="62353-145">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="62353-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="62353-146">在**编辑区域链接**，您可以修改链接的区域或此链接的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="62353-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="62353-147">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="62353-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="62353-148">删除网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62353-148">Delete network region links</span></span>

<span data-ttu-id="62353-149">您可以配置呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。</span><span class="sxs-lookup"><span data-stu-id="62353-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="62353-150">在网络中的区域链接通过物理广域网 (wan) 连接。</span><span class="sxs-lookup"><span data-stu-id="62353-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="62353-151">您可以使用业务 Server Control Panel 的 Skype 删除现有两个网络区域之间的链接。</span><span class="sxs-lookup"><span data-stu-id="62353-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="62353-152">删除网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62353-152">To delete a network region link</span></span>

1.  <span data-ttu-id="62353-153">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="62353-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62353-154">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="62353-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="62353-155">在左侧的导航栏中，单击**网络配置**，然后单击**区域链接**。</span><span class="sxs-lookup"><span data-stu-id="62353-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="62353-156">在**区域链接**页上，单击您想要删除的区域链接。</span><span class="sxs-lookup"><span data-stu-id="62353-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="62353-157">您可以一次删除多个区域链接。</span><span class="sxs-lookup"><span data-stu-id="62353-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="62353-158">若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个区域链接。</span><span class="sxs-lookup"><span data-stu-id="62353-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="62353-159">或者，若要选择所有区域链接，<STRONG>都选择全部</STRONG>上单击<STRONG>编辑</STRONG>菜单。</span><span class="sxs-lookup"><span data-stu-id="62353-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="62353-160">从**编辑**菜单上，选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="62353-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="62353-161">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="62353-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="62353-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62353-162">See Also</span></span>

[<span data-ttu-id="62353-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="62353-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="62353-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="62353-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="62353-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="62353-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="62353-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="62353-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
