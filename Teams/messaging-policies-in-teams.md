---
title: Teams 中的消息传递策略是什么？
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
ms.openlocfilehash: 5292d88c148e2bd23242f96a3593d98178b9a923
ms.sourcegitcommit: d400c8f83a2325c4a8bbb963ddad685a346bc4d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "29760580"
---
# <a name="what-are-messaging-policies-in-teams"></a><span data-ttu-id="f15b1-103">Teams 中的消息传递策略是什么？</span><span class="sxs-lookup"><span data-stu-id="f15b1-103">What are Messaging policies in Teams?</span></span>
::: zone target="docs"
<span data-ttu-id="f15b1-104">邮件策略用于控制哪些聊天和消息功能的通道供 Microsoft 团队中的用户。</span><span class="sxs-lookup"><span data-stu-id="f15b1-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="f15b1-105">您可以使用创建或的组织中的人员创建一个或多个自定义的邮件策略的默认策略。</span><span class="sxs-lookup"><span data-stu-id="f15b1-105">You can use the default policy that is created or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="f15b1-106">创建策略后，您将其分配用户组的组织中。</span><span class="sxs-lookup"><span data-stu-id="f15b1-106">After you create a policy, you will assign it a user or groups of users in your organization.</span></span>

<span data-ttu-id="f15b1-107">可以在工作组管理中心轻松地管理策略 (http://admin.teams.microsoft.com)左侧导航窗格中单击**消息策略**和日志记录使用管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="f15b1-107">Policies can be easily managed in the Teams Admin Center (http://admin.teams.microsoft.com) by logging in with administrator credentials and clicking **Messaging Policies** in the left navigation.</span></span> <span data-ttu-id="f15b1-108">若要编辑现有的默认策略为您的组织，选择**全局 （组织范围内默认值）** 行，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="f15b1-108">To edit the existing default policy for your organization, select the **Global (Org-wide default)** row and click **Edit**.</span></span> <span data-ttu-id="f15b1-109">若要创建新的邮件策略，单击**新建策略**。</span><span class="sxs-lookup"><span data-stu-id="f15b1-109">To create a new messaging policy, click **New policy**.</span></span>

![团队中的邮件策略](media/messaging-policies.png)
::: zone-end

::: zone target="chromeless"
<span data-ttu-id="f15b1-111">下面介绍了可用的策略设置：</span><span class="sxs-lookup"><span data-stu-id="f15b1-111">The available settings for the policy are described below:</span></span> 

- <span data-ttu-id="f15b1-112">**所有者可以删除发送的消息** 使用此设置可以让所有者删除聊天中的用户发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="f15b1-112">**Owners can delete sent messages**  Use this setting to let owners delete messages that users send in chat.</span></span>
- <span data-ttu-id="f15b1-113">**用户可以删除发送的消息**使用此设置可允许用户删除聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="f15b1-113">**Users can delete sent messages** Use this setting to let users delete messages that they send in chat.</span></span>
- <span data-ttu-id="f15b1-114">**用户可以编辑已发送的邮件**使用此设置可允许用户编辑其聊天中发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="f15b1-114">**Users can edit sent messages** Use this setting to let users edit the messages that they send in chat.</span></span>
- <span data-ttu-id="f15b1-115">**已读回执**使用此设置指定是否读回执是控制、 每个人、 启用或禁用的用户。</span><span class="sxs-lookup"><span data-stu-id="f15b1-115">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span></span>
<span data-ttu-id="f15b1-116"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="f15b1-116"></span></span>

- <span data-ttu-id="f15b1-117">**聊天** 如果您希望能够使用团队应用程序与其他人聊天您组织中的用户，请打开此设置。</span><span class="sxs-lookup"><span data-stu-id="f15b1-117">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="f15b1-118">**使用 Giphys 对话中** 如果关闭此，用户可以与其他人聊天对话中包括 Giphys。</span><span class="sxs-lookup"><span data-stu-id="f15b1-118">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="f15b1-119">Giphy 是联机数据库和搜索引擎，使用户可以搜索和共享动态的 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="f15b1-119">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="f15b1-120">每个 Giphy 分配内容评级。</span><span class="sxs-lookup"><span data-stu-id="f15b1-120">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="f15b1-121">**Giphy 内容评级**</span><span class="sxs-lookup"><span data-stu-id="f15b1-121">**Giphy content rating**</span></span> 
    - <span data-ttu-id="f15b1-122">**无限制**这意味着您的用户将能够在聊天内容的分级无论中插入所有 Giphys。</span><span class="sxs-lookup"><span data-stu-id="f15b1-122">**No restriction** This means that your users will be able to insert all Giphys in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="f15b1-123">**中等** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容适度限制。</span><span class="sxs-lookup"><span data-stu-id="f15b1-123">**Moderate**  This means that your users will be able to insert Giphys in chats but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="f15b1-124">**严格** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容严格限制。</span><span class="sxs-lookup"><span data-stu-id="f15b1-124">**Strict**  This means that your users will be able to insert Giphys in chats but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="f15b1-125">**使用 Memes 对话中**如果关闭此，用户可以与其他人聊天对话中包括 Memes。</span><span class="sxs-lookup"><span data-stu-id="f15b1-125">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="f15b1-126">**在对话中使用标签**如果关闭此，用户可以与其他人聊天对话中包括标签。</span><span class="sxs-lookup"><span data-stu-id="f15b1-126">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="f15b1-127">**允许 URL 预览**使用此设置以启用自动 URL 预览打开或关闭消息中。</span><span class="sxs-lookup"><span data-stu-id="f15b1-127">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="f15b1-128">**允许用户将邮件**启用此设置以使用户可以自动将团队邮件转换为 Office 365 其个人语言设置由指定语言。</span><span class="sxs-lookup"><span data-stu-id="f15b1-128">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span>
::: zone-end

::: zone target="docs"
<span data-ttu-id="f15b1-129">如果您已创建的自定义消息策略，它将仅处于活动状态的用户如果该策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="f15b1-129">If you have created a custom Messaging policy, it will only be active for a user if that policy is assigned to a user.</span></span>  <span data-ttu-id="f15b1-130">要自定义策略分配团队管理中心中的用户，请单击**用户**的左侧窗格中，选择要分配到的策略的用户，然后选择在**分配策略**下的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="f15b1-130">To assign a custom policy to a user in the Teams Admin Center, click **Users** in the left navigation, select the user you want to assign the policy to, and then choose **Edit** under **Assigned Policies**.</span></span>


### <a name="related-topics"></a><span data-ttu-id="f15b1-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="f15b1-131">Related topics</span></span>
[<span data-ttu-id="f15b1-132">Teams 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="f15b1-132">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
::: zone-end