---
title: 电话系统直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
ms.openlocfilehash: 08b022799b2c8bf80ee30cbb0a5ef3e74f0a29e1
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065662"
---
# <a name="overview"></a><span data-ttu-id="c1bc0-103">概述</span><span class="sxs-lookup"><span data-stu-id="c1bc0-103">Overview</span></span>

<span data-ttu-id="c1bc0-104">本文介绍直接路由如何支持使用适用于 ICE 精简的会话边界控制器（SBC）的媒体旁路，如[RFC 5245](https://tools.ietf.org/html/rfc5245)中所述。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="c1bc0-105">本文面向负责配置本地 SBC 和 SIP 代理服务之间的连接的语音管理员。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="c1bc0-106">本文概述了 "ICE" 方案和互操作性要求。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="c1bc0-107">本文介绍邮件格式和必需的状态机转换，以确保可靠的呼叫和媒体流。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="c1bc0-108">术语</span><span class="sxs-lookup"><span data-stu-id="c1bc0-108">Terminology</span></span>

- <span data-ttu-id="c1bc0-109">第一名 Hello-呼叫方和被叫方的第一字。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="c1bc0-110">必须确保所有努力都确保来自终结点的第一个数据包可可靠地针对大多数使用案例进行提供。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="c1bc0-111">分叉-如果被呼叫方在多台设备上可用（例如，团队用户可能登录到适用于 Windows 的团队和适用于 Android 或 iPhone 的团队），则可能会将提供给多个被调用方终结点发送给这些终结点。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="c1bc0-112">临时应答（183）-被呼叫方终结点以实现更快的通话设置使用建立媒体流所需的候选项和密钥发送答案。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="c1bc0-113">这是为了预测用户可能会从该特定被叫方实例应答调用（200OK）。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="c1bc0-114">通过分叉，呼叫方应准备好接收多个临时的答案。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="c1bc0-115">重新邀请–提供由 ICE 控制终结点选择的最终候选项。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="c1bc0-116">这将具有 a = 远程候选属性，以解决处理多个派生的任何争用条件。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="c1bc0-117">团队终结点-这可能是服务器（媒体处理器、传输中继）或团队客户端。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="c1bc0-118">邮件格式</span><span class="sxs-lookup"><span data-stu-id="c1bc0-118">Message format</span></span>

<span data-ttu-id="c1bc0-119">团队基础结构遵循 RFC 5245 的冰精简。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="c1bc0-120">这意味着所有 STUN 消息都将符合[RFC 5389](https://tools.ietf.org/html/rfc5389)。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="c1bc0-121">由 RFC 5389 所需的 SBCs 必须忽略其不识别的任何 STUN 属性，并继续处理具有已知属性的消息。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="c1bc0-122">如果收到任何格式错误的数据包，则数据包必须在不影响媒体会话建立的情况下丢弃。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="c1bc0-123">ICE 精简要求</span><span class="sxs-lookup"><span data-stu-id="c1bc0-123">ICE Lite requirements</span></span>

<span data-ttu-id="c1bc0-124">本部分简要介绍了 ICE 精简的要求。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="c1bc0-125">候选收集</span><span class="sxs-lookup"><span data-stu-id="c1bc0-125">Candidate gathering</span></span>

<span data-ttu-id="c1bc0-126">SBC 必须仅提供一个可公开访问的候选项。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="c1bc0-127">目前，仅支持 IPV4 候选人。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="c1bc0-128">连接检查</span><span class="sxs-lookup"><span data-stu-id="c1bc0-128">Connectivity checks</span></span>

<span data-ttu-id="c1bc0-129">ICE Lite 实现必须响应收到的任何连接检查。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="c1bc0-130">ICE Lite 终结点不得发送任何连接检查请求。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="c1bc0-131">（如果连接检查发生冲突，则完整的实现将响应，这可能会导致发现意外的对等派生候选，并且可能会导致调用失败。）</span><span class="sxs-lookup"><span data-stu-id="c1bc0-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="c1bc0-132">Nominations</span><span class="sxs-lookup"><span data-stu-id="c1bc0-132">Nominations</span></span>

<span data-ttu-id="c1bc0-133">ICE 完全实现终结点将始终为控制终结点，并且将遵循 "Regular" nominations 来选择要用于媒体流的最终候选项。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="c1bc0-134">ICE Lite 终结点可以使用 nominations 结束用于媒体和完成通话建立的路径。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="c1bc0-135">注意：在具有对等终结点的发送183临时答案的分叉情况下，SBC 必须准备好响应来自多个终结点的检查，并且还必须准备好从多个终结点 nominations，如果 nominations 在200OK 之前发生。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="c1bc0-136">根据 "ICE 状态" 计算机在最终路径和用户应答计时中的汇聚，nominations 可以在200OK 之前或之后发生。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="c1bc0-137">SBC 必须能够处理这两种情况。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="c1bc0-138">用于分叉的汇聚</span><span class="sxs-lookup"><span data-stu-id="c1bc0-138">Converging for forking</span></span>

<span data-ttu-id="c1bc0-139">如果从 SBC 派生到多个团队终结点的优惠，团队终结点可能会通过临时答案进行响应并启动连接检查。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="c1bc0-140">SBC 必须准备就绪，才能接收来自多个对等终结点的连接性检查和响应连接检查。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="c1bc0-141">例如，团队用户可以同时登录到桌面和手机。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="c1bc0-142">这两个设备将收到入站呼叫通知，并将尝试与 SBC 进行连接检查。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="c1bc0-143">最后，最终仅有一个终结点将接听呼叫（200OK）。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="c1bc0-144">收到200OK 后，SBC 可以为处理媒体包设置正确的上下文。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="c1bc0-145">方案</span><span class="sxs-lookup"><span data-stu-id="c1bc0-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="c1bc0-146">来自 SBC 的入站呼叫</span><span class="sxs-lookup"><span data-stu-id="c1bc0-146">Inbound call from SBC</span></span>

<span data-ttu-id="c1bc0-147">对于此方案，SBC 必须处理几个可能的对等终结点：</span><span class="sxs-lookup"><span data-stu-id="c1bc0-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="c1bc0-148">服务器终结点通常会直接通过200OK 进行响应。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="c1bc0-149">这些是完全冰淇淋终结点，通常包括在语音邮件、呼叫队列和自动助理方案中。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="c1bc0-150">客户端终结点可以发送不同于/To 标记的多个临时应答（183），后跟用于应答呼叫的终结点的200OK。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="c1bc0-151">这些完全冰淇淋终结点通常表示最终用户客户端。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="c1bc0-152">其他 SBC 终结点。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-152">Other SBC endpoints.</span></span> <span data-ttu-id="c1bc0-153">这些是 ICE 精简终结点，这些终结点通常涉及同时拨打客户终结点和另一个电话号码的方案。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="c1bc0-154">SBC 必须响应从完全 ICE 终结点收到的所有有效连接检查请求。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="c1bc0-155">根据 RFC，完全 ICE 终结点将变为控制终结点。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="c1bc0-156">团队（客户端/服务器）终结点将执行 "常规" nominations 以完成连接检查。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="c1bc0-157">最终的200Ok 可以来自发送早期媒体或来自不同终结点的终结点。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="c1bc0-158">在接收200Ok 时，SBC 必须为媒体流设置正确的上下文。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="c1bc0-159">早期媒体</span><span class="sxs-lookup"><span data-stu-id="c1bc0-159">Early media</span></span>

<span data-ttu-id="c1bc0-160">如果存在早期媒体流，则 SBC 必须闩锁到启动流媒体的第一个终结点;媒体流可以在候选人之前开始。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="c1bc0-161">在此阶段，SBC 应支持发送 DTMF 以启用 IVR/语音邮件方案。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="c1bc0-162">如果 nominations 尚未完成，则 SBC 应使用其收到检查的最高优先级路径。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="c1bc0-163">对 SBC 的出站呼叫</span><span class="sxs-lookup"><span data-stu-id="c1bc0-163">Outbound call to SBC</span></span>

<span data-ttu-id="c1bc0-164">团队终结点是此方案的调用方，将成为控制终结点。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="c1bc0-165">在接收临时答案（183）或最终答案（200OK）时，团队终结点将启动连接检查并继续执行 "常规" nominations，以完成连接检查。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="c1bc0-166">注意：如果 SBC 发送临时应答（183），则 SBC 必须准备好接收连接检查请求，并可能在 SBC 发送200OK 之前完成 nominations。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="c1bc0-167">如果在接收200OK 之前完成了检查和/或 nominations，则在收到200OK 后将不会再次执行支票和/或 nominations。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="c1bc0-168">SBC 不得更改183和200之间的 ICE 候选、密码和 ufrag （用户名片段）。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="c1bc0-169">为了支持早期媒体，SBC 可能会开始将媒体流处理到对等的冰候选人，最高优先级基于已接收的连接检查，即使在 nominations 由团队终结点完成之前也是如此。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="c1bc0-170">在 nominations 完成之前，SBC 应期望来自团队的媒体。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="c1bc0-171">预候选人一经命名，SBC 必须重置为正确的上下文才能发送和接收媒体包。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="c1bc0-172">SRTP 支持要求</span><span class="sxs-lookup"><span data-stu-id="c1bc0-172">SRTP support requirements</span></span>

<span data-ttu-id="c1bc0-173">SBC 必须支持 SRTP 加密密码 AES_CM_128_HMAC_SHA1_80 以以下格式提供和应答：</span><span class="sxs-lookup"><span data-stu-id="c1bc0-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="c1bc0-174">下面是来自 SBC 的 SDP 提供的加密属性的示例：</span><span class="sxs-lookup"><span data-stu-id="c1bc0-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="c1bc0-175">MKI 和 Length 参数不是必需的。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="c1bc0-176">有关详细信息，请参阅[第6.1 节中的 RFC 4568](https://tools.ietf.org/html/rfc4568#section-6.1)。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="c1bc0-177">SDES 支持要求</span><span class="sxs-lookup"><span data-stu-id="c1bc0-177">SDES support requirements</span></span>

<span data-ttu-id="c1bc0-178">设备必须能够以如下所述的格式提供 SDES。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="c1bc0-179">Microsoft 媒体处理器始终首选 SDES。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="c1bc0-180">通过非媒体旁路，即使客户仅支持 DTLS，媒体处理器也会转换为 SDES。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="c1bc0-181">使用媒体绕过，如果客户端仅 DTLS （未来 Google Chrome 状态），直接路由将在路径中插入 MP，将来自旁路媒体的呼叫转换为非媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="c1bc0-182">直接路由的 SBC 和媒体处理器组件之间的 SDES 始终使用。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="c1bc0-183">当前没有仅提供 DTLS 的团队客户端;但 Google 已宣布，在某一时间点将停止支持 SDES。</span><span class="sxs-lookup"><span data-stu-id="c1bc0-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="c1bc0-184">在旁路模式下从 SBC 提供的格式</span><span class="sxs-lookup"><span data-stu-id="c1bc0-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="c1bc0-185">优惠必须包含 SDES，并且可以包含以下格式的 DTLS：</span><span class="sxs-lookup"><span data-stu-id="c1bc0-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="c1bc0-186">对 SBC 包含 SDES 的答案的格式</span><span class="sxs-lookup"><span data-stu-id="c1bc0-186">Format for answer containing SDES to SBC</span></span>

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="c1bc0-187">从团队向 SBC 提供的格式</span><span class="sxs-lookup"><span data-stu-id="c1bc0-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="c1bc0-188">SDES 的格式仅向 SBC 提供</span><span class="sxs-lookup"><span data-stu-id="c1bc0-188">Format for SDES only offer to SBC</span></span>

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

