---
title: 为业务服务器与 Skype 的互操作配置 CUCM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 摘要： 配置 CUCM 以使用 Skype 业务服务器。
ms.openlocfilehash: 58896a635b389ca18506ca775ae4fb7715caf0ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894568"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="15edf-103">为业务服务器与 Skype 的互操作配置 CUCM</span><span class="sxs-lookup"><span data-stu-id="15edf-103">Configure CUCM for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="15edf-104">**摘要：** 配置 CUCM 以使用 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="15edf-104">**Summary:** Configure CUCM to work with Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="15edf-105">此功能测试与 Cisco 统一通信管理器 （CallManager 或 CUCM） 版本使用中继的 10.5 tcp 仅安装。</span><span class="sxs-lookup"><span data-stu-id="15edf-105">This capability is tested with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 using Trunks setup over TCP only.</span></span> <span data-ttu-id="15edf-106">请验证 CUCM 环境是否满足这些条件，然后方可继续下一步。</span><span class="sxs-lookup"><span data-stu-id="15edf-106">Verify that the CUCM environment meets these criteria before proceeding.</span></span> 
  
<span data-ttu-id="15edf-107">此处所述的设置，旨在仅作为 CUCM 可以配置方式的示例使用 VIS.</span><span class="sxs-lookup"><span data-stu-id="15edf-107">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="15edf-108">也可使用其他设置和/或备选 CUCM 功能来实现同样的结果。</span><span class="sxs-lookup"><span data-stu-id="15edf-108">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="15edf-109">示例中不对适用于特定场景的最佳配置作任何推荐暗示。</span><span class="sxs-lookup"><span data-stu-id="15edf-109">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
<span data-ttu-id="15edf-p103">需要确认或更改大量 CUCM 设置才能与 VIS 进行互操作。请按照以下过程操作以避免错过必要的设置。</span><span class="sxs-lookup"><span data-stu-id="15edf-p103">A number of CUCM settings need to be confirmed or changed for interoperation with the VIS. Follow the procedures below in order to avoid missing required settings.</span></span>
  
### <a name="configure-the-cucm"></a><span data-ttu-id="15edf-112">配置 CUCM</span><span class="sxs-lookup"><span data-stu-id="15edf-112">Configure the CUCM</span></span>

1. <span data-ttu-id="15edf-113">登录到 CUCM 并导航到 Cisco 统一厘米管理-\>呼叫路由-\>类的控件-\>分区。</span><span class="sxs-lookup"><span data-stu-id="15edf-113">Log in to CUCM and navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Partition.</span></span>
    
2. <span data-ttu-id="15edf-114">在“分区配置”屏幕中，输入分区名称和说明，然后单击“**新增**”。</span><span class="sxs-lookup"><span data-stu-id="15edf-114">In the Partition Configuration screen, enter the partition name and description and click on **Add New**.</span></span>
    
3. <span data-ttu-id="15edf-115">导航到 Cisco 统一厘米管理-\>呼叫路由-\>控件-类\>调用搜索空间。</span><span class="sxs-lookup"><span data-stu-id="15edf-115">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Calling Search Space.</span></span>
    
4. <span data-ttu-id="15edf-p104">在“呼叫搜索空间配置”屏幕中，输入呼叫搜索空间的名称，然后在“所选分区”中输入刚才创建的分区名称。完成时，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="15edf-p104">In the Calling Search Space Configuration screen, enter the name for the calling search space, and in Selected Partitions, enter the name of the partition you just created. Click **Save** when done.</span></span>
    
5. <span data-ttu-id="15edf-118">导航到 Cisco 统一厘米管理-\>系统-\>安全-\>SIP 中继的安全配置文件。</span><span class="sxs-lookup"><span data-stu-id="15edf-118">Navigate to Cisco Unified CM Administration-\>System-\>Security-\>SIP Trunk Security Profile.</span></span>
    
