---
title: "在 Microsoft Teams 中为私人聊天和频道添加聊天机器人 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何在 Microsoft Teams 中为私人聊天和频道添加聊天机器人、创建自定义聊天机器人以及为私人聊天侧向加载你自己的聊天机器人。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 905a105fba269aebb2b01cbccc1a47e7667ca341
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="63a9e-103">在 Microsoft Teams 中为私人聊天和频道添加聊天机器人</span><span class="sxs-lookup"><span data-stu-id="63a9e-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="63a9e-104">聊天机器人是自动化程序，设置它们是为了响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。</span><span class="sxs-lookup"><span data-stu-id="63a9e-104">Bots are automated programs that are set up to respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="63a9e-105">聊天机器人允许用户在 Microsoft Teams 中通过聊天对话与云服务（例如，任务管理、计划和轮询）交互。</span><span class="sxs-lookup"><span data-stu-id="63a9e-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="63a9e-106">适用于 Microsoft Teams 的聊天机器人基于 [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) 构建而成，可以轻松地为 Microsoft Teams 启用使用此框架开发的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) and the bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span>

<span data-ttu-id="63a9e-107">当前，Microsoft Teams 支持在私人聊天和团队的频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-107">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="63a9e-108">管理员可以控制在 Office 365 租户中是允许还是禁止使用聊天机器人。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="63a9e-108">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="63a9e-109">可以在 Microsoft Teams 中利用由社区开发且已可用的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-109">Bots developed by the community and are made available, can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="63a9e-110">必须在租户级别启用聊天机器人的功能和聊天机器人的侧向加载，自定义聊天机器人才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="63a9e-110">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="63a9e-111">可以在私人聊天或频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-111">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="63a9e-112">对于频道，团队所有者或成员可以添加聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-112">For channels, team owners or members can add bots.</span></span>

<a name="add-bots-for-private-chat-and-channels"></a><span data-ttu-id="63a9e-113">为私人聊天和频道添加聊天机器人</span><span class="sxs-lookup"><span data-stu-id="63a9e-113">Add bots for Private Chat and channels</span></span>
--------------------------------------

<span data-ttu-id="63a9e-114">为私人聊天和频道集成聊天机器人的方式有两种：</span><span class="sxs-lookup"><span data-stu-id="63a9e-114">There are two ways to integrate a bot for private chats and channels:</span></span>

1.  <span data-ttu-id="63a9e-115">为**私人聊天**或**频道**安装公开提供的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-115">Install publicly available bots for **private chat** or **channels**.</span></span> <span data-ttu-id="63a9e-116">（这是第一种方式。）</span><span class="sxs-lookup"><span data-stu-id="63a9e-116">(This is the first option.)</span></span>

2.  <span data-ttu-id="63a9e-117">或者，要查找聊天机器人，请导航到**“聊天”**，搜索**联系人**，然后单击**“发现应用”**。</span><span class="sxs-lookup"><span data-stu-id="63a9e-117">Alternatively, to find bots, navigate to **Chat**, search for a **contact,** and click **Discover apps.**</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="63a9e-118">选择你要与其对话的**聊天机器人**，如下所示。</span><span class="sxs-lookup"><span data-stu-id="63a9e-118">Select which **Bot** you want to have a conversation with, as shown below.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  <span data-ttu-id="63a9e-119">选择后，为聊天机器人提供**权限**，然后选择是否要**在私人聊天中使用聊天机器人**，或选择要在其中使用聊天机器人的**团队**。</span><span class="sxs-lookup"><span data-stu-id="63a9e-119">Once selected, provide the bot **permissions,** and select whether you want to use **bots in a private chat** or select a **Team** to use it in.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  <span data-ttu-id="63a9e-120">或者，要在团队的频道中使用聊天机器人，只需单击**“查看团队和聊天机器人”**。</span><span class="sxs-lookup"><span data-stu-id="63a9e-120">Alternatively, to use a bot within a channel of a team, simply click **View Team and Bots**.</span></span> <span data-ttu-id="63a9e-121">你可以在此处发现其他聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-121">Here you can Discover additional bots.</span></span>

6.  <span data-ttu-id="63a9e-122">随时可以从团队中删除聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-122">At any time, a bot can be removed from the team.</span></span> <span data-ttu-id="63a9e-123">只需单击**“查看团队和聊天机器人”**查看所有聊天机器人，然后**删除**你要删除的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-123">Simply click **View Team and Bots,** to see all bots and then **remove** the one you’d like.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="63a9e-124">为 Microsoft Teams 创建自定义聊天机器人</span><span class="sxs-lookup"><span data-stu-id="63a9e-124">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="63a9e-125">你可以使用 Microsoft Bot Framework 轻松创建要集成到你的 LOB 应用中的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-125">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="63a9e-126">请参阅[为 Microsoft Teams 创建和测试聊天机器人](https://go.microsoft.com/fwlink/?linkid=854371)指导，了解如何开发和发布自己的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-126">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="63a9e-127">创建聊天机器人并向 Bot Framework 注册该聊天机器人时，可以选择是否发布该聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-127">When you create a bot and register it with the Bot Framework, you can choose to publish it or not.</span></span> <span data-ttu-id="63a9e-128">如果不发布，则聊天机器人保持专用状态。</span><span class="sxs-lookup"><span data-stu-id="63a9e-128">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="63a9e-129">你还可以要求你的用户先登录才能使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-129">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="63a9e-130">要求登录可确保在即使聊天机器人的应用 ID 已被其他人获知的情况下，仅贵组织的员工可以访问聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="63a9e-130">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="63a9e-131">请参阅 GitHub 上的 [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)，获取有关如何使用聊天机器人按照你的 Active Directory 对用户进行身份验证的代码示例。</span><span class="sxs-lookup"><span data-stu-id="63a9e-131">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="63a9e-132">可以在将聊天机器人部署到你的 Teams 中之前，先使用 [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) 对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="63a9e-132">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="63a9e-133">为私人聊天侧向加载你自己的聊天机器人</span><span class="sxs-lookup"><span data-stu-id="63a9e-133">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="63a9e-134">创建了你的聊天机器人后，导航到你开发的聊天机器人的**“聊天机器人仪表板”**[页面](https://go.microsoft.com/fwlink/?linkid=854374)，在**“详细信息”**下方，复制**Microsoft 应用 ID**。</span><span class="sxs-lookup"><span data-stu-id="63a9e-134">Once you have created your Bot, navigate to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and under **Details**, copy the **Microsoft App ID**.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="63a9e-135">在 Microsoft Teams 中的**“聊天”**窗格上，选择**添加聊天图标**。</span><span class="sxs-lookup"><span data-stu-id="63a9e-135">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="63a9e-136">将你的聊天机器人的 **Microsoft 应用 ID** 粘贴到**“至:”**。</span><span class="sxs-lookup"><span data-stu-id="63a9e-136">For **To:,** paste your bot's **Microsoft app ID**.</span></span>

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="63a9e-137">应用 ID 将解析为你的**聊天机器人名称**，然后你可以使用该聊天机器人启动聊天对话。</span><span class="sxs-lookup"><span data-stu-id="63a9e-137">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
