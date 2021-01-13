---
title: 配置 CUCM 以与 Skype for Business Server 进行互操作
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
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 摘要：配置 CUCM 以使用 Skype for Business Server。
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837112"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="17097-103">配置 CUCM 以与 Skype for Business Server 进行互操作</span><span class="sxs-lookup"><span data-stu-id="17097-103">Configure CUCM for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="17097-104">**摘要：** 配置 CUCM 以使用 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="17097-104">**Summary:** Configure CUCM to work with Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="17097-105">此功能使用 Cisco Unified Communications Manager (CallManager 或 CUCM) 版本 10.5（仅通过 TCP 的中继设置）进行测试。</span><span class="sxs-lookup"><span data-stu-id="17097-105">This capability is tested with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 using Trunks setup over TCP only.</span></span> <span data-ttu-id="17097-106">在继续之前，请验证 CUCM 环境是否满足这些条件。</span><span class="sxs-lookup"><span data-stu-id="17097-106">Verify that the CUCM environment meets these criteria before proceeding.</span></span> 
  
<span data-ttu-id="17097-107">此处所述的设置仅用作如何配置 CUCM 以使用 VIS 的示例。</span><span class="sxs-lookup"><span data-stu-id="17097-107">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="17097-108">备用 CUCM 功能的其他设置和/或用法还可用于实现相同的结果。</span><span class="sxs-lookup"><span data-stu-id="17097-108">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="17097-109">不暗示有关特定方案的最佳配置的建议。</span><span class="sxs-lookup"><span data-stu-id="17097-109">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
<span data-ttu-id="17097-110">需要确认或更改大量 CUCM 设置，以与 VIS 进行互操作。</span><span class="sxs-lookup"><span data-stu-id="17097-110">A number of CUCM settings need to be confirmed or changed for interoperation with the VIS.</span></span> <span data-ttu-id="17097-111">请按照以下过程操作，以避免缺少所需的设置。</span><span class="sxs-lookup"><span data-stu-id="17097-111">Follow the procedures below in order to avoid missing required settings.</span></span>
  
### <a name="configure-the-cucm"></a><span data-ttu-id="17097-112">配置 CUCM</span><span class="sxs-lookup"><span data-stu-id="17097-112">Configure the CUCM</span></span>

1. <span data-ttu-id="17097-113">登录到 CUCM 并导航到 Cisco Unified CM Administration- \> Call Routing- \> Class of Control- \> Partition。</span><span class="sxs-lookup"><span data-stu-id="17097-113">Log in to CUCM and navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Partition.</span></span>
    
2. <span data-ttu-id="17097-114">在分区配置屏幕中，输入分区名称和说明，然后单击"添加新 **"。**</span><span class="sxs-lookup"><span data-stu-id="17097-114">In the Partition Configuration screen, enter the partition name and description and click on **Add New**.</span></span>
    
3. <span data-ttu-id="17097-115">导航到 Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Calling Search \> Space。</span><span class="sxs-lookup"><span data-stu-id="17097-115">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Calling Search Space.</span></span>
    
4. <span data-ttu-id="17097-116">在"呼叫搜索空间配置"屏幕中，输入呼叫搜索空间的名称，在"所选分区"中，输入刚创建的分区的名称。</span><span class="sxs-lookup"><span data-stu-id="17097-116">In the Calling Search Space Configuration screen, enter the name for the calling search space, and in Selected Partitions, enter the name of the partition you just created.</span></span> <span data-ttu-id="17097-117">完成后 **单击** "保存"。</span><span class="sxs-lookup"><span data-stu-id="17097-117">Click **Save** when done.</span></span>
    
5. <span data-ttu-id="17097-118">导航到 Cisco 统一 CM 管理 - \> 系统- \> 安全性 - SIP \> 中继安全配置文件。</span><span class="sxs-lookup"><span data-stu-id="17097-118">Navigate to Cisco Unified CM Administration-\>System-\>Security-\>SIP Trunk Security Profile.</span></span>
    
