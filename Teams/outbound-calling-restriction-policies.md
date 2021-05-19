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
description: 管理员可以控制用户可以进行的音频会议和最终用户 PSTN 呼叫的类型。
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526725"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="970d6-103">音频会议和用户 PSTN 通话的出站通话限制策略</span><span class="sxs-lookup"><span data-stu-id="970d6-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="970d6-104">作为管理员，您可以使用出站呼叫控件来限制音频会议和最终用户公用电话交换网 (PSTN) 呼叫的类型，这些呼叫由您的组织中的用户可以进行。</span><span class="sxs-lookup"><span data-stu-id="970d6-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that can be made by users in your organization.</span></span>

<span data-ttu-id="970d6-105">可以基于每个用户或租户应用出站调用控件，并提供以下两个控件来独立限制每种类型的出站调用。</span><span class="sxs-lookup"><span data-stu-id="970d6-105">Outbound call controls can be applied on a per-user basis or on a tenant basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="970d6-106">默认情况下，这两个控件设置为允许国际和国内出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="970d6-106">By default, both controls are set to allow international and domestic outbound calls.</span></span>

|<span data-ttu-id="970d6-107">控件</span><span class="sxs-lookup"><span data-stu-id="970d6-107">Control</span></span>|<span data-ttu-id="970d6-108">说明</span><span class="sxs-lookup"><span data-stu-id="970d6-108">Description</span></span>|<span data-ttu-id="970d6-109">控件选项</span><span class="sxs-lookup"><span data-stu-id="970d6-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="970d6-110">音频会议 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="970d6-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="970d6-111">限制出站类型</span><span class="sxs-lookup"><span data-stu-id="970d6-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="970d6-112">允许从用户组织</span><span class="sxs-lookup"><span data-stu-id="970d6-112">calls that are allowed from within</span></span> </br><span data-ttu-id="970d6-113">的会议内呼叫。</span><span class="sxs-lookup"><span data-stu-id="970d6-113">meetings organized by a user.</span></span>|<span data-ttu-id="970d6-114">任何目标 (默认) </span><span class="sxs-lookup"><span data-stu-id="970d6-114">Any destination (default)</span></span></br><span data-ttu-id="970d6-115">与组织者在同一国家/地区</span><span class="sxs-lookup"><span data-stu-id="970d6-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="970d6-116">[仅区域 A 国家/地区](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="970d6-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="970d6-117">不允许</span><span class="sxs-lookup"><span data-stu-id="970d6-117">Don't allow</span></span>|
|<span data-ttu-id="970d6-118">最终用户 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="970d6-118">End-user PSTN calls</span></span>|<span data-ttu-id="970d6-119">限制可以由用户</span><span class="sxs-lookup"><span data-stu-id="970d6-119">Restricts the type of calls</span></span> </br><span data-ttu-id="970d6-120">拨打的呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="970d6-120">that can be made by a user.</span></span>|<span data-ttu-id="970d6-121">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="970d6-121">International and Domestic (default)</span></span></br><span data-ttu-id="970d6-122">国内</span><span class="sxs-lookup"><span data-stu-id="970d6-122">Domestic</span></span></br><span data-ttu-id="970d6-123">无</span><span class="sxs-lookup"><span data-stu-id="970d6-123">None</span></span>|

<span data-ttu-id="970d6-124">若要了解哪些国家和地区被视为区域 A，请参阅音频会议 [的国家和地区区域](audio-conferencing-zones.md)。</span><span class="sxs-lookup"><span data-stu-id="970d6-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="970d6-125">如果拨打的号码位于为会议组织者设置了 Microsoft 365 或 Office 365 的国家/地区（对于音频会议 () ）或最终用户 (（对于最终用户 PSTN 呼叫) ）来说，呼叫被视为国内呼叫。</span><span class="sxs-lookup"><span data-stu-id="970d6-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="970d6-126">限制音频会议出站呼叫</span><span class="sxs-lookup"><span data-stu-id="970d6-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="970d6-127">![Microsoft Teams徽标 ](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="970d6-127">![the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="970d6-128">在左侧导航栏中， **选择"用户**"，显示名称可用用户列表中选择该用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="970d6-128">In the left navigation, select **Users**, and then select the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="970d6-129">在"**音频会议"旁边，** 选择"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="970d6-129">Next to **Audio Conferencing**, select **Edit**.</span></span>

4. <span data-ttu-id="970d6-130">在 **"从会议拨出"** 下，选择你需要的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="970d6-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="970d6-131">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="970d6-131">Select **Save**.</span></span>

<span data-ttu-id="970d6-132">![显示 Skype for Business 徽标的图标](media/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="970d6-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="970d6-133">在 **Skype for Business** 管理中心的 左侧导航中，转到"音频会议用户"，然后从可用  >  用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="970d6-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="970d6-134">在"操作"窗格中，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="970d6-134">In the Action pane, select **Edit**.</span></span>

3.  <span data-ttu-id="970d6-135">在 **限制此用户从会议拨出** 下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="970d6-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![拨出选项限制](media/restrictions-to-dial-outs.png)

4. <span data-ttu-id="970d6-137">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="970d6-137">Select **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="970d6-138">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="970d6-138">**Using PowerShell**</span></span>

<span data-ttu-id="970d6-139">出站调用限制由名为 OnlineDialOutPolicy 的单个策略控制，该策略具有每个策略的限制属性。</span><span class="sxs-lookup"><span data-stu-id="970d6-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy, which has a restriction attribute for each.</span></span> <span data-ttu-id="970d6-140">无法自定义策略，而是为每个设置组织使用预定义策略实例。</span><span class="sxs-lookup"><span data-stu-id="970d6-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span>

<span data-ttu-id="970d6-141">可以使用 Get-CSOnlineDialOutPolicy cmdlet 查看出站调用策略，并使用以下命令进行设置。</span><span class="sxs-lookup"><span data-stu-id="970d6-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and use the following command for the setup.</span></span>

<span data-ttu-id="970d6-142">**使用以下 cmdlet 在每个用户级别设置策略**。</span><span class="sxs-lookup"><span data-stu-id="970d6-142">**Set the policy on a per-user level with the following cmdlet**.</span></span> <span data-ttu-id="970d6-143"> (Get cmdlet 不包含"联机"一词，就像 Get cmdlet 一样) </span><span class="sxs-lookup"><span data-stu-id="970d6-143">(The Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span>

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

<span data-ttu-id="970d6-144">**使用以下 cmdlet 在租户级别设置策略**。</span><span class="sxs-lookup"><span data-stu-id="970d6-144">**Set the policy on the tenant level with the following cmdlet**.</span></span>

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

<span data-ttu-id="970d6-145">未分配任何拨出策略的租户的所有用户都将获取此策略。</span><span class="sxs-lookup"><span data-stu-id="970d6-145">All users of the tenant who don't have any dialout policy assigned will get this policy.</span></span> <span data-ttu-id="970d6-146">其他用户仍保留其当前策略。</span><span class="sxs-lookup"><span data-stu-id="970d6-146">Other users remain with their current policy.</span></span>

<span data-ttu-id="970d6-147">下表概述了每个策略。</span><span class="sxs-lookup"><span data-stu-id="970d6-147">The following table provides an overview of each policy.</span></span>

|<span data-ttu-id="970d6-148">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="970d6-148">PowerShell cmdlet</span></span>|<span data-ttu-id="970d6-149">说明</span><span class="sxs-lookup"><span data-stu-id="970d6-149">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="970d6-150">标识='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="970d6-150">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="970d6-151">参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="970d6-151">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="970d6-152">标识='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="970d6-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="970d6-153">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="970d6-153">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="970d6-154">标识='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="970d6-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="970d6-155">会议中的用户无法拨出。此用户可以拨打国际和国内号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="970d6-155">User in the conference can't dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="970d6-156">标识='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="970d6-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="970d6-157">参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="970d6-157">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="970d6-158">标识='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="970d6-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="970d6-159">参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="970d6-159">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="970d6-160">标识='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="970d6-160">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="970d6-161">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="970d6-161">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="970d6-162">标识='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="970d6-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="970d6-163">参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="970d6-163">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="970d6-164">标识='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="970d6-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="970d6-165">会议中的用户无法拨出，并且此用户只能拨打国内 PSTN 号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="970d6-165">User in the conference can't dial out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="970d6-166">标识='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="970d6-166">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="970d6-167">会议中的用户无法拨出，并且除紧急号码外，此用户无法拨打 PSTN 号码的任何出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="970d6-167">User in the conference can't dial out, and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="970d6-168">Identity='tag：DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="970d6-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="970d6-169">会议中的用户只能拨出到区域 [A](audio-conferencing-zones.md)国家和地区，并且此用户可以拨打国际和国内号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="970d6-169">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="970d6-170">Identity='tag：DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="970d6-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="970d6-171">会议中的用户只能拨出到 [区域 A](audio-conferencing-zones.md)国家和地区，并且此用户只能拨打国内 PSTN 号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="970d6-171">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="970d6-172">Identity='tag：DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="970d6-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="970d6-173">会议中的用户只能拨出到区域 [A](audio-conferencing-zones.md)国家和地区，并且除了紧急号码之外，此用户无法对 PSTN 号码进行任何出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="970d6-173">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
