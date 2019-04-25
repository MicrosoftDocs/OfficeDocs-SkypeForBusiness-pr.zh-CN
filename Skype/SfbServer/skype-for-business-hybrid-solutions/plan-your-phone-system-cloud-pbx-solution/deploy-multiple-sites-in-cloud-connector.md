---
title: 在云连接器中部署多个站点
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 了解有关在云连接器版本中部署多个 PSTN 站点的信息。
ms.openlocfilehash: 194eaf0b68489b37a5ab1fc2d5d501177edd0b35
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227899"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="66e50-103">在云连接器中部署多个站点</span><span class="sxs-lookup"><span data-stu-id="66e50-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="66e50-104">了解有关在云连接器版本中部署多个 PSTN 站点的信息。</span><span class="sxs-lookup"><span data-stu-id="66e50-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="66e50-p101">本节介绍如何部署多个公用电话交换网 (PSTN) 站点。这些站点通过使用与部署单个站点相同的步骤，以每次一个的方式进行部署。本主题介绍多站点部署中的注意事项以及各站点之间的差异。</span><span class="sxs-lookup"><span data-stu-id="66e50-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="66e50-108">多个公用电话交换网 (PSTN) 站点</span><span class="sxs-lookup"><span data-stu-id="66e50-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="66e50-109">下面显示的示例配置商务云连接器版 Skype 部署不同的 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="66e50-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="66e50-110">开始部署之前，请确保你的配置设置正确无误。</span><span class="sxs-lookup"><span data-stu-id="66e50-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="66e50-111">PSTN 站点 1</span><span class="sxs-lookup"><span data-stu-id="66e50-111">PSTN Site 1</span></span>
  
```
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

<span data-ttu-id="66e50-112">PSTN 站点 2</span><span class="sxs-lookup"><span data-stu-id="66e50-112">PSTN Site 2</span></span>
  
```
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

