---
title: Teams 电话系统直接路由：定义和 RFC 标准
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 电话系统直接路由如何实现 RFC 标准协议。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01dbd61748d14ef21a600b2e4f44a306517e46d9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271237"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>直接路由 - 定义和 RFC 标准

本文介绍 Microsoft 电话系统直接路由如何实现 RFC 标准协议。 本文适用于负责配置本地会话边界控制器 (SBC) 与 SIP) 代理服务 (会话启动协议之间的连接的语音管理员。

客户 SBC 接口与 Microsoft Teams 后端中的以下组件接口： 

- 用于发出信号 **的 SIP 代理**。 这是直接路由面向 Internet 的组件，用于处理 SBC 和直接路由之间的 SIP (TLS) 连接。

- **媒体的媒体处理器** 。 这是直接路由的面向 Internet 的组件，用于处理媒体流量。 此组件使用 SRTP 和 SRTCP 协议。


有关直接路由的详细信息，请参阅 [电话系统直接路由](direct-routing-landing-page.md)。

有关直接路由如何实现 SIP 协议的详细信息，请参阅 [直接路由 - SIP 协议](direct-routing-protocols-sip.md)。

## <a name="rfc-standards"></a>RFC 标准

直接路由符合 RFC 标准。  连接到直接路由的 SBC 还必须符合以下 RFC (或其后续) 。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>适用于支持非媒体旁路模式的设备的标准 

以下标准适用于仅支持非媒体旁路模式的设备：

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261)：会话启动协议
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). 对受信任网络中断言标识的会话发起协议的专用扩展 -有关处理 P-Asserted-Identity 标头的部分。 直接路由发送具有隐私 ID 标头的 P-Asserted-Identity。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 对所需历史记录信息的会话启动协议 (SIP) 的扩展。 另请参阅：路由 SIP 协议说明，了解详细信息。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 会话启动协议Referred-By机制
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) SIP) “替换”标头 (会话启动协议 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) 会话启动协议 (SIP) 产品/应答模型的使用情况。
  请参阅“与 RFC 的偏差”部分。
- [RFC 3711](https://tools.ietf.org/html/rfc3711) 和 [RFC 4771](https://tools.ietf.org/html/rfc4771)。 使用 SRTP 保护 RTP 流量。 SBC 必须能够使用 SDES 建立密钥。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) 针对 RTP/RTCP 多路复用的会话说明协议 (SDP) 产品/答案说明

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>适用于支持媒体旁路模式的设备的标准

除了列出的适用于非旁路模式的标准外，以下标准还用于媒体旁路模式：

- [用于媒体旁路的 RFC 5245 交互式连接建立 (ICE) ](https://tools.ietf.org/html/rfc5245)。  SBC 必须支持以下各项：
  - ICE Lite - Teams 客户端是完整的 ICE 客户端
  - [ICE 重启](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。 有关 ICE 重启用例和 ICE 重启示例的详细信息：媒体旁路呼叫转移到不支持媒体旁路的终结点   
- [RFC RFC 5589 会话启动协议 (SIP) 呼叫控制 - 传输](https://tools.ietf.org/html/rfc5589)。 
- [RFC 3960 早期媒体和响铃音生成在会话启动协议 (SIP) ](https://tools.ietf.org/html/rfc3960)，请参阅第 3.1、Forking 和 3.2 部分，即响铃音生成 
- [适用于 NAT 的 RFC 5389 会话遍历实用工具 (STUN) ](https://tools.ietf.org/html/rfc5389)
- [围绕 NAT (TURN) 使用中继的 RFC 5766 遍历：用于 NAT (STUN 的会话遍历实用工具的中继扩展) ](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>适用于支持将位置信息传达给 E911 提供程序的标准

- [RFC 6442，会话启动协议的位置传送](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>与 RFC 的偏差

下表列出了 RFC (的) 部分，其中 Microsoft 对 SIP 或媒体堆栈的实现偏离了标准：

| RFC 和部分 | 说明 | 偏差 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337，媒体保留和恢复第 5.3 部分](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC 允许使用“a=inactive”、“a=sendonly”、“a=recvonly”将呼叫置于保留状态。 |SIP 代理仅支持“a=非活动”，并且不了解 SBC 是否发送“a=sendonly”或“a=recvonly”。
| [RFC 6337，第 5.4 节“使用 c=0.0.0.0 接收 SDP 时的行为](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) 要求代理能够接收连接地址为 0.0.0.0 的 SDP，在这种情况下，这意味着 RTP 和 RTCP 都不应发送到对等方。 | SIP 代理不支持此选项。 |

## <a name="operational-modes"></a>操作模式

直接路由有两种操作模式：

- **没有媒体绕过** 所有 RTP 流量在 Teams 客户端、媒体处理器和 SBC 之间流动。  

- **在媒体旁路** 时，所有 RTP 媒体都在 Teams 终结点和 SBC 之间流动。 

请注意，SIP 流量始终通过 SIP 代理流动。 

## <a name="dtmf"></a>Dtmf
媒体堆栈不支持带内 DTMF。
