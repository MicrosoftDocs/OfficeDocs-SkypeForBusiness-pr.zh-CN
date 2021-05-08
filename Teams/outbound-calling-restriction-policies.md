---
title: 出站呼叫限制 - 音频会议& PSTN 呼叫
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 管理员可以控制音频会议和最终用户 PSTN 的呼叫可以由用户所做的类型。
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908651"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="a1661-103">音频会议和用户 PSTN 通话的出站通话限制策略</span><span class="sxs-lookup"><span data-stu-id="a1661-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="a1661-104">作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="a1661-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="a1661-105">出站通话控件可以应用基于每个用户，并提供了下列两个控件，以便独立限制每种类型的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1661-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="a1661-106">默认情况下，这两个控件设置为允许国际和国内出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1661-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="a1661-107">控件</span><span class="sxs-lookup"><span data-stu-id="a1661-107">Control</span></span>|<span data-ttu-id="a1661-108">说明</span><span class="sxs-lookup"><span data-stu-id="a1661-108">Description</span></span>|<span data-ttu-id="a1661-109">控件选项</span><span class="sxs-lookup"><span data-stu-id="a1661-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a1661-110">音频会议 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="a1661-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="a1661-111">限制出站类型</span><span class="sxs-lookup"><span data-stu-id="a1661-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="a1661-112">允许从用户组织</span><span class="sxs-lookup"><span data-stu-id="a1661-112">calls that are allowed from within</span></span> </br><span data-ttu-id="a1661-113">的会议内呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1661-113">meetings organized by a user.</span></span>|<span data-ttu-id="a1661-114">任何目标 (默认) </span><span class="sxs-lookup"><span data-stu-id="a1661-114">Any destination (default)</span></span></br><span data-ttu-id="a1661-115">与组织者在同一国家/地区</span><span class="sxs-lookup"><span data-stu-id="a1661-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="a1661-116">[仅区域 A 国家/地区](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="a1661-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="a1661-117">不允许</span><span class="sxs-lookup"><span data-stu-id="a1661-117">Don't allow</span></span>|
|<span data-ttu-id="a1661-118">最终用户 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="a1661-118">End user PSTN calls</span></span>|<span data-ttu-id="a1661-119">限制可以由用户</span><span class="sxs-lookup"><span data-stu-id="a1661-119">Restricts the type of calls</span></span> </br><span data-ttu-id="a1661-120">拨打的呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="a1661-120">that can be made by a user.</span></span>|<span data-ttu-id="a1661-121">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="a1661-121">International and Domestic (default)</span></span></br><span data-ttu-id="a1661-122">国内</span><span class="sxs-lookup"><span data-stu-id="a1661-122">Domestic</span></span></br><span data-ttu-id="a1661-123">无</span><span class="sxs-lookup"><span data-stu-id="a1661-123">None</span></span>|

<span data-ttu-id="a1661-124">若要了解哪些国家和地区被视为区域 A，请参阅音频会议 [的国家和地区区域](audio-conferencing-zones.md)。</span><span class="sxs-lookup"><span data-stu-id="a1661-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="a1661-125">如果拨打的号码位于为会议组织者设置了 Microsoft 365 或 Office 365 的国家/地区（对于音频会议 () ）或最终用户 (（对于最终用户 PSTN 呼叫) ）来说，呼叫被视为国内呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1661-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="a1661-126">限制音频会议出站呼叫</span><span class="sxs-lookup"><span data-stu-id="a1661-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="a1661-127">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="a1661-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a1661-128">在左侧导航栏中，单击 **"用户**"，显示名称可用用户列表中的用户名称。</span><span class="sxs-lookup"><span data-stu-id="a1661-128">In the left navigation, click **Users**, and then click the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="a1661-129">在 **音频会议** 旁边，单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="a1661-129">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="a1661-130">在 **"从会议拨出"** 下，选择你需要的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="a1661-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="a1661-131">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a1661-131">Click **Save**.</span></span> 

<span data-ttu-id="a1661-132">![显示 Skype for Business 徽标的图标](media/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="a1661-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="a1661-133">在 **Skype for Business** 管理中心的 左侧导航中，转到"音频会议用户"，然后从可用  >  用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="a1661-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a1661-134">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a1661-134">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="a1661-135">在 **限制此用户从会议拨出** 下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="a1661-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![拨出选项限制](media/restrictions-to-dial-outs.png)
      

4. <span data-ttu-id="a1661-137">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a1661-137">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="a1661-138">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a1661-138">**Using PowerShell**</span></span>

<span data-ttu-id="a1661-139">出站呼叫限制由名为 OnlineDialOutPolicy 的单个策略控制，其中每个都有一个限制属性。</span><span class="sxs-lookup"><span data-stu-id="a1661-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="a1661-140">无法自定义策略，而是为每个设置组织使用预定义策略实例。</span><span class="sxs-lookup"><span data-stu-id="a1661-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="a1661-141">Get CSOnlineDialOutPolicy cmdlet 可用于查看出站呼叫策略并使用 CSDialOutPolicy cmdlet 将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a1661-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="a1661-142"> (请注意，Grant cmdlet 不包含"Online"一词，就像 Get cmdlet 一样) </span><span class="sxs-lookup"><span data-stu-id="a1661-142">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="a1661-143">下表概述了每个策略。</span><span class="sxs-lookup"><span data-stu-id="a1661-143">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a1661-144">标识='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a1661-144">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="a1661-145">参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="a1661-145">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="a1661-146">标识='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a1661-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="a1661-147">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="a1661-147">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="a1661-148">标识='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a1661-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="a1661-149">参加会议的用户无法进行任何拨出。此用户可以出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="a1661-149">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="a1661-150">标识='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a1661-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="a1661-151">参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="a1661-151">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="a1661-152">标识='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a1661-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="a1661-153">参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="a1661-153">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="a1661-154">标识='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a1661-154">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="a1661-155">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="a1661-155">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="a1661-156">标识='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a1661-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="a1661-157">参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="a1661-157">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="a1661-158">标识='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a1661-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="a1661-159">参加会议的用户无法进行任何拨出，同时此用户仅可出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="a1661-159">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="a1661-160">标识='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a1661-160">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="a1661-161">参加会议的用户无法拨打任何号码，同时此用户无法出站呼叫  PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="a1661-161">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="a1661-162">Identity='tag：DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a1661-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="a1661-163">会议中的用户只能拨出到区域 [A](audio-conferencing-zones.md)国家和地区，并且此用户可以拨打国际和国内号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1661-163">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="a1661-164">Identity='tag：DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a1661-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="a1661-165">会议中的用户只能拨出到 [区域 A](audio-conferencing-zones.md)国家和地区，并且此用户只能拨打国内 PSTN 号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1661-165">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="a1661-166">Identity='tag：DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a1661-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="a1661-167">会议中的用户只能拨出到区域 [A](audio-conferencing-zones.md)国家和地区，并且除了紧急号码之外，此用户无法拨打 PSTN 号码的任何出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1661-167">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
