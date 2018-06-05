---
title: 适用于 Skype for Business Server 2015 的基于视频的屏幕共享
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 有关基于视频的屏幕共享 (VbSS)，这是现在可供下载的业务服务器 2015年规划和配置信息的 Skype： 业务服务器 2015年累积更新 KB3061064 的 Skype。
ms.openlocfilehash: a76778db02ece625d7c9933662d88aea99dbdf7f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569255"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server-2015"></a><span data-ttu-id="61fa2-103">适用于 Skype for Business Server 2015 的基于视频的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="61fa2-103">Video based Screen Sharing for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="61fa2-104">有关基于视频的屏幕共享 (VbSS)，这是现在可供下载的业务服务器 2015年规划和配置信息的 Skype：[业务服务器 2015年累积更新 KB3061064 的 Skype](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。</span><span class="sxs-lookup"><span data-stu-id="61fa2-104">Skype for Business Server 2015 planning and configuration information for Video-based Screen Sharing (VbSS), which is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690).</span></span>
  
<span data-ttu-id="61fa2-105">基于视频的屏幕共享，或者 VbSS，变得从 Lync 注销屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="61fa2-105">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="61fa2-106">VbSS 与传统屏幕共享之间的区别与所用的基础协议及其所擅长的技能有关。</span><span class="sxs-lookup"><span data-stu-id="61fa2-106">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="61fa2-107">屏幕共享使用远程桌面协议 (RDP)，该协议擅长在各用户计算机之间创建数千个一对一会话。</span><span class="sxs-lookup"><span data-stu-id="61fa2-107">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="61fa2-108">较新的技术 VbSS 将使用用户数据报协议 (UDP)。</span><span class="sxs-lookup"><span data-stu-id="61fa2-108">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="61fa2-109">Skype 业务服务器想要提高人的 1-为-1，以及其 1 对多 （多方） 对话和会议体验。</span><span class="sxs-lookup"><span data-stu-id="61fa2-109">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="61fa2-110">VbSS 使用媒体平台（该平台将 UDP 作为基础协议），旨在改进视频的开始时间、你所观看内容的观看质量（尤其是当你所观看的内容正在快速移动时）以及整体可靠性。</span><span class="sxs-lookup"><span data-stu-id="61fa2-110">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="61fa2-111">改进屏幕共享的部分目的在于尽可能无缝地在 VbSS 与 RDP 之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="61fa2-111">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="61fa2-112">由于 VbSS 是屏幕共享 Skype 业务服务器中使用的基础技术的更新，因此它可能很难检测您在利用除非正在看 SIP 详细信息中的网络流量，或您正在共享的技术内容fast 移动或三维。</span><span class="sxs-lookup"><span data-stu-id="61fa2-112">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="61fa2-113">如果，例如，工作场所中有大量的旧客户端，RDP 将仍可作为安全模式向您的会议和对话。</span><span class="sxs-lookup"><span data-stu-id="61fa2-113">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="61fa2-114">Skype 业务服务器使用内部逻辑决定哪些 （VbSS 或传统的屏幕共享） 客户端连接时要应用的两种方法。</span><span class="sxs-lookup"><span data-stu-id="61fa2-114">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="61fa2-115">RDP 在必要时可以并且会替换为 VbSS，确保你的观看体验不会被中断。</span><span class="sxs-lookup"><span data-stu-id="61fa2-115">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="61fa2-116">规划</span><span class="sxs-lookup"><span data-stu-id="61fa2-116">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="61fa2-117">VbSS 的利与弊</span><span class="sxs-lookup"><span data-stu-id="61fa2-117">VbSS pros and cons</span></span>

