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
ms.openlocfilehash: 6a30843070adc8da14343ad2dc94730a750e1f31
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201216"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="a21a8-103">在 Microsoft Teams 中管理会议设置</span><span class="sxs-lookup"><span data-stu-id="a21a8-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="a21a8-104">作为管理员，你可以使用 Teams 会议设置来控制匿名用户是否可以加入 Teams 会议、自定义会议邀请，并在想要启用服务质量 (QoS) 的情况下设置实时流量端口范围。</span><span class="sxs-lookup"><span data-stu-id="a21a8-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="a21a8-105">这些设置适用于用户在组织中安排的所有 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="a21a8-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="a21a8-106">可以在 Microsoft Teams 管理中心的“**会议**” > “**会议设置**”中管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="a21a8-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="a21a8-107">允许匿名用户加入会议</span><span class="sxs-lookup"><span data-stu-id="a21a8-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="a21a8-108">通过匿名加入，任何人都可以通过单击会议邀请中的链接以匿名用户的身份加入会议。</span><span class="sxs-lookup"><span data-stu-id="a21a8-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="a21a8-109">要了解更多信息，请参阅[在没有 Teams 帐户的情况下加入会议](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)。</span><span class="sxs-lookup"><span data-stu-id="a21a8-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>

<span data-ttu-id="a21a8-110">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="a21a8-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a21a8-111">转到管理中心 <a href="https://go.microsoft.com/fwlink/?linkid=867439" target="_blank">https://admin.teams.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="a21a8-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/?linkid=867439" target="_blank">https://admin.teams.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a21a8-112">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="a21a8-112">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="a21a8-113">在“**参与者**”下，打开“**匿名用户可以加入会议**”。</span><span class="sxs-lookup"><span data-stu-id="a21a8-113">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="a21a8-114">![管理中心会议的参与者设置的屏幕截图](media/meeting-settings-participants.png "Microsoft Teams 管理中心 Teams 会议的参与者设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="a21a8-114">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

> [!CAUTION]
> <span data-ttu-id="a21a8-115">如果不希望匿名用户加入组织中由用户安排的会议，请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="a21a8-115">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="a21a8-116">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="a21a8-116">Customize meeting invitations</span></span>

<span data-ttu-id="a21a8-117">你可以自定义 Teams 会议邀请，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="a21a8-117">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="a21a8-118">可添加组织的徽标，并包含有用的信息，如支持网站的链接和法律免责声明，以及纯文本页脚。</span><span class="sxs-lookup"><span data-stu-id="a21a8-118">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="a21a8-119">为会议邀请创建徽标的提示</span><span class="sxs-lookup"><span data-stu-id="a21a8-119">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="a21a8-120">创建一个不超过 188 像素宽 x 30 像素高（相当小）的图像。</span><span class="sxs-lookup"><span data-stu-id="a21a8-120">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="a21a8-121">将图像保存为 JPG 或 PNG 格式。</span><span class="sxs-lookup"><span data-stu-id="a21a8-121">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="a21a8-122">将图像存储在收到邀请的每个人都可以访问的位置，例如公共网站。</span><span class="sxs-lookup"><span data-stu-id="a21a8-122">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="a21a8-123">现在，你可以将其添加到会议邀请。</span><span class="sxs-lookup"><span data-stu-id="a21a8-123">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="a21a8-124">查看后续步骤。</span><span class="sxs-lookup"><span data-stu-id="a21a8-124">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="a21a8-125">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="a21a8-125">Customize your meeting invitations</span></span>

