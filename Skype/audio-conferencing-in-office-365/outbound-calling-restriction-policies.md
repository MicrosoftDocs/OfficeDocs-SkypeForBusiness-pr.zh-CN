---
title: 音频会议和用户 PSTN 呼叫的出站呼叫限制策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 2/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 管理员可以控制音频会议和最终用户 PSTN 呼叫可以做的用户的类型。
ms.openlocfilehash: ae6039f967b95ebd0c5934105f4e6fb044e431b4
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="1c61e-103">音频会议和用户 PSTN 呼叫的出站呼叫限制策略</span><span class="sxs-lookup"><span data-stu-id="1c61e-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="1c61e-104">作为管理员，可以使用出站呼叫控制来限制音频会议和最终用户 PSTN 呼叫，可以由组织中的用户的类型。</span><span class="sxs-lookup"><span data-stu-id="1c61e-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="1c61e-105">出站呼叫控制可以在每用户基础上应用，并提供以下两个控件分别限制出站呼叫的每个类型。</span><span class="sxs-lookup"><span data-stu-id="1c61e-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="1c61e-106">默认情况下，这两个控件设置为允许国际和国内的出站调用。</span><span class="sxs-lookup"><span data-stu-id="1c61e-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="1c61e-107">控件</span><span class="sxs-lookup"><span data-stu-id="1c61e-107">Control</span></span>|<span data-ttu-id="1c61e-108">说明</span><span class="sxs-lookup"><span data-stu-id="1c61e-108">Description</span></span>|<span data-ttu-id="1c61e-109">控制选项</span><span class="sxs-lookup"><span data-stu-id="1c61e-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1c61e-110">音频会议 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="1c61e-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="1c61e-111">限制类型的出站</span><span class="sxs-lookup"><span data-stu-id="1c61e-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="1c61e-112">从允许的调用</span><span class="sxs-lookup"><span data-stu-id="1c61e-112">calls that are allowed from within</span></span> </br><span data-ttu-id="1c61e-113">组织的用户的会议。</span><span class="sxs-lookup"><span data-stu-id="1c61e-113">meetings organized by a user.</span></span>|<span data-ttu-id="1c61e-114">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="1c61e-114">International and Domestic (default)</span></span></br><span data-ttu-id="1c61e-115">国内</span><span class="sxs-lookup"><span data-stu-id="1c61e-115">Domestic</span></span></br><span data-ttu-id="1c61e-116">无</span><span class="sxs-lookup"><span data-stu-id="1c61e-116">None</span></span>|
|<span data-ttu-id="1c61e-117">最终用户 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="1c61e-117">End user PSTN calls</span></span>|<span data-ttu-id="1c61e-118">限制类型的调用</span><span class="sxs-lookup"><span data-stu-id="1c61e-118">Restricts the type of calls</span></span> </br><span data-ttu-id="1c61e-119">可以由用户进行的。</span><span class="sxs-lookup"><span data-stu-id="1c61e-119">that can be made by a user.</span></span>|<span data-ttu-id="1c61e-120">国际和国内 （默认值）</span><span class="sxs-lookup"><span data-stu-id="1c61e-120">International and Domestic (default)</span></span></br><span data-ttu-id="1c61e-121">国内</span><span class="sxs-lookup"><span data-stu-id="1c61e-121">Domestic</span></span></br><span data-ttu-id="1c61e-122">无</span><span class="sxs-lookup"><span data-stu-id="1c61e-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="1c61e-123">确定调用是如果被调用的电话号码是 （对于音频会议） 会议或最终用户 （如果是最终用户 PSTN 呼叫） 的组织设置 Office 365 中的国家/地区作为同一个国家在国内。</span><span class="sxs-lookup"><span data-stu-id="1c61e-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 


## <a name="restrict-audio-conferencing-outbound-calls-using-the-skype-for-business-admin-center"></a><span data-ttu-id="1c61e-124">限制音频会议的出站调用使用 Skype 业务管理中心</span><span class="sxs-lookup"><span data-stu-id="1c61e-124">Restrict audio conferencing outbound calls using the Skype for Business admin center</span></span> 


