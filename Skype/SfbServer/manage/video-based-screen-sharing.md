---
title: 适用于 Skype for Business Server 的基于视频的屏幕共享
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 基于视频的屏幕共享的 Skype for business 服务器规划和配置信息（VbSS）
ms.openlocfilehash: f0d474772b94389c1d69264be61b3bee2b46a385
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817042"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="9fec5-103">适用于 Skype for Business Server 的基于视频的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="9fec5-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="9fec5-104">Skype for business Server 2015 中的基于视频的屏幕共享（VbSS）现在可供下载： [skype for Business server 2015 累积更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。</span><span class="sxs-lookup"><span data-stu-id="9fec5-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690).</span></span> <span data-ttu-id="9fec5-105">VbSS 包含在 Skype for Business Server 2019 中。</span><span class="sxs-lookup"><span data-stu-id="9fec5-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="9fec5-106">基于视频的屏幕共享或 VbSS 从 Lync 屏幕共享中增长。</span><span class="sxs-lookup"><span data-stu-id="9fec5-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="9fec5-107">VbSS 与传统屏幕共享之间的区别与所用的基础协议及其所擅长的技能有关。</span><span class="sxs-lookup"><span data-stu-id="9fec5-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="9fec5-108">屏幕共享使用远程桌面协议 (RDP)，该协议擅长在各用户计算机之间创建数千个一对一会话。</span><span class="sxs-lookup"><span data-stu-id="9fec5-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="9fec5-109">较新的技术 VbSS 将使用用户数据报协议 (UDP)。</span><span class="sxs-lookup"><span data-stu-id="9fec5-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="9fec5-110">Skype for Business 服务器希望提高人员的1对1，以及其一对多（多方）对话和会议体验。</span><span class="sxs-lookup"><span data-stu-id="9fec5-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="9fec5-111">VbSS 使用媒体平台（该平台将 UDP 作为基础协议），旨在改进视频的开始时间、你所观看内容的观看质量（尤其是当你所观看的内容正在快速移动时）以及整体可靠性。</span><span class="sxs-lookup"><span data-stu-id="9fec5-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="9fec5-112">改进屏幕共享的部分目的在于尽可能无缝地在 VbSS 与 RDP 之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="9fec5-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="9fec5-113">由于 VbSS 是对 Skype for business Server 的屏幕共享中使用的基础技术的更新，因此可能很难检测你正在使用的技术，除非你在网络流量中查看 SIP 详细信息，或者你正在共享的内容快速移动或三维。</span><span class="sxs-lookup"><span data-stu-id="9fec5-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="9fec5-114">例如，如果您的工作场所有大量旧版客户端，则 RDP 仍可用作您的会议和对话的安全保护。</span><span class="sxs-lookup"><span data-stu-id="9fec5-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="9fec5-115">Skype for Business 服务器使用内部逻辑确定在客户端连接时要应用的两种方法（VbSS 或传统的屏幕共享）。</span><span class="sxs-lookup"><span data-stu-id="9fec5-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="9fec5-116">RDP 在必要时可以并且会替换为 VbSS，确保你的观看体验不会被中断。</span><span class="sxs-lookup"><span data-stu-id="9fec5-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="9fec5-117">规划</span><span class="sxs-lookup"><span data-stu-id="9fec5-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="9fec5-118">VbSS 的利与弊</span><span class="sxs-lookup"><span data-stu-id="9fec5-118">VbSS pros and cons</span></span>

<span data-ttu-id="9fec5-119">切换到 VbSS 旨在做出三项关键改进：</span><span class="sxs-lookup"><span data-stu-id="9fec5-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="9fec5-120">与单独的 RDP 相比，提高屏幕共享的可靠性（高达 5%）。</span><span class="sxs-lookup"><span data-stu-id="9fec5-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="9fec5-121">与单独的 RDP 相比，使会话设置和视频体验更快（设置时间减半，每秒帧数提高为 6:1）。</span><span class="sxs-lookup"><span data-stu-id="9fec5-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="9fec5-122">在低带宽情况下优于 RDP，即使在共享高运动内容（如三维图形）时也是如此。</span><span class="sxs-lookup"><span data-stu-id="9fec5-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="9fec5-123">请记住，这些数字依赖于你网络的运行状况和适当性能调整，并且可能涉及你自身外部的网络（如果你的客户端位于移动设备上）。</span><span class="sxs-lookup"><span data-stu-id="9fec5-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="9fec5-p105">你还应注意，我们牺牲了共享内容的部分保真度/脆度来确保可靠性、速度和效率。在大多数情况下，这对用户并不明显。</span><span class="sxs-lookup"><span data-stu-id="9fec5-p105">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency. In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="9fec5-126">端口和协议</span><span class="sxs-lookup"><span data-stu-id="9fec5-126">Ports and protocols</span></span>

<span data-ttu-id="9fec5-127">**所需的服务器端口**</span><span class="sxs-lookup"><span data-stu-id="9fec5-127">**Required server ports**</span></span>

|<span data-ttu-id="9fec5-128">**服务器角色**</span><span class="sxs-lookup"><span data-stu-id="9fec5-128">**Server role**</span></span>|<span data-ttu-id="9fec5-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="9fec5-129">**Service name**</span></span>|<span data-ttu-id="9fec5-130">**端口或端口范围**</span><span class="sxs-lookup"><span data-stu-id="9fec5-130">**Port or port range**</span></span>|<span data-ttu-id="9fec5-131">**协议**</span><span class="sxs-lookup"><span data-stu-id="9fec5-131">**Protocol**</span></span>|<span data-ttu-id="9fec5-132">**备注**</span><span class="sxs-lookup"><span data-stu-id="9fec5-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fec5-133">前端服务器</span><span class="sxs-lookup"><span data-stu-id="9fec5-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="9fec5-134">Skype for Business 服务器应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="9fec5-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="9fec5-135">5065</span><span class="sxs-lookup"><span data-stu-id="9fec5-135">5065</span></span>  <br/> |<span data-ttu-id="9fec5-136">TCP</span><span class="sxs-lookup"><span data-stu-id="9fec5-136">TCP</span></span>  <br/> |<span data-ttu-id="9fec5-137">用于应用程序共享的传入 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="9fec5-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="9fec5-138">前端服务器</span><span class="sxs-lookup"><span data-stu-id="9fec5-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="9fec5-139">Skype for Business 服务器应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="9fec5-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="9fec5-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="9fec5-140">49152-65535</span></span>  <br/> |<span data-ttu-id="9fec5-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="9fec5-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="9fec5-142">用于应用程序共享的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="9fec5-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="9fec5-143">**所需的客户端端口**</span><span class="sxs-lookup"><span data-stu-id="9fec5-143">**Required client ports**</span></span>

|<span data-ttu-id="9fec5-144">**组件**</span><span class="sxs-lookup"><span data-stu-id="9fec5-144">**Component**</span></span>|<span data-ttu-id="9fec5-145">**端口范围**</span><span class="sxs-lookup"><span data-stu-id="9fec5-145">**Port range**</span></span>|<span data-ttu-id="9fec5-146">**协议**</span><span class="sxs-lookup"><span data-stu-id="9fec5-146">**Protocol**</span></span>|<span data-ttu-id="9fec5-147">**注释**</span><span class="sxs-lookup"><span data-stu-id="9fec5-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fec5-148">客户端</span><span class="sxs-lookup"><span data-stu-id="9fec5-148">Clients</span></span>  <br/> |<span data-ttu-id="9fec5-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="9fec5-149">1024-65535</span></span>  <br/> |<span data-ttu-id="9fec5-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="9fec5-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="9fec5-151">应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="9fec5-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="9fec5-152">如果为以下媒体端口启用了 QoS，并且在包括桌面共享的会议期间启用了 VbSS，则在屏幕共享流量中，将使用以粗体显示的视频端口设置。</span><span class="sxs-lookup"><span data-stu-id="9fec5-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9fec5-153">这些设置是一种特殊情况，在实现这些功能时，必须使用这些确切设置。</span><span class="sxs-lookup"><span data-stu-id="9fec5-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="9fec5-154">这将覆盖[文档中针对 QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)的其他推荐设置。</span><span class="sxs-lookup"><span data-stu-id="9fec5-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="9fec5-155">对于应用程序共享，除了定义这些端口值之外，还需要在 QoS GPO 中指定 ASMCUSVC。</span><span class="sxs-lookup"><span data-stu-id="9fec5-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="9fec5-156">**应用程序服务器 QoS/VbSS 所需设置**</span><span class="sxs-lookup"><span data-stu-id="9fec5-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="9fec5-157">**属性**</span><span class="sxs-lookup"><span data-stu-id="9fec5-157">**Property**</span></span>|<span data-ttu-id="9fec5-158">**端口值**</span><span class="sxs-lookup"><span data-stu-id="9fec5-158">**Port value**</span></span>|<span data-ttu-id="9fec5-159">**协议**</span><span class="sxs-lookup"><span data-stu-id="9fec5-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9fec5-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="9fec5-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="9fec5-161">49152</span><span class="sxs-lookup"><span data-stu-id="9fec5-161">49152</span></span>  <br/> |<span data-ttu-id="9fec5-162">UDP</span><span class="sxs-lookup"><span data-stu-id="9fec5-162">UDP</span></span>  <br/> |
|<span data-ttu-id="9fec5-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="9fec5-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="9fec5-164">8348</span><span class="sxs-lookup"><span data-stu-id="9fec5-164">8348</span></span>  <br/> |<span data-ttu-id="9fec5-165">UDP</span><span class="sxs-lookup"><span data-stu-id="9fec5-165">UDP</span></span>  <br/> |
|<span data-ttu-id="9fec5-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="9fec5-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="9fec5-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="9fec5-167">**57501**</span></span> <br/> |<span data-ttu-id="9fec5-168">UDP</span><span class="sxs-lookup"><span data-stu-id="9fec5-168">UDP</span></span>  <br/> |
|<span data-ttu-id="9fec5-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="9fec5-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="9fec5-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="9fec5-170">**8034**</span></span> <br/> |<span data-ttu-id="9fec5-171">UDP</span><span class="sxs-lookup"><span data-stu-id="9fec5-171">UDP</span></span>  <br/> |
|<span data-ttu-id="9fec5-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="9fec5-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="9fec5-173">40803</span><span class="sxs-lookup"><span data-stu-id="9fec5-173">40803</span></span>  <br/> |<span data-ttu-id="9fec5-174">TCP</span><span class="sxs-lookup"><span data-stu-id="9fec5-174">TCP</span></span>  <br/> |
|<span data-ttu-id="9fec5-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="9fec5-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="9fec5-176">8348</span><span class="sxs-lookup"><span data-stu-id="9fec5-176">8348</span></span>  <br/> |<span data-ttu-id="9fec5-177">TCP</span><span class="sxs-lookup"><span data-stu-id="9fec5-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="9fec5-178">容量规划</span><span class="sxs-lookup"><span data-stu-id="9fec5-178">Capacity planning</span></span>

<span data-ttu-id="9fec5-179">运行 Skype for Business Server 2015 累积更新2（CU2）或更高版本的每台前端服务器都支持使用 RDP 的屏幕共享的最多375个参与者（尽管每个会议仅有250）。</span><span class="sxs-lookup"><span data-stu-id="9fec5-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="9fec5-180">引入并使用 VbSS 时，此容量在 CU3 后不会更改。</span><span class="sxs-lookup"><span data-stu-id="9fec5-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="9fec5-181">也就是说，我们已在实验室中完成性能和压力测试，并且就你自己的部署还应考虑以下度量（当然具体要取决于使用情况）。</span><span class="sxs-lookup"><span data-stu-id="9fec5-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="9fec5-182">假设：</span><span class="sxs-lookup"><span data-stu-id="9fec5-182">Assuming:</span></span>
  
- <span data-ttu-id="9fec5-183">您在部署中使用的是 Skype for Business Server 2015 CU2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="9fec5-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="9fec5-184">Skype for Business 服务器环境中的所有用户都具有比1920x1080 更高的屏幕分辨率。</span><span class="sxs-lookup"><span data-stu-id="9fec5-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="9fec5-185">在完全容量（如上所述）是每台前端服务器的375屏幕共享参与者总数，虽然只有250每个会议，但你的前端服务器可能正在使用约1千兆个网卡的89%。</span><span class="sxs-lookup"><span data-stu-id="9fec5-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="9fec5-186">这是因为 Skype for Business Server CU2 （RDP）中的现有屏幕共享技术以演示者电脑的本机分辨率传输屏幕内容。</span><span class="sxs-lookup"><span data-stu-id="9fec5-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="9fec5-187">因此，在中考虑更高的屏幕分辨率，你可能已遇到与 Skype for Business Server 2015 CU2 的屏幕共享的网络瓶颈。</span><span class="sxs-lookup"><span data-stu-id="9fec5-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="9fec5-188">要缓解此问题，以下一个或多个选项可能有用：</span><span class="sxs-lookup"><span data-stu-id="9fec5-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="9fec5-189">将前端服务器从1千兆位网卡升级到10千兆位以太网卡。</span><span class="sxs-lookup"><span data-stu-id="9fec5-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="9fec5-190">增加前端服务器的数量以达到负载平衡流量。</span><span class="sxs-lookup"><span data-stu-id="9fec5-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="9fec5-191">通过对任意通道所用的最大带宽设定限制来限制用于 VbSS 和 RDP 的带宽（比特率）。</span><span class="sxs-lookup"><span data-stu-id="9fec5-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="9fec5-p109">此表中的数字受个别网络和所共享内容的影响。请通过测试建立一个或多个网络的基准。</span><span class="sxs-lookup"><span data-stu-id="9fec5-p109">The numbers in this table are influenced by individual networks and by the content being shared. Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="9fec5-194">\*\*1080p 内容 \*\*</span><span class="sxs-lookup"><span data-stu-id="9fec5-194">**1080p Content**</span></span>|<span data-ttu-id="9fec5-195">**RDP 平均**</span><span class="sxs-lookup"><span data-stu-id="9fec5-195">**RDP Average**</span></span>|<span data-ttu-id="9fec5-196">**RDP 峰值**</span><span class="sxs-lookup"><span data-stu-id="9fec5-196">**RDP Peak**</span></span>|<span data-ttu-id="9fec5-197">**VbSS 平均值**</span><span class="sxs-lookup"><span data-stu-id="9fec5-197">**VbSS Average**</span></span>|<span data-ttu-id="9fec5-198">**VbSS 峰值**</span><span class="sxs-lookup"><span data-stu-id="9fec5-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fec5-199">PPT</span><span class="sxs-lookup"><span data-stu-id="9fec5-199">PPT</span></span>  <br/> |<span data-ttu-id="9fec5-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-200">200kbps</span></span>  <br/> |<span data-ttu-id="9fec5-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-201">12mbps</span></span>  <br/> |<span data-ttu-id="9fec5-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-202">100kbps</span></span>  <br/> |<span data-ttu-id="9fec5-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="9fec5-204">CAD</span><span class="sxs-lookup"><span data-stu-id="9fec5-204">CAD</span></span>  <br/> |<span data-ttu-id="9fec5-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-205">3mbps</span></span>  <br/> |<span data-ttu-id="9fec5-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-206">7mbps</span></span>  <br/> |<span data-ttu-id="9fec5-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-207">1mbps</span></span>  <br/> |<span data-ttu-id="9fec5-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="9fec5-209">视频</span><span class="sxs-lookup"><span data-stu-id="9fec5-209">Video</span></span>  <br/> |<span data-ttu-id="9fec5-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-210">5mbps</span></span>  <br/> |<span data-ttu-id="9fec5-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-211">7mbps</span></span>  <br/> |<span data-ttu-id="9fec5-212">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="9fec5-213">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="9fec5-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="9fec5-214">媒体流量的网络带宽要求</span><span class="sxs-lookup"><span data-stu-id="9fec5-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="9fec5-215">VbSS 带宽为：</span><span class="sxs-lookup"><span data-stu-id="9fec5-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="9fec5-216">**视频编解码器**</span><span class="sxs-lookup"><span data-stu-id="9fec5-216">**Video codec**</span></span>|<span data-ttu-id="9fec5-217">**分辨率和纵横比**</span><span class="sxs-lookup"><span data-stu-id="9fec5-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="9fec5-218">**最大视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="9fec5-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="9fec5-219">**最小视频负载比特率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="9fec5-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fec5-220">H.264</span><span class="sxs-lookup"><span data-stu-id="9fec5-220">H.264</span></span>  <br/> |<span data-ttu-id="9fec5-221">1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="9fec5-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="9fec5-222">（纵横比取决于共享者的显示器分辨率，并且不会始终为 16:9）</span><span class="sxs-lookup"><span data-stu-id="9fec5-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="9fec5-223">4000</span><span class="sxs-lookup"><span data-stu-id="9fec5-223">4000</span></span>  <br/> |<span data-ttu-id="9fec5-224">1500</span><span class="sxs-lookup"><span data-stu-id="9fec5-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="9fec5-225">客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="9fec5-225">Clients and servers support</span></span>

<span data-ttu-id="9fec5-226">基于视频的屏幕共享需要 Skype for business Server 2015 CU3 或更高版本，以及适用于 Skype for business 和[会议支持](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)的[移动客户端功能比较](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)中列出的支持客户端的当前版本。</span><span class="sxs-lookup"><span data-stu-id="9fec5-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="9fec5-227">在某些情况下，屏幕共享将转换为 RDP，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9fec5-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="9fec5-228">如果你的帐户托管在 ASMCU 不满足支持 VbSS 的最低内部版本的环境中。</span><span class="sxs-lookup"><span data-stu-id="9fec5-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="9fec5-229">如果使用较早版本的 Skype for Business 客户端的人员加入你的会话，例如任何使用低于16.0.6330.1000、Skype for Business 会议室系统设备或 Skype for Business 移动应用的任何 Windows 客户端版本的用户。</span><span class="sxs-lookup"><span data-stu-id="9fec5-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="9fec5-230">如果用户从 Skype for Business Web 应用共享。</span><span class="sxs-lookup"><span data-stu-id="9fec5-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="9fec5-231">如果有人使用的是 Mac 版 Skype for business，而不是托管在 Skype for business Online 或 Skype for business Server 2015 上（使用7月、2018累积更新（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="9fec5-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="9fec5-232">如果某人启动了任何程序/Windows 共享。</span><span class="sxs-lookup"><span data-stu-id="9fec5-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="9fec5-233">如果有人开始录制会话。</span><span class="sxs-lookup"><span data-stu-id="9fec5-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="9fec5-234">如果某人在会话期间调用远程屏幕控制。</span><span class="sxs-lookup"><span data-stu-id="9fec5-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="9fec5-235">包含 250 个以上的参与者的会议（当前不支持 VbSS）。</span><span class="sxs-lookup"><span data-stu-id="9fec5-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="9fec5-p110">请注意，会话切换到 RDP 后，将不会切换回 VbSS。另外，从 VbSS 进行切换应为无缝操作，并且希望在大多数情况下不容易被检测到。</span><span class="sxs-lookup"><span data-stu-id="9fec5-p110">Be aware that once the session transitions to RDP it will not transition back to VbSS. Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9fec5-238">在 Skype for Business 屏幕共享中，不支持阻止或尝试阻止、从 VbSS 切换到 RDP。</span><span class="sxs-lookup"><span data-stu-id="9fec5-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="9fec5-239">启用、禁用和配置 VbSS</span><span class="sxs-lookup"><span data-stu-id="9fec5-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="9fec5-240">好的是，一旦您安装了 Skype for Business Server 2015 累积更新3（CU3）或更高版本后，默认情况下，所有用户都将启用1到1和多方 VbSS。</span><span class="sxs-lookup"><span data-stu-id="9fec5-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="9fec5-241">如果你有理由不为所有用户启用此功能，这对你来说可能有问题。</span><span class="sxs-lookup"><span data-stu-id="9fec5-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="9fec5-242">在这种情况下，你可以使用这些步骤禁用用户（然后执行启用用户步骤）：</span><span class="sxs-lookup"><span data-stu-id="9fec5-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="9fec5-243">如何禁止用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="9fec5-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="9fec5-244">你可以通过在 Skype for Business 管理控制台中运行此 cmdlet 来分配不允许 VbSS 使用 VbSS 的用户策略（使用你为其执行此操作的策略替换 [PolicyName]）：</span><span class="sxs-lookup"><span data-stu-id="9fec5-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="9fec5-245">你还可以更新全局会议策略，这会影响所有未分配策略的用户：</span><span class="sxs-lookup"><span data-stu-id="9fec5-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="9fec5-246">有关此命令的详细信息，请参阅[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9fec5-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="9fec5-247">如果需要完全关闭 VbSS，你可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9fec5-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="9fec5-248">有关此命令的详细信息，请参阅[Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9fec5-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="9fec5-249">在多方 Skype for business 会议中，所有客户终结点都将遵守会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="9fec5-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="9fec5-250">如何允许用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="9fec5-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="9fec5-251">你可以通过在 Skype for Business 管理控制台中运行此 cmdlet 来分配特定的用户策略，从而允许 VbSS 使用 VbSS 的任何用户（使用你执行此操作的策略替换 [PolicyName]）：</span><span class="sxs-lookup"><span data-stu-id="9fec5-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="9fec5-252">你还可以更新全局会议策略，这会影响所有未分配策略的用户：</span><span class="sxs-lookup"><span data-stu-id="9fec5-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="9fec5-253">有关此命令的详细信息，请参阅[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9fec5-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="9fec5-254">如果需要在关闭 VbSS 后将其重新打开（默认情况下处于打开状态），你可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9fec5-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="9fec5-255">有关此命令的详细信息，请参阅[Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9fec5-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="9fec5-256">在多方 Skype for business 会议中，所有客户端终结点将遵循会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="9fec5-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9fec5-257">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fec5-257">See also</span></span>

[<span data-ttu-id="9fec5-258">Skype for Business Server 2015 累积更新 KB3061064</span><span class="sxs-lookup"><span data-stu-id="9fec5-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[<span data-ttu-id="9fec5-259">基于视频的屏幕共享（VBSS）在 Skype for Business Server 2015 中可用</span><span class="sxs-lookup"><span data-stu-id="9fec5-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/en-us/kb/3170163)
