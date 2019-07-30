---
title: 配置直接路由
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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 了解如何配置 Microsoft Phone 系统直接路由。
ms.openlocfilehash: 37fe6fa9355a0892720fa32d2bab30474ddaf12a
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925494"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="e801c-103">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="e801c-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="e801c-104">观看以下会话, 了解直接路由的好处、如何为其规划以及如何部署它: [Microsoft 团队中的直接路由](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="e801c-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="e801c-105">如果尚未执行此操作, 请阅读 "针对先决条件的[计划直接路由](direct-routing-plan.md)", 并查看配置 Microsoft Phone 系统网络之前需要执行的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="e801c-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="e801c-106">本文介绍如何配置 Microsoft Phone 系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="e801c-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="e801c-107">它详细介绍了如何将受支持的会话边界控制器 (SBC) 配对到直接路由, 以及如何将 Microsoft 团队用户配置为使用直接路由连接到公共交换电话网络 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="e801c-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="e801c-108">为了完成本文中介绍的步骤, 管理员需要熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e801c-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="e801c-109">有关使用 PowerShell 的详细信息, 请参阅[设置适用于 Windows powershell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e801c-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="e801c-110">我们建议你确认你的 SBC 已按照 SBC 供应商的建议进行配置:</span><span class="sxs-lookup"><span data-stu-id="e801c-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="e801c-111">AudioCodes 部署文档</span><span class="sxs-lookup"><span data-stu-id="e801c-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="e801c-112">Oracle 部署文档</span><span class="sxs-lookup"><span data-stu-id="e801c-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="e801c-113">功能区通信部署文档</span><span class="sxs-lookup"><span data-stu-id="e801c-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="e801c-114">TE-系统 (anynode) 部署文档</span><span class="sxs-lookup"><span data-stu-id="e801c-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="e801c-115">你可以配置 Microsoft Phone 系统并使用户能够使用直接路由, 然后通过完成以下过程将 Microsoft 团队设置为首选调用客户端:</span><span class="sxs-lookup"><span data-stu-id="e801c-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="e801c-116">将 SBC 与 Microsoft Phone 系统配对并验证配对</span><span class="sxs-lookup"><span data-stu-id="e801c-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="e801c-117">为用户启用直接路由服务</span><span class="sxs-lookup"><span data-stu-id="e801c-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="e801c-118">确保 Microsoft 团队是用户的首选调用客户端</span><span class="sxs-lookup"><span data-stu-id="e801c-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="e801c-119">将 SBC 与电话系统的直接路由服务配对</span><span class="sxs-lookup"><span data-stu-id="e801c-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="e801c-120">下面是让你将 SBC 连接或配对到直接路由接口的三个高级步骤:</span><span class="sxs-lookup"><span data-stu-id="e801c-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="e801c-121">使用 PowerShell 连接到**Skype For Business Online**管理中心</span><span class="sxs-lookup"><span data-stu-id="e801c-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="e801c-122">对 SBC 进行配对</span><span class="sxs-lookup"><span data-stu-id="e801c-122">Pair the SBC</span></span> 
- <span data-ttu-id="e801c-123">验证配对</span><span class="sxs-lookup"><span data-stu-id="e801c-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="e801c-124">使用 PowerShell 连接到 Skype for business Online</span><span class="sxs-lookup"><span data-stu-id="e801c-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="e801c-125">你可以使用连接到租户的 PowerShell 会话将 SBC 与直接路由接口配对。</span><span class="sxs-lookup"><span data-stu-id="e801c-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="e801c-126">若要打开 PowerShell 会话, 请按照[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中概述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="e801c-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="e801c-127">建立远程 PowerShell 会话后, 请验证你是否可以看到用于管理 SBC 的命令。</span><span class="sxs-lookup"><span data-stu-id="e801c-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="e801c-128">若要验证命令, 请在 PowerShell 会话中键入或复制/粘贴以下内容, 然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="e801c-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="e801c-129">你的命令将返回此处所示的4个函数, 这些函数将允许你管理 SBC。</span><span class="sxs-lookup"><span data-stu-id="e801c-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="e801c-130">将 SBC 与租户配对</span><span class="sxs-lookup"><span data-stu-id="e801c-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="e801c-131">若要将 SBC 与租户配对, 请在 PowerShell 会话中键入以下内容, 然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="e801c-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="e801c-132">强烈建议使用 SBC 文档中提供的信息, 在 SBC 中设置最大通话限制。</span><span class="sxs-lookup"><span data-stu-id="e801c-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="e801c-133">如果 SBC 处于容量级别, 则该限制将触发通知。</span><span class="sxs-lookup"><span data-stu-id="e801c-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="e801c-134">仅当 FQDN 的域部分与你的租户中注册的一个域 (onmicrosoft.com 除外\*) 匹配时, 你才可以对 SBC 进行配对。</span><span class="sxs-lookup"><span data-stu-id="e801c-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="e801c-135">SBC \*FQDN 名称不支持使用 onmicrosoft.com 域名。</span><span class="sxs-lookup"><span data-stu-id="e801c-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="e801c-136">例如, 如果您有两个域名:</span><span class="sxs-lookup"><span data-stu-id="e801c-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="e801c-137">**contoso**</span><span class="sxs-lookup"><span data-stu-id="e801c-137">**contoso**.com</span></span><br/><span data-ttu-id="e801c-138">\*\*\*\* onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e801c-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="e801c-139">对于 SBC 名称, 你可以使用名称 sbc.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e801c-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="e801c-140">如果你尝试将 SBC 与名称 SBC 对应, 则系统将不会允许你, 因为域不属于此租户。</span><span class="sxs-lookup"><span data-stu-id="e801c-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="e801c-141">除了在租户中注册的域, 还必须有一个具有该域的用户以及分配的 E3 或 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="e801c-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="e801c-142">如果不是, 您将收到以下错误:</span><span class="sxs-lookup"><span data-stu-id="e801c-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="e801c-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="e801c-143"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="e801c-144">返回</span><span class="sxs-lookup"><span data-stu-id="e801c-144">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="e801c-145">在配对过程中, 可以设置其他选项。</span><span class="sxs-lookup"><span data-stu-id="e801c-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="e801c-146">但是, 在前面的示例中, 仅显示所需的最低参数。</span><span class="sxs-lookup"><span data-stu-id="e801c-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="e801c-147">下表列出了可用于设置参数的其他参数`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="e801c-147">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="e801c-148">必填？</span><span class="sxs-lookup"><span data-stu-id="e801c-148">Required?</span></span>|<span data-ttu-id="e801c-149">名称</span><span class="sxs-lookup"><span data-stu-id="e801c-149">Name</span></span>|<span data-ttu-id="e801c-150">描述</span><span class="sxs-lookup"><span data-stu-id="e801c-150">Description</span></span>|<span data-ttu-id="e801c-151">默认值</span><span class="sxs-lookup"><span data-stu-id="e801c-151">Default</span></span>|<span data-ttu-id="e801c-152">可能的值</span><span class="sxs-lookup"><span data-stu-id="e801c-152">Possible values</span></span>|<span data-ttu-id="e801c-153">类型和限制</span><span class="sxs-lookup"><span data-stu-id="e801c-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e801c-154">是</span><span class="sxs-lookup"><span data-stu-id="e801c-154">Yes</span></span>|<span data-ttu-id="e801c-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="e801c-155">FQDN</span></span>|<span data-ttu-id="e801c-156">SBC 的 FQDN 名称</span><span class="sxs-lookup"><span data-stu-id="e801c-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="e801c-157">无</span><span class="sxs-lookup"><span data-stu-id="e801c-157">None</span></span>|<span data-ttu-id="e801c-158">NoneFQDN 名称, 限制63个字符</span><span class="sxs-lookup"><span data-stu-id="e801c-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="e801c-159">字符串、[适用于计算机、域、网站和 ou 的 Active Directory 中的命名约定](https://support.microsoft.com/help/909264)的允许和不允许的字符列表</span><span class="sxs-lookup"><span data-stu-id="e801c-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="e801c-160">否</span><span class="sxs-lookup"><span data-stu-id="e801c-160">No</span></span>|<span data-ttu-id="e801c-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="e801c-161">MediaBypass</span></span> |<span data-ttu-id="e801c-162">保留供将来使用的参数。</span><span class="sxs-lookup"><span data-stu-id="e801c-162">The parameter reserved for future use.</span></span> <span data-ttu-id="e801c-163">指示 SBC 的参数支持媒体绕过, 并且管理员希望使用它。</span><span class="sxs-lookup"><span data-stu-id="e801c-163">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="e801c-164">无</span><span class="sxs-lookup"><span data-stu-id="e801c-164">None</span></span>|<span data-ttu-id="e801c-165">True</span><span class="sxs-lookup"><span data-stu-id="e801c-165">True</span></span><br/><span data-ttu-id="e801c-166">False</span><span class="sxs-lookup"><span data-stu-id="e801c-166">False</span></span>|<span data-ttu-id="e801c-167">Boolean</span><span class="sxs-lookup"><span data-stu-id="e801c-167">Boolean</span></span>|
|<span data-ttu-id="e801c-168">是</span><span class="sxs-lookup"><span data-stu-id="e801c-168">Yes</span></span>|<span data-ttu-id="e801c-169">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="e801c-169">SipSignallingPort</span></span> |<span data-ttu-id="e801c-170">用于通过使用传输层安全性 (TLS) 协议与直接路由服务进行通信的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="e801c-170">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="e801c-171">无</span><span class="sxs-lookup"><span data-stu-id="e801c-171">None</span></span>|<span data-ttu-id="e801c-172">任何端口</span><span class="sxs-lookup"><span data-stu-id="e801c-172">Any port</span></span>|<span data-ttu-id="e801c-173">0到65535</span><span class="sxs-lookup"><span data-stu-id="e801c-173">0 to 65535</span></span> |
|<span data-ttu-id="e801c-174">否</span><span class="sxs-lookup"><span data-stu-id="e801c-174">No</span></span>|<span data-ttu-id="e801c-175">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="e801c-175">FailoverTimeSeconds</span></span> |<span data-ttu-id="e801c-176">设置为 10 (默认值) 时, 在10秒内网关未接听的出站呼叫将被路由到下一个可用的中继;如果没有其他中继, 则会自动删除呼叫。</span><span class="sxs-lookup"><span data-stu-id="e801c-176">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="e801c-177">在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。</span><span class="sxs-lookup"><span data-stu-id="e801c-177">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="e801c-178">默认值为10。</span><span class="sxs-lookup"><span data-stu-id="e801c-178">The default value is 10.</span></span>|<span data-ttu-id="e801c-179">10</span><span class="sxs-lookup"><span data-stu-id="e801c-179">10</span></span>|<span data-ttu-id="e801c-180">数字</span><span class="sxs-lookup"><span data-stu-id="e801c-180">Number</span></span>|<span data-ttu-id="e801c-181">整形</span><span class="sxs-lookup"><span data-stu-id="e801c-181">Int</span></span>|
|<span data-ttu-id="e801c-182">否</span><span class="sxs-lookup"><span data-stu-id="e801c-182">No</span></span>|<span data-ttu-id="e801c-183">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="e801c-183">ForwardCallHistory</span></span> |<span data-ttu-id="e801c-184">指示是否通过中继转移呼叫历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="e801c-184">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="e801c-185">如果启用, 则 Office 365 PSTN 代理将发送两个标头: 历史记录信息和引用者。</span><span class="sxs-lookup"><span data-stu-id="e801c-185">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="e801c-186">默认值为**False** ($False)。</span><span class="sxs-lookup"><span data-stu-id="e801c-186">The default value is **False** ($False).</span></span> |<span data-ttu-id="e801c-187">False</span><span class="sxs-lookup"><span data-stu-id="e801c-187">False</span></span>|<span data-ttu-id="e801c-188">True</span><span class="sxs-lookup"><span data-stu-id="e801c-188">True</span></span><br/><span data-ttu-id="e801c-189">False</span><span class="sxs-lookup"><span data-stu-id="e801c-189">False</span></span>|<span data-ttu-id="e801c-190">Boolean</span><span class="sxs-lookup"><span data-stu-id="e801c-190">Boolean</span></span>|
|<span data-ttu-id="e801c-191">否</span><span class="sxs-lookup"><span data-stu-id="e801c-191">No</span></span>|<span data-ttu-id="e801c-192">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="e801c-192">ForwardPAI</span></span>|<span data-ttu-id="e801c-193">指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。</span><span class="sxs-lookup"><span data-stu-id="e801c-193">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="e801c-194">PAI 标头提供了一种验证呼叫者身份的方法。</span><span class="sxs-lookup"><span data-stu-id="e801c-194">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="e801c-195">如果启用, 则隐私: ID 标头也会发送。</span><span class="sxs-lookup"><span data-stu-id="e801c-195">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="e801c-196">默认值为**False** ($False)。</span><span class="sxs-lookup"><span data-stu-id="e801c-196">The default value is **False** ($False).</span></span>|<span data-ttu-id="e801c-197">False</span><span class="sxs-lookup"><span data-stu-id="e801c-197">False</span></span>|<span data-ttu-id="e801c-198">True</span><span class="sxs-lookup"><span data-stu-id="e801c-198">True</span></span><br/><span data-ttu-id="e801c-199">False</span><span class="sxs-lookup"><span data-stu-id="e801c-199">False</span></span>|<span data-ttu-id="e801c-200">Boolean</span><span class="sxs-lookup"><span data-stu-id="e801c-200">Boolean</span></span>|
|<span data-ttu-id="e801c-201">否</span><span class="sxs-lookup"><span data-stu-id="e801c-201">No</span></span>|<span data-ttu-id="e801c-202">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="e801c-202">SendSIPOptions</span></span> |<span data-ttu-id="e801c-203">定义 SBC 是否将发送 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="e801c-203">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="e801c-204">如果禁用, 将从监视和通知系统中排除 SBC。</span><span class="sxs-lookup"><span data-stu-id="e801c-204">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="e801c-205">强烈建议你启用 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="e801c-205">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="e801c-206">默认值为**True**。</span><span class="sxs-lookup"><span data-stu-id="e801c-206">Default value is **True**.</span></span> |<span data-ttu-id="e801c-207">True</span><span class="sxs-lookup"><span data-stu-id="e801c-207">True</span></span>|<span data-ttu-id="e801c-208">True</span><span class="sxs-lookup"><span data-stu-id="e801c-208">True</span></span><br/><span data-ttu-id="e801c-209">False</span><span class="sxs-lookup"><span data-stu-id="e801c-209">False</span></span>|<span data-ttu-id="e801c-210">Boolean</span><span class="sxs-lookup"><span data-stu-id="e801c-210">Boolean</span></span>|
|<span data-ttu-id="e801c-211">否</span><span class="sxs-lookup"><span data-stu-id="e801c-211">No</span></span>|<span data-ttu-id="e801c-212">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="e801c-212">MaxConcurrentSessions</span></span> |<span data-ttu-id="e801c-213">由警报系统使用。</span><span class="sxs-lookup"><span data-stu-id="e801c-213">Used by alerting system.</span></span> <span data-ttu-id="e801c-214">如果设置了任何值, 则当并发会话的数量为 90% 或高于此值时, 警报系统将向租户管理员生成警报。</span><span class="sxs-lookup"><span data-stu-id="e801c-214">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="e801c-215">如果未设置参数, 则不会生成警报。</span><span class="sxs-lookup"><span data-stu-id="e801c-215">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="e801c-216">但是, 监视系统将每隔24小时报告并发会话的数量。</span><span class="sxs-lookup"><span data-stu-id="e801c-216">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="e801c-217">Null</span><span class="sxs-lookup"><span data-stu-id="e801c-217">Null</span></span>|<span data-ttu-id="e801c-218">Null</span><span class="sxs-lookup"><span data-stu-id="e801c-218">Null</span></span><br/><span data-ttu-id="e801c-219">1到100000</span><span class="sxs-lookup"><span data-stu-id="e801c-219">1 to 100,000</span></span> ||
|<span data-ttu-id="e801c-220">否</span><span class="sxs-lookup"><span data-stu-id="e801c-220">No</span></span>|<span data-ttu-id="e801c-221">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="e801c-221">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="e801c-222">允许手动选择媒体的路径。</span><span class="sxs-lookup"><span data-stu-id="e801c-222">Allows selecting path for media manually.</span></span> <span data-ttu-id="e801c-223">直接路由根据 SBC 的公共 IP 为媒体路径分配一个数据中心。</span><span class="sxs-lookup"><span data-stu-id="e801c-223">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="e801c-224">我们始终选择最接近于 SBC 数据中心的数据。</span><span class="sxs-lookup"><span data-stu-id="e801c-224">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="e801c-225">但是, 在某些情况下, 可以将美国范围的公共 IP 分配给位于欧洲的 SBC。</span><span class="sxs-lookup"><span data-stu-id="e801c-225">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="e801c-226">在这种情况下, 我们将使用非最佳媒体路径。</span><span class="sxs-lookup"><span data-stu-id="e801c-226">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="e801c-227">此参数允许手动设置媒体流量的首选区域。</span><span class="sxs-lookup"><span data-stu-id="e801c-227">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="e801c-228">仅当通话记录明确指明 "自动分配媒体路径的数据中心" 不会向 SBC 数据中心分配最接近的数据中心时, 我们才建议设置此参数。</span><span class="sxs-lookup"><span data-stu-id="e801c-228">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="e801c-229">无</span><span class="sxs-lookup"><span data-stu-id="e801c-229">None</span></span>|<span data-ttu-id="e801c-230">ISO 格式的国家代码</span><span class="sxs-lookup"><span data-stu-id="e801c-230">Country codes in ISO format</span></span>||
|<span data-ttu-id="e801c-231">否</span><span class="sxs-lookup"><span data-stu-id="e801c-231">No</span></span>|<span data-ttu-id="e801c-232">已启用</span><span class="sxs-lookup"><span data-stu-id="e801c-232">Enabled</span></span>|<span data-ttu-id="e801c-233">用于为出站呼叫启用此 SBC。</span><span class="sxs-lookup"><span data-stu-id="e801c-233">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="e801c-234">可用于在其更新或维护期间临时删除 SBC。</span><span class="sxs-lookup"><span data-stu-id="e801c-234">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="e801c-235">False</span><span class="sxs-lookup"><span data-stu-id="e801c-235">False</span></span>|<span data-ttu-id="e801c-236">True</span><span class="sxs-lookup"><span data-stu-id="e801c-236">True</span></span><br/><span data-ttu-id="e801c-237">False</span><span class="sxs-lookup"><span data-stu-id="e801c-237">False</span></span>|<span data-ttu-id="e801c-238">Boolean</span><span class="sxs-lookup"><span data-stu-id="e801c-238">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="e801c-239">验证 SBC 配对</span><span class="sxs-lookup"><span data-stu-id="e801c-239">Verify the SBC pairing</span></span> 

<span data-ttu-id="e801c-240">验证连接:</span><span class="sxs-lookup"><span data-stu-id="e801c-240">Verify the connection:</span></span> 
- <span data-ttu-id="e801c-241">检查 SBC 是否在成对的 SBCs 的列表中。</span><span class="sxs-lookup"><span data-stu-id="e801c-241">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="e801c-242">验证 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="e801c-242">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="e801c-243">验证 SBC 是否位于成对的 SBCs 的列表中</span><span class="sxs-lookup"><span data-stu-id="e801c-243">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="e801c-244">对 SBC 进行配对后, 通过在远程 PowerShell 会话中运行以下命令验证 SBC 是否存在于成对的 SBCs 列表中:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="e801c-244">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="e801c-245">配对网关应显示在列表中, 如下面的示例所示, 并验证*启用*的参数是否显示值**True**。</span><span class="sxs-lookup"><span data-stu-id="e801c-245">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="e801c-246">键</span><span class="sxs-lookup"><span data-stu-id="e801c-246">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="e801c-247">返回:</span><span class="sxs-lookup"><span data-stu-id="e801c-247">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="e801c-248">验证 SIP 选项流</span><span class="sxs-lookup"><span data-stu-id="e801c-248">Validate SIP Options flow</span></span> 

<span data-ttu-id="e801c-249">若要使用传出 SIP 选项验证配对, 请使用 SBC 管理界面并确认 SBC 是否收到对其传出选项消息的 200 OK 响应。</span><span class="sxs-lookup"><span data-stu-id="e801c-249">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="e801c-250">当直接路由看到传入选项时, 它将向 "传入选项" 消息的 "联系人标题" 字段中配置的 SBC FQDN 开始发送传出 SIP 选项消息。</span><span class="sxs-lookup"><span data-stu-id="e801c-250">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="e801c-251">若要使用传入 SIP 选项验证配对, 请使用 SBC 管理接口, 并查看 SBC 是否向来自直接路由的选项消息发送回复, 并且它发送的响应代码为 200 OK。</span><span class="sxs-lookup"><span data-stu-id="e801c-251">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="e801c-252">为用户启用直接路由服务</span><span class="sxs-lookup"><span data-stu-id="e801c-252">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="e801c-253">准备好为直接路由服务用户启用用户时, 请按照下列步骤操作:</span><span class="sxs-lookup"><span data-stu-id="e801c-253">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="e801c-254">在 Office 365 中创建用户并分配电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="e801c-254">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="e801c-255">确保用户托管在 Skype for Business Online 中。</span><span class="sxs-lookup"><span data-stu-id="e801c-255">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="e801c-256">配置电话号码并启用企业语音和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="e801c-256">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="e801c-257">配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="e801c-257">Configure voice routing.</span></span> <span data-ttu-id="e801c-258">将自动验证该路线。</span><span class="sxs-lookup"><span data-stu-id="e801c-258">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="e801c-259">在 Office 365 中创建用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="e801c-259">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="e801c-260">在 Office 365 中创建新用户有两个选项。</span><span class="sxs-lookup"><span data-stu-id="e801c-260">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="e801c-261">但是, 我们建议你的组织选择并使用一个选项来避免路由问题:</span><span class="sxs-lookup"><span data-stu-id="e801c-261">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="e801c-262">在本地 Active Directory 中创建用户并将用户同步到云。</span><span class="sxs-lookup"><span data-stu-id="e801c-262">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="e801c-263">请参阅[将本地目录与 Azure Active Directory 集成](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="e801c-263">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="e801c-264">直接在 Office 365 管理员门户中创建用户。</span><span class="sxs-lookup"><span data-stu-id="e801c-264">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="e801c-265">请参阅[向 Office 365 单独或批量添加用户-管理员帮助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="e801c-265">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="e801c-266">如果您的 Skype for Business Online 部署与 Skype for business 2015 或 Lync 2010/2013 本地部署并存, 则唯一支持的选项是在本地 Active Directory 中创建用户并将用户与云同步 (选项 1)。</span><span class="sxs-lookup"><span data-stu-id="e801c-266">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="e801c-267">所需的许可证:</span><span class="sxs-lookup"><span data-stu-id="e801c-267">Required licenses:</span></span> 

- <span data-ttu-id="e801c-268">Office 365 企业版 E3 (包括 SfB Plan2、Exchange Plan2 和团队) + 电话系统</span><span class="sxs-lookup"><span data-stu-id="e801c-268">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="e801c-269">Office 365 企业版 E5 (包括 SfB Plan2、Exchange Plan2、团队和手机系统)</span><span class="sxs-lookup"><span data-stu-id="e801c-269">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="e801c-270">可选许可证:</span><span class="sxs-lookup"><span data-stu-id="e801c-270">Optional licenses:</span></span> 

- <span data-ttu-id="e801c-271">通话计划</span><span class="sxs-lookup"><span data-stu-id="e801c-271">Calling Plan</span></span> 
- <span data-ttu-id="e801c-272">音频会议</span><span class="sxs-lookup"><span data-stu-id="e801c-272">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="e801c-273">确保用户托管在 Skype for Business Online 中</span><span class="sxs-lookup"><span data-stu-id="e801c-273">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="e801c-274">直接路由要求用户驻留在 Skype for Business Online 中。</span><span class="sxs-lookup"><span data-stu-id="e801c-274">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="e801c-275">你可以通过查看 RegistrarPool 参数来检查此情况。</span><span class="sxs-lookup"><span data-stu-id="e801c-275">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="e801c-276">它需要在 infra.lync.com 域中具有值。</span><span class="sxs-lookup"><span data-stu-id="e801c-276">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="e801c-277">连接到远程 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e801c-277">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="e801c-278">发出命令:</span><span class="sxs-lookup"><span data-stu-id="e801c-278">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="e801c-279">配置电话号码并启用企业语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="e801c-279">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="e801c-280">创建用户并分配许可证后, 下一步是配置其电话号码和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="e801c-280">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="e801c-281">这可通过一个步骤完成。</span><span class="sxs-lookup"><span data-stu-id="e801c-281">This can be done in one step.</span></span> 

<span data-ttu-id="e801c-282">要为语音邮件添加电话号码和启用, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e801c-282">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="e801c-283">连接到远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="e801c-283">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="e801c-284">输入命令:</span><span class="sxs-lookup"><span data-stu-id="e801c-284">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="e801c-285">例如, 若要为用户 "Spencer Low" 添加电话号码, 请输入以下内容:</span><span class="sxs-lookup"><span data-stu-id="e801c-285">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="e801c-286">使用的电话号码必须配置为完整的 E-164 个国家/地区代码的电话号码。</span><span class="sxs-lookup"><span data-stu-id="e801c-286">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="e801c-287">如果用户的电话号码是在本地管理的, 请使用本地 Skype for Business Management Shell 或控制面板配置用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="e801c-287">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="e801c-288">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="e801c-288">Configure Voice Routing</span></span> 

<span data-ttu-id="e801c-289">Microsoft Phone 系统具有一种路由机制, 允许根据以下情况将呼叫发送到特定的 SBC:</span><span class="sxs-lookup"><span data-stu-id="e801c-289">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="e801c-290">名为 "号码模式"</span><span class="sxs-lookup"><span data-stu-id="e801c-290">Called number pattern</span></span> 
- <span data-ttu-id="e801c-291">称为 "号码模式 +" 的特定用户进行呼叫</span><span class="sxs-lookup"><span data-stu-id="e801c-291">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="e801c-292">SBCs 可以指定为 "活动" 和 "备份"。</span><span class="sxs-lookup"><span data-stu-id="e801c-292">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="e801c-293">这意味着当为此号码模式或数字模式 + 特定用户配置为活动的 SBC 不可用时, 呼叫将路由到 backup SBC。</span><span class="sxs-lookup"><span data-stu-id="e801c-293">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="e801c-294">呼叫路由由以下元素组成:</span><span class="sxs-lookup"><span data-stu-id="e801c-294">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="e801c-295">语音路由策略-PSTN 使用的容器;可以分配给用户或多个用户</span><span class="sxs-lookup"><span data-stu-id="e801c-295">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="e801c-296">PSTN 用法–用于语音路由和 PSTN 使用的容器;可以在不同的语音路由策略中共享</span><span class="sxs-lookup"><span data-stu-id="e801c-296">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="e801c-297">语音路由-用于呼叫与模式匹配的呼叫的数字模式和联机 PSTN 网关集</span><span class="sxs-lookup"><span data-stu-id="e801c-297">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="e801c-298">联机 PSTN 网关-指向 SBC 的指针还存储通过 SBC 发出调用时应用的配置, 例如, 前 P 声明的身份 (PAI) 或首选编解码器;可以添加到语音路由</span><span class="sxs-lookup"><span data-stu-id="e801c-298">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="e801c-299">创建具有一种 PSTN 使用的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="e801c-299">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="e801c-300">下图显示了呼叫流中的语音路由策略的两个示例。</span><span class="sxs-lookup"><span data-stu-id="e801c-300">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="e801c-301">**呼叫流 1 (在左侧):** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx, 则该呼叫将路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="e801c-301">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="e801c-302">如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都不可用, 则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="e801c-302">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="e801c-303">**呼叫流程 2 (右侧):** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx, 则该调用首先路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="e801c-303">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="e801c-304">如果两个 SBC 均不可用, 将尝试具有较低优先级的路由 (sbc3.contoso.biz 和 sbc4.contoso.biz)。</span><span class="sxs-lookup"><span data-stu-id="e801c-304">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="e801c-305">如果没有 SBCs 可用, 将丢弃呼叫。</span><span class="sxs-lookup"><span data-stu-id="e801c-305">If none of the SBCs are available, the call is dropped.</span></span> 

![显示语音路由策略示例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="e801c-307">在这两个示例中, 虽然为语音路由分配了优先级, 但路由中的 SBCs 按随机顺序尝试。</span><span class="sxs-lookup"><span data-stu-id="e801c-307">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e801c-308">除非用户也有 Microsoft 通话计划许可证, 否则将删除示例配置中除与模式 + 1 425 XXX xx xx 或 + 1 206 XXX xx 之间的任何号码。</span><span class="sxs-lookup"><span data-stu-id="e801c-308">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="e801c-309">如果用户有呼叫计划许可证, 则会根据 Microsoft 通话计划的政策自动路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="e801c-309">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="e801c-310">Microsoft 通话计划将自动应用为具有 Microsoft 呼叫计划许可证的所有用户的最后一个路由, 并且不需要其他呼叫路由配置。</span><span class="sxs-lookup"><span data-stu-id="e801c-310">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="e801c-311">在下图所示的示例中, 添加了一个语音路由, 用于向所有其他美国和加拿大号码 (转到 "号码模式 + 1 XXX XXX xx xx" 呼叫) 发送呼叫。</span><span class="sxs-lookup"><span data-stu-id="e801c-311">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![显示具有第三个路线的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="e801c-313">对于所有其他呼叫, 如果用户同时具有两个许可证 (Microsoft Phone System 和 Microsoft 通话计划), 则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="e801c-313">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="e801c-314">如果没有与管理员创建的在线语音路线中的数字模式匹配, 请通过 Microsoft 通话计划进行路由。</span><span class="sxs-lookup"><span data-stu-id="e801c-314">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="e801c-315">如果用户仅有 Microsoft Phone 系统, 则呼叫将被丢弃, 因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="e801c-315">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e801c-316">在这种情况下, 路由 "其他 + 1" 的优先级值不重要, 因为只有一个路由与模式 + 1 XXX XXX xx 相匹配。</span><span class="sxs-lookup"><span data-stu-id="e801c-316">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="e801c-317">如果用户拨打 + 1 324 567 89 89 且 sbc5.contoso.biz 和 sbc6.contoso.biz 都不可用, 则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="e801c-317">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="e801c-318">下表总结了使用三个语音路由的配置。</span><span class="sxs-lookup"><span data-stu-id="e801c-318">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="e801c-319">在此示例中, 所有三个路由都属于同一 PSTN 使用 "美国和加拿大"。</span><span class="sxs-lookup"><span data-stu-id="e801c-319">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="e801c-320">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="e801c-320">**PSTN usage**</span></span>|<span data-ttu-id="e801c-321">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="e801c-321">**Voice route**</span></span>|<span data-ttu-id="e801c-322">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="e801c-322">**Number pattern**</span></span>|<span data-ttu-id="e801c-323">**优先级**</span><span class="sxs-lookup"><span data-stu-id="e801c-323">**Priority**</span></span>|<span data-ttu-id="e801c-324">**SBC**</span><span class="sxs-lookup"><span data-stu-id="e801c-324">**SBC**</span></span>|<span data-ttu-id="e801c-325">**说明**</span><span class="sxs-lookup"><span data-stu-id="e801c-325">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e801c-326">仅限美国</span><span class="sxs-lookup"><span data-stu-id="e801c-326">US only</span></span>|<span data-ttu-id="e801c-327">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="e801c-327">"Redmond 1"</span></span>|<span data-ttu-id="e801c-328">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e801c-328">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e801c-329">1</span><span class="sxs-lookup"><span data-stu-id="e801c-329">1</span></span>|<span data-ttu-id="e801c-330">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-330">sbc1.contoso.biz</span></span><br/><span data-ttu-id="e801c-331">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-331">sbc2.contoso.biz</span></span>|<span data-ttu-id="e801c-332">拨打的号码的活动路线 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="e801c-332">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e801c-333">仅限美国</span><span class="sxs-lookup"><span data-stu-id="e801c-333">US only</span></span>|<span data-ttu-id="e801c-334">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="e801c-334">"Redmond 2"</span></span>|<span data-ttu-id="e801c-335">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e801c-335">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e801c-336">2</span><span class="sxs-lookup"><span data-stu-id="e801c-336">2</span></span>|<span data-ttu-id="e801c-337">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-337">sbc3.contoso.biz</span></span><br/><span data-ttu-id="e801c-338">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-338">sbc4.contoso.biz</span></span>|<span data-ttu-id="e801c-339">已呼叫号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="e801c-339">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e801c-340">仅限美国</span><span class="sxs-lookup"><span data-stu-id="e801c-340">US only</span></span>|<span data-ttu-id="e801c-341">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="e801c-341">"Other +1"</span></span>|<span data-ttu-id="e801c-342">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="e801c-342">^\\+1(\d{10})$</span></span>|<span data-ttu-id="e801c-343">3</span><span class="sxs-lookup"><span data-stu-id="e801c-343">3</span></span>|<span data-ttu-id="e801c-344">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-344">sbc5.contoso.biz</span></span><br/><span data-ttu-id="e801c-345">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-345">sbc6.contoso.biz</span></span>|<span data-ttu-id="e801c-346">呼叫号码 + 1 XXX XXX xx (除 + 1 425 XXX xx 或 + 1 206 XXX xx 之间) 的路由</span><span class="sxs-lookup"><span data-stu-id="e801c-346">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="e801c-347">所有路线均与 PSTN 使用 "美国和加拿大" 相关联, PSTN 使用与 "仅美国" 的语音路由策略相关联。</span><span class="sxs-lookup"><span data-stu-id="e801c-347">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="e801c-348">在此示例中, 语音路由策略分配给用户 Spencer Low。</span><span class="sxs-lookup"><span data-stu-id="e801c-348">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="e801c-349">呼叫路线示例</span><span class="sxs-lookup"><span data-stu-id="e801c-349">Examples of call routes</span></span>

<span data-ttu-id="e801c-350">在以下示例中, 我们将演示如何配置路由、PSTN 使用情况和路由策略, 并为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="e801c-350">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="e801c-351">**步骤 1:** 创建 PSTN 使用 "美国和加拿大"。</span><span class="sxs-lookup"><span data-stu-id="e801c-351">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="e801c-352">在 Skype for business 远程 PowerShell 会话中, 键入:</span><span class="sxs-lookup"><span data-stu-id="e801c-352">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="e801c-353">通过输入以下内容验证是否已创建使用:</span><span class="sxs-lookup"><span data-stu-id="e801c-353">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="e801c-354">这将返回可能被截断的名称的列表:</span><span class="sxs-lookup"><span data-stu-id="e801c-354">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="e801c-355">在下面的示例中, 你可以查看运行 PowerShell 命令`(Get-CSOnlinePSTNUsage).usage`的结果以显示完整名称 (未截断)。</span><span class="sxs-lookup"><span data-stu-id="e801c-355">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="e801c-356">**步骤 2:** 在 Skype for Business Online 的 PowerShell 会话中, 创建三个路线: 雷德蒙1、雷德蒙2和其他 + 1, 如上表中所述。</span><span class="sxs-lookup"><span data-stu-id="e801c-356">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="e801c-357">要创建 "Redmond 1" 路线, 请输入:</span><span class="sxs-lookup"><span data-stu-id="e801c-357">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="e801c-358">返回:</span><span class="sxs-lookup"><span data-stu-id="e801c-358">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
<span data-ttu-id="e801c-359">若要创建雷德蒙2路线, 请输入:</span><span class="sxs-lookup"><span data-stu-id="e801c-359">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="e801c-360">若要创建其他 + 1 路线, 请输入:</span><span class="sxs-lookup"><span data-stu-id="e801c-360">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="e801c-361">请确保 NumberPattern 属性中的正则表达式是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="e801c-361">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="e801c-362">你可以使用此网站对其进行测试:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="e801c-362">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="e801c-363">在某些情况下, 需要将所有调用路由到同一 SBC;请使用-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="e801c-363">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="e801c-364">将所有呼叫路由到同一 SBC</span><span class="sxs-lookup"><span data-stu-id="e801c-364">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="e801c-365">通过使用如下所示的选项运行`Get-CSOnlineVoiceRoute` PowerShell 命令验证是否已正确配置路由:</span><span class="sxs-lookup"><span data-stu-id="e801c-365">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="e801c-366">应返回:</span><span class="sxs-lookup"><span data-stu-id="e801c-366">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="e801c-367">在此示例中, 自动为 "其他 + 1" 路由分配优先级4。</span><span class="sxs-lookup"><span data-stu-id="e801c-367">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="e801c-368">**步骤 3:** 创建语音路由策略 "仅美国", 并将 PSTN 使用 "美国和加拿大" 添加到该策略。</span><span class="sxs-lookup"><span data-stu-id="e801c-368">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="e801c-369">在 Skype for Business Online 的 PowerShell 会话中, 键入:</span><span class="sxs-lookup"><span data-stu-id="e801c-369">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="e801c-370">此示例中显示了结果:</span><span class="sxs-lookup"><span data-stu-id="e801c-370">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="e801c-371">**步骤 4:** 使用 PowerShell 向用户授予 Spencer 低的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="e801c-371">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="e801c-372">在 Skype for Business Online 的 PowerShell 会话中, 键入:</span><span class="sxs-lookup"><span data-stu-id="e801c-372">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="e801c-373">通过输入以下命令验证策略分配:</span><span class="sxs-lookup"><span data-stu-id="e801c-373">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="e801c-374">返回:</span><span class="sxs-lookup"><span data-stu-id="e801c-374">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="e801c-375">创建具有多个 PSTN 用法的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="e801c-375">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="e801c-376">以前创建的语音路由策略仅允许拨打美国和加拿大的电话号码, 除非还为用户分配了 Microsoft 通话计划许可证。</span><span class="sxs-lookup"><span data-stu-id="e801c-376">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="e801c-377">在下面的示例中, 您可以创建语音路由策略 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="e801c-377">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="e801c-378">该策略重用在上一个示例中创建的 PSTN 使用 "美国和加拿大", 以及新的 PSTN 使用 "国际"。</span><span class="sxs-lookup"><span data-stu-id="e801c-378">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="e801c-379">这会将所有其他调用路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="e801c-379">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="e801c-380">显示的示例将 "仅美国" 策略分配给用户 "Spencer Low", 不限制用户 "John"。</span><span class="sxs-lookup"><span data-stu-id="e801c-380">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="e801c-381">Spencer 低–只允许拨打美国和加拿大号码的电话。</span><span class="sxs-lookup"><span data-stu-id="e801c-381">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="e801c-382">当呼叫雷德蒙数字范围时, 必须使用一组特定的 SBC。</span><span class="sxs-lookup"><span data-stu-id="e801c-382">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="e801c-383">除非向用户分配了通话计划许可证, 否则不会路由非美国号码。</span><span class="sxs-lookup"><span data-stu-id="e801c-383">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="e801c-384">John 的一对电话-允许拨打任何号码的电话。</span><span class="sxs-lookup"><span data-stu-id="e801c-384">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="e801c-385">当呼叫雷德蒙数字范围时, 必须使用一组特定的 SBC。</span><span class="sxs-lookup"><span data-stu-id="e801c-385">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="e801c-386">非 US 数字将通过 sbc2.contoso.biz 和 sbc5.contoso.biz 进行路由。</span><span class="sxs-lookup"><span data-stu-id="e801c-386">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![显示分配给用户 Spencer 低的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="e801c-388">对于所有其他呼叫, 如果用户同时具有两个许可证 (Microsoft Phone System 和 Microsoft 通话计划), 则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="e801c-388">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="e801c-389">如果没有与管理员创建的在线语音路线中的数字模式匹配, 请通过 Microsoft 通话计划进行路由。</span><span class="sxs-lookup"><span data-stu-id="e801c-389">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="e801c-390">如果用户仅有 Microsoft Phone 系统, 则呼叫将被丢弃, 因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="e801c-390">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![显示分配给用户 John 的的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="e801c-392">下表总结了路由策略 "无限制" 的用法标识和语音路由。</span><span class="sxs-lookup"><span data-stu-id="e801c-392">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="e801c-393">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="e801c-393">**PSTN usage**</span></span>|<span data-ttu-id="e801c-394">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="e801c-394">**Voice route**</span></span>|<span data-ttu-id="e801c-395">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="e801c-395">**Number pattern**</span></span>|<span data-ttu-id="e801c-396">**优先级**</span><span class="sxs-lookup"><span data-stu-id="e801c-396">**Priority**</span></span>|<span data-ttu-id="e801c-397">**SBC**</span><span class="sxs-lookup"><span data-stu-id="e801c-397">**SBC**</span></span>|<span data-ttu-id="e801c-398">**说明**</span><span class="sxs-lookup"><span data-stu-id="e801c-398">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e801c-399">仅限美国</span><span class="sxs-lookup"><span data-stu-id="e801c-399">US Only</span></span>|<span data-ttu-id="e801c-400">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="e801c-400">"Redmond 1"</span></span>|<span data-ttu-id="e801c-401">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e801c-401">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e801c-402">1</span><span class="sxs-lookup"><span data-stu-id="e801c-402">1</span></span>|<span data-ttu-id="e801c-403">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-403">sbc1.contoso.biz</span></span><br/><span data-ttu-id="e801c-404">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-404">sbc2.contoso.biz</span></span>|<span data-ttu-id="e801c-405">被呼叫方号码的活动路由 + 1 425 XXX XX XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="e801c-405">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e801c-406">仅限美国</span><span class="sxs-lookup"><span data-stu-id="e801c-406">US Only</span></span>|<span data-ttu-id="e801c-407">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="e801c-407">"Redmond 2"</span></span>|<span data-ttu-id="e801c-408">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e801c-408">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e801c-409">2</span><span class="sxs-lookup"><span data-stu-id="e801c-409">2</span></span>|<span data-ttu-id="e801c-410">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-410">sbc3.contoso.biz</span></span><br/><span data-ttu-id="e801c-411">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-411">sbc4.contoso.biz</span></span>|<span data-ttu-id="e801c-412">被呼叫方号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="e801c-412">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e801c-413">仅限美国</span><span class="sxs-lookup"><span data-stu-id="e801c-413">US Only</span></span>|<span data-ttu-id="e801c-414">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="e801c-414">"Other +1"</span></span>|<span data-ttu-id="e801c-415">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="e801c-415">^\\+1(\d{10})$</span></span>|<span data-ttu-id="e801c-416">3</span><span class="sxs-lookup"><span data-stu-id="e801c-416">3</span></span>|<span data-ttu-id="e801c-417">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-417">sbc5.contoso.biz</span></span><br/><span data-ttu-id="e801c-418">sbc6> contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-418">sbc6>.contoso.biz</span></span>|<span data-ttu-id="e801c-419">被呼叫方号码的路由 + 1 XXX XXX xx (除 + 1 425 XXX xx 或 + 1 206 XXX xx)</span><span class="sxs-lookup"><span data-stu-id="e801c-419">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="e801c-420">International</span><span class="sxs-lookup"><span data-stu-id="e801c-420">International</span></span>|<span data-ttu-id="e801c-421">International</span><span class="sxs-lookup"><span data-stu-id="e801c-421">International</span></span>|<span data-ttu-id="e801c-422">\d +</span><span class="sxs-lookup"><span data-stu-id="e801c-422">\d+</span></span>|<span data-ttu-id="e801c-423">4</span><span class="sxs-lookup"><span data-stu-id="e801c-423">4</span></span>|<span data-ttu-id="e801c-424">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-424">sbc2.contoso.biz</span></span><br/><span data-ttu-id="e801c-425">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e801c-425">sbc5.contoso.biz</span></span>|<span data-ttu-id="e801c-426">任何数字模式的路由</span><span class="sxs-lookup"><span data-stu-id="e801c-426">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="e801c-427">语音路由策略中的 PSTN 用法的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="e801c-427">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="e801c-428">使用实例按顺序应用, 如果在第一次使用中发现匹配项, 则从不计算其他用法。</span><span class="sxs-lookup"><span data-stu-id="e801c-428">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="e801c-429">PSTN 使用 "国际" 必须放置在 PSTN 使用 "仅限美国" 之后。</span><span class="sxs-lookup"><span data-stu-id="e801c-429">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="e801c-430">若要更改 PSTN 用法的顺序, 请运行`Set-CSOnlineVoiceRoutingPolicy`命令。</span><span class="sxs-lookup"><span data-stu-id="e801c-430">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="e801c-431">例如, 若要将订单从 "美国和加拿大" 的第一个和 "国际" 的订单更改为反向顺序, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e801c-431">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="e801c-432">将自动分配 "其他 + 1" 和 "国际" 语音路由的优先级。</span><span class="sxs-lookup"><span data-stu-id="e801c-432">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="e801c-433">它们的优先级与 "Redmond 1" 和 "雷德蒙 2" 相比, 不是很重要。</span><span class="sxs-lookup"><span data-stu-id="e801c-433">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="e801c-434">用户 John 的 "语音路由策略" 的示例</span><span class="sxs-lookup"><span data-stu-id="e801c-434">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="e801c-435">创建 PSTN 使用 "国际"、语音路由 "国际"、"语音路由策略" 无限制, 然后将其分配给用户 "John (John)" 的步骤如下所示。</span><span class="sxs-lookup"><span data-stu-id="e801c-435">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="e801c-436">首先, 创建 PSTN 使用 "国际"。</span><span class="sxs-lookup"><span data-stu-id="e801c-436">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="e801c-437">在 Skype for Business Online 中的远程 PowerShell 会话中, 输入:</span><span class="sxs-lookup"><span data-stu-id="e801c-437">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="e801c-438">接下来, 创建新的语音路线 "国际"。</span><span class="sxs-lookup"><span data-stu-id="e801c-438">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="e801c-439">返回:</span><span class="sxs-lookup"><span data-stu-id="e801c-439">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SuppressCallerId          :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="e801c-440">接下来, 创建语音路由策略 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="e801c-440">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="e801c-441">PSTN 使用 "Redmond 1" 和 "Redmond" 在此语音路由策略中重复使用, 以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理, 作为本地或本地呼叫。</span><span class="sxs-lookup"><span data-stu-id="e801c-441">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="e801c-442">返回的</span><span class="sxs-lookup"><span data-stu-id="e801c-442">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="e801c-443">使用以下命令将语音路由策略分配给用户 "John 的工作"。</span><span class="sxs-lookup"><span data-stu-id="e801c-443">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="e801c-444">然后使用以下命令验证作业:</span><span class="sxs-lookup"><span data-stu-id="e801c-444">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="e801c-445">返回:</span><span class="sxs-lookup"><span data-stu-id="e801c-445">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="e801c-446">结果是, 应用到 John 54777 的语音政策不受限制, 并且将遵循可用于美国、加拿大和国际通话的呼叫路线逻辑。</span><span class="sxs-lookup"><span data-stu-id="e801c-446">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="e801c-447">将 Microsoft 团队设置为用户的首选调用客户端</span><span class="sxs-lookup"><span data-stu-id="e801c-447">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="e801c-448">"直接路由" 仅当用户使用团队客户端时, 才路由与他们的通话。</span><span class="sxs-lookup"><span data-stu-id="e801c-448">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="e801c-449">如果你的组织仅使用团队, 建议在升级策略中设置 "仅团队" 模式。</span><span class="sxs-lookup"><span data-stu-id="e801c-449">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="e801c-450">如果你的组织使用 Skype for business 服务器或 Skype for business Online, 请参阅以下文章了解详细信息, 然后选择相应选项:[了解 Skype for business 和团队的共存和升级旅程](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="e801c-450">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="e801c-451">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e801c-451">See also</span></span>

[<span data-ttu-id="e801c-452">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="e801c-452">Plan Direct Routing</span></span>](direct-routing-plan.md)
