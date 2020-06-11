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
ms.openlocfilehash: 264e7e3de8031e8ac150c186078ff3d7ccff2f16
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691218"
---
# <a name="direct-routing---sip-protocol"></a><span data-ttu-id="ef767-103">直接路由-SIP 协议</span><span class="sxs-lookup"><span data-stu-id="ef767-103">Direct Routing - SIP protocol</span></span>

<span data-ttu-id="ef767-104">本文介绍直接路由如何实现会话初始协议（SIP）。</span><span class="sxs-lookup"><span data-stu-id="ef767-104">This article describes how Direct Routing implements the Session Initiation Protocol (SIP).</span></span> <span data-ttu-id="ef767-105">若要正确路由会话边界控制器（SBC）和 SIP 代理之间的流量，某些 SIP 参数必须具有特定值。</span><span class="sxs-lookup"><span data-stu-id="ef767-105">To properly route traffic between a Session Border Controller (SBC) and the SIP proxy, some SIP parameters must have specific values.</span></span> <span data-ttu-id="ef767-106">本文面向负责配置本地 SBC 和 SIP 代理服务之间的连接的语音管理员。</span><span class="sxs-lookup"><span data-stu-id="ef767-106">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a><span data-ttu-id="ef767-107">处理传入请求：查找租户和用户</span><span class="sxs-lookup"><span data-stu-id="ef767-107">Processing the incoming request: finding the tenant and user</span></span>

<span data-ttu-id="ef767-108">在传入呼叫中，SIP 代理需要找到呼叫指向的租户，并在此租户内找到特定用户。</span><span class="sxs-lookup"><span data-stu-id="ef767-108">On an incoming call, the SIP proxy needs to find the tenant to which the call is destined and find the specific user within this tenant.</span></span> <span data-ttu-id="ef767-109">租户管理员可以在多个租户中配置非已完成号码（例如 + 1001）。</span><span class="sxs-lookup"><span data-stu-id="ef767-109">The tenant administrator might configure non-DID numbers, for example +1001, in multiple tenants.</span></span> <span data-ttu-id="ef767-110">因此，查找要在其上执行数字查找的特定租户非常重要，因为在多个 Microsoft 365 或 Office 365 组织中的非数字可能相同。</span><span class="sxs-lookup"><span data-stu-id="ef767-110">Therefore, it is important to find the specific tenant on which to perform the number lookup because the non-DID numbers might be the same in multiple Microsoft 365 or Office 365 organizations.</span></span>  

<span data-ttu-id="ef767-111">本部分介绍 SIP 代理如何查找租户和用户，并对传入连接执行 SBC 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ef767-111">This section describes how the SIP proxy finds the tenant and the user, and performs authentication of the SBC on the incoming connection.</span></span>

<span data-ttu-id="ef767-112">下面是一个传入呼叫的 SIP 邀请消息的示例：</span><span class="sxs-lookup"><span data-stu-id="ef767-112">The following is an example of the SIP Invite message on an incoming call:</span></span>

| <span data-ttu-id="ef767-113">参数名称</span><span class="sxs-lookup"><span data-stu-id="ef767-113">Parameter name</span></span> | <span data-ttu-id="ef767-114">值的示例</span><span class="sxs-lookup"><span data-stu-id="ef767-114">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="ef767-115">请求 URI</span><span class="sxs-lookup"><span data-stu-id="ef767-115">Request-URI</span></span> | <span data-ttu-id="ef767-116">邀请 sip:+18338006777@sip.pstnhub.microsoft.com SIP/2。0</span><span class="sxs-lookup"><span data-stu-id="ef767-116">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span></span> |
| <span data-ttu-id="ef767-117">通过页眉</span><span class="sxs-lookup"><span data-stu-id="ef767-117">Via Header</span></span> | <span data-ttu-id="ef767-118">Via： SIP/2.0/TLS sbc1 biz： 5058; alias; branch = z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="ef767-118">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="ef767-119">最大转发标题</span><span class="sxs-lookup"><span data-stu-id="ef767-119">Max-Forwards header</span></span> | <span data-ttu-id="ef767-120">最大转发：68</span><span class="sxs-lookup"><span data-stu-id="ef767-120">Max-Forwards:68</span></span> |
| <span data-ttu-id="ef767-121">从页眉</span><span class="sxs-lookup"><span data-stu-id="ef767-121">From Header</span></span> | <span data-ttu-id="ef767-122">来自以下内容的页眉： <sip： 7168712781@sbc1 biz; transport = udp; tag = 1c747237679</span><span class="sxs-lookup"><span data-stu-id="ef767-122">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span></span> |
| <span data-ttu-id="ef767-123">到页眉</span><span class="sxs-lookup"><span data-stu-id="ef767-123">To Header</span></span> | <span data-ttu-id="ef767-124">收件人： sip:+183338006777@sbc1.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef767-124">To: sip:+183338006777@sbc1.adatum.biz</span></span> | 
| <span data-ttu-id="ef767-125">CSeq 标头</span><span class="sxs-lookup"><span data-stu-id="ef767-125">CSeq header</span></span> | <span data-ttu-id="ef767-126">CSeq：1个邀请</span><span class="sxs-lookup"><span data-stu-id="ef767-126">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="ef767-127">联系人页眉</span><span class="sxs-lookup"><span data-stu-id="ef767-127">Contact Header</span></span> | <span data-ttu-id="ef767-128">联系人： <sip： 68712781@sbc1 biz; 传输 = tls></span><span class="sxs-lookup"><span data-stu-id="ef767-128">Contact: <sip: 68712781@sbc1.adatum.biz;transport=tls></span></span> | 

<span data-ttu-id="ef767-129">收到邀请后，SIP 代理执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ef767-129">On receiving the invite, the SIP proxy performs the following steps:</span></span>

1. <span data-ttu-id="ef767-130">检查证书。</span><span class="sxs-lookup"><span data-stu-id="ef767-130">Check the certificate.</span></span> <span data-ttu-id="ef767-131">在初始连接中，直接路由服务获取在联系人标头中显示的 FQDN 名称，并将其与所显示的证书的公用名或使用者备用名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="ef767-131">On the initial connection, the Direct Routing service takes the FQDN name presented in the Contact header and matches it to the Common Name or Subject Alternative name of the presented certificate.</span></span> <span data-ttu-id="ef767-132">SBC 名称必须匹配以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="ef767-132">The SBC name must match one of the following options:</span></span>

   - <span data-ttu-id="ef767-133">选项 1.</span><span class="sxs-lookup"><span data-stu-id="ef767-133">Option 1.</span></span> <span data-ttu-id="ef767-134">在联系人标题中显示的完整 FQDN 名称必须与所显示的证书的通用名称/使用者备用名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="ef767-134">The full FQDN name presented in the Contact header must match the Common Name/Subject Alternative name of the presented certificate.</span></span>  

   - <span data-ttu-id="ef767-135">选项 2.</span><span class="sxs-lookup"><span data-stu-id="ef767-135">Option 2.</span></span> <span data-ttu-id="ef767-136">在联系人标题中显示的 FQDN 名称的域部分（例如 FQDN 名称 sbc1.adatum.biz 的 adatum.biz）必须与公用名称/使用者可选名称（例如 \*. adatum.biz）中的通配符相匹配。</span><span class="sxs-lookup"><span data-stu-id="ef767-136">The domain portion of the FQDN name presented in the Contact header (for example adatum.biz of the FQDN name sbc1.adatum.biz) must match the wildcard value in Common Name/Subject Alternative Name (for example \*.adatum.biz).</span></span>

