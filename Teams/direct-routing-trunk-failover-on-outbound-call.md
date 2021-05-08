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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 阅读本主题，了解如何处理从 Teams 到会话边界控制器的出站调用的中继故障转移 (SBC) 。
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836174"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="2b7a7-103">出站呼叫发生 Trunk 故障转移</span><span class="sxs-lookup"><span data-stu-id="2b7a7-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="2b7a7-104">本主题介绍如何避免出站调用上的中继故障转移- 从 Teams 到会话边界控制器 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="2b7a7-105">网络错误故障转移</span><span class="sxs-lookup"><span data-stu-id="2b7a7-105">Failover on network errors</span></span>

<span data-ttu-id="2b7a7-106">如果由于任何原因无法连接中继，将尝试从不同的 Microsoft 数据中心连接到同一中继。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="2b7a7-107">例如，如果连接被拒绝、TLS 超时或存在任何其他网络级别问题，则中继可能未连接。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="2b7a7-108">例如，如果管理员仅从已知 IP 地址限制对 SBC 的访问，但忘记将所有 Microsoft 直接路由数据中心的 IP 地址放在 SBC 的访问控制列表 (ACL) ，则连接可能会失败。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="2b7a7-109">从 SBC 会话边界控制器接收的特定 SIP 代码 (SBC) </span><span class="sxs-lookup"><span data-stu-id="2b7a7-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="2b7a7-110">如果直接路由收到任何 4xx 或 6xx SIP 错误代码以响应传出邀请，则默认情况下，呼叫被视为已完成。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="2b7a7-111">传出是指从 Teams 客户端呼叫公用电话交换网 (PSTN) ，流量流如下：Teams 客户端 -> 直接路由 -> SBC -> 电话网络。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="2b7a7-112">SIP 代码列表可在 SIP) 的会话启动协议[ (RFC 中。](https://tools.ietf.org/html/rfc3261)</span><span class="sxs-lookup"><span data-stu-id="2b7a7-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="2b7a7-113">假设 SBC 在传入邀请中回复了代码"408 请求超时：服务器在合适的时间内无法生成响应，例如，如果它无法确定用户的时间位置。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="2b7a7-114">客户端可以重复请求，无需在以后进行任何修改。"</span><span class="sxs-lookup"><span data-stu-id="2b7a7-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="2b7a7-115">此特定 SBC 在连接到被叫方时可能遇到问题，可能是因为网络配置错误或其他错误。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="2b7a7-116">但是，路由中可能还有一个 SBC 能够到达被叫方。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="2b7a7-117">下图中，当用户呼叫电话号码时，路由中可能有两个 SDC 可以传送此呼叫。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="2b7a7-118">最初，SBC1.contoso.com 为呼叫选择一个连接，SBC1.contoso.com 由于网络问题而无法连接到 PTSN 网络。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="2b7a7-119">默认情况下，此时将完成调用。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-119">By default, the call will be completed at this moment.</span></span> 
 
![显示 SBC 由于网络问题无法访问 PSTN 的示意图](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="2b7a7-121">但路由中还有一个 SBC 可以传递调用。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="2b7a7-122">如果配置 参数 `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` ，将尝试第二个 SBC - SBC2.contoso.com 如下图所示：</span><span class="sxs-lookup"><span data-stu-id="2b7a7-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![显示到第二个 SBC 的路由的示意图](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="2b7a7-124">设置参数 -FailoverResponseCodes 并指定代码有助于微调路由，并避免 SBC 由于网络或其他问题而无法进行调用时的潜在问题。</span><span class="sxs-lookup"><span data-stu-id="2b7a7-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="2b7a7-125">默认值：408、503、504</span><span class="sxs-lookup"><span data-stu-id="2b7a7-125">Default values:  408, 503, 504</span></span>

