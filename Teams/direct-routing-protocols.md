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
ms.openlocfilehash: 015b07f538ad33079bbe04649849d22bfebbfb081feb30cea154cb30f9f10fd9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347168"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>直接路由 - 定义和 RFC 标准

本文介绍如何Microsoft 电话直接路由实现 RFC 标准协议。 本文面向负责配置本地会话边界控制器 (SBC) 与会话启动协议 (SIP) 代理服务之间的连接的语音管理员。

客户 SBC 与后端中的以下Microsoft Teams接口： 

- **用于发送信号** 的 SIP 代理。 这是直接路由的面向 Internet 的组件，用于处理 SIP (TLS) SDC 和直接路由之间的连接。

- **媒体的** 媒体处理器。 这是直接路由的面向 Internet 的组件，用于处理媒体流量。 此组件使用 SRTP 和 SRTCP 协议。


有关直接路由详细信息，请参阅 电话系统[直接路由](direct-routing-landing-page.md)。

有关直接路由如何实现 SIP 协议的信息，请参阅 [直接路由 - SIP 协议](direct-routing-protocols-sip.md)。

## <a name="rfc-standards"></a>RFC 标准

直接路由符合 RFC 标准。  连接到直接路由的 SBC 还必须符合以下 RFC (及其后续) 。 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>适用于支持非媒体旁路模式的设备的标准 

以下标准适用于仅支持非媒体旁路模式的设备：

- [RFC 3261 SIP：](https://tools.ietf.org/html/rfc3261)会话启动协议
- [RFC 3325。](https://www.ietf.org/rfc/rfc3325) 受信任网络内断言标识的会话启动协议的专用扩展 -- 有关处理 P-Asserted-Identity 标头的部分。 直接路由发送包含隐私 ID 标头的 P-Asserted-Identity。 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) SIP 会话启动协议扩展 (SIP) 历史记录信息。 有关详细信息，另请参阅：路由 SIP 协议说明。
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 会话启动协议Referred-By机制
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) SIP 会话启动协议 (SIP) "Replaces"标头 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) 会话启动协议 (SIP) /应答模型的使用情况。
  请参阅"与 RFC 的偏差"部分。
- [RFC 3711](https://tools.ietf.org/html/rfc3711)和[RFC 4771。](https://tools.ietf.org/html/rfc4771) 使用 SRTP 保护 RTP 流量。 SBC 必须能够使用 SDES 建立密钥。 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) 会话说明协议 (SDP) RTP/RTCP 多路复用产品/解答说明

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>适用于支持媒体旁路模式的设备的标准

除了列为适用于非绕过模式的标准外，以下标准还用于媒体旁路模式：

- [RFC 5245 Interactive Connectivity Establishment (ICE) 用于媒体旁路](https://tools.ietf.org/html/rfc5245)。  SBC 必须支持以下各项：
  - ICE Lite - Teams是完整的 ICE 客户端
  - [ICE 重启](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)。 有关 ICE 重启用例和示例，请参阅 ICE 重启：传输到不支持媒体旁路的终结点的媒体旁路呼叫   
- [RFC RFC 5589 会话启动协议 (SIP) 呼叫控制 – 传输。](https://tools.ietf.org/html/rfc5589) 
- [RFC 3960 ](https://tools.ietf.org/html/rfc3960)会话启动协议 (SIP) 中的 RFC 3960 早期媒体和铃声生成，请参阅第 3.1、Forking 和 3.2 部分：铃声生成 
- [RFC 5389 会话遍历实用工具，适用于 NAT (STUN) ](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 使用围绕 NAT (TURN) 的中继进行遍历：中继扩展到 NAT (STUN) ](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>适用于支持向 E911 提供商传达位置信息的标准

- [RFC 6442，会话启动协议的位置传达](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>与 RFC 的偏差

下表列出了 RFC 协议 (部分) 其中 Microsoft 对 SIP 或媒体堆栈的实现偏离标准：

| RFC 和节 | 说明 | 偏差 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337，第 5.3 节媒体保留和恢复](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC 允许使用"a=inactive"、"a=sendonly"、"a=recvonly"来保持呼叫。 |SIP 代理仅支持"a=inactive"，并且不知道 SBC 是发送"a=sendonly"还是"a=recvonly"。
| [RFC 6337，第 5.4 节"使用 c=0.0.0.0 接收 SDP 的行为](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) 要求代理能够接收连接地址为 0.0.0.0 的 SDP，在这种情况下，这意味着不应将 RTP 和 RTCP 发送到对等方。 | SIP 代理不支持此选项。 |

## <a name="operational-modes"></a>操作模式

直接路由有两种操作模式：

- **无需绕过媒体**，所有 RTP 流量Teams客户端、媒体处理器和 SBC 之间流动。  

- **使用媒体旁** 路，所有 RTP 媒体Teams终结点和 SBC 之间流动。 

请注意，SIP 流量始终通过 SIP 代理流动。 

## <a name="dtmf"></a>DTMF
媒体堆栈不支持带内 DTMF。
