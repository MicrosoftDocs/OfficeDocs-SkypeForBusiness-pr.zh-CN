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
description: 阅读本主题，了解如何处理从 Teams 到会话边界控制器的出站呼叫的中继故障转移 (SBC) 。
ms.openlocfilehash: 0fa0d452a2611874be570f4e80a746bb07da0163
ms.sourcegitcommit: d7a86b3a72005764c18acb60eedf5163523ffae3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2022
ms.locfileid: "67457132"
---
# <a name="trunk-failover-on-outbound-calls"></a>出站呼叫发生 Trunk 故障转移

本主题介绍如何避免出站呼叫（从 Teams 到会话边界控制器 (SBC) ）的中继故障转移。

## <a name="failover-on-network-errors"></a>网络错误的故障转移

如果由于任何原因无法连接中继，则将从不同的 Microsoft 数据中心尝试与同一中继的连接。 数据中心可能位于当前地理区域之外的不同地理区域中。 如果连接被拒绝、TLS 超时或存在任何其他网络级别问题，则可能无法连接中继。

例如，如果管理员仅限制从已知 IP 地址访问 SBC，但忘记将所有 Microsoft 直接路由数据中心的 IP 地址置于 SBC 的 访问控制 列表 (ACL) ，则连接可能会失败。 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>从会话边界控制器 (SBC) 接收到的特定 SIP 代码的故障转移

如果直接路由收到任何 4xx 或 6xx SIP 错误代码来响应传出邀请，则默认情况下会将调用视为已完成。 传出意味着从 Teams 客户端呼叫到公共交换电话网络 (PSTN) 具有以下流量流：Teams 客户端 ->直接路由 -> SBC -> 电话网络。

可以在 [会话启动协议 (SIP) RFC 中找到 SIP](https://tools.ietf.org/html/rfc3261) 代码列表。

假设 SBC 在传入邀请上回复了代码“408 请求超时：服务器无法在适当时间内生成响应，例如，如果它无法及时确定用户的位置。 客户端 MAY 会在以后不修改的情况下重复请求。

此特定 SBC 可能难以连接到被调用方，原因可能是网络配置错误或其他错误。 但是，路由中还有一个 SBC 可能能够到达被调用方。

在下图中，当用户拨打电话号码时，路由中有两个 SBC 可能会传送此呼叫。 最初，为呼叫选择了 SBC1.contoso.com，但由于网络问题，SBC1.contoso.com 无法访问 PTSN 网络。
默认情况下，此时将完成调用。 
 
![显示 SBC 由于网络问题无法访问 PSTN 的示意图。](media/direct-routing-failover-response-codes1.png)

路由中还有一个 SBC 可能会传送呼叫。
如果配置参数 `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`，则会在下图中尝试第二个 SBC (SBC2.contoso.com) ：

![显示路由到第二个 SBC 的示意图。](media/direct-routing-failover-response-codes2.png)

设置参数 -FailoverResponseCodes 并指定代码有助于微调路由，避免在 SBC 因网络或其他问题而无法进行调用时出现的潜在问题。

默认值：408、503、504

