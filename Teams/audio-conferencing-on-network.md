---
title: 音频会议的网络内会议
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
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 下面介绍音频会议的网络内开放预览版功能。
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637834"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="5eda8-103">打开音频会议网络会议预览版</span><span class="sxs-lookup"><span data-stu-id="5eda8-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="5eda8-104">网络会议开放预览版可供所有客户使用。</span><span class="sxs-lookup"><span data-stu-id="5eda8-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="5eda8-105">网络会议允许组织通过直接路由向 Microsoft 拨入号码发送入站和出站音频会议呼叫。</span><span class="sxs-lookup"><span data-stu-id="5eda8-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="5eda8-106">此功能不旨在将音频会议支持扩展到第三方拨入号码。</span><span class="sxs-lookup"><span data-stu-id="5eda8-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="5eda8-107">如果网络会议用于通过第三方拨入电话号码或 Microsoft 音频会议网桥的出站呼叫将入站呼叫路由到音频会议服务，则不支持网络会议。</span><span class="sxs-lookup"><span data-stu-id="5eda8-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="5eda8-108">本文介绍为组织启用网络会议所需的先决条件和配置步骤。</span><span class="sxs-lookup"><span data-stu-id="5eda8-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5eda8-109">不得使用印度的任何电话设备部署网络内会议。</span><span class="sxs-lookup"><span data-stu-id="5eda8-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="5eda8-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="5eda8-110">Prerequisites</span></span>

