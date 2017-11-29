---
title: "在你的 Office 365 组织中启用 Microsoft Teams 功能 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解可以在你的 Office 365 组织中启用的所有 Microsoft Teams 功能，包括租户范围的设置、电子邮件集成、应用及云存储等。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e2235756e77c3e27c1eeee9fd22decb5e0e4e062
ms.sourcegitcommit: db47b9f4955150859bc35ab9d078fa3ab66b5faa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2017
---
<a name="enable-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="232e9-103">在你的 Office 365 组织中启用 Microsoft Teams 功能</span><span class="sxs-lookup"><span data-stu-id="232e9-103">Enable Microsoft Teams features in your Office 365 organization</span></span>
======================================================

<span data-ttu-id="232e9-104">Microsoft Teams 具有多个可以在租户级别启用或禁用的设置。</span><span class="sxs-lookup"><span data-stu-id="232e9-104">Microsoft Teams has multiple settings that can be enabled or disabled at the tenant level.</span></span> <span data-ttu-id="232e9-105">如果为租户启用了 Teams，同样启用了 Teams 的任何用户都将从租户级别继承设置。</span><span class="sxs-lookup"><span data-stu-id="232e9-105">With Teams enabled for the tenant, any user that is also enabled for Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="232e9-106">下面是 Office 365 管理员可以选择在 Teams 中启用或禁用的功能列表。</span><span class="sxs-lookup"><span data-stu-id="232e9-106">Below is the list of features an Office 365 administrator can choose to enable or disable in Teams.</span></span>