<span data-ttu-id="61fa2-118">切换到 VbSS 旨在做出三项关键改进：</span><span class="sxs-lookup"><span data-stu-id="61fa2-118">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="61fa2-119">与单独的 RDP 相比，提高屏幕共享的可靠性（高达 5%）。</span><span class="sxs-lookup"><span data-stu-id="61fa2-119">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="61fa2-120">与单独的 RDP 相比，使会话设置和视频体验更快（设置时间减半，每秒帧数提高为 6:1）。</span><span class="sxs-lookup"><span data-stu-id="61fa2-120">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="61fa2-121">在低带宽情况下优于 RDP，即使在共享高运动内容（如三维图形）时也是如此。</span><span class="sxs-lookup"><span data-stu-id="61fa2-121">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="61fa2-122">请记住，这些数字依赖于你网络的运行状况和适当性能调整，并且可能涉及你自身外部的网络（如果你的客户端位于移动设备上）。</span><span class="sxs-lookup"><span data-stu-id="61fa2-122">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="61fa2-p104">你还应注意，我们牺牲了共享内容的部分保真度/脆度来确保可靠性、速度和效率。在大多数情况下，这对用户并不明显。</span><span class="sxs-lookup"><span data-stu-id="61fa2-p104">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency. In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="61fa2-125">端口和协议</span><span class="sxs-lookup"><span data-stu-id="61fa2-125">Ports and protocols</span></span>

<span data-ttu-id="61fa2-126">**所需的服务器端口**</span><span class="sxs-lookup"><span data-stu-id="61fa2-126">**Required server ports**</span></span>

|<span data-ttu-id="61fa2-127">**服务器角色**</span><span class="sxs-lookup"><span data-stu-id="61fa2-127">**Server role**</span></span>|<span data-ttu-id="61fa2-128">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="61fa2-128">**Service name**</span></span>|<span data-ttu-id="61fa2-129">**端口或端口范围**</span><span class="sxs-lookup"><span data-stu-id="61fa2-129">**Port or port range**</span></span>|<span data-ttu-id="61fa2-130">**协议**</span><span class="sxs-lookup"><span data-stu-id="61fa2-130">**Protocol**</span></span>|<span data-ttu-id="61fa2-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="61fa2-131">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61fa2-132">前端服务器</span><span class="sxs-lookup"><span data-stu-id="61fa2-132">Front End Servers</span></span>  <br/> |<span data-ttu-id="61fa2-133">Skype 业务服务器应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="61fa2-133">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="61fa2-134">5065</span><span class="sxs-lookup"><span data-stu-id="61fa2-134">5065</span></span>  <br/> |<span data-ttu-id="61fa2-135">TCP</span><span class="sxs-lookup"><span data-stu-id="61fa2-135">TCP</span></span>  <br/> |<span data-ttu-id="61fa2-136">用于应用程序共享的传入 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="61fa2-136">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="61fa2-137">前端服务器</span><span class="sxs-lookup"><span data-stu-id="61fa2-137">Front End Servers</span></span>  <br/> |<span data-ttu-id="61fa2-138">Skype 业务服务器应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="61fa2-138">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="61fa2-139">49152-65535</span><span class="sxs-lookup"><span data-stu-id="61fa2-139">49152-65535</span></span>  <br/> |<span data-ttu-id="61fa2-140">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="61fa2-140">TCP/UDP</span></span>  <br/> |<span data-ttu-id="61fa2-141">用于应用程序共享的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="61fa2-141">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="61fa2-142">**所需的客户端端口**</span><span class="sxs-lookup"><span data-stu-id="61fa2-142">**Required client ports**</span></span>

