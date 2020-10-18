---
title: Microsoft Teams 中的呼叫策略
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 了解如何创建、修改用户以及将用户添加到 Microsoft 团队中的自定义呼叫策略以及各种通话策略设置。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581070"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="76544-103">Microsoft Teams 中的呼叫策略</span><span class="sxs-lookup"><span data-stu-id="76544-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="76544-104">在 Microsoft 团队中，呼叫策略控制用户可以使用哪些呼叫和呼叫转接功能。</span><span class="sxs-lookup"><span data-stu-id="76544-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="76544-105">呼叫策略确定用户是否可以进行私人呼叫、使用呼叫转接或同时拨打给其他用户或外部电话号码、将呼叫路由到语音邮件、将呼叫发送到呼叫组、将呼叫发送到拨入和出站呼叫等。</span><span class="sxs-lookup"><span data-stu-id="76544-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="76544-106">你可以使用全局 (组织范围的默认) 策略，该策略自动创建，或者创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="76544-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="76544-107">创建自定义呼叫策略</span><span class="sxs-lookup"><span data-stu-id="76544-107">Create a custom calling policy</span></span>

<span data-ttu-id="76544-108">请按照以下步骤创建自定义呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="76544-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="76544-109">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫策略**"。</span><span class="sxs-lookup"><span data-stu-id="76544-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="76544-110">选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="76544-110">Select **Add**.</span></span>
3. <span data-ttu-id="76544-111">打开或关闭要在呼叫策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="76544-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="76544-112">要控制用户是否可以将入站呼叫路由到语音邮件，请选择 " **已启用** " 或 " **用户控制**"。</span><span class="sxs-lookup"><span data-stu-id="76544-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="76544-113">若要阻止路由到语音邮件，请选择 " **已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="76544-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="76544-114">选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="76544-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="76544-115">编辑呼叫策略</span><span class="sxs-lookup"><span data-stu-id="76544-115">Edit a calling policy</span></span>

<span data-ttu-id="76544-116">请按照以下步骤编辑现有呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="76544-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="76544-117">在 Microsoft 团队管理中心的左侧导航中，选择 "**语音**  >  **呼叫策略**"。</span><span class="sxs-lookup"><span data-stu-id="76544-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="76544-118">单击要修改的策略旁边的，然后选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="76544-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="76544-119">进行所需的更改，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="76544-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="76544-120">为用户分配自定义呼叫策略</span><span class="sxs-lookup"><span data-stu-id="76544-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="76544-121">呼叫策略设置</span><span class="sxs-lookup"><span data-stu-id="76544-121">Calling policy settings</span></span>

<span data-ttu-id="76544-122">下面是您可以为呼叫策略配置的设置。</span><span class="sxs-lookup"><span data-stu-id="76544-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="76544-123">拨打私人电话</span><span class="sxs-lookup"><span data-stu-id="76544-123">Make private calls</span></span>

<span data-ttu-id="76544-124">此设置控制团队中的所有呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="76544-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="76544-125">关闭此功能以关闭团队中的所有通话功能。</span><span class="sxs-lookup"><span data-stu-id="76544-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="76544-126">呼叫转接和同时拨打您组织中的人员</span><span class="sxs-lookup"><span data-stu-id="76544-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="76544-127">此设置控制是否可以将传入呼叫转发给其他用户，或者可以同时拨打其他用户。</span><span class="sxs-lookup"><span data-stu-id="76544-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="76544-128">呼叫转接和同时拨打外部电话号码</span><span class="sxs-lookup"><span data-stu-id="76544-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="76544-129">此设置控制是否可以将传入呼叫转发到外部号码或同时拨打外部号码。</span><span class="sxs-lookup"><span data-stu-id="76544-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="76544-130">语音邮件可用于路由入站呼叫</span><span class="sxs-lookup"><span data-stu-id="76544-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="76544-131">此设置允许将入站呼叫发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="76544-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="76544-132">有效选项包括：</span><span class="sxs-lookup"><span data-stu-id="76544-132">Valid options are:</span></span>

- <span data-ttu-id="76544-133">**已启用** 语音邮件始终可用于拨入呼叫。</span><span class="sxs-lookup"><span data-stu-id="76544-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="76544-134">**已禁用**  语音邮件不可用于入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="76544-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="76544-135">**用户控制** 用户可以确定是否希望语音邮件可用。</span><span class="sxs-lookup"><span data-stu-id="76544-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="76544-136">入站呼叫可以路由到呼叫组</span><span class="sxs-lookup"><span data-stu-id="76544-136">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="76544-137">此设置控制是否可以将传入呼叫转移到呼叫组。</span><span class="sxs-lookup"><span data-stu-id="76544-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="76544-138">允许委派入站和出站呼叫</span><span class="sxs-lookup"><span data-stu-id="76544-138">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="76544-139">此设置使入站呼叫能够路由到代理人，从而允许代理人代表他们为其委派权限的用户发出出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="76544-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="76544-140">有关详细信息，请参阅 [与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="76544-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="76544-141">通过 PSTN 阻止电话绕过和发送呼叫</span><span class="sxs-lookup"><span data-stu-id="76544-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="76544-142">将此设置为 **"开** " 将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送，而是绕过 tolls。</span><span class="sxs-lookup"><span data-stu-id="76544-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="76544-143">通话时，忙闲电话可用</span><span class="sxs-lookup"><span data-stu-id="76544-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="76544-144">忙碌的忙 (闲选项) 是一种新设置，可让你配置当用户已加入通话或会议或有呼叫处于保持状态时如何处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="76544-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="76544-145">可以使用占线信号拒绝新电话或拨入电话。</span><span class="sxs-lookup"><span data-stu-id="76544-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="76544-146">你可以在租户级别或用户级别启用繁忙选项。</span><span class="sxs-lookup"><span data-stu-id="76544-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="76544-147">无论其繁忙选项是如何配置的，通话或会议中的用户或通话暂停的用户都不会被阻止发起新的通话或会议。</span><span class="sxs-lookup"><span data-stu-id="76544-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="76544-148">默认情况下，此设置处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="76544-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="76544-149">允许 web PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="76544-149">Allow web PSTN calling</span></span>

<span data-ttu-id="76544-150">此设置使用户能够使用团队 web 客户端呼叫 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="76544-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="76544-151">允许暂停音乐</span><span class="sxs-lookup"><span data-stu-id="76544-151">Allow music on hold</span></span>

<span data-ttu-id="76544-152">此设置允许你在将 PSTN 呼叫者置于保持状态时启用或禁用保留的音乐。</span><span class="sxs-lookup"><span data-stu-id="76544-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="76544-153">默认情况下，它处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="76544-153">It's turned on by default.</span></span> <span data-ttu-id="76544-154">此设置不适用于呼叫寄存和老板代理人功能，并且目前仅可通过 PowerShell 使用。</span><span class="sxs-lookup"><span data-stu-id="76544-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="76544-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="76544-155">Related topics</span></span>

[<span data-ttu-id="76544-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="76544-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="76544-157">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="76544-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