<span data-ttu-id="232e9-107">除非另有说明，否则选项的默认值为“开启”。</span><span class="sxs-lookup"><span data-stu-id="232e9-107">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE]
> <span data-ttu-id="232e9-108">Office 365 管理员可以随时通过 Office 365 管理中心关闭 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="232e9-108">An Office 365 admin can turn off Microsoft Teams at any time in the Office 365 Admin center.</span></span> <span data-ttu-id="232e9-109">请注意，即使你关闭 Microsoft Teams，具有 Teams 有效许可证的用户也能继续看到 Teams 应用磁贴。</span><span class="sxs-lookup"><span data-stu-id="232e9-109">Be aware that users with active Microsoft Teams licenses will continue to see the Teams app tile even if you turn off Teams.</span></span> <span data-ttu-id="232e9-110">有关如何从用户删除许可证的详细信息，请参阅[管理对 Microsoft Teams 许可证的用户访问](user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="232e9-110">For details about how to remove licenses from users, see [Manage user access to Microsoft Teams](user-access.md).</span></span> <span data-ttu-id="232e9-111">禁用 Teams 后，将阻止从 Teams 客户端进行访问，但仍可以通过其他客户端和服务获取数据，例如，通过 SharePoint 和 OneDrive 获取文件。</span><span class="sxs-lookup"><span data-stu-id="232e9-111">After Teams is disabled, access from the Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive.</span></span> <span data-ttu-id="232e9-112">除非明确删除团队，否则所有数据保留在原处。</span><span class="sxs-lookup"><span data-stu-id="232e9-112">All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="tenant-wide-settings"></a><span data-ttu-id="232e9-113">租户范围的设置</span><span class="sxs-lookup"><span data-stu-id="232e9-113">Tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="232e9-114">在**租户范围的设置**中，你可以开启或关闭“常规”、“电子邮件集成”、“应用”和“自定义云存储”中的选项。</span><span class="sxs-lookup"><span data-stu-id="232e9-114">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

### <a name="general"></a><span data-ttu-id="232e9-115">常规</span><span class="sxs-lookup"><span data-stu-id="232e9-115">General</span></span>

<span data-ttu-id="232e9-116">在“常规”部分中可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="232e9-116">The General section lets you configure the following settings for your organization:</span></span>

> ![租户范围的设置中的“常规”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="232e9-118">**在个人资料中显示组织结构图：** 如果启用此设置，将在用户的联系人卡片中显示组织结构图图标，单击该图标时，将显示详细的组织结构图。</span><span class="sxs-lookup"><span data-stu-id="232e9-118">**Show organizational chart in personal profile:** When this setting is enabled, it shows the organizational chart icon in the user’s contact card and when clicked, it displays the detailed organizational chart.</span></span>

    ![用户的联系人卡片中的组织结构图图标屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![组织结构图屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   <span data-ttu-id="232e9-121">**对没有 Microsoft Teams 的收件人使用 Skype for Business：** 如果启用此设置，将允许 Microsoft Teams 用户通过 Skype for Business 联系组织中未启用 Microsoft Teams 的其他用户。</span><span class="sxs-lookup"><span data-stu-id="232e9-121">**Use Skype for Business for recipients who don’t have Microsoft Teams:** When this setting is enabled, it allows Microsoft Teams users to contact other users in the organization that are not enabled for Microsoft Teams via Skype for Business.</span></span>

-   <span data-ttu-id="232e9-122">**允许 T-Bot 主动帮助消息：** 如果启用此设置，T-Bot 将启动与用户的私人聊天会话以指导他们使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="232e9-122">**Allow T-bot proactive help messages:** When this setting is enabled, T-bot will initiate a private chat session with users to guide them in using Microsoft Teams.</span></span>

    ![Microsoft Teams 界面中的“T-Bot”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="232e9-124">电子邮件集成</span><span class="sxs-lookup"><span data-stu-id="232e9-124">Email integration</span></span>
-----------------

<span data-ttu-id="232e9-125">开启此功能，以便用户可以使用频道电子邮件地址向 Microsoft Teams 中的频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="232e9-125">Turn this feature on so that users can send an email to a channel in Microsoft Teams, using the channel email address.</span></span> <span data-ttu-id="232e9-126">用户可以对属于其所属团队的任何频道执行此操作。</span><span class="sxs-lookup"><span data-stu-id="232e9-126">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="232e9-127">用户还可以向为团队成员启用了添加连接器的团队中的任何频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="232e9-127">Users can also send emails to any channel in a team that has adding connectors enabled for team members.</span></span> <span data-ttu-id="232e9-128">并且，即使用户无权创建频道电子邮件地址，如果有权限的用户创建了该地址，则用户可以从该频道的\<更多图标\>菜单访问该地址。</span><span class="sxs-lookup"><span data-stu-id="232e9-128">And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the \<more icon\> menu for that channel.</span></span>

<span data-ttu-id="232e9-129">在“电子邮件集成”部分中可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="232e9-129">The Email integration section lets you configure the following settings for your organization:</span></span>

   ![租户范围的设置中的“电子邮件集成”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image5.png)

-   <span data-ttu-id="232e9-131">**允许用户向频道发送电子邮件：** 如果启用此设置，将启用邮件挂钩，用户可以通过向 Microsoft Teams 频道的电子邮件地址发送电子邮件来向频道发布消息。</span><span class="sxs-lookup"><span data-stu-id="232e9-131">**Allow users to send emails to channels:** When enabled, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Microsoft Teams channel.</span></span>

> <span data-ttu-id="232e9-132">要查找频道的电子邮件地址，请单击频道名称旁边的**“更多选项”**，然后选择**“获取电子邮件地址”**。</span><span class="sxs-lookup"><span data-stu-id="232e9-132">To find the channel’s e-mail address, click **More options** next to the channel name and then select **Get email address**.</span></span>

-   <span data-ttu-id="232e9-133">**受限制的发件人列表：** 可以对发件人域做进一步限制，以确保仅允许的 SMTP 域可以向 Microsoft Teams 频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="232e9-133">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Microsoft Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="232e9-134">应用</span><span class="sxs-lookup"><span data-stu-id="232e9-134">Apps</span></span>
----

<span data-ttu-id="232e9-135">Microsoft Teams 中的应用是将你的团队关注的工具和服务正确集成到任何频道或聊天中的绝佳方式。</span><span class="sxs-lookup"><span data-stu-id="232e9-135">Apps in Microsoft Teams are a terrific way to integrate the tools and services your team cares about, right into any channel or chat.</span></span>

<span data-ttu-id="232e9-136">在**“应用”**部分中可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="232e9-136">The **Apps** section lets you configure the following settings for your organization:</span></span>

![“应用”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   <span data-ttu-id="232e9-138">**在 Microsoft Teams 中允许外部应用：** 如果启用此设置，用户可以添加可供 Office 365 租户使用的选项卡和聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="232e9-138">**Allow external apps in Microsoft Teams:** When enabled, users can add tabs and bots that are available to the Office 365 tenant.</span></span>
<span data-ttu-id="232e9-139">![“应用”部分中的允许外部应用控制屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)</span><span class="sxs-lookup"><span data-stu-id="232e9-139">![Screenshot of the Allow external apps control in the Apps section.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)</span></span>

-   <span data-ttu-id="232e9-140">**允许侧向加载外部应用：** 如果启用此设置，用户可以安装和启用自定义聊天机器人和选项卡。</span><span class="sxs-lookup"><span data-stu-id="232e9-140">**Allow sideloading of external apps:** When enabled, users can install and enable custom bots and tabs.</span></span>

<a name="custom-cloud-storage"></a><span data-ttu-id="232e9-141">自定义云存储</span><span class="sxs-lookup"><span data-stu-id="232e9-141">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="232e9-142">Microsoft Teams 中的云存储选项当前包括 Box、Dropbox、Google Drive 和 ShareFile。</span><span class="sxs-lookup"><span data-stu-id="232e9-142">Cloud storage options in Microsoft Teams currently include Box, Dropbox, Google Drive, and ShareFile.</span></span> <span data-ttu-id="232e9-143">用户可以在 Microsoft Teams 频道和聊天中从云存储服务上载和共享文件。</span><span class="sxs-lookup"><span data-stu-id="232e9-143">Users can upload and share files from cloud storage services in Microsoft Teams channels and chats.</span></span> <span data-ttu-id="232e9-144">可单击或点击贵组织要使用的云存储提供程序旁边的切换开关。</span><span class="sxs-lookup"><span data-stu-id="232e9-144">Click or tap the toggle switch next to the cloud storage providers that your organization wants to use.</span></span>

![“自定义云存储”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a><span data-ttu-id="232e9-146">按许可证的用户设置</span><span class="sxs-lookup"><span data-stu-id="232e9-146">User settings by license</span></span>
------------------------

<span data-ttu-id="232e9-147">在**“按许可证的用户设置”**中，可以开启或关闭“团队和频道”、“通话和会议”以及“消息”中的选项。</span><span class="sxs-lookup"><span data-stu-id="232e9-147">In **User settings by license**, you can turn on or turn off options in Teams and channels, Calls and meetings, and Messaging.</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="232e9-148">团队和频道</span><span class="sxs-lookup"><span data-stu-id="232e9-148">Teams and channels</span></span>
------------------

<span data-ttu-id="232e9-149">团队用于将一群人集中在一起，以便这些人密切合作来完成事情。</span><span class="sxs-lookup"><span data-stu-id="232e9-149">A team is designed to bring together a group of people who work closely to get things done.</span></span> <span data-ttu-id="232e9-150">对于基于项目的工作（例如，使某个产品上市或创建数字化作战室），团队可以是动态的。</span><span class="sxs-lookup"><span data-stu-id="232e9-150">Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room).</span></span> <span data-ttu-id="232e9-151">团队也可以是持续存在的，以反映贵组织的内部结构。</span><span class="sxs-lookup"><span data-stu-id="232e9-151">Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="232e9-152">作为管理员，你可以通过使用 Office 365 管理中心门户中的“组”仪表板管理团队所有者和成员。</span><span class="sxs-lookup"><span data-stu-id="232e9-152">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center portal.</span></span> <span data-ttu-id="232e9-153">在“团队和频道”部分中，单击**使用 Office 365 管理中心中的“组”仪表板管理团队**链接。</span><span class="sxs-lookup"><span data-stu-id="232e9-153">In the Teams and channels section, click the link for **Use the Groups dashboard in the Office 365 admin center to manage teams**.</span></span>

<span data-ttu-id="232e9-154">你可以控制贵组织中哪些用户可以在 Microsoft Teams 中创建团队。</span><span class="sxs-lookup"><span data-stu-id="232e9-154">You can control which users in your organization can create teams in Microsoft Teams.</span></span> <span data-ttu-id="232e9-155">Office 365 组定义的相同创建设置适用于 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="232e9-155">The same creation settings defined by Office 365 groups apply to Microsoft Teams.</span></span> <span data-ttu-id="232e9-156">有关管理 Office 365 组的详细信息，请参阅[创建 Office 365 组](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f)和[控制哪些人可以创建 Office 365 组](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="232e9-156">For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

<span data-ttu-id="232e9-157">注意：无法从“组”仪表板创建团队。</span><span class="sxs-lookup"><span data-stu-id="232e9-157">NOTE: You can't create teams from the Groups dashboard.</span></span> <span data-ttu-id="232e9-158">必须使用 Microsoft Teams 桌面客户端或 Web 应用创建团队。</span><span class="sxs-lookup"><span data-stu-id="232e9-158">Teams must be created by using the Microsoft Teams desktop client or web app.</span></span>

<span data-ttu-id="232e9-159">默认情况下，所有用户都可以创建团队或组。</span><span class="sxs-lookup"><span data-stu-id="232e9-159">By default, every user can create a team or group.</span></span> <span data-ttu-id="232e9-160">用户可以选择 Microsoft Teams 客户端（桌面客户端或 Web 应用）中左侧的“团队”，然后选择客户端底部的“创建团队”（在团队列表下方），来创建团队。</span><span class="sxs-lookup"><span data-stu-id="232e9-160">Users can create teams by choosing Teams on the left side in the Microsoft Teams client (desktop client or web app), and then choosing Create team at the bottom of the client, below the team list.</span></span>

<span data-ttu-id="232e9-161">Office 365 租户可以包含的默认最大团队数当前为 500,000。</span><span class="sxs-lookup"><span data-stu-id="232e9-161">The default maximum number of teams that an Office 365 tenant can have is currently 500,000.</span></span> <span data-ttu-id="232e9-162">全局管理员可以创建无限数量的团队。</span><span class="sxs-lookup"><span data-stu-id="232e9-162">A global admin can create an unlimited number of teams.</span></span> <span data-ttu-id="232e9-163">用户可以创建 250 个团队。</span><span class="sxs-lookup"><span data-stu-id="232e9-163">A user can create 250 teams.</span></span> <span data-ttu-id="232e9-164">团队所有者可以向团队添加 2500 个成员。</span><span class="sxs-lookup"><span data-stu-id="232e9-164">A team owner can add 2500 members to a team.</span></span>

![“按许可证的用户设置”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="232e9-166">频道是团队的子类别。</span><span class="sxs-lookup"><span data-stu-id="232e9-166">Channels are subcategories of teams.</span></span> <span data-ttu-id="232e9-167">团队中的任何人都可以添加频道以及参与频道中的对话。</span><span class="sxs-lookup"><span data-stu-id="232e9-167">Anyone on the team can add a channel and participate in the conversations in a channel.</span></span> <span data-ttu-id="232e9-168">你可为活动或部门创建频道。</span><span class="sxs-lookup"><span data-stu-id="232e9-168">You might create a channel for an activity or for a department.</span></span> <span data-ttu-id="232e9-169">对话、文件和 Wiki 是特定于每个频道的，但团队的所有成员都可以查看它们。</span><span class="sxs-lookup"><span data-stu-id="232e9-169">Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

### <a name="calls-and-meetings"></a><span data-ttu-id="232e9-170">通话和会议</span><span class="sxs-lookup"><span data-stu-id="232e9-170">Calls and meetings</span></span>

<span data-ttu-id="232e9-171">在**“通话和会议”**部分中可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="232e9-171">The **Calls and meetings** section lets you configure the following settings for your organization:</span></span>

> ![“通话和会议”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   <span data-ttu-id="232e9-173">**允许安排私人会议：** 如果启用此设置，用户可以安排不在任何频道中列出的私人会议。</span><span class="sxs-lookup"><span data-stu-id="232e9-173">**Allow scheduling for private meetings:** When enabled, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="232e9-174">**允许临时频道聚会：**</span><span class="sxs-lookup"><span data-stu-id="232e9-174">**Allow ad-hoc channel meetup:**</span></span>

-   <span data-ttu-id="232e9-175">**允许安排频道会议：** 如果启用此设置，用户可以为某个频道安排会议，所有频道成员只需单击一下即可轻松加入会议。</span><span class="sxs-lookup"><span data-stu-id="232e9-175">**Allow scheduling for channel meetings:** When enabled, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="232e9-176">**在会议中允许视频：** 指定是否允许在会议中使用视频。</span><span class="sxs-lookup"><span data-stu-id="232e9-176">**Allow videos in meetings:** Specifies whether the use of video is allowed within the meetings.</span></span>

-   <span data-ttu-id="232e9-177">**允许在会议中共享屏幕：** 指定是否允许在会议中共享屏幕。</span><span class="sxs-lookup"><span data-stu-id="232e9-177">**Allow screen sharing in meetings:** Specifies whether screen sharing is allowed within the meetings.</span></span>

-   <span data-ttu-id="232e9-178">**允许专线通话：** 如果启用此设置，用户可以进行专线通话。</span><span class="sxs-lookup"><span data-stu-id="232e9-178">**Allow private calling:** When enabled, users can make private calls.</span></span>

<span data-ttu-id="232e9-179">会议中的最大人数是 80。</span><span class="sxs-lookup"><span data-stu-id="232e9-179">The maximum number of people in a meeting is 80.</span></span> <span data-ttu-id="232e9-180">私人聊天中可以有 20 个成员，包括创建聊天的用户。</span><span class="sxs-lookup"><span data-stu-id="232e9-180">There can be 20 members in a private chat, including the user who created the chat.</span></span>

### <a name="messaging"></a><span data-ttu-id="232e9-181">消息</span><span class="sxs-lookup"><span data-stu-id="232e9-181">Messaging</span></span> 

<span data-ttu-id="232e9-182">在“消息”部分中可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="232e9-182">The Messaging section lets you configure the following settings for your organization:</span></span>

![“消息”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="232e9-184">**启用 Giphy 以便用户可以向对话添加 gif：** 如果启用此设置，用户可以在对话中使用动画图片。</span><span class="sxs-lookup"><span data-stu-id="232e9-184">**Enable Giphy so users can add gifs to conversations:** When enabled, users can use animated pictures within the conversations.</span></span>

    -   <span data-ttu-id="232e9-185">**内容分级：** 如果启用动画图片，可以应用内容分级来限制可以在对话中显示的动画图片的类型。</span><span class="sxs-lookup"><span data-stu-id="232e9-185">**Content Rating:** When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations.</span></span> <span data-ttu-id="232e9-186">可用的内容分级选项如下：</span><span class="sxs-lookup"><span data-stu-id="232e9-186">Available content rating options are:</span></span>

        -   <span data-ttu-id="232e9-187">无限制</span><span class="sxs-lookup"><span data-stu-id="232e9-187">No restriction</span></span>

        -   <span data-ttu-id="232e9-188">适中（默认值）</span><span class="sxs-lookup"><span data-stu-id="232e9-188">Moderate (the default value)</span></span>

        -   <span data-ttu-id="232e9-189">严格</span><span class="sxs-lookup"><span data-stu-id="232e9-189">Strict</span></span>

-   <span data-ttu-id="232e9-190">**启用用户可以编辑和添加到对话的 Meme：** 如果启用此设置，用户可以使用 Internet Meme 制作幽默的帖子。</span><span class="sxs-lookup"><span data-stu-id="232e9-190">**Enable memes that users can edit and add to conversations:** When enabled, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="232e9-191">**启用用户可以编辑和添加到对话的表情图片：** 如果启用此设置，用户可以发布包含可编辑文字的图片以引起频道成员的注意。</span><span class="sxs-lookup"><span data-stu-id="232e9-191">**Enable stickers that users can edit and add to conversations:** When enabled, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="232e9-192">**允许所有者删除所有消息：** 如果启用此设置，频道所有者可以删除频道中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="232e9-192">**Allow owners to delete all messages:** When enabled, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="232e9-193">**允许用户编辑自己的消息：** 如果启用此设置，用户可以编辑自己的消息。</span><span class="sxs-lookup"><span data-stu-id="232e9-193">**Allow users to edit their own messages:** When enabled, users can edit their own messages.</span></span>

-   <span data-ttu-id="232e9-194">**允许用户删除自己的消息：** 如果启用此设置，用户可以删除自己的消息。</span><span class="sxs-lookup"><span data-stu-id="232e9-194">**Allow users to delete their own messages:** When enabled, users can delete their own messages.</span></span>

-   <span data-ttu-id="232e9-195">**允许用户私人聊天：** 如果启用此设置，用户可以参与仅聊天中的人员（而非团队中的所有人）可见的私人聊天。</span><span class="sxs-lookup"><span data-stu-id="232e9-195">**Allow users to chat privately:** When enabled, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>


| |  |  |
|---------|---------|---------|
|![决策点图标。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="232e9-197">决策点</span><span class="sxs-lookup"><span data-stu-id="232e9-197">Decision Point</span></span>         |<span data-ttu-id="232e9-198">贵组织将启用 Microsoft Teams 的哪些设置？</span><span class="sxs-lookup"><span data-stu-id="232e9-198">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![后续步骤图标。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="232e9-200">后续步骤</span><span class="sxs-lookup"><span data-stu-id="232e9-200">Next Steps</span></span>        |<span data-ttu-id="232e9-201">使用[在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md)中的表格记录这些决定。</span><span class="sxs-lookup"><span data-stu-id="232e9-201">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |

