---
title: 为业务服务器与 Skype 的互操作配置 VTC
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 摘要： 配置对业务服务器使用 Skype VTC 设备。
ms.openlocfilehash: 15998fd313faed03886cdc64e758e3436fa858c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894435"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="413ce-103">为业务服务器与 Skype 的互操作配置 VTC</span><span class="sxs-lookup"><span data-stu-id="413ce-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="413ce-104">**摘要：** 配置对业务服务器使用 Skype VTC 设备。</span><span class="sxs-lookup"><span data-stu-id="413ce-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="413ce-105">需要执行以下配置自定义过程将连接到业务 VIS 服务器通过 SIP 中继的 Skype 和 Cisco 统一通信管理器 （CallManager 或 CUCM） 每个 VTC 视频的网关。</span><span class="sxs-lookup"><span data-stu-id="413ce-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="413ce-106">此处所述的设置，旨在仅作为 CUCM 可以配置方式的示例使用 VIS.</span><span class="sxs-lookup"><span data-stu-id="413ce-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="413ce-107">也可使用其他设置和/或备选 CUCM 功能来实现同样的结果。</span><span class="sxs-lookup"><span data-stu-id="413ce-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="413ce-108">示例中不对适用于特定场景的最佳配置作任何推荐暗示。</span><span class="sxs-lookup"><span data-stu-id="413ce-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="413ce-109">配置在 CUCM 注册的 VTC</span><span class="sxs-lookup"><span data-stu-id="413ce-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="413ce-110">登录到 Cisco VTC 设备并导航到配置-\>系统配置-\>设置。</span><span class="sxs-lookup"><span data-stu-id="413ce-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="413ce-111">验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="413ce-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="413ce-112">**参数**</span><span class="sxs-lookup"><span data-stu-id="413ce-112">**Parameter**</span></span>|<span data-ttu-id="413ce-113">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="413ce-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="413ce-114">设置模式</span><span class="sxs-lookup"><span data-stu-id="413ce-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="413ce-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="413ce-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="413ce-116">外部管理器地址</span><span class="sxs-lookup"><span data-stu-id="413ce-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="413ce-117">CUCM 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="413ce-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="413ce-118">ExternalManager 域</span><span class="sxs-lookup"><span data-stu-id="413ce-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="413ce-119">CUCM 的域</span><span class="sxs-lookup"><span data-stu-id="413ce-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="413ce-120">导航到配置-\>系统配置-\>网络。</span><span class="sxs-lookup"><span data-stu-id="413ce-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="413ce-121">验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="413ce-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="413ce-122">**参数**</span><span class="sxs-lookup"><span data-stu-id="413ce-122">**Parameter**</span></span>|<span data-ttu-id="413ce-123">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="413ce-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="413ce-124">DNS 域名</span><span class="sxs-lookup"><span data-stu-id="413ce-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="413ce-125">CUCM 的域名</span><span class="sxs-lookup"><span data-stu-id="413ce-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="413ce-126">DNS 服务器 1 地址</span><span class="sxs-lookup"><span data-stu-id="413ce-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="413ce-127">您所需的 DNS 服务器地址</span><span class="sxs-lookup"><span data-stu-id="413ce-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="413ce-128">导航到配置-\>系统配置-\>网络服务。</span><span class="sxs-lookup"><span data-stu-id="413ce-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="413ce-129">确保关闭 H.323 模式并打开 SIP 模式。</span><span class="sxs-lookup"><span data-stu-id="413ce-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="413ce-p103">终结点在 CUCM 注册时，将自动设置这些选项。验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="413ce-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="413ce-132">**参数**</span><span class="sxs-lookup"><span data-stu-id="413ce-132">**Parameter**</span></span>|<span data-ttu-id="413ce-133">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="413ce-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="413ce-134">H.323 模式</span><span class="sxs-lookup"><span data-stu-id="413ce-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="413ce-135">关</span><span class="sxs-lookup"><span data-stu-id="413ce-135">Off</span></span> <br/> |
   |<span data-ttu-id="413ce-136">HTTP 模式</span><span class="sxs-lookup"><span data-stu-id="413ce-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="413ce-137">开</span><span class="sxs-lookup"><span data-stu-id="413ce-137">On</span></span> <br/> |
   | <span data-ttu-id="413ce-138">SIP 模式</span><span class="sxs-lookup"><span data-stu-id="413ce-138">SIP Mode</span></span> <br/> | <span data-ttu-id="413ce-139">开</span><span class="sxs-lookup"><span data-stu-id="413ce-139">On</span></span> <br/> |
   |<span data-ttu-id="413ce-140">Telnet 模式</span><span class="sxs-lookup"><span data-stu-id="413ce-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="413ce-141">开</span><span class="sxs-lookup"><span data-stu-id="413ce-141">On</span></span> <br/> |
   |<span data-ttu-id="413ce-142">欢迎文本</span><span class="sxs-lookup"><span data-stu-id="413ce-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="413ce-143">开</span><span class="sxs-lookup"><span data-stu-id="413ce-143">On</span></span> <br/> |
   |<span data-ttu-id="413ce-144">XMLAPI 模式</span><span class="sxs-lookup"><span data-stu-id="413ce-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="413ce-145">开</span><span class="sxs-lookup"><span data-stu-id="413ce-145">On</span></span> <br/> |
   
