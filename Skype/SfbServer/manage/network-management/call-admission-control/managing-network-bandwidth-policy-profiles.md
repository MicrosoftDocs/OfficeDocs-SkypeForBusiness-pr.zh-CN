---
title: 管理网络带宽策略配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 使用本文中的过程以查看、 创建、 修改或删除网络带宽策略配置文件。
ms.openlocfilehash: bc76af70002cc1f5b59b754cd8b86fe0d4c5327f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888840"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="d201a-103">在 Skype for Business Server 中管理网络带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="d201a-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="d201a-104">使用本文中的过程以查看、 创建、 修改或删除网络带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="d201a-105">查看网络带宽策略配置文件信息</span><span class="sxs-lookup"><span data-stu-id="d201a-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="d201a-106">作为呼叫允许控制 (CAC) 的一部分，带宽策略用于定义特定形式的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="d201a-107">在业务服务器 Skype，可以将仅音频和视频形式分配带宽限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="d201a-108">您可以设置总体带宽限制和会话限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="d201a-109">为业务 Server Control Panel Skype 可用于创建、 修改或删除这些策略容器配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="d201a-110">每个带宽策略配置文件可以与一个或多个网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="d201a-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="d201a-111">使用以下过程可以查看带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="d201a-112">若要查看带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="d201a-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="d201a-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d201a-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d201a-114">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="d201a-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d201a-115">在左侧的导航栏中，单击**网络配置**，然后单击**带宽策略**。</span><span class="sxs-lookup"><span data-stu-id="d201a-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="d201a-116">在**带宽策略**页上，单击您想要查看的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="d201a-117">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d201a-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d201a-118">通过使用 Windows PowerShell cmdlet 查看网络带宽策略配置文件信息</span><span class="sxs-lookup"><span data-stu-id="d201a-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d201a-119">可以通过使用 Windows PowerShell 和 Get-csnetworkbandwidthpolicyprofile cmdlet 查看网络带宽配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="d201a-120">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d201a-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="d201a-121">若要查看网络带宽策略配置文件信息</span><span class="sxs-lookup"><span data-stu-id="d201a-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="d201a-122">若要查看有关所有网络带宽策略配置文件的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="d201a-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="d201a-123">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="d201a-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="d201a-124">有关详细信息，请参阅[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d201a-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="d201a-125">创建或修改带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="d201a-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="d201a-126">作为呼叫允许控制 (CAC) 的一部分，带宽策略用于定义特定形式的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="d201a-127">在业务服务器 Skype，可以将仅音频和视频形式分配带宽限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="d201a-128">您可以设置总体带宽限制和会话限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="d201a-129">为业务 Server Control Panel Skype 可用于创建、 修改或删除这些策略容器配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="d201a-130">每个带宽策略配置文件可以与一个或多个网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="d201a-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="d201a-131">使用以下过程可创建或修改带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="d201a-132">创建新的带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="d201a-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="d201a-133">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d201a-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d201a-134">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="d201a-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d201a-135">在左侧的导航栏中，单击**网络配置**，然后单击**带宽策略**。</span><span class="sxs-lookup"><span data-stu-id="d201a-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="d201a-136">在**带宽策略**页上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="d201a-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="d201a-137">在**新的带宽策略配置文件**中，键入**名称**字段中的名称。</span><span class="sxs-lookup"><span data-stu-id="d201a-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="d201a-138">此名称必须是唯一的所有带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="d201a-139">在**音频限制**字段中，键入一个数字值。</span><span class="sxs-lookup"><span data-stu-id="d201a-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="d201a-140">此值为的最大带宽为所有音频连接，表示单位： kbps 分配量。</span><span class="sxs-lookup"><span data-stu-id="d201a-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="d201a-141">在**音频会话限制**字段中输入一个数值。</span><span class="sxs-lookup"><span data-stu-id="d201a-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="d201a-142">此值为的最大带宽为个别音频连接，表示单位： kbps 分配量。</span><span class="sxs-lookup"><span data-stu-id="d201a-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="d201a-143">该值必须是 40 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d201a-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="d201a-144">在**视频限制**字段中输入一个数值。</span><span class="sxs-lookup"><span data-stu-id="d201a-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="d201a-145">此值为的最大带宽为所有视频连接，表示单位： kbps 分配量。</span><span class="sxs-lookup"><span data-stu-id="d201a-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="d201a-146">在**视频会话限制**字段中输入一个数值。</span><span class="sxs-lookup"><span data-stu-id="d201a-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="d201a-147">此值为的最大带宽为个别视频连接，表示单位： kbps 分配量。</span><span class="sxs-lookup"><span data-stu-id="d201a-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="d201a-148">该值必须是 100 个或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d201a-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="d201a-149">（可选）在**说明**字段，以提供有关通过名称本身不能表示该带宽策略配置文件的详细信息，请键入一个值。</span><span class="sxs-lookup"><span data-stu-id="d201a-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="d201a-150">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d201a-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="d201a-151">创建新的带宽策略配置文件不自动强制带宽限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="d201a-152">首先必须与网站关联的策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="d201a-153">修改带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="d201a-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="d201a-154">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d201a-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d201a-155">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="d201a-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d201a-156">在左侧的导航栏中，单击**网络配置**，然后单击**带宽策略**。</span><span class="sxs-lookup"><span data-stu-id="d201a-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="d201a-157">在**带宽策略**页上，单击您想要修改的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="d201a-158">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d201a-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="d201a-159">在**编辑带宽策略配置文件**页上，根据需要修改字段 （有关详细信息，请参阅[创建新的带宽策略配置文件](#to-create-a-new-bandwidth-policy-profile)）。</span><span class="sxs-lookup"><span data-stu-id="d201a-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="d201a-160">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d201a-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="d201a-161">修改带宽策略配置文件时，会立即更新与此带宽策略配置文件关联的所有网络站点的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="d201a-162">删除网络带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="d201a-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="d201a-163">作为呼叫允许控制 (CAC) 的一部分，带宽策略用于定义特定形式的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="d201a-164">在业务服务器 Skype，可以将仅音频和视频形式分配带宽限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="d201a-165">您可以设置总体带宽限制和会话限制。</span><span class="sxs-lookup"><span data-stu-id="d201a-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="d201a-166">为业务 Server Control Panel Skype 可用于创建、 修改或删除这些策略容器配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="d201a-167">使用以下过程可删除网络带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="d201a-168">删除带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="d201a-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="d201a-169">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d201a-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d201a-170">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="d201a-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d201a-171">在左侧的导航栏中，单击**网络配置**，然后单击**带宽策略**。</span><span class="sxs-lookup"><span data-stu-id="d201a-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="d201a-172">在**带宽策略**页上，单击要删除的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="d201a-173">您可以一次删除多个配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="d201a-174">若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="d201a-175">或者，若要选择所有配置文件，**选择全部**上单击**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="d201a-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="d201a-176">在**编辑**菜单上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="d201a-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="d201a-177">不能删除与网络站点相关联的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="d201a-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="d201a-178">您可以删除配置文件之前，必须先删除与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="d201a-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="d201a-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d201a-179">See Also</span></span>

[<span data-ttu-id="d201a-180">管理网站的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="d201a-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="d201a-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="d201a-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="d201a-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="d201a-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="d201a-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="d201a-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="d201a-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="d201a-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

