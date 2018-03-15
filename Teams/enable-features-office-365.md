---
title: "在你的 Office 365 组织中启用 Microsoft Teams 功能"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "了解可以在你的 Office 365 组织中启用或禁用的所有 Microsoft Teams 功能，包括租户范围的设置、电子邮件集成、应用及云存储等。"
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87871cb46c1b9e584308b75376622473a3131888
ms.sourcegitcommit: 50446359cd7c359eb2536176545291c723392e47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
<a name="turn-on-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="32025-103">在你的 Office 365 组织中启用 Microsoft Teams 功能</span><span class="sxs-lookup"><span data-stu-id="32025-103">Turn on Microsoft Teams features in your Office 365 organization</span></span>
======================================================

<span data-ttu-id="32025-104">Teams 可以在 Office 365 租户级别启用或关闭多项设置。</span><span class="sxs-lookup"><span data-stu-id="32025-104">Teams has multiple settings that can be turned on or turned off at the Office 365 tenant level.</span></span> <span data-ttu-id="32025-105">如果为租户启用了 Teams，同样启用了 Teams 的任何用户都将从租户级别继承设置。</span><span class="sxs-lookup"><span data-stu-id="32025-105">With Teams turned on for a tenant, any user that is also enabled for Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="32025-106">下面是 Office 365 管理员可以在 Teams 中启用或禁用的功能列表。</span><span class="sxs-lookup"><span data-stu-id="32025-106">Below is the list of features an Office 365 administrator can turn on or turn off in Teams.</span></span> 

