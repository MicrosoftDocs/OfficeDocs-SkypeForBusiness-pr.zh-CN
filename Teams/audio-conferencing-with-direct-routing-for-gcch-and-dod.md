---
title: 使用直接路由、GCCH 和 DoD 的音频会议
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: 管理员可以了解如何在 GCCH 和 DoD 环境中通过直接路由使用音频会议。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 84f2789c6d4f4e9c5446ad39d6f2d50d842b92a6
ms.sourcegitcommit: 0a7c1f52484452f66f678b0feca1455bade4fcf3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "50716927"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="15a4b-103">适用于 GCC High 和 DoD 且含直接路由的音频会议</span><span class="sxs-lookup"><span data-stu-id="15a4b-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="15a4b-104">具有直接路由的 GCC High 和 DoD 的音频会议使参与者能够使用电话设备加入 GCC High 或 DoD 组织中 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="15a4b-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="15a4b-105">在 Internet 连接受限或用户正在路况中且无法访问 Teams 等情况下，会议参与者可能希望使用电话设备加入 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="15a4b-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="15a4b-106">参与者可以通过拨入组织的拨入电话号码或让会议拨出到其电话设备来选择加入会议。</span><span class="sxs-lookup"><span data-stu-id="15a4b-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="15a4b-107">借助具有 GCC High 和 DoD 直接路由的音频会议，您的组织使用自己的号码作为拨入电话号码，并且通过直接路由路由到电话设备的所有会议拨出。</span><span class="sxs-lookup"><span data-stu-id="15a4b-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="15a4b-108">若要启用该服务，组织需要设置直接路由并配置可用作拨入电话号码的电话号码。</span><span class="sxs-lookup"><span data-stu-id="15a4b-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="15a4b-109">使用直接路由的要求不同于提供给非 GCC High 和非 DoD 组织的音频会议服务，其中拨入电话号码由 Microsoft 提供。</span><span class="sxs-lookup"><span data-stu-id="15a4b-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="15a4b-110">使用直接路由为 GCC High 和 DoD 部署音频会议</span><span class="sxs-lookup"><span data-stu-id="15a4b-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="15a4b-111">步骤 1：使用 GCC High 或 DoD 许可证的直接路由获取音频会议</span><span class="sxs-lookup"><span data-stu-id="15a4b-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="15a4b-112">若要在 GCC High 或 DoD 中使用音频会议，您的组织和组织中用户需要分配有具有直接路由许可证的音频会议。</span><span class="sxs-lookup"><span data-stu-id="15a4b-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="15a4b-113">以下是使用直接路由为 GCC High 或 DoD 启用音频会议所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="15a4b-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="15a4b-114">GCC 高：音频会议 - 组织的 GCC 高租户许可证和音频会议 - 用户的 GCC 高许可证。</span><span class="sxs-lookup"><span data-stu-id="15a4b-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="15a4b-115">DoD：音频会议 - 组织的 DoD 租户许可证和音频会议 - 用户的 DoD 许可证。</span><span class="sxs-lookup"><span data-stu-id="15a4b-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="15a4b-116">启用该服务需要租户许可证和至少一个用户许可证。</span><span class="sxs-lookup"><span data-stu-id="15a4b-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="15a4b-117">不能仅启用租户许可证或仅具有用户许可证的服务。</span><span class="sxs-lookup"><span data-stu-id="15a4b-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="15a4b-118">若要获取租户和组织中用户的服务许可证，请联系帐户团队。</span><span class="sxs-lookup"><span data-stu-id="15a4b-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15a4b-119">在设置拨入电话号码并且用户在 Teams 客户端中具有工作拨号盘之前，无法为具有直接路由的音频会议启用用户。</span><span class="sxs-lookup"><span data-stu-id="15a4b-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up and users have a working dial pad in their Teams client.</span></span> <span data-ttu-id="15a4b-120">建议在按本文所述设置拨入电话号码之前，不要向用户分配具有直接路由的 GCC 高或 DoD 许可证的音频会议。</span><span class="sxs-lookup"><span data-stu-id="15a4b-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="15a4b-121">步骤 2：设置直接路由</span><span class="sxs-lookup"><span data-stu-id="15a4b-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="15a4b-122">若要设置直接路由，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="15a4b-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="15a4b-123">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="15a4b-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="15a4b-124">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="15a4b-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="15a4b-125">设置直接路由时，请记住使用这两篇文章中所述的 GCC High 或 DoD 特定的 FQDN 和端口。</span><span class="sxs-lookup"><span data-stu-id="15a4b-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="15a4b-126">步骤 3：设置拨入电话号码</span><span class="sxs-lookup"><span data-stu-id="15a4b-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="15a4b-127">拨入电话号码是关联到音频会议网桥的电话号码。</span><span class="sxs-lookup"><span data-stu-id="15a4b-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="15a4b-128">参与者使用这些数字加入组织中用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="15a4b-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="15a4b-129">在组织中安排会议的用户的会议邀请和"查找本地号码"页面上也包含这些数字。</span><span class="sxs-lookup"><span data-stu-id="15a4b-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="15a4b-130">在租户中定义服务电话号码</span><span class="sxs-lookup"><span data-stu-id="15a4b-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="15a4b-131">可以使用 New-csHybridTelephoneNumber PowerShell cmdlet 在你的租户中定义可用于通过直接路由将呼叫路由到音频会议服务的服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="15a4b-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="15a4b-132">例如：</span><span class="sxs-lookup"><span data-stu-id="15a4b-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="15a4b-133">将服务电话号码分配给组织的音频会议网桥</span><span class="sxs-lookup"><span data-stu-id="15a4b-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="15a4b-134">可以使用 Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet 将服务电话号码分配给组织的音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="15a4b-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="15a4b-135">可以使用 Get-CsOnlineDialInConferencingBridge 查看音频会议网桥的 ID。</span><span class="sxs-lookup"><span data-stu-id="15a4b-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="15a4b-136">例如：</span><span class="sxs-lookup"><span data-stu-id="15a4b-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="15a4b-137">步骤 4：定义全局语音路由策略，以便从会议路由出站呼叫</span><span class="sxs-lookup"><span data-stu-id="15a4b-137">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="15a4b-138">从组织中用户组织的会议向 PSTN 拨打的出站呼叫的路由由组织的全局语音路由策略定义。</span><span class="sxs-lookup"><span data-stu-id="15a4b-138">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="15a4b-139">如果组织定义了全局语音路由策略，请验证全局语音路由策略是否允许从组织中用户组织的会议发起的 PSTN 出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="15a4b-139">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="15a4b-140">如果组织未定义全局语音路由策略，则需要定义一个策略，以便从组织中用户组织的会议中将出站呼叫路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="15a4b-140">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="15a4b-141">请注意，组织的全局语音路由策略也适用于组织中用户对 PSTN 的一对一呼叫。</span><span class="sxs-lookup"><span data-stu-id="15a4b-141">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="15a4b-142">如果为贵组织的用户启用了对 PSTN 的一对一呼叫，请确保全局语音路由策略满足组织对两种类型的呼叫的需求。</span><span class="sxs-lookup"><span data-stu-id="15a4b-142">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="15a4b-143">Location-Based在 Microsoft 365 政府社区云和 GCC (高级或 DoD) 中不可用。</span><span class="sxs-lookup"><span data-stu-id="15a4b-143">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="15a4b-144">启用音频会议时，请验证 GCC High 中未启用音频会议用户或 DoD 环境中是否启用了Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="15a4b-144">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="15a4b-145">定义全局语音路由策略</span><span class="sxs-lookup"><span data-stu-id="15a4b-145">Defining a global voice routing policy</span></span>

