---
title: 管理网络区域
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
description: 网络区域 * 是呼叫许可控制、E9-1 和媒体旁路的配置中使用的网络中心或 backbones。
ms.openlocfilehash: c08232e455edb4388a052c2859b35e6c137b890a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817481"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="30bd1-103">在 Skype for Business Server 中管理网络区域</span><span class="sxs-lookup"><span data-stu-id="30bd1-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="30bd1-104">*网络区域*是用于配置呼叫许可控制、E9-1 和媒体旁路的网络中心或 backbones。</span><span class="sxs-lookup"><span data-stu-id="30bd1-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="30bd1-105">使用以下过程查看、创建或修改网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="30bd1-106">例如，如果已为一个语音功能创建了网络区域，则不需要创建新的网络区域;其他高级企业语音功能将使用相同的网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="30bd1-107">但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。</span><span class="sxs-lookup"><span data-stu-id="30bd1-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="30bd1-108">例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。</span><span class="sxs-lookup"><span data-stu-id="30bd1-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="30bd1-109">使用本文中的过程查看网络区域信息或创建、修改或删除网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="30bd1-110">查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="30bd1-110">View network region information</span></span> 


<span data-ttu-id="30bd1-111">网络区域跨多个地理区域互连网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="30bd1-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="30bd1-112">每个网络区域必须与一个中心网站相关联。</span><span class="sxs-lookup"><span data-stu-id="30bd1-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="30bd1-113">中心网站是运行呼叫许可控制（CAC）带宽策略服务的数据中心网站。</span><span class="sxs-lookup"><span data-stu-id="30bd1-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="30bd1-114">您可以使用 Skype for Business 服务器控制面板查看网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="30bd1-115">网络区域包括用于确定音频和视频连接是否允许通过 Internet 的备用路径的设置。</span><span class="sxs-lookup"><span data-stu-id="30bd1-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="30bd1-116">使用本主题查看现有的网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="30bd1-117">使用 Skype for Business 服务器控制面板查看有关网络区域的信息</span><span class="sxs-lookup"><span data-stu-id="30bd1-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="30bd1-118">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="30bd1-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="30bd1-119">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="30bd1-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="30bd1-120">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域**"。</span><span class="sxs-lookup"><span data-stu-id="30bd1-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="30bd1-121">在 "**区域**" 页面上，单击要查看的区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="30bd1-122">一次只能查看一个区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="30bd1-123">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="30bd1-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="30bd1-124">使用 Windows PowerShell cmdlet 查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="30bd1-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="30bd1-125">你可以使用 Windows PowerShell 和**CsNetworkRegion** cmdlet 查看网络区域信息。</span><span class="sxs-lookup"><span data-stu-id="30bd1-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="30bd1-126">你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="30bd1-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="30bd1-127">查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="30bd1-127">To view network region information</span></span>

  - <span data-ttu-id="30bd1-128">若要查看有关所有网络区域的信息，请在 Skype for Business Server 命令行管理器中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="30bd1-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="30bd1-129">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="30bd1-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="30bd1-130">有关详细信息，请参阅[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="30bd1-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="30bd1-131">创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="30bd1-131">Create or modify network regions</span></span> 

<span data-ttu-id="30bd1-132">网络区域跨多个地理区域互连网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="30bd1-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="30bd1-133">每个网络区域必须与一个中心网站相关联。</span><span class="sxs-lookup"><span data-stu-id="30bd1-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="30bd1-134">中心网站是运行呼叫许可控制（CAC）带宽策略服务的数据中心网站。</span><span class="sxs-lookup"><span data-stu-id="30bd1-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="30bd1-135">您可以使用 Skype for Business 服务器控制面板配置网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="30bd1-136">网络区域包括用于确定音频和视频连接是否允许通过 Internet 的备用路径的设置。</span><span class="sxs-lookup"><span data-stu-id="30bd1-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="30bd1-137">在 "Skype for Business 服务器" 控制面板中，可以创建、修改或删除网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="30bd1-138">使用本主题创建和修改网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="30bd1-139">创建网络区域</span><span class="sxs-lookup"><span data-stu-id="30bd1-139">To create a network region</span></span>

1.  <span data-ttu-id="30bd1-140">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="30bd1-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="30bd1-141">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="30bd1-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="30bd1-142">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域**"。</span><span class="sxs-lookup"><span data-stu-id="30bd1-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="30bd1-143">在 "**区域**" 页面上，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="30bd1-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="30bd1-144">在 "**新区域**" 页面上，在 "**名称**" 字段中键入值。</span><span class="sxs-lookup"><span data-stu-id="30bd1-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="30bd1-145">此值在 Skype for Business 服务器部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="30bd1-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="30bd1-146">从 "**中心站点**" 下拉列表中，选择此网络区域的中心网站。</span><span class="sxs-lookup"><span data-stu-id="30bd1-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="30bd1-147">默认情况下，"**启用音频备用路径**" 复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="30bd1-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="30bd1-148">此字段确定当主路径中不存在足够带宽时是否将通过备用路径路由音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="30bd1-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="30bd1-149">仅当需要关闭将卸载到 Internet 时，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="30bd1-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="30bd1-150">如果你的任何呼叫将是 Internet 呼叫，则必须选中此复选框，无论带宽设置如何。</span><span class="sxs-lookup"><span data-stu-id="30bd1-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="30bd1-151">默认情况下，"**启用视频备用路径**" 复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="30bd1-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="30bd1-152">此字段确定当主路径中不存在足够带宽时，是否会通过备用路径路由视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="30bd1-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="30bd1-153">仅当需要关闭将卸载到 Internet 时，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="30bd1-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="30bd1-154">如果你的任何呼叫将是 Internet 呼叫，则必须选中此复选框，无论带宽设置如何。</span><span class="sxs-lookup"><span data-stu-id="30bd1-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="30bd1-155">可选在 "**说明**" 字段中键入一个值，以提供有关无法单独使用名称表示的此区域的详细信息。</span><span class="sxs-lookup"><span data-stu-id="30bd1-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="30bd1-156">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="30bd1-156">Click **Commit**.</span></span>

<span data-ttu-id="30bd1-157">**关联的网站**表不用于创建网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="30bd1-158">创建或修改网站时，将网站与区域相关联。</span><span class="sxs-lookup"><span data-stu-id="30bd1-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="30bd1-159">有关详细信息，请参阅[管理网站的呼叫许可控制](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="30bd1-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="30bd1-160">修改网络区域</span><span class="sxs-lookup"><span data-stu-id="30bd1-160">To modify a network region</span></span>

1.  <span data-ttu-id="30bd1-161">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="30bd1-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="30bd1-162">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="30bd1-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="30bd1-163">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域**"。</span><span class="sxs-lookup"><span data-stu-id="30bd1-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="30bd1-164">在 "**区域**" 页面上，单击要修改的区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="30bd1-165">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="30bd1-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="30bd1-166">在 "**编辑区域**" 页面上，您可以修改启用和禁用音频和视频备用路径的设置，并更改说明（有关详细信息，请参阅本主题前面的 "创建网络区域" 一节。</span><span class="sxs-lookup"><span data-stu-id="30bd1-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="30bd1-167">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="30bd1-167">Click **Commit**.</span></span>

<span data-ttu-id="30bd1-168">您不能修改此页面上的**相关网站**。</span><span class="sxs-lookup"><span data-stu-id="30bd1-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="30bd1-169">将提供相关网站的列表以供参考，以便你知道在修改区域设置时将受到哪些网站的影响。</span><span class="sxs-lookup"><span data-stu-id="30bd1-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="30bd1-170">删除现有网络区域</span><span class="sxs-lookup"><span data-stu-id="30bd1-170">Delete existing network regions</span></span> 

<span data-ttu-id="30bd1-171">网络区域跨多个地理区域互连网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="30bd1-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="30bd1-172">每个网络区域必须与一个中心网站相关联。</span><span class="sxs-lookup"><span data-stu-id="30bd1-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="30bd1-173">中心网站是运行呼叫许可控制（CAC）带宽策略服务的数据中心网站。</span><span class="sxs-lookup"><span data-stu-id="30bd1-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="30bd1-174">您可以使用 Skype for Business 服务器控制面板配置网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="30bd1-175">网络区域包括用于确定音频和视频连接是否允许通过 Internet 的备用路径的设置。</span><span class="sxs-lookup"><span data-stu-id="30bd1-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="30bd1-176">在 "Skype for Business 服务器" 控制面板中，可以创建、修改或删除网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="30bd1-177">使用本主题删除现有网络区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="30bd1-178">删除网络区域</span><span class="sxs-lookup"><span data-stu-id="30bd1-178">To delete a network region</span></span>

1.  <span data-ttu-id="30bd1-179">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="30bd1-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="30bd1-180">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="30bd1-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="30bd1-181">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域**"。</span><span class="sxs-lookup"><span data-stu-id="30bd1-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="30bd1-182">在 "**区域**" 页面上，单击要删除的区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="30bd1-183">您可以一次删除多个区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="30bd1-184">若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个区域。</span><span class="sxs-lookup"><span data-stu-id="30bd1-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="30bd1-185">或者，若要选择所有区域，请单击 "**编辑**" 菜单上的 "**全选**"。</span><span class="sxs-lookup"><span data-stu-id="30bd1-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="30bd1-186">在 "**编辑**" 菜单上，单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="30bd1-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="30bd1-187">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="30bd1-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="30bd1-188">如果网络区域与网络网站相关联，则无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="30bd1-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="30bd1-189">如果您尝试删除与网站相关联的区域，您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="30bd1-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="30bd1-190">若要查看某个区域是否与任何网站相关联，请选择该区域，然后单击 "**编辑**" 菜单上的 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="30bd1-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="30bd1-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30bd1-191">See Also</span></span>

[<span data-ttu-id="30bd1-192">管理网络区域路由</span><span class="sxs-lookup"><span data-stu-id="30bd1-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="30bd1-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="30bd1-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="30bd1-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="30bd1-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="30bd1-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="30bd1-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="30bd1-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="30bd1-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
