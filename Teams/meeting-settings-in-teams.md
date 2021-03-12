---
title: 管理会议设置
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 了解如何管理用户在组织中安排的 Teams 会议的设置。
ms.openlocfilehash: a0c0e40be84a1b947b5924f97c0c64556a92e249
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711759"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="7812c-103">在 Microsoft Teams 中管理会议设置</span><span class="sxs-lookup"><span data-stu-id="7812c-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="7812c-104">作为管理员，你可以使用 Teams 会议设置来控制匿名用户是否可以加入 Teams 会议、自定义会议邀请，并在想要启用服务质量 (QoS) 的情况下设置实时流量端口范围。</span><span class="sxs-lookup"><span data-stu-id="7812c-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="7812c-105">这些设置适用于用户在组织中安排的所有 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="7812c-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="7812c-106">可以在 Microsoft Teams 管理中心的“**会议**” > “**会议设置**”中管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="7812c-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="7812c-107">允许匿名用户加入会议</span><span class="sxs-lookup"><span data-stu-id="7812c-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="7812c-108">通过匿名加入，任何人都可以通过单击会议邀请中的链接以匿名用户的身份加入会议。</span><span class="sxs-lookup"><span data-stu-id="7812c-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="7812c-109">要了解更多信息，请参阅[在没有 Teams 帐户的情况下加入会议](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)。</span><span class="sxs-lookup"><span data-stu-id="7812c-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>

<span data-ttu-id="7812c-110">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="7812c-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="7812c-111">必须是 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="7812c-111">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="7812c-112">请参阅 [Teams 管理员角色管理 Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) ，了解管理员角色和权限。</span><span class="sxs-lookup"><span data-stu-id="7812c-112">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="7812c-113">转到“管理中心”。</span><span class="sxs-lookup"><span data-stu-id="7812c-113">Go to the admin center.</span></span>