6. <span data-ttu-id="17097-119">在"SIP 中继安全配置文件配置"屏幕中，按如下所示设置 SIP 中继安全配置文件信息选项，然后单击"添加新 **"。**</span><span class="sxs-lookup"><span data-stu-id="17097-119">In the SIP Trunk Security Profile Configuration screen, set the SIP Trunk Security Profile Information options as shown, and click on **Add New**.</span></span>
    
   |<span data-ttu-id="17097-120">**参数**</span><span class="sxs-lookup"><span data-stu-id="17097-120">**Parameter**</span></span>|<span data-ttu-id="17097-121">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="17097-121">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="17097-122">名称</span><span class="sxs-lookup"><span data-stu-id="17097-122">Name</span></span>  <br/> |<span data-ttu-id="17097-123">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="17097-123">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
   |<span data-ttu-id="17097-124">设备安全模式</span><span class="sxs-lookup"><span data-stu-id="17097-124">Device Security Mode</span></span>  <br/> |<span data-ttu-id="17097-125">非安全</span><span class="sxs-lookup"><span data-stu-id="17097-125">Non Secure</span></span>  <br/> |
   |<span data-ttu-id="17097-126">传入传输类型</span><span class="sxs-lookup"><span data-stu-id="17097-126">Incoming Transport Type</span></span>  <br/> |<span data-ttu-id="17097-127">TCP + UDP</span><span class="sxs-lookup"><span data-stu-id="17097-127">TCP + UDP</span></span>  <br/> |
   |<span data-ttu-id="17097-128">传出传输类型</span><span class="sxs-lookup"><span data-stu-id="17097-128">Outgoing Transport Type</span></span>  <br/> |<span data-ttu-id="17097-129">TCP</span><span class="sxs-lookup"><span data-stu-id="17097-129">TCP</span></span>  <br/> |
   |<span data-ttu-id="17097-130">传入端口</span><span class="sxs-lookup"><span data-stu-id="17097-130">Incoming Port</span></span>  <br/> |<span data-ttu-id="17097-131">5060</span><span class="sxs-lookup"><span data-stu-id="17097-131">5060</span></span>  <br/> |
   
7. <span data-ttu-id="17097-132">导航到 Cisco 统一 CM 管理 - \> 设备- \> 设备设置 - \> SIP 配置文件。</span><span class="sxs-lookup"><span data-stu-id="17097-132">Navigate to Cisco Unified CM Administration-\>Device-\>Device Settings-\>SIP Profile.</span></span>
    
8. <span data-ttu-id="17097-133">在"SIP 配置文件配置"屏幕中，设置 SIP 配置文件信息选项，如下所示。</span><span class="sxs-lookup"><span data-stu-id="17097-133">In the SIP Profile Configuration screen, set the SIP Profile Information options as shown.</span></span> 
    
   |<span data-ttu-id="17097-134">**参数**</span><span class="sxs-lookup"><span data-stu-id="17097-134">**Parameter**</span></span>|<span data-ttu-id="17097-135">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="17097-135">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="17097-136">名称</span><span class="sxs-lookup"><span data-stu-id="17097-136">Name</span></span>  <br/> |<span data-ttu-id="17097-137">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="17097-137">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   |<span data-ttu-id="17097-138">说明</span><span class="sxs-lookup"><span data-stu-id="17097-138">Description</span></span>  <br/> |<span data-ttu-id="17097-139">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="17097-139">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   
