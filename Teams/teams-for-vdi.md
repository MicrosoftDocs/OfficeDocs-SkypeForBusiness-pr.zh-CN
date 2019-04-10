---
title: 虚拟桌面基础结构团队
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 03/25/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 了解如何在虚拟化桌面基础结构 (VDI) 环境中运行的 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30577fc8ee2628520bca7329f651f07cecfe6553
ms.sourcegitcommit: 9bb2bfd09ca279752dbedf17911ea46568649c4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "31752701"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="b79fb-103">虚拟桌面基础结构团队</span><span class="sxs-lookup"><span data-stu-id="b79fb-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="b79fb-104">本文介绍的要求和虚拟化环境中使用的 Microsoft 团队的限制。</span><span class="sxs-lookup"><span data-stu-id="b79fb-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="b79fb-105">什么是 VDI？</span><span class="sxs-lookup"><span data-stu-id="b79fb-105">What is VDI?</span></span>

<span data-ttu-id="b79fb-106">虚拟桌面基础结构 (VDI) 是承载桌面的操作系统和应用程序数据中心中的集中式服务器上的虚拟化技术。</span><span class="sxs-lookup"><span data-stu-id="b79fb-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="b79fb-107">这样完全个性化为具有完全安全和合规性的集中源的用户的桌面体验。</span><span class="sxs-lookup"><span data-stu-id="b79fb-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="b79fb-108">目前，在虚拟化环境中的团队是用于使用专用的持久虚拟机 (VM) 与协作和聊天功能支持。</span><span class="sxs-lookup"><span data-stu-id="b79fb-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="b79fb-109">若要确保最佳用户体验，请按照本文中的指南。</span><span class="sxs-lookup"><span data-stu-id="b79fb-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="b79fb-110">团队要求</span><span class="sxs-lookup"><span data-stu-id="b79fb-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="b79fb-111">设置策略，以关闭呼叫和会议团队中的功能</span><span class="sxs-lookup"><span data-stu-id="b79fb-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="b79fb-112">团队呼叫和会议体验不适合在 VDI 环境 （即将推出）。</span><span class="sxs-lookup"><span data-stu-id="b79fb-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="b79fb-113">我们建议您设置用户级别策略，以关闭呼叫和会议团队中的功能。</span><span class="sxs-lookup"><span data-stu-id="b79fb-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="b79fb-114">您可以仍选择运行团队完全 VDI 中使用的工作组桌面应用程序或 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b79fb-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="b79fb-115">但是，我们建议您设置的策略，以避免会损害用户体验。</span><span class="sxs-lookup"><span data-stu-id="b79fb-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="b79fb-116">传播策略更改可能需要一些时间 （几个小时）。</span><span class="sxs-lookup"><span data-stu-id="b79fb-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="b79fb-117">如果您没有立即看到给定帐户的更改，在几个小时后重试。</span><span class="sxs-lookup"><span data-stu-id="b79fb-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="b79fb-118">当团队呼叫和会议最适合在虚拟桌面环境中使用时，可以还原这些策略和允许用户使用团队，他们通常的方式。</span><span class="sxs-lookup"><span data-stu-id="b79fb-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="b79fb-119">通话</span><span class="sxs-lookup"><span data-stu-id="b79fb-119">Calling</span></span>

