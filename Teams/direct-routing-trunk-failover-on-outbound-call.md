---
title: 出站呼叫发生 Trunk 故障转移
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 阅读本主题，了解如何处理从 Teams 到会话边界控制器的出站调用的中继故障转移 (SBC) 。
ms.openlocfilehash: 83320e93df7cbf476d71b3b9165d50ca387292b9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727861"
---
# <a name="trunk-failover-on-outbound-calls"></a>出站呼叫发生 Trunk 故障转移

本主题介绍如何避免出站调用上的中继故障转移- 从 Teams 到会话边界控制器 (SBC) 。

## <a name="failover-on-network-errors"></a>网络错误故障转移

如果由于任何原因无法连接中继，将尝试从不同的 Microsoft 数据中心连接到同一中继。 例如，如果连接被拒绝、TLS 超时或存在任何其他网络级别问题，则中继可能未连接。
例如，如果管理员仅从已知 IP 地址限制对 SBC 的访问，但忘记将所有 Microsoft 直接路由数据中心的 IP 地址放在 SBC 的访问控制列表 (ACL) ，则连接可能会失败。 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>从 SBC 会话边界控制器接收的特定 SIP 代码 (SBC) 

如果直接路由收到任何 4xx 或 6xx SIP 错误代码以响应传出邀请，则默认情况下，呼叫被视为已完成。 传出是指从 Teams 客户端呼叫公用电话交换网 (PSTN) ，流量流如下：Teams 客户端 -> 直接路由 -> SBC -> 电话网络。

SIP 代码列表可在 RFC 的会话启动协议[ (SIP) 中。](https://tools.ietf.org/html/rfc3261)

假设 SBC 在传入邀请中回复了代码"408 请求超时：服务器在合适的时间内无法生成响应，例如，如果它无法确定用户的时间位置。 客户端可以重复请求，无需在以后进行任何修改。"

此特定 SBC 在连接到被叫方时可能遇到问题，可能是因为网络配置错误或其他错误。 但是，路由中可能还有一个 SBC 能够到达被叫方。

下图中，当用户呼叫电话号码时，路由中可能有两个 SDC 可以传送此呼叫。 最初，SBC1.contoso.com 为呼叫选择 SBC1.contoso.com，但由于网络问题，无法连接到 PTSN 网络。
默认情况下，此时将完成调用。 
 
![显示 SBC 由于网络问题无法访问 PSTN 的示意图。](media/direct-routing-failover-response-codes1.png)

但路由中还有一个 SBC 可以传递调用。
如果配置 参数 `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` ，将尝试第二个 SBC -- SBC2.contoso.com 下图中所示：

![显示到第二个 SBC 的路由的示意图。](media/direct-routing-failover-response-codes2.png)

设置参数 -FailoverResponseCodes 并指定代码有助于微调路由，并避免 SBC 由于网络或其他问题而无法进行调用时的潜在问题。

默认值：408、503、504

