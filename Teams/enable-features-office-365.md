---
title: 管理 Office 365 组织中的 Microsoft 团队功能
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: 了解可以在你的 Office 365 组织中启用或禁用的所有 Microsoft Teams 功能，包括租户范围的设置、电子邮件集成、应用及云存储等。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50650d852e87cb885beae4403022464fafb57373
ms.sourcegitcommit: 8c3dcfc564c489f4d33bd5f391a5a66b99ded07e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "20265944"
---
<a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="ed4e4-103">管理 Office 365 组织中的 Microsoft 团队功能</span><span class="sxs-lookup"><span data-stu-id="ed4e4-103">Manage Microsoft Teams features in your Office 365 organization</span></span>
======================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ed4e4-104">Teams 可以在 Office 365 租户级别启用或关闭多项设置。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-104">Teams has multiple settings that can be turned on or turned off at the Office 365 tenant level.</span></span> <span data-ttu-id="ed4e4-105">与团队启用还启用团队的任何用户将继承从租户级别的设置。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-105">With Teams enabled, any user that is also enabled for Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="ed4e4-106">下面是 Office 365 管理员可以在 Teams 中启用或禁用的功能列表。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-106">Below is the list of features an Office 365 administrator can turn on or turn off in Teams.</span></span> 

<span data-ttu-id="ed4e4-107">除非另有说明，否则选项的默认值为“开启”。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-107">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="ed4e4-108">要管理 Teams 的管理员设置，请转到 Office 365 管理中心并打开“**设置**” > “**服务和外接程序**”，然后选择“**Microsoft Teams**”。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-108">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="ed4e4-109">如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作：</span><span class="sxs-lookup"><span data-stu-id="ed4e4-109">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

