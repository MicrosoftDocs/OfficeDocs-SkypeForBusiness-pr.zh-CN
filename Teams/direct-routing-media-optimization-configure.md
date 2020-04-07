---
title: 直接路由本地媒体优化
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 为直接路由配置本地媒体优化
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3097f97a856dc4e947281847c65669c23c73a408
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2020
ms.locfileid: "43157960"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="ae9e4-103">为直接路由配置本地媒体优化</span><span class="sxs-lookup"><span data-stu-id="ae9e4-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="ae9e4-104">本地媒体优化的配置基于由其他云语音功能（如基于位置的路由和动态紧急呼叫）通用的网络设置。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="ae9e4-105">若要了解有关网络区域、网络站点、网络子网和受信任的 IP 地址的详细信息，请参阅[云语音功能的网络设置](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="ae9e4-106">在配置本地媒体优化之前，请参阅[用于直接路由的本地媒体优化](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="ae9e4-107">若要配置本地媒体优化，需要执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="ae9e4-108">你可以使用团队管理员中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="ae9e4-109">有关详细信息，请参阅[管理网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="ae9e4-110">配置用户和 SBC 网站（如本文中所述）。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="ae9e4-111">将 SBCs 配置为本地媒体优化（根据 SBC 供应商的规范）。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="ae9e4-112">下图显示了本文的示例中所用的网络设置。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="ae9e4-113">![显示网络设置示例的图表](media/direct-routing-media-op-9.png "网络设置示例")</span><span class="sxs-lookup"><span data-stu-id="ae9e4-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="ae9e4-114">配置用户和 SBC 网站</span><span class="sxs-lookup"><span data-stu-id="ae9e4-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="ae9e4-115">要配置用户和 SBC 网站，你需要：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="ae9e4-116">[管理外部受信任的 IP 地址](#manage-external-trusted-ip-addresses)。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="ae9e4-117">通过配置网络区域、网络站点和网络子网来[定义网络拓扑](#define-the-network-topology)。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="ae9e4-118">通过将 SBC （s）分配给具有相关模式和代理 SBC 值的站点来[定义虚拟网络拓扑](#define-the-virtual-network-topology)。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="ae9e4-119">根据 SBC 供应商的规范，配置用于本地媒体优化的 SBC</span><span class="sxs-lookup"><span data-stu-id="ae9e4-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="ae9e4-120">本文介绍 Microsoft 组件的配置。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="ae9e4-121">有关 SBC 配置的信息，请参阅 SBC 供应商 documenation。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="ae9e4-122">以下 SBC 供应商支持本地媒体优化：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="ae9e4-123">供应商</span><span class="sxs-lookup"><span data-stu-id="ae9e4-123">Vendor</span></span> | <span data-ttu-id="ae9e4-124">产品</span><span class="sxs-lookup"><span data-stu-id="ae9e4-124">Product</span></span> |    <span data-ttu-id="ae9e4-125">软件版本</span><span class="sxs-lookup"><span data-stu-id="ae9e4-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="ae9e4-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="ae9e4-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="ae9e4-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="ae9e4-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="ae9e4-128">7.20</span><span class="sxs-lookup"><span data-stu-id="ae9e4-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="ae9e4-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="ae9e4-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="ae9e4-130">7.20</span><span class="sxs-lookup"><span data-stu-id="ae9e4-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="ae9e4-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="ae9e4-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="ae9e4-132">7.20</span><span class="sxs-lookup"><span data-stu-id="ae9e4-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="ae9e4-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="ae9e4-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="ae9e4-134">7.20</span><span class="sxs-lookup"><span data-stu-id="ae9e4-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="ae9e4-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="ae9e4-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="ae9e4-136">7.20</span><span class="sxs-lookup"><span data-stu-id="ae9e4-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="ae9e4-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="ae9e4-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="ae9e4-138">7.20</span><span class="sxs-lookup"><span data-stu-id="ae9e4-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="ae9e4-139">Mediant 虚拟版 SBC</span><span class="sxs-lookup"><span data-stu-id="ae9e4-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="ae9e4-140">7.20</span><span class="sxs-lookup"><span data-stu-id="ae9e4-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="ae9e4-141">Mediant 云版 SBC</span><span class="sxs-lookup"><span data-stu-id="ae9e4-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="ae9e4-142">7.20</span><span class="sxs-lookup"><span data-stu-id="ae9e4-142">7.20A.256</span></span> |
| [<span data-ttu-id="ae9e4-143">功能区 SBC 核心</span><span class="sxs-lookup"><span data-stu-id="ae9e4-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="ae9e4-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="ae9e4-144">SBC 5110</span></span>         | <span data-ttu-id="ae9e4-145">8.2</span><span class="sxs-lookup"><span data-stu-id="ae9e4-145">8.2</span></span>  |
|            |  <span data-ttu-id="ae9e4-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="ae9e4-146">SBC 5210</span></span>         | <span data-ttu-id="ae9e4-147">8.2</span><span class="sxs-lookup"><span data-stu-id="ae9e4-147">8.2</span></span>  |
|            |  <span data-ttu-id="ae9e4-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="ae9e4-148">SBC 5400</span></span>         | <span data-ttu-id="ae9e4-149">8.2</span><span class="sxs-lookup"><span data-stu-id="ae9e4-149">8.2</span></span>  |
|            |  <span data-ttu-id="ae9e4-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="ae9e4-150">SBC 7000</span></span>         | <span data-ttu-id="ae9e4-151">8.2</span><span class="sxs-lookup"><span data-stu-id="ae9e4-151">8.2</span></span>  |
|            |  <span data-ttu-id="ae9e4-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="ae9e4-152">SBC SWe</span></span>          | <span data-ttu-id="ae9e4-153">8.2</span><span class="sxs-lookup"><span data-stu-id="ae9e4-153">8.2</span></span>  |
| [<span data-ttu-id="ae9e4-154">功能区 SBC 边缘</span><span class="sxs-lookup"><span data-stu-id="ae9e4-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="ae9e4-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="ae9e4-155">SBC 1000</span></span>         | <span data-ttu-id="ae9e4-156">8.1.1，内部版本527</span><span class="sxs-lookup"><span data-stu-id="ae9e4-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="ae9e4-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="ae9e4-157">SBC 2000</span></span>         | <span data-ttu-id="ae9e4-158">8.1.1，内部版本527</span><span class="sxs-lookup"><span data-stu-id="ae9e4-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="ae9e4-159">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="ae9e4-159">SBC SWe Lite</span></span>     | <span data-ttu-id="ae9e4-160">8.1.0，内部版本222</span><span class="sxs-lookup"><span data-stu-id="ae9e4-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="ae9e4-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="ae9e4-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="ae9e4-162">anynode</span><span class="sxs-lookup"><span data-stu-id="ae9e4-162">anynode</span></span>          | <span data-ttu-id="ae9e4-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="ae9e4-163">4.0.1+</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="ae9e4-164">管理外部受信任的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ae9e4-164">Manage external trusted IP addresses</span></span>

<span data-ttu-id="ae9e4-165">外部受信任的 Ip 是企业网络的 Internet 外部 Ip。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-165">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="ae9e4-166">这些 IP 是 Microsoft 团队客户端连接到 Microsoft 365 时使用的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-166">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="ae9e4-167">你需要为每个具有使用本地媒体优化的用户的网站添加这些外部 Ip。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-167">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="ae9e4-168">若要为每个网站添加公共 IP 地址，请使用 CsTenantTrustedIPAddress cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-168">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="ae9e4-169">你可以为租户定义无限数量的受信任 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-169">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="ae9e4-170">如果 Microsoft 365 所看到的外部 IPs 是 IPv4 和 IPv6 地址，则需要添加这两种类型的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-170">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="ae9e4-171">对于 IPv4，请使用掩码32。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-171">For IPv4, use mask 32.</span></span> <span data-ttu-id="ae9e4-172">对于 IPv6，请使用掩码128。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-172">For IPv6, use mask 128.</span></span> <span data-ttu-id="ae9e4-173">你可以通过在 cmdlet 上指定不同的 MaskBits 来添加单个外部 IP 地址和外部 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-173">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="ae9e4-174">添加受信任的 IP 地址的示例。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-174">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="ae9e4-175">定义网络拓扑</span><span class="sxs-lookup"><span data-stu-id="ae9e4-175">Define the network topology</span></span>

<span data-ttu-id="ae9e4-176">本节介绍如何为你的网络拓扑定义网络区域、网络站点和网络子网。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-176">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="ae9e4-177">所有参数都区分大小写，因此你需要确保使用在安装过程中使用的相同大小写。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-177">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="ae9e4-178">（例如，GatewaySiteID 值 "越南" 和 "越南" 将被视为不同的网站。）</span><span class="sxs-lookup"><span data-stu-id="ae9e4-178">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="ae9e4-179">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="ae9e4-179">Define network regions</span></span>

<span data-ttu-id="ae9e4-180">若要定义网络区域，请使用 CsTenantNetworkRegion cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-180">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="ae9e4-181">RegionID 参数是一个逻辑名称，表示区域的地理位置，并且不具有依赖关系或限制。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-181">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="ae9e4-182">CentralSite <site ID>参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-182">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="ae9e4-183">下面的示例创建了一个名为 APAC 的网络区域：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-183">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="ae9e4-184">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="ae9e4-184">Define network sites</span></span>

<span data-ttu-id="ae9e4-185">若要定义网络网站，请使用 CsTenantNetworkSite cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-185">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="ae9e4-186">每个网络站点都必须与一个网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-186">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="ae9e4-187">以下示例在 APAC 区域中创建三个新的网络站点、越南、印度尼西亚和新加坡：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-187">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="ae9e4-188">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="ae9e4-188">Define network subnets</span></span>

<span data-ttu-id="ae9e4-189">若要定义网络子网并将其与网络站点关联，请使用 CsTenantNetworkSubnet cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-189">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="ae9e4-190">每个网络子网只能与一个网站相关联。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-190">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="ae9e4-191">以下示例定义了三个网络子网，并将其与三个网络站点（越南、印度尼西亚和新加坡）关联：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-191">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="ae9e4-192">定义虚拟网络拓扑</span><span class="sxs-lookup"><span data-stu-id="ae9e4-192">Define the virtual network topology</span></span> 

<span data-ttu-id="ae9e4-193">首先，租户管理员使用 CsOnlinePSTNGateway cmdlet 为每个相关 SBC 创建新的 SBC 配置。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-193">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="ae9e4-194">租户管理员通过使用 CsOnlinePSTNGateway cmdlet 指定 PSTN 网关对象的网络站点来定义虚拟网络拓扑：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-194">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="ae9e4-195">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-195">Note the following:</span></span> 
   - <span data-ttu-id="ae9e4-196">如果客户有单个 SBC，则-ProxySBC 参数必须是必需的 $null 或 SBC FQDN 值（具有集中中继方案的中心 SBC）。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-196">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="ae9e4-197">必须将-MediaBypass 参数设置为 $true，才能支持本地媒体优化。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-197">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="ae9e4-198">如果 SBC 没有-BypassMode 参数集，则不会发送 X 毫秒标头。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-198">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="ae9e4-199">所有参数都区分大小写，因此你需要确保使用的是在安装期间使用的相同大小写。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-199">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="ae9e4-200">（例如，GatewaySiteID 值 "越南" 和 "越南" 将被视为不同的网站。）</span><span class="sxs-lookup"><span data-stu-id="ae9e4-200">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="ae9e4-201">以下示例将3个 SBCs 添加到 APAC 区域中的网络站点越南、印度尼西亚和新加坡，模式始终为 "始终绕过"：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-201">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="ae9e4-202">注意：若要确保在同时配置本地媒体优化和基于位置的路由（LBR）时不间断的操作，必须通过将 GatewaySiteLbrEnabled 参数设置为每个下游 SBC $true 来为 LBR 启用下游 SBCs。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-202">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="ae9e4-203">（对于代理 SBC，此设置不是必需的。）</span><span class="sxs-lookup"><span data-stu-id="ae9e4-203">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="ae9e4-204">根据上述信息，直接路由将包括三个专用 SIP 标题到 SIP 邀请和重新邀请，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-204">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="ae9e4-205">如果定义了 BypassMode，则在邀请和重新邀请时直接路由中引入了 X-MS 标题：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-205">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="ae9e4-206">标题名称</span><span class="sxs-lookup"><span data-stu-id="ae9e4-206">Header name</span></span> | <span data-ttu-id="ae9e4-207">相对值</span><span class="sxs-lookup"><span data-stu-id="ae9e4-207">Values</span></span> | <span data-ttu-id="ae9e4-208">备注</span><span class="sxs-lookup"><span data-stu-id="ae9e4-208">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="ae9e4-209">X 毫秒-UserLocation</span><span class="sxs-lookup"><span data-stu-id="ae9e4-209">X-MS-UserLocation</span></span> | <span data-ttu-id="ae9e4-210">内部/外部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-210">internal/external</span></span> | <span data-ttu-id="ae9e4-211">指示用户是内部还是外部用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-211">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="ae9e4-212">请求 URI 邀请 sip： + 84439263000@VNsbc.contoso.com SIP/2。0</span><span class="sxs-lookup"><span data-stu-id="ae9e4-212">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="ae9e4-213">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="ae9e4-213">SBC FQDN</span></span> | <span data-ttu-id="ae9e4-214">即使 SBC 未直接连接到直接路由，仍针对呼叫的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ae9e4-214">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="ae9e4-215">X 毫秒-MediaPath</span><span class="sxs-lookup"><span data-stu-id="ae9e4-215">X-MS-MediaPath</span></span> | <span data-ttu-id="ae9e4-216">示例： proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-216">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="ae9e4-217">应用于用户和目标 SBC 之间的媒体路径的 SBCs 顺序。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-217">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="ae9e4-218">最终的 SBC 始终持续</span><span class="sxs-lookup"><span data-stu-id="ae9e4-218">The final SBC is always last</span></span> |
| <span data-ttu-id="ae9e4-219">X 毫秒-UserSite</span><span class="sxs-lookup"><span data-stu-id="ae9e4-219">X-MS-UserSite</span></span> | <span data-ttu-id="ae9e4-220">usersiteID</span><span class="sxs-lookup"><span data-stu-id="ae9e4-220">usersiteID</span></span> | <span data-ttu-id="ae9e4-221">租户管理员定义的字符串</span><span class="sxs-lookup"><span data-stu-id="ae9e4-221">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="ae9e4-222">通话流程</span><span class="sxs-lookup"><span data-stu-id="ae9e4-222">Call flows</span></span> 

<span data-ttu-id="ae9e4-223">以下显示了两种模式的通话流：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-223">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="ae9e4-224">始终绕过</span><span class="sxs-lookup"><span data-stu-id="ae9e4-224">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="ae9e4-225">仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-225">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="ae9e4-226">始终绕过模式</span><span class="sxs-lookup"><span data-stu-id="ae9e4-226">Always Bypass mode</span></span>

<span data-ttu-id="ae9e4-227">始终绕过模式是最简单的配置选项。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-227">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="ae9e4-228">租户管理员可以为所有用户和 SBCs 配置单个网站（如果所有 SBCs 均可从任何网站访问）。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-228">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="ae9e4-229">在以下情况下，示例显示 "始终绕过" 模式：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-229">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="ae9e4-230">出站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-230">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="ae9e4-231">入站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-231">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="ae9e4-232">出站呼叫和用户是外部的</span><span class="sxs-lookup"><span data-stu-id="ae9e4-232">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="ae9e4-233">入站呼叫和用户是外部的</span><span class="sxs-lookup"><span data-stu-id="ae9e4-233">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="ae9e4-234">下表显示了示例中使用的 FQDN 和 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-234">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="ae9e4-235">FQDN</span><span class="sxs-lookup"><span data-stu-id="ae9e4-235">FQDN</span></span> | <span data-ttu-id="ae9e4-236">SBC 外部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ae9e4-236">SBC external IP address</span></span> | <span data-ttu-id="ae9e4-237">SBC 内部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ae9e4-237">SBC internal IP Address</span></span> | <span data-ttu-id="ae9e4-238">内部子网</span><span class="sxs-lookup"><span data-stu-id="ae9e4-238">Internal subnet</span></span> | <span data-ttu-id="ae9e4-239">位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-239">Location</span></span> | <span data-ttu-id="ae9e4-240">外部 NAT （受信任的 IP）</span><span class="sxs-lookup"><span data-stu-id="ae9e4-240">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="ae9e4-241">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-241">VNsbc.contoso.com</span></span> | <span data-ttu-id="ae9e4-242">无</span><span class="sxs-lookup"><span data-stu-id="ae9e4-242">None</span></span> | <span data-ttu-id="ae9e4-243">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="ae9e4-243">192.168.1.5</span></span> | <span data-ttu-id="ae9e4-244">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="ae9e4-244">192.168.1.0/24</span></span> | <span data-ttu-id="ae9e4-245">越南</span><span class="sxs-lookup"><span data-stu-id="ae9e4-245">Vietnam</span></span> | <span data-ttu-id="ae9e4-246">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="ae9e4-246">172.16.240.110</span></span> |
| <span data-ttu-id="ae9e4-247">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-247">IDsbc.contoso.com</span></span> | <span data-ttu-id="ae9e4-248">无</span><span class="sxs-lookup"><span data-stu-id="ae9e4-248">None</span></span> | <span data-ttu-id="ae9e4-249">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="ae9e4-249">192.168.2.5</span></span> | <span data-ttu-id="ae9e4-250">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="ae9e4-250">192.168.2.0/24</span></span> | <span data-ttu-id="ae9e4-251">印度尼西亚</span><span class="sxs-lookup"><span data-stu-id="ae9e4-251">Indonesia</span></span> | <span data-ttu-id="ae9e4-252">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="ae9e4-252">172.16.240.120</span></span> |
| <span data-ttu-id="ae9e4-253">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-253">proxysbc.contoso.com</span></span> | <span data-ttu-id="ae9e4-254">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="ae9e4-254">172.16.240.133</span></span> | <span data-ttu-id="ae9e4-255">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="ae9e4-255">192.168.3.5</span></span> | <span data-ttu-id="ae9e4-256">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="ae9e4-256">192.168.3.0/24</span></span> | <span data-ttu-id="ae9e4-257">新加坡</span><span class="sxs-lookup"><span data-stu-id="ae9e4-257">Singapore</span></span> | <span data-ttu-id="ae9e4-258">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="ae9e4-258">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="ae9e4-259">出站呼叫，并且用户与具有始终绕过的 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-259">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="ae9e4-260">众</span><span class="sxs-lookup"><span data-stu-id="ae9e4-260">Mode</span></span> |    <span data-ttu-id="ae9e4-261">用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-261">User</span></span> |  <span data-ttu-id="ae9e4-262">位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-262">Location</span></span> |  <span data-ttu-id="ae9e4-263">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="ae9e4-263">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="ae9e4-264">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="ae9e4-264">AlwaysBypass</span></span> |    <span data-ttu-id="ae9e4-265">内部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-265">Internal</span></span> |  <span data-ttu-id="ae9e4-266">与 SBC 相同的网站</span><span class="sxs-lookup"><span data-stu-id="ae9e4-266">The same site as SBC</span></span> |  <span data-ttu-id="ae9e4-267">出站</span><span class="sxs-lookup"><span data-stu-id="ae9e4-267">Outbound</span></span> |

<span data-ttu-id="ae9e4-268">下表显示了最终用户配置和操作：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-268">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="ae9e4-269">用户物理位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-269">User physical location</span></span>| <span data-ttu-id="ae9e4-270">用户拨打或接听号码</span><span class="sxs-lookup"><span data-stu-id="ae9e4-270">User makes or receives a call to/from number</span></span> | <span data-ttu-id="ae9e4-271">用户电话号码</span><span class="sxs-lookup"><span data-stu-id="ae9e4-271">User phone number</span></span>  | <span data-ttu-id="ae9e4-272">联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="ae9e4-272">Online Voice Routing Policy</span></span> | <span data-ttu-id="ae9e4-273">针对 SBC 配置的模式</span><span class="sxs-lookup"><span data-stu-id="ae9e4-273">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="ae9e4-274">越南</span><span class="sxs-lookup"><span data-stu-id="ae9e4-274">Vietnam</span></span> | <span data-ttu-id="ae9e4-275">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="ae9e4-275">+84 4 3926 3000</span></span> | <span data-ttu-id="ae9e4-276">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="ae9e4-276">+84 4 5555 5555</span></span>   | <span data-ttu-id="ae9e4-277">优先级1： ^\+84 （\d{9}） $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-277">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="ae9e4-278">优先级2：. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-278">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="ae9e4-279">VNsbc.contoso.com-始终绕过</span><span class="sxs-lookup"><span data-stu-id="ae9e4-279">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="ae9e4-280">proxysbc.contoso.com-始终绕过</span><span class="sxs-lookup"><span data-stu-id="ae9e4-280">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="ae9e4-281">下图显示了具有 "始终绕过" 模式的出站呼叫和用户位于 SBC 所在位置的 SIP 阶梯。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-281">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="ae9e4-282">![显示出站通话的图表](media/direct-routing-media-op-10.png "拨出电话")</span><span class="sxs-lookup"><span data-stu-id="ae9e4-282">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="ae9e4-283">下表显示了直接路由发送的 X-MS 标题：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-283">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="ae9e4-284">参数</span><span class="sxs-lookup"><span data-stu-id="ae9e4-284">Parameter</span></span> | <span data-ttu-id="ae9e4-285">解释</span><span class="sxs-lookup"><span data-stu-id="ae9e4-285">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="ae9e4-286">邀请 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-286">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="ae9e4-287">在联机语音路由策略中定义的 SBC 的目标名称在请求 URI 中发送</span><span class="sxs-lookup"><span data-stu-id="ae9e4-287">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="ae9e4-288">X-MS-UserLocation：内部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-288">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="ae9e4-289">指示用户位于企业网络内的字段</span><span class="sxs-lookup"><span data-stu-id="ae9e4-289">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="ae9e4-290">X-MS-MediaPath： VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-290">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="ae9e4-291">指定客户端必须遍历到目标 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-291">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="ae9e4-292">在这种情况下，我们始终绕过，并且客户端是以标题中的唯一名称形式发送的目标名称。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-292">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="ae9e4-293">X-MS-UserSite：越南</span><span class="sxs-lookup"><span data-stu-id="ae9e4-293">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="ae9e4-294">用户所在网站内指示的字段。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-294">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="ae9e4-295">入站呼叫和用户与具有始终绕过的 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-295">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="ae9e4-296">众</span><span class="sxs-lookup"><span data-stu-id="ae9e4-296">Mode</span></span> |    <span data-ttu-id="ae9e4-297">用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-297">User</span></span> |  <span data-ttu-id="ae9e4-298">位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-298">Location</span></span> |  <span data-ttu-id="ae9e4-299">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="ae9e4-299">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="ae9e4-300">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="ae9e4-300">AlwaysBypass</span></span> |    <span data-ttu-id="ae9e4-301">内部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-301">Internal</span></span> | <span data-ttu-id="ae9e4-302">与 SBC 相同的网站</span><span class="sxs-lookup"><span data-stu-id="ae9e4-302">The same site as SBC</span></span> | <span data-ttu-id="ae9e4-303">封</span><span class="sxs-lookup"><span data-stu-id="ae9e4-303">Inbound</span></span> |


<span data-ttu-id="ae9e4-304">在入站呼叫中，用户的位置是未知的，并且 SBC 必须猜测用户所在的位置。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-304">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="ae9e4-305">如果猜测不正确，则需要重新邀请。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-305">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="ae9e4-306">这种情况假设用户是内部用户，媒体可以直接流向，不需要执行其他操作（重新邀请）。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-306">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="ae9e4-307">连接到直接路由服务的 SBC 通过提供记录-路由和联系人字段来报告发起的 SBC 位置。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-307">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="ae9e4-308">根据这些字段，媒体路径由直接路由计算。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-308">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="ae9e4-309">注意：假设用户可以有多个终结点，则不可能支持183。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-309">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="ae9e4-310">在这种情况下，直接路由将始终使用180铃声。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-310">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="ae9e4-311">下图显示了具有 AlwaysBypass 模式的入站调用中的 SIP 阶梯，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-311">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="ae9e4-313">出站呼叫和用户是具有始终绕过的外部呼叫</span><span class="sxs-lookup"><span data-stu-id="ae9e4-313">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="ae9e4-314">众</span><span class="sxs-lookup"><span data-stu-id="ae9e4-314">Mode</span></span> |    <span data-ttu-id="ae9e4-315">用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-315">User</span></span> |  <span data-ttu-id="ae9e4-316">站点</span><span class="sxs-lookup"><span data-stu-id="ae9e4-316">Site</span></span> |  <span data-ttu-id="ae9e4-317">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="ae9e4-317">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="ae9e4-318">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="ae9e4-318">AlwaysBypass</span></span> |  <span data-ttu-id="ae9e4-319">外部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-319">External</span></span> |  <span data-ttu-id="ae9e4-320">不适用</span><span class="sxs-lookup"><span data-stu-id="ae9e4-320">N/A</span></span> | <span data-ttu-id="ae9e4-321">出站</span><span class="sxs-lookup"><span data-stu-id="ae9e4-321">Outbound</span></span> |


<span data-ttu-id="ae9e4-322">下图显示了具有 AlwaysBypass 模式的出站呼叫的 SIP 阶梯，并且用户是外部的：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-322">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-12.png)

<span data-ttu-id="ae9e4-324">下表显示了直接路由服务发送的 X-MS 标头：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-324">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="ae9e4-325">参数</span><span class="sxs-lookup"><span data-stu-id="ae9e4-325">Parameter</span></span> |   <span data-ttu-id="ae9e4-326">解释</span><span class="sxs-lookup"><span data-stu-id="ae9e4-326">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="ae9e4-327">邀请 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-327">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="ae9e4-328">在联机语音路由策略中定义的 SBC 的目标名称在请求 URI 中发送。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-328">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="ae9e4-329">X-UserLocation：外部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-329">X-MS-UserLocation: external</span></span> | <span data-ttu-id="ae9e4-330">指示用户位于企业网络外部的字段。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-330">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="ae9e4-331">X-MS-MediaPath： proxysbc.contoso.com，VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="ae9e4-332">指定客户端必须遍历到目标 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-332">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="ae9e4-333">在此情况下，我们始终绕过，并且客户端是外部客户端。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-333">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="ae9e4-334">入站呼叫和用户是具有始终绕过的外部呼叫</span><span class="sxs-lookup"><span data-stu-id="ae9e4-334">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="ae9e4-335">众</span><span class="sxs-lookup"><span data-stu-id="ae9e4-335">Mode</span></span> | <span data-ttu-id="ae9e4-336">用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-336">User</span></span> | <span data-ttu-id="ae9e4-337">站点</span><span class="sxs-lookup"><span data-stu-id="ae9e4-337">Site</span></span> |  <span data-ttu-id="ae9e4-338">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="ae9e4-338">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="ae9e4-339">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="ae9e4-339">AlwaysBypass</span></span> |  <span data-ttu-id="ae9e4-340">外部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-340">External</span></span> |  <span data-ttu-id="ae9e4-341">不适用</span><span class="sxs-lookup"><span data-stu-id="ae9e4-341">N/A</span></span> |   <span data-ttu-id="ae9e4-342">封</span><span class="sxs-lookup"><span data-stu-id="ae9e4-342">Inbound</span></span> |

<span data-ttu-id="ae9e4-343">对于入站呼叫，连接到直接路由的 SBC 需要发送重新邀请（默认情况下，始终提供本地媒体候选人）（如果用户是外部的位置）。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-343">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="ae9e4-344">X-MediaPath 是基于记录路由和指定的 SBC 用户计算的。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-344">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="ae9e4-345">下图显示了具有 AlwaysBypass 模式的入站呼叫的 SIP 阶梯，并且该用户是外部用户。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-345">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="ae9e4-347">仅适用于本地用户模式</span><span class="sxs-lookup"><span data-stu-id="ae9e4-347">Only for local users mode</span></span>

<span data-ttu-id="ae9e4-348">仅当用户与 SBC 位于同一位置时，才会提供目标 SBC 的本地媒体候选项。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-348">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="ae9e4-349">在所有其他情况下，媒体将通过代理 SBC 的内部或外部 IP 进行通信。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-349">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="ae9e4-350">介绍以下方案：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-350">The following scenarios are described:</span></span>

- [<span data-ttu-id="ae9e4-351">出站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-351">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="ae9e4-352">入站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-352">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="ae9e4-353">用户与 SBC 不在同一位置，但位于企业网络中</span><span class="sxs-lookup"><span data-stu-id="ae9e4-353">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="ae9e4-354">入站呼叫和用户是内部的，但与 SBC 不在同一位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-354">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="ae9e4-355">下表显示最终用户配置和操作：</span><span class="sxs-lookup"><span data-stu-id="ae9e4-355">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="ae9e4-356">用户物理位置</span><span class="sxs-lookup"><span data-stu-id="ae9e4-356">User physical location</span></span> |  <span data-ttu-id="ae9e4-357">用户拨打或接听号码</span><span class="sxs-lookup"><span data-stu-id="ae9e4-357">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="ae9e4-358">用户电话号码</span><span class="sxs-lookup"><span data-stu-id="ae9e4-358">User phone number</span></span> | <span data-ttu-id="ae9e4-359">联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="ae9e4-359">Online Voice Routing Policy</span></span> |   <span data-ttu-id="ae9e4-360">针对 SBC 配置的模式</span><span class="sxs-lookup"><span data-stu-id="ae9e4-360">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="ae9e4-361">越南</span><span class="sxs-lookup"><span data-stu-id="ae9e4-361">Vietnam</span></span> | <span data-ttu-id="ae9e4-362">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="ae9e4-362">+84 4 3926  3000</span></span> |  <span data-ttu-id="ae9e4-363">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="ae9e4-363">+84 4 5555 5555</span></span> | <span data-ttu-id="ae9e4-364">优先级1： ^\+84 （\d{9}） $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-364">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="ae9e4-365">优先级2：. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ae9e4-365">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="ae9e4-366">VNsbc.contoso.com-OnlyForLocalUsers Proxysbc.contoso.com-始终绕过</span><span class="sxs-lookup"><span data-stu-id="ae9e4-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="ae9e4-367">出站呼叫和用户与 SBC 在同一位置，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-367">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="ae9e4-368">众</span><span class="sxs-lookup"><span data-stu-id="ae9e4-368">Mode</span></span> | <span data-ttu-id="ae9e4-369">用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-369">User</span></span> | <span data-ttu-id="ae9e4-370">站点</span><span class="sxs-lookup"><span data-stu-id="ae9e4-370">Site</span></span> | <span data-ttu-id="ae9e4-371">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="ae9e4-371">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="ae9e4-372">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="ae9e4-372">OnlyForLocalUsers</span></span> |   <span data-ttu-id="ae9e4-373">内部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-373">Internal</span></span> |<span data-ttu-id="ae9e4-374">与 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="ae9e4-374">Same as SBC</span></span>   | <span data-ttu-id="ae9e4-375">出站</span><span class="sxs-lookup"><span data-stu-id="ae9e4-375">Outbound</span></span> |

<span data-ttu-id="ae9e4-376">下图显示了具有 OnlyForLocalUsers 模式的出站调用，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-376">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="ae9e4-377">这是[当用户与 SBC 位于同一位置时，在出站呼叫](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)中显示的相同流。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-377">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="ae9e4-379">入站呼叫和用户与 SBC 在同一位置，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-379">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="ae9e4-380">众</span><span class="sxs-lookup"><span data-stu-id="ae9e4-380">Mode</span></span> | <span data-ttu-id="ae9e4-381">用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-381">User</span></span> | <span data-ttu-id="ae9e4-382">站点</span><span class="sxs-lookup"><span data-stu-id="ae9e4-382">Site</span></span> | <span data-ttu-id="ae9e4-383">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="ae9e4-383">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="ae9e4-384">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="ae9e4-384">OnlyForLocalUsers</span></span> |   <span data-ttu-id="ae9e4-385">内部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-385">Internal</span></span> | <span data-ttu-id="ae9e4-386">与 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="ae9e4-386">Same as SBC</span></span> | <span data-ttu-id="ae9e4-387">封</span><span class="sxs-lookup"><span data-stu-id="ae9e4-387">Inbound</span></span> |

<span data-ttu-id="ae9e4-388">下图显示了具有 OnlyForLocalUsers 模式的入站调用，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-388">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="ae9e4-389">[当用户与 SBC 位于同一位置时](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)，这是与入站通话中所示相同的流。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-389">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="ae9e4-391">用户与 SBC 不在同一位置，但位于企业网络中，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-391">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="ae9e4-392">众</span><span class="sxs-lookup"><span data-stu-id="ae9e4-392">Mode</span></span> | <span data-ttu-id="ae9e4-393">用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-393">User</span></span> | <span data-ttu-id="ae9e4-394">站点</span><span class="sxs-lookup"><span data-stu-id="ae9e4-394">Site</span></span> |<span data-ttu-id="ae9e4-395">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="ae9e4-395">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="ae9e4-396">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="ae9e4-396">OnlyForLocalUsers</span></span>  | <span data-ttu-id="ae9e4-397">内部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-397">Internal</span></span> |   <span data-ttu-id="ae9e4-398">与 SBC 不同</span><span class="sxs-lookup"><span data-stu-id="ae9e4-398">Different from SBC</span></span> | <span data-ttu-id="ae9e4-399">出站</span><span class="sxs-lookup"><span data-stu-id="ae9e4-399">Outbound</span></span> |

<span data-ttu-id="ae9e4-400">直接路由基于在 SBC 上配置的用户和模式的已报告位置计算 X MediaPath。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-400">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="ae9e4-401">下图显示了具有 OnlyForLocalUsers 模式的出站呼叫，以及与 SBC 不在同一位置的内部用户。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-401">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="ae9e4-403">入站呼叫和用户是内部的，但与 SBC 不在同一位置，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-403">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="ae9e4-404">众</span><span class="sxs-lookup"><span data-stu-id="ae9e4-404">Mode</span></span> |    <span data-ttu-id="ae9e4-405">用户</span><span class="sxs-lookup"><span data-stu-id="ae9e4-405">User</span></span> |  <span data-ttu-id="ae9e4-406">站点</span><span class="sxs-lookup"><span data-stu-id="ae9e4-406">Site</span></span> |  <span data-ttu-id="ae9e4-407">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="ae9e4-407">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="ae9e4-408">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="ae9e4-408">OnlyForLocalUsers</span></span> | <span data-ttu-id="ae9e4-409">内部</span><span class="sxs-lookup"><span data-stu-id="ae9e4-409">Internal</span></span> |    <span data-ttu-id="ae9e4-410">与 SBC 不同</span><span class="sxs-lookup"><span data-stu-id="ae9e4-410">Different from SBC</span></span> |    <span data-ttu-id="ae9e4-411">封</span><span class="sxs-lookup"><span data-stu-id="ae9e4-411">Inbound</span></span> |

<span data-ttu-id="ae9e4-412">下图显示了具有 OnlyForLocalUsers 模式的入站呼叫，以及与 SBC 不在同一位置的内部用户。</span><span class="sxs-lookup"><span data-stu-id="ae9e4-412">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-17.png)









