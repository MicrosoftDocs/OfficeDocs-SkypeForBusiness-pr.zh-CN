---
title: 在云连接器中部署多个站点
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 了解有关在云连接器版本中部署多个 PSTN 站点的信息。
ms.openlocfilehash: 04af3ffa69a0ba452277d497544d4ba6708b5cb8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="90c24-103">在云连接器中部署多个站点</span><span class="sxs-lookup"><span data-stu-id="90c24-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="90c24-104">了解有关在云连接器版本中部署多个 PSTN 站点的信息。</span><span class="sxs-lookup"><span data-stu-id="90c24-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="90c24-p101">本节介绍如何部署多个公用电话交换网 (PSTN) 站点。这些站点通过使用与部署单个站点相同的步骤，以每次一个的方式进行部署。本主题介绍多站点部署中的注意事项以及各站点之间的差异。</span><span class="sxs-lookup"><span data-stu-id="90c24-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="90c24-108">多个公用电话交换网 (PSTN) 站点</span><span class="sxs-lookup"><span data-stu-id="90c24-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="90c24-109">下面显示了一个示例配置不同的 PSTN 站点部署业务云连接器版的 Skype。</span><span class="sxs-lookup"><span data-stu-id="90c24-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="90c24-110">开始部署之前，请确保你的配置设置正确无误。</span><span class="sxs-lookup"><span data-stu-id="90c24-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="90c24-111">PSTN 站点 1</span><span class="sxs-lookup"><span data-stu-id="90c24-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="90c24-112">PSTN 站点 2</span><span class="sxs-lookup"><span data-stu-id="90c24-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="90c24-113">对于每个要添加的 PSTN 站点，请按照[部署云连接器中单个网站](deploy-a-single-site-in-cloud-connector.md)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="90c24-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="90c24-114">每个 PSTN 站点应具有单独的用于准备高可用性 (HA) 的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="90c24-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="90c24-115">不同 PSTN 站点**必须**使用不同的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="90c24-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="90c24-116">对于多个网站。 不使用相同的共享的文件夹 ></span><span class="sxs-lookup"><span data-stu-id="90c24-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="90c24-117">支持高可用性 (HA) 的单站点部署与多站点部署比较</span><span class="sxs-lookup"><span data-stu-id="90c24-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="90c24-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="90c24-118"></span></span>

