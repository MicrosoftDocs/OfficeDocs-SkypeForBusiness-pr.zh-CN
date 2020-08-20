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
description: 在本文中，你将了解消息策略以及如何用于控制 Teams 中的聊天消息。
ms.openlocfilehash: 0a548eee32fc196157b6a363dd0427b187e52112
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814178"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="56307-103">在 Teams 中管理消息传递策略</span><span class="sxs-lookup"><span data-stu-id="56307-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="56307-104">消息策略用于控制在 Microsoft Teams 中，用户 [有哪些聊天和频道消息功能可供 (所有者和成员使用) ](assign-roles-permissions.md) 消息功能。</span><span class="sxs-lookup"><span data-stu-id="56307-104">Messaging policies are used to control which chat and channel messaging features are available to [users (owners and members)](assign-roles-permissions.md) in Microsoft Teams.</span></span> <span data-ttu-id="56307-105">可使用全局管理员 (应用于内部创建) 或分配自定义消息策略。</span><span class="sxs-lookup"><span data-stu-id="56307-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="56307-106">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="56307-106">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="56307-107">可以编辑全局策略中的设置或创建并分配一个或多个自定义策略以启用或禁用所需功能。</span><span class="sxs-lookup"><span data-stu-id="56307-107">You can edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="56307-108">创建自定义消息策略</span><span class="sxs-lookup"><span data-stu-id="56307-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="56307-109">在 Microsoft Teams 管理中心的左侧导航 **中，转到"消息策略**"。</span><span class="sxs-lookup"><span data-stu-id="56307-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="56307-110">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="56307-110">Click **Add**.</span></span>
3. <span data-ttu-id="56307-111">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="56307-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="56307-112">选择所需的设置。</span><span class="sxs-lookup"><span data-stu-id="56307-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="56307-113">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="56307-113">Click **Save**.</span></span>

<span data-ttu-id="56307-114">例如，您想要确保已发送的邮件未被删除或更改。</span><span class="sxs-lookup"><span data-stu-id="56307-114">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="56307-115">创建一个名为"保留已发送邮件"的新自定义策略并关闭以下设置：</span><span class="sxs-lookup"><span data-stu-id="56307-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="56307-116">所有者可以删除已发送的消息</span><span class="sxs-lookup"><span data-stu-id="56307-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="56307-117">用户可以删除已发送的消息</span><span class="sxs-lookup"><span data-stu-id="56307-117">Users can delete sent messages</span></span>
- <span data-ttu-id="56307-118">用户可以编辑已发送的消息</span><span class="sxs-lookup"><span data-stu-id="56307-118">Users can edit sent messages</span></span>

<span data-ttu-id="56307-119">然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="56307-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="56307-120">编辑消息策略</span><span class="sxs-lookup"><span data-stu-id="56307-120">Edit a messaging policy</span></span>

<span data-ttu-id="56307-121">您可以编辑全局策略和您创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="56307-121">You can edit the global policy and any custom policies that you create.</span></span> 

1. <span data-ttu-id="56307-122">在 Microsoft Teams 管理中心的左侧导航 **中，转到"消息策略**"。</span><span class="sxs-lookup"><span data-stu-id="56307-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="56307-123">单击策略名称左侧位置选择策略，然后单击 **"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="56307-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="56307-124">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="56307-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="56307-125">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="56307-125">Click **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="56307-126">为用户分配自定义消息策略</span><span class="sxs-lookup"><span data-stu-id="56307-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="56307-127">一次只能为一个消息策略分配一个消息策略。</span><span class="sxs-lookup"><span data-stu-id="56307-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="56307-128">如果用户已分配了策略，则无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="56307-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="56307-129">必须先向所有受影响的用户分配不同的策略，然后才能删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="56307-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="56307-130">消息策略设置</span><span class="sxs-lookup"><span data-stu-id="56307-130">Messaging policy settings</span></span>

