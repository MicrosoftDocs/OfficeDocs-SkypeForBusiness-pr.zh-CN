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
ms.openlocfilehash: 9d2466a314876a4ce576727c7673474003994365
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103058"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="4d794-103">适用于 Skype for Business Server 的基于视频的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="4d794-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="4d794-104">Skype for Business Server 2015 (基于视频的屏幕共享) VbSS) 现已可供下载[：Skype for Business Server 2015 累积更新 KB3061064。](https://www.microsoft.com/download/details.aspx?id=47690)</span><span class="sxs-lookup"><span data-stu-id="4d794-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span></span> <span data-ttu-id="4d794-105">VbSS 包含在 Skype for Business Server 2019 中。</span><span class="sxs-lookup"><span data-stu-id="4d794-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="4d794-106">基于视频的屏幕共享（即 VbSS）退出 Lync 屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="4d794-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="4d794-107">VbSS 与传统屏幕共享的区别与所使用的基础协议及其擅长内容有关。</span><span class="sxs-lookup"><span data-stu-id="4d794-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="4d794-108">屏幕共享使用远程桌面协议 (RDP) ，这非常能够创建数千个在用户计算机之间的一对一会话。</span><span class="sxs-lookup"><span data-stu-id="4d794-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="4d794-109">较新的技术 VbSS 将使用用户数据报协议 (UDP) 。</span><span class="sxs-lookup"><span data-stu-id="4d794-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="4d794-110">Skype for Business Server 希望改进人们一对一及其一对多的多方 (对话和) 体验。</span><span class="sxs-lookup"><span data-stu-id="4d794-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="4d794-111">VbSS 利用媒体平台 (它依赖于 UDP 作为基础协议) ，目的是改进视频开始时间、观看 (尤其是当你正在观看的内容快速移动) 时，以及整体可靠性。</span><span class="sxs-lookup"><span data-stu-id="4d794-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="4d794-112">改进屏幕共享的一部分是，在 VbSS 和 RDP 之间实现尽可能无缝的转换。</span><span class="sxs-lookup"><span data-stu-id="4d794-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="4d794-113">由于 VbSS 是 Skype for Business Server 的屏幕共享中使用的基础技术的更新，因此很难检测你正在利用的技术，除非你正在查看网络流量中的 SIP 详细信息，或者你正在共享快速移动或三维内容。</span><span class="sxs-lookup"><span data-stu-id="4d794-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="4d794-114">例如，如果工作区中有许多旧版客户端，RDP 仍将作为会议和对话的故障安全。</span><span class="sxs-lookup"><span data-stu-id="4d794-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="4d794-115">Skype for Business Server 使用内部逻辑决定在客户端连接 (VbSS 或传统屏幕) 应用哪一种方法。</span><span class="sxs-lookup"><span data-stu-id="4d794-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="4d794-116">RDP 可以且将替换为 VbSS（当情况需要它时）以便你的查看体验不会中断。</span><span class="sxs-lookup"><span data-stu-id="4d794-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="4d794-117">规划</span><span class="sxs-lookup"><span data-stu-id="4d794-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="4d794-118">VbSS 的优缺点</span><span class="sxs-lookup"><span data-stu-id="4d794-118">VbSS pros and cons</span></span>

<span data-ttu-id="4d794-119">切换到 VbSS 旨在进行三项关键改进：</span><span class="sxs-lookup"><span data-stu-id="4d794-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="4d794-120">使屏幕共享功能 (RDP 相比) 5% 的可靠性。</span><span class="sxs-lookup"><span data-stu-id="4d794-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="4d794-121">使会话设置和视频体验比仅 RDP 快一 (设置时间，每秒帧数提高 6：1) 。</span><span class="sxs-lookup"><span data-stu-id="4d794-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="4d794-122">在低带宽条件下，即使共享高运动内容（如 3D 图形）也比 RDP 更好。</span><span class="sxs-lookup"><span data-stu-id="4d794-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="4d794-123">请记住，这些数字依赖于网络的运行状况和正确性能调整，如果客户端位于移动设备上，则这些网络可能涉及您自己的外部网络。</span><span class="sxs-lookup"><span data-stu-id="4d794-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="4d794-124">还应注意，共享内容的一些保真度/清晰度已用于可靠性、速度和效率。</span><span class="sxs-lookup"><span data-stu-id="4d794-124">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency.</span></span> <span data-ttu-id="4d794-125">在大多数情况下，用户不会立即看到它。</span><span class="sxs-lookup"><span data-stu-id="4d794-125">In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="4d794-126">端口和协议</span><span class="sxs-lookup"><span data-stu-id="4d794-126">Ports and protocols</span></span>

<span data-ttu-id="4d794-127">**所需的服务器端口**</span><span class="sxs-lookup"><span data-stu-id="4d794-127">**Required server ports**</span></span>

|<span data-ttu-id="4d794-128">**服务器角色**</span><span class="sxs-lookup"><span data-stu-id="4d794-128">**Server role**</span></span>|<span data-ttu-id="4d794-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="4d794-129">**Service name**</span></span>|<span data-ttu-id="4d794-130">**端口或端口范围**</span><span class="sxs-lookup"><span data-stu-id="4d794-130">**Port or port range**</span></span>|<span data-ttu-id="4d794-131">**协议**</span><span class="sxs-lookup"><span data-stu-id="4d794-131">**Protocol**</span></span>|<span data-ttu-id="4d794-132">**备注**</span><span class="sxs-lookup"><span data-stu-id="4d794-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d794-133">前端服务器</span><span class="sxs-lookup"><span data-stu-id="4d794-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="4d794-134">Skype for Business Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="4d794-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="4d794-135">5065</span><span class="sxs-lookup"><span data-stu-id="4d794-135">5065</span></span>  <br/> |<span data-ttu-id="4d794-136">TCP</span><span class="sxs-lookup"><span data-stu-id="4d794-136">TCP</span></span>  <br/> |<span data-ttu-id="4d794-137">用于应用程序共享的传入 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="4d794-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="4d794-138">前端服务器</span><span class="sxs-lookup"><span data-stu-id="4d794-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="4d794-139">Skype for Business Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="4d794-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="4d794-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="4d794-140">49152-65535</span></span>  <br/> |<span data-ttu-id="4d794-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="4d794-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="4d794-142">用于应用程序共享的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="4d794-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="4d794-143">**所需的客户端端口**</span><span class="sxs-lookup"><span data-stu-id="4d794-143">**Required client ports**</span></span>

|<span data-ttu-id="4d794-144">**组件**</span><span class="sxs-lookup"><span data-stu-id="4d794-144">**Component**</span></span>|<span data-ttu-id="4d794-145">**端口范围**</span><span class="sxs-lookup"><span data-stu-id="4d794-145">**Port range**</span></span>|<span data-ttu-id="4d794-146">**协议**</span><span class="sxs-lookup"><span data-stu-id="4d794-146">**Protocol**</span></span>|<span data-ttu-id="4d794-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="4d794-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d794-148">客户端</span><span class="sxs-lookup"><span data-stu-id="4d794-148">Clients</span></span>  <br/> |<span data-ttu-id="4d794-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="4d794-149">1024-65535</span></span>  <br/> |<span data-ttu-id="4d794-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="4d794-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="4d794-151">应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="4d794-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="4d794-152">如果为以下媒体端口启用了 QoS，并且也启用了 VbSS，那么在包含桌面共享的会议期间，AS MCU 将使用屏幕共享流量下方以粗体显示的视频端口设置。</span><span class="sxs-lookup"><span data-stu-id="4d794-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4d794-153">这些设置是一个特例，必须在实现这两个功能时使用这些确切设置。</span><span class="sxs-lookup"><span data-stu-id="4d794-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="4d794-154">这将覆盖 [QoS 文档中建议的其他设置](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos)。</span><span class="sxs-lookup"><span data-stu-id="4d794-154">This overrides other recommended settings in the [documentation for QoS](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos).</span></span> <span data-ttu-id="4d794-155">对于应用程序共享，除了定义这些端口值ASMCUSVC.exe还需要在 QoS GPO 中指定端口。</span><span class="sxs-lookup"><span data-stu-id="4d794-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="4d794-156">**应用程序服务器 QoS/VbSS 所需设置**</span><span class="sxs-lookup"><span data-stu-id="4d794-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="4d794-157">**属性**</span><span class="sxs-lookup"><span data-stu-id="4d794-157">**Property**</span></span>|<span data-ttu-id="4d794-158">**端口值**</span><span class="sxs-lookup"><span data-stu-id="4d794-158">**Port value**</span></span>|<span data-ttu-id="4d794-159">**协议**</span><span class="sxs-lookup"><span data-stu-id="4d794-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d794-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="4d794-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="4d794-161">49152</span><span class="sxs-lookup"><span data-stu-id="4d794-161">49152</span></span>  <br/> |<span data-ttu-id="4d794-162">UDP</span><span class="sxs-lookup"><span data-stu-id="4d794-162">UDP</span></span>  <br/> |
|<span data-ttu-id="4d794-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="4d794-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="4d794-164">8348</span><span class="sxs-lookup"><span data-stu-id="4d794-164">8348</span></span>  <br/> |<span data-ttu-id="4d794-165">UDP</span><span class="sxs-lookup"><span data-stu-id="4d794-165">UDP</span></span>  <br/> |
|<span data-ttu-id="4d794-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="4d794-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="4d794-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="4d794-167">**57501**</span></span> <br/> |<span data-ttu-id="4d794-168">UDP</span><span class="sxs-lookup"><span data-stu-id="4d794-168">UDP</span></span>  <br/> |
|<span data-ttu-id="4d794-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="4d794-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="4d794-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="4d794-170">**8034**</span></span> <br/> |<span data-ttu-id="4d794-171">UDP</span><span class="sxs-lookup"><span data-stu-id="4d794-171">UDP</span></span>  <br/> |
|<span data-ttu-id="4d794-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="4d794-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="4d794-173">40803</span><span class="sxs-lookup"><span data-stu-id="4d794-173">40803</span></span>  <br/> |<span data-ttu-id="4d794-174">TCP</span><span class="sxs-lookup"><span data-stu-id="4d794-174">TCP</span></span>  <br/> |
|<span data-ttu-id="4d794-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="4d794-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="4d794-176">8348</span><span class="sxs-lookup"><span data-stu-id="4d794-176">8348</span></span>  <br/> |<span data-ttu-id="4d794-177">TCP</span><span class="sxs-lookup"><span data-stu-id="4d794-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="4d794-178">容量规划</span><span class="sxs-lookup"><span data-stu-id="4d794-178">Capacity planning</span></span>

<span data-ttu-id="4d794-179">运行 Skype for Business Server 2015 累积更新 2 (CU2) 或更高版本的每个前端服务器最多支持 375 个参与者使用 RDP (但每个会议仅支持 250 个参与者进行屏幕) 。</span><span class="sxs-lookup"><span data-stu-id="4d794-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="4d794-180">引入和使用 VbSS 时，此容量在 CU3 后不会更改。</span><span class="sxs-lookup"><span data-stu-id="4d794-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="4d794-181">也就是说，我们已在实验室中完成性能和压力测试，也应当根据你的部署环境考虑 (测量，当然) 。</span><span class="sxs-lookup"><span data-stu-id="4d794-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="4d794-182">假定：</span><span class="sxs-lookup"><span data-stu-id="4d794-182">Assuming:</span></span>
  
- <span data-ttu-id="4d794-183">在部署中使用 Skype for Business Server 2015 CU2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4d794-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="4d794-184">Skype for Business Server 环境中所有用户的屏幕分辨率都高于 1920x1080。</span><span class="sxs-lookup"><span data-stu-id="4d794-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="4d794-185">达到完整容量时 (如上所述，每个前端服务器总共有 375 个屏幕共享参与者，尽管每个会议) 只有 250 个，但前端服务器可能使用大约 1 GB 网卡的 89%。</span><span class="sxs-lookup"><span data-stu-id="4d794-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="4d794-186">这是因为 Skype for Business Server CU2 (RDP) 中的现有屏幕共享技术以演示者电脑的本机分辨率传输屏幕内容。</span><span class="sxs-lookup"><span data-stu-id="4d794-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="4d794-187">因此，在考虑更高的屏幕分辨率后，你可能已经遇到 Skype for Business Server 2015 CU2 的屏幕共享网络瓶颈。</span><span class="sxs-lookup"><span data-stu-id="4d794-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="4d794-188">若要缓解这种情况，以下一个或多个选项可能会有所帮助：</span><span class="sxs-lookup"><span data-stu-id="4d794-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="4d794-189">将前端服务器从 1 GB 网卡升级到 10 GB 以太网卡。</span><span class="sxs-lookup"><span data-stu-id="4d794-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="4d794-190">增加前端服务器的数量以对流量进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="4d794-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="4d794-191">限制用于 VbSS (RDP) 的最大带宽上限来限制用于 VbSS 和 RDP 的带宽比特率。</span><span class="sxs-lookup"><span data-stu-id="4d794-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="4d794-192">此表中的数字受各个网络和共享内容的影响。</span><span class="sxs-lookup"><span data-stu-id="4d794-192">The numbers in this table are influenced by individual networks and by the content being shared.</span></span> <span data-ttu-id="4d794-193">请进行测试，为网络建立基线。</span><span class="sxs-lookup"><span data-stu-id="4d794-193">Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="4d794-194">**1080p 内容**</span><span class="sxs-lookup"><span data-stu-id="4d794-194">**1080p Content**</span></span>|<span data-ttu-id="4d794-195">**RDP 平均值**</span><span class="sxs-lookup"><span data-stu-id="4d794-195">**RDP Average**</span></span>|<span data-ttu-id="4d794-196">**RDP 峰值**</span><span class="sxs-lookup"><span data-stu-id="4d794-196">**RDP Peak**</span></span>|<span data-ttu-id="4d794-197">**VbSS 平均值**</span><span class="sxs-lookup"><span data-stu-id="4d794-197">**VbSS Average**</span></span>|<span data-ttu-id="4d794-198">**VbSS 峰值**</span><span class="sxs-lookup"><span data-stu-id="4d794-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d794-199">PPT</span><span class="sxs-lookup"><span data-stu-id="4d794-199">PPT</span></span>  <br/> |<span data-ttu-id="4d794-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="4d794-200">200kbps</span></span>  <br/> |<span data-ttu-id="4d794-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-201">12mbps</span></span>  <br/> |<span data-ttu-id="4d794-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="4d794-202">100kbps</span></span>  <br/> |<span data-ttu-id="4d794-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="4d794-204">CAD</span><span class="sxs-lookup"><span data-stu-id="4d794-204">CAD</span></span>  <br/> |<span data-ttu-id="4d794-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-205">3mbps</span></span>  <br/> |<span data-ttu-id="4d794-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-206">7mbps</span></span>  <br/> |<span data-ttu-id="4d794-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-207">1mbps</span></span>  <br/> |<span data-ttu-id="4d794-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="4d794-209">视频</span><span class="sxs-lookup"><span data-stu-id="4d794-209">Video</span></span>  <br/> |<span data-ttu-id="4d794-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-210">5mbps</span></span>  <br/> |<span data-ttu-id="4d794-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-211">7mbps</span></span>  <br/> |<span data-ttu-id="4d794-212">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="4d794-213">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="4d794-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="4d794-214">媒体流量的网络带宽要求</span><span class="sxs-lookup"><span data-stu-id="4d794-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="4d794-215">VbSS 带宽为：</span><span class="sxs-lookup"><span data-stu-id="4d794-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="4d794-216">**视频编解码器**</span><span class="sxs-lookup"><span data-stu-id="4d794-216">**Video codec**</span></span>|<span data-ttu-id="4d794-217">**分辨率和纵横比**</span><span class="sxs-lookup"><span data-stu-id="4d794-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="4d794-218">**最大视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="4d794-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="4d794-219">**最小视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="4d794-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d794-220">H.264</span><span class="sxs-lookup"><span data-stu-id="4d794-220">H.264</span></span>  <br/> |<span data-ttu-id="4d794-221">1920x1080 (16：9) </span><span class="sxs-lookup"><span data-stu-id="4d794-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="4d794-222"> (纵横比取决于共享者监视器的分辨率，并且不会始终为 16：9) </span><span class="sxs-lookup"><span data-stu-id="4d794-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="4d794-223">4000</span><span class="sxs-lookup"><span data-stu-id="4d794-223">4000</span></span>  <br/> |<span data-ttu-id="4d794-224">1500</span><span class="sxs-lookup"><span data-stu-id="4d794-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="4d794-225">客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="4d794-225">Clients and servers support</span></span>

<span data-ttu-id="4d794-226">基于视频的屏幕共享需要 Skype for Business Server 2015 CU3 或更高版本，以及 Skype [for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) 和会议支持的移动客户端功能比较中列出的支持客户端 [的当前版本](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)。</span><span class="sxs-lookup"><span data-stu-id="4d794-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="4d794-227">在某些情况下，屏幕共享将转换为 RDP，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4d794-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="4d794-228">如果你的帐户托管在 ASMCU 不满足支持 VbSS 的最低内部版本的环境中。</span><span class="sxs-lookup"><span data-stu-id="4d794-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="4d794-229">如果使用早期版本的 Skype for Business 客户端的人员加入会话，例如使用低于 16.0.6330.1000、Skype for Business 会议室系统设备或 Skype for Business 移动应用的任何 Windows 客户端版本的任何人。</span><span class="sxs-lookup"><span data-stu-id="4d794-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="4d794-230">如果用户正在从 Skype for Business Web App 共享。</span><span class="sxs-lookup"><span data-stu-id="4d794-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="4d794-231">如果某人使用的是 Mac 版 Skype for Business，而不是在 2018 年 7 月或更高版本的 Skype for Business Online 或 Skype for Business Server 2015 上 (或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="4d794-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="4d794-232">如果有人启动任何计划/Windows 共享。</span><span class="sxs-lookup"><span data-stu-id="4d794-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="4d794-233">如果有人开始录制会话。</span><span class="sxs-lookup"><span data-stu-id="4d794-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="4d794-234">如果有人在会话期间调用远程屏幕控制。</span><span class="sxs-lookup"><span data-stu-id="4d794-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="4d794-235">参与者超过 250 人的会议 (目前不支持 VbSS) 。</span><span class="sxs-lookup"><span data-stu-id="4d794-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="4d794-236">请注意，会话转换到 RDP 后，将不会转换回 VbSS。</span><span class="sxs-lookup"><span data-stu-id="4d794-236">Be aware that once the session transitions to RDP it will not transition back to VbSS.</span></span> <span data-ttu-id="4d794-237">同样，从 VbSS 进行转换是无缝的，并且希望在大多数情况下都很难检测到。</span><span class="sxs-lookup"><span data-stu-id="4d794-237">Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4d794-238">不支持在 Skype for Business 屏幕共享中阻止或尝试阻止从 VbSS 转换到 RDP。</span><span class="sxs-lookup"><span data-stu-id="4d794-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="4d794-239">启用、禁用和配置 VbSS</span><span class="sxs-lookup"><span data-stu-id="4d794-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="4d794-240">最重要的是，安装 Skype for Business Server 2015 累积更新 3 (CU3) 或更高版本后，默认情况下所有用户都将启用一对一和多方 VbSS。</span><span class="sxs-lookup"><span data-stu-id="4d794-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="4d794-241">如果你没有理由不为所有用户启用此功能，这可能会导致你出现问题。</span><span class="sxs-lookup"><span data-stu-id="4d794-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="4d794-242">在这种情况下，可以使用以下步骤禁用用户， (启用用户步骤将) ：</span><span class="sxs-lookup"><span data-stu-id="4d794-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="4d794-243">如何禁止用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="4d794-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="4d794-244">可以通过在 Skype for Business 管理控制台 (中运行此 cmdlet，为不应使用 VbSS 的任何用户分配不允许 VbSS 的用户策略 (将 [PolicyName] 替换为你要为) 执行此操作的策略：</span><span class="sxs-lookup"><span data-stu-id="4d794-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="4d794-245">还可以更新全局会议策略，这将影响没有分配策略的所有用户：</span><span class="sxs-lookup"><span data-stu-id="4d794-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="4d794-246">有关此命令详细信息，请参阅 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4d794-246">For more information on this command, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="4d794-247">如果需要完全关闭 VbSS，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4d794-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="4d794-248">有关此命令详细信息，请参阅 [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4d794-248">For more information on this command, see [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4d794-249">在多方 Skype for Business 会议中，所有客户端终结点都将遵守会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="4d794-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="4d794-250">如何允许用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="4d794-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="4d794-251">可以通过在 Skype for Business 管理控制台 (中运行此 cmdlet，为需要使用 VbSS 的任何用户分配允许 VbSS 的特定用户策略 (将 [PolicyName] 替换为针对) 执行此操作的策略：</span><span class="sxs-lookup"><span data-stu-id="4d794-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="4d794-252">还可以更新全局会议策略，这将影响没有分配策略的所有用户：</span><span class="sxs-lookup"><span data-stu-id="4d794-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="4d794-253">有关此命令详细信息，请参阅 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4d794-253">For more information on this command, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="4d794-254">如果需要在关闭 VbSS (它默认打开，) 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4d794-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="4d794-255">有关此命令详细信息，请参阅 [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4d794-255">For more information on this command, see [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4d794-256">在多方 Skype for Business 会议中，所有客户端终结点都将遵守会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="4d794-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4d794-257">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d794-257">See also</span></span>

[<span data-ttu-id="4d794-258">Skype for Business Server 2015 累积更新 KB3061064</span><span class="sxs-lookup"><span data-stu-id="4d794-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/download/details.aspx?id=47690)
  
[<span data-ttu-id="4d794-259">Skype for Business Server 2015 (VBSS) 基于视频的屏幕共享功能</span><span class="sxs-lookup"><span data-stu-id="4d794-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/kb/3170163)