<span data-ttu-id="90c24-119">下表列出了支持 HA 的单站点部署与多站点部署之间的差异。</span><span class="sxs-lookup"><span data-stu-id="90c24-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="90c24-120">**类别**</span><span class="sxs-lookup"><span data-stu-id="90c24-120">**Category**</span></span>|<span data-ttu-id="90c24-121">**项目**</span><span class="sxs-lookup"><span data-stu-id="90c24-121">**Item**</span></span>|<span data-ttu-id="90c24-122">**单站点与 HA**</span><span class="sxs-lookup"><span data-stu-id="90c24-122">**Single-Site with HA**</span></span>|<span data-ttu-id="90c24-123">**多站点**</span><span class="sxs-lookup"><span data-stu-id="90c24-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90c24-124">设置</span><span class="sxs-lookup"><span data-stu-id="90c24-124">Setup</span></span>  <br/> |<span data-ttu-id="90c24-125">共享文件夹</span><span class="sxs-lookup"><span data-stu-id="90c24-125">Shared folder</span></span>  <br/> |<span data-ttu-id="90c24-126">要求在整个装置**所在**的共享的文件夹</span><span class="sxs-lookup"><span data-stu-id="90c24-126">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="90c24-127">不同设备需要**不同**的共享文件夹</span><span class="sxs-lookup"><span data-stu-id="90c24-127">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="90c24-128">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-128">Configure</span></span>  <br/> |<span data-ttu-id="90c24-129">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="90c24-129">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="90c24-130">不同设备需要**相同**的域</span><span class="sxs-lookup"><span data-stu-id="90c24-130">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="90c24-131">不同 PSTN 站点需要**相同**的域</span><span class="sxs-lookup"><span data-stu-id="90c24-131">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="90c24-132">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-132">Configure</span></span>  <br/> |<span data-ttu-id="90c24-133">SIP 域</span><span class="sxs-lookup"><span data-stu-id="90c24-133">SIPDomains</span></span>  <br/> |<span data-ttu-id="90c24-134">域的名称和顺序应该是**同一个**装置</span><span class="sxs-lookup"><span data-stu-id="90c24-134">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="90c24-135">域的名称和顺序应**相同**跨 PSTN 站点</span><span class="sxs-lookup"><span data-stu-id="90c24-135">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="90c24-136">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-136">Configure</span></span>  <br/> |<span data-ttu-id="90c24-137">站点名称</span><span class="sxs-lookup"><span data-stu-id="90c24-137">Site name</span></span>  <br/> |<span data-ttu-id="90c24-138">不同设备具有**相同**的站点名称</span><span class="sxs-lookup"><span data-stu-id="90c24-138">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="90c24-139">不同 PSTN 站点具有**不同**的站点名称</span><span class="sxs-lookup"><span data-stu-id="90c24-139">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="90c24-140">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-140">Configure</span></span>  <br/> |<span data-ttu-id="90c24-141">服务器名称</span><span class="sxs-lookup"><span data-stu-id="90c24-141">Server names</span></span>  <br/> |<span data-ttu-id="90c24-142">设备之间**不同**</span><span class="sxs-lookup"><span data-stu-id="90c24-142">**Different** across appliances</span></span> <br/> |<span data-ttu-id="90c24-143">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="90c24-143">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="90c24-144">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-144">Configure</span></span>  <br/> |<span data-ttu-id="90c24-145">内部池 FQDN</span><span class="sxs-lookup"><span data-stu-id="90c24-145">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="90c24-146">设备之间**相同**</span><span class="sxs-lookup"><span data-stu-id="90c24-146">**Same** across appliances</span></span> <br/> |<span data-ttu-id="90c24-147">PSTN 站点之间**相同**</span><span class="sxs-lookup"><span data-stu-id="90c24-147">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="90c24-148">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-148">Configure</span></span>  <br/> |<span data-ttu-id="90c24-149">内部 IP</span><span class="sxs-lookup"><span data-stu-id="90c24-149">Internal IPs</span></span>  <br/> |<span data-ttu-id="90c24-150">设备之间**不同**</span><span class="sxs-lookup"><span data-stu-id="90c24-150">**Different** across appliances</span></span> <br/> |<span data-ttu-id="90c24-151">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="90c24-151">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="90c24-152">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-152">Configure</span></span>  <br/> |<span data-ttu-id="90c24-153">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="90c24-153">External FQDN</span></span>  <br/> |<span data-ttu-id="90c24-154">设备之间**相同**</span><span class="sxs-lookup"><span data-stu-id="90c24-154">**Same** across appliances</span></span> <br/> |<span data-ttu-id="90c24-155">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="90c24-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="90c24-156">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-156">Configure</span></span>  <br/> |<span data-ttu-id="90c24-157">外部 IP</span><span class="sxs-lookup"><span data-stu-id="90c24-157">External IPs</span></span>  <br/> |<span data-ttu-id="90c24-158">设备之间**不同**</span><span class="sxs-lookup"><span data-stu-id="90c24-158">**Different** across appliances</span></span> <br/> |<span data-ttu-id="90c24-159">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="90c24-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="90c24-160">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-160">Configure</span></span>  <br/> |<span data-ttu-id="90c24-161">PSTN 网关设置</span><span class="sxs-lookup"><span data-stu-id="90c24-161">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="90c24-162">设备之间**相同**</span><span class="sxs-lookup"><span data-stu-id="90c24-162">**Same** across appliances</span></span> <br/> |<span data-ttu-id="90c24-163">PSTN 站点之间**不同**</span><span class="sxs-lookup"><span data-stu-id="90c24-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="90c24-164">配置</span><span class="sxs-lookup"><span data-stu-id="90c24-164">Configure</span></span>  <br/> |<span data-ttu-id="90c24-165">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="90c24-165">DNS record</span></span>  <br/> |<span data-ttu-id="90c24-166">添加具有**相同**外部访问 Fqdn 记录和**不同**的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="90c24-166">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="90c24-167">添加包含**不同**外部访问 FQDN 和**不同** IP 地址的记录</span><span class="sxs-lookup"><span data-stu-id="90c24-167">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="90c24-168">设置</span><span class="sxs-lookup"><span data-stu-id="90c24-168">Setup</span></span>  <br/> |<span data-ttu-id="90c24-169">混合的租户</span><span class="sxs-lookup"><span data-stu-id="90c24-169">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="90c24-170">设置 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="90c24-170">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="90c24-171">设置用于回退的 PeerDestination</span><span class="sxs-lookup"><span data-stu-id="90c24-171">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="90c24-172">设置 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="90c24-172">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="90c24-173">设置用于回退的 PeerDestination</span><span class="sxs-lookup"><span data-stu-id="90c24-173">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="90c24-174">设置</span><span class="sxs-lookup"><span data-stu-id="90c24-174">Setup</span></span>  <br/> |<span data-ttu-id="90c24-175">网关</span><span class="sxs-lookup"><span data-stu-id="90c24-175">Gateway</span></span>  <br/> |<span data-ttu-id="90c24-176">此站点中采用 MS GW **M:N** 映射</span><span class="sxs-lookup"><span data-stu-id="90c24-176">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="90c24-177">每个 PSTN 站点中的 PSTN 网关应只连接到同一站点中的中介服务器</span><span class="sxs-lookup"><span data-stu-id="90c24-177">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="90c24-178">设置</span><span class="sxs-lookup"><span data-stu-id="90c24-178">Setup</span></span>  <br/> |<span data-ttu-id="90c24-179">用户</span><span class="sxs-lookup"><span data-stu-id="90c24-179">User</span></span>  <br/> |<span data-ttu-id="90c24-180">设置 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="90c24-180">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="90c24-181">设置 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="90c24-181">Set UserPSTNSettings</span></span>  <br/> |
   

