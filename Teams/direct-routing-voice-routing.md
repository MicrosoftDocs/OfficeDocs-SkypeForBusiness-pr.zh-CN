---
title: 为直接路由配置语音路由
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
description: 了解如何通过 Microsoft Phone 系统直接路由配置语音路由。
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157934"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="cd75e-103">为直接路由配置语音路由</span><span class="sxs-lookup"><span data-stu-id="cd75e-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="cd75e-104">本文介绍如何为手机系统直接路由配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="cd75e-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="cd75e-105">这是用于配置直接路由的以下步骤的步骤3：</span><span class="sxs-lookup"><span data-stu-id="cd75e-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="cd75e-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="cd75e-106">Step 1.</span></span> [<span data-ttu-id="cd75e-107">将 SBC 连接到 Microsoft Phone 系统并验证连接</span><span class="sxs-lookup"><span data-stu-id="cd75e-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="cd75e-108">第 2 步</span><span class="sxs-lookup"><span data-stu-id="cd75e-108">Step 2.</span></span> [<span data-ttu-id="cd75e-109">为用户启用直接路由、语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="cd75e-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)    
- <span data-ttu-id="cd75e-110">**步骤3。配置语音路由**（本文）</span><span class="sxs-lookup"><span data-stu-id="cd75e-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="cd75e-111">第 4 步</span><span class="sxs-lookup"><span data-stu-id="cd75e-111">Step 4.</span></span> [<span data-ttu-id="cd75e-112">将数字转换为备用格式</span><span class="sxs-lookup"><span data-stu-id="cd75e-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="cd75e-113">有关设置直接路由所需的所有步骤的信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="cd75e-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="cd75e-114">语音路由概述</span><span class="sxs-lookup"><span data-stu-id="cd75e-114">Voice routing overview</span></span>

<span data-ttu-id="cd75e-115">Microsoft Phone 系统具有一种路由机制，允许将呼叫发送到特定的会话边界控制器（SBC），具体取决于：</span><span class="sxs-lookup"><span data-stu-id="cd75e-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="cd75e-116">被叫号码模式</span><span class="sxs-lookup"><span data-stu-id="cd75e-116">The called number pattern</span></span> 
- <span data-ttu-id="cd75e-117">被叫号码模式和进行呼叫的特定用户</span><span class="sxs-lookup"><span data-stu-id="cd75e-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="cd75e-118">SBCs 可以指定为 "活动" 和 "备份"。</span><span class="sxs-lookup"><span data-stu-id="cd75e-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="cd75e-119">当配置为活动的 SBC 不能用于特定呼叫路由时，该呼叫将路由到 backup SBC。</span><span class="sxs-lookup"><span data-stu-id="cd75e-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="cd75e-120">语音路由由以下元素组成：</span><span class="sxs-lookup"><span data-stu-id="cd75e-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="cd75e-121">**语音路由策略**-PSTN 使用的容器，可分配给用户或多个用户。</span><span class="sxs-lookup"><span data-stu-id="cd75e-121">**Voice routing policy** – A container for PSTN Usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="cd75e-122">**PSTN 用法**-用于语音路由和 PSTN 用途的容器，可在不同的语音路由策略中共享。</span><span class="sxs-lookup"><span data-stu-id="cd75e-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="cd75e-123">**语音路由**-一种数字模式和一组联机 PSTN 网关，用于呼叫号码匹配模式的呼叫。</span><span class="sxs-lookup"><span data-stu-id="cd75e-123">**Voice Routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="cd75e-124">**联机 PSTN 网关**-指向 sbc 的指针，该指针还存储通过 SBC 放置调用时应用的配置，例如，前 P 声明的身份（PAI）或首选编解码器;可添加到语音路由。</span><span class="sxs-lookup"><span data-stu-id="cd75e-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="cd75e-125">示例1：使用一个 PSTN 使用的语音路由</span><span class="sxs-lookup"><span data-stu-id="cd75e-125">Example 1: Voice routing with one PSTN Usage</span></span>

<span data-ttu-id="cd75e-126">下图显示了一个呼叫流中的语音路由策略的两个示例。</span><span class="sxs-lookup"><span data-stu-id="cd75e-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="cd75e-127">**呼叫流1（在左侧）：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该呼叫将路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="cd75e-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="cd75e-128">如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都不可用，则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="cd75e-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="cd75e-129">**呼叫流程2（右侧）：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该调用首先路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="cd75e-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="cd75e-130">如果两个 SBC 均不可用，将尝试具有较低优先级的路由（sbc3.contoso.biz 和 sbc4.contoso.biz）。</span><span class="sxs-lookup"><span data-stu-id="cd75e-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="cd75e-131">如果没有 SBCs 可用，将丢弃呼叫。</span><span class="sxs-lookup"><span data-stu-id="cd75e-131">If none of the SBCs are available, the call is dropped.</span></span> 

![显示语音路由策略示例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="cd75e-133">在这两个示例中，虽然为语音路由分配了优先级，但路由中的 SBCs 按随机顺序尝试。</span><span class="sxs-lookup"><span data-stu-id="cd75e-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cd75e-134">除非用户也有 Microsoft 通话计划许可证，否则将删除示例配置中除与模式 + 1 425 XXX xx xx 或 + 1 206 XXX xx 之间的任何号码。</span><span class="sxs-lookup"><span data-stu-id="cd75e-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="cd75e-135">如果用户有呼叫计划许可证，则会根据 Microsoft 通话计划的政策自动路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="cd75e-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="cd75e-136">Microsoft 通话计划将自动应用为具有 Microsoft 呼叫计划许可证的所有用户的最后一个路由，并且不需要其他呼叫路由配置。</span><span class="sxs-lookup"><span data-stu-id="cd75e-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="cd75e-137">在下图所示的示例中，添加了一个语音路由，用于向所有美国和加拿大的号码（拨叫号码模式 + 1 XXX XXX xx）发送呼叫。</span><span class="sxs-lookup"><span data-stu-id="cd75e-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![显示具有第三个路线的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="cd75e-139">对于所有其他呼叫：</span><span class="sxs-lookup"><span data-stu-id="cd75e-139">For all other calls:</span></span>

- <span data-ttu-id="cd75e-140">如果用户同时具有两个许可证（Microsoft Phone System 和 Microsoft 通话计划），则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="cd75e-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="cd75e-141">如果没有与管理员创建的在线语音路线中的数字模式匹配的内容，则呼叫将通过 Microsoft 通话计划进行路由。</span><span class="sxs-lookup"><span data-stu-id="cd75e-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="cd75e-142">如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="cd75e-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cd75e-143">在此情况下，路由 "其他 + 1" 的优先级值不重要，因为只有一条路线与模式 + 1 XXX XXX xx 相匹配。</span><span class="sxs-lookup"><span data-stu-id="cd75e-143">The Priority value for route "Other +1" doesn’t matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="cd75e-144">如果用户拨打 + 1 324 567 89 89 且 sbc5.contoso.biz 和 sbc6.contoso.biz 都不可用，则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="cd75e-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="cd75e-145">下表总结了使用三个语音路由的配置。</span><span class="sxs-lookup"><span data-stu-id="cd75e-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="cd75e-146">在此示例中，所有三个路由都属于同一 PSTN 使用 "美国和加拿大"。</span><span class="sxs-lookup"><span data-stu-id="cd75e-146">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>  <span data-ttu-id="cd75e-147">所有路线均与 PSTN 使用 "美国和加拿大" 相关联，PSTN 使用与 "仅美国" 的语音路由策略相关联。</span><span class="sxs-lookup"><span data-stu-id="cd75e-147">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> 

|<span data-ttu-id="cd75e-148">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="cd75e-148">**PSTN usage**</span></span>|<span data-ttu-id="cd75e-149">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="cd75e-149">**Voice route**</span></span>|<span data-ttu-id="cd75e-150">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="cd75e-150">**Number pattern**</span></span>|<span data-ttu-id="cd75e-151">**优先级**</span><span class="sxs-lookup"><span data-stu-id="cd75e-151">**Priority**</span></span>|<span data-ttu-id="cd75e-152">**SBC**</span><span class="sxs-lookup"><span data-stu-id="cd75e-152">**SBC**</span></span>|<span data-ttu-id="cd75e-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="cd75e-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cd75e-154">仅限美国</span><span class="sxs-lookup"><span data-stu-id="cd75e-154">US only</span></span>|<span data-ttu-id="cd75e-155">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="cd75e-155">"Redmond 1"</span></span>|<span data-ttu-id="cd75e-156">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="cd75e-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cd75e-157">1</span><span class="sxs-lookup"><span data-stu-id="cd75e-157">1</span></span>|<span data-ttu-id="cd75e-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="cd75e-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="cd75e-160">拨打的号码的活动路线 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="cd75e-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cd75e-161">仅限美国</span><span class="sxs-lookup"><span data-stu-id="cd75e-161">US only</span></span>|<span data-ttu-id="cd75e-162">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="cd75e-162">"Redmond 2"</span></span>|<span data-ttu-id="cd75e-163">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="cd75e-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cd75e-164">ppls-2</span><span class="sxs-lookup"><span data-stu-id="cd75e-164">2</span></span>|<span data-ttu-id="cd75e-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="cd75e-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="cd75e-167">已呼叫号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="cd75e-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cd75e-168">仅限美国</span><span class="sxs-lookup"><span data-stu-id="cd75e-168">US only</span></span>|<span data-ttu-id="cd75e-169">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="cd75e-169">"Other +1"</span></span>|<span data-ttu-id="cd75e-170">^\\+ 1 （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="cd75e-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="cd75e-171">3</span><span class="sxs-lookup"><span data-stu-id="cd75e-171">3</span></span>|<span data-ttu-id="cd75e-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="cd75e-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="cd75e-174">呼叫号码 + 1 XXX XXX xx （除 + 1 425 XXX xx 或 + 1 206 XXX xx 之间）的路由</span><span class="sxs-lookup"><span data-stu-id="cd75e-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||


### <a name="example-1-configuration-steps"></a><span data-ttu-id="cd75e-175">示例1：配置步骤</span><span class="sxs-lookup"><span data-stu-id="cd75e-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="cd75e-176">以下示例显示了如何：</span><span class="sxs-lookup"><span data-stu-id="cd75e-176">The following example shows how to:</span></span>

- <span data-ttu-id="cd75e-177">创建单 PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="cd75e-177">Create a single PSTN Usage</span></span> 
- <span data-ttu-id="cd75e-178">配置三个语音路由</span><span class="sxs-lookup"><span data-stu-id="cd75e-178">Configure three voice routes</span></span>
- <span data-ttu-id="cd75e-179">创建语音路由策略</span><span class="sxs-lookup"><span data-stu-id="cd75e-179">Create a voice routing policy</span></span>
- <span data-ttu-id="cd75e-180">将策略分配给用户 Spencer 低</span><span class="sxs-lookup"><span data-stu-id="cd75e-180">Assign the policy to user Spencer Low</span></span>

<span data-ttu-id="cd75e-181">**步骤1：** 创建 PSTN 使用 "美国和加拿大"</span><span class="sxs-lookup"><span data-stu-id="cd75e-181">**Step 1:** Create the PSTN Usage "US and Canada"</span></span>

<span data-ttu-id="cd75e-182">在 Skype for business 远程 PowerShell 会话中，键入：</span><span class="sxs-lookup"><span data-stu-id="cd75e-182">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="cd75e-183">通过输入以下内容验证是否已创建使用：</span><span class="sxs-lookup"><span data-stu-id="cd75e-183">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="cd75e-184">这将返回可能被截断的名称的列表：</span><span class="sxs-lookup"><span data-stu-id="cd75e-184">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="cd75e-185">下面的示例显示运行 PowerShell 命令`(Get-CSOnlinePSTNUsage).usage`以显示全名（未截断）的结果：</span><span class="sxs-lookup"><span data-stu-id="cd75e-185">The example below shows the result of  running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated):</span></span>

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

<span data-ttu-id="cd75e-186">**步骤2：** 在 Skype for Business Online 的 PowerShell 会话中，创建三个路线： Redmond 1、Redmond 2 和其他 + 1，如上表所示</span><span class="sxs-lookup"><span data-stu-id="cd75e-186">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as shown in the previous table</span></span>

<span data-ttu-id="cd75e-187">要创建 "Redmond 1" 路线，请输入：</span><span class="sxs-lookup"><span data-stu-id="cd75e-187">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cd75e-188">返回：</span><span class="sxs-lookup"><span data-stu-id="cd75e-188">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="cd75e-189">若要创建雷德蒙2路线，请输入：</span><span class="sxs-lookup"><span data-stu-id="cd75e-189">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cd75e-190">若要创建其他 + 1 路线，请输入：</span><span class="sxs-lookup"><span data-stu-id="cd75e-190">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="cd75e-191">请确保 NumberPattern 属性中的正则表达式是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="cd75e-191">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="cd75e-192">你可以使用此网站对其进行测试：[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="cd75e-192">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="cd75e-193">在某些情况下，需要将所有调用路由到同一 SBC;使用-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="cd75e-193">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="cd75e-194">将所有呼叫路由到同一个 SBC。</span><span class="sxs-lookup"><span data-stu-id="cd75e-194">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="cd75e-195">通过使用如下所示的选项运行`Get-CSOnlineVoiceRoute` PowerShell 命令验证是否已正确配置路由：</span><span class="sxs-lookup"><span data-stu-id="cd75e-195">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="cd75e-196">应返回：</span><span class="sxs-lookup"><span data-stu-id="cd75e-196">Which should return:</span></span>
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

<span data-ttu-id="cd75e-197">在此示例中，自动为 "其他 + 1" 路由分配优先级4。</span><span class="sxs-lookup"><span data-stu-id="cd75e-197">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="cd75e-198">**步骤3：** 创建语音路由策略 "仅美国"，并将 PSTN 使用 "美国和加拿大" 添加到该策略。</span><span class="sxs-lookup"><span data-stu-id="cd75e-198">**Step 3:** Create a voice routing policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="cd75e-199">在 Skype for Business Online 的 PowerShell 会话中，键入：</span><span class="sxs-lookup"><span data-stu-id="cd75e-199">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cd75e-200">此示例中显示了结果：</span><span class="sxs-lookup"><span data-stu-id="cd75e-200">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="cd75e-201">**步骤4：** 通过使用 PowerShell，向用户授予 Spencer Low 的语音路由策略：</span><span class="sxs-lookup"><span data-stu-id="cd75e-201">**Step 4:** By using PowerShell, grant the voice routing policy to the user Spencer Low:</span></span>

<span data-ttu-id="cd75e-202">在 Skype for Business Online 的 PowerShell 会话中，键入：</span><span class="sxs-lookup"><span data-stu-id="cd75e-202">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="cd75e-203">通过输入以下命令验证策略分配：</span><span class="sxs-lookup"><span data-stu-id="cd75e-203">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="cd75e-204">该命令将返回以下内容：</span><span class="sxs-lookup"><span data-stu-id="cd75e-204">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="cd75e-205">示例2：具有多个 PSTN 用法的语音路由</span><span class="sxs-lookup"><span data-stu-id="cd75e-205">Example 2: Voice routing with multiple PSTN Usages</span></span>

<span data-ttu-id="cd75e-206">在示例1中创建的 "语音路由策略" 仅允许拨打美国和加拿大的电话号码，除非还为用户分配了 Microsoft 通话计划许可证。</span><span class="sxs-lookup"><span data-stu-id="cd75e-206">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="cd75e-207">在下面的示例中，您可以创建语音路由策略 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="cd75e-207">In the example that follows, you can create the voice routing policy "No Restrictions."</span></span> <span data-ttu-id="cd75e-208">该策略重用在示例1中创建的 PSTN 使用 "美国和加拿大"，以及新的 PSTN 使用 "国际"。</span><span class="sxs-lookup"><span data-stu-id="cd75e-208">The policy reuses the PSTN Usage "US and Canada" created in Example 1, as well as the new PSTN Usage "International."</span></span>  <span data-ttu-id="cd75e-209">此策略将所有其他调用路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="cd75e-209">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> 

<span data-ttu-id="cd75e-210">显示的示例将 "仅美国" 策略分配给用户 Spencer Low，将 "无限制" 策略分配给用户 John 的，以便按如下方式进行路由：</span><span class="sxs-lookup"><span data-stu-id="cd75e-210">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="cd75e-211">Spencer 低–美国的政策。</span><span class="sxs-lookup"><span data-stu-id="cd75e-211">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="cd75e-212">通话仅允许使用美国和加拿大号码。</span><span class="sxs-lookup"><span data-stu-id="cd75e-212">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="cd75e-213">当调用 Redmond 数字范围时，必须使用特定的 SBCs 集。</span><span class="sxs-lookup"><span data-stu-id="cd75e-213">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="cd75e-214">除非向用户分配了通话计划许可证，否则不会路由非美国号码。</span><span class="sxs-lookup"><span data-stu-id="cd75e-214">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="cd75e-215">John 的 54777-国际政策。</span><span class="sxs-lookup"><span data-stu-id="cd75e-215">John Woods – International policy.</span></span>  <span data-ttu-id="cd75e-216">任何号码都允许通话。</span><span class="sxs-lookup"><span data-stu-id="cd75e-216">Calls are allowed to any number.</span></span> <span data-ttu-id="cd75e-217">当调用 Redmond 数字范围时，必须使用特定的 SBCs 集。</span><span class="sxs-lookup"><span data-stu-id="cd75e-217">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="cd75e-218">非 US 数字将使用 sbc2.contoso.biz 和 sbc5.contoso.biz 进行路由。</span><span class="sxs-lookup"><span data-stu-id="cd75e-218">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![显示分配给用户 Spencer 低的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="cd75e-220">对于所有其他呼叫，如果用户同时具有两个许可证（Microsoft Phone System 和 Microsoft 通话计划），则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="cd75e-220">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="cd75e-221">如果没有与管理员创建的在线语音路线中的数字模式匹配的内容，则使用 Microsoft 通话计划路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="cd75e-221">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="cd75e-222">如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="cd75e-222">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![显示分配给用户 John 的的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="cd75e-224">下表总结了路由策略 "无限制" 的用法标识和语音路由。</span><span class="sxs-lookup"><span data-stu-id="cd75e-224">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="cd75e-225">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="cd75e-225">**PSTN usage**</span></span>|<span data-ttu-id="cd75e-226">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="cd75e-226">**Voice route**</span></span>|<span data-ttu-id="cd75e-227">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="cd75e-227">**Number pattern**</span></span>|<span data-ttu-id="cd75e-228">**优先级**</span><span class="sxs-lookup"><span data-stu-id="cd75e-228">**Priority**</span></span>|<span data-ttu-id="cd75e-229">**SBC**</span><span class="sxs-lookup"><span data-stu-id="cd75e-229">**SBC**</span></span>|<span data-ttu-id="cd75e-230">**说明**</span><span class="sxs-lookup"><span data-stu-id="cd75e-230">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cd75e-231">仅限美国</span><span class="sxs-lookup"><span data-stu-id="cd75e-231">US Only</span></span>|<span data-ttu-id="cd75e-232">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="cd75e-232">"Redmond 1"</span></span>|<span data-ttu-id="cd75e-233">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="cd75e-233">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cd75e-234">1</span><span class="sxs-lookup"><span data-stu-id="cd75e-234">1</span></span>|<span data-ttu-id="cd75e-235">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-235">sbc1.contoso.biz</span></span><br/><span data-ttu-id="cd75e-236">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-236">sbc2.contoso.biz</span></span>|<span data-ttu-id="cd75e-237">被呼叫方号码的活动路由 + 1 425 XXX XX XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="cd75e-237">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cd75e-238">仅限美国</span><span class="sxs-lookup"><span data-stu-id="cd75e-238">US Only</span></span>|<span data-ttu-id="cd75e-239">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="cd75e-239">"Redmond 2"</span></span>|<span data-ttu-id="cd75e-240">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="cd75e-240">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cd75e-241">ppls-2</span><span class="sxs-lookup"><span data-stu-id="cd75e-241">2</span></span>|<span data-ttu-id="cd75e-242">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-242">sbc3.contoso.biz</span></span><br/><span data-ttu-id="cd75e-243">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-243">sbc4.contoso.biz</span></span>|<span data-ttu-id="cd75e-244">被呼叫方号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="cd75e-244">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cd75e-245">仅限美国</span><span class="sxs-lookup"><span data-stu-id="cd75e-245">US Only</span></span>|<span data-ttu-id="cd75e-246">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="cd75e-246">"Other +1"</span></span>|<span data-ttu-id="cd75e-247">^\\+ 1 （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="cd75e-247">^\\+1(\d{10})$</span></span>|<span data-ttu-id="cd75e-248">3</span><span class="sxs-lookup"><span data-stu-id="cd75e-248">3</span></span>|<span data-ttu-id="cd75e-249">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-249">sbc5.contoso.biz</span></span><br/><span data-ttu-id="cd75e-250">sbc6> contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-250">sbc6>.contoso.biz</span></span>|<span data-ttu-id="cd75e-251">被呼叫方号码的路由 + 1 XXX XXX xx （除 + 1 425 XXX xx 或 + 1 206 XXX xx）</span><span class="sxs-lookup"><span data-stu-id="cd75e-251">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="cd75e-252">International</span><span class="sxs-lookup"><span data-stu-id="cd75e-252">International</span></span>|<span data-ttu-id="cd75e-253">International</span><span class="sxs-lookup"><span data-stu-id="cd75e-253">International</span></span>|<span data-ttu-id="cd75e-254">\d +</span><span class="sxs-lookup"><span data-stu-id="cd75e-254">\d+</span></span>|<span data-ttu-id="cd75e-255">4</span><span class="sxs-lookup"><span data-stu-id="cd75e-255">4</span></span>|<span data-ttu-id="cd75e-256">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-256">sbc2.contoso.biz</span></span><br/><span data-ttu-id="cd75e-257">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cd75e-257">sbc5.contoso.biz</span></span>|<span data-ttu-id="cd75e-258">任何数字模式的路由</span><span class="sxs-lookup"><span data-stu-id="cd75e-258">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="cd75e-259">语音路由策略中的 PSTN 用法的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="cd75e-259">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="cd75e-260">使用实例按顺序应用，如果在第一次使用中发现匹配项，则从不计算其他用法。</span><span class="sxs-lookup"><span data-stu-id="cd75e-260">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="cd75e-261">PSTN 使用 "国际" 必须放置在 PSTN 使用 "仅限美国" 之后。</span><span class="sxs-lookup"><span data-stu-id="cd75e-261">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="cd75e-262">若要更改 PSTN 用法的顺序，请运行`Set-CSOnlineVoiceRoutingPolicy`命令。</span><span class="sxs-lookup"><span data-stu-id="cd75e-262">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="cd75e-263">例如，若要将订单从 "美国和加拿大" 的第一个和 "国际" 的订单更改为反向顺序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cd75e-263">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="cd75e-264">将自动分配 "其他 + 1" 和 "国际" 语音路由的优先级。</span><span class="sxs-lookup"><span data-stu-id="cd75e-264">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="cd75e-265">它们的优先级与 "Redmond 1" 和 "雷德蒙 2" 相比，不是很重要。</span><span class="sxs-lookup"><span data-stu-id="cd75e-265">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>


### <a name="example-2-configuration-steps"></a><span data-ttu-id="cd75e-266">示例2：配置步骤</span><span class="sxs-lookup"><span data-stu-id="cd75e-266">Example 2: Configuration steps</span></span>

<span data-ttu-id="cd75e-267">以下示例显示了如何：</span><span class="sxs-lookup"><span data-stu-id="cd75e-267">The following example shows how to:</span></span>

- <span data-ttu-id="cd75e-268">创建名为国际的新 PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="cd75e-268">Create a new PSTN Usage called International</span></span>
- <span data-ttu-id="cd75e-269">创建名为 "国际" 的新语音路线</span><span class="sxs-lookup"><span data-stu-id="cd75e-269">Create a new voice route called International</span></span>
- <span data-ttu-id="cd75e-270">创建名为 "无限制" 的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="cd75e-270">Create a voice routing policy called No Restrictions</span></span>
- <span data-ttu-id="cd75e-271">将策略分配给用户 John 的一对用户</span><span class="sxs-lookup"><span data-stu-id="cd75e-271">Assign the policy to user John Woods</span></span>


<span data-ttu-id="cd75e-272">**步骤 1**：创建 PSTN 使用 "国际"。</span><span class="sxs-lookup"><span data-stu-id="cd75e-272">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="cd75e-273">在 Skype for Business Online 中的远程 PowerShell 会话中，输入：</span><span class="sxs-lookup"><span data-stu-id="cd75e-273">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="cd75e-274">**步骤 2**：创建新的语音路由 "国际"。</span><span class="sxs-lookup"><span data-stu-id="cd75e-274">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="cd75e-275">返回：</span><span class="sxs-lookup"><span data-stu-id="cd75e-275">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="cd75e-276">**步骤 3**：创建语音路由策略 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="cd75e-276">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="cd75e-277">PSTN 使用 "Redmond 1" 和 "Redmond" 在此语音路由策略中重复使用，以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理，作为本地或本地呼叫。</span><span class="sxs-lookup"><span data-stu-id="cd75e-277">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="cd75e-278">记下 PSTN 用法的顺序：</span><span class="sxs-lookup"><span data-stu-id="cd75e-278">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="cd75e-279">a.</span><span class="sxs-lookup"><span data-stu-id="cd75e-279">a.</span></span> <span data-ttu-id="cd75e-280">如果对数字 "+ 1 425 XXX XX XX" 的调用配置为以下示例中所示的使用实例，则呼叫将遵循 "美国和加拿大" 使用中设置的路由，并应用特殊路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="cd75e-280">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="cd75e-281">也就是说，将首先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由呼叫，然后 sbc3.contoso.biz 和 sbc4.contoso.biz 作为备份路由。</span><span class="sxs-lookup"><span data-stu-id="cd75e-281">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="cd75e-282">b.</span><span class="sxs-lookup"><span data-stu-id="cd75e-282">b.</span></span> <span data-ttu-id="cd75e-283">如果 "国际" PSTN 使用早于 "美国和加拿大"，则对 + 1 425 XXX xx 的调用将作为路由逻辑的一部分路由到 sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="cd75e-283">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="cd75e-284">输入命令：</span><span class="sxs-lookup"><span data-stu-id="cd75e-284">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="cd75e-285">返回：</span><span class="sxs-lookup"><span data-stu-id="cd75e-285">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="cd75e-286">**步骤 4**：使用以下命令将语音路由策略分配给用户 "John 的工作"。</span><span class="sxs-lookup"><span data-stu-id="cd75e-286">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="cd75e-287">然后使用以下命令验证作业：</span><span class="sxs-lookup"><span data-stu-id="cd75e-287">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="cd75e-288">返回：</span><span class="sxs-lookup"><span data-stu-id="cd75e-288">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="cd75e-289">结果是，应用到 John 54777 的语音政策不受限制，并且将遵循可用于美国、加拿大和国际通话的呼叫路线逻辑。</span><span class="sxs-lookup"><span data-stu-id="cd75e-289">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>



## <a name="see-also"></a><span data-ttu-id="cd75e-290">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd75e-290">See also</span></span>

[<span data-ttu-id="cd75e-291">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="cd75e-291">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="cd75e-292">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="cd75e-292">Configure Direct Routing</span></span>](direct-routing-configure.md)
