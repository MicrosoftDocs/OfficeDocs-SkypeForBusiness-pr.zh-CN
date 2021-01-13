---
title: 配置 VTC 以与 Skype for Business Server 进行互操作
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 摘要：配置 VTC 设备以使用 Skype for Business Server。
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802072"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="76ff4-103">配置 VTC 以与 Skype for Business Server 进行互操作</span><span class="sxs-lookup"><span data-stu-id="76ff4-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="76ff4-104">**摘要：** 配置 VTC 设备以使用 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="76ff4-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="76ff4-105">对于将通过 SIP 中继和 Cisco 统一通信管理器 (CallManager 或 CUCM) 网关连接到 Skype for Business VIS 服务器的每个 VTC，你需要执行以下配置自定义过程。</span><span class="sxs-lookup"><span data-stu-id="76ff4-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="76ff4-106">此处所述的设置仅用作如何配置 CUCM 以使用 VIS 的示例。</span><span class="sxs-lookup"><span data-stu-id="76ff4-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="76ff4-107">备用 CUCM 功能的其他设置和/或用法还可用于实现相同的结果。</span><span class="sxs-lookup"><span data-stu-id="76ff4-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="76ff4-108">不暗示有关特定方案的最佳配置的建议。</span><span class="sxs-lookup"><span data-stu-id="76ff4-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="76ff4-109">配置在 CUCM 中注册的 VTC</span><span class="sxs-lookup"><span data-stu-id="76ff4-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="76ff4-110">登录到 Cisco VTC 设备并导航到"配置- \> 系统配置- \> 预配"。</span><span class="sxs-lookup"><span data-stu-id="76ff4-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="76ff4-111">验证以下设置，根据需要更正：</span><span class="sxs-lookup"><span data-stu-id="76ff4-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="76ff4-112">**参数**</span><span class="sxs-lookup"><span data-stu-id="76ff4-112">**Parameter**</span></span>|<span data-ttu-id="76ff4-113">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="76ff4-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="76ff4-114">设置模式</span><span class="sxs-lookup"><span data-stu-id="76ff4-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="76ff4-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="76ff4-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="76ff4-116">ExternalManager 地址</span><span class="sxs-lookup"><span data-stu-id="76ff4-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="76ff4-117">CUCM 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="76ff4-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="76ff4-118">ExternalManager 域</span><span class="sxs-lookup"><span data-stu-id="76ff4-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="76ff4-119">CUCM 的域</span><span class="sxs-lookup"><span data-stu-id="76ff4-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="76ff4-120">导航到"配置- \> 系统配置- \> 网络"。</span><span class="sxs-lookup"><span data-stu-id="76ff4-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="76ff4-121">验证以下设置，根据需要更正：</span><span class="sxs-lookup"><span data-stu-id="76ff4-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="76ff4-122">**参数**</span><span class="sxs-lookup"><span data-stu-id="76ff4-122">**Parameter**</span></span>|<span data-ttu-id="76ff4-123">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="76ff4-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="76ff4-124">DNS 域名</span><span class="sxs-lookup"><span data-stu-id="76ff4-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="76ff4-125">CUCM 的域名</span><span class="sxs-lookup"><span data-stu-id="76ff4-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="76ff4-126">DNS Server 1 地址</span><span class="sxs-lookup"><span data-stu-id="76ff4-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="76ff4-127">所需的 DNS 服务器地址</span><span class="sxs-lookup"><span data-stu-id="76ff4-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="76ff4-128">导航到 Configuration- \> 系统配置 - \> 网络服务。</span><span class="sxs-lookup"><span data-stu-id="76ff4-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="76ff4-129">确保 H.323 模式已关闭，SIP 模式已打开。</span><span class="sxs-lookup"><span data-stu-id="76ff4-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="76ff4-130">当终结点注册 CUCM 时，将自动设置这些选项。</span><span class="sxs-lookup"><span data-stu-id="76ff4-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="76ff4-131">验证以下设置，根据需要更正：</span><span class="sxs-lookup"><span data-stu-id="76ff4-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="76ff4-132">**参数**</span><span class="sxs-lookup"><span data-stu-id="76ff4-132">**Parameter**</span></span>|<span data-ttu-id="76ff4-133">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="76ff4-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="76ff4-134">H.323 模式</span><span class="sxs-lookup"><span data-stu-id="76ff4-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="76ff4-135">关闭</span><span class="sxs-lookup"><span data-stu-id="76ff4-135">Off</span></span> <br/> |
   |<span data-ttu-id="76ff4-136">HTTP 模式</span><span class="sxs-lookup"><span data-stu-id="76ff4-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="76ff4-137">打开</span><span class="sxs-lookup"><span data-stu-id="76ff4-137">On</span></span> <br/> |
   | <span data-ttu-id="76ff4-138">SIP 模式</span><span class="sxs-lookup"><span data-stu-id="76ff4-138">SIP Mode</span></span> <br/> | <span data-ttu-id="76ff4-139">打开</span><span class="sxs-lookup"><span data-stu-id="76ff4-139">On</span></span> <br/> |
   |<span data-ttu-id="76ff4-140">Telnet 模式</span><span class="sxs-lookup"><span data-stu-id="76ff4-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="76ff4-141">打开</span><span class="sxs-lookup"><span data-stu-id="76ff4-141">On</span></span> <br/> |
   |<span data-ttu-id="76ff4-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="76ff4-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="76ff4-143">打开</span><span class="sxs-lookup"><span data-stu-id="76ff4-143">On</span></span> <br/> |
   |<span data-ttu-id="76ff4-144">XMLAPI 模式</span><span class="sxs-lookup"><span data-stu-id="76ff4-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="76ff4-145">打开</span><span class="sxs-lookup"><span data-stu-id="76ff4-145">On</span></span> <br/> |
   
