---
title: 管理网站的呼叫许可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络站点是呼叫许可控制 (CAC)、E9-1 和媒体绕过部署的每个网络区域内的办公室或位置。
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279541"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="0a7f6-103">在 Skype for Business Server 中管理站点的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="0a7f6-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="0a7f6-104">网络站点是呼叫许可控制 (CAC)、E9-1 和媒体绕过部署的每个网络区域内的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="0a7f6-105">使用本文中的过程配置网络站点的 "呼叫许可控制"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="0a7f6-106">配置网络站点链接</span><span class="sxs-lookup"><span data-stu-id="0a7f6-106">Configure network site links</span></span>

<span data-ttu-id="0a7f6-107">在呼叫许可控制 (CAC) 配置中, 你可以创建网络间策略来定义直接链接的网站之间的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="0a7f6-108">当网络站点共享直接链接时, 可以在这两个站点之间定义音频和视频连接的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="0a7f6-109">您不能使用 Skype for Business 服务器控制面板配置网络站点策略, 只能通过使用 Skype for Business Server 命令行管理程序中的 cmdlet 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0a7f6-110">你可以从 Skype for Business Server 命令行管理程序创建、修改和删除网络网站链接 (也称为网络内部站点策略)。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="0a7f6-111">创建网络站点链接</span><span class="sxs-lookup"><span data-stu-id="0a7f6-111">To create a network site link</span></span>

