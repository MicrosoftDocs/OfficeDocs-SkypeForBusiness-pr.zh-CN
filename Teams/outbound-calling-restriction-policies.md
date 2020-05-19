---
title: 出站呼叫限制-& PSTN 呼叫的音频会议
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
ms.openlocfilehash: 84acbed4017a709b63e657f12ef0bbe3c1eb620c
ms.sourcegitcommit: 5a88788bd0a0b2ccbc5b977b38dcfe4681cd5d10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2020
ms.locfileid: "44278175"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="f212b-103">音频会议和用户 PSTN 通话的出站通话限制策略</span><span class="sxs-lookup"><span data-stu-id="f212b-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="f212b-104">作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="f212b-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="f212b-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span><span class="sxs-lookup"><span data-stu-id="f212b-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="f212b-107">源代码</span><span class="sxs-lookup"><span data-stu-id="f212b-107">Control</span></span>|<span data-ttu-id="f212b-108">说明</span><span class="sxs-lookup"><span data-stu-id="f212b-108">Description</span></span>|<span data-ttu-id="f212b-109">控件选项</span><span class="sxs-lookup"><span data-stu-id="f212b-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f212b-110">音频会议 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="f212b-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="f212b-111">限制出站类型</span><span class="sxs-lookup"><span data-stu-id="f212b-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="f212b-112">允许从用户组织</span><span class="sxs-lookup"><span data-stu-id="f212b-112">calls that are allowed from within</span></span> </br><span data-ttu-id="f212b-113">的会议内呼叫。</span><span class="sxs-lookup"><span data-stu-id="f212b-113">meetings organized by a user.</span></span>|<span data-ttu-id="f212b-114">任何目的地（默认值）</span><span class="sxs-lookup"><span data-stu-id="f212b-114">Any destination (default)</span></span></br><span data-ttu-id="f212b-115">在与 organizor 相同的国家或地区</span><span class="sxs-lookup"><span data-stu-id="f212b-115">In the same country or region as the organizor</span></span> </br> </br><span data-ttu-id="f212b-116">仅对国家或地区进行分区</span><span class="sxs-lookup"><span data-stu-id="f212b-116">Zone A countries or regions only</span></span> </br><span data-ttu-id="f212b-117">不允许</span><span class="sxs-lookup"><span data-stu-id="f212b-117">Don't allow</span></span>|
|<span data-ttu-id="f212b-118">最终用户 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="f212b-118">End user PSTN calls</span></span>|<span data-ttu-id="f212b-119">限制可以由用户</span><span class="sxs-lookup"><span data-stu-id="f212b-119">Restricts the type of calls</span></span> </br><span data-ttu-id="f212b-120">拨打的呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="f212b-120">that can be made by a user.</span></span>|<span data-ttu-id="f212b-121">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="f212b-121">International and Domestic (default)</span></span></br><span data-ttu-id="f212b-122">版</span><span class="sxs-lookup"><span data-stu-id="f212b-122">Domestic</span></span></br><span data-ttu-id="f212b-123">无</span><span class="sxs-lookup"><span data-stu-id="f212b-123">None</span></span>|

