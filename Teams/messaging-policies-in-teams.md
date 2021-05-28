---
title: 在 Teams 中管理消息传递策略
ms.author: serdars
author: SerdarSoysal
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
description: 了解消息传送策略以及如何使用策略来控制聊天消息传送Teams。
ms.openlocfilehash: 5b202d0a1895c3fd9b4279d6a7db072cd18f72ad
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689780"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="b2b81-103">在 Teams 中管理消息传递策略</span><span class="sxs-lookup"><span data-stu-id="b2b81-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="b2b81-104">消息传送策略用于控制哪些聊天和频道消息传送功能可供用户在 ([所有者](assign-roles-permissions.md)) 成员Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="b2b81-104">Messaging policies are used to control which chat and channel messaging features are available to [users (owners and members)](assign-roles-permissions.md) in Microsoft Teams.</span></span> <span data-ttu-id="b2b81-105">可以使用自动创建的 (组织范围的默认) 策略，或者创建和分配自定义消息传送策略。</span><span class="sxs-lookup"><span data-stu-id="b2b81-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="b2b81-106">除非创建并分配自定义策略，否则组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="b2b81-106">Users in your organization will automatically get the global policy, unless you create and assign a custom policy.</span></span> <span data-ttu-id="b2b81-107">编辑全局策略中的设置，或创建并分配一个或多个自定义策略以打开或关闭您需要的功能。</span><span class="sxs-lookup"><span data-stu-id="b2b81-107">Edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="b2b81-108">创建自定义消息传送策略</span><span class="sxs-lookup"><span data-stu-id="b2b81-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="b2b81-109">在管理中心左侧导航Microsoft Teams，转到"**消息传送策略"。**</span><span class="sxs-lookup"><span data-stu-id="b2b81-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="b2b81-110">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="b2b81-110">Select **Add**.</span></span>
3. <span data-ttu-id="b2b81-111">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="b2b81-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="b2b81-112">选择想要的设置。</span><span class="sxs-lookup"><span data-stu-id="b2b81-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="b2b81-113">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b2b81-113">Select **Save**.</span></span>

<span data-ttu-id="b2b81-114">例如，您希望确保发送的邮件不会被删除或更改。</span><span class="sxs-lookup"><span data-stu-id="b2b81-114">For example, you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="b2b81-115">创建名为"保留已发送消息"的新自定义策略，并关闭以下设置：</span><span class="sxs-lookup"><span data-stu-id="b2b81-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="b2b81-116">所有者可以删除已发送的消息</span><span class="sxs-lookup"><span data-stu-id="b2b81-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="b2b81-117">用户可以删除已发送的消息</span><span class="sxs-lookup"><span data-stu-id="b2b81-117">Users can delete sent messages</span></span>
- <span data-ttu-id="b2b81-118">用户可以编辑已发送的消息</span><span class="sxs-lookup"><span data-stu-id="b2b81-118">Users can edit sent messages</span></span>

<span data-ttu-id="b2b81-119">然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b2b81-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="b2b81-120">编辑消息策略</span><span class="sxs-lookup"><span data-stu-id="b2b81-120">Edit a messaging policy</span></span>

<span data-ttu-id="b2b81-121">可以编辑全局策略和创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b2b81-121">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="b2b81-122">在管理中心左侧导航Microsoft Teams，转到"**消息传送策略"。**</span><span class="sxs-lookup"><span data-stu-id="b2b81-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="b2b81-123">通过单击策略名称的左侧选择策略，然后选择 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="b2b81-123">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>
3. <span data-ttu-id="b2b81-124">在此处根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="b2b81-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="b2b81-125">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b2b81-125">Select **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="b2b81-126">向用户分配自定义消息传送策略</span><span class="sxs-lookup"><span data-stu-id="b2b81-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="b2b81-127">一次只能为用户分配一个消息传送策略。</span><span class="sxs-lookup"><span data-stu-id="b2b81-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="b2b81-128">如果已将它分配给用户，则无法删除该策略。</span><span class="sxs-lookup"><span data-stu-id="b2b81-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="b2b81-129">必须首先为所有受影响的用户指定不同的策略，然后才能删除原来的策略。</span><span class="sxs-lookup"><span data-stu-id="b2b81-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="b2b81-130">消息策略设置</span><span class="sxs-lookup"><span data-stu-id="b2b81-130">Messaging policy settings</span></span>