2. <span data-ttu-id="ef767-137">尝试使用在联系人标题中显示的完整 FQDN 名称查找租户。</span><span class="sxs-lookup"><span data-stu-id="ef767-137">Try to find a tenant using the full FQDN name presented in the Contact header.</span></span>  

   <span data-ttu-id="ef767-138">检查联系人标题（sbc1.adatum.biz）中的 FQDN 名称是否注册为任何 Microsoft 365 或 Office 365 组织中的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="ef767-138">Check if the FQDN name from the Contact header (sbc1.adatum.biz) is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="ef767-139">如果找到，将在具有注册为域名的 SBC FQDN 的租户中执行用户查找。</span><span class="sxs-lookup"><span data-stu-id="ef767-139">If found, the lookup of the user is performed in the tenant that has the SBC FQDN registered as a Domain name.</span></span> <span data-ttu-id="ef767-140">如果未找到，则应用步骤3。</span><span class="sxs-lookup"><span data-stu-id="ef767-140">If not found, Step 3 applies.</span></span>   

3. <span data-ttu-id="ef767-141">步骤3仅适用于步骤2失败的情况。</span><span class="sxs-lookup"><span data-stu-id="ef767-141">Step 3 only applies if Step 2 failed.</span></span> 

   <span data-ttu-id="ef767-142">从 FQDN 中删除主机部分，显示在联系人标头（FQDN： sbc12.adatum.biz 中，删除主机部分后： adatum.biz），然后检查此名称是否注册为任何 Microsoft 365 或 Office 365 组织中的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="ef767-142">Remove the host portion from the FQDN, presented in the Contact header (FQDN: sbc12.adatum.biz, after removing the host portion: adatum.biz), and check if this name is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="ef767-143">如果找到，将在此租户中执行用户查找。</span><span class="sxs-lookup"><span data-stu-id="ef767-143">If found, the user lookup is performed in this tenant.</span></span> <span data-ttu-id="ef767-144">如果找不到，调用将失败。</span><span class="sxs-lookup"><span data-stu-id="ef767-144">If not found, the call fails.</span></span>

4. <span data-ttu-id="ef767-145">使用请求 URI 中显示的电话号码，在步骤2或3中发现的租户内执行反向号码查找。</span><span class="sxs-lookup"><span data-stu-id="ef767-145">Using the phone number presented in the Request-URI, perform the reverse number lookup within the tenant found in Step 2 or 3.</span></span> <span data-ttu-id="ef767-146">将所提供的电话号码与上一步中找到的租户内的用户 SIP URI 相匹配。</span><span class="sxs-lookup"><span data-stu-id="ef767-146">Match the presented phone number to a user SIP URI within the tenant found on the previous step.</span></span>

5. <span data-ttu-id="ef767-147">应用干线设置。</span><span class="sxs-lookup"><span data-stu-id="ef767-147">Apply trunk settings.</span></span> <span data-ttu-id="ef767-148">查找由租户管理员为此 SBC 设置的参数。</span><span class="sxs-lookup"><span data-stu-id="ef767-148">Find the parameters set by the tenant admin for this SBC.</span></span>

   <span data-ttu-id="ef767-149">Microsoft 不支持在 Microsoft SIP 代理和成对的 SBC 之间拥有第三方 SIP 代理或用户代理服务器，这可能会修改成对的 SBC 创建的请求 URI。</span><span class="sxs-lookup"><span data-stu-id="ef767-149">Microsoft does not support having a third-party SIP proxy or User Agent Server between the Microsoft SIP proxy and the paired SBC, which might modify the Request URI created by the paired SBC.</span></span>

   <span data-ttu-id="ef767-150">本文稍后部分将介绍两个查找（步骤2和3）所需的情况（步骤2和步骤3）。</span><span class="sxs-lookup"><span data-stu-id="ef767-150">The requirements for the two lookups (steps 2 and 3) needed for the scenario where one SBC is interconnected to many tenants (carrier scenario) are covered later in this article.</span></span>

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a><span data-ttu-id="ef767-151">联系人标题和请求 URI 的详细要求</span><span class="sxs-lookup"><span data-stu-id="ef767-151">Detailed requirements for Contact header and Request-URI</span></span>

#### <a name="contact-header"></a><span data-ttu-id="ef767-152">联系人页眉</span><span class="sxs-lookup"><span data-stu-id="ef767-152">Contact header</span></span>

<span data-ttu-id="ef767-153">对于所有传入的 Microsoft SIP 代理呼叫，联系人头必须在 URI 主机名中具有成对的 SBC FQDN，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef767-153">For all incoming calls to the Microsoft SIP proxy, the Contact header must have the paired SBC FQDN in the URI hostname as follows:</span></span>

<span data-ttu-id="ef767-154">语法： Contact： <sip： SBC 的电话或 sip address@FQDN; 传输 = tls></span><span class="sxs-lookup"><span data-stu-id="ef767-154">Syntax: Contact:  <sip:phone or sip address@FQDN of the SBC;transport=tls></span></span> 

<span data-ttu-id="ef767-155">此名称还必须位于所显示的证书的 "公用名" 或 "主题备用名称" 字段中。</span><span class="sxs-lookup"><span data-stu-id="ef767-155">This name must also be in the Common Name or Subject Alternative name field(s) of the presented certificate.</span></span> <span data-ttu-id="ef767-156">Microsoft 支持在证书的 "公用名" 或 "主题备用名称" 字段中使用名称的通配符。</span><span class="sxs-lookup"><span data-stu-id="ef767-156">Microsoft supports using wildcard values of the name(s) in the Common Name or Subject Alternative Name fields of the certificate.</span></span>   