<span data-ttu-id="b79fb-120">是否允许用户使用调用和专用中调用选项和组聊天，请使用控制**CSTeamsCallingPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b79fb-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="b79fb-121">下面是策略设置和建议的值的列表。</span><span class="sxs-lookup"><span data-stu-id="b79fb-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="b79fb-122">策略名称</span><span class="sxs-lookup"><span data-stu-id="b79fb-122">Policy name</span></span>  |<span data-ttu-id="b79fb-123">说明</span><span class="sxs-lookup"><span data-stu-id="b79fb-123">Description</span></span> |<span data-ttu-id="b79fb-124">建议的值</span><span class="sxs-lookup"><span data-stu-id="b79fb-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b79fb-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="b79fb-125">AllowCalling</span></span>    |<span data-ttu-id="b79fb-126">调用功能控件互操作。</span><span class="sxs-lookup"><span data-stu-id="b79fb-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="b79fb-127">打开允许 Skype 的业务用户来使一对一呼叫与团队用户，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="b79fb-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="b79fb-128">设置为 False，以防止 Skype 登录团队中的业务用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b79fb-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="b79fb-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="b79fb-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="b79fb-130">控制是否在左侧的团队客户端应用程序栏中提供的电话应用程序和用户请参阅呼叫和视频呼叫私人聊天中的选项</span><span class="sxs-lookup"><span data-stu-id="b79fb-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="b79fb-131">若要删除应用程序栏左侧的团队呼叫应用程序和私人聊天中删除电话和视频呼叫选项，则设置为 False。</span><span class="sxs-lookup"><span data-stu-id="b79fb-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="b79fb-132">创建和分配调用策略</span><span class="sxs-lookup"><span data-stu-id="b79fb-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="b79fb-133">以管理员身份启动 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="b79fb-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="b79fb-134">连接到 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="b79fb-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="b79fb-135">查看呼叫策略选项的列表。</span><span class="sxs-lookup"><span data-stu-id="b79fb-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="b79fb-136">查找内置策略选项其中禁用所有呼叫的策略。</span><span class="sxs-lookup"><span data-stu-id="b79fb-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="b79fb-137">它如下所示。</span><span class="sxs-lookup"><span data-stu-id="b79fb-137">It looks like this.</span></span>
   
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

5. <span data-ttu-id="b79fb-138">将使用团队虚拟化环境中的所有用户应用都于 DisallowCalling 内置策略选项。</span><span class="sxs-lookup"><span data-stu-id="b79fb-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="b79fb-139">有关团队调用策略的详细信息，请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b79fb-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="b79fb-140">会议</span><span class="sxs-lookup"><span data-stu-id="b79fb-140">Meetings</span></span>

