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
ms.openlocfilehash: 550836275a1ea060d6004c75e0f2bf301f3094a7752ae80ad44dc2c91bbf96bd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339778"
---
# <a name="overview"></a>概述

本文介绍直接路由如何支持使用会话边界控制器 (SBC) 为 ICE Lite 启用媒体旁路，如 [RFC 5245 中所述](https://tools.ietf.org/html/rfc5245)。 本文适用于负责配置本地 SBC 与 SIP 代理服务之间的连接的语音管理员。

本文概述了 ICE Lite 方案和互操作性要求。 本文介绍消息格式和确保可靠的呼叫和媒体流所需的状态机转换。

## <a name="terminology"></a>术语

- First Hello – 呼叫方和被呼叫者说出的第一个字词。 必须确保在大部分用例中可靠地传递来自终结点的第一个数据包。

- 分步 - 如果被调用方在多个设备上可用，则调用方提供的优惠可能会传递到多个被调用方终结点 (例如，Teams 用户可能登录到 Teams for Windows，Teams for Android 或 iPhone) 。

- 临时应答 (183) - 用于加快呼叫设置的被呼叫方终结点发送答案，以及建立媒体流所需的候选项和密钥。 这是在预期用户可能会从该特定被叫方实例 (200OK) 时完成。 使用分路时，调用方应已准备好接收多个临时答案。

- Re-Invite - 具有 ICE 控制终结点选择的最终候选项的优惠。 这将具有 a=remote-candidate 属性，以解决处理多个分叉时的任何竞争条件。

- Teams终结点 – 可以是媒体处理器 (传输中继) 服务器Teams客户端。

## <a name="message-format"></a>消息格式

该Teams遵循 RFC 5245 for ICE-Lite。 这意味着所有 STUN 消息都将符合[RFC 5389。](https://tools.ietf.org/html/rfc5389)

RFC 5389 要求的 SDC 必须忽略它们无法识别的任何 STUN 属性，并继续处理具有已知属性的消息。 

如果收到任何格式错误的数据包，则必须丢弃数据包，而不会影响媒体会话建立。

## <a name="ice-lite-requirements"></a>ICE Lite 要求

本部分简要介绍 ICE Lite 的要求。

### <a name="candidate-gathering"></a>候选人收集

SBC 只能提供一个可公开联系的候选项。 目前仅支持 IPV4 候选项。


#### <a name="connectivity-checks"></a>连接性检查

ICE Lite 实现必须响应收到的任何连接检查。 ICE Lite 终结点不得发送任何连接检查请求。  (如果违反连接检查，则完整实现将做出响应，这可能会导致发现意外的对等派生候选项，并可能导致调用失败。) 

#### <a name="nominations"></a>提名

ICE 完整实现终结点始终是控制终结点，并且将按照"常规"提名来选择用于媒体流的最终候选项。 ICE Lite 终结点可以使用提名来结束用于媒体和完整的呼叫建立的路径。

注意：如果使用对等终结点（发送 183 个临时答案）进行分贝，SBC 必须准备好响应来自多个终结点的检查，并且如果提名发生在 200OK 之前，还必须响应来自多个终结点的提名。 提名可以在 200OK 之前或之后进行，具体取决于 ICE 状态机在用户应答的最终路径和时间上的收敛。 SBC 必须能够处理这两种情况。

#### <a name="converging-for-forking"></a>为分型聚合

如果 SBC 中的产品/Teams终结点，Teams终结点可能会做出响应并启动连接检查。 SBC 必须准备好接收连接检查，并响应来自多个对等终结点的连接检查。 例如，Teams用户可以同时登录到桌面和移动电话。 两台设备都将收到入站呼叫的通知，并尝试使用 SBC 进行连接检查。

最终，只有一个终结点会应答 (200OK) 。 收到 200OK 时，SBC 可以设置用于处理媒体数据包的合适上下文。

## <a name="scenarios"></a>方案

###  <a name="inbound-call-from-sbc"></a>来自 SBC 的入站呼叫

对于此方案，SBC 必须处理多个可能的对等终结点：

- 服务器终结点通常使用 200OK 直接响应。 这些是通常在语音邮件、呼叫队列和自动助理方案中涉及的完整 ICE 终结点。

- 客户端终结点可以发送多个临时答案，其"从/到"标记 (183) 后跟来自应答呼叫的终结点的 200OK。 这些是完整的 ICE 终结点，通常代表最终用户客户端。

- 其他 SBC 终结点。 这些是 ICE Lite 终结点，通常涉及同时拨打客户端终结点和另一个电话号码 () 。

SBC 必须响应从完整 ICE 终结点接收的所有有效连接检查请求。 根据 RFC，完整的 ICE 终结点将成为控制终结点。 客户端Teams (服务器) 将执行"常规"提名以完成连接检查。 最终的 200Ok 可以来自发送早期媒体的终结点，也可以来自其他终结点。 收到 200Ok 时，SBC 必须为媒体流设置正确的上下文。 

###  <a name="early-media"></a>早期媒体

如果存在早期媒体流，SBC 必须闩锁到第一个启动流媒体的终结点;媒体流可以在提名候选项之前启动。 SBC 应支持在此阶段发送 DTMF 以启用 IVR/语音邮件方案。 如果提名未完成，SBC 应该使用收到检查的最高优先级路径。

### <a name="outbound-call-to-sbc"></a>对 SBC 的出站调用

Teams终结点是此方案的调用方，并且将是控制终结点。 收到临时答案 (183) 或最终答案 (200OK) 时，Teams 终结点将开始连接检查，并继续进行"常规"提名以完成连接检查。

注意：如果 SBC 发送临时答案 (183) ，则 SBC 必须准备好接收连接检查请求，并有可能在 SBC 发送 200OK 之前完成提名。 如果在收到 200OK 之前已完成检查和/或提名，则 200OK 收到后，将不会再次执行检查和/或提名。 SBC 不得更改 ICE 候选项、密码和 ufrag (183) 200 之间的用户名片段。

为了支持早期媒体，SBC 可能会开始将媒体流式传输给对等 ICE 候选项，根据收到的连接检查获得最高优先级，即使在提名完成之前，Teams终结点。 在提名完成之前，SBC Teams来自任何候选项的媒体。 提名候选项后，SBC 必须重置为正确的上下文，以发送和接收媒体数据包。

## <a name="srtp-support-requirements"></a>SRTP 支持要求

SBC 必须支持 SRTP 加密密码AES_CM_128_HMAC_SHA1_80以下格式提供和应答：

```console
"inline:" <key||salt> ["|" lifetime]
```

下面是 SBC 提供的 SDP 产品/服务中的加密属性示例：

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI 和 Length 参数不是必需的。

有关详细信息，请参阅 [RFC 4568 第 6.1 部分](https://tools.ietf.org/html/rfc4568#section-6.1)。

## <a name="sdes-support-requirements"></a>SDES 支持要求

设备必须能够提供 SDES 格式，如下所述。 Microsoft 媒体处理器始终首选 SDES。

- 使用非媒体旁路，即使客户端仅支持 DTLS，媒体处理器也将转换为 SDES。

- 借助媒体旁路，如果客户端仅为 DTLS (Google Chrome 状态) ，则直接路由将在路径中插入 MP，将呼叫从媒体旁路转换为非媒体旁路。 在直接路由的 SBC 和媒体处理器组件之间，始终使用 SDES。

目前，没有一个Teams仅提供 DTLS 的客户端;但 Google 已宣布，在某些时间点，他们将停止支持 SDES。

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>在绕过模式下从 SBC 提供产品/服务的格式 

产品/服务必须包含 SDES，并且可以包含以下格式的 DTLS 可选：

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

## <a name="format-for-offer-from-teams-to-sbc"></a>产品/服务的格式Teams SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>仅适用于 SBC 的 SDES 产品/服务的格式

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

