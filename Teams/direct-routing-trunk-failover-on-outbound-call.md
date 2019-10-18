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
description: 阅读本主题，了解如何处理来自团队的出站呼叫和会话边界控制器（SBC）的中继故障转移。
ms.openlocfilehash: a5462de971fed32a0618800b257b9c6e37b462af
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572120"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="591b5-103">出站呼叫发生 Trunk 故障转移</span><span class="sxs-lookup"><span data-stu-id="591b5-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="591b5-104">本主题介绍如何在出站呼叫（从团队到会话边界控制器（SBC））中避免中继故障转移。</span><span class="sxs-lookup"><span data-stu-id="591b5-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="591b5-105">网络错误故障转移</span><span class="sxs-lookup"><span data-stu-id="591b5-105">Failover on network errors</span></span>

<span data-ttu-id="591b5-106">如果由于任何原因无法连接主干，则将从另一个 Microsoft 数据中心尝试连接到同一主干。</span><span class="sxs-lookup"><span data-stu-id="591b5-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="591b5-107">可能无法连接主干，例如，如果连接被拒绝、TLS 超时或存在任何其他网络级别问题。</span><span class="sxs-lookup"><span data-stu-id="591b5-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="591b5-108">例如，如果管理员仅通过众所周知的 IP 地址限制对 SBC 的访问，但忘记将所有 Microsoft 直接路由数据中心的 IP 地址放入 SBC 的访问控制列表（ACL）中，则连接可能失败。</span><span class="sxs-lookup"><span data-stu-id="591b5-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="591b5-109">从会话边界控制器（SBC）收到的特定 SIP 代码的故障转移</span><span class="sxs-lookup"><span data-stu-id="591b5-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="591b5-110">如果直接路由接收到任何用于响应传出邀请的4xx 或 6xx SIP 错误代码，则默认情况下该呼叫视为已完成。</span><span class="sxs-lookup"><span data-stu-id="591b5-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="591b5-111">"传出" 指通过以下通信流从团队客户端呼叫到公共交换电话网络（PSTN）的呼叫：团队客户端-> 直接路由-> SBC-> 电话网络。</span><span class="sxs-lookup"><span data-stu-id="591b5-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="591b5-112">SIP 代码列表可在 "[会话初始协议（SIP） RFC](https://tools.ietf.org/html/rfc3261)" 中找到。</span><span class="sxs-lookup"><span data-stu-id="591b5-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="591b5-113">假设 SBC 使用代码 "408 请求超时" 在传入邀请上回复的情况：服务器无法在合适的时间内生成响应，例如，如果无法确定用户的时间位置。</span><span class="sxs-lookup"><span data-stu-id="591b5-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="591b5-114">客户端可在以后任何时间重复请求，不进行任何修改。 "</span><span class="sxs-lookup"><span data-stu-id="591b5-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="591b5-115">此特定的 SBC 可能会在连接到被呼叫方时遇到问题，可能是因为网络配置错误或其他错误。</span><span class="sxs-lookup"><span data-stu-id="591b5-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="591b5-116">但是，路由中还有一个 SBC 可以访问被呼叫方。</span><span class="sxs-lookup"><span data-stu-id="591b5-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="591b5-117">在下图中，当用户拨打电话号码时，路由中有两个 SBCs 可潜在地传递此呼叫。</span><span class="sxs-lookup"><span data-stu-id="591b5-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="591b5-118">最初，SBC1.contoso.com 已选择用于呼叫，但 SBC1.contoso.com 无法联系 PTSN 网络，因为出现网络问题。</span><span class="sxs-lookup"><span data-stu-id="591b5-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="591b5-119">默认情况下，将在此时完成通话。</span><span class="sxs-lookup"><span data-stu-id="591b5-119">By default, the call will be completed at this moment.</span></span> 
 
![图表显示 SBC 由于网络问题而无法访问 PSTN](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="591b5-121">但是，路由中的一个 SBC 可能可以发送呼叫。</span><span class="sxs-lookup"><span data-stu-id="591b5-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="591b5-122">如果您配置该参数`Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`，将在下图中尝试第二个 SBC-SBC2.contoso.com：</span><span class="sxs-lookup"><span data-stu-id="591b5-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![显示路由到第二个 SBC 的图表](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="591b5-124">设置参数 FailoverResponseCodes 并指定代码可帮助你微调路由，并在 SBC 由于网络或其他问题而无法进行呼叫时避免潜在问题。</span><span class="sxs-lookup"><span data-stu-id="591b5-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="591b5-125">默认值：408、503、504</span><span class="sxs-lookup"><span data-stu-id="591b5-125">Default values:  408, 503, 504</span></span>

