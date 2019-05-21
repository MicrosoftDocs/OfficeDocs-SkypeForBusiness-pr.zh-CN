---
title: 为与 Skype for Business 服务器的互操作配置 VTC
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '摘要: 将 VTC 设备配置为与 Skype for Business 服务器配合使用。'
ms.openlocfilehash: 460ac0a301ee9c9b2cb5bb1b4ca4c1aaf6ee4825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302788"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="5b758-103">为与 Skype for Business 服务器的互操作配置 VTC</span><span class="sxs-lookup"><span data-stu-id="5b758-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="5b758-104">**摘要:** 将 VTC 设备配置为与 Skype for Business 服务器配合使用。</span><span class="sxs-lookup"><span data-stu-id="5b758-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="5b758-105">对于将通过 SIP 主干和 Cisco 统一通信管理器 (CallManager 或 CUCM) 视频网关连接到 Skype for Business VIS 服务器的每个 VTC, 你将需要执行以下配置自定义过程。</span><span class="sxs-lookup"><span data-stu-id="5b758-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="5b758-106">此处所述的设置仅用作如何配置 CUCM 以使用 VIS 的示例。</span><span class="sxs-lookup"><span data-stu-id="5b758-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="5b758-107">也可使用其他设置和/或备选 CUCM 功能来实现同样的结果。</span><span class="sxs-lookup"><span data-stu-id="5b758-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="5b758-108">示例中不对适用于特定场景的最佳配置作任何推荐暗示。</span><span class="sxs-lookup"><span data-stu-id="5b758-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="5b758-109">配置在 CUCM 注册的 VTC</span><span class="sxs-lookup"><span data-stu-id="5b758-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="5b758-110">登录 Cisco VTC 设备并导航到配置\>系统配置-\>预配。</span><span class="sxs-lookup"><span data-stu-id="5b758-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="5b758-111">验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="5b758-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="5b758-112">**参数**</span><span class="sxs-lookup"><span data-stu-id="5b758-112">**Parameter**</span></span>|<span data-ttu-id="5b758-113">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="5b758-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5b758-114">设置模式</span><span class="sxs-lookup"><span data-stu-id="5b758-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="5b758-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="5b758-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="5b758-116">外部管理器地址</span><span class="sxs-lookup"><span data-stu-id="5b758-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="5b758-117">CUCM 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="5b758-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="5b758-118">ExternalManager 域</span><span class="sxs-lookup"><span data-stu-id="5b758-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="5b758-119">CUCM 的域</span><span class="sxs-lookup"><span data-stu-id="5b758-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="5b758-120">导航到 "配置\>-系统配置\>-网络"。</span><span class="sxs-lookup"><span data-stu-id="5b758-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="5b758-121">验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="5b758-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="5b758-122">**参数**</span><span class="sxs-lookup"><span data-stu-id="5b758-122">**Parameter**</span></span>|<span data-ttu-id="5b758-123">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="5b758-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5b758-124">DNS 域名</span><span class="sxs-lookup"><span data-stu-id="5b758-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="5b758-125">CUCM 的域名</span><span class="sxs-lookup"><span data-stu-id="5b758-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="5b758-126">DNS 服务器 1 地址</span><span class="sxs-lookup"><span data-stu-id="5b758-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="5b758-127">您所需的 DNS 服务器地址</span><span class="sxs-lookup"><span data-stu-id="5b758-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="5b758-128">导航到 "配置\>-系统配置\>-网络服务"。</span><span class="sxs-lookup"><span data-stu-id="5b758-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="5b758-129">确保关闭 H.323 模式并打开 SIP 模式。</span><span class="sxs-lookup"><span data-stu-id="5b758-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="5b758-p103">终结点在 CUCM 注册时，将自动设置这些选项。验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="5b758-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="5b758-132">**参数**</span><span class="sxs-lookup"><span data-stu-id="5b758-132">**Parameter**</span></span>|<span data-ttu-id="5b758-133">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="5b758-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5b758-134">H.323 模式</span><span class="sxs-lookup"><span data-stu-id="5b758-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="5b758-135">关</span><span class="sxs-lookup"><span data-stu-id="5b758-135">Off</span></span> <br/> |
   |<span data-ttu-id="5b758-136">HTTP 模式</span><span class="sxs-lookup"><span data-stu-id="5b758-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="5b758-137">开</span><span class="sxs-lookup"><span data-stu-id="5b758-137">On</span></span> <br/> |
   | <span data-ttu-id="5b758-138">SIP 模式</span><span class="sxs-lookup"><span data-stu-id="5b758-138">SIP Mode</span></span> <br/> | <span data-ttu-id="5b758-139">开</span><span class="sxs-lookup"><span data-stu-id="5b758-139">On</span></span> <br/> |
   |<span data-ttu-id="5b758-140">Telnet 模式</span><span class="sxs-lookup"><span data-stu-id="5b758-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="5b758-141">开</span><span class="sxs-lookup"><span data-stu-id="5b758-141">On</span></span> <br/> |
   |<span data-ttu-id="5b758-142">欢迎文本</span><span class="sxs-lookup"><span data-stu-id="5b758-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="5b758-143">开</span><span class="sxs-lookup"><span data-stu-id="5b758-143">On</span></span> <br/> |
   |<span data-ttu-id="5b758-144">XMLAPI 模式</span><span class="sxs-lookup"><span data-stu-id="5b758-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="5b758-145">开</span><span class="sxs-lookup"><span data-stu-id="5b758-145">On</span></span> <br/> |
   