<span data-ttu-id="f212b-124">若要了解哪些国家/地区被视为区域 A，请参阅将[国家/地区分区](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="f212b-124">To find out which countries/regions are considered Zone A, see [Zone A countries/regions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span></span>

   > [!NOTE]
   > <span data-ttu-id="f212b-125">如果所拨打的号码位于与为会议组织者设置的 Office 365 相同的国家/地区（对于音频会议）或最终用户（如果最终用户 PSTN 呼叫），则会将呼叫视为国内呼叫。</span><span class="sxs-lookup"><span data-stu-id="f212b-125">A call is considered domestic if the number dialed is in the same country/region where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="f212b-126">限制音频会议出站呼叫</span><span class="sxs-lookup"><span data-stu-id="f212b-126">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="f212b-127">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="f212b-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f212b-128">在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="f212b-128">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f212b-129">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="f212b-129">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f212b-130">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="f212b-130">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="f212b-131">在**会议拨出权限**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="f212b-131">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="f212b-132">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f212b-132">Click **Save**.</span></span> 

<span data-ttu-id="f212b-133">![显示 Skype for Business 徽标的图标](media/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="f212b-133">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.    <span data-ttu-id="f212b-134">在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议**  >  **用户**"，然后从可用的用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="f212b-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.    <span data-ttu-id="f212b-135">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="f212b-135">In the Action pane, click **Edit**.</span></span>

3.    <span data-ttu-id="f212b-136">在**限制此用户从会议拨出**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="f212b-136">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![拨出选项限制](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="f212b-138">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f212b-138">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="f212b-139">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f212b-139">**Using PowerShell**</span></span>

<span data-ttu-id="f212b-140">出站呼叫限制由名为 OnlineDialOutPolicy 的单个策略控制，其中每个都有一个限制属性。</span><span class="sxs-lookup"><span data-stu-id="f212b-140">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="f212b-141">无法自定义策略，而是为每个设置组织使用预定义策略实例。</span><span class="sxs-lookup"><span data-stu-id="f212b-141">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="f212b-142">Get CSOnlineDialOutPolicy cmdlet 可用于查看出站呼叫策略并使用 CSDialOutPolicy cmdlet 将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="f212b-142">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="f212b-143">（请注意，授予 cmdlet 不包含 "Online" 一词，因为 Get cmdlet 是。）</span><span class="sxs-lookup"><span data-stu-id="f212b-143">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="f212b-144">下表概述了每个策略。</span><span class="sxs-lookup"><span data-stu-id="f212b-144">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f212b-145">标识='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="f212b-145">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="f212b-146">参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="f212b-146">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="f212b-147">标识='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="f212b-147">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="f212b-148">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="f212b-148">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="f212b-149">标识='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="f212b-149">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="f212b-150">参加会议的用户无法进行任何拨出。此用户可以出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="f212b-150">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="f212b-151">标识='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="f212b-151">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="f212b-152">参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="f212b-152">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="f212b-153">标识='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="f212b-153">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="f212b-154">参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="f212b-154">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="f212b-155">标识='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="f212b-155">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="f212b-156">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="f212b-156">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="f212b-157">标识='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="f212b-157">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="f212b-158">参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="f212b-158">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="f212b-159">标识='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="f212b-159">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="f212b-160">参加会议的用户无法进行任何拨出，同时此用户仅可出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="f212b-160">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="f212b-161">标识='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="f212b-161">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="f212b-162">参加会议的用户无法拨打任何号码，同时此用户无法出站呼叫  PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="f212b-162">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="f212b-163">Identity = "tag： DialoutCPCZoneAPSTNInternational"</span><span class="sxs-lookup"><span data-stu-id="f212b-163">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="f212b-164">会议中的用户只能拨出以对国家和地区进行分区，并且此用户可以拨出到国际和国内号码的电话。</span><span class="sxs-lookup"><span data-stu-id="f212b-164">User in the conference can only dial out to Zone A countries and regions, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="f212b-165">Identity = "tag： DialoutCPCZoneAPSTNDomestic"</span><span class="sxs-lookup"><span data-stu-id="f212b-165">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="f212b-166">会议中的用户只能拨出以对国家和地区进行分区，并且此用户只能拨出到国内 PSTN 号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="f212b-166">User in the conference can only dial out to Zone A countries and regions, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="f212b-167">Identity = "tag： DialoutCPCZoneAPSTNDisabled"</span><span class="sxs-lookup"><span data-stu-id="f212b-167">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="f212b-168">会议中的用户只能拨出以对国家和地区进行分区，并且除了紧急号码之外，此用户不能对 PSTN 号码进行任何出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="f212b-168">User in the conference can only dial out to Zone A countries and regions, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
