---
title: Microsoft Teams 中的呼叫策略
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 了解如何在 Microsoft 团队中调用策略设置。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-voice
f1keywords:
- ms.teamsadmincenter.callingpolicies.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 788cc0e93b16585f1d3424d3bfa0a62693528740
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972443"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="58db1-103">Microsoft Teams 中的呼叫策略</span><span class="sxs-lookup"><span data-stu-id="58db1-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="58db1-104">在 Microsoft 团队中，呼叫策略控制用户可以使用哪些呼叫和呼叫转接功能。</span><span class="sxs-lookup"><span data-stu-id="58db1-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="58db1-105">呼叫策略确定用户是否可以进行私人呼叫、使用呼叫转接或同时拨打给其他用户或外部电话号码、将呼叫路由到语音邮件、将呼叫发送到呼叫组、将呼叫发送到拨入和出站呼叫等。</span><span class="sxs-lookup"><span data-stu-id="58db1-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="58db1-106">默认全局策略是自动创建的，但是管理员还可以创建和分配自定义呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="58db1-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="58db1-107">创建自定义呼叫策略</span><span class="sxs-lookup"><span data-stu-id="58db1-107">Create a custom calling policy</span></span>

<span data-ttu-id="58db1-108">请按照以下步骤创建自定义呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="58db1-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="58db1-109">在 "Microsoft 团队管理中心" 中，选择 "**语音** > **呼叫策略**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="58db1-110">选择 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-110">Select **New policy**.</span></span>
3. <span data-ttu-id="58db1-111">打开要在呼叫策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="58db1-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="58db1-112">默认情况下，所有选项均处于**关闭状态**。</span><span class="sxs-lookup"><span data-stu-id="58db1-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="58db1-113">若要控制用户是否可以将入站呼叫路由到语音邮件，请选择 "**始终启用**" 或 "**用户控制**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="58db1-114">若要阻止路由到语音邮件，请选择 "**始终禁用**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="58db1-115">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="58db1-116">修改现有呼叫策略</span><span class="sxs-lookup"><span data-stu-id="58db1-116">Modify an existing calling policy</span></span>

<span data-ttu-id="58db1-117">请按照以下步骤修改现有的呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="58db1-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="58db1-118">在 "Microsoft 团队管理中心" 中，选择 "**语音** > **呼叫策略**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="58db1-119">单击要修改的策略旁边的，然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="58db1-120">打开要在呼叫策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="58db1-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="58db1-121">默认情况下，所有选项均处于**关闭状态**。</span><span class="sxs-lookup"><span data-stu-id="58db1-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="58db1-122">若要控制用户是否可以将入站呼叫路由到语音邮件，请选择 "**始终启用**" 或 "**用户控制**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="58db1-123">若要阻止路由到语音邮件，请选择 "**始终禁用**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="58db1-124">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="58db1-125">向用户分配呼叫策略</span><span class="sxs-lookup"><span data-stu-id="58db1-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="58db1-126">按照以下步骤将自定义呼叫策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="58db1-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="58db1-127">在 "Microsoft 团队管理中心" 中，选择 "**语音** > **呼叫策略**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="58db1-128">单击策略名称旁边的以将其选中，然后选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="58db1-129">在 "**管理用户**" 窗格中，搜索用户的名称。</span><span class="sxs-lookup"><span data-stu-id="58db1-129">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="58db1-130">（必须至少输入三个字符。）</span><span class="sxs-lookup"><span data-stu-id="58db1-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="58db1-131">选择用户的名称，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-131">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="58db1-132">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="58db1-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="58db1-133">呼叫策略设置</span><span class="sxs-lookup"><span data-stu-id="58db1-133">Calling policy settings</span></span>

<span data-ttu-id="58db1-134">使用以下设置创建自定义呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="58db1-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="58db1-135">用户可以进行私人通话</span><span class="sxs-lookup"><span data-stu-id="58db1-135">User can make private calls</span></span>

<span data-ttu-id="58db1-136">此设置控制团队中的所有呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="58db1-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="58db1-137">关闭此功能以关闭团队中的所有通话功能。</span><span class="sxs-lookup"><span data-stu-id="58db1-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="58db1-138">呼叫转接和同时拨打给其他用户</span><span class="sxs-lookup"><span data-stu-id="58db1-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="58db1-139">此设置控制是否可以将传入呼叫转发给其他用户，或者可以同时拨打其他用户。</span><span class="sxs-lookup"><span data-stu-id="58db1-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="58db1-140">呼叫转接和同时拨打外部电话号码</span><span class="sxs-lookup"><span data-stu-id="58db1-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="58db1-141">此设置控制是否可以将传入呼叫转发到外部号码或同时拨打外部号码。</span><span class="sxs-lookup"><span data-stu-id="58db1-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="58db1-142">语音邮件可用于将入站呼叫路由到用户</span><span class="sxs-lookup"><span data-stu-id="58db1-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="58db1-143">此设置允许将入站呼叫发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="58db1-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="58db1-144">有效选项包括：</span><span class="sxs-lookup"><span data-stu-id="58db1-144">Valid options are:</span></span>

   - <span data-ttu-id="58db1-145">**始终启用**语音邮件始终可用于拨入呼叫。</span><span class="sxs-lookup"><span data-stu-id="58db1-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="58db1-146">**始终禁用** 语音邮件不可用于入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="58db1-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="58db1-147">**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="58db1-147">**User controlled**.</span></span> <span data-ttu-id="58db1-148">用户可以确定是否希望语音邮件可用。</span><span class="sxs-lookup"><span data-stu-id="58db1-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="58db1-149">入站呼叫可以路由到呼叫组</span><span class="sxs-lookup"><span data-stu-id="58db1-149">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="58db1-150">此设置控制是否可以将传入呼叫转移到呼叫组。</span><span class="sxs-lookup"><span data-stu-id="58db1-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="58db1-151">允许委派入站和出站呼叫</span><span class="sxs-lookup"><span data-stu-id="58db1-151">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="58db1-152">此设置使入站呼叫能够路由到代理人，从而允许代理人代表他们为其委派权限的用户发出出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="58db1-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="58db1-153">有关详细信息，请参阅[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="58db1-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="58db1-154">通过 PSTN 阻止电话绕过和发送呼叫</span><span class="sxs-lookup"><span data-stu-id="58db1-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="58db1-155">将此设置为 **"开**" 将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送，而是绕过 tolls。</span><span class="sxs-lookup"><span data-stu-id="58db1-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="58db1-156">通话时，忙闲电话可用</span><span class="sxs-lookup"><span data-stu-id="58db1-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="58db1-157">忙/闲（忙碌选项））是团队调用策略的新设置，可让你配置当用户已加入通话或会议或有呼叫处于保持状态时如何处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="58db1-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="58db1-158">可以使用占线信号拒绝新电话或拨入电话。</span><span class="sxs-lookup"><span data-stu-id="58db1-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="58db1-159">你可以在租户级别或用户级别启用繁忙选项。</span><span class="sxs-lookup"><span data-stu-id="58db1-159">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="58db1-160">无论其繁忙选项是如何配置的，通话或会议中的用户或通话暂停的用户都不会被阻止发起新的通话或会议。</span><span class="sxs-lookup"><span data-stu-id="58db1-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="58db1-161">默认情况下，此设置处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="58db1-161">This setting is disabled by default.</span></span>

## <a name="see-also"></a><span data-ttu-id="58db1-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58db1-162">See also</span></span>

[<span data-ttu-id="58db1-163">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="58db1-163">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)