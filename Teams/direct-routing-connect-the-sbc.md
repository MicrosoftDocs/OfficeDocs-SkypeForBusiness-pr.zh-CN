---
title: 将会话边界控制器（SBC）连接到直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: 了解如何配置 Microsoft Phone 系统直接路由。
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157932"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a><span data-ttu-id="8bd58-103">将会话边界控制器（SBC）连接到直接路由</span><span class="sxs-lookup"><span data-stu-id="8bd58-103">Connect your Session Border Controller (SBC) to Direct Routing</span></span> 

<span data-ttu-id="8bd58-104">本文介绍如何将会话边界控制器（SBC）连接到手机系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="8bd58-104">This article describes how to connect your Session Border Controller (SBC) to Phone System Direct Routing.</span></span>  <span data-ttu-id="8bd58-105">这是配置直接路由的以下步骤的步骤1：</span><span class="sxs-lookup"><span data-stu-id="8bd58-105">This is step 1 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="8bd58-106">**步骤1。将 SBC 与电话系统连接并验证连接**（本文）</span><span class="sxs-lookup"><span data-stu-id="8bd58-106">**Step 1. Connect your SBC with Phone System and validate the connection** (This article)</span></span>
- <span data-ttu-id="8bd58-107">第 2 步</span><span class="sxs-lookup"><span data-stu-id="8bd58-107">Step 2.</span></span> [<span data-ttu-id="8bd58-108">为用户启用直接路由</span><span class="sxs-lookup"><span data-stu-id="8bd58-108">Enable users for Direct Routing</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="8bd58-109">第 3 步</span><span class="sxs-lookup"><span data-stu-id="8bd58-109">Step 3.</span></span> [<span data-ttu-id="8bd58-110">配置呼叫路由</span><span class="sxs-lookup"><span data-stu-id="8bd58-110">Configure call routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="8bd58-111">第 4 步</span><span class="sxs-lookup"><span data-stu-id="8bd58-111">Step 4.</span></span> [<span data-ttu-id="8bd58-112">将数字转换为备用格式</span><span class="sxs-lookup"><span data-stu-id="8bd58-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="8bd58-113">有关设置直接路由所需的所有步骤的信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="8bd58-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="8bd58-114">要将 SBC 连接到直接路由，您需要：</span><span class="sxs-lookup"><span data-stu-id="8bd58-114">To connect your SBC to Direct Routing, you'll need to:</span></span> 

1. <span data-ttu-id="8bd58-115">使用 PowerShell 连接到**Skype For Business Online**管理中心。</span><span class="sxs-lookup"><span data-stu-id="8bd58-115">Connect to **Skype for Business Online** admin center by using PowerShell.</span></span>            
2. <span data-ttu-id="8bd58-116">将 SBC 连接到租户。</span><span class="sxs-lookup"><span data-stu-id="8bd58-116">Connect the SBC to the tenant.</span></span>
3. <span data-ttu-id="8bd58-117">验证连接。</span><span class="sxs-lookup"><span data-stu-id="8bd58-117">Validate the connection.</span></span> 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="8bd58-118">使用 PowerShell 连接到 Skype for business Online</span><span class="sxs-lookup"><span data-stu-id="8bd58-118">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="8bd58-119">你可以使用连接到租户的 PowerShell 会话将 SBC 与直接路由接口配对。</span><span class="sxs-lookup"><span data-stu-id="8bd58-119">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="8bd58-120">若要打开 PowerShell 会话，请按照[为 Windows PowerShell 设置计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中概述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="8bd58-120">To open a PowerShell session, follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="8bd58-121">建立远程 PowerShell 会话后，请验证你是否可以查看用于管理 SBC 的命令。</span><span class="sxs-lookup"><span data-stu-id="8bd58-121">After you establish a remote PowerShell session, validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="8bd58-122">若要验证命令，请在 PowerShell 会话中键入或复制并粘贴以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="8bd58-122">To validate the commands, type or copy and paste the following command in the PowerShell session and press Enter:</span></span> 

```PowerShell
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="8bd58-123">该命令返回此处显示的四个函数，可让你管理 SBC。</span><span class="sxs-lookup"><span data-stu-id="8bd58-123">The command returns the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a><span data-ttu-id="8bd58-124">将 SBC 连接到租户</span><span class="sxs-lookup"><span data-stu-id="8bd58-124">Connect the SBC to the tenant</span></span> 

<span data-ttu-id="8bd58-125">若要将 SBC 连接到租户，请在 PowerShell 会话中键入以下内容，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="8bd58-125">To connect the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="8bd58-126">Microsoft 建议使用 SBC 文档中可以找到的信息，在 SBC 中设置最大通话限制。</span><span class="sxs-lookup"><span data-stu-id="8bd58-126">Microsoft recommends setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="8bd58-127">如果 SBC 处于容量级别，则该限制将触发通知。</span><span class="sxs-lookup"><span data-stu-id="8bd58-127">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="8bd58-128">仅当 FQDN 的域部分与你的租户中注册的一个域（onmicrosoft.com 除外\*）匹配时，你才可以对 SBC 进行配对。</span><span class="sxs-lookup"><span data-stu-id="8bd58-128">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="8bd58-129">SBC \*FQDN 名称不支持使用 onmicrosoft.com 域名。</span><span class="sxs-lookup"><span data-stu-id="8bd58-129">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="8bd58-130">例如，如果您有两个域名：</span><span class="sxs-lookup"><span data-stu-id="8bd58-130">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="8bd58-131">**contoso**</span><span class="sxs-lookup"><span data-stu-id="8bd58-131">**contoso**.com</span></span><br/><span data-ttu-id="8bd58-132">\*\*\*\* onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8bd58-132">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="8bd58-133">对于 SBC 名称，你可以使用名称 sbc.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="8bd58-133">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="8bd58-134">如果你尝试将 SBC 与名称 SBC 对应，则系统将不会允许你，因为域不属于此租户。</span><span class="sxs-lookup"><span data-stu-id="8bd58-134">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="8bd58-135">除了在租户中注册的域，还必须有一个具有该域的用户以及分配的 E3 或 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="8bd58-135">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="8bd58-136">如果不是，您将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="8bd58-136">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="8bd58-137">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="8bd58-137">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span></span>

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="8bd58-138">返回</span><span class="sxs-lookup"><span data-stu-id="8bd58-138">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="8bd58-139">在连接过程中，可以设置其他选项。</span><span class="sxs-lookup"><span data-stu-id="8bd58-139">There are additional options that can be set during the connection process.</span></span> <span data-ttu-id="8bd58-140">但是，在前面的示例中，仅显示所需的最低参数。</span><span class="sxs-lookup"><span data-stu-id="8bd58-140">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="8bd58-141">下表列出了可在为```New-CsOnlinePstnGateway```设置参数时使用的其他参数。</span><span class="sxs-lookup"><span data-stu-id="8bd58-141">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="8bd58-142">必填？</span><span class="sxs-lookup"><span data-stu-id="8bd58-142">Required?</span></span>|<span data-ttu-id="8bd58-143">名称</span><span class="sxs-lookup"><span data-stu-id="8bd58-143">Name</span></span>|<span data-ttu-id="8bd58-144">描述</span><span class="sxs-lookup"><span data-stu-id="8bd58-144">Description</span></span>|<span data-ttu-id="8bd58-145">默认值</span><span class="sxs-lookup"><span data-stu-id="8bd58-145">Default</span></span>|<span data-ttu-id="8bd58-146">可能的值</span><span class="sxs-lookup"><span data-stu-id="8bd58-146">Possible values</span></span>|<span data-ttu-id="8bd58-147">类型和限制</span><span class="sxs-lookup"><span data-stu-id="8bd58-147">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8bd58-148">是</span><span class="sxs-lookup"><span data-stu-id="8bd58-148">Yes</span></span>|<span data-ttu-id="8bd58-149">FQDN</span><span class="sxs-lookup"><span data-stu-id="8bd58-149">FQDN</span></span>|<span data-ttu-id="8bd58-150">SBC 的 FQDN 名称</span><span class="sxs-lookup"><span data-stu-id="8bd58-150">The FQDN name of the SBC</span></span> |<span data-ttu-id="8bd58-151">无</span><span class="sxs-lookup"><span data-stu-id="8bd58-151">None</span></span>|<span data-ttu-id="8bd58-152">NoneFQDN 名称，限制63个字符</span><span class="sxs-lookup"><span data-stu-id="8bd58-152">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="8bd58-153">字符串、[适用于计算机、域、网站和 ou 的 Active Directory 中的命名约定](https://support.microsoft.com/help/909264)的允许和不允许的字符列表</span><span class="sxs-lookup"><span data-stu-id="8bd58-153">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="8bd58-154">否</span><span class="sxs-lookup"><span data-stu-id="8bd58-154">No</span></span>|<span data-ttu-id="8bd58-155">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="8bd58-155">MediaBypass</span></span> |<span data-ttu-id="8bd58-156">指示 SBC 的参数支持媒体绕过，并且管理员希望使用它。</span><span class="sxs-lookup"><span data-stu-id="8bd58-156">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="8bd58-157">无</span><span class="sxs-lookup"><span data-stu-id="8bd58-157">None</span></span>|<span data-ttu-id="8bd58-158">True</span><span class="sxs-lookup"><span data-stu-id="8bd58-158">True</span></span><br/><span data-ttu-id="8bd58-159">False</span><span class="sxs-lookup"><span data-stu-id="8bd58-159">False</span></span>|<span data-ttu-id="8bd58-160">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bd58-160">Boolean</span></span>|
|<span data-ttu-id="8bd58-161">是</span><span class="sxs-lookup"><span data-stu-id="8bd58-161">Yes</span></span>|<span data-ttu-id="8bd58-162">SipSignalingPort</span><span class="sxs-lookup"><span data-stu-id="8bd58-162">SipSignalingPort</span></span> |<span data-ttu-id="8bd58-163">用于通过使用传输层安全性（TLS）协议与直接路由服务进行通信的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="8bd58-163">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="8bd58-164">无</span><span class="sxs-lookup"><span data-stu-id="8bd58-164">None</span></span>|<span data-ttu-id="8bd58-165">任何端口</span><span class="sxs-lookup"><span data-stu-id="8bd58-165">Any port</span></span>|<span data-ttu-id="8bd58-166">0到65535</span><span class="sxs-lookup"><span data-stu-id="8bd58-166">0 to 65535</span></span> |
|<span data-ttu-id="8bd58-167">否</span><span class="sxs-lookup"><span data-stu-id="8bd58-167">No</span></span>|<span data-ttu-id="8bd58-168">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="8bd58-168">FailoverTimeSeconds</span></span> |<span data-ttu-id="8bd58-169">设置为10（默认值）时，在10秒内网关未接听的出站呼叫将被路由到下一个可用的中继;如果没有其他中继，则会自动删除呼叫。</span><span class="sxs-lookup"><span data-stu-id="8bd58-169">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="8bd58-170">在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。</span><span class="sxs-lookup"><span data-stu-id="8bd58-170">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="8bd58-171">默认值为10。</span><span class="sxs-lookup"><span data-stu-id="8bd58-171">The default value is 10.</span></span>|<span data-ttu-id="8bd58-172">10</span><span class="sxs-lookup"><span data-stu-id="8bd58-172">10</span></span>|<span data-ttu-id="8bd58-173">数字</span><span class="sxs-lookup"><span data-stu-id="8bd58-173">Number</span></span>|<span data-ttu-id="8bd58-174">整形</span><span class="sxs-lookup"><span data-stu-id="8bd58-174">Int</span></span>|
|<span data-ttu-id="8bd58-175">否</span><span class="sxs-lookup"><span data-stu-id="8bd58-175">No</span></span>|<span data-ttu-id="8bd58-176">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="8bd58-176">ForwardCallHistory</span></span> |<span data-ttu-id="8bd58-177">指示是否通过中继转移呼叫历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="8bd58-177">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="8bd58-178">如果启用，则 Office 365 PSTN 代理将发送两个标头：历史记录信息和引用者。</span><span class="sxs-lookup"><span data-stu-id="8bd58-178">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="8bd58-179">默认值为**False** （$False）。</span><span class="sxs-lookup"><span data-stu-id="8bd58-179">The default value is **False** ($False).</span></span> |<span data-ttu-id="8bd58-180">False</span><span class="sxs-lookup"><span data-stu-id="8bd58-180">False</span></span>|<span data-ttu-id="8bd58-181">True</span><span class="sxs-lookup"><span data-stu-id="8bd58-181">True</span></span><br/><span data-ttu-id="8bd58-182">False</span><span class="sxs-lookup"><span data-stu-id="8bd58-182">False</span></span>|<span data-ttu-id="8bd58-183">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bd58-183">Boolean</span></span>|
|<span data-ttu-id="8bd58-184">否</span><span class="sxs-lookup"><span data-stu-id="8bd58-184">No</span></span>|<span data-ttu-id="8bd58-185">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="8bd58-185">ForwardPAI</span></span>|<span data-ttu-id="8bd58-186">指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。</span><span class="sxs-lookup"><span data-stu-id="8bd58-186">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="8bd58-187">PAI 标头提供了一种验证呼叫者身份的方法。</span><span class="sxs-lookup"><span data-stu-id="8bd58-187">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="8bd58-188">如果启用，则隐私： ID 标头也会发送。</span><span class="sxs-lookup"><span data-stu-id="8bd58-188">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="8bd58-189">默认值为**False** （$False）。</span><span class="sxs-lookup"><span data-stu-id="8bd58-189">The default value is **False** ($False).</span></span>|<span data-ttu-id="8bd58-190">False</span><span class="sxs-lookup"><span data-stu-id="8bd58-190">False</span></span>|<span data-ttu-id="8bd58-191">True</span><span class="sxs-lookup"><span data-stu-id="8bd58-191">True</span></span><br/><span data-ttu-id="8bd58-192">False</span><span class="sxs-lookup"><span data-stu-id="8bd58-192">False</span></span>|<span data-ttu-id="8bd58-193">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bd58-193">Boolean</span></span>|
|<span data-ttu-id="8bd58-194">否</span><span class="sxs-lookup"><span data-stu-id="8bd58-194">No</span></span>|<span data-ttu-id="8bd58-195">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="8bd58-195">SendSIPOptions</span></span> |<span data-ttu-id="8bd58-196">定义 SBC 是否将发送 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="8bd58-196">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="8bd58-197">如果禁用，将从监视和通知系统中排除 SBC。</span><span class="sxs-lookup"><span data-stu-id="8bd58-197">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="8bd58-198">强烈建议你启用 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="8bd58-198">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="8bd58-199">默认值为**True**。</span><span class="sxs-lookup"><span data-stu-id="8bd58-199">Default value is **True**.</span></span> |<span data-ttu-id="8bd58-200">True</span><span class="sxs-lookup"><span data-stu-id="8bd58-200">True</span></span>|<span data-ttu-id="8bd58-201">True</span><span class="sxs-lookup"><span data-stu-id="8bd58-201">True</span></span><br/><span data-ttu-id="8bd58-202">False</span><span class="sxs-lookup"><span data-stu-id="8bd58-202">False</span></span>|<span data-ttu-id="8bd58-203">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bd58-203">Boolean</span></span>|
|<span data-ttu-id="8bd58-204">否</span><span class="sxs-lookup"><span data-stu-id="8bd58-204">No</span></span>|<span data-ttu-id="8bd58-205">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="8bd58-205">MaxConcurrentSessions</span></span> |<span data-ttu-id="8bd58-206">由警报系统使用。</span><span class="sxs-lookup"><span data-stu-id="8bd58-206">Used by alerting system.</span></span> <span data-ttu-id="8bd58-207">如果设置了任何值，则当并发会话的数量为90% 或高于此值时，警报系统将向租户管理员生成警报。</span><span class="sxs-lookup"><span data-stu-id="8bd58-207">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent sessions is 90% or higher than this value.</span></span> <span data-ttu-id="8bd58-208">如果未设置该参数，则不会生成警报。</span><span class="sxs-lookup"><span data-stu-id="8bd58-208">If the parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="8bd58-209">但是，监视系统将每隔24小时报告并发会话的数量。</span><span class="sxs-lookup"><span data-stu-id="8bd58-209">However, the monitoring system will report number of concurrent sessions every 24 hours.</span></span> |<span data-ttu-id="8bd58-210">Null</span><span class="sxs-lookup"><span data-stu-id="8bd58-210">Null</span></span>|<span data-ttu-id="8bd58-211">Null</span><span class="sxs-lookup"><span data-stu-id="8bd58-211">Null</span></span><br/><span data-ttu-id="8bd58-212">1到100000</span><span class="sxs-lookup"><span data-stu-id="8bd58-212">1 to 100,000</span></span> ||
|<span data-ttu-id="8bd58-213">否</span><span class="sxs-lookup"><span data-stu-id="8bd58-213">No</span></span>|<span data-ttu-id="8bd58-214">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="8bd58-214">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="8bd58-215">允许手动选择媒体的路径。</span><span class="sxs-lookup"><span data-stu-id="8bd58-215">Allows selecting path for media manually.</span></span> <span data-ttu-id="8bd58-216">直接路由根据 SBC 的公共 IP 为媒体路径分配一个数据中心。</span><span class="sxs-lookup"><span data-stu-id="8bd58-216">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="8bd58-217">我们始终选择最接近于 SBC 数据中心的数据。</span><span class="sxs-lookup"><span data-stu-id="8bd58-217">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="8bd58-218">但是，在某些情况下，可以将美国范围内的公共 IP 分配给位于欧洲的 SBC。</span><span class="sxs-lookup"><span data-stu-id="8bd58-218">However, in some cases a public IP from, for example, a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="8bd58-219">在这种情况下，我们将使用非最佳媒体路径。</span><span class="sxs-lookup"><span data-stu-id="8bd58-219">In this case, we will be using not optimal media path.</span></span> <span data-ttu-id="8bd58-220">此参数允许手动设置媒体流量的首选区域。</span><span class="sxs-lookup"><span data-stu-id="8bd58-220">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="8bd58-221">Microsoft 仅建议设置此参数（如果通话记录清晰地指明自动分配媒体路径的数据中心）不会向 SBC 数据中心分配最接近的数据中心。</span><span class="sxs-lookup"><span data-stu-id="8bd58-221">Microsoft only recommends setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="8bd58-222">无</span><span class="sxs-lookup"><span data-stu-id="8bd58-222">None</span></span>|<span data-ttu-id="8bd58-223">ISO 格式的国家代码</span><span class="sxs-lookup"><span data-stu-id="8bd58-223">Country codes in ISO format</span></span>||
|<span data-ttu-id="8bd58-224">否</span><span class="sxs-lookup"><span data-stu-id="8bd58-224">No</span></span>|<span data-ttu-id="8bd58-225">已启用</span><span class="sxs-lookup"><span data-stu-id="8bd58-225">Enabled</span></span>|<span data-ttu-id="8bd58-226">用于为出站呼叫启用此 SBC。</span><span class="sxs-lookup"><span data-stu-id="8bd58-226">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="8bd58-227">可用于在其更新或维护期间临时删除 SBC。</span><span class="sxs-lookup"><span data-stu-id="8bd58-227">Can be used to temporarily remove the SBC while it is being updated or during maintenance.</span></span> |<span data-ttu-id="8bd58-228">False</span><span class="sxs-lookup"><span data-stu-id="8bd58-228">False</span></span>|<span data-ttu-id="8bd58-229">True</span><span class="sxs-lookup"><span data-stu-id="8bd58-229">True</span></span><br/><span data-ttu-id="8bd58-230">False</span><span class="sxs-lookup"><span data-stu-id="8bd58-230">False</span></span>|<span data-ttu-id="8bd58-231">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bd58-231">Boolean</span></span>|
 
## <a name="verify-the-sbc-connection"></a><span data-ttu-id="8bd58-232">验证 SBC 连接</span><span class="sxs-lookup"><span data-stu-id="8bd58-232">Verify the SBC connection</span></span> 

<span data-ttu-id="8bd58-233">若要验证连接，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8bd58-233">To verify the connection:</span></span> 
- <span data-ttu-id="8bd58-234">检查 SBC 是否在成对的 SBCs 的列表中。</span><span class="sxs-lookup"><span data-stu-id="8bd58-234">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="8bd58-235">验证 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="8bd58-235">Validate SIP Options.</span></span> 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="8bd58-236">检查 SBC 是否位于成对的 SBCs 的列表中</span><span class="sxs-lookup"><span data-stu-id="8bd58-236">Check if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="8bd58-237">连接 SBC 后，通过在远程 PowerShell 会话中运行以下命令验证 SBC 是否存在于成对的 SBCs 列表中：</span><span class="sxs-lookup"><span data-stu-id="8bd58-237">After you connect the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session:</span></span> 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

<span data-ttu-id="8bd58-238">配对网关应显示在列表中，如下面的示例所示，并且**Enabled**参数应显示值**True**。</span><span class="sxs-lookup"><span data-stu-id="8bd58-238">The paired gateway should appear in the list as shown in the example below, and the **Enabled** parameter should display a value of **True**.</span></span> 


<span data-ttu-id="8bd58-239">返回：</span><span class="sxs-lookup"><span data-stu-id="8bd58-239">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

### <a name="validate-sip-options-flow"></a><span data-ttu-id="8bd58-240">验证 SIP 选项流</span><span class="sxs-lookup"><span data-stu-id="8bd58-240">Validate SIP Options flow</span></span> 

<span data-ttu-id="8bd58-241">若要使用传出 SIP 选项验证配对，请使用 SBC 管理界面并确认 SBC 是否收到对其传出选项消息的 200 OK 响应。</span><span class="sxs-lookup"><span data-stu-id="8bd58-241">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="8bd58-242">当直接路由看到传入选项时，它将向 "传入选项" 消息的 "联系人标题" 字段中配置的 SBC FQDN 开始发送传出 SIP 选项消息。</span><span class="sxs-lookup"><span data-stu-id="8bd58-242">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="8bd58-243">若要使用传入 SIP 选项验证配对，请使用 SBC 管理接口，并查看 SBC 是否向来自直接路由的选项消息发送回复，并且它发送的响应代码为 200 OK。</span><span class="sxs-lookup"><span data-stu-id="8bd58-243">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>


## <a name="see-also"></a><span data-ttu-id="8bd58-244">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bd58-244">See also</span></span>

[<span data-ttu-id="8bd58-245">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="8bd58-245">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="8bd58-246">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="8bd58-246">Configure Direct Routing</span></span>](direct-routing-configure.md)
