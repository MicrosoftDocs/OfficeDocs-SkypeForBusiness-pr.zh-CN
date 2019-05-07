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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制音频会议和最终用户 PSTN 的呼叫可以由用户所做的类型。
ms.openlocfilehash: acd75df192211465071940148e35bc7e269c7976
ms.sourcegitcommit: d1b14268efe334aa93a6889f25fcfe46e07d5daa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "33584220"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="7a1ab-103">音频会议和用户 PSTN 通话的出站通话限制策略</span><span class="sxs-lookup"><span data-stu-id="7a1ab-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="7a1ab-104">作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="7a1ab-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span><span class="sxs-lookup"><span data-stu-id="7a1ab-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="7a1ab-107">控件</span><span class="sxs-lookup"><span data-stu-id="7a1ab-107">Control</span></span>|<span data-ttu-id="7a1ab-108">说明</span><span class="sxs-lookup"><span data-stu-id="7a1ab-108">Description</span></span>|<span data-ttu-id="7a1ab-109">控件选项</span><span class="sxs-lookup"><span data-stu-id="7a1ab-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a1ab-110">音频会议 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="7a1ab-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="7a1ab-111">限制出站类型</span><span class="sxs-lookup"><span data-stu-id="7a1ab-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="7a1ab-112">允许从用户组织</span><span class="sxs-lookup"><span data-stu-id="7a1ab-112">calls that are allowed from within</span></span> </br><span data-ttu-id="7a1ab-113">的会议内呼叫。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-113">meetings organized by a user.</span></span>|<span data-ttu-id="7a1ab-114">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="7a1ab-114">International and Domestic (default)</span></span></br><span data-ttu-id="7a1ab-115">国内</span><span class="sxs-lookup"><span data-stu-id="7a1ab-115">Domestic</span></span></br><span data-ttu-id="7a1ab-116">无</span><span class="sxs-lookup"><span data-stu-id="7a1ab-116">None</span></span>|
|<span data-ttu-id="7a1ab-117">最终用户 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="7a1ab-117">End user PSTN calls</span></span>|<span data-ttu-id="7a1ab-118">限制可以由用户</span><span class="sxs-lookup"><span data-stu-id="7a1ab-118">Restricts the type of calls</span></span> </br><span data-ttu-id="7a1ab-119">拨打的呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-119">that can be made by a user.</span></span>|<span data-ttu-id="7a1ab-120">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="7a1ab-120">International and Domestic (default)</span></span></br><span data-ttu-id="7a1ab-121">国内</span><span class="sxs-lookup"><span data-stu-id="7a1ab-121">Domestic</span></span></br><span data-ttu-id="7a1ab-122">无</span><span class="sxs-lookup"><span data-stu-id="7a1ab-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="7a1ab-123">呼叫被视为国内如果拨打的号码位于相同的国家/地区其中 Office 365 已设置的组织者的 （对于音频会议），会议组织者或最终用户 （对于最终用户 PSTN 呼叫）。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-123">A call is considered domestic if the number dialed is in the same country where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="7a1ab-124">限制音频会议出站呼叫</span><span class="sxs-lookup"><span data-stu-id="7a1ab-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="7a1ab-125">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="7a1ab-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7a1ab-126">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7a1ab-127">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="7a1ab-128">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="7a1ab-129">在**会议拨出权限**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="7a1ab-130">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-130">Click **Save**.</span></span> 

<span data-ttu-id="7a1ab-131">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="7a1ab-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="7a1ab-132">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，然后选择用户可用的用户列表。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="7a1ab-133">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="7a1ab-134">在**限制此用户从会议拨出**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![拨出选项限制](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="7a1ab-136">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="7a1ab-137">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7a1ab-137">**Using PowerShell**</span></span>

<span data-ttu-id="7a1ab-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span><span class="sxs-lookup"><span data-stu-id="7a1ab-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="7a1ab-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span><span class="sxs-lookup"><span data-stu-id="7a1ab-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="7a1ab-142">下表概述了每个策略。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7a1ab-143">标识='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="7a1ab-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="7a1ab-144">参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="7a1ab-145">标识='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="7a1ab-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="7a1ab-146">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="7a1ab-147">标识='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="7a1ab-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="7a1ab-148">参加会议的用户无法进行任何拨出。此用户可以出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="7a1ab-149">标识='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="7a1ab-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="7a1ab-150">参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="7a1ab-151">标识='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="7a1ab-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="7a1ab-152">参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="7a1ab-153">标识='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="7a1ab-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="7a1ab-154">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="7a1ab-155">标识='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="7a1ab-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="7a1ab-156">参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="7a1ab-157">标识='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="7a1ab-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="7a1ab-158">参加会议的用户无法进行任何拨出，同时此用户仅可出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="7a1ab-159">标识='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="7a1ab-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="7a1ab-160">参加会议的用户无法拨打任何号码，同时此用户无法出站呼叫  PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="7a1ab-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
