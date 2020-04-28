---
title: 在 Teams 中管理消息传递策略
ms.author: lolaj
author: lolajacobsen
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: 在本文中，你将了解消息策略以及如何使用它们控制团队中的聊天消息服务。
ms.openlocfilehash: d9cc2fbd9d3ba2eef77114228130a763d3f4fd25
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904417"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="167ed-103">在 Teams 中管理消息传递策略</span><span class="sxs-lookup"><span data-stu-id="167ed-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="167ed-104">消息传递策略用于控制为 Microsoft Teams 中的用户提供哪些聊天和频道消息功能。</span><span class="sxs-lookup"><span data-stu-id="167ed-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="167ed-105">你可以使用为组织中的人员自动创建或创建一个或多个自定义消息策略的默认策略。</span><span class="sxs-lookup"><span data-stu-id="167ed-105">You can use the default policy that is created automatically or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="167ed-106">创建策略后，您可以将其分配给组织中的用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="167ed-106">After you create a policy, you can assign it to a user or group of users in your organization.</span></span>

<span data-ttu-id="167ed-107">默认情况下，将创建名为 Global 的策略（组织范围的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="167ed-107">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="167ed-108">默认情况下，将为组织中的所有用户分配此邮件策略。</span><span class="sxs-lookup"><span data-stu-id="167ed-108">All users in your organization will be assigned this messaging policy by default.</span></span> <span data-ttu-id="167ed-109">你可以更改此策略，也可以创建一个或多个自定义策略并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="167ed-109">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="167ed-110">创建自定义策略时，你可以允许或阻止你的用户使用某些功能，然后将其分配给需要应用这些设置的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="167ed-110">When you create a custom policy, you can allow or prevent certain features from being available to your users and then assign it to one or more users who will need the settings applied to them.</span></span> 

## <a name="change-or-create-a-messaging-policy"></a><span data-ttu-id="167ed-111">更改或创建邮件策略</span><span class="sxs-lookup"><span data-stu-id="167ed-111">Change or create a messaging policy</span></span>

<span data-ttu-id="167ed-112">你可以在 Microsoft 团队管理中心（https://admin.teams.microsoft.com)通过管理员凭据登录，然后在左侧导航窗格中选择**消息策略**）轻松管理消息策略。</span><span class="sxs-lookup"><span data-stu-id="167ed-112">You can easily manage messaging policies in the Microsoft Teams admin center (https://admin.teams.microsoft.com) by signing in with administrator credentials and choosing **Messaging policies** in the left navigation pane.</span></span> <span data-ttu-id="167ed-113">若要编辑你的组织的现有默认消息策略，请选择 "**全局（组织范围默认）** " 行，然后进行更改。</span><span class="sxs-lookup"><span data-stu-id="167ed-113">To edit the existing default messaging policy for your organization, select the **Global (Org-wide default)** row, and then make your changes.</span></span> <span data-ttu-id="167ed-114">若要创建新的自定义消息策略，请选择 "**新建策略**"，为新策略提供一个名称，然后选择您的设置。</span><span class="sxs-lookup"><span data-stu-id="167ed-114">To create a new custom messaging policy, select **New policy**, give the new policy a name, and then select your settings.</span></span> <span data-ttu-id="167ed-115">完成后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="167ed-115">Choose **Save** when you are done.</span></span>

<span data-ttu-id="167ed-116">例如，假设您想要确保已发送的邮件不会被删除或更改。</span><span class="sxs-lookup"><span data-stu-id="167ed-116">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="167ed-117">您将创建一个名为 "保留已发送邮件" 的新自定义策略，并关闭以下设置：</span><span class="sxs-lookup"><span data-stu-id="167ed-117">You would create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="167ed-118">所有者可以删除已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="167ed-118">Owners can delete sent messages</span></span>
- <span data-ttu-id="167ed-119">用户可以删除已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="167ed-119">Users can delete sent messages</span></span>
- <span data-ttu-id="167ed-120">用户可以编辑已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="167ed-120">Users can edit sent messages</span></span>

