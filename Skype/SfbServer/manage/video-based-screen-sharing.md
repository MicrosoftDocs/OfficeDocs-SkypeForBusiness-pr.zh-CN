---
title: 适用于 Skype for Business Server 的基于视频的屏幕共享
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype 的基于视频的屏幕共享 (VbSS) 的业务服务器规划和配置信息
ms.openlocfilehash: d899e07fc478e33c4480cd235b3eb0cafd95ecba
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878912"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="dc4a7-103">适用于 Skype for Business Server 的基于视频的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="dc4a7-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="dc4a7-104">基于视频的屏幕中的业务服务器 2015 Skype 中共享 (VbSS) 现可供下载：[业务服务器 2015年累积更新 KB3061064 的 Skype](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690).</span></span> <span data-ttu-id="dc4a7-105">附带的业务服务器 2019 Skype VbSS。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="dc4a7-106">基于视频的屏幕共享，或者 VbSS，变得从 Lync 注销屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="dc4a7-107">VbSS 与传统屏幕共享之间的区别与所用的基础协议及其所擅长的技能有关。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="dc4a7-108">屏幕共享使用远程桌面协议 (RDP)，该协议擅长在各用户计算机之间创建数千个一对一会话。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="dc4a7-109">较新的技术 VbSS 将使用用户数据报协议 (UDP)。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="dc4a7-110">Skype 业务服务器想要提高人的 1-为-1，以及其 1 对多 （多方） 对话和会议体验。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="dc4a7-111">VbSS 使用媒体平台（该平台将 UDP 作为基础协议），旨在改进视频的开始时间、你所观看内容的观看质量（尤其是当你所观看的内容正在快速移动时）以及整体可靠性。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="dc4a7-112">改进屏幕共享的部分目的在于尽可能无缝地在 VbSS 与 RDP 之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="dc4a7-113">由于 VbSS 是屏幕共享 Skype 业务服务器中使用的基础技术的更新，因此它可能很难检测您在利用除非正在看 SIP 详细信息中的网络流量，或您正在共享的技术内容fast 移动或三维。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="dc4a7-114">如果，例如，工作场所中有大量的旧客户端，RDP 将仍可作为安全模式向您的会议和对话。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="dc4a7-115">Skype 业务服务器使用内部逻辑决定哪些 （VbSS 或传统的屏幕共享） 客户端连接时要应用的两种方法。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="dc4a7-116">RDP 在必要时可以并且会替换为 VbSS，确保你的观看体验不会被中断。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="dc4a7-117">规划</span><span class="sxs-lookup"><span data-stu-id="dc4a7-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="dc4a7-118">VbSS 的利与弊</span><span class="sxs-lookup"><span data-stu-id="dc4a7-118">VbSS pros and cons</span></span>

<span data-ttu-id="dc4a7-119">切换到 VbSS 旨在做出三项关键改进：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="dc4a7-120">与单独的 RDP 相比，提高屏幕共享的可靠性（高达 5%）。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="dc4a7-121">与单独的 RDP 相比，使会话设置和视频体验更快（设置时间减半，每秒帧数提高为 6:1）。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="dc4a7-122">在低带宽情况下优于 RDP，即使在共享高运动内容（如三维图形）时也是如此。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="dc4a7-123">请记住，这些数字依赖于你网络的运行状况和适当性能调整，并且可能涉及你自身外部的网络（如果你的客户端位于移动设备上）。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="dc4a7-p105">你还应注意，我们牺牲了共享内容的部分保真度/脆度来确保可靠性、速度和效率。在大多数情况下，这对用户并不明显。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-p105">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency. In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="dc4a7-126">端口和协议</span><span class="sxs-lookup"><span data-stu-id="dc4a7-126">Ports and protocols</span></span>

<span data-ttu-id="dc4a7-127">**所需的服务器端口**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-127">**Required server ports**</span></span>

|<span data-ttu-id="dc4a7-128">**服务器角色**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-128">**Server role**</span></span>|<span data-ttu-id="dc4a7-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-129">**Service name**</span></span>|<span data-ttu-id="dc4a7-130">**端口或端口范围**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-130">**Port or port range**</span></span>|<span data-ttu-id="dc4a7-131">**协议**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-131">**Protocol**</span></span>|<span data-ttu-id="dc4a7-132">**备注**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc4a7-133">前端服务器</span><span class="sxs-lookup"><span data-stu-id="dc4a7-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="dc4a7-134">Skype 业务服务器应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="dc4a7-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="dc4a7-135">5065</span><span class="sxs-lookup"><span data-stu-id="dc4a7-135">5065</span></span>  <br/> |<span data-ttu-id="dc4a7-136">TCP</span><span class="sxs-lookup"><span data-stu-id="dc4a7-136">TCP</span></span>  <br/> |<span data-ttu-id="dc4a7-137">用于应用程序共享的传入 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="dc4a7-138">前端服务器</span><span class="sxs-lookup"><span data-stu-id="dc4a7-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="dc4a7-139">Skype 业务服务器应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="dc4a7-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="dc4a7-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="dc4a7-140">49152-65535</span></span>  <br/> |<span data-ttu-id="dc4a7-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="dc4a7-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="dc4a7-142">用于应用程序共享的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="dc4a7-143">**所需的客户端端口**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-143">**Required client ports**</span></span>

|<span data-ttu-id="dc4a7-144">**组件**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-144">**Component**</span></span>|<span data-ttu-id="dc4a7-145">**端口范围**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-145">**Port range**</span></span>|<span data-ttu-id="dc4a7-146">**协议**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-146">**Protocol**</span></span>|<span data-ttu-id="dc4a7-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc4a7-148">客户端</span><span class="sxs-lookup"><span data-stu-id="dc4a7-148">Clients</span></span>  <br/> |<span data-ttu-id="dc4a7-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="dc4a7-149">1024-65535</span></span>  <br/> |<span data-ttu-id="dc4a7-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="dc4a7-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="dc4a7-151">应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="dc4a7-152">如果以下的媒体端口已启用 QoS，还启用 VbSS 包括 AS MCU 将使用视频端口设置中所示的桌面共享会议期间加粗下面的屏幕共享流量。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dc4a7-153">这些设置是一个特例，并实现这些功能的时，必须使用这些准确的设置。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="dc4a7-154">这将覆盖[QoS 文档](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)中的其他建议的设置。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="dc4a7-155">应用程序共享您需要指定 ASMCUSVC.exe QoS GPO 除了定义这些端口值中。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="dc4a7-156">**应用程序服务器 QoS/VbSS 所需的设置**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="dc4a7-157">**属性**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-157">**Property**</span></span>|<span data-ttu-id="dc4a7-158">**端口值**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-158">**Port value**</span></span>|<span data-ttu-id="dc4a7-159">**协议**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dc4a7-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="dc4a7-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="dc4a7-161">49152</span><span class="sxs-lookup"><span data-stu-id="dc4a7-161">49152</span></span>  <br/> |<span data-ttu-id="dc4a7-162">UDP</span><span class="sxs-lookup"><span data-stu-id="dc4a7-162">UDP</span></span>  <br/> |
|<span data-ttu-id="dc4a7-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="dc4a7-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="dc4a7-164">8348</span><span class="sxs-lookup"><span data-stu-id="dc4a7-164">8348</span></span>  <br/> |<span data-ttu-id="dc4a7-165">UDP</span><span class="sxs-lookup"><span data-stu-id="dc4a7-165">UDP</span></span>  <br/> |
|<span data-ttu-id="dc4a7-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="dc4a7-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-167">**57501**</span></span> <br/> |<span data-ttu-id="dc4a7-168">UDP</span><span class="sxs-lookup"><span data-stu-id="dc4a7-168">UDP</span></span>  <br/> |
|<span data-ttu-id="dc4a7-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="dc4a7-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-170">**8034**</span></span> <br/> |<span data-ttu-id="dc4a7-171">UDP</span><span class="sxs-lookup"><span data-stu-id="dc4a7-171">UDP</span></span>  <br/> |
|<span data-ttu-id="dc4a7-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="dc4a7-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="dc4a7-173">40803</span><span class="sxs-lookup"><span data-stu-id="dc4a7-173">40803</span></span>  <br/> |<span data-ttu-id="dc4a7-174">UDP</span><span class="sxs-lookup"><span data-stu-id="dc4a7-174">UDP</span></span>  <br/> |
|<span data-ttu-id="dc4a7-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="dc4a7-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="dc4a7-176">8348</span><span class="sxs-lookup"><span data-stu-id="dc4a7-176">8348</span></span>  <br/> |<span data-ttu-id="dc4a7-177">UDP</span><span class="sxs-lookup"><span data-stu-id="dc4a7-177">UDP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="dc4a7-178">容量规划</span><span class="sxs-lookup"><span data-stu-id="dc4a7-178">Capacity planning</span></span>

