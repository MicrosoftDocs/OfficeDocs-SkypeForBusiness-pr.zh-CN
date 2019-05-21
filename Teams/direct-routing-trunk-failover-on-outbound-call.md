---
title: 出站呼叫发生 Trunk 故障转移
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 阅读本主题, 了解如何处理来自团队的出站呼叫和会话边界控制器 (SBC) 的中继故障转移。
ms.openlocfilehash: e9efcfba696886c0fc4885778b79832956ccb893
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290360"
---
# <a name="trunk-failover-on-outbound-calls"></a>出站呼叫发生 Trunk 故障转移

本主题介绍如何在出站呼叫 (从团队到会话边界控制器 (SBC)) 中避免中继故障转移。

## <a name="failover-on-network-errors"></a>网络错误故障转移

如果由于任何原因无法连接主干, 则将从另一个 Microsoft 数据中心尝试连接到同一主干。 可能无法连接主干, 例如, 如果连接被拒绝、TLS 超时或存在任何其他网络级别问题。
例如, 如果管理员仅通过众所周知的 IP 地址限制对 SBC 的访问, 但忘记将所有 Microsoft 直接路由数据中心的 IP 地址放入 SBC 的访问控制列表 (ACL) 中, 则连接可能失败。 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>从会话边界控制器 (SBC) 收到的特定 SIP 代码的故障转移

如果直接路由接收到任何用于响应传出邀请的4xx 或 6xx SIP 错误代码, 则默认情况下该呼叫视为已完成。 "传出" 指通过以下通信流从团队客户端呼叫到公共交换电话网络 (PSTN) 的呼叫: 团队客户端-> 直接路由 > SBC-> 电话网络。

SIP 代码列表可在 "[会话初始协议 (SIP) RFC](https://tools.ietf.org/html/rfc3261)" 中找到。

假设 SBC 使用代码 "408 请求超时" 在传入邀请上回复的情况: 服务器无法在合适的时间内生成响应, 例如, 如果无法确定用户的时间位置。 客户端可在以后任何时间重复请求, 不进行任何修改。 "

此特定的 SBC 可能会在连接到被呼叫方时遇到问题, 可能是因为网络配置错误或其他错误。 但是, 路由中还有一个 SBC 可以访问被呼叫方。

在下图中, 当用户拨打电话号码时, 路由中有两个 SBCs 可潜在地传递此呼叫。 最初, SBC1.contoso.com 已选择用于呼叫, 但 SBC1.contoso.com 无法联系 PTSN 网络, 因为出现网络问题。
默认情况下, 将在此时完成通话。 
 
![显示 SBC 由于网络问题而无法访问 PSTN](media/direct-routing-failover-response-codes1.png)

但是, 路由中的一个 SBC 可能可以发送呼叫。
如果您配置该参数`Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, 将在下图中尝试第二个 SBC-SBC2.contoso.com:

![显示到第二个 SBC 的路由](media/direct-routing-failover-response-codes2.png)

设置参数 FailoverResponseCodes 并指定代码可帮助你微调路由, 并在 SBC 由于网络或其他问题而无法进行呼叫时避免潜在问题。

默认值: 408、503、504

