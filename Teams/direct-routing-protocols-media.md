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
f1.keywords:
- NOCSH
description: 直接路由协议
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888571"
---
# <a name="overview"></a><span data-ttu-id="b6a6c-103">概述</span><span class="sxs-lookup"><span data-stu-id="b6a6c-103">Overview</span></span>

<span data-ttu-id="b6a6c-104">本文介绍直接路由如何支持使用会话边界控制器 (SBC) 为 ICE Lite 启用媒体旁路，如 [RFC 5245 中所述](https://tools.ietf.org/html/rfc5245)。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="b6a6c-105">本文适用于负责配置本地 SBC 与 SIP 代理服务之间的连接的语音管理员。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="b6a6c-106">本文概述了 ICE Lite 方案和互操作性要求。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="b6a6c-107">本文介绍消息格式和确保可靠的呼叫和媒体流所需的状态机转换。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="b6a6c-108">术语</span><span class="sxs-lookup"><span data-stu-id="b6a6c-108">Terminology</span></span>

- <span data-ttu-id="b6a6c-109">First Hello – 呼叫方和被呼叫者说出的第一个字词。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="b6a6c-110">必须确保在大部分用例中可靠地传递来自终结点的第一个数据包。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="b6a6c-111">分步 - 如果被调用方在多个设备上可用，则调用方提供的优惠可能会传递到多个被调用方终结点 (例如，Teams 用户可能登录到 Teams for Windows，Teams for Android 或 iPhone) 。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="b6a6c-112">临时应答 (183) - 用于加快呼叫设置的被呼叫方终结点发送答案，以及建立媒体流所需的候选项和密钥。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="b6a6c-113">这是在预期用户可能会从该特定被叫方实例 (200OK) 时完成。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="b6a6c-114">使用分路时，调用方应已准备好接收多个临时答案。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="b6a6c-115">Re-Invite - 具有 ICE 控制终结点选择的最终候选项的优惠。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="b6a6c-116">这将具有 a=remote-candidate 属性，以解决处理多个分叉时的任何竞争条件。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="b6a6c-117">Teams终结点 – 可以是媒体处理器 (传输中继) 服务器Teams客户端。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="b6a6c-118">消息格式</span><span class="sxs-lookup"><span data-stu-id="b6a6c-118">Message format</span></span>

<span data-ttu-id="b6a6c-119">该Teams遵循 RFC 5245 for ICE-Lite。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="b6a6c-120">这意味着所有 STUN 消息都将符合[RFC 5389。](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="b6a6c-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="b6a6c-121">RFC 5389 要求的 SDC 必须忽略它们无法识别的任何 STUN 属性，并继续处理具有已知属性的消息。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="b6a6c-122">如果收到任何格式错误的数据包，则必须丢弃数据包，而不会影响媒体会话建立。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="b6a6c-123">ICE Lite 要求</span><span class="sxs-lookup"><span data-stu-id="b6a6c-123">ICE Lite requirements</span></span>

<span data-ttu-id="b6a6c-124">本部分简要介绍 ICE Lite 的要求。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="b6a6c-125">候选人收集</span><span class="sxs-lookup"><span data-stu-id="b6a6c-125">Candidate gathering</span></span>

<span data-ttu-id="b6a6c-126">SBC 只能提供一个可公开联系的候选项。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="b6a6c-127">目前仅支持 IPV4 候选项。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="b6a6c-128">连接性检查</span><span class="sxs-lookup"><span data-stu-id="b6a6c-128">Connectivity checks</span></span>

<span data-ttu-id="b6a6c-129">ICE Lite 实现必须响应收到的任何连接检查。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="b6a6c-130">ICE Lite 终结点不得发送任何连接检查请求。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="b6a6c-131"> (如果违反连接检查，则完整实现将做出响应，这可能会导致发现意外的对等派生候选项，并可能导致调用失败。) </span><span class="sxs-lookup"><span data-stu-id="b6a6c-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="b6a6c-132">提名</span><span class="sxs-lookup"><span data-stu-id="b6a6c-132">Nominations</span></span>

<span data-ttu-id="b6a6c-133">ICE 完整实现终结点始终是控制终结点，并且将按照"常规"提名来选择用于媒体流的最终候选项。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="b6a6c-134">ICE Lite 终结点可以使用提名来结束用于媒体和完整的呼叫建立的路径。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="b6a6c-135">注意：如果使用对等终结点（发送 183 个临时答案）进行分贝，SBC 必须准备好响应来自多个终结点的检查，并且如果提名发生在 200OK 之前，还必须响应来自多个终结点的提名。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="b6a6c-136">提名可以在 200OK 之前或之后进行，具体取决于 ICE 状态机在用户应答的最终路径和时间上的收敛。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="b6a6c-137">SBC 必须能够处理这两种情况。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="b6a6c-138">为分型聚合</span><span class="sxs-lookup"><span data-stu-id="b6a6c-138">Converging for forking</span></span>

<span data-ttu-id="b6a6c-139">如果 SBC 中的产品/Teams终结点，Teams终结点可能会做出响应并启动连接检查。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="b6a6c-140">SBC 必须准备好接收连接检查，并响应来自多个对等终结点的连接检查。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="b6a6c-141">例如，Teams用户可以同时登录到桌面和移动电话。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="b6a6c-142">两台设备都将收到入站呼叫的通知，并尝试使用 SBC 进行连接检查。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="b6a6c-143">最终，只有一个终结点会应答 (200OK) 。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="b6a6c-144">收到 200OK 时，SBC 可以设置用于处理媒体数据包的合适上下文。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="b6a6c-145">方案</span><span class="sxs-lookup"><span data-stu-id="b6a6c-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="b6a6c-146">来自 SBC 的入站呼叫</span><span class="sxs-lookup"><span data-stu-id="b6a6c-146">Inbound call from SBC</span></span>

<span data-ttu-id="b6a6c-147">对于此方案，SBC 必须处理多个可能的对等终结点：</span><span class="sxs-lookup"><span data-stu-id="b6a6c-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="b6a6c-148">服务器终结点通常使用 200OK 直接响应。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="b6a6c-149">这些是通常在语音邮件、呼叫队列和自动助理方案中涉及的完整 ICE 终结点。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="b6a6c-150">客户端终结点可以发送多个临时答案，其"从/到"标记 (183) 后跟来自应答呼叫的终结点的 200OK。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="b6a6c-151">这些是完整的 ICE 终结点，通常代表最终用户客户端。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="b6a6c-152">其他 SBC 终结点。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-152">Other SBC endpoints.</span></span> <span data-ttu-id="b6a6c-153">这些是 ICE Lite 终结点，通常涉及同时拨打客户端终结点和另一个电话号码 () 。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="b6a6c-154">SBC 必须响应从完整 ICE 终结点接收的所有有效连接检查请求。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="b6a6c-155">根据 RFC，完整的 ICE 终结点将成为控制终结点。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="b6a6c-156">客户端Teams (服务器) 将执行"常规"提名以完成连接检查。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="b6a6c-157">最终的 200Ok 可以来自发送早期媒体的终结点，也可以来自其他终结点。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="b6a6c-158">收到 200Ok 时，SBC 必须为媒体流设置正确的上下文。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="b6a6c-159">早期媒体</span><span class="sxs-lookup"><span data-stu-id="b6a6c-159">Early media</span></span>

<span data-ttu-id="b6a6c-160">如果存在早期媒体流，SBC 必须闩锁到第一个启动流媒体的终结点;媒体流可以在提名候选项之前启动。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="b6a6c-161">SBC 应支持在此阶段发送 DTMF 以启用 IVR/语音邮件方案。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="b6a6c-162">如果提名未完成，SBC 应该使用收到检查的最高优先级路径。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="b6a6c-163">对 SBC 的出站调用</span><span class="sxs-lookup"><span data-stu-id="b6a6c-163">Outbound call to SBC</span></span>

<span data-ttu-id="b6a6c-164">Teams终结点是此方案的调用方，并且将是控制终结点。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="b6a6c-165">收到临时答案 (183) 或最终答案 (200OK) 时，Teams 终结点将开始连接检查，并继续进行"常规"提名以完成连接检查。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="b6a6c-166">注意：如果 SBC 发送临时答案 (183) ，则 SBC 必须准备好接收连接检查请求，并有可能在 SBC 发送 200OK 之前完成提名。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="b6a6c-167">如果在收到 200OK 之前已完成检查和/或提名，则 200OK 收到后，将不会再次执行检查和/或提名。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="b6a6c-168">SBC 不得更改 ICE 候选项、密码和 ufrag (183) 200 之间的用户名片段。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="b6a6c-169">为了支持早期媒体，SBC 可能会开始将媒体流式传输给对等 ICE 候选项，根据收到的连接检查获得最高优先级，即使在提名完成之前，Teams终结点。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="b6a6c-170">在提名完成之前，SBC Teams来自任何候选项的媒体。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="b6a6c-171">提名候选项后，SBC 必须重置为正确的上下文，以发送和接收媒体数据包。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="b6a6c-172">SRTP 支持要求</span><span class="sxs-lookup"><span data-stu-id="b6a6c-172">SRTP support requirements</span></span>

<span data-ttu-id="b6a6c-173">SBC 必须支持 SRTP 加密密码AES_CM_128_HMAC_SHA1_80以下格式提供和应答：</span><span class="sxs-lookup"><span data-stu-id="b6a6c-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="b6a6c-174">下面是 SBC 提供的 SDP 产品/服务中的加密属性示例：</span><span class="sxs-lookup"><span data-stu-id="b6a6c-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="b6a6c-175">MKI 和 Length 参数不是必需的。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="b6a6c-176">有关详细信息，请参阅 [RFC 4568 第 6.1 部分](https://tools.ietf.org/html/rfc4568#section-6.1)。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="b6a6c-177">SDES 支持要求</span><span class="sxs-lookup"><span data-stu-id="b6a6c-177">SDES support requirements</span></span>

<span data-ttu-id="b6a6c-178">设备必须能够提供 SDES 格式，如下所述。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="b6a6c-179">Microsoft 媒体处理器始终首选 SDES。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="b6a6c-180">使用非媒体旁路，即使客户端仅支持 DTLS，媒体处理器也将转换为 SDES。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="b6a6c-181">借助媒体旁路，如果客户端仅为 DTLS (Google Chrome 状态) ，则直接路由将在路径中插入 MP，将呼叫从媒体旁路转换为非媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="b6a6c-182">在直接路由的 SBC 和媒体处理器组件之间，始终使用 SDES。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="b6a6c-183">目前，没有一个Teams仅提供 DTLS 的客户端;但 Google 已宣布，在某些时间点，他们将停止支持 SDES。</span><span class="sxs-lookup"><span data-stu-id="b6a6c-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="b6a6c-184">在绕过模式下从 SBC 提供产品/服务的格式</span><span class="sxs-lookup"><span data-stu-id="b6a6c-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="b6a6c-185">产品/服务必须包含 SDES，并且可以包含以下格式的 DTLS 可选：</span><span class="sxs-lookup"><span data-stu-id="b6a6c-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="b6a6c-186">包含 SDES 到 SBC 的答案的格式</span><span class="sxs-lookup"><span data-stu-id="b6a6c-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="b6a6c-187">产品/服务的格式Teams SBC</span><span class="sxs-lookup"><span data-stu-id="b6a6c-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="b6a6c-188">仅适用于 SBC 的 SDES 产品/服务的格式</span><span class="sxs-lookup"><span data-stu-id="b6a6c-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