<span data-ttu-id="167ed-121">然后将此策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="167ed-121">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="167ed-122">一次只能向一个用户分配一个邮件策略。</span><span class="sxs-lookup"><span data-stu-id="167ed-122">A user can only be assigned one messaging policy at a time.</span></span>
 
## <a name="assign-a-messaging-policy-to-a-user"></a><span data-ttu-id="167ed-123">向用户分配消息策略</span><span class="sxs-lookup"><span data-stu-id="167ed-123">Assign a messaging policy to a user</span></span>

<span data-ttu-id="167ed-124">如果创建自定义消息策略，则仅当为用户分配了该策略时，该策略才会处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="167ed-124">If you create a custom messaging policy, it will only be active for a user if the policy is assigned to the user.</span></span> <span data-ttu-id="167ed-125">若要向用户分配自定义策略，请转到 Microsoft 团队管理中心，在左侧导航窗格中选择 "**用户**"，然后选择要为其分配策略的用户。</span><span class="sxs-lookup"><span data-stu-id="167ed-125">To assign a custom policy to a user, go to the Microsoft Teams admin center, choose **Users** in the left navigation pane, and select the user you want to assign the policy to.</span></span> <span data-ttu-id="167ed-126">在用户的页面上，选择 "分配的**策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="167ed-126">On the user's page, choose **Edit** next to **Assigned policies**.</span></span> <span data-ttu-id="167ed-127">然后，在 "**编辑用户策略**" 窗格中的 "**邮件策略**" 下，从下拉列表中选择 "邮件策略"，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="167ed-127">Then, in the **Edit user policies** pane, under **Messaging policy**, select the messaging policy from the drop-down list, and select **Save**.</span></span> <span data-ttu-id="167ed-128">您也可以从用户列表中编辑设置。</span><span class="sxs-lookup"><span data-stu-id="167ed-128">You can also edit settings from the list of users.</span></span> <span data-ttu-id="167ed-129">若要执行此操作，请单击用户的显示名称左侧的用户选择用户。</span><span class="sxs-lookup"><span data-stu-id="167ed-129">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="167ed-130">选择 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="167ed-130">Select **Edit settings**.</span></span> <span data-ttu-id="167ed-131">然后，在 "**编辑设置**" 窗格的 "**邮件策略**" 下，从下拉列表中选择策略，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="167ed-131">Then, on the **Edit settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="167ed-132">如果要将策略应用于多个用户，请单击用户名左侧的用户选择每个用户，然后选择 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="167ed-132">If you are applying a policy to more than one user, select each of the users by clicking to the left of the user name, and then select **Edit settings**.</span></span> <span data-ttu-id="167ed-133">在 "**编辑设置**" 窗格的 "**邮件策略**" 下，从下拉列表中选择策略，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="167ed-133">On the **Edit Settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="167ed-134">您还可以将邮件策略分配给一个或多个用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="167ed-134">You can also assign a messaging policy to one or more users as follows:</span></span>

1. <span data-ttu-id="167ed-135">转到**Microsoft 团队管理中心** > **消息策略**。</span><span class="sxs-lookup"><span data-stu-id="167ed-135">Go to **Microsoft Teams admin center** > **Messaging policies**.</span></span>
2. <span data-ttu-id="167ed-136">单击策略名称的左侧以选择该策略。</span><span class="sxs-lookup"><span data-stu-id="167ed-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="167ed-137">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="167ed-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="167ed-138">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="167ed-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="167ed-139">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="167ed-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="167ed-140">完成添加用户后，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="167ed-140">When you are finished adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="167ed-141">如果向用户分配了该策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="167ed-141">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="167ed-142">必须先为所有受影响的用户分配不同的策略，然后才能删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="167ed-142">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="167ed-143">邮件策略设置</span><span class="sxs-lookup"><span data-stu-id="167ed-143">Messaging policy settings</span></span>

