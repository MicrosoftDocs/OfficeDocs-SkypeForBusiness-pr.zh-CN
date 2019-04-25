---
title: 为基于位置的路由配置网络设置
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 了解如何创建和设置网络区域、 网站和子网为基于位置的路由直接路由。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60af1c90cd1dbd7855da7686950ffd135d1da5dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222360"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="bd07b-103">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="bd07b-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="bd07b-104">如果您尚未进行，请阅读[Plan Location-Based 路由直接路由中](location-based-routing-plan.md)查看您需要执行其他步骤之后，配置基于位置的路由的网络设置。</span><span class="sxs-lookup"><span data-stu-id="bd07b-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="bd07b-105">本文介绍如何配置基于位置的路由的网络设置。</span><span class="sxs-lookup"><span data-stu-id="bd07b-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="bd07b-106">在组织中部署电话系统直接路由后下, 一步步骤是创建和设置网络区域、 网络站点和网络子网。</span><span class="sxs-lookup"><span data-stu-id="bd07b-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="bd07b-107">若要完成本文中的步骤，您将需要一些熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd07b-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="bd07b-108">若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bd07b-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="bd07b-109">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="bd07b-109">Define network regions</span></span>
 <span data-ttu-id="bd07b-110">网络区域互连跨多个地理区域的网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="bd07b-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="bd07b-111">[新建 CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet 用于定义网络区域。</span><span class="sxs-lookup"><span data-stu-id="bd07b-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="bd07b-112">请注意，RegionID 参数是逻辑名称，它代表区域的地理位置和已没有依赖项或限制和 CentralSite&lt;网站 ID&gt;参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="bd07b-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="bd07b-113">本示例中，我们将创建名为印度网络区域。</span><span class="sxs-lookup"><span data-stu-id="bd07b-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="bd07b-114">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="bd07b-114">Define network sites</span></span>

<span data-ttu-id="bd07b-115">[新建 CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet 用于定义网络站点。</span><span class="sxs-lookup"><span data-stu-id="bd07b-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="bd07b-116">本示例中，我们将创建两个新网络站点，德里和海德拉巴，印度区域中。</span><span class="sxs-lookup"><span data-stu-id="bd07b-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="bd07b-117">下表显示了在此示例中定义的网络站点。</span><span class="sxs-lookup"><span data-stu-id="bd07b-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="bd07b-118">站点 1</span><span class="sxs-lookup"><span data-stu-id="bd07b-118">Site 1</span></span> |<span data-ttu-id="bd07b-119">站点 2</span><span class="sxs-lookup"><span data-stu-id="bd07b-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="bd07b-120">网站 ID</span><span class="sxs-lookup"><span data-stu-id="bd07b-120">Site ID</span></span>    |    <span data-ttu-id="bd07b-121">站点 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="bd07b-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="bd07b-122">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="bd07b-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="bd07b-123">地区 ID</span><span class="sxs-lookup"><span data-stu-id="bd07b-123">Region ID</span></span>  |     <span data-ttu-id="bd07b-124">区域 1 （印度）</span><span class="sxs-lookup"><span data-stu-id="bd07b-124">Region 1 (India)</span></span>    |   <span data-ttu-id="bd07b-125">区域 1 （印度）</span><span class="sxs-lookup"><span data-stu-id="bd07b-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="bd07b-126">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="bd07b-126">Define network subnets</span></span>

<span data-ttu-id="bd07b-127">[新建 CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet 用于定义网络子网，并将它们关联到网络站点。</span><span class="sxs-lookup"><span data-stu-id="bd07b-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="bd07b-128">每个内部子网只能与一个站点关联。</span><span class="sxs-lookup"><span data-stu-id="bd07b-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="bd07b-129">本示例中，我们将创建子网 192.168.0.0 之间德里网络站点和子网为 192.168.1.0 和海德拉巴网络站点之间的关联。</span><span class="sxs-lookup"><span data-stu-id="bd07b-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="bd07b-130">下表显示了在此示例中定义的子网。</span><span class="sxs-lookup"><span data-stu-id="bd07b-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="bd07b-131">站点 1</span><span class="sxs-lookup"><span data-stu-id="bd07b-131">Site 1</span></span> |<span data-ttu-id="bd07b-132">站点 2</span><span class="sxs-lookup"><span data-stu-id="bd07b-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="bd07b-133">子网 ID</span><span class="sxs-lookup"><span data-stu-id="bd07b-133">Subnet ID</span></span>   |    <span data-ttu-id="bd07b-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="bd07b-134">192.168.0.0</span></span>     |  <span data-ttu-id="bd07b-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="bd07b-135">192.168.1.0</span></span>     |
|<span data-ttu-id="bd07b-136">掩码</span><span class="sxs-lookup"><span data-stu-id="bd07b-136">Mask</span></span>  |     <span data-ttu-id="bd07b-137">24</span><span class="sxs-lookup"><span data-stu-id="bd07b-137">24</span></span>    |   <span data-ttu-id="bd07b-138">24</span><span class="sxs-lookup"><span data-stu-id="bd07b-138">24</span></span>      |
|<span data-ttu-id="bd07b-139">网站 ID</span><span class="sxs-lookup"><span data-stu-id="bd07b-139">Site ID</span></span>  | <span data-ttu-id="bd07b-140">网站 （德里）</span><span class="sxs-lookup"><span data-stu-id="bd07b-140">Site (Delhi)</span></span> | <span data-ttu-id="bd07b-141">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="bd07b-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="bd07b-142">对于多子网，您可以使用如下所示脚本导入 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="bd07b-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="bd07b-143">本示例中，该 CSV 文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="bd07b-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="bd07b-144">定义外部子网</span><span class="sxs-lookup"><span data-stu-id="bd07b-144">Define external subnets</span></span>
<span data-ttu-id="bd07b-145">[新建 CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet 用于定义外部子网，并将其分配到租户。</span><span class="sxs-lookup"><span data-stu-id="bd07b-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="bd07b-146">您可以定义任意的数量的子网租户。</span><span class="sxs-lookup"><span data-stu-id="bd07b-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="bd07b-147">例如：</span><span class="sxs-lookup"><span data-stu-id="bd07b-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="bd07b-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bd07b-148">Next steps</span></span>
<span data-ttu-id="bd07b-149">转到[启用直接路由基于位置的路由](location-based-routing-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="bd07b-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="bd07b-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="bd07b-150">Related topics</span></span>
- [<span data-ttu-id="bd07b-151">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="bd07b-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="bd07b-152">基于位置的路由术语</span><span class="sxs-lookup"><span data-stu-id="bd07b-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