6. <span data-ttu-id="15edf-119">在“SIP 中继安全配置文件配置”屏幕中，如图所示设置“SIP 中继安全配置文件信息”选项，然后单击“**新增**”。</span><span class="sxs-lookup"><span data-stu-id="15edf-119">In the SIP Trunk Security Profile Configuration screen, set the SIP Trunk Security Profile Information options as shown, and click on **Add New**.</span></span>
    
   |<span data-ttu-id="15edf-120">**参数**</span><span class="sxs-lookup"><span data-stu-id="15edf-120">**Parameter**</span></span>|<span data-ttu-id="15edf-121">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="15edf-121">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="15edf-122">名称</span><span class="sxs-lookup"><span data-stu-id="15edf-122">Name</span></span>  <br/> |<span data-ttu-id="15edf-123">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="15edf-123">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
   |<span data-ttu-id="15edf-124">设备安全模式</span><span class="sxs-lookup"><span data-stu-id="15edf-124">Device Security Mode</span></span>  <br/> |<span data-ttu-id="15edf-125">非安全</span><span class="sxs-lookup"><span data-stu-id="15edf-125">Non Secure</span></span>  <br/> |
   |<span data-ttu-id="15edf-126">传入传输类型</span><span class="sxs-lookup"><span data-stu-id="15edf-126">Incoming Transport Type</span></span>  <br/> |<span data-ttu-id="15edf-127">TCP + UDP</span><span class="sxs-lookup"><span data-stu-id="15edf-127">TCP + UDP</span></span>  <br/> |
   |<span data-ttu-id="15edf-128">传出传输类型</span><span class="sxs-lookup"><span data-stu-id="15edf-128">Outgoing Transport Type</span></span>  <br/> |<span data-ttu-id="15edf-129">TCP</span><span class="sxs-lookup"><span data-stu-id="15edf-129">TCP</span></span>  <br/> |
   |<span data-ttu-id="15edf-130">传入端口</span><span class="sxs-lookup"><span data-stu-id="15edf-130">Incoming Port</span></span>  <br/> |<span data-ttu-id="15edf-131">5060</span><span class="sxs-lookup"><span data-stu-id="15edf-131">5060</span></span>  <br/> |
   
7. <span data-ttu-id="15edf-132">导航到 Cisco 统一厘米管理-\>设备-\>设备设置-\>SIP 配置文件。</span><span class="sxs-lookup"><span data-stu-id="15edf-132">Navigate to Cisco Unified CM Administration-\>Device-\>Device Settings-\>SIP Profile.</span></span>
    
8. <span data-ttu-id="15edf-133">在“SIP 配置文件配置”屏幕中，如图所示设置“SIP 配置文件信息”选项。</span><span class="sxs-lookup"><span data-stu-id="15edf-133">In the SIP Profile Configuration screen, set the SIP Profile Information options as shown.</span></span> 
    
   |<span data-ttu-id="15edf-134">**参数**</span><span class="sxs-lookup"><span data-stu-id="15edf-134">**Parameter**</span></span>|<span data-ttu-id="15edf-135">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="15edf-135">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="15edf-136">名称</span><span class="sxs-lookup"><span data-stu-id="15edf-136">Name</span></span>  <br/> |<span data-ttu-id="15edf-137">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="15edf-137">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   |<span data-ttu-id="15edf-138">说明</span><span class="sxs-lookup"><span data-stu-id="15edf-138">Description</span></span>  <br/> |<span data-ttu-id="15edf-139">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="15edf-139">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   
9. <span data-ttu-id="15edf-140">在同一个屏幕上，向下滚动 SDP 配置文件信息部分。</span><span class="sxs-lookup"><span data-stu-id="15edf-140">On the same screen, scroll down to the SDP Profile Information section.</span></span> <span data-ttu-id="15edf-141">“**Early Offer 和重新邀请的 SDP 会话级别带宽修饰符**”选项默认设为 TIAS 和 AS。</span><span class="sxs-lookup"><span data-stu-id="15edf-141">The **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** option is set by default to TIAS and AS.</span></span> <span data-ttu-id="15edf-142">将此选项更改为仅 TIAS。</span><span class="sxs-lookup"><span data-stu-id="15edf-142">Change this option to TIAS only.</span></span> <span data-ttu-id="15edf-143">如果您将此选项保留为其默认设置，Skype 业务服务器不能理解的 SIP 消息对话中的带宽修饰符信息。</span><span class="sxs-lookup"><span data-stu-id="15edf-143">If you leave this option at its default setting, Skype for Business Server will not understand the bandwidth modifier information in the SIP message.</span></span> <span data-ttu-id="15edf-144">TIAS 表示 Transport Independent Application Specific（特定于传输独立的应用程序），AS 表示 Application Specific（特定于应用程序）。</span><span class="sxs-lookup"><span data-stu-id="15edf-144">TIAS means Transport Independent Application Specific while AS means Application Specific.</span></span> <span data-ttu-id="15edf-145">这些是在 RFC3890 中指定的 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="15edf-145">These are SIP options specified in RFC3890.</span></span>
    
10. <span data-ttu-id="15edf-146">在同一屏幕上，继续向下滚动。</span><span class="sxs-lookup"><span data-stu-id="15edf-146">On the same screen, scroll down further.</span></span> <span data-ttu-id="15edf-147">SIP 配置文件的中继特定配置下选择**的语音和视频呼叫的最早提供支持**，并将其设置为**强制 （插入 MTP 如果需要）** 选项。</span><span class="sxs-lookup"><span data-stu-id="15edf-147">Under the SIP Profile's Trunk Specific Configuration, select **Early Offer Support for voice and video calls** and set it to the **Mandatory (insert MTP if needed)** option.</span></span> <span data-ttu-id="15edf-148">这使得 CUCM 能够设置具有 Early Offer 的传出 SIP 呼叫。</span><span class="sxs-lookup"><span data-stu-id="15edf-148">This will enable CUCM to set up an outgoing SIP call with Early Offer.</span></span> <span data-ttu-id="15edf-149">CUCM 8.5 中有一些新增功能，其中一个在于，它无需媒体端点 (MTP) 便可支持具有 Early Offer 的传出呼叫设置。</span><span class="sxs-lookup"><span data-stu-id="15edf-149">One new feature in CUCM 8.5 and beyond is that it supports outgoing call setup with Early Offer without requiring Media Termination Point (MTP).</span></span>
    
11. <span data-ttu-id="15edf-150">在“SIP 选项 ping”部分，验证是否选中“启用选项 Ping 以监控具有服务类型‘无（默认）’的中继的目标状态”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="15edf-150">Verify that in the SIP Options ping section, the box is checked next to "Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'."</span></span>
    
12. <span data-ttu-id="15edf-151">完成后，单击“**新增**”。</span><span class="sxs-lookup"><span data-stu-id="15edf-151">When you are finished, click on **Add New**.</span></span>
    
13. <span data-ttu-id="15edf-152">导航到 Cisco 统一厘米管理-\>设备-\>中继。</span><span class="sxs-lookup"><span data-stu-id="15edf-152">Navigate to Cisco Unified CM Administration-\>Device-\>Trunk.</span></span> 
    
14. <span data-ttu-id="15edf-153">将设备协议设为 SIP，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="15edf-153">Set the Device Protocol to SIP and press **Next**.</span></span>
    
15. <span data-ttu-id="15edf-154">在“设备信息”下，设置“设备名称”和“说明”（比如 SfBVideoInterop_SIPTrunk），然后将“媒体资源组列表”设为包含正确的媒体资源的 MRGL。</span><span class="sxs-lookup"><span data-stu-id="15edf-154">Under Device Information, Set the Device Name and Description (probably to something like SfBVideoInterop_SIPTrunk), and set the Media Resource Group List to an MRGL that contains the right media resources.</span></span> 
    
