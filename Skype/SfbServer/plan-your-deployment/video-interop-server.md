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
description: 摘要： 查看 while planning to 将 Skype 与第三方电话会议设备集成的业务服务器 2015年本主题。
ms.openlocfilehash: cd8d4ec7ad854dc87d9bf9c86e2552996a09215d
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19505179"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="6113b-103">在 Skype for Business Server 2015 中规划视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="6113b-103">Plan for Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6113b-104">**摘要：** While planning to 将 Skype 与第三方电话会议设备集成的业务服务器 2015年查看以下主题。</span><span class="sxs-lookup"><span data-stu-id="6113b-104">**Summary:** Review this topic while planning to integrate Skype for Business Server 2015 with third-party teleconferencing devices.</span></span>
  
<span data-ttu-id="6113b-105">Skype 业务服务器现在可以使用某些第三方 VTC （视频电话会议系统） 解决方案的集成。</span><span class="sxs-lookup"><span data-stu-id="6113b-105">Skype for Business Server now allows you to integrate with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="6113b-106">启用此视频会议的互操作性的新服务器角色是视频互操作服务器 (VIS)，其当前作为独立服务器角色仅适用于本地安装实现。</span><span class="sxs-lookup"><span data-stu-id="6113b-106">The new server role that enables this video conferencing interoperability is the Video Interop Server (VIS), which is currently implemented as a standalone server role available only for on-premises installations.</span></span> <span data-ttu-id="6113b-107">VIS 作为中介的第三方电话会议系统和 Skype 业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="6113b-107">A VIS acts as an intermediary between a third party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="6113b-108">对于此版本，VIS 着重实现了与 Cisco/Tandberg 视频系统之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="6113b-108">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span> <span data-ttu-id="6113b-109">查看此文，确定是否业务服务器安装在您 Skype 中使用此功能。</span><span class="sxs-lookup"><span data-stu-id="6113b-109">Review this article to determine whether to use this feature in your Skype for Business Server installation.</span></span>
  
## <a name="device-interoperability"></a><span data-ttu-id="6113b-110">设备互操作性</span><span class="sxs-lookup"><span data-stu-id="6113b-110">Device interoperability</span></span>

<span data-ttu-id="6113b-111">在 Cisco VTC 向 CUCM 版本 10.5 注册，并且在 CUCM 与 VIS 之间设置了 TCP SIP 中继的情况下，互操作性经过测试，并得到支持。</span><span class="sxs-lookup"><span data-stu-id="6113b-111">Interoperation is tested and supported with Cisco VTCs registering with CUCM version 10.5 and TCP SIP trunks set up between CUCM and the VIS.</span></span>
  
<span data-ttu-id="6113b-112">当前支持的 VTC 包括：</span><span class="sxs-lookup"><span data-stu-id="6113b-112">The currently supported VTCs are:</span></span>
  
- <span data-ttu-id="6113b-113">Cisco C40</span><span class="sxs-lookup"><span data-stu-id="6113b-113">Cisco C40</span></span>
    
- <span data-ttu-id="6113b-114">Cisco C60</span><span class="sxs-lookup"><span data-stu-id="6113b-114">Cisco C60</span></span>
    
- <span data-ttu-id="6113b-115">Cisco C90</span><span class="sxs-lookup"><span data-stu-id="6113b-115">Cisco C90</span></span>
    
- <span data-ttu-id="6113b-116">Cisco MX200</span><span class="sxs-lookup"><span data-stu-id="6113b-116">Cisco MX200</span></span>
    
- <span data-ttu-id="6113b-117">Cisco MX300</span><span class="sxs-lookup"><span data-stu-id="6113b-117">Cisco MX300</span></span>
    
- <span data-ttu-id="6113b-118">Cisco DX80</span><span class="sxs-lookup"><span data-stu-id="6113b-118">Cisco DX80</span></span>
    
- <span data-ttu-id="6113b-119">Cisco EX60</span><span class="sxs-lookup"><span data-stu-id="6113b-119">Cisco EX60</span></span>
    
- <span data-ttu-id="6113b-120">Cisco EX90</span><span class="sxs-lookup"><span data-stu-id="6113b-120">Cisco EX90</span></span>
    
