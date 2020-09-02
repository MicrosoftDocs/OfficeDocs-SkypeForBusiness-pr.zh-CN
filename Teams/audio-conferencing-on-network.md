---
title: 音频会议的网络会议
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 以下介绍音频会议的开放预览功能。
ms.openlocfilehash: 3b33c67cc79f79d36cf2a11213dc934103b026fb
ms.sourcegitcommit: 19662d4bc4070f6031084d93e8794e0e02decd2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321785"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="b98eb-103">为音频会议打开网络会议预览</span><span class="sxs-lookup"><span data-stu-id="b98eb-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="b98eb-104">所有客户均可使用网络会议的开放预览。</span><span class="sxs-lookup"><span data-stu-id="b98eb-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="b98eb-105">网络会议允许组织通过直接路由向 Microsoft 拨入号码发送入站和出站音频会议呼叫。</span><span class="sxs-lookup"><span data-stu-id="b98eb-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="b98eb-106">此功能不用于将音频会议的支持扩展到第三方拨入号码。</span><span class="sxs-lookup"><span data-stu-id="b98eb-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="b98eb-107">如果网络会议用于通过第三方拨入电话号码将入站呼叫路由到音频会议服务，则不支持网络会议。</span><span class="sxs-lookup"><span data-stu-id="b98eb-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="b98eb-108">本文介绍为你的组织启用网络会议所需的先决条件和配置步骤。</span><span class="sxs-lookup"><span data-stu-id="b98eb-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b98eb-109">网络会议不得与印度的任何电话设备一起部署。</span><span class="sxs-lookup"><span data-stu-id="b98eb-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="b98eb-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="b98eb-110">Prerequisites</span></span>