9. <span data-ttu-id="17097-140">在同一屏幕上，向下滚动到"SDP 配置文件信息"部分。</span><span class="sxs-lookup"><span data-stu-id="17097-140">On the same screen, scroll down to the SDP Profile Information section.</span></span> <span data-ttu-id="17097-141">默认情况下 **，"提前提供"** 和"重新邀请"选项的 SDP 会话级别带宽修饰符设置为 TIAS 和 AS。</span><span class="sxs-lookup"><span data-stu-id="17097-141">The **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** option is set by default to TIAS and AS.</span></span> <span data-ttu-id="17097-142">仅将此选项更改为 TIAS。</span><span class="sxs-lookup"><span data-stu-id="17097-142">Change this option to TIAS only.</span></span> <span data-ttu-id="17097-143">如果将此选项保留为默认设置，Skype for Business Server 将不能了解 SIP 消息中的带宽修饰符信息。</span><span class="sxs-lookup"><span data-stu-id="17097-143">If you leave this option at its default setting, Skype for Business Server will not understand the bandwidth modifier information in the SIP message.</span></span> <span data-ttu-id="17097-144">TIAS 表示"特定于传输独立应用程序"，而"AS"表示"特定于应用程序"。</span><span class="sxs-lookup"><span data-stu-id="17097-144">TIAS means Transport Independent Application Specific while AS means Application Specific.</span></span> <span data-ttu-id="17097-145">这些是 RFC3890 中指定的 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="17097-145">These are SIP options specified in RFC3890.</span></span>
    
10. <span data-ttu-id="17097-146">在同一屏幕上，进一步向下滚动。</span><span class="sxs-lookup"><span data-stu-id="17097-146">On the same screen, scroll down further.</span></span> <span data-ttu-id="17097-147">在 SIP 配置文件的"特定中继配置"下，选择"语音和视频呼叫的早期提供支持"，并将其设置为"强制 (**插入 MTP（** 如果需要) 选项）。</span><span class="sxs-lookup"><span data-stu-id="17097-147">Under the SIP Profile's Trunk Specific Configuration, select **Early Offer Support for voice and video calls** and set it to the **Mandatory (insert MTP if needed)** option.</span></span> <span data-ttu-id="17097-148">这将允许 CUCM 设置具有早期优惠的传出 SIP 呼叫。</span><span class="sxs-lookup"><span data-stu-id="17097-148">This will enable CUCM to set up an outgoing SIP call with Early Offer.</span></span> <span data-ttu-id="17097-149">CUCM 8.5 及以后的一项新功能是，它支持具有早期优惠的传出呼叫设置，而无需媒体 (MTP) 。</span><span class="sxs-lookup"><span data-stu-id="17097-149">One new feature in CUCM 8.5 and beyond is that it supports outgoing call setup with Early Offer without requiring Media Termination Point (MTP).</span></span>
    
11. <span data-ttu-id="17097-150">确认在"SIP 选项 ping"部分，选中了"启用 OPTIONS Ping 以监视服务类型为'无或默认 ('的中继的目标状态) "。</span><span class="sxs-lookup"><span data-stu-id="17097-150">Verify that in the SIP Options ping section, the box is checked next to "Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'."</span></span>
    
12. <span data-ttu-id="17097-151">完成后，单击"添加新 **"。**</span><span class="sxs-lookup"><span data-stu-id="17097-151">When you are finished, click on **Add New**.</span></span>
    
13. <span data-ttu-id="17097-152">导航到 Cisco Unified CM Administration- \> Device- \> Trunk。</span><span class="sxs-lookup"><span data-stu-id="17097-152">Navigate to Cisco Unified CM Administration-\>Device-\>Trunk.</span></span> 
    
14. <span data-ttu-id="17097-153">将设备协议设置为 SIP 并按"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="17097-153">Set the Device Protocol to SIP and press **Next**.</span></span>
    
15. <span data-ttu-id="17097-154">在"设备信息"下，将设备名称和说明 (设置为 SfBVideoInterop_SIPTrunk) ，将媒体资源组列表设置为包含正确媒体资源的 MRGL。</span><span class="sxs-lookup"><span data-stu-id="17097-154">Under Device Information, Set the Device Name and Description (probably to something like SfBVideoInterop_SIPTrunk), and set the Media Resource Group List to an MRGL that contains the right media resources.</span></span> 
    
