---
title: 电话系统直接路由概述
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: hHw 直接路由支持媒体旁路，为 ICE Lite 启用了会话边框控制器。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6f9715ee410116a66c572522a910cd16ef27154
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614415"
---
# <a name="overview"></a>概述

本文介绍直接路由如何支持通过为 ICE Lite 启用会话边界控制器 (SBC) 的媒体旁路，如 [RFC 5245](https://tools.ietf.org/html/rfc5245) 中所述。 本文适用于负责配置本地 SBC 与 SIP 代理服务之间的连接的语音管理员。

本文概述了 ICE Lite 方案和互操作性要求。 本文介绍消息格式以及确保可靠调用和媒体流所需的状态机转换。

## <a name="terminology"></a>术语

- First Hello – 被调用方和被调用方说出的第一个单词。 必须作出一切努力，确保在大多数用例中可靠地传递终结点中的第一个数据包。

- 分叉 - 如果被调用方在多个设备上可用，则调用方提供的套餐可能会传递到多个被调用方终结点 (例如，Teams 用户可能已登录到 Teams for Windows 和 Teams for Android 或 iPhone) 。

- 临时应答 (183) - 用于加快呼叫设置的被调用方终结点发送一个答案，其中包含建立媒体流所需的候选项和密钥。 此操作是在预期用户可能从该特定被调用方实例接听呼叫 (200OK) 时完成的。 使用分叉时，调用方应准备好接收多个临时答案。

- Re-Invite – 提供由 ICE 控制终结点选择的最终候选项。 这将具有 a=remote-candidate 属性，用于解决处理多个分叉时出现的任何争用条件。

- Teams 终结点 - 可以是服务器 (媒体处理器、传输中继) 或 Teams 客户端。

## <a name="message-format"></a>消息格式

Teams 基础结构遵循 RFC 5245 for ICE-Lite。 这意味着所有 STUN 消息都将符合 [RFC 5389](https://tools.ietf.org/html/rfc5389)。

RFC 5389 所需的 SBC 必须忽略它们无法识别的任何 STUN 属性，并继续使用已知属性处理消息。 

如果收到任何格式不正确的数据包，则必须丢弃数据包，而不会影响媒体会话的建立。

## <a name="ice-lite-requirements"></a>ICE Lite 要求

本部分简要介绍了 ICE Lite 的要求。

### <a name="candidate-gathering"></a>候选人聚会

SBC 只能提供一个候选项。 目前，仅支持 IPV4 候选项。


#### <a name="connectivity-checks"></a>连接性检查

ICE Lite 实现必须响应收到的任何连接检查。 ICE Lite 终结点不得发送任何连接检查请求。  (如果违反连接性检查发送，则完整实现会做出响应，这可能导致发现意外的对等派生候选项，并可能导致呼叫失败。) 

#### <a name="nominations"></a>提名

ICE 完整实现终结点将始终是控制终结点，并将遵循“常规”提名，选择要用于媒体流的最终候选人。 ICE Lite 终结点可以使用提名来结束用于媒体和完成呼叫建立的路径。

注意：对于使用发送 183 个临时答案的对等终结点进行分叉，如果提名发生在 200OK 之前，SBC 必须准备好响应来自多个终结点的检查以及多个终结点的提名。 根据 ICE 状态计算机在用户回答的最终路径和时间上的收敛，提名可能会在 200OK 之前或之后进行。 SBC 必须能够处理这两种情况。

#### <a name="converging-for-forking"></a>聚合分叉

如果产品/服务从 SBC 分叉到多个 Teams 终结点，则 Teams 终结点可能会以临时答案进行响应并启动连接检查。 SBC 必须准备好接收连接检查，并响应来自多个对等终结点的连接检查。 例如，Teams 用户可以同时登录到桌面和手机。 这两台设备都将收到入站调用的通知，并将尝试与 SBC 进行连接检查。

最终只有一个终结点会接听调用 (200OK) 。 收到 200OK 后，SBC 可以设置正确的上下文来处理媒体数据包。

## <a name="scenarios"></a>方案

###  <a name="inbound-call-from-sbc"></a>来自 SBC 的入站调用

对于此方案，SBC 必须处理几个可能的对等终结点：

- 服务器终结点通常会直接响应 200OK。 这些是通常涉及语音邮件、呼叫队列和自动助理方案的完整 ICE 终结点。

- 客户端终结点可以 (183) 发送多个具有不同 From/To 标记的临时答案，然后从响应调用的终结点发送 200OK。 这些是通常表示最终用户客户端的完整 ICE 终结点。

- 其他 SBC 终结点。 这些是 ICE Lite 终结点，通常涉及同时拨打客户端终结点的方案，另一个电话号码 () 。

SBC 必须响应从完整 ICE 终结点收到的所有有效连接检查请求。 根据 RFC，完整的 ICE 终结点将成为控制终结点。 Teams (客户端/服务器) 终结点将执行“常规”提名以完成连接检查。 最终的 200Ok 可以来自发送早期媒体的终结点，也可以来自其他终结点。 接收 200Ok 时，SBC 必须为媒体流设置正确的上下文。 

###  <a name="early-media"></a>早期媒体

如果存在早期媒体流，则 SBC 必须锁定到启动流媒体流的第一个终结点;媒体流可以在候选人被提名之前启动。 在此阶段，SBC 应支持发送 DTMF 以启用 IVR/语音邮件方案。 SBC 应使用其收到检查的优先级最高的路径（如果提名尚未完成）。

### <a name="outbound-call-to-sbc"></a>对 SBC 的出站调用

Teams 终结点是此方案的调用方，将成为控制终结点。 在收到临时答案 (183) 或 200OK)  (最终答案时，Teams 终结点将启动连接性检查，并继续进行“常规”提名以完成连接检查。

注意：如果 SBC (183) 发送临时答案，则 SBC 必须准备好接收连接性检查请求，并有可能在 SBC 发送 200OK 之前完成提名。 如果在收到 200OK 之前完成检查和/或提名，则在收到 200OK 后，将不再执行检查和/或提名。 SBC 不得更改 183 到 200 之间的 ICE 候选项、密码和 ufrag (用户名片段) 。

为了支持早期媒体，SBC 可能会开始将媒体流式传输到对等 ICE 候选人，其优先级最高，具体取决于收到的连接性检查，甚至在 Teams 终结点完成提名之前。 在提名完成之前，SBC 应期待 Teams 对任何候选人进行媒体处理。 候选人被提名后，SBC 必须重置到正确的上下文才能发送和接收媒体数据包。

## <a name="srtp-support-requirements"></a>SRTP 支持要求

SBC 必须支持 SRTP 加密密码AES_CM_128_HMAC_SHA1_80以以下格式提供和答案：

```console
"inline:" <key||salt> ["|" lifetime]
```

下面是 SBC 提供的 SDP 产品/服务中的加密属性示例：

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

不需要 MKI 和 Length 参数。

有关详细信息，请参阅 [RFC 4568 第 6.1 节](https://tools.ietf.org/html/rfc4568#section-6.1)。

## <a name="sdes-support-requirements"></a>SDES 支持要求

设备必须能够以如下所述的格式提供 SDES。 Microsoft 媒体处理器始终首选 SDES。

- 使用非媒体旁路，即使客户端仅支持 DTLS，媒体处理器也会转换为 SDES。

- 借助媒体旁路，如果客户端仅 (未来的 Google Chrome 状态) ，则直接路由会在路径中插入 MP，将呼叫从媒体旁路转换为非媒体旁路。 在直接路由的 SBC 和媒体处理器组件之间，始终使用 SDES。

目前，没有仅提供 DTLS 的 Teams 客户端;然而谷歌已经宣布，在某个时候，他们将停止支持SDES。

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>在旁路模式下从 SBC 提供产品/服务的格式 

产品/服务必须包含 SDES，并且可以采用以下格式包含 DTLS 可选：

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>包含 SDES 到 SBC 的答案的格式

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>从 Teams 到 SBC 的产品/服务格式 

### <a name="format-for-sdes-only-offer-to-sbc"></a>仅向 SBC 提供 SDES 的格式

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

