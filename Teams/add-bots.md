---
title: 在 Microsoft Teams 中为私人聊天和频道添加聊天机器人
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: 了解如何在 Microsoft 团队中为个人聊天、群组聊天和频道添加机器人，并上传自己的用于个人聊天、群组聊天和频道的 bot。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7837fd3a832a1764cfde3968b73337069762dab3
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "37516158"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="ad11b-103">在 Microsoft 团队中添加个人聊天、群组聊天和频道的 bot</span><span class="sxs-lookup"><span data-stu-id="ad11b-103">Add bots for personal chats, group chats, and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ad11b-104">聊天机器人是自动化程序，它们可响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。</span><span class="sxs-lookup"><span data-stu-id="ad11b-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="ad11b-105">聊天机器人允许用户在 Microsoft Teams 中通过聊天对话与云服务（例如，任务管理、计划和轮询）交互。</span><span class="sxs-lookup"><span data-stu-id="ad11b-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="ad11b-106">团队的 bot 基于[Microsoft Bot 框架](https://go.microsoft.com/fwlink/?linkid=854370)构建。</span><span class="sxs-lookup"><span data-stu-id="ad11b-106">Bots for Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="ad11b-107">可轻松为团队启用使用此框架开发的 bot。</span><span class="sxs-lookup"><span data-stu-id="ad11b-107">The bots that are developed using this framework can be enabled easily for Teams.</span></span> <span data-ttu-id="ad11b-108">有关详细信息，请参阅[为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ad11b-108">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="ad11b-109">当前，团队在团队中支持个人聊天、群组聊天和频道中的 bot。</span><span class="sxs-lookup"><span data-stu-id="ad11b-109">Currently, Teams supports bots in personal chats, group chats, and channels within a team.</span></span> <span data-ttu-id="ad11b-110">管理员可以控制在 Office 365 租户中是允许还是禁止使用聊天机器人。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="ad11b-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="ad11b-111">可在团队内利用社区开发的 bot。</span><span class="sxs-lookup"><span data-stu-id="ad11b-111">Bots developed by the community can be leveraged within Teams.</span></span> <span data-ttu-id="ad11b-112">必须在租户级别启用 bot 功能和上载自定义应用（也称为旁加载）的功能，才能使自定义机器人工作。</span><span class="sxs-lookup"><span data-stu-id="ad11b-112">The bot's functionality and the ability to upload custom apps (also known as sideloading) must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="ad11b-113">可以在个人聊天、群组聊天和频道中使用机器人。</span><span class="sxs-lookup"><span data-stu-id="ad11b-113">Bots can be used in personal chats, group chats, and channels.</span></span> <span data-ttu-id="ad11b-114">对于频道，团队所有者或成员可以添加聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="ad11b-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="ad11b-115">有关详细信息，请参阅[应用和服务](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)。</span><span class="sxs-lookup"><span data-stu-id="ad11b-115">For more information, see [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad11b-116">对于除测试用途之外的任何内容，建议不要通过 GUID 添加 bot。</span><span class="sxs-lookup"><span data-stu-id="ad11b-116">Adding a bot by GUID, for anything other than testing purposes, is not recommended.</span></span> <span data-ttu-id="ad11b-117">这样做会严重限制机器人的功能。</span><span class="sxs-lookup"><span data-stu-id="ad11b-117">Doing so severely limits the functionality of a bot.</span></span> <span data-ttu-id="ad11b-118">应将生产使用中的 bot 作为应用的一部分添加到团队。</span><span class="sxs-lookup"><span data-stu-id="ad11b-118">Bots in production use should be added to Teams as part of an app.</span></span> <span data-ttu-id="ad11b-119">请参阅[创建 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create)和[测试和调试 Microsoft 团队 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)</span><span class="sxs-lookup"><span data-stu-id="ad11b-119">See [Create a bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) and [Test and debug your Microsoft Teams bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)</span></span>

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="ad11b-120">为 Microsoft Teams 创建自定义聊天机器人</span><span class="sxs-lookup"><span data-stu-id="ad11b-120">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="ad11b-121">你可以使用 Microsoft Bot Framework 轻松创建要集成到你的 LOB 应用中的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="ad11b-121">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="ad11b-122">请参阅[创建和测试 Microsoft 团队的 bot bot](https://go.microsoft.com/fwlink/?linkid=854371)指南，了解如何开发和发布自己的 bot。</span><span class="sxs-lookup"><span data-stu-id="ad11b-122">See the [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="ad11b-123">创建聊天机器人并向 Bot Framework 注册该聊天机器人时，可以选择是否发布该聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="ad11b-123">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="ad11b-124">如果不发布，则聊天机器人保持专用状态。</span><span class="sxs-lookup"><span data-stu-id="ad11b-124">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="ad11b-125">你还可以要求你的用户先登录才能使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="ad11b-125">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="ad11b-126">要求登录可确保在即使聊天机器人的应用 ID 已被其他人获知的情况下，仅贵组织的员工可以访问聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="ad11b-126">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="ad11b-127">请参阅 GitHub 上的 [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)，获取有关如何使用聊天机器人按照你的 Active Directory 对用户进行身份验证的代码示例。</span><span class="sxs-lookup"><span data-stu-id="ad11b-127">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="ad11b-128">可以在将聊天机器人部署到你的 Teams 中之前，先使用 [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) 对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="ad11b-128">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="upload-your-bot-for-personal-chat"></a><span data-ttu-id="ad11b-129">上载个人聊天机器人</span><span class="sxs-lookup"><span data-stu-id="ad11b-129">Upload your bot for personal chat</span></span>
---------------------------------------

1. <span data-ttu-id="ad11b-130">创建你的 bot 后，请转到你开发的 bot 的**应用程序设置**，然后在 "**应用设置**" 下复制**MicrosoftAppId**设置的值。![Bot 的 "应用程序设置" 页面的屏幕截图](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="ad11b-130">After you create your bot, go to the **Application Settings** for the bot you developed, and then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>

2.  <span data-ttu-id="ad11b-131">在 "团队" 中的 "**聊天**" 窗格上，选择 "**添加聊天" 图标**。</span><span class="sxs-lookup"><span data-stu-id="ad11b-131">In Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="ad11b-132">在 "**收件人**" 中，粘贴你的 Bot 的**Microsoft 应用 ID**。</span><span class="sxs-lookup"><span data-stu-id="ad11b-132">In **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="ad11b-133">![突出显示了 Microsoft 应用 ID 的聊天窗格的屏幕截图](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="ad11b-133">![Screenshot of a chat pane with Microsoft app ID highlighted](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>

3. <span data-ttu-id="ad11b-134">应用 ID 将解析为你的**bot 名称，** 然后你可以开始与该 bot 聊天对话。</span><span class="sxs-lookup"><span data-stu-id="ad11b-134">The app ID will resolve to your **bot name,** and then you can start a chat conversation with that bot.</span></span>

<a name="upload-your-bot-for-group-chats-or-channels"></a><span data-ttu-id="ad11b-135">为群组聊天或频道上载机器人</span><span class="sxs-lookup"><span data-stu-id="ad11b-135">Upload your bot for group chats or channels</span></span>
-----------------------------------

<span data-ttu-id="ad11b-136">如果你想要与同事共享你的机器人，请按以下方法将其添加到组聊天或不同团队的频道：</span><span class="sxs-lookup"><span data-stu-id="ad11b-136">If you want to share your bot with your colleagues, here's how to add it to group chats or channels of different teams:</span></span>

1. <span data-ttu-id="ad11b-137">[为你的 bot 创建应用包](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)后，打开团队并浏览到要在其中上载机器人的团队。</span><span class="sxs-lookup"><span data-stu-id="ad11b-137">After you [create an app package for your bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be uploading the bot.</span></span>
2. <span data-ttu-id="ad11b-138">向团队添加**[应用程序 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)** 和应用。</span><span class="sxs-lookup"><span data-stu-id="ad11b-138">Add **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app to Teams.</span></span>
3. <span data-ttu-id="ad11b-139">在应用程序 Studio 中，选择 "**清单编辑器**" 选项卡。 !["清单编辑器" 选项卡的屏幕截图。](media/Adding_Bot_To_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="ad11b-139">In App Studio, select the **Manifest Editor** Tab. ![Screenshot of the Manifest Editor Tab.](media/Adding_Bot_To_Teams.png)</span></span>
4. <span data-ttu-id="ad11b-140">要在 "功能" 中添加你的机器人，请选择机器人，然后选择添加现有机器人。</span><span class="sxs-lookup"><span data-stu-id="ad11b-140">To add your bot, in capabilities, select the bot and choose to add an existing bot.</span></span> <span data-ttu-id="ad11b-141">然后，选择现有机器人或输入现有机器人的 Id。</span><span class="sxs-lookup"><span data-stu-id="ad11b-141">Then, choose an existing bot or enter the Id of an existing bot.</span></span>
<span data-ttu-id="ad11b-142">![显示选择已创建的 bot。](media/Select_Existing_Bot.png)</span><span class="sxs-lookup"><span data-stu-id="ad11b-142">![Shows selecting the bot you already created.](media/Select_Existing_Bot.png)</span></span>
5. <span data-ttu-id="ad11b-143">通过浏览找到应用包的位置，将其选中，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="ad11b-143">Browse to the location of your app package, select it, and then click **Open**.</span></span>
6. <span data-ttu-id="ad11b-144">选择你的 bot 的名称。</span><span class="sxs-lookup"><span data-stu-id="ad11b-144">Select your bot's name.</span></span> <span data-ttu-id="ad11b-145">（不要忘记选中 "范围" 部分下的 "**群组聊天**或**团队**" 复选框）。</span><span class="sxs-lookup"><span data-stu-id="ad11b-145">(Don't forget to select the **Group chat** or **Team** check box under the scope section).</span></span>
7. <span data-ttu-id="ad11b-146">选择 "**测试和分发**"。</span><span class="sxs-lookup"><span data-stu-id="ad11b-146">Select **Test and distribute**.</span></span>
8. <span data-ttu-id="ad11b-147">选择要将你的 bot 连接到的群组聊天或团队。</span><span class="sxs-lookup"><span data-stu-id="ad11b-147">Select the group chat or team where you want to connect your bot to.</span></span>

    <span data-ttu-id="ad11b-148">你的 bot 将在团队中的群组聊天或团队中可用。</span><span class="sxs-lookup"><span data-stu-id="ad11b-148">Your bot will be available in your group chat or team in Teams.</span></span>
