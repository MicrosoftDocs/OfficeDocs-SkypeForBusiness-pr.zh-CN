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
ms.openlocfilehash: 3f21a4532a841a23f6bbb78a57e223616ae539fa
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835132"
---
# <a name="overview"></a>概述

本文介绍直接路由如何支持使用适用于 ICE 精简的会话边界控制器（SBC）的媒体旁路，如[RFC 5245](https://tools.ietf.org/html/rfc5245)中所述。 本文面向负责配置本地 SBC 和 SIP 代理服务之间的连接的语音管理员。

本文概述了 "ICE" 方案和互操作性要求。 本文介绍邮件格式和必需的状态机转换，以确保可靠的呼叫和媒体流。

## <a name="terminology"></a>术语

- 第一名 Hello-呼叫方和被叫方的第一字。 必须确保所有努力都确保来自终结点的第一个数据包可可靠地针对大多数使用案例进行提供。

- 分叉-如果被呼叫方在多台设备上可用（例如，团队用户可能登录到适用于 Windows 的团队和适用于 Android 或 iPhone 的团队），则可能会将提供给多个被调用方终结点发送给这些终结点。

- 临时应答（183）-被呼叫方终结点以实现更快的通话设置使用建立媒体流所需的候选项和密钥发送答案。 这是为了预测用户可能会从该特定被叫方实例应答调用（200OK）。 通过分叉，呼叫方应准备好接收多个临时的答案。

- 重新邀请–提供由 ICE 控制终结点选择的最终候选项。 这将具有 a = 远程候选属性，以解决处理多个派生的任何争用条件。

- 团队终结点-这可能是服务器（媒体处理器、传输中继）或团队客户端。

## <a name="message-format"></a>邮件格式

团队基础结构遵循 RFC 5245 的冰精简。 这意味着所有 STUN 消息都将符合[RFC 5389](https://tools.ietf.org/html/rfc5389)。

由 RFC 5389 所需的 SBCs 必须忽略其不识别的任何 STUN 属性，并继续处理具有已知属性的消息。 

如果收到任何格式错误的数据包，则数据包必须在不影响媒体会话建立的情况下丢弃。

## <a name="ice-lite-requirements"></a>ICE 精简要求

本部分简要介绍了 ICE 精简的要求。

### <a name="candidate-gathering"></a>候选收集

SBC 必须仅提供一个可公开访问的候选项。 目前，仅支持 IPV4 候选人。


#### <a name="connectivity-checks"></a>连接检查

ICE Lite 实现必须响应收到的任何连接检查。 ICE Lite 终结点不得发送任何连接检查请求。 （如果连接检查发生冲突，则完整的实现将响应，这可能会导致发现意外的对等派生候选，并且可能会导致调用失败。）

#### <a name="nominations"></a>Nominations

ICE 完全实现终结点将始终为控制终结点，并且将遵循 "Regular" nominations 来选择要用于媒体流的最终候选项。 ICE Lite 终结点可以使用 nominations 结束用于媒体和完成通话建立的路径。

注意：在具有对等终结点的发送183临时答案的分叉情况下，SBC 必须准备好响应来自多个终结点的检查，并且还必须准备好从多个终结点 nominations，如果 nominations 在200OK 之前发生。 根据 "ICE 状态" 计算机在最终路径和用户应答计时中的汇聚，nominations 可以在200OK 之前或之后发生。 SBC 必须能够处理这两种情况。

#### <a name="converging-for-forking"></a>用于分叉的汇聚

如果从 SBC 派生到多个团队终结点的优惠，团队终结点可能会通过临时答案进行响应并启动连接检查。 SBC 必须准备就绪，才能接收来自多个对等终结点的连接性检查和响应连接检查。 例如，团队用户可以同时登录到桌面和手机。 这两个设备将收到入站呼叫通知，并将尝试与 SBC 进行连接检查。

最后，最终仅有一个终结点将接听呼叫（200OK）。 收到200OK 后，SBC 可以为处理媒体包设置正确的上下文。

## <a name="scenarios"></a>方案

###  <a name="inbound-call-from-sbc"></a>来自 SBC 的入站呼叫

对于此方案，SBC 必须处理几个可能的对等终结点：

- 服务器终结点通常会直接通过200OK 进行响应。 这些是完全冰淇淋终结点，通常包括在语音邮件、呼叫队列和自动助理方案中。

- 客户端终结点可以发送不同于/To 标记的多个临时应答（183），后跟用于应答呼叫的终结点的200OK。 这些完全冰淇淋终结点通常表示最终用户客户端。

- 其他 SBC 终结点。 这些是 ICE 精简终结点，这些终结点通常涉及同时拨打客户终结点和另一个电话号码的方案。

SBC 必须响应从完全 ICE 终结点收到的所有有效连接检查请求。 根据 RFC，完全 ICE 终结点将变为控制终结点。 团队（客户端/服务器）终结点将执行 "常规" nominations 以完成连接检查。 最终的200Ok 可以来自发送早期媒体或来自不同终结点的终结点。 在接收200Ok 时，SBC 必须为媒体流设置正确的上下文。 

###  <a name="early-media"></a>早期媒体

如果存在早期媒体流，则 SBC 必须闩锁到启动流媒体的第一个终结点;媒体流可以在候选人之前开始。 在此阶段，SBC 应支持发送 DTMF 以启用 IVR/语音邮件方案。 如果 nominations 尚未完成，则 SBC 应使用其收到检查的最高优先级路径。

### <a name="outbound-call-to-sbc"></a>对 SBC 的出站呼叫

团队终结点是此方案的调用方，将成为控制终结点。 在接收临时答案（183）或最终答案（200OK）时，团队终结点将启动连接检查并继续执行 "常规" nominations，以完成连接检查。

注意：如果 SBC 发送临时应答（183），则 SBC 必须准备好接收连接检查请求，并可能在 SBC 发送200OK 之前完成 nominations。 如果在接收200OK 之前完成了检查和/或 nominations，则在收到200OK 后将不会再次执行支票和/或 nominations。 SBC 不得更改183和200之间的 ICE 候选、密码和 ufrag （用户名片段）。

为了支持早期媒体，SBC 可能会开始将媒体流处理到对等的冰候选人，最高优先级基于已接收的连接检查，即使在 nominations 由团队终结点完成之前也是如此。 在 nominations 完成之前，SBC 应期望来自团队的媒体。 预候选人一经命名，SBC 必须重置为正确的上下文才能发送和接收媒体包。

## <a name="srtp-support-requirements"></a>SRTP 支持要求

SBC 必须支持 SRTP 加密密码 AES_CM_128_HMAC_SHA1_80 以以下格式提供和应答：

```
"inline:" <key||salt> ["|" lifetime]
```

下面是来自 SBC 的 SDP 提供的加密属性的示例：

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI 和 Length 参数不是必需的。

有关详细信息，请参阅[第6.1 节中的 RFC 4568](https://tools.ietf.org/html/rfc4568#section-6.1)。

## <a name="sdes-support-requirements"></a>SDES 支持要求

设备必须能够以如下所述的格式提供 SDES。 Microsoft 媒体处理器始终首选 SDES。

- 通过非媒体旁路，即使客户仅支持 DTLS，媒体处理器也会转换为 SDES。

- 使用媒体绕过，如果客户端仅 DTLS （未来 Google Chrome 状态），直接路由将在路径中插入 MP，将来自旁路媒体的呼叫转换为非媒体旁路。 直接路由的 SBC 和媒体处理器组件之间的 SDES 始终使用。

当前没有仅提供 DTLS 的团队客户端;但 Google 已宣布，在某一时间点将停止支持 SDES。

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>在旁路模式下从 SBC 提供的格式 

优惠必须包含 SDES，并且可以包含以下格式的 DTLS：

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>对 SBC 包含 SDES 的答案的格式

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>从团队向 SBC 提供的格式 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SDES 的格式仅向 SBC 提供

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