<span data-ttu-id="15a4b-146">可以通过定义 PSTN 使用情况、语音路由、语音路由策略和分配新的语音路由策略作为组织的全局语音路由策略来定义全局语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="15a4b-146">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="15a4b-147">以下步骤介绍了如何为组织定义新的全局语音路由策略（不带策略）。</span><span class="sxs-lookup"><span data-stu-id="15a4b-147">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="15a4b-148">如果组织已定义语音路由策略，请验证以下配置是否不与组织的现有语音路由策略冲突。</span><span class="sxs-lookup"><span data-stu-id="15a4b-148">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="15a4b-149">若要在 Skype for Business Online 的远程 PowerShell 会话中创建新的 PSTN 使用情况，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="15a4b-149">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="15a4b-150">有关详细信息，请参阅[Set-CsOnlinePstnUsage。](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)</span><span class="sxs-lookup"><span data-stu-id="15a4b-150">For additional information, see [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="15a4b-151">若要创建新的语音路由，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="15a4b-151">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="15a4b-152">为组织定义新的语音路由时，请指定在配置直接路由期间为组织定义的一个或多个 PSTN 联机 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="15a4b-152">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="15a4b-153">号码模式根据呼叫的目标电话号码，指定将通过指定的网关列表路由哪些呼叫。</span><span class="sxs-lookup"><span data-stu-id="15a4b-153">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="15a4b-154">在以上示例中，对世界上任何目的地的调用都将与语音路由匹配。</span><span class="sxs-lookup"><span data-stu-id="15a4b-154">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="15a4b-155">如果要限制可以从组织中用户的会议拨打的电话号码，可以更改号码模式，使语音路由仅与允许的目标号码模式匹配。</span><span class="sxs-lookup"><span data-stu-id="15a4b-155">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="15a4b-156">请注意，如果没有与给定呼叫的目标电话号码的号码模式匹配的语音路由，将不会路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="15a4b-156">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="15a4b-157">有关详细信息，请参阅[New-CsOnlineVoiceRoute。](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)</span><span class="sxs-lookup"><span data-stu-id="15a4b-157">For additional information, see [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="15a4b-158">若要创建新的语音路由策略，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="15a4b-158">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="15a4b-159">如果在语音路由策略中定义了多个 PSTN 使用情况，将按照定义的顺序评估这些 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="15a4b-159">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="15a4b-160">建议根据与 PSTN 用法关联的语音路由的数量模式，按照最具体、更通用的顺序定义 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="15a4b-160">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="15a4b-161">例如，如果定义了 PSTN 使用情况以将呼叫路由到美国，并且定义了另一个 PSTN 使用情况以将呼叫路由到世界上任何其他位置，那么在 PSTN 使用将呼叫路由到世界上任何其他位置之前，应先在语音路由策略中列出美国呼叫的 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="15a4b-161">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="15a4b-162">有关详细信息，请参阅[New-CsOnlineVoiceRoutingPolicy。](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="15a4b-162">For additional information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="15a4b-163">若要将新的语音路由分配到组织的全局语音路由策略，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="15a4b-163">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="15a4b-164">有关详细信息，请参阅[Grant-CsOnlineVoiceRoutingPolicy。](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="15a4b-164">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="15a4b-165">定义全局语音路由策略后，将针对与全局语音路由策略的 PSTN 用法关联的语音路由，对组织中用户组织的会议进行的任何出站呼叫进行评估。</span><span class="sxs-lookup"><span data-stu-id="15a4b-165">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="15a4b-166">出站呼叫将按照与拨号电话号码的号码模式匹配的第一个语音路由进行路由。</span><span class="sxs-lookup"><span data-stu-id="15a4b-166">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="15a4b-167">步骤 5：使用直接路由为用户分配具有 GCC High 或 DoD 许可证的音频会议</span><span class="sxs-lookup"><span data-stu-id="15a4b-167">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="15a4b-168">若要为用户分配具有直接路由的音频会议，以便 GCC 高或 DoD 许可证，请参阅"向[用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="15a4b-168">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="15a4b-169">步骤 6： (可选) 查看 Teams 中的音频会议号码列表</span><span class="sxs-lookup"><span data-stu-id="15a4b-169">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="15a4b-170">若要查看组织的音频会议号码列表，请转到 Microsoft Teams 中的音频会议 [号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="15a4b-170">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="15a4b-171">步骤 7： (可选) 为贵组织的音频会议拨入号码设置自动助理语言</span><span class="sxs-lookup"><span data-stu-id="15a4b-171">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="15a4b-172">若要更改组织的音频会议拨入号码的语言，请参阅"在 Microsoft Teams 中为音频会议设置[自动助理语言"。](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="15a4b-172">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="15a4b-173">步骤 8： (可选) 更改组织的音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="15a4b-173">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="15a4b-174">若要更改组织的音频会议网桥的设置，请参阅"更改音频[会议网桥的设置"。](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="15a4b-174">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="15a4b-175">步骤 9： (可选) 设置组织中用户的会议邀请中包含的电话号码</span><span class="sxs-lookup"><span data-stu-id="15a4b-175">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="15a4b-176">若要更改用户的会议邀请中包含的电话号码集，请参阅"设置 Microsoft Teams 中的邀请中包含的电话号码["。](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="15a4b-176">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="15a4b-177">音频会议功能在具有直接路由的 GCC High 和 DoD 音频会议中不受支持</span><span class="sxs-lookup"><span data-stu-id="15a4b-177">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="15a4b-178">以下是音频会议功能，对于 GCC High 和 DoD，使用直接路由的音频会议不支持这些功能：</span><span class="sxs-lookup"><span data-stu-id="15a4b-178">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="15a4b-179">使用名称录制的进入和退出通知。</span><span class="sxs-lookup"><span data-stu-id="15a4b-179">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="15a4b-180">对于具有直接路由的音频会议，进入和退出通知在会议中以音调播放。</span><span class="sxs-lookup"><span data-stu-id="15a4b-180">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="15a4b-181">音频会议出站呼叫限制策略。</span><span class="sxs-lookup"><span data-stu-id="15a4b-181">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="15a4b-182">用于限制出站呼叫的用户级控件不适用于通过直接路由路由的会议拨出呼叫。</span><span class="sxs-lookup"><span data-stu-id="15a4b-182">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="15a4b-183">禁止对会议特定组织者使用免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="15a4b-183">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="15a4b-184">限制使用免费电话号码加入组织会议的用户级控制不适用于通过直接路由路由的呼叫。</span><span class="sxs-lookup"><span data-stu-id="15a4b-184">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="15a4b-185">当用户的设置更改时，向用户发送通知电子邮件。</span><span class="sxs-lookup"><span data-stu-id="15a4b-185">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="15a4b-186">音频会议通知电子邮件不支持使用直接路由进行 GCC High 和 DoD 的音频会议。</span><span class="sxs-lookup"><span data-stu-id="15a4b-186">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
