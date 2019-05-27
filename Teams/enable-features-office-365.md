---
title: 为你的组织管理 Microsoft Teams 设置
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/18/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何为组织打开或关闭组织范围的 Microsoft Teams 设置，包括应用、外部访问权限、来宾访问权限、Teams 设置和 Teams 升级首选项。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69b23cefcfa6329e95e3413d720b3033250dd504
ms.sourcegitcommit: 349df7248c168e629bc1bb633187e39a37b17ba5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "34421992"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a><span data-ttu-id="640db-103">为你的组织管理 Microsoft Teams 设置</span><span class="sxs-lookup"><span data-stu-id="640db-103">Manage Microsoft Teams settings for your organization</span></span>

<span data-ttu-id="640db-p101">所有 Teams 设置将很快迁移到新的 Microsoft Teams 管理中心。在 Microsoft 365 管理中心进行管理的唯一 Teams 功能是“应用”。</span><span class="sxs-lookup"><span data-stu-id="640db-p101">All Teams settings will soon be migrated to the new Microsoft Teams admin center. The only Teams feature that's managed in the Microsoft 365 admin center is Apps.</span></span> 

<span data-ttu-id="640db-106">除非另有说明，否则选项的默认值为“**开启**”。</span><span class="sxs-lookup"><span data-stu-id="640db-106">Unless otherwise noted, the default value for an option is **On**.</span></span>

## <a name="tenant-wide-settings-in-the-microsoft-365-admin-center"></a><span data-ttu-id="640db-107">在 Microsoft 365 管理中心的租户范围设置</span><span class="sxs-lookup"><span data-stu-id="640db-107">Tenant-wide settings in the Microsoft 365 admin center</span></span>

<span data-ttu-id="640db-108">你可以在 Microsoft 365 管理中心的“**租户范围的设置**”中关闭或打开 Teams 的应用功能。</span><span class="sxs-lookup"><span data-stu-id="640db-108">You can turn off or turn on apps for Teams in **Tenant-wide settings** in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="640db-p102">要编辑 Teams 的**租户范围的设置**，请访问 Microsoft 365 管理中心，然后选择“**设置**” > “**服务和外接程序**” > “**Microsoft Teams**”。如果你已使用 Office 365 管理员身份登录，单击此链接应该能转到相应位置：</span><span class="sxs-lookup"><span data-stu-id="640db-p102">To edit **Tenant-wide settings** for Teams, go to the Microsoft 365 admin center, choose **Settings** > **Services & add-ins** > **Microsoft Teams**. If you're signed in as an Office 365 admin, this link should take you there:</span></span> 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a><span data-ttu-id="640db-111">应用</span><span class="sxs-lookup"><span data-stu-id="640db-111">Apps</span></span>

<span data-ttu-id="640db-p103">应用为选项卡、连接器、机器人或这三者的任意组合，它们由 Teams（第一方应用，亦称为默认应用）或第三方（亦称为外部应用）提供。在“应用”\*\*\*\* 下，可以启用和禁用默认应用，并配置用于控制外部应用的设置。若要详细了解如何在 Teams 中推出应用、机器人、连接器和选项卡，请参阅(应用、机器人和连接器)[deploy-apps-microsoft-teams-landing-page.md]。</span><span class="sxs-lookup"><span data-stu-id="640db-p103">Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, also known as default apps) or by a third-party (also known as external apps). Under **Apps**, you can enable and disable default apps and configure settings to control external apps. To learn about rolling out apps, bots, connectors, and tabs in Teams, read (Apps, bots, & connectors)[deploy-apps-microsoft-teams-landing-page.md].</span></span>

#### <a name="default-apps"></a><span data-ttu-id="640db-115">默认应用</span><span class="sxs-lookup"><span data-stu-id="640db-115">Default apps</span></span>

<span data-ttu-id="640db-116">这些应用（例如 Planner、Praise 和 Weather）由 Teams 提供。</span><span class="sxs-lookup"><span data-stu-id="640db-116">These apps, such as Planner, Praise, and Weather, are provided by Teams.</span></span> <span data-ttu-id="640db-117">要打开某个应用，请选中该应用对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="640db-117">To turn on an app, select the check box for that app.</span></span> <span data-ttu-id="640db-118">要关闭某个应用，请取消选中相应的复选框。</span><span class="sxs-lookup"><span data-stu-id="640db-118">To turn off an app, clear the check box.</span></span> 

