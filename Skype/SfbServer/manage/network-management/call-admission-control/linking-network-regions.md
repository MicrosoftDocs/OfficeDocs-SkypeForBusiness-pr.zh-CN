---
title: 链接网络区域
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
description: '您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。 '
ms.openlocfilehash: 163f214b05ba0dca3bc7dd4ec722f148cafe724e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096678"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="62b5c-103">在 Skype for Business Server 中链接网络区域</span><span class="sxs-lookup"><span data-stu-id="62b5c-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="62b5c-104">您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="62b5c-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="62b5c-105">使用本文中的各节查看 newtwork 区域链接信息，或者配置或删除 netwrok 区域链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="62b5c-106">查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="62b5c-106">View network region link information</span></span> 

<span data-ttu-id="62b5c-107">您可以查看两个网络区域之间作为呼叫允许控制 (CAC) 的一部分的链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="62b5c-108">网络内的区域通过物理广域网 (WAN) 连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="62b5c-109">可以使用 Skype for Business Server 控制面板查看两个网络区域之间的现有链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="62b5c-110">在 Skype for Business Server 控制面板中查看网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62b5c-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="62b5c-111">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="62b5c-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62b5c-112">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="62b5c-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="62b5c-113">在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **链接"。**</span><span class="sxs-lookup"><span data-stu-id="62b5c-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="62b5c-114">在“区域链接”页上，单击要查看的区域链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="62b5c-115">您一次只能查看一个区域链接的相关信息。</span><span class="sxs-lookup"><span data-stu-id="62b5c-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="62b5c-116">从“编辑”菜单中选择“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="62b5c-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="62b5c-117">使用 cmdlet 查看网络区域Windows PowerShell信息</span><span class="sxs-lookup"><span data-stu-id="62b5c-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="62b5c-118">可以通过使用 Windows PowerShell **和 Get-CsNetworkRegionLink** cmdlet 查看网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="62b5c-119">还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62b5c-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="62b5c-120">查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="62b5c-120">To view network region link information</span></span>

  - <span data-ttu-id="62b5c-121">若要查看有关所有网络区域链接的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="62b5c-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="62b5c-122">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="62b5c-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="62b5c-123">有关详细信息，请参阅[Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)。</span><span class="sxs-lookup"><span data-stu-id="62b5c-123">For details, see [Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="62b5c-124">配置网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62b5c-124">Configure network region links</span></span> 

<span data-ttu-id="62b5c-125">您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="62b5c-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="62b5c-126">网络内的区域通过物理广域网 (WAN) 连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="62b5c-127">可以使用 Skype for Business Server 控制面板定义两个网络区域之间的链接，并设置这些区域之间的音频和视频连接的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="62b5c-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="62b5c-128">创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62b5c-128">To create a network region link</span></span>

1.  <span data-ttu-id="62b5c-129">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="62b5c-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62b5c-130">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="62b5c-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="62b5c-131">在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **链接"。**</span><span class="sxs-lookup"><span data-stu-id="62b5c-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="62b5c-132">在"区域 **链接"** 页上，单击"新建 **"。**</span><span class="sxs-lookup"><span data-stu-id="62b5c-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="62b5c-133">在 **"新建区域链接**"中的"名称"字段中 **键入** 值。</span><span class="sxs-lookup"><span data-stu-id="62b5c-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="62b5c-134">此值在 Skype for Business Server 部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="62b5c-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="62b5c-135">从" **网络区域 \# 1"** 下拉列表中，选择要链接的两个区域之一。</span><span class="sxs-lookup"><span data-stu-id="62b5c-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="62b5c-136">从 **"网络区域 \# 2"** 下拉列表中，选择要链接的其他区域。</span><span class="sxs-lookup"><span data-stu-id="62b5c-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="62b5c-137">此区域必须与为网络区域 1 所选的区域 \# 不同。</span><span class="sxs-lookup"><span data-stu-id="62b5c-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="62b5c-138"> (可选) 如果要在这些区域之间的音频或视频呼叫上设置带宽限制，请从"带宽策略"下拉列表中选择带宽策略配置文件。 </span><span class="sxs-lookup"><span data-stu-id="62b5c-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="62b5c-139">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="62b5c-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="62b5c-140">修改网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62b5c-140">To modify a network region link</span></span>

1.  <span data-ttu-id="62b5c-141">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="62b5c-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62b5c-142">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="62b5c-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="62b5c-143">在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **链接"。**</span><span class="sxs-lookup"><span data-stu-id="62b5c-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="62b5c-144">在" **区域链接"** 页上，单击要修改的区域链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="62b5c-145">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="62b5c-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="62b5c-146">在 **"编辑区域链接**"中，可以修改链接的区域或此链接的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="62b5c-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="62b5c-147">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="62b5c-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="62b5c-148">删除网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62b5c-148">Delete network region links</span></span>

<span data-ttu-id="62b5c-149">您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="62b5c-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="62b5c-150">网络内的区域通过物理广域网 (WAN) 连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="62b5c-151">可以使用 Skype for Business Server 控制面板删除两个网络区域之间的现有链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="62b5c-152">删除网络区域链接</span><span class="sxs-lookup"><span data-stu-id="62b5c-152">To delete a network region link</span></span>

1.  <span data-ttu-id="62b5c-153">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="62b5c-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62b5c-154">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="62b5c-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="62b5c-155">在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **链接"。**</span><span class="sxs-lookup"><span data-stu-id="62b5c-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="62b5c-156">在“区域链接”页上，单击要删除的区域链接。</span><span class="sxs-lookup"><span data-stu-id="62b5c-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="62b5c-p107">可一次性删除多个区域链接。要执行此操作，请按住 Ctrl 键，同时选择多个区域链接。或者，要选择全部区域链接，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="62b5c-p107">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="62b5c-160">从“编辑”菜单中选择“删除”。</span><span class="sxs-lookup"><span data-stu-id="62b5c-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="62b5c-161">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="62b5c-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="62b5c-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62b5c-162">See Also</span></span>

[<span data-ttu-id="62b5c-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="62b5c-163">New-CsNetworkRegionLink</span></span>](/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="62b5c-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="62b5c-164">Set-CsNetworkRegionLink</span></span>](/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="62b5c-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="62b5c-165">Remove-CsNetworkRegionLink</span></span>](/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="62b5c-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="62b5c-166">Get-CsNetworkRegionLink</span></span>](/powershell/module/skype/Get-CsNetworkRegionLink)