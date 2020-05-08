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
ms.openlocfilehash: 0611684c79d92572ade41f2545096fe1d9bb4dd2
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159009"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="feff1-103">为直接路由配置语音路由</span><span class="sxs-lookup"><span data-stu-id="feff1-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="feff1-104">本文介绍如何为手机系统直接路由配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="feff1-105">这是用于配置直接路由的以下步骤的步骤3：</span><span class="sxs-lookup"><span data-stu-id="feff1-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="feff1-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="feff1-106">Step 1.</span></span> [<span data-ttu-id="feff1-107">将 SBC 连接到 Microsoft Phone 系统并验证连接</span><span class="sxs-lookup"><span data-stu-id="feff1-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="feff1-108">第 2 步</span><span class="sxs-lookup"><span data-stu-id="feff1-108">Step 2.</span></span> [<span data-ttu-id="feff1-109">为用户启用直接路由、语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="feff1-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="feff1-110">**步骤3。配置语音路由**（本文）</span><span class="sxs-lookup"><span data-stu-id="feff1-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="feff1-111">第 4 步</span><span class="sxs-lookup"><span data-stu-id="feff1-111">Step 4.</span></span> [<span data-ttu-id="feff1-112">将数字转换为备用格式</span><span class="sxs-lookup"><span data-stu-id="feff1-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="feff1-113">有关设置直接路由所需的所有步骤的信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="feff1-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="feff1-114">语音路由概述</span><span class="sxs-lookup"><span data-stu-id="feff1-114">Voice routing overview</span></span>

<span data-ttu-id="feff1-115">Microsoft Phone 系统具有一种路由机制，允许将呼叫发送到特定的会话边界控制器（SBC），具体取决于：</span><span class="sxs-lookup"><span data-stu-id="feff1-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="feff1-116">被叫号码模式</span><span class="sxs-lookup"><span data-stu-id="feff1-116">The called number pattern</span></span> 
- <span data-ttu-id="feff1-117">被叫号码模式和进行呼叫的特定用户</span><span class="sxs-lookup"><span data-stu-id="feff1-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="feff1-118">SBCs 可以指定为 "活动" 和 "备份"。</span><span class="sxs-lookup"><span data-stu-id="feff1-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="feff1-119">当配置为活动的 SBC 不能用于特定呼叫路由时，该呼叫将路由到 backup SBC。</span><span class="sxs-lookup"><span data-stu-id="feff1-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="feff1-120">语音路由由以下元素组成：</span><span class="sxs-lookup"><span data-stu-id="feff1-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="feff1-121">**语音路由策略**-PSTN 使用的容器，可分配给用户或多个用户。</span><span class="sxs-lookup"><span data-stu-id="feff1-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="feff1-122">**PSTN 用法**-用于语音路由和 PSTN 用途的容器，可在不同的语音路由策略中共享。</span><span class="sxs-lookup"><span data-stu-id="feff1-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="feff1-123">**语音路由**-一种数字模式和一组联机 PSTN 网关，用于呼叫号码匹配模式的呼叫。</span><span class="sxs-lookup"><span data-stu-id="feff1-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="feff1-124">**联机 PSTN 网关**-指向 sbc 的指针，该指针还存储通过 SBC 放置调用时应用的配置，例如，前 P 声明的身份（PAI）或首选编解码器;可添加到语音路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="feff1-125">示例1：使用一个 PSTN 使用的语音路由</span><span class="sxs-lookup"><span data-stu-id="feff1-125">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="feff1-126">下图显示了一个呼叫流中的语音路由策略的两个示例。</span><span class="sxs-lookup"><span data-stu-id="feff1-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="feff1-127">**呼叫流1（在左侧）：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该呼叫将路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="feff1-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="feff1-128">如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都不可用，则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="feff1-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="feff1-129">**呼叫流程2（右侧）：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该调用首先路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="feff1-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="feff1-130">如果两个 SBC 均不可用，将尝试具有较低优先级的路由（sbc3.contoso.biz 和 sbc4.contoso.biz）。</span><span class="sxs-lookup"><span data-stu-id="feff1-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="feff1-131">如果没有 SBCs 可用，将丢弃呼叫。</span><span class="sxs-lookup"><span data-stu-id="feff1-131">If none of the SBCs are available, the call is dropped.</span></span> 

![显示语音路由策略示例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="feff1-133">在这两个示例中，虽然为语音路由分配了优先级，但路由中的 SBCs 按随机顺序尝试。</span><span class="sxs-lookup"><span data-stu-id="feff1-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="feff1-134">除非用户也有 Microsoft 通话计划许可证，否则将删除示例配置中除与模式 + 1 425 XXX xx xx 或 + 1 206 XXX xx 之间的任何号码。</span><span class="sxs-lookup"><span data-stu-id="feff1-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="feff1-135">如果用户有呼叫计划许可证，则会根据 Microsoft 通话计划的政策自动路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="feff1-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="feff1-136">Microsoft 通话计划将自动应用为具有 Microsoft 呼叫计划许可证的所有用户的最后一个路由，并且不需要其他呼叫路由配置。</span><span class="sxs-lookup"><span data-stu-id="feff1-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="feff1-137">在下图所示的示例中，添加了一个语音路由，用于向所有美国和加拿大的号码（拨叫号码模式 + 1 XXX XXX xx）发送呼叫。</span><span class="sxs-lookup"><span data-stu-id="feff1-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![显示具有第三个路线的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="feff1-139">对于所有其他呼叫：</span><span class="sxs-lookup"><span data-stu-id="feff1-139">For all other calls:</span></span>

- <span data-ttu-id="feff1-140">如果用户同时具有两个许可证（Microsoft Phone System 和 Microsoft 通话计划），则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="feff1-141">如果没有与管理员创建的在线语音路线中的数字模式匹配的内容，则呼叫将通过 Microsoft 通话计划进行路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="feff1-142">如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="feff1-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="feff1-143">在此情况下，路由 "其他 + 1" 的优先级值不重要，因为只有一条路线与模式 + 1 XXX XXX xx 相匹配。</span><span class="sxs-lookup"><span data-stu-id="feff1-143">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="feff1-144">如果用户拨打 + 1 324 567 89 89 且 sbc5.contoso.biz 和 sbc6.contoso.biz 都不可用，则呼叫将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="feff1-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="feff1-145">下表总结了使用三个语音路由的配置。</span><span class="sxs-lookup"><span data-stu-id="feff1-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="feff1-146">在此示例中，所有三个路由都属于同一 PSTN 使用，即 "美国和加拿大"。</span><span class="sxs-lookup"><span data-stu-id="feff1-146">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="feff1-147">所有路线均与 "美国和加拿大" PSTN 使用相关联，PSTN 使用与 "仅美国" 语音路由策略相关联。</span><span class="sxs-lookup"><span data-stu-id="feff1-147">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="feff1-148">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="feff1-148">**PSTN usage**</span></span>|<span data-ttu-id="feff1-149">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="feff1-149">**Voice route**</span></span>|<span data-ttu-id="feff1-150">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="feff1-150">**Number pattern**</span></span>|<span data-ttu-id="feff1-151">**优先级**</span><span class="sxs-lookup"><span data-stu-id="feff1-151">**Priority**</span></span>|<span data-ttu-id="feff1-152">**SBC**</span><span class="sxs-lookup"><span data-stu-id="feff1-152">**SBC**</span></span>|<span data-ttu-id="feff1-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="feff1-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="feff1-154">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="feff1-154">US and Canada</span></span>|<span data-ttu-id="feff1-155">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="feff1-155">"Redmond 1"</span></span>|<span data-ttu-id="feff1-156">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="feff1-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="feff1-157">1</span><span class="sxs-lookup"><span data-stu-id="feff1-157">1</span></span>|<span data-ttu-id="feff1-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="feff1-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="feff1-160">拨打的号码的活动路线 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="feff1-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="feff1-161">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="feff1-161">US and Canada</span></span>|<span data-ttu-id="feff1-162">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="feff1-162">"Redmond 2"</span></span>|<span data-ttu-id="feff1-163">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="feff1-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="feff1-164">2</span><span class="sxs-lookup"><span data-stu-id="feff1-164">2</span></span>|<span data-ttu-id="feff1-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="feff1-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="feff1-167">已呼叫号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="feff1-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="feff1-168">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="feff1-168">US and Canada</span></span>|<span data-ttu-id="feff1-169">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="feff1-169">"Other +1"</span></span>|<span data-ttu-id="feff1-170">^\\+ 1 （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="feff1-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="feff1-171">3</span><span class="sxs-lookup"><span data-stu-id="feff1-171">3</span></span>|<span data-ttu-id="feff1-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="feff1-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="feff1-174">呼叫号码 + 1 XXX XXX xx （除 + 1 425 XXX xx 或 + 1 206 XXX xx 之间）的路由</span><span class="sxs-lookup"><span data-stu-id="feff1-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="feff1-175">示例1：配置步骤</span><span class="sxs-lookup"><span data-stu-id="feff1-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="feff1-176">以下示例显示了如何：</span><span class="sxs-lookup"><span data-stu-id="feff1-176">The following example shows how to:</span></span>

1. <span data-ttu-id="feff1-177">创建单个 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="feff1-177">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="feff1-178">配置三个语音路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-178">Configure three voice routes.</span></span>
3. <span data-ttu-id="feff1-179">创建语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="feff1-179">Create a voice routing policy.</span></span>
4. <span data-ttu-id="feff1-180">将策略分配给名为 Spencer Low 的用户。</span><span class="sxs-lookup"><span data-stu-id="feff1-180">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="feff1-181">你可以使用[Microsoft 团队管理中心](#admincenterexample1)或[PowerShell](#powershellexample1)执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="feff1-181">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="feff1-182">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="feff1-182">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="feff1-183">步骤1：创建 "美国和加拿大" PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="feff1-183">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="feff1-184">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **直接路由**"，然后在右上角选择 "**管理 PSTN 使用情况记录**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-184">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="feff1-185">单击 "**添加**"，键入 "**美国和加拿大**"，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-185">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="feff1-186">步骤2：创建三个语音路线（Redmond 1、Redmond 2 和其他 + 1）</span><span class="sxs-lookup"><span data-stu-id="feff1-186">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="feff1-187">以下步骤介绍如何创建语音路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-187">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="feff1-188">使用这些步骤，通过使用前面表中所述的设置，为本示例创建三个名为 Redmond 1、Redmond 2 和其他 + 1 的语音路线。</span><span class="sxs-lookup"><span data-stu-id="feff1-188">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="feff1-189">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **直接路由**"，然后选择 "**语音路由**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="feff1-189">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="feff1-190">单击 "**添加**"，然后输入语音路线的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="feff1-190">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="feff1-191">设置优先级并指定拨出的号码模式。</span><span class="sxs-lookup"><span data-stu-id="feff1-191">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="feff1-192">若要使用语音路由注册 SBC，请在 " **SBCs 已注册（可选）**" 下，单击 "**添加 sbcs**"，选择要注册的 SBCs，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-192">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="feff1-193">要添加 PSTN 使用记录，请在 " **PSTN 使用记录（可选）**" 下，单击 "**添加 PSTN 使用情况**"，选择要添加的 PSTN 记录，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-193">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="feff1-194">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="feff1-194">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="feff1-195">步骤3：创建名为 "仅美国" 的语音路由策略，并向策略添加 "美国和加拿大" PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="feff1-195">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="feff1-196">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **语音路由策略**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="feff1-197">**仅键入 US**作为名称，然后添加说明。</span><span class="sxs-lookup"><span data-stu-id="feff1-197">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="feff1-198">在 " **PSTN 使用记录**" 下，单击 "**添加 PSTN 使用情况**"，选择 "美国和加拿大" PSTN 使用记录，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-198">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="feff1-199">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="feff1-199">Click **Save**.</span></span>

<span data-ttu-id="feff1-200">若要了解详细信息，请参阅[管理语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="feff1-200">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="feff1-201">步骤4：将语音路由策略分配给名为 Spencer Low 的用户</span><span class="sxs-lookup"><span data-stu-id="feff1-201">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="feff1-202">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="feff1-202">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="feff1-203">单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-203">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="feff1-204">在 "**语音路由策略**" 下，选择 "仅美国" 策略，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-204">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="feff1-205">若要了解详细信息，请参阅[管理语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="feff1-205">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="feff1-206">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="feff1-206">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="feff1-207">步骤1：创建 "美国和加拿大" PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="feff1-207">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="feff1-208">在 Skype for Business Online 中的远程 PowerShell 会话中，键入：</span><span class="sxs-lookup"><span data-stu-id="feff1-208">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="feff1-209">通过输入以下内容验证是否已创建使用：</span><span class="sxs-lookup"><span data-stu-id="feff1-209">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="feff1-210">这将返回可能被截断的名称的列表：</span><span class="sxs-lookup"><span data-stu-id="feff1-210">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="feff1-211">以下示例显示运行`(Get-CSOnlinePSTNUsage).usage` Powershell 命令以显示完整名称（未截断）的结果：</span><span class="sxs-lookup"><span data-stu-id="feff1-211">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="feff1-212">步骤2：创建三个语音路线（Redmond 1、Redmond 2 和其他 + 1）</span><span class="sxs-lookup"><span data-stu-id="feff1-212">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="feff1-213">若要在 Skype for business Online 的 PowerShell 会话中创建 "Redmond 1" 路线，请输入：</span><span class="sxs-lookup"><span data-stu-id="feff1-213">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="feff1-214">返回：</span><span class="sxs-lookup"><span data-stu-id="feff1-214">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="feff1-215">若要创建雷德蒙2路线，请输入：</span><span class="sxs-lookup"><span data-stu-id="feff1-215">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="feff1-216">若要创建其他 + 1 路线，请输入：</span><span class="sxs-lookup"><span data-stu-id="feff1-216">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="feff1-217">请确保 NumberPattern 属性中的正则表达式是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="feff1-217">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="feff1-218">你可以使用此网站对其进行测试：[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="feff1-218">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="feff1-219">在某些情况下，需要将所有调用路由到同一 SBC;使用-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="feff1-219">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="feff1-220">将所有调用路由到同一个 SBC。</span><span class="sxs-lookup"><span data-stu-id="feff1-220">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="feff1-221">通过使用如下所示的选项运行`Get-CSOnlineVoiceRoute` PowerShell 命令验证是否已正确配置路由：</span><span class="sxs-lookup"><span data-stu-id="feff1-221">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="feff1-222">应返回：</span><span class="sxs-lookup"><span data-stu-id="feff1-222">Which should return:</span></span>
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

<span data-ttu-id="feff1-223">在此示例中，自动为 "其他 + 1" 路由分配优先级4。</span><span class="sxs-lookup"><span data-stu-id="feff1-223">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="feff1-224">步骤3：创建名为 "仅美国" 的语音路由策略，并向策略添加 "美国和加拿大" PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="feff1-224">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="feff1-225">在 Skype for Business Online 的 PowerShell 会话中，键入：</span><span class="sxs-lookup"><span data-stu-id="feff1-225">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="feff1-226">此示例中显示了结果：</span><span class="sxs-lookup"><span data-stu-id="feff1-226">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="feff1-227">步骤4：将语音路由策略分配给名为 Spencer Low 的用户</span><span class="sxs-lookup"><span data-stu-id="feff1-227">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="feff1-228">在 Skype for Business Online 的 PowerShell 会话中，键入：</span><span class="sxs-lookup"><span data-stu-id="feff1-228">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="feff1-229">通过输入以下命令验证策略分配：</span><span class="sxs-lookup"><span data-stu-id="feff1-229">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="feff1-230">该命令将返回以下内容：</span><span class="sxs-lookup"><span data-stu-id="feff1-230">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="feff1-231">示例2：具有多个 PSTN 用法的语音路由</span><span class="sxs-lookup"><span data-stu-id="feff1-231">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="feff1-232">在示例1中创建的 "语音路由策略" 仅允许拨打美国和加拿大的电话号码，除非还为用户分配了 Microsoft 通话计划许可证。</span><span class="sxs-lookup"><span data-stu-id="feff1-232">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="feff1-233">在下面的示例中，您可以创建 "无限制" 语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="feff1-233">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="feff1-234">该策略重用在示例1中创建的 "美国和加拿大" PSTN 使用情况，以及新的 "国际" PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="feff1-234">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="feff1-235">此策略将所有其他调用路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="feff1-235">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="feff1-236">显示的示例将 "仅美国" 策略分配给用户 Spencer Low，将 "无限制" 策略分配给用户 John 的，以便按如下方式进行路由：</span><span class="sxs-lookup"><span data-stu-id="feff1-236">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="feff1-237">Spencer 低–美国的政策。</span><span class="sxs-lookup"><span data-stu-id="feff1-237">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="feff1-238">通话仅允许使用美国和加拿大号码。</span><span class="sxs-lookup"><span data-stu-id="feff1-238">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="feff1-239">当调用 Redmond 数字范围时，必须使用特定的 SBCs 集。</span><span class="sxs-lookup"><span data-stu-id="feff1-239">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="feff1-240">除非向用户分配了通话计划许可证，否则不会路由非美国号码。</span><span class="sxs-lookup"><span data-stu-id="feff1-240">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="feff1-241">John 的 54777-国际政策。</span><span class="sxs-lookup"><span data-stu-id="feff1-241">John Woods – International policy.</span></span>  <span data-ttu-id="feff1-242">任何号码都允许通话。</span><span class="sxs-lookup"><span data-stu-id="feff1-242">Calls are allowed to any number.</span></span> <span data-ttu-id="feff1-243">当调用 Redmond 数字范围时，必须使用特定的 SBCs 集。</span><span class="sxs-lookup"><span data-stu-id="feff1-243">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="feff1-244">非 US 数字将使用 sbc2.contoso.biz 和 sbc5.contoso.biz 进行路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-244">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![显示分配给用户 Spencer 低的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="feff1-246">对于所有其他呼叫，如果用户同时具有两个许可证（Microsoft Phone System 和 Microsoft 通话计划），则使用自动路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-246">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="feff1-247">如果没有与管理员创建的在线语音路线中的数字模式匹配的内容，则使用 Microsoft 通话计划路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="feff1-247">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="feff1-248">如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="feff1-248">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![显示分配给用户 John 的的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="feff1-250">下表总结了路由策略 "无限制" 的用法标识和语音路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-250">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="feff1-251">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="feff1-251">**PSTN usage**</span></span>|<span data-ttu-id="feff1-252">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="feff1-252">**Voice route**</span></span>|<span data-ttu-id="feff1-253">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="feff1-253">**Number pattern**</span></span>|<span data-ttu-id="feff1-254">**优先级**</span><span class="sxs-lookup"><span data-stu-id="feff1-254">**Priority**</span></span>|<span data-ttu-id="feff1-255">**SBC**</span><span class="sxs-lookup"><span data-stu-id="feff1-255">**SBC**</span></span>|<span data-ttu-id="feff1-256">**说明**</span><span class="sxs-lookup"><span data-stu-id="feff1-256">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="feff1-257">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="feff1-257">US and Canada</span></span>|<span data-ttu-id="feff1-258">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="feff1-258">"Redmond 1"</span></span>|<span data-ttu-id="feff1-259">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="feff1-259">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="feff1-260">1</span><span class="sxs-lookup"><span data-stu-id="feff1-260">1</span></span>|<span data-ttu-id="feff1-261">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-261">sbc1.contoso.biz</span></span><br/><span data-ttu-id="feff1-262">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-262">sbc2.contoso.biz</span></span>|<span data-ttu-id="feff1-263">被呼叫方号码的活动路由 + 1 425 XXX XX XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="feff1-263">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="feff1-264">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="feff1-264">US and Canada</span></span>|<span data-ttu-id="feff1-265">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="feff1-265">"Redmond 2"</span></span>|<span data-ttu-id="feff1-266">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="feff1-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="feff1-267">2</span><span class="sxs-lookup"><span data-stu-id="feff1-267">2</span></span>|<span data-ttu-id="feff1-268">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-268">sbc3.contoso.biz</span></span><br/><span data-ttu-id="feff1-269">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-269">sbc4.contoso.biz</span></span>|<span data-ttu-id="feff1-270">被呼叫方号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="feff1-270">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="feff1-271">美国和加拿大</span><span class="sxs-lookup"><span data-stu-id="feff1-271">US and Canada</span></span>|<span data-ttu-id="feff1-272">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="feff1-272">"Other +1"</span></span>|<span data-ttu-id="feff1-273">^\\+ 1 （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="feff1-273">^\\+1(\d{10})$</span></span>|<span data-ttu-id="feff1-274">3</span><span class="sxs-lookup"><span data-stu-id="feff1-274">3</span></span>|<span data-ttu-id="feff1-275">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-275">sbc5.contoso.biz</span></span><br/><span data-ttu-id="feff1-276">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-276">sbc6.contoso.biz</span></span>|<span data-ttu-id="feff1-277">被呼叫方号码的路由 + 1 XXX XXX xx （除 + 1 425 XXX xx 或 + 1 206 XXX xx）</span><span class="sxs-lookup"><span data-stu-id="feff1-277">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="feff1-278">International</span><span class="sxs-lookup"><span data-stu-id="feff1-278">International</span></span>|<span data-ttu-id="feff1-279">International</span><span class="sxs-lookup"><span data-stu-id="feff1-279">International</span></span>|<span data-ttu-id="feff1-280">\d +</span><span class="sxs-lookup"><span data-stu-id="feff1-280">\d+</span></span>|<span data-ttu-id="feff1-281">4</span><span class="sxs-lookup"><span data-stu-id="feff1-281">4</span></span>|<span data-ttu-id="feff1-282">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-282">sbc2.contoso.biz</span></span><br/><span data-ttu-id="feff1-283">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="feff1-283">sbc5.contoso.biz</span></span>|<span data-ttu-id="feff1-284">任何数字模式的路由</span><span class="sxs-lookup"><span data-stu-id="feff1-284">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="feff1-285">语音路由策略中的 PSTN 用法的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="feff1-285">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="feff1-286">使用实例按顺序应用，如果在第一次使用中发现匹配项，则从不计算其他用法。</span><span class="sxs-lookup"><span data-stu-id="feff1-286">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="feff1-287">"国际" PSTN 使用必须位于 "美国和加拿大" PSTN 使用后。</span><span class="sxs-lookup"><span data-stu-id="feff1-287">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="feff1-288">若要更改 PSTN 用法的顺序，请运行`Set-CSOnlineVoiceRoutingPolicy`命令。</span><span class="sxs-lookup"><span data-stu-id="feff1-288">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="feff1-289">例如，若要将订单从 "美国和加拿大" 的第一个和 "国际" 的订单更改为反向顺序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="feff1-289">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="feff1-290">将自动分配 "其他 + 1" 和 "国际" 语音路由的优先级。</span><span class="sxs-lookup"><span data-stu-id="feff1-290">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="feff1-291">它们的优先级与 "Redmond 1" 和 "雷德蒙 2" 相比，不是很重要。</span><span class="sxs-lookup"><span data-stu-id="feff1-291">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="feff1-292">示例2：配置步骤</span><span class="sxs-lookup"><span data-stu-id="feff1-292">Example 2: Configuration steps</span></span>

<span data-ttu-id="feff1-293">以下示例显示了如何：</span><span class="sxs-lookup"><span data-stu-id="feff1-293">The following example shows how to:</span></span>

1. <span data-ttu-id="feff1-294">创建名为 "国际" 的新 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="feff1-294">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="feff1-295">创建名为 "国际" 的新语音路线。</span><span class="sxs-lookup"><span data-stu-id="feff1-295">Create a new voice route called International.</span></span>
3. <span data-ttu-id="feff1-296">创建名为 "无限制" 的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="feff1-296">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="feff1-297">将策略分配给用户 John 的一对用户。</span><span class="sxs-lookup"><span data-stu-id="feff1-297">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="feff1-298">你可以使用[Microsoft 团队管理中心](#admincenterexample2)或[PowerShell](#powershellexample2)执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="feff1-298">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="feff1-299">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="feff1-299">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="feff1-300">步骤1：创建 "国际" PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="feff1-300">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="feff1-301">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **直接路由**"，然后在右上角选择 "**管理 PSTN 使用情况记录**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-301">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="feff1-302">单击 "**添加**"，键入 "**国际**"，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-302">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="feff1-303">步骤2：创建 "国际" 语音路由</span><span class="sxs-lookup"><span data-stu-id="feff1-303">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="feff1-304">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **直接路由**"，然后选择 "**语音路由**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="feff1-304">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="feff1-305">单击 "**添加**"，输入 "国际" 作为名称，然后添加说明。</span><span class="sxs-lookup"><span data-stu-id="feff1-305">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="feff1-306">将 "优先级" 设置为 "4"，然后将 "拨打的号码" 模式设置为 "\d +"。</span><span class="sxs-lookup"><span data-stu-id="feff1-306">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="feff1-307">在 " **SBCs 注册（可选）**" 下，单击 "**添加 SBCs**"，选择 "sbc2.contoso.biz" 和 "sbc5.contoso.biz"，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-307">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="feff1-308">在 " **PSTN 使用记录（可选）**" 下，单击 "**添加 PSTN 使用情况**"，选择 "国际" PSTN 使用记录，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-308">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="feff1-309">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="feff1-309">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="feff1-310">步骤3：创建名为 "无限制" 的语音路由策略，并将 "美国和加拿大" 和 "国际" PSTN 使用情况添加到策略</span><span class="sxs-lookup"><span data-stu-id="feff1-310">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="feff1-311">PSTN 使用 "美国和加拿大" 将在此语音路由策略中重复使用，以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理，作为本地或本地呼叫。</span><span class="sxs-lookup"><span data-stu-id="feff1-311">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="feff1-312">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **语音路由策略**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-312">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="feff1-313">键入 "**无限制**" 作为名称并添加说明。</span><span class="sxs-lookup"><span data-stu-id="feff1-313">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="feff1-314">在 " **PSTN 使用记录**" 下，单击 "**添加 PSTN 使用情况**"，选择 "美国和加拿大" pstn 使用记录，然后选择 "国际" pstn 使用记录。</span><span class="sxs-lookup"><span data-stu-id="feff1-314">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="feff1-315">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="feff1-315">Click **Apply**.</span></span>

    <span data-ttu-id="feff1-316">记下 PSTN 用法的顺序：</span><span class="sxs-lookup"><span data-stu-id="feff1-316">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="feff1-317">如果对号码 "+ 1 425 XXX XX XX" 的调用与此示例中配置的用法相同，则呼叫将遵循 "美国和加拿大" 使用中设置的路由，并应用特殊路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="feff1-317">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="feff1-318">也就是说，将首先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由呼叫，然后 sbc3.contoso.biz 和 sbc4.contoso.biz 作为备份路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-318">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="feff1-319">如果 "国际" PSTN 使用早于 "美国和加拿大"，则对 + 1 425 XXX xx 的调用将作为路由逻辑的一部分路由到 sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="feff1-319">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="feff1-320">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="feff1-320">Click **Save**.</span></span>

<span data-ttu-id="feff1-321">若要了解详细信息，请参阅[管理语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="feff1-321">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="feff1-322">步骤4：将语音路由策略分配给名为 John 的的用户</span><span class="sxs-lookup"><span data-stu-id="feff1-322">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="feff1-323">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="feff1-323">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="feff1-324">单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-324">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="feff1-325">在 "**语音路由策略**" 下，选择 "无限制" 策略，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="feff1-325">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="feff1-326">结果是，应用到 John 54777 的语音政策不受限制，并且将遵循呼叫路由的逻辑，可用于美国、加拿大和国际通话。</span><span class="sxs-lookup"><span data-stu-id="feff1-326">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="feff1-327">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="feff1-327">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="feff1-328">步骤1：创建 "国际" PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="feff1-328">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="feff1-329">在 Skype for Business Online 中的远程 PowerShell 会话中，输入：</span><span class="sxs-lookup"><span data-stu-id="feff1-329">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="feff1-330">步骤2：创建名为 "国际" 的新语音路线</span><span class="sxs-lookup"><span data-stu-id="feff1-330">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="feff1-331">返回：</span><span class="sxs-lookup"><span data-stu-id="feff1-331">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="feff1-332">步骤3：创建名为 "无限制" 的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="feff1-332">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="feff1-333">PSTN 使用 "Redmond 1" 和 "Redmond" 在此语音路由策略中重复使用，以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理，作为本地或本地呼叫。</span><span class="sxs-lookup"><span data-stu-id="feff1-333">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="feff1-334">记下 PSTN 用法的顺序：</span><span class="sxs-lookup"><span data-stu-id="feff1-334">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="feff1-335">如果对数字 "+ 1 425 XXX XX XX" 的调用配置为以下示例中所示的使用实例，则呼叫将遵循 "美国和加拿大" 使用中设置的路由，并应用特殊路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="feff1-335">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="feff1-336">也就是说，将首先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由呼叫，然后 sbc3.contoso.biz 和 sbc4.contoso.biz 作为备份路由。</span><span class="sxs-lookup"><span data-stu-id="feff1-336">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="feff1-337">如果 "国际" PSTN 使用早于 "美国和加拿大"，则对 + 1 425 XXX xx 的调用将作为路由逻辑的一部分路由到 sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="feff1-337">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="feff1-338">输入命令：</span><span class="sxs-lookup"><span data-stu-id="feff1-338">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="feff1-339">返回：</span><span class="sxs-lookup"><span data-stu-id="feff1-339">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="feff1-340">步骤4：将语音路由策略分配给名为 John 的的用户</span><span class="sxs-lookup"><span data-stu-id="feff1-340">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="feff1-341">然后使用以下命令验证作业：</span><span class="sxs-lookup"><span data-stu-id="feff1-341">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="feff1-342">返回：</span><span class="sxs-lookup"><span data-stu-id="feff1-342">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="feff1-343">结果是，应用到 John 54777 的语音政策不受限制，并且将遵循可用于美国、加拿大和国际通话的呼叫路线逻辑。</span><span class="sxs-lookup"><span data-stu-id="feff1-343">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="feff1-344">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feff1-344">See also</span></span>

[<span data-ttu-id="feff1-345">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="feff1-345">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="feff1-346">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="feff1-346">Configure Direct Routing</span></span>](direct-routing-configure.md)
