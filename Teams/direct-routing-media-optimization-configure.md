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
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121602"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="9a8e9-103">为直接路由配置本地媒体优化</span><span class="sxs-lookup"><span data-stu-id="9a8e9-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="9a8e9-104">本地媒体优化的配置基于由其他云语音功能（如基于位置的路由和动态紧急呼叫）通用的网络设置。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="9a8e9-105">若要了解有关网络区域、网络站点、网络子网和受信任的 IP 地址的详细信息，请参阅[云语音功能的网络设置](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="9a8e9-106">在配置本地媒体优化之前，请参阅[用于直接路由的本地媒体优化](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="9a8e9-107">若要配置本地媒体优化，需要执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="9a8e9-108">你可以使用团队管理员中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="9a8e9-109">有关详细信息，请参阅[管理网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="9a8e9-110">配置用户和 SBC 网站（如本文中所述）。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="9a8e9-111">将 SBCs 配置为本地媒体优化（根据 SBC 供应商的规范）。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="9a8e9-112">下图显示了本文的示例中所用的网络设置。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="9a8e9-113">![显示网络设置示例的图表](media/direct-routing-media-op-9.png "网络设置示例")</span><span class="sxs-lookup"><span data-stu-id="9a8e9-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="9a8e9-114">配置用户和 SBC 网站</span><span class="sxs-lookup"><span data-stu-id="9a8e9-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="9a8e9-115">要配置用户和 SBC 网站，你需要：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="9a8e9-116">[管理外部受信任的 IP 地址](#manage-external-trusted-ip-addresses)。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="9a8e9-117">通过配置网络区域、网络站点和网络子网来[定义网络拓扑](#define-the-network-topology)。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="9a8e9-118">通过将 SBC （s）分配给具有相关模式和代理 SBC 值的站点来[定义虚拟网络拓扑](#define-the-virtual-network-topology)。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="9a8e9-119">根据 SBC 供应商的规范，配置用于本地媒体优化的 SBC</span><span class="sxs-lookup"><span data-stu-id="9a8e9-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="9a8e9-120">本文介绍 Microsoft 组件的配置。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="9a8e9-121">有关 SBC 配置的信息，请参阅 SBC 供应商的文档。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="9a8e9-122">以下 SBC 供应商支持本地媒体优化：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="9a8e9-123">供应商</span><span class="sxs-lookup"><span data-stu-id="9a8e9-123">Vendor</span></span> | <span data-ttu-id="9a8e9-124">产品</span><span class="sxs-lookup"><span data-stu-id="9a8e9-124">Product</span></span> |    <span data-ttu-id="9a8e9-125">软件版本</span><span class="sxs-lookup"><span data-stu-id="9a8e9-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="9a8e9-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="9a8e9-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="9a8e9-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="9a8e9-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="9a8e9-128">7.20</span><span class="sxs-lookup"><span data-stu-id="9a8e9-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="9a8e9-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="9a8e9-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="9a8e9-130">7.20</span><span class="sxs-lookup"><span data-stu-id="9a8e9-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="9a8e9-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="9a8e9-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="9a8e9-132">7.20</span><span class="sxs-lookup"><span data-stu-id="9a8e9-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="9a8e9-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="9a8e9-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="9a8e9-134">7.20</span><span class="sxs-lookup"><span data-stu-id="9a8e9-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="9a8e9-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="9a8e9-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="9a8e9-136">7.20</span><span class="sxs-lookup"><span data-stu-id="9a8e9-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="9a8e9-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="9a8e9-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="9a8e9-138">7.20</span><span class="sxs-lookup"><span data-stu-id="9a8e9-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="9a8e9-139">Mediant 虚拟版 SBC</span><span class="sxs-lookup"><span data-stu-id="9a8e9-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="9a8e9-140">7.20</span><span class="sxs-lookup"><span data-stu-id="9a8e9-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="9a8e9-141">Mediant 云版 SBC</span><span class="sxs-lookup"><span data-stu-id="9a8e9-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="9a8e9-142">7.20</span><span class="sxs-lookup"><span data-stu-id="9a8e9-142">7.20A.256</span></span> |
| [<span data-ttu-id="9a8e9-143">功能区 SBC 核心</span><span class="sxs-lookup"><span data-stu-id="9a8e9-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="9a8e9-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="9a8e9-144">SBC 5110</span></span>         | <span data-ttu-id="9a8e9-145">8.2</span><span class="sxs-lookup"><span data-stu-id="9a8e9-145">8.2</span></span>  |
|            |  <span data-ttu-id="9a8e9-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="9a8e9-146">SBC 5210</span></span>         | <span data-ttu-id="9a8e9-147">8.2</span><span class="sxs-lookup"><span data-stu-id="9a8e9-147">8.2</span></span>  |
|            |  <span data-ttu-id="9a8e9-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="9a8e9-148">SBC 5400</span></span>         | <span data-ttu-id="9a8e9-149">8.2</span><span class="sxs-lookup"><span data-stu-id="9a8e9-149">8.2</span></span>  |
|            |  <span data-ttu-id="9a8e9-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="9a8e9-150">SBC 7000</span></span>         | <span data-ttu-id="9a8e9-151">8.2</span><span class="sxs-lookup"><span data-stu-id="9a8e9-151">8.2</span></span>  |
|            |  <span data-ttu-id="9a8e9-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="9a8e9-152">SBC SWe</span></span>          | <span data-ttu-id="9a8e9-153">8.2</span><span class="sxs-lookup"><span data-stu-id="9a8e9-153">8.2</span></span>  |
| [<span data-ttu-id="9a8e9-154">功能区 SBC 边缘</span><span class="sxs-lookup"><span data-stu-id="9a8e9-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="9a8e9-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="9a8e9-155">SBC SWe Lite</span></span> | <span data-ttu-id="9a8e9-156">8.1.5 （内部版本239）</span><span class="sxs-lookup"><span data-stu-id="9a8e9-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="9a8e9-157">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="9a8e9-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="9a8e9-158">anynode</span><span class="sxs-lookup"><span data-stu-id="9a8e9-158">anynode</span></span>          | <span data-ttu-id="9a8e9-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="9a8e9-159">4.0.1+</span></span> |
| [<span data-ttu-id="9a8e9-160">Oracle</span><span class="sxs-lookup"><span data-stu-id="9a8e9-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="9a8e9-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="9a8e9-161">AP 1100</span></span> | <span data-ttu-id="9a8e9-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="9a8e9-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="9a8e9-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="9a8e9-163">AP 3900</span></span> | <span data-ttu-id="9a8e9-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="9a8e9-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="9a8e9-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="9a8e9-165">AP 4600</span></span> | <span data-ttu-id="9a8e9-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="9a8e9-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="9a8e9-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="9a8e9-167">AP 6300</span></span> | <span data-ttu-id="9a8e9-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="9a8e9-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="9a8e9-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="9a8e9-169">AP 6350</span></span> | <span data-ttu-id="9a8e9-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="9a8e9-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="9a8e9-171">VME</span><span class="sxs-lookup"><span data-stu-id="9a8e9-171">VME</span></span>     | <span data-ttu-id="9a8e9-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="9a8e9-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="9a8e9-173">管理外部受信任的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="9a8e9-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="9a8e9-174">外部受信任的 Ip 是企业网络的 Internet 外部 Ip。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="9a8e9-175">这些 IP 是 Microsoft 团队客户端连接到 Microsoft 365 时使用的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="9a8e9-176">你需要为每个具有使用本地媒体优化的用户的网站添加这些外部 Ip。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="9a8e9-177">若要为每个网站添加公共 IP 地址，请使用 CsTenantTrustedIPAddress cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="9a8e9-178">你可以为租户定义无限数量的受信任 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="9a8e9-179">如果 Microsoft 365 所看到的外部 IPs 是 IPv4 和 IPv6 地址，则需要添加这两种类型的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="9a8e9-180">对于 IPv4，请使用掩码32。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="9a8e9-181">对于 IPv6，请使用掩码128。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="9a8e9-182">你可以通过在 cmdlet 上指定不同的 MaskBits 来添加单个外部 IP 地址和外部 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="9a8e9-183">添加受信任的 IP 地址的示例。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="9a8e9-184">定义网络拓扑</span><span class="sxs-lookup"><span data-stu-id="9a8e9-184">Define the network topology</span></span>

<span data-ttu-id="9a8e9-185">本节介绍如何为你的网络拓扑定义网络区域、网络站点和网络子网。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="9a8e9-186">所有参数都区分大小写，因此你需要确保使用在安装过程中使用的相同大小写。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="9a8e9-187">（例如，GatewaySiteID 值 "越南" 和 "越南" 将被视为不同的网站。）</span><span class="sxs-lookup"><span data-stu-id="9a8e9-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="9a8e9-188">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="9a8e9-188">Define network regions</span></span>

<span data-ttu-id="9a8e9-189">若要定义网络区域，请使用 CsTenantNetworkRegion cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="9a8e9-190">RegionID 参数是一个逻辑名称，表示区域的地理位置，并且不具有依赖关系或限制。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="9a8e9-191">CentralSite <site ID> 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="9a8e9-192">下面的示例创建了一个名为 APAC 的网络区域：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="9a8e9-193">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="9a8e9-193">Define network sites</span></span>

<span data-ttu-id="9a8e9-194">若要定义网络网站，请使用 CsTenantNetworkSite cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="9a8e9-195">每个网络站点都必须与一个网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="9a8e9-196">以下示例在 APAC 区域中创建三个新的网络站点、越南、印度尼西亚和新加坡：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="9a8e9-197">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="9a8e9-197">Define network subnets</span></span>

<span data-ttu-id="9a8e9-198">若要定义网络子网并将其与网络站点关联，请使用 CsTenantNetworkSubnet cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="9a8e9-199">每个网络子网只能与一个网站相关联。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="9a8e9-200">以下示例定义了三个网络子网，并将其与三个网络站点（越南、印度尼西亚和新加坡）关联：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="9a8e9-201">定义虚拟网络拓扑</span><span class="sxs-lookup"><span data-stu-id="9a8e9-201">Define the virtual network topology</span></span> 

<span data-ttu-id="9a8e9-202">首先，租户管理员使用 CsOnlinePSTNGateway cmdlet 为每个相关 SBC 创建新的 SBC 配置。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="9a8e9-203">租户管理员通过使用 CsOnlinePSTNGateway cmdlet 指定 PSTN 网关对象的网络站点来定义虚拟网络拓扑：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="9a8e9-204">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-204">Note the following:</span></span> 
   - <span data-ttu-id="9a8e9-205">如果客户有单个 SBC，则-ProxySBC 参数必须是必需的 $null 或 SBC FQDN 值（具有集中中继方案的中心 SBC）。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="9a8e9-206">必须将-MediaBypass 参数设置为 $true，才能支持本地媒体优化。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="9a8e9-207">如果 SBC 没有-BypassMode 参数集，则不会发送 X 毫秒标头。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="9a8e9-208">所有参数都区分大小写，因此你需要确保使用的是在安装期间使用的相同大小写。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="9a8e9-209">（例如，GatewaySiteID 值 "越南" 和 "越南" 将被视为不同的网站。）</span><span class="sxs-lookup"><span data-stu-id="9a8e9-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="9a8e9-210">以下示例将3个 SBCs 添加到 APAC 区域中的网络站点越南、印度尼西亚和新加坡，模式始终为 "始终绕过"：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="9a8e9-211">注意：若要确保在同时配置本地媒体优化和基于位置的路由（LBR）时不间断的操作，必须通过将 GatewaySiteLbrEnabled 参数设置为每个下游 SBC $true 来为 LBR 启用下游 SBCs。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="9a8e9-212">（对于代理 SBC，此设置不是必需的。）</span><span class="sxs-lookup"><span data-stu-id="9a8e9-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="9a8e9-213">根据上述信息，直接路由将包括三个专用 SIP 标题到 SIP 邀请和重新邀请，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="9a8e9-214">如果定义了 BypassMode，则在邀请和重新邀请时直接路由中引入了 X-MS 标题：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="9a8e9-215">标题名称</span><span class="sxs-lookup"><span data-stu-id="9a8e9-215">Header name</span></span> | <span data-ttu-id="9a8e9-216">相对值</span><span class="sxs-lookup"><span data-stu-id="9a8e9-216">Values</span></span> | <span data-ttu-id="9a8e9-217">备注</span><span class="sxs-lookup"><span data-stu-id="9a8e9-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="9a8e9-218">X 毫秒-UserLocation</span><span class="sxs-lookup"><span data-stu-id="9a8e9-218">X-MS-UserLocation</span></span> | <span data-ttu-id="9a8e9-219">内部/外部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-219">internal/external</span></span> | <span data-ttu-id="9a8e9-220">指示用户是内部还是外部用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="9a8e9-221">请求 URI 邀请 sip： + 84439263000@VNsbc.contoso.com SIP/2。0</span><span class="sxs-lookup"><span data-stu-id="9a8e9-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="9a8e9-222">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="9a8e9-222">SBC FQDN</span></span> | <span data-ttu-id="9a8e9-223">即使 SBC 未直接连接到直接路由，仍针对呼叫的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9a8e9-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="9a8e9-224">X 毫秒-MediaPath</span><span class="sxs-lookup"><span data-stu-id="9a8e9-224">X-MS-MediaPath</span></span> | <span data-ttu-id="9a8e9-225">示例： proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="9a8e9-226">应用于用户和目标 SBC 之间的媒体路径的 SBCs 顺序。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="9a8e9-227">最终的 SBC 始终持续</span><span class="sxs-lookup"><span data-stu-id="9a8e9-227">The final SBC is always last</span></span> |
| <span data-ttu-id="9a8e9-228">X 毫秒-UserSite</span><span class="sxs-lookup"><span data-stu-id="9a8e9-228">X-MS-UserSite</span></span> | <span data-ttu-id="9a8e9-229">usersiteID</span><span class="sxs-lookup"><span data-stu-id="9a8e9-229">usersiteID</span></span> | <span data-ttu-id="9a8e9-230">租户管理员定义的字符串</span><span class="sxs-lookup"><span data-stu-id="9a8e9-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="9a8e9-231">通话流程</span><span class="sxs-lookup"><span data-stu-id="9a8e9-231">Call flows</span></span> 

<span data-ttu-id="9a8e9-232">以下显示了两种模式的通话流：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="9a8e9-233">始终绕过</span><span class="sxs-lookup"><span data-stu-id="9a8e9-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="9a8e9-234">仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="9a8e9-235">始终绕过模式</span><span class="sxs-lookup"><span data-stu-id="9a8e9-235">Always Bypass mode</span></span>

<span data-ttu-id="9a8e9-236">始终绕过模式是最简单的配置选项。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="9a8e9-237">租户管理员可以为所有用户和 SBCs 配置单个网站（如果所有 SBCs 均可从任何网站访问）。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="9a8e9-238">在以下情况下，示例显示 "始终绕过" 模式：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="9a8e9-239">出站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="9a8e9-240">入站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="9a8e9-241">出站呼叫和用户是外部的</span><span class="sxs-lookup"><span data-stu-id="9a8e9-241">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="9a8e9-242">入站呼叫和用户是外部的</span><span class="sxs-lookup"><span data-stu-id="9a8e9-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="9a8e9-243">下表显示了示例中使用的 FQDN 和 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="9a8e9-244">FQDN</span><span class="sxs-lookup"><span data-stu-id="9a8e9-244">FQDN</span></span> | <span data-ttu-id="9a8e9-245">SBC 外部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="9a8e9-245">SBC external IP address</span></span> | <span data-ttu-id="9a8e9-246">SBC 内部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="9a8e9-246">SBC internal IP Address</span></span> | <span data-ttu-id="9a8e9-247">内部子网</span><span class="sxs-lookup"><span data-stu-id="9a8e9-247">Internal subnet</span></span> | <span data-ttu-id="9a8e9-248">位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-248">Location</span></span> | <span data-ttu-id="9a8e9-249">外部 NAT （受信任的 IP）</span><span class="sxs-lookup"><span data-stu-id="9a8e9-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="9a8e9-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="9a8e9-251">无</span><span class="sxs-lookup"><span data-stu-id="9a8e9-251">None</span></span> | <span data-ttu-id="9a8e9-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="9a8e9-252">192.168.1.5</span></span> | <span data-ttu-id="9a8e9-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="9a8e9-253">192.168.1.0/24</span></span> | <span data-ttu-id="9a8e9-254">越南</span><span class="sxs-lookup"><span data-stu-id="9a8e9-254">Vietnam</span></span> | <span data-ttu-id="9a8e9-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="9a8e9-255">172.16.240.110</span></span> |
| <span data-ttu-id="9a8e9-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="9a8e9-257">无</span><span class="sxs-lookup"><span data-stu-id="9a8e9-257">None</span></span> | <span data-ttu-id="9a8e9-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="9a8e9-258">192.168.2.5</span></span> | <span data-ttu-id="9a8e9-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="9a8e9-259">192.168.2.0/24</span></span> | <span data-ttu-id="9a8e9-260">印度尼西亚</span><span class="sxs-lookup"><span data-stu-id="9a8e9-260">Indonesia</span></span> | <span data-ttu-id="9a8e9-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="9a8e9-261">172.16.240.120</span></span> |
| <span data-ttu-id="9a8e9-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="9a8e9-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="9a8e9-263">172.16.240.133</span></span> | <span data-ttu-id="9a8e9-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="9a8e9-264">192.168.3.5</span></span> | <span data-ttu-id="9a8e9-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="9a8e9-265">192.168.3.0/24</span></span> | <span data-ttu-id="9a8e9-266">新加坡</span><span class="sxs-lookup"><span data-stu-id="9a8e9-266">Singapore</span></span> | <span data-ttu-id="9a8e9-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="9a8e9-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="9a8e9-268">出站呼叫，并且用户与具有始终绕过的 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="9a8e9-269">众</span><span class="sxs-lookup"><span data-stu-id="9a8e9-269">Mode</span></span> |    <span data-ttu-id="9a8e9-270">用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-270">User</span></span> |  <span data-ttu-id="9a8e9-271">位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-271">Location</span></span> |  <span data-ttu-id="9a8e9-272">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="9a8e9-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="9a8e9-273">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="9a8e9-273">AlwaysBypass</span></span> |    <span data-ttu-id="9a8e9-274">内部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-274">Internal</span></span> |  <span data-ttu-id="9a8e9-275">与 SBC 相同的网站</span><span class="sxs-lookup"><span data-stu-id="9a8e9-275">The same site as SBC</span></span> |  <span data-ttu-id="9a8e9-276">出站</span><span class="sxs-lookup"><span data-stu-id="9a8e9-276">Outbound</span></span> |

<span data-ttu-id="9a8e9-277">下表显示了最终用户配置和操作：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="9a8e9-278">用户物理位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-278">User physical location</span></span>| <span data-ttu-id="9a8e9-279">用户拨打或接听号码</span><span class="sxs-lookup"><span data-stu-id="9a8e9-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="9a8e9-280">用户电话号码</span><span class="sxs-lookup"><span data-stu-id="9a8e9-280">User phone number</span></span>  | <span data-ttu-id="9a8e9-281">联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="9a8e9-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="9a8e9-282">针对 SBC 配置的模式</span><span class="sxs-lookup"><span data-stu-id="9a8e9-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="9a8e9-283">越南</span><span class="sxs-lookup"><span data-stu-id="9a8e9-283">Vietnam</span></span> | <span data-ttu-id="9a8e9-284">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="9a8e9-284">+84 4 3926 3000</span></span> | <span data-ttu-id="9a8e9-285">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="9a8e9-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="9a8e9-286">优先级1： ^ \+ 84 （\d {9} ） $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="9a8e9-287">优先级2：. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="9a8e9-288">VNsbc.contoso.com-始终绕过</span><span class="sxs-lookup"><span data-stu-id="9a8e9-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="9a8e9-289">proxysbc.contoso.com-始终绕过</span><span class="sxs-lookup"><span data-stu-id="9a8e9-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="9a8e9-290">下图显示了具有 "始终绕过" 模式的出站呼叫和用户位于 SBC 所在位置的 SIP 阶梯。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="9a8e9-291">![显示出站通话的图表](media/direct-routing-media-op-10.png "拨出电话")</span><span class="sxs-lookup"><span data-stu-id="9a8e9-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="9a8e9-292">下表显示了直接路由发送的 X-MS 标题：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="9a8e9-293">参数</span><span class="sxs-lookup"><span data-stu-id="9a8e9-293">Parameter</span></span> | <span data-ttu-id="9a8e9-294">解释</span><span class="sxs-lookup"><span data-stu-id="9a8e9-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="9a8e9-295">邀请 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="9a8e9-296">在联机语音路由策略中定义的 SBC 的目标 FQDN 在请求 URI 中发送</span><span class="sxs-lookup"><span data-stu-id="9a8e9-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="9a8e9-297">X-MS-UserLocation：内部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="9a8e9-298">指示用户位于企业网络内的字段</span><span class="sxs-lookup"><span data-stu-id="9a8e9-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="9a8e9-299">X-MS-MediaPath： VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="9a8e9-300">指定客户端必须遍历到目标 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="9a8e9-301">在这种情况下，我们始终绕过，并且客户端是以标题中的唯一名称形式发送的目标名称。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="9a8e9-302">X-MS-UserSite：越南</span><span class="sxs-lookup"><span data-stu-id="9a8e9-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="9a8e9-303">用户所在网站内指示的字段。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="9a8e9-304">入站呼叫和用户与具有始终绕过的 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="9a8e9-305">众</span><span class="sxs-lookup"><span data-stu-id="9a8e9-305">Mode</span></span> |    <span data-ttu-id="9a8e9-306">用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-306">User</span></span> |  <span data-ttu-id="9a8e9-307">位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-307">Location</span></span> |  <span data-ttu-id="9a8e9-308">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="9a8e9-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="9a8e9-309">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="9a8e9-309">AlwaysBypass</span></span> |    <span data-ttu-id="9a8e9-310">内部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-310">Internal</span></span> | <span data-ttu-id="9a8e9-311">与 SBC 相同的网站</span><span class="sxs-lookup"><span data-stu-id="9a8e9-311">The same site as SBC</span></span> | <span data-ttu-id="9a8e9-312">封</span><span class="sxs-lookup"><span data-stu-id="9a8e9-312">Inbound</span></span> |


<span data-ttu-id="9a8e9-313">在入站呼叫中，用户的位置是未知的，并且 SBC 必须猜测用户所在的位置。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="9a8e9-314">如果猜测不正确，则需要重新邀请。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="9a8e9-315">这种情况假设用户是内部用户，媒体可以直接流向，不需要执行其他操作（重新邀请）。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="9a8e9-316">连接到直接路由服务的 SBC 通过提供记录-路由和联系人字段来报告发起的 SBC 位置。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="9a8e9-317">根据这些字段，媒体路径由直接路由计算。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="9a8e9-318">注意：假设用户可以有多个终结点，则不可能支持183。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="9a8e9-319">在这种情况下，直接路由将始终使用180铃声。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="9a8e9-320">下图显示了具有 AlwaysBypass 模式的入站调用中的 SIP 阶梯，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="9a8e9-322">出站呼叫和用户是具有始终绕过的外部呼叫</span><span class="sxs-lookup"><span data-stu-id="9a8e9-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="9a8e9-323">众</span><span class="sxs-lookup"><span data-stu-id="9a8e9-323">Mode</span></span> |    <span data-ttu-id="9a8e9-324">用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-324">User</span></span> |  <span data-ttu-id="9a8e9-325">站点</span><span class="sxs-lookup"><span data-stu-id="9a8e9-325">Site</span></span> |  <span data-ttu-id="9a8e9-326">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="9a8e9-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="9a8e9-327">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="9a8e9-327">AlwaysBypass</span></span> |  <span data-ttu-id="9a8e9-328">外部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-328">External</span></span> |  <span data-ttu-id="9a8e9-329">不适用</span><span class="sxs-lookup"><span data-stu-id="9a8e9-329">N/A</span></span> | <span data-ttu-id="9a8e9-330">出站</span><span class="sxs-lookup"><span data-stu-id="9a8e9-330">Outbound</span></span> |


<span data-ttu-id="9a8e9-331">下图显示了具有 AlwaysBypass 模式的出站呼叫的 SIP 阶梯，并且用户是外部的：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-12.png)

<span data-ttu-id="9a8e9-333">下表显示了直接路由服务发送的 X-MS 标头：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="9a8e9-334">参数</span><span class="sxs-lookup"><span data-stu-id="9a8e9-334">Parameter</span></span> |   <span data-ttu-id="9a8e9-335">解释</span><span class="sxs-lookup"><span data-stu-id="9a8e9-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="9a8e9-336">邀请 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="9a8e9-337">在联机语音路由策略中定义的 SBC 的目标 FQDN 在请求 URI 中发送。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="9a8e9-338">X-UserLocation：外部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="9a8e9-339">指示用户位于企业网络外部的字段。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="9a8e9-340">X-MS-MediaPath： proxysbc.contoso.com，VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="9a8e9-341">指定客户端必须遍历到目标 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="9a8e9-342">在此情况下，我们始终绕过，并且客户端是外部客户端。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="9a8e9-343">入站呼叫和用户是具有始终绕过的外部呼叫</span><span class="sxs-lookup"><span data-stu-id="9a8e9-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="9a8e9-344">众</span><span class="sxs-lookup"><span data-stu-id="9a8e9-344">Mode</span></span> | <span data-ttu-id="9a8e9-345">用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-345">User</span></span> | <span data-ttu-id="9a8e9-346">站点</span><span class="sxs-lookup"><span data-stu-id="9a8e9-346">Site</span></span> |  <span data-ttu-id="9a8e9-347">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="9a8e9-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="9a8e9-348">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="9a8e9-348">AlwaysBypass</span></span> |  <span data-ttu-id="9a8e9-349">外部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-349">External</span></span> |  <span data-ttu-id="9a8e9-350">不适用</span><span class="sxs-lookup"><span data-stu-id="9a8e9-350">N/A</span></span> |   <span data-ttu-id="9a8e9-351">封</span><span class="sxs-lookup"><span data-stu-id="9a8e9-351">Inbound</span></span> |

<span data-ttu-id="9a8e9-352">对于入站呼叫，连接到直接路由的 SBC 需要发送重新邀请（默认情况下，始终提供本地媒体候选人）（如果用户是外部的位置）。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="9a8e9-353">X-MediaPath 是基于记录路由和指定的 SBC 用户计算的。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="9a8e9-354">下图显示了具有 AlwaysBypass 模式的入站呼叫的 SIP 阶梯，并且该用户是外部用户。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="9a8e9-356">仅适用于本地用户模式</span><span class="sxs-lookup"><span data-stu-id="9a8e9-356">Only for local users mode</span></span>

<span data-ttu-id="9a8e9-357">仅当用户与 SBC 位于同一位置时，才会提供目标 SBC 的本地媒体候选项。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="9a8e9-358">在所有其他情况下，媒体将通过代理 SBC 的内部或外部 IP 进行通信。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="9a8e9-359">介绍以下方案：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="9a8e9-360">出站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="9a8e9-361">入站呼叫和用户与 SBC 位于同一位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="9a8e9-362">用户与 SBC 不在同一位置，但位于企业网络中</span><span class="sxs-lookup"><span data-stu-id="9a8e9-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="9a8e9-363">入站呼叫和用户是内部的，但与 SBC 不在同一位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="9a8e9-364">下表显示最终用户配置和操作：</span><span class="sxs-lookup"><span data-stu-id="9a8e9-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="9a8e9-365">用户物理位置</span><span class="sxs-lookup"><span data-stu-id="9a8e9-365">User physical location</span></span> |  <span data-ttu-id="9a8e9-366">用户拨打或接听号码</span><span class="sxs-lookup"><span data-stu-id="9a8e9-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="9a8e9-367">用户电话号码</span><span class="sxs-lookup"><span data-stu-id="9a8e9-367">User phone number</span></span> | <span data-ttu-id="9a8e9-368">联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="9a8e9-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="9a8e9-369">针对 SBC 配置的模式</span><span class="sxs-lookup"><span data-stu-id="9a8e9-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="9a8e9-370">越南</span><span class="sxs-lookup"><span data-stu-id="9a8e9-370">Vietnam</span></span> | <span data-ttu-id="9a8e9-371">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="9a8e9-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="9a8e9-372">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="9a8e9-372">+84 4 5555 5555</span></span> | <span data-ttu-id="9a8e9-373">优先级1： ^ \+ 84 （\d {9} ） $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="9a8e9-374">优先级2：. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a8e9-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="9a8e9-375">VNsbc.contoso.com-OnlyForLocalUsers Proxysbc.contoso.com-始终绕过</span><span class="sxs-lookup"><span data-stu-id="9a8e9-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="9a8e9-376">出站呼叫和用户与 SBC 在同一位置，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="9a8e9-377">众</span><span class="sxs-lookup"><span data-stu-id="9a8e9-377">Mode</span></span> | <span data-ttu-id="9a8e9-378">用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-378">User</span></span> | <span data-ttu-id="9a8e9-379">站点</span><span class="sxs-lookup"><span data-stu-id="9a8e9-379">Site</span></span> | <span data-ttu-id="9a8e9-380">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="9a8e9-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="9a8e9-381">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="9a8e9-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="9a8e9-382">内部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-382">Internal</span></span> |<span data-ttu-id="9a8e9-383">与 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="9a8e9-383">Same as SBC</span></span>   | <span data-ttu-id="9a8e9-384">出站</span><span class="sxs-lookup"><span data-stu-id="9a8e9-384">Outbound</span></span> |

<span data-ttu-id="9a8e9-385">下图显示了具有 OnlyForLocalUsers 模式的出站调用，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="9a8e9-386">这是[当用户与 SBC 位于同一位置时，在出站呼叫](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)中显示的相同流。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="9a8e9-388">入站呼叫和用户与 SBC 在同一位置，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="9a8e9-389">众</span><span class="sxs-lookup"><span data-stu-id="9a8e9-389">Mode</span></span> | <span data-ttu-id="9a8e9-390">用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-390">User</span></span> | <span data-ttu-id="9a8e9-391">站点</span><span class="sxs-lookup"><span data-stu-id="9a8e9-391">Site</span></span> | <span data-ttu-id="9a8e9-392">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="9a8e9-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="9a8e9-393">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="9a8e9-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="9a8e9-394">内部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-394">Internal</span></span> | <span data-ttu-id="9a8e9-395">与 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="9a8e9-395">Same as SBC</span></span> | <span data-ttu-id="9a8e9-396">封</span><span class="sxs-lookup"><span data-stu-id="9a8e9-396">Inbound</span></span> |

<span data-ttu-id="9a8e9-397">下图显示了具有 OnlyForLocalUsers 模式的入站调用，并且用户与 SBC 位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="9a8e9-398">[当用户与 SBC 位于同一位置时](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)，这是与入站通话中所示相同的流。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="9a8e9-400">用户与 SBC 不在同一位置，但位于企业网络中，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="9a8e9-401">众</span><span class="sxs-lookup"><span data-stu-id="9a8e9-401">Mode</span></span> | <span data-ttu-id="9a8e9-402">用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-402">User</span></span> | <span data-ttu-id="9a8e9-403">站点</span><span class="sxs-lookup"><span data-stu-id="9a8e9-403">Site</span></span> |<span data-ttu-id="9a8e9-404">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="9a8e9-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="9a8e9-405">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="9a8e9-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="9a8e9-406">内部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-406">Internal</span></span> |   <span data-ttu-id="9a8e9-407">与 SBC 不同</span><span class="sxs-lookup"><span data-stu-id="9a8e9-407">Different from SBC</span></span> | <span data-ttu-id="9a8e9-408">出站</span><span class="sxs-lookup"><span data-stu-id="9a8e9-408">Outbound</span></span> |

<span data-ttu-id="9a8e9-409">直接路由基于在 SBC 上配置的用户和模式的已报告位置计算 X MediaPath。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="9a8e9-410">下图显示了具有 OnlyForLocalUsers 模式的出站呼叫，以及与 SBC 不在同一位置的内部用户。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="9a8e9-412">入站呼叫和用户是内部的，但与 SBC 不在同一位置，仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="9a8e9-413">众</span><span class="sxs-lookup"><span data-stu-id="9a8e9-413">Mode</span></span> |    <span data-ttu-id="9a8e9-414">用户</span><span class="sxs-lookup"><span data-stu-id="9a8e9-414">User</span></span> |  <span data-ttu-id="9a8e9-415">站点</span><span class="sxs-lookup"><span data-stu-id="9a8e9-415">Site</span></span> |  <span data-ttu-id="9a8e9-416">呼叫方向</span><span class="sxs-lookup"><span data-stu-id="9a8e9-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="9a8e9-417">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="9a8e9-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="9a8e9-418">内部</span><span class="sxs-lookup"><span data-stu-id="9a8e9-418">Internal</span></span> |    <span data-ttu-id="9a8e9-419">与 SBC 不同</span><span class="sxs-lookup"><span data-stu-id="9a8e9-419">Different from SBC</span></span> |    <span data-ttu-id="9a8e9-420">封</span><span class="sxs-lookup"><span data-stu-id="9a8e9-420">Inbound</span></span> |

<span data-ttu-id="9a8e9-421">下图显示了具有 OnlyForLocalUsers 模式的入站呼叫，以及与 SBC 不在同一位置的内部用户。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![显示 SIP 阶梯的图表](media/direct-routing-media-op-17.png)









