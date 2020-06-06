---
title: Microsoft Teams 中的呼叫策略
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 了解如何创建、修改用户以及将用户添加到 Microsoft 团队中的自定义呼叫策略以及各种通话策略设置。
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a67952854f608512e88786c2b49d1e2ad8dfcf9
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2020
ms.locfileid: "44592840"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="d0441-103">Microsoft Teams 中的呼叫策略</span><span class="sxs-lookup"><span data-stu-id="d0441-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="d0441-104">在 Microsoft 团队中，呼叫策略控制用户可以使用哪些呼叫和呼叫转接功能。</span><span class="sxs-lookup"><span data-stu-id="d0441-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="d0441-105">呼叫策略确定用户是否可以进行私人呼叫、使用呼叫转接或同时拨打给其他用户或外部电话号码、将呼叫路由到语音邮件、将呼叫发送到呼叫组、将呼叫发送到拨入和出站呼叫等。</span><span class="sxs-lookup"><span data-stu-id="d0441-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="d0441-106">默认全局策略是自动创建的，但是管理员还可以创建和分配自定义呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="d0441-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="d0441-107">创建自定义呼叫策略</span><span class="sxs-lookup"><span data-stu-id="d0441-107">Create a custom calling policy</span></span>

<span data-ttu-id="d0441-108">请按照以下步骤创建自定义呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="d0441-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="d0441-109">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫策略**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="d0441-110">选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-110">Select **Add**.</span></span>
3. <span data-ttu-id="d0441-111">打开或关闭要在呼叫策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="d0441-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="d0441-112">要控制用户是否可以将入站呼叫路由到语音邮件，请选择 "**已启用**" 或 "**用户控制**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="d0441-113">若要阻止路由到语音邮件，请选择 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="d0441-114">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-114">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="d0441-115">修改现有呼叫策略</span><span class="sxs-lookup"><span data-stu-id="d0441-115">Modify an existing calling policy</span></span>

<span data-ttu-id="d0441-116">请按照以下步骤修改现有的呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="d0441-116">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="d0441-117">在 Microsoft 团队管理中心的左侧导航中，选择 "**语音**  >  **呼叫策略**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="d0441-118">单击要修改的策略旁边的，然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="d0441-119">进行所需的更改，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="d0441-120">为用户分配自定义呼叫策略</span><span class="sxs-lookup"><span data-stu-id="d0441-120">Assign a custom calling policy to users</span></span>

<span data-ttu-id="d0441-121">若要向一个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0441-121">To assign a policy to one user:</span></span>

1. <span data-ttu-id="d0441-122">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d0441-122">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="d0441-123">单击用户名的左侧以选择用户，然后单击“编辑设置”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d0441-123">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="d0441-124">在 "**呼叫策略**" 下，选择要分配的呼叫策略，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-124">Under **Calling policy**, select the calling policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="d0441-125">要一次为多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0441-125">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="d0441-126">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后搜索用户或筛选视图以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="d0441-126">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="d0441-127">在 " **&#x2713;** " （复选标记）列中，选择用户。</span><span class="sxs-lookup"><span data-stu-id="d0441-127">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d0441-128">若要选择 "所有用户"，请单击表格顶部的 "&#x2713;" （复选标记）。</span><span class="sxs-lookup"><span data-stu-id="d0441-128">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="d0441-129">单击 "**编辑设置**"，进行所需的更改，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-129">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="d0441-130">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0441-130">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d0441-131">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫策略**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="d0441-132">单击策略名称的左侧以选择该策略。</span><span class="sxs-lookup"><span data-stu-id="d0441-132">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d0441-133">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0441-133">Select **Manage users**.</span></span>
4. <span data-ttu-id="d0441-134">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d0441-134">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d0441-135">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="d0441-135">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d0441-136">添加完用户后，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d0441-136">After you finish adding users, select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="d0441-137">呼叫策略设置</span><span class="sxs-lookup"><span data-stu-id="d0441-137">Calling policy settings</span></span>

<span data-ttu-id="d0441-138">下面是您可以为呼叫策略配置的设置。</span><span class="sxs-lookup"><span data-stu-id="d0441-138">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="d0441-139">拨打私人电话</span><span class="sxs-lookup"><span data-stu-id="d0441-139">Make private calls</span></span>

