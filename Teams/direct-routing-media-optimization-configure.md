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
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576984"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="65de1-103">为直接路由配置本地媒体优化</span><span class="sxs-lookup"><span data-stu-id="65de1-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="65de1-104">本地媒体优化的配置基于其他云语音功能常用的网络设置，例如Location-Based和动态紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="65de1-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="65de1-105">若要详细了解网络区域、网络站点、网络子网和受信任的 IP 地址，请参阅云 [语音功能的网络设置](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="65de1-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="65de1-106">配置本地媒体优化之前，请参阅 [直接路由的本地媒体优化](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="65de1-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="65de1-107">若要配置本地媒体优化，需要执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="65de1-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="65de1-108">可以使用 Teams 管理中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="65de1-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="65de1-109">有关详细信息，请参阅 [管理网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="65de1-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="65de1-110">根据本文 (配置用户和 SBC) 。</span><span class="sxs-lookup"><span data-stu-id="65de1-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="65de1-111">根据 SBC 供应商规范 (为本地媒体优化配置 SBC) 。</span><span class="sxs-lookup"><span data-stu-id="65de1-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="65de1-112">下图显示了本文中示例中使用的网络设置。</span><span class="sxs-lookup"><span data-stu-id="65de1-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="65de1-113">![显示示例网络设置的示意图](media/direct-routing-media-op-9.png "示例的网络设置")</span><span class="sxs-lookup"><span data-stu-id="65de1-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="65de1-114">配置用户和 SBC 站点</span><span class="sxs-lookup"><span data-stu-id="65de1-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="65de1-115">若要配置用户和 SBC 站点，需要：</span><span class="sxs-lookup"><span data-stu-id="65de1-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="65de1-116">[管理外部受信任的 IP 地址](#manage-external-trusted-ip-addresses)。</span><span class="sxs-lookup"><span data-stu-id="65de1-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="65de1-117">[通过配置网络区域](#define-the-network-topology) 、网络站点和网络子网来定义网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="65de1-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="65de1-118">[通过使用相关模式和](#define-the-virtual-network-topology) 代理 SBC 值 (SBC) 站点 () 定义虚拟网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="65de1-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="65de1-119">根据 SBC (规范) SBC 优化的 SBC 配置</span><span class="sxs-lookup"><span data-stu-id="65de1-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="65de1-120">本文介绍 Microsoft 组件的配置。</span><span class="sxs-lookup"><span data-stu-id="65de1-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="65de1-121">有关 SBC 配置的信息，请参阅 SBC 供应商文档。</span><span class="sxs-lookup"><span data-stu-id="65de1-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="65de1-122">以下 SBC 供应商支持本地媒体优化：</span><span class="sxs-lookup"><span data-stu-id="65de1-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="65de1-123">供应商</span><span class="sxs-lookup"><span data-stu-id="65de1-123">Vendor</span></span> | <span data-ttu-id="65de1-124">产品</span><span class="sxs-lookup"><span data-stu-id="65de1-124">Product</span></span> |    <span data-ttu-id="65de1-125">软件版本</span><span class="sxs-lookup"><span data-stu-id="65de1-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="65de1-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="65de1-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="65de1-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="65de1-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="65de1-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="65de1-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="65de1-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="65de1-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="65de1-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="65de1-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="65de1-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="65de1-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="65de1-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="65de1-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="65de1-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="65de1-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="65de1-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="65de1-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="65de1-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="65de1-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="65de1-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="65de1-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="65de1-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="65de1-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="65de1-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="65de1-142">7.20A.256</span></span> |
| [<span data-ttu-id="65de1-143">功能区 SBC Core</span><span class="sxs-lookup"><span data-stu-id="65de1-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="65de1-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="65de1-144">SBC 5110</span></span>         | <span data-ttu-id="65de1-145">8.2</span><span class="sxs-lookup"><span data-stu-id="65de1-145">8.2</span></span>  |
|            |  <span data-ttu-id="65de1-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="65de1-146">SBC 5210</span></span>         | <span data-ttu-id="65de1-147">8.2</span><span class="sxs-lookup"><span data-stu-id="65de1-147">8.2</span></span>  |
|            |  <span data-ttu-id="65de1-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="65de1-148">SBC 5400</span></span>         | <span data-ttu-id="65de1-149">8.2</span><span class="sxs-lookup"><span data-stu-id="65de1-149">8.2</span></span>  |
|            |  <span data-ttu-id="65de1-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="65de1-150">SBC 7000</span></span>         | <span data-ttu-id="65de1-151">8.2</span><span class="sxs-lookup"><span data-stu-id="65de1-151">8.2</span></span>  |
|            |  <span data-ttu-id="65de1-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="65de1-152">SBC SWe</span></span>          | <span data-ttu-id="65de1-153">8.2</span><span class="sxs-lookup"><span data-stu-id="65de1-153">8.2</span></span>  |
| [<span data-ttu-id="65de1-154">功能区 SBC Edge</span><span class="sxs-lookup"><span data-stu-id="65de1-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="65de1-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="65de1-155">SBC SWe Lite</span></span> | <span data-ttu-id="65de1-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="65de1-156">8.1.5</span></span> |
|               | <span data-ttu-id="65de1-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="65de1-157">SBC 1000</span></span> | <span data-ttu-id="65de1-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="65de1-158">8.1.5</span></span>  |
|               | <span data-ttu-id="65de1-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="65de1-159">SBC 2000</span></span> | <span data-ttu-id="65de1-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="65de1-160">8.1.5</span></span>  |
| [<span data-ttu-id="65de1-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="65de1-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="65de1-162">anynode</span><span class="sxs-lookup"><span data-stu-id="65de1-162">anynode</span></span>          | <span data-ttu-id="65de1-163">4.0.1+</span><span class="sxs-lookup"><span data-stu-id="65de1-163">4.0.1+</span></span> |
| [<span data-ttu-id="65de1-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="65de1-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="65de1-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="65de1-165">AP 1100</span></span> | <span data-ttu-id="65de1-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="65de1-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="65de1-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="65de1-167">AP 3900</span></span> | <span data-ttu-id="65de1-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="65de1-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="65de1-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="65de1-169">AP 4600</span></span> | <span data-ttu-id="65de1-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="65de1-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="65de1-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="65de1-171">AP 6300</span></span> | <span data-ttu-id="65de1-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="65de1-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="65de1-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="65de1-173">AP 6350</span></span> | <span data-ttu-id="65de1-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="65de1-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="65de1-175">VME</span><span class="sxs-lookup"><span data-stu-id="65de1-175">VME</span></span>     | <span data-ttu-id="65de1-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="65de1-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="65de1-177">管理外部受信任的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="65de1-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="65de1-178">外部受信任的 IP 是企业网络的 Internet 外部 IP。</span><span class="sxs-lookup"><span data-stu-id="65de1-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="65de1-179">这些 IP 是客户端连接到 Microsoft Teams 使用的 IP Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="65de1-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="65de1-180">您需要为用户使用本地媒体优化的每个站点添加这些外部 IP。</span><span class="sxs-lookup"><span data-stu-id="65de1-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="65de1-181">若要添加每个站点的公共 IP 地址，请使用 New-CsTenantTrustedIPAddress cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65de1-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="65de1-182">可以定义租户的无限数量的受信任 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="65de1-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="65de1-183">如果用户看到的外部 IP Microsoft 365 IPv4 和 IPv6 地址，则需要添加这两种类型的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="65de1-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="65de1-184">对于 IPv4，请使用掩码 32。</span><span class="sxs-lookup"><span data-stu-id="65de1-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="65de1-185">对于 IPv6，请使用掩码 128。</span><span class="sxs-lookup"><span data-stu-id="65de1-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="65de1-186">可以通过在 cmdlet 上指定不同的 MaskBits 来添加单个外部 IP 地址和外部 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="65de1-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="65de1-187">添加受信任的 IP 地址的示例。</span><span class="sxs-lookup"><span data-stu-id="65de1-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="65de1-188">定义网络拓扑</span><span class="sxs-lookup"><span data-stu-id="65de1-188">Define the network topology</span></span>

<span data-ttu-id="65de1-189">本部分介绍如何为网络拓扑定义网络区域、网络站点和网络子网。</span><span class="sxs-lookup"><span data-stu-id="65de1-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="65de1-190">所有参数都区分大小写，因此需确保使用与设置期间使用的大小写相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="65de1-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="65de1-191"> (例如，GatewaySiteID 值"越南"和"越南"将视为不同的站点。) </span><span class="sxs-lookup"><span data-stu-id="65de1-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="65de1-192">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="65de1-192">Define network regions</span></span>

<span data-ttu-id="65de1-193">若要定义网络区域，请使用 New-CsTenantNetworkRegion cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65de1-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="65de1-194">RegionID 参数是一个逻辑名称，表示区域地理位置，没有依赖关系或限制。</span><span class="sxs-lookup"><span data-stu-id="65de1-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="65de1-195">CentralSite <site ID> 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="65de1-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="65de1-196">以下示例创建名为 APAC 的网络区域：</span><span class="sxs-lookup"><span data-stu-id="65de1-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="65de1-197">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="65de1-197">Define network sites</span></span>

<span data-ttu-id="65de1-198">若要定义网络站点，请使用 New-CsTenantNetworkSite cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65de1-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="65de1-199">每个网络站点必须与网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="65de1-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="65de1-200">以下示例在 APAC 区域创建三个新的网络站点：越南、印度尼西亚和新加坡：</span><span class="sxs-lookup"><span data-stu-id="65de1-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="65de1-201">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="65de1-201">Define network subnets</span></span>

<span data-ttu-id="65de1-202">若要定义网络子网并将其关联到网络站点，请使用 New-CsTenantNetworkSubnet cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65de1-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="65de1-203">每个网络子网只能与一个站点相关联。</span><span class="sxs-lookup"><span data-stu-id="65de1-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="65de1-204">以下示例定义三个网络子网，并使它们与三个网络站点关联：越南、印度尼西亚和新加坡：</span><span class="sxs-lookup"><span data-stu-id="65de1-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="65de1-205">定义虚拟网络拓扑</span><span class="sxs-lookup"><span data-stu-id="65de1-205">Define the virtual network topology</span></span> 

<span data-ttu-id="65de1-206">首先，租户管理员使用 New-CsOnlinePSTNGateway cmdlet 为每个相关的 SBC 创建新的 SBC 配置。</span><span class="sxs-lookup"><span data-stu-id="65de1-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="65de1-207">租户管理员通过使用 Set-CsOnlinePSTNGateway cmdlet 为 PSTN 网关对象指定网络站点来定义虚拟网络拓扑：</span><span class="sxs-lookup"><span data-stu-id="65de1-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="65de1-208">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="65de1-208">Note the following:</span></span> 
   - <span data-ttu-id="65de1-209">如果客户具有单个 SBC，则 -ProxySBC 参数必须是具有集中式中继方案的 $null 或 SBC FQDN 值 (Central S) BC。</span><span class="sxs-lookup"><span data-stu-id="65de1-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="65de1-210">-MediaBypass 参数必须设置为 $true 以支持本地媒体优化。</span><span class="sxs-lookup"><span data-stu-id="65de1-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="65de1-211">如果 SBC 未设置 -BypassMode 参数，将不会发送 X-MS 标头。</span><span class="sxs-lookup"><span data-stu-id="65de1-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="65de1-212">所有参数都区分大小写，因此需确保使用与设置期间使用的大小写相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="65de1-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="65de1-213"> (例如，GatewaySiteID 值"越南"和"越南"将视为不同的站点。) </span><span class="sxs-lookup"><span data-stu-id="65de1-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="65de1-214">以下示例使用"始终绕过"模式将三个 SDC 添加到 APAC 区域的网络站点越南、印度尼西亚和新加坡：</span><span class="sxs-lookup"><span data-stu-id="65de1-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="65de1-215">注意：若要确保在同时配置本地媒体优化和 Location-Based 路由 (LBR) 时不间断操作，必须通过将 GatewaySiteLbrEnabled 参数设置为每个下游 SBC 的 $true 来为 LBR 启用下游 SBC。</span><span class="sxs-lookup"><span data-stu-id="65de1-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="65de1-216"> (代理 SBC.) </span><span class="sxs-lookup"><span data-stu-id="65de1-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="65de1-217">根据上述信息，直接路由将包括三个专有的 SIP 标头到 SIP 邀请和重新邀请，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="65de1-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="65de1-218">在邀请和邀请的直接路由中引入的 X-MS Re-Invites（如果已定义 BypassMode）：</span><span class="sxs-lookup"><span data-stu-id="65de1-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="65de1-219">标头名称</span><span class="sxs-lookup"><span data-stu-id="65de1-219">Header name</span></span> | <span data-ttu-id="65de1-220">值</span><span class="sxs-lookup"><span data-stu-id="65de1-220">Values</span></span> | <span data-ttu-id="65de1-221">备注</span><span class="sxs-lookup"><span data-stu-id="65de1-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="65de1-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="65de1-222">X-MS-UserLocation</span></span> | <span data-ttu-id="65de1-223">internal/external</span><span class="sxs-lookup"><span data-stu-id="65de1-223">internal/external</span></span> | <span data-ttu-id="65de1-224">指示用户是内部用户还是外部用户</span><span class="sxs-lookup"><span data-stu-id="65de1-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="65de1-225">请求 URI 邀请 sip：+84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="65de1-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="65de1-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="65de1-226">SBC FQDN</span></span> | <span data-ttu-id="65de1-227">针对调用的 FQDN，即使 SBC 未直接连接到直接路由</span><span class="sxs-lookup"><span data-stu-id="65de1-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="65de1-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="65de1-228">X-MS-MediaPath</span></span> | <span data-ttu-id="65de1-229">示例：proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="65de1-230">应用于用户和目标 SBC 之间的媒体路径的 SBC 顺序。</span><span class="sxs-lookup"><span data-stu-id="65de1-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="65de1-231">最终的 SBC 始终为最后</span><span class="sxs-lookup"><span data-stu-id="65de1-231">The final SBC is always last</span></span> |
| <span data-ttu-id="65de1-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="65de1-232">X-MS-UserSite</span></span> | <span data-ttu-id="65de1-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="65de1-233">usersiteID</span></span> | <span data-ttu-id="65de1-234">租户管理员定义的字符串</span><span class="sxs-lookup"><span data-stu-id="65de1-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="65de1-235">调用流</span><span class="sxs-lookup"><span data-stu-id="65de1-235">Call flows</span></span> 

<span data-ttu-id="65de1-236">下面显示了两种模式的调用流：</span><span class="sxs-lookup"><span data-stu-id="65de1-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="65de1-237">始终绕过</span><span class="sxs-lookup"><span data-stu-id="65de1-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="65de1-238">仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="65de1-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="65de1-239">始终绕过模式</span><span class="sxs-lookup"><span data-stu-id="65de1-239">Always Bypass mode</span></span>

<span data-ttu-id="65de1-240">始终绕过模式是最简单的配置选项。</span><span class="sxs-lookup"><span data-stu-id="65de1-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="65de1-241">如果可以从任何站点访问所有 SDC，租户管理员可以为所有用户和 SDC 配置单个站点。</span><span class="sxs-lookup"><span data-stu-id="65de1-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="65de1-242">这些示例显示了以下情况的始终绕过模式：</span><span class="sxs-lookup"><span data-stu-id="65de1-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="65de1-243">出站调用，并且用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="65de1-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="65de1-244">入站呼叫和用户位于 SBC 相同的位置</span><span class="sxs-lookup"><span data-stu-id="65de1-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="65de1-245">出站调用且用户是外部用户</span><span class="sxs-lookup"><span data-stu-id="65de1-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="65de1-246">入站呼叫和用户是外部用户</span><span class="sxs-lookup"><span data-stu-id="65de1-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="65de1-247">下表显示了示例中使用的 FQDN 和 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="65de1-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="65de1-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="65de1-248">FQDN</span></span> | <span data-ttu-id="65de1-249">SBC 外部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="65de1-249">SBC external IP address</span></span> | <span data-ttu-id="65de1-250">SBC 内部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="65de1-250">SBC internal IP Address</span></span> | <span data-ttu-id="65de1-251">内部子网</span><span class="sxs-lookup"><span data-stu-id="65de1-251">Internal subnet</span></span> | <span data-ttu-id="65de1-252">位置</span><span class="sxs-lookup"><span data-stu-id="65de1-252">Location</span></span> | <span data-ttu-id="65de1-253">外部 NAT (受信任的 IP) </span><span class="sxs-lookup"><span data-stu-id="65de1-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="65de1-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="65de1-255">无</span><span class="sxs-lookup"><span data-stu-id="65de1-255">None</span></span> | <span data-ttu-id="65de1-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="65de1-256">192.168.1.5</span></span> | <span data-ttu-id="65de1-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="65de1-257">192.168.1.0/24</span></span> | <span data-ttu-id="65de1-258">越南</span><span class="sxs-lookup"><span data-stu-id="65de1-258">Vietnam</span></span> | <span data-ttu-id="65de1-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="65de1-259">172.16.240.110</span></span> |
| <span data-ttu-id="65de1-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="65de1-261">无</span><span class="sxs-lookup"><span data-stu-id="65de1-261">None</span></span> | <span data-ttu-id="65de1-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="65de1-262">192.168.2.5</span></span> | <span data-ttu-id="65de1-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="65de1-263">192.168.2.0/24</span></span> | <span data-ttu-id="65de1-264">印度尼西亚</span><span class="sxs-lookup"><span data-stu-id="65de1-264">Indonesia</span></span> | <span data-ttu-id="65de1-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="65de1-265">172.16.240.120</span></span> |
| <span data-ttu-id="65de1-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="65de1-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="65de1-267">172.16.240.133</span></span> | <span data-ttu-id="65de1-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="65de1-268">192.168.3.5</span></span> | <span data-ttu-id="65de1-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="65de1-269">192.168.3.0/24</span></span> | <span data-ttu-id="65de1-270">新加坡</span><span class="sxs-lookup"><span data-stu-id="65de1-270">Singapore</span></span> | <span data-ttu-id="65de1-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="65de1-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="65de1-272">出站呼叫和用户位于与始终绕过的 SBC 相同的位置</span><span class="sxs-lookup"><span data-stu-id="65de1-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="65de1-273">模式</span><span class="sxs-lookup"><span data-stu-id="65de1-273">Mode</span></span> |    <span data-ttu-id="65de1-274">用户</span><span class="sxs-lookup"><span data-stu-id="65de1-274">User</span></span> |  <span data-ttu-id="65de1-275">位置</span><span class="sxs-lookup"><span data-stu-id="65de1-275">Location</span></span> |  <span data-ttu-id="65de1-276">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="65de1-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="65de1-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="65de1-277">AlwaysBypass</span></span> |    <span data-ttu-id="65de1-278">内部</span><span class="sxs-lookup"><span data-stu-id="65de1-278">Internal</span></span> |  <span data-ttu-id="65de1-279">与 SBC 相同的站点</span><span class="sxs-lookup"><span data-stu-id="65de1-279">The same site as SBC</span></span> |  <span data-ttu-id="65de1-280">出站</span><span class="sxs-lookup"><span data-stu-id="65de1-280">Outbound</span></span> |

<span data-ttu-id="65de1-281">下表显示了最终用户配置和操作：</span><span class="sxs-lookup"><span data-stu-id="65de1-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="65de1-282">用户物理位置</span><span class="sxs-lookup"><span data-stu-id="65de1-282">User physical location</span></span>| <span data-ttu-id="65de1-283">用户拨打或接收对号码的呼叫</span><span class="sxs-lookup"><span data-stu-id="65de1-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="65de1-284">用户电话号码</span><span class="sxs-lookup"><span data-stu-id="65de1-284">User phone number</span></span>  | <span data-ttu-id="65de1-285">联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="65de1-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="65de1-286">为 SBC 配置的模式</span><span class="sxs-lookup"><span data-stu-id="65de1-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="65de1-287">越南</span><span class="sxs-lookup"><span data-stu-id="65de1-287">Vietnam</span></span> | <span data-ttu-id="65de1-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="65de1-288">+84 4 3926 3000</span></span> | <span data-ttu-id="65de1-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="65de1-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="65de1-290">优先级 1：^ \+ 84 (\d {9}) $ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="65de1-291">优先级 2：.\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="65de1-292">VNsbc.contoso.com – 始终绕过</span><span class="sxs-lookup"><span data-stu-id="65de1-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="65de1-293">proxysbc.contoso.com – 始终绕过</span><span class="sxs-lookup"><span data-stu-id="65de1-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="65de1-294">下图显示了始终绕过模式的出站呼叫的 SIP 阶梯，以及与 SBC 位于同一位置的用户。</span><span class="sxs-lookup"><span data-stu-id="65de1-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="65de1-295">![显示出站呼叫的示意图](media/direct-routing-media-op-10.png "出站调用")</span><span class="sxs-lookup"><span data-stu-id="65de1-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="65de1-296">下表显示了直接路由发送的 X-MS 标头：</span><span class="sxs-lookup"><span data-stu-id="65de1-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="65de1-297">参数</span><span class="sxs-lookup"><span data-stu-id="65de1-297">Parameter</span></span> | <span data-ttu-id="65de1-298">解释</span><span class="sxs-lookup"><span data-stu-id="65de1-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="65de1-299">邀请 +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="65de1-300">在请求 URI 中发送联机语音路由策略中定义的 SBC 的目标 FQDN</span><span class="sxs-lookup"><span data-stu-id="65de1-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="65de1-301">X-MS-UserLocation：内部</span><span class="sxs-lookup"><span data-stu-id="65de1-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="65de1-302">字段指示用户位于企业网络内</span><span class="sxs-lookup"><span data-stu-id="65de1-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="65de1-303">X-MS-MediaPath：VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="65de1-304">指定客户端必须遍历到目标 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="65de1-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="65de1-305">在这种情况下，由于我们始终绕过，并且客户端在内部是作为标头中的唯一名称发送的目标名称。</span><span class="sxs-lookup"><span data-stu-id="65de1-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="65de1-306">X-MS-UserSite：越南</span><span class="sxs-lookup"><span data-stu-id="65de1-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="65de1-307">在用户所在的站点内指示的字段。</span><span class="sxs-lookup"><span data-stu-id="65de1-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="65de1-308">入站呼叫和用户位于与始终绕过的 SBC 相同的位置</span><span class="sxs-lookup"><span data-stu-id="65de1-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="65de1-309">模式</span><span class="sxs-lookup"><span data-stu-id="65de1-309">Mode</span></span> |    <span data-ttu-id="65de1-310">用户</span><span class="sxs-lookup"><span data-stu-id="65de1-310">User</span></span> |  <span data-ttu-id="65de1-311">位置</span><span class="sxs-lookup"><span data-stu-id="65de1-311">Location</span></span> |  <span data-ttu-id="65de1-312">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="65de1-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="65de1-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="65de1-313">AlwaysBypass</span></span> |    <span data-ttu-id="65de1-314">内部</span><span class="sxs-lookup"><span data-stu-id="65de1-314">Internal</span></span> | <span data-ttu-id="65de1-315">与 SBC 相同的站点</span><span class="sxs-lookup"><span data-stu-id="65de1-315">The same site as SBC</span></span> | <span data-ttu-id="65de1-316">入站</span><span class="sxs-lookup"><span data-stu-id="65de1-316">Inbound</span></span> |


<span data-ttu-id="65de1-317">在入站呼叫中，用户的位置未知，SBC 必须猜测用户的位置。</span><span class="sxs-lookup"><span data-stu-id="65de1-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="65de1-318">如果猜测不正确，需要重新邀请。</span><span class="sxs-lookup"><span data-stu-id="65de1-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="65de1-319">此情况假定用户是内部用户，媒体可以直接流动，在重新邀请用户 (不需要进一步) 。</span><span class="sxs-lookup"><span data-stu-id="65de1-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="65de1-320">连接到直接路由服务的 SBC 通过提供"直接路由"和"Record-Route报告原始 SBC 位置。</span><span class="sxs-lookup"><span data-stu-id="65de1-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="65de1-321">根据这些字段，媒体路径由直接路由计算。</span><span class="sxs-lookup"><span data-stu-id="65de1-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="65de1-322">注意：如果用户可以有多个终结点，则不能支持 183。</span><span class="sxs-lookup"><span data-stu-id="65de1-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="65de1-323">在这种情况下，直接路由始终使用 180 响铃。</span><span class="sxs-lookup"><span data-stu-id="65de1-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="65de1-324">下图显示了使用 AlwaysBypass 模式的入站呼叫中的 SIP 阶梯，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="65de1-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![显示 SIP 阶梯的示意图](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="65de1-326">出站呼叫和用户是外部的始终绕过</span><span class="sxs-lookup"><span data-stu-id="65de1-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="65de1-327">模式</span><span class="sxs-lookup"><span data-stu-id="65de1-327">Mode</span></span> |    <span data-ttu-id="65de1-328">用户</span><span class="sxs-lookup"><span data-stu-id="65de1-328">User</span></span> |  <span data-ttu-id="65de1-329">站点</span><span class="sxs-lookup"><span data-stu-id="65de1-329">Site</span></span> |  <span data-ttu-id="65de1-330">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="65de1-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="65de1-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="65de1-331">AlwaysBypass</span></span> |  <span data-ttu-id="65de1-332">外部</span><span class="sxs-lookup"><span data-stu-id="65de1-332">External</span></span> |  <span data-ttu-id="65de1-333">不适用</span><span class="sxs-lookup"><span data-stu-id="65de1-333">N/A</span></span> | <span data-ttu-id="65de1-334">出站</span><span class="sxs-lookup"><span data-stu-id="65de1-334">Outbound</span></span> |


<span data-ttu-id="65de1-335">下图显示了使用 AlwaysBypass 模式的出站呼叫的 SIP 阶梯，用户是外部用户：</span><span class="sxs-lookup"><span data-stu-id="65de1-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![显示 SIP 阶梯的示意图](media/direct-routing-media-op-12.png)

<span data-ttu-id="65de1-337">下表显示了直接路由服务发送的 X-MS 标头：</span><span class="sxs-lookup"><span data-stu-id="65de1-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="65de1-338">参数</span><span class="sxs-lookup"><span data-stu-id="65de1-338">Parameter</span></span> |   <span data-ttu-id="65de1-339">解释</span><span class="sxs-lookup"><span data-stu-id="65de1-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="65de1-340">邀请 +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="65de1-341">在请求 URI 中发送联机语音路由策略中定义的 SBC 的目标 FQDN。</span><span class="sxs-lookup"><span data-stu-id="65de1-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="65de1-342">X-MS-UserLocation：external</span><span class="sxs-lookup"><span data-stu-id="65de1-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="65de1-343">字段指示用户位于企业网络外部。</span><span class="sxs-lookup"><span data-stu-id="65de1-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="65de1-344">X-MS-MediaPath：proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="65de1-345">指定客户端必须遍历到目标 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="65de1-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="65de1-346">在这种情况下，由于我们始终绕过，并且客户端是外部的。</span><span class="sxs-lookup"><span data-stu-id="65de1-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="65de1-347">入站呼叫和用户是外部的始终绕过</span><span class="sxs-lookup"><span data-stu-id="65de1-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="65de1-348">模式</span><span class="sxs-lookup"><span data-stu-id="65de1-348">Mode</span></span> | <span data-ttu-id="65de1-349">用户</span><span class="sxs-lookup"><span data-stu-id="65de1-349">User</span></span> | <span data-ttu-id="65de1-350">站点</span><span class="sxs-lookup"><span data-stu-id="65de1-350">Site</span></span> |  <span data-ttu-id="65de1-351">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="65de1-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="65de1-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="65de1-352">AlwaysBypass</span></span> |  <span data-ttu-id="65de1-353">外部</span><span class="sxs-lookup"><span data-stu-id="65de1-353">External</span></span> |  <span data-ttu-id="65de1-354">不适用</span><span class="sxs-lookup"><span data-stu-id="65de1-354">N/A</span></span> |   <span data-ttu-id="65de1-355">入站</span><span class="sxs-lookup"><span data-stu-id="65de1-355">Inbound</span></span> |

<span data-ttu-id="65de1-356">对于入站呼叫，默认情况下，连接到直接路由的 SBC 需要发送重新邀请 (，如果用户的位置在外部，则始终提供本地媒体候选) 。</span><span class="sxs-lookup"><span data-stu-id="65de1-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="65de1-357">X-MediaPath 基于指定的 Record-Route SBC 用户计算。</span><span class="sxs-lookup"><span data-stu-id="65de1-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="65de1-358">下图显示了具有 AlwaysBypass 模式的入站呼叫的 SIP 阶梯，并且用户是外部用户。</span><span class="sxs-lookup"><span data-stu-id="65de1-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![显示 SIP 阶梯的示意图](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="65de1-360">仅适用于本地用户模式</span><span class="sxs-lookup"><span data-stu-id="65de1-360">Only for local users mode</span></span>

<span data-ttu-id="65de1-361">目标 SBC 的本地媒体候选项仅在用户与 SBC 位于同一位置时提供。</span><span class="sxs-lookup"><span data-stu-id="65de1-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="65de1-362">在所有其他情况下，媒体将流经代理 SBC 的内部或外部 IP。</span><span class="sxs-lookup"><span data-stu-id="65de1-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="65de1-363">描述了以下方案：</span><span class="sxs-lookup"><span data-stu-id="65de1-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="65de1-364">出站调用，并且用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="65de1-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="65de1-365">入站呼叫和用户位于 SBC 相同的位置</span><span class="sxs-lookup"><span data-stu-id="65de1-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="65de1-366">用户不与 SBC 位于同一位置，但位于企业网络中</span><span class="sxs-lookup"><span data-stu-id="65de1-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="65de1-367">入站呼叫和用户是内部用户，但不与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="65de1-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="65de1-368">下表显示了最终用户配置和操作：</span><span class="sxs-lookup"><span data-stu-id="65de1-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="65de1-369">用户物理位置</span><span class="sxs-lookup"><span data-stu-id="65de1-369">User physical location</span></span> |  <span data-ttu-id="65de1-370">用户拨打或接收对号码的呼叫</span><span class="sxs-lookup"><span data-stu-id="65de1-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="65de1-371">用户电话号码</span><span class="sxs-lookup"><span data-stu-id="65de1-371">User phone number</span></span> | <span data-ttu-id="65de1-372">联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="65de1-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="65de1-373">为 SBC 配置的模式</span><span class="sxs-lookup"><span data-stu-id="65de1-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="65de1-374">越南</span><span class="sxs-lookup"><span data-stu-id="65de1-374">Vietnam</span></span> | <span data-ttu-id="65de1-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="65de1-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="65de1-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="65de1-376">+84 4 5555 5555</span></span> | <span data-ttu-id="65de1-377">优先级 1：^ \+ 84 (\d {9}) $ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="65de1-378">优先级 2：.\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65de1-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="65de1-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – 始终绕过</span><span class="sxs-lookup"><span data-stu-id="65de1-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="65de1-380">出站呼叫和用户位于 SBC 的同一位置，仅针对本地用户</span><span class="sxs-lookup"><span data-stu-id="65de1-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="65de1-381">模式</span><span class="sxs-lookup"><span data-stu-id="65de1-381">Mode</span></span> | <span data-ttu-id="65de1-382">用户</span><span class="sxs-lookup"><span data-stu-id="65de1-382">User</span></span> | <span data-ttu-id="65de1-383">站点</span><span class="sxs-lookup"><span data-stu-id="65de1-383">Site</span></span> | <span data-ttu-id="65de1-384">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="65de1-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="65de1-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="65de1-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="65de1-386">内部</span><span class="sxs-lookup"><span data-stu-id="65de1-386">Internal</span></span> |<span data-ttu-id="65de1-387">与 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="65de1-387">Same as SBC</span></span>   | <span data-ttu-id="65de1-388">出站</span><span class="sxs-lookup"><span data-stu-id="65de1-388">Outbound</span></span> |

<span data-ttu-id="65de1-389">下图显示了具有 OnlyForLocalUsers 模式的出站调用，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="65de1-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="65de1-390">当用户与 SBC 位于同一位置时，此流显示在出站 [调用中](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。</span><span class="sxs-lookup"><span data-stu-id="65de1-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![显示 SIP 阶梯的示意图](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="65de1-392">入站呼叫和用户位于 SBC 的同一位置，仅针对本地用户</span><span class="sxs-lookup"><span data-stu-id="65de1-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="65de1-393">模式</span><span class="sxs-lookup"><span data-stu-id="65de1-393">Mode</span></span> | <span data-ttu-id="65de1-394">用户</span><span class="sxs-lookup"><span data-stu-id="65de1-394">User</span></span> | <span data-ttu-id="65de1-395">站点</span><span class="sxs-lookup"><span data-stu-id="65de1-395">Site</span></span> | <span data-ttu-id="65de1-396">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="65de1-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="65de1-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="65de1-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="65de1-398">内部</span><span class="sxs-lookup"><span data-stu-id="65de1-398">Internal</span></span> | <span data-ttu-id="65de1-399">与 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="65de1-399">Same as SBC</span></span> | <span data-ttu-id="65de1-400">入站</span><span class="sxs-lookup"><span data-stu-id="65de1-400">Inbound</span></span> |

<span data-ttu-id="65de1-401">下图显示了具有 OnlyForLocalUsers 模式的入站调用，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="65de1-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="65de1-402">当用户与 SBC 位于同一位置时，此流与入站调用 [中所示的流相同](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。</span><span class="sxs-lookup"><span data-stu-id="65de1-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![显示 SIP 阶梯的示意图](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="65de1-404">用户不与 SBC 位于同一位置，而是位于企业网络中，仅针对本地用户</span><span class="sxs-lookup"><span data-stu-id="65de1-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="65de1-405">模式</span><span class="sxs-lookup"><span data-stu-id="65de1-405">Mode</span></span> | <span data-ttu-id="65de1-406">用户</span><span class="sxs-lookup"><span data-stu-id="65de1-406">User</span></span> | <span data-ttu-id="65de1-407">站点</span><span class="sxs-lookup"><span data-stu-id="65de1-407">Site</span></span> |<span data-ttu-id="65de1-408">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="65de1-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="65de1-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="65de1-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="65de1-410">内部</span><span class="sxs-lookup"><span data-stu-id="65de1-410">Internal</span></span> |   <span data-ttu-id="65de1-411">不同于 SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-411">Different from SBC</span></span> | <span data-ttu-id="65de1-412">出站</span><span class="sxs-lookup"><span data-stu-id="65de1-412">Outbound</span></span> |

<span data-ttu-id="65de1-413">直接路由根据用户在 SBC 上配置的报告位置和模式来计算 X-MediaPath。</span><span class="sxs-lookup"><span data-stu-id="65de1-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="65de1-414">下图显示了具有 OnlyForLocalUsers 模式的出站调用，以及与 SBC 不在同一位置的内部用户。</span><span class="sxs-lookup"><span data-stu-id="65de1-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![显示 SIP 阶梯的示意图](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="65de1-416">入站呼叫和用户是内部用户，但不与仅针对本地用户的 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="65de1-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="65de1-417">模式</span><span class="sxs-lookup"><span data-stu-id="65de1-417">Mode</span></span> |    <span data-ttu-id="65de1-418">用户</span><span class="sxs-lookup"><span data-stu-id="65de1-418">User</span></span> |  <span data-ttu-id="65de1-419">站点</span><span class="sxs-lookup"><span data-stu-id="65de1-419">Site</span></span> |  <span data-ttu-id="65de1-420">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="65de1-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="65de1-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="65de1-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="65de1-422">内部</span><span class="sxs-lookup"><span data-stu-id="65de1-422">Internal</span></span> |    <span data-ttu-id="65de1-423">不同于 SBC</span><span class="sxs-lookup"><span data-stu-id="65de1-423">Different from SBC</span></span> |    <span data-ttu-id="65de1-424">入站</span><span class="sxs-lookup"><span data-stu-id="65de1-424">Inbound</span></span> |

<span data-ttu-id="65de1-425">下图显示了具有 OnlyForLocalUsers 模式的入站呼叫，以及与 SBC 不在同一位置的内部用户。</span><span class="sxs-lookup"><span data-stu-id="65de1-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![显示 SIP 阶梯的示意图](media/direct-routing-media-op-17.png)









