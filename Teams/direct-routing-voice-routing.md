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
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530989"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="44412-103">为直接路由配置语音路由</span><span class="sxs-lookup"><span data-stu-id="44412-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="44412-104">本文介绍如何为手机系统直接路由配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="44412-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="44412-105">这是用于配置直接路由的以下步骤的步骤3：</span><span class="sxs-lookup"><span data-stu-id="44412-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="44412-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="44412-106">Step 1.</span></span> [<span data-ttu-id="44412-107">将 SBC 连接到 Microsoft Phone 系统并验证连接</span><span class="sxs-lookup"><span data-stu-id="44412-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="44412-108">第 2 步</span><span class="sxs-lookup"><span data-stu-id="44412-108">Step 2.</span></span> [<span data-ttu-id="44412-109">为用户启用直接路由、语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="44412-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="44412-110">**步骤3。 (本文配置语音路由**) </span><span class="sxs-lookup"><span data-stu-id="44412-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="44412-111">第 4 步</span><span class="sxs-lookup"><span data-stu-id="44412-111">Step 4.</span></span> [<span data-ttu-id="44412-112">将数字转换为备用格式</span><span class="sxs-lookup"><span data-stu-id="44412-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="44412-113">有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="44412-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="44412-114">语音路由概述</span><span class="sxs-lookup"><span data-stu-id="44412-114">Voice routing overview</span></span>

<span data-ttu-id="44412-115">Microsoft Phone 系统具有一种路由机制，可用于将呼叫发送到特定的会话边界控制器 (SBC) ，具体取决于：</span><span class="sxs-lookup"><span data-stu-id="44412-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="44412-116">被叫号码模式</span><span class="sxs-lookup"><span data-stu-id="44412-116">The called number pattern</span></span> 
- <span data-ttu-id="44412-117">被叫号码模式和进行呼叫的特定用户</span><span class="sxs-lookup"><span data-stu-id="44412-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="44412-118">SBCs 可以指定为 "活动" 和 "备份"。</span><span class="sxs-lookup"><span data-stu-id="44412-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="44412-119">当配置为活动的 SBC 不能用于特定呼叫路由时，该呼叫将路由到 backup SBC。</span><span class="sxs-lookup"><span data-stu-id="44412-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="44412-120">语音路由由以下元素组成：</span><span class="sxs-lookup"><span data-stu-id="44412-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="44412-121">**语音路由策略** -PSTN 使用的容器，可分配给用户或多个用户。</span><span class="sxs-lookup"><span data-stu-id="44412-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="44412-122">**PSTN 用法** -用于语音路由和 PSTN 用途的容器，可在不同的语音路由策略中共享。</span><span class="sxs-lookup"><span data-stu-id="44412-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="44412-123">**语音路由** -一种数字模式和一组联机 PSTN 网关，用于呼叫号码匹配模式的呼叫。</span><span class="sxs-lookup"><span data-stu-id="44412-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="44412-124">**联机 PSTN 网关** -指向 sbc 的指针，该指针还存储在通过 SBC 放置调用时应用的配置，例如，将 P 声明身份 (PAI) 或首选编解码器。可添加到语音路由。</span><span class="sxs-lookup"><span data-stu-id="44412-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="44412-125">语音路由策略注意事项</span><span class="sxs-lookup"><span data-stu-id="44412-125">Voice routing policy considerations</span></span>

<span data-ttu-id="44412-126">如果用户具有呼叫计划许可证，则该用户的传出呼叫将通过 Microsoft 呼叫计划 PSTN 基础结构自动路由。</span><span class="sxs-lookup"><span data-stu-id="44412-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="44412-127">如果将联机语音路由策略配置并分配给呼叫计划用户，则会检查该用户的传出呼叫以确定所拨号码是否与联机语音路由策略中定义的数字模式匹配。</span><span class="sxs-lookup"><span data-stu-id="44412-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="44412-128">如果存在匹配项，则通过直接路由主干路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="44412-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="44412-129">如果没有匹配项，则通过呼叫计划 PSTN 基础结构路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="44412-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="44412-130">如果你配置并应用全球 (组织范围的默认) 联机语音路由策略，则你组织中的所有支持语音的用户将继承该策略，这可能会导致来自呼叫计划用户的 PSTN 呼叫不小心路由到直接路由主干。</span><span class="sxs-lookup"><span data-stu-id="44412-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="44412-131">如果不希望所有用户都使用全局联机语音路由策略，请配置自定义联机语音路由策略，并将其分配给单个支持语音的用户。</span><span class="sxs-lookup"><span data-stu-id="44412-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="44412-132">示例1：使用一个 PSTN 使用的语音路由</span><span class="sxs-lookup"><span data-stu-id="44412-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="44412-133">下图显示了一个呼叫流中的语音路由策略的两个示例。</span><span class="sxs-lookup"><span data-stu-id="44412-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="44412-134">**通话流 1 (左侧) ：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该呼叫将路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="44412-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="44412-135">如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都不可用，则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="44412-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="44412-136">**(右侧) 的 "呼叫流程 2"：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该调用首先路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="44412-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="44412-137">如果两个 SBC 均不可用，将尝试使用较低优先级的路由 (sbc3.contoso.biz 和 sbc4.contoso.biz) 。</span><span class="sxs-lookup"><span data-stu-id="44412-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="44412-138">如果没有 SBCs 可用，将丢弃呼叫。</span><span class="sxs-lookup"><span data-stu-id="44412-138">If none of the SBCs are available, the call is dropped.</span></span> 

![显示语音路由策略示例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="44412-140">在这两个示例中，虽然为语音路由分配了优先级，但路由中的 SBCs 按随机顺序尝试。</span><span class="sxs-lookup"><span data-stu-id="44412-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span> <span data-ttu-id="44412-141">当两个 SBC 在一个路由中配置时，必须能够在 SBC 或 media 之间路由网络流量，因为可能会在传输中将新的邀请发送到路由中的不同 SBC。</span><span class="sxs-lookup"><span data-stu-id="44412-141">When two SBC's are configured in one route, network traffic must be routable between both SBC's or media will fail to be established on transfers as it is possible that the new invite for the transfer will be sent to a different SBC in the route.</span></span>

  > [!NOTE]
  > <span data-ttu-id="44412-142">除非用户也有 Microsoft 通话计划许可证，否则将删除示例配置中除与模式 + 1 425 XXX xx xx 或 + 1 206 XXX xx 之间的任何号码。</span><span class="sxs-lookup"><span data-stu-id="44412-142">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="44412-143">如果用户有呼叫计划许可证，则会根据 Microsoft 通话计划的政策自动路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="44412-143">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="44412-144">Microsoft 通话计划将自动应用为具有 Microsoft 呼叫计划许可证的所有用户的最后一个路由，并且不需要其他呼叫路由配置。</span><span class="sxs-lookup"><span data-stu-id="44412-144">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="44412-145">在下图所示的示例中，添加了一个语音路由，用于将呼叫发送给您的所有其他美国和加拿大的号码 (呼叫号码模式 + 1 XXX XXX xx xx) 。</span><span class="sxs-lookup"><span data-stu-id="44412-145">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![显示具有第三个路线的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="44412-147">对于所有其他呼叫，如果用户在 Microsoft Phone 系统和 Microsoft 通话计划) 中同时具有两个许可证 (，则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="44412-147">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="44412-148">如果没有与管理员创建的在线语音路线中的数字模式匹配的内容，则呼叫将通过 Microsoft 通话计划进行路由。</span><span class="sxs-lookup"><span data-stu-id="44412-148">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="44412-149">如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="44412-149">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="44412-150">在此情况下，路由 "其他 + 1" 的优先级值不重要，因为只有一条路线与模式 + 1 XXX XXX xx 相匹配。</span><span class="sxs-lookup"><span data-stu-id="44412-150">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="44412-151">如果用户拨打 + 1 324 567 89 89 且 sbc5.contoso.biz 和 sbc6.contoso.biz 都不可用，则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="44412-151">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="44412-152">下表总结了使用三个语音路由的配置。</span><span class="sxs-lookup"><span data-stu-id="44412-152">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="44412-153">在此示例中，所有三个路由都属于同一 PSTN 使用，即 "美国和加拿大"。</span><span class="sxs-lookup"><span data-stu-id="44412-153">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="44412-154">所有路线均与 "美国和加拿大" PSTN 使用相关联，PSTN 使用与 "仅美国" 语音路由策略相关联。</span><span class="sxs-lookup"><span data-stu-id="44412-154">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="44412-155">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="44412-155">**PSTN usage**</span></span>|<span data-ttu-id="44412-156">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="44412-156">**Voice route**</span></span>|<span data-ttu-id="44412-157">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="44412-157">**Number pattern**</span></span>|<span data-ttu-id="44412-158">**优先级**</span><span class="sxs-lookup"><span data-stu-id="44412-158">**Priority**</span></span>|<span data-ttu-id="44412-159">**SBC**</span><span class="sxs-lookup"><span data-stu-id="44412-159">**SBC**</span></span>|<span data-ttu-id="44412-160">**说明**</span><span class="sxs-lookup"><span data-stu-id="44412-160">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44412-161">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="44412-161">US and Canada</span></span>|<span data-ttu-id="44412-162">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="44412-162">"Redmond 1"</span></span>|<span data-ttu-id="44412-163">^\\+ 1 (425 \| 206) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="44412-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="44412-164">1</span><span class="sxs-lookup"><span data-stu-id="44412-164">1</span></span>|<span data-ttu-id="44412-165">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-165">sbc1.contoso.biz</span></span><br/><span data-ttu-id="44412-166">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-166">sbc2.contoso.biz</span></span>|<span data-ttu-id="44412-167">拨打的号码的活动路线 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="44412-167">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="44412-168">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="44412-168">US and Canada</span></span>|<span data-ttu-id="44412-169">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="44412-169">"Redmond 2"</span></span>|<span data-ttu-id="44412-170">^\\+ 1 (425 \| 206) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="44412-170">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="44412-171">2</span><span class="sxs-lookup"><span data-stu-id="44412-171">2</span></span>|<span data-ttu-id="44412-172">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-172">sbc3.contoso.biz</span></span><br/><span data-ttu-id="44412-173">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-173">sbc4.contoso.biz</span></span>|<span data-ttu-id="44412-174">已呼叫号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="44412-174">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="44412-175">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="44412-175">US and Canada</span></span>|<span data-ttu-id="44412-176">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="44412-176">"Other +1"</span></span>|<span data-ttu-id="44412-177">^\\+ 1 ( \d {10}) $</span><span class="sxs-lookup"><span data-stu-id="44412-177">^\\+1(\d{10})$</span></span>|<span data-ttu-id="44412-178">3</span><span class="sxs-lookup"><span data-stu-id="44412-178">3</span></span>|<span data-ttu-id="44412-179">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-179">sbc5.contoso.biz</span></span><br/><span data-ttu-id="44412-180">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-180">sbc6.contoso.biz</span></span>|<span data-ttu-id="44412-181">呼叫号码的路由 + 1 XXX XXX xx (，但 + 1 425 XXX xx 或 + 1 206 XXX xx) </span><span class="sxs-lookup"><span data-stu-id="44412-181">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="44412-182">示例1：配置步骤</span><span class="sxs-lookup"><span data-stu-id="44412-182">Example 1: Configuration steps</span></span>

<span data-ttu-id="44412-183">以下示例显示了如何：</span><span class="sxs-lookup"><span data-stu-id="44412-183">The following example shows how to:</span></span>

1. <span data-ttu-id="44412-184">创建单个 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="44412-184">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="44412-185">配置三个语音路由。</span><span class="sxs-lookup"><span data-stu-id="44412-185">Configure three voice routes.</span></span>
3. <span data-ttu-id="44412-186">创建语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="44412-186">Create a voice routing policy.</span></span>
4. <span data-ttu-id="44412-187">将策略分配给名为 Spencer Low 的用户。</span><span class="sxs-lookup"><span data-stu-id="44412-187">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="44412-188">你可以使用 [Microsoft 团队管理中心](#admincenterexample1) 或 [PowerShell](#powershellexample1) 执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="44412-188">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="44412-189">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="44412-189">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="44412-190">步骤1：创建 "美国和加拿大" PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="44412-190">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="44412-191">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **直接路由**"，然后在右上角选择 "**管理 PSTN 使用情况记录**"。</span><span class="sxs-lookup"><span data-stu-id="44412-191">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="44412-192">单击 " **添加**"，键入 " **美国和加拿大**"，然后单击 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="44412-192">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="44412-193">步骤2：创建三个语音路线 (雷德蒙1、雷德蒙2和其他 + 1) </span><span class="sxs-lookup"><span data-stu-id="44412-193">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="44412-194">以下步骤介绍如何创建语音路由。</span><span class="sxs-lookup"><span data-stu-id="44412-194">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="44412-195">使用这些步骤，通过使用前面表中所述的设置，为本示例创建三个名为 Redmond 1、Redmond 2 和其他 + 1 的语音路线。</span><span class="sxs-lookup"><span data-stu-id="44412-195">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="44412-196">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **直接路由**"，然后选择 "**语音路由**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="44412-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="44412-197">单击 " **添加**"，然后输入语音路线的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="44412-197">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="44412-198">设置优先级并指定拨出的号码模式。</span><span class="sxs-lookup"><span data-stu-id="44412-198">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="44412-199">若要将 SBC 注册到语音路由，请在 " **SBCs 注册 (可选)** 中，单击" **添加 sbcs**"，选择要注册的 SBCs，然后单击" **应用**"。</span><span class="sxs-lookup"><span data-stu-id="44412-199">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="44412-200">要添加 PSTN 使用记录，请在 " **PSTN 使用记录 (可选)** 下，单击" **添加 PSTN 使用情况**"，选择要添加的 PSTN 记录，然后单击" **应用**"。</span><span class="sxs-lookup"><span data-stu-id="44412-200">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="44412-201">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="44412-201">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="44412-202">步骤3：创建名为 "仅美国" 的语音路由策略，并向策略添加 "美国和加拿大" PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="44412-202">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="44412-203">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **语音路由策略**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="44412-203">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="44412-204">**仅键入 US** 作为名称，然后添加说明。</span><span class="sxs-lookup"><span data-stu-id="44412-204">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="44412-205">在 " **PSTN 使用记录**" 下，单击 " **添加 PSTN 使用情况**"，选择 "美国和加拿大" PSTN 使用记录，然后单击 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="44412-205">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="44412-206">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="44412-206">Click **Save**.</span></span>

<span data-ttu-id="44412-207">若要了解详细信息，请参阅 [管理语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="44412-207">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="44412-208">步骤4：将语音路由策略分配给名为 Spencer Low 的用户</span><span class="sxs-lookup"><span data-stu-id="44412-208">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="44412-209">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。</span><span class="sxs-lookup"><span data-stu-id="44412-209">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="44412-210">单击 " **策略**"，然后单击 " **分配的策略**" 旁边的 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="44412-210">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="44412-211">在 " **语音路由策略**" 下，选择 "仅美国" 策略，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="44412-211">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="44412-212">若要了解详细信息，请参阅 [管理语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="44412-212">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="44412-213">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="44412-213">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="44412-214">步骤1：创建 "美国和加拿大" PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="44412-214">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="44412-215">在 Skype for Business Online 中的远程 PowerShell 会话中，键入：</span><span class="sxs-lookup"><span data-stu-id="44412-215">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="44412-216">通过输入以下内容验证是否已创建使用：</span><span class="sxs-lookup"><span data-stu-id="44412-216">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="44412-217">这将返回可能被截断的名称的列表：</span><span class="sxs-lookup"><span data-stu-id="44412-217">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="44412-218">以下示例显示运行 `(Get-CSOnlinePSTNUsage).usage` Powershell 命令以显示全名 (未截断) 的结果：</span><span class="sxs-lookup"><span data-stu-id="44412-218">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="44412-219">步骤2：创建三个语音路线 (雷德蒙1、雷德蒙2和其他 + 1) </span><span class="sxs-lookup"><span data-stu-id="44412-219">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="44412-220">若要在 Skype for business Online 的 PowerShell 会话中创建 "Redmond 1" 路线，请输入：</span><span class="sxs-lookup"><span data-stu-id="44412-220">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="44412-221">返回：</span><span class="sxs-lookup"><span data-stu-id="44412-221">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="44412-222">若要创建雷德蒙2路线，请输入：</span><span class="sxs-lookup"><span data-stu-id="44412-222">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="44412-223">若要创建其他 + 1 路线，请输入：</span><span class="sxs-lookup"><span data-stu-id="44412-223">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="44412-224">请确保 NumberPattern 属性中的正则表达式是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="44412-224">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="44412-225">你可以使用此网站对其进行测试： [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="44412-225">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="44412-226">在某些情况下，需要将所有调用路由到同一 SBC;使用-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="44412-226">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="44412-227">将所有调用路由到同一个 SBC。</span><span class="sxs-lookup"><span data-stu-id="44412-227">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="44412-228">通过 `Get-CSOnlineVoiceRoute` 使用如下所示的选项运行 PowerShell 命令验证是否已正确配置路由：</span><span class="sxs-lookup"><span data-stu-id="44412-228">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="44412-229">应返回：</span><span class="sxs-lookup"><span data-stu-id="44412-229">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
</pre>

<span data-ttu-id="44412-230">在此示例中，自动为 "其他 + 1" 路由分配优先级4。</span><span class="sxs-lookup"><span data-stu-id="44412-230">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="44412-231">步骤3：创建名为 "仅美国" 的语音路由策略，并向策略添加 "美国和加拿大" PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="44412-231">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="44412-232">在 Skype for Business Online 的 PowerShell 会话中，键入：</span><span class="sxs-lookup"><span data-stu-id="44412-232">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="44412-233">此示例中显示了结果：</span><span class="sxs-lookup"><span data-stu-id="44412-233">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="44412-234">步骤4：将语音路由策略分配给名为 Spencer Low 的用户</span><span class="sxs-lookup"><span data-stu-id="44412-234">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="44412-235">在 Skype for Business Online 的 PowerShell 会话中，键入：</span><span class="sxs-lookup"><span data-stu-id="44412-235">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="44412-236">通过输入以下命令验证策略分配：</span><span class="sxs-lookup"><span data-stu-id="44412-236">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="44412-237">该命令将返回以下内容：</span><span class="sxs-lookup"><span data-stu-id="44412-237">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="44412-238">示例2：具有多个 PSTN 用法的语音路由</span><span class="sxs-lookup"><span data-stu-id="44412-238">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="44412-239">在示例1中创建的 "语音路由策略" 仅允许拨打美国和加拿大的电话号码，除非还为用户分配了 Microsoft 通话计划许可证。</span><span class="sxs-lookup"><span data-stu-id="44412-239">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="44412-240">在下面的示例中，您可以创建 "无限制" 语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="44412-240">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="44412-241">该策略重用在示例1中创建的 "美国和加拿大" PSTN 使用情况，以及新的 "国际" PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="44412-241">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="44412-242">此策略将所有其他调用路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="44412-242">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="44412-243">显示的示例将 "仅美国" 策略分配给用户 Spencer Low，将 "无限制" 策略分配给用户 John 的，以便按如下方式进行路由：</span><span class="sxs-lookup"><span data-stu-id="44412-243">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="44412-244">Spencer 低–美国的政策。</span><span class="sxs-lookup"><span data-stu-id="44412-244">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="44412-245">通话仅允许使用美国和加拿大号码。</span><span class="sxs-lookup"><span data-stu-id="44412-245">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="44412-246">当调用 Redmond 数字范围时，必须使用特定的 SBCs 集。</span><span class="sxs-lookup"><span data-stu-id="44412-246">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="44412-247">除非向用户分配了通话计划许可证，否则不会路由非美国号码。</span><span class="sxs-lookup"><span data-stu-id="44412-247">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="44412-248">John 的 54777-国际政策。</span><span class="sxs-lookup"><span data-stu-id="44412-248">John Woods – International policy.</span></span>  <span data-ttu-id="44412-249">任何号码都允许通话。</span><span class="sxs-lookup"><span data-stu-id="44412-249">Calls are allowed to any number.</span></span> <span data-ttu-id="44412-250">当调用 Redmond 数字范围时，必须使用特定的 SBCs 集。</span><span class="sxs-lookup"><span data-stu-id="44412-250">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="44412-251">非 US 数字将使用 sbc2.contoso.biz 和 sbc5.contoso.biz 进行路由。</span><span class="sxs-lookup"><span data-stu-id="44412-251">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![显示分配给用户 Spencer 低的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="44412-253">对于所有其他呼叫，如果用户在 Microsoft Phone 系统和 Microsoft 通话计划) 中同时具有两个许可证 (，则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="44412-253">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="44412-254">如果没有与管理员创建的在线语音路线中的数字模式匹配的内容，则使用 Microsoft 通话计划路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="44412-254">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="44412-255">如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="44412-255">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![显示分配给用户 John 的的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="44412-257">下表总结了路由策略 "无限制" 的用法标识和语音路由。</span><span class="sxs-lookup"><span data-stu-id="44412-257">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="44412-258">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="44412-258">**PSTN usage**</span></span>|<span data-ttu-id="44412-259">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="44412-259">**Voice route**</span></span>|<span data-ttu-id="44412-260">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="44412-260">**Number pattern**</span></span>|<span data-ttu-id="44412-261">**优先级**</span><span class="sxs-lookup"><span data-stu-id="44412-261">**Priority**</span></span>|<span data-ttu-id="44412-262">**SBC**</span><span class="sxs-lookup"><span data-stu-id="44412-262">**SBC**</span></span>|<span data-ttu-id="44412-263">**说明**</span><span class="sxs-lookup"><span data-stu-id="44412-263">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44412-264">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="44412-264">US and Canada</span></span>|<span data-ttu-id="44412-265">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="44412-265">"Redmond 1"</span></span>|<span data-ttu-id="44412-266">^\\+ 1 (425 \| 206) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="44412-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="44412-267">1</span><span class="sxs-lookup"><span data-stu-id="44412-267">1</span></span>|<span data-ttu-id="44412-268">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-268">sbc1.contoso.biz</span></span><br/><span data-ttu-id="44412-269">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-269">sbc2.contoso.biz</span></span>|<span data-ttu-id="44412-270">被呼叫方号码的活动路由 + 1 425 XXX XX XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="44412-270">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="44412-271">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="44412-271">US and Canada</span></span>|<span data-ttu-id="44412-272">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="44412-272">"Redmond 2"</span></span>|<span data-ttu-id="44412-273">^\\+ 1 (425 \| 206) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="44412-273">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="44412-274">2</span><span class="sxs-lookup"><span data-stu-id="44412-274">2</span></span>|<span data-ttu-id="44412-275">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-275">sbc3.contoso.biz</span></span><br/><span data-ttu-id="44412-276">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-276">sbc4.contoso.biz</span></span>|<span data-ttu-id="44412-277">被呼叫方号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="44412-277">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="44412-278">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="44412-278">US and Canada</span></span>|<span data-ttu-id="44412-279">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="44412-279">"Other +1"</span></span>|<span data-ttu-id="44412-280">^\\+ 1 ( \d {10}) $</span><span class="sxs-lookup"><span data-stu-id="44412-280">^\\+1(\d{10})$</span></span>|<span data-ttu-id="44412-281">3</span><span class="sxs-lookup"><span data-stu-id="44412-281">3</span></span>|<span data-ttu-id="44412-282">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-282">sbc5.contoso.biz</span></span><br/><span data-ttu-id="44412-283">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-283">sbc6.contoso.biz</span></span>|<span data-ttu-id="44412-284">被呼叫方号码的路由 + 1 XXX XXX xx (，但 + 1 425 XXX xx 或 + 1 206 XXX xx) </span><span class="sxs-lookup"><span data-stu-id="44412-284">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="44412-285">International</span><span class="sxs-lookup"><span data-stu-id="44412-285">International</span></span>|<span data-ttu-id="44412-286">International</span><span class="sxs-lookup"><span data-stu-id="44412-286">International</span></span>|<span data-ttu-id="44412-287">\d +</span><span class="sxs-lookup"><span data-stu-id="44412-287">\d+</span></span>|<span data-ttu-id="44412-288">4</span><span class="sxs-lookup"><span data-stu-id="44412-288">4</span></span>|<span data-ttu-id="44412-289">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-289">sbc2.contoso.biz</span></span><br/><span data-ttu-id="44412-290">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="44412-290">sbc5.contoso.biz</span></span>|<span data-ttu-id="44412-291">任何数字模式的路由</span><span class="sxs-lookup"><span data-stu-id="44412-291">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="44412-292">语音路由策略中的 PSTN 用法的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="44412-292">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="44412-293">使用实例按顺序应用，如果在第一次使用中发现匹配项，则从不计算其他用法。</span><span class="sxs-lookup"><span data-stu-id="44412-293">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="44412-294">"国际" PSTN 使用必须位于 "美国和加拿大" PSTN 使用后。</span><span class="sxs-lookup"><span data-stu-id="44412-294">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="44412-295">若要更改 PSTN 用法的顺序，请运行 `Set-CSOnlineVoiceRoutingPolicy` 命令。</span><span class="sxs-lookup"><span data-stu-id="44412-295">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="44412-296">例如，若要将订单从 "美国和加拿大" 的第一个和 "国际" 的订单更改为反向顺序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="44412-296">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="44412-297">将自动分配 "其他 + 1" 和 "国际" 语音路由的优先级。</span><span class="sxs-lookup"><span data-stu-id="44412-297">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="44412-298">它们的优先级与 "Redmond 1" 和 "雷德蒙 2" 相比，不是很重要。</span><span class="sxs-lookup"><span data-stu-id="44412-298">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="44412-299">示例2：配置步骤</span><span class="sxs-lookup"><span data-stu-id="44412-299">Example 2: Configuration steps</span></span>

<span data-ttu-id="44412-300">以下示例显示了如何：</span><span class="sxs-lookup"><span data-stu-id="44412-300">The following example shows how to:</span></span>

1. <span data-ttu-id="44412-301">创建名为 "国际" 的新 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="44412-301">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="44412-302">创建名为 "国际" 的新语音路线。</span><span class="sxs-lookup"><span data-stu-id="44412-302">Create a new voice route called International.</span></span>
3. <span data-ttu-id="44412-303">创建名为 "无限制" 的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="44412-303">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="44412-304">将策略分配给用户 John 的一对用户。</span><span class="sxs-lookup"><span data-stu-id="44412-304">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="44412-305">你可以使用 [Microsoft 团队管理中心](#admincenterexample2) 或 [PowerShell](#powershellexample2) 执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="44412-305">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="44412-306">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="44412-306">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="44412-307">步骤1：创建 "国际" PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="44412-307">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="44412-308">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **直接路由**"，然后在右上角选择 "**管理 PSTN 使用情况记录**"。</span><span class="sxs-lookup"><span data-stu-id="44412-308">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="44412-309">单击 " **添加**"，键入 " **国际**"，然后单击 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="44412-309">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="44412-310">步骤2：创建 "国际" 语音路由</span><span class="sxs-lookup"><span data-stu-id="44412-310">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="44412-311">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **直接路由**"，然后选择 "**语音路由**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="44412-311">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="44412-312">单击 " **添加**"，输入 "国际" 作为名称，然后添加说明。</span><span class="sxs-lookup"><span data-stu-id="44412-312">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="44412-313">将 "优先级" 设置为 "4"，然后将 "拨打的号码" 模式设置为 "\d +"。</span><span class="sxs-lookup"><span data-stu-id="44412-313">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="44412-314">在 " **SBCs 注册 (可选)** 中，单击" **添加 SBCs**"，选择" sbc2.contoso.biz "和" sbc5.contoso.biz "，然后单击" **应用**"。</span><span class="sxs-lookup"><span data-stu-id="44412-314">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="44412-315">在 " **PSTN 使用记录 (可选)**" 下，单击 " **添加 PSTN 使用情况**"，选择 "国际" PSTN 使用记录，然后单击 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="44412-315">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="44412-316">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="44412-316">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="44412-317">步骤3：创建名为 "无限制" 的语音路由策略，并将 "美国和加拿大" 和 "国际" PSTN 使用情况添加到策略</span><span class="sxs-lookup"><span data-stu-id="44412-317">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="44412-318">PSTN 使用 "美国和加拿大" 将在此语音路由策略中重复使用，以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理，作为本地或本地呼叫。</span><span class="sxs-lookup"><span data-stu-id="44412-318">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="44412-319">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **语音路由策略**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="44412-319">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="44412-320">键入 " **无限制** " 作为名称并添加说明。</span><span class="sxs-lookup"><span data-stu-id="44412-320">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="44412-321">在 " **PSTN 使用记录**" 下，单击 " **添加 PSTN 使用情况**"，选择 "美国和加拿大" pstn 使用记录，然后选择 "国际" pstn 使用记录。</span><span class="sxs-lookup"><span data-stu-id="44412-321">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="44412-322">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="44412-322">Click **Apply**.</span></span>

    <span data-ttu-id="44412-323">记下 PSTN 用法的顺序：</span><span class="sxs-lookup"><span data-stu-id="44412-323">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="44412-324">如果对号码 "+ 1 425 XXX XX XX" 的调用与此示例中配置的用法相同，则呼叫将遵循 "美国和加拿大" 使用中设置的路由，并应用特殊路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="44412-324">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="44412-325">也就是说，将首先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由呼叫，然后 sbc3.contoso.biz 和 sbc4.contoso.biz 作为备份路由。</span><span class="sxs-lookup"><span data-stu-id="44412-325">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="44412-326">如果 "国际" PSTN 使用早于 "美国和加拿大"，则对 + 1 425 XXX xx 的调用将作为路由逻辑的一部分路由到 sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="44412-326">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="44412-327">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="44412-327">Click **Save**.</span></span>

<span data-ttu-id="44412-328">若要了解详细信息，请参阅 [管理语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="44412-328">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="44412-329">步骤4：将语音路由策略分配给名为 John 的的用户</span><span class="sxs-lookup"><span data-stu-id="44412-329">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="44412-330">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。</span><span class="sxs-lookup"><span data-stu-id="44412-330">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="44412-331">单击 " **策略**"，然后单击 " **分配的策略**" 旁边的 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="44412-331">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="44412-332">在 " **语音路由策略**" 下，选择 "无限制" 策略，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="44412-332">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="44412-333">结果是，应用到 John 54777 的语音政策不受限制，并且将遵循呼叫路由的逻辑，可用于美国、加拿大和国际通话。</span><span class="sxs-lookup"><span data-stu-id="44412-333">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="44412-334">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="44412-334">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="44412-335">步骤1：创建 "国际" PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="44412-335">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="44412-336">在 Skype for Business Online 中的远程 PowerShell 会话中，输入：</span><span class="sxs-lookup"><span data-stu-id="44412-336">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="44412-337">步骤2：创建名为 "国际" 的新语音路线</span><span class="sxs-lookup"><span data-stu-id="44412-337">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="44412-338">返回：</span><span class="sxs-lookup"><span data-stu-id="44412-338">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="44412-339">步骤3：创建名为 "无限制" 的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="44412-339">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="44412-340">PSTN 使用 "Redmond 1" 和 "Redmond" 在此语音路由策略中重复使用，以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理，作为本地或本地呼叫。</span><span class="sxs-lookup"><span data-stu-id="44412-340">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="44412-341">记下 PSTN 用法的顺序：</span><span class="sxs-lookup"><span data-stu-id="44412-341">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="44412-342">如果对数字 "+ 1 425 XXX XX XX" 的调用配置为以下示例中所示的使用实例，则呼叫将遵循 "美国和加拿大" 使用中设置的路由，并应用特殊路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="44412-342">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="44412-343">也就是说，将首先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由呼叫，然后 sbc3.contoso.biz 和 sbc4.contoso.biz 作为备份路由。</span><span class="sxs-lookup"><span data-stu-id="44412-343">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="44412-344">如果 "国际" PSTN 使用早于 "美国和加拿大"，则对 + 1 425 XXX xx 的调用将作为路由逻辑的一部分路由到 sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="44412-344">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="44412-345">输入命令：</span><span class="sxs-lookup"><span data-stu-id="44412-345">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="44412-346">返回：</span><span class="sxs-lookup"><span data-stu-id="44412-346">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="44412-347">步骤4：将语音路由策略分配给名为 John 的的用户</span><span class="sxs-lookup"><span data-stu-id="44412-347">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="44412-348">然后使用以下命令验证作业：</span><span class="sxs-lookup"><span data-stu-id="44412-348">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="44412-349">返回：</span><span class="sxs-lookup"><span data-stu-id="44412-349">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="44412-350">结果是，应用到 John 54777 的语音政策不受限制，并且将遵循可用于美国、加拿大和国际通话的呼叫路线逻辑。</span><span class="sxs-lookup"><span data-stu-id="44412-350">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="44412-351">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44412-351">See also</span></span>

[<span data-ttu-id="44412-352">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="44412-352">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="44412-353">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="44412-353">Configure Direct Routing</span></span>](direct-routing-configure.md)
