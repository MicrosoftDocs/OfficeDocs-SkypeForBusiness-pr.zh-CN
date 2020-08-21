---
title: 管理会议设置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: 了解如何管理用户在组织中安排的 Teams 会议的设置。
ms.openlocfilehash: b1c71c4b22b90c38e4b34eebd745b85f7d27e86c
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824943"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="fc718-103">在 Microsoft Teams 中管理会议设置</span><span class="sxs-lookup"><span data-stu-id="fc718-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="fc718-104">作为管理员，你可以使用 Teams 会议设置来控制匿名用户是否可以加入 Teams 会议、自定义会议邀请，并在想要启用服务质量 (QoS) 的情况下设置实时流量端口范围。</span><span class="sxs-lookup"><span data-stu-id="fc718-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="fc718-105">这些设置适用于用户在组织中安排的所有 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="fc718-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="fc718-106">可以在 Microsoft Teams 管理中心的“**会议**” > “**会议设置**”中管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="fc718-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="fc718-107">允许匿名用户加入会议</span><span class="sxs-lookup"><span data-stu-id="fc718-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="fc718-108">通过匿名加入，任何人都可以通过单击会议邀请中的链接以匿名用户的身份加入会议。</span><span class="sxs-lookup"><span data-stu-id="fc718-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="fc718-109">要了解更多信息，请参阅[在没有 Teams 帐户的情况下加入会议](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)。</span><span class="sxs-lookup"><span data-stu-id="fc718-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>

<span data-ttu-id="fc718-110">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="fc718-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="fc718-111">仅拥有 Teams 服务管理员才能进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="fc718-111">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="fc718-112">请参阅 ["使用 Teams 管理员"角色管理 Teams，](https://docs.microsoft.com/microsoftteams/using-admin-roles) 以了解有关获取管理员角色和权限的信息。</span><span class="sxs-lookup"><span data-stu-id="fc718-112">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="fc718-113">转到管理中心。</span><span class="sxs-lookup"><span data-stu-id="fc718-113">Go to the admin center.</span></span>

