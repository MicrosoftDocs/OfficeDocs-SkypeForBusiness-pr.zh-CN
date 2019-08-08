---
title: 适用于虚拟化桌面基础结构的 Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: 了解如何在虚拟桌面基础结构 (VDI) 环境中运行 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d0680e81799152bfc6eb9a976634384eb70954c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243816"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="382fb-103">适用于虚拟化桌面基础结构的 Teams</span><span class="sxs-lookup"><span data-stu-id="382fb-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="382fb-104">本文介绍在虚拟化环境中使用 Microsoft 团队的要求和限制。</span><span class="sxs-lookup"><span data-stu-id="382fb-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="382fb-105">什么是 VDI？</span><span class="sxs-lookup"><span data-stu-id="382fb-105">What is VDI?</span></span>

<span data-ttu-id="382fb-106">虚拟桌面基础结构 (VDI) 是在数据中心的集中式服务器上托管桌面操作系统和应用程序的虚拟化技术。</span><span class="sxs-lookup"><span data-stu-id="382fb-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="382fb-107">这使具有完全安全和合规的集中源的用户能够获得完全个性化的桌面体验。</span><span class="sxs-lookup"><span data-stu-id="382fb-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="382fb-108">目前, 虚拟化环境中的团队可通过专用永久性虚拟机 (VM) 支持协作和聊天功能。</span><span class="sxs-lookup"><span data-stu-id="382fb-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="382fb-109">若要确保获得最佳的用户体验, 请按照本文中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="382fb-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="382fb-110">团队要求</span><span class="sxs-lookup"><span data-stu-id="382fb-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="382fb-111">设置策略以关闭团队中的呼叫和会议功能</span><span class="sxs-lookup"><span data-stu-id="382fb-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="382fb-112">团队通话和会议体验未针对 VDI 环境进行优化 (即将推出)。</span><span class="sxs-lookup"><span data-stu-id="382fb-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="382fb-113">我们建议你设置用户级策略以关闭团队中的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="382fb-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="382fb-114">你仍然可以选择使用团队桌面应用或 web 应用在 VDI 中完全运行团队。</span><span class="sxs-lookup"><span data-stu-id="382fb-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="382fb-115">但是, 我们建议你设置策略以避免损害用户体验。</span><span class="sxs-lookup"><span data-stu-id="382fb-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="382fb-116">需要花费一些时间 (几个小时) 才能传播策略更改。</span><span class="sxs-lookup"><span data-stu-id="382fb-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="382fb-117">如果你没有立即看到给定帐户的更改, 请在几个小时后重试。</span><span class="sxs-lookup"><span data-stu-id="382fb-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="382fb-118">当团队通话和会议被优化为在虚拟桌面环境中使用时, 您可以还原这些策略, 并允许用户按正常方式使用团队。</span><span class="sxs-lookup"><span data-stu-id="382fb-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="382fb-119">通话</span><span class="sxs-lookup"><span data-stu-id="382fb-119">Calling</span></span>

<span data-ttu-id="382fb-120">使用**CSTeamsCallingPolicy** cmdlet 控制是否允许用户在私人聊天和群组聊天中使用呼叫和呼叫选项。</span><span class="sxs-lookup"><span data-stu-id="382fb-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="382fb-121">下面是策略设置和推荐值的列表。</span><span class="sxs-lookup"><span data-stu-id="382fb-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="382fb-122">策略名称</span><span class="sxs-lookup"><span data-stu-id="382fb-122">Policy name</span></span>  |<span data-ttu-id="382fb-123">说明</span><span class="sxs-lookup"><span data-stu-id="382fb-123">Description</span></span> |<span data-ttu-id="382fb-124">推荐值</span><span class="sxs-lookup"><span data-stu-id="382fb-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="382fb-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="382fb-125">AllowCalling</span></span>    |<span data-ttu-id="382fb-126">控制互操作调用功能。</span><span class="sxs-lookup"><span data-stu-id="382fb-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="382fb-127">启用此功能将允许 Skype for Business 用户与团队用户进行一对一呼叫, 反之亦然。</span><span class="sxs-lookup"><span data-stu-id="382fb-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="382fb-128">设置为 False 以阻止来自团队的 Skype for Business 用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="382fb-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="382fb-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="382fb-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="382fb-130">控制呼叫应用是否在团队客户端左侧的应用栏中可用, 以及用户是否在私人聊天中看到呼叫和视频通话选项</span><span class="sxs-lookup"><span data-stu-id="382fb-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="382fb-131">设置为 False 可从团队左侧的应用栏中删除呼叫应用, 并删除私人聊天中的呼叫和视频通话选项。</span><span class="sxs-lookup"><span data-stu-id="382fb-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="382fb-132">创建和分配呼叫策略</span><span class="sxs-lookup"><span data-stu-id="382fb-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="382fb-133">以管理员身份启动 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="382fb-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="382fb-134">连接到 Skype Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="382fb-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="382fb-135">查看通话策略选项列表。</span><span class="sxs-lookup"><span data-stu-id="382fb-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="382fb-136">查找已禁用所有呼叫策略的内置策略选项。</span><span class="sxs-lookup"><span data-stu-id="382fb-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="382fb-137">其外观如下所示。</span><span class="sxs-lookup"><span data-stu-id="382fb-137">It looks like this.</span></span>
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="382fb-138">将 DisallowCalling 内置策略选项应用于将在虚拟化环境中使用团队的所有用户。</span><span class="sxs-lookup"><span data-stu-id="382fb-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="382fb-139">有关团队调用策略的详细信息, 请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="382fb-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="382fb-140">会议</span><span class="sxs-lookup"><span data-stu-id="382fb-140">Meetings</span></span>

<span data-ttu-id="382fb-141">使用**CsTeamsMeetingPolicy** cmdlet 控制用户可以创建的会议类型、会议期间可以访问的功能以及匿名用户和外部用户可用的会议功能。</span><span class="sxs-lookup"><span data-stu-id="382fb-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="382fb-142">下面是策略设置和推荐值的列表。</span><span class="sxs-lookup"><span data-stu-id="382fb-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="382fb-143">策略名称</span><span class="sxs-lookup"><span data-stu-id="382fb-143">Policy Name</span></span> |<span data-ttu-id="382fb-144">说明</span><span class="sxs-lookup"><span data-stu-id="382fb-144">Description</span></span>|<span data-ttu-id="382fb-145">推荐值</span><span class="sxs-lookup"><span data-stu-id="382fb-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="382fb-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="382fb-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="382fb-147">确定是否允许用户安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="382fb-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="382fb-148">设置为 False 将禁止用户安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="382fb-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="382fb-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="382fb-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="382fb-150">确定是否允许用户安排频道会议。</span><span class="sxs-lookup"><span data-stu-id="382fb-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="382fb-151">设置为 False 可禁止用户安排频道会议。</span><span class="sxs-lookup"><span data-stu-id="382fb-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="382fb-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="382fb-152">AllowMeetNow</span></span> |<span data-ttu-id="382fb-153">确定是否允许用户创建或启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="382fb-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="382fb-154">将此值设置为 False 可禁止用户启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="382fb-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="382fb-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="382fb-155">ScreenSharingMode</span></span> | <span data-ttu-id="382fb-156">确定允许用户在通话或会议中共享其屏幕的模式。</span><span class="sxs-lookup"><span data-stu-id="382fb-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="382fb-157">设置为 "已禁用" 以禁止用户共享其屏幕</span><span class="sxs-lookup"><span data-stu-id="382fb-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="382fb-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="382fb-158">AllowIPVideo</span></span> |<span data-ttu-id="382fb-159">确定是否在用户的会议或呼叫中启用视频。</span><span class="sxs-lookup"><span data-stu-id="382fb-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="382fb-160">设置为 False 以禁止用户共享其视频</span><span class="sxs-lookup"><span data-stu-id="382fb-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="382fb-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="382fb-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="382fb-162">确定是否允许匿名用户拨出到 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="382fb-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="382fb-163">设置为 False 以禁止匿名用户拨出</span><span class="sxs-lookup"><span data-stu-id="382fb-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="382fb-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="382fb-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="382fb-165">确定匿名用户是否可以启动会议。</span><span class="sxs-lookup"><span data-stu-id="382fb-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="382fb-166">设置为 False 以禁止用户启动会议</span><span class="sxs-lookup"><span data-stu-id="382fb-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="382fb-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="382fb-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="382fb-168">确定用户是否可以在 Outlook 桌面客户端中安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="382fb-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="382fb-169">设置为 False 以禁止用户在 Outlook 桌面客户端中安排团队会议</span><span class="sxs-lookup"><span data-stu-id="382fb-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="382fb-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="382fb-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="382fb-171">确定参与者是否可以请求或提供屏幕共享的控制权。</span><span class="sxs-lookup"><span data-stu-id="382fb-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="382fb-172">设置为 False 以禁止用户在会议中授予和请求控件</span><span class="sxs-lookup"><span data-stu-id="382fb-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="382fb-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="382fb-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="382fb-174">确定外部参与者是否可以请求或提供屏幕共享的控制权。</span><span class="sxs-lookup"><span data-stu-id="382fb-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="382fb-175">设置为 False 以禁止外部用户授予, 请求在会议中控制</span><span class="sxs-lookup"><span data-stu-id="382fb-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="382fb-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="382fb-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="382fb-177">确定用户的会议中是否允许 PowerPoint 共享。</span><span class="sxs-lookup"><span data-stu-id="382fb-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="382fb-178">设置为 False 以禁止用户在会议中共享 PowerPoint 文件</span><span class="sxs-lookup"><span data-stu-id="382fb-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="382fb-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="382fb-179">AllowWhiteboard</span></span> | <span data-ttu-id="382fb-180">确定用户的会议中是否允许白板。</span><span class="sxs-lookup"><span data-stu-id="382fb-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="382fb-181">设置为 False 以在会议中禁用白板</span><span class="sxs-lookup"><span data-stu-id="382fb-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="382fb-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="382fb-182">AllowTranscription</span></span> |<span data-ttu-id="382fb-183">确定用户的会议中是否允许实时和/或后期会议标题和转录。</span><span class="sxs-lookup"><span data-stu-id="382fb-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="382fb-184">设置为 False 以禁止会议中的脚本和字幕</span><span class="sxs-lookup"><span data-stu-id="382fb-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="382fb-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="382fb-185">AllowSharedNotes</span></span> | <span data-ttu-id="382fb-186">确定是否允许用户接受共享笔记。</span><span class="sxs-lookup"><span data-stu-id="382fb-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="382fb-187">设置为 False 以禁止用户接受共享笔记</span><span class="sxs-lookup"><span data-stu-id="382fb-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="382fb-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="382fb-188">MediaBitRateKB</span></span> |<span data-ttu-id="382fb-189">确定会议中音频/视频/应用共享传输的媒体比特率</span><span class="sxs-lookup"><span data-stu-id="382fb-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="382fb-190">建议值为 5000 (5 MB)。</span><span class="sxs-lookup"><span data-stu-id="382fb-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="382fb-191">您可以根据组织的需要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="382fb-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="382fb-192">创建和分配会议策略</span><span class="sxs-lookup"><span data-stu-id="382fb-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="382fb-193">以管理员身份启动 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="382fb-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="382fb-194">连接到 Skype Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="382fb-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="382fb-195">查看会议策略选项列表。</span><span class="sxs-lookup"><span data-stu-id="382fb-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="382fb-196">查找已禁用所有会议策略的内置策略选项。</span><span class="sxs-lookup"><span data-stu-id="382fb-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="382fb-197">其外观如下所示。</span><span class="sxs-lookup"><span data-stu-id="382fb-197">It looks like this.</span></span>
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="382fb-198">将 AllOff 内置策略选项应用于将在虚拟化环境中使用团队的所有用户。</span><span class="sxs-lookup"><span data-stu-id="382fb-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="382fb-199">有关团队会议策略的详细信息, 请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="382fb-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="382fb-200">虚拟化提供商要求</span><span class="sxs-lookup"><span data-stu-id="382fb-200">Virtualization provider requirements</span></span>

<span data-ttu-id="382fb-201">团队应用已在主流虚拟化解决方案提供商处验证。</span><span class="sxs-lookup"><span data-stu-id="382fb-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="382fb-202">有了多个市场提供商, 请咨询您的虚拟化解决方案提供商以确保满足最低要求。</span><span class="sxs-lookup"><span data-stu-id="382fb-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="382fb-203">虚拟机要求</span><span class="sxs-lookup"><span data-stu-id="382fb-203">Virtual Machine requirements</span></span>

<span data-ttu-id="382fb-204">利用虚拟化环境中的各种工作负载和用户需求, 以下是推荐的最低 VM 配置。</span><span class="sxs-lookup"><span data-stu-id="382fb-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="382fb-205">参数</span><span class="sxs-lookup"><span data-stu-id="382fb-205">Parameter</span></span>  |<span data-ttu-id="382fb-206">测度</span><span class="sxs-lookup"><span data-stu-id="382fb-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="382fb-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="382fb-207">vCPU</span></span>    |  <span data-ttu-id="382fb-208">2核</span><span class="sxs-lookup"><span data-stu-id="382fb-208">2 cores</span></span>       |
|<span data-ttu-id="382fb-209">RAM</span><span class="sxs-lookup"><span data-stu-id="382fb-209">RAM</span></span>     |  <span data-ttu-id="382fb-210">4 GB</span><span class="sxs-lookup"><span data-stu-id="382fb-210">4 GB</span></span>      |
|<span data-ttu-id="382fb-211">Storage</span><span class="sxs-lookup"><span data-stu-id="382fb-211">Storage</span></span>     | <span data-ttu-id="382fb-212">8 GB</span><span class="sxs-lookup"><span data-stu-id="382fb-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="382fb-213">虚拟机操作系统要求</span><span class="sxs-lookup"><span data-stu-id="382fb-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="382fb-214">适用于 VM 的受支持的操作系统是:</span><span class="sxs-lookup"><span data-stu-id="382fb-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="382fb-215">Windows 10 及更高版本</span><span class="sxs-lookup"><span data-stu-id="382fb-215">Windows 10 and later</span></span>
- <span data-ttu-id="382fb-216">Windows Server 2012 R2 及更高版本</span><span class="sxs-lookup"><span data-stu-id="382fb-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="382fb-217">在 VDI 上安装团队</span><span class="sxs-lookup"><span data-stu-id="382fb-217">Install Teams on VDI</span></span>

<span data-ttu-id="382fb-218">下面是部署团队桌面应用的过程和工具。</span><span class="sxs-lookup"><span data-stu-id="382fb-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="382fb-219">根据环境, 使用下列链接之一下载团队 MSI 程序包。</span><span class="sxs-lookup"><span data-stu-id="382fb-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="382fb-220">我们建议使用64位操作系统的 VDI VM 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="382fb-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="382fb-221">32位版本</span><span class="sxs-lookup"><span data-stu-id="382fb-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="382fb-222">64位版本</span><span class="sxs-lookup"><span data-stu-id="382fb-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="382fb-223">运行以下命令, 将 MSI 安装到 VDI VM (或完成更新)。</span><span class="sxs-lookup"><span data-stu-id="382fb-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="382fb-224">这将把团队安装到程序文件。</span><span class="sxs-lookup"><span data-stu-id="382fb-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="382fb-225">此时, 将完成黄金图像设置。</span><span class="sxs-lookup"><span data-stu-id="382fb-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="382fb-226">下一个交互式登录会话将启动团队并要求提供凭据。</span><span class="sxs-lookup"><span data-stu-id="382fb-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="382fb-227">请注意, 在 VDI 上使用 ALLUSER 属性安装团队时, 不可能禁用团队的自动启动。</span><span class="sxs-lookup"><span data-stu-id="382fb-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="382fb-228">运行以下命令以从 VDI VM 卸载 MSI (或准备更新它)。</span><span class="sxs-lookup"><span data-stu-id="382fb-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="382fb-229">这将从程序文件中卸载团队。</span><span class="sxs-lookup"><span data-stu-id="382fb-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="382fb-230">已知问题和限制</span><span class="sxs-lookup"><span data-stu-id="382fb-230">Known issues and limitations</span></span>