16. <span data-ttu-id="17097-155">进一步向下滚动。</span><span class="sxs-lookup"><span data-stu-id="17097-155">Scroll down further.</span></span> <span data-ttu-id="17097-156">视频呼叫 (MTP) ，如果尚未取消选中，请取消选中它。</span><span class="sxs-lookup"><span data-stu-id="17097-156">Media Termination Point (MTP) is not required for Video Calls, if it is not already unchecked, uncheck it.</span></span> <span data-ttu-id="17097-157">选中"在所有 **活动统一 CM 节点上运行"选项**。</span><span class="sxs-lookup"><span data-stu-id="17097-157">Check the option to **Run on all active Unified CM Nodes**.</span></span> <span data-ttu-id="17097-158">请注意，你应该将所有 CUCM 节点添加到 Skype for Business Server 配置。</span><span class="sxs-lookup"><span data-stu-id="17097-158">Please note that you should add all CUCM nodes to the Skype for Business Server configuration.</span></span>
    
17. <span data-ttu-id="17097-159">进一步向下滚动。</span><span class="sxs-lookup"><span data-stu-id="17097-159">Scroll down further.</span></span> <span data-ttu-id="17097-160">设置"入站呼叫和连接方设置"选项，如下所示。</span><span class="sxs-lookup"><span data-stu-id="17097-160">Set the Inbound Calls and Connected Party Settings options as shown.</span></span>
    
    |<span data-ttu-id="17097-161">**参数**</span><span class="sxs-lookup"><span data-stu-id="17097-161">**Parameter**</span></span>|<span data-ttu-id="17097-162">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="17097-162">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="17097-163">调用搜索空间</span><span class="sxs-lookup"><span data-stu-id="17097-163">Calling Search Space</span></span>  <br/> |<span data-ttu-id="17097-164">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="17097-164">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="17097-165">AAR 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="17097-165">AAR Calling Search Space</span></span>  <br/> |<span data-ttu-id="17097-166">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="17097-166">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="17097-167">连接方转换 CSS</span><span class="sxs-lookup"><span data-stu-id="17097-167">Connected Party Transformation CSS</span></span>  <br/> |<span data-ttu-id="17097-168">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="17097-168">CSS_SfBVideoInterop</span></span>  <br/> |
   
18. <span data-ttu-id="17097-169">进一步向下滚动。</span><span class="sxs-lookup"><span data-stu-id="17097-169">Scroll down further.</span></span> <span data-ttu-id="17097-170">在 SIP 中继配置的"SIP 信息目标"部分下，指定 VIS 池的 FQDN 或池中各个 VIS 服务器的 IP 地址， (添加多个) 。</span><span class="sxs-lookup"><span data-stu-id="17097-170">Under the SIP Information Destination section of the SIP Trunk configuration, specify the VIS Pool's FQDN or the IP address of individual VIS servers in the pool (adding multiple entries).</span></span> <span data-ttu-id="17097-171">在"目标端口"中，指定 VIS 侦听来自 CUCM 的连接的端口 (默认值为 6001) 。</span><span class="sxs-lookup"><span data-stu-id="17097-171">In the Destination Port specify the Port that VIS is listening at for connections from CUCM (the default is 6001).</span></span> <span data-ttu-id="17097-172">还要指定之前创建的 SIP 中继安全配置文件和 SIP 配置文件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="17097-172">Also specify the SIP Trunk security profile and SIP profile you created earlier, as shown.</span></span>
    
    |<span data-ttu-id="17097-173">**参数**</span><span class="sxs-lookup"><span data-stu-id="17097-173">**Parameter**</span></span>|<span data-ttu-id="17097-174">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="17097-174">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="17097-175">SIP 中继安全配置文件</span><span class="sxs-lookup"><span data-stu-id="17097-175">SIP Trunk Security Profile</span></span>  <br/> |<span data-ttu-id="17097-176">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="17097-176">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
    |<span data-ttu-id="17097-177">重新路由呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="17097-177">Rerouting Calling Search Space</span></span>  <br/> |<span data-ttu-id="17097-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="17097-178">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="17097-179">Out-of-Dialog Refer Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="17097-179">Out-of-Dialog Refer Calling Search Space</span></span>  <br/> |<span data-ttu-id="17097-180">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="17097-180">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="17097-181">订阅呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="17097-181">Subscribe Calling Search Space</span></span>  <br/> |<span data-ttu-id="17097-182">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="17097-182">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="17097-183">SIP 配置文件</span><span class="sxs-lookup"><span data-stu-id="17097-183">SIP Profile</span></span>  <br/> |<span data-ttu-id="17097-184">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="17097-184">SfBVideoInterop_SIPProfile</span></span>  <br/> |
    |<span data-ttu-id="17097-185">DTMF 信号方法</span><span class="sxs-lookup"><span data-stu-id="17097-185">DTMF Signaling Method</span></span>  <br/> |<span data-ttu-id="17097-186">RFC 2833</span><span class="sxs-lookup"><span data-stu-id="17097-186">RFC 2833</span></span>  <br/> |
   
