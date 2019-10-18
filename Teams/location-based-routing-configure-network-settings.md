---
title: 为基于位置的路由配置网络设置
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何创建和设置用于直接路由的基于位置的路由的网络区域、站点和子网。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240bbce48452edf505a61830891d0fcd6a6d199d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570695"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="6e2c9-103">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="6e2c9-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="6e2c9-104">如果尚未执行此操作，请阅读[基于计划位置的路由，直接路由](location-based-routing-plan.md)以查看在为基于位置的路由配置网络设置之前需要执行的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="6e2c9-105">本文介绍如何为基于位置的路由配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="6e2c9-106">在组织中部署手机系统直接路由后，下一步是创建和设置网络区域、网络网站和网络子网。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="6e2c9-107">若要完成本文中的步骤，你需要熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="6e2c9-108">若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="6e2c9-109">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="6e2c9-109">Define network regions</span></span>
 <span data-ttu-id="6e2c9-110">网络区域跨多个地理区域互连网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="6e2c9-111">使用[CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet 定义网络区域。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="6e2c9-112">请注意，RegionID 参数是一个逻辑名称，表示区域的地理位置，并且没有相关性或限制，并且 CentralSite &lt;site ID&gt;参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="6e2c9-113">在此示例中，我们创建一个名为 "印度" 的网络区域。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="6e2c9-114">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="6e2c9-114">Define network sites</span></span>

<span data-ttu-id="6e2c9-115">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet 定义网络站点。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="6e2c9-116">在此示例中，我们将在印度地区创建两个新的网络站点：新德里和 Hyderabad。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="6e2c9-117">下表显示了本示例中定义的网络站点。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="6e2c9-118">站点1</span><span class="sxs-lookup"><span data-stu-id="6e2c9-118">Site 1</span></span> |<span data-ttu-id="6e2c9-119">网站2</span><span class="sxs-lookup"><span data-stu-id="6e2c9-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6e2c9-120">网站 ID</span><span class="sxs-lookup"><span data-stu-id="6e2c9-120">Site ID</span></span>    |    <span data-ttu-id="6e2c9-121">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="6e2c9-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="6e2c9-122">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="6e2c9-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="6e2c9-123">区域 ID</span><span class="sxs-lookup"><span data-stu-id="6e2c9-123">Region ID</span></span>  |     <span data-ttu-id="6e2c9-124">区域1（印度）</span><span class="sxs-lookup"><span data-stu-id="6e2c9-124">Region 1 (India)</span></span>    |   <span data-ttu-id="6e2c9-125">区域1（印度）</span><span class="sxs-lookup"><span data-stu-id="6e2c9-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="6e2c9-126">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="6e2c9-126">Define network subnets</span></span>

<span data-ttu-id="6e2c9-127">使用[CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet 定义网络子网并将其与网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="6e2c9-128">每个内部子网仅可与一个网站相关联。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="6e2c9-129">在此示例中，我们将创建子网192.168.0.0 和新德里网络站点之间以及子网2001之间的关联：4898： e8：25：844e：926f：85ad： dd8e 和 Hyderabad 网络站点。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="6e2c9-130">下表显示了在此示例中定义的子网。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="6e2c9-131">站点1</span><span class="sxs-lookup"><span data-stu-id="6e2c9-131">Site 1</span></span> |<span data-ttu-id="6e2c9-132">网站2</span><span class="sxs-lookup"><span data-stu-id="6e2c9-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6e2c9-133">子网 ID</span><span class="sxs-lookup"><span data-stu-id="6e2c9-133">Subnet ID</span></span>   |    <span data-ttu-id="6e2c9-134">含</span><span class="sxs-lookup"><span data-stu-id="6e2c9-134">192.168.0.0</span></span>     |  <span data-ttu-id="6e2c9-135">2001：4898： e8：25：844e：926f：85ad： dd8e</span><span class="sxs-lookup"><span data-stu-id="6e2c9-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="6e2c9-136">Usm</span><span class="sxs-lookup"><span data-stu-id="6e2c9-136">Mask</span></span>  |     <span data-ttu-id="6e2c9-137">全</span><span class="sxs-lookup"><span data-stu-id="6e2c9-137">24</span></span>    |   <span data-ttu-id="6e2c9-138">120</span><span class="sxs-lookup"><span data-stu-id="6e2c9-138">120</span></span>      |
|<span data-ttu-id="6e2c9-139">网站 ID</span><span class="sxs-lookup"><span data-stu-id="6e2c9-139">Site ID</span></span>  | <span data-ttu-id="6e2c9-140">站点（新德里）</span><span class="sxs-lookup"><span data-stu-id="6e2c9-140">Site (Delhi)</span></span> | <span data-ttu-id="6e2c9-141">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="6e2c9-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="6e2c9-142">对于多个子网，您可以使用如下所示的脚本导入 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="6e2c9-143">在此示例中，CSV 文件的外观如下所示：</span><span class="sxs-lookup"><span data-stu-id="6e2c9-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="6e2c9-144">定义外部子网</span><span class="sxs-lookup"><span data-stu-id="6e2c9-144">Define external subnets</span></span>
<span data-ttu-id="6e2c9-145">使用[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet 定义外部子网并将其分配给租户。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="6e2c9-146">你可以为租户定义无限数量的子网。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="6e2c9-147">例如：</span><span class="sxs-lookup"><span data-stu-id="6e2c9-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="6e2c9-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6e2c9-148">Next steps</span></span>
<span data-ttu-id="6e2c9-149">转到 "为[直接路由启用基于位置的路由](location-based-routing-enable.md)"。</span><span class="sxs-lookup"><span data-stu-id="6e2c9-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="6e2c9-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="6e2c9-150">Related topics</span></span>
- [<span data-ttu-id="6e2c9-151">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="6e2c9-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="6e2c9-152">基于位置的路由术语</span><span class="sxs-lookup"><span data-stu-id="6e2c9-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
