---
title: 在 Microsoft Teams 中管理云语音功能的网络拓扑
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中配置云语音功能的网络设置。
ms.openlocfilehash: 7d8bc7f06934134538fca59a3f19285d97756e2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802572"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="0ecc0-103">在 Microsoft Teams 中管理云语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="0ecc0-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="0ecc0-104">如果组织为直接路由或[](location-based-routing-plan.md)动态紧急呼叫部署基于位置的路由[](configure-dynamic-emergency-calling.md)，则必须配置网络设置，以在 Microsoft Teams 中使用这些云语音功能。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="0ecc0-105">网络设置用于确定 Teams 客户端的位置，包括网络区域、网络站点、子网和受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="0ecc0-106">根据要部署的云语音功能，可以配置其中一些或所有设置。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="0ecc0-107">若要详细了解这些条款，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="0ecc0-108">在 Microsoft Teams 管理中心的"网络 **拓扑** "页上配置网络设置，或者使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="0ecc0-109">在 Microsoft Teams 管理中心配置网络设置</span><span class="sxs-lookup"><span data-stu-id="0ecc0-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="0ecc0-110">在"网络拓扑"页的"网络站点"选项卡上定义网络区域、网络站点 **和** 子网。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="0ecc0-111">在这里，可以创建或修改网络站点、将站点与网络区域关联、将子网关联到站点、启用基于位置的路由，以及向站点分配紧急策略。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="0ecc0-112">还可以添加可全局用于所有站点的网络区域。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="0ecc0-113">添加和配置网络站点</span><span class="sxs-lookup"><span data-stu-id="0ecc0-113">Add and configure a network site</span></span>