19.  <span data-ttu-id="17097-187">进一步向下滚动。</span><span class="sxs-lookup"><span data-stu-id="17097-187">Scroll down further.</span></span> <span data-ttu-id="17097-188">根据系统情况设置录制信息。</span><span class="sxs-lookup"><span data-stu-id="17097-188">Set the Recording Information as appropriate for your system.</span></span> <span data-ttu-id="17097-189">可以保持其设置为"无 **"。**</span><span class="sxs-lookup"><span data-stu-id="17097-189">It's fine to leave it set to **None**.</span></span> 
    
20. <span data-ttu-id="17097-190">完成后，单击"添加新 **"。**</span><span class="sxs-lookup"><span data-stu-id="17097-190">When you are finished, click on **Add New**.</span></span>
    
21. <span data-ttu-id="17097-191">导航到 Cisco 统一 CM 管理 - \> 呼叫路由- \> 路由/智能 \> 寻线模式。</span><span class="sxs-lookup"><span data-stu-id="17097-191">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Route/Hunt-\>Route pattern.</span></span>
    
22. <span data-ttu-id="17097-192">在"路由模式配置"屏幕中，输入如下所示的模式定义参数。</span><span class="sxs-lookup"><span data-stu-id="17097-192">In the Route Pattern Configuration screen, enter the Pattern definition parameters shown below.</span></span> <span data-ttu-id="17097-193">向下滚动到"被叫方转换"部分并按如下所示设置掩码，然后在完成后单击"添加新"。</span><span class="sxs-lookup"><span data-stu-id="17097-193">Scroll down to the Called Party Transformations section and set the mask as shown, and then click on **Add New** when finished.</span></span>
    
    |<span data-ttu-id="17097-194">**参数**</span><span class="sxs-lookup"><span data-stu-id="17097-194">**Parameter**</span></span>|<span data-ttu-id="17097-195">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="17097-195">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="17097-196">路由模式</span><span class="sxs-lookup"><span data-stu-id="17097-196">Route Pattern</span></span>  <br/> |<span data-ttu-id="17097-197">7779999</span><span class="sxs-lookup"><span data-stu-id="17097-197">7779999</span></span>  <br/> |
    |<span data-ttu-id="17097-198">路由分区</span><span class="sxs-lookup"><span data-stu-id="17097-198">Route Partition</span></span>  <br/> |<span data-ttu-id="17097-199">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="17097-199">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="17097-200">说明</span><span class="sxs-lookup"><span data-stu-id="17097-200">Description</span></span>  <br/> |<span data-ttu-id="17097-201">SfBVideoInterop 的分区</span><span class="sxs-lookup"><span data-stu-id="17097-201">Partition for SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="17097-202">网关/路由列表</span><span class="sxs-lookup"><span data-stu-id="17097-202">Gateway/Route List</span></span>  <br/> |<span data-ttu-id="17097-203">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="17097-203">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="17097-204">被叫方转换掩码</span><span class="sxs-lookup"><span data-stu-id="17097-204">Called Party Transform Mask</span></span>  <br/> |<span data-ttu-id="17097-205">+14257779999</span><span class="sxs-lookup"><span data-stu-id="17097-205">+14257779999</span></span>  <br/> |
   
