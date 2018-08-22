---
title: 音频会议和用户 PSTN 通话的出站通话限制策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: 6096816ef9fb98811ec3ebed5a56b90a90b58c29
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490572"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="bba30-103">音频会议和用户 PSTN 通话的出站通话限制策略</span><span class="sxs-lookup"><span data-stu-id="bba30-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="bba30-104">作为管理员，您可以使用出站呼叫控件来限制的音频会议和最终用户 PSTN 的呼叫可以由组织中用户的类型。</span><span class="sxs-lookup"><span data-stu-id="bba30-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="bba30-105">出站呼叫控件可以应用基于每个用户，并提供了下列两个控件，以便独立限制每种类型的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="bba30-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="bba30-106">默认情况下，这两个控件设置为允许国际和国内出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="bba30-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="bba30-107">控件</span><span class="sxs-lookup"><span data-stu-id="bba30-107">Control</span></span>|<span data-ttu-id="bba30-108">说明</span><span class="sxs-lookup"><span data-stu-id="bba30-108">Description</span></span>|<span data-ttu-id="bba30-109">控制选项</span><span class="sxs-lookup"><span data-stu-id="bba30-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bba30-110">音频会议的 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="bba30-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="bba30-111">限制的出站的类型</span><span class="sxs-lookup"><span data-stu-id="bba30-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="bba30-112">从中允许的呼叫</span><span class="sxs-lookup"><span data-stu-id="bba30-112">calls that are allowed from within</span></span> </br><span data-ttu-id="bba30-113">由用户组织的会议。</span><span class="sxs-lookup"><span data-stu-id="bba30-113">meetings organized by a user.</span></span>|<span data-ttu-id="bba30-114">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="bba30-114">International and Domestic (default)</span></span></br><span data-ttu-id="bba30-115">国内</span><span class="sxs-lookup"><span data-stu-id="bba30-115">Domestic</span></span></br><span data-ttu-id="bba30-116">无</span><span class="sxs-lookup"><span data-stu-id="bba30-116">None</span></span>|
|<span data-ttu-id="bba30-117">最终用户 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="bba30-117">End user PSTN calls</span></span>|<span data-ttu-id="bba30-118">限制呼叫的类型</span><span class="sxs-lookup"><span data-stu-id="bba30-118">Restricts the type of calls</span></span> </br><span data-ttu-id="bba30-119">可以由用户进行的。</span><span class="sxs-lookup"><span data-stu-id="bba30-119">that can be made by a user.</span></span>|<span data-ttu-id="bba30-120">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="bba30-120">International and Domestic (default)</span></span></br><span data-ttu-id="bba30-121">国内</span><span class="sxs-lookup"><span data-stu-id="bba30-121">Domestic</span></span></br><span data-ttu-id="bba30-122">无</span><span class="sxs-lookup"><span data-stu-id="bba30-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="bba30-123">呼叫被确定为国内如果的呼叫的电话号码位于相同的国家/地区作为会议 （对于音频会议） 或最终用户 （对于最终用户 PSTN 呼叫） 的组织者设置 Office 365 中的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="bba30-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="bba30-124">限制音频会议出站呼叫</span><span class="sxs-lookup"><span data-stu-id="bba30-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="bba30-125">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="bba30-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bba30-126">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="bba30-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bba30-127">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="bba30-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bba30-128">**音频会议**，旁边单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="bba30-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="bba30-129">**电话拨出式会议的权限**下, 选择所需的电话拨出式限制选项。</span><span class="sxs-lookup"><span data-stu-id="bba30-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="bba30-130">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="bba30-130">Click **Save**.</span></span> 

<span data-ttu-id="bba30-131">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="bba30-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="bba30-132">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，然后选择用户可用的用户列表。</span><span class="sxs-lookup"><span data-stu-id="bba30-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="bba30-133">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="bba30-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="bba30-134">在**为此用户的会议的电话拨出的限制**选择所需的电话拨出式限制选项。</span><span class="sxs-lookup"><span data-stu-id="bba30-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![电话拨出选项限制](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="bba30-136">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="bba30-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="bba30-137">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bba30-137">**Using PowerShell**</span></span>

<span data-ttu-id="bba30-138">出站呼叫限制由一个策略调用 OnlineDialOutPolicy 其中每个具有限制属性控制。</span><span class="sxs-lookup"><span data-stu-id="bba30-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="bba30-139">不能自定义策略，而是有预定义的策略设置的每个组合的实例。</span><span class="sxs-lookup"><span data-stu-id="bba30-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="bba30-140">Get CSOnlineDialOutPolicy cmdlet 可用于查看的出站呼叫的策略和使用授予 CSDialOutPolicy cmdlet 将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="bba30-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="bba30-141">（请注意，授予 cmdlet 不包含单词"联机"Get cmdlet 一样。）</span><span class="sxs-lookup"><span data-stu-id="bba30-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="bba30-142">下表概述了每个策略。</span><span class="sxs-lookup"><span data-stu-id="bba30-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bba30-143">标识 = 标记： DialoutCPCandPSTNInternational</span><span class="sxs-lookup"><span data-stu-id="bba30-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="bba30-144">在会议中的用户可以发起电话拨出到国际和国内号码和此用户还可以发出对国际和国内号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="bba30-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="bba30-145">标识 = 标记： DialoutCPCDomesticPSTNInternational</span><span class="sxs-lookup"><span data-stu-id="bba30-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="bba30-146">用户在会议中的只能拨出到国内号码和此用户只能发出对国际和国内号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="bba30-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="bba30-147">标识 = 标记： DialoutCPCDisabledPSTNInternational</span><span class="sxs-lookup"><span data-stu-id="bba30-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="bba30-148">在会议中的用户无法使任意电话拨。此用户可以发起出站呼叫对国际和国内号码。</span><span class="sxs-lookup"><span data-stu-id="bba30-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="bba30-149">标识 = 标记： DialoutCPCInternationalPSTNDomestic</span><span class="sxs-lookup"><span data-stu-id="bba30-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="bba30-150">在会议中的用户可以发起电话拨出到国际和国内号码和此用户只能出国内 PSTN 号码的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="bba30-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="bba30-151">标识 = 标记： DialoutCPCInternationalPSTNDisabled</span><span class="sxs-lookup"><span data-stu-id="bba30-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="bba30-152">在会议中的用户可以发起电话拨出到国际和国内号码和此用户无法进行任何出站呼叫紧急号码除了 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="bba30-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="bba30-153">标识 = 标记： DialoutCPCandPSTNDomestic</span><span class="sxs-lookup"><span data-stu-id="bba30-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="bba30-154">用户在会议中的只能拨出到国内号码和此用户可以仅出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="bba30-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="bba30-155">标识 = 标记： DialoutCPCDomesticPSTNDisabled</span><span class="sxs-lookup"><span data-stu-id="bba30-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="bba30-156">用户在会议中的只能拨出到国内号码和此用户无法进行任何出站呼叫紧急号码除了 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="bba30-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="bba30-157">标识 = 标记： DialoutCPCDisabledPSTNDomestic</span><span class="sxs-lookup"><span data-stu-id="bba30-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="bba30-158">在会议中的用户无法使任意拨出和该用户可以仅出站呼叫国内 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="bba30-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="bba30-159">标识 = 标记： DialoutCPCandPSTNDisabled</span><span class="sxs-lookup"><span data-stu-id="bba30-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="bba30-160">在会议中的用户无法使任意拨出和此用户无法进行任何出站呼叫紧急号码除了 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="bba30-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