<span data-ttu-id="b98eb-111">在配置网络会议之前，请确保你的组织满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="b98eb-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="b98eb-112">确保您的组织中启用或启用音频会议的所有用户都处于 "仅工作组" 模式。</span><span class="sxs-lookup"><span data-stu-id="b98eb-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are in Teams Only mode.</span></span> <span data-ttu-id="b98eb-113">只有团队会议才支持通过网络会议进行入站和 outboud 音频会议通话的路由。</span><span class="sxs-lookup"><span data-stu-id="b98eb-113">The routing of inbound and outboud Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="b98eb-114">将音频会议许可证分配给将使用网络会议的所有用户。</span><span class="sxs-lookup"><span data-stu-id="b98eb-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="b98eb-115">设置音频会议服务。</span><span class="sxs-lookup"><span data-stu-id="b98eb-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="b98eb-116">有关其他信息，请参阅 [为 Microsoft 团队设置音频会议](set-up-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b98eb-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="b98eb-117">设置会话边界控制器 (SBC) 直接路由。</span><span class="sxs-lookup"><span data-stu-id="b98eb-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="b98eb-118">有关其他信息，请参阅 [规划直接路由](direct-routing-plan.md) 和 [配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="b98eb-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="b98eb-119">如果仅为音频会议设置直接路由，则只需要完整的 "步骤1：连接 SBC" 即可进行网络会议。</span><span class="sxs-lookup"><span data-stu-id="b98eb-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="b98eb-120">通过直接路由支持将拨入呼叫路由到 Microsoft 音频会议</span><span class="sxs-lookup"><span data-stu-id="b98eb-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="b98eb-121">若要通过直接路由将本地用户拨打的拨入呼叫路由到音频会议服务，您需要为 SBCs 和专用分支 Exchange 配置适当的路由规则， (s)  (Pbx) 。</span><span class="sxs-lookup"><span data-stu-id="b98eb-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="b98eb-122">您需要配置您的站点的电话服务设备，通过直接路由主干将呼叫路由到您的组织的任何服务号码。</span><span class="sxs-lookup"><span data-stu-id="b98eb-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="b98eb-123">你可以在 "会议" 下的 "团队管理中心" 下找到服务号码 **> 会议桥** 或使用 Skype For Business Online PowerShell cmdlet get-csonlinedialinconferencingbridge。</span><span class="sxs-lookup"><span data-stu-id="b98eb-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="b98eb-124">有关其他信息，请参阅 [Microsoft 团队中的音频会议号码](see-a-list-of-audio-conferencing-numbers-in-teams.md)列表。</span><span class="sxs-lookup"><span data-stu-id="b98eb-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>


## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="b98eb-125">通过直接路由启用团队的路由会议拨出呼叫</span><span class="sxs-lookup"><span data-stu-id="b98eb-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="b98eb-126">从组织中的会议开始拨出呼叫的团队将从您的组织内的某个会议开始，包括呼叫我的呼叫和呼叫，并将新参与者加入会议。</span><span class="sxs-lookup"><span data-stu-id="b98eb-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="b98eb-127">若要通过直接路由启用团队会议拨出路由，你需要创建并分配一个名为 "OnlineAudioConferencingRoutingPolicy" 的音频会议路由策略。</span><span class="sxs-lookup"><span data-stu-id="b98eb-127">To enable Teams meeting dial-out routing through Direct Routing, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="b98eb-128">OnlineAudioConferencingRoutingPolicy 策略等效于 CsOnlineVoiceRoutingPolicy 通过直接路由进行的 1:1 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="b98eb-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="b98eb-129">可以使用以下 cmdlet 管理 OnlineAudioConferencingRoutingPolicy 策略：</span><span class="sxs-lookup"><span data-stu-id="b98eb-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="b98eb-130">新-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b98eb-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b98eb-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b98eb-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b98eb-132">CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b98eb-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b98eb-133">授权-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b98eb-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b98eb-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b98eb-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="b98eb-135">有关路由选择直接路由的详细信息，请参阅 [为直接路由配置语音路由](direct-routing-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="b98eb-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="b98eb-136">若要通过直接路由启用会议拨出呼叫的路由，您需要：</span><span class="sxs-lookup"><span data-stu-id="b98eb-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="b98eb-137">配置音频会议路由策略</span><span class="sxs-lookup"><span data-stu-id="b98eb-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="b98eb-138">在组织的电话服务设备上配置路由</span><span class="sxs-lookup"><span data-stu-id="b98eb-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="b98eb-139"> (可选) 配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="b98eb-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="b98eb-140">来自团队会议的拨出呼叫来自会议网桥上的默认服务号码。</span><span class="sxs-lookup"><span data-stu-id="b98eb-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="b98eb-141">有关音频会议桥的默认服务号码的其他信息，请参阅 [在音频会议网桥上更改电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="b98eb-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="b98eb-142">配置音频会议路由策略</span><span class="sxs-lookup"><span data-stu-id="b98eb-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="b98eb-143">音频会议路由策略 OnlineAudioConferencingRoutingPolicy 确定将哪些会议拨出呼叫路由到直接路由中继。</span><span class="sxs-lookup"><span data-stu-id="b98eb-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="b98eb-144">如果你熟悉 CsOnlineVoiceRoutingPolicy 策略，此策略的工作方式非常类似。</span><span class="sxs-lookup"><span data-stu-id="b98eb-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="b98eb-145">设置音频会议路由策略需要以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b98eb-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="b98eb-146">创建 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="b98eb-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="b98eb-147">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="b98eb-147">Configure voice routes</span></span>
3.  <span data-ttu-id="b98eb-148">创建音频会议语音路由策略</span><span class="sxs-lookup"><span data-stu-id="b98eb-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="b98eb-149">为你的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b98eb-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="b98eb-150">创建 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="b98eb-150">Create PSTN usages</span></span>

<span data-ttu-id="b98eb-151">PSTN 用法是语音路由的集合。</span><span class="sxs-lookup"><span data-stu-id="b98eb-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="b98eb-152">从给定组织者的会议启动拨出呼叫时，将使用语音路由基于通过用户的语音路由策略与用户关联的 PSTN 用法确定呼叫的路由路径。</span><span class="sxs-lookup"><span data-stu-id="b98eb-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="b98eb-153">你可以使用 "CsOnlinePstnUsage" cmdlet 创建 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="b98eb-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="b98eb-154">例如：</span><span class="sxs-lookup"><span data-stu-id="b98eb-154">For Example:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="b98eb-155">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="b98eb-155">Configure voice routes</span></span>

<span data-ttu-id="b98eb-156">语音路由根据从团队会议中拨出的电话号码确定应用于路由呼叫的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="b98eb-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="b98eb-157">语音路由通过匹配使用 regex 模式的团队会议所拨的电话号码，确定应用于路由给定呼叫的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="b98eb-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="b98eb-158">创建语音路由时，路由必须与一个或多个 PSTN 使用实例相关联。</span><span class="sxs-lookup"><span data-stu-id="b98eb-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="b98eb-159">你可以使用 "CsOnlineVoiceRoute" cmdlet 创建语音路由，并定义要与语音路由关联的 regex 和网关。</span><span class="sxs-lookup"><span data-stu-id="b98eb-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="b98eb-160">例如：</span><span class="sxs-lookup"><span data-stu-id="b98eb-160">For Example:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="b98eb-161">创建音频会议语音路由策略</span><span class="sxs-lookup"><span data-stu-id="b98eb-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="b98eb-162">音频会议语音路由策略确定可能的路由，可用于根据会议拨出呼叫的目标电话号码传送来自组织者会议的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b98eb-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="b98eb-163">音频会议语音路由策略与一个或多个 PSTN 用途相关联，后者随后确定可能尝试用于与策略关联的组织者拨出呼叫的可能路线。</span><span class="sxs-lookup"><span data-stu-id="b98eb-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="b98eb-164">可以使用 "CsOnlineAudioConferencingRoutingPolicy" cmdlet 创建音频会议语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="b98eb-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="b98eb-165">例如：</span><span class="sxs-lookup"><span data-stu-id="b98eb-165">For Example:</span></span>

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b98eb-166">将策略分配给用户并从用户的其中一个会议中启动会议拨出呼叫时，将评估 PSTN 使用中通过用户的语音路由策略关联到组织者的语音路由。</span><span class="sxs-lookup"><span data-stu-id="b98eb-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="b98eb-167">如果会议拨出呼叫目标与与管理器关联的某个语音路由中的 regex 匹配，则会议拨出呼叫将路由到在语音路由中定义的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="b98eb-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="b98eb-168">如果会议拨出呼叫目标与与组织者关联的任何语音路由都不匹配，则由 Microsoft 发送会议拨出呼叫。</span><span class="sxs-lookup"><span data-stu-id="b98eb-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="b98eb-169">为你的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b98eb-169">Assign a policy to your users</span></span>

<span data-ttu-id="b98eb-170">定义音频会议路由策略后，您现在可以将它们分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b98eb-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="b98eb-171">向其分配策略后，将对会议拨出呼叫进行评估，以确定其路由路径。</span><span class="sxs-lookup"><span data-stu-id="b98eb-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="b98eb-172">音频会议路由策略始终基于会议的组织者（独立于会议中启动会议拨出呼叫的用户）进行评估。</span><span class="sxs-lookup"><span data-stu-id="b98eb-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="b98eb-173">可以使用 "授权-CsOnlineAudioConferencingRoutingPolicy" cmdlet 将音频会议语音路由策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b98eb-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="b98eb-174">例如：</span><span class="sxs-lookup"><span data-stu-id="b98eb-174">For example:</span></span>

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="b98eb-175">在组织的电话服务设备上配置路由</span><span class="sxs-lookup"><span data-stu-id="b98eb-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="b98eb-176">在你的组织的电话服务设备上，你需要确保通过直接路由路由的会议拨出呼叫路由到目标目标。</span><span class="sxs-lookup"><span data-stu-id="b98eb-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="b98eb-177"> (可选) 配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="b98eb-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="b98eb-178">拨号计划是一组规范化规则，将已拨打的电话号码由单个用户转换为备用格式 (通常是) ，以供呼叫授权和呼叫路由使用。</span><span class="sxs-lookup"><span data-stu-id="b98eb-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="b98eb-179">默认情况下，团队用户可以采用 E：164格式拨出到 PSTN 号码，即 + \<country code\> \<number\> 。</span><span class="sxs-lookup"><span data-stu-id="b98eb-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="b98eb-180">但是，拨号计划可用于允许用户以其他格式拨打电话号码，例如4位数的分机号码。</span><span class="sxs-lookup"><span data-stu-id="b98eb-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="b98eb-181">如果想要通过网络会议启用基于扩展的拨号，可以将拨号计划设置为与 "分机" 拨号模式匹配，使其与您的组织的电话号码区域的电话号码范围相匹配。</span><span class="sxs-lookup"><span data-stu-id="b98eb-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="b98eb-182">若要设置拨号计划，请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="b98eb-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="b98eb-183">打开预览中的已知问题</span><span class="sxs-lookup"><span data-stu-id="b98eb-183">Known issues in Open Preview</span></span>

<span data-ttu-id="b98eb-184">以下是当前在网络会议的开放式预览版中当前存在的已知问题的列表。</span><span class="sxs-lookup"><span data-stu-id="b98eb-184">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="b98eb-185">Microsoft 正在努力解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="b98eb-185">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="b98eb-186">问题</span><span class="sxs-lookup"><span data-stu-id="b98eb-186">Issue</span></span> | <span data-ttu-id="b98eb-187">规避</span><span class="sxs-lookup"><span data-stu-id="b98eb-187">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="b98eb-188">通过网络会议路由的匿名/隐藏呼叫方 Id 的拨入呼叫无法连接到会议。</span><span class="sxs-lookup"><span data-stu-id="b98eb-188">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="b98eb-189">如果可能，请将 PBX 或 SBC 中的配置设置为始终发送呼叫者 ID，以便通过网络会议路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="b98eb-189">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="b98eb-190">在某些情况下，当用户拨入服务时，向用户播放的欢迎消息 ( "欢迎使用音频会议服务 ..." ) 被截断，并且用户听不到 "欢迎" word。</span><span class="sxs-lookup"><span data-stu-id="b98eb-190">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="b98eb-191">目前尚无此问题的解决方法。</span><span class="sxs-lookup"><span data-stu-id="b98eb-191">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="b98eb-192">相关主题</span><span class="sxs-lookup"><span data-stu-id="b98eb-192">Related topics</span></span>


