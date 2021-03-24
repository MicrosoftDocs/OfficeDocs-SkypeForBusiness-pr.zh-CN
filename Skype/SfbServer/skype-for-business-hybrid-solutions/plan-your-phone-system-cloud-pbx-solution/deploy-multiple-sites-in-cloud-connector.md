---
title: 在云连接器中部署多个站点
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 了解如何在云连接器版本中部署多个 PSTN 站点。
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098398"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="fdadf-103">在云连接器中部署多个站点</span><span class="sxs-lookup"><span data-stu-id="fdadf-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="fdadf-104">云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="fdadf-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="fdadf-105">组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="fdadf-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="fdadf-106">了解如何在云连接器版本中部署多个 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="fdadf-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="fdadf-107">本节介绍如何在 PSTN 站点中部署 (公用电话) 网络。</span><span class="sxs-lookup"><span data-stu-id="fdadf-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="fdadf-108">使用与部署单个网站相同的步骤，一次部署一个站点。</span><span class="sxs-lookup"><span data-stu-id="fdadf-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="fdadf-109">本主题介绍多站点部署中的注意事项以及网站之间的差异。</span><span class="sxs-lookup"><span data-stu-id="fdadf-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="fdadf-110">多个公用电话交换网 (PSTN) 站点</span><span class="sxs-lookup"><span data-stu-id="fdadf-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="fdadf-111">下面显示了为不同 PSTN 站点部署 Skype for Business 云连接器版本的示例配置。</span><span class="sxs-lookup"><span data-stu-id="fdadf-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="fdadf-112">在开始部署之前，请确保配置设置正确。</span><span class="sxs-lookup"><span data-stu-id="fdadf-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="fdadf-113">PSTN 站点 1</span><span class="sxs-lookup"><span data-stu-id="fdadf-113">PSTN Site 1</span></span>
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="fdadf-114">PSTN 站点 2</span><span class="sxs-lookup"><span data-stu-id="fdadf-114">PSTN Site 2</span></span>
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="fdadf-115">对于要添加的每个 PSTN 站点，请按照在云连接器 [中部署单个站点中的步骤操作](deploy-a-single-site-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="fdadf-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fdadf-116">用于准备高可用性的共享文件夹 (HA) 每个 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="fdadf-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="fdadf-117">PSTN **站点之间的** 共享文件夹必须不同。</span><span class="sxs-lookup"><span data-stu-id="fdadf-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="fdadf-118">不要对多个网站使用相同的共享文件夹。></span><span class="sxs-lookup"><span data-stu-id="fdadf-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="fdadf-119">与多站点部署 (HA) 具有高可用性的单个站点</span><span class="sxs-lookup"><span data-stu-id="fdadf-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="fdadf-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="fdadf-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="fdadf-121">下表列出了支持 HA 的单站点和多站点部署之间的差异。</span><span class="sxs-lookup"><span data-stu-id="fdadf-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="fdadf-122">**类别**</span><span class="sxs-lookup"><span data-stu-id="fdadf-122">**Category**</span></span>|<span data-ttu-id="fdadf-123">**项目**</span><span class="sxs-lookup"><span data-stu-id="fdadf-123">**Item**</span></span>|<span data-ttu-id="fdadf-124">**具有 HA 的单站点**</span><span class="sxs-lookup"><span data-stu-id="fdadf-124">**Single-Site with HA**</span></span>|<span data-ttu-id="fdadf-125">**多站点**</span><span class="sxs-lookup"><span data-stu-id="fdadf-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fdadf-126">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-126">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-127">设备主机名</span><span class="sxs-lookup"><span data-stu-id="fdadf-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="fdadf-128">**不同** 设备</span><span class="sxs-lookup"><span data-stu-id="fdadf-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fdadf-129">**不同** PSTN 站点</span><span class="sxs-lookup"><span data-stu-id="fdadf-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-130">设置</span><span class="sxs-lookup"><span data-stu-id="fdadf-130">Setup</span></span>  <br/> |<span data-ttu-id="fdadf-131">共享文件夹</span><span class="sxs-lookup"><span data-stu-id="fdadf-131">Shared folder</span></span>  <br/> |<span data-ttu-id="fdadf-132">需要跨 **设备** 使用相同的共享文件夹</span><span class="sxs-lookup"><span data-stu-id="fdadf-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="fdadf-133">需要不同 **设备** 之间的不同共享文件夹</span><span class="sxs-lookup"><span data-stu-id="fdadf-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="fdadf-134">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-134">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="fdadf-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="fdadf-136">需要跨 **设备** 相同的域</span><span class="sxs-lookup"><span data-stu-id="fdadf-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="fdadf-137">需要跨 PSTN 站点相同的域</span><span class="sxs-lookup"><span data-stu-id="fdadf-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-138">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-138">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="fdadf-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="fdadf-140">不同设备域名和 **顺序** 应相同</span><span class="sxs-lookup"><span data-stu-id="fdadf-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="fdadf-141">各个 PSTN 网站的域名 **和顺序** 应该相同</span><span class="sxs-lookup"><span data-stu-id="fdadf-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-142">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-142">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-143">网站名称</span><span class="sxs-lookup"><span data-stu-id="fdadf-143">Site name</span></span>  <br/> |<span data-ttu-id="fdadf-144">**相同** 跨设备的网站名称</span><span class="sxs-lookup"><span data-stu-id="fdadf-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="fdadf-145">**不同** 跨 PSTN 站点的站点名称</span><span class="sxs-lookup"><span data-stu-id="fdadf-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-146">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-146">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-147">服务器名称</span><span class="sxs-lookup"><span data-stu-id="fdadf-147">Server names</span></span>  <br/> |<span data-ttu-id="fdadf-148">**不同** 设备</span><span class="sxs-lookup"><span data-stu-id="fdadf-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fdadf-149">**不同** PSTN 站点</span><span class="sxs-lookup"><span data-stu-id="fdadf-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-150">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-150">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-151">内部池 FQDN</span><span class="sxs-lookup"><span data-stu-id="fdadf-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="fdadf-152">**在设备** 之间相同</span><span class="sxs-lookup"><span data-stu-id="fdadf-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="fdadf-153">**在** PSTN 站点之间相同</span><span class="sxs-lookup"><span data-stu-id="fdadf-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-154">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-154">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-155">内部 IP</span><span class="sxs-lookup"><span data-stu-id="fdadf-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="fdadf-156">**不同** 设备</span><span class="sxs-lookup"><span data-stu-id="fdadf-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fdadf-157">**不同** PSTN 站点</span><span class="sxs-lookup"><span data-stu-id="fdadf-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-158">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-158">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-159">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="fdadf-159">External FQDN</span></span>  <br/> |<span data-ttu-id="fdadf-160">**在设备** 之间相同</span><span class="sxs-lookup"><span data-stu-id="fdadf-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="fdadf-161">**不同** PSTN 站点</span><span class="sxs-lookup"><span data-stu-id="fdadf-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-162">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-162">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-163">外部 IP</span><span class="sxs-lookup"><span data-stu-id="fdadf-163">External IPs</span></span>  <br/> |<span data-ttu-id="fdadf-164">**不同** 设备</span><span class="sxs-lookup"><span data-stu-id="fdadf-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fdadf-165">**不同** PSTN 站点</span><span class="sxs-lookup"><span data-stu-id="fdadf-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-166">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-166">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-167">PSTN GW 设置</span><span class="sxs-lookup"><span data-stu-id="fdadf-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="fdadf-168">**在设备** 之间相同</span><span class="sxs-lookup"><span data-stu-id="fdadf-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="fdadf-169">**不同** PSTN 站点</span><span class="sxs-lookup"><span data-stu-id="fdadf-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fdadf-170">配置</span><span class="sxs-lookup"><span data-stu-id="fdadf-170">Configure</span></span>  <br/> |<span data-ttu-id="fdadf-171">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="fdadf-171">DNS record</span></span>  <br/> |<span data-ttu-id="fdadf-172">添加具有相同的外部 **访问** FQDN 和 **不同** IP 地址的记录</span><span class="sxs-lookup"><span data-stu-id="fdadf-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="fdadf-173">添加具有不同的 **外部访问** FQN **和不同** IP 地址的记录</span><span class="sxs-lookup"><span data-stu-id="fdadf-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="fdadf-174">设置</span><span class="sxs-lookup"><span data-stu-id="fdadf-174">Setup</span></span>  <br/> |<span data-ttu-id="fdadf-175">混合租户</span><span class="sxs-lookup"><span data-stu-id="fdadf-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="fdadf-176">设置 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="fdadf-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="fdadf-177">设置用于回退的 PeerDestination</span><span class="sxs-lookup"><span data-stu-id="fdadf-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="fdadf-178">设置 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="fdadf-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="fdadf-179">设置用于回退的 PeerDestination</span><span class="sxs-lookup"><span data-stu-id="fdadf-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="fdadf-180">设置</span><span class="sxs-lookup"><span data-stu-id="fdadf-180">Setup</span></span>  <br/> |<span data-ttu-id="fdadf-181">网关</span><span class="sxs-lookup"><span data-stu-id="fdadf-181">Gateway</span></span>  <br/> |<span data-ttu-id="fdadf-182">此站点中的 MS GW **M：N** 映射</span><span class="sxs-lookup"><span data-stu-id="fdadf-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="fdadf-183">每个 PSTN 站点 (PSTN 网关) 应仅连接到同一站点中的中介 (服务器) 服务器</span><span class="sxs-lookup"><span data-stu-id="fdadf-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="fdadf-184">设置</span><span class="sxs-lookup"><span data-stu-id="fdadf-184">Setup</span></span>  <br/> |<span data-ttu-id="fdadf-185">User</span><span class="sxs-lookup"><span data-stu-id="fdadf-185">User</span></span>  <br/> |<span data-ttu-id="fdadf-186">设置 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="fdadf-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="fdadf-187">设置 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="fdadf-187">Set UserPSTNSettings</span></span>  <br/> |
