---
title: 在 Skype for Business Server 中规划视频互操作服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要：在计划将 Skype for Business Server 与第三方电话会议设备集成时，请查看本主题。
ms.openlocfilehash: c14d92042922f30ca5dd43acce12d11ef50a8683
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831942"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="02714-103">在 Skype for Business Server 中规划视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="02714-103">Plan for Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="02714-104">**摘要：** 在计划将 Skype for Business Server 与第三方电话会议设备集成时，请查看本主题。</span><span class="sxs-lookup"><span data-stu-id="02714-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with third-party teleconferencing devices.</span></span>
  
<span data-ttu-id="02714-105">Skype for Business Server 现在允许你与某些第三方 VTC (视频电话会议系统) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="02714-105">Skype for Business Server now allows you to integrate with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="02714-106">启用此视频会议互操作性的新服务器角色是视频互操作服务器 (VIS) ，当前作为仅可用于本地安装的独立服务器角色实现。</span><span class="sxs-lookup"><span data-stu-id="02714-106">The new server role that enables this video conferencing interoperability is the Video Interop Server (VIS), which is currently implemented as a standalone server role available only for on-premises installations.</span></span> <span data-ttu-id="02714-107">VIS 充当第三方电话会议系统和 Skype for Business Server 部署之间的中介。</span><span class="sxs-lookup"><span data-stu-id="02714-107">A VIS acts as an intermediary between a third party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="02714-108">对于此版本，VIS 侧重于与 Cisco/Tandberg 视频系统的互操作性。</span><span class="sxs-lookup"><span data-stu-id="02714-108">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span> <span data-ttu-id="02714-109">查看本文，确定是否在 Skype for Business Server 安装中使用此功能。</span><span class="sxs-lookup"><span data-stu-id="02714-109">Review this article to determine whether to use this feature in your Skype for Business Server installation.</span></span>
  
## <a name="device-interoperability"></a><span data-ttu-id="02714-110">设备互操作性</span><span class="sxs-lookup"><span data-stu-id="02714-110">Device interoperability</span></span>

<span data-ttu-id="02714-111">使用在 Cisco 统一通信管理器 (CallManager 或 CUCM) 版本 10.5 中注册的 Cisco VTC 和在 CUCM 和 VIS 之间设置的 TCP SIP 中继，对互操作进行测试和支持。</span><span class="sxs-lookup"><span data-stu-id="02714-111">Interoperation is tested and supported with Cisco VTCs registering with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 and TCP SIP trunks set up between CUCM and the VIS.</span></span>
  
<span data-ttu-id="02714-112">当前支持的 VTC 包括：</span><span class="sxs-lookup"><span data-stu-id="02714-112">The currently supported VTCs are:</span></span>
  
- <span data-ttu-id="02714-113">Cisco C40</span><span class="sxs-lookup"><span data-stu-id="02714-113">Cisco C40</span></span>
    
- <span data-ttu-id="02714-114">Cisco C60</span><span class="sxs-lookup"><span data-stu-id="02714-114">Cisco C60</span></span>
    
- <span data-ttu-id="02714-115">Cisco C90</span><span class="sxs-lookup"><span data-stu-id="02714-115">Cisco C90</span></span>
    
- <span data-ttu-id="02714-116">Cisco MX200</span><span class="sxs-lookup"><span data-stu-id="02714-116">Cisco MX200</span></span>
    
- <span data-ttu-id="02714-117">Cisco MX300</span><span class="sxs-lookup"><span data-stu-id="02714-117">Cisco MX300</span></span>
    
- <span data-ttu-id="02714-118">Cisco DX80</span><span class="sxs-lookup"><span data-stu-id="02714-118">Cisco DX80</span></span>
    
- <span data-ttu-id="02714-119">Cisco EX60</span><span class="sxs-lookup"><span data-stu-id="02714-119">Cisco EX60</span></span>
    
- <span data-ttu-id="02714-120">Cisco EX90</span><span class="sxs-lookup"><span data-stu-id="02714-120">Cisco EX90</span></span>
    