- <span data-ttu-id="6113b-121">Cisco SX20</span><span class="sxs-lookup"><span data-stu-id="6113b-121">Cisco SX20</span></span>
    
> [!NOTE]
>  <span data-ttu-id="6113b-122">Cisco 软件版本 TC7.0.0 或集成业务服务器按预期方式工作的 Skype 与这些系统上需要上方。</span><span class="sxs-lookup"><span data-stu-id="6113b-122">Cisco software release TC7.0.0 or above is required on these systems for integration with Skype for Business Server to work as expected.</span></span>
  
## <a name="sip-trunks"></a><span data-ttu-id="6113b-123">SIP 中继</span><span class="sxs-lookup"><span data-stu-id="6113b-123">SIP trunks</span></span>

<span data-ttu-id="6113b-124">在 SIP 中继模式下，VTCs 继续 Cisco 呼叫管理器 (CUCM) 注册的现有 Cisco 基础结构-例如，视频互操作服务器功能。</span><span class="sxs-lookup"><span data-stu-id="6113b-124">The Video Interop Server functions in SIP trunk mode, where the VTCs continue to register with the existing Cisco infrastructure - for example, Cisco Call Manager (CUCM).</span></span> <span data-ttu-id="6113b-125">在 CUCM 和 VIS 之间定义了视频 SIP 中继，从而可以在两个系统之间路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="6113b-125">A video SIP trunk is defined between CUCM and the VIS so that calls can be routed between the two systems.</span></span> <span data-ttu-id="6113b-126">仅支持通过 SIP 中继从 VTC 向 VIS 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="6113b-126">Only calls over the SIP trunk from the VTC to the VIS are supported.</span></span> <span data-ttu-id="6113b-127">因此，VTCs 可以 （通过拨打与呼叫自动助理的电话号码），拨入 Skype 业务会议但不能拖放入会议。</span><span class="sxs-lookup"><span data-stu-id="6113b-127">Thus, VTCs can dial into a Skype for Business conference (by dialing the phone number associated with the Call Automated Attendant), but cannot be dragged and dropped into the conference.</span></span>
  
