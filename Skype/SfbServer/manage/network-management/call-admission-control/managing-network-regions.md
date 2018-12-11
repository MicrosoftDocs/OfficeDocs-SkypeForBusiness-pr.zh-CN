---
title: 管理网络区域
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络区域 * 是网络中心或网络中枢的呼叫允许控制、 E9-1-1 和媒体绕过配置中使用。
ms.openlocfilehash: 3fe6707e6949fa47a9cc5e96703e06132ed8cb2f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223309"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="defcf-103">管理 Business Server Skype 中的网络区域</span><span class="sxs-lookup"><span data-stu-id="defcf-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="defcf-104">*网络区域*的网络中心或网络中枢的呼叫允许控制、 E9-1-1 和媒体绕过配置中使用。</span><span class="sxs-lookup"><span data-stu-id="defcf-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="defcf-105">使用以下过程以查看、 创建或修改网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="defcf-106">例如，如果您已经创建一个语音功能的网络区域，您不需要创建新的网络区域;其他高级的企业语音功能将使用这些相同的网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="defcf-107">但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。</span><span class="sxs-lookup"><span data-stu-id="defcf-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="defcf-108">例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。</span><span class="sxs-lookup"><span data-stu-id="defcf-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="defcf-109">使用本文中的过程以查看网络区域信息或创建、 修改或删除网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="defcf-110">查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="defcf-110">View network region information</span></span> 


