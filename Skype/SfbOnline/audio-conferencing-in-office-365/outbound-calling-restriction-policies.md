---
title: 音频会议和用户 PSTN 通话的出站通话限制策略
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
ms.openlocfilehash: 97df093168e896eabbc210545d516f386e1a6d25
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753469"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="837ec-103">音频会议和用户 PSTN 通话的出站通话限制策略</span><span class="sxs-lookup"><span data-stu-id="837ec-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="837ec-104">作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="837ec-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="837ec-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span><span class="sxs-lookup"><span data-stu-id="837ec-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="837ec-107">控件</span><span class="sxs-lookup"><span data-stu-id="837ec-107">Control</span></span>|<span data-ttu-id="837ec-108">说明</span><span class="sxs-lookup"><span data-stu-id="837ec-108">Description</span></span>|<span data-ttu-id="837ec-109">控件选项</span><span class="sxs-lookup"><span data-stu-id="837ec-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="837ec-110">音频会议 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="837ec-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="837ec-111">限制出站类型</span><span class="sxs-lookup"><span data-stu-id="837ec-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="837ec-112">允许从用户组织</span><span class="sxs-lookup"><span data-stu-id="837ec-112">calls that are allowed from within</span></span> </br><span data-ttu-id="837ec-113">的会议内呼叫。</span><span class="sxs-lookup"><span data-stu-id="837ec-113">meetings organized by a user.</span></span>|<span data-ttu-id="837ec-114">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="837ec-114">International and Domestic (default)</span></span></br><span data-ttu-id="837ec-115">国内</span><span class="sxs-lookup"><span data-stu-id="837ec-115">Domestic</span></span></br><span data-ttu-id="837ec-116">无</span><span class="sxs-lookup"><span data-stu-id="837ec-116">None</span></span>|
|<span data-ttu-id="837ec-117">最终用户 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="837ec-117">End user PSTN calls</span></span>|<span data-ttu-id="837ec-118">限制可以由用户</span><span class="sxs-lookup"><span data-stu-id="837ec-118">Restricts the type of calls</span></span> </br><span data-ttu-id="837ec-119">拨打的呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="837ec-119">that can be made by a user.</span></span>|<span data-ttu-id="837ec-120">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="837ec-120">International and Domestic (default)</span></span></br><span data-ttu-id="837ec-121">国内</span><span class="sxs-lookup"><span data-stu-id="837ec-121">Domestic</span></span></br><span data-ttu-id="837ec-122">无</span><span class="sxs-lookup"><span data-stu-id="837ec-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="837ec-123">如果呼叫的电话号码位于与会议组织者（对于音频会议）或最终用户（对于最终用户 PSTN 呼叫）的 Office 365 中设置的国家/地区相同，则呼叫被确定为国内。</span><span class="sxs-lookup"><span data-stu-id="837ec-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="837ec-124">限制音频会议出站呼叫</span><span class="sxs-lookup"><span data-stu-id="837ec-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="837ec-125">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="837ec-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="837ec-126">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="837ec-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="837ec-127">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="837ec-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="837ec-128">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="837ec-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="837ec-129">在**会议拨出权限**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="837ec-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="837ec-130">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="837ec-130">Click **Save**.</span></span> 

<span data-ttu-id="837ec-131">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="837ec-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="837ec-132">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，然后选择用户可用的用户列表。</span><span class="sxs-lookup"><span data-stu-id="837ec-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="837ec-133">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="837ec-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="837ec-134">在**限制此用户从会议拨出**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="837ec-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![拨出选项限制](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="837ec-136">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="837ec-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="837ec-137">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="837ec-137">**Using PowerShell**</span></span>

<span data-ttu-id="837ec-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span><span class="sxs-lookup"><span data-stu-id="837ec-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="837ec-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span><span class="sxs-lookup"><span data-stu-id="837ec-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="837ec-142">下表概述了每个策略。</span><span class="sxs-lookup"><span data-stu-id="837ec-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="837ec-143">标识='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="837ec-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="837ec-144">参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="837ec-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="837ec-145">标识='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="837ec-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="837ec-146">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="837ec-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="837ec-147">标识='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="837ec-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="837ec-148">参加会议的用户无法进行任何拨出。此用户可以出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="837ec-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="837ec-149">标识='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="837ec-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="837ec-150">参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="837ec-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="837ec-151">标识='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="837ec-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="837ec-152">参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="837ec-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="837ec-153">标识='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="837ec-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="837ec-154">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="837ec-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="837ec-155">标识='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="837ec-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="837ec-156">参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="837ec-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="837ec-157">标识='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="837ec-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="837ec-158">参加会议的用户无法进行任何拨出，同时此用户仅可出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="837ec-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="837ec-159">标识='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="837ec-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="837ec-160">参加会议的用户无法拨打任何号码，同时此用户无法出站呼叫  PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="837ec-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