7. <span data-ttu-id="5b758-146">导航到 "配置\>-系统配置\>-SIP"。</span><span class="sxs-lookup"><span data-stu-id="5b758-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="5b758-147">验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="5b758-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="5b758-148">**参数**</span><span class="sxs-lookup"><span data-stu-id="5b758-148">**Parameter**</span></span>|<span data-ttu-id="5b758-149">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="5b758-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5b758-150">配置文件 1 - 默认传输</span><span class="sxs-lookup"><span data-stu-id="5b758-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="5b758-151">TCP</span><span class="sxs-lookup"><span data-stu-id="5b758-151">TCP</span></span> <br/> |
   |<span data-ttu-id="5b758-152">配置文件 1 - 出站</span><span class="sxs-lookup"><span data-stu-id="5b758-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="5b758-153">关</span><span class="sxs-lookup"><span data-stu-id="5b758-153">Off</span></span> <br/> |
   |<span data-ttu-id="5b758-154">配置文件 1-TlsVerify</span><span class="sxs-lookup"><span data-stu-id="5b758-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="5b758-155">开</span><span class="sxs-lookup"><span data-stu-id="5b758-155">On</span></span> <br/> |
   |<span data-ttu-id="5b758-156">配置文件 1 - 类型</span><span class="sxs-lookup"><span data-stu-id="5b758-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="5b758-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="5b758-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="5b758-158">配置文件 1 - URI</span><span class="sxs-lookup"><span data-stu-id="5b758-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="5b758-159">在注册 CUCM 时自动分配</span><span class="sxs-lookup"><span data-stu-id="5b758-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="5b758-160">代理 1 - 地址</span><span class="sxs-lookup"><span data-stu-id="5b758-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="5b758-161">CUCM 的主机名称</span><span class="sxs-lookup"><span data-stu-id="5b758-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="5b758-p104">VTC 现已配置为可进行互操作。在开始服务前，还需在 CUCM 端执行最后几步。</span><span class="sxs-lookup"><span data-stu-id="5b758-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="5b758-164">在 CUCM 上配置 VTC 设备</span><span class="sxs-lookup"><span data-stu-id="5b758-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="5b758-165">登录到 CUCM 并导航到 Cisco 统一 CM 管理-\>设备-\>电话-\>查找。</span><span class="sxs-lookup"><span data-stu-id="5b758-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="5b758-p105">选择要配置的 VTC 设备。在“电话配置”屏幕上验证以下设置并根据需要进行更正。更改或验证这些设置后，请单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5b758-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="5b758-169">**参数**</span><span class="sxs-lookup"><span data-stu-id="5b758-169">**Parameter**</span></span>|<span data-ttu-id="5b758-170">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="5b758-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5b758-171">设备信息 - 电话按钮模板</span><span class="sxs-lookup"><span data-stu-id="5b758-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="5b758-172">标准 Cisco Telepresence 编解码器 C40</span><span class="sxs-lookup"><span data-stu-id="5b758-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="5b758-173">设备信息 - 通用电话配置文件</span><span class="sxs-lookup"><span data-stu-id="5b758-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="5b758-174">标准通用电话配置文件</span><span class="sxs-lookup"><span data-stu-id="5b758-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="5b758-175">设备信息 - 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="5b758-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="5b758-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5b758-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5b758-177">设备信息 - AAR 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="5b758-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="5b758-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5b758-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5b758-179">设备信息 - 媒体资源组列表</span><span class="sxs-lookup"><span data-stu-id="5b758-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="5b758-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5b758-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5b758-181">特定于协议的信息 - 设备安全配置文件</span><span class="sxs-lookup"><span data-stu-id="5b758-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="5b758-182">Cisco Telepresence 编解码器 C40</span><span class="sxs-lookup"><span data-stu-id="5b758-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="5b758-183">特定于协议的信息 - 重新路由呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="5b758-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="5b758-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5b758-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5b758-185">特定于协议的信息-订阅通话搜索空间</span><span class="sxs-lookup"><span data-stu-id="5b758-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="5b758-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5b758-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5b758-187">特定于协议的信息 - SIP 配置文件</span><span class="sxs-lookup"><span data-stu-id="5b758-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="5b758-188">网真终结点的标准 SIP 配置文件</span><span class="sxs-lookup"><span data-stu-id="5b758-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="5b758-189">保存 VTC 配置后，重新导航至设备的“电话配置”屏幕。</span><span class="sxs-lookup"><span data-stu-id="5b758-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="5b758-190">在“关联”组的屏幕顶部，单击“视频互操作”的关联。</span><span class="sxs-lookup"><span data-stu-id="5b758-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="5b758-191">然后将显示“目录号码配置”屏幕。</span><span class="sxs-lookup"><span data-stu-id="5b758-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="5b758-192">验证以下设置并根据需要进行更正：</span><span class="sxs-lookup"><span data-stu-id="5b758-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="5b758-193">如图所示对“目录号码信息”和“目录号码设置”进行相应的更改。</span><span class="sxs-lookup"><span data-stu-id="5b758-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="5b758-194">**参数**</span><span class="sxs-lookup"><span data-stu-id="5b758-194">**Parameter**</span></span>|<span data-ttu-id="5b758-195">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="5b758-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="5b758-196">目录号码信息 - 重新路由分区</span><span class="sxs-lookup"><span data-stu-id="5b758-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="5b758-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="5b758-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="5b758-198">目录号码设置 - 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="5b758-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="5b758-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5b758-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5b758-200">MLPP 备选方和机密访问级别设置 - MLPP 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="5b758-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="5b758-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="5b758-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="5b758-202">设备上的第1行 (来电显示)</span><span class="sxs-lookup"><span data-stu-id="5b758-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="5b758-203">根据需要</span><span class="sxs-lookup"><span data-stu-id="5b758-203">As desired</span></span> <br/> |
   |<span data-ttu-id="5b758-204">设备上的第1行-ASCII 显示 (来电显示)</span><span class="sxs-lookup"><span data-stu-id="5b758-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="5b758-205">根据需要</span><span class="sxs-lookup"><span data-stu-id="5b758-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="5b758-206">完成时，滚动至屏幕顶部并单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5b758-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="5b758-p107">现已为此 VTC 设备完成配置。您将需要为企业中的其他 VTC 设备重复此流程。</span><span class="sxs-lookup"><span data-stu-id="5b758-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>