<span data-ttu-id="b79fb-141">使用**CsTeamsMeetingPolicy** cmdlet 来控制用户可以创建的会议、 其可以访问会议中的功能和供匿名用户和外部用户的会议功能的类型。</span><span class="sxs-lookup"><span data-stu-id="b79fb-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="b79fb-142">下面是策略设置和建议的值的列表。</span><span class="sxs-lookup"><span data-stu-id="b79fb-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="b79fb-143">策略名称</span><span class="sxs-lookup"><span data-stu-id="b79fb-143">Policy Name</span></span> |<span data-ttu-id="b79fb-144">说明</span><span class="sxs-lookup"><span data-stu-id="b79fb-144">Description</span></span>|<span data-ttu-id="b79fb-145">建议的值</span><span class="sxs-lookup"><span data-stu-id="b79fb-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="b79fb-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b79fb-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="b79fb-147">确定是否允许用户安排专用会议。</span><span class="sxs-lookup"><span data-stu-id="b79fb-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="b79fb-148">设置为 False 以禁止用户能够安排专用会议。</span><span class="sxs-lookup"><span data-stu-id="b79fb-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="b79fb-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b79fb-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="b79fb-150">确定是否允许用户安排通道会议。</span><span class="sxs-lookup"><span data-stu-id="b79fb-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="b79fb-151">设置为 False 以禁止用户能够安排通道会议。</span><span class="sxs-lookup"><span data-stu-id="b79fb-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="b79fb-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="b79fb-152">AllowMeetNow</span></span> |<span data-ttu-id="b79fb-153">确定是否允许用户创建或启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="b79fb-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="b79fb-154">将此参数设置为 False，以禁止用户启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="b79fb-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="b79fb-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="b79fb-155">ScreenSharingMode</span></span> | <span data-ttu-id="b79fb-156">确定允许用户共享其屏幕呼叫或会议中的模式。</span><span class="sxs-lookup"><span data-stu-id="b79fb-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="b79fb-157">设置为 Disabled，以禁止用户共享其屏幕</span><span class="sxs-lookup"><span data-stu-id="b79fb-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="b79fb-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="b79fb-158">AllowIPVideo</span></span> |<span data-ttu-id="b79fb-159">确定是否将视频启用中用户的会议或进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="b79fb-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="b79fb-160">设置为 False 以禁止用户共享其视频</span><span class="sxs-lookup"><span data-stu-id="b79fb-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="b79fb-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="b79fb-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="b79fb-162">确定是否允许匿名用户拨到 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="b79fb-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="b79fb-163">设置为 False 以禁止匿名用户外拨</span><span class="sxs-lookup"><span data-stu-id="b79fb-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="b79fb-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="b79fb-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="b79fb-165">确定匿名用户是否可以开始会议。</span><span class="sxs-lookup"><span data-stu-id="b79fb-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="b79fb-166">设置为 False 以禁止用户启动会议</span><span class="sxs-lookup"><span data-stu-id="b79fb-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="b79fb-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="b79fb-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="b79fb-168">确定用户是否可以安排 Outlook 桌面客户端中的团队会议。</span><span class="sxs-lookup"><span data-stu-id="b79fb-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="b79fb-169">设置为 False 以禁止用户安排 Outlook 桌面客户端中的团队会议</span><span class="sxs-lookup"><span data-stu-id="b79fb-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="b79fb-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="b79fb-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="b79fb-171">确定参与者是否可以请求或授予的屏幕共享控制权。</span><span class="sxs-lookup"><span data-stu-id="b79fb-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="b79fb-172">设置为 False 以禁止用户授予权限，并要求在会议中的控件</span><span class="sxs-lookup"><span data-stu-id="b79fb-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="b79fb-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="b79fb-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="b79fb-174">确定外部参与者是否可以请求或授予的屏幕共享控制权。</span><span class="sxs-lookup"><span data-stu-id="b79fb-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="b79fb-175">设置为 False 以禁止外部用户授予权限，请求在会议中的控件</span><span class="sxs-lookup"><span data-stu-id="b79fb-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="b79fb-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="b79fb-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="b79fb-177">确定是否在用户的会议中允许 PowerPoint 共享。</span><span class="sxs-lookup"><span data-stu-id="b79fb-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="b79fb-178">设置为 False 以禁止用户共享在会议中的 PowerPoint 文件</span><span class="sxs-lookup"><span data-stu-id="b79fb-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="b79fb-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="b79fb-179">AllowWhiteboard</span></span> | <span data-ttu-id="b79fb-180">确定是否在用户的会议中允许白板。</span><span class="sxs-lookup"><span data-stu-id="b79fb-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="b79fb-181">设置为 False 以禁止在会议中的白板</span><span class="sxs-lookup"><span data-stu-id="b79fb-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="b79fb-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="b79fb-182">AllowTranscription</span></span> |<span data-ttu-id="b79fb-183">确定是否在用户的会议中允许实时和/或后 meeting 标题和录音。</span><span class="sxs-lookup"><span data-stu-id="b79fb-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="b79fb-184">设置为 False 以禁止转录和会议中的标题</span><span class="sxs-lookup"><span data-stu-id="b79fb-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="b79fb-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="b79fb-185">AllowSharedNotes</span></span> | <span data-ttu-id="b79fb-186">确定是否允许用户才能共享的便笺。</span><span class="sxs-lookup"><span data-stu-id="b79fb-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="b79fb-187">设置为 False 以禁止用户正在共享的便笺</span><span class="sxs-lookup"><span data-stu-id="b79fb-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="b79fb-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="b79fb-188">MediaBitRateKB</span></span> |<span data-ttu-id="b79fb-189">确定音频/视频/应用程序共享会议中的传输媒体比特率</span><span class="sxs-lookup"><span data-stu-id="b79fb-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="b79fb-190">建议的值为 5000 (5 MB)。</span><span class="sxs-lookup"><span data-stu-id="b79fb-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="b79fb-191">您可以更改它根据贵组织的需要。</span><span class="sxs-lookup"><span data-stu-id="b79fb-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="b79fb-192">创建并分配的会议策略</span><span class="sxs-lookup"><span data-stu-id="b79fb-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="b79fb-193">以管理员身份启动 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="b79fb-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="b79fb-194">连接到 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="b79fb-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="b79fb-195">查看会议策略选项的列表。</span><span class="sxs-lookup"><span data-stu-id="b79fb-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="b79fb-196">查找内置策略选项其中禁用所有会议策略。</span><span class="sxs-lookup"><span data-stu-id="b79fb-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="b79fb-197">它如下所示。</span><span class="sxs-lookup"><span data-stu-id="b79fb-197">It looks like this.</span></span>
   
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
        AlowTranscription                           : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="b79fb-198">将使用团队虚拟化环境中的所有用户应用都于 AllOff 内置策略选项。</span><span class="sxs-lookup"><span data-stu-id="b79fb-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="b79fb-199">有关团队会议策略的详细信息，请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b79fb-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="b79fb-200">虚拟化提供程序要求</span><span class="sxs-lookup"><span data-stu-id="b79fb-200">Virtualization provider requirements</span></span>