<span data-ttu-id="382fb-231">以下是 VDI 上团队的已知问题和限制。</span><span class="sxs-lookup"><span data-stu-id="382fb-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="382fb-232">**共享会话主机类型部署**: 共享会话主机类型部署 (例如, 共享非永久性 VM 配置) 不在作用域内。</span><span class="sxs-lookup"><span data-stu-id="382fb-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="382fb-233">**通话和会议**:</span><span class="sxs-lookup"><span data-stu-id="382fb-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="382fb-234">不会针对 VDI 优化通话和会议方案。</span><span class="sxs-lookup"><span data-stu-id="382fb-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="382fb-235">这些方案的性能将较差。</span><span class="sxs-lookup"><span data-stu-id="382fb-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="382fb-236">我们建议使用用户级策略, 如在团队部分中[关闭呼叫和会议功能的 "设置策略](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="382fb-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="382fb-237">应用本文中所述的策略会影响使用呼叫和会议功能的能力, 这取决于其他策略可能会影响组织中的其他用户。</span><span class="sxs-lookup"><span data-stu-id="382fb-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="382fb-238">如果你的组织中的用户使用非 VDI 客户端, 你可以选择不应用策略。</span><span class="sxs-lookup"><span data-stu-id="382fb-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="382fb-239">**加入由其他用户创建的呼叫和会议**: 虽然这些策略限制用户创建会议, 但如果其他用户通过会议拨出, 他们仍可以加入会议。</span><span class="sxs-lookup"><span data-stu-id="382fb-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="382fb-240">在这些会议中, 用户共享视频的能力, 使用白板和其他功能取决于是否使用 TeamsMeetingPolicy 禁用了这些功能。</span><span class="sxs-lookup"><span data-stu-id="382fb-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="382fb-241">**缓存的内容**: 如果运行团队的虚拟环境不是永久性的 (在每个用户会话结束时清除数据), 用户可能会因内容刷新而发现性能下降, 无论用户是否访问以前会话中的内容。</span><span class="sxs-lookup"><span data-stu-id="382fb-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="382fb-242">**客户端更新**: 不会通过每计算机 MSI 安装自动更新 VDI 上的团队。</span><span class="sxs-lookup"><span data-stu-id="382fb-242">**Client updates**: Teams on VDI isn't automatically updated with per-machine MSI installation.</span></span> <span data-ttu-id="382fb-243">你必须按照 "在[VDI 上安装团队](#install-teams-on-vdi)" 部分中的说明, 通过安装新 MSI 来更新 VM 映像。</span><span class="sxs-lookup"><span data-stu-id="382fb-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="382fb-244">必须卸载当前版本才能更新到较新版本。</span><span class="sxs-lookup"><span data-stu-id="382fb-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="382fb-245">**用户体验**: VDI 环境中的团队用户体验可能与非 VDI 环境不同。</span><span class="sxs-lookup"><span data-stu-id="382fb-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="382fb-246">这些差异可能是由于环境中的策略设置和/或功能支持而造成的。</span><span class="sxs-lookup"><span data-stu-id="382fb-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="382fb-247">对于不与 VDI 无关的团队已知问题, 请参阅[Microsoft 团队的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="382fb-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="382fb-248">相关主题</span><span class="sxs-lookup"><span data-stu-id="382fb-248">Related topics</span></span>

- [<span data-ttu-id="382fb-249">使用 MSI 安装 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="382fb-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
