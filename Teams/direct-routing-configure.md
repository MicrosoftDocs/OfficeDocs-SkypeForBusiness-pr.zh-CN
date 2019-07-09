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
ms.openlocfilehash: 154f1b08d01bc9e66d7928d6f136c3c69c48efcc
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588148"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="3263f-103">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="3263f-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="3263f-104">观看以下会话, 了解直接路由的好处、如何为其规划以及如何部署它: [Microsoft 团队中的直接路由](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="3263f-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="3263f-105">如果尚未执行此操作, 请阅读 "针对先决条件的[计划直接路由](direct-routing-plan.md)", 并查看配置 Microsoft Phone 系统网络之前需要执行的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="3263f-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="3263f-106">本文介绍如何配置 Microsoft Phone 系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="3263f-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="3263f-107">它详细介绍了如何将受支持的会话边界控制器 (SBC) 配对到直接路由, 以及如何将 Microsoft 团队用户配置为使用直接路由连接到公共交换电话网络 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="3263f-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="3263f-108">为了完成本文中介绍的步骤, 管理员需要熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3263f-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="3263f-109">有关使用 PowerShell 的详细信息, 请参阅[设置适用于 Windows powershell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3263f-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="3263f-110">我们建议你确认你的 SBC 已按照 SBC 供应商的建议进行配置:</span><span class="sxs-lookup"><span data-stu-id="3263f-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="3263f-111">AudioCodes 部署文档</span><span class="sxs-lookup"><span data-stu-id="3263f-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="3263f-112">功能区通信部署文档</span><span class="sxs-lookup"><span data-stu-id="3263f-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="3263f-113">你可以配置 Microsoft Phone 系统并使用户能够使用直接路由, 然后通过完成以下过程将 Microsoft 团队设置为首选调用客户端:</span><span class="sxs-lookup"><span data-stu-id="3263f-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="3263f-114">将 SBC 与 Microsoft Phone 系统配对并验证配对</span><span class="sxs-lookup"><span data-stu-id="3263f-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="3263f-115">为用户启用直接路由服务</span><span class="sxs-lookup"><span data-stu-id="3263f-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="3263f-116">确保 Microsoft 团队是用户的首选调用客户端</span><span class="sxs-lookup"><span data-stu-id="3263f-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="3263f-117">将 SBC 与电话系统的直接路由服务配对</span><span class="sxs-lookup"><span data-stu-id="3263f-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="3263f-118">下面是让你将 SBC 连接或配对到直接路由接口的三个高级步骤:</span><span class="sxs-lookup"><span data-stu-id="3263f-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="3263f-119">使用 PowerShell 连接到**Skype For Business Online**管理中心</span><span class="sxs-lookup"><span data-stu-id="3263f-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="3263f-120">对 SBC 进行配对</span><span class="sxs-lookup"><span data-stu-id="3263f-120">Pair the SBC</span></span> 
- <span data-ttu-id="3263f-121">验证配对</span><span class="sxs-lookup"><span data-stu-id="3263f-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="3263f-122">使用 PowerShell 连接到 Skype for business Online</span><span class="sxs-lookup"><span data-stu-id="3263f-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="3263f-123">你可以使用连接到租户的 PowerShell 会话将 SBC 与直接路由接口配对。</span><span class="sxs-lookup"><span data-stu-id="3263f-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="3263f-124">若要打开 PowerShell 会话, 请按照[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中概述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="3263f-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="3263f-125">建立远程 PowerShell 会话后, 请验证你是否可以看到用于管理 SBC 的命令。</span><span class="sxs-lookup"><span data-stu-id="3263f-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="3263f-126">若要验证命令, 请在 PowerShell 会话中键入或复制/粘贴以下内容, 然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="3263f-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="3263f-127">你的命令将返回此处所示的4个函数, 这些函数将允许你管理 SBC。</span><span class="sxs-lookup"><span data-stu-id="3263f-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="3263f-128">将 SBC 与租户配对</span><span class="sxs-lookup"><span data-stu-id="3263f-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="3263f-129">若要将 SBC 与租户配对, 请在 PowerShell 会话中键入以下内容, 然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="3263f-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="3263f-130">强烈建议使用 SBC 文档中提供的信息, 在 SBC 中设置最大通话限制。</span><span class="sxs-lookup"><span data-stu-id="3263f-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="3263f-131">如果 SBC 处于容量级别, 则该限制将触发通知。</span><span class="sxs-lookup"><span data-stu-id="3263f-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="3263f-132">仅当 FQDN 的域部分与你的租户中注册的一个域 (onmicrosoft.com 除外\*) 匹配时, 你才可以对 SBC 进行配对。</span><span class="sxs-lookup"><span data-stu-id="3263f-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="3263f-133">SBC \*FQDN 名称不支持使用 onmicrosoft.com 域名。</span><span class="sxs-lookup"><span data-stu-id="3263f-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="3263f-134">例如, 如果您有两个域名:</span><span class="sxs-lookup"><span data-stu-id="3263f-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="3263f-135">**contoso**</span><span class="sxs-lookup"><span data-stu-id="3263f-135">**contoso**.com</span></span><br/><span data-ttu-id="3263f-136">\*\*\*\* onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3263f-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="3263f-137">对于 SBC 名称, 你可以使用名称 sbc.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3263f-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="3263f-138">如果你尝试将 SBC 与名称 SBC 对应, 则系统将不会允许你, 因为域不属于此租户。</span><span class="sxs-lookup"><span data-stu-id="3263f-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="3263f-139">除了在租户中注册的域, 还必须有一个具有该域的用户以及分配的 E3 或 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="3263f-139">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="3263f-140">如果不是, 您将收到以下错误:</span><span class="sxs-lookup"><span data-stu-id="3263f-140">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="3263f-141">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="3263f-141"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="3263f-142">返回</span><span class="sxs-lookup"><span data-stu-id="3263f-142">Returns:</span></span>
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
<span data-ttu-id="3263f-143">在配对过程中, 可以设置其他选项。</span><span class="sxs-lookup"><span data-stu-id="3263f-143">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="3263f-144">但是, 在前面的示例中, 仅显示所需的最低参数。</span><span class="sxs-lookup"><span data-stu-id="3263f-144">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="3263f-145">下表列出了可用于设置参数的其他参数`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="3263f-145">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="3263f-146">必填？</span><span class="sxs-lookup"><span data-stu-id="3263f-146">Required?</span></span>|<span data-ttu-id="3263f-147">名称</span><span class="sxs-lookup"><span data-stu-id="3263f-147">Name</span></span>|<span data-ttu-id="3263f-148">描述</span><span class="sxs-lookup"><span data-stu-id="3263f-148">Description</span></span>|<span data-ttu-id="3263f-149">默认值</span><span class="sxs-lookup"><span data-stu-id="3263f-149">Default</span></span>|<span data-ttu-id="3263f-150">可能的值</span><span class="sxs-lookup"><span data-stu-id="3263f-150">Possible values</span></span>|<span data-ttu-id="3263f-151">类型和限制</span><span class="sxs-lookup"><span data-stu-id="3263f-151">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3263f-152">是</span><span class="sxs-lookup"><span data-stu-id="3263f-152">Yes</span></span>|<span data-ttu-id="3263f-153">FQDN</span><span class="sxs-lookup"><span data-stu-id="3263f-153">FQDN</span></span>|<span data-ttu-id="3263f-154">SBC 的 FQDN 名称</span><span class="sxs-lookup"><span data-stu-id="3263f-154">The FQDN name of the SBC</span></span> |<span data-ttu-id="3263f-155">无</span><span class="sxs-lookup"><span data-stu-id="3263f-155">None</span></span>|<span data-ttu-id="3263f-156">NoneFQDN 名称, 限制63个字符</span><span class="sxs-lookup"><span data-stu-id="3263f-156">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="3263f-157">字符串、[适用于计算机、域、网站和 ou 的 Active Directory 中的命名约定](https://support.microsoft.com/help/909264)的允许和不允许的字符列表</span><span class="sxs-lookup"><span data-stu-id="3263f-157">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="3263f-158">否</span><span class="sxs-lookup"><span data-stu-id="3263f-158">No</span></span>|<span data-ttu-id="3263f-159">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="3263f-159">MediaBypass</span></span> |<span data-ttu-id="3263f-160">保留供将来使用的参数。</span><span class="sxs-lookup"><span data-stu-id="3263f-160">The parameter reserved for future use.</span></span> <span data-ttu-id="3263f-161">指示 SBC 的参数支持媒体绕过, 并且管理员希望使用它。</span><span class="sxs-lookup"><span data-stu-id="3263f-161">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="3263f-162">无</span><span class="sxs-lookup"><span data-stu-id="3263f-162">None</span></span>|<span data-ttu-id="3263f-163">True</span><span class="sxs-lookup"><span data-stu-id="3263f-163">True</span></span><br/><span data-ttu-id="3263f-164">False</span><span class="sxs-lookup"><span data-stu-id="3263f-164">False</span></span>|<span data-ttu-id="3263f-165">Boolean</span><span class="sxs-lookup"><span data-stu-id="3263f-165">Boolean</span></span>|
|<span data-ttu-id="3263f-166">是</span><span class="sxs-lookup"><span data-stu-id="3263f-166">Yes</span></span>|<span data-ttu-id="3263f-167">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="3263f-167">SipSignallingPort</span></span> |<span data-ttu-id="3263f-168">用于通过使用传输层安全性 (TLS) 协议与直接路由服务进行通信的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="3263f-168">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="3263f-169">无</span><span class="sxs-lookup"><span data-stu-id="3263f-169">None</span></span>|<span data-ttu-id="3263f-170">任何端口</span><span class="sxs-lookup"><span data-stu-id="3263f-170">Any port</span></span>|<span data-ttu-id="3263f-171">0到65535</span><span class="sxs-lookup"><span data-stu-id="3263f-171">0 to 65535</span></span> |
|<span data-ttu-id="3263f-172">否</span><span class="sxs-lookup"><span data-stu-id="3263f-172">No</span></span>|<span data-ttu-id="3263f-173">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="3263f-173">FailoverTimeSeconds</span></span> |<span data-ttu-id="3263f-174">设置为 10 (默认值) 时, 在10秒内网关未接听的出站呼叫将被路由到下一个可用的中继;如果没有其他中继, 则会自动删除呼叫。</span><span class="sxs-lookup"><span data-stu-id="3263f-174">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="3263f-175">在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。</span><span class="sxs-lookup"><span data-stu-id="3263f-175">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="3263f-176">默认值为10。</span><span class="sxs-lookup"><span data-stu-id="3263f-176">The default value is 10.</span></span>|<span data-ttu-id="3263f-177">10</span><span class="sxs-lookup"><span data-stu-id="3263f-177">10</span></span>|<span data-ttu-id="3263f-178">数字</span><span class="sxs-lookup"><span data-stu-id="3263f-178">Number</span></span>|<span data-ttu-id="3263f-179">整形</span><span class="sxs-lookup"><span data-stu-id="3263f-179">Int</span></span>|
|<span data-ttu-id="3263f-180">否</span><span class="sxs-lookup"><span data-stu-id="3263f-180">No</span></span>|<span data-ttu-id="3263f-181">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="3263f-181">ForwardCallHistory</span></span> |<span data-ttu-id="3263f-182">指示是否通过中继转移呼叫历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="3263f-182">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="3263f-183">如果启用, 则 Office 365 PSTN 代理将发送两个标头: 历史记录信息和引用者。</span><span class="sxs-lookup"><span data-stu-id="3263f-183">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="3263f-184">默认值为**False** ($False)。</span><span class="sxs-lookup"><span data-stu-id="3263f-184">The default value is **False** ($False).</span></span> |<span data-ttu-id="3263f-185">False</span><span class="sxs-lookup"><span data-stu-id="3263f-185">False</span></span>|<span data-ttu-id="3263f-186">True</span><span class="sxs-lookup"><span data-stu-id="3263f-186">True</span></span><br/><span data-ttu-id="3263f-187">False</span><span class="sxs-lookup"><span data-stu-id="3263f-187">False</span></span>|<span data-ttu-id="3263f-188">Boolean</span><span class="sxs-lookup"><span data-stu-id="3263f-188">Boolean</span></span>|
|<span data-ttu-id="3263f-189">否</span><span class="sxs-lookup"><span data-stu-id="3263f-189">No</span></span>|<span data-ttu-id="3263f-190">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="3263f-190">ForwardPAI</span></span>|<span data-ttu-id="3263f-191">指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。</span><span class="sxs-lookup"><span data-stu-id="3263f-191">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="3263f-192">PAI 标头提供了一种验证呼叫者身份的方法。</span><span class="sxs-lookup"><span data-stu-id="3263f-192">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="3263f-193">如果启用, 则隐私: ID 标头也会发送。</span><span class="sxs-lookup"><span data-stu-id="3263f-193">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="3263f-194">默认值为**False** ($False)。</span><span class="sxs-lookup"><span data-stu-id="3263f-194">The default value is **False** ($False).</span></span>|<span data-ttu-id="3263f-195">False</span><span class="sxs-lookup"><span data-stu-id="3263f-195">False</span></span>|<span data-ttu-id="3263f-196">True</span><span class="sxs-lookup"><span data-stu-id="3263f-196">True</span></span><br/><span data-ttu-id="3263f-197">False</span><span class="sxs-lookup"><span data-stu-id="3263f-197">False</span></span>|<span data-ttu-id="3263f-198">Boolean</span><span class="sxs-lookup"><span data-stu-id="3263f-198">Boolean</span></span>|
|<span data-ttu-id="3263f-199">否</span><span class="sxs-lookup"><span data-stu-id="3263f-199">No</span></span>|<span data-ttu-id="3263f-200">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="3263f-200">SendSIPOptions</span></span> |<span data-ttu-id="3263f-201">定义 SBC 是否将发送 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="3263f-201">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="3263f-202">如果禁用, 将从监视和通知系统中排除 SBC。</span><span class="sxs-lookup"><span data-stu-id="3263f-202">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="3263f-203">强烈建议你启用 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="3263f-203">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="3263f-204">默认值为**True**。</span><span class="sxs-lookup"><span data-stu-id="3263f-204">Default value is **True**.</span></span> |<span data-ttu-id="3263f-205">True</span><span class="sxs-lookup"><span data-stu-id="3263f-205">True</span></span>|<span data-ttu-id="3263f-206">True</span><span class="sxs-lookup"><span data-stu-id="3263f-206">True</span></span><br/><span data-ttu-id="3263f-207">False</span><span class="sxs-lookup"><span data-stu-id="3263f-207">False</span></span>|<span data-ttu-id="3263f-208">Boolean</span><span class="sxs-lookup"><span data-stu-id="3263f-208">Boolean</span></span>|
|<span data-ttu-id="3263f-209">否</span><span class="sxs-lookup"><span data-stu-id="3263f-209">No</span></span>|<span data-ttu-id="3263f-210">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="3263f-210">MaxConcurrentSessions</span></span> |<span data-ttu-id="3263f-211">由警报系统使用。</span><span class="sxs-lookup"><span data-stu-id="3263f-211">Used by alerting system.</span></span> <span data-ttu-id="3263f-212">如果设置了任何值, 则当并发会话的数量为 90% 或高于此值时, 警报系统将向租户管理员生成警报。</span><span class="sxs-lookup"><span data-stu-id="3263f-212">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="3263f-213">如果未设置参数, 则不会生成警报。</span><span class="sxs-lookup"><span data-stu-id="3263f-213">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="3263f-214">但是, 监视系统将每隔24小时报告并发会话的数量。</span><span class="sxs-lookup"><span data-stu-id="3263f-214">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="3263f-215">Null</span><span class="sxs-lookup"><span data-stu-id="3263f-215">Null</span></span>|<span data-ttu-id="3263f-216">Null</span><span class="sxs-lookup"><span data-stu-id="3263f-216">Null</span></span><br/><span data-ttu-id="3263f-217">1到100000</span><span class="sxs-lookup"><span data-stu-id="3263f-217">1 to 100,000</span></span> ||
|<span data-ttu-id="3263f-218">否</span><span class="sxs-lookup"><span data-stu-id="3263f-218">No</span></span>|<span data-ttu-id="3263f-219">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="3263f-219">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="3263f-220">允许手动选择媒体的路径。</span><span class="sxs-lookup"><span data-stu-id="3263f-220">Allows selecting path for media manually.</span></span> <span data-ttu-id="3263f-221">直接路由根据 SBC 的公共 IP 为媒体路径分配一个数据中心。</span><span class="sxs-lookup"><span data-stu-id="3263f-221">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="3263f-222">我们始终选择最接近于 SBC 数据中心的数据。</span><span class="sxs-lookup"><span data-stu-id="3263f-222">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="3263f-223">但是, 在某些情况下, 可以将美国范围的公共 IP 分配给位于欧洲的 SBC。</span><span class="sxs-lookup"><span data-stu-id="3263f-223">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="3263f-224">在这种情况下, 我们将使用非最佳媒体路径。</span><span class="sxs-lookup"><span data-stu-id="3263f-224">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="3263f-225">此参数允许手动设置媒体流量的首选区域。</span><span class="sxs-lookup"><span data-stu-id="3263f-225">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="3263f-226">仅当通话记录明确指明 "自动分配媒体路径的数据中心" 不会向 SBC 数据中心分配最接近的数据中心时, 我们才建议设置此参数。</span><span class="sxs-lookup"><span data-stu-id="3263f-226">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="3263f-227">无</span><span class="sxs-lookup"><span data-stu-id="3263f-227">None</span></span>|<span data-ttu-id="3263f-228">ISO 格式的国家代码</span><span class="sxs-lookup"><span data-stu-id="3263f-228">Country codes in ISO format</span></span>||
|<span data-ttu-id="3263f-229">否</span><span class="sxs-lookup"><span data-stu-id="3263f-229">No</span></span>|<span data-ttu-id="3263f-230">已启用</span><span class="sxs-lookup"><span data-stu-id="3263f-230">Enabled</span></span>|<span data-ttu-id="3263f-231">用于为出站呼叫启用此 SBC。</span><span class="sxs-lookup"><span data-stu-id="3263f-231">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="3263f-232">可用于在其更新或维护期间临时删除 SBC。</span><span class="sxs-lookup"><span data-stu-id="3263f-232">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="3263f-233">False</span><span class="sxs-lookup"><span data-stu-id="3263f-233">False</span></span>|<span data-ttu-id="3263f-234">True</span><span class="sxs-lookup"><span data-stu-id="3263f-234">True</span></span><br/><span data-ttu-id="3263f-235">False</span><span class="sxs-lookup"><span data-stu-id="3263f-235">False</span></span>|<span data-ttu-id="3263f-236">Boolean</span><span class="sxs-lookup"><span data-stu-id="3263f-236">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="3263f-237">验证 SBC 配对</span><span class="sxs-lookup"><span data-stu-id="3263f-237">Verify the SBC pairing</span></span> 

<span data-ttu-id="3263f-238">验证连接:</span><span class="sxs-lookup"><span data-stu-id="3263f-238">Verify the connection:</span></span> 
- <span data-ttu-id="3263f-239">检查 SBC 是否在成对的 SBCs 的列表中。</span><span class="sxs-lookup"><span data-stu-id="3263f-239">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="3263f-240">验证 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="3263f-240">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="3263f-241">验证 SBC 是否位于成对的 SBCs 的列表中</span><span class="sxs-lookup"><span data-stu-id="3263f-241">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="3263f-242">对 SBC 进行配对后, 通过在远程 PowerShell 会话中运行以下命令验证 SBC 是否存在于成对的 SBCs 列表中:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="3263f-242">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="3263f-243">配对网关应显示在列表中, 如下面的示例所示, 并验证*启用*的参数是否显示值**True**。</span><span class="sxs-lookup"><span data-stu-id="3263f-243">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="3263f-244">键</span><span class="sxs-lookup"><span data-stu-id="3263f-244">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="3263f-245">返回:</span><span class="sxs-lookup"><span data-stu-id="3263f-245">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="3263f-246">验证 SIP 选项流</span><span class="sxs-lookup"><span data-stu-id="3263f-246">Validate SIP Options flow</span></span> 

<span data-ttu-id="3263f-247">若要使用传出 SIP 选项验证配对, 请使用 SBC 管理界面并确认 SBC 是否收到对其传出选项消息的 200 OK 响应。</span><span class="sxs-lookup"><span data-stu-id="3263f-247">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="3263f-248">当直接路由看到传入选项时, 它将向 "传入选项" 消息的 "联系人标题" 字段中配置的 SBC FQDN 开始发送传出 SIP 选项消息。</span><span class="sxs-lookup"><span data-stu-id="3263f-248">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="3263f-249">若要使用传入 SIP 选项验证配对, 请使用 SBC 管理接口, 并查看 SBC 是否向来自直接路由的选项消息发送回复, 并且它发送的响应代码为 200 OK。</span><span class="sxs-lookup"><span data-stu-id="3263f-249">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="3263f-250">为用户启用直接路由服务</span><span class="sxs-lookup"><span data-stu-id="3263f-250">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="3263f-251">准备好为直接路由服务用户启用用户时, 请按照下列步骤操作:</span><span class="sxs-lookup"><span data-stu-id="3263f-251">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="3263f-252">在 Office 365 中创建用户并分配电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="3263f-252">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="3263f-253">确保用户托管在 Skype for Business Online 中。</span><span class="sxs-lookup"><span data-stu-id="3263f-253">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="3263f-254">配置电话号码并启用企业语音和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3263f-254">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="3263f-255">配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="3263f-255">Configure voice routing.</span></span> <span data-ttu-id="3263f-256">将自动验证该路线。</span><span class="sxs-lookup"><span data-stu-id="3263f-256">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="3263f-257">在 Office 365 中创建用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="3263f-257">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="3263f-258">在 Office 365 中创建新用户有两个选项。</span><span class="sxs-lookup"><span data-stu-id="3263f-258">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="3263f-259">但是, 我们建议你的组织选择并使用一个选项来避免路由问题:</span><span class="sxs-lookup"><span data-stu-id="3263f-259">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="3263f-260">在本地 Active Directory 中创建用户并将用户同步到云。</span><span class="sxs-lookup"><span data-stu-id="3263f-260">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="3263f-261">请参阅[将本地目录与 Azure Active Directory 集成](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="3263f-261">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="3263f-262">直接在 Office 365 管理员门户中创建用户。</span><span class="sxs-lookup"><span data-stu-id="3263f-262">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="3263f-263">请参阅[向 Office 365 单独或批量添加用户-管理员帮助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="3263f-263">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="3263f-264">如果您的 Skype for Business Online 部署与 Skype for business 2015 或 Lync 2010/2013 本地部署并存, 则唯一支持的选项是在本地 Active Directory 中创建用户并将用户与云同步 (选项 1)。</span><span class="sxs-lookup"><span data-stu-id="3263f-264">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="3263f-265">所需的许可证:</span><span class="sxs-lookup"><span data-stu-id="3263f-265">Required licenses:</span></span> 

- <span data-ttu-id="3263f-266">Office 365 企业版 E3 (包括 SfB Plan2、Exchange Plan2 和团队) + 电话系统</span><span class="sxs-lookup"><span data-stu-id="3263f-266">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="3263f-267">Office 365 企业版 E5 (包括 SfB Plan2、Exchange Plan2、团队和手机系统)</span><span class="sxs-lookup"><span data-stu-id="3263f-267">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="3263f-268">可选许可证:</span><span class="sxs-lookup"><span data-stu-id="3263f-268">Optional licenses:</span></span> 

- <span data-ttu-id="3263f-269">通话计划</span><span class="sxs-lookup"><span data-stu-id="3263f-269">Calling Plan</span></span> 
- <span data-ttu-id="3263f-270">音频会议</span><span class="sxs-lookup"><span data-stu-id="3263f-270">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="3263f-271">确保用户托管在 Skype for Business Online 中</span><span class="sxs-lookup"><span data-stu-id="3263f-271">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="3263f-272">直接路由要求用户驻留在 Skype for Business Online 中。</span><span class="sxs-lookup"><span data-stu-id="3263f-272">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="3263f-273">你可以通过查看 RegistrarPool 参数来检查此情况。</span><span class="sxs-lookup"><span data-stu-id="3263f-273">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="3263f-274">它需要在 infra.lync.com 域中具有值。</span><span class="sxs-lookup"><span data-stu-id="3263f-274">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="3263f-275">连接到远程 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3263f-275">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="3263f-276">发出命令:</span><span class="sxs-lookup"><span data-stu-id="3263f-276">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="3263f-277">配置电话号码并启用企业语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="3263f-277">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="3263f-278">创建用户并分配许可证后, 下一步是配置其电话号码和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3263f-278">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="3263f-279">这可通过一个步骤完成。</span><span class="sxs-lookup"><span data-stu-id="3263f-279">This can be done in one step.</span></span> 

<span data-ttu-id="3263f-280">要为语音邮件添加电话号码和启用, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3263f-280">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="3263f-281">连接到远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="3263f-281">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="3263f-282">输入命令:</span><span class="sxs-lookup"><span data-stu-id="3263f-282">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="3263f-283">例如, 若要为用户 "Spencer Low" 添加电话号码, 请输入以下内容:</span><span class="sxs-lookup"><span data-stu-id="3263f-283">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="3263f-284">使用的电话号码必须配置为完整的 E-164 个国家/地区代码的电话号码。</span><span class="sxs-lookup"><span data-stu-id="3263f-284">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="3263f-285">如果用户的电话号码是在本地管理的, 请使用本地 Skype for Business Management Shell 或控制面板配置用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="3263f-285">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="3263f-286">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="3263f-286">Configure Voice Routing</span></span> 

<span data-ttu-id="3263f-287">Microsoft Phone 系统具有一种路由机制, 允许根据以下情况将呼叫发送到特定的 SBC:</span><span class="sxs-lookup"><span data-stu-id="3263f-287">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="3263f-288">名为 "号码模式"</span><span class="sxs-lookup"><span data-stu-id="3263f-288">Called number pattern</span></span> 
- <span data-ttu-id="3263f-289">称为 "号码模式 +" 的特定用户进行呼叫</span><span class="sxs-lookup"><span data-stu-id="3263f-289">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="3263f-290">SBCs 可以指定为 "活动" 和 "备份"。</span><span class="sxs-lookup"><span data-stu-id="3263f-290">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="3263f-291">这意味着当为此号码模式或数字模式 + 特定用户配置为活动的 SBC 不可用时, 呼叫将路由到 backup SBC。</span><span class="sxs-lookup"><span data-stu-id="3263f-291">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="3263f-292">呼叫路由由以下元素组成:</span><span class="sxs-lookup"><span data-stu-id="3263f-292">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="3263f-293">语音路由策略-PSTN 使用的容器;可以分配给用户或多个用户</span><span class="sxs-lookup"><span data-stu-id="3263f-293">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="3263f-294">PSTN 用法–用于语音路由和 PSTN 使用的容器;可以在不同的语音路由策略中共享</span><span class="sxs-lookup"><span data-stu-id="3263f-294">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="3263f-295">语音路由-用于呼叫与模式匹配的呼叫的数字模式和联机 PSTN 网关集</span><span class="sxs-lookup"><span data-stu-id="3263f-295">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="3263f-296">联机 PSTN 网关-指向 SBC 的指针还存储通过 SBC 发出调用时应用的配置, 例如, 前 P 声明的身份 (PAI) 或首选编解码器;可以添加到语音路由</span><span class="sxs-lookup"><span data-stu-id="3263f-296">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="3263f-297">创建具有一种 PSTN 使用的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="3263f-297">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="3263f-298">下图显示了呼叫流中的语音路由策略的两个示例。</span><span class="sxs-lookup"><span data-stu-id="3263f-298">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="3263f-299">**呼叫流 1 (在左侧):** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx, 则该呼叫将路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="3263f-299">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="3263f-300">如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都不可用, 则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="3263f-300">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="3263f-301">**呼叫流程 2 (右侧):** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx, 则该调用首先路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="3263f-301">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="3263f-302">如果两个 SBC 均不可用, 将尝试具有较低优先级的路由 (sbc3.contoso.biz 和 sbc4.contoso.biz)。</span><span class="sxs-lookup"><span data-stu-id="3263f-302">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="3263f-303">如果没有 SBCs 可用, 将丢弃呼叫。</span><span class="sxs-lookup"><span data-stu-id="3263f-303">If none of the SBCs are available, the call is dropped.</span></span> 

![显示语音路由策略示例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="3263f-305">在这两个示例中, 虽然为语音路由分配了优先级, 但路由中的 SBCs 按随机顺序尝试。</span><span class="sxs-lookup"><span data-stu-id="3263f-305">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3263f-306">除非用户也有 Microsoft 通话计划许可证, 否则将删除示例配置中除与模式 + 1 425 XXX xx xx 或 + 1 206 XXX xx 之间的任何号码。</span><span class="sxs-lookup"><span data-stu-id="3263f-306">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="3263f-307">如果用户有呼叫计划许可证, 则会根据 Microsoft 通话计划的政策自动路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="3263f-307">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="3263f-308">Microsoft 通话计划将自动应用为具有 Microsoft 呼叫计划许可证的所有用户的最后一个路由, 并且不需要其他呼叫路由配置。</span><span class="sxs-lookup"><span data-stu-id="3263f-308">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="3263f-309">在下图所示的示例中, 添加了一个语音路由, 用于向所有其他美国和加拿大号码 (转到 "号码模式 + 1 XXX XXX xx xx" 呼叫) 发送呼叫。</span><span class="sxs-lookup"><span data-stu-id="3263f-309">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![显示具有第三个路线的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="3263f-311">对于所有其他呼叫, 如果用户同时具有两个许可证 (Microsoft Phone System 和 Microsoft 通话计划), 则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="3263f-311">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="3263f-312">如果没有与管理员创建的在线语音路线中的数字模式匹配, 请通过 Microsoft 通话计划进行路由。</span><span class="sxs-lookup"><span data-stu-id="3263f-312">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="3263f-313">如果用户仅有 Microsoft Phone 系统, 则呼叫将被丢弃, 因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="3263f-313">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3263f-314">在这种情况下, 路由 "其他 + 1" 的优先级值不重要, 因为只有一个路由与模式 + 1 XXX XXX xx 相匹配。</span><span class="sxs-lookup"><span data-stu-id="3263f-314">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="3263f-315">如果用户拨打 + 1 324 567 89 89 且 sbc5.contoso.biz 和 sbc6.contoso.biz 都不可用, 则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="3263f-315">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="3263f-316">下表总结了使用三个语音路由的配置。</span><span class="sxs-lookup"><span data-stu-id="3263f-316">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="3263f-317">在此示例中, 所有三个路由都属于同一 PSTN 使用 "美国和加拿大"。</span><span class="sxs-lookup"><span data-stu-id="3263f-317">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="3263f-318">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="3263f-318">**PSTN usage**</span></span>|<span data-ttu-id="3263f-319">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="3263f-319">**Voice route**</span></span>|<span data-ttu-id="3263f-320">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="3263f-320">**Number pattern**</span></span>|<span data-ttu-id="3263f-321">**优先级**</span><span class="sxs-lookup"><span data-stu-id="3263f-321">**Priority**</span></span>|<span data-ttu-id="3263f-322">**SBC**</span><span class="sxs-lookup"><span data-stu-id="3263f-322">**SBC**</span></span>|<span data-ttu-id="3263f-323">**说明**</span><span class="sxs-lookup"><span data-stu-id="3263f-323">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3263f-324">仅限美国</span><span class="sxs-lookup"><span data-stu-id="3263f-324">US only</span></span>|<span data-ttu-id="3263f-325">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="3263f-325">"Redmond 1"</span></span>|<span data-ttu-id="3263f-326">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="3263f-326">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="3263f-327">1</span><span class="sxs-lookup"><span data-stu-id="3263f-327">1</span></span>|<span data-ttu-id="3263f-328">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-328">sbc1.contoso.biz</span></span><br/><span data-ttu-id="3263f-329">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-329">sbc2.contoso.biz</span></span>|<span data-ttu-id="3263f-330">拨打的号码的活动路线 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="3263f-330">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="3263f-331">仅限美国</span><span class="sxs-lookup"><span data-stu-id="3263f-331">US only</span></span>|<span data-ttu-id="3263f-332">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="3263f-332">"Redmond 2"</span></span>|<span data-ttu-id="3263f-333">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="3263f-333">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="3263f-334">2</span><span class="sxs-lookup"><span data-stu-id="3263f-334">2</span></span>|<span data-ttu-id="3263f-335">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-335">sbc3.contoso.biz</span></span><br/><span data-ttu-id="3263f-336">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-336">sbc4.contoso.biz</span></span>|<span data-ttu-id="3263f-337">已呼叫号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="3263f-337">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="3263f-338">仅限美国</span><span class="sxs-lookup"><span data-stu-id="3263f-338">US only</span></span>|<span data-ttu-id="3263f-339">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="3263f-339">"Other +1"</span></span>|<span data-ttu-id="3263f-340">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="3263f-340">^\\+1(\d{10})$</span></span>|<span data-ttu-id="3263f-341">3</span><span class="sxs-lookup"><span data-stu-id="3263f-341">3</span></span>|<span data-ttu-id="3263f-342">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-342">sbc5.contoso.biz</span></span><br/><span data-ttu-id="3263f-343">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-343">sbc6.contoso.biz</span></span>|<span data-ttu-id="3263f-344">呼叫号码 + 1 XXX XXX xx (除 + 1 425 XXX xx 或 + 1 206 XXX xx 之间) 的路由</span><span class="sxs-lookup"><span data-stu-id="3263f-344">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="3263f-345">所有路线均与 PSTN 使用 "美国和加拿大" 相关联, PSTN 使用与 "仅美国" 的语音路由策略相关联。</span><span class="sxs-lookup"><span data-stu-id="3263f-345">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="3263f-346">在此示例中, 语音路由策略分配给用户 Spencer Low。</span><span class="sxs-lookup"><span data-stu-id="3263f-346">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="3263f-347">呼叫路线示例</span><span class="sxs-lookup"><span data-stu-id="3263f-347">Examples of call routes</span></span>

<span data-ttu-id="3263f-348">在以下示例中, 我们将演示如何配置路由、PSTN 使用情况和路由策略, 并为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="3263f-348">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="3263f-349">**步骤 1:** 创建 PSTN 使用 "美国和加拿大"。</span><span class="sxs-lookup"><span data-stu-id="3263f-349">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="3263f-350">在 Skype for business 远程 PowerShell 会话中, 键入:</span><span class="sxs-lookup"><span data-stu-id="3263f-350">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="3263f-351">通过输入以下内容验证是否已创建使用:</span><span class="sxs-lookup"><span data-stu-id="3263f-351">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="3263f-352">这将返回可能被截断的名称的列表:</span><span class="sxs-lookup"><span data-stu-id="3263f-352">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="3263f-353">在下面的示例中, 你可以查看运行 PowerShell 命令`(Get-CSOnlinePSTNUsage).usage`的结果以显示完整名称 (未截断)。</span><span class="sxs-lookup"><span data-stu-id="3263f-353">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="3263f-354">**步骤 2:** 在 Skype for Business Online 的 PowerShell 会话中, 创建三个路线: 雷德蒙1、雷德蒙2和其他 + 1, 如上表中所述。</span><span class="sxs-lookup"><span data-stu-id="3263f-354">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="3263f-355">要创建 "Redmond 1" 路线, 请输入:</span><span class="sxs-lookup"><span data-stu-id="3263f-355">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="3263f-356">返回:</span><span class="sxs-lookup"><span data-stu-id="3263f-356">Which returns:</span></span>
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
<span data-ttu-id="3263f-357">若要创建雷德蒙2路线, 请输入:</span><span class="sxs-lookup"><span data-stu-id="3263f-357">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="3263f-358">若要创建其他 + 1 路线, 请输入:</span><span class="sxs-lookup"><span data-stu-id="3263f-358">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="3263f-359">请确保 NumberPattern 属性中的正则表达式是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="3263f-359">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="3263f-360">你可以使用此网站对其进行测试:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="3263f-360">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="3263f-361">在某些情况下, 需要将所有调用路由到同一 SBC;请使用-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="3263f-361">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="3263f-362">将所有呼叫路由到同一 SBC</span><span class="sxs-lookup"><span data-stu-id="3263f-362">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="3263f-363">通过使用如下所示的选项运行`Get-CSOnlineVoiceRoute` PowerShell 命令验证是否已正确配置路由:</span><span class="sxs-lookup"><span data-stu-id="3263f-363">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="3263f-364">应返回:</span><span class="sxs-lookup"><span data-stu-id="3263f-364">Which should return:</span></span>
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

<span data-ttu-id="3263f-365">在此示例中, 自动为 "其他 + 1" 路由分配优先级4。</span><span class="sxs-lookup"><span data-stu-id="3263f-365">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="3263f-366">**步骤 3:** 创建语音路由策略 "仅美国", 并将 PSTN 使用 "美国和加拿大" 添加到该策略。</span><span class="sxs-lookup"><span data-stu-id="3263f-366">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="3263f-367">在 Skype for Business Online 的 PowerShell 会话中, 键入:</span><span class="sxs-lookup"><span data-stu-id="3263f-367">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="3263f-368">此示例中显示了结果:</span><span class="sxs-lookup"><span data-stu-id="3263f-368">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="3263f-369">**步骤 4:** 使用 PowerShell 向用户授予 Spencer 低的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="3263f-369">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="3263f-370">在 Skype for Business Online 的 PowerShell 会话中, 键入:</span><span class="sxs-lookup"><span data-stu-id="3263f-370">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="3263f-371">通过输入以下命令验证策略分配:</span><span class="sxs-lookup"><span data-stu-id="3263f-371">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="3263f-372">返回:</span><span class="sxs-lookup"><span data-stu-id="3263f-372">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="3263f-373">创建具有多个 PSTN 用法的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="3263f-373">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="3263f-374">以前创建的语音路由策略仅允许拨打美国和加拿大的电话号码, 除非还为用户分配了 Microsoft 通话计划许可证。</span><span class="sxs-lookup"><span data-stu-id="3263f-374">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="3263f-375">在下面的示例中, 您可以创建语音路由策略 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="3263f-375">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="3263f-376">该策略重用在上一个示例中创建的 PSTN 使用 "美国和加拿大", 以及新的 PSTN 使用 "国际"。</span><span class="sxs-lookup"><span data-stu-id="3263f-376">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="3263f-377">这会将所有其他调用路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="3263f-377">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="3263f-378">显示的示例将 "仅美国" 策略分配给用户 "Spencer Low", 不限制用户 "John"。</span><span class="sxs-lookup"><span data-stu-id="3263f-378">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="3263f-379">Spencer 低–只允许拨打美国和加拿大号码的电话。</span><span class="sxs-lookup"><span data-stu-id="3263f-379">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="3263f-380">当呼叫雷德蒙数字范围时, 必须使用一组特定的 SBC。</span><span class="sxs-lookup"><span data-stu-id="3263f-380">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="3263f-381">除非向用户分配了通话计划许可证, 否则不会路由非美国号码。</span><span class="sxs-lookup"><span data-stu-id="3263f-381">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="3263f-382">John 的一对电话-允许拨打任何号码的电话。</span><span class="sxs-lookup"><span data-stu-id="3263f-382">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="3263f-383">当呼叫雷德蒙数字范围时, 必须使用一组特定的 SBC。</span><span class="sxs-lookup"><span data-stu-id="3263f-383">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="3263f-384">非 US 数字将通过 sbc2.contoso.biz 和 sbc5.contoso.biz 进行路由。</span><span class="sxs-lookup"><span data-stu-id="3263f-384">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![显示分配给用户 Spencer 低的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="3263f-386">对于所有其他呼叫, 如果用户同时具有两个许可证 (Microsoft Phone System 和 Microsoft 通话计划), 则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="3263f-386">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="3263f-387">如果没有与管理员创建的在线语音路线中的数字模式匹配, 请通过 Microsoft 通话计划进行路由。</span><span class="sxs-lookup"><span data-stu-id="3263f-387">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="3263f-388">如果用户仅有 Microsoft Phone 系统, 则呼叫将被丢弃, 因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="3263f-388">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![显示分配给用户 John 的的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="3263f-390">下表总结了路由策略 "无限制" 的用法标识和语音路由。</span><span class="sxs-lookup"><span data-stu-id="3263f-390">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="3263f-391">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="3263f-391">**PSTN usage**</span></span>|<span data-ttu-id="3263f-392">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="3263f-392">**Voice route**</span></span>|<span data-ttu-id="3263f-393">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="3263f-393">**Number pattern**</span></span>|<span data-ttu-id="3263f-394">**优先级**</span><span class="sxs-lookup"><span data-stu-id="3263f-394">**Priority**</span></span>|<span data-ttu-id="3263f-395">**SBC**</span><span class="sxs-lookup"><span data-stu-id="3263f-395">**SBC**</span></span>|<span data-ttu-id="3263f-396">**说明**</span><span class="sxs-lookup"><span data-stu-id="3263f-396">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3263f-397">仅限美国</span><span class="sxs-lookup"><span data-stu-id="3263f-397">US Only</span></span>|<span data-ttu-id="3263f-398">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="3263f-398">"Redmond 1"</span></span>|<span data-ttu-id="3263f-399">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="3263f-399">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="3263f-400">1</span><span class="sxs-lookup"><span data-stu-id="3263f-400">1</span></span>|<span data-ttu-id="3263f-401">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-401">sbc1.contoso.biz</span></span><br/><span data-ttu-id="3263f-402">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-402">sbc2.contoso.biz</span></span>|<span data-ttu-id="3263f-403">被呼叫方号码的活动路由 + 1 425 XXX XX XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="3263f-403">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="3263f-404">仅限美国</span><span class="sxs-lookup"><span data-stu-id="3263f-404">US Only</span></span>|<span data-ttu-id="3263f-405">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="3263f-405">"Redmond 2"</span></span>|<span data-ttu-id="3263f-406">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="3263f-406">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="3263f-407">2</span><span class="sxs-lookup"><span data-stu-id="3263f-407">2</span></span>|<span data-ttu-id="3263f-408">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-408">sbc3.contoso.biz</span></span><br/><span data-ttu-id="3263f-409">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-409">sbc4.contoso.biz</span></span>|<span data-ttu-id="3263f-410">被呼叫方号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="3263f-410">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="3263f-411">仅限美国</span><span class="sxs-lookup"><span data-stu-id="3263f-411">US Only</span></span>|<span data-ttu-id="3263f-412">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="3263f-412">"Other +1"</span></span>|<span data-ttu-id="3263f-413">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="3263f-413">^\\+1(\d{10})$</span></span>|<span data-ttu-id="3263f-414">3</span><span class="sxs-lookup"><span data-stu-id="3263f-414">3</span></span>|<span data-ttu-id="3263f-415">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-415">sbc5.contoso.biz</span></span><br/><span data-ttu-id="3263f-416">sbc6> contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-416">sbc6>.contoso.biz</span></span>|<span data-ttu-id="3263f-417">被呼叫方号码的路由 + 1 XXX XXX xx (除 + 1 425 XXX xx 或 + 1 206 XXX xx)</span><span class="sxs-lookup"><span data-stu-id="3263f-417">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="3263f-418">International</span><span class="sxs-lookup"><span data-stu-id="3263f-418">International</span></span>|<span data-ttu-id="3263f-419">International</span><span class="sxs-lookup"><span data-stu-id="3263f-419">International</span></span>|<span data-ttu-id="3263f-420">\d +</span><span class="sxs-lookup"><span data-stu-id="3263f-420">\d+</span></span>|<span data-ttu-id="3263f-421">4</span><span class="sxs-lookup"><span data-stu-id="3263f-421">4</span></span>|<span data-ttu-id="3263f-422">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-422">sbc2.contoso.biz</span></span><br/><span data-ttu-id="3263f-423">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="3263f-423">sbc5.contoso.biz</span></span>|<span data-ttu-id="3263f-424">任何数字模式的路由</span><span class="sxs-lookup"><span data-stu-id="3263f-424">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="3263f-425">语音路由策略中的 PSTN 用法的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="3263f-425">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="3263f-426">使用实例按顺序应用, 如果在第一次使用中发现匹配项, 则从不计算其他用法。</span><span class="sxs-lookup"><span data-stu-id="3263f-426">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="3263f-427">PSTN 使用 "国际" 必须放置在 PSTN 使用 "仅限美国" 之后。</span><span class="sxs-lookup"><span data-stu-id="3263f-427">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="3263f-428">若要更改 PSTN 用法的顺序, 请运行`Set-CSOnlineVoiceRoutingPolicy`命令。</span><span class="sxs-lookup"><span data-stu-id="3263f-428">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="3263f-429">例如, 若要将订单从 "美国和加拿大" 的第一个和 "国际" 的订单更改为反向顺序, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3263f-429">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="3263f-430">将自动分配 "其他 + 1" 和 "国际" 语音路由的优先级。</span><span class="sxs-lookup"><span data-stu-id="3263f-430">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="3263f-431">它们的优先级与 "Redmond 1" 和 "雷德蒙 2" 相比, 不是很重要。</span><span class="sxs-lookup"><span data-stu-id="3263f-431">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="3263f-432">用户 John 的 "语音路由策略" 的示例</span><span class="sxs-lookup"><span data-stu-id="3263f-432">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="3263f-433">创建 PSTN 使用 "国际"、语音路由 "国际"、"语音路由策略" 无限制, 然后将其分配给用户 "John (John)" 的步骤如下所示。</span><span class="sxs-lookup"><span data-stu-id="3263f-433">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="3263f-434">首先, 创建 PSTN 使用 "国际"。</span><span class="sxs-lookup"><span data-stu-id="3263f-434">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="3263f-435">在 Skype for Business Online 中的远程 PowerShell 会话中, 输入:</span><span class="sxs-lookup"><span data-stu-id="3263f-435">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="3263f-436">接下来, 创建新的语音路线 "国际"。</span><span class="sxs-lookup"><span data-stu-id="3263f-436">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="3263f-437">返回:</span><span class="sxs-lookup"><span data-stu-id="3263f-437">Which returns:</span></span>

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
3. <span data-ttu-id="3263f-438">接下来, 创建语音路由策略 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="3263f-438">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="3263f-439">PSTN 使用 "Redmond 1" 和 "Redmond" 在此语音路由策略中重复使用, 以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理, 作为本地或本地呼叫。</span><span class="sxs-lookup"><span data-stu-id="3263f-439">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="3263f-440">返回的</span><span class="sxs-lookup"><span data-stu-id="3263f-440">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="3263f-441">使用以下命令将语音路由策略分配给用户 "John 的工作"。</span><span class="sxs-lookup"><span data-stu-id="3263f-441">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="3263f-442">然后使用以下命令验证作业:</span><span class="sxs-lookup"><span data-stu-id="3263f-442">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="3263f-443">返回:</span><span class="sxs-lookup"><span data-stu-id="3263f-443">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="3263f-444">结果是, 应用到 John 54777 的语音政策不受限制, 并且将遵循可用于美国、加拿大和国际通话的呼叫路线逻辑。</span><span class="sxs-lookup"><span data-stu-id="3263f-444">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="3263f-445">将 Microsoft 团队设置为用户的首选调用客户端</span><span class="sxs-lookup"><span data-stu-id="3263f-445">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="3263f-446">"直接路由" 仅当用户使用团队客户端时, 才路由与他们的通话。</span><span class="sxs-lookup"><span data-stu-id="3263f-446">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="3263f-447">如果你的组织仅使用团队, 建议在升级策略中设置 "仅团队" 模式。</span><span class="sxs-lookup"><span data-stu-id="3263f-447">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="3263f-448">如果你的组织使用 Skype for business 服务器或 Skype for business Online, 请参阅以下文章了解详细信息, 然后选择相应选项:[了解 Skype for business 和团队的共存和升级旅程](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="3263f-448">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="3263f-449">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3263f-449">See also</span></span>

[<span data-ttu-id="3263f-450">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="3263f-450">Plan Direct Routing</span></span>](direct-routing-plan.md)
