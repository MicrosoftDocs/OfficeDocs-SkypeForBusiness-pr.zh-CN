---
title: 管理网站的呼叫允许控制
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
description: “网络站点”是指部署了呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的每个网络区域内的办公室或位置。
ms.openlocfilehash: dbe02c78c40cab48a79d7c63d3c6239b4ae59458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816452"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="6d350-103">在 Skype for Business Server 中管理站点的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="6d350-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="6d350-104">“网络站点”是指部署了呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的每个网络区域内的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="6d350-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="6d350-105">使用本文中的过程为网络站点配置呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="6d350-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="6d350-106">配置网络站点链接</span><span class="sxs-lookup"><span data-stu-id="6d350-106">Configure network site links</span></span>

<span data-ttu-id="6d350-107">在呼叫允许控制 (CAC) 配置中，可以创建定义直接链接的站点之间的带宽限制的网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="6d350-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="6d350-108">当两个网络站点共享一条直接链接时，可定义这两个站点之间的音频和视频连接的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="6d350-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="6d350-109">不能使用 Skype for Business Server 控制面板配置网络站点策略，这只能通过使用 Skype for Business Server 命令行管理程序 中的 cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="6d350-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="6d350-110">可以创建、修改和删除网络站点链接 (Skype for Business Server 命令行管理程序) 网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="6d350-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="6d350-111">创建网络站点链接</span><span class="sxs-lookup"><span data-stu-id="6d350-111">To create a network site link</span></span>

1.  <span data-ttu-id="6d350-112">以 RTCUniversalServerAdmins 组的成员或必要的用户权限登录到安装了 Skype for Business Server 命令行管理程序的计算机。</span><span class="sxs-lookup"><span data-stu-id="6d350-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="6d350-113">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business Server"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="6d350-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d350-114">在命令提示符处，键入以下命令，取代有效的配置值：</span><span class="sxs-lookup"><span data-stu-id="6d350-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="6d350-115">此示例创建一个名为 Reno Portland 的新网络站点链接，该链接设置 Reno 和 Portland 网络站点之间的 \_ 带宽限制。</span><span class="sxs-lookup"><span data-stu-id="6d350-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="6d350-116">运行此命令之前，必须已存在网络站点和带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="6d350-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="6d350-117">有关详细的参数说明，请参阅 [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d350-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="6d350-118">要检索可应用于网络站点链接的带宽策略配置文件列表，请调用 **Get-CsNetworkBandwidthPolicyProfile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d350-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="6d350-119">有关详细信息，请参阅 [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。</span><span class="sxs-lookup"><span data-stu-id="6d350-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="6d350-120">修改网络站点链接</span><span class="sxs-lookup"><span data-stu-id="6d350-120">To modify a network site link</span></span>

1.  <span data-ttu-id="6d350-121">以 RTCUniversalServerAdmins 组的成员或必要的用户权限登录到安装了 Skype for Business Server 命令行管理程序的计算机。</span><span class="sxs-lookup"><span data-stu-id="6d350-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="6d350-122">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business Server"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="6d350-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d350-123">使用 **Set-CsNetworkInterSitePolicy** cmdlet 修改给定网络站点链接的属性。</span><span class="sxs-lookup"><span data-stu-id="6d350-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="6d350-124">可以修改连接站点中的任一个（或两个），也可以修改与链接关联的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="6d350-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="6d350-125">下面是修改名为 Reno Portland 的站点链接的带宽策略 \_ 配置文件的示例：</span><span class="sxs-lookup"><span data-stu-id="6d350-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="6d350-126">有关详细的参数说明，请参阅 [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d350-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="6d350-127">删除网络站点链接</span><span class="sxs-lookup"><span data-stu-id="6d350-127">To delete a network site link</span></span>