2. <span data-ttu-id="fc718-114">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="fc718-114">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="fc718-115">在“**参与者**”下，打开“**匿名用户可以加入会议**”。</span><span class="sxs-lookup"><span data-stu-id="fc718-115">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="fc718-116">![管理中心会议的参与者设置的屏幕截图](media/meeting-settings-participants.png "Microsoft Teams 管理中心 Teams 会议的参与者设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="fc718-116">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

> [!CAUTION]
> <span data-ttu-id="fc718-117">如果不希望匿名用户加入组织中由用户安排的会议，请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="fc718-117">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="fc718-118">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="fc718-118">Customize meeting invitations</span></span>

<span data-ttu-id="fc718-119">你可以自定义 Teams 会议邀请，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="fc718-119">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="fc718-120">可添加组织的徽标，并包含有用的信息，如支持网站的链接和法律免责声明，以及纯文本页脚。</span><span class="sxs-lookup"><span data-stu-id="fc718-120">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="fc718-121">为会议邀请创建徽标的提示</span><span class="sxs-lookup"><span data-stu-id="fc718-121">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="fc718-122">创建一个不超过 188 像素宽 x 30 像素高（相当小）的图像。</span><span class="sxs-lookup"><span data-stu-id="fc718-122">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="fc718-123">将图像保存为 JPG 或 PNG 格式。</span><span class="sxs-lookup"><span data-stu-id="fc718-123">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="fc718-124">将图像存储在收到邀请的每个人都可以访问的位置，例如公共网站。</span><span class="sxs-lookup"><span data-stu-id="fc718-124">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="fc718-125">现在，你可以将其添加到会议邀请。</span><span class="sxs-lookup"><span data-stu-id="fc718-125">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="fc718-126">查看后续步骤。</span><span class="sxs-lookup"><span data-stu-id="fc718-126">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="fc718-127">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="fc718-127">Customize your meeting invitations</span></span>

<span data-ttu-id="fc718-128">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="fc718-128">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="fc718-129">转到管理中心。</span><span class="sxs-lookup"><span data-stu-id="fc718-129">Go to the admin center.</span></span>
2. <span data-ttu-id="fc718-130">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="fc718-130">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="fc718-131">在“**电子邮件邀请**”下，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fc718-131">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="fc718-132">![可自定义的会议邀请设置的屏幕截图](media/meeting-settings-invitation.png "可以为 Teams 会议自定义的会议邀请设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="fc718-132">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="fc718-133">**徽标 URL** 输入存储徽标的 URL。</span><span class="sxs-lookup"><span data-stu-id="fc718-133">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="fc718-134">**法律 URL** 如果你的组织有一个法律网站，并且你希望其他人转至该网站了解任何法律问题，请在此处输入其 URL。</span><span class="sxs-lookup"><span data-stu-id="fc718-134">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="fc718-135">**帮助 URL** 如果你的组织有一个支持网站，并且你希望人们在遇到问题时转至该网站，请在此处输入其 URL。</span><span class="sxs-lookup"><span data-stu-id="fc718-135">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="fc718-136">**页脚**输入要作为页脚包含在内的文本。</span><span class="sxs-lookup"><span data-stu-id="fc718-136">**Footer** Enter text that you want to include as a footer.</span></span>
4. <span data-ttu-id="fc718-137">单击“**预览邀请**”可查看会议邀请的预览。</span><span class="sxs-lookup"><span data-stu-id="fc718-137">Click **Preview invite** to see a preview of your meeting invitation.</span></span>
5. <span data-ttu-id="fc718-138">完成时单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fc718-138">When you're done, click **Save**.</span></span>
6. <span data-ttu-id="fc718-139">等待一个小时左右，以便传播所作的更改。</span><span class="sxs-lookup"><span data-stu-id="fc718-139">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="fc718-140">然后，安排一次 Teams 会议，查看会议邀请的外观。</span><span class="sxs-lookup"><span data-stu-id="fc718-140">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="fc718-141">设置你希望如何处理 Teams 会议的实时媒体流量</span><span class="sxs-lookup"><span data-stu-id="fc718-141">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="fc718-142"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="fc718-142"><a name="bknetwork"> </a></span></span>

<span data-ttu-id="fc718-143">如果要使用 (QoS) 来优先考虑网络流量，则可以启用 QoS 标记并为每种媒体流量类型设置端口范围。</span><span class="sxs-lookup"><span data-stu-id="fc718-143">If you're using Quality of Service (QoS)to prioritize network traffic, you can enable QoS markers and set port ranges for each type of media traffic.</span></span> <span data-ttu-id="fc718-144">为不同流量类型设置端口范围只是处理实时媒体的其中一个步骤；有关详细信息，请参阅 [Teams 中的服务质量 (QoS)](qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="fc718-144">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc718-145">如果在 Teams 服务的 Microsoft Teams 管理中心启用 QoS 或更改设置，则还需将 [匹配设置应用到所有用户设备](QoS-in-Teams-clients.md) 和所有内部网络设备，才能完全将更改完全实施到 Teams 中的 QoS。</span><span class="sxs-lookup"><span data-stu-id="fc718-145">If you enable QoS or change settings in the Microsoft Teams admin center for the Teams service, you'll also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="fc718-146">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="fc718-146">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="fc718-147">转到管理中心。</span><span class="sxs-lookup"><span data-stu-id="fc718-147">Go to the admin center.</span></span>
2. <span data-ttu-id="fc718-148">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="fc718-148">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="fc718-149">在“**网络**”下，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fc718-149">Under **Network**, do the following:</span></span>

    <span data-ttu-id="fc718-150">![管理中心会议的网络设置的屏幕截图](media/meeting-settings-network.png "Microsoft Teams 管理中心 Teams 会议的网络设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="fc718-150">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screenshot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="fc718-151">要允许对 QoS 使用 DSCP 标记，请打开**插入实时媒体流量的服务质量 (QoS) 标记**。</span><span class="sxs-lookup"><span data-stu-id="fc718-151">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="fc718-152">你只能选择是否使用标记；不能为每种流量类型设置自定义标记。</span><span class="sxs-lookup"><span data-stu-id="fc718-152">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="fc718-153">有关 DSCP 标记的更多信息，请参阅[选择 QoS 实施方法](QoS-in-Teams.md#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="fc718-153">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
        > [!NOTE]
        > <span data-ttu-id="fc718-154">通常通过源端口完成 DSCP 标记，而 UDP 通信流默认情况下将路由到"传输中迟"（3478 的目标端口）。</span><span class="sxs-lookup"><span data-stu-id="fc718-154">DSCP tagging is typically done via Source Ports and UDP traffic will route to Transport Relay with destination port of 3478 by default.</span></span> <span data-ttu-id="fc718-155">如果您的公司需要标记目标端口，请联系支持人员以使传输中文的通信包括 UDP 端口 3479 (Audio) 、3480 (视频) 和 3481 (共享) 。</span><span class="sxs-lookup"><span data-stu-id="fc718-155">If your company requires tagging on destination ports, please contact support to enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video), and 3481 (Sharing).</span></span>
    - <span data-ttu-id="fc718-156">要指定端口范围，请在“**选择每种媒体实时流量的端口范围**”旁选择“**指定端口范围**”，然后输入音频、视频和屏幕共享的起始和结束端口。</span><span class="sxs-lookup"><span data-stu-id="fc718-156">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="fc718-157">要实施 QoS，必须选择此选项。</span><span class="sxs-lookup"><span data-stu-id="fc718-157">Selecting this option is required to implement QoS.</span></span> 
        > [!Note]
        > <span data-ttu-id="fc718-158">如果 **在 QoS () 流** 量的) 上传输器已启用，则必须管理你的移植设置。</span><span class="sxs-lookup"><span data-stu-id="fc718-158">If **Quality of Service (QoS) markers for real-time media traffic** is on, then you have to manage your port settings.</span></span> <span data-ttu-id="fc718-159">它们不会自动管理。</span><span class="sxs-lookup"><span data-stu-id="fc718-159">They aren't managed automatically.</span></span>
        
        > [!IMPORTANT]
        > <span data-ttu-id="fc718-160">如果你选择了**自动使用任何可用的端口**，则将使用 1024 和 65535 之间的可用端口。</span><span class="sxs-lookup"><span data-stu-id="fc718-160">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="fc718-161">仅在未实施 QoS 的情况下使用此选项。</span><span class="sxs-lookup"><span data-stu-id="fc718-161">Use this option only when not implementing QoS.</span></span>
        >
        > <span data-ttu-id="fc718-162">选择的端口范围过窄会导致通话中断或通话质量不佳。</span><span class="sxs-lookup"><span data-stu-id="fc718-162">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="fc718-163">下面的建议只是最低要求。</span><span class="sxs-lookup"><span data-stu-id="fc718-163">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="fc718-164">如果你不确定要在环境中使用的端口范围，不妨从以下设置开始。</span><span class="sxs-lookup"><span data-stu-id="fc718-164">If you're unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="fc718-165">要了解更多信息，请阅读[在 Microsoft Teams 中实施服务质量 (QoS)](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="fc718-165">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="fc718-166">以下是所需的 DSCP 标记和由 Teams 和 ExpressRoute 使用的建议相应媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="fc718-166">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

