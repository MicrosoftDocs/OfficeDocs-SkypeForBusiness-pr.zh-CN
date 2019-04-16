---
title: 调用中的 Microsoft 团队的策略
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/15/2019
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
ms.openlocfilehash: 20dc75dfeb39fbd7a00e6c389dc923617265cc0b
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869803"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="ba8f4-103">调用中的 Microsoft 团队的策略</span><span class="sxs-lookup"><span data-stu-id="ba8f4-103">Calling policies in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="ba8f4-104">在 Microsoft 团队中，调用策略控制的呼叫和呼叫转接功能是对用户可用。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="ba8f4-105">呼叫策略确定是否用户可以接听私人电话，使用呼叫转接或同时响铃到其他用户或外部电话号码，将呼叫路由到语音邮件，呼叫组发送呼叫使用的入站和出站呼叫委派，依此类推。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="ba8f4-106">默认全局策略自动创建的但管理员还可以创建和分配调用的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="ba8f4-107">调用策略设置</span><span class="sxs-lookup"><span data-stu-id="ba8f4-107">Calling policy settings</span></span>

|<span data-ttu-id="ba8f4-108">调用策略设置</span><span class="sxs-lookup"><span data-stu-id="ba8f4-108">Calling policy setting</span></span> | <span data-ttu-id="ba8f4-109">说明</span><span class="sxs-lookup"><span data-stu-id="ba8f4-109">Description</span></span> |
|-----------------------|-------------|
|<span data-ttu-id="ba8f4-110">用户可以接听私人电话</span><span class="sxs-lookup"><span data-stu-id="ba8f4-110">User can make private calls</span></span> | <span data-ttu-id="ba8f4-111">控制团队中的所有呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-111">Controls all calling capabilities in Teams.</span></span> <span data-ttu-id="ba8f4-112">关闭这将导致关闭团队中的所有呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-112">Turning this off will turn off all calling functionality in Teams.</span></span>|
|<span data-ttu-id="ba8f4-113">呼叫转接和同时响铃向其他用户</span><span class="sxs-lookup"><span data-stu-id="ba8f4-113">Call forwarding and simultaneous ringing to other users</span></span> | <span data-ttu-id="ba8f4-114">控件是否传入呼叫可以转移到其他用户或可以同时拨打其他人。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-114">Controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> |
|<span data-ttu-id="ba8f4-115">呼叫转接和同时响铃到外部电话号码</span><span class="sxs-lookup"><span data-stu-id="ba8f4-115">Call forwarding and simultaneous ringing to external phone numbers</span></span> | <span data-ttu-id="ba8f4-116">控件是否传入呼叫可以转移到外部号码或可以同时拨打外部号码。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-116">Controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>|
|<span data-ttu-id="ba8f4-117">语音邮件是可用于向用户的入站呼叫路由</span><span class="sxs-lookup"><span data-stu-id="ba8f4-117">Voicemail is available for routing inbound calls to users</span></span> | <span data-ttu-id="ba8f4-118">允许入站呼叫发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-118">Enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="ba8f4-119">有效的选项为**始终启用**、**始终禁用**，或**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-119">Valid options are **Always enabled**, **Always disabled**, or **User controlled**.</span></span> |
|<span data-ttu-id="ba8f4-120">入站的呼叫可以路由到呼叫组</span><span class="sxs-lookup"><span data-stu-id="ba8f4-120">Inbound calls can be routed to call groups</span></span> | <span data-ttu-id="ba8f4-121">控制是否可以将传入呼叫转接到的呼叫组。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-121">Controls whether incoming calls can be forwarded to a call group.</span></span>  |
|<span data-ttu-id="ba8f4-122">允许入站和出站呼叫的委派</span><span class="sxs-lookup"><span data-stu-id="ba8f4-122">Allow delegation for inbound and outbound calls</span></span> | <span data-ttu-id="ba8f4-123">允许入站的呼叫路由到的代理人;允许代理人发起出站呼叫代表他们具有其委派权限的用户。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-123">Enables inbound calls to be routed to delegates; allows delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> |
|<span data-ttu-id="ba8f4-124">阻止收费绕过和发送通过 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="ba8f4-124">Prevent toll bypass and send calls through the PSTN</span></span> | <span data-ttu-id="ba8f4-125">将其设置为**上**将将通过 PSTN 的呼叫发送，并会导致费用，而不经由网络和绕过费。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-125">Setting this to **On** will send calls through PSTN and incur charges rather than going through the network and bypassing the tolls.</span></span> |
|<span data-ttu-id="ba8f4-126">在呼叫中可用时在闲忙。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-126">Busy on Busy is available while in a call.</span></span>| <span data-ttu-id="ba8f4-127">配置如何传入呼叫在用户已在呼叫或会议时进行处理。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-127">Configures how incoming calls are handled when a user is already in a call or conference.</span></span> <span data-ttu-id="ba8f4-128">新的或传入呼叫可以被拒绝，并繁忙信号。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-128">New or incoming calls can be rejected with a busy signal.</span></span> |

