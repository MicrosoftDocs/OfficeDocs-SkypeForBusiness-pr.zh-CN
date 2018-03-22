---
title: 在 Microsoft Teams 中为私人聊天和频道添加聊天机器人
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
description: 了解如何在 Microsoft Teams 中为私人聊天和频道添加聊天机器人、创建自定义聊天机器人以及为私人聊天侧向加载你自己的聊天机器人。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50abaf5e6fb15451bfa1695ab2a16e0ce1747232
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="da322-103">在 Microsoft Teams 中为私人聊天和频道添加聊天机器人</span><span class="sxs-lookup"><span data-stu-id="da322-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="da322-104">聊天机器人是自动化程序，它们可响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。</span><span class="sxs-lookup"><span data-stu-id="da322-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="da322-105">聊天机器人允许用户在 Microsoft Teams 中通过聊天对话与云服务（例如，任务管理、计划和轮询）交互。</span><span class="sxs-lookup"><span data-stu-id="da322-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="da322-106">适用于 Microsoft Teams 的聊天机器人基于 [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) 构建而成，</span><span class="sxs-lookup"><span data-stu-id="da322-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="da322-107">可以轻松地为 Microsoft Teams 启用使用此框架开发的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="da322-108">有关详细信息，请参阅[Office 365 提供组织中的管理 Microsoft 小组功能](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="da322-108">For more information, see [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="da322-109">当前，Microsoft Teams 支持在私人聊天和团队的频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-109">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="da322-110">管理员可以控制在 Office 365 租户中是允许还是禁止使用聊天机器人。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="da322-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="da322-111">可以在 Microsoft Teams 中利用由社区开发的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="da322-112">必须在租户级别启用聊天机器人的功能和聊天机器人的侧向加载，自定义聊天机器人才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="da322-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="da322-113">可以在私人聊天或频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="da322-114">对于频道，团队所有者或成员可以添加聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="da322-115">有关详细信息，请参阅[应用和服务](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)中的“使用聊天机器人”一节。</span><span class="sxs-lookup"><span data-stu-id="da322-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="da322-116">为 Microsoft Teams 创建自定义聊天机器人</span><span class="sxs-lookup"><span data-stu-id="da322-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="da322-117">你可以使用 Microsoft Bot Framework 轻松创建要集成到你的 LOB 应用中的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-117">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="da322-118">请参阅[为 Microsoft Teams 创建和测试聊天机器人](https://go.microsoft.com/fwlink/?linkid=854371)指导，了解如何开发和发布自己的聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-118">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="da322-119">创建聊天机器人并向 Bot Framework 注册该聊天机器人时，可以选择是否发布该聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="da322-120">如果不发布，则聊天机器人保持专用状态。</span><span class="sxs-lookup"><span data-stu-id="da322-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="da322-121">你还可以要求你的用户先登录才能使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="da322-122">要求登录可确保在即使聊天机器人的应用 ID 已被其他人获知的情况下，仅贵组织的员工可以访问聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="da322-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="da322-123">请参阅 GitHub 上的 [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)，获取有关如何使用聊天机器人按照你的 Active Directory 对用户进行身份验证的代码示例。</span><span class="sxs-lookup"><span data-stu-id="da322-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="da322-124">可以在将聊天机器人部署到你的 Teams 中之前，先使用 [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) 对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="da322-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="da322-125">为私人聊天侧向加载你自己的聊天机器人</span><span class="sxs-lookup"><span data-stu-id="da322-125">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="da322-126">创建聊天机器人后，转到你开发的聊天机器人的**“聊天机器人仪表板”**[页面](https://go.microsoft.com/fwlink/?linkid=854374)，然后在**“详细信息”**下复制**“Microsoft 应用 ID”**。![突出显示 Microsoft 应用 ID 的聊天机器人的详细信息页面屏幕截图。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="da322-126">After you have created your bot, go to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and then under **Details**, copy the **Microsoft App ID**.![Screenshot of details page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span> 



2.  <span data-ttu-id="da322-127">在 Microsoft Teams 中的**“聊天”**窗格上，选择**添加聊天图标**。</span><span class="sxs-lookup"><span data-stu-id="da322-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="da322-128">将你的聊天机器人的 **Microsoft 应用 ID** 粘贴到**“至:”**。</span><span class="sxs-lookup"><span data-stu-id="da322-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="da322-129">![具有“添加聊天”图标且“至:”行中突出显示了 Microsoft 应用 ID 的聊天窗格屏幕截图。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="da322-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="da322-130">应用 ID 将解析为你的**聊天机器人名称**，然后你可以使用该聊天机器人启动聊天对话。</span><span class="sxs-lookup"><span data-stu-id="da322-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
