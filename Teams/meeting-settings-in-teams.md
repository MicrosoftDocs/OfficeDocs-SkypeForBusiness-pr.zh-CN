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
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何管理组织中用户安排的团队会议的设置。
ms.openlocfilehash: 1828d626261c97cf3514781a5c55dbecd59d7666
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344874"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="c7483-103">在 Microsoft Teams 中管理会议设置</span><span class="sxs-lookup"><span data-stu-id="c7483-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="c7483-104">作为管理员, 你可以使用团队会议设置控制匿名用户是否可以加入团队会议、自定义会议邀请, 以及是否要启用服务质量 (QoS), 并为实时流量设置端口范围。</span><span class="sxs-lookup"><span data-stu-id="c7483-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="c7483-105">这些设置适用于用户在你的组织中安排的所有团队会议。</span><span class="sxs-lookup"><span data-stu-id="c7483-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="c7483-106">可在 Microsoft 团队管理中心\*\*\*\* > 的会议 "**会议设置**" 中管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="c7483-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="c7483-107">允许匿名用户加入会议</span><span class="sxs-lookup"><span data-stu-id="c7483-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="c7483-108">通过匿名加入, 任何人都可以通过单击会议邀请中的链接以匿名用户身份加入会议。</span><span class="sxs-lookup"><span data-stu-id="c7483-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span>

<span data-ttu-id="c7483-109">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="c7483-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c7483-110">在左侧导航中, 转到 "**会议** > **会议设置**"。</span><span class="sxs-lookup"><span data-stu-id="c7483-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="c7483-111">在 "**参与者**" 下, 打开**匿名用户可以加入会议**。</span><span class="sxs-lookup"><span data-stu-id="c7483-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="c7483-112">![meeting-settings-participants](media/meeting-settings-participants.png "Microsoft 团队管理中心中团队会议的参与者设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="c7483-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="c7483-113">如果您不希望匿名用户加入您的组织中的用户计划的会议, 请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="c7483-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="c7483-114">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="c7483-114">Customize meeting invitations</span></span>

<span data-ttu-id="c7483-115">您可以自定义团队会议邀请以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="c7483-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="c7483-116">你可以添加组织的徽标并包含有用的信息, 如指向支持网站和法律免责声明的链接, 以及纯文本页脚。</span><span class="sxs-lookup"><span data-stu-id="c7483-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="c7483-117">为会议邀请创建徽标的提示</span><span class="sxs-lookup"><span data-stu-id="c7483-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="c7483-118">创建宽度不188超过30像素的图像 (相当小)。</span><span class="sxs-lookup"><span data-stu-id="c7483-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="c7483-119">以 JPG 格式保存图像。</span><span class="sxs-lookup"><span data-stu-id="c7483-119">Save the image in JPG format.</span></span>
3. <span data-ttu-id="c7483-120">将图像存储在你的组织中的每个人都可以访问的中心位置, 例如网络共享。</span><span class="sxs-lookup"><span data-stu-id="c7483-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="c7483-121">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="c7483-121">Customize your meeting invitations</span></span>

<span data-ttu-id="c7483-122">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="c7483-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c7483-123">在左侧导航中, 转到 "**会议** > **会议设置**"。</span><span class="sxs-lookup"><span data-stu-id="c7483-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="c7483-124">在 "**电子邮件邀请**" 下, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="c7483-124">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="c7483-125">![meeting-settings-invitation](media/meeting-settings-invitation.png "可为团队会议自定义的会议邀请设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="c7483-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="c7483-126">**徽标 URL**输入存储徽标的 URL。</span><span class="sxs-lookup"><span data-stu-id="c7483-126">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="c7483-127">**合法 URL**如果你的组织拥有法律网站, 而你希望其他人出于任何法律问题而转到该网站, 请在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="c7483-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="c7483-128">**帮助 URL**如果你的组织有支持网站, 而你希望用户在遇到问题时转到该网站, 请在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="c7483-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="c7483-129">**页脚**输入要包含在页脚中的文本。</span><span class="sxs-lookup"><span data-stu-id="c7483-129">**Footer** Enter text that you want to include as a footer.</span></span>
3. <span data-ttu-id="c7483-130">等待一小时, 这样才能传播所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c7483-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="c7483-131">然后安排团队会议以查看会议邀请的外观。</span><span class="sxs-lookup"><span data-stu-id="c7483-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="c7483-132">设置你希望如何处理团队会议的实时媒体流量</span><span class="sxs-lookup"><span data-stu-id="c7483-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="c7483-133"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="c7483-133"></span></span>

<span data-ttu-id="c7483-134">如果你使用 "服务质量[(QoS)](qos-in-teams.md) " 来设置网络流量的优先级, 则可以启用 QoS 标记, 并且可以为每种类型的媒体流量设置端口范围。</span><span class="sxs-lookup"><span data-stu-id="c7483-134">If you're using Quality of Service [(QoS)](qos-in-teams.md) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span>

 <span data-ttu-id="c7483-135">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="c7483-135">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c7483-136">在左侧导航中, 转到 "**会议** > **会议设置**"。</span><span class="sxs-lookup"><span data-stu-id="c7483-136">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="c7483-137">在 "**网络**" 下, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="c7483-137">Under **Network**, do the following:</span></span>

    <span data-ttu-id="c7483-138">![meeting-settings-network](media/meeting-settings-network.png "Microsoft 团队管理中心中团队会议的网络设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="c7483-138">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="c7483-139">若要允许对 QoS 使用 DSCP 标记, 请打开**实时媒体流量的 "插入服务质量 (QoS)" 标记**。</span><span class="sxs-lookup"><span data-stu-id="c7483-139">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="c7483-140">您只能选择使用标记, 也可以不选择。不能为每种流量类型设置自定义标记。</span><span class="sxs-lookup"><span data-stu-id="c7483-140">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="c7483-141">有关 DSCP 标记的详细信息, 请参阅[选择 QoS 实现方法](QoS-in-Teams.md#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="c7483-141">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
    - <span data-ttu-id="c7483-142">若要指定端口范围, 请在 "为**每种实时媒体流量选择端口范围**" 旁边, 选择 "**指定端口范围**", 然后输入音频、视频和屏幕共享的起始和结束端口。</span><span class="sxs-lookup"><span data-stu-id="c7483-142">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="c7483-143">若要实现 QoS, 选择此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="c7483-143">Selecting this option is required to implement QoS.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="c7483-144">如果选择 "**自动使用任何可用端口**", 将使用1024和65535之间的可用端口。</span><span class="sxs-lookup"><span data-stu-id="c7483-144">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="c7483-145">仅在未实现 QoS 时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="c7483-145">Use this option only when not implementing QoS.</span></span>
    >
    > <span data-ttu-id="c7483-146">选择太窄的端口范围将导致呼叫中断和通话质量不佳。</span><span class="sxs-lookup"><span data-stu-id="c7483-146">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="c7483-147">下面的建议最少。</span><span class="sxs-lookup"><span data-stu-id="c7483-147">The recommendations below should be a bare minimum.</span></span>

 <span data-ttu-id="c7483-148">如果不确定要在环境中使用的端口范围, 以下设置是一个很好的起始点。</span><span class="sxs-lookup"><span data-stu-id="c7483-148">If you are unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="c7483-149">若要了解详细信息, 请参阅[Microsoft 团队中的实施服务质量 (QoS)](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c7483-149">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="c7483-150">这些是所需的 DSCP 标记和建议的相应媒体端口范围 (由团队和 ExpressRoute 使用)。</span><span class="sxs-lookup"><span data-stu-id="c7483-150">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

<span data-ttu-id="c7483-151">_端口范围和 DSCP 标记_</span><span class="sxs-lookup"><span data-stu-id="c7483-151">_Port ranges and DSCP markings_</span></span>

<span data-ttu-id="c7483-152">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="c7483-152">Media traffic type</span></span>| <span data-ttu-id="c7483-153">客户端源端口范围\*</span><span class="sxs-lookup"><span data-stu-id="c7483-153">Client source port range \*</span></span> |<span data-ttu-id="c7483-154">协议</span><span class="sxs-lookup"><span data-stu-id="c7483-154">Protocol</span></span>|<span data-ttu-id="c7483-155">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="c7483-155">DSCP value</span></span>|<span data-ttu-id="c7483-156">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="c7483-156">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="c7483-157">音频</span><span class="sxs-lookup"><span data-stu-id="c7483-157">Audio</span></span>            | <span data-ttu-id="c7483-158">50000-50019</span><span class="sxs-lookup"><span data-stu-id="c7483-158">50,000–50,019</span></span>               |<span data-ttu-id="c7483-159">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c7483-159">TCP/UDP</span></span> |<span data-ttu-id="c7483-160">46</span><span class="sxs-lookup"><span data-stu-id="c7483-160">46</span></span>        |<span data-ttu-id="c7483-161">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="c7483-161">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="c7483-162">视频</span><span class="sxs-lookup"><span data-stu-id="c7483-162">Video</span></span>            | <span data-ttu-id="c7483-163">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="c7483-163">50,020–50,039</span></span>               |<span data-ttu-id="c7483-164">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c7483-164">TCP/UDP</span></span> |<span data-ttu-id="c7483-165">34</span><span class="sxs-lookup"><span data-stu-id="c7483-165">34</span></span>        |<span data-ttu-id="c7483-166">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="c7483-166">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="c7483-167">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="c7483-167">Application/Screen Sharing</span></span>| <span data-ttu-id="c7483-168">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="c7483-168">50,040–50,059</span></span>      |<span data-ttu-id="c7483-169">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c7483-169">TCP/UDP</span></span> |<span data-ttu-id="c7483-170">18</span><span class="sxs-lookup"><span data-stu-id="c7483-170">18</span></span>        |<span data-ttu-id="c7483-171">有保证的转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="c7483-171">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="c7483-172">\*您分配的端口范围不能重叠, 并且必须彼此相邻。</span><span class="sxs-lookup"><span data-stu-id="c7483-172">\* The port ranges you assign cannot overlap and must be adjacent to each other.</span></span>

<span data-ttu-id="c7483-173">为不同的流量类型设置端口范围只是处理实时媒体的一个步骤;[在团队中查看服务质量 (QoS)](qos-in-teams.md) , 了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c7483-173">Setting port ranges for different traffic types is only one step in handling real time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span> <span data-ttu-id="c7483-174">如果你启用或更改 Microsoft 团队管理中心中的设置, 你需要将[匹配设置应用到所有用户设备](QoS-in-Teams-clients.md)和内部网络设备, 以完全实现团队中的 QoS 的更改。</span><span class="sxs-lookup"><span data-stu-id="c7483-174">If you enable or change settings in the Microsoft Teams admin center, you will need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and internal network devices to fully implement the changes to QoS in Teams.</span></span>

<span data-ttu-id="c7483-175">在 QoS 已使用过一段时间后, 你将在每个这三个工作负荷的需求上获得使用信息, 你可以根据特定需要选择要进行的更改。</span><span class="sxs-lookup"><span data-stu-id="c7483-175">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="c7483-176">[通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)将非常有用。</span><span class="sxs-lookup"><span data-stu-id="c7483-176">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
