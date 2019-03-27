---
title: 管理网站的呼叫允许控制
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络站点间办公室或位置中的每个网络区域呼叫允许控制 (CAC)、 E9-1-1 和媒体绕过部署。
ms.openlocfilehash: 53140cf03110991f2c757e5d52e30a6c7db1d7de
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895417"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="f982a-103">在 Skype for Business Server 中管理站点的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="f982a-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="f982a-104">网络站点间办公室或位置中的每个网络区域呼叫允许控制 (CAC)、 E9-1-1 和媒体绕过部署。</span><span class="sxs-lookup"><span data-stu-id="f982a-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="f982a-105">使用本文中的过程配置网络站点的呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="f982a-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="f982a-106">配置网络站点链接</span><span class="sxs-lookup"><span data-stu-id="f982a-106">Configure network site links</span></span>

<span data-ttu-id="f982a-107">在呼叫允许控制 (CAC) 配置，您可以创建网络定义直接链接的站点间带宽限制的站点间策略。</span><span class="sxs-lookup"><span data-stu-id="f982a-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="f982a-108">当网络站点共享直接链接时，可以在这些两个站点之间定义连接音频和视频的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="f982a-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="f982a-109">您无法使用的业务 Server Control Panel Skype 配置网络站点策略，这可以仅通过使用 for Business Server Management Shell cmdlet 从 Skype 完成。</span><span class="sxs-lookup"><span data-stu-id="f982a-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f982a-110">您可以创建、 修改和删除业务 Server 命令行管理程序从 Skype 网络站点链接 （也称为网络站点间策略）。</span><span class="sxs-lookup"><span data-stu-id="f982a-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="f982a-111">创建网络站点链接</span><span class="sxs-lookup"><span data-stu-id="f982a-111">To create a network site link</span></span>

