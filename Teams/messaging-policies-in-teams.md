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
ms.openlocfilehash: c29697c8ec4d235ed232616e34590351bea59e9e
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042974"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="833b8-103">在 Teams 中管理消息传递策略</span><span class="sxs-lookup"><span data-stu-id="833b8-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="833b8-104">消息传递策略用于控制为 Microsoft Teams 中的用户提供哪些聊天和频道消息功能。</span><span class="sxs-lookup"><span data-stu-id="833b8-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="833b8-105">你可以使用自动创建的全局（组织范围默认）策略，也可以创建并分配自定义消息策略。</span><span class="sxs-lookup"><span data-stu-id="833b8-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="833b8-106">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="833b8-106">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="833b8-107">你可以编辑全局策略中的设置，或者创建并分配一个或多个自定义策略来打开或关闭所需的功能。</span><span class="sxs-lookup"><span data-stu-id="833b8-107">You can edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="833b8-108">创建自定义邮件策略</span><span class="sxs-lookup"><span data-stu-id="833b8-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="833b8-109">在 Microsoft 团队管理中心的左侧导航中，转到 "**消息策略**"。</span><span class="sxs-lookup"><span data-stu-id="833b8-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="833b8-110">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833b8-110">Click **Add**.</span></span>
3. <span data-ttu-id="833b8-111">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="833b8-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="833b8-112">选择所需的设置。</span><span class="sxs-lookup"><span data-stu-id="833b8-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="833b8-113">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="833b8-113">Click **Save**.</span></span>

<span data-ttu-id="833b8-114">例如，假设您想要确保已发送的邮件不会被删除或更改。</span><span class="sxs-lookup"><span data-stu-id="833b8-114">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="833b8-115">创建名为 "保留已发送邮件" 的新自定义策略，然后关闭以下设置：</span><span class="sxs-lookup"><span data-stu-id="833b8-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="833b8-116">所有者可以删除已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="833b8-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="833b8-117">用户可以删除已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="833b8-117">Users can delete sent messages</span></span>
- <span data-ttu-id="833b8-118">用户可以编辑已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="833b8-118">Users can edit sent messages</span></span>

<span data-ttu-id="833b8-119">然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="833b8-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="833b8-120">编辑邮件策略</span><span class="sxs-lookup"><span data-stu-id="833b8-120">Edit a messaging policy</span></span>

<span data-ttu-id="833b8-121">你可以编辑全局策略你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="833b8-121">You can edit the global policy an any custom policies that you create.</span></span> 

1. <span data-ttu-id="833b8-122">在 Microsoft 团队管理中心的左侧导航中，转到 "**消息策略**"。</span><span class="sxs-lookup"><span data-stu-id="833b8-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="833b8-123">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="833b8-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="833b8-124">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="833b8-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="833b8-125">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="833b8-125">Click **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="833b8-126">向用户分配自定义消息策略</span><span class="sxs-lookup"><span data-stu-id="833b8-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="833b8-127">一次只能向一个用户分配一个邮件策略。</span><span class="sxs-lookup"><span data-stu-id="833b8-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="833b8-128">如果向用户分配了该策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="833b8-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="833b8-129">必须先为所有受影响的用户分配不同的策略，然后才能删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="833b8-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="833b8-130">邮件策略设置</span><span class="sxs-lookup"><span data-stu-id="833b8-130">Messaging policy settings</span></span>

