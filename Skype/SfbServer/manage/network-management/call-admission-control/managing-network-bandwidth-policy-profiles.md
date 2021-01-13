---
title: 管理网络带宽策略配置文件
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
description: 使用本文中的过程查看、创建、修改或删除网络带宽策略配置文件。
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816442"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="2ba80-103">在 Skype for Business Server 中管理网络带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="2ba80-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="2ba80-104">使用本文中的过程查看、创建、修改或删除网络带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="2ba80-105">查看网络带宽策略配置文件信息</span><span class="sxs-lookup"><span data-stu-id="2ba80-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="2ba80-106">作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="2ba80-107">在 Skype for Business Server 中，只能为音频和视频形式分配带宽限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="2ba80-108">您可以设置总体带宽限制和会话限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="2ba80-109">可以使用 Skype for Business Server 控制面板创建、修改或删除这些策略的容器配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="2ba80-110">每个带宽策略配置文件都可以与一个或多个网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="2ba80-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="2ba80-111">使用下列过程可查看带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="2ba80-112">查看带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="2ba80-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="2ba80-113">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="2ba80-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ba80-114">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2ba80-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2ba80-115">在左侧导航栏中，单击“网络配置”，然后单击“带宽策略”。</span><span class="sxs-lookup"><span data-stu-id="2ba80-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="2ba80-116">在 **"带宽策略** "页上，单击要查看的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="2ba80-117">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="2ba80-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2ba80-118">使用 cmdlet 查看网络带宽策略Windows PowerShell信息</span><span class="sxs-lookup"><span data-stu-id="2ba80-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2ba80-119">网络带宽配置文件可通过使用 Windows PowerShell 和 Get-CsNetworkBandwidthPolicyProfile cmdlet 进行查看。</span><span class="sxs-lookup"><span data-stu-id="2ba80-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="2ba80-120">此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2ba80-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="2ba80-121">查看网络带宽策略配置文件信息</span><span class="sxs-lookup"><span data-stu-id="2ba80-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="2ba80-122">若要查看有关所有网络带宽策略配置文件的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="2ba80-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="2ba80-123">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="2ba80-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="2ba80-124">有关详细信息，请参阅[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="2ba80-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="2ba80-125">创建或修改带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="2ba80-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="2ba80-126">作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="2ba80-127">在 Skype for Business Server 中，只能为音频和视频形式分配带宽限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="2ba80-128">您可以设置总体带宽限制和会话限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="2ba80-129">可以使用 Skype for Business Server 控制面板创建、修改或删除这些策略的容器配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="2ba80-130">每个带宽策略配置文件都可以与一个或多个网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="2ba80-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="2ba80-131">可使用以下过程创建或修改带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="2ba80-132">创建新的带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="2ba80-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="2ba80-133">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="2ba80-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ba80-134">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2ba80-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2ba80-135">在左侧导航栏中，单击 **"网络配置**"，然后单击"**带宽策略"。**</span><span class="sxs-lookup"><span data-stu-id="2ba80-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="2ba80-136">在“带宽策略”页上，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="2ba80-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="2ba80-p104">在“新建带宽策略配置文件”的“名称”字段中键入名称。此名称必须在所有带宽策略配置文件中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2ba80-p104">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="2ba80-p105">在“音频限制”字段中，键入一个数值。此值是要为所有音频连接分配的最大带宽量，以 kbps 为单位表示。</span><span class="sxs-lookup"><span data-stu-id="2ba80-p105">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="2ba80-p106">在“音频会话限制”字段中输入一个数值。此值是要为单个音频连接分配的最大带宽量，以 kbps 为单位表示。此值必须为 40 或更大。</span><span class="sxs-lookup"><span data-stu-id="2ba80-p106">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="2ba80-p107">在“视频限制”字段中输入一个数值。此值是要为所有视频连接分配的最大带宽量，以 kbps 为单位表示。</span><span class="sxs-lookup"><span data-stu-id="2ba80-p107">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="2ba80-p108">在“视频会话限制”字段中输入一个数值。此值是要为单个视频连接分配的最大带宽量，以 kbps 为单位表示。此值必须为 100 或更大。</span><span class="sxs-lookup"><span data-stu-id="2ba80-p108">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="2ba80-149">（可选）在“说明”字段中键入值，用以提供仅通过名称无法表达的更多有关该带宽策略配置文件的信息。</span><span class="sxs-lookup"><span data-stu-id="2ba80-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="2ba80-150">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="2ba80-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="2ba80-151">创建新的带宽策略配置文件不会自动强制实施带宽限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="2ba80-152">必须先将策略配置文件与站点相关联。</span><span class="sxs-lookup"><span data-stu-id="2ba80-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="2ba80-153">修改带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="2ba80-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="2ba80-154">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="2ba80-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ba80-155">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2ba80-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2ba80-156">在左侧导航栏中，单击 **"网络配置**"，然后单击"**带宽策略"。**</span><span class="sxs-lookup"><span data-stu-id="2ba80-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="2ba80-157">在“带宽策略”页上，单击要修改的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="2ba80-158">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="2ba80-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="2ba80-159">在 **"编辑带宽策略配置文件**"页上，根据需要 (字段，有关详细信息，请参阅"创建新的带宽策略配置文件 [](#to-create-a-new-bandwidth-policy-profile)) 。</span><span class="sxs-lookup"><span data-stu-id="2ba80-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="2ba80-160">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="2ba80-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="2ba80-161">修改带宽策略配置文件时，会立即更新与此带宽策略配置文件关联的所有网络站点的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="2ba80-162">删除网络带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="2ba80-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="2ba80-163">作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="2ba80-164">在 Skype for Business Server 中，只能为音频和视频形式分配带宽限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="2ba80-165">您可以设置总体带宽限制和会话限制。</span><span class="sxs-lookup"><span data-stu-id="2ba80-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="2ba80-166">可以使用 Skype for Business Server 控制面板创建、修改或删除这些策略的容器配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="2ba80-167">请使用下列过程删除网络带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="2ba80-168">删除带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="2ba80-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="2ba80-169">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="2ba80-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ba80-170">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2ba80-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2ba80-171">在左侧导航栏中，单击 **"网络配置**"，然后单击"**带宽策略"。**</span><span class="sxs-lookup"><span data-stu-id="2ba80-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="2ba80-172">在“带宽策略”页上，单击要删除的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="2ba80-p111">可一次性删除多个配置文件。要执行此操作，请按住 Ctrl 键，同时选择多个配置文件。或者，要选择全部配置文件，请单击“编辑”菜单中的“全选”。</span><span class="sxs-lookup"><span data-stu-id="2ba80-p111">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="2ba80-176">在“编辑”菜单上，单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="2ba80-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="2ba80-177">不能删除与网络站点关联的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ba80-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="2ba80-178">只有先删除配置文件与网络站点之间的关联，然后才能将配置文件删除。</span><span class="sxs-lookup"><span data-stu-id="2ba80-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="2ba80-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ba80-179">See Also</span></span>

[<span data-ttu-id="2ba80-180">管理网站的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="2ba80-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="2ba80-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2ba80-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="2ba80-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2ba80-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="2ba80-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2ba80-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="2ba80-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2ba80-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

