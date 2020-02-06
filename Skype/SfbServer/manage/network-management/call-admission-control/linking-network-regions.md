---
title: 链接网络区域
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
description: '你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。 '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817521"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="17a8e-103">在 Skype for Business Server 中链接网络区域</span><span class="sxs-lookup"><span data-stu-id="17a8e-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="17a8e-104">你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。</span><span class="sxs-lookup"><span data-stu-id="17a8e-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="17a8e-105">使用本文中的部分可查看 newtwork 区域链接信息，或配置或删除 netwrok 区域链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="17a8e-106">查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="17a8e-106">View network region link information</span></span> 

<span data-ttu-id="17a8e-107">您可以查看两个网络区域之间的链接，作为呼叫许可控制（CAC）的一部分。</span><span class="sxs-lookup"><span data-stu-id="17a8e-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="17a8e-108">网络中的区域通过物理广域网络（WAN）连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="17a8e-109">您可以使用 Skype for Business 服务器控制面板查看两个网络区域之间的现有链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="17a8e-110">在 "Skype for Business 服务器" 控制面板中查看网络区域链接</span><span class="sxs-lookup"><span data-stu-id="17a8e-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="17a8e-111">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="17a8e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17a8e-112">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="17a8e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="17a8e-113">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。</span><span class="sxs-lookup"><span data-stu-id="17a8e-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="17a8e-114">在 "**区域链接**" 页面上，单击要查看的区域链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="17a8e-115">一次只能查看有关一个区域链接的信息。</span><span class="sxs-lookup"><span data-stu-id="17a8e-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="17a8e-116">从 "**编辑**" 菜单中，选择 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="17a8e-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="17a8e-117">使用 Windows PowerShell cmdlet 查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="17a8e-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="17a8e-118">你可以使用 Windows PowerShell 和**CsNetworkRegionLink** cmdlet 查看网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="17a8e-119">你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="17a8e-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="17a8e-120">查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="17a8e-120">To view network region link information</span></span>

  - <span data-ttu-id="17a8e-121">若要查看有关所有网络区域链接的信息，请在 Skype for Business Server 命令行管理器中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="17a8e-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="17a8e-122">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="17a8e-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="17a8e-123">有关详细信息，请参阅[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。</span><span class="sxs-lookup"><span data-stu-id="17a8e-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="17a8e-124">配置网络区域链接</span><span class="sxs-lookup"><span data-stu-id="17a8e-124">Configure network region links</span></span> 

<span data-ttu-id="17a8e-125">你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。</span><span class="sxs-lookup"><span data-stu-id="17a8e-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="17a8e-126">网络中的区域通过物理广域网络（WAN）连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="17a8e-127">您可以使用 Skype for Business 服务器控制面板定义两个网络区域之间的链接，并设置这些区域之间的音频和视频连接的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="17a8e-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="17a8e-128">创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="17a8e-128">To create a network region link</span></span>

1.  <span data-ttu-id="17a8e-129">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="17a8e-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17a8e-130">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="17a8e-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="17a8e-131">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。</span><span class="sxs-lookup"><span data-stu-id="17a8e-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="17a8e-132">在 "**区域链接**" 页面上，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="17a8e-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="17a8e-133">在 "**新区域链接**" 中，在 "**名称**" 字段中键入值。</span><span class="sxs-lookup"><span data-stu-id="17a8e-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="17a8e-134">此值在 Skype for Business 服务器部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="17a8e-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="17a8e-135">从 "**网络区域\#1** " 下拉列表中，选择要链接的两个区域之一。</span><span class="sxs-lookup"><span data-stu-id="17a8e-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="17a8e-136">从 "**网络区域\#2** " 下拉列表中，选择要链接的其他区域。</span><span class="sxs-lookup"><span data-stu-id="17a8e-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="17a8e-137">此区域必须与为 "网络区域\#1" 选择的区域不同。</span><span class="sxs-lookup"><span data-stu-id="17a8e-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="17a8e-138">可选如果您想要对这些区域之间的音频或视频通话设置带宽限制，请从 "**带宽策略**" 下拉列表中选择一个带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="17a8e-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="17a8e-139">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="17a8e-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="17a8e-140">修改网络区域链接</span><span class="sxs-lookup"><span data-stu-id="17a8e-140">To modify a network region link</span></span>

1.  <span data-ttu-id="17a8e-141">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="17a8e-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17a8e-142">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="17a8e-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="17a8e-143">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。</span><span class="sxs-lookup"><span data-stu-id="17a8e-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="17a8e-144">在 "**区域链接**" 页面上，单击要修改的区域链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="17a8e-145">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="17a8e-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="17a8e-146">在 "**编辑区域" 链接**中，可以修改链接的区域或此链接的 "带宽策略" 配置文件。</span><span class="sxs-lookup"><span data-stu-id="17a8e-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="17a8e-147">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="17a8e-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="17a8e-148">删除网络区域链接</span><span class="sxs-lookup"><span data-stu-id="17a8e-148">Delete network region links</span></span>

<span data-ttu-id="17a8e-149">你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。</span><span class="sxs-lookup"><span data-stu-id="17a8e-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="17a8e-150">网络中的区域通过物理广域网络（WAN）连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="17a8e-151">您可以使用 Skype for Business 服务器控制面板删除两个网络区域之间的现有链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="17a8e-152">删除网络区域链接</span><span class="sxs-lookup"><span data-stu-id="17a8e-152">To delete a network region link</span></span>

1.  <span data-ttu-id="17a8e-153">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="17a8e-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17a8e-154">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="17a8e-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="17a8e-155">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。</span><span class="sxs-lookup"><span data-stu-id="17a8e-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="17a8e-156">在 "**区域链接**" 页面上，单击要删除的区域链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="17a8e-157">您可以一次删除多个区域链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="17a8e-158">若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个区域链接。</span><span class="sxs-lookup"><span data-stu-id="17a8e-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="17a8e-159">或者，若要选择所有区域链接，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="17a8e-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="17a8e-160">从 "**编辑**" 菜单中，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="17a8e-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="17a8e-161">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="17a8e-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="17a8e-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17a8e-162">See Also</span></span>

[<span data-ttu-id="17a8e-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="17a8e-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="17a8e-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="17a8e-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="17a8e-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="17a8e-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="17a8e-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="17a8e-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
