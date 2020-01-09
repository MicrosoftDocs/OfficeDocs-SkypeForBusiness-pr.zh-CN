---
title: 带有 GCCH 和 DoD 直接路由的音频会议
author: LanaChin
ms.author: v-lanac
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
localization_priority: Normal
description: 了解如何在 GCCH 和 DoD 环境中通过直接路由使用音频会议。
ms.openlocfilehash: 6c1403fedbbb47231780916eb8c7acb8014539e9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992892"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="bd680-103">适用于 GCC High 和 DoD 且含直接路由的音频会议</span><span class="sxs-lookup"><span data-stu-id="bd680-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="bd680-104">具有适用于 GCC 高和 DoD 的直接路由的音频会议使参与者能够使用电话设备加入您的 GCC 高或 DoD 组织中的团队会议。</span><span class="sxs-lookup"><span data-stu-id="bd680-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="bd680-105">会议参与者可能希望使用电话设备在方案中加入团队会议，例如，当 internet 连接受到限制或用户处于旅途中且无权访问团队时。</span><span class="sxs-lookup"><span data-stu-id="bd680-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don’t have access to Teams.</span></span> <span data-ttu-id="bd680-106">参与者可以通过拨入到组织的拨入电话号码或通过将会议拨出到电话设备来选择加入会议。</span><span class="sxs-lookup"><span data-stu-id="bd680-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="bd680-107">通过具有适用于 GCC 高和 DoD 的直接路由的音频会议，你的组织使用其自己的号码作为拨入电话号码，并且通过直接路由路由对电话设备的所有拨出会议。</span><span class="sxs-lookup"><span data-stu-id="bd680-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="bd680-108">若要启用该服务，组织需要设置直接路由和配置可用作拨入电话号码的电话号码。</span><span class="sxs-lookup"><span data-stu-id="bd680-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="bd680-109">使用直接路由的要求与向非 GCC 的高和非 DoD 组织提供的音频会议服务不同，电话拨入电话号码由 Microsoft 提供。</span><span class="sxs-lookup"><span data-stu-id="bd680-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="bd680-110">通过适用于 GCC 高和 DoD 的直接路由部署音频会议</span><span class="sxs-lookup"><span data-stu-id="bd680-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="bd680-111">步骤1：使用适用于 GCC 的高或 DoD 许可证的直接路由获得音频会议</span><span class="sxs-lookup"><span data-stu-id="bd680-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="bd680-112">若要在 GCC 高或 DoD 中使用音频会议，你的组织和组织中的用户需要具有分配了直接路由许可证的音频会议。</span><span class="sxs-lookup"><span data-stu-id="bd680-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="bd680-113">以下是使用适用于 GCC 高或 DoD 的直接路由启用音频会议所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="bd680-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="bd680-114">GCC 高：音频会议-适用于您的组织的 GCC 高租户许可证和音频会议-适用于您的用户的 GCC 高许可证。</span><span class="sxs-lookup"><span data-stu-id="bd680-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="bd680-115">DoD：针对你的组织和音频会议的 DoD 租户许可证-适用于你的用户的 dod 许可证。</span><span class="sxs-lookup"><span data-stu-id="bd680-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="bd680-116">启用服务需要租户许可证和至少一个用户许可证。</span><span class="sxs-lookup"><span data-stu-id="bd680-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="bd680-117">不能仅使用租户许可证或仅使用用户许可证启用服务。</span><span class="sxs-lookup"><span data-stu-id="bd680-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="bd680-118">若要为你的租户和组织中的用户获取服务许可证，请联系你的帐户团队。</span><span class="sxs-lookup"><span data-stu-id="bd680-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd680-119">在设置电话拨入式电话号码之前，不能通过直接路由为音频会议启用用户。</span><span class="sxs-lookup"><span data-stu-id="bd680-119">Users can’t be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="bd680-120">我们建议您不要向用户分配具有针对 GCC 高或 DoD 许可证的直接路由的音频会议，直到您按照本文所述设置电话拨入式电话号码。</span><span class="sxs-lookup"><span data-stu-id="bd680-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="bd680-121">步骤2：设置直接路由</span><span class="sxs-lookup"><span data-stu-id="bd680-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="bd680-122">若要设置直接路由，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="bd680-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="bd680-123">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="bd680-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="bd680-124">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="bd680-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="bd680-125">设置直接路由时，请记住使用特定于 GCC 的高或 DoD 特定的 Fqdn 和在这两个文章中介绍的端口。</span><span class="sxs-lookup"><span data-stu-id="bd680-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="bd680-126">步骤3：设置电话拨入式电话号码</span><span class="sxs-lookup"><span data-stu-id="bd680-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="bd680-127">电话拨入电话号码是与您的音频会议网桥相关联的电话号码。</span><span class="sxs-lookup"><span data-stu-id="bd680-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="bd680-128">参与者使用这些号码加入您的组织中的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="bd680-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="bd680-129">这些号码还包括在您的组织中安排会议的用户和 "查找本地号码" 页面上的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="bd680-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the “Find a local number” page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="bd680-130">在租户中定义服务电话号码</span><span class="sxs-lookup"><span data-stu-id="bd680-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="bd680-131">你可以使用 csHybridTelephoneNumber PowerShell cmdlet 定义租户中的服务电话号码，这些电话号码可用于通过直接路由将呼叫路由到音频会议服务。</span><span class="sxs-lookup"><span data-stu-id="bd680-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="bd680-132">例如：</span><span class="sxs-lookup"><span data-stu-id="bd680-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="bd680-133">将服务电话号码分配给组织的音频会议桥</span><span class="sxs-lookup"><span data-stu-id="bd680-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="bd680-134">你可以使用 Set-csonlinedialinconferencingservicenumber PowerShell cmdlet 将服务电话号码分配给你的组织的音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="bd680-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="bd680-135">你可以使用 Get-csonlinedialinconferencingbridge 查看音频会议桥的 ID。</span><span class="sxs-lookup"><span data-stu-id="bd680-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="bd680-136">例如：</span><span class="sxs-lookup"><span data-stu-id="bd680-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="bd680-137">步骤4：为你的用户分配适用于 GCC 的最高或 DoD 许可证的直接路由的音频会议</span><span class="sxs-lookup"><span data-stu-id="bd680-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="bd680-138">若要向你的用户分配适用于适用于 GCC 的适用于 GCC 或 DoD 许可证的直接路由的音频会议，请参阅[在 Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="bd680-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="bd680-139">步骤5：（可选）查看团队中的音频会议号码列表</span><span class="sxs-lookup"><span data-stu-id="bd680-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="bd680-140">若要查看您的组织的音频会议号码列表，请[参阅 Microsoft 团队中的音频会议号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bd680-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="bd680-141">步骤6：（可选）为你的组织的音频会议拨入号码设置自动助理语言</span><span class="sxs-lookup"><span data-stu-id="bd680-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="bd680-142">若要更改组织的音频会议拨入号码的语言，请参阅[在 Microsoft 团队中设置音频会议的自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bd680-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="bd680-143">步骤7：（可选）更改你的组织的音频会议桥的设置</span><span class="sxs-lookup"><span data-stu-id="bd680-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="bd680-144">若要更改组织的音频会议桥的设置，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="bd680-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="bd680-145">步骤8：（可选）设置你的组织中的用户的会议邀请中包含的电话号码</span><span class="sxs-lookup"><span data-stu-id="bd680-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="bd680-146">若要更改用户的会议邀请中包含的电话号码集，请参阅[设置 Microsoft 团队邀请中包含的电话](set-the-phone-numbers-included-on-invites-in-teams.md)号码</span><span class="sxs-lookup"><span data-stu-id="bd680-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="bd680-147">音频会议中不支持的音频会议功能，适用于 GCC 高和 DoD 的直接路由</span><span class="sxs-lookup"><span data-stu-id="bd680-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="bd680-148">以下是适用于 GCC 高和 DoD 直接路由的音频会议的音频会议功能：</span><span class="sxs-lookup"><span data-stu-id="bd680-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="bd680-149">使用名称录制进入和退出通知。</span><span class="sxs-lookup"><span data-stu-id="bd680-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="bd680-150">对于带有直接路由的音频会议，进入和退出通知将在会议中作为声音播放。</span><span class="sxs-lookup"><span data-stu-id="bd680-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="bd680-151">音频会议的出站呼叫限制策略。</span><span class="sxs-lookup"><span data-stu-id="bd680-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="bd680-152">限制出站呼叫的用户级控件不适用于通过直接路由路由的会议拨出呼叫。</span><span class="sxs-lookup"><span data-stu-id="bd680-152">User-level controls to restrict outbound calls aren’t applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="bd680-153">禁止会议特定组织者使用免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="bd680-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="bd680-154">限制免费号码的使用以限制您的组织的会议的用户级控件不适用于通过直接路由路由的呼叫。</span><span class="sxs-lookup"><span data-stu-id="bd680-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren’t applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="bd680-155">在用户的设置更改时向用户发送通知电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bd680-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="bd680-156">对于具有适用于 GCC 高和 DoD 的直接路由的音频会议，音频会议通知电子邮件不受支持。</span><span class="sxs-lookup"><span data-stu-id="bd680-156">Audio Conferencing notification emails aren’t supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
