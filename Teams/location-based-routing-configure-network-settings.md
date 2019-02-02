---
title: 配置基于位置的路由的网络设置
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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: adb84f58c48292c13bd4af6f355f5e4da22458c9
ms.sourcegitcommit: 9f767b48e5f0eaf43869cba9c42ba3ba3225bcf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2019
ms.locfileid: "29715474"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="110d1-103">配置基于位置的路由的网络设置</span><span class="sxs-lookup"><span data-stu-id="110d1-103">Configure network settings for Location-Based Routing</span></span> 

<span data-ttu-id="110d1-104">如果您尚未进行，请阅读[Plan Location-Based 路由直接路由中](location-based-routing-plan.md)查看您需要执行其他步骤之前部署基于位置的路由的网络设置。</span><span class="sxs-lookup"><span data-stu-id="110d1-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you deploy network settings for Location-Based Routing.</span></span>

<span data-ttu-id="110d1-105">本文介绍如何配置基于位置的路由的网络设置。</span><span class="sxs-lookup"><span data-stu-id="110d1-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="110d1-106">在组织中部署电话系统直接路由后下, 一步步骤是创建和设置网络区域、 网络站点和网络子网。</span><span class="sxs-lookup"><span data-stu-id="110d1-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="110d1-107">若要完成本文中的步骤，您将需要一些熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="110d1-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="110d1-108">若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="110d1-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="110d1-109">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="110d1-109">Define network regions</span></span>
 <span data-ttu-id="110d1-110">网络区域互连跨多个地理区域的网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="110d1-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="110d1-111">使用``New-CsTenantNetworkRegion``PowerShell cmdlet 定义网络区域。</span><span class="sxs-lookup"><span data-stu-id="110d1-111">Use the ``New-CsTenantNetworkRegion`` PowerShell cmdlet to define network regions.</span></span> <span data-ttu-id="110d1-112">请注意，``RegionID``参数是一个代表区域的 geography 并且没有依赖项或限制的逻辑名称和``CentralSite <site ID>``参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="110d1-112">Note that the ``RegionID`` parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the ``CentralSite <site ID>`` parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="110d1-113">本示例中，我们将创建名为印度网络区域。</span><span class="sxs-lookup"><span data-stu-id="110d1-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="110d1-114">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="110d1-114">Define network sites</span></span>

<span data-ttu-id="110d1-115">使用``New-CsTenantNetworkSitePowerShell``PowerShell cmdlet 定义网络站点。</span><span class="sxs-lookup"><span data-stu-id="110d1-115">Use the ``New-CsTenantNetworkSitePowerShell`` PowerShell cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkRegionID <region ID>  
```
<span data-ttu-id="110d1-116">本示例中，我们将创建两个新网络站点，德里和海德拉巴，印度区域中。</span><span class="sxs-lookup"><span data-stu-id="110d1-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="110d1-117">下表显示了在此示例中定义的网络站点。</span><span class="sxs-lookup"><span data-stu-id="110d1-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="110d1-118">站点 1</span><span class="sxs-lookup"><span data-stu-id="110d1-118">Site 1</span></span> |<span data-ttu-id="110d1-119">站点 2</span><span class="sxs-lookup"><span data-stu-id="110d1-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="110d1-120">网站 ID</span><span class="sxs-lookup"><span data-stu-id="110d1-120">Site ID</span></span>    |    <span data-ttu-id="110d1-121">站点 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="110d1-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="110d1-122">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="110d1-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="110d1-123">地区 ID</span><span class="sxs-lookup"><span data-stu-id="110d1-123">Region ID</span></span>  |     <span data-ttu-id="110d1-124">区域 1 （印度）</span><span class="sxs-lookup"><span data-stu-id="110d1-124">Region 1 (India)</span></span>    |   <span data-ttu-id="110d1-125">区域 1 （印度）</span><span class="sxs-lookup"><span data-stu-id="110d1-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="110d1-126">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="110d1-126">Define network subnets</span></span>

<span data-ttu-id="110d1-127">使用``New-Cs-TenantNetworkSubnet``cmdlet，以定义网络子网，并将它们关联到网络站点。</span><span class="sxs-lookup"><span data-stu-id="110d1-127">Use the ``New-Cs-TenantNetworkSubnet`` cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="110d1-128">每个内部子网只能与一个站点关联。</span><span class="sxs-lookup"><span data-stu-id="110d1-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="110d1-129">本示例中，我们将创建子网 192.168.0.0 之间德里网络站点和子网为 192.168.1.0 和海德拉巴网络站点之间的关联。</span><span class="sxs-lookup"><span data-stu-id="110d1-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="110d1-130">下表显示了在此示例中定义的子网。</span><span class="sxs-lookup"><span data-stu-id="110d1-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="110d1-131">站点 1</span><span class="sxs-lookup"><span data-stu-id="110d1-131">Site 1</span></span> |<span data-ttu-id="110d1-132">站点 2</span><span class="sxs-lookup"><span data-stu-id="110d1-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="110d1-133">子网 ID</span><span class="sxs-lookup"><span data-stu-id="110d1-133">Subnet ID</span></span>   |    <span data-ttu-id="110d1-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="110d1-134">192.168.0.0</span></span>     |  <span data-ttu-id="110d1-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="110d1-135">192.168.1.0</span></span>     |
|<span data-ttu-id="110d1-136">掩码</span><span class="sxs-lookup"><span data-stu-id="110d1-136">Mask</span></span>  |     <span data-ttu-id="110d1-137">24</span><span class="sxs-lookup"><span data-stu-id="110d1-137">24</span></span>    |   <span data-ttu-id="110d1-138">24</span><span class="sxs-lookup"><span data-stu-id="110d1-138">24</span></span>      |
|<span data-ttu-id="110d1-139">网站 ID</span><span class="sxs-lookup"><span data-stu-id="110d1-139">Site ID</span></span>  | <span data-ttu-id="110d1-140">网站 （德里）</span><span class="sxs-lookup"><span data-stu-id="110d1-140">Site (Delhi)</span></span> | <span data-ttu-id="110d1-141">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="110d1-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="110d1-142">对于多子网，您可以使用如下所示脚本导入 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="110d1-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="110d1-143">本示例中，该 CSV 文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="110d1-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="110d1-144">定义外部子网</span><span class="sxs-lookup"><span data-stu-id="110d1-144">Define external subnets</span></span>
<span data-ttu-id="110d1-145">使用``New-Cs-TenantTrustedIPAddress``cmdlet，以定义外部子网，并将其分配到租户。</span><span class="sxs-lookup"><span data-stu-id="110d1-145">Use the ``New-Cs-TenantTrustedIPAddress`` cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="110d1-146">您可以定义任意的数量的子网租户。</span><span class="sxs-lookup"><span data-stu-id="110d1-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <Subnet IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="110d1-147">例如：</span><span class="sxs-lookup"><span data-stu-id="110d1-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 192.168.0.1 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="110d1-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="110d1-148">Next steps</span></span>
<span data-ttu-id="110d1-149">转到[启用直接路由基于位置的路由](location-based-routing-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="110d1-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="110d1-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="110d1-150">Related topics</span></span>
- [<span data-ttu-id="110d1-151">规划基于位置的路由直接路由</span><span class="sxs-lookup"><span data-stu-id="110d1-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="110d1-152">基于位置的路由术语</span><span class="sxs-lookup"><span data-stu-id="110d1-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)