<span data-ttu-id="640db-119">![“默认应用”部分屏幕截图。](media/teams-manage-features-in-office365-image1.png "“默认应用”部分屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="640db-119">![Screen shot of the Default Apps section.](media/teams-manage-features-in-office365-image1.png "Screen shot of the Default Apps section")</span></span>

#### <a name="external-apps"></a><span data-ttu-id="640db-120">外部应用</span><span class="sxs-lookup"><span data-stu-id="640db-120">External apps</span></span>

<span data-ttu-id="640db-121">这些应用由第三方提供。</span><span class="sxs-lookup"><span data-stu-id="640db-121">These apps are provided by third parties.</span></span> <span data-ttu-id="640db-122">你可以为外部应用配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="640db-122">You can configure the following settings for external apps.</span></span>

<span data-ttu-id="640db-123">![“外部应用”部分屏幕截图。](media/teams-manage-features-in-office365-image2.png "“外部应用”部分屏幕截图，显示了你可以打开和关闭的设置")</span><span class="sxs-lookup"><span data-stu-id="640db-123">![Screenshot of the External Apps section.](media/teams-manage-features-in-office365-image2.png "Screen shot of the External Apps section, showing settings that you can turn on and off")</span></span>

- <span data-ttu-id="640db-124">**在 Microsoft Teams 中允许外部应用**：打开此设置后，用户可以添加贵组织可用的外部应用。</span><span class="sxs-lookup"><span data-stu-id="640db-124">**Allow external apps in Microsoft Teams**: When this setting is turned on, users can add external apps that are available to your organization.</span></span> 

- <span data-ttu-id="640db-125">**允许外部应用的旁加载**：如果你希望打开一些外部应用并关闭其他外部应用，请关闭此设置，然后在外部应用列表中，关闭你不希望用户访问的应用。</span><span class="sxs-lookup"><span data-stu-id="640db-125">**Allow sideloading of external apps**: If you want to turn on some external apps and turn off others , turn off this setting, and then in the list of external apps, turn off the apps that you don't want users to access.</span></span> <span data-ttu-id="640db-126">打开此设置后，团队所有者和被授予权限的成员可以向 Teams 旁加载应用。</span><span class="sxs-lookup"><span data-stu-id="640db-126">When this setting is turned on, team owners and members who are granted permission can sideload apps to Teams.</span></span> 

- <span data-ttu-id="640db-127">**默认启用新的外部应用**：打开此设置后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。</span><span class="sxs-lookup"><span data-stu-id="640db-127">**Enable new external apps by default**: When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="640db-128">如果你希望控制新应用，请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="640db-128">Turn off this setting if you want to control new apps.</span></span> <span data-ttu-id="640db-129">当然，如果你关闭此设置，必须记得定期查看新应用，以免贵组织错过新应用。</span><span class="sxs-lookup"><span data-stu-id="640db-129">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on new apps.</span></span> 

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="640db-130">Microsoft Teams 管理中心中的 Teams 组织范围设置</span><span class="sxs-lookup"><span data-stu-id="640db-130">Teams org-wide settings in the Microsoft Teams admin center</span></span>
<span data-ttu-id="640db-p108">你可以在 Microsoft Teams 管理中心中控制组织范围内的用户设置。若要编辑组织范围内的设置，请转到 Microsoft Teams 管理中心，然后选择“**组织范围的设置**”。你可以配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="640db-p108">You can control organization-wide user settings in the Microsoft Teams admin center. To edit org-wide settings, go to the Microsoft Teams admin center, and then select **Org-wide settings**. You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="640db-134">外部访问</span><span class="sxs-lookup"><span data-stu-id="640db-134">External access</span></span>

<span data-ttu-id="640db-p109">利用**外部访问**功能，你的 Teams 和 Skype for Business 用户可以与贵组织外部的用户通信。要配置外部访问，请访问[让你的 Teams 用户与其他 Teams 组织中的用户聊天和通信](let-your-teams-users-communicate-with-other-people.md)。</span><span class="sxs-lookup"><span data-stu-id="640db-p109">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization. To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

<span data-ttu-id="640db-137">要添加或阻止某个域：</span><span class="sxs-lookup"><span data-stu-id="640db-137">To add or block a domain:</span></span>

1. <span data-ttu-id="640db-138">选择“**添加域**”。</span><span class="sxs-lookup"><span data-stu-id="640db-138">Select **Add a domain**.</span></span>
2. <span data-ttu-id="640db-139">在“添加域”窗格中，输入域名，然后单击空格键保存名称。</span><span class="sxs-lookup"><span data-stu-id="640db-139">In the Add a domain pane, enter the domain name, and click the space bar to save the name.</span></span>
3. <span data-ttu-id="640db-140">选择“**已允许**”或“**已阻止**”。</span><span class="sxs-lookup"><span data-stu-id="640db-140">Select **Allowed** or **Blocked**.</span></span>
4. <span data-ttu-id="640db-141">选择“**完成**”以保存更改。</span><span class="sxs-lookup"><span data-stu-id="640db-141">Select **Done** to save your changes.</span></span> 

### <a name="guest-access"></a><span data-ttu-id="640db-142">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="640db-142">Guest access</span></span>

<span data-ttu-id="640db-p110">利用 Microsoft Teams 中的**来宾访问**功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。具有企业或消费者电子邮件帐户（例如 Outlook、Gmail 或其他帐户）的任何人都能以访客身份参与 Teams，并对团队聊天、会议和文件具有完全访问权限。有关详细信息，请参阅 [Microsoft Teams 中的来宾访问](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="640db-p110">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="640db-146">Teams 设置</span><span class="sxs-lookup"><span data-stu-id="640db-146">Teams settings</span></span>

<span data-ttu-id="640db-147">在 **Teams 设置**中，你可以设置电子邮件集成、云存储选项、Skype for Business 互操作性和设备。</span><span class="sxs-lookup"><span data-stu-id="640db-147">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="640db-148">电子邮件集成</span><span class="sxs-lookup"><span data-stu-id="640db-148">Email integration</span></span>

<span data-ttu-id="640db-p111">开启此功能，以便用户可以使用频道电子邮件地址向 Teams 中的频道发送电子邮件。用户可以对属于其所属团队的任何频道执行此操作。用户还可以向为团队成员启用了添加连接器的团队中的任何频道发送电子邮件。要启用电子邮件集成，请确保“**允许用户向频道电子邮件地址发送电子邮件**”为“**打开**”</span><span class="sxs-lookup"><span data-stu-id="640db-p111">Turn on this feature so users can send email to a channel in Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors turned on for team members. To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="640db-153">文件</span><span class="sxs-lookup"><span data-stu-id="640db-153">Files</span></span>

<span data-ttu-id="640db-154">你可以在此处打开或关闭文件共享和云文件存储选项。</span><span class="sxs-lookup"><span data-stu-id="640db-154">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="640db-p112">用户可以在 Teams 频道和聊天中从云存储服务上载和共享文件。Teams 中的云存储选项当前包括 ShareFile、Dropbox、Box 和 Google Drive。可打开贵组织要使用的云存储提供商对应的开关。</span><span class="sxs-lookup"><span data-stu-id="640db-p112">Users can upload and share files from cloud storage services in Teams channels and chats. Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive. Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="640db-158">组织</span><span class="sxs-lookup"><span data-stu-id="640db-158">Organization</span></span>

<span data-ttu-id="640db-p113">你可以在此处打开“**组织**”选项卡，其中显示用户组织的详细组织结构图。有关详细信息，请参阅[在 Teams 中使用“组织”选项卡](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)。</span><span class="sxs-lookup"><span data-stu-id="640db-p113">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization. For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="devices"></a><span data-ttu-id="640db-161">设备</span><span class="sxs-lookup"><span data-stu-id="640db-161">Devices</span></span>

<span data-ttu-id="640db-p114">这些设置控制参加 Microsoft Teams 会议的 Surface Hub 设备的资源帐户行为。可使用这些设置来配置身份验证要求、要求提供内容 PIN 以及启用 Surface Hub 资源帐户以发送消息。</span><span class="sxs-lookup"><span data-stu-id="640db-p114">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings. Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="640db-164">**要求进行辅助形式的身份验证才能访问会议内容** - 选择用户输入内容 PIN 时拥有的访问级别。</span><span class="sxs-lookup"><span data-stu-id="640db-164">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="640db-p115">**设置内容 PIN** - 要求用户输入此 PIN 以防止未经授权访问文档。这可防止未经授权的用户加入即将召开的会议以及浏览附件。</span><span class="sxs-lookup"><span data-stu-id="640db-p115">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents. This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="640db-167">**资源帐户可以发送消息** - **启用**此设置将允许 Surface Hub 资源帐户发送消息。</span><span class="sxs-lookup"><span data-stu-id="640db-167">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search-by-name"></a><span data-ttu-id="640db-168">按名称搜索</span><span class="sxs-lookup"><span data-stu-id="640db-168">Search by name</span></span>

<span data-ttu-id="640db-p116">Microsoft Teams 范围目录搜索使用 Exchange 通讯簿策略 (APB) 允许组织创建虚拟边界，用于控制用户查找其组织中的其他用户以及与这些用户通信的方式。在某些情况下你可能想要使用范围目录搜索，例如：</span><span class="sxs-lookup"><span data-stu-id="640db-p116">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization. You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="640db-171">贵组织的租户中有多家你要保持独立的公司。</span><span class="sxs-lookup"><span data-stu-id="640db-171">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="640db-172">贵学校要限制教职员工与学生之间的聊天。</span><span class="sxs-lookup"><span data-stu-id="640db-172">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="640db-173">**启用**此设置将启用范围目录搜索。</span><span class="sxs-lookup"><span data-stu-id="640db-173">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="640db-174">Teams 升级</span><span class="sxs-lookup"><span data-stu-id="640db-174">Teams upgrade</span></span>

<span data-ttu-id="640db-175">你可以使用这些设置来配置你的用户从 Skype for Business 到 Microsoft Teams 的升级方式。</span><span class="sxs-lookup"><span data-stu-id="640db-175">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="640db-176">共存模式</span><span class="sxs-lookup"><span data-stu-id="640db-176">Coexistence mode</span></span>
<span data-ttu-id="640db-p117">你可以指定共存模式：“**仅 Teams**”、“**群岛**”（Teams 和 Skype for Business 将共存）或“**仅 Skype for Business**”。你选择的共存模式将决定传入呼叫和聊天的路由方式，以及用户用于启动聊天和通话或安排会议的应用。有关共存模式的详细信息，请访问[了解 Microsoft Teams 和 Skype for Business 的共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="640db-p117">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**. The Coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings. For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="640db-180">应用首选项</span><span class="sxs-lookup"><span data-stu-id="640db-180">App preferences</span></span>

<span data-ttu-id="640db-p118">你可以在此处选择用户加入 Skype for Business 会议时使用的应用（Skype for Business 或 [Skype Meetings 应用](https://support.office.com/zh-CN/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)）。此设置与共存模式设置无关。</span><span class="sxs-lookup"><span data-stu-id="640db-p118">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). This setting isn't dependent on the coexistence mode setting.</span></span>

## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="640db-183">如何了解提供了哪些功能？</span><span class="sxs-lookup"><span data-stu-id="640db-183">How can I tell which features are available?</span></span>

<span data-ttu-id="640db-p119">有关 Teams 新功能的信息，请参阅 [Microsoft 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)。有关新功能和即将推出的功能的详细信息，请参阅 Teams [新增功能](https://support.office.com/zh-CN/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)页面和适用于 Teams 的[技术社区 Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)。</span><span class="sxs-lookup"><span data-stu-id="640db-p119">See the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features. For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="640db-186">更多信息</span><span class="sxs-lookup"><span data-stu-id="640db-186">More information</span></span>

<span data-ttu-id="640db-187">有关可以执行管理员功能的角色的信息，请参阅[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="640db-187">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