<span data-ttu-id="a21a8-126">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="a21a8-126">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a21a8-127">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。。</span><span class="sxs-lookup"><span data-stu-id="a21a8-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>..</span></span>
2. <span data-ttu-id="a21a8-128">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="a21a8-128">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="a21a8-129">在“**电子邮件邀请**”下，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a21a8-129">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="a21a8-130">![可自定义的会议邀请设置的屏幕截图](media/meeting-settings-invitation.png "可以为 Teams 会议自定义的会议邀请设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="a21a8-130">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="a21a8-131">**徽标 URL** 输入存储徽标的 URL。</span><span class="sxs-lookup"><span data-stu-id="a21a8-131">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="a21a8-132">**法律 URL** 如果你的组织有一个法律网站，并且你希望其他人转至该网站了解任何法律问题，请在此处输入其 URL。</span><span class="sxs-lookup"><span data-stu-id="a21a8-132">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="a21a8-133">**帮助 URL** 如果你的组织有一个支持网站，并且你希望人们在遇到问题时转至该网站，请在此处输入其 URL。</span><span class="sxs-lookup"><span data-stu-id="a21a8-133">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="a21a8-134">**页脚**输入要作为页脚包含在内的文本。</span><span class="sxs-lookup"><span data-stu-id="a21a8-134">**Footer** Enter text that you want to include as a footer.</span></span>
4. <span data-ttu-id="a21a8-135">单击“**预览邀请**”可查看会议邀请的预览。</span><span class="sxs-lookup"><span data-stu-id="a21a8-135">Click **Preview invite** to see a preview of your meeting invitation.</span></span>
5. <span data-ttu-id="a21a8-136">完成时单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a21a8-136">When you're done, click **Save**.</span></span>
6. <span data-ttu-id="a21a8-137">等待一个小时左右，以便传播所作的更改。</span><span class="sxs-lookup"><span data-stu-id="a21a8-137">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="a21a8-138">然后，安排一次 Teams 会议，查看会议邀请的外观。</span><span class="sxs-lookup"><span data-stu-id="a21a8-138">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="a21a8-139">设置你希望如何处理 Teams 会议的实时媒体流量</span><span class="sxs-lookup"><span data-stu-id="a21a8-139">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="a21a8-140"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="a21a8-140"><a name="bknetwork"> </a></span></span>

<span data-ttu-id="a21a8-141">如果你使用 "服务质量（QoS）" 来设置网络流量的优先级，则可以为每种类型的媒体流量启用 QoS 标记和设置端口范围。</span><span class="sxs-lookup"><span data-stu-id="a21a8-141">If you're using Quality of Service (QoS)to prioritize network traffic, you can enable QoS markers and set port ranges for each type of media traffic.</span></span> <span data-ttu-id="a21a8-142">为不同流量类型设置端口范围只是处理实时媒体的其中一个步骤；有关详细信息，请参阅 [Teams 中的服务质量 (QoS)](qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a21a8-142">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a21a8-143">如果为团队服务启用 QoS 或更改 Microsoft 团队管理中心中的设置，你还需要[将匹配设置应用到所有用户设备](QoS-in-Teams-clients.md)和所有内部网络设备，以完全实现团队中的 QoS 的更改。</span><span class="sxs-lookup"><span data-stu-id="a21a8-143">If you enable QoS or change settings in the Microsoft Teams admin center for the Teams service, you'll also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="a21a8-144">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="a21a8-144">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="a21a8-145">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="a21a8-145">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>
2. <span data-ttu-id="a21a8-146">在左侧导航中，转到“**会议**” > “**会议设置**”。</span><span class="sxs-lookup"><span data-stu-id="a21a8-146">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="a21a8-147">在“**网络**”下，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a21a8-147">Under **Network**, do the following:</span></span>

    <span data-ttu-id="a21a8-148">![管理中心会议的网络设置的屏幕截图](media/meeting-settings-network.png "Microsoft Teams 管理中心 Teams 会议的网络设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="a21a8-148">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screenshot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="a21a8-149">要允许对 QoS 使用 DSCP 标记，请打开**插入实时媒体流量的服务质量 (QoS) 标记**。</span><span class="sxs-lookup"><span data-stu-id="a21a8-149">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="a21a8-150">你只能选择是否使用标记；不能为每种流量类型设置自定义标记。</span><span class="sxs-lookup"><span data-stu-id="a21a8-150">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="a21a8-151">有关 DSCP 标记的更多信息，请参阅[选择 QoS 实施方法](QoS-in-Teams.md#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="a21a8-151">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
        > [!NOTE]
        > <span data-ttu-id="a21a8-152">DSCP 标记通常通过源端口完成，并且 UDP 流量默认情况下将路由到 Transfport 中继和目标端口3478。</span><span class="sxs-lookup"><span data-stu-id="a21a8-152">DSCP tagging is typically done via Source Ports and UDP traffic will route to Transfport Relay with destination port of 3478 by default.</span></span>  <span data-ttu-id="a21a8-153">如果您的公司需要在目标端口上添加标签，请联系支持人员以启用与传输中继的通信，使用 UDP 端口3479（音频）、3480（视频）和3481（共享）。</span><span class="sxs-lookup"><span data-stu-id="a21a8-153">If your company requires tagging on destination ports, please contact support to enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video) and 3481 (Sharing).</span></span>
    - <span data-ttu-id="a21a8-154">要指定端口范围，请在“**选择每种媒体实时流量的端口范围**”旁选择“**指定端口范围**”，然后输入音频、视频和屏幕共享的起始和结束端口。</span><span class="sxs-lookup"><span data-stu-id="a21a8-154">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="a21a8-155">要实施 QoS，必须选择此选项。</span><span class="sxs-lookup"><span data-stu-id="a21a8-155">Selecting this option is required to implement QoS.</span></span>
        > [!IMPORTANT]
        > <span data-ttu-id="a21a8-156">如果你选择了**自动使用任何可用的端口**，则将使用 1024 和 65535 之间的可用端口。</span><span class="sxs-lookup"><span data-stu-id="a21a8-156">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="a21a8-157">仅在未实施 QoS 的情况下使用此选项。</span><span class="sxs-lookup"><span data-stu-id="a21a8-157">Use this option only when not implementing QoS.</span></span>
        >
        > <span data-ttu-id="a21a8-158">选择的端口范围过窄会导致通话中断或通话质量不佳。</span><span class="sxs-lookup"><span data-stu-id="a21a8-158">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="a21a8-159">下面的建议只是最低要求。</span><span class="sxs-lookup"><span data-stu-id="a21a8-159">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="a21a8-160">如果你不确定要在环境中使用的端口范围，不妨从以下设置开始。</span><span class="sxs-lookup"><span data-stu-id="a21a8-160">If you're unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="a21a8-161">要了解更多信息，请阅读[在 Microsoft Teams 中实施服务质量 (QoS)](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a21a8-161">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="a21a8-162">以下是所需的 DSCP 标记和由 Teams 和 ExpressRoute 使用的建议相应媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="a21a8-162">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