16. <span data-ttu-id="15edf-155">继续向下滚动。</span><span class="sxs-lookup"><span data-stu-id="15edf-155">Scroll down further.</span></span> <span data-ttu-id="15edf-156">视频呼叫无需媒体端点 (MTP)，如果尚未取消选中它，请取消选中。</span><span class="sxs-lookup"><span data-stu-id="15edf-156">Media Termination Point (MTP) is not required for Video Calls, if it is not already unchecked, uncheck it.</span></span> <span data-ttu-id="15edf-157">选中“**在所有活动统一 CM 节点上运行**”的选项。</span><span class="sxs-lookup"><span data-stu-id="15edf-157">Check the option to **Run on all active Unified CM Nodes**.</span></span> <span data-ttu-id="15edf-158">请注意，您应将所有 CUCM 节点都添加到业务服务器配置的 Skype。</span><span class="sxs-lookup"><span data-stu-id="15edf-158">Please note that you should add all CUCM nodes to the Skype for Business Server configuration.</span></span>
    
17. <span data-ttu-id="15edf-p108">继续向下滚动。如图所示设置“入站呼叫”和“连接方设置”选项。</span><span class="sxs-lookup"><span data-stu-id="15edf-p108">Scroll down further. Set the Inbound Calls and Connected Party Settings options as shown.</span></span>
    
    |<span data-ttu-id="15edf-161">**参数**</span><span class="sxs-lookup"><span data-stu-id="15edf-161">**Parameter**</span></span>|<span data-ttu-id="15edf-162">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="15edf-162">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="15edf-163">呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="15edf-163">Calling Search Space</span></span>  <br/> |<span data-ttu-id="15edf-164">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="15edf-164">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="15edf-165">AAR 呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="15edf-165">AAR Calling Search Space</span></span>  <br/> |<span data-ttu-id="15edf-166">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="15edf-166">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="15edf-167">连接方转换 CSS</span><span class="sxs-lookup"><span data-stu-id="15edf-167">Connected Party Transformation CSS</span></span>  <br/> |<span data-ttu-id="15edf-168">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="15edf-168">CSS_SfBVideoInterop</span></span>  <br/> |
   
18. <span data-ttu-id="15edf-169">继续向下滚动。</span><span class="sxs-lookup"><span data-stu-id="15edf-169">Scroll down further.</span></span> <span data-ttu-id="15edf-170">在 SIP 中继配置的 SIP 信息目标部分中，在池 （添加多个条目） 指定 VIS 池的 FQDN 或 IP 地址的单个 VIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="15edf-170">Under the SIP Information Destination section of the SIP Trunk configuration, specify the VIS Pool's FQDN or the IP address of individual VIS servers in the pool (adding multiple entries).</span></span> <span data-ttu-id="15edf-171">在目标端口指定 VIS 正在监听来自 CUCM 的连接的端口 （默认为 6001）。</span><span class="sxs-lookup"><span data-stu-id="15edf-171">In the Destination Port specify the Port that VIS is listening at for connections from CUCM (the default is 6001).</span></span> <span data-ttu-id="15edf-172">此外指定的 SIP 中继安全配置文件和更早版本，创建的 SIP 配置文件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="15edf-172">Also specify the SIP Trunk security profile and SIP profile you created earlier, as shown.</span></span>
    
    |<span data-ttu-id="15edf-173">**参数**</span><span class="sxs-lookup"><span data-stu-id="15edf-173">**Parameter**</span></span>|<span data-ttu-id="15edf-174">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="15edf-174">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="15edf-175">SIP 中继安全配置文件</span><span class="sxs-lookup"><span data-stu-id="15edf-175">SIP Trunk Security Profile</span></span>  <br/> |<span data-ttu-id="15edf-176">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="15edf-176">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
    |<span data-ttu-id="15edf-177">重新路由呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="15edf-177">Rerouting Calling Search Space</span></span>  <br/> |<span data-ttu-id="15edf-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="15edf-178">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="15edf-179">Out-of-Dialog 引用呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="15edf-179">Out-of-Dialog Refer Calling Search Space</span></span>  <br/> |<span data-ttu-id="15edf-180">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="15edf-180">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="15edf-181">订阅呼叫搜索空间</span><span class="sxs-lookup"><span data-stu-id="15edf-181">Subscribe Calling Search Space</span></span>  <br/> |<span data-ttu-id="15edf-182">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="15edf-182">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="15edf-183">SIP 配置文件</span><span class="sxs-lookup"><span data-stu-id="15edf-183">SIP Profile</span></span>  <br/> |<span data-ttu-id="15edf-184">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="15edf-184">SfBVideoInterop_SIPProfile</span></span>  <br/> |
    |<span data-ttu-id="15edf-185">DTMF 信号方法</span><span class="sxs-lookup"><span data-stu-id="15edf-185">DTMF Signaling Method</span></span>  <br/> |<span data-ttu-id="15edf-186">RFC 2833</span><span class="sxs-lookup"><span data-stu-id="15edf-186">RFC 2833</span></span>  <br/> |
   
19.  <span data-ttu-id="15edf-187">继续向下滚动。</span><span class="sxs-lookup"><span data-stu-id="15edf-187">Scroll down further.</span></span> <span data-ttu-id="15edf-188">为您的系统设置相应的“记录信息”。</span><span class="sxs-lookup"><span data-stu-id="15edf-188">Set the Recording Information as appropriate for your system.</span></span> <span data-ttu-id="15edf-189">若要将其设置为**None**没关系。</span><span class="sxs-lookup"><span data-stu-id="15edf-189">It's fine to leave it set to **None**.</span></span> 
    
20. <span data-ttu-id="15edf-190">完成后，单击“**新增**”。</span><span class="sxs-lookup"><span data-stu-id="15edf-190">When you are finished, click on **Add New**.</span></span>
    
21. <span data-ttu-id="15edf-191">导航到 Cisco 统一厘米管理-\>呼叫路由-\>路由/智能寻线-\>路由模式。</span><span class="sxs-lookup"><span data-stu-id="15edf-191">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Route/Hunt-\>Route pattern.</span></span>
    
22. <span data-ttu-id="15edf-p111">在“路由模式配置”屏幕中，如下所示输入模式定义参数。向下滚动至“被叫方转换”部分并按图中所示设置掩码，然后在完成时单击“**新增**”。</span><span class="sxs-lookup"><span data-stu-id="15edf-p111">In the Route Pattern Configuration screen, enter the Pattern definition parameters shown below. Scroll down to the Called Party Transformations section and set the mask as shown, and then click on **Add New** when finished.</span></span>
    
    |<span data-ttu-id="15edf-194">**参数**</span><span class="sxs-lookup"><span data-stu-id="15edf-194">**Parameter**</span></span>|<span data-ttu-id="15edf-195">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="15edf-195">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="15edf-196">路由模式</span><span class="sxs-lookup"><span data-stu-id="15edf-196">Route Pattern</span></span>  <br/> |<span data-ttu-id="15edf-197">7779999</span><span class="sxs-lookup"><span data-stu-id="15edf-197">7779999</span></span>  <br/> |
    |<span data-ttu-id="15edf-198">路由分区</span><span class="sxs-lookup"><span data-stu-id="15edf-198">Route Partition</span></span>  <br/> |<span data-ttu-id="15edf-199">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="15edf-199">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="15edf-200">说明</span><span class="sxs-lookup"><span data-stu-id="15edf-200">Description</span></span>  <br/> |<span data-ttu-id="15edf-201">SfBVideoInterop 的分区</span><span class="sxs-lookup"><span data-stu-id="15edf-201">Partition for SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="15edf-202">网关/路由列表</span><span class="sxs-lookup"><span data-stu-id="15edf-202">Gateway/Route List</span></span>  <br/> |<span data-ttu-id="15edf-203">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="15edf-203">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="15edf-204">被叫方转换掩码</span><span class="sxs-lookup"><span data-stu-id="15edf-204">Called Party Transform Mask</span></span>  <br/> |<span data-ttu-id="15edf-205">+14257779999</span><span class="sxs-lookup"><span data-stu-id="15edf-205">+14257779999</span></span>  <br/> |
   
23. <span data-ttu-id="15edf-206">导航到 Cisco 统一厘米管理-\>呼叫路由-\>SIP 路由模式。</span><span class="sxs-lookup"><span data-stu-id="15edf-206">Navigate to Cisco Unified CM Administration-\>Call Routing-\>SIP Route Pattern.</span></span>
    
24. <span data-ttu-id="15edf-207">在“SIP 路由模式配置”屏幕中，如图所示设置“模式定义”选项，然后单击“**新增**”。</span><span class="sxs-lookup"><span data-stu-id="15edf-207">In the SIP Route Pattern Configuration screen, set the Pattern Definition options as shown, and click on **Add New**.</span></span>
    
    |<span data-ttu-id="15edf-208">**参数**</span><span class="sxs-lookup"><span data-stu-id="15edf-208">**Parameter**</span></span>|<span data-ttu-id="15edf-209">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="15edf-209">**Recommended setting**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="15edf-210">模式使用</span><span class="sxs-lookup"><span data-stu-id="15edf-210">Pattern Usage</span></span> <br/> |<span data-ttu-id="15edf-211">域路由</span><span class="sxs-lookup"><span data-stu-id="15edf-211">Domain Routing</span></span>  <br/> |
    |<span data-ttu-id="15edf-212">IPv4 模式</span><span class="sxs-lookup"><span data-stu-id="15edf-212">IPv4 Pattern</span></span>  <br/> |<span data-ttu-id="15edf-213">contoso.com（ 使用 IPv6 时则留空）</span><span class="sxs-lookup"><span data-stu-id="15edf-213">contoso.com (leave blank if using IPv6)</span></span>  <br/> |
    |<span data-ttu-id="15edf-214">IPv6 模式</span><span class="sxs-lookup"><span data-stu-id="15edf-214">IPv6 Pattern</span></span>  <br/> |<span data-ttu-id="15edf-215">contoso.com（ 使用 IPv4 时则留空）</span><span class="sxs-lookup"><span data-stu-id="15edf-215">contoso.com (leave blank if using IPv4)</span></span>  <br/> |
    |<span data-ttu-id="15edf-216">说明</span><span class="sxs-lookup"><span data-stu-id="15edf-216">Description</span></span>  <br/> |<span data-ttu-id="15edf-217">到 mediarv 的 SIP 路由模式</span><span class="sxs-lookup"><span data-stu-id="15edf-217">SIPRoute Pattern to mediarv</span></span>  <br/> |
    |<span data-ttu-id="15edf-218">路由分区</span><span class="sxs-lookup"><span data-stu-id="15edf-218">Route Partition</span></span>  <br/> |<span data-ttu-id="15edf-219">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="15edf-219">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="15edf-220">SIP 中继/路由列表</span><span class="sxs-lookup"><span data-stu-id="15edf-220">SIP Trunk/Route List</span></span>  <br/> |<span data-ttu-id="15edf-221">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="15edf-221">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="15edf-222">“阻止模式”复选框</span><span class="sxs-lookup"><span data-stu-id="15edf-222">Block Pattern checkbox</span></span>  <br/> |<span data-ttu-id="15edf-223">保留未选中状态</span><span class="sxs-lookup"><span data-stu-id="15edf-223">leave unchecked</span></span>  <br/> |
   
