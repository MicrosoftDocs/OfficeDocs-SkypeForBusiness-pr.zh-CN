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
f1.keywords:
- NOCSH
description: 直接路由协议
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835022"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="98bbc-103">直接路由 - 定义和 RFC 标准</span><span class="sxs-lookup"><span data-stu-id="98bbc-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="98bbc-104">本文介绍如何Microsoft 电话直接路由实现 RFC 标准协议。</span><span class="sxs-lookup"><span data-stu-id="98bbc-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="98bbc-105">本文面向负责配置本地会话边界控制器 (SBC) 与会话启动协议 (SIP) 代理服务之间的连接的语音管理员。</span><span class="sxs-lookup"><span data-stu-id="98bbc-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="98bbc-106">客户 SBC 与后端中的以下Microsoft Teams接口：</span><span class="sxs-lookup"><span data-stu-id="98bbc-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="98bbc-107">**用于发送信号** 的 SIP 代理。</span><span class="sxs-lookup"><span data-stu-id="98bbc-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="98bbc-108">这是直接路由的面向 Internet 的组件，用于处理 SIP (TLS) SDC 和直接路由之间的连接。</span><span class="sxs-lookup"><span data-stu-id="98bbc-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="98bbc-109">**媒体的** 媒体处理器。</span><span class="sxs-lookup"><span data-stu-id="98bbc-109">**The media processors** for media.</span></span> <span data-ttu-id="98bbc-110">这是直接路由的面向 Internet 的组件，用于处理媒体流量。</span><span class="sxs-lookup"><span data-stu-id="98bbc-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="98bbc-111">此组件使用 SRTP 和 SRTCP 协议。</span><span class="sxs-lookup"><span data-stu-id="98bbc-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="98bbc-112">有关直接路由详细信息，请参阅 电话系统[直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="98bbc-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="98bbc-113">有关直接路由如何实现 SIP 协议的信息，请参阅 [直接路由 - SIP 协议](direct-routing-protocols-sip.md)。</span><span class="sxs-lookup"><span data-stu-id="98bbc-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="98bbc-114">RFC 标准</span><span class="sxs-lookup"><span data-stu-id="98bbc-114">RFC standards</span></span>

