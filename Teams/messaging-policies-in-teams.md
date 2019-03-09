---
title: 管理消息传递策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
- ms.teamsadmincenter.messagingpolicies.settings.chat
description: 了解有关消息策略以及如何使用它们来控制聊天消息团队。
ms.openlocfilehash: 69097888038699b8d30084598fcf411fe0f97dc2
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494098"
---
# <a name="what-are-messaging-policies-in-teams"></a><span data-ttu-id="e5bb6-103">Teams 中的消息传递策略是什么？</span><span class="sxs-lookup"><span data-stu-id="e5bb6-103">What are Messaging policies in Teams?</span></span>  

::: zone target="docs"
<span data-ttu-id="e5bb6-104">邮件策略用于控制哪些聊天和消息功能的通道供 Microsoft 团队中的用户。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="e5bb6-105">您可以使用创建或的组织中的人员创建一个或多个自定义的邮件策略的默认策略。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-105">You can use the default policy that is created or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="e5bb6-106">创建策略后，您将其分配用户组的组织中。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-106">After you create a policy, you will assign it a user or groups of users in your organization.</span></span>

<span data-ttu-id="e5bb6-107">可以在 Microsoft 团队管理中心轻松地管理策略 (http://admin.teams.microsoft.com) ，日志记录使用管理员凭据，然后在左侧的导航窗格中选择**消息策略**。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-107">Policies can be easily managed in the Microsoft Teams admin center (http://admin.teams.microsoft.com) by logging in with administrator credentials and choosing **Messaging Policies** in the left navigation pane.</span></span> 

![团队中的邮件策略](media/messaging-policies-image1.png)

<span data-ttu-id="e5bb6-109">若要编辑您的组织的现有默认消息策略，请单击**全局 （组织范围内默认值）** 行中，然后进行更改。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-109">To edit the existing default Messaging policy for your organization, click the **Global (Org-wide default)** row, and then make your changes.</span></span> <span data-ttu-id="e5bb6-110">若要创建新的自定义邮件策略，单击**新建策略**，然后选择您的设置。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-110">To create a new custom messaging policy, click **New policy** and select your settings.</span></span> <span data-ttu-id="e5bb6-111">完成后，请选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-111">Choose **Save** when you are done.</span></span>

![消息团队中的策略设置](media/messaging-policies-image2.png)
::: zone-end  
::: zone target="chromeless"
<span data-ttu-id="e5bb6-113">使用以下设置来更改全局消息策略或创建新的自定义策略：</span><span class="sxs-lookup"><span data-stu-id="e5bb6-113">Use the following settings to change the global Messaging policy or create a new custom policy:</span></span>

- <span data-ttu-id="e5bb6-114">**所有者可以删除发送的消息** 使用此设置让删除邮件的所有者发送聊天中的用户。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-114">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="e5bb6-115">**用户可以删除发送的消息**使用此设置可允许用户删除它们聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-115">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="e5bb6-116">**用户可以编辑已发送的邮件**使用此设置以使用户可以编辑他们聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-116">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="e5bb6-117">**已读回执**使用此设置指定是否读回执是控制、 每个人、 启用或禁用的用户。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-117">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span></span>

<span data-ttu-id="e5bb6-118"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="e5bb6-118"></span></span>

- <span data-ttu-id="e5bb6-119">**聊天** 如果您希望能够使用团队应用程序与其他人聊天您组织中的用户，请打开此设置。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-119">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="e5bb6-120">**使用 Giphys 对话中** 如果关闭此，用户可以与其他人聊天对话中包括 Giphys。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-120">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="e5bb6-121">Giphy 是联机数据库和搜索引擎，使用户可以搜索和共享动态的 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-121">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="e5bb6-122">每个 Giphy 分配内容评级。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-122">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="e5bb6-123">**Giphy 内容评级**</span><span class="sxs-lookup"><span data-stu-id="e5bb6-123">**Giphy content rating**</span></span> 
    - <span data-ttu-id="e5bb6-124">**无限制**这意味着您的用户将能够在聊天内容的分级无论中插入任何 Giphy。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-124">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="e5bb6-125">**中等** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容适度限制。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-125">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="e5bb6-126">**严格** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容严格限制。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-126">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="e5bb6-127">**使用 Memes 对话中**如果关闭此，用户可以与其他人聊天对话中包括 Memes。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-127">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="e5bb6-128">**在对话中使用标签**如果关闭此，用户可以与其他人聊天对话中包括标签。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-128">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="e5bb6-129">**允许 URL 预览**使用此设置以启用自动 URL 预览打开或关闭消息中。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-129">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="e5bb6-130">**允许用户将邮件**启用此设置以使用户可以自动将团队邮件转换为 Office 365 其个人语言设置由指定语言。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-130">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span> 

[<span data-ttu-id="e5bb6-131">完整的文章</span><span class="sxs-lookup"><span data-stu-id="e5bb6-131">Full article</span></span>](messaging-policies-in-teams.md)
::: zone-end

::: zone target="docs"
<span data-ttu-id="e5bb6-132">如果您已创建的自定义消息策略，它将仅处于活动状态的用户如果该策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-132">If you have created a custom Messaging policy, it will only be active for a user if that policy is assigned to a user.</span></span> <span data-ttu-id="e5bb6-133">将自定义策略分配给用户的 Microsoft 团队管理中心中，选择**用户**的左侧窗格中，并选择您想要分配给策略的用户。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-133">To assign a custom policy to a user in the Microsoft Teams admin center, choose **Users** in the left navigation, and select the user you want to assign the policy to.</span></span> <span data-ttu-id="e5bb6-134">在用户的页上，选择**分配策略**旁边的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="e5bb6-134">On the user's page, choose **Edit** next to **Assigned Policies**.</span></span>
::: zone-end

### <a name="related-topics"></a><span data-ttu-id="e5bb6-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="e5bb6-135">Related topics</span></span>
[<span data-ttu-id="e5bb6-136">Teams 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="e5bb6-136">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)