25. <span data-ttu-id="15edf-224">如果您更改了音频或视频比特率的默认设置，您需要将其重设为默认设置。</span><span class="sxs-lookup"><span data-stu-id="15edf-224">If you have changed the audio or video bit rates from the default settings, you will need to return them to the defaults.</span></span> <span data-ttu-id="15edf-225">若要设置的音频/视频呼叫的比特率，导航到 Cisco 统一厘米管理-\>系统-\>地区信息-\>区域。</span><span class="sxs-lookup"><span data-stu-id="15edf-225">To set the bit rate for Audio/Video calls, navigate to Cisco Unified CM Administration-\>System-\>Region Information-\>Region.</span></span> <span data-ttu-id="15edf-226">默认设置如下所示（供参考）：</span><span class="sxs-lookup"><span data-stu-id="15edf-226">The defaults are shown below for reference:</span></span>
    
    |<span data-ttu-id="15edf-227">**参数**</span><span class="sxs-lookup"><span data-stu-id="15edf-227">**Parameter**</span></span>|<span data-ttu-id="15edf-228">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="15edf-228">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="15edf-229">区域</span><span class="sxs-lookup"><span data-stu-id="15edf-229">Region</span></span>  <br/> |<span data-ttu-id="15edf-230">默认值</span><span class="sxs-lookup"><span data-stu-id="15edf-230">Default</span></span>  <br/> |
    |<span data-ttu-id="15edf-231">音频编解码器首选项列表</span><span class="sxs-lookup"><span data-stu-id="15edf-231">Audio Codec Preference List</span></span>  <br/> |<span data-ttu-id="15edf-232">系统默认值</span><span class="sxs-lookup"><span data-stu-id="15edf-232">System Default</span></span>  <br/> |
    |<span data-ttu-id="15edf-233">最大音频比特率</span><span class="sxs-lookup"><span data-stu-id="15edf-233">Maximum Audio Bit Rate</span></span>  <br/> |<span data-ttu-id="15edf-234">64 kbps（G.722、G.711）</span><span class="sxs-lookup"><span data-stu-id="15edf-234">64 kbps (G.722, G.711)</span></span>  <br/> |
    |<span data-ttu-id="15edf-235">视频呼叫的最大会话比特率</span><span class="sxs-lookup"><span data-stu-id="15edf-235">Maximum Session Bit Rate for Video Calls</span></span>  <br/> |<span data-ttu-id="15edf-236">200000 kbps</span><span class="sxs-lookup"><span data-stu-id="15edf-236">200000 kbps</span></span>  <br/> |
    |<span data-ttu-id="15edf-237">最大会话比特率</span><span class="sxs-lookup"><span data-stu-id="15edf-237">Maximum Session Bit Rate</span></span>  <br/> |<span data-ttu-id="15edf-238">2000000000 kbps</span><span class="sxs-lookup"><span data-stu-id="15edf-238">2000000000 kbps</span></span>  <br/> |
   
<span data-ttu-id="15edf-239">此时，CUCM 视频网关被配置为与 VIS 进行协作。</span><span class="sxs-lookup"><span data-stu-id="15edf-239">At this point the CUCM video gateway is configured to work with the VIS.</span></span> <span data-ttu-id="15edf-240">必须在要集成的每个 VTC 上完成相应的配置。</span><span class="sxs-lookup"><span data-stu-id="15edf-240">Corresponding configuration will need to be done on each VTC you wish to integrate.</span></span>
> [!NOTE]
> <span data-ttu-id="15edf-241">若要提高恢复能力，您可能要配置此 CUCM 网关以与第二个视频互操作服务器或 VIS 池一起使用。</span><span class="sxs-lookup"><span data-stu-id="15edf-241">To improve resiliency, you may want to configure this CUCM gateway to work with a second Video Interop Server or VIS pool.</span></span> <span data-ttu-id="15edf-242">有关更多信息，请参阅[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)。</span><span class="sxs-lookup"><span data-stu-id="15edf-242">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="15edf-243">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15edf-243">See also</span></span>

[<span data-ttu-id="15edf-244">为业务服务器与 Skype 的互操作配置 VTC</span><span class="sxs-lookup"><span data-stu-id="15edf-244">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