<span data-ttu-id="defcf-111">网络区域互连跨多个地理区域的网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="defcf-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="defcf-112">每个网络区域必须与中央站点相关联。</span><span class="sxs-lookup"><span data-stu-id="defcf-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="defcf-113">中央站点是在其运行呼叫允许控制 (CAC) 带宽策略服务数据中心站点。</span><span class="sxs-lookup"><span data-stu-id="defcf-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="defcf-114">您可以使用业务 Server Control Panel 的 Skype 查看网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="defcf-115">网络区域包括确定是否允许通过 Internet 的备用路径对音频和视频连接的设置。</span><span class="sxs-lookup"><span data-stu-id="defcf-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="defcf-116">使用本主题可查看现有的网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="defcf-117">若要查看有关 Business Server Control Panel 与 Skype 的网络区域信息</span><span class="sxs-lookup"><span data-stu-id="defcf-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="defcf-118">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="defcf-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="defcf-119">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="defcf-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="defcf-120">在左侧的导航栏中，单击**网络配置**，然后单击**区域**。</span><span class="sxs-lookup"><span data-stu-id="defcf-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="defcf-121">在**区域**页上，单击您想要查看的区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="defcf-122">一次只能查看一个区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="defcf-123">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="defcf-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="defcf-124">通过使用 Windows PowerShell cmdlet 查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="defcf-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="defcf-125">您可以使用 Windows PowerShell 和**Get-csnetworkregion** cmdlet 查看网络区域信息。</span><span class="sxs-lookup"><span data-stu-id="defcf-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="defcf-126">可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="defcf-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="defcf-127">若要查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="defcf-127">To view network region information</span></span>

  - <span data-ttu-id="defcf-128">若要查看有关所有网络区域的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="defcf-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="defcf-129">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="defcf-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="defcf-130">有关详细信息，请参阅[Get-csnetworkregion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="defcf-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="defcf-131">创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="defcf-131">Create or modify network regions</span></span> 

<span data-ttu-id="defcf-132">网络区域互连跨多个地理区域的网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="defcf-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="defcf-133">每个网络区域必须与中央站点相关联。</span><span class="sxs-lookup"><span data-stu-id="defcf-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="defcf-134">中央站点是在其运行呼叫允许控制 (CAC) 带宽策略服务数据中心站点。</span><span class="sxs-lookup"><span data-stu-id="defcf-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="defcf-135">您可以使用业务 Server Control Panel 的 Skype 配置网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="defcf-136">网络区域包括确定是否允许通过 Internet 的备用路径对音频和视频连接的设置。</span><span class="sxs-lookup"><span data-stu-id="defcf-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="defcf-137">从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="defcf-138">本主题可用于创建和修改网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="defcf-139">创建网络区域</span><span class="sxs-lookup"><span data-stu-id="defcf-139">To create a network region</span></span>

1.  <span data-ttu-id="defcf-140">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="defcf-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="defcf-141">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="defcf-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="defcf-142">在左侧的导航栏中，单击**网络配置**，然后单击**区域**。</span><span class="sxs-lookup"><span data-stu-id="defcf-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="defcf-143">在**区域**页上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="defcf-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="defcf-144">在**新建区域**页中，键入**名称**字段中的值。</span><span class="sxs-lookup"><span data-stu-id="defcf-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="defcf-145">此值必须是唯一您 Skype 业务服务器部署中。</span><span class="sxs-lookup"><span data-stu-id="defcf-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="defcf-146">从**中央站点**下拉列表中选择此网络区域的中央站点。</span><span class="sxs-lookup"><span data-stu-id="defcf-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="defcf-147">默认情况下选中**启用音频的备用路径**复选框。</span><span class="sxs-lookup"><span data-stu-id="defcf-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="defcf-148">此字段确定是否主路径中没有足够带宽，是否将通过备用路径中路由音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="defcf-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="defcf-149">仅当您需要关闭卸载到 Internet，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="defcf-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="defcf-150">如果任何呼叫是 Internet 呼叫，此复选框必须选中，无论带宽设置。</span><span class="sxs-lookup"><span data-stu-id="defcf-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="defcf-151">默认情况下选中**启用视频的备用路径**复选框。</span><span class="sxs-lookup"><span data-stu-id="defcf-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="defcf-152">此字段确定是否主路径中没有足够带宽，是否将通过备用路径中路由视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="defcf-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="defcf-153">仅当您需要关闭卸载到 Internet，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="defcf-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="defcf-154">如果任何呼叫是 Internet 呼叫，此复选框必须选中，无论带宽设置。</span><span class="sxs-lookup"><span data-stu-id="defcf-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="defcf-155">（可选）在**说明**字段，以提供有关通过名称本身不能表示该区域的详细信息，请键入一个值。</span><span class="sxs-lookup"><span data-stu-id="defcf-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="defcf-156">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="defcf-156">Click **Commit**.</span></span>

<span data-ttu-id="defcf-157">**关联网站**表不用于创建网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="defcf-158">创建或修改站点时，可以与区域关联网站。</span><span class="sxs-lookup"><span data-stu-id="defcf-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="defcf-159">有关详细信息，请参阅[Managing 呼叫允许控制的网站](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="defcf-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="defcf-160">修改网络区域</span><span class="sxs-lookup"><span data-stu-id="defcf-160">To modify a network region</span></span>

1.  <span data-ttu-id="defcf-161">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="defcf-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="defcf-162">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="defcf-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="defcf-163">在左侧的导航栏中，单击**网络配置**，然后单击**区域**。</span><span class="sxs-lookup"><span data-stu-id="defcf-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="defcf-164">在**区域**页上，单击您想要修改的区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="defcf-165">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="defcf-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="defcf-166">在**编辑区域**页中中，您可以修改设置启用和禁用音频和视频备用路径，并更改说明 （有关详细信息，请参阅"创建网络区域"一节本主题中前面。</span><span class="sxs-lookup"><span data-stu-id="defcf-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="defcf-167">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="defcf-167">Click **Commit**.</span></span>

<span data-ttu-id="defcf-168">不能修改此页上的**关联网站**。</span><span class="sxs-lookup"><span data-stu-id="defcf-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="defcf-169">使您了解当您修改的区域设置时，将影响的网站，供参考提供关联的网站的列表。</span><span class="sxs-lookup"><span data-stu-id="defcf-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="defcf-170">删除现有网络区域</span><span class="sxs-lookup"><span data-stu-id="defcf-170">Delete existing network regions</span></span> 

<span data-ttu-id="defcf-171">网络区域互连跨多个地理区域的网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="defcf-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="defcf-172">每个网络区域必须与中央站点相关联。</span><span class="sxs-lookup"><span data-stu-id="defcf-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="defcf-173">中央站点是在其运行呼叫允许控制 (CAC) 带宽策略服务数据中心站点。</span><span class="sxs-lookup"><span data-stu-id="defcf-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="defcf-174">您可以使用业务 Server Control Panel 的 Skype 配置网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="defcf-175">网络区域包括确定是否允许通过 Internet 的备用路径对音频和视频连接的设置。</span><span class="sxs-lookup"><span data-stu-id="defcf-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="defcf-176">从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="defcf-177">使用本主题可删除现有网络区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="defcf-178">删除网络区域</span><span class="sxs-lookup"><span data-stu-id="defcf-178">To delete a network region</span></span>

1.  <span data-ttu-id="defcf-179">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="defcf-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="defcf-180">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="defcf-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="defcf-181">在左侧的导航栏中，单击**网络配置**，然后单击**区域**。</span><span class="sxs-lookup"><span data-stu-id="defcf-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="defcf-182">在**区域**页上，单击您想要删除的区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="defcf-183">您可以一次删除多个区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="defcf-184">若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个区域。</span><span class="sxs-lookup"><span data-stu-id="defcf-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="defcf-185">或者，若要选择所有区域，**都选择全部**上单击**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="defcf-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="defcf-186">在**编辑**菜单上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="defcf-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="defcf-187">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="defcf-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="defcf-188">无法删除网络区域，如果它是与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="defcf-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="defcf-189">如果尝试删除与网站关联的区域，您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="defcf-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="defcf-190">若要查看是否区域相关联的任何网站，选择的区域，然后单击**编辑**菜单上的**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="defcf-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="defcf-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="defcf-191">See Also</span></span>

[<span data-ttu-id="defcf-192">管理网络区域路由</span><span class="sxs-lookup"><span data-stu-id="defcf-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="defcf-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="defcf-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="defcf-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="defcf-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="defcf-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="defcf-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="defcf-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="defcf-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  