- <span data-ttu-id="02714-121">Cisco SX20</span><span class="sxs-lookup"><span data-stu-id="02714-121">Cisco SX20</span></span>
    
> [!NOTE]
>  <span data-ttu-id="02714-122">这些系统上需要 Cisco 软件版本 TC7.0.0 或以上版本，才能与 Skype for Business Server 集成以按预期工作。</span><span class="sxs-lookup"><span data-stu-id="02714-122">Cisco software release TC7.0.0 or above is required on these systems for integration with Skype for Business Server to work as expected.</span></span>
  
## <a name="sip-trunks"></a><span data-ttu-id="02714-123">SIP 中继</span><span class="sxs-lookup"><span data-stu-id="02714-123">SIP trunks</span></span>

<span data-ttu-id="02714-124">视频互操作服务器在 SIP 中继模式下运行，VTC 继续注册现有 Cisco 基础结构-例如，Cisco Call Manager (CUCM) 。</span><span class="sxs-lookup"><span data-stu-id="02714-124">The Video Interop Server functions in SIP trunk mode, where the VTCs continue to register with the existing Cisco infrastructure - for example, Cisco Call Manager (CUCM).</span></span> <span data-ttu-id="02714-125">在 CUCM 和 VIS 之间定义视频 SIP 中继，以便可以在两个系统之间路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-125">A video SIP trunk is defined between CUCM and the VIS so that calls can be routed between the two systems.</span></span> <span data-ttu-id="02714-126">仅支持通过 SIP 中继从 VTC 到 VIS 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-126">Only calls over the SIP trunk from the VTC to the VIS are supported.</span></span> <span data-ttu-id="02714-127">因此，VTC 可以通过拨打与呼叫自动助理 (关联的电话号码拨入 Skype for Business 会议) 但不能拖放到会议。</span><span class="sxs-lookup"><span data-stu-id="02714-127">Thus, VTCs can dial into a Skype for Business conference (by dialing the phone number associated with the Call Automated Attendant), but cannot be dragged and dropped into the conference.</span></span>
  
