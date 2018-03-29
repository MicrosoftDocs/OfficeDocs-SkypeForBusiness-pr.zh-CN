---
title: 在 Skype for Business Server 2015 中规划视频互操作服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要： 在规划将 Skype 与第三方电话会议设备集成的业务服务器 2015年时仔细阅读本主题。
ms.openlocfilehash: 1a0ae30cf383f9f05cc8c37ef2c1ba7b7c76cfb8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="63387-103">在 Skype for Business Server 2015 中规划视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="63387-103">Plan for Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="63387-104">**摘要：**在规划与第三方电话会议设备集成的业务服务器 2015年的 Skype 时仔细阅读本主题。</span><span class="sxs-lookup"><span data-stu-id="63387-104">**Summary:** Review this topic while planning to integrate Skype for Business Server 2015 with third-party teleconferencing devices.</span></span>
  
<span data-ttu-id="63387-105">Skype 业务服务器，现在可以与某些第三方 VTC （视频电话会议系统） 解决方案进行集成。</span><span class="sxs-lookup"><span data-stu-id="63387-105">Skype for Business Server now allows you to integrate with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="63387-106">使此视频会议的互操作性的新服务器角色是视频互操作服务器 (VIS)，这当前实现作为独立服务器角色仅用于内部部署安装。</span><span class="sxs-lookup"><span data-stu-id="63387-106">The new server role that enables this video conferencing interoperability is the Video Interop Server (VIS), which is currently implemented as a standalone server role available only for on-premises installations.</span></span> <span data-ttu-id="63387-107">VIS 作为第三方电话会议系统和业务服务器部署 Skype 之间的媒介。</span><span class="sxs-lookup"><span data-stu-id="63387-107">A VIS acts as an intermediary between a third party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="63387-108">对于此版本，VIS 着重实现了与 Cisco/Tandberg 视频系统之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="63387-108">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span> <span data-ttu-id="63387-109">查看这篇文章，以确定是否适用于业务服务器安装在您的 Skype 使用此功能。</span><span class="sxs-lookup"><span data-stu-id="63387-109">Review this article to determine whether to use this feature in your Skype for Business Server installation.</span></span>
  
## <a name="device-interoperability"></a><span data-ttu-id="63387-110">设备互操作性</span><span class="sxs-lookup"><span data-stu-id="63387-110">Device interoperability</span></span>

<span data-ttu-id="63387-111">在 Cisco VTC 向 CUCM 版本 10.5 注册，并且在 CUCM 与 VIS 之间设置了 TCP SIP 中继的情况下，互操作性经过测试，并得到支持。</span><span class="sxs-lookup"><span data-stu-id="63387-111">Interoperation is tested and supported with Cisco VTCs registering with CUCM version 10.5 and TCP SIP trunks set up between CUCM and the VIS.</span></span>
  
<span data-ttu-id="63387-112">当前支持的 VTC 包括：</span><span class="sxs-lookup"><span data-stu-id="63387-112">The currently supported VTCs are:</span></span>
  
- <span data-ttu-id="63387-113">Cisco C40</span><span class="sxs-lookup"><span data-stu-id="63387-113">Cisco C40</span></span>
    
- <span data-ttu-id="63387-114">Cisco C60</span><span class="sxs-lookup"><span data-stu-id="63387-114">Cisco C60</span></span>
    
- <span data-ttu-id="63387-115">Cisco C90</span><span class="sxs-lookup"><span data-stu-id="63387-115">Cisco C90</span></span>
    
- <span data-ttu-id="63387-116">Cisco MX200</span><span class="sxs-lookup"><span data-stu-id="63387-116">Cisco MX200</span></span>
    
- <span data-ttu-id="63387-117">Cisco MX300</span><span class="sxs-lookup"><span data-stu-id="63387-117">Cisco MX300</span></span>
    
- <span data-ttu-id="63387-118">Cisco DX80</span><span class="sxs-lookup"><span data-stu-id="63387-118">Cisco DX80</span></span>
    
- <span data-ttu-id="63387-119">Cisco EX60</span><span class="sxs-lookup"><span data-stu-id="63387-119">Cisco EX60</span></span>
    