### <a name="busy-options-busy-on-busy-setting"></a><span data-ttu-id="ba8f4-129">闲选项 （忙/闲设置）</span><span class="sxs-lookup"><span data-stu-id="ba8f4-129">Busy options (Busy on Busy setting)</span></span>

<span data-ttu-id="ba8f4-130">忙选项是允许您配置如何传入呼叫的呼叫策略处理用户已在呼叫或会议或上发出呼叫时的团队中的新设置保留。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-130">Busy options is a new setting in Teams calling policies that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="ba8f4-131">新的或传入呼叫可以被拒绝，并繁忙信号。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-131">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="ba8f4-132">您可以启用忙选项在租户级别或用户级别。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-132">You can enable busy options at a tenant level or at a user level.</span></span> 

<span data-ttu-id="ba8f4-133">无论其忙选项的配置方式，呼叫或会议或呼叫置于保持状态的那些将不阻止用户发起新呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-133">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="ba8f4-134">您可以使用中调用策略设置忙设置忙碌配置忙选项。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-134">You can use the Busy on Busy setting in Calling policy settings to configure busy options.</span></span> <span data-ttu-id="ba8f4-135">默认情况下禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-135">This setting is disabled by default.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="ba8f4-136">创建自定义调用策略</span><span class="sxs-lookup"><span data-stu-id="ba8f4-136">Create a custom calling policy</span></span>

<span data-ttu-id="ba8f4-137">按照以下步骤创建一个新的自定义调用策略。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-137">Follow these steps to create a new custom calling policy.</span></span>

1. <span data-ttu-id="ba8f4-138">在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-138">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="ba8f4-139">选择**新策略**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-139">Select **New policy**.</span></span>
3. <span data-ttu-id="ba8f4-140">打开要调用策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-140">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="ba8f4-141">默认情况下，所有选项都包括**关闭**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-141">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="ba8f4-142">若要控制用户是否可以将到语音邮件的入站的呼叫路由，请选择**始终启用**或**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-142">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="ba8f4-143">若要阻止传送到语音邮件，请选择**总是禁用**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-143">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="ba8f4-144">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-144">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="ba8f4-145">修改现有的调用策略</span><span class="sxs-lookup"><span data-stu-id="ba8f4-145">Modify an existing calling policy</span></span>

<span data-ttu-id="ba8f4-146">按照以下步骤修改现有的调用策略。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-146">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="ba8f4-147">在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-147">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="ba8f4-148">单击您想要修改，然后选择**编辑**策略旁边。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-148">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="ba8f4-149">打开要调用策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-149">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="ba8f4-150">默认情况下，所有选项都包括**关闭**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-150">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="ba8f4-151">若要控制用户是否可以将到语音邮件的入站的呼叫路由，请选择**始终启用**或**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-151">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="ba8f4-152">若要阻止传送到语音邮件，请选择**总是禁用**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-152">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="ba8f4-153">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-153">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="ba8f4-154">调用策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="ba8f4-154">Assign a calling policy to a user</span></span>

<span data-ttu-id="ba8f4-155">按照以下步骤将自定义调用策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-155">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="ba8f4-156">在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-156">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="ba8f4-157">单击以选中它，然后选择**管理用户**的策略名称旁边。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-157">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="ba8f4-158">在**管理用户**窗格中，搜索用户的名称。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-158">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="ba8f4-159">（您必须输入至少三个字符）。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-159">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="ba8f4-160">选择用户的名称，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-160">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="ba8f4-161">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="ba8f4-161">Select **Save**.</span></span>