![SfB 中的 VIS 图表](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a><span data-ttu-id="02714-129">功能</span><span class="sxs-lookup"><span data-stu-id="02714-129">Features</span></span>

<span data-ttu-id="02714-130">此服务器角色提供：</span><span class="sxs-lookup"><span data-stu-id="02714-130">This server role provides:</span></span>
  
- <span data-ttu-id="02714-131">第三方视频系统和 Skype for Business Server 部署使用的 H.264 格式之间的转换。</span><span class="sxs-lookup"><span data-stu-id="02714-131">Conversion between the H.264 formats used by 3rd party video systems and the Skype for Business Server deployment.</span></span>
    
- <span data-ttu-id="02714-132">将给定分辨率的单个视频流从 VTC 转换为多个不同分辨率的模拟视频流，以用于 Skype for Business Server 部署。</span><span class="sxs-lookup"><span data-stu-id="02714-132">Conversion of a single video stream at a given resolution from a VTC into multiple simulcast streams of different resolutions for use in the Skype for Business Server deployment.</span></span> <span data-ttu-id="02714-133">这些流可以发送到 AVMCU，然后发送到 Skype for Business Server 终结点和已请求不同分辨率的其他视频系统。</span><span class="sxs-lookup"><span data-stu-id="02714-133">These streams can be sent to the AVMCU and then to Skype for Business Server endpoints and other video systems that have requested different resolutions.</span></span> <span data-ttu-id="02714-134">在 Skype for Business A/V 电话会议中涉及第三方视频系统时，也会使用此转换。</span><span class="sxs-lookup"><span data-stu-id="02714-134">This conversion is also used when the third party video system is involved in a Skype for Business A/V conference call.</span></span> <span data-ttu-id="02714-135">在特定的 VIS 服务器中达到转换代码限制后，对不同分辨率的任何以下请求都只会收到分辨率最低的流。</span><span class="sxs-lookup"><span data-stu-id="02714-135">Once the transcoding limit is reached in a particular VIS server, any following requests for different resolutions will only receive a stream with the lowest resolution.</span></span> 
    
- <span data-ttu-id="02714-136">支持 CUCM 网关与 Skype for Business Server 视频互操作服务器之间的视频 SIP 中继;VTC 继续注册 Cisco 网关，并通过网关发起对 Skype for Business 部署的呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-136">Support for a video SIP trunk between the CUCM gateway and a Skype for Business Server Video Interop Server; VTCs continue to register with the Cisco gateway, and initiate calls to the Skype for Business deployment through the gateway.</span></span> <span data-ttu-id="02714-137">呼叫通过视频 SIP 中继从网关路由到 Skype for Business 视频互操作服务器。</span><span class="sxs-lookup"><span data-stu-id="02714-137">Calls are routed from the gateway to the Skype for Business Video Interop Server over the video SIP trunk.</span></span>
    
- <span data-ttu-id="02714-138">支持具有受支持视频系统的会议室中的用户从该系统拨号加入打开或关闭的会议。</span><span class="sxs-lookup"><span data-stu-id="02714-138">Support for a user in a conference room with a supported video system to dial from that system to join an open or closed conference.</span></span> <span data-ttu-id="02714-139">此呼叫将遍历视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="02714-139">This call will traverse the video SIP trunk.</span></span>
    
- <span data-ttu-id="02714-140">支持会议室中的用户通过受支持的视频系统呼叫 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="02714-140">Support for a user in a conference room with a supported video system to call a Skype for Business client.</span></span> <span data-ttu-id="02714-141">呼叫将遍历 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="02714-141">The call will traverse the SIP trunk.</span></span>
    
- <span data-ttu-id="02714-142">支持从 Skype for Business Server 端或支持的 VTC 系统对点到点呼叫和多点呼叫进行呼叫中间控制，包括静音/取消静音音频、暂停/恢复视频、锁定视频以及保持/取消保留呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-142">Support for mid-call control from the Skype for Business Server side or from the supported VTC system for both point to point and multipoint calls including mute/un-mute audio, pause/resume video, lock video, and hold/un-hold call.</span></span>
    
## <a name="known-limitations"></a><span data-ttu-id="02714-143">已知限制</span><span class="sxs-lookup"><span data-stu-id="02714-143">Known limitations</span></span>

<span data-ttu-id="02714-144">此服务器角色具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="02714-144">This server role has the following limitations:</span></span>
  
- <span data-ttu-id="02714-145">不支持通过视频 SIP 中继从 Skype for Business 部署到 VTC 的新呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-145">New calls from the Skype for Business deployment to the VTCs over the video SIP trunk are not supported.</span></span> <span data-ttu-id="02714-146">.</span><span class="sxs-lookup"><span data-stu-id="02714-146">.</span></span> <span data-ttu-id="02714-147">这意味着视频 SIP 中继仅支持从 VTC 到 Skype for Business 部署的新呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-147">This means that only new calls from the VTCs into the Skype for Business deployment are supported over the video SIP trunk.</span></span> <span data-ttu-id="02714-148">支持的视频系统状态无法通过视频 SIP 中继提供给 VIS。</span><span class="sxs-lookup"><span data-stu-id="02714-148">Presence for the supported video system will not be available over the video SIP trunk to the VIS.</span></span> 
    
- <span data-ttu-id="02714-149">视频 SIP 中继模式仅支持独立的 VIS 池。</span><span class="sxs-lookup"><span data-stu-id="02714-149">Only a standalone VIS pool will be supported for video SIP trunk mode.</span></span>
    
-  <span data-ttu-id="02714-150">VTC 和 VIS 之间通过视频 SIP 中继的通信将支持 TLS + SRTP 或 TCP + RTP。</span><span class="sxs-lookup"><span data-stu-id="02714-150">TLS + SRTP or TCP + RTP will be supported for communications between the VTC and VIS over the video SIP trunk.</span></span>
    
- <span data-ttu-id="02714-151">不支持应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="02714-151">Application sharing is not supported.</span></span> <span data-ttu-id="02714-152">会议室中的 Skype for Business 用户需要通过笔记本电脑加入 Skype for Business 会议 (例如) ，在会议室中未与 VTC 关联的免费监视器之一上显示应用共享屏幕。</span><span class="sxs-lookup"><span data-stu-id="02714-152">A Skype for Business user in the conference room needs to join the Skype for Business conference (via a laptop for example) and display the app sharing screens on one of the free monitors in the conference room not associated with the VTC.</span></span>
    
- <span data-ttu-id="02714-153">不支持 VTC 通过 VIS 加入联盟会议。</span><span class="sxs-lookup"><span data-stu-id="02714-153">The ability for a VTC to join a federated meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="02714-154">不支持 VTC 通过 VIS 加入联机会议。</span><span class="sxs-lookup"><span data-stu-id="02714-154">The ability for a VTC to join an online meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="02714-155">不支持通过 VIS 从 VTC 到 PSTN 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-155">Calls from a VTC to the PSTN via VIS are not supported.</span></span>
    
- <span data-ttu-id="02714-156">不支持通过 VIS 从 PSTN 呼叫 VTC。</span><span class="sxs-lookup"><span data-stu-id="02714-156">Calls from the PSTN to a VTC via VIS are not supported.</span></span>
    
## <a name="resiliency-mechanisms"></a><span data-ttu-id="02714-157">复原机制</span><span class="sxs-lookup"><span data-stu-id="02714-157">Resiliency mechanisms</span></span>
<span data-ttu-id="02714-158"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="02714-158"><a name="resiliency"> </a></span></span>

<span data-ttu-id="02714-159">VIS 支持通过视频 SIP 中继传输的 CUCM 传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-159">The VIS supports incoming calls from a CUCM that are carried over a video SIP trunk.</span></span> <span data-ttu-id="02714-160">可能会丢失上游或下游的连接，因此若要获得可靠的复原能力，请考虑以下两种可能性：</span><span class="sxs-lookup"><span data-stu-id="02714-160">It's possible to lose connectivity either upstream or downstream, so for robust resiliency consider both possibilities:</span></span>
  
1. <span data-ttu-id="02714-161">**VIS 池故障转移** 如果视频网关指向的主 VIS 池关闭，则视频网关在 VIS 池中定义了两个或两 (中继) 恢复。</span><span class="sxs-lookup"><span data-stu-id="02714-161">**VIS Pool Failover** If the main VIS pool that the video gateway points to is down, recovery is possible if the video gateway has defined trunks to two (or more) VIS pools.</span></span> <span data-ttu-id="02714-162">如果视频网关确定它无法对主 VIS 池进行呼叫，它只需将呼叫路由到辅助 VIS 池。</span><span class="sxs-lookup"><span data-stu-id="02714-162">If the video gateway determines it cannot make calls to the primary VIS pool, it simply routes the calls to a secondary VIS pool.</span></span>
    
     ![VIS 池故障转移关系图](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    <span data-ttu-id="02714-164">特定 VIS 池可以具有到多个网关的中继，但通常特定网关无法具有到多个 VIS 池的中继，因此需要执行一个技巧来支持此故障转移：在 DNS 中定义 2 个 FDQN，它们解析为视频网关的相同 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="02714-164">A particular VIS pool can have trunks to multiple gateways, but normally a particular gateway can't have trunks to multiple VIS pools, so a trick needs to be done to support this failover: Define 2 FDQNs in DNS which resolve to the same IP address of a video gateway.</span></span> <span data-ttu-id="02714-165">将每个 FQDN 表示为拓扑文档中的单独视频网关，其中每个视频网关都有一个到不同 VIS 池的中继，现在可以恢复。</span><span class="sxs-lookup"><span data-stu-id="02714-165">Represent each FQDN as a separate video gateway in the Topology Document where each video gateway has a trunk to a different VIS pool, and recovery is now possible.</span></span> <span data-ttu-id="02714-166"> (如果使用 TLS，则多个名称将需要位于视频网关证书的 SAN 中。) </span><span class="sxs-lookup"><span data-stu-id="02714-166">(If TLS is used, the multiple names will need to be in the SAN of the video gateway certificate.)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="02714-167">VIS 仅允许来自拓扑文档中配置的网关的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-167">VIS only allows incoming calls from gateways configured in the Topology Document.</span></span> 
  
2. <span data-ttu-id="02714-168">**前端故障转移** 如果 VIS 池收到来自 CUCM 的呼叫，但无法访问其主下一跃点注册器或前端池，则呼叫将路由到备份前端池。</span><span class="sxs-lookup"><span data-stu-id="02714-168">**Front End failover** If a VIS pool receives a call from CUCM but cannot reach its primary next-hop Registrar or Front End pool, calls are routed to a backup Front End pool.</span></span>
    
     ![前端故障转移关系图](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    <span data-ttu-id="02714-170">VIS 将跟踪其主前端池及其备份前端池的状态 (该设置位于拓扑文档库的注册器服务的备份设置) 。</span><span class="sxs-lookup"><span data-stu-id="02714-170">The VIS will keep track of the status of its primary Front End pool and its backup Front End pool (the setting is found in the backup setting for the Registrar service in the Topology Document).</span></span> <span data-ttu-id="02714-171">它每分钟向两个池发送一次"选项"轮询，如果连续五次失败，VIS 会假定特定前端池出现故障。</span><span class="sxs-lookup"><span data-stu-id="02714-171">It sends Options polls once a minute to both pools, and if there are five consecutive failures the VIS assumes that a particular Front End pool is down.</span></span> <span data-ttu-id="02714-172">如果主前端池标记为"关闭"且有可用的配置备份，VIS 将新呼叫从网关发送到备份前端池。</span><span class="sxs-lookup"><span data-stu-id="02714-172">If the primary Front End pool is marked as down and there is an available configured backup the VIS sends new calls from the gateway to the backup Front End pool.</span></span> <span data-ttu-id="02714-173">主前端池返回后，VIS 将恢复使用主前端池进行新呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-173">Once the primary Front End pool comes back, the VIS will resume using the primary Front End pool for new calls.</span></span>
    
    <span data-ttu-id="02714-174">VIS 还将为来自视频 SIP 中继的呼叫实现 10 秒计时器。</span><span class="sxs-lookup"><span data-stu-id="02714-174">The VIS will also implement a 10 second timer for calls from the video SIP trunk.</span></span> <span data-ttu-id="02714-175">如果主下一跃点前端池用于来自视频 SIP 中继的呼叫，并且主下一跃点前端池未应答某些 SIP 消息 (包括 100 尝试) 到在此计时器值内发送给它的邀请，则应该尝试呼叫的备份下一跃点代理（如果已配置）。</span><span class="sxs-lookup"><span data-stu-id="02714-175">If the primary next-hop Front End pool was used for a call from the video SIP trunk, and the primary next-hop Front End pool did not answer with some SIP message (including 100 Trying) to the Invite sent to it within this timer value, the backup next-hop proxy for the call should be tried if configured.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="02714-176">如果首先尝试了备份下一跃点，则下一步将不会尝试主跃点。</span><span class="sxs-lookup"><span data-stu-id="02714-176">If the backup next hop was tried first, the primary will not be tried next.</span></span> 
  
    <span data-ttu-id="02714-177">管理员还可使用 Windows PowerShell 故障转移命令强制 VIS 使用备份前端池，例如，当主前端池上必须执行维护时。</span><span class="sxs-lookup"><span data-stu-id="02714-177">The admin could also use the Windows PowerShell failover command to force VIS to use the backup Front End pool, for example, when maintenance has to be performed on the primary Front End pool.</span></span>
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a><span data-ttu-id="02714-178">语音和视频中继共存到同一网关对等方</span><span class="sxs-lookup"><span data-stu-id="02714-178">Co-existence of Voice and Video Trunks to the Same Gateway Peer</span></span>
<span data-ttu-id="02714-179"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="02714-179"><a name="resiliency"> </a></span></span>

<span data-ttu-id="02714-180">Skype for Business Server 支持语音和视频 SIP 中继使用相同的网关对等方。</span><span class="sxs-lookup"><span data-stu-id="02714-180">Skype for Business Server supports having voice and video SIP trunks use the same gateway peer.</span></span> <span data-ttu-id="02714-181">因此，同一 CUCM 部署可以具有到中介服务器的语音 SIP 中继和到 VIS 的视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="02714-181">So the same CUCM deployment could have voice SIP trunks to the Mediation Server and video SIP trunks to VIS.</span></span>
  
- <span data-ttu-id="02714-182">PSTN 网关将需要使用语音 SIP 中继的拓扑文档中的特定 FQDN 进行定义。</span><span class="sxs-lookup"><span data-stu-id="02714-182">A PSTN Gateway will need to be defined with a particular FQDN in the Topology Document for the voice SIP trunks.</span></span>
    
- <span data-ttu-id="02714-183">PSTN 网关的对等方将是中介服务器。</span><span class="sxs-lookup"><span data-stu-id="02714-183">The peer to the PSTN Gateway will be the Mediation Server.</span></span>
    
- <span data-ttu-id="02714-184">如有必要，可以定义从 PSTN 网关到多个中介服务器池的多个语音中继。</span><span class="sxs-lookup"><span data-stu-id="02714-184">Multiple voice trunks can be defines spanning from a PSTN Gateway to multiple Mediation Server pools if necessary.</span></span>
    
- <span data-ttu-id="02714-185">视频网关需要在拓扑文档中为与 PSTN 网关具有相同的 FQDN 的视频 SIP 中继定义。</span><span class="sxs-lookup"><span data-stu-id="02714-185">A Video Gateway will need to be defined in the Topology Document for the video SIP trunk with the same FQDN as for the PSTN Gateway.</span></span>
    
- <span data-ttu-id="02714-186">视频网关的对等方将为 VIS。</span><span class="sxs-lookup"><span data-stu-id="02714-186">The peer to the Video Gateway will be VIS.</span></span>
    
- <span data-ttu-id="02714-187">可以定义从视频网关到特定 VIS 池的单个视频中继。</span><span class="sxs-lookup"><span data-stu-id="02714-187">A single video trunk can be defined from a Video Gateway to a particular VIS pool.</span></span>
    
- <span data-ttu-id="02714-188">需要将 CUCM 配置为通过语音中继和视频中继正确路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-188">CUCM will need to be configured to correctly route calls over the voice trunk vs. the video trunk.</span></span> <span data-ttu-id="02714-189">例如，从 VTC 拨号时，可能会使用特殊的拨号前缀;CUCM 可以将此拨号前缀与对 VIS 的呼叫关联，相应的转换规则会从对 VIS 的 SIP 邀请中去除此前缀。</span><span class="sxs-lookup"><span data-stu-id="02714-189">For example, a special dial prefix could be used when dialing from the VTC; CUCM could associate this dial prefix with calls to VIS, and appropriate translation rules would strip this prefix from the SIP Invite to VIS.</span></span>
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a><span data-ttu-id="02714-190">在 Skype for Business 版本中与 Lync 早期版本共存的 VIS</span><span class="sxs-lookup"><span data-stu-id="02714-190">Co-existence of VIS in the Skype for Business Release with Previous Releases of Lync</span></span>
<span data-ttu-id="02714-191"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="02714-191"><a name="resiliency"> </a></span></span>

<span data-ttu-id="02714-192">VIS 只能部署为 Skype for Business 部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="02714-192">VIS can only be deployed as part of Skype for Business deployment.</span></span> <span data-ttu-id="02714-193">它可以与 Lync 2013 会议以及作为现有部署的一部分的客户端进行互操作;在这种情况下，VIS 池将需要是 Skype for Business 部署的一部分，其中包括作为 VIS 池的下一跃点注册器/FE 池。</span><span class="sxs-lookup"><span data-stu-id="02714-193">It can interoperate with Lync 2013 conferences and clients that are a part of an existing deployment; in those cases, the VIS pool will need to be part of a Skype for Business deployment that includes a Registrar/FE pool that is the next-hop for the VIS pool.</span></span>
  
<span data-ttu-id="02714-194">VIS 不支持在 RTV 和 H.264 之间进行转码。</span><span class="sxs-lookup"><span data-stu-id="02714-194">VIS does not support transcoding between RTV and H.264.</span></span> <span data-ttu-id="02714-195">Lync 2013 之前客户端与会议中的 VTC 参与者之间没有视频互操作性。</span><span class="sxs-lookup"><span data-stu-id="02714-195">There is no video interoperability between pre-Lync 2013 clients and VTC participants in a conference.</span></span>
  
<span data-ttu-id="02714-196">在会议拥有 Lync 2013 之前客户端将导致移动客户端使用 RTV 进行发送，从而导致当移动客户端成为主要扬声器时，VTC 不会接收任何视频。</span><span class="sxs-lookup"><span data-stu-id="02714-196">Having pre-Lync 2013 clients in a conference will cause mobile clients to send using RTV resulting in VTCs receiving no video when the mobile client becomes the dominant speaker.</span></span>
  
<span data-ttu-id="02714-197">为了使 Lync 2013 正确使用作为 Skype for Business 部署的一部分的 VIS，Lync 2013 需要应用相应的 CU，以便升级 Lync 2013 客户端、CAA 和 AVMCU 以使用 VIS。</span><span class="sxs-lookup"><span data-stu-id="02714-197">In order for Lync 2013 to work correctly with VIS that is part of a Skype for Business deployment, Lync 2013 needs the appropriate CU to be applied that upgrades the Lync 2013 client, CAA, and AVMCU to work with VIS.</span></span>
  
<span data-ttu-id="02714-198">VIS 与 Lync 2013 和 Skype for Business 桌面客户端的互操作性已经过测试且受支持。</span><span class="sxs-lookup"><span data-stu-id="02714-198">Interoperability of VIS with Lync 2013 and Skype for Business desktop clients has been tested and is supported.</span></span>
  
<span data-ttu-id="02714-199">VIS 与非桌面 (Android、Ipad、Iphone、Windows Phone、LMX 等 ) SKYPE for Business 客户端在 VIS 发布时可从适用的应用应用商店获得互操作性已经过测试，并且受支持。</span><span class="sxs-lookup"><span data-stu-id="02714-199">Interoperability of VIS with non-desktop (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype for Business clients available from the applicable Apps Store at the time of VIS release has been tested and is supported.</span></span>
  
## <a name="recovery-from-packet-loss-via-fec"></a><span data-ttu-id="02714-200">通过 FEC 从数据包丢失恢复</span><span class="sxs-lookup"><span data-stu-id="02714-200">Recovery from Packet Loss via FEC</span></span>
<span data-ttu-id="02714-201"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="02714-201"><a name="resiliency"> </a></span></span>

<span data-ttu-id="02714-202">可以打开 FEC，帮助从数据包丢失中恢复。</span><span class="sxs-lookup"><span data-stu-id="02714-202">FEC can be turned on to aid in recovery from packet loss.</span></span> <span data-ttu-id="02714-203">如果打开，将在 VIS 到 VTC 方向使用 50% 以上的视频带宽。</span><span class="sxs-lookup"><span data-stu-id="02714-203">If turned on, 50% more video bandwidth will be used in the VIS to VTC direction.</span></span>
  
## <a name="vis-sizing-and-transcoding-costs"></a><span data-ttu-id="02714-204">VIS 大小调整和转换成本</span><span class="sxs-lookup"><span data-stu-id="02714-204">VIS Sizing and Transcoding Costs</span></span>
<span data-ttu-id="02714-205"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="02714-205"><a name="resiliency"> </a></span></span>

<span data-ttu-id="02714-206">将单个视频流从 Cisco VTC 转换到多个模拟视频流使用 CPU 容量。</span><span class="sxs-lookup"><span data-stu-id="02714-206">Transcoding the single video streams from the Cisco VTC to multiple simulcast streams uses CPU capacity.</span></span> <span data-ttu-id="02714-207">在运行与 Lync 2013 建议的 FE 平台等效的单个 VIS 中，大约 16 个 VTC 可以将视频转码为 (假定每个 VTC 中的 720p 视频流在 720p、360p 和 180p) 中转换为 3 个单独的模拟视频流。</span><span class="sxs-lookup"><span data-stu-id="02714-207">Approximately 16 VTCs can have their video transcoded (assuming a 720p video stream from each VTC is transcoded into 3 separate simulcast streams at 720p, 360p, and 180p) in a single VIS running on the equivalent of the Lync 2013 recommended FE platform.</span></span> <span data-ttu-id="02714-208">如果关闭转码，这将节省 VIS CPU。</span><span class="sxs-lookup"><span data-stu-id="02714-208">If Transcoding is turned off, this will save on VIS CPU.</span></span> <span data-ttu-id="02714-209">但是，VIS 从 VTC 请求的视频图像将是满足 Skype for Business 端的所有接收器的最低通用分辨率。</span><span class="sxs-lookup"><span data-stu-id="02714-209">However, the video image requested by VIS from the VTC will be the lowest common resolution to satisfy all receivers on the Skype for Business side.</span></span> <span data-ttu-id="02714-210">请注意，即使关闭代码转换，当 Skype for Business 客户端请求 VTC 无法发送的某些低分辨率时，也可能激活代码转换。</span><span class="sxs-lookup"><span data-stu-id="02714-210">Note that even with transcoding off, transcoding may be activated when Skype for Business clients request certain low resolutions that VTCs cannot send.</span></span>
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a><span data-ttu-id="02714-211">从视频网关到 VIS 的呼叫分布</span><span class="sxs-lookup"><span data-stu-id="02714-211">Call Distribution from the Video Gateway to VIS</span></span>
<span data-ttu-id="02714-212"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="02714-212"><a name="resiliency"> </a></span></span>

<span data-ttu-id="02714-213">通过 CUCM 分布机制之一完成分发：</span><span class="sxs-lookup"><span data-stu-id="02714-213">Distribution is accomplished via one of the CUCM distribution mechanisms:</span></span>
  
- <span data-ttu-id="02714-214">使用 DNS 动态。</span><span class="sxs-lookup"><span data-stu-id="02714-214">Dynamically using DNS.</span></span>
    
- <span data-ttu-id="02714-215">在 CUCM 端，可以定义单个中继，其中每个中继在 VIS 池中的不同服务器上终止。</span><span class="sxs-lookup"><span data-stu-id="02714-215">On the CUCM side, you can define individual trunks, where each trunk terminates on a different server in the VIS pool.</span></span> <span data-ttu-id="02714-216">CUCM 将跨不同的中继路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="02714-216">CUCM will route calls across the different trunks.</span></span>
    
## <a name="no-hybrid-interoperability"></a><span data-ttu-id="02714-217">无混合互操作性</span><span class="sxs-lookup"><span data-stu-id="02714-217">No Hybrid Interoperability</span></span>
<span data-ttu-id="02714-218"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="02714-218"><a name="resiliency"> </a></span></span>

<span data-ttu-id="02714-219">Skype for Business 不支持 VTC 通过本地 VIS 加入联机会议。</span><span class="sxs-lookup"><span data-stu-id="02714-219">Support for VTCs joining online meetings via on-premises VIS is not part of Skype for Business.</span></span>
  
## <a name="no-federation-support"></a><span data-ttu-id="02714-220">无联合身份验证支持</span><span class="sxs-lookup"><span data-stu-id="02714-220">No Federation Support</span></span>
<span data-ttu-id="02714-221"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="02714-221"><a name="resiliency"> </a></span></span>

<span data-ttu-id="02714-222">支持 VTC 通过 VIS 加入联盟会议不是 Skype for Business 的一部分。</span><span class="sxs-lookup"><span data-stu-id="02714-222">Support for VTCs joining federated meetings via VIS is not part of Skype for Business.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="02714-223">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02714-223">See also</span></span>
<span data-ttu-id="02714-224"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="02714-224"><a name="resiliency"> </a></span></span>

[<span data-ttu-id="02714-225">在 Skype for Business Server 中部署视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="02714-225">Deploy Video Interop Server in Skype for Business Server</span></span>](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