<span data-ttu-id="b79fb-201">已在前导虚拟化解决方案提供商验证团队应用程序。</span><span class="sxs-lookup"><span data-stu-id="b79fb-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="b79fb-202">多个市场提供程序，请参阅虚拟化解决方案提供商，以确保满足最低要求。</span><span class="sxs-lookup"><span data-stu-id="b79fb-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="b79fb-203">虚拟机要求</span><span class="sxs-lookup"><span data-stu-id="b79fb-203">Virtual Machine requirements</span></span>

<span data-ttu-id="b79fb-204">使用不同的工作负荷和虚拟化环境中的用户需求，下面是 VM 配置的推荐最低值。</span><span class="sxs-lookup"><span data-stu-id="b79fb-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="b79fb-205">参数</span><span class="sxs-lookup"><span data-stu-id="b79fb-205">Parameter</span></span>  |<span data-ttu-id="b79fb-206">度量值</span><span class="sxs-lookup"><span data-stu-id="b79fb-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="b79fb-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="b79fb-207">vCPU</span></span>    |  <span data-ttu-id="b79fb-208">2 个内核</span><span class="sxs-lookup"><span data-stu-id="b79fb-208">2 cores</span></span>       |
|<span data-ttu-id="b79fb-209">RAM</span><span class="sxs-lookup"><span data-stu-id="b79fb-209">RAM</span></span>     |  <span data-ttu-id="b79fb-210">4 GB</span><span class="sxs-lookup"><span data-stu-id="b79fb-210">4 GB</span></span>      |
|<span data-ttu-id="b79fb-211">存储</span><span class="sxs-lookup"><span data-stu-id="b79fb-211">Storage</span></span>     | <span data-ttu-id="b79fb-212">8 GB</span><span class="sxs-lookup"><span data-stu-id="b79fb-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="b79fb-213">虚拟机操作系统要求</span><span class="sxs-lookup"><span data-stu-id="b79fb-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="b79fb-214">支持的操作系统的虚拟机是：</span><span class="sxs-lookup"><span data-stu-id="b79fb-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="b79fb-215">Windows 10 及更高版本</span><span class="sxs-lookup"><span data-stu-id="b79fb-215">Windows 10 and later</span></span>
- <span data-ttu-id="b79fb-216">Windows Server 2012 R2 及更高版本</span><span class="sxs-lookup"><span data-stu-id="b79fb-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="b79fb-217">在 VDI 上安装团队</span><span class="sxs-lookup"><span data-stu-id="b79fb-217">Install Teams on VDI</span></span>

<span data-ttu-id="b79fb-218">下面是过程和工具，以部署团队桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="b79fb-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="b79fb-219">下载团队 MSI 程序包使用具体取决于环境的以下链接之一。</span><span class="sxs-lookup"><span data-stu-id="b79fb-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="b79fb-220">建议 VDI vm 与 64 位操作系统的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="b79fb-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="b79fb-221">32 位版本</span><span class="sxs-lookup"><span data-stu-id="b79fb-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="b79fb-222">64 位版本</span><span class="sxs-lookup"><span data-stu-id="b79fb-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="b79fb-223">运行以下命令以安装 VDI VM MSI （或完成更新它）。</span><span class="sxs-lookup"><span data-stu-id="b79fb-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="b79fb-224">此安装程序文件的团队。</span><span class="sxs-lookup"><span data-stu-id="b79fb-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="b79fb-225">此时，金色映像安装已完成。</span><span class="sxs-lookup"><span data-stu-id="b79fb-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="b79fb-226">下一个交互式登录会话启动团队，并要求提供凭据。</span><span class="sxs-lookup"><span data-stu-id="b79fb-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="b79fb-227">请注意，不能使用 ALLUSER 属性 VDI 上安装团队时禁用自动启动的团队。</span><span class="sxs-lookup"><span data-stu-id="b79fb-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="b79fb-228">运行以下命令以卸载从 VDI 虚拟机的 MSI （或准备更新它）。</span><span class="sxs-lookup"><span data-stu-id="b79fb-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="b79fb-229">这将从 Program Files 卸载团队。</span><span class="sxs-lookup"><span data-stu-id="b79fb-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="b79fb-230">已知的问题和限制</span><span class="sxs-lookup"><span data-stu-id="b79fb-230">Known issues and limitations</span></span>