|<span data-ttu-id="61fa2-143">**组件**</span><span class="sxs-lookup"><span data-stu-id="61fa2-143">**Component**</span></span>|<span data-ttu-id="61fa2-144">**端口范围**</span><span class="sxs-lookup"><span data-stu-id="61fa2-144">**Port range**</span></span>|<span data-ttu-id="61fa2-145">**协议**</span><span class="sxs-lookup"><span data-stu-id="61fa2-145">**Protocol**</span></span>|<span data-ttu-id="61fa2-146">**说明**</span><span class="sxs-lookup"><span data-stu-id="61fa2-146">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61fa2-147">客户端</span><span class="sxs-lookup"><span data-stu-id="61fa2-147">Clients</span></span>  <br/> |<span data-ttu-id="61fa2-148">1024-65535</span><span class="sxs-lookup"><span data-stu-id="61fa2-148">1024-65535</span></span>  <br/> |<span data-ttu-id="61fa2-149">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="61fa2-149">TCP/UDP</span></span>  <br/> |<span data-ttu-id="61fa2-150">应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="61fa2-150">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="61fa2-151">如果以下的媒体端口已启用 QoS，还启用 VbSS 包括 AS MCU 将使用视频端口设置中所示的桌面共享会议期间加粗下面的屏幕共享流量。</span><span class="sxs-lookup"><span data-stu-id="61fa2-151">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="61fa2-152">这些设置是一个特例，并实现这些功能的时，必须使用这些准确的设置。</span><span class="sxs-lookup"><span data-stu-id="61fa2-152">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="61fa2-153">这将覆盖[QoS 文档](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)中的其他建议的设置。</span><span class="sxs-lookup"><span data-stu-id="61fa2-153">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="61fa2-154">此外需要 QoS GPO 除了定义这些端口值中指定 ASMCUSVC.exe Fo 共享您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="61fa2-154">Fo application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="61fa2-155">**应用程序服务器 QoS/VbSS 所需的设置**</span><span class="sxs-lookup"><span data-stu-id="61fa2-155">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="61fa2-156">**属性**</span><span class="sxs-lookup"><span data-stu-id="61fa2-156">**Property**</span></span>|<span data-ttu-id="61fa2-157">**端口值**</span><span class="sxs-lookup"><span data-stu-id="61fa2-157">**Port value**</span></span>|<span data-ttu-id="61fa2-158">**协议**</span><span class="sxs-lookup"><span data-stu-id="61fa2-158">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="61fa2-159">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="61fa2-159">AudioPortStart</span></span>  <br/> |<span data-ttu-id="61fa2-160">49152</span><span class="sxs-lookup"><span data-stu-id="61fa2-160">49152</span></span>  <br/> |<span data-ttu-id="61fa2-161">UDP</span><span class="sxs-lookup"><span data-stu-id="61fa2-161">UDP</span></span>  <br/> |
|<span data-ttu-id="61fa2-162">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="61fa2-162">AudioPortCount</span></span>  <br/> |<span data-ttu-id="61fa2-163">8348</span><span class="sxs-lookup"><span data-stu-id="61fa2-163">8348</span></span>  <br/> |<span data-ttu-id="61fa2-164">UDP</span><span class="sxs-lookup"><span data-stu-id="61fa2-164">UDP</span></span>  <br/> |
|<span data-ttu-id="61fa2-165">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="61fa2-165">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="61fa2-166">**57501**</span><span class="sxs-lookup"><span data-stu-id="61fa2-166">**57501**</span></span> <br/> |<span data-ttu-id="61fa2-167">UDP</span><span class="sxs-lookup"><span data-stu-id="61fa2-167">UDP</span></span>  <br/> |
|<span data-ttu-id="61fa2-168">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="61fa2-168">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="61fa2-169">**8034**</span><span class="sxs-lookup"><span data-stu-id="61fa2-169">**8034**</span></span> <br/> |<span data-ttu-id="61fa2-170">UDP</span><span class="sxs-lookup"><span data-stu-id="61fa2-170">UDP</span></span>  <br/> |
|<span data-ttu-id="61fa2-171">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="61fa2-171">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="61fa2-172">40803</span><span class="sxs-lookup"><span data-stu-id="61fa2-172">40803</span></span>  <br/> |<span data-ttu-id="61fa2-173">UDP</span><span class="sxs-lookup"><span data-stu-id="61fa2-173">UDP</span></span>  <br/> |
|<span data-ttu-id="61fa2-174">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="61fa2-174">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="61fa2-175">8348</span><span class="sxs-lookup"><span data-stu-id="61fa2-175">8348</span></span>  <br/> |<span data-ttu-id="61fa2-176">UDP</span><span class="sxs-lookup"><span data-stu-id="61fa2-176">UDP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="61fa2-177">容量规划</span><span class="sxs-lookup"><span data-stu-id="61fa2-177">Capacity planning</span></span>