1. <span data-ttu-id="0ecc0-114">在 Microsoft Teams 管理中心的左侧导航栏中，转到"位置网络拓扑"，然后单击"网络  >  **网站"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="0ecc0-115">单击 **"** 添加"，然后输入网站的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-115">Click **Add**, and then enter a name and description for the site.</span></span>

    !["添加网络网站"页的屏幕截图](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="0ecc0-117">若要将站点与网络区域关联，请单击"添加网络区域"，选择现有区域或单击"添加"以添加区域，然后单击"链接 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ecc0-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="0ecc0-118">若要为Location-Based启用基于位置的路由， **请启用基于位置的路由**。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="0ecc0-119">若要向网站分配紧急服务策略，请执行下列一项或两项操作：</span><span class="sxs-lookup"><span data-stu-id="0ecc0-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="0ecc0-120">如果组织使用呼叫计划或已部署的电话系统直接路由，请在"紧急呼叫策略"下选择想要的策略。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="0ecc0-121">如果组织部署了电话系统直接路由，请在 **"紧急** 呼叫路由策略"下选择想要的策略。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="0ecc0-122">若要将子网关联到站点，请在 **"子网**"下单击"**添加子网"。**</span><span class="sxs-lookup"><span data-stu-id="0ecc0-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="0ecc0-123">指定 IP 版本、IP 地址、网络范围，添加说明，并单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ecc0-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="0ecc0-124">每个子网必须与特定站点相关联。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="0ecc0-125">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="0ecc0-126">修改网络站点</span><span class="sxs-lookup"><span data-stu-id="0ecc0-126">Modify a network site</span></span>

1. <span data-ttu-id="0ecc0-127">在 Microsoft Teams 管理中心的左侧导航栏中，转到"位置网络拓扑"，然后单击"网络  >  **网站"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="0ecc0-128">通过单击网站名称左侧选择网站，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ecc0-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0ecc0-129">进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ecc0-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="0ecc0-130">管理外部受信任的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="0ecc0-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="0ecc0-131">在 Microsoft Teams 管理中心的"网络拓扑"页上的"受信任的IP"选项卡上管理外部受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="0ecc0-132">可以添加无限数量的外部受信任 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="0ecc0-133">添加受信任的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="0ecc0-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="0ecc0-134">在 Microsoft Teams 管理中心的左侧导航中，转到"位置网络拓扑"，然后单击"受信任的  >  **IP"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="0ecc0-135">单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-135">Click **New**.</span></span>
3. <span data-ttu-id="0ecc0-136">在"**添加受信任的 IP 地址**"窗格中，指定 IP 版本、IP 地址、网络范围，添加说明，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ecc0-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    !["添加受信任的 IP 地址"窗格的屏幕截图](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="0ecc0-138">编辑受信任的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="0ecc0-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="0ecc0-139">在 Microsoft Teams 管理中心的左侧导航中，转到"位置网络拓扑"，然后单击"受信任的  >  **IP"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="0ecc0-140">单击 IP 地址左侧并选择该 IP 地址，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ecc0-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="0ecc0-141">在 **"编辑受信任的 IP 地址**"窗格中，进行想要的更改，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ecc0-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="0ecc0-142">使用 PowerShell 配置网络设置</span><span class="sxs-lookup"><span data-stu-id="0ecc0-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="0ecc0-143">若要完成本部分中的步骤，需要熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="0ecc0-144">若要了解有关详细信息，请参阅 [Teams PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="0ecc0-145">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="0ecc0-145">Define network regions</span></span>

 <span data-ttu-id="0ecc0-146">使用 [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet 定义网络区域。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="0ecc0-147">请注意，RegionID 参数是一个逻辑名称，表示区域地理位置，没有任何依赖关系或限制，并且 CentralSite &lt; 站点 ID &gt; 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="0ecc0-148">本示例创建一个名为"印度"的网络区域。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="0ecc0-149">另请参阅[Set-CsTenantNetworkRegion。](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)</span><span class="sxs-lookup"><span data-stu-id="0ecc0-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="0ecc0-150">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="0ecc0-150">Define network sites</span></span>

<span data-ttu-id="0ecc0-151">使用 [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet 定义网络站点。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="0ecc0-152">每个网络站点都必须与一个网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="0ecc0-153">本示例将印度区域创建两个新的网络站点，即内容网和海得拉巴。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="0ecc0-154">下表显示了本示例中定义的网络站点。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="0ecc0-155">站点 1</span><span class="sxs-lookup"><span data-stu-id="0ecc0-155">Site 1</span></span> |<span data-ttu-id="0ecc0-156">站点 2</span><span class="sxs-lookup"><span data-stu-id="0ecc0-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0ecc0-157">站点 ID</span><span class="sxs-lookup"><span data-stu-id="0ecc0-157">Site ID</span></span>    |    <span data-ttu-id="0ecc0-158">站点 1 (西) </span><span class="sxs-lookup"><span data-stu-id="0ecc0-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="0ecc0-159">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="0ecc0-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="0ecc0-160">区域 ID</span><span class="sxs-lookup"><span data-stu-id="0ecc0-160">Region ID</span></span>  |     <span data-ttu-id="0ecc0-161">印度 (区域 1) </span><span class="sxs-lookup"><span data-stu-id="0ecc0-161">Region 1 (India)</span></span>    |   <span data-ttu-id="0ecc0-162">印度区域 1 () </span><span class="sxs-lookup"><span data-stu-id="0ecc0-162">Region 1 (India)</span></span>      |

<span data-ttu-id="0ecc0-163">另请参阅[Set-CsTenantNetworkRegion。](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)</span><span class="sxs-lookup"><span data-stu-id="0ecc0-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="0ecc0-164">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="0ecc0-164">Define network subnets</span></span>

<span data-ttu-id="0ecc0-165">使用 [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet 定义网络子网并将其关联到网络站点。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="0ecc0-166">每个网络子网只能与一个站点相关联。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="0ecc0-167">本示例在子网 192.168.0.0 和 Subnet 2001：4898：e8：25：844e：926f：85ad：dd8e 与 Hyderabad 网络站点之间创建关联。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="0ecc0-168">下表显示了本示例中定义的子网。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="0ecc0-169">站点 1</span><span class="sxs-lookup"><span data-stu-id="0ecc0-169">Site 1</span></span> |<span data-ttu-id="0ecc0-170">站点 2</span><span class="sxs-lookup"><span data-stu-id="0ecc0-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0ecc0-171">子网 ID</span><span class="sxs-lookup"><span data-stu-id="0ecc0-171">Subnet ID</span></span>   |    <span data-ttu-id="0ecc0-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="0ecc0-172">192.168.0.0</span></span>     |  <span data-ttu-id="0ecc0-173">2001：4898：e8：25：844e：926f：85ad：dd8e</span><span class="sxs-lookup"><span data-stu-id="0ecc0-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="0ecc0-174">掩码</span><span class="sxs-lookup"><span data-stu-id="0ecc0-174">Mask</span></span>  |     <span data-ttu-id="0ecc0-175">24</span><span class="sxs-lookup"><span data-stu-id="0ecc0-175">24</span></span>    |   <span data-ttu-id="0ecc0-176">120</span><span class="sxs-lookup"><span data-stu-id="0ecc0-176">120</span></span>      |
|<span data-ttu-id="0ecc0-177">站点 ID</span><span class="sxs-lookup"><span data-stu-id="0ecc0-177">Site ID</span></span>  | <span data-ttu-id="0ecc0-178">Site (）) </span><span class="sxs-lookup"><span data-stu-id="0ecc0-178">Site (Delhi)</span></span> | <span data-ttu-id="0ecc0-179">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="0ecc0-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="0ecc0-180">对于多个子网，可以使用如下脚本导入 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="0ecc0-181">本示例中的 CSV 文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="0ecc0-181">In this example, the CSV file looks something like this:</span></span> 

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="0ecc0-182">另请参阅[Set-CsTenantNetworkSubnet。](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)</span><span class="sxs-lookup"><span data-stu-id="0ecc0-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="0ecc0-183">定义外部子网 (外部受信任的 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="0ecc0-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="0ecc0-184">使用 [New-CsTenantTrustedIPAddress cmdlet](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) 定义外部子网并将其分配给租户。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="0ecc0-185">可以定义无限数量的租户外部子网。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="0ecc0-186">例如：</span><span class="sxs-lookup"><span data-stu-id="0ecc0-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="0ecc0-187">另请参阅[Set-CsTenantTrustedIPAddress。](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)</span><span class="sxs-lookup"><span data-stu-id="0ecc0-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ecc0-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="0ecc0-188">Related topics</span></span>

- [<span data-ttu-id="0ecc0-189">Teams 中云语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="0ecc0-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
