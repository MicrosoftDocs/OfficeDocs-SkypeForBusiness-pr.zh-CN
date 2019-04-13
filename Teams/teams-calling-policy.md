---
title: 调用中的 Microsoft 团队的策略
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/12/2019
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
ms.openlocfilehash: c97fd5ff9228d0761f55f2f56b9a908cc3861c29
ms.sourcegitcommit: 82490c2ef74900c348c14968b605a313b5bf3078
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2019
ms.locfileid: "31860256"
---
<a name="calling-policy-in-microsoft-teams"></a><span data-ttu-id="4cb57-103">调用中的 Microsoft 团队的策略</span><span class="sxs-lookup"><span data-stu-id="4cb57-103">Calling policy in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="4cb57-104">在 Microsoft 团队中，调用策略控制的呼叫和呼叫转接功能是对用户可用。</span><span class="sxs-lookup"><span data-stu-id="4cb57-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="4cb57-105">呼叫策略确定是否用户可以接听私人电话，使用呼叫转接或同时响铃到其他用户或外部电话号码，将呼叫路由到语音邮件，呼叫组发送呼叫使用的入站和出站呼叫委派，依此类推。</span><span class="sxs-lookup"><span data-stu-id="4cb57-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="4cb57-106">默认全局策略自动创建的但管理员还可以创建和分配调用的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="4cb57-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="4cb57-107">调用策略设置</span><span class="sxs-lookup"><span data-stu-id="4cb57-107">Calling policy settings</span></span>

|<span data-ttu-id="4cb57-108">调用策略设置</span><span class="sxs-lookup"><span data-stu-id="4cb57-108">Calling policy setting</span></span> | <span data-ttu-id="4cb57-109">说明</span><span class="sxs-lookup"><span data-stu-id="4cb57-109">Description</span></span> |
|-----------------------|-------------|
|<span data-ttu-id="4cb57-110">用户可以接听私人电话</span><span class="sxs-lookup"><span data-stu-id="4cb57-110">User can make private calls</span></span> | <span data-ttu-id="4cb57-111">控制团队中的所有呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="4cb57-111">Controls all calling capabilities in Teams.</span></span> <span data-ttu-id="4cb57-112">关闭这将导致关闭团队中的所有呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="4cb57-112">Turning this off will turn off all calling functionality in Teams.</span></span>|
|<span data-ttu-id="4cb57-113">呼叫转接和同时响铃向其他用户</span><span class="sxs-lookup"><span data-stu-id="4cb57-113">Call forwarding and simultaneous ringing to other users</span></span> | <span data-ttu-id="4cb57-114">控件是否传入呼叫可以转移到其他用户或可以同时拨打其他人。</span><span class="sxs-lookup"><span data-stu-id="4cb57-114">Controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> |
|<span data-ttu-id="4cb57-115">呼叫转接和同时响铃到外部电话号码</span><span class="sxs-lookup"><span data-stu-id="4cb57-115">Call forwarding and simultaneous ringing to external phone numbers</span></span> | <span data-ttu-id="4cb57-116">控件是否传入呼叫可以转移到外部号码或可以同时拨打外部号码。</span><span class="sxs-lookup"><span data-stu-id="4cb57-116">Controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>|
|<span data-ttu-id="4cb57-117">语音邮件是可用于向用户的入站呼叫路由</span><span class="sxs-lookup"><span data-stu-id="4cb57-117">Voicemail is available for routing inbound calls to users</span></span> | <span data-ttu-id="4cb57-118">允许入站呼叫发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="4cb57-118">Enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="4cb57-119">有效的选项为**始终启用**、**始终禁用**，或**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-119">Valid options are **Always enabled**, **Always disabled**, or **User controlled**.</span></span> |
|<span data-ttu-id="4cb57-120">入站的呼叫可以路由到呼叫组</span><span class="sxs-lookup"><span data-stu-id="4cb57-120">Inbound calls can be routed to call groups</span></span> | <span data-ttu-id="4cb57-121">控制是否可以将传入呼叫转接到的呼叫组。</span><span class="sxs-lookup"><span data-stu-id="4cb57-121">Controls whether incoming calls can be forwarded to a call group.</span></span>  |
|<span data-ttu-id="4cb57-122">允许入站和出站呼叫的委派</span><span class="sxs-lookup"><span data-stu-id="4cb57-122">Allow delegation for inbound and outbound calls</span></span> | <span data-ttu-id="4cb57-123">允许入站的呼叫路由到的代理人;允许代理人发起出站呼叫代表他们具有其委派权限的用户。</span><span class="sxs-lookup"><span data-stu-id="4cb57-123">Enables inbound calls to be routed to delegates; allows delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> |
|<span data-ttu-id="4cb57-124">阻止收费绕过和发送通过 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="4cb57-124">Prevent toll bypass and send calls through the PSTN</span></span> | <span data-ttu-id="4cb57-125">将其设置为**上**将将通过 PSTN 的呼叫发送，并会导致费用，而不经由网络和绕过费。</span><span class="sxs-lookup"><span data-stu-id="4cb57-125">Setting this to **On** will send calls through PSTN and incur charges rather than going through the network and bypassing the tolls.</span></span> |
|<span data-ttu-id="4cb57-126">在呼叫中可用时在闲忙。</span><span class="sxs-lookup"><span data-stu-id="4cb57-126">Busy on Busy is available while in a call.</span></span>| <span data-ttu-id="4cb57-127">配置如何传入呼叫在用户已在呼叫或会议时进行处理。</span><span class="sxs-lookup"><span data-stu-id="4cb57-127">Configures how incoming calls are handled when a user is already in a call or conference.</span></span> <span data-ttu-id="4cb57-128">新的或传入呼叫可以被拒绝，并繁忙信号。</span><span class="sxs-lookup"><span data-stu-id="4cb57-128">New or incoming calls can be rejected with a busy signal.</span></span> |

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="4cb57-129">创建自定义调用策略</span><span class="sxs-lookup"><span data-stu-id="4cb57-129">Create a custom calling policy</span></span>

