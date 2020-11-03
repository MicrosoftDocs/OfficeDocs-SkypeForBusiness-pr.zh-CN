---
title: 在 Microsoft 团队管理中心中管理 Skype for Business 设置
author: lanachin
ms.author: v-lanac
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
description: 了解如何在 Microsoft 团队管理中心中管理 Skype for business 功能的设置。
ms.openlocfilehash: 0a74b2586fa706dc8fe9db73c58b7d938eae59ee
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2020
ms.locfileid: "48827756"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d0865-103">在 Microsoft 团队管理中心中管理 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="d0865-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="d0865-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="d0865-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="d0865-105">作为管理员，Microsoft 团队管理中心是你在其中管理你的组织中 Skype for business 用户的 Skype for business 功能的地方。</span><span class="sxs-lookup"><span data-stu-id="d0865-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="d0865-106">你可以在 " **skype** for business" 页面上管理 [你的组织](#manage-skype-for-business-settings-for-your-organization)的设置，并在用户详细信息页面的 " **skype for business** " 选项卡上管理 [单个用户](#manage-skype-for-business-settings-for-individual-users)的设置。</span><span class="sxs-lookup"><span data-stu-id="d0865-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="d0865-107">如果你的组织的共存模式未设置为 " **仅限团队** "，你将仅看到 " **Skype for business** " 页面。</span><span class="sxs-lookup"><span data-stu-id="d0865-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="d0865-108">同样，如果用户的共存模式不是 **团队成员** ，你将只能看到用户的 " **Skype for business** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d0865-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="d0865-109">若要了解有关共存模式的详细信息，请参阅 [了解团队和 Skype for business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ，并 [设置你的共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="d0865-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d0865-110">Skype for Business 设置以前位于 Microsoft 团队管理中心的 **旧版门户** 中。</span><span class="sxs-lookup"><span data-stu-id="d0865-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d0865-111">在停用旧版门户后，我们会将这些新位置的设置迁移到 Skype for business 管理的团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="d0865-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="d0865-112">你必须分配有全局管理员或 Skype for Business 管理员的 [AZURE AD 管理员角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能在 Microsoft 团队管理中心中管理 Skype for business 功能。</span><span class="sxs-lookup"><span data-stu-id="d0865-112">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="d0865-113">管理你的组织的 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="d0865-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="d0865-114">在 Microsoft 团队管理中心的左侧导航中，转到 " **组织范围的设置**  >  **Skype for** business"。</span><span class="sxs-lookup"><span data-stu-id="d0865-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="d0865-115">在此处，你可以为组织中的所有 Skype for business 用户配置和管理 Skype 会议直播、状态隐私和移动设备通知。</span><span class="sxs-lookup"><span data-stu-id="d0865-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="d0865-116">Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="d0865-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="d0865-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="d0865-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="d0865-118">使用以下设置管理组织中的 [Skype 会议直播](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 。</span><span class="sxs-lookup"><span data-stu-id="d0865-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理中心中的 Skype 会议直播设置的屏幕截图":::

- <span data-ttu-id="d0865-120">**Skype 会议广播** ：打开此项可为你的组织启用 Skype 会议直播。</span><span class="sxs-lookup"><span data-stu-id="d0865-120">**Skype Meeting Broadcasts** : Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="d0865-121">启用此功能后，您需要为 [Skype 会议直播设置您的网络](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="d0865-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="d0865-122">**请参阅预览功能** ：打开此功能可提前获取新功能。</span><span class="sxs-lookup"><span data-stu-id="d0865-122">**See preview features** : Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="d0865-123">**组织者可以安排匿名会议** ：如果要让组织者创建允许组织外部的任何人无需登录即可加入的广播事件，请打开此操作。</span><span class="sxs-lookup"><span data-stu-id="d0865-123">**Organizers can schedule anonymous meetings** : Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="d0865-124">**录制 Skype 会议直播会议** ：启用此项可使组织者和演示者可以录制会议。</span><span class="sxs-lookup"><span data-stu-id="d0865-124">**Record Skype Meeting Broadcast meetings** : Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="d0865-125">**面向与会者的帮助者支持 url** ：输入组织的支持 url （如果与会者在会议期间需要帮助）。</span><span class="sxs-lookup"><span data-stu-id="d0865-125">**Helpdesk support URL for attendees** : Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="d0865-126">联机状态和手机通知</span><span class="sxs-lookup"><span data-stu-id="d0865-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="d0865-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="d0865-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="d0865-128">使用以下设置管理组织中的 Skype for business 状态隐私和手机通知。</span><span class="sxs-lookup"><span data-stu-id="d0865-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理中心中的状态设置的屏幕截图":::

#### <a name="presence"></a><span data-ttu-id="d0865-130">状态</span><span class="sxs-lookup"><span data-stu-id="d0865-130">Presence</span></span>

<span data-ttu-id="d0865-131">默认情况下，组织中的 Skype for Business 用户可以查看状态状态 (如 "可用"、"忙碌" 或 "离开其他 Skype for Business 用户") 。</span><span class="sxs-lookup"><span data-stu-id="d0865-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="d0865-132">选择下列操作之一，设置哪些人可以查看您的 Skype for Business 用户的状态。</span><span class="sxs-lookup"><span data-stu-id="d0865-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="d0865-133">**自动显示状态信息** ：你的组织中未添加到用户的 **外部** 或 **阻止** 列表的任何 Skype for business 用户都可以看到该用户的状态。</span><span class="sxs-lookup"><span data-stu-id="d0865-133">**Automatically display presence information** : Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="d0865-134">**仅向用户的联系人显示状态信息** ：用户联系人列表中未添加到其 **外部** 或 **被阻止** 列表的任何 Skype for business 用户都可以看到该用户的状态。</span><span class="sxs-lookup"><span data-stu-id="d0865-134">**Display presence information only to a user's contacts** : Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="d0865-135">用户可以转到 " **设置**  >  **工具** "  >  **选项** ，在 Skype for business 中覆盖此设置。</span><span class="sxs-lookup"><span data-stu-id="d0865-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="d0865-136">手机通知</span><span class="sxs-lookup"><span data-stu-id="d0865-136">Mobile notifications</span></span>

<span data-ttu-id="d0865-137">你可以设置 Skype for Business 移动用户是否收到有关传入和错过的即时消息、语音邮件和未接来电通知服务的通知。</span><span class="sxs-lookup"><span data-stu-id="d0865-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="d0865-138">根据你的组织中使用的移动设备，你可以使用 **Microsoft 推送通知服务** 、 **Apple 推送通知服务** ，或者同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="d0865-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service** , the **Apple Push Notification Service** , or both.</span></span>

<span data-ttu-id="d0865-139">注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="d0865-139">Keep the following in mind:</span></span>

- <span data-ttu-id="d0865-140">如果您关闭推送通知，用户将在其移动设备上下次启动 Skype for Business 时收到所有通知。</span><span class="sxs-lookup"><span data-stu-id="d0865-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="d0865-141">默认情况下，推送通知处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="d0865-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="d0865-142">单个用户可在其移动设备上的 Skype for Business 中将其关闭。</span><span class="sxs-lookup"><span data-stu-id="d0865-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="d0865-143">当关闭推送通知时，用户将无法再打开推送通知。</span><span class="sxs-lookup"><span data-stu-id="d0865-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d0865-144">[!重要信息] Microsoft 通过其他公司为 Windows Phone、iPhone 和 iPad 用户提供实时的 Skype for Business 移动电话通知。</span><span class="sxs-lookup"><span data-stu-id="d0865-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="d0865-145">请参阅本 [隐私声明](https://go.microsoft.com/fwlink/p/?linkid=247732)。</span><span class="sxs-lookup"><span data-stu-id="d0865-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="d0865-146">管理单个用户的 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="d0865-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="d0865-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="d0865-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="d0865-148">若要管理单个用户的 Skype for Business 设置，请在团队管理中心的左侧导航中，转到 " **用户** "，单击用户的显示名称以打开 "用户详细信息" 页面，然后选择 " **Skype for business 设置** " 选项卡。在此处，你可以为用户配置外部访问和会议设置。</span><span class="sxs-lookup"><span data-stu-id="d0865-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users** , click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="用户详细信息页面上的 "Skype for Business" 选项卡的屏幕截图":::

### <a name="external-access-settings"></a><span data-ttu-id="d0865-150">外部访问设置</span><span class="sxs-lookup"><span data-stu-id="d0865-150">External access settings</span></span>

<span data-ttu-id="d0865-151">你可以有选择地允许或阻止用户是否可以与组织外部的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="d0865-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="d0865-152">**外部 Skype For business 用户** ：如果你希望允许用户与联盟域中的 Skype for business 用户通信，请打开此项。</span><span class="sxs-lookup"><span data-stu-id="d0865-152">**External Skype for Business users** : Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="d0865-153">**外部 Skype 用户** ：如果您希望允许用户与 Skype 用户通信，请打开此项。</span><span class="sxs-lookup"><span data-stu-id="d0865-153">**External Skype users** : Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="d0865-154">会议设置</span><span class="sxs-lookup"><span data-stu-id="d0865-154">Meeting settings</span></span>

<span data-ttu-id="d0865-155">你可以为用户配置以下会议设置。</span><span class="sxs-lookup"><span data-stu-id="d0865-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="d0865-156">**音频 & 视频** ：选择以下音频和视频设置之一：</span><span class="sxs-lookup"><span data-stu-id="d0865-156">**Audio & Video** : Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="d0865-157">**None** ：用户不能使用音频或视频。</span><span class="sxs-lookup"><span data-stu-id="d0865-157">**None** : User can't use audio or video.</span></span>
    - <span data-ttu-id="d0865-158">**仅适用于音频** ：用户可以使用音频，但不能使用视频。</span><span class="sxs-lookup"><span data-stu-id="d0865-158">**Audio only** : User can use audio but not video.</span></span>
    - <span data-ttu-id="d0865-159">**音频和视频** ：用户可以使用音频和视频。</span><span class="sxs-lookup"><span data-stu-id="d0865-159">**Audio and video** : User can use audio and video.</span></span>
    - <span data-ttu-id="d0865-160">**音频和视频 (HD)** ：用户可以使用音频和高清晰度视频。</span><span class="sxs-lookup"><span data-stu-id="d0865-160">**Audio and video (HD)** : User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="d0865-161">**& 会议中记录对话** ：启用此项可允许用户录制对话和会议。</span><span class="sxs-lookup"><span data-stu-id="d0865-161">**Record conversations & meetings** : Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="d0865-162">**合规性** ：如果你被法律要求保留电子存储的信息，请启用此项。</span><span class="sxs-lookup"><span data-stu-id="d0865-162">**Compliance** : Turn this on if you're legally required to retain electronically stored information.</span></span> 
