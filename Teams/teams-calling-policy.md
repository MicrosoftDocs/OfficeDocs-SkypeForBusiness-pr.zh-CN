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
description: 了解如何在 Microsoft Teams 中创建、修改用户和将用户添加到自定义呼叫策略，以及各种调用策略设置。
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
ms.openlocfilehash: 6cfa0043b4da6c3087c0e144bb0759ed5b87f01c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50465392"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="f1c54-103">Microsoft Teams 中的呼叫策略</span><span class="sxs-lookup"><span data-stu-id="f1c54-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="f1c54-104">在 Microsoft Teams 中，调用策略控制哪些呼叫和呼叫转发功能可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="f1c54-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="f1c54-105">呼叫策略确定用户是否可以进行私人呼叫、使用呼叫转发或同时拨打其他用户或外部电话号码、将呼叫路由到语音邮件、将呼叫发送到呼叫组、对入站和出站呼叫使用委派等。</span><span class="sxs-lookup"><span data-stu-id="f1c54-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="f1c54-106">可以使用自动创建的 (组织范围的) 策略，或者创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="f1c54-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="f1c54-107">创建自定义调用策略</span><span class="sxs-lookup"><span data-stu-id="f1c54-107">Create a custom calling policy</span></span>

<span data-ttu-id="f1c54-108">请按照以下步骤创建自定义调用策略。</span><span class="sxs-lookup"><span data-stu-id="f1c54-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="f1c54-109">在 Microsoft Teams 管理中心的左侧导航中，转到 **语音**  >  **呼叫策略**。</span><span class="sxs-lookup"><span data-stu-id="f1c54-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="f1c54-110">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="f1c54-110">Select **Add**.</span></span>
3. <span data-ttu-id="f1c54-111">打开或关闭要用于调用策略的功能。</span><span class="sxs-lookup"><span data-stu-id="f1c54-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="f1c54-112">若要控制用户是否可以将入站呼叫路由到语音邮件，请选择 **"已启用**"或"**用户控制"。**</span><span class="sxs-lookup"><span data-stu-id="f1c54-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="f1c54-113">若要阻止路由到语音邮件，请选择"**已禁用"。**</span><span class="sxs-lookup"><span data-stu-id="f1c54-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="f1c54-114">选择 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="f1c54-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="f1c54-115">编辑呼叫策略</span><span class="sxs-lookup"><span data-stu-id="f1c54-115">Edit a calling policy</span></span>

<span data-ttu-id="f1c54-116">请按照以下步骤编辑现有调用策略。</span><span class="sxs-lookup"><span data-stu-id="f1c54-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="f1c54-117">在 Microsoft Teams 管理中心的左侧导航栏中，选择 **"语音**  >  **呼叫策略"。**</span><span class="sxs-lookup"><span data-stu-id="f1c54-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="f1c54-118">单击要修改的策略旁边，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="f1c54-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="f1c54-119">进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="f1c54-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="f1c54-120">向用户分配自定义呼叫策略</span><span class="sxs-lookup"><span data-stu-id="f1c54-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="f1c54-121">调用策略设置</span><span class="sxs-lookup"><span data-stu-id="f1c54-121">Calling policy settings</span></span>

<span data-ttu-id="f1c54-122">下面是你可以为调用策略配置的设置。</span><span class="sxs-lookup"><span data-stu-id="f1c54-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="f1c54-123">拨打私人电话</span><span class="sxs-lookup"><span data-stu-id="f1c54-123">Make private calls</span></span>

