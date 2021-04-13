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
description: 了解如何在 Microsoft Teams 中创建、修改用户以及将其添加到自定义呼叫策略，以及各种呼叫策略设置。
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
ms.openlocfilehash: e469cc183134bab35855e83257126029ce78a8cc
ms.sourcegitcommit: c80af314f1a573f99dd66858301c004ccc5410d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2021
ms.locfileid: "51653945"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="4fa6e-103">Microsoft Teams 中的呼叫策略</span><span class="sxs-lookup"><span data-stu-id="4fa6e-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="4fa6e-104">在 Microsoft Teams 中，呼叫策略控制哪些呼叫和呼叫转发功能可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="4fa6e-105">呼叫策略确定用户是否可以进行私人呼叫、使用呼叫转发或同时拨打其他用户或外部电话号码、将呼叫路由到语音邮件、将呼叫发送到呼叫组、对入站和出站呼叫使用委派，等等。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="4fa6e-106">可以使用自动创建的 (组织范围的) 策略，或者创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="4fa6e-107">创建自定义调用策略</span><span class="sxs-lookup"><span data-stu-id="4fa6e-107">Create a custom calling policy</span></span>

<span data-ttu-id="4fa6e-108">按照以下步骤创建自定义调用策略。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="4fa6e-109">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"语音**  >  **呼叫策略"。**</span><span class="sxs-lookup"><span data-stu-id="4fa6e-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="4fa6e-110">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-110">Select **Add**.</span></span>
3. <span data-ttu-id="4fa6e-111">打开或关闭要用于呼叫策略的功能。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="4fa6e-112">若要控制用户是否可以将入站呼叫路由到语音邮件，请选择"**已启用"或**"**用户控制"。**</span><span class="sxs-lookup"><span data-stu-id="4fa6e-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="4fa6e-113">若要阻止路由到语音邮件，请选择"已 **禁用"。**</span><span class="sxs-lookup"><span data-stu-id="4fa6e-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="4fa6e-114">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="4fa6e-115">编辑呼叫策略</span><span class="sxs-lookup"><span data-stu-id="4fa6e-115">Edit a calling policy</span></span>

<span data-ttu-id="4fa6e-116">按照以下步骤编辑现有的调用策略。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="4fa6e-117">在 Microsoft Teams 管理中心的左侧导航栏中，选择"**语音**  >  **呼叫策略"。**</span><span class="sxs-lookup"><span data-stu-id="4fa6e-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="4fa6e-118">单击要修改的策略旁边的 ，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="4fa6e-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="4fa6e-119">进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="4fa6e-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="4fa6e-120">向用户分配自定义呼叫策略</span><span class="sxs-lookup"><span data-stu-id="4fa6e-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="4fa6e-121">调用策略设置</span><span class="sxs-lookup"><span data-stu-id="4fa6e-121">Calling policy settings</span></span>

<span data-ttu-id="4fa6e-122">下面是你可以为调用策略配置的设置。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="4fa6e-123">拨打私人电话</span><span class="sxs-lookup"><span data-stu-id="4fa6e-123">Make private calls</span></span>

<span data-ttu-id="4fa6e-124">此设置控制 Teams 中的所有通话功能。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="4fa6e-125">关闭此选项可关闭 Teams 中的所有通话功能。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="4fa6e-126">呼叫转发和同时拨打给您的组织中的人员</span><span class="sxs-lookup"><span data-stu-id="4fa6e-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="4fa6e-127">此设置控制传入呼叫是否可以转发给其他用户，还是可以同时拨打其他人。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="4fa6e-128">呼叫转发和同时拨打外部电话号码</span><span class="sxs-lookup"><span data-stu-id="4fa6e-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="4fa6e-129">此设置控制传入呼叫是否可以转发到外部号码，或者是否可以同时拨打外部号码。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="4fa6e-130">语音邮件可用于路由入站呼叫</span><span class="sxs-lookup"><span data-stu-id="4fa6e-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="4fa6e-131">此设置允许将入站呼叫发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="4fa6e-132">有效选项包括：</span><span class="sxs-lookup"><span data-stu-id="4fa6e-132">Valid options are:</span></span>

- <span data-ttu-id="4fa6e-133">**已启用** 语音邮件始终可用于入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="4fa6e-134">**已禁用**  语音邮件不可用于入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="4fa6e-135">**用户控制** 用户可以确定是否希望语音邮件可用。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="4fa6e-136">入站呼叫可以路由到呼叫组</span><span class="sxs-lookup"><span data-stu-id="4fa6e-136">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="4fa6e-137">此设置控制是否可以将传入呼叫转发到呼叫组。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="4fa6e-138">允许委派入站和出站呼叫</span><span class="sxs-lookup"><span data-stu-id="4fa6e-138">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="4fa6e-139">此设置允许将入站呼叫路由到代理人，允许代理人代表其具有委派权限的用户进行出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="4fa6e-140">有关详细信息，请参阅 [与代理人共享电话线](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="4fa6e-141">防止收费绕过并通过 PSTN 发送呼叫</span><span class="sxs-lookup"><span data-stu-id="4fa6e-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="4fa6e-142">将此设置 **设置为"开** "会通过 PSTN 发送呼叫并产生费用，而不是通过网络发送呼叫和绕过收费。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="4fa6e-143">呼叫时"忙碌"可用</span><span class="sxs-lookup"><span data-stu-id="4fa6e-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="4fa6e-144">"忙碌" (") "选项"是一个新设置，用于配置在用户已处于呼叫或会议状态或呼叫处于保持状态时如何处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="4fa6e-145">新的或传入的呼叫可能会被拒绝并发出繁忙信号，也可以相应地根据用户的未答设置进行路由。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-145">New or incoming calls can be rejected with a busy signal or can be routed accordingly to the user's unanswered settings.</span></span> <span data-ttu-id="4fa6e-146">可以在租户级别或用户级别启用繁忙选项。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="4fa6e-147">无论如何配置其忙碌选项，呼叫或会议中的用户或呼叫保持的用户不会阻止发起新的呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="4fa6e-148">此设置在默认情况下处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="4fa6e-149">允许 Web PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="4fa6e-149">Allow web PSTN calling</span></span>

<span data-ttu-id="4fa6e-150">此设置允许用户使用 Teams Web 客户端呼叫 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="4fa6e-151">允许保留音乐</span><span class="sxs-lookup"><span data-stu-id="4fa6e-151">Allow music on hold</span></span>

<span data-ttu-id="4fa6e-152">此设置允许你在 PSTN 呼叫者处于保持状态时打开或关闭保持音乐。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="4fa6e-153">默认情况下，它已打开。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-153">It's turned on by default.</span></span> <span data-ttu-id="4fa6e-154">此设置不适用于呼叫公园和老板代理人功能，目前仅通过 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="4fa6e-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4fa6e-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="4fa6e-155">Related topics</span></span>

[<span data-ttu-id="4fa6e-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="4fa6e-156">Set-CSTeamsCallingPolicy</span></span>](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="4fa6e-157">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="4fa6e-157">Assign policies to your users in Teams</span></span>](assign-policies.md)