7. <span data-ttu-id="413ce-146">导航到配置-\>系统配置-\>SIP。</span><span class="sxs-lookup"><span data-stu-id="413ce-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="413ce-147">验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="413ce-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="413ce-148">**参数**</span><span class="sxs-lookup"><span data-stu-id="413ce-148">**Parameter**</span></span>|<span data-ttu-id="413ce-149">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="413ce-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="413ce-150">配置文件 1 - 默认传输</span><span class="sxs-lookup"><span data-stu-id="413ce-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="413ce-151">TCP</span><span class="sxs-lookup"><span data-stu-id="413ce-151">TCP</span></span> <br/> |
   |<span data-ttu-id="413ce-152">配置文件 1 - 出站</span><span class="sxs-lookup"><span data-stu-id="413ce-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="413ce-153">关</span><span class="sxs-lookup"><span data-stu-id="413ce-153">Off</span></span> <br/> |
   |<span data-ttu-id="413ce-154">配置文件 1-TlsVerify</span><span class="sxs-lookup"><span data-stu-id="413ce-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="413ce-155">开</span><span class="sxs-lookup"><span data-stu-id="413ce-155">On</span></span> <br/> |
   |<span data-ttu-id="413ce-156">配置文件 1 - 类型</span><span class="sxs-lookup"><span data-stu-id="413ce-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="413ce-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="413ce-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="413ce-158">配置文件 1 - URI</span><span class="sxs-lookup"><span data-stu-id="413ce-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="413ce-159">在注册 CUCM 时自动分配</span><span class="sxs-lookup"><span data-stu-id="413ce-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="413ce-160">代理 1 - 地址</span><span class="sxs-lookup"><span data-stu-id="413ce-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="413ce-161">CUCM 的主机名称</span><span class="sxs-lookup"><span data-stu-id="413ce-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="413ce-p104">VTC 现已配置为可进行互操作。在开始服务前，还需在 CUCM 端执行最后几步。</span><span class="sxs-lookup"><span data-stu-id="413ce-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="413ce-164">在 CUCM 上配置 VTC 设备</span><span class="sxs-lookup"><span data-stu-id="413ce-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="413ce-165">登录到 CUCM 并导航到 Cisco 统一厘米管理-\>设备-\>电话-\>查找。</span><span class="sxs-lookup"><span data-stu-id="413ce-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="413ce-p105">选择要配置的 VTC 设备。在“电话配置”屏幕上验证以下设置并根据需要进行更正。更改或验证这些设置后，请单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="413ce-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="413ce-169">**参数**</span><span class="sxs-lookup"><span data-stu-id="413ce-169">**Parameter**</span></span>|<span data-ttu-id="413ce-170">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="413ce-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="413ce-171">设备信息 - 电话按钮模板</span><span class="sxs-lookup"><span data-stu-id="413ce-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="413ce-172">标准 Cisco 适量编解码器 C40</span><span class="sxs-lookup"><span data-stu-id="413ce-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="413ce-173">设备信息 - 通用电话配置文件</span><span class="sxs-lookup"><span data-stu-id="413ce-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="413ce-174">标准通用电话配置文件</span><span class="sxs-lookup"><span data-stu-id="413ce-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="413ce-175">设备信息 - 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="413ce-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="413ce-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="413ce-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="413ce-177">设备信息 - AAR 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="413ce-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="413ce-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="413ce-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="413ce-179">设备信息 - 媒体资源组列表</span><span class="sxs-lookup"><span data-stu-id="413ce-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="413ce-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="413ce-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="413ce-181">特定于协议的信息 - 设备安全配置文件</span><span class="sxs-lookup"><span data-stu-id="413ce-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="413ce-182">Cisco 适量编解码器 C40</span><span class="sxs-lookup"><span data-stu-id="413ce-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="413ce-183">特定于协议的信息 - 重新路由呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="413ce-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="413ce-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="413ce-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="413ce-185">协议的特定信息-订阅调用搜索空间</span><span class="sxs-lookup"><span data-stu-id="413ce-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="413ce-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="413ce-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="413ce-187">特定于协议的信息 - SIP 配置文件</span><span class="sxs-lookup"><span data-stu-id="413ce-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="413ce-188">网真终结点的标准 SIP 配置文件</span><span class="sxs-lookup"><span data-stu-id="413ce-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="413ce-189">保存 VTC 配置后，重新导航至设备的“电话配置”屏幕。</span><span class="sxs-lookup"><span data-stu-id="413ce-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="413ce-190">在“关联”组的屏幕顶部，单击“视频互操作”的关联。</span><span class="sxs-lookup"><span data-stu-id="413ce-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="413ce-191">然后将显示“目录号码配置”屏幕。</span><span class="sxs-lookup"><span data-stu-id="413ce-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="413ce-192">验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="413ce-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="413ce-193">如图所示对“目录号码信息”和“目录号码设置”进行相应的更改。</span><span class="sxs-lookup"><span data-stu-id="413ce-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="413ce-194">**参数**</span><span class="sxs-lookup"><span data-stu-id="413ce-194">**Parameter**</span></span>|<span data-ttu-id="413ce-195">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="413ce-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="413ce-196">目录号码信息 - 重新路由分区</span><span class="sxs-lookup"><span data-stu-id="413ce-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="413ce-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="413ce-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="413ce-198">目录号码设置 - 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="413ce-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="413ce-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="413ce-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="413ce-200">MLPP 备选方和机密访问级别设置 - MLPP 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="413ce-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="413ce-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="413ce-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="413ce-202">行 1 上的设备-显示 (呼叫者 ID)</span><span class="sxs-lookup"><span data-stu-id="413ce-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="413ce-203">根据需要</span><span class="sxs-lookup"><span data-stu-id="413ce-203">As desired</span></span> <br/> |
   |<span data-ttu-id="413ce-204">行 1 上的设备-ASCII 显示 (呼叫者 ID)</span><span class="sxs-lookup"><span data-stu-id="413ce-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="413ce-205">根据需要</span><span class="sxs-lookup"><span data-stu-id="413ce-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="413ce-206">完成时，滚动至屏幕顶部并单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="413ce-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="413ce-p107">现已为此 VTC 设备完成配置。您将需要为企业中的其他 VTC 设备重复此流程。</span><span class="sxs-lookup"><span data-stu-id="413ce-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>