<span data-ttu-id="4cb57-130">按照以下步骤创建一个新的自定义调用策略。</span><span class="sxs-lookup"><span data-stu-id="4cb57-130">Follow these steps to create a new custom calling policy.</span></span>

1. <span data-ttu-id="4cb57-131">在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-131">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="4cb57-132">选择**新策略**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-132">Select **New policy**.</span></span>
3. <span data-ttu-id="4cb57-133">打开要调用策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="4cb57-133">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="4cb57-134">默认情况下，所有选项都包括**关闭**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-134">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="4cb57-135">若要控制用户是否可以将到语音邮件的入站的呼叫路由，请选择**始终启用**或**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-135">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="4cb57-136">若要阻止传送到语音邮件，请选择**总是禁用**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-136">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="4cb57-137">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-137">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="4cb57-138">修改现有的调用策略</span><span class="sxs-lookup"><span data-stu-id="4cb57-138">Modify an existing calling policy</span></span>

<span data-ttu-id="4cb57-139">按照以下步骤修改现有的调用策略。</span><span class="sxs-lookup"><span data-stu-id="4cb57-139">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="4cb57-140">在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-140">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="4cb57-141">单击您想要修改，然后选择**编辑**策略旁边。</span><span class="sxs-lookup"><span data-stu-id="4cb57-141">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="4cb57-142">打开要调用策略中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="4cb57-142">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="4cb57-143">默认情况下，所有选项都包括**关闭**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-143">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="4cb57-144">若要控制用户是否可以将到语音邮件的入站的呼叫路由，请选择**始终启用**或**用户控制**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-144">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="4cb57-145">若要阻止传送到语音邮件，请选择**总是禁用**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-145">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="4cb57-146">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-146">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="4cb57-147">调用策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="4cb57-147">Assign a calling policy to a user</span></span>

<span data-ttu-id="4cb57-148">按照以下步骤将自定义调用策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="4cb57-148">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="4cb57-149">在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-149">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="4cb57-150">单击以选中它，然后选择**管理用户**的策略名称旁边。</span><span class="sxs-lookup"><span data-stu-id="4cb57-150">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="4cb57-151">在**管理用户**窗格中，搜索用户的名称。</span><span class="sxs-lookup"><span data-stu-id="4cb57-151">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="4cb57-152">（您必须输入至少三个字符）。</span><span class="sxs-lookup"><span data-stu-id="4cb57-152">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="4cb57-153">选择用户的名称，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-153">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="4cb57-154">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="4cb57-154">Select **Save**.</span></span>
