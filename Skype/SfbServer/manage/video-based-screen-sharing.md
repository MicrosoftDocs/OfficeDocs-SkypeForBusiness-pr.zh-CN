---
title: 适用于 Skype for Business Server 的基于视频的屏幕共享
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: '基于视频的屏幕共享和 VbSS (Skype for Business Server) '
ms.openlocfilehash: 6c24ad9e2f74495fc616a66472f338f1b0b281d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832762"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="8b988-103">适用于 Skype for Business Server 的基于视频的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="8b988-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="8b988-104">Skype for Business Server 2015 中基于视频的屏幕共享 (VbSS) 现已可供下载[：Skype for Business Server 2015 累积更新 KB3061064。](https://www.microsoft.com/download/details.aspx?id=47690)</span><span class="sxs-lookup"><span data-stu-id="8b988-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span></span> <span data-ttu-id="8b988-105">VbSS 包含在 Skype for Business Server 2019 中。</span><span class="sxs-lookup"><span data-stu-id="8b988-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="8b988-106">基于视频的屏幕共享（即 VbSS）退出 Lync 屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="8b988-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="8b988-107">VbSS 与传统屏幕共享的区别与使用的基础协议及其擅长内容有关。</span><span class="sxs-lookup"><span data-stu-id="8b988-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="8b988-108">屏幕共享使用远程桌面协议 (RDP) ，这非常能够创建用户计算机之间的数千个一对一会话。</span><span class="sxs-lookup"><span data-stu-id="8b988-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="8b988-109">较新的技术 VbSS 将使用 UDP (用户数据报) 。</span><span class="sxs-lookup"><span data-stu-id="8b988-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="8b988-110">Skype for Business Server 希望改进人员一对一及其一对多的多方 (对话和) 体验。</span><span class="sxs-lookup"><span data-stu-id="8b988-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="8b988-111">VbSS 利用媒体平台 (它依赖于 UDP 作为基础协议) ，目的是改善视频开始时间、观看 (（尤其是当你正在观看的内容快速移动) 时）以及整体的可靠性。</span><span class="sxs-lookup"><span data-stu-id="8b988-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="8b988-112">改进屏幕共享的一部分是，VbSS 和 RDP 之间的转换在出现时尽可能无缝。</span><span class="sxs-lookup"><span data-stu-id="8b988-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="8b988-113">由于 VbSS 是 Skype for Business Server 的屏幕共享中使用的基础技术的更新，因此，除非正在查看网络流量中的 SIP 详细信息，或者正在共享快速移动或三维内容，否则可能很难检测你正在利用的技术。</span><span class="sxs-lookup"><span data-stu-id="8b988-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="8b988-114">例如，如果工作区中有许多旧客户端，RDP 仍将作为会议和对话的故障保护提供。</span><span class="sxs-lookup"><span data-stu-id="8b988-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="8b988-115">Skype for Business Server 使用内部逻辑决定在客户端连接时 (VbSS 或传统屏幕) 应用哪一种方法。</span><span class="sxs-lookup"><span data-stu-id="8b988-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="8b988-116">当情况需要 VbSS 时，RDP 可以且将替换为 VbSS，以便你的查看体验不会中断。</span><span class="sxs-lookup"><span data-stu-id="8b988-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="8b988-117">规划</span><span class="sxs-lookup"><span data-stu-id="8b988-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="8b988-118">VbSS 的优缺点</span><span class="sxs-lookup"><span data-stu-id="8b988-118">VbSS pros and cons</span></span>

<span data-ttu-id="8b988-119">切换到 VbSS 旨在进行三个关键改进：</span><span class="sxs-lookup"><span data-stu-id="8b988-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="8b988-120">使屏幕共享 (比 RDP ) 高 5%。</span><span class="sxs-lookup"><span data-stu-id="8b988-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="8b988-121">与 RDP 相比，将会话设置和视频体验提高一半 (RDP 设置更快，每秒帧数提高 6：1) 。</span><span class="sxs-lookup"><span data-stu-id="8b988-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="8b988-122">在低带宽条件下，即使共享高运动内容（如 3D 图形）也比 RDP 更有效。</span><span class="sxs-lookup"><span data-stu-id="8b988-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="8b988-123">请记住，这些数字依赖于网络的运行状况和正确性能调整，如果客户端位于移动设备上，则它们可能涉及您自己的外部网络。</span><span class="sxs-lookup"><span data-stu-id="8b988-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="8b988-124">还应注意，共享内容的一些保真度/清晰度已用于可靠性、速度和效率。</span><span class="sxs-lookup"><span data-stu-id="8b988-124">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency.</span></span> <span data-ttu-id="8b988-125">在大多数情况下，用户不会立即看到此内容。</span><span class="sxs-lookup"><span data-stu-id="8b988-125">In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="8b988-126">端口和协议</span><span class="sxs-lookup"><span data-stu-id="8b988-126">Ports and protocols</span></span>

<span data-ttu-id="8b988-127">**所需的服务器端口**</span><span class="sxs-lookup"><span data-stu-id="8b988-127">**Required server ports**</span></span>

|<span data-ttu-id="8b988-128">**服务器角色**</span><span class="sxs-lookup"><span data-stu-id="8b988-128">**Server role**</span></span>|<span data-ttu-id="8b988-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="8b988-129">**Service name**</span></span>|<span data-ttu-id="8b988-130">**端口或端口范围**</span><span class="sxs-lookup"><span data-stu-id="8b988-130">**Port or port range**</span></span>|<span data-ttu-id="8b988-131">**协议**</span><span class="sxs-lookup"><span data-stu-id="8b988-131">**Protocol**</span></span>|<span data-ttu-id="8b988-132">**备注**</span><span class="sxs-lookup"><span data-stu-id="8b988-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b988-133">前端服务器</span><span class="sxs-lookup"><span data-stu-id="8b988-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="8b988-134">Skype for Business Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="8b988-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="8b988-135">5065</span><span class="sxs-lookup"><span data-stu-id="8b988-135">5065</span></span>  <br/> |<span data-ttu-id="8b988-136">TCP</span><span class="sxs-lookup"><span data-stu-id="8b988-136">TCP</span></span>  <br/> |<span data-ttu-id="8b988-137">用于应用程序共享的传入 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="8b988-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="8b988-138">前端服务器</span><span class="sxs-lookup"><span data-stu-id="8b988-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="8b988-139">Skype for Business Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="8b988-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="8b988-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="8b988-140">49152-65535</span></span>  <br/> |<span data-ttu-id="8b988-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8b988-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="8b988-142">用于应用程序共享的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="8b988-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="8b988-143">**必需的客户端端口**</span><span class="sxs-lookup"><span data-stu-id="8b988-143">**Required client ports**</span></span>

|<span data-ttu-id="8b988-144">**组件**</span><span class="sxs-lookup"><span data-stu-id="8b988-144">**Component**</span></span>|<span data-ttu-id="8b988-145">**端口范围**</span><span class="sxs-lookup"><span data-stu-id="8b988-145">**Port range**</span></span>|<span data-ttu-id="8b988-146">**协议**</span><span class="sxs-lookup"><span data-stu-id="8b988-146">**Protocol**</span></span>|<span data-ttu-id="8b988-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="8b988-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b988-148">客户端</span><span class="sxs-lookup"><span data-stu-id="8b988-148">Clients</span></span>  <br/> |<span data-ttu-id="8b988-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="8b988-149">1024-65535</span></span>  <br/> |<span data-ttu-id="8b988-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8b988-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="8b988-151">应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="8b988-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="8b988-152">如果为以下媒体端口启用了 QoS，并且还启用了 VbSS，在包括桌面共享的会议期间，AS MCU 将使用下面粗体显示的视频端口设置用于屏幕共享流量。</span><span class="sxs-lookup"><span data-stu-id="8b988-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8b988-153">这些设置是一个特例，并且必须在实现这两个功能时使用这些确切设置。</span><span class="sxs-lookup"><span data-stu-id="8b988-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="8b988-154">这将覆盖 [QoS 文档中建议的其他设置](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8b988-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="8b988-155">对于应用程序共享，除了定义这些端口值ASMCUSVC.exe还需要在 QoS GPO 中指定端口值。</span><span class="sxs-lookup"><span data-stu-id="8b988-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="8b988-156">**应用程序服务器 QoS/VbSS 所需设置**</span><span class="sxs-lookup"><span data-stu-id="8b988-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="8b988-157">**属性**</span><span class="sxs-lookup"><span data-stu-id="8b988-157">**Property**</span></span>|<span data-ttu-id="8b988-158">**端口值**</span><span class="sxs-lookup"><span data-stu-id="8b988-158">**Port value**</span></span>|<span data-ttu-id="8b988-159">**协议**</span><span class="sxs-lookup"><span data-stu-id="8b988-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b988-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="8b988-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="8b988-161">49152</span><span class="sxs-lookup"><span data-stu-id="8b988-161">49152</span></span>  <br/> |<span data-ttu-id="8b988-162">UDP</span><span class="sxs-lookup"><span data-stu-id="8b988-162">UDP</span></span>  <br/> |
|<span data-ttu-id="8b988-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="8b988-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="8b988-164">8348</span><span class="sxs-lookup"><span data-stu-id="8b988-164">8348</span></span>  <br/> |<span data-ttu-id="8b988-165">UDP</span><span class="sxs-lookup"><span data-stu-id="8b988-165">UDP</span></span>  <br/> |
|<span data-ttu-id="8b988-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="8b988-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="8b988-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="8b988-167">**57501**</span></span> <br/> |<span data-ttu-id="8b988-168">UDP</span><span class="sxs-lookup"><span data-stu-id="8b988-168">UDP</span></span>  <br/> |
|<span data-ttu-id="8b988-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="8b988-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="8b988-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="8b988-170">**8034**</span></span> <br/> |<span data-ttu-id="8b988-171">UDP</span><span class="sxs-lookup"><span data-stu-id="8b988-171">UDP</span></span>  <br/> |
|<span data-ttu-id="8b988-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="8b988-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="8b988-173">40803</span><span class="sxs-lookup"><span data-stu-id="8b988-173">40803</span></span>  <br/> |<span data-ttu-id="8b988-174">TCP</span><span class="sxs-lookup"><span data-stu-id="8b988-174">TCP</span></span>  <br/> |
|<span data-ttu-id="8b988-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="8b988-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="8b988-176">8348</span><span class="sxs-lookup"><span data-stu-id="8b988-176">8348</span></span>  <br/> |<span data-ttu-id="8b988-177">TCP</span><span class="sxs-lookup"><span data-stu-id="8b988-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="8b988-178">容量规划</span><span class="sxs-lookup"><span data-stu-id="8b988-178">Capacity planning</span></span>

<span data-ttu-id="8b988-179">运行 Skype for Business Server 2015 累积更新 2 (CU2) 或更高版本的每个前端服务器最多支持 375 个参与者使用 RDP (进行屏幕共享，但每个会议仅支持 250) 。</span><span class="sxs-lookup"><span data-stu-id="8b988-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="8b988-180">引入和使用 VbSS 时，此容量在 CU3 之后不会更改。</span><span class="sxs-lookup"><span data-stu-id="8b988-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="8b988-181">也就是说，我们已在实验室中完成了性能和压力测试，还应当根据使用情况考虑以下有关您自己的部署 (测量，当然，) 。</span><span class="sxs-lookup"><span data-stu-id="8b988-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="8b988-182">假定：</span><span class="sxs-lookup"><span data-stu-id="8b988-182">Assuming:</span></span>
  
- <span data-ttu-id="8b988-183">你正在部署中使用 Skype for Business Server 2015 CU2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8b988-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="8b988-184">Skype for Business Server 环境中所有用户的屏幕分辨率都高于 1920x1080。</span><span class="sxs-lookup"><span data-stu-id="8b988-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="8b988-185">达到完整容量 (如上所述，每个前端服务器总共有 375 个屏幕共享参与者，尽管每个会议) 只有 250 个，但前端服务器可能利用大约 1 GB 网卡的 89%。</span><span class="sxs-lookup"><span data-stu-id="8b988-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="8b988-186">这是因为 Skype for Business Server CU2 中的现有屏幕共享技术 (RDP) 以演示者电脑的本机分辨率传输屏幕内容。</span><span class="sxs-lookup"><span data-stu-id="8b988-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="8b988-187">因此，在考虑更高的屏幕分辨率后，你可能已经遇到使用 Skype for Business Server 2015 CU2 进行屏幕共享的网络瓶颈。</span><span class="sxs-lookup"><span data-stu-id="8b988-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="8b988-188">若要缓解这种情况，以下一个或多个选项可能会有所帮助：</span><span class="sxs-lookup"><span data-stu-id="8b988-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="8b988-189">将前端服务器从 1 GB 网卡升级到 10 GB 以太网卡。</span><span class="sxs-lookup"><span data-stu-id="8b988-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="8b988-190">增加前端服务器的数量以平衡流量负载。</span><span class="sxs-lookup"><span data-stu-id="8b988-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="8b988-191">限制用于 VbSS (VbSS) RDP 的带宽比特率，方法为任一通道使用的最大带宽设置上限。</span><span class="sxs-lookup"><span data-stu-id="8b988-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="8b988-192">此表中的数字受各个网络和共享内容的影响。</span><span class="sxs-lookup"><span data-stu-id="8b988-192">The numbers in this table are influenced by individual networks and by the content being shared.</span></span> <span data-ttu-id="8b988-193">请测试以建立网络或网络的基线。</span><span class="sxs-lookup"><span data-stu-id="8b988-193">Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="8b988-194">**1080p 内容**</span><span class="sxs-lookup"><span data-stu-id="8b988-194">**1080p Content**</span></span>|<span data-ttu-id="8b988-195">**RDP 平均值**</span><span class="sxs-lookup"><span data-stu-id="8b988-195">**RDP Average**</span></span>|<span data-ttu-id="8b988-196">**RDP 峰值**</span><span class="sxs-lookup"><span data-stu-id="8b988-196">**RDP Peak**</span></span>|<span data-ttu-id="8b988-197">**VbSS 平均值**</span><span class="sxs-lookup"><span data-stu-id="8b988-197">**VbSS Average**</span></span>|<span data-ttu-id="8b988-198">**VbSS 峰值**</span><span class="sxs-lookup"><span data-stu-id="8b988-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b988-199">PPT</span><span class="sxs-lookup"><span data-stu-id="8b988-199">PPT</span></span>  <br/> |<span data-ttu-id="8b988-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="8b988-200">200kbps</span></span>  <br/> |<span data-ttu-id="8b988-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-201">12mbps</span></span>  <br/> |<span data-ttu-id="8b988-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="8b988-202">100kbps</span></span>  <br/> |<span data-ttu-id="8b988-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="8b988-204">CAD</span><span class="sxs-lookup"><span data-stu-id="8b988-204">CAD</span></span>  <br/> |<span data-ttu-id="8b988-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-205">3mbps</span></span>  <br/> |<span data-ttu-id="8b988-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-206">7mbps</span></span>  <br/> |<span data-ttu-id="8b988-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-207">1mbps</span></span>  <br/> |<span data-ttu-id="8b988-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="8b988-209">视频</span><span class="sxs-lookup"><span data-stu-id="8b988-209">Video</span></span>  <br/> |<span data-ttu-id="8b988-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-210">5mbps</span></span>  <br/> |<span data-ttu-id="8b988-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-211">7mbps</span></span>  <br/> |<span data-ttu-id="8b988-212">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="8b988-213">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="8b988-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="8b988-214">媒体流量的网络带宽要求</span><span class="sxs-lookup"><span data-stu-id="8b988-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="8b988-215">VbSS 带宽为：</span><span class="sxs-lookup"><span data-stu-id="8b988-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="8b988-216">**视频编解码器**</span><span class="sxs-lookup"><span data-stu-id="8b988-216">**Video codec**</span></span>|<span data-ttu-id="8b988-217">**分辨率和纵横比**</span><span class="sxs-lookup"><span data-stu-id="8b988-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="8b988-218">**最大视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="8b988-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="8b988-219">**最小视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="8b988-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b988-220">H.264</span><span class="sxs-lookup"><span data-stu-id="8b988-220">H.264</span></span>  <br/> |<span data-ttu-id="8b988-221">1920x1080 (16：9) </span><span class="sxs-lookup"><span data-stu-id="8b988-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="8b988-222"> (纵横比取决于共享者监视器的分辨率，并且不会始终为 16：9) </span><span class="sxs-lookup"><span data-stu-id="8b988-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="8b988-223">4000</span><span class="sxs-lookup"><span data-stu-id="8b988-223">4000</span></span>  <br/> |<span data-ttu-id="8b988-224">1500</span><span class="sxs-lookup"><span data-stu-id="8b988-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="8b988-225">客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="8b988-225">Clients and servers support</span></span>

<span data-ttu-id="8b988-226">基于视频的屏幕共享需要 Skype for Business Server 2015 CU3 或更高版本，以及 Skype [for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) 和会议支持的移动客户端功能比较中列出的支持客户端 [的当前版本](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)。</span><span class="sxs-lookup"><span data-stu-id="8b988-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="8b988-227">在某些情况下，屏幕共享将转换为 RDP，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b988-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="8b988-228">如果你的帐户托管在 ASMCU 不满足支持 VbSS 的最低内部版本的环境中。</span><span class="sxs-lookup"><span data-stu-id="8b988-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="8b988-229">如果使用较旧版本的 Skype for Business 客户端的人员加入会话，例如，使用低于 16.0.6330.1000、Skype for Business 会议室系统设备或 Skype for Business 移动应用的任何 Windows 客户端版本的任何人。</span><span class="sxs-lookup"><span data-stu-id="8b988-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="8b988-230">如果用户正在从 Skype for Business Web App 共享。</span><span class="sxs-lookup"><span data-stu-id="8b988-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="8b988-231">如果有人在 Mac 上使用 Skype for Business，而不是在 2018 年 7 月或更高版本的 Skype for Business Online 或 Skype for Business Server 2015 上 (累积更新) 。</span><span class="sxs-lookup"><span data-stu-id="8b988-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="8b988-232">如果有人启动任何计划/Windows 共享。</span><span class="sxs-lookup"><span data-stu-id="8b988-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="8b988-233">如果有人开始录制会话。</span><span class="sxs-lookup"><span data-stu-id="8b988-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="8b988-234">如果有人在会话期间调用远程屏幕控制。</span><span class="sxs-lookup"><span data-stu-id="8b988-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="8b988-235">与会者超过 250 人的会议 (目前不支持 VbSS) 。</span><span class="sxs-lookup"><span data-stu-id="8b988-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="8b988-236">请注意，会话转换到 RDP 后，将不会转换回 VbSS。</span><span class="sxs-lookup"><span data-stu-id="8b988-236">Be aware that once the session transitions to RDP it will not transition back to VbSS.</span></span> <span data-ttu-id="8b988-237">同样，从 VbSS 的转换是无缝的，并且希望在大多数情况下都很难检测。</span><span class="sxs-lookup"><span data-stu-id="8b988-237">Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8b988-238">不支持阻止或尝试阻止从 VbSS 转换为 Skype for Business 屏幕共享中的 RDP。</span><span class="sxs-lookup"><span data-stu-id="8b988-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="8b988-239">启用、禁用和配置 VbSS</span><span class="sxs-lookup"><span data-stu-id="8b988-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="8b988-240">最重要的是，安装 Skype for Business Server 2015 累积更新 3 (CU3) 或更高版本后，默认情况下，所有用户都将启用一对一和多方 VbSS。</span><span class="sxs-lookup"><span data-stu-id="8b988-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="8b988-241">如果你没有理由不为所有用户启用此功能，这可能有问题。</span><span class="sxs-lookup"><span data-stu-id="8b988-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="8b988-242">在这种情况下，可以使用以下步骤禁用用户， (启用用户步骤将) ：</span><span class="sxs-lookup"><span data-stu-id="8b988-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="8b988-243">如何禁止用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="8b988-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="8b988-244">可以通过在 Skype for Business 管理控制台中运行此 cmdlet 来将不允许 VbSS 的用户策略分配给不应使用 VbSS 的任何用户 (将 [PolicyName] 替换为你要为) 执行此操作的策略：</span><span class="sxs-lookup"><span data-stu-id="8b988-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="8b988-245">还可以更新全局会议策略，这将影响没有分配策略的所有用户：</span><span class="sxs-lookup"><span data-stu-id="8b988-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="8b988-246">有关此命令的信息，请参阅 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8b988-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="8b988-247">如果需要完全关闭 VbSS，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8b988-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="8b988-248">有关此命令详细信息，请参阅[Set-CsMediaConfiguration。](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8b988-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="8b988-249">在多方 Skype for Business 会议中，所有客户端终结点都将遵守会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="8b988-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="8b988-250">如何允许用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="8b988-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="8b988-251">可以通过在 Skype for Business 管理控制台 (中运行此 cmdlet，将 [PolicyName] 替换为你要为) 执行此操作的策略，将允许 VbSS 分配给任何需要使用 VbSS 的用户：</span><span class="sxs-lookup"><span data-stu-id="8b988-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="8b988-252">还可以更新全局会议策略，这将影响没有分配策略的所有用户：</span><span class="sxs-lookup"><span data-stu-id="8b988-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="8b988-253">有关此命令的信息，请参阅 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8b988-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="8b988-254">如果需要在关闭 VbSS 后将其关闭 (它默认) ，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8b988-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="8b988-255">有关此命令详细信息，请参阅[Set-CsMediaConfiguration。](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8b988-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="8b988-256">在多方 Skype for Business 会议中，所有客户端终结点都将遵守会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="8b988-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8b988-257">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b988-257">See also</span></span>

[<span data-ttu-id="8b988-258">Skype for Business Server 2015 累积更新 KB3061064</span><span class="sxs-lookup"><span data-stu-id="8b988-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/download/details.aspx?id=47690)
  
[<span data-ttu-id="8b988-259">Skype for Business Server 2015 (VBSS) 基于视频的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="8b988-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/kb/3170163)