23. <span data-ttu-id="17097-206">导航到 Cisco 统一 CM 管理- \> 呼叫路由 - \> SIP 路由模式。</span><span class="sxs-lookup"><span data-stu-id="17097-206">Navigate to Cisco Unified CM Administration-\>Call Routing-\>SIP Route Pattern.</span></span>
    
24. <span data-ttu-id="17097-207">在 SIP 路由模式配置屏幕中，按如下所示设置模式定义选项，然后单击"添加新 **"。**</span><span class="sxs-lookup"><span data-stu-id="17097-207">In the SIP Route Pattern Configuration screen, set the Pattern Definition options as shown, and click on **Add New**.</span></span>
    
    |<span data-ttu-id="17097-208">**参数**</span><span class="sxs-lookup"><span data-stu-id="17097-208">**Parameter**</span></span>|<span data-ttu-id="17097-209">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="17097-209">**Recommended setting**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="17097-210">模式用法</span><span class="sxs-lookup"><span data-stu-id="17097-210">Pattern Usage</span></span> <br/> |<span data-ttu-id="17097-211">域路由</span><span class="sxs-lookup"><span data-stu-id="17097-211">Domain Routing</span></span>  <br/> |
    |<span data-ttu-id="17097-212">IPv4 模式</span><span class="sxs-lookup"><span data-stu-id="17097-212">IPv4 Pattern</span></span>  <br/> |<span data-ttu-id="17097-213">contoso.com (IPv6) </span><span class="sxs-lookup"><span data-stu-id="17097-213">contoso.com (leave blank if using IPv6)</span></span>  <br/> |
    |<span data-ttu-id="17097-214">IPv6 模式</span><span class="sxs-lookup"><span data-stu-id="17097-214">IPv6 Pattern</span></span>  <br/> |<span data-ttu-id="17097-215">contoso.com (IPv4) </span><span class="sxs-lookup"><span data-stu-id="17097-215">contoso.com (leave blank if using IPv4)</span></span>  <br/> |
    |<span data-ttu-id="17097-216">说明</span><span class="sxs-lookup"><span data-stu-id="17097-216">Description</span></span>  <br/> |<span data-ttu-id="17097-217">到 mediarv 的 SIPRoute 模式</span><span class="sxs-lookup"><span data-stu-id="17097-217">SIPRoute Pattern to mediarv</span></span>  <br/> |
    |<span data-ttu-id="17097-218">路由分区</span><span class="sxs-lookup"><span data-stu-id="17097-218">Route Partition</span></span>  <br/> |<span data-ttu-id="17097-219">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="17097-219">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="17097-220">SIP 中继/路由列表</span><span class="sxs-lookup"><span data-stu-id="17097-220">SIP Trunk/Route List</span></span>  <br/> |<span data-ttu-id="17097-221">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="17097-221">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="17097-222">阻止模式复选框</span><span class="sxs-lookup"><span data-stu-id="17097-222">Block Pattern checkbox</span></span>  <br/> |<span data-ttu-id="17097-223">保留未选中状态</span><span class="sxs-lookup"><span data-stu-id="17097-223">leave unchecked</span></span>  <br/> |
   
