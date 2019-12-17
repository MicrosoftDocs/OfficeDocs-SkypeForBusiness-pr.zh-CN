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
# <a name="direct-routing---definitions-and-rfc-standards"></a>直接路由定义和 RFC 标准

本文介绍 Microsoft Phone 系统直接路由如何实现 RFC 标准协议。 本文适用于负责配置本地会话边界控制器（SBC）和会话初始协议（SIP）代理服务之间的连接的语音管理员。

客户 SBC 接口，其中包含 Microsoft 团队后端中的以下组件： 

- 用于发送信号**的 SIP 代理**。 这是直接路由的面向 Internet 的组件，用于处理 SBCs 和直接路由之间的 SIP （TLS）连接。

- 媒体**处理**程序。 这是面向 Internet 的直接路由组件，用于处理媒体流量。 此组件使用 SRTP 和 SRTCP 协议。


有关直接路由的详细信息，请参阅[手机系统直接路由](direct-routing-landing-page.md)。

有关直接路由如何实现 SIP 协议的详细信息，请参阅[直接路由 SIP 协议](direct-routing-protocols-sip.md)。

## <a name="rfc-standards"></a>RFC 标准

直接路由符合 RFC 标准。  连接到直接路由的 SBC 还必须遵守以下 Rfc （或其后续任务）。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>适用于支持非媒体绕过模式的设备的标准 

以下标准适用于仅支持非媒体绕过模式的设备：

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261)：会话初始协议
- [RFC 3325](https://www.ietf.org/rfc/rfc3325)。 在受信任的网络内断言标识的会话初始协议的专用扩展--有关处理 P 声明标识标头的部分。 直接路由发送带有隐私 ID 标头的 P 声明标识。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt)针对所需历史记录信息的会话初始协议（SIP）的扩展。 另请参阅：路由 SIP 协议说明了解详细信息。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)会话初始协议，即 "按机制"
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt)会话初始协议（SIP） "替换" 标头 
- [RFC 6337](https://tools.ietf.org/html/rfc6337)优惠/应答模型的会话初始协议（SIP）使用。
  请参阅 "与 RFC 的偏差" 部分。
- [Rfc 3711](https://tools.ietf.org/html/rfc3711)和[rfc 4771](https://tools.ietf.org/html/rfc4771)。 使用 SRTP 保护 RTP 流量。 SBC 必须能够使用 SDES 建立密钥。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt)适用于 RTP/RTCP 复用的会话描述协议（SDP）优惠/答案说明

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>适用于支持媒体绕过模式的设备的标准

除了列出的适用于非绕过模式的标准，以下标准用于媒体绕过模式：

- [适用于媒体绕过的 RFC 5245 交互式连接建立（ICE）](https://tools.ietf.org/html/rfc5245)。  SBC 必须支持以下内容：
  - 冰精简-团队客户是完全 ICE 客户端
  - [ICE 重启](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。 了解有关 ICE 重启的更多信息使用案例和示例在 ICE 重启：将媒体绕过呼叫转移到不支持媒体绕过的终结点   
- [RFC rfc 5589 会话初始协议（SIP）呼叫控制-转移](https://tools.ietf.org/html/rfc5589)。 
- [RFC 3960 早期媒体和铃声生成在会话启动协议（SIP）中](https://tools.ietf.org/html/rfc3960)，请参阅3.1、分叉和3.2 部分、铃声生成 
- [适用于 NAT 的 RFC 5389 会话遍历实用工具（STUN）](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 遍历 NAT 周围的中继（转换）：用于 NAT 的会话遍历实用工具的中继扩展（STUN）](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>适用于支持将位置信息传达给 E911 提供商的标准

- [RFC 6442，位置 Conveyance 会话启动协议的位置](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>RFC 的偏差

下表列出了 Microsoft 实施 SIP 或媒体堆栈的 RFC 部分与标准的不同：

| RFC 和分区 | 说明 | 差值 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337，第5.3 节保留和恢复媒体](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC 允许使用 "a = 非活动"，"a = sendonly"，a = recvonly "将呼叫置于保持状态。 |SIP 代理仅支持 "a = 非活动"，并且不知道 SBC 是否发送 "a = sendonly" 或 "a = recvonly"。
| [在 c = 0.0.0.0 的情况下接收 SDP 的 RFC 6337，第5.4 部分](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264)要求代理能够接收连接地址为0.0.0.0 的 SDP，在这种情况下，不应将 RTP 和 RTCP 发送到对等。 | SIP 代理不支持此选项。 |

## <a name="operational-modes"></a>运行模式

直接路由有两种操作模式：

- 如果**没有媒体旁路**，则在团队客户端、媒体处理器和 SBC 之间的所有 RTP 通信流。  

- 在**媒体旁路**中，所有 RTP 媒体都在团队终结点和 SBC 之间流动。 

请注意，SIP 流量始终通过 SIP 代理流出。   