<span data-ttu-id="167ed-144">使用以下设置更改全局消息策略或创建新的自定义策略：</span><span class="sxs-lookup"><span data-stu-id="167ed-144">Use the following settings to change the global messaging policy or create a new custom policy:</span></span>

- <span data-ttu-id="167ed-145">**所有者可以删除已发送的邮件** 使用此设置可让所有者删除用户在聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="167ed-145">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="167ed-146">**用户可以删除已发送的邮件**使用此设置可让用户删除他们在聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="167ed-146">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="167ed-147">**用户可以编辑已发送的邮件**使用此设置可让用户编辑他们在聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="167ed-147">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="167ed-148">已**读回执**"已读" 回执允许收件人在1:1 和群组聊天20人或更少的人阅读其邮件时，收到聊天消息的发件人。</span><span class="sxs-lookup"><span data-stu-id="167ed-148">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or less.</span></span> <span data-ttu-id="167ed-149">邮件已读回执删除有关邮件是否已被阅读的 uncertainly，并改善团队沟通。</span><span class="sxs-lookup"><span data-stu-id="167ed-149">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="167ed-150">请注意，未在电子数据展示报告中捕获 "已读回执"。</span><span class="sxs-lookup"><span data-stu-id="167ed-150">Please note that read receipts are not captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="167ed-151">**用户控制**这意味着用户可以决定是否要打开或关闭 "已读" 回执。</span><span class="sxs-lookup"><span data-stu-id="167ed-151">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="167ed-152">应用内的默认设置为 "打开"。</span><span class="sxs-lookup"><span data-stu-id="167ed-152">Default setting within the app is ON.</span></span> <span data-ttu-id="167ed-153">然后，用户可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="167ed-153">Users can then turn it OFF.</span></span> 
    - <span data-ttu-id="167ed-154">对**所有人启用**这意味着租户中的每个人都将启用该功能，而不选择将其关闭。</span><span class="sxs-lookup"><span data-stu-id="167ed-154">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="167ed-155">请注意 **，为整个**租户设置回执的唯一方式是仅为整个租户设置一个消息策略（名为 "Global （组织范围默认）" 的默认策略），或者让租户中的所有消息策略对收据使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="167ed-155">Be aware that when using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="167ed-156">当**为所有人**启用该功能时，"已读回执" 功能最有效。</span><span class="sxs-lookup"><span data-stu-id="167ed-156">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="167ed-157">**对所有人关闭**这意味着该功能将被禁用，并且租户中的任何人均未读回执，也不能将其打开。</span><span class="sxs-lookup"><span data-stu-id="167ed-157">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span> 
<span data-ttu-id="167ed-158"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="167ed-158"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="167ed-159">**聊天** 如果希望组织中的用户能够使用 "团队" 应用与其他人聊天，请打开此设置。</span><span class="sxs-lookup"><span data-stu-id="167ed-159">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="167ed-160">**在对话中使用 giphy** 如果启用此功能，则用户可以在与其他人的聊天对话中加入 Giphy。</span><span class="sxs-lookup"><span data-stu-id="167ed-160">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="167ed-161">Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="167ed-161">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="167ed-162">每个 Giphy 都分配有一个内容分级。</span><span class="sxs-lookup"><span data-stu-id="167ed-162">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="167ed-163">**Giphy 内容分级**</span><span class="sxs-lookup"><span data-stu-id="167ed-163">**Giphy content rating**</span></span> 
    - <span data-ttu-id="167ed-164">**无限制**这意味着，无论内容分级如何，你的用户都可以在聊天室中插入任何 Giphy。</span><span class="sxs-lookup"><span data-stu-id="167ed-164">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="167ed-165">**中等** 这意味着你的用户将能够在聊天中插入 Giphy，但将适度受到成人内容的限制。</span><span class="sxs-lookup"><span data-stu-id="167ed-165">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="167ed-166">**严格** 这意味着你的用户将能够在聊天中插入 Giphy，但将严格限制成人内容。</span><span class="sxs-lookup"><span data-stu-id="167ed-166">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="167ed-167">**在对话中使用 meme**如果启用此功能，则用户可以在与其他人的聊天对话中加入 Meme。</span><span class="sxs-lookup"><span data-stu-id="167ed-167">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="167ed-168">**在对话中使用贴纸**如果启用此功能，则用户可以在与其他人的聊天对话中包含贴纸。</span><span class="sxs-lookup"><span data-stu-id="167ed-168">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="167ed-169">**允许 URL 预览**使用此设置可在邮件中打开或关闭自动 URL 预览。</span><span class="sxs-lookup"><span data-stu-id="167ed-169">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="167ed-170">**允许用户翻译邮件**启用此设置，让用户自动将团队邮件翻译为 Office 365 的个人语言设置所指定的语言。</span><span class="sxs-lookup"><span data-stu-id="167ed-170">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span>
- <span data-ttu-id="167ed-171">**允许沉浸式阅读器查看邮件**启用此设置，让用户在 Microsoft 沉浸式阅读器中查看邮件。</span><span class="sxs-lookup"><span data-stu-id="167ed-171">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="167ed-172">沉浸式阅读器是一种学习工具，可提供全屏阅读体验以增加文本的可读性。</span><span class="sxs-lookup"><span data-stu-id="167ed-172">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="167ed-173">**使用优先级通知发送紧急邮件**如果启用此操作，则用户可以使用[优先级通知](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)发送消息。</span><span class="sxs-lookup"><span data-stu-id="167ed-173">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="167ed-174">优先级通知将每隔2分钟通知用户一段20分钟，或者直到被标记为*紧急*的邮件被接收并阅读时，最大程度地提高邮件的处理可能性。</span><span class="sxs-lookup"><span data-stu-id="167ed-174">Priority notifications notify users every 2 minutes for a period of 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient, maximizing the likelihood that the message is acted upon in a timely manner.</span></span>   [!INCLUDE [pri-message-offer](includes/pri-message-offer.md)]
- <span data-ttu-id="167ed-175">**创建音频消息**</span><span class="sxs-lookup"><span data-stu-id="167ed-175">**Audio message creation**</span></span> 
  > [!Important]
  > <span data-ttu-id="167ed-176">在电子数据展示报告中不捕获音频消息。</span><span class="sxs-lookup"><span data-stu-id="167ed-176">Audio messages are not captured in eDiscovery reporting.</span></span> 
    - <span data-ttu-id="167ed-177">**在聊天和频道中允许**这意味着用户可以在聊天和频道中留下音频消息。</span><span class="sxs-lookup"><span data-stu-id="167ed-177">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="167ed-178">**仅在聊天中允许**这意味着用户可以将音频消息保留在聊天中，而不是在频道中。</span><span class="sxs-lookup"><span data-stu-id="167ed-178">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="167ed-179">**已禁用**这意味着用户无法在聊天或频道中创建音频消息。</span><span class="sxs-lookup"><span data-stu-id="167ed-179">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="167ed-180">**在移动设备上，在最近的聊天上显示收藏频道**启用此设置可将收藏频道移动到移动设备屏幕顶部，以便用户无需滚动即可找到它们。</span><span class="sxs-lookup"><span data-stu-id="167ed-180">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span> 
- <span data-ttu-id="167ed-181">**允许用户从群组聊天中删除用户**启用此设置，让用户从群组聊天中删除其他用户。</span><span class="sxs-lookup"><span data-stu-id="167ed-181">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="167ed-182">利用此功能，您可以继续与一组较小的人进行聊天，而不会丢失聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="167ed-182">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>

> [!NOTE]
> <span data-ttu-id="167ed-183">某些设置（如使用 Giphy）也可以由团队所有者在团队级别配置，并由专用通道所有者在专用频道级别进行配置。</span><span class="sxs-lookup"><span data-stu-id="167ed-183">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="167ed-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="167ed-184">Related topics</span></span>
[<span data-ttu-id="167ed-185">团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="167ed-185">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