### <a name="port-ranges-and-dscp-markings"></a><span data-ttu-id="fc718-167">端口范围和 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="fc718-167">Port ranges and DSCP markings</span></span>

<span data-ttu-id="fc718-168">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="fc718-168">Media traffic type</span></span>| <span data-ttu-id="fc718-169">客户端源端口范围\*</span><span class="sxs-lookup"><span data-stu-id="fc718-169">Client source port range \*</span></span> |<span data-ttu-id="fc718-170">协议</span><span class="sxs-lookup"><span data-stu-id="fc718-170">Protocol</span></span>|<span data-ttu-id="fc718-171">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="fc718-171">DSCP value</span></span>|<span data-ttu-id="fc718-172">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="fc718-172">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="fc718-173">音频</span><span class="sxs-lookup"><span data-stu-id="fc718-173">Audio</span></span>            | <span data-ttu-id="fc718-174">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="fc718-174">50,000–50,019</span></span>               |<span data-ttu-id="fc718-175">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fc718-175">TCP/UDP</span></span> |<span data-ttu-id="fc718-176">46</span><span class="sxs-lookup"><span data-stu-id="fc718-176">46</span></span>        |<span data-ttu-id="fc718-177">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="fc718-177">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="fc718-178">视频</span><span class="sxs-lookup"><span data-stu-id="fc718-178">Video</span></span>            | <span data-ttu-id="fc718-179">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="fc718-179">50,020–50,039</span></span>               |<span data-ttu-id="fc718-180">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fc718-180">TCP/UDP</span></span> |<span data-ttu-id="fc718-181">34</span><span class="sxs-lookup"><span data-stu-id="fc718-181">34</span></span>        |<span data-ttu-id="fc718-182">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="fc718-182">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="fc718-183">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="fc718-183">Application/Screen Sharing</span></span>| <span data-ttu-id="fc718-184">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="fc718-184">50,040–50,059</span></span>      |<span data-ttu-id="fc718-185">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fc718-185">TCP/UDP</span></span> |<span data-ttu-id="fc718-186">18</span><span class="sxs-lookup"><span data-stu-id="fc718-186">18</span></span>        |<span data-ttu-id="fc718-187">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="fc718-187">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="fc718-188">\* 分配的端口范围不能重叠，必须彼此相邻。</span><span class="sxs-lookup"><span data-stu-id="fc718-188">\* The port ranges you assign cannot overlap and must be next to each other.</span></span>

<span data-ttu-id="fc718-189">在 QoS 使用过一段时间后，你将获得这三种工作负载中每一种的需求信息，并且可以根据特定需求选择要进行的更改。</span><span class="sxs-lookup"><span data-stu-id="fc718-189">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="fc718-190">[通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)将非常有用。</span><span class="sxs-lookup"><span data-stu-id="fc718-190">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