1.  <span data-ttu-id="6d350-128">以 RTCUniversalServerAdmins 组的成员或必要的用户权限登录到安装了 Skype for Business Server 命令行管理程序的计算机。</span><span class="sxs-lookup"><span data-stu-id="6d350-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="6d350-129">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business Server"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="6d350-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d350-130">使用 **Remove-CsNetworkInterSitePolicy** cmdlet 删除网络站点链接。</span><span class="sxs-lookup"><span data-stu-id="6d350-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="6d350-131">以下示例删除 Reno Portland \_ 网络站点链接：</span><span class="sxs-lookup"><span data-stu-id="6d350-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="6d350-132">有关详细的参数说明，请参阅 [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d350-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="6d350-133">查看网络站点信息</span><span class="sxs-lookup"><span data-stu-id="6d350-133">View network site information</span></span>

<span data-ttu-id="6d350-134">网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="6d350-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="6d350-135">可以在 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序 中查看网络站点信息。</span><span class="sxs-lookup"><span data-stu-id="6d350-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="6d350-136">在 Skype for Business Server 控制面板中查看网络站点信息</span><span class="sxs-lookup"><span data-stu-id="6d350-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="6d350-137">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="6d350-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d350-138">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="6d350-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6d350-139">在左侧导航栏中，单击 **"网络配置**"，然后单击"站点 **"。**</span><span class="sxs-lookup"><span data-stu-id="6d350-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="6d350-140">在“站点”页上，单击要查看的站点。</span><span class="sxs-lookup"><span data-stu-id="6d350-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="6d350-141">一次只能查看一个站点的信息。</span><span class="sxs-lookup"><span data-stu-id="6d350-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="6d350-142">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="6d350-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6d350-143">使用 cmdlet Windows PowerShell网络站点信息</span><span class="sxs-lookup"><span data-stu-id="6d350-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="6d350-144">可以使用 Windows PowerShell 和 Get-CsNetworkSite cmdlet 查看网络站点信息。</span><span class="sxs-lookup"><span data-stu-id="6d350-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="6d350-145">此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6d350-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="6d350-146">查看网络站点信息</span><span class="sxs-lookup"><span data-stu-id="6d350-146">To view network site information</span></span>

  - <span data-ttu-id="6d350-147">若要查看有关所有网络站点的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="6d350-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="6d350-148">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="6d350-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="6d350-149">有关详细信息，请参阅 [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6d350-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="6d350-150">创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="6d350-150">Create or modify network sites</span></span> 

<span data-ttu-id="6d350-151">网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="6d350-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="6d350-152">可以使用 Skype for Business Server 控制面板配置站点并将其与区域关联。</span><span class="sxs-lookup"><span data-stu-id="6d350-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="6d350-153">例如，可将北美网络区域与 Chicago、Redmond 和 Vancouver 之类的网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="6d350-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="6d350-154">必须为组织中的每个站点创建一个 CAC 网络站点，即使该站点没有带宽限制也应如此。</span><span class="sxs-lookup"><span data-stu-id="6d350-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="6d350-155">在 Skype for Business Server 控制面板中，可以创建、修改和删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="6d350-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="6d350-156">使用下面的过程可创建或修改网络站点。</span><span class="sxs-lookup"><span data-stu-id="6d350-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="6d350-157">创建网络站点</span><span class="sxs-lookup"><span data-stu-id="6d350-157">To create a network site</span></span>

1.  <span data-ttu-id="6d350-158">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="6d350-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d350-159">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="6d350-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6d350-160">在左侧导航栏中，单击 **"网络配置**"，然后单击"站点 **"。**</span><span class="sxs-lookup"><span data-stu-id="6d350-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="6d350-161">在“站点”页上，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="6d350-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="6d350-162">在“新建站点”的“名称”字段中，键入此站点的名称。</span><span class="sxs-lookup"><span data-stu-id="6d350-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="6d350-163">站点名称在 Skype for Business Server 部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6d350-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="6d350-164">在“区域”下拉列表中，选择与此站点关联的网络区域。</span><span class="sxs-lookup"><span data-stu-id="6d350-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="6d350-165">（可选）如果要对此站点的音频或视频呼叫设置带宽限制，请从“带宽策略”下拉列表中选择具有相应设置的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="6d350-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="6d350-166">您可以在"网络配置"组的"策略分析"页上查看可用带宽策略配置文件的详细信息，或创建新的带宽 **策略** 配置文件。 </span><span class="sxs-lookup"><span data-stu-id="6d350-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="6d350-167">有关详细信息，请参阅 [管理网络带宽策略配置文件](managing-network-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="6d350-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="6d350-168">（可选）如果要为此站点提供位置设置，请从“位置策略”下拉列表中选择位置策略。</span><span class="sxs-lookup"><span data-stu-id="6d350-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="6d350-169">位置策略会将特定的增强型 9-1-1 (E9-1-1) 和客户端位置设置分配给站点。</span><span class="sxs-lookup"><span data-stu-id="6d350-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="6d350-170">在“网络配置”组的“位置策略”页上，可以查看可用位置策略的详细信息，或创建新的位置策略。</span><span class="sxs-lookup"><span data-stu-id="6d350-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="6d350-171">（可选）在“说明”字段中键入值，用以提供仅通过名称无法表达的更多有关该站点的信息。</span><span class="sxs-lookup"><span data-stu-id="6d350-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="6d350-172">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="6d350-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="6d350-173">创建新网络站点时，不要使用“关联子网”表。</span><span class="sxs-lookup"><span data-stu-id="6d350-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="6d350-174">创建或修改子网时，会将子网与站点相关联。</span><span class="sxs-lookup"><span data-stu-id="6d350-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="6d350-175">有关详细信息，请参阅["管理网络子网"。](managing-network-subnets.md)</span><span class="sxs-lookup"><span data-stu-id="6d350-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="6d350-176">修改网络站点</span><span class="sxs-lookup"><span data-stu-id="6d350-176">To modify a network site</span></span>

1.  <span data-ttu-id="6d350-177">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="6d350-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d350-178">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="6d350-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6d350-179">在左侧导航栏中，单击 **"网络配置**"，然后单击"站点 **"。**</span><span class="sxs-lookup"><span data-stu-id="6d350-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="6d350-180">在“站点”页上，单击要修改的站点。</span><span class="sxs-lookup"><span data-stu-id="6d350-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="6d350-181">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="6d350-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="6d350-182">在“编辑站点”页上，可以修改与站点关联的说明、区域、带宽策略配置文件以及位置策略。</span><span class="sxs-lookup"><span data-stu-id="6d350-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="6d350-183">有关详细信息，请参阅 [上面的"创建网络站点](#to-create-a-network-site) "。</span><span class="sxs-lookup"><span data-stu-id="6d350-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="6d350-184">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="6d350-184">Click **Commit**.</span></span>

<span data-ttu-id="6d350-p114">不能修改此页面中的“关联子网”表。关联子网列表仅供参考，以使您注意修改站点设置时将影响的子网。</span><span class="sxs-lookup"><span data-stu-id="6d350-p114">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="6d350-187">删除现有网络站点</span><span class="sxs-lookup"><span data-stu-id="6d350-187">Delete an existing network site</span></span>

<span data-ttu-id="6d350-188">网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="6d350-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="6d350-189">可以使用 Skype for Business Server 控制面板配置站点并将其与区域关联。</span><span class="sxs-lookup"><span data-stu-id="6d350-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="6d350-190">例如，可将北美网络区域与 Chicago、Redmond 和 Vancouver 之类的网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="6d350-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="6d350-191">必须为组织中的每个站点创建一个 CAC 网络站点，即使该站点没有带宽限制也应如此。</span><span class="sxs-lookup"><span data-stu-id="6d350-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="6d350-192">在 Skype for Business Server 控制面板中，可以创建、修改和删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="6d350-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="6d350-193">使用以下过程可删除现有网络站点。</span><span class="sxs-lookup"><span data-stu-id="6d350-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="6d350-194">有关创建或修改网络站点的详细信息，请参阅["管理网站的呼叫允许控制"。](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="6d350-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="6d350-195">删除网络站点</span><span class="sxs-lookup"><span data-stu-id="6d350-195">To delete a network site</span></span>

1.  <span data-ttu-id="6d350-196">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="6d350-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d350-197">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="6d350-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6d350-198">在左侧导航栏中，单击 **"网络配置**"，然后单击"站点 **"。**</span><span class="sxs-lookup"><span data-stu-id="6d350-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="6d350-199">在“站点”页上，单击要删除的站点。</span><span class="sxs-lookup"><span data-stu-id="6d350-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="6d350-p116">可一次性删除多个站点。要执行此操作，请按住 Ctrl 键，同时选择多个站点。或者，要选择全部站点，请单击“编辑”菜单中的“全选”。</span><span class="sxs-lookup"><span data-stu-id="6d350-p116">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="6d350-203">在“编辑”菜单上，单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="6d350-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="6d350-204">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6d350-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="6d350-p117">不能删除与网络子网关联的网络站点。如果尝试删除与某个子网关联的站点，您将收到错误消息。要查看站点是否与任何子网关联，请单击相应的站点，然后单击“编辑”菜单中的“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="6d350-p117">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="6d350-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d350-208">See Also</span></span>


[<span data-ttu-id="6d350-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6d350-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="6d350-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6d350-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="6d350-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6d350-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="6d350-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6d350-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="6d350-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6d350-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="6d350-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="6d350-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="6d350-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="6d350-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="6d350-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="6d350-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="6d350-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="6d350-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