25. <span data-ttu-id="17097-224">如果已更改默认设置中的音频或视频比特率，则需要将其恢复为默认值。</span><span class="sxs-lookup"><span data-stu-id="17097-224">If you have changed the audio or video bit rates from the default settings, you will need to return them to the defaults.</span></span> <span data-ttu-id="17097-225">若要设置音频/视频呼叫的比特率，请导航到"Cisco 统一 CM 管理- \> 系统- 区域 \> 信息- \> 区域"。</span><span class="sxs-lookup"><span data-stu-id="17097-225">To set the bit rate for Audio/Video calls, navigate to Cisco Unified CM Administration-\>System-\>Region Information-\>Region.</span></span> <span data-ttu-id="17097-226">下面显示了默认值，仅供参考：</span><span class="sxs-lookup"><span data-stu-id="17097-226">The defaults are shown below for reference:</span></span>
    
    |<span data-ttu-id="17097-227">**参数**</span><span class="sxs-lookup"><span data-stu-id="17097-227">**Parameter**</span></span>|<span data-ttu-id="17097-228">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="17097-228">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="17097-229">地区</span><span class="sxs-lookup"><span data-stu-id="17097-229">Region</span></span>  <br/> |<span data-ttu-id="17097-230">默认</span><span class="sxs-lookup"><span data-stu-id="17097-230">Default</span></span>  <br/> |
    |<span data-ttu-id="17097-231">音频编解码器首选项列表</span><span class="sxs-lookup"><span data-stu-id="17097-231">Audio Codec Preference List</span></span>  <br/> |<span data-ttu-id="17097-232">系统默认值</span><span class="sxs-lookup"><span data-stu-id="17097-232">System Default</span></span>  <br/> |
    |<span data-ttu-id="17097-233">最大音频比特率</span><span class="sxs-lookup"><span data-stu-id="17097-233">Maximum Audio Bit Rate</span></span>  <br/> |<span data-ttu-id="17097-234">64 kbps (G.722、G.711) </span><span class="sxs-lookup"><span data-stu-id="17097-234">64 kbps (G.722, G.711)</span></span>  <br/> |
    |<span data-ttu-id="17097-235">视频呼叫的最大会话比特率</span><span class="sxs-lookup"><span data-stu-id="17097-235">Maximum Session Bit Rate for Video Calls</span></span>  <br/> |<span data-ttu-id="17097-236">200000 kbps</span><span class="sxs-lookup"><span data-stu-id="17097-236">200000 kbps</span></span>  <br/> |
    |<span data-ttu-id="17097-237">最大会话比特率</span><span class="sxs-lookup"><span data-stu-id="17097-237">Maximum Session Bit Rate</span></span>  <br/> |<span data-ttu-id="17097-238">20000000000 kbps</span><span class="sxs-lookup"><span data-stu-id="17097-238">2000000000 kbps</span></span>  <br/> |
   
<span data-ttu-id="17097-239">此时，CUCM 视频网关已配置为与 VIS 一起工作。</span><span class="sxs-lookup"><span data-stu-id="17097-239">At this point the CUCM video gateway is configured to work with the VIS.</span></span> <span data-ttu-id="17097-240">需要在要集成的每个 VTC 上执行相应的配置。</span><span class="sxs-lookup"><span data-stu-id="17097-240">Corresponding configuration will need to be done on each VTC you wish to integrate.</span></span>
> [!NOTE]
> <span data-ttu-id="17097-241">为了提高恢复能力，您可能需要配置此 CUCM 网关以使用第二个视频互操作服务器或 VIS 池。</span><span class="sxs-lookup"><span data-stu-id="17097-241">To improve resiliency, you may want to configure this CUCM gateway to work with a second Video Interop Server or VIS pool.</span></span> <span data-ttu-id="17097-242">有关详细信息 [，请参阅](../../plan-your-deployment/video-interop-server.md#resiliency) 复原机制。</span><span class="sxs-lookup"><span data-stu-id="17097-242">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="17097-243">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17097-243">See also</span></span>

[<span data-ttu-id="17097-244">配置 VTC 以与 Skype for Business Server 进行互操作</span><span class="sxs-lookup"><span data-stu-id="17097-244">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