7. <span data-ttu-id="76ff4-146">导航到 Configuration- \> 系统配置 - \> SIP。</span><span class="sxs-lookup"><span data-stu-id="76ff4-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="76ff4-147">验证以下设置，根据需要更正：</span><span class="sxs-lookup"><span data-stu-id="76ff4-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="76ff4-148">**参数**</span><span class="sxs-lookup"><span data-stu-id="76ff4-148">**Parameter**</span></span>|<span data-ttu-id="76ff4-149">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="76ff4-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="76ff4-150">配置文件 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="76ff4-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="76ff4-151">TCP</span><span class="sxs-lookup"><span data-stu-id="76ff4-151">TCP</span></span> <br/> |
   |<span data-ttu-id="76ff4-152">配置文件 1 - 出站</span><span class="sxs-lookup"><span data-stu-id="76ff4-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="76ff4-153">关闭</span><span class="sxs-lookup"><span data-stu-id="76ff4-153">Off</span></span> <br/> |
   |<span data-ttu-id="76ff4-154">配置文件 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="76ff4-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="76ff4-155">打开</span><span class="sxs-lookup"><span data-stu-id="76ff4-155">On</span></span> <br/> |
   |<span data-ttu-id="76ff4-156">配置文件 1 - 类型</span><span class="sxs-lookup"><span data-stu-id="76ff4-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="76ff4-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="76ff4-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="76ff4-158">配置文件 1 - URI</span><span class="sxs-lookup"><span data-stu-id="76ff4-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="76ff4-159">在 CUCM 注册时自动分配</span><span class="sxs-lookup"><span data-stu-id="76ff4-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="76ff4-160">代理 1 - 地址</span><span class="sxs-lookup"><span data-stu-id="76ff4-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="76ff4-161">CUCM 的主机名</span><span class="sxs-lookup"><span data-stu-id="76ff4-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="76ff4-162">VTC 现已配置为进行互操作。</span><span class="sxs-lookup"><span data-stu-id="76ff4-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="76ff4-163">在服务开始之前，需要先在 CUCM 端执行最后一步。</span><span class="sxs-lookup"><span data-stu-id="76ff4-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="76ff4-164">在 CUCM 上配置 VTC 设备</span><span class="sxs-lookup"><span data-stu-id="76ff4-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="76ff4-165">登录到 CUCM 并导航到 Cisco 统一 CM 管理 - \> Device- \> Phone- \> Find。</span><span class="sxs-lookup"><span data-stu-id="76ff4-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="76ff4-166">选择要配置的 VTC 设备。</span><span class="sxs-lookup"><span data-stu-id="76ff4-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="76ff4-167">在"电话配置"屏幕上验证以下设置，根据需要更正。</span><span class="sxs-lookup"><span data-stu-id="76ff4-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="76ff4-168">更改或验证这些设置后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="76ff4-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="76ff4-169">**参数**</span><span class="sxs-lookup"><span data-stu-id="76ff4-169">**Parameter**</span></span>|<span data-ttu-id="76ff4-170">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="76ff4-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="76ff4-171">设备信息 - 电话按钮模板</span><span class="sxs-lookup"><span data-stu-id="76ff4-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="76ff4-172">标准 Cisco 网真编解码器 C40</span><span class="sxs-lookup"><span data-stu-id="76ff4-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="76ff4-173">设备信息 - 通用电话配置文件</span><span class="sxs-lookup"><span data-stu-id="76ff4-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="76ff4-174">标准公用电话配置文件</span><span class="sxs-lookup"><span data-stu-id="76ff4-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="76ff4-175">设备信息 - 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="76ff4-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="76ff4-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="76ff4-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="76ff4-177">设备信息 - AAR 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="76ff4-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="76ff4-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="76ff4-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="76ff4-179">设备信息 - 媒体资源组列表</span><span class="sxs-lookup"><span data-stu-id="76ff4-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="76ff4-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="76ff4-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="76ff4-181">协议特定信息 - 设备安全配置文件</span><span class="sxs-lookup"><span data-stu-id="76ff4-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="76ff4-182">Cisco Telepresence 编解码器 C40</span><span class="sxs-lookup"><span data-stu-id="76ff4-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="76ff4-183">协议特定信息 - 重新路由呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="76ff4-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="76ff4-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="76ff4-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="76ff4-185">协议特定信息 - SUBSCRIBE 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="76ff4-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="76ff4-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="76ff4-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="76ff4-187">协议特定信息 -SIP 配置文件</span><span class="sxs-lookup"><span data-stu-id="76ff4-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="76ff4-188">网真终结点的标准 SIP 配置文件</span><span class="sxs-lookup"><span data-stu-id="76ff4-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="76ff4-189">保存 VTC 配置后，重新导航到设备的"电话配置"屏幕。</span><span class="sxs-lookup"><span data-stu-id="76ff4-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="76ff4-190">在关联组的屏幕顶部，单击"视频互操作"的关联。</span><span class="sxs-lookup"><span data-stu-id="76ff4-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="76ff4-191">此时将显示"目录号码配置"屏幕。</span><span class="sxs-lookup"><span data-stu-id="76ff4-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="76ff4-192">验证以下设置，根据需要更正：</span><span class="sxs-lookup"><span data-stu-id="76ff4-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="76ff4-193">对目录号码信息和目录号码设置进行相应的更改。</span><span class="sxs-lookup"><span data-stu-id="76ff4-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="76ff4-194">**参数**</span><span class="sxs-lookup"><span data-stu-id="76ff4-194">**Parameter**</span></span>|<span data-ttu-id="76ff4-195">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="76ff4-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="76ff4-196">目录号码信息 - 路由分区</span><span class="sxs-lookup"><span data-stu-id="76ff4-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="76ff4-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="76ff4-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="76ff4-198">目录号码设置 - 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="76ff4-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="76ff4-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="76ff4-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="76ff4-200">MLPP 备用方和机密访问级别设置 - MLPP 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="76ff4-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="76ff4-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="76ff4-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="76ff4-202">设备上第 1 行 - (来电显示) </span><span class="sxs-lookup"><span data-stu-id="76ff4-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="76ff4-203">如需要</span><span class="sxs-lookup"><span data-stu-id="76ff4-203">As desired</span></span> <br/> |
   |<span data-ttu-id="76ff4-204">设备上第 1 行 - ASCII (来电显示) </span><span class="sxs-lookup"><span data-stu-id="76ff4-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="76ff4-205">如需要</span><span class="sxs-lookup"><span data-stu-id="76ff4-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="76ff4-206">完成后，滚动到屏幕顶部，然后按"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="76ff4-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="76ff4-207">此 VTC 设备的配置现已完成。</span><span class="sxs-lookup"><span data-stu-id="76ff4-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="76ff4-208">你需要为企业中其他 VTC 设备重复此过程。</span><span class="sxs-lookup"><span data-stu-id="76ff4-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

