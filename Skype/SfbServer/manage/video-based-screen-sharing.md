---
title: Skype for business Server 的基于视频的屏幕共享
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
description: Skype for Business Server 规划和配置信息，用于基于视频的屏幕共享（VbSS）
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009565"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="5f0f1-103">Skype for business Server 的基于视频的屏幕共享</span><span class="sxs-lookup"><span data-stu-id="5f0f1-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="5f0f1-104">Skype For business Server 2015 中基于视频的屏幕共享（VbSS）现在可供下载： [skype For Business server 2015 累积更新 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span></span> <span data-ttu-id="5f0f1-105">VbSS 包含在 Skype for Business Server 2019 中。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="5f0f1-106">基于视频的屏幕共享（或 VbSS）在 Lync 屏幕共享中增长。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="5f0f1-107">VbSS 与传统屏幕共享的区别与所使用的基本协议以及它们的 excel 的区别相同。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="5f0f1-108">屏幕共享使用远程桌面协议（RDP），这在用户计算机之间创建数千个1到1会话时非常有用。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="5f0f1-109">较新的技术 VbSS 将使用用户数据报协议（UDP）。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="5f0f1-110">Skype for Business Server 希望改进人员的1到1，以及其一对多（多方）对话和会议体验。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="5f0f1-111">VbSS 使用媒体平台（依赖 UDP 作为基础协议），目的是改进视频启动时间、观看内容的质量（尤其是您正在观看的内容是快速移动的）以及整体的可靠性。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="5f0f1-112">改进屏幕共享的目标的一部分是在 VbSS 和 RDP 发生时尽可能无缝地进行转换。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="5f0f1-113">由于 VbSS 是对适用于 Skype for business Server 的屏幕共享中使用的基础技术的更新，因此如果您在网络流量中查看 SIP 详细信息，或者您正在共享的内容，则可能很难检测到您要利用的技术。为快速移动或三维。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="5f0f1-114">例如，如果您的工作场所有大量旧版客户端，则 RDP 仍可用作您的会议和对话的故障安全。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="5f0f1-115">Skype for Business Server 使用内部逻辑决定在客户端连接时要应用的两种方法（VbSS 或传统屏幕共享）中的哪一种。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="5f0f1-116">在对 VbSS 的情况下，RDP 可以和将替换为，以便您的观看体验不会中断。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="5f0f1-117">计划</span><span class="sxs-lookup"><span data-stu-id="5f0f1-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="5f0f1-118">VbSS 的优点和缺点</span><span class="sxs-lookup"><span data-stu-id="5f0f1-118">VbSS pros and cons</span></span>

<span data-ttu-id="5f0f1-119">切换到 VbSS 旨在实现三项关键改进：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="5f0f1-120">进行屏幕共享（最长为5%）与 RDP 相比，单独进行更可靠的比较。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="5f0f1-121">使会话设置和视频体验与 RDP 的比较速度更快（安装时间减半，每秒帧数提高6:1）。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="5f0f1-122">在低带宽条件下，即使在共享高运动内容（如三维图形）时，工作原理也会更好。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="5f0f1-123">请记住，这些数字依赖于运行状况和正确的网络性能调整，如果客户端在移动设备上，则可能会涉及自己外部的网络。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="5f0f1-124">此外，您还应注意，共享内容的一些保真度/脆已得到可靠性、速度和效率的提高。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-124">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency.</span></span> <span data-ttu-id="5f0f1-125">在大多数情况下，不会对用户很容易看到这一点。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-125">In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="5f0f1-126">端口和协议</span><span class="sxs-lookup"><span data-stu-id="5f0f1-126">Ports and protocols</span></span>

<span data-ttu-id="5f0f1-127">**所需的服务器端口**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-127">**Required server ports**</span></span>

|<span data-ttu-id="5f0f1-128">**服务器角色**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-128">**Server role**</span></span>|<span data-ttu-id="5f0f1-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-129">**Service name**</span></span>|<span data-ttu-id="5f0f1-130">**端口或端口范围**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-130">**Port or port range**</span></span>|<span data-ttu-id="5f0f1-131">**协议**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-131">**Protocol**</span></span>|<span data-ttu-id="5f0f1-132">**注释**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f0f1-133">前端服务器</span><span class="sxs-lookup"><span data-stu-id="5f0f1-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="5f0f1-134">Skype for Business Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="5f0f1-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="5f0f1-135">5065</span><span class="sxs-lookup"><span data-stu-id="5f0f1-135">5065</span></span>  <br/> |<span data-ttu-id="5f0f1-136">TCP</span><span class="sxs-lookup"><span data-stu-id="5f0f1-136">TCP</span></span>  <br/> |<span data-ttu-id="5f0f1-137">用于应用程序共享的传入 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="5f0f1-138">前端服务器</span><span class="sxs-lookup"><span data-stu-id="5f0f1-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="5f0f1-139">Skype for Business Server 应用程序共享服务</span><span class="sxs-lookup"><span data-stu-id="5f0f1-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="5f0f1-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="5f0f1-140">49152-65535</span></span>  <br/> |<span data-ttu-id="5f0f1-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="5f0f1-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="5f0f1-142">用于应用程序共享的媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="5f0f1-143">**必需的客户端端口**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-143">**Required client ports**</span></span>

|<span data-ttu-id="5f0f1-144">**组件**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-144">**Component**</span></span>|<span data-ttu-id="5f0f1-145">**端口范围**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-145">**Port range**</span></span>|<span data-ttu-id="5f0f1-146">**协议**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-146">**Protocol**</span></span>|<span data-ttu-id="5f0f1-147">**注释**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f0f1-148">客户端</span><span class="sxs-lookup"><span data-stu-id="5f0f1-148">Clients</span></span>  <br/> |<span data-ttu-id="5f0f1-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="5f0f1-149">1024-65535</span></span>  <br/> |<span data-ttu-id="5f0f1-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="5f0f1-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="5f0f1-151">应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="5f0f1-152">如果为以下媒体端口启用了 QoS，同时还启用了 VbSS，则在包含桌面共享的会议过程中，在屏幕共享流量的下面以粗体显示的视频端口设置将使用。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5f0f1-153">这些设置是一种特殊情况，在实现这两种功能时，必须使用这些确切的设置。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="5f0f1-154">这将覆盖[针对 QoS 的文档](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)中的其他建议设置。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="5f0f1-155">对于应用程序共享，除了定义这些端口值之外，还需要在 QoS GPO 中指定 ASMCUSVC。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="5f0f1-156">**应用程序服务器 QoS/VbSS 必需设置**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="5f0f1-157">**Property**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-157">**Property**</span></span>|<span data-ttu-id="5f0f1-158">**端口值**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-158">**Port value**</span></span>|<span data-ttu-id="5f0f1-159">**协议**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f0f1-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="5f0f1-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="5f0f1-161">49152</span><span class="sxs-lookup"><span data-stu-id="5f0f1-161">49152</span></span>  <br/> |<span data-ttu-id="5f0f1-162">UDP</span><span class="sxs-lookup"><span data-stu-id="5f0f1-162">UDP</span></span>  <br/> |
|<span data-ttu-id="5f0f1-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="5f0f1-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="5f0f1-164">8348</span><span class="sxs-lookup"><span data-stu-id="5f0f1-164">8348</span></span>  <br/> |<span data-ttu-id="5f0f1-165">UDP</span><span class="sxs-lookup"><span data-stu-id="5f0f1-165">UDP</span></span>  <br/> |
|<span data-ttu-id="5f0f1-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="5f0f1-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-167">**57501**</span></span> <br/> |<span data-ttu-id="5f0f1-168">UDP</span><span class="sxs-lookup"><span data-stu-id="5f0f1-168">UDP</span></span>  <br/> |
|<span data-ttu-id="5f0f1-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="5f0f1-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-170">**8034**</span></span> <br/> |<span data-ttu-id="5f0f1-171">UDP</span><span class="sxs-lookup"><span data-stu-id="5f0f1-171">UDP</span></span>  <br/> |
|<span data-ttu-id="5f0f1-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="5f0f1-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="5f0f1-173">40803</span><span class="sxs-lookup"><span data-stu-id="5f0f1-173">40803</span></span>  <br/> |<span data-ttu-id="5f0f1-174">TCP</span><span class="sxs-lookup"><span data-stu-id="5f0f1-174">TCP</span></span>  <br/> |
|<span data-ttu-id="5f0f1-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="5f0f1-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="5f0f1-176">8348</span><span class="sxs-lookup"><span data-stu-id="5f0f1-176">8348</span></span>  <br/> |<span data-ttu-id="5f0f1-177">TCP</span><span class="sxs-lookup"><span data-stu-id="5f0f1-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="5f0f1-178">容量规划</span><span class="sxs-lookup"><span data-stu-id="5f0f1-178">Capacity planning</span></span>

<span data-ttu-id="5f0f1-179">每个运行 Skype for Business Server 2015 累积更新2（CU2）或更高版本的前端服务器都支持最高为375个参与者使用 RDP 进行屏幕共享（尽管每个会议仅有250）。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="5f0f1-180">当引入并使用 VbSS 时，此容量不会更改 CU3。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="5f0f1-181">在这种情况下，我们已在实验室中完成了性能和压力测试，还应考虑使用您自己的部署（当然，这取决于使用情况）的以下度量。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="5f0f1-182">假如</span><span class="sxs-lookup"><span data-stu-id="5f0f1-182">Assuming:</span></span>
  
- <span data-ttu-id="5f0f1-183">您在部署中使用的是 Skype for Business Server 2015 CU2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="5f0f1-184">Skype for Business Server 环境中的所有用户都具有高于1920x1080 的屏幕分辨率。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="5f0f1-185">在全容量（如上所述）中，每个前端服务器总共为375个屏幕共享参与者，尽管每个会议仅有250，但前端服务器可能会使用约1千兆个网卡的 ~ 89%。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="5f0f1-186">这是因为 Skype for Business Server CU2 （RDP）中的现有屏幕共享技术以演示者电脑的本机分辨率传输屏幕内容。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="5f0f1-187">因此，在中分解更高的屏幕分辨率时，您可能已遇到与 Skype for business Server 2015 CU2 的屏幕共享的网络瓶颈。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="5f0f1-188">若要缓解这一情况，可以通过以下一种或多种方法来获得帮助：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="5f0f1-189">将前端服务器从1千兆网卡升级到10千兆以太网卡。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="5f0f1-190">增加前端服务器的数量以实现负载平衡流量。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="5f0f1-191">通过将 cap 放在两个通道使用的最大带宽上，限制用于 VbSS 和 RDP 的带宽（比特率）。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="5f0f1-192">此表中的数字受单个网络和共享内容的影响。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-192">The numbers in this table are influenced by individual networks and by the content being shared.</span></span> <span data-ttu-id="5f0f1-193">请进行测试以建立网络或网络的基准。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-193">Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="5f0f1-194">**1080p 内容**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-194">**1080p Content**</span></span>|<span data-ttu-id="5f0f1-195">**RDP 平均**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-195">**RDP Average**</span></span>|<span data-ttu-id="5f0f1-196">**RDP 峰值**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-196">**RDP Peak**</span></span>|<span data-ttu-id="5f0f1-197">**VbSS 平均值**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-197">**VbSS Average**</span></span>|<span data-ttu-id="5f0f1-198">**VbSS 峰值**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f0f1-199">PPT</span><span class="sxs-lookup"><span data-stu-id="5f0f1-199">PPT</span></span>  <br/> |<span data-ttu-id="5f0f1-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-200">200kbps</span></span>  <br/> |<span data-ttu-id="5f0f1-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-201">12mbps</span></span>  <br/> |<span data-ttu-id="5f0f1-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-202">100kbps</span></span>  <br/> |<span data-ttu-id="5f0f1-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="5f0f1-204">CAD</span><span class="sxs-lookup"><span data-stu-id="5f0f1-204">CAD</span></span>  <br/> |<span data-ttu-id="5f0f1-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-205">3mbps</span></span>  <br/> |<span data-ttu-id="5f0f1-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-206">7mbps</span></span>  <br/> |<span data-ttu-id="5f0f1-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-207">1mbps</span></span>  <br/> |<span data-ttu-id="5f0f1-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="5f0f1-209">视频</span><span class="sxs-lookup"><span data-stu-id="5f0f1-209">Video</span></span>  <br/> |<span data-ttu-id="5f0f1-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-210">5mbps</span></span>  <br/> |<span data-ttu-id="5f0f1-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-211">7mbps</span></span>  <br/> |<span data-ttu-id="5f0f1-212">1.3 mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="5f0f1-213">2.2 mbps</span><span class="sxs-lookup"><span data-stu-id="5f0f1-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="5f0f1-214">媒体流量的网络带宽要求</span><span class="sxs-lookup"><span data-stu-id="5f0f1-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="5f0f1-215">VbSS 带宽为：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="5f0f1-216">**视频编解码器**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-216">**Video codec**</span></span>|<span data-ttu-id="5f0f1-217">**分辨率和纵横比**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="5f0f1-218">**最大视频负载比特率（Kbps）**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="5f0f1-219">**最小视频负载比特率（Kbps）**</span><span class="sxs-lookup"><span data-stu-id="5f0f1-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f0f1-220">H-p</span><span class="sxs-lookup"><span data-stu-id="5f0f1-220">H.264</span></span>  <br/> |<span data-ttu-id="5f0f1-221">1920x1080 （16:9）</span><span class="sxs-lookup"><span data-stu-id="5f0f1-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="5f0f1-222">（纵横比取决于共享者的监视器分辨率，而不是始终为16:9）</span><span class="sxs-lookup"><span data-stu-id="5f0f1-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="5f0f1-223">4000</span><span class="sxs-lookup"><span data-stu-id="5f0f1-223">4000</span></span>  <br/> |<span data-ttu-id="5f0f1-224">1500</span><span class="sxs-lookup"><span data-stu-id="5f0f1-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="5f0f1-225">客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="5f0f1-225">Clients and servers support</span></span>

<span data-ttu-id="5f0f1-226">基于视频的屏幕共享需要 Skype for Business Server 2015 CU3 或更高版本，以及在[适用于 Skype For business 和会议支持的移动客户端功能比较](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)中[](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)列出的支持客户端的当前版本。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="5f0f1-227">在某些情况下，屏幕共享将转换为 RDP，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="5f0f1-228">如果您的帐户托管在 ASMCU 不符合支持 VbSS 的最低版本的环境中。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="5f0f1-229">如果使用较旧版本 Skype for business 客户端的用户加入了您的会话，例如，任何人使用的 Windows 客户端版本低于16.0.6330.1000、Skype for Business 会议室系统设备或 Skype for Business 移动应用。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="5f0f1-230">如果用户是从 Skype for Business Web 应用程序共享的。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="5f0f1-231">如果有人在 Mac 上使用 Skype for business，而不是托管在 Skype for Business Online 或 Skype for business Server 2015 （使用7月、2018累积更新（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="5f0f1-232">如果某人启动了任何程序/Windows 共享。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="5f0f1-233">如果有人开始记录会话。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="5f0f1-234">如果有人在会话期间调用远程屏幕控制。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="5f0f1-235">参与者超过250个（当前不支持 VbSS）的会议。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="5f0f1-236">请注意，一旦会话转换为 RDP，它就不会转换回 VbSS。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-236">Be aware that once the session transitions to RDP it will not transition back to VbSS.</span></span> <span data-ttu-id="5f0f1-237">同样，从 VbSS 进行的转换也是无缝的，因此，在大多数情况下，不能很容易地检测到，并且希望这样做。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-237">Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5f0f1-238">不支持在 Skype for Business 屏幕共享中阻止或尝试阻止、从 VbSS 转换为 RDP。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="5f0f1-239">启用、禁用和配置 VbSS</span><span class="sxs-lookup"><span data-stu-id="5f0f1-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="5f0f1-240">很棒的是，一旦您安装了 Skype for Business Server 2015 累积更新3（CU3）或更高版本，默认情况下将为所有用户启用1到1和多方 VbSS。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="5f0f1-241">如果你有理由对你的所有用户启用此功能，则这可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="5f0f1-242">在这种情况下，您可以使用以下步骤禁用用户（"启用用户" 步骤将遵循）：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="5f0f1-243">如何禁止用户使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="5f0f1-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="5f0f1-244">通过在 Skype for Business 管理控制台中运行此 cmdlet （将 [PolicyName] 替换为您要执行此操作的策略），您可以将不允许 VbSS 的用户策略分配给任何不应使用 VbSS 的用户：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="5f0f1-245">您还可以更新全局会议策略，这将影响未分配策略的所有用户：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="5f0f1-246">有关此命令的详细信息，请参阅[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="5f0f1-247">如果需要完全关闭 VbSS，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="5f0f1-248">有关此命令的详细信息，请参阅[set-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="5f0f1-249">在多方 Skype for Business 会议中，所有客户端终结点都将遵循会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="5f0f1-250">如何使用户能够使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="5f0f1-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="5f0f1-251">您可以通过在 Skype for Business 管理控制台中运行此 cmdlet （将 [PolicyName] 替换为您要执行此操作的策略），为需要使用 VbSS 的任何用户分配特定的用户策略（将 [] 替换为）：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="5f0f1-252">您还可以更新全局会议策略，这将影响未分配策略的所有用户：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="5f0f1-253">有关此命令的详细信息，请参阅[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="5f0f1-254">如果您需要在 VbSS 关闭后重新打开它（默认情况下处于启用状态），则可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5f0f1-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="5f0f1-255">有关此命令的详细信息，请参阅[set-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="5f0f1-256">在多方 Skype for Business 会议中，所有客户端终结点都将遵循会议组织者的策略设置。</span><span class="sxs-lookup"><span data-stu-id="5f0f1-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5f0f1-257">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f0f1-257">See also</span></span>

[<span data-ttu-id="5f0f1-258">Skype for Business Server 2015 累积更新 KB3061064</span><span class="sxs-lookup"><span data-stu-id="5f0f1-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/download/details.aspx?id=47690)
  
[<span data-ttu-id="5f0f1-259">基于视频的屏幕共享（VBSS）在 Skype for Business Server 2015 中可用</span><span class="sxs-lookup"><span data-stu-id="5f0f1-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/kb/3170163)
