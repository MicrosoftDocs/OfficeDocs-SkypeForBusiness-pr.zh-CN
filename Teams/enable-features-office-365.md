---
title: 管理 Office 365 组织中的 Microsoft 团队功能
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何启用或禁用 Office 365 组织，包括选项卡、 连接器、 自动程序或这三个任意组合中的 Microsoft 团队应用程序。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7411494c3baa56c1761ee3bcd69c2d49fdd4a961
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533164"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="26465-103">管理 Office 365 组织中的 Microsoft 团队功能</span><span class="sxs-lookup"><span data-stu-id="26465-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

<span data-ttu-id="26465-104">所有团队设置很快将都迁移到新的 Microsoft 团队和 Skype 的业务 Admin Center。</span><span class="sxs-lookup"><span data-stu-id="26465-104">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="26465-105">在 Office 365 管理中心中托管的唯一团队功能是应用程序。</span><span class="sxs-lookup"><span data-stu-id="26465-105">The only Teams feature that is managed in the Office 365 admin center is Apps.</span></span> 

<span data-ttu-id="26465-106">除非另行说明，否则选项的默认值是**在上**。</span><span class="sxs-lookup"><span data-stu-id="26465-106">Unless otherwise noted, the default value for an option is **On**.</span></span>

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="26465-107">Office 365 租户范围的设置</span><span class="sxs-lookup"><span data-stu-id="26465-107">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="26465-108">在**租户范围的设置**，可以打开或关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="26465-108">In **Tenant-wide settings**, you can turn on or turn off Apps.</span></span>

<span data-ttu-id="26465-109">编辑团队**租户范围的设置**，请转到 Microsoft 团队和 Skype 的业务管理中心中，并选择**旧门户**。</span><span class="sxs-lookup"><span data-stu-id="26465-109">To edit **Tenant-wide settings** for Teams, go to the Microsoft Teams & Skype for Business Admin Center, and select **Legacy portal**.</span></span> <span data-ttu-id="26465-110">选择 **“设置”** > **“服务和外接程序”** > **“Microsoft Teams”**。</span><span class="sxs-lookup"><span data-stu-id="26465-110">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="26465-111">如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作：</span><span class="sxs-lookup"><span data-stu-id="26465-111">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a><span data-ttu-id="26465-112">应用</span><span class="sxs-lookup"><span data-stu-id="26465-112">Apps</span></span>