### <a name="port-ranges-and-dscp-markings"></a><span data-ttu-id="a21a8-163">端口范围和 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="a21a8-163">Port ranges and DSCP markings</span></span>

<span data-ttu-id="a21a8-164">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="a21a8-164">Media traffic type</span></span>| <span data-ttu-id="a21a8-165">客户端源端口范围\*</span><span class="sxs-lookup"><span data-stu-id="a21a8-165">Client source port range \*</span></span> |<span data-ttu-id="a21a8-166">协议</span><span class="sxs-lookup"><span data-stu-id="a21a8-166">Protocol</span></span>|<span data-ttu-id="a21a8-167">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="a21a8-167">DSCP value</span></span>|<span data-ttu-id="a21a8-168">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="a21a8-168">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="a21a8-169">音频</span><span class="sxs-lookup"><span data-stu-id="a21a8-169">Audio</span></span>            | <span data-ttu-id="a21a8-170">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="a21a8-170">50,000–50,019</span></span>               |<span data-ttu-id="a21a8-171">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a21a8-171">TCP/UDP</span></span> |<span data-ttu-id="a21a8-172">46</span><span class="sxs-lookup"><span data-stu-id="a21a8-172">46</span></span>        |<span data-ttu-id="a21a8-173">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="a21a8-173">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="a21a8-174">视频</span><span class="sxs-lookup"><span data-stu-id="a21a8-174">Video</span></span>            | <span data-ttu-id="a21a8-175">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="a21a8-175">50,020–50,039</span></span>               |<span data-ttu-id="a21a8-176">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a21a8-176">TCP/UDP</span></span> |<span data-ttu-id="a21a8-177">34</span><span class="sxs-lookup"><span data-stu-id="a21a8-177">34</span></span>        |<span data-ttu-id="a21a8-178">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="a21a8-178">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="a21a8-179">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="a21a8-179">Application/Screen Sharing</span></span>| <span data-ttu-id="a21a8-180">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="a21a8-180">50,040–50,059</span></span>      |<span data-ttu-id="a21a8-181">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a21a8-181">TCP/UDP</span></span> |<span data-ttu-id="a21a8-182">18</span><span class="sxs-lookup"><span data-stu-id="a21a8-182">18</span></span>        |<span data-ttu-id="a21a8-183">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="a21a8-183">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="a21a8-184">\* 分配的端口范围不能重叠，必须彼此相邻。</span><span class="sxs-lookup"><span data-stu-id="a21a8-184">\* The port ranges you assign cannot overlap and must be next to each other.</span></span>

<span data-ttu-id="a21a8-185">在 QoS 使用过一段时间后，你将获得这三种工作负载中每一种的需求信息，并且可以根据特定需求选择要进行的更改。</span><span class="sxs-lookup"><span data-stu-id="a21a8-185">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="a21a8-186">[通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)将非常有用。</span><span class="sxs-lookup"><span data-stu-id="a21a8-186">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