- <span data-ttu-id="63387-120">Cisco EX90</span><span class="sxs-lookup"><span data-stu-id="63387-120">Cisco EX90</span></span>
    
- <span data-ttu-id="63387-121">Cisco SX20</span><span class="sxs-lookup"><span data-stu-id="63387-121">Cisco SX20</span></span>
    
> [!NOTE]
>  <span data-ttu-id="63387-122">Cisco 软件版本 TC7.0.0 或以上需要在集成业务服务器以达到预期效果的 Skype 与这些系统上。</span><span class="sxs-lookup"><span data-stu-id="63387-122">Cisco software release TC7.0.0 or above is required on these systems for integration with Skype for Business Server to work as expected.</span></span>
  
## <a name="sip-trunks"></a><span data-ttu-id="63387-123">SIP 中继</span><span class="sxs-lookup"><span data-stu-id="63387-123">SIP trunks</span></span>

<span data-ttu-id="63387-124">在 SIP 中继模式下，VTCs 继续注册现有 Cisco 基础结构 — 例如，Cisco 调用管理器 (CUCM) 的视频互操作服务器功能。</span><span class="sxs-lookup"><span data-stu-id="63387-124">The Video Interop Server functions in SIP trunk mode, where the VTCs continue to register with the existing Cisco infrastructure - for example, Cisco Call Manager (CUCM).</span></span> <span data-ttu-id="63387-125">在 CUCM 和 VIS 之间定义了视频 SIP 中继，从而可以在两个系统之间路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-125">A video SIP trunk is defined between CUCM and the VIS so that calls can be routed between the two systems.</span></span> <span data-ttu-id="63387-126">仅支持通过 SIP 中继从 VTC 向 VIS 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-126">Only calls over the SIP trunk from the VTC to the VIS are supported.</span></span> <span data-ttu-id="63387-127">因此，VTCs 可以拨入业务会议的 Skype （拨与调用自动助理关联的号码），但不能拖放到会议。</span><span class="sxs-lookup"><span data-stu-id="63387-127">Thus, VTCs can dial into a Skype for Business conference (by dialing the phone number associated with the Call Automated Attendant), but cannot be dragged and dropped into the conference.</span></span>
  