<span data-ttu-id="26465-113">应用是第三方服务提供的选项卡、连接器或聊天机器人或这三者的任意组合。</span><span class="sxs-lookup"><span data-stu-id="26465-113">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="26465-114">可以在 Office 365 管理中心配置 Teams 管理策略来控制允许哪些外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="26465-114">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="26465-115">这些策略允许您指定的应用程序允许的和不允许，新的外部应用程序行为，以及是否允许端加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="26465-115">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="26465-116">在 **“应用”** 下，可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="26465-116">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![“应用”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="26465-118">**在 Microsoft Teams 中允许外部应用：** 如果打开此开关，用户可以添加可供 Office 365 租户使用的选项卡和聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="26465-118">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![“应用”部分中的“允许外部应用”控件的屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="26465-120">**默认启用新的外部应用：** 打开此开关后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。</span><span class="sxs-lookup"><span data-stu-id="26465-120">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="26465-121">如果你希望控制新应用，请关闭此开关。</span><span class="sxs-lookup"><span data-stu-id="26465-121">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="26465-122">当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。</span><span class="sxs-lookup"><span data-stu-id="26465-122">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="26465-123">**允许 sideloading 的外部应用程序**： 启用此开关后，用户可以安装和启用自定义自动程序和选项卡。</span><span class="sxs-lookup"><span data-stu-id="26465-123">**Allow sideloading of external apps**: When this switch is turned on, users can install and turn on custom bots and tabs.</span></span> 

<span data-ttu-id="26465-124">要了解详细信息，请阅读 [Teams 中适用于应用的管理员设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="26465-124">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

## <a name="teams-org-wide-settings"></a><span data-ttu-id="26465-125">团队组织范围的设置</span><span class="sxs-lookup"><span data-stu-id="26465-125">Teams org-wide settings</span></span>

<span data-ttu-id="26465-126">您可以控制组织范围内用户设置中的 Microsoft 团队业务管理中心的 Skype。</span><span class="sxs-lookup"><span data-stu-id="26465-126">You can control organization-wide user settings in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="26465-127">若要编辑组织范围的设置，请转到的业务管理中心中，Microsoft Skype，然后选择**组织范围的设置**。</span><span class="sxs-lookup"><span data-stu-id="26465-127">To edit org-wide settings, go to the Microsoft Skype for Business Admin Center, and then select **Org-wide settings**.</span></span> <span data-ttu-id="26465-128">您可以配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="26465-128">You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="26465-129">外部访问</span><span class="sxs-lookup"><span data-stu-id="26465-129">External access</span></span>

<span data-ttu-id="26465-130">**外部访问**允许您的团队和 Skype 业务用户与组织外部的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="26465-130">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization.</span></span> <span data-ttu-id="26465-131">若要配置外部访问，请转到[让您的团队用户聊天并与其他团队组织中的用户进行通信](let-your-teams-users-communicate-with-other-people.md)。</span><span class="sxs-lookup"><span data-stu-id="26465-131">To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

### <a name="guest-access"></a><span data-ttu-id="26465-132">来宾访问</span><span class="sxs-lookup"><span data-stu-id="26465-132">Guest access</span></span>

<span data-ttu-id="26465-133">**来宾访问**中的 Microsoft 团队允许在与组织外部的人员协作通过授予其访问权限的团队和频道贵组织中的团队。</span><span class="sxs-lookup"><span data-stu-id="26465-133">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="26465-134">具有业务或使用者的电子邮件帐户，如 Outlook、 Gmail，或其他任何人都可以参与作为来宾团队中具有到团队聊天、 会议和文件的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="26465-134">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="26465-135">有关详细信息，请参阅[中的 Microsoft 团队的来宾访问](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="26465-135">For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="26465-136">团队设置</span><span class="sxs-lookup"><span data-stu-id="26465-136">Teams settings</span></span>

<span data-ttu-id="26465-137">在**工作组设置**，您可以设置电子邮件集成，云存储选项 Skype 业务互操作性和设备。</span><span class="sxs-lookup"><span data-stu-id="26465-137">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="26465-138">电子邮件集成</span><span class="sxs-lookup"><span data-stu-id="26465-138">Email integration</span></span>

<span data-ttu-id="26465-139">开启此功能，以便用户可以使用频道电子邮件地址向 Teams 中的频道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="26465-139">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="26465-140">用户可以对属于其所属团队的任何频道执行此操作。</span><span class="sxs-lookup"><span data-stu-id="26465-140">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="26465-141">用户还可以向任何已添加为工作组成员开启连接器团队中的通道发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="26465-141">Users can also send emails to any channel in a team that has adding connectors turned on for team members.</span></span> <span data-ttu-id="26465-142">若要启用电子邮件集成，请确保**允许用户发送到通道电子邮件地址的电子邮件\*\*\*\*上**。</span><span class="sxs-lookup"><span data-stu-id="26465-142">To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="26465-143">文件</span><span class="sxs-lookup"><span data-stu-id="26465-143">Files</span></span>

<span data-ttu-id="26465-144">此处可以在打开或关闭文件共享和云文件存储选项。</span><span class="sxs-lookup"><span data-stu-id="26465-144">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="26465-145">用户可以在 Teams 频道和聊天中从云存储服务上载和共享文件。</span><span class="sxs-lookup"><span data-stu-id="26465-145">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="26465-146">当前，团队中的云存储选项包括 ShareFile、 收存箱、 框中，和 Google 驱动器。</span><span class="sxs-lookup"><span data-stu-id="26465-146">Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive.</span></span> <span data-ttu-id="26465-147">可打开贵组织要使用的云存储提供商对应的开关。</span><span class="sxs-lookup"><span data-stu-id="26465-147">Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="26465-148">组织</span><span class="sxs-lookup"><span data-stu-id="26465-148">Organization</span></span>

<span data-ttu-id="26465-149">此处可以打开**组织**选项卡，其中显示用户的组织详细组织结构图。</span><span class="sxs-lookup"><span data-stu-id="26465-149">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization.</span></span> <span data-ttu-id="26465-150">有关详细信息，请参阅[使用团队中的组织选项卡](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)。</span><span class="sxs-lookup"><span data-stu-id="26465-150">For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="skype-for-business-interop"></a><span data-ttu-id="26465-151">业务互操作的的 Skype</span><span class="sxs-lookup"><span data-stu-id="26465-151">Skype for Business interop</span></span>

<span data-ttu-id="26465-152">使用此设置可允许与 Skype 的业务用户的工作组用户聊天。</span><span class="sxs-lookup"><span data-stu-id="26465-152">Use this setting to let Teams users chat with Skype for Business users.</span></span> <span data-ttu-id="26465-153">有关团队之间 for Business 的 Skype 的互操作性的详细信息，请转到[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="26465-153">For detailed information about interoperability between Teams and Skype for Business, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="devices"></a><span data-ttu-id="26465-154">设备</span><span class="sxs-lookup"><span data-stu-id="26465-154">Devices</span></span>

<span data-ttu-id="26465-155">这些设置控制参加会议的 Microsoft 团队的图面集线器设备资源帐户行为。</span><span class="sxs-lookup"><span data-stu-id="26465-155">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings.</span></span> <span data-ttu-id="26465-156">使用这些设置来配置身份验证要求、 需要内容的 PIN，然后打开面集线器资源帐户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="26465-156">Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="26465-157">**需要第二窗体的身份验证才能访问会议内容**– 选择用户可以输入内容时的访问级别的 PIN。</span><span class="sxs-lookup"><span data-stu-id="26465-157">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="26465-158">**设置内容 PIN** – 要求用户输入此 PIN，以防止未经授权的访问文档。</span><span class="sxs-lookup"><span data-stu-id="26465-158">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents.</span></span> <span data-ttu-id="26465-159">这样可以防止未经授权的用户加入即将召开的会议和浏览附件。</span><span class="sxs-lookup"><span data-stu-id="26465-159">This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="26465-160">**资源帐户可以发送邮件**– 启用**此设置**以允许从面集线器资源帐户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="26465-160">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search"></a><span data-ttu-id="26465-161">搜索</span><span class="sxs-lookup"><span data-stu-id="26465-161">Search</span></span>

<span data-ttu-id="26465-162">Microsoft 团队作用域的目录搜索使用 Exchange 通讯簿策略 (APB) 以允许组织创建虚拟边界的控件如何查找用户并与其他组织中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="26465-162">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> <span data-ttu-id="26465-163">您可能需要在以下情况下使用作用域的目录搜索：</span><span class="sxs-lookup"><span data-stu-id="26465-163">You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="26465-164">您的组织具有多个公司内您希望用于保存单独其租户。</span><span class="sxs-lookup"><span data-stu-id="26465-164">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="26465-165">您的学校希望限制教职员工学生之间的聊天。</span><span class="sxs-lookup"><span data-stu-id="26465-165">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="26465-166">切换**上**打开作用域的目录搜索此设置。</span><span class="sxs-lookup"><span data-stu-id="26465-166">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="26465-167">团队升级</span><span class="sxs-lookup"><span data-stu-id="26465-167">Teams upgrade</span></span>

<span data-ttu-id="26465-168">您可以使用这些设置配置如何您的用户将从升级 for Business 的 Skype 到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="26465-168">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="26465-169">共存模式</span><span class="sxs-lookup"><span data-stu-id="26465-169">Coexistence mode</span></span>
<span data-ttu-id="26465-170">您可以指定共存模式：**仅团队**、**群岛**（团队和共存的业务将 Skype） 或**仅业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="26465-170">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**.</span></span> <span data-ttu-id="26465-171">您选择的共存模式确定传入呼叫和聊天和启动聊天和呼叫或安排会议的用户使用的应用程序的路由。</span><span class="sxs-lookup"><span data-stu-id="26465-171">The Coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings.</span></span> <span data-ttu-id="26465-172">有关共存模式的详细信息，请转到[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="26465-172">For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="26465-173">应用程序首选项</span><span class="sxs-lookup"><span data-stu-id="26465-173">App preferences</span></span>

<span data-ttu-id="26465-174">您可以在此处选择应用程序的用户将用来加入 for Business 的 Skype 会议 (适用于商务或[Skype 会议应用程序](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)的 Skype)。</span><span class="sxs-lookup"><span data-stu-id="26465-174">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)).</span></span> <span data-ttu-id="26465-175">此设置不依赖于在共存模式设置。</span><span class="sxs-lookup"><span data-stu-id="26465-175">This setting isn't dependent on the coexistence mode setting.</span></span>

## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="26465-176">如何判断提供了哪些功能？</span><span class="sxs-lookup"><span data-stu-id="26465-176">How can I tell which features are available?</span></span>

<span data-ttu-id="26465-177">请参阅[Office 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)有关团队的新功能的信息。</span><span class="sxs-lookup"><span data-stu-id="26465-177">See the [Office 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features.</span></span> <span data-ttu-id="26465-178">有关新增和即将发布功能的详细信息，请参阅团队[What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)页和团队[技术社区的 Microsoft 团队博客 （英文）](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) 。</span><span class="sxs-lookup"><span data-stu-id="26465-178">For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 