<span data-ttu-id="b79fb-231">以下是已知问题和限制在 VDI 团队。</span><span class="sxs-lookup"><span data-stu-id="b79fb-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="b79fb-232">**共享会话主机类型部署**： 范围内不共享会话主机类型部署 （例如，共享非持久 VM 配置）。</span><span class="sxs-lookup"><span data-stu-id="b79fb-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="b79fb-233">**呼叫和会议**：</span><span class="sxs-lookup"><span data-stu-id="b79fb-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="b79fb-234">呼叫和会议方案不为 VDI 进行优化。</span><span class="sxs-lookup"><span data-stu-id="b79fb-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="b79fb-235">这些方案将执行差。</span><span class="sxs-lookup"><span data-stu-id="b79fb-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="b79fb-236">我们建议使用用户级别策略，在[呼叫和会议团队中的功能设置策略，以关闭](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)部分所述。</span><span class="sxs-lookup"><span data-stu-id="b79fb-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="b79fb-237">应用本文中所述的策略会影响使用呼叫和会议功能，具体取决于其他策略可能会影响您的组织中的其他用户的功能。</span><span class="sxs-lookup"><span data-stu-id="b79fb-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="b79fb-238">如果您的组织中的用户使用非 VDI 客户端，您可以选择不应用策略。</span><span class="sxs-lookup"><span data-stu-id="b79fb-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="b79fb-239">**加入呼叫和由其他用户创建的会议**： 虽然策略限制从创建会议的用户，他们仍可以加入会议如果另一个用户拨出到这些会议中。</span><span class="sxs-lookup"><span data-stu-id="b79fb-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="b79fb-240">在这些会议，用户可以共享视频，使用白板和其他功能取决于是否禁用使用 TeamsMeetingPolicy 这些功能。</span><span class="sxs-lookup"><span data-stu-id="b79fb-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="b79fb-241">**缓存内容**： 虚拟环境中哪些团队是否运行不持久 （和数据的每个用户会话末尾清理的方式），用户可能会注意到由于内容刷新，而不管用户是否访问相同的性能下降以前的会话中的内容。</span><span class="sxs-lookup"><span data-stu-id="b79fb-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="b79fb-242">**客户端更新**： 上 VDI 团队不自动更新像 VDI 团队客户端的方式。</span><span class="sxs-lookup"><span data-stu-id="b79fb-242">**Client updates**: Teams on VDI isn't automatically updated like the way that non-VDI Teams clients are.</span></span>  <span data-ttu-id="b79fb-243">您必须通过[VDI 上安装的工作组](#install-teams-on-vdi)部分中所述安装新的 MSI 来更新虚拟机映像。</span><span class="sxs-lookup"><span data-stu-id="b79fb-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="b79fb-244">您必须先卸载要更新为新版本的当前版本。</span><span class="sxs-lookup"><span data-stu-id="b79fb-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="b79fb-245">**用户体验**： 工作组在 VDI 环境中的用户体验可能不同于非 VDI 环境。</span><span class="sxs-lookup"><span data-stu-id="b79fb-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="b79fb-246">差异可能是因为策略设置和/或环境中的支持的功能。</span><span class="sxs-lookup"><span data-stu-id="b79fb-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="b79fb-247">对于团队已知未与 VDI 的问题，请参阅[已知问题的 Microsoft 团队](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b79fb-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b79fb-248">相关主题</span><span class="sxs-lookup"><span data-stu-id="b79fb-248">Related topics</span></span>

- [<span data-ttu-id="b79fb-249">安装 Microsoft 团队使用 MSI</span><span class="sxs-lookup"><span data-stu-id="b79fb-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)