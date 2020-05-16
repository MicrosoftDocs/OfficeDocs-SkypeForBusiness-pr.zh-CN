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
ms.openlocfilehash: c3da3cf243b24d0f614c05e9d09eb68796a68545
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256487"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="84850-103">为直接路由配置本地媒体优化</span><span class="sxs-lookup"><span data-stu-id="84850-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="84850-104">本地媒体优化的配置基于由其他云语音功能（如基于位置的路由和动态紧急呼叫）通用的网络设置。</span><span class="sxs-lookup"><span data-stu-id="84850-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="84850-105">若要了解有关网络区域、网络站点、网络子网和受信任的 IP 地址的详细信息，请参阅[云语音功能的网络设置](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="84850-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="84850-106">在配置本地媒体优化之前，请参阅[用于直接路由的本地媒体优化](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="84850-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="84850-107">若要配置本地媒体优化，需要执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="84850-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="84850-108">你可以使用团队管理员中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="84850-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="84850-109">有关详细信息，请参阅[管理网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="84850-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="84850-110">配置用户和 SBC 网站（如本文中所述）。</span><span class="sxs-lookup"><span data-stu-id="84850-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="84850-111">将 SBCs 配置为本地媒体优化（根据 SBC 供应商的规范）。</span><span class="sxs-lookup"><span data-stu-id="84850-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="84850-112">下图显示了本文的示例中所用的网络设置。</span><span class="sxs-lookup"><span data-stu-id="84850-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="84850-113">![显示网络设置示例的图表](media/direct-routing-media-op-9.png "网络设置示例")</span><span class="sxs-lookup"><span data-stu-id="84850-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="84850-114">配置用户和 SBC 网站</span><span class="sxs-lookup"><span data-stu-id="84850-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="84850-115">要配置用户和 SBC 网站，你需要：</span><span class="sxs-lookup"><span data-stu-id="84850-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="84850-116">[管理外部受信任的 IP 地址](#manage-external-trusted-ip-addresses)。</span><span class="sxs-lookup"><span data-stu-id="84850-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="84850-117">通过配置网络区域、网络站点和网络子网来[定义网络拓扑](#define-the-network-topology)。</span><span class="sxs-lookup"><span data-stu-id="84850-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="84850-118">通过将 SBC （s）分配给具有相关模式和代理 SBC 值的站点来[定义虚拟网络拓扑](#define-the-virtual-network-topology)。</span><span class="sxs-lookup"><span data-stu-id="84850-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="84850-119">根据 SBC 供应商的规范，配置用于本地媒体优化的 SBC</span><span class="sxs-lookup"><span data-stu-id="84850-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="84850-120">本文介绍 Microsoft 组件的配置。</span><span class="sxs-lookup"><span data-stu-id="84850-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="84850-121">有关 SBC 配置的信息，请参阅 SBC 供应商的文档。</span><span class="sxs-lookup"><span data-stu-id="84850-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="84850-122">以下 SBC 供应商支持本地媒体优化：</span><span class="sxs-lookup"><span data-stu-id="84850-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="84850-123">供应商</span><span class="sxs-lookup"><span data-stu-id="84850-123">Vendor</span></span> | <span data-ttu-id="84850-124">产品</span><span class="sxs-lookup"><span data-stu-id="84850-124">Product</span></span> |    <span data-ttu-id="84850-125">软件版本</span><span class="sxs-lookup"><span data-stu-id="84850-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="84850-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="84850-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="84850-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="84850-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="84850-128">7.20</span><span class="sxs-lookup"><span data-stu-id="84850-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="84850-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="84850-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="84850-130">7.20</span><span class="sxs-lookup"><span data-stu-id="84850-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="84850-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="84850-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="84850-132">7.20</span><span class="sxs-lookup"><span data-stu-id="84850-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="84850-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="84850-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="84850-134">7.20</span><span class="sxs-lookup"><span data-stu-id="84850-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="84850-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="84850-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="84850-136">7.20</span><span class="sxs-lookup"><span data-stu-id="84850-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="84850-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="84850-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="84850-138">7.20</span><span class="sxs-lookup"><span data-stu-id="84850-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="84850-139">Mediant 虚拟版 SBC</span><span class="sxs-lookup"><span data-stu-id="84850-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="84850-140">7.20</span><span class="sxs-lookup"><span data-stu-id="84850-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="84850-141">Mediant 云版 SBC</span><span class="sxs-lookup"><span data-stu-id="84850-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="84850-142">7.20</span><span class="sxs-lookup"><span data-stu-id="84850-142">7.20A.256</span></span> |
| [<span data-ttu-id="84850-143">功能区 SBC 核心</span><span class="sxs-lookup"><span data-stu-id="84850-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="84850-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="84850-144">SBC 5110</span></span>         | <span data-ttu-id="84850-145">8.2</span><span class="sxs-lookup"><span data-stu-id="84850-145">8.2</span></span>  |
|            |  <span data-ttu-id="84850-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="84850-146">SBC 5210</span></span>         | <span data-ttu-id="84850-147">8.2</span><span class="sxs-lookup"><span data-stu-id="84850-147">8.2</span></span>  |
|            |  <span data-ttu-id="84850-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="84850-148">SBC 5400</span></span>         | <span data-ttu-id="84850-149">8.2</span><span class="sxs-lookup"><span data-stu-id="84850-149">8.2</span></span>  |
|            |  <span data-ttu-id="84850-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="84850-150">SBC 7000</span></span>         | <span data-ttu-id="84850-151">8.2</span><span class="sxs-lookup"><span data-stu-id="84850-151">8.2</span></span>  |
|            |  <span data-ttu-id="84850-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="84850-152">SBC SWe</span></span>          | <span data-ttu-id="84850-153">8.2</span><span class="sxs-lookup"><span data-stu-id="84850-153">8.2</span></span>  |
| [<span data-ttu-id="84850-154">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="84850-154">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="84850-155">anynode</span><span class="sxs-lookup"><span data-stu-id="84850-155">anynode</span></span>          | <span data-ttu-id="84850-156">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="84850-156">4.0.1+</span></span> |
| [<span data-ttu-id="84850-157">Oracle</span><span class="sxs-lookup"><span data-stu-id="84850-157">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="84850-158">AP 1100</span><span class="sxs-lookup"><span data-stu-id="84850-158">AP 1100</span></span> | <span data-ttu-id="84850-159">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="84850-159">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="84850-160">AP 3900</span><span class="sxs-lookup"><span data-stu-id="84850-160">AP 3900</span></span> | <span data-ttu-id="84850-161">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="84850-161">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="84850-162">AP 4600</span><span class="sxs-lookup"><span data-stu-id="84850-162">AP 4600</span></span> | <span data-ttu-id="84850-163">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="84850-163">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="84850-164">AP 6300</span><span class="sxs-lookup"><span data-stu-id="84850-164">AP 6300</span></span> | <span data-ttu-id="84850-165">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="84850-165">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="84850-166">AP 6350</span><span class="sxs-lookup"><span data-stu-id="84850-166">AP 6350</span></span> | <span data-ttu-id="84850-167">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="84850-167">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="84850-168">VME</span><span class="sxs-lookup"><span data-stu-id="84850-168">VME</span></span>     | <span data-ttu-id="84850-169">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="84850-169">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="84850-170">管理外部受信任的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="84850-170">Manage external trusted IP addresses</span></span>

<span data-ttu-id="84850-171">外部受信任的 Ip 是企业网络的 Internet 外部 Ip。</span><span class="sxs-lookup"><span data-stu-id="84850-171">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="84850-172">这些 IP 是 Microsoft 团队客户端连接到 Microsoft 365 时使用的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="84850-172">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="84850-173">你需要为每个具有使用本地媒体优化的用户的网站添加这些外部 Ip。</span><span class="sxs-lookup"><span data-stu-id="84850-173">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="84850-174">若要为每个网站添加公共 IP 地址，请使用 CsTenantTrustedIPAddress cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84850-174">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="84850-175">你可以为租户定义无限数量的受信任 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="84850-175">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="84850-176">如果 Microsoft 365 所看到的外部 IPs 是 IPv4 和 IPv6 地址，则需要添加这两种类型的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="84850-176">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="84850-177">对于 IPv4，请使用掩码32。</span><span class="sxs-lookup"><span data-stu-id="84850-177">For IPv4, use mask 32.</span></span> <span data-ttu-id="84850-178">对于 IPv6，请使用掩码128。</span><span class="sxs-lookup"><span data-stu-id="84850-178">For IPv6, use mask 128.</span></span> <span data-ttu-id="84850-179">你可以通过在 cmdlet 上指定不同的 MaskBits 来添加单个外部 IP 地址和外部 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="84850-179">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="84850-180">添加受信任的 IP 地址的示例。</span><span class="sxs-lookup"><span data-stu-id="84850-180">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="84850-181">定义网络拓扑</span><span class="sxs-lookup"><span data-stu-id="84850-181">Define the network topology</span></span>

<span data-ttu-id="84850-182">本节介绍如何为你的网络拓扑定义网络区域、网络站点和网络子网。</span><span class="sxs-lookup"><span data-stu-id="84850-182">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="84850-183">所有参数都区分大小写，因此你需要确保使用在安装过程中使用的相同大小写。</span><span class="sxs-lookup"><span data-stu-id="84850-183">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="84850-184">（例如，GatewaySiteID 值 "越南" 和 "越南" 将被视为不同的网站。）</span><span class="sxs-lookup"><span data-stu-id="84850-184">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="84850-185">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="84850-185">Define network regions</span></span>

<span data-ttu-id="84850-186">若要定义网络区域，请使用 CsTenantNetworkRegion cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84850-186">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="84850-187">RegionID 参数是一个逻辑名称，表示区域的地理位置，并且不具有依赖关系或限制。</span><span class="sxs-lookup"><span data-stu-id="84850-187">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="84850-188">CentralSite <site ID> 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="84850-188">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="84850-189">下面的示例创建了一个名为 APAC 的网络区域：</span><span class="sxs-lookup"><span data-stu-id="84850-189">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="84850-190">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="84850-190">Define network sites</span></span>

<span data-ttu-id="84850-191">若要定义网络网站，请使用 CsTenantNetworkSite cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84850-191">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="84850-192">每个网络站点都必须与一个网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="84850-192">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="84850-193">以下示例在 APAC 区域中创建三个新的网络站点、越南、印度尼西亚和新加坡：</span><span class="sxs-lookup"><span data-stu-id="84850-193">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="84850-194">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="84850-194">Define network subnets</span></span>

<span data-ttu-id="84850-195">若要定义网络子网并将其与网络站点关联，请使用 CsTenantNetworkSubnet cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84850-195">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="84850-196">每个网络子网只能与一个网站相关联。</span><span class="sxs-lookup"><span data-stu-id="84850-196">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="84850-197">以下示例定义了三个网络子网，并将其与三个网络站点（越南、印度尼西亚和新加坡）关联：</span><span class="sxs-lookup"><span data-stu-id="84850-197">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="84850-198">定义虚拟网络拓扑</span><span class="sxs-lookup"><span data-stu-id="84850-198">Define the virtual network topology</span></span> 

<span data-ttu-id="84850-199">首先，租户管理员使用 CsOnlinePSTNGateway cmdlet 为每个相关 SBC 创建新的 SBC 配置。</span><span class="sxs-lookup"><span data-stu-id="84850-199">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="84850-200">租户管理员通过使用 CsOnlinePSTNGateway cmdlet 指定 PSTN 网关对象的网络站点来定义虚拟网络拓扑：</span><span class="sxs-lookup"><span data-stu-id="84850-200">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="84850-201">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="84850-201">Note the following:</span></span> 
   - <span data-ttu-id="84850-202">如果客户有单个 SBC，则-ProxySBC 参数必须是必需的 $null 或 SBC FQDN 值（具有集中中继方案的中心 SBC）。</span><span class="sxs-lookup"><span data-stu-id="84850-202">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="84850-203">必须将-MediaBypass 参数设置为 $true，才能支持本地媒体优化。</span><span class="sxs-lookup"><span data-stu-id="84850-203">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="84850-204">如果 SBC 没有-BypassMode 参数集，则不会发送 X 毫秒标头。</span><span class="sxs-lookup"><span data-stu-id="84850-204">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="84850-205">所有参数都区分大小写，因此你需要确保使用的是在安装期间使用的相同大小写。</span><span class="sxs-lookup"><span data-stu-id="84850-205">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="84850-206">（例如，GatewaySiteID 值 "越南" 和 "越南" 将被视为不同的网站。）</span><span class="sxs-lookup"><span data-stu-id="84850-206">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="84850-207">以下示例将3个 SBCs 添加到 APAC 区域中的网络站点越南、印度尼西亚和新加坡，模式始终为 "始终绕过"：</span><span class="sxs-lookup"><span data-stu-id="84850-207">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="84850-208">注意：若要确保在同时配置本地媒体优化和基于位置的路由（LBR）时不间断的操作，必须通过将 GatewaySiteLbrEnabled 参数设置为每个下游 SBC $true 来为 LBR 启用下游 SBCs。</span><span class="sxs-lookup"><span data-stu-id="84850-208">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="84850-209">（对于代理 SBC，此设置不是必需的。）</span><span class="sxs-lookup"><span data-stu-id="84850-209">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="84850-210">根据上述信息，直接路由将包括三个专用 SIP 标题到 SIP 邀请和重新邀请，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="84850-210">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="84850-211">如果定义了 BypassMode，则在邀请和重新邀请时直接路由中引入了 X-MS 标题：</span><span class="sxs-lookup"><span data-stu-id="84850-211">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="84850-212">标题名称</span><span class="sxs-lookup"><span data-stu-id="84850-212">Header name</span></span> | <span data-ttu-id="84850-213">相对值</span><span class="sxs-lookup"><span data-stu-id="84850-213">Values</span></span> | <span data-ttu-id="84850-214">备注</span><span class="sxs-lookup"><span data-stu-id="84850-214">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="84850-215">X 毫秒-UserLocation</span><span class="sxs-lookup"><span data-stu-id="84850-215">X-MS-UserLocation</span></span> | <span data-ttu-id="84850-216">内部/外部</span><span class="sxs-lookup"><span data-stu-id="84850-216">internal/external</span></span> | <span data-ttu-id="84850-217">指示用户是内部还是外部用户</span><span class="sxs-lookup"><span data-stu-id="84850-217">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="84850-218">请求 URI 邀请 sip： + 84439263000@VNsbc.contoso.com SIP/2。0</span><span class="sxs-lookup"><span data-stu-id="84850-218">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="84850-219">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="84850-219">SBC FQDN</span></span> | <span data-ttu-id="84850-220">即使 SBC 未直接连接到直接路由，仍针对呼叫的 FQDN</span><span class="sxs-lookup"><span data-stu-id="84850-220">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="84850-221">X 毫秒-MediaPath</span><span class="sxs-lookup"><span data-stu-id="84850-221">X-MS-MediaPath</span></span> | <span data-ttu-id="84850-222">示例： proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-222">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="84850-223">应用于用户和目标 SBC 之间的媒体路径的 SBCs 顺序。</span><span class="sxs-lookup"><span data-stu-id="84850-223">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="84850-224">最终的 SBC 始终持续</span><span class="sxs-lookup"><span data-stu-id="84850-224">The final SBC is always last</span></span> |
| <span data-ttu-id="84850-225">X 毫秒-UserSite</span><span class="sxs-lookup"><span data-stu-id="84850-225">X-MS-UserSite</span></span> | <span data-ttu-id="84850-226">usersiteID</span><span class="sxs-lookup"><span data-stu-id="84850-226">usersiteID</span></span> | <span data-ttu-id="84850-227">租户管理员定义的字符串</span><span class="sxs-lookup"><span data-stu-id="84850-227">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="84850-228">通话流程</span><span class="sxs-lookup"><span data-stu-id="84850-228">Call flows</span></span> 

<span data-ttu-id="84850-229">以下显示了两种模式的通话流：</span><span class="sxs-lookup"><span data-stu-id="84850-229">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="84850-230">始终绕过</span><span class="sxs-lookup"><span data-stu-id="84850-230">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="84850-231">仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="84850-231">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="84850-232">始终绕过模式</span><span class="sxs-lookup"><span data-stu-id="84850-232">Always Bypass mode</span></span>

<span data-ttu-id="84850-233">始终绕过模式是最简单的配置选项。</span><span class="sxs-lookup"><span data-stu-id="84850-233">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="84850-234">租户管理员可以为所有用户和 SBCs 配置单个网站（如果所有 SBCs 均可从任何网站访问）。</span><span class="sxs-lookup"><span data-stu-id="84850-234">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="84850-235">在以下情况下，示例显示 "始终绕过" 模式：</span><span class="sxs-lookup"><span data-stu-id="84850-235">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="84850-236">出站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="84850-236">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="84850-237">入站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="84850-237">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="84850-238">出站呼叫和用户是外部的</span><span class="sxs-lookup"><span data-stu-id="84850-238">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="84850-239">入站呼叫和用户是外部的</span><span class="sxs-lookup"><span data-stu-id="84850-239">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="84850-240">下表显示了示例中使用的 FQDN 和 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="84850-240">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="84850-241">FQDN</span><span class="sxs-lookup"><span data-stu-id="84850-241">FQDN</span></span> | <span data-ttu-id="84850-242">SBC 外部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="84850-242">SBC external IP address</span></span> | <span data-ttu-id="84850-243">SBC 内部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="84850-243">SBC internal IP Address</span></span> | <span data-ttu-id="84850-244">内部子网</span><span class="sxs-lookup"><span data-stu-id="84850-244">Internal subnet</span></span> | <span data-ttu-id="84850-245">位置</span><span class="sxs-lookup"><span data-stu-id="84850-245">Location</span></span> | <span data-ttu-id="84850-246">外部 NAT （受信任的 IP）</span><span class="sxs-lookup"><span data-stu-id="84850-246">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="84850-247">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-247">VNsbc.contoso.com</span></span> | <span data-ttu-id="84850-248">无</span><span class="sxs-lookup"><span data-stu-id="84850-248">None</span></span> | <span data-ttu-id="84850-249">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="84850-249">192.168.1.5</span></span> | <span data-ttu-id="84850-250">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="84850-250">192.168.1.0/24</span></span> | <span data-ttu-id="84850-251">越南</span><span class="sxs-lookup"><span data-stu-id="84850-251">Vietnam</span></span> | <span data-ttu-id="84850-252">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="84850-252">172.16.240.110</span></span> |
| <span data-ttu-id="84850-253">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-253">IDsbc.contoso.com</span></span> | <span data-ttu-id="84850-254">无</span><span class="sxs-lookup"><span data-stu-id="84850-254">None</span></span> | <span data-ttu-id="84850-255">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="84850-255">192.168.2.5</span></span> | <span data-ttu-id="84850-256">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="84850-256">192.168.2.0/24</span></span> | <span data-ttu-id="84850-257">印度尼西亚</span><span class="sxs-lookup"><span data-stu-id="84850-257">Indonesia</span></span> | <span data-ttu-id="84850-258">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="84850-258">172.16.240.120</span></span> |
| <span data-ttu-id="84850-259">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-259">proxysbc.contoso.com</span></span> | <span data-ttu-id="84850-260">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="84850-260">172.16.240.133</span></span> | <span data-ttu-id="84850-261">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="84850-261">192.168.3.5</span></span> | <span data-ttu-id="84850-262">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="84850-262">192.168.3.0/24</span></span> | <span data-ttu-id="84850-263">新加坡</span><span class="sxs-lookup"><span data-stu-id="84850-263">Singapore</span></span> | <span data-ttu-id="84850-264">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="84850-264">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="84850-265">出站呼叫，并且用户与具有始终绕过的 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="84850-265">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="84850-266">众</span><span class="sxs-lookup"><span data-stu-id="84850-266">Mode</span></span> |    <span data-ttu-id="84850-267">用户</span><span class="sxs-lookup"><span data-stu-id="84850-267">User</span></span> |  <span data-ttu-id="84850-268">位置</span><span class="sxs-lookup"><span data-stu-id="84850-268">Location</span></span> |  <span data-ttu-id="84850-269">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="84850-269">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="84850-270">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="84850-270">AlwaysBypass</span></span> |    <span data-ttu-id="84850-271">内部</span><span class="sxs-lookup"><span data-stu-id="84850-271">Internal</span></span> |  <span data-ttu-id="84850-272">与 SBC 相同的网站</span><span class="sxs-lookup"><span data-stu-id="84850-272">The same site as SBC</span></span> |  <span data-ttu-id="84850-273">出站</span><span class="sxs-lookup"><span data-stu-id="84850-273">Outbound</span></span> |

<span data-ttu-id="84850-274">下表显示了最终用户配置和操作：</span><span class="sxs-lookup"><span data-stu-id="84850-274">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="84850-275">用户物理位置</span><span class="sxs-lookup"><span data-stu-id="84850-275">User physical location</span></span>| <span data-ttu-id="84850-276">用户拨打或接听号码</span><span class="sxs-lookup"><span data-stu-id="84850-276">User makes or receives a call to/from number</span></span> | <span data-ttu-id="84850-277">用户电话号码</span><span class="sxs-lookup"><span data-stu-id="84850-277">User phone number</span></span>  | <span data-ttu-id="84850-278">联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="84850-278">Online Voice Routing Policy</span></span> | <span data-ttu-id="84850-279">针对 SBC 配置的模式</span><span class="sxs-lookup"><span data-stu-id="84850-279">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="84850-280">越南</span><span class="sxs-lookup"><span data-stu-id="84850-280">Vietnam</span></span> | <span data-ttu-id="84850-281">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="84850-281">+84 4 3926 3000</span></span> | <span data-ttu-id="84850-282">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="84850-282">+84 4 5555 5555</span></span>   | <span data-ttu-id="84850-283">优先级1： ^ \+ 84 （\d {9} ） $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-283">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="84850-284">优先级2：. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-284">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="84850-285">VNsbc.contoso.com-始终绕过</span><span class="sxs-lookup"><span data-stu-id="84850-285">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="84850-286">proxysbc.contoso.com-始终绕过</span><span class="sxs-lookup"><span data-stu-id="84850-286">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="84850-287">下图显示了具有 "始终绕过" 模式的出站呼叫和用户位于 SBC 所在位置的 SIP 阶梯。</span><span class="sxs-lookup"><span data-stu-id="84850-287">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="84850-288">![显示出站通话的图表](media/direct-routing-media-op-10.png "拨出电话")</span><span class="sxs-lookup"><span data-stu-id="84850-288">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="84850-289">下表显示了直接路由发送的 X-MS 标题：</span><span class="sxs-lookup"><span data-stu-id="84850-289">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="84850-290">参数</span><span class="sxs-lookup"><span data-stu-id="84850-290">Parameter</span></span> | <span data-ttu-id="84850-291">解释</span><span class="sxs-lookup"><span data-stu-id="84850-291">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="84850-292">邀请 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-292">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="84850-293">在联机语音路由策略中定义的 SBC 的目标 FQDN 在请求 URI 中发送</span><span class="sxs-lookup"><span data-stu-id="84850-293">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="84850-294">X-MS-UserLocation：内部</span><span class="sxs-lookup"><span data-stu-id="84850-294">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="84850-295">指示用户位于企业网络内的字段</span><span class="sxs-lookup"><span data-stu-id="84850-295">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="84850-296">X-MS-MediaPath： VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-296">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="84850-297">指定客户端必须遍历到目标 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="84850-297">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="84850-298">在这种情况下，我们始终绕过，并且客户端是以标题中的唯一名称形式发送的目标名称。</span><span class="sxs-lookup"><span data-stu-id="84850-298">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="84850-299">X-MS-UserSite：越南</span><span class="sxs-lookup"><span data-stu-id="84850-299">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="84850-300">用户所在网站内指示的字段。</span><span class="sxs-lookup"><span data-stu-id="84850-300">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="84850-301">入站呼叫和用户与具有始终绕过的 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="84850-301">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="84850-302">众</span><span class="sxs-lookup"><span data-stu-id="84850-302">Mode</span></span> |    <span data-ttu-id="84850-303">用户</span><span class="sxs-lookup"><span data-stu-id="84850-303">User</span></span> |  <span data-ttu-id="84850-304">位置</span><span class="sxs-lookup"><span data-stu-id="84850-304">Location</span></span> |  <span data-ttu-id="84850-305">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="84850-305">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="84850-306">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="84850-306">AlwaysBypass</span></span> |    <span data-ttu-id="84850-307">内部</span><span class="sxs-lookup"><span data-stu-id="84850-307">Internal</span></span> | <span data-ttu-id="84850-308">与 SBC 相同的网站</span><span class="sxs-lookup"><span data-stu-id="84850-308">The same site as SBC</span></span> | <span data-ttu-id="84850-309">封</span><span class="sxs-lookup"><span data-stu-id="84850-309">Inbound</span></span> |


<span data-ttu-id="84850-310">在入站呼叫中，用户的位置是未知的，并且 SBC 必须猜测用户所在的位置。</span><span class="sxs-lookup"><span data-stu-id="84850-310">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="84850-311">如果猜测不正确，则需要重新邀请。</span><span class="sxs-lookup"><span data-stu-id="84850-311">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="84850-312">这种情况假设用户是内部用户，媒体可以直接流向，不需要执行其他操作（重新邀请）。</span><span class="sxs-lookup"><span data-stu-id="84850-312">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="84850-313">连接到直接路由服务的 SBC 通过提供记录-路由和联系人字段来报告发起的 SBC 位置。</span><span class="sxs-lookup"><span data-stu-id="84850-313">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="84850-314">根据这些字段，媒体路径由直接路由计算。</span><span class="sxs-lookup"><span data-stu-id="84850-314">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="84850-315">注意：假设用户可以有多个终结点，则不可能支持183。</span><span class="sxs-lookup"><span data-stu-id="84850-315">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="84850-316">在这种情况下，直接路由将始终使用180铃声。</span><span class="sxs-lookup"><span data-stu-id="84850-316">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="84850-317">下图显示了具有 AlwaysBypass 模式的入站调用中的 SIP 阶梯，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="84850-317">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="84850-319">出站呼叫和用户是具有始终绕过的外部呼叫</span><span class="sxs-lookup"><span data-stu-id="84850-319">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="84850-320">众</span><span class="sxs-lookup"><span data-stu-id="84850-320">Mode</span></span> |    <span data-ttu-id="84850-321">用户</span><span class="sxs-lookup"><span data-stu-id="84850-321">User</span></span> |  <span data-ttu-id="84850-322">站点</span><span class="sxs-lookup"><span data-stu-id="84850-322">Site</span></span> |  <span data-ttu-id="84850-323">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="84850-323">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="84850-324">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="84850-324">AlwaysBypass</span></span> |  <span data-ttu-id="84850-325">外部</span><span class="sxs-lookup"><span data-stu-id="84850-325">External</span></span> |  <span data-ttu-id="84850-326">不适用</span><span class="sxs-lookup"><span data-stu-id="84850-326">N/A</span></span> | <span data-ttu-id="84850-327">出站</span><span class="sxs-lookup"><span data-stu-id="84850-327">Outbound</span></span> |


<span data-ttu-id="84850-328">下图显示了具有 AlwaysBypass 模式的出站呼叫的 SIP 阶梯，并且用户是外部的：</span><span class="sxs-lookup"><span data-stu-id="84850-328">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-12.png)

<span data-ttu-id="84850-330">下表显示了直接路由服务发送的 X-MS 标头：</span><span class="sxs-lookup"><span data-stu-id="84850-330">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="84850-331">参数</span><span class="sxs-lookup"><span data-stu-id="84850-331">Parameter</span></span> |   <span data-ttu-id="84850-332">解释</span><span class="sxs-lookup"><span data-stu-id="84850-332">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="84850-333">邀请 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-333">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="84850-334">在联机语音路由策略中定义的 SBC 的目标 FQDN 在请求 URI 中发送。</span><span class="sxs-lookup"><span data-stu-id="84850-334">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="84850-335">X-UserLocation：外部</span><span class="sxs-lookup"><span data-stu-id="84850-335">X-MS-UserLocation: external</span></span> | <span data-ttu-id="84850-336">指示用户位于企业网络外部的字段。</span><span class="sxs-lookup"><span data-stu-id="84850-336">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="84850-337">X-MS-MediaPath： proxysbc.contoso.com，VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-337">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="84850-338">指定客户端必须遍历到目标 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="84850-338">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="84850-339">在此情况下，我们始终绕过，并且客户端是外部客户端。</span><span class="sxs-lookup"><span data-stu-id="84850-339">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="84850-340">入站呼叫和用户是具有始终绕过的外部呼叫</span><span class="sxs-lookup"><span data-stu-id="84850-340">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="84850-341">众</span><span class="sxs-lookup"><span data-stu-id="84850-341">Mode</span></span> | <span data-ttu-id="84850-342">用户</span><span class="sxs-lookup"><span data-stu-id="84850-342">User</span></span> | <span data-ttu-id="84850-343">站点</span><span class="sxs-lookup"><span data-stu-id="84850-343">Site</span></span> |  <span data-ttu-id="84850-344">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="84850-344">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="84850-345">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="84850-345">AlwaysBypass</span></span> |  <span data-ttu-id="84850-346">外部</span><span class="sxs-lookup"><span data-stu-id="84850-346">External</span></span> |  <span data-ttu-id="84850-347">不适用</span><span class="sxs-lookup"><span data-stu-id="84850-347">N/A</span></span> |   <span data-ttu-id="84850-348">封</span><span class="sxs-lookup"><span data-stu-id="84850-348">Inbound</span></span> |

<span data-ttu-id="84850-349">对于入站呼叫，连接到直接路由的 SBC 需要发送重新邀请（默认情况下，始终提供本地媒体候选人）（如果用户是外部的位置）。</span><span class="sxs-lookup"><span data-stu-id="84850-349">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="84850-350">X-MediaPath 是基于记录路由和指定的 SBC 用户计算的。</span><span class="sxs-lookup"><span data-stu-id="84850-350">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="84850-351">下图显示了具有 AlwaysBypass 模式的入站呼叫的 SIP 阶梯，并且该用户是外部用户。</span><span class="sxs-lookup"><span data-stu-id="84850-351">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="84850-353">仅适用于本地用户模式</span><span class="sxs-lookup"><span data-stu-id="84850-353">Only for local users mode</span></span>

<span data-ttu-id="84850-354">仅当用户与 SBC 位于同一位置时，才会提供目标 SBC 的本地媒体候选项。</span><span class="sxs-lookup"><span data-stu-id="84850-354">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="84850-355">在所有其他情况下，媒体将通过代理 SBC 的内部或外部 IP 进行通信。</span><span class="sxs-lookup"><span data-stu-id="84850-355">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="84850-356">介绍以下方案：</span><span class="sxs-lookup"><span data-stu-id="84850-356">The following scenarios are described:</span></span>

- [<span data-ttu-id="84850-357">出站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="84850-357">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="84850-358">入站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="84850-358">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="84850-359">用户与 SBC 不在同一位置，但位于企业网络中</span><span class="sxs-lookup"><span data-stu-id="84850-359">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="84850-360">入站呼叫和用户是内部的，但与 SBC 不在同一位置</span><span class="sxs-lookup"><span data-stu-id="84850-360">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="84850-361">下表显示最终用户配置和操作：</span><span class="sxs-lookup"><span data-stu-id="84850-361">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="84850-362">用户物理位置</span><span class="sxs-lookup"><span data-stu-id="84850-362">User physical location</span></span> |  <span data-ttu-id="84850-363">用户拨打或接听号码</span><span class="sxs-lookup"><span data-stu-id="84850-363">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="84850-364">用户电话号码</span><span class="sxs-lookup"><span data-stu-id="84850-364">User phone number</span></span> | <span data-ttu-id="84850-365">联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="84850-365">Online Voice Routing Policy</span></span> |   <span data-ttu-id="84850-366">针对 SBC 配置的模式</span><span class="sxs-lookup"><span data-stu-id="84850-366">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="84850-367">越南</span><span class="sxs-lookup"><span data-stu-id="84850-367">Vietnam</span></span> | <span data-ttu-id="84850-368">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="84850-368">+84 4 3926  3000</span></span> |  <span data-ttu-id="84850-369">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="84850-369">+84 4 5555 5555</span></span> | <span data-ttu-id="84850-370">优先级1： ^ \+ 84 （\d {9} ） $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-370">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="84850-371">优先级2：. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="84850-371">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="84850-372">VNsbc.contoso.com-OnlyForLocalUsers Proxysbc.contoso.com-始终绕过</span><span class="sxs-lookup"><span data-stu-id="84850-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="84850-373">出站呼叫和用户与 SBC 在同一位置，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="84850-373">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="84850-374">众</span><span class="sxs-lookup"><span data-stu-id="84850-374">Mode</span></span> | <span data-ttu-id="84850-375">用户</span><span class="sxs-lookup"><span data-stu-id="84850-375">User</span></span> | <span data-ttu-id="84850-376">站点</span><span class="sxs-lookup"><span data-stu-id="84850-376">Site</span></span> | <span data-ttu-id="84850-377">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="84850-377">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="84850-378">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="84850-378">OnlyForLocalUsers</span></span> |   <span data-ttu-id="84850-379">内部</span><span class="sxs-lookup"><span data-stu-id="84850-379">Internal</span></span> |<span data-ttu-id="84850-380">与 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="84850-380">Same as SBC</span></span>   | <span data-ttu-id="84850-381">出站</span><span class="sxs-lookup"><span data-stu-id="84850-381">Outbound</span></span> |

<span data-ttu-id="84850-382">下图显示了具有 OnlyForLocalUsers 模式的出站调用，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="84850-382">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="84850-383">这是[当用户与 SBC 位于同一位置时，在出站呼叫](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)中显示的相同流。</span><span class="sxs-lookup"><span data-stu-id="84850-383">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="84850-385">入站呼叫和用户与 SBC 在同一位置，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="84850-385">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="84850-386">众</span><span class="sxs-lookup"><span data-stu-id="84850-386">Mode</span></span> | <span data-ttu-id="84850-387">用户</span><span class="sxs-lookup"><span data-stu-id="84850-387">User</span></span> | <span data-ttu-id="84850-388">站点</span><span class="sxs-lookup"><span data-stu-id="84850-388">Site</span></span> | <span data-ttu-id="84850-389">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="84850-389">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="84850-390">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="84850-390">OnlyForLocalUsers</span></span> |   <span data-ttu-id="84850-391">内部</span><span class="sxs-lookup"><span data-stu-id="84850-391">Internal</span></span> | <span data-ttu-id="84850-392">与 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="84850-392">Same as SBC</span></span> | <span data-ttu-id="84850-393">封</span><span class="sxs-lookup"><span data-stu-id="84850-393">Inbound</span></span> |

<span data-ttu-id="84850-394">下图显示了具有 OnlyForLocalUsers 模式的入站调用，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="84850-394">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="84850-395">[当用户与 SBC 位于同一位置时](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)，这是与入站通话中所示相同的流。</span><span class="sxs-lookup"><span data-stu-id="84850-395">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="84850-397">用户与 SBC 不在同一位置，但位于企业网络中，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="84850-397">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="84850-398">众</span><span class="sxs-lookup"><span data-stu-id="84850-398">Mode</span></span> | <span data-ttu-id="84850-399">用户</span><span class="sxs-lookup"><span data-stu-id="84850-399">User</span></span> | <span data-ttu-id="84850-400">站点</span><span class="sxs-lookup"><span data-stu-id="84850-400">Site</span></span> |<span data-ttu-id="84850-401">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="84850-401">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="84850-402">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="84850-402">OnlyForLocalUsers</span></span>  | <span data-ttu-id="84850-403">内部</span><span class="sxs-lookup"><span data-stu-id="84850-403">Internal</span></span> |   <span data-ttu-id="84850-404">与 SBC 不同</span><span class="sxs-lookup"><span data-stu-id="84850-404">Different from SBC</span></span> | <span data-ttu-id="84850-405">出站</span><span class="sxs-lookup"><span data-stu-id="84850-405">Outbound</span></span> |

<span data-ttu-id="84850-406">直接路由基于在 SBC 上配置的用户和模式的已报告位置计算 X MediaPath。</span><span class="sxs-lookup"><span data-stu-id="84850-406">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="84850-407">下图显示了具有 OnlyForLocalUsers 模式的出站呼叫，以及与 SBC 不在同一位置的内部用户。</span><span class="sxs-lookup"><span data-stu-id="84850-407">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="84850-409">入站呼叫和用户是内部的，但与 SBC 不在同一位置，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="84850-409">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="84850-410">众</span><span class="sxs-lookup"><span data-stu-id="84850-410">Mode</span></span> |    <span data-ttu-id="84850-411">用户</span><span class="sxs-lookup"><span data-stu-id="84850-411">User</span></span> |  <span data-ttu-id="84850-412">站点</span><span class="sxs-lookup"><span data-stu-id="84850-412">Site</span></span> |  <span data-ttu-id="84850-413">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="84850-413">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="84850-414">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="84850-414">OnlyForLocalUsers</span></span> | <span data-ttu-id="84850-415">内部</span><span class="sxs-lookup"><span data-stu-id="84850-415">Internal</span></span> |    <span data-ttu-id="84850-416">与 SBC 不同</span><span class="sxs-lookup"><span data-stu-id="84850-416">Different from SBC</span></span> |    <span data-ttu-id="84850-417">封</span><span class="sxs-lookup"><span data-stu-id="84850-417">Inbound</span></span> |

<span data-ttu-id="84850-418">下图显示了具有 OnlyForLocalUsers 模式的入站呼叫，以及与 SBC 不在同一位置的内部用户。</span><span class="sxs-lookup"><span data-stu-id="84850-418">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-17.png)