![SfB 中的 VIS 图表](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a><span data-ttu-id="63387-129">功能</span><span class="sxs-lookup"><span data-stu-id="63387-129">Features</span></span>

<span data-ttu-id="63387-130">此服务器角色提供：</span><span class="sxs-lookup"><span data-stu-id="63387-130">This server role provides:</span></span>
  
- <span data-ttu-id="63387-131">使用第三方视频系统和 Skype 业务服务器部署的 H.264 格式之间的转换。</span><span class="sxs-lookup"><span data-stu-id="63387-131">Conversion between the H.264 formats used by 3rd party video systems and the Skype for Business Server deployment.</span></span>
    
- <span data-ttu-id="63387-132">在给定解析一个视频流从转换 VTC 到供使用 Skype 业务服务器部署不同分辨率的多个 simulcast 流。</span><span class="sxs-lookup"><span data-stu-id="63387-132">Conversion of a single video stream at a given resolution from a VTC into multiple simulcast streams of different resolutions for use in the Skype for Business Server deployment.</span></span> <span data-ttu-id="63387-133">这些流可以发送到 AVMCU 然后到 Skype 业务服务器终结点和其它已请求在不同分辨率的视频系统。</span><span class="sxs-lookup"><span data-stu-id="63387-133">These streams can be sent to the AVMCU and then to Skype for Business Server endpoints and other video systems that have requested different resolutions.</span></span> <span data-ttu-id="63387-134">第三方视频系统所涉及的业务 A 的 Skype 时也将使用此转换 / V 会议呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-134">This conversion is also used when the third party video system is involved in a Skype for Business A/V conference call.</span></span> <span data-ttu-id="63387-135">一旦转码达到特定的 VIS 服务器中，不同的分辨率为任何以下请求只能收到的最低分辨率的流。</span><span class="sxs-lookup"><span data-stu-id="63387-135">Once the transcoding limit is reached in a particular VIS server, any following requests for different resolutions will only receive a stream with the lowest resolution.</span></span> 
    
- <span data-ttu-id="63387-136">支持视频的 CUCM 网关和 Skype 之间的 SIP 中继业务服务器视频互操作服务器;VTCs 继续注册与 Cisco 网关，并发起向业务部署网关通过 Skype 呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-136">Support for a video SIP trunk between the CUCM gateway and a Skype for Business Server Video Interop Server; VTCs continue to register with the Cisco gateway, and initiate calls to the Skype for Business deployment through the gateway.</span></span> <span data-ttu-id="63387-137">调用从路由的网关的 Skype 业务视频互操作服务器通过视频的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="63387-137">Calls are routed from the gateway to the Skype for Business Video Interop Server over the video SIP trunk.</span></span>
    
- <span data-ttu-id="63387-138">支持会议室中的用户使用支持的视频系统从该系统拨号加入开启或关闭的会议。</span><span class="sxs-lookup"><span data-stu-id="63387-138">Support for a user in a conference room with a supported video system to dial from that system to join an open or closed conference.</span></span> <span data-ttu-id="63387-139">此呼叫将遍历视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="63387-139">This call will traverse the video SIP trunk.</span></span>
    
- <span data-ttu-id="63387-140">业务客户端调用 Skype 在会议室使用受支持的视频系统用户的支持。</span><span class="sxs-lookup"><span data-stu-id="63387-140">Support for a user in a conference room with a supported video system to call a Skype for Business client.</span></span> <span data-ttu-id="63387-141">此呼叫将遍历视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="63387-141">The call will traverse the SIP trunk.</span></span>
    
- <span data-ttu-id="63387-142">中端呼叫控制从业务服务器端为 Skype 或受支持的 VTC 系统的点到点和多点包括静音/未经 mute 音频、 暂停/恢复视频、 锁视频和暂停/取消暂停呼叫的电话支持。</span><span class="sxs-lookup"><span data-stu-id="63387-142">Support for mid-call control from the Skype for Business Server side or from the supported VTC system for both point to point and multipoint calls including mute/un-mute audio, pause/resume video, lock video, and hold/un-hold call.</span></span>
    
## <a name="known-limitations"></a><span data-ttu-id="63387-143">已知限制</span><span class="sxs-lookup"><span data-stu-id="63387-143">Known limitations</span></span>

<span data-ttu-id="63387-144">此服务器角色存在以下限制：</span><span class="sxs-lookup"><span data-stu-id="63387-144">This server role has the following limitations:</span></span>
  
- <span data-ttu-id="63387-145">不支持通过视频的 SIP 中继 VTCs 从业务部署 Skype 新调用。</span><span class="sxs-lookup"><span data-stu-id="63387-145">New calls from the Skype for Business deployment to the VTCs over the video SIP trunk are not supported.</span></span> <span data-ttu-id="63387-146">.</span><span class="sxs-lookup"><span data-stu-id="63387-146"></span></span> <span data-ttu-id="63387-147">这意味着只有新从 VTCs 到调用业务部署 Skype 支持视频的 SIP 中继段。</span><span class="sxs-lookup"><span data-stu-id="63387-147">This means that only new calls from the VTCs into the Skype for Business deployment are supported over the video SIP trunk.</span></span> <span data-ttu-id="63387-148">有关受支持的视频系统存在不能通过向 VIS.视频的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="63387-148">Presence for the supported video system will not be available over the video SIP trunk to the VIS.</span></span> 
    
- <span data-ttu-id="63387-149">对于视频 SIP 中继模式，仅支持独立的 VIS 池。</span><span class="sxs-lookup"><span data-stu-id="63387-149">Only a standalone VIS pool will be supported for video SIP trunk mode.</span></span>
    
-  <span data-ttu-id="63387-150">对于通过视频 SIP 中继在 VTC 和 VIS 之间进行的通信，支持 TLS + SRTP 或 TCP + RTP。</span><span class="sxs-lookup"><span data-stu-id="63387-150">TLS + SRTP or TCP + RTP will be supported for communications between the VTC and VIS over the video SIP trunk.</span></span>
    
- <span data-ttu-id="63387-151">不支持应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="63387-151">Application sharing is not supported.</span></span> <span data-ttu-id="63387-152">在会议室中的业务用户的 Skype 需要加入 Skype 业务大会 （通过例如膝上型电脑） 和应用程序共享一个免费在会议室与 VTC 无关显示器上的屏幕显示。</span><span class="sxs-lookup"><span data-stu-id="63387-152">A Skype for Business user in the conference room needs to join the Skype for Business conference (via a laptop for example) and display the app sharing screens on one of the free monitors in the conference room not associated with the VTC.</span></span>
    
- <span data-ttu-id="63387-153">不支持 VTC 通过 VIS 加入联盟会议。</span><span class="sxs-lookup"><span data-stu-id="63387-153">The ability for a VTC to join a federated meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="63387-154">不支持 VTC 通过 VIS 加入联机会议。</span><span class="sxs-lookup"><span data-stu-id="63387-154">The ability for a VTC to join an online meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="63387-155">不支持通过 VIS 从 VTC 向 PSTN 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-155">Calls from a VTC to the PSTN via VIS are not supported.</span></span>
    
- <span data-ttu-id="63387-156">不支持通过 VIS 从 PSTN 向 VTC 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-156">Calls from the PSTN to a VTC via VIS are not supported.</span></span>
    
## <a name="resiliency-mechanisms"></a><span data-ttu-id="63387-157">复原机制</span><span class="sxs-lookup"><span data-stu-id="63387-157">Resiliency mechanisms</span></span>
<span data-ttu-id="63387-158"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-158"></span></span>

<span data-ttu-id="63387-159">VIS 支持通过视频 SIP 中继传递的、来自 CUCM 的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-159">The VIS supports incoming calls from a CUCM that are carried over a video SIP trunk.</span></span> <span data-ttu-id="63387-160">可能会丢失上游或下游连接，因此，要实现强大的复原能力，请考虑两种可能性：</span><span class="sxs-lookup"><span data-stu-id="63387-160">It's possible to lose connectivity either upstream or downstream, so for robust resiliency consider both possibilities:</span></span>
  
1. <span data-ttu-id="63387-161">**VIS 池故障转移**如果视频网关指向主 VIS 池出现故障，恢复是可能如果视频网关已于两个 （或更多） VIS 池定义中继。</span><span class="sxs-lookup"><span data-stu-id="63387-161">**VIS Pool Failover** If the main VIS pool that the video gateway points to is down, recovery is possible if the video gateway has defined trunks to two (or more) VIS pools.</span></span> <span data-ttu-id="63387-162">如果视频网关确定不能打电话的主要 VIS 池，它只是路由到辅助 VIS 池调用。</span><span class="sxs-lookup"><span data-stu-id="63387-162">If the video gateway determines it cannot make calls to the primary VIS pool, it simply routes the calls to a secondary VIS pool.</span></span>
    
     ![VIS 池故障转移图](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    <span data-ttu-id="63387-164">特定的 VIS 池可以具有中继到多个网关，但正常情况下特定网关不能具有中继到 VIS 的多个池，因此一轮必须要做，以支持这种故障转移： 它解析为同一视频网关的 IP 地址的 DNS 中定义 2 FDQNs。</span><span class="sxs-lookup"><span data-stu-id="63387-164">A particular VIS pool can have trunks to multiple gateways, but normally a particular gateway can't have trunks to multiple VIS pools, so a trick needs to be done to support this failover: Define 2 FDQNs in DNS which resolve to the same IP address of a video gateway.</span></span> <span data-ttu-id="63387-165">为其中每个视频网关具有到其他的 VIS 池，主干拓扑文档中的不同视频网关表示每个 FQDN 和恢复现在已成为可能。</span><span class="sxs-lookup"><span data-stu-id="63387-165">Represent each FQDN as a separate video gateway in the Topology Document where each video gateway has a trunk to a different VIS pool, and recovery is now possible.</span></span> <span data-ttu-id="63387-166">（如果使用 TLS，则多个名称需要视频网关证书的 SAN 中。）</span><span class="sxs-lookup"><span data-stu-id="63387-166">(If TLS is used, the multiple names will need to be in the SAN of the video gateway certificate.)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="63387-167">VIS 仅允许传入呼叫来自拓扑文档中配置的网关。</span><span class="sxs-lookup"><span data-stu-id="63387-167">VIS only allows incoming calls from gateways configured in the Topology Document.</span></span> 
  
2. <span data-ttu-id="63387-168">**前端故障转移**如果 VIS 池接收来自 CUCM 的调用，但不能达到其主要的下一个跃点注册或前端池，调用路由到前端备份池。</span><span class="sxs-lookup"><span data-stu-id="63387-168">**Front End failover** If a VIS pool receives a call from CUCM but cannot reach its primary next-hop Registrar or Front End pool, calls are routed to a backup Front End pool.</span></span>
    
     ![前端故障转移图表](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    <span data-ttu-id="63387-170">VIS 将跟踪的其主要的前端池和其备份 （拓扑文档中注册服务的备份设置中找到的设置） 的前端池的状态。</span><span class="sxs-lookup"><span data-stu-id="63387-170">The VIS will keep track of the status of its primary Front End pool and its backup Front End pool (the setting is found in the backup setting for the Registrar service in the Topology Document).</span></span> <span data-ttu-id="63387-171">选项轮询一次一分钟的时间向两个池，和如果有五个连续失败 VIS 假定特定的前端池出现故障。</span><span class="sxs-lookup"><span data-stu-id="63387-171">It sends Options polls once a minute to both pools, and if there are five consecutive failures the VIS assumes that a particular Front End pool is down.</span></span> <span data-ttu-id="63387-172">如果主前端池标记为向下并且还没有可用的配置备份 VIS 新呼叫从发送到前端备份池的网关。</span><span class="sxs-lookup"><span data-stu-id="63387-172">If the primary Front End pool is marked as down and there is an available configured backup the VIS sends new calls from the gateway to the backup Front End pool.</span></span> <span data-ttu-id="63387-173">一旦主前端池恢复后，VIS 将恢复主前端池用于新的呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-173">Once the primary Front End pool comes back, the VIS will resume using the primary Front End pool for new calls.</span></span>
    
    <span data-ttu-id="63387-174">VIS 还会为来自视频 SIP 中继的呼叫设置 10 秒计时。</span><span class="sxs-lookup"><span data-stu-id="63387-174">The VIS will also implement a 10 second timer for calls from the video SIP trunk.</span></span> <span data-ttu-id="63387-175">如果主下一中继站前端池用于池没有应答 （包括 100 尝试） 某些 SIP 消息在此计时器值，调用 s 的备份下一中继站代理发送给它的邀请到来自视频的 SIP 中继和主要的下一个跃点前结束呼叫如果配置，试 hould。</span><span class="sxs-lookup"><span data-stu-id="63387-175">If the primary next-hop Front End pool was used for a call from the video SIP trunk, and the primary next-hop Front End pool did not answer with some SIP message (including 100 Trying) to the Invite sent to it within this timer value, the backup next-hop proxy for the call should be tried if configured.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="63387-176">如果备份的下一跃点第一次尝试，将不会接下来尝试主。</span><span class="sxs-lookup"><span data-stu-id="63387-176">If the backup next hop was tried first, the primary will not be tried next.</span></span> 
  
    <span data-ttu-id="63387-177">管理员还可以使用 Windows PowerShell 故障切换命令强制 VIS 使用备份前端池，例如，当主前端池上执行维护。</span><span class="sxs-lookup"><span data-stu-id="63387-177">The admin could also use the Windows PowerShell failover command to force VIS to use the backup Front End pool, for example, when maintenance has to be performed on the primary Front End pool.</span></span>
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a><span data-ttu-id="63387-178">指向同一网关对等方的语音和视频中继的共存</span><span class="sxs-lookup"><span data-stu-id="63387-178">Co-existence of Voice and Video Trunks to the Same Gateway Peer</span></span>
<span data-ttu-id="63387-179"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-179"></span></span>

<span data-ttu-id="63387-180">对于语音和视频的 SIP 中继具有的业务服务器支持 Skype 使用相同的网关等。</span><span class="sxs-lookup"><span data-stu-id="63387-180">Skype for Business Server supports having voice and video SIP trunks use the same gateway peer.</span></span> <span data-ttu-id="63387-181">因此，同一 CUCM 部署可能具有指向中介服务器的语音 SIP 中继和指向 VIS 的视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="63387-181">So the same CUCM deployment could have voice SIP trunks to the Mediation Server and video SIP trunks to VIS.</span></span>
  
- <span data-ttu-id="63387-182">需要在语音 SIP 中继的拓扑文档中使用特定 FQDN 定义 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="63387-182">A PSTN Gateway will need to be defined with a particular FQDN in the Topology Document for the voice SIP trunks.</span></span>
    
- <span data-ttu-id="63387-183">PSTN 网关的对等方将为中介服务器。</span><span class="sxs-lookup"><span data-stu-id="63387-183">The peer to the PSTN Gateway will be the Mediation Server.</span></span>
    
- <span data-ttu-id="63387-184">如有必要可定义多个语音中继，范围从单个 PSTN 网关涵盖到多个中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="63387-184">Multiple voice trunks can be defines spanning from a PSTN Gateway to multiple Mediation Server pools if necessary.</span></span>
    
- <span data-ttu-id="63387-185">需要在视频 SIP 中继的拓扑文档中定义视频网关并使用与 PSTN 网关相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="63387-185">A Video Gateway will need to be defined in the Topology Document for the video SIP trunk with the same FQDN as for the PSTN Gateway.</span></span>
    
- <span data-ttu-id="63387-186">视频网关的对等方将为 VIS。</span><span class="sxs-lookup"><span data-stu-id="63387-186">The peer to the Video Gateway will be VIS.</span></span>
    
- <span data-ttu-id="63387-187">可从视频网关到特定 VIS 池定义单个视频中继。</span><span class="sxs-lookup"><span data-stu-id="63387-187">A single video trunk can be defined from a Video Gateway to a particular VIS pool.</span></span>
    
- <span data-ttu-id="63387-188">需要配置 CUCM 以正确路由通过语音中继（或通过视频中继）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-188">CUCM will need to be configured to correctly route calls over the voice trunk vs. the video trunk.</span></span> <span data-ttu-id="63387-189">例如，从 VTC 拨号时，可能会使用特殊的拨号前缀；CUCM 可将此拨号前缀与指向 VIS 的呼叫关联，相应的转换规则会从指向 VIS 的 SIP 邀请中去掉此前缀。</span><span class="sxs-lookup"><span data-stu-id="63387-189">For example, a special dial prefix could be used when dialing from the VTC; CUCM could associate this dial prefix with calls to VIS, and appropriate translation rules would strip this prefix from the SIP Invite to VIS.</span></span>
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a><span data-ttu-id="63387-190">Skype for Business 版本中的 VIS 与先前 Lync 版本的共存</span><span class="sxs-lookup"><span data-stu-id="63387-190">Co-existence of VIS in the Skype for Business Release with Previous Releases of Lync</span></span>
<span data-ttu-id="63387-191"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-191"></span></span>

<span data-ttu-id="63387-192">VIS 可以仅部署 Skype 的业务部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="63387-192">VIS can only be deployed as part of Skype for Business deployment.</span></span> <span data-ttu-id="63387-193">它可兼容 Lync 2013 会议和属于现有部署; 客户端在这些情况下，VIS 池需要包括的注册/FE 池，则下一中继站 VIS 池的业务部署 Skype 的一部分。</span><span class="sxs-lookup"><span data-stu-id="63387-193">It can interoperate with Lync 2013 conferences and clients that are a part of an existing deployment; in those cases, the VIS pool will need to be part of a Skype for Business deployment that includes a Registrar/FE pool that is the next-hop for the VIS pool.</span></span>
  
<span data-ttu-id="63387-194">VIS 不支持在 RTV 和 H.264 之间进行代码转换。</span><span class="sxs-lookup"><span data-stu-id="63387-194">VIS does not support transcoding between RTV and H.264.</span></span> <span data-ttu-id="63387-195">在会议中，Lync 2013 之前的客户端与 VTC 参与者之间不存在视频互操作性。</span><span class="sxs-lookup"><span data-stu-id="63387-195">There is no video interoperability between pre-Lync 2013 clients and VTC participants in a conference.</span></span>
  
<span data-ttu-id="63387-196">在会议中有前 Lync 2013 客户端会导致移动客户端发送使用 RTV 导致 VTCs 移动客户端将成为主导的扬声器时接收到任何视频。</span><span class="sxs-lookup"><span data-stu-id="63387-196">Having pre-Lync 2013 clients in a conference will cause mobile clients to send using RTV resulting in VTCs receiving no video when the mobile client becomes the dominant speaker.</span></span>
  
<span data-ttu-id="63387-197">Lync 2013 为了 Lync 2013 VIS 属于业务部署 Skype 与正常工作，需要适当的 CU 应用程序升级为使用 VIS.Lync 2013 客户端、 CAA，以及 AVMCU</span><span class="sxs-lookup"><span data-stu-id="63387-197">In order for Lync 2013 to work correctly with VIS that is part of a Skype for Business deployment, Lync 2013 needs the appropriate CU to be applied that upgrades the Lync 2013 client, CAA, and AVMCU to work with VIS.</span></span>
  
<span data-ttu-id="63387-198">业务桌面客户端使用 Lync 2013 和 Skype 的 VIS 的互操作性测试，支持它。</span><span class="sxs-lookup"><span data-stu-id="63387-198">Interoperability of VIS with Lync 2013 and Skype for Business desktop clients has been tested and is supported.</span></span>
  
<span data-ttu-id="63387-199">与非桌面 （Android、 Ipad、 Iphone、 Windows Phone、 LMX 等） VIS 的互操作性业务客户可从 VIS 发行时适用的应用程序商店的 Skype 已经过测试和支持。</span><span class="sxs-lookup"><span data-stu-id="63387-199">Interoperability of VIS with non-desktop (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype for Business clients available from the applicable Apps Store at the time of VIS release has been tested and is supported.</span></span>
  
## <a name="recovery-from-packet-loss-via-fec"></a><span data-ttu-id="63387-200">通过 FEC 从数据包丢失中恢复</span><span class="sxs-lookup"><span data-stu-id="63387-200">Recovery from Packet Loss via FEC</span></span>
<span data-ttu-id="63387-201"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-201"></span></span>

<span data-ttu-id="63387-202">可打开 FEC 以帮助从数据包丢失中恢复。</span><span class="sxs-lookup"><span data-stu-id="63387-202">FEC can be turned on to aid in recovery from packet loss.</span></span> <span data-ttu-id="63387-203">如果打开，则 VIS 到 VTC 的路径中使用的视频带宽将增加 50%。</span><span class="sxs-lookup"><span data-stu-id="63387-203">If turned on, 50% more video bandwidth will be used in the VIS to VTC direction.</span></span>
  
## <a name="vis-sizing-and-transcoding-costs"></a><span data-ttu-id="63387-204">VIS 大小调整和代码转换成本</span><span class="sxs-lookup"><span data-stu-id="63387-204">VIS Sizing and Transcoding Costs</span></span>
<span data-ttu-id="63387-205"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-205"></span></span>

<span data-ttu-id="63387-206">要将来自 Cisco VTC 的单个视频流转换为多个联播视频流，需要利用 CPU 容量。</span><span class="sxs-lookup"><span data-stu-id="63387-206">Transcoding the single video streams from the Cisco VTC to multiple simulcast streams uses CPU capacity.</span></span> <span data-ttu-id="63387-207">大约 16 VTCs 建议 FE 平台 Lync 2013 的等效项上运行单个 VIS 中有 （假定每个 VTC 的 720p 视频流将转换成 3 单独 simulcast 流在 720p、 360 p 和 p 180） 其视频转换代码。</span><span class="sxs-lookup"><span data-stu-id="63387-207">Approximately 16 VTCs can have their video transcoded (assuming a 720p video stream from each VTC is transcoded into 3 separate simulcast streams at 720p, 360p, and 180p) in a single VIS running on the equivalent of the Lync 2013 recommended FE platform.</span></span> <span data-ttu-id="63387-208">如果关闭代码转换功能，可以节省 VIS CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="63387-208">If Transcoding is turned off, this will save on VIS CPU.</span></span> <span data-ttu-id="63387-209">但是，VIS 从 VTC 请求的视频图像将为最低的通用分辨率，以便满足 Skype for Business 端的所有接收者要求。</span><span class="sxs-lookup"><span data-stu-id="63387-209">However, the video image requested by VIS from the VTC will be the lowest common resolution to satisfy all receivers on the Skype for Business side.</span></span> <span data-ttu-id="63387-210">请注意，即便关闭代码转换功能，在 Skype for Business 客户端请求某些 VTC 无法发送的低分辨率时，此功能仍可能会被激活。</span><span class="sxs-lookup"><span data-stu-id="63387-210">Note that even with transcoding off, transcoding may be activated when Skype for Business clients request certain low resolutions that VTCs cannot send.</span></span>
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a><span data-ttu-id="63387-211">从视频网关到 VIS 的呼叫分配</span><span class="sxs-lookup"><span data-stu-id="63387-211">Call Distribution from the Video Gateway to VIS</span></span>
<span data-ttu-id="63387-212"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-212"></span></span>

<span data-ttu-id="63387-213">通过以下其中一种 CUCM 分配机制来实现分配：</span><span class="sxs-lookup"><span data-stu-id="63387-213">Distribution is accomplished via one of the CUCM distribution mechanisms:</span></span>
  
- <span data-ttu-id="63387-214">使用 DNS 进行动态分配。</span><span class="sxs-lookup"><span data-stu-id="63387-214">Dynamically using DNS.</span></span>
    
- <span data-ttu-id="63387-215">在 CUCM 端，您可以定义各个中继，在其中，每个中继都在 VIS 池中的不同服务器上终结。</span><span class="sxs-lookup"><span data-stu-id="63387-215">On the CUCM side, you can define individual trunks, where each trunk terminates on a different server in the VIS pool.</span></span> <span data-ttu-id="63387-216">CUCM 将跨不同中继路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="63387-216">CUCM will route calls across the different trunks.</span></span>
    
## <a name="no-hybrid-interoperability"></a><span data-ttu-id="63387-217">无混合互操作性</span><span class="sxs-lookup"><span data-stu-id="63387-217">No Hybrid Interoperability</span></span>
<span data-ttu-id="63387-218"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-218"></span></span>

<span data-ttu-id="63387-219">Skype for Business 不支持 VTC 通过本地 VIS 加入联机会议。</span><span class="sxs-lookup"><span data-stu-id="63387-219">Support for VTCs joining online meetings via on-premises VIS is not part of Skype for Business.</span></span>
  
## <a name="no-federation-support"></a><span data-ttu-id="63387-220">无联盟支持</span><span class="sxs-lookup"><span data-stu-id="63387-220">No Federation Support</span></span>
<span data-ttu-id="63387-221"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-221"></span></span>

<span data-ttu-id="63387-222">Skype for Business 不支持 VTC 通过 VIS 加入联盟会议。</span><span class="sxs-lookup"><span data-stu-id="63387-222">Support for VTCs joining federated meetings via VIS is not part of Skype for Business.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="63387-223">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63387-223">See also</span></span>
<span data-ttu-id="63387-224"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="63387-224"></span></span>

#### 

[<span data-ttu-id="63387-225">在 Skype 的视频互操作服务器部署为业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="63387-225">Deploy Video Interop Server in Skype for Business Server 2015</span></span>](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)