<span data-ttu-id="61fa2-178">每个前端服务器运行 Skype 业务服务器 2015年累积更新 2 (CU2) 支持针对屏幕显示使用 RDP (每个会议的虽然只 250) 共享达 375 参与者。</span><span class="sxs-lookup"><span data-stu-id="61fa2-178">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="61fa2-179">引入并使用 VbSS 时，此容量在 CU3 后不会更改。</span><span class="sxs-lookup"><span data-stu-id="61fa2-179">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="61fa2-180">也就是说，我们已在实验室中完成性能和压力测试，并且就你自己的部署还应考虑以下度量（当然具体要取决于使用情况）。</span><span class="sxs-lookup"><span data-stu-id="61fa2-180">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="61fa2-181">假设：</span><span class="sxs-lookup"><span data-stu-id="61fa2-181">Assuming:</span></span>
  
- <span data-ttu-id="61fa2-182">您将 Skype 用于业务 Server 2015 CU2 部署中。</span><span class="sxs-lookup"><span data-stu-id="61fa2-182">You're using Skype for Business Server 2015 CU2 in your deployment.</span></span>
    
- <span data-ttu-id="61fa2-183">在您 Skype 业务服务器环境中的所有用户都具有高于 1920 x 1080 的屏幕分辨率。</span><span class="sxs-lookup"><span data-stu-id="61fa2-183">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="61fa2-184">全容量 （即如上所述，每个前端服务器的 375 屏幕共享参与者在每个会议的总，但仅 250），您前端服务器可能正在使用 ~ 89%1 千兆位网卡。</span><span class="sxs-lookup"><span data-stu-id="61fa2-184">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="61fa2-185">这是因为现有屏幕共享业务服务器 CU2 (RDP) 的技术 Skype 中的传输屏幕上内容的演示者的 PC 本机的分辨率。</span><span class="sxs-lookup"><span data-stu-id="61fa2-185">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="61fa2-186">因此使用较高的屏幕分辨率分解，您可能已遇到屏幕与 Skype 的业务 Server 2015 CU2 共享的网络瓶颈。</span><span class="sxs-lookup"><span data-stu-id="61fa2-186">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="61fa2-187">要缓解此问题，以下一个或多个选项可能有用：</span><span class="sxs-lookup"><span data-stu-id="61fa2-187">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="61fa2-188">从 1 千兆位网卡的您前端服务器升级到 10 的千兆以太网卡片。</span><span class="sxs-lookup"><span data-stu-id="61fa2-188">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="61fa2-189">增加到负载平衡流量的前端服务器数量。</span><span class="sxs-lookup"><span data-stu-id="61fa2-189">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="61fa2-190">通过对任意通道所用的最大带宽设定限制来限制用于 VbSS 和 RDP 的带宽（比特率）。</span><span class="sxs-lookup"><span data-stu-id="61fa2-190">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="61fa2-p108">此表中的数字受个别网络和所共享内容的影响。请通过测试建立一个或多个网络的基准。</span><span class="sxs-lookup"><span data-stu-id="61fa2-p108">The numbers in this table are influenced by individual networks and by the content being shared. Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="61fa2-193">**1080p 内容**</span><span class="sxs-lookup"><span data-stu-id="61fa2-193">**1080p Content**</span></span>|<span data-ttu-id="61fa2-194">**RDP 平均值**</span><span class="sxs-lookup"><span data-stu-id="61fa2-194">**RDP Average**</span></span>|<span data-ttu-id="61fa2-195">**RDP 峰值**</span><span class="sxs-lookup"><span data-stu-id="61fa2-195">**RDP Peak**</span></span>|<span data-ttu-id="61fa2-196">**VbSS 平均值**</span><span class="sxs-lookup"><span data-stu-id="61fa2-196">**VbSS Average**</span></span>|<span data-ttu-id="61fa2-197">**VbSS 峰值**</span><span class="sxs-lookup"><span data-stu-id="61fa2-197">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61fa2-198">PPT</span><span class="sxs-lookup"><span data-stu-id="61fa2-198">PPT</span></span>  <br/> |<span data-ttu-id="61fa2-199">200 kbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-199">200kbps</span></span>  <br/> |<span data-ttu-id="61fa2-200">12mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-200">12mbps</span></span>  <br/> |<span data-ttu-id="61fa2-201">100 kbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-201">100kbps</span></span>  <br/> |<span data-ttu-id="61fa2-202">3mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-202">3mbps</span></span>  <br/> |
|<span data-ttu-id="61fa2-203">CAD</span><span class="sxs-lookup"><span data-stu-id="61fa2-203">CAD</span></span>  <br/> |<span data-ttu-id="61fa2-204">3mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-204">3mbps</span></span>  <br/> |<span data-ttu-id="61fa2-205">7mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-205">7mbps</span></span>  <br/> |<span data-ttu-id="61fa2-206">1mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-206">1mbps</span></span>  <br/> |<span data-ttu-id="61fa2-207">3mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-207">3mbps</span></span>  <br/> |
|<span data-ttu-id="61fa2-208">视频</span><span class="sxs-lookup"><span data-stu-id="61fa2-208">Video</span></span>  <br/> |<span data-ttu-id="61fa2-209">5mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-209">5mbps</span></span>  <br/> |<span data-ttu-id="61fa2-210">7mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-210">7mbps</span></span>  <br/> |<span data-ttu-id="61fa2-211">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-211">1.3mbps</span></span>  <br/> |<span data-ttu-id="61fa2-212">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="61fa2-212">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="61fa2-213">媒体流量的网络带宽要求</span><span class="sxs-lookup"><span data-stu-id="61fa2-213">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="61fa2-214">VbSS 带宽为：</span><span class="sxs-lookup"><span data-stu-id="61fa2-214">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="61fa2-215">**视频编解码器**</span><span class="sxs-lookup"><span data-stu-id="61fa2-215">**Video codec**</span></span>|<span data-ttu-id="61fa2-216">**分辨率和纵横比**</span><span class="sxs-lookup"><span data-stu-id="61fa2-216">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="61fa2-217">**最大视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="61fa2-217">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="61fa2-218">**最小视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="61fa2-218">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61fa2-219">H.264</span><span class="sxs-lookup"><span data-stu-id="61fa2-219">H.264</span></span>  <br/> |<span data-ttu-id="61fa2-220">1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="61fa2-220">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="61fa2-221">（纵横比取决于共享者的显示器分辨率，并且不会始终为 16:9）</span><span class="sxs-lookup"><span data-stu-id="61fa2-221">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="61fa2-222">4000</span><span class="sxs-lookup"><span data-stu-id="61fa2-222">4000</span></span>  <br/> |<span data-ttu-id="61fa2-223">1500</span><span class="sxs-lookup"><span data-stu-id="61fa2-223">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="61fa2-224">客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="61fa2-224">Clients and servers support</span></span>