<span data-ttu-id="66e50-113">对于您要添加的每个 PSTN 网站，请按照[Deploy 云 Connector 中单个网站](deploy-a-single-site-in-cloud-connector.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="66e50-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="66e50-114">每个 PSTN 站点应具有单独的用于准备高可用性 (HA) 的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="66e50-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="66e50-115">不同 PSTN 站点**必须**使用不同的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="66e50-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="66e50-116">为多个 sites.> 不使用相同的共享的文件夹</span><span class="sxs-lookup"><span data-stu-id="66e50-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="66e50-117">支持高可用性 (HA) 的单站点部署与多站点部署比较</span><span class="sxs-lookup"><span data-stu-id="66e50-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="66e50-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="66e50-118"></span></span>

<span data-ttu-id="66e50-119">下表列出了支持 HA 的单站点部署与多站点部署之间的差异。</span><span class="sxs-lookup"><span data-stu-id="66e50-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="66e50-120">**类别**</span><span class="sxs-lookup"><span data-stu-id="66e50-120">**Category**</span></span>|<span data-ttu-id="66e50-121">**项目**</span><span class="sxs-lookup"><span data-stu-id="66e50-121">**Item**</span></span>|<span data-ttu-id="66e50-122">**支持 HA 的单站点**</span><span class="sxs-lookup"><span data-stu-id="66e50-122">**Single-Site with HA**</span></span>|<span data-ttu-id="66e50-123">**多站点**</span><span class="sxs-lookup"><span data-stu-id="66e50-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66e50-124">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-124">Configure</span></span>  <br/> |<span data-ttu-id="66e50-125">装置主机名</span><span class="sxs-lookup"><span data-stu-id="66e50-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="66e50-126">设备之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="66e50-127">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-128">设置</span><span class="sxs-lookup"><span data-stu-id="66e50-128">Setup</span></span>  <br/> |<span data-ttu-id="66e50-129">共享文件夹</span><span class="sxs-lookup"><span data-stu-id="66e50-129">Shared folder</span></span>  <br/> |<span data-ttu-id="66e50-130">要求在设备之间的**相同**的共享的文件夹</span><span class="sxs-lookup"><span data-stu-id="66e50-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="66e50-131">不同设备需要**不同**的共享文件夹</span><span class="sxs-lookup"><span data-stu-id="66e50-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="66e50-132">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-132">Configure</span></span>  <br/> |<span data-ttu-id="66e50-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="66e50-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="66e50-134">不同设备需要**相同**的域</span><span class="sxs-lookup"><span data-stu-id="66e50-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="66e50-135">不同 PSTN 站点需要**相同**的域</span><span class="sxs-lookup"><span data-stu-id="66e50-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-136">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-136">Configure</span></span>  <br/> |<span data-ttu-id="66e50-137">SIP 域</span><span class="sxs-lookup"><span data-stu-id="66e50-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="66e50-138">域名和顺序应**相同**跨 appliance</span><span class="sxs-lookup"><span data-stu-id="66e50-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="66e50-139">域名和顺序应**相同**跨 PSTN 网站</span><span class="sxs-lookup"><span data-stu-id="66e50-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-140">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-140">Configure</span></span>  <br/> |<span data-ttu-id="66e50-141">站点名称</span><span class="sxs-lookup"><span data-stu-id="66e50-141">Site name</span></span>  <br/> |<span data-ttu-id="66e50-142">不同设备具有**相同**的站点名称</span><span class="sxs-lookup"><span data-stu-id="66e50-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="66e50-143">不同 PSTN 站点具有**不同**的站点名称</span><span class="sxs-lookup"><span data-stu-id="66e50-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-144">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-144">Configure</span></span>  <br/> |<span data-ttu-id="66e50-145">服务器名称</span><span class="sxs-lookup"><span data-stu-id="66e50-145">Server names</span></span>  <br/> |<span data-ttu-id="66e50-146">设备之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="66e50-147">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-148">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-148">Configure</span></span>  <br/> |<span data-ttu-id="66e50-149">内部池 FQDN</span><span class="sxs-lookup"><span data-stu-id="66e50-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="66e50-150">设备之间**相同**</span><span class="sxs-lookup"><span data-stu-id="66e50-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="66e50-151">PSTN 站点之间**相同**</span><span class="sxs-lookup"><span data-stu-id="66e50-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-152">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-152">Configure</span></span>  <br/> |<span data-ttu-id="66e50-153">内部 IP</span><span class="sxs-lookup"><span data-stu-id="66e50-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="66e50-154">设备之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="66e50-155">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-156">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-156">Configure</span></span>  <br/> |<span data-ttu-id="66e50-157">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="66e50-157">External FQDN</span></span>  <br/> |<span data-ttu-id="66e50-158">设备之间**相同**</span><span class="sxs-lookup"><span data-stu-id="66e50-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="66e50-159">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-160">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-160">Configure</span></span>  <br/> |<span data-ttu-id="66e50-161">外部 IP</span><span class="sxs-lookup"><span data-stu-id="66e50-161">External IPs</span></span>  <br/> |<span data-ttu-id="66e50-162">设备之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="66e50-163">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-164">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-164">Configure</span></span>  <br/> |<span data-ttu-id="66e50-165">PSTN 网关设置</span><span class="sxs-lookup"><span data-stu-id="66e50-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="66e50-166">设备之间**相同**</span><span class="sxs-lookup"><span data-stu-id="66e50-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="66e50-167">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="66e50-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="66e50-168">配置</span><span class="sxs-lookup"><span data-stu-id="66e50-168">Configure</span></span>  <br/> |<span data-ttu-id="66e50-169">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="66e50-169">DNS record</span></span>  <br/> |<span data-ttu-id="66e50-170">添加具有**相同**外部访问 Fqdn 记录和**不同**的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="66e50-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="66e50-171">添加包含**不同**外部访问 FQDN 和**不同** IP 地址的记录</span><span class="sxs-lookup"><span data-stu-id="66e50-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="66e50-172">设置</span><span class="sxs-lookup"><span data-stu-id="66e50-172">Setup</span></span>  <br/> |<span data-ttu-id="66e50-173">混合租户</span><span class="sxs-lookup"><span data-stu-id="66e50-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="66e50-174">设置 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="66e50-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="66e50-175">设置用于回退的 PeerDestination</span><span class="sxs-lookup"><span data-stu-id="66e50-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="66e50-176">设置 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="66e50-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="66e50-177">设置用于回退的 PeerDestination</span><span class="sxs-lookup"><span data-stu-id="66e50-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="66e50-178">设置</span><span class="sxs-lookup"><span data-stu-id="66e50-178">Setup</span></span>  <br/> |<span data-ttu-id="66e50-179">网关</span><span class="sxs-lookup"><span data-stu-id="66e50-179">Gateway</span></span>  <br/> |<span data-ttu-id="66e50-180">此站点中采用 MS GW **M:N** 映射</span><span class="sxs-lookup"><span data-stu-id="66e50-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="66e50-181">每个 PSTN 站点中的 PSTN 网关应只连接到同一站点中的中介服务器</span><span class="sxs-lookup"><span data-stu-id="66e50-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="66e50-182">设置</span><span class="sxs-lookup"><span data-stu-id="66e50-182">Setup</span></span>  <br/> |<span data-ttu-id="66e50-183">用户</span><span class="sxs-lookup"><span data-stu-id="66e50-183">User</span></span>  <br/> |<span data-ttu-id="66e50-184">设置 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="66e50-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="66e50-185">设置 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="66e50-185">Set UserPSTNSettings</span></span>  <br/> |
   

