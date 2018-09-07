---
title: 音频会议和用户 PSTN 通话的出站呼叫限制策略
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制音频会议和最终用户 PSTN 的呼叫可以由用户所做的类型。
ms.openlocfilehash: fd1a3b770debfcc6aa048d150b6536c94db4f9ce
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856878"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="a7cca-103">音频会议和用户 PSTN 通话的出站呼叫限制策略</span><span class="sxs-lookup"><span data-stu-id="a7cca-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="a7cca-104">作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="a7cca-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="a7cca-105">出站通话控件可以应用基于每个用户，并提供了下列两个控件，以便独立限制每种类型的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7cca-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="a7cca-106">默认情况下，这两个控件设置为允许国际和国内出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7cca-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="a7cca-107">控件</span><span class="sxs-lookup"><span data-stu-id="a7cca-107">CONTROL</span></span>|<span data-ttu-id="a7cca-108">说明</span><span class="sxs-lookup"><span data-stu-id="a7cca-108">Description</span></span>|<span data-ttu-id="a7cca-109">控件选项</span><span class="sxs-lookup"><span data-stu-id="a7cca-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7cca-110">音频会议 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="a7cca-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="a7cca-111">限制出站类型</span><span class="sxs-lookup"><span data-stu-id="a7cca-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="a7cca-112">允许从用户组织</span><span class="sxs-lookup"><span data-stu-id="a7cca-112">calls that are allowed from within</span></span> </br><span data-ttu-id="a7cca-113">的会议内呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7cca-113">meetings organized by a user.</span></span>|<span data-ttu-id="a7cca-114">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="a7cca-114">International and Domestic (default)</span></span></br><span data-ttu-id="a7cca-115">国内</span><span class="sxs-lookup"><span data-stu-id="a7cca-115">Domestic</span></span></br><span data-ttu-id="a7cca-116">无</span><span class="sxs-lookup"><span data-stu-id="a7cca-116">None</span></span>|
|<span data-ttu-id="a7cca-117">最终用户 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="a7cca-117">End user PSTN calls</span></span>|<span data-ttu-id="a7cca-118">限制可以由用户</span><span class="sxs-lookup"><span data-stu-id="a7cca-118">Restricts the type of calls</span></span> </br><span data-ttu-id="a7cca-119">拨打的呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="a7cca-119">that can be made by a user.</span></span>|<span data-ttu-id="a7cca-120">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="a7cca-120">International and Domestic (default)</span></span></br><span data-ttu-id="a7cca-121">国内</span><span class="sxs-lookup"><span data-stu-id="a7cca-121">Domestic</span></span></br><span data-ttu-id="a7cca-122">无</span><span class="sxs-lookup"><span data-stu-id="a7cca-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="a7cca-123">如果呼叫的电话号码位于与会议组织者（对于音频会议）或最终用户（对于最终用户 PSTN 呼叫）的 Office 365 中设置的国家/地区相同，则呼叫被确定为国内。</span><span class="sxs-lookup"><span data-stu-id="a7cca-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="a7cca-124">限制音频会议出站呼叫</span><span class="sxs-lookup"><span data-stu-id="a7cca-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="a7cca-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="a7cca-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="a7cca-126">在左侧导航窗格中，单击**用户**，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="a7cca-126">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a7cca-127">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a7cca-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a7cca-128">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a7cca-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="a7cca-129">在**会议拨出权限**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="a7cca-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="a7cca-130">单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="a7cca-130">Click **Save**.</span></span> 

<span data-ttu-id="a7cca-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="a7cca-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1.  <span data-ttu-id="a7cca-132">在左侧导航窗格的 **Skype for Business 管理中心**中，转到**音频会议** > **用户**，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="a7cca-132">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Dial-in users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="a7cca-133">在“操作”窗格中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a7cca-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="a7cca-134">在**限制此用户从会议拨出**下，选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="a7cca-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![拨出选项限制](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="a7cca-136">单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="a7cca-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="a7cca-137">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a7cca-137">\*\*\*\* Using Windows PowerShell</span></span>

<span data-ttu-id="a7cca-138">出站呼叫限制由名为 OnlineDialOutPolicy 的单个策略控制，其中每个都有一个限制属性。</span><span class="sxs-lookup"><span data-stu-id="a7cca-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="a7cca-139">无法自定义策略，而是为每个设置组织使用预定义策略实例。</span><span class="sxs-lookup"><span data-stu-id="a7cca-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="a7cca-140">Get CSOnlineDialOutPolicy cmdlet 可用于查看出站呼叫策略并使用 CSDialOutPolicy cmdlet 将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a7cca-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="a7cca-141">（请注意，授予 cmdlet 不包含 Get cmdlet 使用的单词“Online”。）</span><span class="sxs-lookup"><span data-stu-id="a7cca-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="a7cca-142">下表概述了每个策略。</span><span class="sxs-lookup"><span data-stu-id="a7cca-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a7cca-143">标识='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a7cca-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="a7cca-144">参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="a7cca-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="a7cca-145">标识='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a7cca-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="a7cca-146">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="a7cca-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="a7cca-147">标识='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a7cca-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="a7cca-148">参加会议的用户无法进行任何拨出。此用户可以出站呼叫国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="a7cca-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="a7cca-149">标识='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a7cca-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="a7cca-150">参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="a7cca-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="a7cca-151">标识='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a7cca-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="a7cca-152">参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="a7cca-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="a7cca-153">标识='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a7cca-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="a7cca-154">参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="a7cca-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="a7cca-155">标识='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a7cca-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="a7cca-156">参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="a7cca-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="a7cca-157">标识='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a7cca-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="a7cca-158">参加会议的用户无法进行任何拨出，同时此用户仅可出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="a7cca-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="a7cca-159">标识='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a7cca-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="a7cca-160">参加会议的用户无法拨打任何号码，同时此用户无法出站呼叫  PSTN 号码，紧急号码除外。</span><span class="sxs-lookup"><span data-stu-id="a7cca-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