1.  <span data-ttu-id="0a7f6-112">登录到安装了 Skype for Business 服务器管理外壳的计算机作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="0a7f6-113">启动 Skype for Business 服务器命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **skype for business 服务器**", 然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="0a7f6-114">在命令提示符处, 键入以下命令, 替换适用于您的配置的有效值:</span><span class="sxs-lookup"><span data-stu-id="0a7f6-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="0a7f6-115">此示例创建一个名为 Reno\_的新网络网站链接, 该链接设置 Reno 和网络站点之间的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="0a7f6-116">运行此命令之前, 网络站点和带宽策略配置文件必须已经存在。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="0a7f6-117">有关详细的参数说明, 请参阅[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="0a7f6-118">若要检索可应用于网络站点链接的带宽策略配置文件的列表, 请调用**CsNetworkBandwidthPolicyProfile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="0a7f6-119">有关详细信息, 请参阅[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="0a7f6-120">修改网络站点链接</span><span class="sxs-lookup"><span data-stu-id="0a7f6-120">To modify a network site link</span></span>

1.  <span data-ttu-id="0a7f6-121">登录到安装了 Skype for Business 服务器管理外壳的计算机作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="0a7f6-122">启动 Skype for Business 服务器命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **skype for business 服务器**", 然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="0a7f6-123">使用**CsNetworkInterSitePolicy** cmdlet 修改给定网络网站链接的属性。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="0a7f6-124">您可以修改两个 (或两者) 或连接的网站, 并且可以修改与链接关联的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="0a7f6-125">下面是修改名为 Reno\_的网站链接的带宽策略配置文件的示例:</span><span class="sxs-lookup"><span data-stu-id="0a7f6-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="0a7f6-126">有关详细的参数说明, 请参阅[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="0a7f6-127">删除网络网站链接</span><span class="sxs-lookup"><span data-stu-id="0a7f6-127">To delete a network site link</span></span>

1.  <span data-ttu-id="0a7f6-128">登录到安装了 Skype for Business 服务器管理外壳的计算机作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="0a7f6-129">启动 Skype for Business 服务器命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **skype for business 服务器**", 然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="0a7f6-130">使用**CsNetworkInterSitePolicy** cmdlet 删除网络站点链接。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="0a7f6-131">以下示例删除 Reno\_的 "上海" 网络网站链接:</span><span class="sxs-lookup"><span data-stu-id="0a7f6-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="0a7f6-132">有关详细的参数说明, 请参阅[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="0a7f6-133">查看网络网站信息</span><span class="sxs-lookup"><span data-stu-id="0a7f6-133">View network site information</span></span>

<span data-ttu-id="0a7f6-134">网络站点是在呼叫许可控制 (CAC) 或增强的9-1-1 部署的每个区域内配置的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="0a7f6-135">您可以在 Skype for Business Server 控制面板或 Skype for business Server 命令行管理程序中查看网络站点信息。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="0a7f6-136">在 "Skype for Business 服务器" 控制面板中查看网络站点信息</span><span class="sxs-lookup"><span data-stu-id="0a7f6-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0a7f6-137">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a7f6-138">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0a7f6-139">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="0a7f6-140">在 "**网站**" 页面上, 单击要查看的网站。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="0a7f6-141">您一次只能查看一个网站的信息。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="0a7f6-142">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0a7f6-143">使用 Windows PowerShell cmdlet 查看网络网站信息</span><span class="sxs-lookup"><span data-stu-id="0a7f6-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0a7f6-144">你可以使用 Windows PowerShell 和 CsNetworkSite cmdlet 查看网络网站信息。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="0a7f6-145">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="0a7f6-146">查看网络站点信息</span><span class="sxs-lookup"><span data-stu-id="0a7f6-146">To view network site information</span></span>

  - <span data-ttu-id="0a7f6-147">若要查看有关所有网络网站的信息, 请在 Skype for Business Server 命令行管理程序中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="0a7f6-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="0a7f6-148">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="0a7f6-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="0a7f6-149">有关详细信息, 请参阅[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="0a7f6-150">创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="0a7f6-150">Create or modify network sites</span></span> 

<span data-ttu-id="0a7f6-151">网络站点是在呼叫许可控制 (CAC) 或增强的9-1-1 部署的每个区域内配置的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="0a7f6-152">您可以使用 Skype for Business 服务器控制面板配置网站并将其与区域相关联。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="0a7f6-153">例如, 北美洲的网络区域可能与诸如芝加哥、雷德蒙和范区的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="0a7f6-154">必须为组织内的每个网站创建 CAC 网络网站, 即使该网站没有带宽限制也是如此。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="0a7f6-155">从 Skype for Business 服务器控制面板, 您可以创建、修改和删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="0a7f6-156">使用以下过程创建或修改网络网站。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="0a7f6-157">创建网络网站</span><span class="sxs-lookup"><span data-stu-id="0a7f6-157">To create a network site</span></span>

1.  <span data-ttu-id="0a7f6-158">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a7f6-159">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0a7f6-160">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="0a7f6-161">在 "**网站**" 页面上, 单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="0a7f6-162">在 "**新建网站**" 中, 在 "**名称**" 字段中键入此网站的名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="0a7f6-163">网站名称在 Skype for Business 服务器部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="0a7f6-164">在 "**区域**" 下拉列表中, 选择要与此网站相关联的网络区域。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="0a7f6-165">可选如果要对此网站的音频或视频呼叫设置带宽限制, 请从 "**带宽策略**" 下拉列表中选择具有相应设置的 "带宽策略配置文件"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="0a7f6-166">你可以在 "**网络配置**" 组的 "**策略 Profil** " 页面上查看可用带宽策略配置文件的详细信息, 或者创建新的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="0a7f6-167">有关详细信息, 请参阅[管理网络带宽策略配置文件](managing-network-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="0a7f6-168">可选如果要为此网站提供位置设置, 请从 "**位置策略**" 下拉列表中选择一个位置策略。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="0a7f6-169">位置策略将特定的增强 9-1-1 (E9-1) 和客户端位置设置分配给该网站。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="0a7f6-170">你可以从 "**网络配置**" 组的 "**位置策略**" 页查看可用位置策略的详细信息, 或者创建新的位置策略。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="0a7f6-171">可选在 "**说明**" 字段中键入一个值, 以提供有关此网站的详细信息, 该信息不能单独以名称表示。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="0a7f6-172">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="0a7f6-173">创建新网络网站时, 请不要使用**关联的子网**表。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="0a7f6-174">创建或修改子网时, 将子网与网站相关联。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="0a7f6-175">有关详细信息, 请参阅[管理网络子网](managing-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="0a7f6-176">修改网络网站</span><span class="sxs-lookup"><span data-stu-id="0a7f6-176">To modify a network site</span></span>

1.  <span data-ttu-id="0a7f6-177">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a7f6-178">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0a7f6-179">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="0a7f6-180">在 "**网站**" 页面上, 单击要修改的网站。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="0a7f6-181">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="0a7f6-182">在 "**编辑网站**" 页面上, 您可以修改与该网站相关联的说明、区域、带宽策略配置文件和位置策略。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="0a7f6-183">有关详细信息, 请参阅[在上面创建网络站点](#to-create-a-network-site)。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="0a7f6-184">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-184">Click **Commit**.</span></span>

<span data-ttu-id="0a7f6-185">不能在此页面上修改**关联的子网**表。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="0a7f6-186">将为参考提供关联子网的列表, 以便你在修改网站设置时知道将受到哪些子网的影响。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="0a7f6-187">删除现有网络网站</span><span class="sxs-lookup"><span data-stu-id="0a7f6-187">Delete an existing network site</span></span>

<span data-ttu-id="0a7f6-188">网络站点是在呼叫许可控制 (CAC) 或增强的9-1-1 部署的每个区域内配置的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="0a7f6-189">您可以使用 Skype for Business 服务器控制面板配置网站并将其与区域相关联。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="0a7f6-190">例如, 北美洲的网络区域可能与诸如芝加哥、雷德蒙和范区的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="0a7f6-191">必须为组织内的每个网站创建 CAC 网络网站, 即使该网站没有带宽限制也是如此。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="0a7f6-192">从 Skype for Business 服务器控制面板, 您可以创建、修改和删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="0a7f6-193">使用以下过程删除现有网络网站。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="0a7f6-194">有关创建或修改网络站点的详细信息, 请参阅[管理网站的呼叫许可控制](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="0a7f6-195">删除网络网站</span><span class="sxs-lookup"><span data-stu-id="0a7f6-195">To delete a network site</span></span>

1.  <span data-ttu-id="0a7f6-196">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a7f6-197">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0a7f6-198">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="0a7f6-199">在 "**网站**" 页面上, 单击要删除的网站。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="0a7f6-200">您可以一次删除多个网站。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="0a7f6-201">若要执行此操作, 请在按住 CTRL 键的同时按 CTRL 并选择多个网站。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="0a7f6-202">或者, 若要选择 "所有网站", 请单击 "**编辑**" 菜单上的 "**全选**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="0a7f6-203">在 "**编辑**" 菜单上, 单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="0a7f6-204">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="0a7f6-205">如果网络站点与网络子网相关联, 则不能将其删除。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="0a7f6-206">如果您尝试删除与子网相关联的网站, 您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="0a7f6-207">若要查看某个网站是否与任何子网相关联, 请单击该网站, 然后单击 "**编辑**" 菜单上的 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="0a7f6-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="0a7f6-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a7f6-208">See Also</span></span>


[<span data-ttu-id="0a7f6-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="0a7f6-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="0a7f6-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="0a7f6-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="0a7f6-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="0a7f6-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="0a7f6-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="0a7f6-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="0a7f6-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="0a7f6-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="0a7f6-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="0a7f6-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="0a7f6-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="0a7f6-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="0a7f6-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="0a7f6-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="0a7f6-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="0a7f6-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