> [!IMPORTANT]
> <span data-ttu-id="ed4e4-110">Office 365 管理员可以随时通过 Office 365 管理中心关闭 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-110">An Office 365 admin can turn off Microsoft Teams at any time in the Office 365 admin center.</span></span> <span data-ttu-id="ed4e4-111">请注意，即使你关闭 Microsoft Teams，具有 Teams 有效许可证的用户也能继续看到 Teams 应用磁贴。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-111">Be aware that users with active Microsoft Teams licenses will continue to see the Teams app tile even if you turn off Teams.</span></span> <span data-ttu-id="ed4e4-112">有关如何从用户删除许可证的详细信息，请参阅[管理对 Microsoft Teams 许可证的用户访问](user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-112">For details about how to remove licenses from users, see [Manage user access to Microsoft Teams](user-access.md).</span></span> <span data-ttu-id="ed4e4-113">禁用 Teams 后，将阻止从 Teams 客户端进行访问，但仍可以通过其他客户端和服务获取数据，例如，通过 SharePoint 和 OneDrive 获取文件。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-113">After Teams is disabled, access from the Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive.</span></span> <span data-ttu-id="ed4e4-114">除非明确删除团队，否则所有数据保留在原处。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-114">All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="office-365-tenant-wide-settings"></a><span data-ttu-id="ed4e4-115">Office 365 租户范围的设置</span><span class="sxs-lookup"><span data-stu-id="ed4e4-115">Office 365 tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="ed4e4-116">在**租户范围的设置**中，你可以开启或关闭“常规”、“电子邮件集成”、“应用”和“自定义云存储”中的选项。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-116">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

<span data-ttu-id="ed4e4-117">要编辑 Teams 的**租户范围的设置**，请转到 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-117">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="ed4e4-118">选择 **“设置”** > **“服务和外接程序”** > **“Microsoft Teams”**。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-118">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

### <a name="general"></a><span data-ttu-id="ed4e4-119">常规</span><span class="sxs-lookup"><span data-stu-id="ed4e4-119">General</span></span>

<span data-ttu-id="ed4e4-120">在“常规”部分中可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="ed4e4-120">The General section lets you configure the following settings for your organization:</span></span>

> ![租户范围的设置中的“常规”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="ed4e4-122">**在个人资料中显示组织结构图：** 如果启用此设置，将在用户的联系人卡片中显示组织结构图图标，单击该图标后，将显示详细的组织结构图。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-122">**Show organizational chart in personal profile:** When this setting is turned on, it shows the organizational chart icon in the user’s contact card, and when clicked, it displays the detailed organizational chart.</span></span>

    ![用户的联系人卡片中的组织结构图图标屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![组织结构图屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-  <span data-ttu-id="ed4e4-125">**对没有 Teams 的收件人使用 Skype for Business：** 如果启用此设置，对于未启用 Teams 的用户，Teams 对话将自动显示在 Skype for Business 中。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-125">**Use Skype for Business for recipients who don’t have Teams:** When this setting is turned on, Teams conversations automatically show up in Skype for Business for users that aren't enabled for Teams.</span></span>  

-   <span data-ttu-id="ed4e4-126">**允许 T-Bot 主动发送帮助消息：** 如果启用此设置，T-Bot 将启动与用户的私人聊天会话以帮助他们使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-126">**Allow T-bot proactive help messages:** When this setting is turned on, T-bot will initiate a private chat session with users to help them use Teams.</span></span>

    ![Teams 界面中的“T-Bot”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="ed4e4-128">电子邮件集成</span><span class="sxs-lookup"><span data-stu-id="ed4e4-128">Email integration</span></span>
-----------------

<span data-ttu-id="ed4e4-129">开启此功能，以便用户可以使用频道电子邮件地址向 Teams 中的频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-129">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="ed4e4-130">用户可以对属于其所属团队的任何频道执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-130">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="ed4e4-131">用户还可以向为团队成员启用了添加连接器的团队中的任何频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-131">Users can also send emails to any channel in a team that has adding connectors enabled for team members.</span></span> <span data-ttu-id="ed4e4-132">并且，即使用户无权创建频道电子邮件地址，如果有权限的用户创建了该地址，则用户可以从该频道的“**更多选项**”菜单访问该地址。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-132">And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the **More options** menu for that channel.</span></span>

<span data-ttu-id="ed4e4-133">为贵组织配置以下“**电子邮件集成**”设置：</span><span class="sxs-lookup"><span data-stu-id="ed4e4-133">Configure the following **Email integration** settings for your organization:</span></span> 

   ![租户范围的设置中的“电子邮件集成”部分屏幕截图。](media/QS-edu-email-integration.png)


-   <span data-ttu-id="ed4e4-135">**允许用户向频道发送电子邮件：** 如果启用此设置，将启用邮件挂钩，用户可以通过向 Teams 频道的电子邮件地址发送电子邮件来向频道发布消息。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-135">**Allow users to send emails to channels:** When turned on, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Teams channel.</span></span> 

    <span data-ttu-id="ed4e4-136">要查找频道的电子邮件地址，请单击频道的“**更多选项**”菜单，然后选择“**获取电子邮件地址**”。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-136">To find the email address for a channel, click the **More options** menu for the channel and then select **Get email address**.</span></span> 

-   <span data-ttu-id="ed4e4-137">**受限制的发件人列表：** 可以对发件人域做进一步限制，以确保仅允许的 SMTP 域可以向 Teams 频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-137">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="ed4e4-138">应用</span><span class="sxs-lookup"><span data-stu-id="ed4e4-138">Apps</span></span>
----

<span data-ttu-id="ed4e4-139">应用是第三方服务提供的选项卡、连接器或聊天机器人或这三者的任意组合。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-139">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="ed4e4-140">可以在 Office 365 管理中心配置 Teams 管理策略来控制允许哪些外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-140">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="ed4e4-141">通过这些策略可以指定允许和不允许哪些应用、新的外部应用行为以及是否允许侧向加载应用。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-141">These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="ed4e4-142">在 **“应用”** 下，可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="ed4e4-142">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![“应用”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="ed4e4-144">**在 Microsoft Teams 中允许外部应用：** 如果打开此开关，用户可以添加可供 Office 365 租户使用的选项卡和聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-144">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![“应用”部分中的“允许外部应用”控件的屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="ed4e4-146">**默认启用新的外部应用：** 打开此开关后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-146">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="ed4e4-147">如果你希望控制新应用，请关闭此开关。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-147">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="ed4e4-148">当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-148">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="ed4e4-149">**允许侧向加载外部应用：** 如果打开此开关，用户可以安装和启用自定义聊天机器人和选项卡。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-149">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="ed4e4-150">要了解详细信息，请阅读 [Teams 中适用于应用的管理员设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-150">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 



<a name="custom-cloud-storage"></a><span data-ttu-id="ed4e4-151">自定义云存储</span><span class="sxs-lookup"><span data-stu-id="ed4e4-151">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="ed4e4-152">Teams 中的云存储选项当前包括 Box、Dropbox、Google Drive 和 ShareFile。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-152">Cloud storage options in Teams currently include Box, Dropbox, Google Drive, and ShareFile.</span></span> <span data-ttu-id="ed4e4-153">用户可以在 Teams 频道和聊天中从云存储服务上载和共享文件。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-153">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="ed4e4-154">可打开贵组织要使用的云存储提供商对应的开关。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-154">Turn on the switch for the cloud storage providers that your organization wants to use.</span></span> 

![“自定义云存储”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="settings-by-userlicense-type"></a><span data-ttu-id="ed4e4-156">设置用户/许可证类型</span><span class="sxs-lookup"><span data-stu-id="ed4e4-156">Settings by user/license type</span></span>
------------------------
<span data-ttu-id="ed4e4-157">设置时的 Microsoft 团队为您的组织最初，您可以使用**用户/许可证类型设置**下拉列表菜单选择许可证类型然后为该许可证类型的所有用户打开团队。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-157">When you set up Microsoft Teams for your organization initially, you used the the **Settings by user/license type** drop-down menu to select a license type and then turned Teams on for all users of that license type.</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

 <span data-ttu-id="ed4e4-158">用户/许可证类型的一些示例包括**企业**和**来宾**。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-158">Some examples of user/license types are **Business & Enterprise** and **Guest**.</span></span> <span data-ttu-id="ed4e4-159">（如果您具有教育版 SKU 许可证，**教育-教职员工**或**培训-学生**都可用。）![设置用户许可证的控件](media/enable-microsoft-teams-features-in-your-office-365-organization-image13.png)</span><span class="sxs-lookup"><span data-stu-id="ed4e4-159">(If you have an Education SKU license, **Education - Faculty and Staff** or **Education - Student** are available.)![Control for Set user license](media/enable-microsoft-teams-features-in-your-office-365-organization-image13.png)</span></span>

<span data-ttu-id="ed4e4-160">您具有多个许可证类型中您的组织，例如，同时**企业**和**来宾**。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-160">You can you have multiple license types within your organization, for example, both **Business & Enterprise** and **Guest**.</span></span> <span data-ttu-id="ed4e4-161">Microsoft 团队可以仅区分基于的许可证已分配给这些用户。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-161">Microsoft Teams can only differentiate users based on the licenses you've assigned them.</span></span> <span data-ttu-id="ed4e4-162">您可以打开或关闭**团队和频道**、**呼叫和会议**，以及**消息**中这些用户的选项。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-162">You can turn on or turn off options for these users in **Teams and channels**, **Calls and meetings**, and **Messaging**.</span></span> <span data-ttu-id="ed4e4-163">如果您使用只有一个许可证类型，请考虑为租户范围的设置的设置。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-163">If you use only one license type, consider the settings here as tenant-wide settings.</span></span>
> [!NOTE]
> <span data-ttu-id="ed4e4-164">有关来宾访问的详细信息，请参阅[打开或关闭向 Microsoft 工作组的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-164">For more details about guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="ed4e4-165">团队和频道</span><span class="sxs-lookup"><span data-stu-id="ed4e4-165">Teams and channels</span></span>
------------------

<span data-ttu-id="ed4e4-166">团队用于将一群人集中在一起，以便这些人密切合作来完成事情。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-166">A team is designed to bring together a group of people who work closely to get things done.</span></span> <span data-ttu-id="ed4e4-167">对于基于项目的工作（例如，使某个产品上市或创建数字化作战室），团队可以是动态的。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-167">Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room).</span></span> <span data-ttu-id="ed4e4-168">团队也可以是持续存在的，以反映贵组织的内部结构。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-168">Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="ed4e4-169">Office 365 租户可以拥有的最大团队数当前为 500,000。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-169">The maximum number of teams that an Office 365 tenant can have is currently 500,000.</span></span> <span data-ttu-id="ed4e4-170">全局管理员可以创建无限数量的团队。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-170">A global admin can create an unlimited number of teams.</span></span> <span data-ttu-id="ed4e4-171">用户可以创建 250 个团队。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-171">A user can create 250 teams.</span></span> <span data-ttu-id="ed4e4-172">团队所有者可以向团队添加 2500 个成员。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-172">A team owner can add 2500 members to a team.</span></span>

<span data-ttu-id="ed4e4-173">作为管理员，你可以通过使用 Office 365 管理中心中的“组”仪表板管理团队所有者和成员。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-173">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center.</span></span> <span data-ttu-id="ed4e4-174">要了解详细信息，请单击“**团队和频道**”下的“**使用 Office 365 管理中心中的‘组’仪表板管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-174">To learn more, click **Use the Groups dashboard in the Office 365 admin center to manage teams** under **Teams and channels**.</span></span>

<span data-ttu-id="ed4e4-175">你可以控制贵组织中哪些用户可以在 Teams 中创建团队。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-175">You can control which users in your organization can create teams in Teams.</span></span> <span data-ttu-id="ed4e4-176">Office 365 组定义的相同创建设置适用于 Teams。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-176">The same creation settings defined by Office 365 groups apply to Teams.</span></span> <span data-ttu-id="ed4e4-177">有关管理 Office 365 组的详细信息，请参阅[创建 Office 365 组](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f)和[控制哪些人可以创建 Office 365 组](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-177">For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

> [!NOTE]
> <span data-ttu-id="ed4e4-178">无法从“组”仪表板创建团队。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-178">You can't create teams from the Groups dashboard.</span></span> <span data-ttu-id="ed4e4-179">必须使用 Teams 桌面客户端或 Web 应用创建团队。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-179">Teams must be created by using the Teams desktop client or web app.</span></span>

<span data-ttu-id="ed4e4-180">默认情况下，所有用户都可以创建团队或组。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-180">By default, every user can create a team or group.</span></span> <span data-ttu-id="ed4e4-181">选择 Teams 客户端（桌面客户端或 Web 应用）中左侧的 **“团队”**，然后选择客户端底部的 **“创建并加入团队”**（在团队列表下方）。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-181">Choose **Teams** on the left side in the Teams client (desktop client or web app), then choose **Create and join team** at the bottom of the client, below the team list.</span></span>

![“按许可证的用户设置”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="ed4e4-183">频道是团队的子类别。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-183">Channels are subcategories of teams.</span></span> <span data-ttu-id="ed4e4-184">团队中的任何人都可以添加频道以及参与频道中的对话。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-184">Anyone on the team can add a channel and participate in the conversations in a channel.</span></span> <span data-ttu-id="ed4e4-185">你可为活动或部门创建频道。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-185">You might create a channel for an activity or for a department.</span></span> <span data-ttu-id="ed4e4-186">对话、文件和 Wiki 是特定于每个频道的，但团队的所有成员都可以查看它们。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-186">Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

## <a name="calls-and-meetings"></a><span data-ttu-id="ed4e4-187">通话和会议</span><span class="sxs-lookup"><span data-stu-id="ed4e4-187">Calls and meetings</span></span>

<span data-ttu-id="ed4e4-188">为贵组织配置以下“**通话和会议**”设置：</span><span class="sxs-lookup"><span data-stu-id="ed4e4-188">Configure the following **Calls and meetings** settings for your organization:</span></span>

![“通话和会议”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="ed4e4-190">会议中的最大人数是 80。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-190">The maximum number of people in a meeting is 80.</span></span> <span data-ttu-id="ed4e4-191">私人聊天中可以有 20 个成员，包括创建聊天的用户。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-191">There can be 20 members in a private chat, including the user who created the chat.</span></span>

-   <span data-ttu-id="ed4e4-192">**允许安排私人会议：** 如果启用此设置，用户可以安排不在任何频道中列出的私人会议。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-192">**Allow scheduling for private meetings**: When turned on, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="ed4e4-193">**允许临时频道聚会**：打开此功能后，用户可以快速为专为紧急或特定目的而创建的频道快速启动会议。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-193">**Allow ad-hoc channel meetup**: When turned on, users can quickly start a meeting for a channel that has been created for an immediate or specific purpose.</span></span>

-   <span data-ttu-id="ed4e4-194">**允许安排频道会议：** 如果启用此设置，用户可以为某个频道安排会议，所有频道成员只需单击一下即可轻松加入会议。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-194">**Allow scheduling for channel meetings**: When turned on, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="ed4e4-195">**在会议中允许视频：** 指定是否允许在会议中使用视频。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-195">**Allow videos in meetings:** Specifies whether the use of video is allowed in meetings.</span></span>

-   <span data-ttu-id="ed4e4-196">**允许在会议中共享屏幕：** 指定是否允许在会议中共享屏幕。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-196">**Allow screen sharing in meetings**: Specifies whether screen sharing is allowed in meetings.</span></span>

-   <span data-ttu-id="ed4e4-197">**允许专线通话：** 如果启用此设置，用户可以进行专线通话。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-197">**Allow private calling**: When turned on, users can make private calls.</span></span>

## <a name="messaging"></a><span data-ttu-id="ed4e4-198">消息</span><span class="sxs-lookup"><span data-stu-id="ed4e4-198">Messaging</span></span> 

<span data-ttu-id="ed4e4-199">在“消息”部分中可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="ed4e4-199">The Messaging section lets you configure the following settings for your organization:</span></span>

![“消息”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="ed4e4-201">**启用 Giphy 以便用户可以向对话添加 gif：** 如果启用此设置，用户可以在对话中使用动画图片。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-201">**Enable Giphy so users can add gifs to conversations**: When turned on, users can use animated pictures within the conversations.</span></span>

-   <span data-ttu-id="ed4e4-202">**内容分级：** 如果启用动画图片，可以应用内容分级来限制可以在对话中显示的动画图片的类型。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-202">**Content Rating**: When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations.</span></span> <span data-ttu-id="ed4e4-203">可用的内容分级选项如下：</span><span class="sxs-lookup"><span data-stu-id="ed4e4-203">Available content rating options are:</span></span>

    -   <span data-ttu-id="ed4e4-204">无限制</span><span class="sxs-lookup"><span data-stu-id="ed4e4-204">No restriction</span></span>
    -   <span data-ttu-id="ed4e4-205">适中（默认值）</span><span class="sxs-lookup"><span data-stu-id="ed4e4-205">Moderate (the default value)</span></span>
    -   <span data-ttu-id="ed4e4-206">严格</span><span class="sxs-lookup"><span data-stu-id="ed4e4-206">Strict</span></span>

-   <span data-ttu-id="ed4e4-207">**启用用户可以编辑和添加到对话的 Meme：** 如果启用此设置，用户可以使用 Internet Meme 制作幽默的帖子。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-207">**Enable memes that users can edit and add to conversations**: When turned on, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="ed4e4-208">**启用用户可以编辑和添加到对话的表情图片：** 如果启用此设置，用户可以发布包含可编辑文字的图片以引起频道成员的注意。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-208">**Enable stickers that users can edit and add to conversations**: When turned on, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="ed4e4-209">**允许所有者删除所有消息：** 如果启用此设置，频道所有者可以删除频道中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-209">**Allow owners to delete all messages**: When turned on, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="ed4e4-210">**允许用户编辑自己的消息：** 如果启用此设置，用户可以编辑自己的消息。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-210">**Allow users to edit their own messages**: When turned on, users can edit their own messages.</span></span>

-   <span data-ttu-id="ed4e4-211">**允许用户删除自己的消息：** 如果启用此设置，用户可以删除自己的消息。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-211">**Allow users to delete their own messages**: When turned on, users can delete their own messages.</span></span>

-   <span data-ttu-id="ed4e4-212">**允许用户私人聊天：** 如果启用此设置，用户可以参与仅聊天中的人员（而非团队中的所有人）可见的私人聊天。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-212">**Allow users to chat privately**: When turned on, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>


| |  |  |
|---------|---------|---------|
|![决策点图标。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="ed4e4-214">决策点</span><span class="sxs-lookup"><span data-stu-id="ed4e4-214">Decision Point</span></span>         |<span data-ttu-id="ed4e4-215">贵组织将启用 Microsoft Teams 的哪些设置？</span><span class="sxs-lookup"><span data-stu-id="ed4e4-215">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![后续步骤图标。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="ed4e4-217">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ed4e4-217">Next Steps</span></span>        |<span data-ttu-id="ed4e4-218">使用[在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md)中的表格记录这些决定。</span><span class="sxs-lookup"><span data-stu-id="ed4e4-218">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |

