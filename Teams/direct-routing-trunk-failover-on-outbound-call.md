---
title: 出站呼叫发生 Trunk 故障转移
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
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
description: 阅读本主题可了解如何处理出站呼叫从团队对会话边界控制器 (SBC) 上的中继故障转移。
ms.openlocfilehash: b2da454097fcb0f0af91aefad987d195e9e0f912
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298553"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="95452-103">出站呼叫发生 Trunk 故障转移</span><span class="sxs-lookup"><span data-stu-id="95452-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="95452-104">本主题介绍如何避免出站呼叫-从团队对会话边界控制器 (SBC) 上的中继故障转移。</span><span class="sxs-lookup"><span data-stu-id="95452-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="95452-105">在网络错误的故障转移</span><span class="sxs-lookup"><span data-stu-id="95452-105">Failover on network errors</span></span>

<span data-ttu-id="95452-106">如果出于任何原因，无法连接到中继，则将从不同的 Microsoft 数据中心尝试与同一个中继的连接。</span><span class="sxs-lookup"><span data-stu-id="95452-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="95452-107">中继可能不连接，例如，如果被拒绝的连接，如果 TLS 的超时设置，或有其他任何网络级别问题。</span><span class="sxs-lookup"><span data-stu-id="95452-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="95452-108">例如，连接可能无法如果管理员限制访问 SBC 只能从已知的 IP 地址，但离职放置在 SBC 访问控制列表 (ACL) 的所有 Microsoft 直接路由数据中心的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="95452-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="95452-109">接收从会话边界控制器 (SBC) 的特定 SIP 代码的故障转移</span><span class="sxs-lookup"><span data-stu-id="95452-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="95452-110">如果直接路由到传出 Invite 的响应中收到任何 4xx 或 6xx SIP 错误代码，请呼叫被视为完成默认情况下。</span><span class="sxs-lookup"><span data-stu-id="95452-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="95452-111">传出意味着来自团队客户端呼叫到公共公用电话交换网 (PSTN) 与以下通信流： 团队客户端的直接路由 >-> SBC-> 电话网络。</span><span class="sxs-lookup"><span data-stu-id="95452-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="95452-112">[会话初始协议 (SIP) RFC](https://tools.ietf.org/html/rfc3261)中，可以找到 SIP 代码的列表。</span><span class="sxs-lookup"><span data-stu-id="95452-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="95452-113">假定 SBC 其中替换为代码传入邀请回复的情况"408 请求超时： 服务器无法生成响应中合适的一段时间，例如，如果未能及时确定用户的位置。</span><span class="sxs-lookup"><span data-stu-id="95452-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="95452-114">客户端可以重复没有修改的请求随时都更高版本。"</span><span class="sxs-lookup"><span data-stu-id="95452-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="95452-115">此特定 SBC 可能会有连接到被叫方-可能由于网络配置错误或其他错误的困难。</span><span class="sxs-lookup"><span data-stu-id="95452-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="95452-116">但是，这可能是能够访问被叫方作为路由中是一个多个 SBC。</span><span class="sxs-lookup"><span data-stu-id="95452-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="95452-117">在下面的图中，当用户发出呼叫的电话号码，还有两个 SBCs 可能可以提供此呼叫作为路由中。</span><span class="sxs-lookup"><span data-stu-id="95452-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="95452-118">最初，SBC1.contoso.com 选定的呼叫，但 SBC1.contoso.com 不能够访问 PTSN 网络由于网络问题。</span><span class="sxs-lookup"><span data-stu-id="95452-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="95452-119">默认情况下，将此此时完成呼叫。</span><span class="sxs-lookup"><span data-stu-id="95452-119">By default, the call will be completed at this moment.</span></span> 
 
![显示 SBC 无法访问 PSTN 由于网络问题](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="95452-121">但是，其中可能可以将传入呼叫路由中没有一个详细的 SBC。</span><span class="sxs-lookup"><span data-stu-id="95452-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="95452-122">如果您配置参数`Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`，将尝试第二个 SBC-SBC2.contoso.com 如下图中：</span><span class="sxs-lookup"><span data-stu-id="95452-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![显示传送到第二个 SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="95452-124">参数-FailoverResponseCodes 并指定代码可帮助您可以精细优化您的路由，并避免设置潜在 SBC 不能因网络或其他问题而呼叫时的问题。</span><span class="sxs-lookup"><span data-stu-id="95452-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="95452-125">默认值： 408 503、 504</span><span class="sxs-lookup"><span data-stu-id="95452-125">Default values:  408, 503, 504</span></span>