1.  <span data-ttu-id="1c61e-125">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1c61e-125">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
2.  <span data-ttu-id="1c61e-126">在有关业务管理中心在左侧的导航中，Skype 转到**音频会议** > **用户**，然后选择可用的用户列表中用户。</span><span class="sxs-lookup"><span data-stu-id="1c61e-126">In the Skype for Business admin center, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>
3.  <span data-ttu-id="1c61e-127">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="1c61e-127">In the Action pane, click **Edit**.</span></span>
4.  <span data-ttu-id="1c61e-128">在**限制到此用户的会议中拨出**选择所需的拨出限制选项。</span><span class="sxs-lookup"><span data-stu-id="1c61e-128">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![拨出选项限制](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="1c61e-130">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="1c61e-130">Click **Save**.</span></span>

## <a name="restrict-audio-conferencing-and-end-user-outbound-calls-using-powershell"></a><span data-ttu-id="1c61e-131">限制音频会议和最终用户的出站调用使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c61e-131">Restrict audio conferencing and end user outbound calls using PowerShell</span></span>

<span data-ttu-id="1c61e-132">由一个称为 OnlineDialOutPolicy 具有限制属性为每个策略控制出站呼叫限制。</span><span class="sxs-lookup"><span data-stu-id="1c61e-132">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="1c61e-133">不能自定义策略，而是在预定义的策略情况下，每个组合的设置。</span><span class="sxs-lookup"><span data-stu-id="1c61e-133">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="1c61e-134">可以使用 Get CSOnlineDialOutPolicy cmdlet 以查看出站调用策略并将它们分配给用户，通过授予 CSDialOutPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1c61e-134">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="1c61e-135">（请注意，授予 cmdlet 不包含单词"联机"Get cmdlet 一样。）</span><span class="sxs-lookup"><span data-stu-id="1c61e-135">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="1c61e-136">下表概述了每个策略。</span><span class="sxs-lookup"><span data-stu-id="1c61e-136">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1c61e-137">标识 = 标记： DialoutCPCandPSTNInternational</span><span class="sxs-lookup"><span data-stu-id="1c61e-137">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="1c61e-138">会议中的用户可以对国际和国内数字拨出，该用户还可以为国际和国内的数字的出站调用。</span><span class="sxs-lookup"><span data-stu-id="1c61e-138">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="1c61e-139">标识 = 标记： DialoutCPCDomesticPSTNInternational</span><span class="sxs-lookup"><span data-stu-id="1c61e-139">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="1c61e-140">在会议中的用户只能拨出对国内数字，和此用户可以进行出站呼叫的国际和国内的号码。</span><span class="sxs-lookup"><span data-stu-id="1c61e-140">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="1c61e-141">标识 = 标记： DialoutCPCDisabledPSTNInternational</span><span class="sxs-lookup"><span data-stu-id="1c61e-141">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="1c61e-142">在会议中的用户无法进行任何拨。此用户可以制作出站呼叫的国际和国内的号码。</span><span class="sxs-lookup"><span data-stu-id="1c61e-142">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="1c61e-143">标识 = 标记： DialoutCPCInternationalPSTNDomestic</span><span class="sxs-lookup"><span data-stu-id="1c61e-143">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="1c61e-144">用户在大会于国际和国内的号码，可拨出和此用户只能使国内 PSTN 号码的出站调用。</span><span class="sxs-lookup"><span data-stu-id="1c61e-144">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="1c61e-145">标识 = 标记： DialoutCPCInternationalPSTNDisabled</span><span class="sxs-lookup"><span data-stu-id="1c61e-145">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="1c61e-146">于国际和国内的号码，用户在会议中的可以拨出，该用户不能进行任何出站呼叫 PSTN 数字除了紧急号码。</span><span class="sxs-lookup"><span data-stu-id="1c61e-146">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="1c61e-147">标识 = 标记： DialoutCPCandPSTNDomestic</span><span class="sxs-lookup"><span data-stu-id="1c61e-147">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="1c61e-148">在会议中的用户只能拨出对国内数字，和该用户只能使国内 PSTN 号对出站调用。</span><span class="sxs-lookup"><span data-stu-id="1c61e-148">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="1c61e-149">标识 = 标记： DialoutCPCDomesticPSTNDisabled</span><span class="sxs-lookup"><span data-stu-id="1c61e-149">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="1c61e-150">在会议中的用户只能拨出对国内数字，和此用户不能进行任何出站呼叫 PSTN 数字除了紧急号码。</span><span class="sxs-lookup"><span data-stu-id="1c61e-150">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="1c61e-151">标识 = 标记： DialoutCPCDisabledPSTNDomestic</span><span class="sxs-lookup"><span data-stu-id="1c61e-151">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="1c61e-152">在会议中的用户不能进行任何拨出，并且此用户只能使国内 PSTN 号对出站调用。</span><span class="sxs-lookup"><span data-stu-id="1c61e-152">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="1c61e-153">标识 = 标记： DialoutCPCandPSTNDisabled</span><span class="sxs-lookup"><span data-stu-id="1c61e-153">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="1c61e-154">在会议中的用户不能进行任何拨出，并且此用户不能进行任何出站呼叫 PSTN 数字除了紧急号码。</span><span class="sxs-lookup"><span data-stu-id="1c61e-154">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