![SfB 中的 VIS 图表](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a><span data-ttu-id="6113b-129">功能</span><span class="sxs-lookup"><span data-stu-id="6113b-129">Features</span></span>

<span data-ttu-id="6113b-130">此服务器角色提供：</span><span class="sxs-lookup"><span data-stu-id="6113b-130">This server role provides:</span></span>
  
- <span data-ttu-id="6113b-131">用于通过第三方视频系统和 Skype Business Server 部署的 H.264 格式之间的转换。</span><span class="sxs-lookup"><span data-stu-id="6113b-131">Conversion between the H.264 formats used by 3rd party video systems and the Skype for Business Server deployment.</span></span>
    
- <span data-ttu-id="6113b-132">在给定分辨率为单个视频流的从转换 VTC 到多个 simulcast 流的不同的业务服务器部署在 Skype 中使用的分辨率。</span><span class="sxs-lookup"><span data-stu-id="6113b-132">Conversion of a single video stream at a given resolution from a VTC into multiple simulcast streams of different resolutions for use in the Skype for Business Server deployment.</span></span> <span data-ttu-id="6113b-133">这些流可被发送到 AVMCU 和 Skype 业务服务器终结点和其他视频系统所请求不同的分辨率。</span><span class="sxs-lookup"><span data-stu-id="6113b-133">These streams can be sent to the AVMCU and then to Skype for Business Server endpoints and other video systems that have requested different resolutions.</span></span> <span data-ttu-id="6113b-134">第三方视频系统参与 for Business A Skype 时也可用于此转换 / V 会议呼叫。</span><span class="sxs-lookup"><span data-stu-id="6113b-134">This conversion is also used when the third party video system is involved in a Skype for Business A/V conference call.</span></span> <span data-ttu-id="6113b-135">一旦转码限制达到特定 VIS 服务器中，为不同的分辨率任何以下请求只会收到的最低分辨率的流。</span><span class="sxs-lookup"><span data-stu-id="6113b-135">Once the transcoding limit is reached in a particular VIS server, any following requests for different resolutions will only receive a stream with the lowest resolution.</span></span> 
    
- <span data-ttu-id="6113b-136">业务 Server 视频互操作服务器; CUCM 网关和 Skype 之间视频 SIP 中继支持VTCs 继续注册 Cisco 网关，并启动通过网关的业务部署 Skype 调用。</span><span class="sxs-lookup"><span data-stu-id="6113b-136">Support for a video SIP trunk between the CUCM gateway and a Skype for Business Server Video Interop Server; VTCs continue to register with the Cisco gateway, and initiate calls to the Skype for Business deployment through the gateway.</span></span> <span data-ttu-id="6113b-137">呼叫转移视频的 SIP 中继路由的网关的 Skype 从业务视频互操作服务器。</span><span class="sxs-lookup"><span data-stu-id="6113b-137">Calls are routed from the gateway to the Skype for Business Video Interop Server over the video SIP trunk.</span></span>
    
- <span data-ttu-id="6113b-138">支持会议室中的用户使用支持的视频系统从该系统拨号加入开启或关闭的会议。</span><span class="sxs-lookup"><span data-stu-id="6113b-138">Support for a user in a conference room with a supported video system to dial from that system to join an open or closed conference.</span></span> <span data-ttu-id="6113b-139">此呼叫将遍历视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="6113b-139">This call will traverse the video SIP trunk.</span></span>
    
- <span data-ttu-id="6113b-140">与支持视频系统会议室中的用户，为业务客户端调用 Skype 的支持。</span><span class="sxs-lookup"><span data-stu-id="6113b-140">Support for a user in a conference room with a supported video system to call a Skype for Business client.</span></span> <span data-ttu-id="6113b-141">此呼叫将遍历视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="6113b-141">The call will traverse the SIP trunk.</span></span>
    
- <span data-ttu-id="6113b-142">从业务服务器端 Skype 或点到点和多点包括静音/未经 mute 音频、 暂停/继续视频、 锁定视频和保留/取消保留呼叫的呼叫的支持 VTC 系统中的呼叫控制的支持。</span><span class="sxs-lookup"><span data-stu-id="6113b-142">Support for mid-call control from the Skype for Business Server side or from the supported VTC system for both point to point and multipoint calls including mute/un-mute audio, pause/resume video, lock video, and hold/un-hold call.</span></span>
    
## <a name="known-limitations"></a><span data-ttu-id="6113b-143">已知限制</span><span class="sxs-lookup"><span data-stu-id="6113b-143">Known limitations</span></span>

<span data-ttu-id="6113b-144">此服务器角色存在以下限制：</span><span class="sxs-lookup"><span data-stu-id="6113b-144">This server role has the following limitations:</span></span>
  
- <span data-ttu-id="6113b-145">不支持新调用从业务部署 Skype 通过视频的 SIP 中继 VTCs。</span><span class="sxs-lookup"><span data-stu-id="6113b-145">New calls from the Skype for Business deployment to the VTCs over the video SIP trunk are not supported.</span></span> <span data-ttu-id="6113b-146">.</span><span class="sxs-lookup"><span data-stu-id="6113b-146"></span></span> <span data-ttu-id="6113b-147">这意味着，仅新从 VTCs 到业务部署 Skype 支持呼叫通过视频的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="6113b-147">This means that only new calls from the VTCs into the Skype for Business deployment are supported over the video SIP trunk.</span></span> <span data-ttu-id="6113b-148">受支持的视频系统的状态将不可用转移到 VIS.视频的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="6113b-148">Presence for the supported video system will not be available over the video SIP trunk to the VIS.</span></span> 
    
- <span data-ttu-id="6113b-149">对于视频 SIP 中继模式，仅支持独立的 VIS 池。</span><span class="sxs-lookup"><span data-stu-id="6113b-149">Only a standalone VIS pool will be supported for video SIP trunk mode.</span></span>
    
-  <span data-ttu-id="6113b-150">对于通过视频 SIP 中继在 VTC 和 VIS 之间进行的通信，支持 TLS + SRTP 或 TCP + RTP。</span><span class="sxs-lookup"><span data-stu-id="6113b-150">TLS + SRTP or TCP + RTP will be supported for communications between the VTC and VIS over the video SIP trunk.</span></span>
    
- <span data-ttu-id="6113b-151">不支持应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="6113b-151">Application sharing is not supported.</span></span> <span data-ttu-id="6113b-152">会议室中的业务用户 Skype 需要加入 （通过例如便携式计算机） 的业务会议 Skype 和显示应用程序共享屏幕上一个不与 VTC 关联的会议室中可用的监视器。</span><span class="sxs-lookup"><span data-stu-id="6113b-152">A Skype for Business user in the conference room needs to join the Skype for Business conference (via a laptop for example) and display the app sharing screens on one of the free monitors in the conference room not associated with the VTC.</span></span>
    
- <span data-ttu-id="6113b-153">不支持 VTC 通过 VIS 加入联盟会议。</span><span class="sxs-lookup"><span data-stu-id="6113b-153">The ability for a VTC to join a federated meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="6113b-154">不支持 VTC 通过 VIS 加入联机会议。</span><span class="sxs-lookup"><span data-stu-id="6113b-154">The ability for a VTC to join an online meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="6113b-155">不支持通过 VIS 从 VTC 向 PSTN 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="6113b-155">Calls from a VTC to the PSTN via VIS are not supported.</span></span>
    
- <span data-ttu-id="6113b-156">不支持通过 VIS 从 PSTN 向 VTC 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="6113b-156">Calls from the PSTN to a VTC via VIS are not supported.</span></span>
    
## <a name="resiliency-mechanisms"></a><span data-ttu-id="6113b-157">复原机制</span><span class="sxs-lookup"><span data-stu-id="6113b-157">Resiliency mechanisms</span></span>
<span data-ttu-id="6113b-158"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-158"></span></span>

<span data-ttu-id="6113b-159">VIS 支持通过视频 SIP 中继传递的、来自 CUCM 的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="6113b-159">The VIS supports incoming calls from a CUCM that are carried over a video SIP trunk.</span></span> <span data-ttu-id="6113b-160">可能会丢失上游或下游连接，因此，要实现强大的复原能力，请考虑两种可能性：</span><span class="sxs-lookup"><span data-stu-id="6113b-160">It's possible to lose connectivity either upstream or downstream, so for robust resiliency consider both possibilities:</span></span>
  
1. <span data-ttu-id="6113b-161">**VIS 池故障转移**如果主视频的网关指向 VIS 池已关闭，恢复是当视频的网关到两个 （或多个） VIS 池定义了中继。</span><span class="sxs-lookup"><span data-stu-id="6113b-161">**VIS Pool Failover** If the main VIS pool that the video gateway points to is down, recovery is possible if the video gateway has defined trunks to two (or more) VIS pools.</span></span> <span data-ttu-id="6113b-162">如果视频的网关确定但不能对主要 VIS 池的呼叫，则只需将呼叫路由到辅助 VIS 池。</span><span class="sxs-lookup"><span data-stu-id="6113b-162">If the video gateway determines it cannot make calls to the primary VIS pool, it simply routes the calls to a secondary VIS pool.</span></span>
    
     ![VIS 池故障转移图](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    <span data-ttu-id="6113b-164">特定 VIS 池可以有中继到多个网关，但通常特定网关不能具有中继到多个 VIS 池，因此技巧需要进行以支持此故障转移： 在 DNS 中解析视频的网关的同一个 IP 地址为其定义 2 FDQNs。</span><span class="sxs-lookup"><span data-stu-id="6113b-164">A particular VIS pool can have trunks to multiple gateways, but normally a particular gateway can't have trunks to multiple VIS pools, so a trick needs to be done to support this failover: Define 2 FDQNs in DNS which resolve to the same IP address of a video gateway.</span></span> <span data-ttu-id="6113b-165">表示每个 FQDN 为拓扑文档，其中每个视频的网关具有中继到另一个 VIS 池，并恢复现在是可能的单独视频网关。</span><span class="sxs-lookup"><span data-stu-id="6113b-165">Represent each FQDN as a separate video gateway in the Topology Document where each video gateway has a trunk to a different VIS pool, and recovery is now possible.</span></span> <span data-ttu-id="6113b-166">（如果使用 TLS，则多个名称将需要视频的网关证书的 SAN 中。）</span><span class="sxs-lookup"><span data-stu-id="6113b-166">(If TLS is used, the multiple names will need to be in the SAN of the video gateway certificate.)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6113b-167">VIS 仅允许传入呼叫来自拓扑文档中配置的网关。</span><span class="sxs-lookup"><span data-stu-id="6113b-167">VIS only allows incoming calls from gateways configured in the Topology Document.</span></span> 
  
2. <span data-ttu-id="6113b-168">**前端故障转移**如果 VIS 池接收来自 CUCM 的调用，但无法访问其主跃注册机构或前端池，则呼叫将路由至备份前端池。</span><span class="sxs-lookup"><span data-stu-id="6113b-168">**Front End failover** If a VIS pool receives a call from CUCM but cannot reach its primary next-hop Registrar or Front End pool, calls are routed to a backup Front End pool.</span></span>
    
     ![前端故障转移图表](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    <span data-ttu-id="6113b-170">VIS 将跟踪的与其主前端池和与其 （拓扑文档中的注册器服务的备份设置中查找的设置） 的备份的前端池的状态。</span><span class="sxs-lookup"><span data-stu-id="6113b-170">The VIS will keep track of the status of its primary Front End pool and its backup Front End pool (the setting is found in the backup setting for the Registrar service in the Topology Document).</span></span> <span data-ttu-id="6113b-171">向这两个池中，发送选项投票一分钟一次并 VIS 五个连续故障时假定特定的前端池已关闭。</span><span class="sxs-lookup"><span data-stu-id="6113b-171">It sends Options polls once a minute to both pools, and if there are five consecutive failures the VIS assumes that a particular Front End pool is down.</span></span> <span data-ttu-id="6113b-172">如果主前端池将标记为已向下并且还没有可用的配置备份 VIS 发送新呼叫的网关到备份的前端池。</span><span class="sxs-lookup"><span data-stu-id="6113b-172">If the primary Front End pool is marked as down and there is an available configured backup the VIS sends new calls from the gateway to the backup Front End pool.</span></span> <span data-ttu-id="6113b-173">一旦主前端池恢复后，VIS 将继续使用新的呼叫的主前端池。</span><span class="sxs-lookup"><span data-stu-id="6113b-173">Once the primary Front End pool comes back, the VIS will resume using the primary Front End pool for new calls.</span></span>
    
    <span data-ttu-id="6113b-174">VIS 还会为来自视频 SIP 中继的呼叫设置 10 秒计时。</span><span class="sxs-lookup"><span data-stu-id="6113b-174">The VIS will also implement a 10 second timer for calls from the video SIP trunk.</span></span> <span data-ttu-id="6113b-175">如果在呼叫的视频的 SIP 中继和主下一个跃点前端池没有应答使用一些 （包括 100 尝试） 的 SIP 消息为邀请向其发送此计时器值时，呼叫 s 的备份下一个跃点代理中使用了主要的下一个跃点前端池如果配置，尝试 hould。</span><span class="sxs-lookup"><span data-stu-id="6113b-175">If the primary next-hop Front End pool was used for a call from the video SIP trunk, and the primary next-hop Front End pool did not answer with some SIP message (including 100 Trying) to the Invite sent to it within this timer value, the backup next-hop proxy for the call should be tried if configured.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6113b-176">如果首次尝试备份的下一个跃点，将不会下一步尝试主。</span><span class="sxs-lookup"><span data-stu-id="6113b-176">If the backup next hop was tried first, the primary will not be tried next.</span></span> 
  
    <span data-ttu-id="6113b-177">管理员还可以使用 Windows PowerShell 故障转移命令强制 VIS 时要使用备份前端池，例如，维护具有主前端池上执行。</span><span class="sxs-lookup"><span data-stu-id="6113b-177">The admin could also use the Windows PowerShell failover command to force VIS to use the backup Front End pool, for example, when maintenance has to be performed on the primary Front End pool.</span></span>
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a><span data-ttu-id="6113b-178">指向同一网关对等方的语音和视频中继的共存</span><span class="sxs-lookup"><span data-stu-id="6113b-178">Co-existence of Voice and Video Trunks to the Same Gateway Peer</span></span>
<span data-ttu-id="6113b-179"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-179"></span></span>

<span data-ttu-id="6113b-180">具有语音和视频的 SIP 中继的业务服务器支持的 Skype 使用相同的对等网关。</span><span class="sxs-lookup"><span data-stu-id="6113b-180">Skype for Business Server supports having voice and video SIP trunks use the same gateway peer.</span></span> <span data-ttu-id="6113b-181">因此，同一 CUCM 部署可能具有指向中介服务器的语音 SIP 中继和指向 VIS 的视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="6113b-181">So the same CUCM deployment could have voice SIP trunks to the Mediation Server and video SIP trunks to VIS.</span></span>
  
- <span data-ttu-id="6113b-182">需要在语音 SIP 中继的拓扑文档中使用特定 FQDN 定义 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="6113b-182">A PSTN Gateway will need to be defined with a particular FQDN in the Topology Document for the voice SIP trunks.</span></span>
    
- <span data-ttu-id="6113b-183">PSTN 网关的对等方将为中介服务器。</span><span class="sxs-lookup"><span data-stu-id="6113b-183">The peer to the PSTN Gateway will be the Mediation Server.</span></span>
    
- <span data-ttu-id="6113b-184">如有必要可定义多个语音中继，范围从单个 PSTN 网关涵盖到多个中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="6113b-184">Multiple voice trunks can be defines spanning from a PSTN Gateway to multiple Mediation Server pools if necessary.</span></span>
    
- <span data-ttu-id="6113b-185">需要在视频 SIP 中继的拓扑文档中定义视频网关并使用与 PSTN 网关相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6113b-185">A Video Gateway will need to be defined in the Topology Document for the video SIP trunk with the same FQDN as for the PSTN Gateway.</span></span>
    
- <span data-ttu-id="6113b-186">视频网关的对等方将为 VIS。</span><span class="sxs-lookup"><span data-stu-id="6113b-186">The peer to the Video Gateway will be VIS.</span></span>
    
- <span data-ttu-id="6113b-187">可从视频网关到特定 VIS 池定义单个视频中继。</span><span class="sxs-lookup"><span data-stu-id="6113b-187">A single video trunk can be defined from a Video Gateway to a particular VIS pool.</span></span>
    
- <span data-ttu-id="6113b-188">需要配置 CUCM 以正确路由通过语音中继（或通过视频中继）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6113b-188">CUCM will need to be configured to correctly route calls over the voice trunk vs. the video trunk.</span></span> <span data-ttu-id="6113b-189">例如，从 VTC 拨号时，可能会使用特殊的拨号前缀；CUCM 可将此拨号前缀与指向 VIS 的呼叫关联，相应的转换规则会从指向 VIS 的 SIP 邀请中去掉此前缀。</span><span class="sxs-lookup"><span data-stu-id="6113b-189">For example, a special dial prefix could be used when dialing from the VTC; CUCM could associate this dial prefix with calls to VIS, and appropriate translation rules would strip this prefix from the SIP Invite to VIS.</span></span>
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a><span data-ttu-id="6113b-190">Skype for Business 版本中的 VIS 与先前 Lync 版本的共存</span><span class="sxs-lookup"><span data-stu-id="6113b-190">Co-existence of VIS in the Skype for Business Release with Previous Releases of Lync</span></span>
<span data-ttu-id="6113b-191"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-191"></span></span>

<span data-ttu-id="6113b-192">VIS 只能部署的 Skype 业务部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="6113b-192">VIS can only be deployed as part of Skype for Business deployment.</span></span> <span data-ttu-id="6113b-193">它可以与 Lync 2013 会议和客户端的属于现有部署; 互操作在这些情况下，VIS 池将需要 Skype 包括 VIS 池的下一个跃点的注册器/FE 池中的业务部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="6113b-193">It can interoperate with Lync 2013 conferences and clients that are a part of an existing deployment; in those cases, the VIS pool will need to be part of a Skype for Business deployment that includes a Registrar/FE pool that is the next-hop for the VIS pool.</span></span>
  
<span data-ttu-id="6113b-194">VIS 不支持在 RTV 和 H.264 之间进行代码转换。</span><span class="sxs-lookup"><span data-stu-id="6113b-194">VIS does not support transcoding between RTV and H.264.</span></span> <span data-ttu-id="6113b-195">在会议中，Lync 2013 之前的客户端与 VTC 参与者之间不存在视频互操作性。</span><span class="sxs-lookup"><span data-stu-id="6113b-195">There is no video interoperability between pre-Lync 2013 clients and VTC participants in a conference.</span></span>
  
<span data-ttu-id="6113b-196">在会议中无预 Lync 2013 客户端会导致移动客户端发送使用 RTV 导致 VTCs 时移动客户端将成为基准扬声器接收到任何视频。</span><span class="sxs-lookup"><span data-stu-id="6113b-196">Having pre-Lync 2013 clients in a conference will cause mobile clients to send using RTV resulting in VTCs receiving no video when the mobile client becomes the dominant speaker.</span></span>
  
<span data-ttu-id="6113b-197">Lync 2013 为了使 Lync 2013 与 VIS 属于业务部署 Skype 正常工作，需要相应的 CU 要应用的升级的 Lync 2013 客户端，CAA 和 AVMCU，以使用 VIS.</span><span class="sxs-lookup"><span data-stu-id="6113b-197">In order for Lync 2013 to work correctly with VIS that is part of a Skype for Business deployment, Lync 2013 needs the appropriate CU to be applied that upgrades the Lync 2013 client, CAA, and AVMCU to work with VIS.</span></span>
  
<span data-ttu-id="6113b-198">为业务桌面客户端 VIS 与 Lync 2013 和 Skype 的互操作性已经过测试和支持。</span><span class="sxs-lookup"><span data-stu-id="6113b-198">Interoperability of VIS with Lync 2013 and Skype for Business desktop clients has been tested and is supported.</span></span>
  
<span data-ttu-id="6113b-199">与非桌面 （Android、 Ipad、 Iphone、 Windows Phone、 LMX 等） 的 VIS 互操作性为业务客户端可用 VIS 发行版时适用的应用程序存储中的 Skype 已经过测试和支持。</span><span class="sxs-lookup"><span data-stu-id="6113b-199">Interoperability of VIS with non-desktop (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype for Business clients available from the applicable Apps Store at the time of VIS release has been tested and is supported.</span></span>
  
## <a name="recovery-from-packet-loss-via-fec"></a><span data-ttu-id="6113b-200">通过 FEC 从数据包丢失中恢复</span><span class="sxs-lookup"><span data-stu-id="6113b-200">Recovery from Packet Loss via FEC</span></span>
<span data-ttu-id="6113b-201"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-201"></span></span>

<span data-ttu-id="6113b-202">可打开 FEC 以帮助从数据包丢失中恢复。</span><span class="sxs-lookup"><span data-stu-id="6113b-202">FEC can be turned on to aid in recovery from packet loss.</span></span> <span data-ttu-id="6113b-203">如果打开，则 VIS 到 VTC 的路径中使用的视频带宽将增加 50%。</span><span class="sxs-lookup"><span data-stu-id="6113b-203">If turned on, 50% more video bandwidth will be used in the VIS to VTC direction.</span></span>
  
## <a name="vis-sizing-and-transcoding-costs"></a><span data-ttu-id="6113b-204">VIS 大小调整和代码转换成本</span><span class="sxs-lookup"><span data-stu-id="6113b-204">VIS Sizing and Transcoding Costs</span></span>
<span data-ttu-id="6113b-205"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-205"></span></span>

<span data-ttu-id="6113b-206">要将来自 Cisco VTC 的单个视频流转换为多个联播视频流，需要利用 CPU 容量。</span><span class="sxs-lookup"><span data-stu-id="6113b-206">Transcoding the single video streams from the Cisco VTC to multiple simulcast streams uses CPU capacity.</span></span> <span data-ttu-id="6113b-207">大约 16 VTCs 可以 （假定 720 p 视频流，从每个 VTC 为 720 p、 360 p、 和 180 p 3 单独 simulcast 流到转换代码） 其视频转换代码中单个 VIS 推荐 FE 平台 Lync 2013 的等效项上运行。</span><span class="sxs-lookup"><span data-stu-id="6113b-207">Approximately 16 VTCs can have their video transcoded (assuming a 720p video stream from each VTC is transcoded into 3 separate simulcast streams at 720p, 360p, and 180p) in a single VIS running on the equivalent of the Lync 2013 recommended FE platform.</span></span> <span data-ttu-id="6113b-208">如果关闭代码转换功能，可以节省 VIS CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="6113b-208">If Transcoding is turned off, this will save on VIS CPU.</span></span> <span data-ttu-id="6113b-209">但是，VIS 从 VTC 请求的视频图像将为最低的通用分辨率，以便满足 Skype for Business 端的所有接收者要求。</span><span class="sxs-lookup"><span data-stu-id="6113b-209">However, the video image requested by VIS from the VTC will be the lowest common resolution to satisfy all receivers on the Skype for Business side.</span></span> <span data-ttu-id="6113b-210">请注意，即便关闭代码转换功能，在 Skype for Business 客户端请求某些 VTC 无法发送的低分辨率时，此功能仍可能会被激活。</span><span class="sxs-lookup"><span data-stu-id="6113b-210">Note that even with transcoding off, transcoding may be activated when Skype for Business clients request certain low resolutions that VTCs cannot send.</span></span>
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a><span data-ttu-id="6113b-211">从视频网关到 VIS 的呼叫分配</span><span class="sxs-lookup"><span data-stu-id="6113b-211">Call Distribution from the Video Gateway to VIS</span></span>
<span data-ttu-id="6113b-212"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-212"></span></span>

<span data-ttu-id="6113b-213">通过以下其中一种 CUCM 分配机制来实现分配：</span><span class="sxs-lookup"><span data-stu-id="6113b-213">Distribution is accomplished via one of the CUCM distribution mechanisms:</span></span>
  
- <span data-ttu-id="6113b-214">使用 DNS 进行动态分配。</span><span class="sxs-lookup"><span data-stu-id="6113b-214">Dynamically using DNS.</span></span>
    
- <span data-ttu-id="6113b-215">在 CUCM 端，您可以定义各个中继，在其中，每个中继都在 VIS 池中的不同服务器上终结。</span><span class="sxs-lookup"><span data-stu-id="6113b-215">On the CUCM side, you can define individual trunks, where each trunk terminates on a different server in the VIS pool.</span></span> <span data-ttu-id="6113b-216">CUCM 将跨不同中继路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="6113b-216">CUCM will route calls across the different trunks.</span></span>
    
## <a name="no-hybrid-interoperability"></a><span data-ttu-id="6113b-217">无混合互操作性</span><span class="sxs-lookup"><span data-stu-id="6113b-217">No Hybrid Interoperability</span></span>
<span data-ttu-id="6113b-218"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-218"></span></span>

<span data-ttu-id="6113b-219">Skype for Business 不支持 VTC 通过本地 VIS 加入联机会议。</span><span class="sxs-lookup"><span data-stu-id="6113b-219">Support for VTCs joining online meetings via on-premises VIS is not part of Skype for Business.</span></span>
  
## <a name="no-federation-support"></a><span data-ttu-id="6113b-220">无联盟支持</span><span class="sxs-lookup"><span data-stu-id="6113b-220">No Federation Support</span></span>
<span data-ttu-id="6113b-221"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-221"></span></span>

<span data-ttu-id="6113b-222">Skype for Business 不支持 VTC 通过 VIS 加入联盟会议。</span><span class="sxs-lookup"><span data-stu-id="6113b-222">Support for VTCs joining federated meetings via VIS is not part of Skype for Business.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6113b-223">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6113b-223">See also</span></span>
<span data-ttu-id="6113b-224"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-224"></span></span>

[<span data-ttu-id="6113b-225">部署业务服务器 2015年视频中 Skype 的互操作性服务器</span><span class="sxs-lookup"><span data-stu-id="6113b-225">Deploy Video Interop Server in Skype for Business Server 2015</span></span>](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)