<span data-ttu-id="ef767-157">在[RFC 2818 的第3.1 节](https://tools.ietf.org/html/rfc2818#section-3.1)中介绍了对通配符的支持。</span><span class="sxs-lookup"><span data-stu-id="ef767-157">The support for wildcards is described in [RFC 2818, section 3.1](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="ef767-158">具体地说</span><span class="sxs-lookup"><span data-stu-id="ef767-158">Specifically:</span></span>

<span data-ttu-id="ef767-159">*"名称可以包含通配符， \* 该字符被视为匹配任何单个域名组件或组件片段。例如， \* a.com 匹配 foo.a.com，而不是 bar.foo.a.com \* 匹配 foo.com，而不是 bar.com。 "*</span><span class="sxs-lookup"><span data-stu-id="ef767-159">*"Names may contain the wildcard character \* which is considered to match any single domain name component or component fragment. E.g., \*.a.com matches foo.a.com but not bar.foo.a.com. f\*.com matches foo.com but not bar.com."*</span></span>

<span data-ttu-id="ef767-160">如果由 SBC 发送 SIP 消息中显示的联系人标头中的多个值，则仅使用联系人标头第一个值的 FQDN 部分。</span><span class="sxs-lookup"><span data-stu-id="ef767-160">If more than one value in the Contact header presented in a SIP message is sent by the SBC, only the FQDN portion of the first value of the Contact header is used.</span></span>

#### <a name="request-uri"></a><span data-ttu-id="ef767-161">请求 URI</span><span class="sxs-lookup"><span data-stu-id="ef767-161">Request-URI</span></span> 

<span data-ttu-id="ef767-162">对于所有传入呼叫，请求 URI 用于匹配用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="ef767-162">For all incoming calls, the Request-URI is used to match the phone number to a user.</span></span>   

<span data-ttu-id="ef767-163">当前电话号码必须包含加号（+），如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="ef767-163">Currently The phone number must contain a plus sign (+) as shown in the following example.</span></span> 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a><span data-ttu-id="ef767-164">联系人和记录-路线标题注意事项</span><span class="sxs-lookup"><span data-stu-id="ef767-164">Contact and Record-Route headers considerations</span></span>

<span data-ttu-id="ef767-165">SIP 代理需要为新的对话客户端事务（如再见或重新邀请）和答复 SIP 选项计算下一个跃点 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ef767-165">The SIP proxy needs to calculate the next hop FQDN for new in-dialog client transactions (for example Bye or Re-Invite), and when replying to SIP Options.</span></span> <span data-ttu-id="ef767-166">使用 "联系人" 或 "记录"-路线。</span><span class="sxs-lookup"><span data-stu-id="ef767-166">Either Contact or Record-Route are used.</span></span> 

<span data-ttu-id="ef767-167">根据 RFC 3261，任何可能导致新对话的请求都需要联系人标题。</span><span class="sxs-lookup"><span data-stu-id="ef767-167">According to RFC 3261, Contact header is required in any request that can result in a new dialog.</span></span> <span data-ttu-id="ef767-168">仅当代理希望在对话框中保留未来请求的路径时，才需要记录路由。</span><span class="sxs-lookup"><span data-stu-id="ef767-168">The Record-Route is only required if a proxy wants to stay on the path of future requests in a dialog.</span></span> 

<span data-ttu-id="ef767-169">Microsoft 建议仅出于以下原因使用联系人标头：</span><span class="sxs-lookup"><span data-stu-id="ef767-169">Microsoft recommends using only Contact header for the following reasons:</span></span>

- <span data-ttu-id="ef767-170">在每个 RFC 3261 中，如果代理希望在对话中保留未来请求的路径，而在 Microsoft SIP 代理和成对的 SBC 之间传输所有通信，则使用记录路由。</span><span class="sxs-lookup"><span data-stu-id="ef767-170">Per RFC 3261, Record-Route is used if a proxy wants to stay on the path of future requests in a dialog, which is not essential as all traffic goes between the Microsoft SIP proxy and the paired SBC.</span></span> <span data-ttu-id="ef767-171">在 SBC 和 Microsoft SIP 代理之间不需要中间代理服务器。</span><span class="sxs-lookup"><span data-stu-id="ef767-171">There is no need for an intermediate proxy server between the SBC and Microsoft SIP proxy.</span></span>

- <span data-ttu-id="ef767-172">Microsoft SIP 代理仅使用联系人头（而不是记录路由）来确定发送出站 ping 选项时的下一跃点。</span><span class="sxs-lookup"><span data-stu-id="ef767-172">The Microsoft SIP proxy uses only Contact header (not Record-Route) to determine the next hop when sending outbound ping Options.</span></span> <span data-ttu-id="ef767-173">仅配置一个参数（联系人），而不是两个（联系人和记录-路线）可简化管理。</span><span class="sxs-lookup"><span data-stu-id="ef767-173">Configuring only one parameter (Contact) instead of two (Contact and Record-Route) simplifies the administration.</span></span>

<span data-ttu-id="ef767-174">要计算下一跃点，SIP 代理使用：</span><span class="sxs-lookup"><span data-stu-id="ef767-174">To calculate the next hop, the SIP proxy uses:</span></span>

- <span data-ttu-id="ef767-175">优先级1。</span><span class="sxs-lookup"><span data-stu-id="ef767-175">Priority 1.</span></span> <span data-ttu-id="ef767-176">顶层记录-路由。</span><span class="sxs-lookup"><span data-stu-id="ef767-176">Top-level Record-Route.</span></span> <span data-ttu-id="ef767-177">如果顶级记录路由包含 FQDN 名称或 IP，则 FQDN 名称或 IP 用于创建出站内置对话连接。</span><span class="sxs-lookup"><span data-stu-id="ef767-177">If the top-level Record-Route contains the FQDN name or IP, the FQDN name or IP is used to make the outbound in-dialog connection.</span></span>

- <span data-ttu-id="ef767-178">优先级2。</span><span class="sxs-lookup"><span data-stu-id="ef767-178">Priority 2.</span></span> <span data-ttu-id="ef767-179">联系人标题。</span><span class="sxs-lookup"><span data-stu-id="ef767-179">Contact header.</span></span> <span data-ttu-id="ef767-180">如果记录路径不存在，SIP 代理将查找联系人标头的值以建立出站连接。</span><span class="sxs-lookup"><span data-stu-id="ef767-180">If Record-Route does not exist, the SIP proxy will look up the value of the Contact header to make the outbound connection.</span></span> <span data-ttu-id="ef767-181">（这是推荐的配置。）</span><span class="sxs-lookup"><span data-stu-id="ef767-181">(This is the recommended configuration.)</span></span>

<span data-ttu-id="ef767-182">如果同时使用了联系人和记录路线，则 SBC 管理员必须保持其值相同，从而导致管理开销。</span><span class="sxs-lookup"><span data-stu-id="ef767-182">If both Contact and Record-Route are used, the SBC administrator must keep their values identical, which causes administrative overhead.</span></span> 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a><span data-ttu-id="ef767-183">在联系人或记录中使用 FQDN 名称-路由</span><span class="sxs-lookup"><span data-stu-id="ef767-183">Use of FQDN name in Contact or Record-Route</span></span>

<span data-ttu-id="ef767-184">在记录-路由或联系人中不支持使用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ef767-184">Use of an IP address is not supported in either Record-Route or Contact.</span></span> <span data-ttu-id="ef767-185">唯一支持的选项是 FQDN，它必须与 SBC 证书的公用名称或使用者备用名称匹配（证书中的通配符受支持）。</span><span class="sxs-lookup"><span data-stu-id="ef767-185">The only supported option is an FQDN, which must match either the Common Name or Subject Alternative Name of the SBC certificate (wildcard values in the certificate are supported).</span></span>

- <span data-ttu-id="ef767-186">如果 IP 地址显示在 "记录"-"路由" 或 "联系人" 中，则证书检查失败，并且呼叫失败。</span><span class="sxs-lookup"><span data-stu-id="ef767-186">If an IP address is presented in Record-route or Contact, the certificate check fails and the call fails.</span></span>

- <span data-ttu-id="ef767-187">如果 FQDN 与所显示的证书中的常见或主题备用名称的值不匹配，则调用将失败。</span><span class="sxs-lookup"><span data-stu-id="ef767-187">If the FQDN does not match the value of the Common or Subject Alternative Name in the presented certificate, the call fails.</span></span> 

## <a name="inbound-call-sip-dialog-description"></a><span data-ttu-id="ef767-188">入站呼叫： SIP 对话框说明</span><span class="sxs-lookup"><span data-stu-id="ef767-188">Inbound call: SIP dialog description</span></span>

<span data-ttu-id="ef767-189">下表总结了非绕过和绕过模式之间的通话流差异和相似性：</span><span class="sxs-lookup"><span data-stu-id="ef767-189">The following table below summarizes the call flow differences and similarities between non-bypass and bypass modes:</span></span>

| <span data-ttu-id="ef767-190">参数名称</span><span class="sxs-lookup"><span data-stu-id="ef767-190">Parameter name</span></span> | <span data-ttu-id="ef767-191">非绕过模式</span><span class="sxs-lookup"><span data-stu-id="ef767-191">Non-bypass mode</span></span> | <span data-ttu-id="ef767-192">绕过模式</span><span class="sxs-lookup"><span data-stu-id="ef767-192">Bypass mode</span></span>
| :---------------------  |:---------------------- |:----------------|
| <span data-ttu-id="ef767-193">183和200消息中的媒体候选人来自</span><span class="sxs-lookup"><span data-stu-id="ef767-193">Media candidates in 183 and 200 messages coming from</span></span> | <span data-ttu-id="ef767-194">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="ef767-194">Media processors</span></span> | <span data-ttu-id="ef767-195">客户端</span><span class="sxs-lookup"><span data-stu-id="ef767-195">Clients</span></span> | 
| <span data-ttu-id="ef767-196">SBC 可以接收的183消息数</span><span class="sxs-lookup"><span data-stu-id="ef767-196">Number of 183 messages SBC can receive</span></span> | <span data-ttu-id="ef767-197">每个会话一个</span><span class="sxs-lookup"><span data-stu-id="ef767-197">One per session</span></span> | <span data-ttu-id="ef767-198">名</span><span class="sxs-lookup"><span data-stu-id="ef767-198">Multiple</span></span> | 
| <span data-ttu-id="ef767-199">可通过临时答案进行呼叫（183）</span><span class="sxs-lookup"><span data-stu-id="ef767-199">Call can be with provisional answer (183)</span></span> | <span data-ttu-id="ef767-200">是</span><span class="sxs-lookup"><span data-stu-id="ef767-200">Yes</span></span> | <span data-ttu-id="ef767-201">是</span><span class="sxs-lookup"><span data-stu-id="ef767-201">Yes</span></span> |
| <span data-ttu-id="ef767-202">通话可能没有临时应答（183）</span><span class="sxs-lookup"><span data-stu-id="ef767-202">Call can be without provisional answer (183)</span></span> | <span data-ttu-id="ef767-203">是</span><span class="sxs-lookup"><span data-stu-id="ef767-203">Yes</span></span> | <span data-ttu-id="ef767-204">是</span><span class="sxs-lookup"><span data-stu-id="ef767-204">Yes</span></span> |

###  <a name="non-media-bypass-flow"></a><span data-ttu-id="ef767-205">非媒体旁路流</span><span class="sxs-lookup"><span data-stu-id="ef767-205">Non-media bypass flow</span></span>

<span data-ttu-id="ef767-206">团队用户可能同时具有多个终结点。</span><span class="sxs-lookup"><span data-stu-id="ef767-206">A Teams user might have multiple endpoints at the same time.</span></span> <span data-ttu-id="ef767-207">例如，Windows 客户端团队、iPhone 客户端团队和团队手机（团队 Android 客户端）。</span><span class="sxs-lookup"><span data-stu-id="ef767-207">For example, Teams for Windows client, Teams for iPhone client, and Teams Phone (Teams Android client).</span></span> <span data-ttu-id="ef767-208">每个终结点可能发出 HTTP rest 的信号，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef767-208">Each endpoint might signal an HTTP rest as follows:</span></span>

-   <span data-ttu-id="ef767-209">呼叫进度–由 SIP 代理将其转换为 SIP 消息180。</span><span class="sxs-lookup"><span data-stu-id="ef767-209">Call progress – converted by the SIP proxy to the SIP message 180.</span></span> <span data-ttu-id="ef767-210">在接收消息180时，SBC 必须生成本地震铃。</span><span class="sxs-lookup"><span data-stu-id="ef767-210">On receiving message 180, the SBC must generate local ringing.</span></span>

-   <span data-ttu-id="ef767-211">媒体应答–通过 SIP 代理将其转换为消息183，在会话描述协议（SDP）中使用媒体候选人。</span><span class="sxs-lookup"><span data-stu-id="ef767-211">Media answer – converted by the SIP proxy to message 183 with media candidates in Session Description Protocol (SDP).</span></span> <span data-ttu-id="ef767-212">在接收消息183时，SBC 预期连接到在 SDP 消息中接收的媒体候选人。</span><span class="sxs-lookup"><span data-stu-id="ef767-212">On receiving message 183, the SBC expects to connect to the media candidates received in the SDP message.</span></span> <span data-ttu-id="ef767-213">请注意，在某些情况下，可能不会生成媒体答案，并且终结点可能会收到 "接受通话" 消息的答案。</span><span class="sxs-lookup"><span data-stu-id="ef767-213">Note that in some cases the Media answer might not be generated, and the end point might answer with “Call Accepted” message.</span></span>

-   <span data-ttu-id="ef767-214">通话被接受–由 SIP 代理通过 SDP 转换到 SIP 消息200。</span><span class="sxs-lookup"><span data-stu-id="ef767-214">Call accepted – converted by the SIP proxy to SIP message 200 with SDP.</span></span> <span data-ttu-id="ef767-215">在接收消息200时，SBC 应在提供的 SDP 候选人中发送和接收媒体。</span><span class="sxs-lookup"><span data-stu-id="ef767-215">On receiving message 200, the SBC is expected to send and receive media to and from the provided SDP candidates.</span></span>

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a><span data-ttu-id="ef767-216">多个终结点通过临时答案进行铃声</span><span class="sxs-lookup"><span data-stu-id="ef767-216">Multiple endpoints ringing with provisional answer</span></span>

1.  <span data-ttu-id="ef767-217">收到来自 SBC 的第一个邀请后，SIP 代理会发送消息 "SIP SIP/2.0 100 尝试"，并通知所有最终用户终结点的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="ef767-217">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="ef767-218">收到通知后，每个终结点将开始向 SIP 代理发送 "呼叫进度" 消息。</span><span class="sxs-lookup"><span data-stu-id="ef767-218">Upon notification, each endpoint will start ringing and sending "Call progress” messages to the SIP proxy.</span></span> <span data-ttu-id="ef767-219">由于团队用户可以有多个终结点，因此 SIP 代理可能会收到多个呼叫进度消息。</span><span class="sxs-lookup"><span data-stu-id="ef767-219">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="ef767-220">对于从客户收到的每个呼叫进度消息，SIP 代理将呼叫进度消息转换为 SIP 消息 "SIP SIP/2.0 180 尝试"。</span><span class="sxs-lookup"><span data-stu-id="ef767-220">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span> <span data-ttu-id="ef767-221">发送此类消息的间隔由来自呼叫控制器的接收邮件的间隔定义。</span><span class="sxs-lookup"><span data-stu-id="ef767-221">The interval for sending such messages is defined by the interval of the receiving messages from the Call Controller.</span></span> <span data-ttu-id="ef767-222">在下图中，SIP 代理生成了 2 180 封邮件。</span><span class="sxs-lookup"><span data-stu-id="ef767-222">In the following diagram, there are two 180 messages generated by the SIP proxy.</span></span> <span data-ttu-id="ef767-223">这些消息来自用户的两个团队终结点。</span><span class="sxs-lookup"><span data-stu-id="ef767-223">These messages come from the two Teams endpoints of the user.</span></span> <span data-ttu-id="ef767-224">每个客户都有一个唯一的标记 ID。</span><span class="sxs-lookup"><span data-stu-id="ef767-224">The clients each have a unique Tag ID.</span></span>  <span data-ttu-id="ef767-225">来自不同终结点的每条消息将是一个单独的会话（"收件人" 字段中的参数 "tag" 将不同）。</span><span class="sxs-lookup"><span data-stu-id="ef767-225">Every message coming from a different endpoint will be a separate session (the parameter “tag” in the “To” field will be different).</span></span> <span data-ttu-id="ef767-226">但是，终结点可能不会生成消息180并立即发送消息183，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="ef767-226">But an endpoint might not generate message 180 and send message 183 right away as shown in the following diagram.</span></span>

4.  <span data-ttu-id="ef767-227">一旦终结点生成带有终结点媒体候选人的 IP 地址的媒体答案消息，SIP 代理会将收到的消息转换为 "SIP 183 会话进度" 消息，该消息包含客户端从媒体处理器替换的来自客户端的 sdp。</span><span class="sxs-lookup"><span data-stu-id="ef767-227">Once an endpoint generates a Media Answer message with the IP addresses of endpoint’s media candidates, the SIP proxy converts the message received to a "SIP 183 Session Progress" message with the SDP from the client replaced by the SDP from the Media Processor.</span></span> <span data-ttu-id="ef767-228">在下图中，派生2的终结点应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="ef767-228">In the following diagram, the endpoint from Fork 2 answered the call.</span></span> <span data-ttu-id="ef767-229">如果主干是非绕过的，则 183 SIP 消息仅生成一次（即环机器人或客户端终结点）。</span><span class="sxs-lookup"><span data-stu-id="ef767-229">If the trunk is non-bypassed, the 183 SIP message is generated only once (either Ring Bot or Client End Point).</span></span> <span data-ttu-id="ef767-230">183可能会产生一个现有的分叉或开始一个新的分叉。</span><span class="sxs-lookup"><span data-stu-id="ef767-230">The 183 might come on an existing fork or start a new one.</span></span>

5.  <span data-ttu-id="ef767-231">将使用接受呼叫的终结点的最终候选项发送呼叫接受消息。</span><span class="sxs-lookup"><span data-stu-id="ef767-231">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="ef767-232">通话接受消息将转换为 SIP 消息200。</span><span class="sxs-lookup"><span data-stu-id="ef767-232">The Call Acceptance message is converted to SIP message 200.</span></span> 

![显示多个终结点和临时应答的图表](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a><span data-ttu-id="ef767-234">多个终结点在没有临时应答的情况下响铃</span><span class="sxs-lookup"><span data-stu-id="ef767-234">Multiple endpoints ringing without provisional answer</span></span>

1.  <span data-ttu-id="ef767-235">收到来自 SBC 的第一个邀请后，SIP 代理会发送消息 "SIP SIP/2.0 100 尝试"，并通知所有最终用户终结点的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="ef767-235">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="ef767-236">收到通知后，每个终结点将开始向 SIP 代理发送消息 "呼叫进度"。</span><span class="sxs-lookup"><span data-stu-id="ef767-236">Upon notification, each endpoint will start ringing and sending the message "Call progress” to the SIP proxy.</span></span> <span data-ttu-id="ef767-237">由于团队用户可以有多个终结点，因此 SIP 代理可能会收到多个呼叫进度消息。</span><span class="sxs-lookup"><span data-stu-id="ef767-237">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="ef767-238">对于从客户收到的每个呼叫进度消息，SIP 代理将呼叫进度消息转换为 SIP 消息 "SIP SIP/2.0 180 尝试"。</span><span class="sxs-lookup"><span data-stu-id="ef767-238">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span>  <span data-ttu-id="ef767-239">发送消息的间隔由接收来自呼叫控制器的邮件的间隔定义。</span><span class="sxs-lookup"><span data-stu-id="ef767-239">The interval for sending the messages is defined by the interval of receiving the messages from the Call Controller.</span></span> <span data-ttu-id="ef767-240">在下面的图片中，SIP 代理生成 2 180 消息，这意味着用户登录到三个团队客户和每个客户端发送呼叫进度。</span><span class="sxs-lookup"><span data-stu-id="ef767-240">On the picture below there are two 180 messages generated by the SIP proxy, meaning that user logged into three Teams clients and each client send the call progress.</span></span> <span data-ttu-id="ef767-241">每封邮件都将是单独的会话（"收件人" 字段中的参数 "标记" 不同）</span><span class="sxs-lookup"><span data-stu-id="ef767-241">Every message will be a separate session (parameter “tag” in “To” field is different)</span></span>

4.  <span data-ttu-id="ef767-242">将使用接受呼叫的终结点的最终候选项发送呼叫接受消息。</span><span class="sxs-lookup"><span data-stu-id="ef767-242">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="ef767-243">通话接受消息将转换为 SIP 消息200。</span><span class="sxs-lookup"><span data-stu-id="ef767-243">The Call Acceptance message is converted to SIP message 200.</span></span> 

![图表显示多个终结点在没有临时应答的情况下响铃](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a><span data-ttu-id="ef767-245">媒体绕过流</span><span class="sxs-lookup"><span data-stu-id="ef767-245">Media bypass flow</span></span>

<span data-ttu-id="ef767-246">媒体绕过方案中使用的消息（100尝试、180、183）相同。</span><span class="sxs-lookup"><span data-stu-id="ef767-246">The same messages (100 Trying, 180, 183) are used in the media bypass scenario.</span></span> 

<span data-ttu-id="ef767-247">下面的架构显示了绕过通话流的示例。</span><span class="sxs-lookup"><span data-stu-id="ef767-247">The schema below shows an example of the bypass call flow.</span></span> <span data-ttu-id="ef767-248">请注意，媒体候选人可以来自不同的终结点。</span><span class="sxs-lookup"><span data-stu-id="ef767-248">Note that the media candidates can come from different endpoints.</span></span> 

![显示多个终结点和临时应答的图表](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a><span data-ttu-id="ef767-250">替换选项</span><span class="sxs-lookup"><span data-stu-id="ef767-250">Replaces option</span></span>

<span data-ttu-id="ef767-251">SBC 必须支持替换的邀请。</span><span class="sxs-lookup"><span data-stu-id="ef767-251">The SBC must support Invite with Replaces.</span></span>

## <a name="size-of-sdp-considerations"></a><span data-ttu-id="ef767-252">SDP 注意事项的大小</span><span class="sxs-lookup"><span data-stu-id="ef767-252">Size of SDP considerations</span></span>

<span data-ttu-id="ef767-253">直接路由接口可能会发送超过1500字节的 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="ef767-253">The Direct Routing interface might send a SIP message exceeding 1,500 bytes.</span></span>  <span data-ttu-id="ef767-254">SDP 的大小主要是导致这种情况。</span><span class="sxs-lookup"><span data-stu-id="ef767-254">The size of SDP primarily causes this.</span></span> <span data-ttu-id="ef767-255">但是，如果在 SBC 后面有一个 UDP 主干，则它可能会在从 Microsoft SIP 代理转发到未修改的中继时拒绝该消息。</span><span class="sxs-lookup"><span data-stu-id="ef767-255">However, if there is a UDP trunk behind the SBC, it might reject the message if it is forwarded from the Microsoft SIP proxy to the trunk unmodified.</span></span> <span data-ttu-id="ef767-256">Microsoft 建议在 SBC 上将消息发送到 UDP 中继时，在 SBC 上去除一些值。</span><span class="sxs-lookup"><span data-stu-id="ef767-256">Microsoft recommends stripping some values in SDP on the SBC when sending the message to the UDP trunks.</span></span> <span data-ttu-id="ef767-257">例如，可以删除 ICE 候选人或未使用的编解码器。</span><span class="sxs-lookup"><span data-stu-id="ef767-257">For example, the ICE candidates or unused codecs can be removed.</span></span>

## <a name="call-transfer"></a><span data-ttu-id="ef767-258">呼叫转接</span><span class="sxs-lookup"><span data-stu-id="ef767-258">Call transfer</span></span>

<span data-ttu-id="ef767-259">直接路由支持呼叫转接的两种方法：</span><span class="sxs-lookup"><span data-stu-id="ef767-259">Direct Routing supports two methods for call transfer:</span></span>

- <span data-ttu-id="ef767-260">选项 1.</span><span class="sxs-lookup"><span data-stu-id="ef767-260">Option 1.</span></span> <span data-ttu-id="ef767-261">SIP 代理进程从本地引用客户端，并充当 RFC 3892 第7.1 节中所述的 Referee。</span><span class="sxs-lookup"><span data-stu-id="ef767-261">SIP proxy processes Refer from the client locally and acts as a Referee as described in section 7.1 of RFC 3892.</span></span>

  <span data-ttu-id="ef767-262">使用此选项，SIP 代理将终止传输并添加新邀请。</span><span class="sxs-lookup"><span data-stu-id="ef767-262">With this option, the SIP proxy terminates the transfer and adds a new Invite.</span></span> 


- <span data-ttu-id="ef767-263">选项 2.</span><span class="sxs-lookup"><span data-stu-id="ef767-263">Option 2.</span></span> <span data-ttu-id="ef767-264">SIP 代理发送对 SBC 的引用并充当 Transferor，如 RFC 5589 的第6节中的描述所述。</span><span class="sxs-lookup"><span data-stu-id="ef767-264">SIP proxy sends the Refer to the SBC and acts as a Transferor as describing in Section 6 of RFC 5589.</span></span>

  <span data-ttu-id="ef767-265">使用此选项，SIP 代理会发送一个指向 SBC 的参考，并期望 SBC 完全处理传输。</span><span class="sxs-lookup"><span data-stu-id="ef767-265">With this option, the SIP proxy sends a Refer to the SBC and expects the SBC to handle the Transfer fully.</span></span>

<span data-ttu-id="ef767-266">SIP 代理根据 SBC 所报告的功能选择该方法。</span><span class="sxs-lookup"><span data-stu-id="ef767-266">The SIP proxy selects the method based on the capabilities reported by the SBC.</span></span> <span data-ttu-id="ef767-267">如果 SBC 指示它支持方法 "参阅"，则 SIP 代理将对呼叫转移使用选项2。</span><span class="sxs-lookup"><span data-stu-id="ef767-267">If the SBC indicates that it supports the method “Refer”, the SIP proxy will use Option 2 for call transfers.</span></span>

<span data-ttu-id="ef767-268">下面是一个 SBC 的示例，该示例发送消息指出支持引用方法：</span><span class="sxs-lookup"><span data-stu-id="ef767-268">The following is an example of an SBC sending the message that the Refer method is supported:</span></span>

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

<span data-ttu-id="ef767-269">如果 SBC 未指示引用为受支持的方法，直接路由将使用选项1（SIP 代理充当 Referee）。</span><span class="sxs-lookup"><span data-stu-id="ef767-269">If the SBC doesn’t indicate that Refer as a supported method, Direct Routing will use Option 1 (SIP proxy acts as a Referee) .</span></span> <span data-ttu-id="ef767-270">SBC 还必须发出支持 Notify 方法的信号：</span><span class="sxs-lookup"><span data-stu-id="ef767-270">The SBC  must also signal that it supports the Notify method:</span></span>

<span data-ttu-id="ef767-271">SBC 的示例（指示不支持参考方法）：</span><span class="sxs-lookup"><span data-stu-id="ef767-271">Example of SBC indicating that Refer method is not supported:</span></span>

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a><span data-ttu-id="ef767-272">SIP 代理进程在本地引用客户端并充当 Referee</span><span class="sxs-lookup"><span data-stu-id="ef767-272">SIP proxy processes Refer from the client locally and acts as a Referee</span></span>

<span data-ttu-id="ef767-273">如果 SBC 指示不支持参阅方法，则 SIP 代理充当 Referee。</span><span class="sxs-lookup"><span data-stu-id="ef767-273">If the SBC indicated that the Refer method is not supported, the SIP proxy acts as a Referee.</span></span> 

<span data-ttu-id="ef767-274">来自客户端的引用请求将在 SIP 代理上终止。</span><span class="sxs-lookup"><span data-stu-id="ef767-274">The Refer request that comes from the client will be terminated on the SIP proxy.</span></span> <span data-ttu-id="ef767-275">（客户端的引用请求在下图中显示为 "呼叫转接至 Dave"。</span><span class="sxs-lookup"><span data-stu-id="ef767-275">(The Refer request from the client is shown as “Call transfer to Dave” in the following diagram.</span></span>  <span data-ttu-id="ef767-276">有关详细信息，请参阅[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)的7.1 节。</span><span class="sxs-lookup"><span data-stu-id="ef767-276">For more information, see section 7.1 of [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt).</span></span> 

![显示多个终结点和临时应答的图表](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a><span data-ttu-id="ef767-278">SIP 代理发送对 SBC 的引用并充当 Transferor</span><span class="sxs-lookup"><span data-stu-id="ef767-278">SIP proxy send the Refer to the SBC and acts as a Transferor</span></span>

<span data-ttu-id="ef767-279">这是呼叫转接的首选方法，对于寻找媒体绕过证书的设备是必需的。</span><span class="sxs-lookup"><span data-stu-id="ef767-279">This is the preferred method for call transfers, and it is mandatory for devices seeking media bypass certification.</span></span> <span data-ttu-id="ef767-280">在媒体绕过模式下不支持 SBC 能够处理引用的呼叫转接。</span><span class="sxs-lookup"><span data-stu-id="ef767-280">Call Transfer without the SBC being able to handle Refer is not supported in media bypass mode.</span></span> 

<span data-ttu-id="ef767-281">标准将在 RFC 5589 的第6节中介绍。</span><span class="sxs-lookup"><span data-stu-id="ef767-281">The standard is explained in Section 6 of RFC 5589.</span></span> <span data-ttu-id="ef767-282">相关 Rfc 包括：</span><span class="sxs-lookup"><span data-stu-id="ef767-282">The related RFCs are:</span></span>

- [<span data-ttu-id="ef767-283">会话初始协议（SIP）呼叫控制-转移</span><span class="sxs-lookup"><span data-stu-id="ef767-283">Session Initiation Protocol (SIP) Call Control - Transfer</span></span>](https://tools.ietf.org/html/rfc5589)

- [<span data-ttu-id="ef767-284">会话初始协议（SIP） "替换" 标头</span><span class="sxs-lookup"><span data-stu-id="ef767-284">Session Initiation Protocol (SIP) "Replaces" Header</span></span>](https://tools.ietf.org/html/rfc3891)

- [<span data-ttu-id="ef767-285">会话初始协议（SIP） "被指" 机制</span><span class="sxs-lookup"><span data-stu-id="ef767-285">Session Initiation Protocol (SIP) "Referred-By" mechanism</span></span>](https://tools.ietf.org/html/rfc3892)

<span data-ttu-id="ef767-286">此选项假定 SIP 代理充当 Transferor，并向 SBC 发送一条参考消息。</span><span class="sxs-lookup"><span data-stu-id="ef767-286">This option assumes that the SIP proxy acts as a Transferor and sends a Refer message to the SBC.</span></span> <span data-ttu-id="ef767-287">SBC 充当 Transferee 并处理用于传输的新优惠的参考。</span><span class="sxs-lookup"><span data-stu-id="ef767-287">The SBC acts as a Transferee and handles the Refer to generate a new offer for transfer.</span></span> <span data-ttu-id="ef767-288">有两种可能的情况：</span><span class="sxs-lookup"><span data-stu-id="ef767-288">There are two possible cases:</span></span>

- <span data-ttu-id="ef767-289">将呼叫转移到外部 PSTN 参与者。</span><span class="sxs-lookup"><span data-stu-id="ef767-289">The call is transferred to an external PSTN participant.</span></span> 
- <span data-ttu-id="ef767-290">通过 SBC 将呼叫从一个团队用户转移到同一租户中的另一个团队用户。</span><span class="sxs-lookup"><span data-stu-id="ef767-290">The call is transferred from one Teams user to another Teams user in the same tenant via the SBC.</span></span> 

<span data-ttu-id="ef767-291">如果通过 SBC 将呼叫从一个团队用户转移到另一个团队，则 SBC 应使用参考消息中接收的信息为传输目标（团队用户）发出新的邀请（开始新的对话框）。</span><span class="sxs-lookup"><span data-stu-id="ef767-291">If the call is transferred from one Teams user to another via the SBC, the SBC is expected to issue a new invite (start a new dialog) for the transfer target (the Teams user) using the information received in the Refer message.</span></span> 

<span data-ttu-id="ef767-292">要为请求的内部事务填充 "收件人/Transferor" 字段，SIP 代理需要将此信息传达在 "引用"/"引用方" 标题内。</span><span class="sxs-lookup"><span data-stu-id="ef767-292">To populate the To/Transferor fields for the transaction of the request internally, the SIP proxy needs to convey this information  inside the REFER-TO/REFERRED-BY headers.</span></span> 

<span data-ttu-id="ef767-293">SIP 代理将作为 SIP URI （由主机名中的 SIP 代理 FQDN 和下列任一项之一）组成的 "引用为 SIP URI"：</span><span class="sxs-lookup"><span data-stu-id="ef767-293">The SIP proxy will form the REFER-TO as a SIP URI comprised of a SIP proxy FQDN in the hostname and either one of the following:</span></span>

- <span data-ttu-id="ef767-294">URI 的用户名部分中的 E.i 电话号码，如果转移目标是电话号码，则为</span><span class="sxs-lookup"><span data-stu-id="ef767-294">An E.164 phone number in the username part of the URI in case the transfer target is a phone number, or</span></span>

- <span data-ttu-id="ef767-295">每个 x-m 和 x t 参数分别编码完整的传输目标 MRI 和租户 ID</span><span class="sxs-lookup"><span data-stu-id="ef767-295">x-m and x-t parameters encoding the full transfer target MRI and tenant ID respectively</span></span> 

<span data-ttu-id="ef767-296">被引用的标头是 transferor MRI 编码的 SIP URI，以及 transferor 租户 ID 和其他传输上下文参数，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="ef767-296">The REFERRED-BY header is a SIP URI with transferor MRI encoded in it as well as transferor tenant ID and other transfer context parameters as shown in the following table:</span></span>

| <span data-ttu-id="ef767-297">参数</span><span class="sxs-lookup"><span data-stu-id="ef767-297">Parameter</span></span> | <span data-ttu-id="ef767-298">值</span><span class="sxs-lookup"><span data-stu-id="ef767-298">Value</span></span> | <span data-ttu-id="ef767-299">说明</span><span class="sxs-lookup"><span data-stu-id="ef767-299">Description</span></span> |  
|:---------------------  |:---------------------- |:---------------------- |
| <span data-ttu-id="ef767-300">x-m</span><span class="sxs-lookup"><span data-stu-id="ef767-300">x-m</span></span> | <span data-ttu-id="ef767-301">MRI</span><span class="sxs-lookup"><span data-stu-id="ef767-301">MRI</span></span> | <span data-ttu-id="ef767-302">Transferor 的所有 MRI/转移目标（由 CC 填充）</span><span class="sxs-lookup"><span data-stu-id="ef767-302">Full MRI of transferor/transfer target as populated by CC</span></span> |
| <span data-ttu-id="ef767-303">x-t</span><span class="sxs-lookup"><span data-stu-id="ef767-303">x-t</span></span> | <span data-ttu-id="ef767-304">租户 ID</span><span class="sxs-lookup"><span data-stu-id="ef767-304">Tenant ID</span></span> | <span data-ttu-id="ef767-305">x-t 租户 ID 由 CC 填充的可选租户 Id</span><span class="sxs-lookup"><span data-stu-id="ef767-305">x-t Tenant ID Optional Tenant Id as populated by CC</span></span> |
| <span data-ttu-id="ef767-306">x-ti</span><span class="sxs-lookup"><span data-stu-id="ef767-306">x-ti</span></span> | <span data-ttu-id="ef767-307">Transferor 相关性 Id</span><span class="sxs-lookup"><span data-stu-id="ef767-307">Transferor Correlation Id</span></span> | <span data-ttu-id="ef767-308">对 transferor 的调用的相关 Id</span><span class="sxs-lookup"><span data-stu-id="ef767-308">Correlation Id of the call to the transferor</span></span> |
| <span data-ttu-id="ef767-309">x-tt</span><span class="sxs-lookup"><span data-stu-id="ef767-309">x-tt</span></span> | <span data-ttu-id="ef767-310">传输目标呼叫 URI</span><span class="sxs-lookup"><span data-stu-id="ef767-310">Transfer target call URI</span></span> | <span data-ttu-id="ef767-311">已编码的调用替换 URI</span><span class="sxs-lookup"><span data-stu-id="ef767-311">Encoded call replacement URI</span></span> |

<span data-ttu-id="ef767-312">在这种情况下，引用页眉的大小最多可以为400符号。</span><span class="sxs-lookup"><span data-stu-id="ef767-312">The size of the Refer Header can be up to 400 symbols in this case.</span></span> <span data-ttu-id="ef767-313">SBC 必须支持处理引用的消息大小最多为400个符号。</span><span class="sxs-lookup"><span data-stu-id="ef767-313">The SBC must support handling Refer messages with size up to 400 symbols.</span></span>

![显示多个终结点和临时应答的图表](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a><span data-ttu-id="ef767-315">会话计时器</span><span class="sxs-lookup"><span data-stu-id="ef767-315">Session timer</span></span>

<span data-ttu-id="ef767-316">SIP 代理支持（始终提供）在非绕过呼叫中的会话计时器，但不在绕过呼叫时提供。</span><span class="sxs-lookup"><span data-stu-id="ef767-316">The SIP proxy supports (always offers) the Session Timer on non-bypass calls but does not offer it on bypass calls.</span></span> <span data-ttu-id="ef767-317">SBC 使用会话计时器不是必需的。</span><span class="sxs-lookup"><span data-stu-id="ef767-317">Use of the Session Timer by the SBC is not mandatory.</span></span>

##  <a name="use-of-request-uri-parameter-userphone"></a><span data-ttu-id="ef767-318">使用请求 URI 参数 user = phone</span><span class="sxs-lookup"><span data-stu-id="ef767-318">Use of Request-URI parameter user=phone</span></span>

<span data-ttu-id="ef767-319">SIP 代理分析请求 URI，如果参数 user = phone 存在，服务会将请求 URI 作为电话号码处理，并将该号码与用户相匹配。</span><span class="sxs-lookup"><span data-stu-id="ef767-319">The SIP proxy analyses the Request-URI and if the parameter user=phone is present, the service will handle the Request-URI as a phone number, matching the number to a user.</span></span> <span data-ttu-id="ef767-320">如果参数不存在，SIP 代理会应用试探法来确定请求 URI 用户类型（电话号码或 SIP 地址）。</span><span class="sxs-lookup"><span data-stu-id="ef767-320">If parameter is not present the SIP proxy applies heuristics to determine  the Request-URI user type (phone number or a SIP address).</span></span>

<span data-ttu-id="ef767-321">Microsof 建议始终应用 user = phone 参数以简化呼叫设置过程。</span><span class="sxs-lookup"><span data-stu-id="ef767-321">Microsof recommends always applying the user=phone parameter to simplify the call setup process.</span></span>

## <a name="history-info-header"></a><span data-ttu-id="ef767-322">历史记录-信息标题</span><span class="sxs-lookup"><span data-stu-id="ef767-322">History-Info header</span></span>

<span data-ttu-id="ef767-323">历史记录信息标头用于 retargeting SIP 请求和 "提供一种用于捕获请求历史记录信息的标准机制，以便为网络和最终用户提供多种服务。"</span><span class="sxs-lookup"><span data-stu-id="ef767-323">The History-Info header is used for retargeting SIP requests and “provide(s) a standard mechanism for capturing the request history information to enable a wide variety of services for networks and end-users.”</span></span> <span data-ttu-id="ef767-324">有关详细信息，请参阅[RFC 4244 –第1.1 部分](http://www.ietf.org/rfc/rfc4244.txt)。</span><span class="sxs-lookup"><span data-stu-id="ef767-324">For more information, see [RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt).</span></span> <span data-ttu-id="ef767-325">对于 Microsoft Phone 系统，在 Simulring 和呼叫转发方案中使用此标题。</span><span class="sxs-lookup"><span data-stu-id="ef767-325">For Microsoft Phone System, this header is used in Simulring and Call Forwarding scenarios.</span></span>  

<span data-ttu-id="ef767-326">如果发送，则将启用历史记录信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef767-326">If sending, the History-Info is enabled as follows:</span></span>

- <span data-ttu-id="ef767-327">SIP 代理将在包含历史记录信息头（已发送到 PSTN 控制器）的单个历史记录信息条目中插入一个包含相关电话号码的参数。</span><span class="sxs-lookup"><span data-stu-id="ef767-327">The SIP proxy will insert a parameter containing the associated phone number in individual History-Info entries that comprise the History-Info header sent to the PSTN Controller.</span></span>  <span data-ttu-id="ef767-328">PSTN 控制器仅使用具有电话号码参数的条目，它将重建新的历史记录信息标头，并通过 SIP 代理将其传递到 SIP 中继提供程序。</span><span class="sxs-lookup"><span data-stu-id="ef767-328">Using only entries that have the phone number parameter, the PSTN Controller will rebuild a new History-Info header, and pass it on to the SIP trunk provider via SIP proxy.</span></span>

- <span data-ttu-id="ef767-329">将为同时拨打和呼叫转移案例添加历史记录-信息标题。</span><span class="sxs-lookup"><span data-stu-id="ef767-329">History-Info header will be added for simultaneous ring and call forwarding cases.</span></span>

- <span data-ttu-id="ef767-330">将不会为呼叫转移案例添加历史记录-信息标题。</span><span class="sxs-lookup"><span data-stu-id="ef767-330">History-Info header will not be added for call transfer cases.</span></span>

- <span data-ttu-id="ef767-331">已重建历史记录-信息标头中的单个历史记录项将提供与直接路由 FQDN （sip.pstnhub.microsoft.com）组合的电话号码参数，该参数设置为 URI 的主机部分;"user = phone" 的参数将作为 SIP URI 的一部分添加。</span><span class="sxs-lookup"><span data-stu-id="ef767-331">An individual history entry in the reconstructed History-Info header will have the phone number parameter provided combined with the Direct Routing FQDN (sip.pstnhub.microsoft.com) set as the host part of the URI; a parameter of ‘user=phone’ will be added as part of the SIP URI.</span></span>  <span data-ttu-id="ef767-332">除了手机上下文参数外，与原始历史记录信息标题关联的任何其他参数都将在重新构建的历史记录信息标题中传递。</span><span class="sxs-lookup"><span data-stu-id="ef767-332">Any other parameters associated with the original History-Info header, except for phone context parameters, will be passed through in the re-constructed History-Info header.</span></span>  <span data-ttu-id="ef767-333">请注意，专用项（由 RFC 4244 的3.3 中定义的机制确定）将按原样转发，因为 SIP 中继提供程序是受信任的对等。</span><span class="sxs-lookup"><span data-stu-id="ef767-333">Note that entries that are private (as determined by the mechanisms defined in Section 3.3 of RFC 4244) will be forwarded as is because  the SIP trunk provider is a trusted peer.</span></span>

- <span data-ttu-id="ef767-334">入站历史记录-信息被忽略。</span><span class="sxs-lookup"><span data-stu-id="ef767-334">Inbound History-Info is ignored.</span></span>

<span data-ttu-id="ef767-335">以下是 SIP 代理发送的历史记录信息头的格式：</span><span class="sxs-lookup"><span data-stu-id="ef767-335">Following is the format of the History-info header sent by the SIP proxy:</span></span>

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

<span data-ttu-id="ef767-336">如果多次呼叫被重定向，则有关每次重定向的信息都包含在按时间顺序排列的相应原因中。</span><span class="sxs-lookup"><span data-stu-id="ef767-336">If the call was redirected several times, information about every redirect is included with the appropriate reason in chronological order.</span></span>


<span data-ttu-id="ef767-337">页眉示例：</span><span class="sxs-lookup"><span data-stu-id="ef767-337">Header Example:</span></span>

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

<span data-ttu-id="ef767-338">历史记录-信息受强制 TLS 机制的保护。</span><span class="sxs-lookup"><span data-stu-id="ef767-338">The History-Info is protected by a mandatory TLS mechanism.</span></span> 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a><span data-ttu-id="ef767-339">与直接路由和故障转移机制的 SBC 连接</span><span class="sxs-lookup"><span data-stu-id="ef767-339">SBC connection to Direct Routing and failover mechanism</span></span>

<span data-ttu-id="ef767-340">请参阅[计划中用于直接路由](direct-routing-plan.md#failover-mechanism-for-sip-signaling)的 SIP 信号的故障转移机制部分。</span><span class="sxs-lookup"><span data-stu-id="ef767-340">See the section Failover mechanism for SIP signaling in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).</span></span>

## <a name="retry-after"></a><span data-ttu-id="ef767-341">重试-在</span><span class="sxs-lookup"><span data-stu-id="ef767-341">Retry-After</span></span>

<span data-ttu-id="ef767-342">如果直接路由数据中心正忙，则该服务可以向 SBC 发送一秒钟间隔后的重试消息。</span><span class="sxs-lookup"><span data-stu-id="ef767-342">If a Direct Routing datacenter is busy, the service can send a Retry-After message with a one-second interval to the SBC.</span></span> <span data-ttu-id="ef767-343">当 SBC 收到503消息，并且使用重试头响应某个邀请时，SBC 必须终止该连接并尝试下一个可用的 Microsoft 数据中心。</span><span class="sxs-lookup"><span data-stu-id="ef767-343">When the SBC receives a 503 message with a Retry-After header in response to an INVITE, the SBC must terminate that connection and try the next available Microsoft datacenter.</span></span> 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a><span data-ttu-id="ef767-344">ICE 重启：转到不支持媒体绕过的终结点的媒体旁路呼叫。</span><span class="sxs-lookup"><span data-stu-id="ef767-344">ICE Restart: Media bypass call transferred to an endpoint that does not support media bypass</span></span>

<span data-ttu-id="ef767-345">SBC 必须支持["9.1.1.1" 部分中的 RFC 5245](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)中所述的 ICE 重启。</span><span class="sxs-lookup"><span data-stu-id="ef767-345">The SBC must support ICE restarts as described in [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span>

<span data-ttu-id="ef767-346">直接路由中的重启按照 RFC 的以下段落实现：</span><span class="sxs-lookup"><span data-stu-id="ef767-346">The restart in Direct Routing is implemented according to the following paragraphs of the RFC:</span></span>

<span data-ttu-id="ef767-347">*若要重新启动 ICE，工程师必须在优惠中更改媒体流的冰密码和 ice ufrag。 请注意，允许在一个提供中使用会话级属性，但在后续优惠中提供与媒体级属性相同的 ice pwd 或 ice ufrag。 这不是密码更改，而是对其表示形式的更改，并且不会导致 ICE 重启。*</span><span class="sxs-lookup"><span data-stu-id="ef767-347">*To restart ICE, an agent MUST change both the ice-pwd and the ice-ufrag for the media stream in an offer.  Note that it is permissible to use a session-level attribute in one offer, but to provide the same ice-pwd or ice-ufrag as a media-level attribute in a subsequent offer.  This is not a change in password, just a change in its representation, and does not cause an ICE restart.*</span></span>

<span data-ttu-id="ef767-348">*在此媒体流的初始提供中，代理将此媒体流的其他字段设置为该媒体流的其他字段（请参阅4.3 节）。 因此，候选集可能包含该流的部分、全部或所有候选项，并且可能包括一组全新的候选项，如4.1.1 节中所述。*</span><span class="sxs-lookup"><span data-stu-id="ef767-348">*An agent sets the rest of the fields in the SDP for this media stream as it would in an initial offer of this media stream (see Section 4.3).  Consequently, the set of candidates MAY include some, none, or all of the previous candidates for that stream and MAY include a totally new set of candidates gathered as described in Section 4.1.1.*</span></span>

<span data-ttu-id="ef767-349">如果呼叫最初是使用 "媒体绕过" 建立的，并且呼叫转移到 Skype for business 客户端，直接路由需要插入媒体处理器-这是因为直接路由无法与具有媒体旁路的 Skype for Business 客户端配合使用。</span><span class="sxs-lookup"><span data-stu-id="ef767-349">If the call was initially established with media bypass, and the call is transferred to a Skype for Business client, Direct Routing needs to insert a Media Processor--this is because Direct Routing cannot be used with a Skype for Business client with media bypass.</span></span> <span data-ttu-id="ef767-350">直接路由通过更改 ice-pwd 和 ice ufrag 并在 reinvite 中提供新的媒体候选人来启动 ICE 重启过程。</span><span class="sxs-lookup"><span data-stu-id="ef767-350">Direct Routing starts the ICE restart process by  changing the ice-pwd and ice-ufrag and offering new media candidates in a reinvite.</span></span> 


