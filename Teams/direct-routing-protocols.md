---
title: 电话系统直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: 直接路由协议
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470c402ebfd4e70955f4e864d45dbaaca476dfd
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065622"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="d5cfb-103">直接路由定义和 RFC 标准</span><span class="sxs-lookup"><span data-stu-id="d5cfb-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="d5cfb-104">本文介绍 Microsoft Phone 系统直接路由如何实现 RFC 标准协议。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="d5cfb-105">本文适用于负责配置本地会话边界控制器（SBC）和会话初始协议（SIP）代理服务之间的连接的语音管理员。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="d5cfb-106">客户 SBC 接口，其中包含 Microsoft 团队后端中的以下组件：</span><span class="sxs-lookup"><span data-stu-id="d5cfb-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="d5cfb-107">用于发送信号**的 SIP 代理**。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="d5cfb-108">这是直接路由的面向 Internet 的组件，用于处理 SBCs 和直接路由之间的 SIP （TLS）连接。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="d5cfb-109">媒体**处理**程序。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-109">**The media processors** for media.</span></span> <span data-ttu-id="d5cfb-110">这是面向 Internet 的直接路由组件，用于处理媒体流量。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="d5cfb-111">此组件使用 SRTP 和 SRTCP 协议。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="d5cfb-112">有关直接路由的详细信息，请参阅[手机系统直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="d5cfb-113">有关直接路由如何实现 SIP 协议的详细信息，请参阅[直接路由 SIP 协议](direct-routing-protocols-sip.md)。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="d5cfb-114">RFC 标准</span><span class="sxs-lookup"><span data-stu-id="d5cfb-114">RFC standards</span></span>

<span data-ttu-id="d5cfb-115">直接路由符合 RFC 标准。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="d5cfb-116">连接到直接路由的 SBC 还必须遵守以下 Rfc （或其后续任务）。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="d5cfb-117">适用于支持非媒体绕过模式的设备的标准</span><span class="sxs-lookup"><span data-stu-id="d5cfb-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="d5cfb-118">以下标准适用于仅支持非媒体绕过模式的设备：</span><span class="sxs-lookup"><span data-stu-id="d5cfb-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="d5cfb-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261)：会话初始协议</span><span class="sxs-lookup"><span data-stu-id="d5cfb-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="d5cfb-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325)。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="d5cfb-121">在受信任的网络内断言标识的会话初始协议的专用扩展--有关处理 P 声明标识标头的部分。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="d5cfb-122">直接路由发送带有隐私 ID 标头的 P 声明标识。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="d5cfb-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt)针对所需历史记录信息的会话初始协议（SIP）的扩展。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="d5cfb-124">另请参阅：路由 SIP 协议说明了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="d5cfb-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)会话初始协议，即 "按机制"</span><span class="sxs-lookup"><span data-stu-id="d5cfb-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="d5cfb-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt)会话初始协议（SIP） "替换" 标头</span><span class="sxs-lookup"><span data-stu-id="d5cfb-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="d5cfb-127">[RFC 6337](https://tools.ietf.org/html/rfc6337)优惠/应答模型的会话初始协议（SIP）使用。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="d5cfb-128">请参阅 "与 RFC 的偏差" 部分。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="d5cfb-129">[Rfc 3711](https://tools.ietf.org/html/rfc3711)和[rfc 4771](https://tools.ietf.org/html/rfc4771)。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="d5cfb-130">使用 SRTP 保护 RTP 流量。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="d5cfb-131">SBC 必须能够使用 SDES 建立密钥。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="d5cfb-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt)适用于 RTP/RTCP 复用的会话描述协议（SDP）优惠/答案说明</span><span class="sxs-lookup"><span data-stu-id="d5cfb-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="d5cfb-133">适用于支持媒体绕过模式的设备的标准</span><span class="sxs-lookup"><span data-stu-id="d5cfb-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="d5cfb-134">除了列出的适用于非绕过模式的标准，以下标准用于媒体绕过模式：</span><span class="sxs-lookup"><span data-stu-id="d5cfb-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="d5cfb-135">[适用于媒体绕过的 RFC 5245 交互式连接建立（ICE）](https://tools.ietf.org/html/rfc5245)。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="d5cfb-136">SBC 必须支持以下内容：</span><span class="sxs-lookup"><span data-stu-id="d5cfb-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="d5cfb-137">冰精简-团队客户是完全 ICE 客户端</span><span class="sxs-lookup"><span data-stu-id="d5cfb-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="d5cfb-138">[ICE 重启](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="d5cfb-139">了解有关 ICE 重启的更多信息使用案例和示例在 ICE 重启：将媒体绕过呼叫转移到不支持媒体绕过的终结点</span><span class="sxs-lookup"><span data-stu-id="d5cfb-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="d5cfb-140">[RFC rfc 5589 会话初始协议（SIP）呼叫控制-转移](https://tools.ietf.org/html/rfc5589)。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="d5cfb-141">[RFC 3960 早期媒体和铃声生成在会话启动协议（SIP）中](https://tools.ietf.org/html/rfc3960)，请参阅3.1、分叉和3.2 部分、铃声生成</span><span class="sxs-lookup"><span data-stu-id="d5cfb-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="d5cfb-142">适用于 NAT 的 RFC 5389 会话遍历实用工具（STUN）</span><span class="sxs-lookup"><span data-stu-id="d5cfb-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="d5cfb-143">RFC 5766 遍历 NAT 周围的中继（转换）：用于 NAT 的会话遍历实用工具的中继扩展（STUN）</span><span class="sxs-lookup"><span data-stu-id="d5cfb-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="d5cfb-144">适用于支持将位置信息传达给 E911 提供商的标准</span><span class="sxs-lookup"><span data-stu-id="d5cfb-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="d5cfb-145">RFC 6442，位置 Conveyance 会话启动协议的位置</span><span class="sxs-lookup"><span data-stu-id="d5cfb-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="d5cfb-146">RFC 的偏差</span><span class="sxs-lookup"><span data-stu-id="d5cfb-146">Deviations from the RFC's</span></span>

<span data-ttu-id="d5cfb-147">下表列出了 Microsoft 实施 SIP 或媒体堆栈的 RFC 部分与标准的不同：</span><span class="sxs-lookup"><span data-stu-id="d5cfb-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="d5cfb-148">RFC 和分区</span><span class="sxs-lookup"><span data-stu-id="d5cfb-148">RFC and sections</span></span> | <span data-ttu-id="d5cfb-149">说明</span><span class="sxs-lookup"><span data-stu-id="d5cfb-149">Description</span></span> | <span data-ttu-id="d5cfb-150">差值</span><span class="sxs-lookup"><span data-stu-id="d5cfb-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="d5cfb-151">RFC 6337，第5.3 节保留和恢复媒体</span><span class="sxs-lookup"><span data-stu-id="d5cfb-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="d5cfb-152">RFC 允许使用 "a = 非活动"，"a = sendonly"，a = recvonly "将呼叫置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="d5cfb-153">SIP 代理仅支持 "a = 非活动"，并且不知道 SBC 是否发送 "a = sendonly" 或 "a = recvonly"。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="d5cfb-154">在 c = 0.0.0.0 的情况下接收 SDP 的 RFC 6337，第5.4 部分</span><span class="sxs-lookup"><span data-stu-id="d5cfb-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="d5cfb-155">[RFC3264](https://tools.ietf.org/html/rfc3264)要求代理能够接收连接地址为0.0.0.0 的 SDP，在这种情况下，不应将 RTP 和 RTCP 发送到对等。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="d5cfb-156">SIP 代理不支持此选项。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="d5cfb-157">运行模式</span><span class="sxs-lookup"><span data-stu-id="d5cfb-157">Operational modes</span></span>

<span data-ttu-id="d5cfb-158">直接路由有两种操作模式：</span><span class="sxs-lookup"><span data-stu-id="d5cfb-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="d5cfb-159">如果**没有媒体旁路**，则在团队客户端、媒体处理器和 SBC 之间的所有 RTP 通信流。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="d5cfb-160">在**媒体旁路**中，所有 RTP 媒体都在团队终结点和 SBC 之间流动。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="d5cfb-161">请注意，SIP 流量始终通过 SIP 代理流出。</span><span class="sxs-lookup"><span data-stu-id="d5cfb-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