<span data-ttu-id="56307-131">下面是您可以配置的消息策略设置。</span><span class="sxs-lookup"><span data-stu-id="56307-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="56307-132">**所有者可以删除已发送的消息**  使用此设置，所有者可以删除用户在聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="56307-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="56307-133">**用户可以删除已发送的消息** 使用此设置，用户可以删除他们在聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="56307-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="56307-134">**用户可以编辑已发送的消息** 使用此设置，用户可以编辑他们聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="56307-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="56307-135">**已读回收** 通过"已读"收件人，可以收到聊天消息的发件人在 1：1 及小组聊天 20 人或更少的时间进行阅读。</span><span class="sxs-lookup"><span data-stu-id="56307-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or less.</span></span> <span data-ttu-id="56307-136">邮件已读回收结果将在很大程度上取消统一读取消息，并改进团队沟通。</span><span class="sxs-lookup"><span data-stu-id="56307-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="56307-137">请注意，未在电子数据展示报告中捕获已读回收。</span><span class="sxs-lookup"><span data-stu-id="56307-137">Please note that read receipts are not captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="56307-138">**用户已控制** 这意味着用户决定是否要打开或关闭已读回据。</span><span class="sxs-lookup"><span data-stu-id="56307-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="56307-139">应用程序内的默认设置为"打开"。</span><span class="sxs-lookup"><span data-stu-id="56307-139">Default setting within the app is ON.</span></span> <span data-ttu-id="56307-140">然后，用户可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="56307-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="56307-141">**对所有人启用** 这意味着租户中的每个人都将提供该功能，而不提供将其关闭的选项。</span><span class="sxs-lookup"><span data-stu-id="56307-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="56307-142">请注意，当为所有 **人** 设置使用"开"时，为整个租户设置收据的测量方法是只有 (一个邮件策略："全局 (组织范围默认值) ") 或者在租户中拥有对收据设置所用的相同设置。</span><span class="sxs-lookup"><span data-stu-id="56307-142">Be aware that when using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="56307-143">如果对每个人都启用此功能，"已读回据"功能最 **有效**。</span><span class="sxs-lookup"><span data-stu-id="56307-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="56307-144">**对每个人禁用** 这意味着该功能被禁用，租户中没有人已读回收，也不能开启该功能。</span><span class="sxs-lookup"><span data-stu-id="56307-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="56307-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="56307-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="56307-146">**聊天**  如果你希望组织中的用户能够使用 Teams 应用与其他人聊天，请启用此设置。</span><span class="sxs-lookup"><span data-stu-id="56307-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="56307-147">**在对话中使用 Giphy**  如果启用此选项，用户可以将 Giphy 信息包含在与他人的聊天中。</span><span class="sxs-lookup"><span data-stu-id="56307-147">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="56307-148">Giphy 是联机数据库和搜索引文，可供用户搜索和共享动时 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="56307-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="56307-149">为每个 Ipiphy 分配了一个内容分级。</span><span class="sxs-lookup"><span data-stu-id="56307-149">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="56307-150">**Giphy 内容分级**</span><span class="sxs-lookup"><span data-stu-id="56307-150">**Giphy content rating**</span></span>
    - <span data-ttu-id="56307-151">**没有限制** 这意味着无管内容分级如何，您的用户将能够在聊天中插入任何 Giphy。</span><span class="sxs-lookup"><span data-stu-id="56307-151">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="56307-152">**"中等"**  这意味着你的用户将能够在聊天中插入 Giphy，但将受成人内容的中等限制。</span><span class="sxs-lookup"><span data-stu-id="56307-152">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="56307-153">**"限制"**  这意味着你的用户将能够在聊天中插入 Giphy，但将限制在成人内容中。</span><span class="sxs-lookup"><span data-stu-id="56307-153">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="56307-154">**在对话中使用 Meme** 如果启用此选项，用户可以将 Meme 用于与其他人进行聊天。</span><span class="sxs-lookup"><span data-stu-id="56307-154">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="56307-155">**在对话中使用贴中** 如果启用此设置，用户可以将贴子信息包含在与其他人的聊天中。</span><span class="sxs-lookup"><span data-stu-id="56307-155">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="56307-156">**允许 URL 预览** 使用此设置来打开或关闭邮件中的自动 URL 预览。</span><span class="sxs-lookup"><span data-stu-id="56307-156">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="56307-157">**允许用户翻译邮件** 启用此设置，让用户可以将 Teams 消息自动翻译为由 Microsoft 365 或 Office 365 的个人语言设置指定的语言。</span><span class="sxs-lookup"><span data-stu-id="56307-157">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="56307-158">**允许沉浸式阅读器查看邮件** 打开此设置以允许用户在 Microsoft 沉浸式阅读器中查看邮件。</span><span class="sxs-lookup"><span data-stu-id="56307-158">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="56307-159">沉浸式阅读器是一种学习工具，它提供了全屏阅读体验，提高文本的可读性。</span><span class="sxs-lookup"><span data-stu-id="56307-159">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="56307-160">**使用优先级通知发送明绿消息** 如果启用此功能，用户可以使用优先级 [通知发送消息](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)。</span><span class="sxs-lookup"><span data-stu-id="56307-160">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="56307-161">优先级通知用户每隔 20 分钟一段时间通知用户一次超过 20 分钟，或者直到收件人选取和*urgent*阅读被收件人标记为代理的消息，从而最大程度地使邮件及时作出的可能性最大。</span><span class="sxs-lookup"><span data-stu-id="56307-161">Priority notifications notify users every 2 minutes for a period of 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient, maximizing the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="56307-162">**创建音频消息**</span><span class="sxs-lookup"><span data-stu-id="56307-162">**Audio message creation**</span></span> 
  > [!Important]
  > <span data-ttu-id="56307-163">电子数据展示报告中未捕获音频消息。</span><span class="sxs-lookup"><span data-stu-id="56307-163">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="56307-164">**在聊天和频道中允许** 这意味着用户可以将音频消息同时保留在聊天和频道中。</span><span class="sxs-lookup"><span data-stu-id="56307-164">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="56307-165">**仅在聊天中允许** 这意味着用户可以进行聊天，但不能在频道中进行语音发送消息。</span><span class="sxs-lookup"><span data-stu-id="56307-165">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="56307-166">**已禁用** 这意味着用户无法在聊天或频道中创建音频消息。</span><span class="sxs-lookup"><span data-stu-id="56307-166">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="56307-167">**在移动设备上，显示最近聊天上方的收藏频道** 启用此设置可将收藏的通道移动到移动设备屏幕顶部，以便用户无需滚动查找它们。</span><span class="sxs-lookup"><span data-stu-id="56307-167">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="56307-168">**允许用户从群组聊天中删除用户** 打开此设置，使用户可以从群组聊天中删除其他用户。</span><span class="sxs-lookup"><span data-stu-id="56307-168">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="56307-169">利用此功能，你可以继续与较少一组人员的聊天，无需丢失聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="56307-169">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="56307-170">**启用建议的答复**  打开此设置以启用聊天消息建议的回复。</span><span class="sxs-lookup"><span data-stu-id="56307-170">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>

> [!NOTE]
> <span data-ttu-id="56307-171">这些设置中的某些设置（如使用 Giphy）还可以由团队所有者和专用频道所有者在专用频道级别配置。</span><span class="sxs-lookup"><span data-stu-id="56307-171">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="56307-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="56307-172">Related topics</span></span>

- [<span data-ttu-id="56307-173">在 Teams 中向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="56307-173">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="56307-174">在 Microsoft Teams 中分配团队所有者和成员</span><span class="sxs-lookup"><span data-stu-id="56307-174">Assign team owners and members in Microsoft Teams</span></span>](assign-roles-permissions.md)