<span data-ttu-id="5eda8-111">在配置网络会议之前，请确保组织满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="5eda8-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="5eda8-112">确保组织中已启用或将启用音频会议的所有用户都Teams会议。</span><span class="sxs-lookup"><span data-stu-id="5eda8-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="5eda8-113">仅支持通过网络内会议进行入站和出站音频会议呼叫的路由，Teams会议。</span><span class="sxs-lookup"><span data-stu-id="5eda8-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="5eda8-114">将音频会议许可证分配给将使用网络内会议的所有用户。</span><span class="sxs-lookup"><span data-stu-id="5eda8-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="5eda8-115">设置音频会议服务。</span><span class="sxs-lookup"><span data-stu-id="5eda8-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="5eda8-116">有关其他信息，请参阅[为会议设置音频Microsoft Teams。](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5eda8-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="5eda8-117">为直接路由设置 SBC () 边界控制器。</span><span class="sxs-lookup"><span data-stu-id="5eda8-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="5eda8-118">有关其他信息，请参阅 [规划直接路由](direct-routing-plan.md) 和 [配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="5eda8-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="5eda8-119">如果您仅出于音频会议的目的设置直接路由，则对于网络会议，只需完成"步骤 1：连接 SBC"。</span><span class="sxs-lookup"><span data-stu-id="5eda8-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="5eda8-120">启用通过直接路由将拨入呼叫路由到 Microsoft 音频会议</span><span class="sxs-lookup"><span data-stu-id="5eda8-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="5eda8-121">若要通过直接路由将本地用户拨打的拨入呼叫路由到音频会议服务，需要为 SDC 和专用分支 Exchange ()  (PBX) 。</span><span class="sxs-lookup"><span data-stu-id="5eda8-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="5eda8-122">需要配置站点的电话设备，以通过直接路由中继将呼叫路由到组织会议网桥的任何服务号码。</span><span class="sxs-lookup"><span data-stu-id="5eda8-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="5eda8-123">可以在会议 **-> 会议** 网桥下的 Teams 管理中心中查找服务号码，或者使用 Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge 查找服务号码。</span><span class="sxs-lookup"><span data-stu-id="5eda8-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="5eda8-124">有关其他信息，请参阅音频会议[号码列表Microsoft Teams。](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5eda8-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5eda8-125">具有每分钟音频会议付费许可证的用户无法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="5eda8-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="5eda8-126">通过直接路由Teams会议拨出呼叫的路由</span><span class="sxs-lookup"><span data-stu-id="5eda8-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="5eda8-127">Teams会议拨出呼叫从您组织的会议内发起到 PSTN 号码，包括呼叫我电话和呼叫以将新参与者带到会议。</span><span class="sxs-lookup"><span data-stu-id="5eda8-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="5eda8-128">若要Teams通过直接路由向网络用户启用会议拨出路由，需要创建并分配名为"OnlineAudioConferencingRoutingPolicy"的音频会议路由策略。</span><span class="sxs-lookup"><span data-stu-id="5eda8-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="5eda8-129">OnlineAudioConferencingRoutingPolicy 策略等同于通过直接路由进行 1：1 PSTN 呼叫的 CsOnlineVoiceRoutingPolicy。</span><span class="sxs-lookup"><span data-stu-id="5eda8-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="5eda8-130">可以使用以下 cmdlet 管理 OnlineAudioConferencingRoutingPolicy 策略：</span><span class="sxs-lookup"><span data-stu-id="5eda8-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="5eda8-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="5eda8-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="5eda8-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="5eda8-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="5eda8-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="5eda8-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="5eda8-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="5eda8-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="5eda8-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="5eda8-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="5eda8-136">有关直接路由的路由详细信息，请参阅 [为直接路由配置语音路由](direct-routing-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="5eda8-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="5eda8-137">若要通过直接路由启用会议拨出呼叫的路由，需要：</span><span class="sxs-lookup"><span data-stu-id="5eda8-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="5eda8-138">配置音频会议路由策略</span><span class="sxs-lookup"><span data-stu-id="5eda8-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="5eda8-139">在组织的电话设备上配置路由</span><span class="sxs-lookup"><span data-stu-id="5eda8-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="5eda8-140"> (可选) 配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="5eda8-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="5eda8-141">来自会议Teams呼叫来自会议网桥上的默认服务号码。</span><span class="sxs-lookup"><span data-stu-id="5eda8-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="5eda8-142">有关音频会议网桥的默认服务号码的其他信息，请参阅更改音频会议网桥 [上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="5eda8-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="5eda8-143">配置音频会议路由策略</span><span class="sxs-lookup"><span data-stu-id="5eda8-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="5eda8-144">音频会议路由策略 OnlineAudioConferencingRoutingPolicy 确定将哪些会议拨出呼叫路由到直接路由中继。</span><span class="sxs-lookup"><span data-stu-id="5eda8-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="5eda8-145">如果熟悉 CsOnlineVoiceRoutingPolicy 策略，此策略的工作方式非常相似。</span><span class="sxs-lookup"><span data-stu-id="5eda8-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="5eda8-146">需要执行以下步骤来设置音频会议路由策略：</span><span class="sxs-lookup"><span data-stu-id="5eda8-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="5eda8-147">创建 PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="5eda8-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="5eda8-148">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="5eda8-148">Configure voice routes</span></span>
3.  <span data-ttu-id="5eda8-149">创建音频会议语音路由策略</span><span class="sxs-lookup"><span data-stu-id="5eda8-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="5eda8-150">向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="5eda8-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="5eda8-151">创建 PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="5eda8-151">Create PSTN usages</span></span>

<span data-ttu-id="5eda8-152">PSTN 用法是语音路由的集合。</span><span class="sxs-lookup"><span data-stu-id="5eda8-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="5eda8-153">当从给定组织者的会议发起拨出呼叫时，语音路由将用于根据通过用户的语音路由策略关联到用户的 PSTN 使用情况来确定呼叫的路由路径。</span><span class="sxs-lookup"><span data-stu-id="5eda8-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="5eda8-154">可以使用"Set-CsOnlinePstnUsage"cmdlet 创建 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="5eda8-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="5eda8-155">例如：</span><span class="sxs-lookup"><span data-stu-id="5eda8-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="5eda8-156">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="5eda8-156">Configure voice routes</span></span>

<span data-ttu-id="5eda8-157">语音路由确定 PSTN 网关，该网关应该用于根据从会议呼叫Teams电话号码路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="5eda8-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="5eda8-158">语音路由通过匹配从 Teams 会议拨打的电话号码与正则表达式模式来确定用于路由给定呼叫的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="5eda8-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="5eda8-159">创建语音路由时，该路由必须与一个或多个 PSTN 用法相关联。</span><span class="sxs-lookup"><span data-stu-id="5eda8-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="5eda8-160">可以使用"New-CsOnlineVoiceRoute"cmdlet 创建语音路由并定义要与语音路由关联的正则表达式和网关。</span><span class="sxs-lookup"><span data-stu-id="5eda8-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="5eda8-161">例如：</span><span class="sxs-lookup"><span data-stu-id="5eda8-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="5eda8-162">创建音频会议语音路由策略</span><span class="sxs-lookup"><span data-stu-id="5eda8-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="5eda8-163">音频会议语音路由策略根据会议拨出呼叫的目标电话号码，确定可用于路由源自组织者会议的呼叫的可能路由。</span><span class="sxs-lookup"><span data-stu-id="5eda8-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="5eda8-164">音频会议语音路由策略与一个或多个 PSTN 使用相关联，这反过来决定了可能尝试用于与该策略关联的组织者的会议拨出呼叫的路由。</span><span class="sxs-lookup"><span data-stu-id="5eda8-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="5eda8-165">可以使用"New- CsOnlineAudioConferencingRoutingPolicy"cmdlet 创建音频会议语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="5eda8-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="5eda8-166">例如：</span><span class="sxs-lookup"><span data-stu-id="5eda8-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="5eda8-167">将策略分配给用户后，当从用户的其中一个会议发起会议拨出呼叫时，将评估通过用户的语音路由策略关联到组织者的 PSTN 使用情况中的语音路由。</span><span class="sxs-lookup"><span data-stu-id="5eda8-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="5eda8-168">如果会议拨出呼叫目标与与组织者关联的其中一个语音路由中的正则表达式匹配，会议拨出呼叫将路由到语音路由中定义的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="5eda8-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="5eda8-169">如果会议拨出呼叫目标与与组织者关联的任何语音路由不匹配，则会议拨出呼叫由 Microsoft 路由。</span><span class="sxs-lookup"><span data-stu-id="5eda8-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="5eda8-170">向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="5eda8-170">Assign a policy to your users</span></span>

<span data-ttu-id="5eda8-171">定义音频会议路由策略后，现在可以将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="5eda8-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="5eda8-172">为它们分配策略后，将针对会议拨出呼叫进行评估，以确定其路由路径。</span><span class="sxs-lookup"><span data-stu-id="5eda8-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="5eda8-173">音频会议路由策略始终根据会议组织者进行评估，独立于发起会议拨出呼叫的会议用户。</span><span class="sxs-lookup"><span data-stu-id="5eda8-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="5eda8-174">可以使用"Grant-CsOnlineAudioConferencingRoutingPolicy"cmdlet 向用户分配音频会议语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="5eda8-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="5eda8-175">例如：</span><span class="sxs-lookup"><span data-stu-id="5eda8-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="5eda8-176">在组织的电话设备上配置路由</span><span class="sxs-lookup"><span data-stu-id="5eda8-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="5eda8-177">在组织的电话设备上，你需要确保通过直接路由路由的会议拨出呼叫路由到预期的网络目标。</span><span class="sxs-lookup"><span data-stu-id="5eda8-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="5eda8-178"> (可选) 配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="5eda8-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="5eda8-179">拨号计划是一组规范化规则，用于将单个用户拨打的电话号码转换为备用格式 (通常为 E.164) ，以便进行呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="5eda8-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="5eda8-180">默认情况下，Teams E.164 格式（即 + ）拨打 PSTN \<country code\> \<number\> 号码。</span><span class="sxs-lookup"><span data-stu-id="5eda8-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="5eda8-181">但是，拨号计划可用于允许用户以其他格式拨打电话号码，例如 4 位数分机号码。</span><span class="sxs-lookup"><span data-stu-id="5eda8-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="5eda8-182">如果要通过网络内会议启用基于分机的拨号，可以设置拨号计划，以将分机拨号模式与贵组织的电话号码范围相匹配。</span><span class="sxs-lookup"><span data-stu-id="5eda8-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="5eda8-183">若要设置拨号计划，请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="5eda8-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="5eda8-184">开放预览版中的已知问题</span><span class="sxs-lookup"><span data-stu-id="5eda8-184">Known issues in Open Preview</span></span>

<span data-ttu-id="5eda8-185">下面是网络会议开放预览版当前存在已知问题的列表。</span><span class="sxs-lookup"><span data-stu-id="5eda8-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="5eda8-186">Microsoft 正在努力解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="5eda8-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="5eda8-187">问题</span><span class="sxs-lookup"><span data-stu-id="5eda8-187">Issue</span></span> | <span data-ttu-id="5eda8-188">解决方法</span><span class="sxs-lookup"><span data-stu-id="5eda8-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="5eda8-189">通过网络会议路由的具有匿名/隐藏呼叫 ID 的拨入呼叫无法连接到会议。</span><span class="sxs-lookup"><span data-stu-id="5eda8-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="5eda8-190">如果可能，在 PBX 或 SBC 中设置配置，始终发送通过网络会议路由的呼叫的来电显示。</span><span class="sxs-lookup"><span data-stu-id="5eda8-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="5eda8-191">在某些情况下，当用户拨入服务时向用户播放的欢迎消息 ("欢迎使用音频会议服务...") 将被截断，用户不会听到"欢迎"一词。</span><span class="sxs-lookup"><span data-stu-id="5eda8-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="5eda8-192">目前没有此问题的解决方法。</span><span class="sxs-lookup"><span data-stu-id="5eda8-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="5eda8-193">相关主题</span><span class="sxs-lookup"><span data-stu-id="5eda8-193">Related topics</span></span>