<span data-ttu-id="f1c54-124">此设置控制 Teams 中的所有调用功能。</span><span class="sxs-lookup"><span data-stu-id="f1c54-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="f1c54-125">关闭此选项可关闭 Teams 中的所有通话功能。</span><span class="sxs-lookup"><span data-stu-id="f1c54-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="f1c54-126">呼叫呼叫转发和同时拨打给您的组织中的人员</span><span class="sxs-lookup"><span data-stu-id="f1c54-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="f1c54-127">此设置控制传入呼叫是否可以转发给其他用户，还是可以同时拨打其他人。</span><span class="sxs-lookup"><span data-stu-id="f1c54-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="f1c54-128">呼叫转发和同时拨打外部电话号码</span><span class="sxs-lookup"><span data-stu-id="f1c54-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="f1c54-129">此设置控制传入呼叫是否可以转发到外部号码，还是可以同时拨打外部号码。</span><span class="sxs-lookup"><span data-stu-id="f1c54-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="f1c54-130">语音邮件可用于路由入站呼叫</span><span class="sxs-lookup"><span data-stu-id="f1c54-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="f1c54-131">此设置允许将入站呼叫发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f1c54-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="f1c54-132">有效选项包括：</span><span class="sxs-lookup"><span data-stu-id="f1c54-132">Valid options are:</span></span>

- <span data-ttu-id="f1c54-133">**已启用** 语音邮件始终可用于入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="f1c54-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="f1c54-134">**已禁用**  语音邮件不可用于入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="f1c54-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="f1c54-135">**用户控制** 用户可以确定是否希望语音邮件可用。</span><span class="sxs-lookup"><span data-stu-id="f1c54-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="f1c54-136">入站呼叫可以路由到呼叫组</span><span class="sxs-lookup"><span data-stu-id="f1c54-136">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="f1c54-137">此设置控制传入呼叫是否可以转发到呼叫组。</span><span class="sxs-lookup"><span data-stu-id="f1c54-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="f1c54-138">允许委派入站和出站呼叫</span><span class="sxs-lookup"><span data-stu-id="f1c54-138">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="f1c54-139">此设置允许将入站呼叫路由到代理人，允许代理人代表他们拥有委派权限的用户进行出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="f1c54-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="f1c54-140">有关详细信息，请参阅"与[代理人共享电话线"。](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="f1c54-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="f1c54-141">防止绕过收费站并通过 PSTN 发送呼叫</span><span class="sxs-lookup"><span data-stu-id="f1c54-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="f1c54-142">将此设置设置为 **"开** "将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送呼叫并绕过收费站。</span><span class="sxs-lookup"><span data-stu-id="f1c54-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="f1c54-143">呼叫时"忙碌"可用</span><span class="sxs-lookup"><span data-stu-id="f1c54-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="f1c54-144">"忙碌 (") "选项"是一个新设置，可用于配置当用户已进入呼叫或会议或已暂停呼叫时如何处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="f1c54-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="f1c54-145">新呼叫或传入呼叫可能会被拒绝，但信号繁忙。</span><span class="sxs-lookup"><span data-stu-id="f1c54-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="f1c54-146">可以在租户级别或用户级别启用忙选项。</span><span class="sxs-lookup"><span data-stu-id="f1c54-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="f1c54-147">无论其忙选项的配置方式如何，呼叫或会议中的用户或保持通话的用户不会阻止其发起新的呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="f1c54-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="f1c54-148">此设置默认处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="f1c54-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="f1c54-149">允许 Web PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="f1c54-149">Allow web PSTN calling</span></span>

<span data-ttu-id="f1c54-150">此设置允许用户使用 Teams Web 客户端呼叫 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="f1c54-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="f1c54-151">允许音乐保持</span><span class="sxs-lookup"><span data-stu-id="f1c54-151">Allow music on hold</span></span>

<span data-ttu-id="f1c54-152">此设置允许你在 PSTN 呼叫者处于保留状态时打开或关闭保持音乐。</span><span class="sxs-lookup"><span data-stu-id="f1c54-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="f1c54-153">默认情况下，它已打开。</span><span class="sxs-lookup"><span data-stu-id="f1c54-153">It's turned on by default.</span></span> <span data-ttu-id="f1c54-154">此设置不适用于呼叫公园和老板代理人功能，当前仅可通过 PowerShell 使用。</span><span class="sxs-lookup"><span data-stu-id="f1c54-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f1c54-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="f1c54-155">Related topics</span></span>

[<span data-ttu-id="f1c54-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="f1c54-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="f1c54-157">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="f1c54-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
