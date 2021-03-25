---
title: 在 Microsoft Teams 管理中心管理 Skype for Business 设置
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心管理 Skype for Business 功能的设置。
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117000"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="10e53-103">在 Microsoft Teams 管理中心管理 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="10e53-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="10e53-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="10e53-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="10e53-105">作为管理员，Microsoft Teams 管理中心是管理组织中 Skype for Business 用户的 Skype for Business 功能的地方。</span><span class="sxs-lookup"><span data-stu-id="10e53-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="10e53-106">您可以在 Skype [](#manage-skype-for-business-settings-for-your-organization) **for Business** 页面上管理组织的设置，在用户 [](#manage-skype-for-business-settings-for-individual-users)详细信息页面的 Skype **for Business** 选项卡上管理单个用户的设置。</span><span class="sxs-lookup"><span data-stu-id="10e53-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="10e53-107">如果你的组织共存模式未设置为"仅 Teams"，你将只能看到 **Skype for Business** **页面**。</span><span class="sxs-lookup"><span data-stu-id="10e53-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="10e53-108">同样，如果用户的共存模式不是 Teams，你将只看到用户的 **"Skype for Business"\*\*\*\*选项卡**。</span><span class="sxs-lookup"><span data-stu-id="10e53-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="10e53-109">若要详细了解共存模式，请参阅了解 Teams 和 [Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 共存和互操作性和 [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="10e53-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="10e53-110">Skype for Business 设置 **以前位于** Microsoft Teams 管理中心的旧版门户中。</span><span class="sxs-lookup"><span data-stu-id="10e53-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="10e53-111">旧门户停用后，我们在用于 Skype for Business 管理的 Teams 管理中心中将设置迁移到这些新位置。</span><span class="sxs-lookup"><span data-stu-id="10e53-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="10e53-112">必须分配全局管理员或 Skype for Business 管理员 [的 Azure AD](/azure/active-directory/roles/permissions-reference) 管理员角色，才能在 Microsoft Teams 管理中心管理 Skype for Business 功能。</span><span class="sxs-lookup"><span data-stu-id="10e53-112">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="10e53-113">管理组织的 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="10e53-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="10e53-114">在 Microsoft Teams 管理中心的左侧导航中，转到 **"组织范围的** 设置  >  **""Skype for Business"。**</span><span class="sxs-lookup"><span data-stu-id="10e53-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="10e53-115">在这里，你可以为贵组织的所有 Skype for Business 用户配置和管理 Skype 会议直播、状态隐私和移动设备通知。</span><span class="sxs-lookup"><span data-stu-id="10e53-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="10e53-116">Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="10e53-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="10e53-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="10e53-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="10e53-118">使用以下设置在你的 [组织中管理 Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 会议直播。</span><span class="sxs-lookup"><span data-stu-id="10e53-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理中心中的 Skype 会议直播设置的屏幕截图":::

- <span data-ttu-id="10e53-120">**Skype 会议直播**：打开此选项，为组织启用 Skype 会议直播。</span><span class="sxs-lookup"><span data-stu-id="10e53-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="10e53-121">启用此功能后，你需要为 Skype 会议直播 [设置你的网络](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="10e53-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="10e53-122">**请参阅预览功能**：启用此功能可提前访问新功能。</span><span class="sxs-lookup"><span data-stu-id="10e53-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="10e53-123">**组织者可以安排匿名会议**：如果希望组织者创建允许组织外部任何人无需登录即可加入的直播活动，请启用此功能。</span><span class="sxs-lookup"><span data-stu-id="10e53-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="10e53-124">**录制 Skype 会议直播会议**：启用此功能，使组织者和演示者能够录制会议。</span><span class="sxs-lookup"><span data-stu-id="10e53-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="10e53-125">**与会者的支持 URL：** 输入组织的支持 URL，与会者在会议期间需要帮助时可以使用该 URL。</span><span class="sxs-lookup"><span data-stu-id="10e53-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="10e53-126">状态和移动通知</span><span class="sxs-lookup"><span data-stu-id="10e53-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="10e53-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="10e53-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="10e53-128">使用以下设置在你的组织中管理 Skype for Business 状态隐私和移动通知。</span><span class="sxs-lookup"><span data-stu-id="10e53-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理中心中状态设置的屏幕截图":::

#### <a name="presence"></a><span data-ttu-id="10e53-130">状态</span><span class="sxs-lookup"><span data-stu-id="10e53-130">Presence</span></span>

<span data-ttu-id="10e53-131">默认情况下，你组织的 Skype for Business 用户可以看到其他 Skype for Business (的状态，例如") 、忙碌或离开"状态。</span><span class="sxs-lookup"><span data-stu-id="10e53-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="10e53-132">选择下列选项之一，设置谁可以看到你的 Skype for Business 用户。</span><span class="sxs-lookup"><span data-stu-id="10e53-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="10e53-133">**自动显示状态信息**：组织中尚未添加到用户的"外部"或"阻止"列表中的任何 Skype for Business用户都可以看到该用户的显示状态。</span><span class="sxs-lookup"><span data-stu-id="10e53-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="10e53-134">**仅向用户的** 联系人显示状态信息：用户的联系人列表中未添加到"外部"或"阻止"列表中的任何 Skype for Business 用户都可以看到该用户的显示状态。</span><span class="sxs-lookup"><span data-stu-id="10e53-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="10e53-135">用户可以在 Skype for Business 中通过访问"设置工具选项  >  **"来替代**  >  **此设置**。</span><span class="sxs-lookup"><span data-stu-id="10e53-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="10e53-136">移动通知</span><span class="sxs-lookup"><span data-stu-id="10e53-136">Mobile notifications</span></span>

<span data-ttu-id="10e53-137">你可以设置你的 Skype for Business 移动用户是否通过推送通知服务收到有关传入和错过的即时消息、语音邮件和错过的呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="10e53-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="10e53-138">根据组织中使用的移动设备，可以使用 **Microsoft** 推送通知服务和/或 **Apple 推送通知** 服务。</span><span class="sxs-lookup"><span data-stu-id="10e53-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="10e53-139">注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="10e53-139">Keep the following in mind:</span></span>

- <span data-ttu-id="10e53-140">如果关闭推送通知，用户在下次在移动设备上启动 Skype for Business 时将收到通知。</span><span class="sxs-lookup"><span data-stu-id="10e53-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="10e53-141">默认情况下，推送通知已打开。</span><span class="sxs-lookup"><span data-stu-id="10e53-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="10e53-142">个人用户可以在移动设备上的 Skype for Business 中将其关闭。</span><span class="sxs-lookup"><span data-stu-id="10e53-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="10e53-143">当关闭推送通知时，用户将无法再打开推送通知。</span><span class="sxs-lookup"><span data-stu-id="10e53-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="10e53-144">[!重要信息] Microsoft 通过其他公司为 Windows Phone、iPhone 和 iPad 用户提供实时的 Skype for Business 移动电话通知。</span><span class="sxs-lookup"><span data-stu-id="10e53-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="10e53-145">请参阅 [本隐私声明](https://go.microsoft.com/fwlink/p/?linkid=247732)。</span><span class="sxs-lookup"><span data-stu-id="10e53-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="10e53-146">管理单个用户的 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="10e53-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="10e53-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="10e53-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="10e53-148">若要管理单个用户的 Skype for Business 设置，请在 Teams 管理中心的左侧导航栏中，转到"用户"，单击用户的 显示名称 以打开用户详细信息页面，然后选择 **"Skype for Business** 设置"选项卡。在这里，您可以为用户配置外部访问和会议设置。</span><span class="sxs-lookup"><span data-stu-id="10e53-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="用户详细信息页面上 Skype for Business 选项卡的屏幕截图":::

### <a name="external-access-settings"></a><span data-ttu-id="10e53-150">外部访问设置</span><span class="sxs-lookup"><span data-stu-id="10e53-150">External access settings</span></span>

<span data-ttu-id="10e53-151">可以选择性地允许或阻止用户是否可以与组织外部人员通信。</span><span class="sxs-lookup"><span data-stu-id="10e53-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="10e53-152">**外部 Skype for Business 用户**：如果希望允许用户与联盟域中的 Skype for Business 用户通信，请启用此功能。</span><span class="sxs-lookup"><span data-stu-id="10e53-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="10e53-153">**外部 Skype 用户**：如果希望允许用户与 Skype 用户通信，请启用此功能。</span><span class="sxs-lookup"><span data-stu-id="10e53-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="10e53-154">会议设置</span><span class="sxs-lookup"><span data-stu-id="10e53-154">Meeting settings</span></span>

<span data-ttu-id="10e53-155">你可以为用户配置以下会议设置。</span><span class="sxs-lookup"><span data-stu-id="10e53-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="10e53-156">**音频和视频&：** 选择以下音频和视频设置之一：</span><span class="sxs-lookup"><span data-stu-id="10e53-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="10e53-157">**无**：用户不能使用音频或视频。</span><span class="sxs-lookup"><span data-stu-id="10e53-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="10e53-158">**仅音频**：用户可以使用音频，但不能使用视频。</span><span class="sxs-lookup"><span data-stu-id="10e53-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="10e53-159">**音频和视频**：用户可以使用音频和视频。</span><span class="sxs-lookup"><span data-stu-id="10e53-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="10e53-160">**音频和视频 (HD) ：** 用户可以使用音频和视频。</span><span class="sxs-lookup"><span data-stu-id="10e53-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="10e53-161">**录制&** 对话：启用此功能以允许用户录制对话和会议。</span><span class="sxs-lookup"><span data-stu-id="10e53-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="10e53-162">**合规性**：如果法律要求您保留电子存储的信息，请启用此功能。</span><span class="sxs-lookup"><span data-stu-id="10e53-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span>