<span data-ttu-id="61fa2-225">基于视频的屏幕共享要求 Skype 的业务服务器 2015 CU3 或更高版本，以及支持客户端[的 Skype for Business 的移动客户端功能比较](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)和[会议支持](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)中列出的当前版本。</span><span class="sxs-lookup"><span data-stu-id="61fa2-225">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="61fa2-226">有其中屏幕共享将转换到 RDP，类似这样的情况下：</span><span class="sxs-lookup"><span data-stu-id="61fa2-226">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="61fa2-227">如果你的帐户托管在 ASMCU 不满足支持 VbSS 的最低内部版本的环境中。</span><span class="sxs-lookup"><span data-stu-id="61fa2-227">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="61fa2-228">如果 for Business 客户端使用的 Skype 较早版本的任何人加入会话，例如任何人都使用低于 16.0.6330.1000，对于业务会议室系统设备，Skype 或业务移动应用程序的 Skype 任何 Windows 客户端版本。</span><span class="sxs-lookup"><span data-stu-id="61fa2-228">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="61fa2-229">如果用户正在共享 Skype 的企业 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="61fa2-229">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="61fa2-230">如果某人的 Businesson Mac 使用 Skype 并不驻留在 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="61fa2-230">If someone is using Skype for Businesson Mac and not is homed on Skype for Business Online.</span></span>
- <span data-ttu-id="61fa2-231">如果某人开始任何程序/Windows 共享。</span><span class="sxs-lookup"><span data-stu-id="61fa2-231">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="61fa2-232">如果某人开始录制会话。</span><span class="sxs-lookup"><span data-stu-id="61fa2-232">If someone starts recording the session.</span></span>
- <span data-ttu-id="61fa2-233">如果某人在会话期间调用远程屏幕控制。</span><span class="sxs-lookup"><span data-stu-id="61fa2-233">If someone invokes Remote Screen Control during the session.</span></span>

    <span data-ttu-id="61fa2-p109">请注意，会话切换到 RDP 后，将不会切换回 VbSS。另外，从 VbSS 进行切换应为无缝操作，并且希望在大多数情况下不容易被检测到。</span><span class="sxs-lookup"><span data-stu-id="61fa2-p109">Be aware that once the session transitions to RDP it will not transition back to VbSS. Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
  
