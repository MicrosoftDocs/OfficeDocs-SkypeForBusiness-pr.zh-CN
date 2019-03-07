---
title: 在 Microsoft Teams 中为私人聊天和频道添加聊天机器人
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: 了解如何在 Microsoft Teams 中为私人聊天和频道添加聊天机器人、创建自定义聊天机器人以及为私人聊天侧向加载你自己的聊天机器人。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3dfaabcbb2099f0b677e03b58ce79b5a7fca3237
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458801"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="6376f-103">在 Microsoft Teams 中为私人聊天和频道添加聊天机器人</span><span class="sxs-lookup"><span data-stu-id="6376f-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="6376f-104">聊天机器人是自动化程序，它们可响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。</span><span class="sxs-lookup"><span data-stu-id="6376f-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="6376f-105">聊天机器人允许用户在 Microsoft Teams 中通过聊天对话与云服务（例如，任务管理、计划和轮询）交互。</span><span class="sxs-lookup"><span data-stu-id="6376f-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="6376f-106">适用于 Microsoft Teams 的聊天机器人基于 [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) 构建而成，</span><span class="sxs-lookup"><span data-stu-id="6376f-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="6376f-107">可以轻松地为 Microsoft Teams 启用使用此框架开发的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="6376f-108">有关详细信息，请参阅[Office 365 组织中的管理 Microsoft 团队 features](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="6376f-108">For more information, see [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="6376f-109">当前，Microsoft Teams 支持在私人聊天和团队的频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-109">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="6376f-110">管理员可以控制在 Office 365 租户中是允许还是禁止使用聊天机器人。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="6376f-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="6376f-111">可以在 Microsoft Teams 中利用由社区开发的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="6376f-112">必须在租户级别启用聊天机器人的功能和聊天机器人的侧向加载，自定义聊天机器人才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="6376f-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="6376f-113">可以在私人聊天或频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="6376f-114">对于频道，团队所有者或成员可以添加聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="6376f-115">有关详细信息，请参阅[应用和服务](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)中的“使用聊天机器人”一节。</span><span class="sxs-lookup"><span data-stu-id="6376f-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="6376f-116">为 Microsoft Teams 创建自定义聊天机器人</span><span class="sxs-lookup"><span data-stu-id="6376f-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="6376f-117">你可以使用 Microsoft Bot Framework 轻松创建要集成到你的 LOB 应用中的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-117">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="6376f-118">请参阅[为 Microsoft Teams 创建和测试聊天机器人](https://go.microsoft.com/fwlink/?linkid=854371)指导，了解如何开发和发布自己的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-118">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="6376f-119">创建聊天机器人并向 Bot Framework 注册该聊天机器人时，可以选择是否发布该聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="6376f-120">如果不发布，则聊天机器人保持专用状态。</span><span class="sxs-lookup"><span data-stu-id="6376f-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="6376f-121">你还可以要求你的用户先登录才能使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="6376f-122">要求登录可确保在即使聊天机器人的应用 ID 已被其他人获知的情况下，仅贵组织的员工可以访问聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="6376f-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="6376f-123">请参阅 GitHub 上的 [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)，获取有关如何使用聊天机器人按照你的 Active Directory 对用户进行身份验证的代码示例。</span><span class="sxs-lookup"><span data-stu-id="6376f-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="6376f-124">可以在将聊天机器人部署到你的 Teams 中之前，先使用 [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) 对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="6376f-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="6376f-125">为私人聊天侧向加载你自己的聊天机器人</span><span class="sxs-lookup"><span data-stu-id="6376f-125">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="6376f-126">您已创建您自动程序后，转到**应用程序设置**为自动程序您开发，然后在**应用程序设置**下，复制**MicrosoftAppId**设置的值。![与 Microsoft 应用程序 ID 突出显示自动程序的应用程序设置的屏幕截图页。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="6376f-126">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="6376f-127">在 Microsoft Teams 中的 **“聊天”** 窗格上，选择**添加聊天图标**。</span><span class="sxs-lookup"><span data-stu-id="6376f-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="6376f-128">将你的聊天机器人的 **Microsoft 应用 ID** 粘贴到 **“至:”**。</span><span class="sxs-lookup"><span data-stu-id="6376f-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="6376f-129">![具有“添加聊天”图标且“至:”行中突出显示了 Microsoft 应用 ID 的聊天窗格屏幕截图。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="6376f-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="6376f-130">应用 ID 将解析为你的**聊天机器人名称**，然后你可以使用该聊天机器人启动聊天对话。</span><span class="sxs-lookup"><span data-stu-id="6376f-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>

<a name="side-load-your-bot-for-channels"></a><span data-ttu-id="6376f-131">端加载通道您 bot</span><span class="sxs-lookup"><span data-stu-id="6376f-131">Side load your bot for channels</span></span>
-----------------------------------

<span data-ttu-id="6376f-132">如果您想要与同事共享您自动程序，下面介绍了如何将其添加到不同的团队的通道：</span><span class="sxs-lookup"><span data-stu-id="6376f-132">If you want to share your bot with your colleagues, here's how to add it to channels of different teams:</span></span>

1. <span data-ttu-id="6376f-133">[创建应用程序包为您自动程序](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/apps/apps-upload)后，打开团队，并浏览到工作组在其中您将在一侧加载 bot。</span><span class="sxs-lookup"><span data-stu-id="6376f-133">After you have [created an app package for your bot](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be side-loading the bot.</span></span>
2. <span data-ttu-id="6376f-134">团队名称旁边，选择**更多**（...）。</span><span class="sxs-lookup"><span data-stu-id="6376f-134">Select **More** (...) next to the team name.</span></span>
3. <span data-ttu-id="6376f-135">选择**管理团队**，然后选择**应用程序**选项卡。</span><span class="sxs-lookup"><span data-stu-id="6376f-135">Select **Manage team** and then select the **Apps** tab.</span></span>
4. <span data-ttu-id="6376f-136">您会在屏幕右下角，选择**上载自定义应用程序**。</span><span class="sxs-lookup"><span data-stu-id="6376f-136">At the bottom-right of your screen, select **Upload a custom app**.</span></span>
5. <span data-ttu-id="6376f-137">浏览到应用程序包的位置，选择它，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="6376f-137">Browse to the location of your app package, select it, and then click **Open**.</span></span>
