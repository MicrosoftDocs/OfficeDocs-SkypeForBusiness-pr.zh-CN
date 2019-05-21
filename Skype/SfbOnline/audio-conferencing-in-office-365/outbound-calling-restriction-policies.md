---
title: 音频会议和用户 PSTN 通话的出站通话限制策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制音频会议和最终用户 PSTN 的呼叫可以由用户所做的类型。
ms.openlocfilehash: e4589a2785d5debf4de6d6a146ede76b020cd2d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299150"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="cf8f7-103">音频会议和用户 PSTN 通话的出站通话限制策略</span><span class="sxs-lookup"><span data-stu-id="cf8f7-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="cf8f7-104">作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="cf8f7-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span><span class="sxs-lookup"><span data-stu-id="cf8f7-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="cf8f7-107">源代码</span><span class="sxs-lookup"><span data-stu-id="cf8f7-107">Control</span></span>|<span data-ttu-id="cf8f7-108">说明</span><span class="sxs-lookup"><span data-stu-id="cf8f7-108">Description</span></span>|<span data-ttu-id="cf8f7-109">控件选项</span><span class="sxs-lookup"><span data-stu-id="cf8f7-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cf8f7-110">音频会议 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="cf8f7-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="cf8f7-111">限制出站类型</span><span class="sxs-lookup"><span data-stu-id="cf8f7-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="cf8f7-112">允许从用户组织</span><span class="sxs-lookup"><span data-stu-id="cf8f7-112">calls that are allowed from within</span></span> </br><span data-ttu-id="cf8f7-113">的会议内呼叫。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-113">meetings organized by a user.</span></span>|<span data-ttu-id="cf8f7-114">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="cf8f7-114">International and Domestic (default)</span></span></br><span data-ttu-id="cf8f7-115">版</span><span class="sxs-lookup"><span data-stu-id="cf8f7-115">Domestic</span></span></br><span data-ttu-id="cf8f7-116">无</span><span class="sxs-lookup"><span data-stu-id="cf8f7-116">None</span></span>|
|<span data-ttu-id="cf8f7-117">最终用户 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="cf8f7-117">End user PSTN calls</span></span>|<span data-ttu-id="cf8f7-118">限制可以由用户</span><span class="sxs-lookup"><span data-stu-id="cf8f7-118">Restricts the type of calls</span></span> </br><span data-ttu-id="cf8f7-119">拨打的呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-119">that can be made by a user.</span></span>|<span data-ttu-id="cf8f7-120">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="cf8f7-120">International and Domestic (default)</span></span></br><span data-ttu-id="cf8f7-121">版</span><span class="sxs-lookup"><span data-stu-id="cf8f7-121">Domestic</span></span></br><span data-ttu-id="cf8f7-122">无</span><span class="sxs-lookup"><span data-stu-id="cf8f7-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="cf8f7-123">如果所拨打的号码位于与会议组织者 (如音频会议) 或最终用户 (如果最终用户 PSTN 呼叫) 的组织者相同的365国家内, 则会将呼叫视为国内呼叫。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-123">A call is considered domestic if the number dialed is in the same country where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="cf8f7-124">限制音频会议出站呼叫</span><span class="sxs-lookup"><span data-stu-id="cf8f7-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="cf8f7-125">![](../images/teams-logo-30x30.png) **使用 Microsoft 团队管理中心的**teams-logo-30x30</span><span class="sxs-lookup"><span data-stu-id="cf8f7-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="cf8f7-126">在左侧导航中, 单击 "**用户**", 然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="cf8f7-127">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="cf8f7-128">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="cf8f7-129">在**会议拨出权限**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="cf8f7-130">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-130">Click **Save**.</span></span> 

<span data-ttu-id="cf8f7-131">![](../images/sfb-logo-30x30.png) **使用 Skype for business 管理中心**sfb-logo-30x30</span><span class="sxs-lookup"><span data-stu-id="cf8f7-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="cf8f7-132">在**Skype for business 管理中心**的左侧导航中, 转到 "**音频会议** > **用户**", 然后从可用的用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="cf8f7-133">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="cf8f7-134">在**限制此用户从会议拨出**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![拨出选项限制](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="cf8f7-136">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="cf8f7-137">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cf8f7-137">**Using PowerShell**</span></span>

<span data-ttu-id="cf8f7-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span><span class="sxs-lookup"><span data-stu-id="cf8f7-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="cf8f7-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span><span class="sxs-lookup"><span data-stu-id="cf8f7-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="cf8f7-142">下表概述了每个策略。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="cf8f7-143">标识='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="cf8f7-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="cf8f7-144">参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="cf8f7-145">标识='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="cf8f7-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="cf8f7-146">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="cf8f7-147">标识='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="cf8f7-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="cf8f7-148">参加会议的用户无法进行任何拨出。此用户可以出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="cf8f7-149">标识='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="cf8f7-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="cf8f7-150">参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="cf8f7-151">标识='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="cf8f7-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="cf8f7-152">参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="cf8f7-153">标识='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="cf8f7-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="cf8f7-154">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="cf8f7-155">标识='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="cf8f7-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="cf8f7-156">参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="cf8f7-157">标识='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="cf8f7-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="cf8f7-158">参加会议的用户无法进行任何拨出，同时此用户仅可出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="cf8f7-159">标识='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="cf8f7-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="cf8f7-160">参加会议的用户无法拨打任何号码，同时此用户无法出站呼叫  PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="cf8f7-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
