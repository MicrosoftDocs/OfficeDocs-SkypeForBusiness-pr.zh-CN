---
title: Microsoft Teams 中的呼叫策略
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 了解调用中的 Microsoft 团队的策略设置。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c35c2455c3164f04dd9fdbbb210e20809a719bc6
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835324"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="ec25c-103">Microsoft Teams 中的呼叫策略</span><span class="sxs-lookup"><span data-stu-id="ec25c-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="ec25c-104">在 Microsoft 团队中，调用策略控制的呼叫和呼叫转接功能是对用户可用。</span><span class="sxs-lookup"><span data-stu-id="ec25c-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="ec25c-105">呼叫策略确定是否用户可以接听私人电话，使用呼叫转接或同时响铃到其他用户或外部电话号码，将呼叫路由到语音邮件，呼叫组发送呼叫使用的入站和出站呼叫委派，依此类推。</span><span class="sxs-lookup"><span data-stu-id="ec25c-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="ec25c-106">默认全局策略自动创建的但管理员还可以创建和分配调用的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="ec25c-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="ec25c-107">创建自定义调用策略</span><span class="sxs-lookup"><span data-stu-id="ec25c-107">Create a custom calling policy</span></span>

<span data-ttu-id="ec25c-108">按照以下步骤创建自定义调用策略。</span><span class="sxs-lookup"><span data-stu-id="ec25c-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="ec25c-109">在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="ec25c-110">选择**新策略**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-110">Select **New policy**.</span></span>
3. <span data-ttu-id="ec25c-111">打开要调用策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="ec25c-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="ec25c-112">默认情况下，所有选项都包括**关闭**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="ec25c-113">若要控制用户是否可以将到语音邮件的入站的呼叫路由，请选择**始终启用**或**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="ec25c-114">若要阻止传送到语音邮件，请选择**总是禁用**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="ec25c-115">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="ec25c-116">修改现有的调用策略</span><span class="sxs-lookup"><span data-stu-id="ec25c-116">Modify an existing calling policy</span></span>

<span data-ttu-id="ec25c-117">按照以下步骤修改现有的调用策略。</span><span class="sxs-lookup"><span data-stu-id="ec25c-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="ec25c-118">在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="ec25c-119">单击您想要修改，然后选择**编辑**策略旁边。</span><span class="sxs-lookup"><span data-stu-id="ec25c-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="ec25c-120">打开要调用策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="ec25c-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="ec25c-121">默认情况下，所有选项都包括**关闭**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="ec25c-122">若要控制用户是否可以将到语音邮件的入站的呼叫路由，请选择**始终启用**或**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="ec25c-123">若要阻止传送到语音邮件，请选择**总是禁用**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="ec25c-124">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="ec25c-125">调用策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="ec25c-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="ec25c-126">按照以下步骤将自定义调用策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="ec25c-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="ec25c-127">在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="ec25c-128">单击以选中它，然后选择**管理用户**的策略名称旁边。</span><span class="sxs-lookup"><span data-stu-id="ec25c-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="ec25c-129">在**管理用户**窗格中，搜索用户的名称。</span><span class="sxs-lookup"><span data-stu-id="ec25c-129">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="ec25c-130">（您必须输入至少三个字符）。</span><span class="sxs-lookup"><span data-stu-id="ec25c-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="ec25c-131">选择用户的名称，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-131">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="ec25c-132">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="ec25c-133">调用策略设置</span><span class="sxs-lookup"><span data-stu-id="ec25c-133">Calling policy settings</span></span>

<span data-ttu-id="ec25c-134">使用以下设置创建自定义调用策略。</span><span class="sxs-lookup"><span data-stu-id="ec25c-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="ec25c-135">用户可以接听私人电话</span><span class="sxs-lookup"><span data-stu-id="ec25c-135">User can make private calls</span></span>

<span data-ttu-id="ec25c-136">此设置控制团队中的所有呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="ec25c-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="ec25c-137">禁用此选项，将会关闭团队中的所有呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="ec25c-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="ec25c-138">呼叫转接和同时响铃向其他用户</span><span class="sxs-lookup"><span data-stu-id="ec25c-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="ec25c-139">此设置控制传入呼叫可以转移到其他用户还是可以同时拨打其他人。</span><span class="sxs-lookup"><span data-stu-id="ec25c-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="ec25c-140">呼叫转接和同时响铃到外部电话号码</span><span class="sxs-lookup"><span data-stu-id="ec25c-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="ec25c-141">此设置控制传入呼叫可以转移到外部号码还是可以同时拨打外部号码。</span><span class="sxs-lookup"><span data-stu-id="ec25c-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="ec25c-142">语音邮件是可用于向用户的入站呼叫路由</span><span class="sxs-lookup"><span data-stu-id="ec25c-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="ec25c-143">此设置，入站的呼叫就可以发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="ec25c-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="ec25c-144">有效的选项为：</span><span class="sxs-lookup"><span data-stu-id="ec25c-144">Valid options are:</span></span>

   - <span data-ttu-id="ec25c-145">**始终启用**语音邮件始终是适用于入站调用的。</span><span class="sxs-lookup"><span data-stu-id="ec25c-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="ec25c-146">**始终禁用** 不可用入站呼叫的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="ec25c-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="ec25c-147">**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="ec25c-147">**User controlled**.</span></span> <span data-ttu-id="ec25c-148">用户可以确定是否需要能够使用的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="ec25c-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="ec25c-149">入站的呼叫可以路由到呼叫组</span><span class="sxs-lookup"><span data-stu-id="ec25c-149">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="ec25c-150">此设置控制是否可以将传入呼叫转接到的呼叫组。</span><span class="sxs-lookup"><span data-stu-id="ec25c-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="ec25c-151">允许入站和出站呼叫的委派</span><span class="sxs-lookup"><span data-stu-id="ec25c-151">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="ec25c-152">此设置使入站的呼叫路由到允许代理人发起代表他们具有其委派权限的用户的出站呼叫的代理人。</span><span class="sxs-lookup"><span data-stu-id="ec25c-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="ec25c-153">有关详细信息，请参阅[共享与代理人的电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="ec25c-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="ec25c-154">阻止收费绕过和发送通过 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="ec25c-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="ec25c-155">将其设置为**上**将发送通过 PSTN 呼叫，并会导致费用而不是将其发送网络通过和绕过费。</span><span class="sxs-lookup"><span data-stu-id="ec25c-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="ec25c-156">忙闲上的有时呼叫</span><span class="sxs-lookup"><span data-stu-id="ec25c-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="ec25c-157">忙碌 （忙选项） 的忙碌） 是，您可以配置如何传入呼叫的呼叫策略处理用户已在呼叫或会议，或具有呼叫时，团队中的新设置置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="ec25c-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="ec25c-158">新的或传入呼叫可以被拒绝，并繁忙信号。</span><span class="sxs-lookup"><span data-stu-id="ec25c-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="ec25c-159">您可以启用忙选项在租户级别或在用户级别。</span><span class="sxs-lookup"><span data-stu-id="ec25c-159">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="ec25c-160">无论其忙选项的配置方式，呼叫或会议或呼叫置于保持状态的那些将不阻止用户发起新呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="ec25c-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="ec25c-161">默认情况下禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="ec25c-161">This setting is disabled by default.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec25c-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec25c-162">See also</span></span>

[<span data-ttu-id="ec25c-163">设置 CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="ec25c-163">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)