<span data-ttu-id="d0441-140">此设置控制团队中的所有呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="d0441-140">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="d0441-141">关闭此功能以关闭团队中的所有通话功能。</span><span class="sxs-lookup"><span data-stu-id="d0441-141">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="d0441-142">呼叫转接和同时拨打您组织中的人员</span><span class="sxs-lookup"><span data-stu-id="d0441-142">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="d0441-143">此设置控制是否可以将传入呼叫转发给其他用户，或者可以同时拨打其他用户。</span><span class="sxs-lookup"><span data-stu-id="d0441-143">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="d0441-144">呼叫转接和同时拨打外部电话号码</span><span class="sxs-lookup"><span data-stu-id="d0441-144">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="d0441-145">此设置控制是否可以将传入呼叫转发到外部号码或同时拨打外部号码。</span><span class="sxs-lookup"><span data-stu-id="d0441-145">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="d0441-146">语音邮件可用于路由入站呼叫</span><span class="sxs-lookup"><span data-stu-id="d0441-146">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="d0441-147">此设置允许将入站呼叫发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="d0441-147">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="d0441-148">有效选项包括：</span><span class="sxs-lookup"><span data-stu-id="d0441-148">Valid options are:</span></span>

- <span data-ttu-id="d0441-149">**已启用**语音邮件始终可用于拨入呼叫。</span><span class="sxs-lookup"><span data-stu-id="d0441-149">**Enabled** Voicemail is always available for inbound calls.</span></span> 
- <span data-ttu-id="d0441-150">**已禁用** 语音邮件不可用于入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="d0441-150">**Disabled**  Voicemail is not available for inbound calls.</span></span> 
- <span data-ttu-id="d0441-151">**用户控制**用户可以确定是否希望语音邮件可用。</span><span class="sxs-lookup"><span data-stu-id="d0441-151">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="d0441-152">入站呼叫可以路由到呼叫组</span><span class="sxs-lookup"><span data-stu-id="d0441-152">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="d0441-153">此设置控制是否可以将传入呼叫转移到呼叫组。</span><span class="sxs-lookup"><span data-stu-id="d0441-153">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="d0441-154">允许委派入站和出站呼叫</span><span class="sxs-lookup"><span data-stu-id="d0441-154">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="d0441-155">此设置使入站呼叫能够路由到代理人，从而允许代理人代表他们为其委派权限的用户发出出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="d0441-155">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="d0441-156">有关详细信息，请参阅[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="d0441-156">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="d0441-157">通过 PSTN 阻止电话绕过和发送呼叫</span><span class="sxs-lookup"><span data-stu-id="d0441-157">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="d0441-158">将此设置为 **"开**" 将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送，而是绕过 tolls。</span><span class="sxs-lookup"><span data-stu-id="d0441-158">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="d0441-159">通话时，忙闲电话可用</span><span class="sxs-lookup"><span data-stu-id="d0441-159">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="d0441-160">忙/闲（忙碌选项）是一种新设置，可让你配置当用户已加入通话或会议或有呼叫处于保持状态时如何处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="d0441-160">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="d0441-161">可以使用占线信号拒绝新电话或拨入电话。</span><span class="sxs-lookup"><span data-stu-id="d0441-161">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="d0441-162">你可以在租户级别或用户级别启用繁忙选项。</span><span class="sxs-lookup"><span data-stu-id="d0441-162">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="d0441-163">无论其繁忙选项是如何配置的，通话或会议中的用户或通话暂停的用户都不会被阻止发起新的通话或会议。</span><span class="sxs-lookup"><span data-stu-id="d0441-163">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="d0441-164">默认情况下，此设置处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="d0441-164">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="d0441-165">允许 web PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="d0441-165">Allow web PSTN calling</span></span>

<span data-ttu-id="d0441-166">此设置使用户能够使用团队 web 客户端呼叫 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="d0441-166">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="d0441-167">允许暂停音乐</span><span class="sxs-lookup"><span data-stu-id="d0441-167">Allow music on hold</span></span>

<span data-ttu-id="d0441-168">此设置允许你在将 PSTN 呼叫者置于保持状态时启用或禁用保留的音乐。</span><span class="sxs-lookup"><span data-stu-id="d0441-168">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="d0441-169">默认情况下，它处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="d0441-169">It's turned on by default.</span></span> <span data-ttu-id="d0441-170">此设置不适用于呼叫寄存和老板代理人功能，并且目前仅可通过 PowerShell 使用。</span><span class="sxs-lookup"><span data-stu-id="d0441-170">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0441-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0441-171">See also</span></span>

[<span data-ttu-id="d0441-172">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="d0441-172">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