1.  <span data-ttu-id="f982a-112">登录到计算机的业务 Server Management Shell 的 Skype 或使用的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="f982a-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="f982a-113">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="f982a-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="f982a-114">在命令提示符处，键入以下命令，取代有效的配置的值：</span><span class="sxs-lookup"><span data-stu-id="f982a-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="f982a-115">本示例创建新的网络站点链接名为 Reno\_波特兰里诺和波特兰网络站点之间设置带宽限制。</span><span class="sxs-lookup"><span data-stu-id="f982a-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="f982a-116">网络站点和带宽策略配置文件必须运行此命令之前已经存在。</span><span class="sxs-lookup"><span data-stu-id="f982a-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="f982a-117">有关详细的参数说明，请参阅[新建 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="f982a-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="f982a-118">若要检索可应用于网络站点链接的带宽策略配置文件的列表，请调用**Get-csnetworkbandwidthpolicyprofile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f982a-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="f982a-119">有关详细信息，请参阅[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。</span><span class="sxs-lookup"><span data-stu-id="f982a-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="f982a-120">修改网络站点链接</span><span class="sxs-lookup"><span data-stu-id="f982a-120">To modify a network site link</span></span>

1.  <span data-ttu-id="f982a-121">登录到计算机的业务 Server Management Shell 的 Skype 或使用的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="f982a-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="f982a-122">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="f982a-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="f982a-123">使用**Set-csnetworkintersitepolicy** cmdlet 可以修改给定的网络站点链接的属性。</span><span class="sxs-lookup"><span data-stu-id="f982a-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="f982a-124">您可以修改 （或两者） 或连接的站点，并且您可以修改与链接关联的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="f982a-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="f982a-125">下面是一个示例修改名为 Reno 站点链接的带宽策略配置文件的\_波特兰：</span><span class="sxs-lookup"><span data-stu-id="f982a-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="f982a-126">有关详细的参数说明，请参阅[Set-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="f982a-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="f982a-127">删除网络站点链接</span><span class="sxs-lookup"><span data-stu-id="f982a-127">To delete a network site link</span></span>

1.  <span data-ttu-id="f982a-128">登录到计算机的业务 Server Management Shell 的 Skype 或使用的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="f982a-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="f982a-129">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="f982a-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="f982a-130">使用**Remove-csnetworkintersitepolicy** cmdlet 可以删除网络站点链接。</span><span class="sxs-lookup"><span data-stu-id="f982a-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="f982a-131">下面的示例删除 Reno\_波特兰网络站点链接：</span><span class="sxs-lookup"><span data-stu-id="f982a-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="f982a-132">有关详细的参数说明，请参阅[Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="f982a-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="f982a-133">查看网络站点信息</span><span class="sxs-lookup"><span data-stu-id="f982a-133">View network site information</span></span>

<span data-ttu-id="f982a-134">网络站点的办公室或配置呼叫允许控制 (CAC) 或增强型 9-1-1 部署的每个区域中的位置。</span><span class="sxs-lookup"><span data-stu-id="f982a-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f982a-135">您可以查看网络站点信息中任一 Skype 业务 Server Control Panel 或 Skype 的业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="f982a-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="f982a-136">若要查看网络站点信息 Skype 中的业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="f982a-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f982a-137">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f982a-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f982a-138">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f982a-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f982a-139">在左侧的导航栏中，单击**网络配置**，然后单击**网站**。</span><span class="sxs-lookup"><span data-stu-id="f982a-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f982a-140">在**网站**页上，单击您想要查看的站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="f982a-141">您只能查看一个站点一次的信息。</span><span class="sxs-lookup"><span data-stu-id="f982a-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="f982a-142">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f982a-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f982a-143">通过使用 Windows PowerShell cmdlet 查看网络站点信息</span><span class="sxs-lookup"><span data-stu-id="f982a-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f982a-144">您可以使用 Windows PowerShell 和 Get-csnetworksite cmdlet 查看网络站点信息。</span><span class="sxs-lookup"><span data-stu-id="f982a-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="f982a-145">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f982a-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="f982a-146">若要查看网络站点信息</span><span class="sxs-lookup"><span data-stu-id="f982a-146">To view network site information</span></span>

  - <span data-ttu-id="f982a-147">若要查看有关所有网络站点的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="f982a-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="f982a-148">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="f982a-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="f982a-149">有关详细信息，请参阅[Get-csnetworksite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="f982a-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="f982a-150">创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="f982a-150">Create or modify network sites</span></span> 

<span data-ttu-id="f982a-151">网络站点的办公室或配置呼叫允许控制 (CAC) 或增强型 9-1-1 部署的每个区域中的位置。</span><span class="sxs-lookup"><span data-stu-id="f982a-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f982a-152">为业务 Server Control Panel Skype 可用于配置站点和将它们与区域关联。</span><span class="sxs-lookup"><span data-stu-id="f982a-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="f982a-153">例如，网络区域北美可能与芝加哥，Redmond，等 Vancouver 的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="f982a-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="f982a-154">CAC 网络站点必须创建为在组织内每个站点，即使该网站具有没有带宽限制。</span><span class="sxs-lookup"><span data-stu-id="f982a-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="f982a-155">从业务 Server Control Panel Skype 您可以创建、 修改和删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="f982a-156">使用以下过程可创建或修改网络站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="f982a-157">创建网络站点</span><span class="sxs-lookup"><span data-stu-id="f982a-157">To create a network site</span></span>

1.  <span data-ttu-id="f982a-158">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f982a-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f982a-159">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f982a-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f982a-160">在左侧的导航栏中，单击**网络配置**，然后单击**网站**。</span><span class="sxs-lookup"><span data-stu-id="f982a-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f982a-161">在**网站**页上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="f982a-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="f982a-162">在**新的网站**中，键入此网站的**名称**字段的名称。</span><span class="sxs-lookup"><span data-stu-id="f982a-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f982a-163">网站名称必须是唯一的业务服务器部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="f982a-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="f982a-164">在**区域**下拉列表中，选择与此站点关联的网络区域。</span><span class="sxs-lookup"><span data-stu-id="f982a-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="f982a-165">（可选）如果您想要访问此网站的音频或视频呼叫设置带宽限制，具有相应设置从**带宽策略**下拉列表中选择带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="f982a-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="f982a-166">您可以查看可用带宽策略配置文件的详细信息，或创建一个新的带宽策略配置文件，在**网络配置**组**策略 Profil**网页上。</span><span class="sxs-lookup"><span data-stu-id="f982a-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="f982a-167">有关详细信息，请参阅[Managing 网络带宽策略配置文件](managing-network-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="f982a-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="f982a-168">（可选）如果您想要为此站点提供位置设置，请从**位置策略**下拉列表中选择位置策略。</span><span class="sxs-lookup"><span data-stu-id="f982a-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f982a-169">位置策略分配特定的增强型 9-1-1 (E9-1-1) 和客户端位置设置到网站。</span><span class="sxs-lookup"><span data-stu-id="f982a-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="f982a-170">您可以查看可用位置策略的详细信息，或创建新的位置策略，从**位置策略**页上的**网络配置**组。</span><span class="sxs-lookup"><span data-stu-id="f982a-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="f982a-171">（可选）在**说明**字段，以提供有关该站点的名称本身不能表示的详细信息，请键入一个值。</span><span class="sxs-lookup"><span data-stu-id="f982a-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="f982a-172">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f982a-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f982a-173">创建新的网络站点时不使用**关联子网**表。</span><span class="sxs-lookup"><span data-stu-id="f982a-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="f982a-174">当您创建或修改子网与站点关联子网。</span><span class="sxs-lookup"><span data-stu-id="f982a-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="f982a-175">有关详细信息，请参阅[管理网络子网](managing-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="f982a-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="f982a-176">修改网络站点</span><span class="sxs-lookup"><span data-stu-id="f982a-176">To modify a network site</span></span>

1.  <span data-ttu-id="f982a-177">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f982a-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f982a-178">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f982a-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f982a-179">在左侧的导航栏中，单击**网络配置**，然后单击**网站**。</span><span class="sxs-lookup"><span data-stu-id="f982a-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f982a-180">在**网站**页上，单击要修改的站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="f982a-181">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f982a-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f982a-182">在**编辑站点**页上，可以修改说明、 区域、 带宽策略配置文件和与网站关联的位置策略。</span><span class="sxs-lookup"><span data-stu-id="f982a-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="f982a-183">有关详细信息，请参阅[创建网络站点](#to-create-a-network-site)上面。</span><span class="sxs-lookup"><span data-stu-id="f982a-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="f982a-184">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f982a-184">Click **Commit**.</span></span>

<span data-ttu-id="f982a-185">不能修改此页上的**关联子网**表格。</span><span class="sxs-lookup"><span data-stu-id="f982a-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="f982a-186">关联子网列表提供的引用，以便了解当您修改的网站设置时，将影响哪些子网。</span><span class="sxs-lookup"><span data-stu-id="f982a-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="f982a-187">删除现有网络站点</span><span class="sxs-lookup"><span data-stu-id="f982a-187">Delete an existing network site</span></span>

<span data-ttu-id="f982a-188">网络站点的办公室或配置呼叫允许控制 (CAC) 或增强型 9-1-1 部署的每个区域中的位置。</span><span class="sxs-lookup"><span data-stu-id="f982a-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f982a-189">为业务 Server Control Panel Skype 可用于配置站点和将它们与区域关联。</span><span class="sxs-lookup"><span data-stu-id="f982a-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="f982a-190">例如，网络区域北美可能与芝加哥，Redmond，等 Vancouver 的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="f982a-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="f982a-191">CAC 网络站点必须创建为在组织内每个站点，即使该网站具有没有带宽限制。</span><span class="sxs-lookup"><span data-stu-id="f982a-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="f982a-192">从业务 Server Control Panel Skype 您可以创建、 修改和删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="f982a-193">使用以下过程可删除现有网络站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="f982a-194">有关创建或修改网络站点的详细信息，请参阅[Managing 呼叫允许控制的网站](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="f982a-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="f982a-195">删除网络站点</span><span class="sxs-lookup"><span data-stu-id="f982a-195">To delete a network site</span></span>

1.  <span data-ttu-id="f982a-196">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f982a-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f982a-197">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f982a-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f982a-198">在左侧的导航栏中，单击**网络配置**，然后单击**网站**。</span><span class="sxs-lookup"><span data-stu-id="f982a-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f982a-199">在**网站**页上，单击您要删除的站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f982a-200">您可以一次删除多个站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="f982a-201">若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="f982a-202">或者，若要选择所有网站，**都选择全部**上单击**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="f982a-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="f982a-203">在**编辑**菜单上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="f982a-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="f982a-204">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="f982a-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="f982a-205">网络子网与关联时，不能删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="f982a-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="f982a-206">如果尝试删除站点与子网关联将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="f982a-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="f982a-207">要查看网站是否与任何子网关联，请单击网站，然后单击**编辑**菜单上的**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="f982a-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="f982a-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f982a-208">See Also</span></span>


[<span data-ttu-id="f982a-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f982a-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="f982a-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f982a-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="f982a-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f982a-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="f982a-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f982a-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="f982a-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f982a-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="f982a-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f982a-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="f982a-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f982a-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="f982a-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f982a-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="f982a-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f982a-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
