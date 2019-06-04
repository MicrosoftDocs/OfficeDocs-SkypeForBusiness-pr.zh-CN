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
ms.openlocfilehash: 926a698e65176596e0009e42d3912fb88c771a5d
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681855"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="befcb-103">在 Microsoft Teams 中为私人聊天和频道添加聊天机器人</span><span class="sxs-lookup"><span data-stu-id="befcb-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="befcb-104">聊天机器人是自动化程序，它们可响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。</span><span class="sxs-lookup"><span data-stu-id="befcb-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="befcb-105">聊天机器人允许用户在 Microsoft Teams 中通过聊天对话与云服务（例如，任务管理、计划和轮询）交互。</span><span class="sxs-lookup"><span data-stu-id="befcb-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="befcb-106">适用于 Microsoft Teams 的聊天机器人基于 [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) 构建而成，</span><span class="sxs-lookup"><span data-stu-id="befcb-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="befcb-107">可以轻松地为 Microsoft Teams 启用使用此框架开发的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="befcb-108">有关详细信息，请参阅[为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="befcb-108">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="befcb-109">当前，Microsoft Teams 支持在私人聊天和团队的频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-109">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="befcb-110">管理员可以控制在 Office 365 租户中是允许还是禁止使用聊天机器人。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="befcb-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="befcb-111">可以在 Microsoft Teams 中利用由社区开发的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="befcb-112">必须在租户级别启用聊天机器人的功能和聊天机器人的侧向加载，自定义聊天机器人才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="befcb-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="befcb-113">可以在私人聊天或频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="befcb-114">对于频道，团队所有者或成员可以添加聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="befcb-115">有关详细信息，请参阅[应用和服务](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)中的“使用聊天机器人”一节。</span><span class="sxs-lookup"><span data-stu-id="befcb-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="befcb-116">对于除测试用途之外的任何内容, 建议不要通过 GUID 添加 bot。</span><span class="sxs-lookup"><span data-stu-id="befcb-116">Adding a bot by GUID, for anything other than testing purposes, is not recommended.</span></span> <span data-ttu-id="befcb-117">这样做会严重限制机器人的功能。</span><span class="sxs-lookup"><span data-stu-id="befcb-117">Doing so severely limits the functionality of a bot.</span></span> <span data-ttu-id="befcb-118">应将生产使用中的 bot 作为应用的一部分添加到团队。</span><span class="sxs-lookup"><span data-stu-id="befcb-118">Bots in production use should be added to Teams as part of an app.</span></span> <span data-ttu-id="befcb-119">请参阅[创建 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create)和[测试和调试 Microsoft 团队 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)</span><span class="sxs-lookup"><span data-stu-id="befcb-119">See [Create a bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) and [Test and debug your Microsoft Teams bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)</span></span>

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="befcb-120">为 Microsoft Teams 创建自定义聊天机器人</span><span class="sxs-lookup"><span data-stu-id="befcb-120">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="befcb-121">你可以使用 Microsoft Bot Framework 轻松创建要集成到你的 LOB 应用中的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-121">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="befcb-122">请参阅[为 Microsoft Teams 创建和测试聊天机器人](https://go.microsoft.com/fwlink/?linkid=854371)指导，了解如何开发和发布自己的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-122">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="befcb-123">创建聊天机器人并向 Bot Framework 注册该聊天机器人时，可以选择是否发布该聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-123">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="befcb-124">如果不发布，则聊天机器人保持专用状态。</span><span class="sxs-lookup"><span data-stu-id="befcb-124">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="befcb-125">你还可以要求你的用户先登录才能使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-125">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="befcb-126">要求登录可确保在即使聊天机器人的应用 ID 已被其他人获知的情况下，仅贵组织的员工可以访问聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="befcb-126">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="befcb-127">请参阅 GitHub 上的 [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)，获取有关如何使用聊天机器人按照你的 Active Directory 对用户进行身份验证的代码示例。</span><span class="sxs-lookup"><span data-stu-id="befcb-127">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="befcb-128">可以在将聊天机器人部署到你的 Teams 中之前，先使用 [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) 对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="befcb-128">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="befcb-129">为私人聊天侧向加载你自己的聊天机器人</span><span class="sxs-lookup"><span data-stu-id="befcb-129">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="befcb-130">创建你的 bot 后, 请转到你开发的 bot 的**应用程序设置**, 然后在 "**应用设置**" 下复制**MicrosoftAppId**设置的值。![Bot 的 "应用程序设置" 页面的屏幕截图](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="befcb-130">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="befcb-131">在 Microsoft Teams 中的 **“聊天”** 窗格上，选择**添加聊天图标**。</span><span class="sxs-lookup"><span data-stu-id="befcb-131">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="befcb-132">将你的聊天机器人的 **Microsoft 应用 ID** 粘贴到 **“至:”**。</span><span class="sxs-lookup"><span data-stu-id="befcb-132">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="befcb-133">![突出显示了 Microsoft 应用 ID 的聊天窗格的屏幕截图](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="befcb-133">![Screenshot of a chat pane with Microsoft app ID highlighted](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="befcb-134">应用 ID 将解析为你的**聊天机器人名称**，然后你可以使用该聊天机器人启动聊天对话。</span><span class="sxs-lookup"><span data-stu-id="befcb-134">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>

<a name="side-load-your-bot-for-channels"></a><span data-ttu-id="befcb-135">侧面加载频道的 bot</span><span class="sxs-lookup"><span data-stu-id="befcb-135">Side load your bot for channels</span></span>
-----------------------------------

<span data-ttu-id="befcb-136">如果你想要与同事共享你的机器人, 请按以下方法将其添加到不同团队的频道:</span><span class="sxs-lookup"><span data-stu-id="befcb-136">If you want to share your bot with your colleagues, here's how to add it to channels of different teams:</span></span>

1. <span data-ttu-id="befcb-137">[为你的 bot 创建应用包](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)后, 打开团队并浏览到要在其中加载机器人的团队。</span><span class="sxs-lookup"><span data-stu-id="befcb-137">After you have [created an app package for your bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be side-loading the bot.</span></span>
2. <span data-ttu-id="befcb-138">向 Microsoft 团队添加**[应用程序 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)** 应用程序。</span><span class="sxs-lookup"><span data-stu-id="befcb-138">Add **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app to Microsoft Teams.</span></span>
3. <span data-ttu-id="befcb-139">在应用程序 Studio 中, 选择 "**清单编辑器**" 选项卡。 !["清单编辑器" 选项卡的屏幕截图。](media/Adding_Bot_To_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="befcb-139">In App Studio, select the **Manifest Editor** Tab. ![Screenshot of the Manifest Editor Tab.](media/Adding_Bot_To_Teams.png)</span></span>
4. <span data-ttu-id="befcb-140">若要在 "功能" 中添加你的机器人, 请选择 "bot" 并选择添加现有机器人, 然后你可以选择删除一个现有的 bot 或输入一个现有 bot 的 Id。</span><span class="sxs-lookup"><span data-stu-id="befcb-140">To add your bot, In capabilities, select bot and chose to add an existing bot, then you will have the option to chose an existing bot from a drop or enter the Id of one of your existing bots.</span></span>
<span data-ttu-id="befcb-141">![显示选择已创建的 bot。](media/Select_Existing_Bot.png)</span><span class="sxs-lookup"><span data-stu-id="befcb-141">![Shows selecting the bot you already created.](media/Select_Existing_Bot.png)</span></span>
5. <span data-ttu-id="befcb-142">通过浏览找到应用包的位置, 将其选中, 然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="befcb-142">Browse to the location of your app package, select it, and then click **Open**.</span></span>
6. <span data-ttu-id="befcb-143">选择你的 bot 的名称 (不要忘记选中 "范围" 部分下的 "团队" 复选框)</span><span class="sxs-lookup"><span data-stu-id="befcb-143">Select your bot's name (Don't forget to check the "Team" checkbox under the scope section)</span></span>
7. <span data-ttu-id="befcb-144">选择 "测试和分布" 选项。</span><span class="sxs-lookup"><span data-stu-id="befcb-144">Select the Test and distribute option.</span></span>
8. <span data-ttu-id="befcb-145">在弹出的对话框中, 选择您希望将机器人连接到的团队。</span><span class="sxs-lookup"><span data-stu-id="befcb-145">Select the team where you wish to connect your bot to in the dialog which pops up.</span></span>

<span data-ttu-id="befcb-146">因此, 你的 bot 将在你的 Microsoft 团队的团队中可用。</span><span class="sxs-lookup"><span data-stu-id="befcb-146">With this, your bot will be available in your Microsoft Team's team.</span></span>