<span data-ttu-id="b2b81-131">下面是可以配置的消息策略设置。</span><span class="sxs-lookup"><span data-stu-id="b2b81-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="b2b81-132">**所有者可以删除已发送的消息**  使用此设置，让所有者删除用户在聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="b2b81-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="b2b81-133">**用户可以删除已发送的消息** 使用此设置可让用户删除他们在聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="b2b81-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="b2b81-134">**用户可以编辑已发送的消息** 使用此设置可让用户编辑他们在聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="b2b81-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="b2b81-135">**已读回执** 阅读回执允许当收件人在 1：1 和群聊 20 人或更少人中阅读其消息时，聊天消息的发送者收到通知。</span><span class="sxs-lookup"><span data-stu-id="b2b81-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or fewer.</span></span> <span data-ttu-id="b2b81-136">消息已读回执会不确定地删除消息是否已阅读，并改进团队沟通。</span><span class="sxs-lookup"><span data-stu-id="b2b81-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="b2b81-137">电子数据展示报告不会捕获已读回执。</span><span class="sxs-lookup"><span data-stu-id="b2b81-137">Read receipts aren't captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="b2b81-138">**用户控制** 这意味着用户需要决定是打开还是关闭已读回执。</span><span class="sxs-lookup"><span data-stu-id="b2b81-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="b2b81-139">应用中的默认设置为"打开"。</span><span class="sxs-lookup"><span data-stu-id="b2b81-139">Default setting within the app is ON.</span></span> <span data-ttu-id="b2b81-140">然后，用户可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="b2b81-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="b2b81-141">**适用于所有人的打开** 这意味着租户中的每个人都将具有"打开"功能，没有关闭该功能的选项。</span><span class="sxs-lookup"><span data-stu-id="b2b81-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="b2b81-142">使用"为所有人打开"设置时，设置整个租户的回执的唯一方法就是为整个租户仅设置一个消息传送策略 (该策略是名为"全局 (组织范围内的默认) 默认) ") ，或者让租户中所有消息传送策略对收据使用相同的设置。</span><span class="sxs-lookup"><span data-stu-id="b2b81-142">When using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="b2b81-143">当已读回执功能启用为“**面向所有人打开**”时，该功能最有效。</span><span class="sxs-lookup"><span data-stu-id="b2b81-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="b2b81-144">**为所有人关闭** 这意味着该功能已禁用，租户中没有任何用户具有已读回执，也不能将其打开。</span><span class="sxs-lookup"><span data-stu-id="b2b81-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="b2b81-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="b2b81-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="b2b81-146">**聊天** 如果希望您的组织中的用户能够使用 Teams 应用来与其他用户聊天，请启用此设置。</span><span class="sxs-lookup"><span data-stu-id="b2b81-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="b2b81-147">**在对话中使用 Giphy**  如果打开 Giphy，用户可以在与他人的聊天对话中包括 Giphy。</span><span class="sxs-lookup"><span data-stu-id="b2b81-147">**Use Giphys in conversations**  If you turn on Giphys, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="b2b81-148">Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="b2b81-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="b2b81-149">每个 Giphy 都分配有一个内容分级。</span><span class="sxs-lookup"><span data-stu-id="b2b81-149">Each Giphy is assigned a content rating.</span></span> <span data-ttu-id="b2b81-150">除了启用此设置外，还需要启用可选连接 [体验](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) 以允许对话中的 Giphy。</span><span class="sxs-lookup"><span data-stu-id="b2b81-150">In addition to turning on this setting, you need to enable [Optional Connected Experiences](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) to allow Giphys in conversations.</span></span>
- <span data-ttu-id="b2b81-151">**Giphy 内容分级**</span><span class="sxs-lookup"><span data-stu-id="b2b81-151">**Giphy content rating**</span></span>
    - <span data-ttu-id="b2b81-152">**无限制** 这意味着，无论内容评级如何，用户都能在聊天中插入任何 Giphy。</span><span class="sxs-lookup"><span data-stu-id="b2b81-152">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="b2b81-153">**中等**  这意味着你的用户将能够在聊天中插入 Giphy，但会适度限制成人内容。</span><span class="sxs-lookup"><span data-stu-id="b2b81-153">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="b2b81-154">**严格**  这意味着你的用户将能够在聊天中插入 Giphy，但将严格限制成人内容。</span><span class="sxs-lookup"><span data-stu-id="b2b81-154">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="b2b81-155">**在对话中使用 Meme** 如果打开 Meme，用户可以在与他人的聊天对话中包括 Meme。</span><span class="sxs-lookup"><span data-stu-id="b2b81-155">**Use Memes in conversations** If you turn Memes on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="b2b81-156">**在对话中使用贴纸** 如果启用此功能，用户可以在与他人的聊天对话中包括贴纸。</span><span class="sxs-lookup"><span data-stu-id="b2b81-156">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="b2b81-157">**允许 URL 预览** 使用此设置可打开或关闭邮件中的自动 URL 预览。</span><span class="sxs-lookup"><span data-stu-id="b2b81-157">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="b2b81-158">**允许用户翻译邮件** 打开此设置，让用户自动将Teams翻译为个人语言设置指定的语言，Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b2b81-158">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="b2b81-159">**允许沉浸式阅读器查看消息** 打开此设置，让用户在 Microsoft 沉浸式阅读器 中查看消息。</span><span class="sxs-lookup"><span data-stu-id="b2b81-159">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="b2b81-160">沉浸式阅读器是一种学习工具，可提供全屏阅读体验以提高文本可读性。</span><span class="sxs-lookup"><span data-stu-id="b2b81-160">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="b2b81-161">**使用优先级通知发送紧急消息** 如果启用此功能，用户可以使用优先级通知 [发送消息](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)。</span><span class="sxs-lookup"><span data-stu-id="b2b81-161">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="b2b81-162">优先级通知每 2 分钟通知用户 20 分钟，或直到收件人选取并阅读标记为紧急的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b81-162">Priority notifications notify users every 2 minutes for 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient.</span></span> <span data-ttu-id="b2b81-163">此功能增加了及时处理消息的可能性。</span><span class="sxs-lookup"><span data-stu-id="b2b81-163">This feature increases the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="b2b81-164">**音频消息创建**</span><span class="sxs-lookup"><span data-stu-id="b2b81-164">**Audio message creation**</span></span>
  > [!Important]
  > <span data-ttu-id="b2b81-165">电子数据展示报告不会捕获音频消息。</span><span class="sxs-lookup"><span data-stu-id="b2b81-165">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="b2b81-166">**在聊天和频道中允许** 这意味着用户可以在聊天和频道中留下音频消息。</span><span class="sxs-lookup"><span data-stu-id="b2b81-166">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="b2b81-167">**仅允许聊天** 这意味着用户可以在聊天中保留音频消息，但不能在频道中留下消息。</span><span class="sxs-lookup"><span data-stu-id="b2b81-167">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="b2b81-168">**已禁用** 这意味着用户无法在聊天或频道中创建音频消息。</span><span class="sxs-lookup"><span data-stu-id="b2b81-168">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="b2b81-169">**在移动设备上，显示最近聊天上方的收藏频道** 启用此设置，将收藏的频道移动到移动设备屏幕顶部，以便用户无需滚动查找它们。</span><span class="sxs-lookup"><span data-stu-id="b2b81-169">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="b2b81-170">**允许用户从群组聊天中删除用户** 打开此设置，让用户从群组聊天中删除其他用户。</span><span class="sxs-lookup"><span data-stu-id="b2b81-170">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="b2b81-171">此功能允许你继续与一小组人员聊天，而不会丢失聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="b2b81-171">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="b2b81-172">**启用建议的答复**  打开此设置，为聊天消息启用建议的答复。</span><span class="sxs-lookup"><span data-stu-id="b2b81-172">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>
- <span data-ttu-id="b2b81-173">**聊天权限角色** 使用此设置定义用户的监督聊天角色。</span><span class="sxs-lookup"><span data-stu-id="b2b81-173">**Chat permission role** Use this setting to define the supervised chat role of the user.</span></span>  <span data-ttu-id="b2b81-174">深入了解如何 [的聊天](supervise-chats-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b81-174">Learn more about [supervised chat](supervise-chats-edu.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b2b81-175">其中一些设置（例如使用 Giphys）也可由团队所有者在团队级别配置，在专用频道级别由专用频道所有者配置。</span><span class="sxs-lookup"><span data-stu-id="b2b81-175">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="b2b81-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="b2b81-176">Related topics</span></span>

- [<span data-ttu-id="b2b81-177">将策略分配给用户和组中Teams</span><span class="sxs-lookup"><span data-stu-id="b2b81-177">Assign policies to users and groups in Teams</span></span>](assign-policies-users-and-groups.md)
- [<span data-ttu-id="b2b81-178">在 Microsoft Teams 中分配团队所有者和成员</span><span class="sxs-lookup"><span data-stu-id="b2b81-178">Assign team owners and members in Microsoft Teams</span></span>](assign-roles-permissions.md)