<span data-ttu-id="dc4a7-179">每个前端服务器运行 Skype 业务服务器 2015年累积更新 2 (CU2) 或更高版本支持的屏幕共享使用 RDP (每个会议的虽然只 250) 达 375 参与者。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="dc4a7-180">引入并使用 VbSS 时，此容量在 CU3 后不会更改。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="dc4a7-181">也就是说，我们已在实验室中完成性能和压力测试，并且就你自己的部署还应考虑以下度量（当然具体要取决于使用情况）。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="dc4a7-182">假设：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-182">Assuming:</span></span>
  
- <span data-ttu-id="dc4a7-183">您正在使用 Skype 业务 Server 2015 CU2 或更高版本中您的部署。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="dc4a7-184">在您 Skype 业务服务器环境中的所有用户都具有高于 1920 x 1080 的屏幕分辨率。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="dc4a7-185">全容量 （即如上所述，每个前端服务器的 375 屏幕共享参与者在每个会议的总，但仅 250），您前端服务器可能正在使用 ~ 89%1 千兆位网卡。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="dc4a7-186">这是因为现有屏幕共享业务服务器 CU2 (RDP) 的技术 Skype 中的传输屏幕上内容的演示者的 PC 本机的分辨率。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="dc4a7-187">因此使用较高的屏幕分辨率分解，您可能已遇到屏幕与 Skype 的业务 Server 2015 CU2 共享的网络瓶颈。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="dc4a7-188">要缓解此问题，以下一个或多个选项可能有用：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="dc4a7-189">从 1 千兆位网卡的您前端服务器升级到 10 的千兆以太网卡片。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="dc4a7-190">增加到负载平衡流量的前端服务器数量。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="dc4a7-191">通过对任意通道所用的最大带宽设定限制来限制用于 VbSS 和 RDP 的带宽（比特率）。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="dc4a7-p109">此表中的数字受个别网络和所共享内容的影响。请通过测试建立一个或多个网络的基准。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-p109">The numbers in this table are influenced by individual networks and by the content being shared. Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="dc4a7-194">\*\*1080p 内容 \*\*</span><span class="sxs-lookup"><span data-stu-id="dc4a7-194">**1080p Content**</span></span>|<span data-ttu-id="dc4a7-195">**RDP 平均值**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-195">**RDP Average**</span></span>|<span data-ttu-id="dc4a7-196">**RDP 峰值**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-196">**RDP Peak**</span></span>|<span data-ttu-id="dc4a7-197">**VbSS 平均值**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-197">**VbSS Average**</span></span>|<span data-ttu-id="dc4a7-198">**VbSS 峰值**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc4a7-199">PPT</span><span class="sxs-lookup"><span data-stu-id="dc4a7-199">PPT</span></span>  <br/> |<span data-ttu-id="dc4a7-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-200">200kbps</span></span>  <br/> |<span data-ttu-id="dc4a7-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-201">12mbps</span></span>  <br/> |<span data-ttu-id="dc4a7-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-202">100kbps</span></span>  <br/> |<span data-ttu-id="dc4a7-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="dc4a7-204">CAD</span><span class="sxs-lookup"><span data-stu-id="dc4a7-204">CAD</span></span>  <br/> |<span data-ttu-id="dc4a7-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-205">3mbps</span></span>  <br/> |<span data-ttu-id="dc4a7-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-206">7mbps</span></span>  <br/> |<span data-ttu-id="dc4a7-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-207">1mbps</span></span>  <br/> |<span data-ttu-id="dc4a7-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="dc4a7-209">视频</span><span class="sxs-lookup"><span data-stu-id="dc4a7-209">Video</span></span>  <br/> |<span data-ttu-id="dc4a7-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-210">5mbps</span></span>  <br/> |<span data-ttu-id="dc4a7-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-211">7mbps</span></span>  <br/> |<span data-ttu-id="dc4a7-212">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="dc4a7-213">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="dc4a7-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="dc4a7-214">媒体流量的网络带宽要求</span><span class="sxs-lookup"><span data-stu-id="dc4a7-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="dc4a7-215">VbSS 带宽为：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="dc4a7-216">**视频编解码器**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-216">**Video codec**</span></span>|<span data-ttu-id="dc4a7-217">**分辨率和纵横比**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="dc4a7-218">**最大视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="dc4a7-219">**最小视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="dc4a7-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc4a7-220">H.264</span><span class="sxs-lookup"><span data-stu-id="dc4a7-220">H.264</span></span>  <br/> |<span data-ttu-id="dc4a7-221">1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="dc4a7-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="dc4a7-222">（纵横比取决于共享者的显示器分辨率，并且不会始终为 16:9）</span><span class="sxs-lookup"><span data-stu-id="dc4a7-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="dc4a7-223">4000</span><span class="sxs-lookup"><span data-stu-id="dc4a7-223">4000</span></span>  <br/> |<span data-ttu-id="dc4a7-224">1500</span><span class="sxs-lookup"><span data-stu-id="dc4a7-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="dc4a7-225">客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="dc4a7-225">Clients and servers support</span></span>

<span data-ttu-id="dc4a7-226">基于视频的屏幕共享要求 Skype 的业务服务器 2015 CU3 或更高版本，以及支持客户端[的 Skype for Business 的移动客户端功能比较](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)和[会议支持](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)中列出的当前版本。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="dc4a7-227">有其中屏幕共享将转换到 RDP，类似这样的情况下：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="dc4a7-228">如果你的帐户托管在 ASMCU 不满足支持 VbSS 的最低内部版本的环境中。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="dc4a7-229">如果 for Business 客户端使用的 Skype 较早版本的任何人加入会话，例如任何人都使用低于 16.0.6330.1000，对于业务会议室系统设备，Skype 或业务移动应用程序的 Skype 任何 Windows 客户端版本。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="dc4a7-230">如果用户正在共享 Skype 的企业 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="dc4a7-231">如果有人在 Mac 上的业务用 Skype 并不驻留在上业务 online Skype 或业务服务器 2015年的 Skype 年 7 月，2018 累积更新 （或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="dc4a7-232">如果某人开始任何程序/Windows 共享。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="dc4a7-233">如果某人开始录制会话。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="dc4a7-234">如果某人在会话期间调用远程屏幕控制。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="dc4a7-235">包含 250 个以上的参与者的会议（当前不支持 VbSS）。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="dc4a7-p110">请注意，会话切换到 RDP 后，将不会切换回 VbSS。另外，从 VbSS 进行切换应为无缝操作，并且希望在大多数情况下不容易被检测到。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-p110">Be aware that once the session transitions to RDP it will not transition back to VbSS. Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dc4a7-238">它具有不受支持到块中，或尝试阻止，请从转换 VbSS 到中 Skype RDP 业务屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="dc4a7-239">启用、禁用和配置 VbSS</span><span class="sxs-lookup"><span data-stu-id="dc4a7-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="dc4a7-240">很好的做法是，您已安装 Skype 业务服务器 2015年累积更新 3 (CU3) 或更高版本，您的所有用户将为都启用 1-1 和多方 VbSS 默认情况下之后。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="dc4a7-241">如果你有理由不为所有用户启用此功能，这对你来说可能有问题。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="dc4a7-242">在这种情况下，你可以使用这些步骤禁用用户（然后执行启用用户步骤）：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="dc4a7-243">如何禁止用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="dc4a7-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="dc4a7-244">您可以分配给不应通过为业务管理控制台 （替换 [PolicyName] 与您正在执行此操作的策略） Skype 中运行此 cmdlet 使用 VbSS 任何用户不允许 VbSS 的用户策略：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="dc4a7-245">你还可以更新全局会议策略，这会影响所有未分配策略的用户：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="dc4a7-246">此命令的详细信息，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="dc4a7-247">如果需要完全关闭 VbSS，你可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="dc4a7-248">此命令的详细信息，请参阅[设置 CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="dc4a7-249">在业务会议多方 Skype，所有客户端终结点将尊重会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="dc4a7-250">如何允许用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="dc4a7-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="dc4a7-251">您可以分配给需要通过业务管理控制台 （替换 [PolicyName] 与您正在执行此操作的策略） 的 Skype 中运行此 cmdlet 使用 VbSS 任何用户允许 VbSS 的特定用户策略：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="dc4a7-252">你还可以更新全局会议策略，这会影响所有未分配策略的用户：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="dc4a7-253">此命令的详细信息，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="dc4a7-254">如果需要在关闭 VbSS 后将其重新打开（默认情况下处于打开状态），你可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dc4a7-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="dc4a7-255">此命令的详细信息，请参阅[设置 CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="dc4a7-256">在业务会议多方 Skype，所有客户端终结点将尊重会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="dc4a7-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dc4a7-257">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc4a7-257">See also</span></span>

[<span data-ttu-id="dc4a7-258">业务服务器 2015年累积更新 KB3061064 的 Skype</span><span class="sxs-lookup"><span data-stu-id="dc4a7-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[<span data-ttu-id="dc4a7-259">基于视频的屏幕共享 (VBSS) 有业务服务器 2015年的 Skype</span><span class="sxs-lookup"><span data-stu-id="dc4a7-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/en-us/kb/3170163)