2. <span data-ttu-id="7812c-114">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="7812c-114">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="7812c-115">在“**参与者**”下，打开“**匿名用户可以加入会议**”。</span><span class="sxs-lookup"><span data-stu-id="7812c-115">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="7812c-116">![管理中心会议的参与者设置的屏幕截图](media/meeting-settings-participants.png "Microsoft Teams 管理中心 Teams 会议的参与者设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="7812c-116">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

> [!CAUTION]
> <span data-ttu-id="7812c-117">如果不希望匿名用户加入组织中由用户安排的会议，请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="7812c-117">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a><span data-ttu-id="7812c-118">允许匿名用户与会议中的应用交互</span><span class="sxs-lookup"><span data-stu-id="7812c-118">Allow anonymous users to interact with apps in meetings</span></span>

<span data-ttu-id="7812c-119">匿名用户现在将继承用户级全局默认权限策略。</span><span class="sxs-lookup"><span data-stu-id="7812c-119">Anonymous users will now inherit the user-level global default permission policy.</span></span> <span data-ttu-id="7812c-120">然后，只要用户级别的权限策略启用了应用，此控件将允许匿名用户与 Teams 会议中的应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="7812c-120">This control will then allow anonymous users to interact with apps in Teams meetings as long as the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="7812c-121">请注意，匿名用户只能与会议中可用的应用交互，无法获取和/或管理这些应用。</span><span class="sxs-lookup"><span data-stu-id="7812c-121">Note that anonymous users can only interact with apps that are already available in a meeting and cannot acquire and/or manage these apps.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7812c-122">默认情况下，将启用允许匿名用户与会议中的应用进行交互的设置。</span><span class="sxs-lookup"><span data-stu-id="7812c-122">By default, the setting to allow anonymous users to interact with apps in meetings is enabled.</span></span>

<span data-ttu-id="7812c-123">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="7812c-123">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="7812c-124">只有 Teams 服务管理员才能访问此设置。</span><span class="sxs-lookup"><span data-stu-id="7812c-124">You must be a Teams service admin to access this setting.</span></span> <span data-ttu-id="7812c-125">请参阅 [Teams 管理员角色管理 Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) ，了解管理员角色和权限。</span><span class="sxs-lookup"><span data-stu-id="7812c-125">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="7812c-126">转到“管理中心”。</span><span class="sxs-lookup"><span data-stu-id="7812c-126">Go to the admin center.</span></span>

2. <span data-ttu-id="7812c-127">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="7812c-127">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="7812c-128">在 **参与者** 下，"匿名 **用户可以与会议中的应用交互** 更改。</span><span class="sxs-lookup"><span data-stu-id="7812c-128">Under **Participants**, the setting for **Anonymous users can interact with apps in meetings** can be changed.</span></span>

> [!CAUTION]
> <span data-ttu-id="7812c-129">如果不希望匿名用户与组织中用户安排的会议中的应用交互，请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="7812c-129">If you don't want anonymous users to interact with apps in meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="7812c-130">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="7812c-130">Customize meeting invitations</span></span>

<span data-ttu-id="7812c-131">你可以自定义 Teams 会议邀请，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="7812c-131">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="7812c-132">可添加组织的徽标，并包含有用的信息，如支持网站的链接和法律免责声明，以及纯文本页脚。</span><span class="sxs-lookup"><span data-stu-id="7812c-132">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="7812c-133">为会议邀请创建徽标的提示</span><span class="sxs-lookup"><span data-stu-id="7812c-133">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="7812c-134">创建一个不超过 188 像素宽 x 30 像素高（相当小）的图像。</span><span class="sxs-lookup"><span data-stu-id="7812c-134">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="7812c-135">将图像保存为 JPG 或 PNG 格式。</span><span class="sxs-lookup"><span data-stu-id="7812c-135">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="7812c-136">将图像存储在收到邀请的每个人都可以访问的位置，例如公共网站。</span><span class="sxs-lookup"><span data-stu-id="7812c-136">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="7812c-137">现在，你可以将其添加到会议邀请。</span><span class="sxs-lookup"><span data-stu-id="7812c-137">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="7812c-138">查看后续步骤。</span><span class="sxs-lookup"><span data-stu-id="7812c-138">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="7812c-139">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="7812c-139">Customize your meeting invitations</span></span>

<span data-ttu-id="7812c-140">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="7812c-140">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7812c-141">转到“管理中心”。</span><span class="sxs-lookup"><span data-stu-id="7812c-141">Go to the admin center.</span></span>
2. <span data-ttu-id="7812c-142">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="7812c-142">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="7812c-143">在“**电子邮件邀请**”下，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7812c-143">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="7812c-144">![可自定义的会议邀请设置的屏幕截图](media/meeting-settings-invitation.png "可以为 Teams 会议自定义的会议邀请设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="7812c-144">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="7812c-145">**徽标 URL** 输入存储徽标的 URL。</span><span class="sxs-lookup"><span data-stu-id="7812c-145">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="7812c-146">**法律 URL** 如果你的组织有一个法律网站，并且你希望其他人转至该网站了解任何法律问题，请在此处输入其 URL。</span><span class="sxs-lookup"><span data-stu-id="7812c-146">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="7812c-147">**帮助 URL** 如果你的组织有一个支持网站，并且你希望人们在遇到问题时转至该网站，请在此处输入其 URL。</span><span class="sxs-lookup"><span data-stu-id="7812c-147">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="7812c-148">**页脚** 输入要作为页脚包含在内的文本。</span><span class="sxs-lookup"><span data-stu-id="7812c-148">**Footer** Enter text that you want to include as a footer.</span></span>
4. <span data-ttu-id="7812c-149">单击“**预览邀请**”可查看会议邀请的预览。</span><span class="sxs-lookup"><span data-stu-id="7812c-149">Click **Preview invite** to see a preview of your meeting invitation.</span></span>
5. <span data-ttu-id="7812c-150">完成时单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7812c-150">When you're done, click **Save**.</span></span>
6. <span data-ttu-id="7812c-151">等待一个小时左右，以便传播所作的更改。</span><span class="sxs-lookup"><span data-stu-id="7812c-151">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="7812c-152">然后，安排一次 Teams 会议，查看会议邀请的外观。</span><span class="sxs-lookup"><span data-stu-id="7812c-152">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="7812c-153">设置你希望如何处理 Teams 会议的实时媒体流量</span><span class="sxs-lookup"><span data-stu-id="7812c-153">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="7812c-154"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="7812c-154"><a name="bknetwork"> </a></span></span>

<span data-ttu-id="7812c-155">如果使用服务质量 （QoS） 确定网络流量的优先顺序，可启用 QoS 标记，并设置每种类型的媒体流量的端口范围。</span><span class="sxs-lookup"><span data-stu-id="7812c-155">If you're using Quality of Service (QoS)to prioritize network traffic, you can enable QoS markers and set port ranges for each type of media traffic.</span></span> <span data-ttu-id="7812c-156">为不同流量类型设置端口范围只是处理实时媒体的其中一个步骤；有关详细信息，请参阅 [Teams 中的服务质量 (QoS)](qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="7812c-156">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7812c-157">如果为 Teams 服务在 Microsoft Teams 管理中心启用 QoS 或更改设置，还需要 [将匹配设置应用到所有用户设备](QoS-in-Teams-clients.md) 以及所有内部网络设备，以在 Teams 中完全实施 QoS 更改。</span><span class="sxs-lookup"><span data-stu-id="7812c-157">If you enable QoS or change settings in the Microsoft Teams admin center for the Teams service, you'll also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="7812c-158">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="7812c-158">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="7812c-159">转到“管理中心”。</span><span class="sxs-lookup"><span data-stu-id="7812c-159">Go to the admin center.</span></span>
2. <span data-ttu-id="7812c-160">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="7812c-160">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="7812c-161">在“**网络**”下，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7812c-161">Under **Network**, do the following:</span></span>

    <span data-ttu-id="7812c-162">![管理中心会议的网络设置的屏幕截图](media/meeting-settings-network.png "Microsoft Teams 管理中心 Teams 会议的网络设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="7812c-162">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screenshot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="7812c-163">要允许对 QoS 使用 DSCP 标记，请打开 **插入实时媒体流量的服务质量 (QoS) 标记**。</span><span class="sxs-lookup"><span data-stu-id="7812c-163">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="7812c-164">你只能选择是否使用标记；不能为每种流量类型设置自定义标记。</span><span class="sxs-lookup"><span data-stu-id="7812c-164">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="7812c-165">有关 DSCP 标记的更多信息，请参阅[选择 QoS 实施方法](QoS-in-Teams.md#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="7812c-165">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
        > [!NOTE]
        > <span data-ttu-id="7812c-166">DSCP 标记通常通过源端口完成，UDP 通信流将默认通过目标端口 3478 路由到传输中继。</span><span class="sxs-lookup"><span data-stu-id="7812c-166">DSCP tagging is typically done via Source Ports and UDP traffic will route to Transport Relay with destination port of 3478 by default.</span></span> <span data-ttu-id="7812c-167">如果你的公司要求在目标端口上标记，请联系支持人员以启用与 UDP 端口 3479（音频）、3480（视频）和 3481（共享）的传输中继通信。</span><span class="sxs-lookup"><span data-stu-id="7812c-167">If your company requires tagging on destination ports, please contact support to enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video), and 3481 (Sharing).</span></span>
    - <span data-ttu-id="7812c-168">要指定端口范围，请在“**选择每种媒体实时流量的端口范围**”旁选择“**指定端口范围**”，然后输入音频、视频和屏幕共享的起始和结束端口。</span><span class="sxs-lookup"><span data-stu-id="7812c-168">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="7812c-169">要实施 QoS，必须选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7812c-169">Selecting this option is required to implement QoS.</span></span> 
        > [!Note]
        > <span data-ttu-id="7812c-170">如果 **媒体通信流标记** 服务质量 （QoS） 标记，必须管理端口设置。</span><span class="sxs-lookup"><span data-stu-id="7812c-170">If **Quality of Service (QoS) markers for real-time media traffic** is on, then you have to manage your port settings.</span></span> <span data-ttu-id="7812c-171">不会自动管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="7812c-171">They aren't managed automatically.</span></span>
        
        > [!IMPORTANT]
        > <span data-ttu-id="7812c-172">如果你选择了 **自动使用任何可用的端口**，则将使用 1024 和 65535 之间的可用端口。</span><span class="sxs-lookup"><span data-stu-id="7812c-172">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="7812c-173">仅在未实施 QoS 的情况下使用此选项。</span><span class="sxs-lookup"><span data-stu-id="7812c-173">Use this option only when not implementing QoS.</span></span>
        >
        > <span data-ttu-id="7812c-174">选择的端口范围过窄会导致通话中断或通话质量不佳。</span><span class="sxs-lookup"><span data-stu-id="7812c-174">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="7812c-175">下面的建议只是最低要求。</span><span class="sxs-lookup"><span data-stu-id="7812c-175">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="7812c-176">如果你不确定要在环境中使用的端口范围，不妨从以下设置开始。</span><span class="sxs-lookup"><span data-stu-id="7812c-176">If you're unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="7812c-177">要了解更多信息，请阅读[在 Microsoft Teams 中实施服务质量 (QoS)](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="7812c-177">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="7812c-178">以下是所需的 DSCP 标记和由 Teams 和 ExpressRoute 使用的建议相应媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="7812c-178">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

### <a name="port-ranges-and-dscp-markings"></a><span data-ttu-id="7812c-179">端口范围和 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="7812c-179">Port ranges and DSCP markings</span></span>

<span data-ttu-id="7812c-180">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="7812c-180">Media traffic type</span></span>| <span data-ttu-id="7812c-181">客户端源端口范围\*</span><span class="sxs-lookup"><span data-stu-id="7812c-181">Client source port range \*</span></span> |<span data-ttu-id="7812c-182">协议</span><span class="sxs-lookup"><span data-stu-id="7812c-182">Protocol</span></span>|<span data-ttu-id="7812c-183">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="7812c-183">DSCP value</span></span>|<span data-ttu-id="7812c-184">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="7812c-184">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="7812c-185">音频</span><span class="sxs-lookup"><span data-stu-id="7812c-185">Audio</span></span>            | <span data-ttu-id="7812c-186">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="7812c-186">50,000–50,019</span></span>               |<span data-ttu-id="7812c-187">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7812c-187">TCP/UDP</span></span> |<span data-ttu-id="7812c-188">46</span><span class="sxs-lookup"><span data-stu-id="7812c-188">46</span></span>        |<span data-ttu-id="7812c-189">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="7812c-189">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="7812c-190">视频</span><span class="sxs-lookup"><span data-stu-id="7812c-190">Video</span></span>            | <span data-ttu-id="7812c-191">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="7812c-191">50,020–50,039</span></span>               |<span data-ttu-id="7812c-192">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7812c-192">TCP/UDP</span></span> |<span data-ttu-id="7812c-193">34</span><span class="sxs-lookup"><span data-stu-id="7812c-193">34</span></span>        |<span data-ttu-id="7812c-194">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="7812c-194">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="7812c-195">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="7812c-195">Application/Screen Sharing</span></span>| <span data-ttu-id="7812c-196">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="7812c-196">50,040–50,059</span></span>      |<span data-ttu-id="7812c-197">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7812c-197">TCP/UDP</span></span> |<span data-ttu-id="7812c-198">18</span><span class="sxs-lookup"><span data-stu-id="7812c-198">18</span></span>        |<span data-ttu-id="7812c-199">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="7812c-199">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="7812c-200">\* 分配的端口区域不能重叠，并且应该彼此相邻。</span><span class="sxs-lookup"><span data-stu-id="7812c-200">\* The port ranges you assign can't overlap and should be adjacent to each other.</span></span>

<span data-ttu-id="7812c-201">在 QoS 使用过一段时间后，你将获得这三种工作负载中每一种的需求信息，并且可以根据特定需求选择要进行的更改。</span><span class="sxs-lookup"><span data-stu-id="7812c-201">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="7812c-202">[通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)将非常有用。</span><span class="sxs-lookup"><span data-stu-id="7812c-202">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