<span data-ttu-id="833b8-131">下面是您可以配置的邮件策略设置。</span><span class="sxs-lookup"><span data-stu-id="833b8-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="833b8-132">**所有者可以删除已发送的邮件** 使用此设置可让所有者删除用户在聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="833b8-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="833b8-133">**用户可以删除已发送的邮件**使用此设置可让用户删除他们在聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="833b8-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="833b8-134">**用户可以编辑已发送的邮件**使用此设置可让用户编辑他们在聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="833b8-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="833b8-135">已**读回执**"已读" 回执允许收件人在1:1 和群组聊天20人或更少的人阅读其邮件时，收到聊天消息的发件人。</span><span class="sxs-lookup"><span data-stu-id="833b8-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or less.</span></span> <span data-ttu-id="833b8-136">邮件已读回执删除有关邮件是否已被阅读的 uncertainly，并改善团队沟通。</span><span class="sxs-lookup"><span data-stu-id="833b8-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="833b8-137">请注意，未在电子数据展示报告中捕获 "已读回执"。</span><span class="sxs-lookup"><span data-stu-id="833b8-137">Please note that read receipts are not captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="833b8-138">**用户控制**这意味着用户可以决定是否要打开或关闭 "已读" 回执。</span><span class="sxs-lookup"><span data-stu-id="833b8-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="833b8-139">应用内的默认设置为 "打开"。</span><span class="sxs-lookup"><span data-stu-id="833b8-139">Default setting within the app is ON.</span></span> <span data-ttu-id="833b8-140">然后，用户可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="833b8-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="833b8-141">对**所有人启用**这意味着租户中的每个人都将启用该功能，而不选择将其关闭。</span><span class="sxs-lookup"><span data-stu-id="833b8-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="833b8-142">请注意 **，为整个**租户设置回执的唯一方式是仅为整个租户设置一个消息策略（名为 "Global （组织范围默认）" 的默认策略），或者让租户中的所有消息策略对收据使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="833b8-142">Be aware that when using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="833b8-143">当**为所有人**启用该功能时，"已读回执" 功能最有效。</span><span class="sxs-lookup"><span data-stu-id="833b8-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="833b8-144">**对所有人关闭**这意味着该功能将被禁用，并且租户中的任何人均未读回执，也不能将其打开。</span><span class="sxs-lookup"><span data-stu-id="833b8-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="833b8-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="833b8-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="833b8-146">**聊天** 如果希望组织中的用户能够使用 "团队" 应用与其他人聊天，请打开此设置。</span><span class="sxs-lookup"><span data-stu-id="833b8-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="833b8-147">**在对话中使用 giphy** 如果启用此功能，则用户可以在与其他人的聊天对话中加入 Giphy。</span><span class="sxs-lookup"><span data-stu-id="833b8-147">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="833b8-148">Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="833b8-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="833b8-149">每个 Giphy 都分配有一个内容分级。</span><span class="sxs-lookup"><span data-stu-id="833b8-149">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="833b8-150">**Giphy 内容分级**</span><span class="sxs-lookup"><span data-stu-id="833b8-150">**Giphy content rating**</span></span>
    - <span data-ttu-id="833b8-151">**无限制**这意味着，无论内容分级如何，你的用户都可以在聊天室中插入任何 Giphy。</span><span class="sxs-lookup"><span data-stu-id="833b8-151">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="833b8-152">**中等** 这意味着你的用户将能够在聊天中插入 Giphy，但将适度受到成人内容的限制。</span><span class="sxs-lookup"><span data-stu-id="833b8-152">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="833b8-153">**严格** 这意味着你的用户将能够在聊天中插入 Giphy，但将严格限制成人内容。</span><span class="sxs-lookup"><span data-stu-id="833b8-153">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="833b8-154">**在对话中使用 meme**如果启用此功能，则用户可以在与其他人的聊天对话中加入 Meme。</span><span class="sxs-lookup"><span data-stu-id="833b8-154">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="833b8-155">**在对话中使用贴纸**如果启用此功能，则用户可以在与其他人的聊天对话中包含贴纸。</span><span class="sxs-lookup"><span data-stu-id="833b8-155">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="833b8-156">**允许 URL 预览**使用此设置可在邮件中打开或关闭自动 URL 预览。</span><span class="sxs-lookup"><span data-stu-id="833b8-156">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="833b8-157">**允许用户翻译邮件**启用此设置，让用户自动将团队邮件转换为 Microsoft 365 或 Office 365 的个人语言设置所指定的语言。</span><span class="sxs-lookup"><span data-stu-id="833b8-157">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="833b8-158">**允许沉浸式阅读器查看邮件**启用此设置，让用户在 Microsoft 沉浸式阅读器中查看邮件。</span><span class="sxs-lookup"><span data-stu-id="833b8-158">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="833b8-159">沉浸式阅读器是一种学习工具，可提供全屏阅读体验以增加文本的可读性。</span><span class="sxs-lookup"><span data-stu-id="833b8-159">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="833b8-160">**使用优先级通知发送紧急邮件**如果启用此操作，则用户可以使用[优先级通知](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)发送消息。</span><span class="sxs-lookup"><span data-stu-id="833b8-160">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="833b8-161">优先级通知将每隔2分钟通知用户一段20分钟，或者直到被标记为*紧急*的邮件被接收并阅读时，最大程度地提高邮件的处理可能性。</span><span class="sxs-lookup"><span data-stu-id="833b8-161">Priority notifications notify users every 2 minutes for a period of 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient, maximizing the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="833b8-162">**创建音频消息**</span><span class="sxs-lookup"><span data-stu-id="833b8-162">**Audio message creation**</span></span> 
  > [!Important]
  > <span data-ttu-id="833b8-163">在电子数据展示报告中不捕获音频消息。</span><span class="sxs-lookup"><span data-stu-id="833b8-163">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="833b8-164">**在聊天和频道中允许**这意味着用户可以在聊天和频道中留下音频消息。</span><span class="sxs-lookup"><span data-stu-id="833b8-164">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="833b8-165">**仅在聊天中允许**这意味着用户可以将音频消息保留在聊天中，而不是在频道中。</span><span class="sxs-lookup"><span data-stu-id="833b8-165">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="833b8-166">**已禁用**这意味着用户无法在聊天或频道中创建音频消息。</span><span class="sxs-lookup"><span data-stu-id="833b8-166">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="833b8-167">**在移动设备上，在最近的聊天上显示收藏频道**启用此设置可将收藏频道移动到移动设备屏幕顶部，以便用户无需滚动即可找到它们。</span><span class="sxs-lookup"><span data-stu-id="833b8-167">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="833b8-168">**允许用户从群组聊天中删除用户**启用此设置，让用户从群组聊天中删除其他用户。</span><span class="sxs-lookup"><span data-stu-id="833b8-168">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="833b8-169">利用此功能，您可以继续与一组较小的人进行聊天，而不会丢失聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="833b8-169">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="833b8-170">**启用建议的答复** 启用此设置以启用聊天消息的建议答复。</span><span class="sxs-lookup"><span data-stu-id="833b8-170">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>

> [!NOTE]
> <span data-ttu-id="833b8-171">某些设置（如使用 Giphy）也可以由团队所有者在团队级别配置，并由专用通道所有者在专用频道级别进行配置。</span><span class="sxs-lookup"><span data-stu-id="833b8-171">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="833b8-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="833b8-172">Related topics</span></span>

- [<span data-ttu-id="833b8-173">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="833b8-173">Assign policies to your users in Teams</span></span>](assign-policies.md)