<span data-ttu-id="32025-107">除非另有说明，否则选项的默认值为“开启”。</span><span class="sxs-lookup"><span data-stu-id="32025-107">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="32025-108">要管理 Teams 的管理员设置，请转到 Office 365 管理中心并打开“**设置**” > “**服务和外接程序**”，然后选择“**Microsoft Teams**”。</span><span class="sxs-lookup"><span data-stu-id="32025-108">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="32025-109">如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作：</span><span class="sxs-lookup"><span data-stu-id="32025-109">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> <span data-ttu-id="32025-110">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="32025-110">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="32025-111">Office 365 管理员可以随时通过 Office 365 管理中心关闭 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="32025-111">An Office 365 admin can turn off Microsoft Teams at any time in the Office 365 admin center.</span></span> <span data-ttu-id="32025-112">请注意，即使你关闭 Microsoft Teams，具有 Teams 有效许可证的用户也能继续看到 Teams 应用磁贴。</span><span class="sxs-lookup"><span data-stu-id="32025-112">Be aware that users with active Microsoft Teams licenses will continue to see the Teams app tile even if you turn off Teams.</span></span> <span data-ttu-id="32025-113">有关如何从用户删除许可证的详细信息，请参阅[管理对 Microsoft Teams 许可证的用户访问](user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="32025-113">For details about how to remove licenses from users, see [Manage user access to Microsoft Teams](user-access.md).</span></span> <span data-ttu-id="32025-114">禁用 Teams 后，将阻止从 Teams 客户端进行访问，但仍可以通过其他客户端和服务获取数据，例如，通过 SharePoint 和 OneDrive 获取文件。</span><span class="sxs-lookup"><span data-stu-id="32025-114">After Teams is disabled, access from the Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive.</span></span> <span data-ttu-id="32025-115">除非明确删除团队，否则所有数据保留在原处。</span><span class="sxs-lookup"><span data-stu-id="32025-115">All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="office-365-tenant-wide-settings"></a><span data-ttu-id="32025-116">Office 365 租户范围的设置</span><span class="sxs-lookup"><span data-stu-id="32025-116">Office 365 tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="32025-117">在**租户范围的设置**中，你可以开启或关闭“常规”、“电子邮件集成”、“应用”和“自定义云存储”中的选项。</span><span class="sxs-lookup"><span data-stu-id="32025-117">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

<span data-ttu-id="32025-118">要编辑 Teams 的**租户范围的设置**，请转到 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="32025-118">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="32025-119">选择**“设置”** > **“服务和外接程序”** > **“Microsoft Teams”**。</span><span class="sxs-lookup"><span data-stu-id="32025-119">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

### <a name="general"></a><span data-ttu-id="32025-120">常规</span><span class="sxs-lookup"><span data-stu-id="32025-120">General</span></span>

<span data-ttu-id="32025-121">在“常规”部分中可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="32025-121">The General section lets you configure the following settings for your organization:</span></span>

> ![租户范围的设置中的“常规”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="32025-123">**在个人资料中显示组织结构图：**如果启用此设置，将在用户的联系人卡片中显示组织结构图图标，单击该图标后，将显示详细的组织结构图。</span><span class="sxs-lookup"><span data-stu-id="32025-123">**Show organizational chart in personal profile:** When this setting is turned on, it shows the organizational chart icon in the user’s contact card, and when clicked, it displays the detailed organizational chart.</span></span>

    ![用户的联系人卡片中的组织结构图图标屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![组织结构图屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-  <span data-ttu-id="32025-126">**对没有 Teams 的收件人使用 Skype for Business：**如果启用此设置，对于未启用 Teams 的用户，Teams 对话将自动显示在 Skype for Business 中。</span><span class="sxs-lookup"><span data-stu-id="32025-126">**Use Skype for Business for recipients who don’t have Teams:** When this setting is turned on, Teams conversations automatically show up in Skype for Business for users that aren't enabled for Teams.</span></span>  

-   <span data-ttu-id="32025-127">**允许 T-Bot 主动发送帮助消息：**如果启用此设置，T-Bot 将启动与用户的私人聊天会话以帮助他们使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="32025-127">**Allow T-bot proactive help messages:** When this setting is turned on, T-bot will initiate a private chat session with users to help them use Teams.</span></span>

    ![Teams 界面中的“T-Bot”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="32025-129">电子邮件集成</span><span class="sxs-lookup"><span data-stu-id="32025-129">Email integration</span></span>
-----------------

<span data-ttu-id="32025-130">开启此功能，以便用户可以使用频道电子邮件地址向 Teams 中的频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32025-130">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="32025-131">用户可以对属于其所属团队的任何频道执行此操作。</span><span class="sxs-lookup"><span data-stu-id="32025-131">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="32025-132">用户还可以向为团队成员启用了添加连接器的团队中的任何频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32025-132">Users can also send emails to any channel in a team that has adding connectors enabled for team members.</span></span> <span data-ttu-id="32025-133">并且，即使用户无权创建频道电子邮件地址，如果有权限的用户创建了该地址，则用户可以从该频道的“**更多选项**”菜单访问该地址。</span><span class="sxs-lookup"><span data-stu-id="32025-133">And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the **More options** menu for that channel.</span></span>

<span data-ttu-id="32025-134">为贵组织配置以下“**电子邮件集成**”设置：</span><span class="sxs-lookup"><span data-stu-id="32025-134">Configure the following **Email integration** settings for your organization:</span></span> 

   ![租户范围的设置中的“电子邮件集成”部分屏幕截图。](media/QS-edu-email-integration.png)

-   <span data-ttu-id="32025-136">**允许用户向频道发送电子邮件：**如果启用此设置，将启用邮件挂钩，用户可以通过向 Teams 频道的电子邮件地址发送电子邮件来向频道发布消息。</span><span class="sxs-lookup"><span data-stu-id="32025-136">**Allow users to send emails to channels:** When turned on, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of a Teams channel.</span></span> 

 
-   <span data-ttu-id="32025-137">**允许用户向频道发送电子邮件：**如果启用此设置，将启用邮件挂钩，用户可以通过向 Teams 频道的电子邮件地址发送电子邮件来向频道发布消息。</span><span class="sxs-lookup"><span data-stu-id="32025-137">**Allow users to send emails to channels:** When turned on, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Teams channel.</span></span> 

    <span data-ttu-id="32025-138">要查找频道的电子邮件地址，请单击频道的“**更多选项**”菜单，然后选择“**获取电子邮件地址**”。</span><span class="sxs-lookup"><span data-stu-id="32025-138">To find the email address for a channel, click the **More options** menu for the channel and then select **Get email address**.</span></span> 

-   <span data-ttu-id="32025-139">**受限制的发件人列表：**可以对发件人域做进一步限制，以确保仅允许的 SMTP 域可以向 Teams 频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32025-139">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="32025-140">应用</span><span class="sxs-lookup"><span data-stu-id="32025-140">Apps</span></span>
----

<span data-ttu-id="32025-141">应用是第三方服务提供的选项卡、连接器或聊天机器人或这三者的任意组合。</span><span class="sxs-lookup"><span data-stu-id="32025-141">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="32025-142">可以在 Office 365 管理中心配置 Teams 管理策略来控制允许哪些外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="32025-142">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="32025-143">通过这些策略可以指定允许和不允许哪些应用、新的外部应用行为以及是否允许侧向加载应用。</span><span class="sxs-lookup"><span data-stu-id="32025-143">These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="32025-144">在**“应用”**下，可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="32025-144">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![“应用”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="32025-146">**在 Microsoft Teams 中允许外部应用：**如果打开此开关，用户可以添加可供 Office 365 租户使用的选项卡和聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="32025-146">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![“应用”部分中的“允许外部应用”控件的屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="32025-148">**默认启用新的外部应用：**打开此开关后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。</span><span class="sxs-lookup"><span data-stu-id="32025-148">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="32025-149">如果你希望控制新应用，请关闭此开关。</span><span class="sxs-lookup"><span data-stu-id="32025-149">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="32025-150">当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。</span><span class="sxs-lookup"><span data-stu-id="32025-150">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="32025-151">**允许侧向加载外部应用：**如果打开此开关，用户可以安装和启用自定义聊天机器人和选项卡。</span><span class="sxs-lookup"><span data-stu-id="32025-151">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="32025-152">要了解详细信息，请阅读 [Teams 中适用于应用的管理员设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="32025-152">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 



<a name="custom-cloud-storage"></a><span data-ttu-id="32025-153">自定义云存储</span><span class="sxs-lookup"><span data-stu-id="32025-153">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="32025-154">Teams 中的云存储选项当前包括 Box、Dropbox、Google Drive 和 ShareFile。</span><span class="sxs-lookup"><span data-stu-id="32025-154">Cloud storage options in Teams currently include Box, Dropbox, Google Drive, and ShareFile.</span></span> <span data-ttu-id="32025-155">用户可以在 Teams 频道和聊天中从云存储服务上载和共享文件。</span><span class="sxs-lookup"><span data-stu-id="32025-155">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="32025-156">可打开贵组织要使用的云存储提供商对应的开关。</span><span class="sxs-lookup"><span data-stu-id="32025-156">Turn on the switch for the cloud storage providers that your organization wants to use.</span></span> 

![“自定义云存储”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a><span data-ttu-id="32025-158">按许可证的用户设置</span><span class="sxs-lookup"><span data-stu-id="32025-158">User settings by license</span></span>
------------------------

<span data-ttu-id="32025-159">在**“按许可证的用户设置”**中，可以开启或关闭“团队和频道”、“通话和会议”以及“消息”中的选项。</span><span class="sxs-lookup"><span data-stu-id="32025-159">In **User settings by license**, you can turn on or turn off options in Teams and channels, Calls and meetings, and Messaging.</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="32025-160">团队和频道</span><span class="sxs-lookup"><span data-stu-id="32025-160">Teams and channels</span></span>
------------------

<span data-ttu-id="32025-161">团队用于将一群人集中在一起，以便这些人密切合作来完成事情。</span><span class="sxs-lookup"><span data-stu-id="32025-161">A team is designed to bring together a group of people who work closely to get things done.</span></span> <span data-ttu-id="32025-162">对于基于项目的工作（例如，使某个产品上市或创建数字化作战室），团队可以是动态的。</span><span class="sxs-lookup"><span data-stu-id="32025-162">Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room).</span></span> <span data-ttu-id="32025-163">团队也可以是持续存在的，以反映贵组织的内部结构。</span><span class="sxs-lookup"><span data-stu-id="32025-163">Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="32025-164">Office 365 租户可以拥有的最大团队数当前为 500,000。</span><span class="sxs-lookup"><span data-stu-id="32025-164">The maximum number of teams that an Office 365 tenant can have is currently 500,000.</span></span> <span data-ttu-id="32025-165">全局管理员可以创建无限数量的团队。</span><span class="sxs-lookup"><span data-stu-id="32025-165">A global admin can create an unlimited number of teams.</span></span> <span data-ttu-id="32025-166">用户可以创建 250 个团队。</span><span class="sxs-lookup"><span data-stu-id="32025-166">A user can create 250 teams.</span></span> <span data-ttu-id="32025-167">团队所有者可以向团队添加 2500 个成员。</span><span class="sxs-lookup"><span data-stu-id="32025-167">A team owner can add 2500 members to a team.</span></span>

<span data-ttu-id="32025-168">作为管理员，你可以通过使用 Office 365 管理中心中的“组”仪表板管理团队所有者和成员。</span><span class="sxs-lookup"><span data-stu-id="32025-168">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center.</span></span> <span data-ttu-id="32025-169">要了解详细信息，请单击“**团队和频道**”下的“**使用 Office 365 管理中心中的‘组’仪表板管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="32025-169">To learn more, click **Use the Groups dashboard in the Office 365 admin center to manage teams** under **Teams and channels**.</span></span>

<span data-ttu-id="32025-170">你可以控制贵组织中哪些用户可以在 Teams 中创建团队。</span><span class="sxs-lookup"><span data-stu-id="32025-170">You can control which users in your organization can create teams in Teams.</span></span> <span data-ttu-id="32025-171">Office 365 组定义的相同创建设置适用于 Teams。</span><span class="sxs-lookup"><span data-stu-id="32025-171">The same creation settings defined by Office 365 groups apply to Teams.</span></span> <span data-ttu-id="32025-172">有关管理 Office 365 组的详细信息，请参阅[创建 Office 365 组](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f)和[控制哪些人可以创建 Office 365 组](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="32025-172">For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

> [!NOTE]
> <span data-ttu-id="32025-173">无法从“组”仪表板创建团队。</span><span class="sxs-lookup"><span data-stu-id="32025-173">You can't create teams from the Groups dashboard.</span></span> <span data-ttu-id="32025-174">必须使用 Teams 桌面客户端或 Web 应用创建团队。</span><span class="sxs-lookup"><span data-stu-id="32025-174">Teams must be created by using the Teams desktop client or web app.</span></span>

<span data-ttu-id="32025-175">默认情况下，所有用户都可以创建团队或组。</span><span class="sxs-lookup"><span data-stu-id="32025-175">By default, every user can create a team or group.</span></span> <span data-ttu-id="32025-176">选择 Teams 客户端（桌面客户端或 Web 应用）中左侧的**“团队”**，然后选择客户端底部的**“创建并加入团队”**（在团队列表下方）。</span><span class="sxs-lookup"><span data-stu-id="32025-176">Choose **Teams** on the left side in the Teams client (desktop client or web app), then choose **Create and join team** at the bottom of the client, below the team list.</span></span>

![“按许可证的用户设置”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="32025-178">频道是团队的子类别。</span><span class="sxs-lookup"><span data-stu-id="32025-178">Channels are subcategories of teams.</span></span> <span data-ttu-id="32025-179">团队中的任何人都可以添加频道以及参与频道中的对话。</span><span class="sxs-lookup"><span data-stu-id="32025-179">Anyone on the team can add a channel and participate in the conversations in a channel.</span></span> <span data-ttu-id="32025-180">你可为活动或部门创建频道。</span><span class="sxs-lookup"><span data-stu-id="32025-180">You might create a channel for an activity or for a department.</span></span> <span data-ttu-id="32025-181">对话、文件和 Wiki 是特定于每个频道的，但团队的所有成员都可以查看它们。</span><span class="sxs-lookup"><span data-stu-id="32025-181">Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

## <a name="calls-and-meetings"></a><span data-ttu-id="32025-182">通话和会议</span><span class="sxs-lookup"><span data-stu-id="32025-182">Calls and meetings</span></span>

<span data-ttu-id="32025-183">为贵组织配置以下“**通话和会议**”设置：</span><span class="sxs-lookup"><span data-stu-id="32025-183">Configure the following **Calls and meetings** settings for your organization:</span></span>

![“通话和会议”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="32025-185">会议中的最大人数是 80。</span><span class="sxs-lookup"><span data-stu-id="32025-185">The maximum number of people in a meeting is 80.</span></span> <span data-ttu-id="32025-186">私人聊天中可以有 20 个成员，包括创建聊天的用户。</span><span class="sxs-lookup"><span data-stu-id="32025-186">There can be 20 members in a private chat, including the user who created the chat.</span></span>

-   <span data-ttu-id="32025-187">**允许安排私人会议：**如果启用此设置，用户可以安排不在任何频道中列出的私人会议。</span><span class="sxs-lookup"><span data-stu-id="32025-187">**Allow scheduling for private meetings**: When turned on, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="32025-188">**允许临时频道聚会**：打开此功能后，用户可以快速为专为紧急或特定目的而创建的频道快速启动会议。</span><span class="sxs-lookup"><span data-stu-id="32025-188">**Allow ad-hoc channel meetup**: When turned on, users can quickly start a meeting for a channel that has been created for an immediate or specific purpose.</span></span>

-   <span data-ttu-id="32025-189">**允许安排频道会议：**如果启用此设置，用户可以为某个频道安排会议，所有频道成员只需单击一下即可轻松加入会议。</span><span class="sxs-lookup"><span data-stu-id="32025-189">**Allow scheduling for channel meetings**: When turned on, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="32025-190">**在会议中允许视频：**指定是否允许在会议中使用视频。</span><span class="sxs-lookup"><span data-stu-id="32025-190">**Allow videos in meetings:** Specifies whether the use of video is allowed in meetings.</span></span>

-   <span data-ttu-id="32025-191">**允许在会议中共享屏幕：**指定是否允许在会议中共享屏幕。</span><span class="sxs-lookup"><span data-stu-id="32025-191">**Allow screen sharing in meetings**: Specifies whether screen sharing is allowed in meetings.</span></span>

-   <span data-ttu-id="32025-192">**允许专线通话：**如果启用此设置，用户可以进行专线通话。</span><span class="sxs-lookup"><span data-stu-id="32025-192">**Allow private calling**: When turned on, users can make private calls.</span></span>

## <a name="messaging"></a><span data-ttu-id="32025-193">消息</span><span class="sxs-lookup"><span data-stu-id="32025-193">Messaging</span></span> 

<span data-ttu-id="32025-194">在“消息”部分中可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="32025-194">The Messaging section lets you configure the following settings for your organization:</span></span>

![“消息”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="32025-196">**启用 Giphy 以便用户可以向对话添加 gif：**如果启用此设置，用户可以在对话中使用动画图片。</span><span class="sxs-lookup"><span data-stu-id="32025-196">**Enable Giphy so users can add gifs to conversations**: When turned on, users can use animated pictures within the conversations.</span></span>

-   <span data-ttu-id="32025-197">**内容分级：**如果启用动画图片，可以应用内容分级来限制可以在对话中显示的动画图片的类型。</span><span class="sxs-lookup"><span data-stu-id="32025-197">**Content Rating**: When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations.</span></span> <span data-ttu-id="32025-198">可用的内容分级选项如下：</span><span class="sxs-lookup"><span data-stu-id="32025-198">Available content rating options are:</span></span>

    -   <span data-ttu-id="32025-199">无限制</span><span class="sxs-lookup"><span data-stu-id="32025-199">No restriction</span></span>
    -   <span data-ttu-id="32025-200">适中（默认值）</span><span class="sxs-lookup"><span data-stu-id="32025-200">Moderate (the default value)</span></span>
    -   <span data-ttu-id="32025-201">严格</span><span class="sxs-lookup"><span data-stu-id="32025-201">Strict</span></span>

-   <span data-ttu-id="32025-202">**启用用户可以编辑和添加到对话的 Meme：**如果启用此设置，用户可以使用 Internet Meme 制作幽默的帖子。</span><span class="sxs-lookup"><span data-stu-id="32025-202">**Enable memes that users can edit and add to conversations**: When turned on, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="32025-203">**启用用户可以编辑和添加到对话的表情图片：**如果启用此设置，用户可以发布包含可编辑文字的图片以引起频道成员的注意。</span><span class="sxs-lookup"><span data-stu-id="32025-203">**Enable stickers that users can edit and add to conversations**: When turned on, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="32025-204">**允许所有者删除所有消息：**如果启用此设置，频道所有者可以删除频道中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="32025-204">**Allow owners to delete all messages**: When turned on, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="32025-205">**允许用户编辑自己的消息：**如果启用此设置，用户可以编辑自己的消息。</span><span class="sxs-lookup"><span data-stu-id="32025-205">**Allow users to edit their own messages**: When turned on, users can edit their own messages.</span></span>

-   <span data-ttu-id="32025-206">**允许用户删除自己的消息：**如果启用此设置，用户可以删除自己的消息。</span><span class="sxs-lookup"><span data-stu-id="32025-206">**Allow users to delete their own messages**: When turned on, users can delete their own messages.</span></span>

-   <span data-ttu-id="32025-207">**允许用户私人聊天：**如果启用此设置，用户可以参与仅聊天中的人员（而非团队中的所有人）可见的私人聊天。</span><span class="sxs-lookup"><span data-stu-id="32025-207">**Allow users to chat privately**: When turned on, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>


| |  |  |
|---------|---------|---------|
|![决策点图标。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="32025-209">决策点</span><span class="sxs-lookup"><span data-stu-id="32025-209">Decision Point</span></span>         |<span data-ttu-id="32025-210">贵组织将启用 Microsoft Teams 的哪些设置？</span><span class="sxs-lookup"><span data-stu-id="32025-210">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![后续步骤图标。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="32025-212">后续步骤</span><span class="sxs-lookup"><span data-stu-id="32025-212">Next Steps</span></span>        |<span data-ttu-id="32025-213">使用[在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md)中的表格记录这些决定。</span><span class="sxs-lookup"><span data-stu-id="32025-213">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |

