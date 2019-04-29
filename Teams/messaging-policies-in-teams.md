---
title: 在 Teams 中管理消息传递策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: 了解有关消息策略以及如何使用它们来控制聊天消息团队。
ms.openlocfilehash: f0dd52dac1bd2563a0ef5c500714ab63eeadf84d
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401417"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="85aa2-103">在 Teams 中管理消息传递策略</span><span class="sxs-lookup"><span data-stu-id="85aa2-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="85aa2-104">邮件策略用于控制哪些聊天和消息功能的通道供 Microsoft 团队中的用户。</span><span class="sxs-lookup"><span data-stu-id="85aa2-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="85aa2-105">您可以使用自动创建或的组织中的人员创建一个或多个自定义的邮件策略的默认策略。</span><span class="sxs-lookup"><span data-stu-id="85aa2-105">You can use the default policy that is created automatically or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="85aa2-106">创建策略后，您可以将其分配到用户或用户组的组织中。</span><span class="sxs-lookup"><span data-stu-id="85aa2-106">After you create a policy, you can assign it to a user or group of users in your organization.</span></span>

<span data-ttu-id="85aa2-107">默认情况下，创建名为全局 （组织范围内默认值） 的策略。</span><span class="sxs-lookup"><span data-stu-id="85aa2-107">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="85aa2-108">默认情况下，您的组织中的所有用户将都分配此邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="85aa2-108">All users in your organization will be assigned this messaging policy by default.</span></span> <span data-ttu-id="85aa2-109">可以更改此策略，或创建一个或多个自定义策略并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="85aa2-109">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="85aa2-110">创建自定义策略时，可以允许或阻止某些功能对用户可用，然后将其分配给一个或多个用户需要向其应用的设置。</span><span class="sxs-lookup"><span data-stu-id="85aa2-110">When you create a custom policy, you can allow or prevent certain features from being available to your users and then assign it to one or more users who will need the settings applied to them.</span></span> 

## <a name="change-or-create-a-messaging-policy"></a><span data-ttu-id="85aa2-111">更改或创建邮件策略</span><span class="sxs-lookup"><span data-stu-id="85aa2-111">Change or create a messaging policy</span></span>

<span data-ttu-id="85aa2-112">您可以方便地管理 Microsoft 团队管理中心中的邮件策略 (http://admin.teams.microsoft.com)使用管理员凭据登录，在左侧的导航窗格中选择**邮件策略**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-112">You can easily manage messaging policies in the Microsoft Teams admin center (http://admin.teams.microsoft.com) by signing in with administrator credentials and choosing **Messaging policies** in the left navigation pane.</span></span> <span data-ttu-id="85aa2-113">若要编辑现有的默认邮件为您的组织的策略，选择**全局 （组织范围内默认值）** 行中，然后进行更改。</span><span class="sxs-lookup"><span data-stu-id="85aa2-113">To edit the existing default messaging policy for your organization, select the **Global (Org-wide default)** row, and then make your changes.</span></span> <span data-ttu-id="85aa2-114">若要创建新的自定义邮件策略，选择**新策略**，指定新策略的名称，，然后选择设置。</span><span class="sxs-lookup"><span data-stu-id="85aa2-114">To create a new custom messaging policy, select **New policy**, give the new policy a name, and then select your settings.</span></span> <span data-ttu-id="85aa2-115">完成后，请选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-115">Choose **Save** when you are done.</span></span>

<span data-ttu-id="85aa2-116">例如，假设您想要确保发送消息不会删除或更改。</span><span class="sxs-lookup"><span data-stu-id="85aa2-116">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="85aa2-117">您可以创建名为"已发送邮件的保留"的新自定义策略，并关闭以下设置：</span><span class="sxs-lookup"><span data-stu-id="85aa2-117">You would create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="85aa2-118">所有者可以删除发送的消息</span><span class="sxs-lookup"><span data-stu-id="85aa2-118">Owners can delete sent messages</span></span>
- <span data-ttu-id="85aa2-119">用户可以删除发送的消息</span><span class="sxs-lookup"><span data-stu-id="85aa2-119">Users can delete sent messages</span></span>
- <span data-ttu-id="85aa2-120">用户可以编辑已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="85aa2-120">Users can edit sent messages</span></span>

<span data-ttu-id="85aa2-121">然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="85aa2-121">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="85aa2-122">仅可以每次向用户分配一个邮件策略。</span><span class="sxs-lookup"><span data-stu-id="85aa2-122">A user can only be assigned one messaging policy at a time.</span></span>
 
## <a name="assign-a-messaging-policy-to-a-user"></a><span data-ttu-id="85aa2-123">邮件策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="85aa2-123">Assign a messaging policy to a user</span></span>

<span data-ttu-id="85aa2-124">如果创建自定义邮件策略，则它将仅处于活动状态的用户如果策略已分配给用户。</span><span class="sxs-lookup"><span data-stu-id="85aa2-124">If you create a custom messaging policy, it will only be active for a user if the policy is assigned to the user.</span></span> <span data-ttu-id="85aa2-125">要将自定义策略分配给用户，请转到 Microsoft 团队管理中心中，选择**用户**的左侧的导航窗格中，并选择您想要分配给策略的用户。</span><span class="sxs-lookup"><span data-stu-id="85aa2-125">To assign a custom policy to a user, go to the Microsoft Teams admin center, choose **Users** in the left navigation pane, and select the user you want to assign the policy to.</span></span> <span data-ttu-id="85aa2-126">在用户的页上，选择**分配策略**旁边的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-126">On the user's page, choose **Edit** next to **Assigned policies**.</span></span> <span data-ttu-id="85aa2-127">然后，在**编辑用户策略**窗格中的**消息策略**，下，从下拉列表中，选择的邮件策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-127">Then, in the **Edit user policies** pane, under **Messaging policy**, select the messaging policy from the drop-down list, and select **Save**.</span></span> <span data-ttu-id="85aa2-128">您还可以编辑的用户列表中的设置。</span><span class="sxs-lookup"><span data-stu-id="85aa2-128">You can also edit settings from the list of users.</span></span> <span data-ttu-id="85aa2-129">若要执行此操作，请通过单击左侧的用户的显示名称选择用户。</span><span class="sxs-lookup"><span data-stu-id="85aa2-129">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="85aa2-130">选择**编辑设置**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-130">Select **Edit settings**.</span></span> <span data-ttu-id="85aa2-131">然后，**编辑设置**窗格中的**消息策略**，下，从下拉列表中选择策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-131">Then, on the **Edit settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="85aa2-132">如果您要向多个用户应用策略，通过单击左侧的用户名称，选择每个用户，然后选择**编辑设置**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-132">If you are applying a policy to more than one user, select each of the users by clicking to the left of the user name, and then select **Edit settings**.</span></span> <span data-ttu-id="85aa2-133">在**编辑设置**窗格中的**消息策略**，下，从下拉列表中选择策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-133">On the **Edit Settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="85aa2-134">也可以分配邮件策略一个或多个用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="85aa2-134">You can also assign a messaging policy to one or more users as follows:</span></span>

1. <span data-ttu-id="85aa2-135">转到**Microsoft 团队管理中心** > **消息策略**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-135">Go to **Microsoft Teams admin center** > **Messaging policies**.</span></span>
2. <span data-ttu-id="85aa2-136">通过单击左侧的策略名称选择的策略。</span><span class="sxs-lookup"><span data-stu-id="85aa2-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="85aa2-137">选择**管理用户**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="85aa2-138">在**管理用户**窗格中，搜索用户按显示名称或用户名称，选择名称，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="85aa2-139">要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="85aa2-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="85aa2-140">添加完用户后，选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="85aa2-140">When you are finished adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="85aa2-141">不能删除策略，如果用户已分配给它。</span><span class="sxs-lookup"><span data-stu-id="85aa2-141">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="85aa2-142">您必须首先将不同的策略分配给所有受影响的用户，然后可以删除原始的策略。</span><span class="sxs-lookup"><span data-stu-id="85aa2-142">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="85aa2-143">邮件策略设置</span><span class="sxs-lookup"><span data-stu-id="85aa2-143">Messaging policy settings</span></span>

<span data-ttu-id="85aa2-144">使用以下设置来更改全局邮件策略或创建新的自定义策略：</span><span class="sxs-lookup"><span data-stu-id="85aa2-144">Use the following settings to change the global messaging policy or create a new custom policy:</span></span>

- <span data-ttu-id="85aa2-145">**所有者可以删除发送的消息** 使用此设置让删除邮件的所有者发送聊天中的用户。</span><span class="sxs-lookup"><span data-stu-id="85aa2-145">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="85aa2-146">**用户可以删除发送的消息**使用此设置可允许用户删除它们聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="85aa2-146">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="85aa2-147">**用户可以编辑已发送的邮件**使用此设置以使用户可以编辑他们聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="85aa2-147">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="85aa2-148">**已读回执**使用此设置指定是否读回执是控制、 每个人、 启用或禁用的用户。</span><span class="sxs-lookup"><span data-stu-id="85aa2-148">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span></span>
<span data-ttu-id="85aa2-149"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="85aa2-149"></span></span>

- <span data-ttu-id="85aa2-150">**聊天** 如果您希望能够使用团队应用程序与其他人聊天您组织中的用户，请打开此设置。</span><span class="sxs-lookup"><span data-stu-id="85aa2-150">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="85aa2-151">**使用 Giphys 对话中** 如果关闭此，用户可以与其他人聊天对话中包括 Giphys。</span><span class="sxs-lookup"><span data-stu-id="85aa2-151">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="85aa2-152">Giphy 是联机数据库和搜索引擎，使用户可以搜索和共享动态的 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="85aa2-152">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="85aa2-153">每个 Giphy 分配内容评级。</span><span class="sxs-lookup"><span data-stu-id="85aa2-153">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="85aa2-154">**Giphy 内容评级**</span><span class="sxs-lookup"><span data-stu-id="85aa2-154">**Giphy content rating**</span></span> 
    - <span data-ttu-id="85aa2-155">**无限制**这意味着您的用户将能够在聊天内容的分级无论中插入任何 Giphy。</span><span class="sxs-lookup"><span data-stu-id="85aa2-155">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="85aa2-156">**中等** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容适度限制。</span><span class="sxs-lookup"><span data-stu-id="85aa2-156">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="85aa2-157">**严格** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容严格限制。</span><span class="sxs-lookup"><span data-stu-id="85aa2-157">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="85aa2-158">**使用 Memes 对话中**如果关闭此，用户可以与其他人聊天对话中包括 Memes。</span><span class="sxs-lookup"><span data-stu-id="85aa2-158">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="85aa2-159">**在对话中使用标签**如果关闭此，用户可以与其他人聊天对话中包括标签。</span><span class="sxs-lookup"><span data-stu-id="85aa2-159">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="85aa2-160">**允许 URL 预览**使用此设置以启用自动 URL 预览打开或关闭消息中。</span><span class="sxs-lookup"><span data-stu-id="85aa2-160">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="85aa2-161">**允许用户将邮件**启用此设置以使用户可以自动将团队邮件转换为 Office 365 其个人语言设置由指定语言。</span><span class="sxs-lookup"><span data-stu-id="85aa2-161">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span>
- <span data-ttu-id="85aa2-162">**允许查看邮件的沉浸式读者**启用此设置到让用户查看邮件中的 Microsoft 沉浸式读取器。</span><span class="sxs-lookup"><span data-stu-id="85aa2-162">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="85aa2-163">沉浸式读取器学习工具，它提供全屏幕阅读体验，以提高可读性文本。</span><span class="sxs-lookup"><span data-stu-id="85aa2-163">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="85aa2-164">**用户可以发送优先级通知**如果关闭此，用户可以发送一条消息，使用优先级通知。</span><span class="sxs-lookup"><span data-stu-id="85aa2-164">**Users can send priority notifications** If you turn this on, users can send a message that uses priority notifications.</span></span> <span data-ttu-id="85aa2-165">优先级通知 20 分钟或直到邮件已选取一段反复通知用户，并读取的收件人，最大化邮件是选取并及时处理的可能性。</span><span class="sxs-lookup"><span data-stu-id="85aa2-165">Priority notifications notify users repeatedly for a period of 20 minutes or until messages are picked up and read by the recipient, maximizing the likelihood that the message is picked up and acted upon in a timely manner.</span></span>
- <span data-ttu-id="85aa2-166">**创建语音消息**</span><span class="sxs-lookup"><span data-stu-id="85aa2-166">**Voice message creation**</span></span> 
    - <span data-ttu-id="85aa2-167">**允许在聊天和频道**这意味着用户可以将中聊天和频道的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="85aa2-167">**Allowed in chats and channels** This means that users can leave voice messages in both chats and channels.</span></span>
    - <span data-ttu-id="85aa2-168">**仅允许中聊天**这意味着在聊天，但不是在通道，用户可以将语音邮件。</span><span class="sxs-lookup"><span data-stu-id="85aa2-168">**Allowed in chats only** This means that users can leave voice messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="85aa2-169">**已禁用**这意味着，用户不能在聊天或通道中创建语音邮件。</span><span class="sxs-lookup"><span data-stu-id="85aa2-169">**Disabled** This means that users cannot create voice messages in chats or channels.</span></span>  
- <span data-ttu-id="85aa2-170">**在移动设备上显示最近聊天上方的收藏夹通道**启用此设置可以将最喜爱的通道移动到的移动设备的屏幕顶部，以便用户不需要滚动查找它们。</span><span class="sxs-lookup"><span data-stu-id="85aa2-170">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span> 
- <span data-ttu-id="85aa2-171">**允许用户删除用户从群聊**启用此设置以使用户可以从群聊中删除其他用户。</span><span class="sxs-lookup"><span data-stu-id="85aa2-171">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="85aa2-172">此功能允许您继续使用较小的一组人聊天，而不会丢失聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="85aa2-172">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>

### <a name="related-topics"></a><span data-ttu-id="85aa2-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="85aa2-173">Related topics</span></span>
[<span data-ttu-id="85aa2-174">团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="85aa2-174">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