<span data-ttu-id="98bbc-115">直接路由符合 RFC 标准。</span><span class="sxs-lookup"><span data-stu-id="98bbc-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="98bbc-116">连接到直接路由的 SBC 还必须符合以下 RFC (及其后续) 。</span><span class="sxs-lookup"><span data-stu-id="98bbc-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="98bbc-117">适用于支持非媒体旁路模式的设备的标准</span><span class="sxs-lookup"><span data-stu-id="98bbc-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="98bbc-118">以下标准适用于仅支持非媒体旁路模式的设备：</span><span class="sxs-lookup"><span data-stu-id="98bbc-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="98bbc-119">[RFC 3261 SIP：](https://tools.ietf.org/html/rfc3261)会话启动协议</span><span class="sxs-lookup"><span data-stu-id="98bbc-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="98bbc-120">[RFC 3325。](https://www.ietf.org/rfc/rfc3325)</span><span class="sxs-lookup"><span data-stu-id="98bbc-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="98bbc-121">受信任网络内断言标识的会话启动协议的专用扩展 -- 有关处理 P-Asserted-Identity 标头的部分。</span><span class="sxs-lookup"><span data-stu-id="98bbc-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="98bbc-122">直接路由发送包含隐私 ID 标头的 P-Asserted-Identity。</span><span class="sxs-lookup"><span data-stu-id="98bbc-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="98bbc-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) SIP 会话启动协议扩展 (SIP) 历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="98bbc-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="98bbc-124">有关详细信息，另请参阅：路由 SIP 协议说明。</span><span class="sxs-lookup"><span data-stu-id="98bbc-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="98bbc-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 会话启动协议Referred-By机制</span><span class="sxs-lookup"><span data-stu-id="98bbc-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="98bbc-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) SIP 会话启动协议 (SIP) "Replaces"标头</span><span class="sxs-lookup"><span data-stu-id="98bbc-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="98bbc-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) 会话启动协议 (SIP) /应答模型的使用情况。</span><span class="sxs-lookup"><span data-stu-id="98bbc-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="98bbc-128">请参阅"与 RFC 的偏差"部分。</span><span class="sxs-lookup"><span data-stu-id="98bbc-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="98bbc-129">[RFC 3711](https://tools.ietf.org/html/rfc3711)和[RFC 4771。](https://tools.ietf.org/html/rfc4771)</span><span class="sxs-lookup"><span data-stu-id="98bbc-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="98bbc-130">使用 SRTP 保护 RTP 流量。</span><span class="sxs-lookup"><span data-stu-id="98bbc-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="98bbc-131">SBC 必须能够使用 SDES 建立密钥。</span><span class="sxs-lookup"><span data-stu-id="98bbc-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="98bbc-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) 会话说明协议 (SDP) RTP/RTCP 多路复用产品/解答说明</span><span class="sxs-lookup"><span data-stu-id="98bbc-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="98bbc-133">适用于支持媒体旁路模式的设备的标准</span><span class="sxs-lookup"><span data-stu-id="98bbc-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="98bbc-134">除了列为适用于非绕过模式的标准外，以下标准还用于媒体旁路模式：</span><span class="sxs-lookup"><span data-stu-id="98bbc-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="98bbc-135">[RFC 5245 Interactive Connectivity Establishment (ICE) 用于媒体旁路](https://tools.ietf.org/html/rfc5245)。</span><span class="sxs-lookup"><span data-stu-id="98bbc-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="98bbc-136">SBC 必须支持以下各项：</span><span class="sxs-lookup"><span data-stu-id="98bbc-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="98bbc-137">ICE Lite - Teams是完整的 ICE 客户端</span><span class="sxs-lookup"><span data-stu-id="98bbc-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="98bbc-138">[ICE 重启](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。</span><span class="sxs-lookup"><span data-stu-id="98bbc-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="98bbc-139">有关 ICE 重启用例和示例，请参阅 ICE 重启：传输到不支持媒体旁路的终结点的媒体旁路呼叫</span><span class="sxs-lookup"><span data-stu-id="98bbc-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="98bbc-140">[RFC RFC 5589 会话启动协议 (SIP) 呼叫控制 – 传输。](https://tools.ietf.org/html/rfc5589)</span><span class="sxs-lookup"><span data-stu-id="98bbc-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="98bbc-141">[RFC 3960 ](https://tools.ietf.org/html/rfc3960)会话启动协议 (SIP) 中的 RFC 3960 早期媒体和铃声生成，请参阅第 3.1、Forking 和 3.2 部分：铃声生成</span><span class="sxs-lookup"><span data-stu-id="98bbc-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="98bbc-142">RFC 5389 会话遍历实用工具，适用于 NAT (STUN) </span><span class="sxs-lookup"><span data-stu-id="98bbc-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="98bbc-143">RFC 5766 使用围绕 NAT (TURN) 的中继进行遍历：中继扩展到 NAT (STUN) </span><span class="sxs-lookup"><span data-stu-id="98bbc-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="98bbc-144">适用于支持向 E911 提供商传达位置信息的标准</span><span class="sxs-lookup"><span data-stu-id="98bbc-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="98bbc-145">RFC 6442，会话启动协议的位置传达</span><span class="sxs-lookup"><span data-stu-id="98bbc-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="98bbc-146">与 RFC 的偏差</span><span class="sxs-lookup"><span data-stu-id="98bbc-146">Deviations from the RFC's</span></span>

<span data-ttu-id="98bbc-147">下表列出了 RFC 协议 (部分) 其中 Microsoft 对 SIP 或媒体堆栈的实现偏离标准：</span><span class="sxs-lookup"><span data-stu-id="98bbc-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="98bbc-148">RFC 和节</span><span class="sxs-lookup"><span data-stu-id="98bbc-148">RFC and sections</span></span> | <span data-ttu-id="98bbc-149">说明</span><span class="sxs-lookup"><span data-stu-id="98bbc-149">Description</span></span> | <span data-ttu-id="98bbc-150">偏差</span><span class="sxs-lookup"><span data-stu-id="98bbc-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="98bbc-151">RFC 6337，第 5.3 节媒体保留和恢复</span><span class="sxs-lookup"><span data-stu-id="98bbc-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="98bbc-152">RFC 允许使用"a=inactive"、"a=sendonly"、"a=recvonly"来保持呼叫。</span><span class="sxs-lookup"><span data-stu-id="98bbc-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="98bbc-153">SIP 代理仅支持"a=inactive"，并且不知道 SBC 是发送"a=sendonly"还是"a=recvonly"。</span><span class="sxs-lookup"><span data-stu-id="98bbc-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="98bbc-154">RFC 6337，第 5.4 节"使用 c=0.0.0.0 接收 SDP 的行为</span><span class="sxs-lookup"><span data-stu-id="98bbc-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="98bbc-155">[RFC3264](https://tools.ietf.org/html/rfc3264) 要求代理能够接收连接地址为 0.0.0.0 的 SDP，在这种情况下，这意味着不应将 RTP 和 RTCP 发送到对等方。</span><span class="sxs-lookup"><span data-stu-id="98bbc-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="98bbc-156">SIP 代理不支持此选项。</span><span class="sxs-lookup"><span data-stu-id="98bbc-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="98bbc-157">操作模式</span><span class="sxs-lookup"><span data-stu-id="98bbc-157">Operational modes</span></span>

<span data-ttu-id="98bbc-158">直接路由有两种操作模式：</span><span class="sxs-lookup"><span data-stu-id="98bbc-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="98bbc-159">**无需绕过媒体**，所有 RTP 流量Teams客户端、媒体处理器和 SBC 之间流动。</span><span class="sxs-lookup"><span data-stu-id="98bbc-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="98bbc-160">**使用媒体旁** 路，所有 RTP 媒体Teams终结点和 SBC 之间流动。</span><span class="sxs-lookup"><span data-stu-id="98bbc-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="98bbc-161">请注意，SIP 流量始终通过 SIP 代理流动。</span><span class="sxs-lookup"><span data-stu-id="98bbc-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