- <span data-ttu-id="61fa2-236">包含 250 个以上的参与者的会议（当前不支持 VbSS）。</span><span class="sxs-lookup"><span data-stu-id="61fa2-236">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>
    
> [!NOTE]
> <span data-ttu-id="61fa2-237">它具有不受支持到块中，或尝试阻止，请从转换 VbSS 到中 Skype RDP 业务屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="61fa2-237">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="61fa2-238">启用、禁用和配置 VbSS</span><span class="sxs-lookup"><span data-stu-id="61fa2-238">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="61fa2-239">很好的做法是，您已经为业务服务器 2015年累积更新 3 (CU3)，所有用户将默认情况下启用为 1-1 和多方 VbSS 安装 Skype 后。</span><span class="sxs-lookup"><span data-stu-id="61fa2-239">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3), all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="61fa2-240">如果你有理由不为所有用户启用此功能，这对你来说可能有问题。</span><span class="sxs-lookup"><span data-stu-id="61fa2-240">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="61fa2-241">在这种情况下，你可以使用这些步骤禁用用户（然后执行启用用户步骤）：</span><span class="sxs-lookup"><span data-stu-id="61fa2-241">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="61fa2-242">如何禁止用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="61fa2-242">How to disable users from using VbSS</span></span>

- <span data-ttu-id="61fa2-243">您可以分配给不应通过为业务管理控制台 （替换 [PolicyName] 与您正在执行此操作的策略） Skype 中运行此 cmdlet 使用 VbSS 任何用户不允许 VbSS 的用户策略：</span><span class="sxs-lookup"><span data-stu-id="61fa2-243">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="61fa2-244">你还可以更新全局会议策略，这会影响所有未分配策略的用户：</span><span class="sxs-lookup"><span data-stu-id="61fa2-244">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="61fa2-245">此命令的详细信息，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="61fa2-245">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="61fa2-246">如果需要完全关闭 VbSS，你可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="61fa2-246">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="61fa2-247">此命令的详细信息，请参阅[设置 CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="61fa2-247">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="61fa2-248">在业务会议多方 Skype，所有客户端终结点将尊重会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="61fa2-248">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="61fa2-249">如何允许用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="61fa2-249">How to enable users to use VbSS</span></span>

- <span data-ttu-id="61fa2-250">您可以分配给需要通过业务管理控制台 （替换 [PolicyName] 与您正在执行此操作的策略） 的 Skype 中运行此 cmdlet 使用 VbSS 任何用户允许 VbSS 的特定用户策略：</span><span class="sxs-lookup"><span data-stu-id="61fa2-250">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="61fa2-251">你还可以更新全局会议策略，这会影响所有未分配策略的用户：</span><span class="sxs-lookup"><span data-stu-id="61fa2-251">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="61fa2-252">此命令的详细信息，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="61fa2-252">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="61fa2-253">如果需要在关闭 VbSS 后将其重新打开（默认情况下处于打开状态），你可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="61fa2-253">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="61fa2-254">此命令的详细信息，请参阅[设置 CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="61fa2-254">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="61fa2-255">在业务会议多方 Skype，所有客户端终结点将尊重会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="61fa2-255">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="61fa2-256">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61fa2-256">See also</span></span>

[<span data-ttu-id="61fa2-257">业务服务器 2015年累积更新 KB3061064 的 Skype</span><span class="sxs-lookup"><span data-stu-id="61fa2-257">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[<span data-ttu-id="61fa2-258">基于视频的屏幕共享 (VBSS) 有业务服务器 2015年的 Skype</span><span class="sxs-lookup"><span data-stu-id="61fa2-258">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/en-us/kb/3170163)
