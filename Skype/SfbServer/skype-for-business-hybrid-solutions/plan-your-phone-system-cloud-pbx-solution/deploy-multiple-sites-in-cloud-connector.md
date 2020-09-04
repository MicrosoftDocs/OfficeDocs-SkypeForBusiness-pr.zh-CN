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
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358918"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="621eb-103">在云连接器中部署多个站点</span><span class="sxs-lookup"><span data-stu-id="621eb-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="621eb-104">云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。</span><span class="sxs-lookup"><span data-stu-id="621eb-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="621eb-105">组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。</span><span class="sxs-lookup"><span data-stu-id="621eb-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="621eb-106">了解如何在云连接器版本中部署多个 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="621eb-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="621eb-107">本节介绍如何将多个公用电话交换电话网络 (PSTN) 站点部署。</span><span class="sxs-lookup"><span data-stu-id="621eb-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="621eb-108">使用与部署单个网站相同的步骤一次部署一个网站。</span><span class="sxs-lookup"><span data-stu-id="621eb-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="621eb-109">本主题介绍多站点部署中的网站之间的注意事项和差异。</span><span class="sxs-lookup"><span data-stu-id="621eb-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="621eb-110"> (PSTN) 站点的多个公用电话交换电话网络</span><span class="sxs-lookup"><span data-stu-id="621eb-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="621eb-111">下面显示了为不同 PSTN 站点部署 Skype for Business 云连接器版本的示例配置。</span><span class="sxs-lookup"><span data-stu-id="621eb-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="621eb-112">在开始部署之前，请确保您的配置设置正确。</span><span class="sxs-lookup"><span data-stu-id="621eb-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="621eb-113">PSTN 站点1</span><span class="sxs-lookup"><span data-stu-id="621eb-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="621eb-114">PSTN 站点2</span><span class="sxs-lookup"><span data-stu-id="621eb-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="621eb-115">对于要添加的每个 PSTN 站点，按照 "在 [云连接器中部署单个站点](deploy-a-single-site-in-cloud-connector.md)" 中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="621eb-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="621eb-116">为每个 PSTN 站点准备高可用性 (HA) 的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="621eb-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="621eb-117">PSTN 站点之间的共享文件夹 **必须** 不同。</span><span class="sxs-lookup"><span data-stu-id="621eb-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="621eb-118">请勿对多个网站使用相同的共享文件夹。 ></span><span class="sxs-lookup"><span data-stu-id="621eb-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="621eb-119">与多站点部署相比具有高可用性 (HA) 的单个站点</span><span class="sxs-lookup"><span data-stu-id="621eb-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="621eb-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="621eb-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="621eb-121">下表列出了具有 HA 支持的单站点和多站点部署之间的差异。</span><span class="sxs-lookup"><span data-stu-id="621eb-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="621eb-122">**类别**</span><span class="sxs-lookup"><span data-stu-id="621eb-122">**Category**</span></span>|<span data-ttu-id="621eb-123">**项**</span><span class="sxs-lookup"><span data-stu-id="621eb-123">**Item**</span></span>|<span data-ttu-id="621eb-124">**具有 HA 的单站点**</span><span class="sxs-lookup"><span data-stu-id="621eb-124">**Single-Site with HA**</span></span>|<span data-ttu-id="621eb-125">**多站点**</span><span class="sxs-lookup"><span data-stu-id="621eb-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="621eb-126">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-126">Configure</span></span>  <br/> |<span data-ttu-id="621eb-127">设备主机名</span><span class="sxs-lookup"><span data-stu-id="621eb-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="621eb-128">跨设备**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="621eb-129">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-130">设置</span><span class="sxs-lookup"><span data-stu-id="621eb-130">Setup</span></span>  <br/> |<span data-ttu-id="621eb-131">共享文件夹</span><span class="sxs-lookup"><span data-stu-id="621eb-131">Shared folder</span></span>  <br/> |<span data-ttu-id="621eb-132">跨设备需要 **相同** 的共享文件夹</span><span class="sxs-lookup"><span data-stu-id="621eb-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="621eb-133">跨设备需要 **不同** 的共享文件夹</span><span class="sxs-lookup"><span data-stu-id="621eb-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="621eb-134">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-134">Configure</span></span>  <br/> |<span data-ttu-id="621eb-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="621eb-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="621eb-136">跨设备需要 **相同** 的域</span><span class="sxs-lookup"><span data-stu-id="621eb-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="621eb-137">在 PSTN 站点上需要 **相同** 的域</span><span class="sxs-lookup"><span data-stu-id="621eb-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-138">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-138">Configure</span></span>  <br/> |<span data-ttu-id="621eb-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="621eb-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="621eb-140">跨设备的域名和顺序应**相同**</span><span class="sxs-lookup"><span data-stu-id="621eb-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="621eb-141">PSTN 站点之间的域名和顺序应**相同**</span><span class="sxs-lookup"><span data-stu-id="621eb-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-142">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-142">Configure</span></span>  <br/> |<span data-ttu-id="621eb-143">网站名称</span><span class="sxs-lookup"><span data-stu-id="621eb-143">Site name</span></span>  <br/> |<span data-ttu-id="621eb-144">**相同** 跨设备的站点名称</span><span class="sxs-lookup"><span data-stu-id="621eb-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="621eb-145">**不同** PSTN 站点之间的站点名称</span><span class="sxs-lookup"><span data-stu-id="621eb-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-146">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-146">Configure</span></span>  <br/> |<span data-ttu-id="621eb-147">服务器名称</span><span class="sxs-lookup"><span data-stu-id="621eb-147">Server names</span></span>  <br/> |<span data-ttu-id="621eb-148">跨设备**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="621eb-149">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-150">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-150">Configure</span></span>  <br/> |<span data-ttu-id="621eb-151">内部池 Fqdn</span><span class="sxs-lookup"><span data-stu-id="621eb-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="621eb-152">跨设备**相同**</span><span class="sxs-lookup"><span data-stu-id="621eb-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="621eb-153">PSTN 站点之间**相同**</span><span class="sxs-lookup"><span data-stu-id="621eb-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-154">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-154">Configure</span></span>  <br/> |<span data-ttu-id="621eb-155">内部 Ip</span><span class="sxs-lookup"><span data-stu-id="621eb-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="621eb-156">跨设备**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="621eb-157">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-158">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-158">Configure</span></span>  <br/> |<span data-ttu-id="621eb-159">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="621eb-159">External FQDN</span></span>  <br/> |<span data-ttu-id="621eb-160">跨设备**相同**</span><span class="sxs-lookup"><span data-stu-id="621eb-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="621eb-161">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-162">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-162">Configure</span></span>  <br/> |<span data-ttu-id="621eb-163">外部 Ip</span><span class="sxs-lookup"><span data-stu-id="621eb-163">External IPs</span></span>  <br/> |<span data-ttu-id="621eb-164">跨设备**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="621eb-165">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-166">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-166">Configure</span></span>  <br/> |<span data-ttu-id="621eb-167">PSTN GW 设置</span><span class="sxs-lookup"><span data-stu-id="621eb-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="621eb-168">跨设备**相同**</span><span class="sxs-lookup"><span data-stu-id="621eb-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="621eb-169">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="621eb-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="621eb-170">配置</span><span class="sxs-lookup"><span data-stu-id="621eb-170">Configure</span></span>  <br/> |<span data-ttu-id="621eb-171">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="621eb-171">DNS record</span></span>  <br/> |<span data-ttu-id="621eb-172">添加具有 **相同** 外部访问 fqdn 和 **不同** IP 地址的记录</span><span class="sxs-lookup"><span data-stu-id="621eb-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="621eb-173">添加具有 **不同** 外部访问 fqdn 和 **不同** IP 地址的记录</span><span class="sxs-lookup"><span data-stu-id="621eb-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="621eb-174">设置</span><span class="sxs-lookup"><span data-stu-id="621eb-174">Setup</span></span>  <br/> |<span data-ttu-id="621eb-175">混合租户</span><span class="sxs-lookup"><span data-stu-id="621eb-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="621eb-176">设置 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="621eb-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="621eb-177">设置 PeerDestination 以进行回退</span><span class="sxs-lookup"><span data-stu-id="621eb-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="621eb-178">设置 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="621eb-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="621eb-179">设置 PeerDestination 以进行回退</span><span class="sxs-lookup"><span data-stu-id="621eb-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="621eb-180">设置</span><span class="sxs-lookup"><span data-stu-id="621eb-180">Setup</span></span>  <br/> |<span data-ttu-id="621eb-181">网关</span><span class="sxs-lookup"><span data-stu-id="621eb-181">Gateway</span></span>  <br/> |<span data-ttu-id="621eb-182">此站点中的 MS GW **M:N** 映射</span><span class="sxs-lookup"><span data-stu-id="621eb-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="621eb-183">PSTN 网关 (s) 在每个 PSTN 站点中只应连接到同一站点中的中介服务器 (s) </span><span class="sxs-lookup"><span data-stu-id="621eb-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="621eb-184">设置</span><span class="sxs-lookup"><span data-stu-id="621eb-184">Setup</span></span>  <br/> |<span data-ttu-id="621eb-185">User</span><span class="sxs-lookup"><span data-stu-id="621eb-185">User</span></span>  <br/> |<span data-ttu-id="621eb-186">设置 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="621eb-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="621eb-187">设置 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="621eb-187">Set UserPSTNSettings</span></span>  <br/> |
   

