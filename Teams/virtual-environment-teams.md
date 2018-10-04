---
title: 在虚拟环境中运行的 Microsoft 团队
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/28/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jaym
description: 了解如何在虚拟化环境中运行的 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: c908cbfbd7daace3665ff99ccd3962fabf440e65
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373397"
---
<a name="run-microsoft-teams-in-a-virtual-environment"></a><span data-ttu-id="d0516-103">在虚拟环境中运行的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="d0516-103">Run Microsoft Teams in a virtual environment</span></span>
============================================

<span data-ttu-id="d0516-104">本文介绍虚拟化环境中使用团队的要求和限制。</span><span class="sxs-lookup"><span data-stu-id="d0516-104">This article describes requirements and limitations for using Teams in a virtualized environment.</span></span>

<span data-ttu-id="d0516-105">某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。</span><span class="sxs-lookup"><span data-stu-id="d0516-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="d0516-106">用户执行虚拟桌面包含所有其桌面应用程序和使用远程桌面服务或类似的远程连接的文件上的工作。</span><span class="sxs-lookup"><span data-stu-id="d0516-106">Their users do their work on a virtual desktop containing all their desktop applications and files using Remote Desktop Services or a similar remote connection.</span></span> <span data-ttu-id="d0516-107">由于没有优化虚拟桌面上的团队访问或 （不带其他软件） 的用户的本地设备上使用的音频或视频设备，在 VDI 环境中工作将通常具有与呼叫，如多媒体方案相关的挑战视频呼叫、 屏幕共享、 应用程序共享、 共同创作和详细信息。</span><span class="sxs-lookup"><span data-stu-id="d0516-107">Since Teams on the virtual desktop has not been optimized to access or use the audio or video devices on the user’s local device (without additional software), working in a VDI environment will usually have challenges related to multimedia scenarios such as calling, video calling, screen sharing, app sharing, co-authoring, and more.</span></span> 

> [!NOTE]
> <span data-ttu-id="d0516-108">组织可以选择运行团队完全 vdi （使用的 Web 应用程序或桌面客户端），但建议以下策略已关闭，使用户不必虚拟化环境中都不好的体验。</span><span class="sxs-lookup"><span data-stu-id="d0516-108">Organizations can choose to run Teams fully in VDI (using either the Web App or Desktop Client) but it is recommended that the following policies be turned off, so users don’t have a poor experience in a virtualized environment.</span></span> <span data-ttu-id="d0516-109">请注意，可能需要一些时间，这些策略更改将传播。</span><span class="sxs-lookup"><span data-stu-id="d0516-109">Note that it can take some time for these policy changes to propagate.</span></span> <span data-ttu-id="d0516-110">如果您没有立即看到给定帐户的更改，几个小时后重试。</span><span class="sxs-lookup"><span data-stu-id="d0516-110">If you don’t see changes for a given account immediately, try again after a few hours.</span></span> 

## <a name="calling"></a><span data-ttu-id="d0516-111">通话</span><span class="sxs-lookup"><span data-stu-id="d0516-111">Calling</span></span>

<span data-ttu-id="d0516-112">*CsTeamsCallingPolicy* cmdlet 启用管理员控制是否调用，并在专用呼叫选项和群聊或未启用。</span><span class="sxs-lookup"><span data-stu-id="d0516-112">The *CsTeamsCallingPolicy* cmdlets enable administrators to control whether calling and calling options in private and group chats are enabled or not.</span></span> 


|<span data-ttu-id="d0516-113">策略名称</span><span class="sxs-lookup"><span data-stu-id="d0516-113">Policy name</span></span> |<span data-ttu-id="d0516-114">说明</span><span class="sxs-lookup"><span data-stu-id="d0516-114">Description</span></span>  |<span data-ttu-id="d0516-115">推荐的值</span><span class="sxs-lookup"><span data-stu-id="d0516-115">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d0516-116">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="d0516-116">AllowPrivateCalling</span></span>   |<span data-ttu-id="d0516-117">控制呼叫应用程序是否为左滑轨团队客户端中可用。</span><span class="sxs-lookup"><span data-stu-id="d0516-117">Controls whether the Calling app is available in the left rail of the Teams client or not.</span></span> <span data-ttu-id="d0516-118">此外将控制用户是否可以看到私人聊天中的电话和视频呼叫选项。</span><span class="sxs-lookup"><span data-stu-id="d0516-118">Also controls whether users see Calling and Video Call options in private chat.</span></span> |<span data-ttu-id="d0516-119">此设置为**False**以删除左滑轨调用应用程序并删除私人聊天中的电话和视频呼叫选项。</span><span class="sxs-lookup"><span data-stu-id="d0516-119">Set this to **False** to remove the Calling app from the left rail and to remove the Calling and Video Call options in private chat.</span></span> |

### <a name="powershell-instructions"></a><span data-ttu-id="d0516-120">PowerShell 说明</span><span class="sxs-lookup"><span data-stu-id="d0516-120">PowerShell instructions</span></span>

1.  <span data-ttu-id="d0516-121">以管理员身份启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d0516-121">Launch PowerShell as an Administrator.</span></span>
2.  <span data-ttu-id="d0516-122">连接到 Skype 联机连接器：</span><span class="sxs-lookup"><span data-stu-id="d0516-122">Connect to Skype Online Connector:</span></span><br>
<span data-ttu-id="d0516-123">\>> *# 设置 Office 365 用户名和密码*</span><span class="sxs-lookup"><span data-stu-id="d0516-123">\>> *# Set Office 365 User Name and Password*</span></span><br>
<span data-ttu-id="d0516-124">\>> *$username ="管理电子邮件地址"*</span><span class="sxs-lookup"><span data-stu-id="d0516-124">\>> *$username = “admin email address”*</span></span><br>
<span data-ttu-id="d0516-125">\>> *$password = ConvertTo SecureString"密码"-AsPlainText-Force*</span><span class="sxs-lookup"><span data-stu-id="d0516-125">\>> *$password = ConvertTo-SecureString "password" -AsPlainText -Force*</span></span><br>
<span data-ttu-id="d0516-126">\>> *$LiveCred = 新对象 typename System.Management.Automation.PSCredential-参数列表 $username，$password*</span><span class="sxs-lookup"><span data-stu-id="d0516-126">\>> *$LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password*</span></span><br><br>
<span data-ttu-id="d0516-127">\>> *# 连接到 Skype Online*</span><span class="sxs-lookup"><span data-stu-id="d0516-127">\>> *# Connect to Skype Online*</span></span><br>
<span data-ttu-id="d0516-128">\>> *导入模块 SkypeOnlineConnector*</span><span class="sxs-lookup"><span data-stu-id="d0516-128">\>> *Import-Module SkypeOnlineConnector*</span></span><br>
<span data-ttu-id="d0516-129">\>> *$sfboSession = 新建 CsOnlineSession-凭据 $LiveCred*</span><span class="sxs-lookup"><span data-stu-id="d0516-129">\>> *$sfboSession = New-CsOnlineSession -Credential $LiveCred*</span></span><br>
<span data-ttu-id="d0516-130">\>> *导入 PSSession $sfboSession*</span><span class="sxs-lookup"><span data-stu-id="d0516-130">\>> *Import-PSSession $sfboSession*</span></span><br>
3.  <span data-ttu-id="d0516-131">查看的调用策略选项的列表：</span><span class="sxs-lookup"><span data-stu-id="d0516-131">View list of Calling Policy Options:</span></span><br>
<span data-ttu-id="d0516-132">\>> *Get CsTeamsCallingPolicy*</span><span class="sxs-lookup"><span data-stu-id="d0516-132">\>> *Get-CsTeamsCallingPolicy*</span></span>
4.  <span data-ttu-id="d0516-133">查找其中禁用所有呼叫策略前 canned 选项：</span><span class="sxs-lookup"><span data-stu-id="d0516-133">Look for the pre-canned option where all calling policies are disabled:</span></span><br>
<span data-ttu-id="d0516-134">![与禁用的所有会议策略的会议选项的屏幕截图。](media/virtual-environment-image2.png)</span><span class="sxs-lookup"><span data-stu-id="d0516-134">![Screenshot of meetings option with all meeting policies disabled.](media/virtual-environment-image2.png)</span></span>
5.  <span data-ttu-id="d0516-135">适用于所有用户都将使用团队虚拟化环境中的"DisallowCalling"前 canned 的策略选项：</span><span class="sxs-lookup"><span data-stu-id="d0516-135">Apply the “DisallowCalling” pre-canned policy option to all users who will be using Teams in a virtualized environment:</span></span><br>
<span data-ttu-id="d0516-136">\>> *授予 CsTeamsCallingPolicy PolicyName DisallowCalling-Identity"用户电子邮件 id"*</span><span class="sxs-lookup"><span data-stu-id="d0516-136">\>> *Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”*</span></span>

## <a name="meetings"></a><span data-ttu-id="d0516-137">会议</span><span class="sxs-lookup"><span data-stu-id="d0516-137">Meetings</span></span>

<span data-ttu-id="d0516-138">*CsTeamsMeetingPolicy* cmdlet 使管理员能够控制用户可以创建的会议或他们可以访问会议中的功能的类型。</span><span class="sxs-lookup"><span data-stu-id="d0516-138">The *CsTeamsMeetingPolicy* cmdlets enable administrators to control the type of meetings that users can create or the features that they can access while in a meeting.</span></span> <span data-ttu-id="d0516-139">它还有助于确定会议如何处理匿名或外部用户。</span><span class="sxs-lookup"><span data-stu-id="d0516-139">It also helps determine how meetings deal with anonymous or external users.</span></span>

|<span data-ttu-id="d0516-140">策略名称</span><span class="sxs-lookup"><span data-stu-id="d0516-140">Policy name</span></span> |<span data-ttu-id="d0516-141">说明</span><span class="sxs-lookup"><span data-stu-id="d0516-141">Description</span></span>  |<span data-ttu-id="d0516-142">推荐的值</span><span class="sxs-lookup"><span data-stu-id="d0516-142">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d0516-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d0516-143">AllowPrivateMeetingScheduling</span></span>    |<span data-ttu-id="d0516-144">确定是否将允许用户安排专用会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-144">Determines whether a user would be allowed to schedule private meetings.</span></span>         |<span data-ttu-id="d0516-145">此设置为**False**以禁止用户能够安排专用会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-145">Set this to **False** to prohibit the user from being able to schedule private meetings.</span></span>         |
|<span data-ttu-id="d0516-146">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d0516-146">AllowChannelMeetingScheduling</span></span>     |<span data-ttu-id="d0516-147">确定是否将允许用户安排通道会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-147">Determines whether a user would be allowed to schedule channel meetings.</span></span>         |<span data-ttu-id="d0516-148">此设置为**False**以禁止用户能够安排通道会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-148">Set this to **False** to prohibit the user from being able to schedule channel meetings.</span></span>         |
|<span data-ttu-id="d0516-149">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="d0516-149">AllowMeetNow</span></span>     |<span data-ttu-id="d0516-150">确定是否将允许用户创建或启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-150">Determines whether a user would be allowed to create or start ad-hoc meetings.</span></span>         |<span data-ttu-id="d0516-151">此设置为**False**以禁止用户启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-151">Set this to **False** to prohibit the user from being able to start ad-hoc meetings.</span></span>         |
|<span data-ttu-id="d0516-152">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="d0516-152">ScreenSharingMode</span></span>     |<span data-ttu-id="d0516-153">确定在将允许用户共享屏幕呼叫或会议中的模式。</span><span class="sxs-lookup"><span data-stu-id="d0516-153">Determines the mode in which a user would be allowed to share screen in calls or meetings.</span></span>         |<span data-ttu-id="d0516-154">此设置为**已禁用**以禁止用户共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="d0516-154">Set this to **Disabled** to prohibit the user from sharing their screens.</span></span>         |
|<span data-ttu-id="d0516-155">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="d0516-155">AllowIPVideo</span></span>     |<span data-ttu-id="d0516-156">确定是否将视频启用中用户的会议或进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="d0516-156">Determines whether video is enabled in a user's meetings or calls.</span></span>         |<span data-ttu-id="d0516-157">此设置为**False**以禁止用户共享其视频。</span><span class="sxs-lookup"><span data-stu-id="d0516-157">Set this to **False** to prohibit the user from sharing their video.</span></span>         |
|<span data-ttu-id="d0516-158">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="d0516-158">AllowAnonymousUsersToDialOut</span></span>     |<span data-ttu-id="d0516-159">确定是否允许匿名用户拨到 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="d0516-159">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span>         |<span data-ttu-id="d0516-160">此设置为**False**可禁止匿名用户拨出。</span><span class="sxs-lookup"><span data-stu-id="d0516-160">Set this to **False** to prohibit anonymous users from dialing out.</span></span>         |
|<span data-ttu-id="d0516-161">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="d0516-161">AllowAnonymousUsersToStartMeeting</span></span>     |<span data-ttu-id="d0516-162">确定是否匿名用户可以启动会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-162">Determines whether anonymous users can initiate a meeting.</span></span>         |<span data-ttu-id="d0516-163">此设置为**False**可禁止他们发起会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-163">Set this to **False** to prohibit them from initiating a meeting.</span></span>         |
|<span data-ttu-id="d0516-164">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="d0516-164">AllowOutlookAddIn</span></span>     |<span data-ttu-id="d0516-165">确定用户是否可以安排 Outlook 桌面客户端中的团队会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-165">Determines whether a user can schedule Teams Meetings in Outlook desktop client.</span></span>         |<span data-ttu-id="d0516-166">此设置为**False**以禁止用户安排 Outlook 客户端中的团队会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-166">Set this to **False** to prohibit a user from scheduling Teams meeting in Outlook client.</span></span>         |
|<span data-ttu-id="d0516-167">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d0516-167">AllowParticipantGiveRequestControl</span></span>     |<span data-ttu-id="d0516-168">确定参与者是否可以请求或授予的屏幕共享控制权。</span><span class="sxs-lookup"><span data-stu-id="d0516-168">Determines whether participants can request or give control of screen sharing.</span></span>         |<span data-ttu-id="d0516-169">将此设置为**False**可禁止用户授予权限，请求在会议中的控件。</span><span class="sxs-lookup"><span data-stu-id="d0516-169">Set this to **False** to prohibit the user from giving, requesting control in a meeting.</span></span>         |
|<span data-ttu-id="d0516-170">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d0516-170">AllowExternalParticipantGiveRequestControl</span></span>     |<span data-ttu-id="d0516-171">确定外部参与者是否可以请求或授予的屏幕共享控制权。</span><span class="sxs-lookup"><span data-stu-id="d0516-171">Determines whether external participants can request or give control of screen sharing.</span></span>         |<span data-ttu-id="d0516-172">将此设置为**False**可禁止外部用户授予权限，请求在会议中的控件。</span><span class="sxs-lookup"><span data-stu-id="d0516-172">Set this to **False** to prohibit an external user from giving, requesting control in a meeting.</span></span>         |
|<span data-ttu-id="d0516-173">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="d0516-173">AllowPowerPointSharing</span></span>     |<span data-ttu-id="d0516-174">确定是否在用户的会议中允许 PowerPoint 共享。</span><span class="sxs-lookup"><span data-stu-id="d0516-174">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span>         |<span data-ttu-id="d0516-175">此设置为**True**以允许。</span><span class="sxs-lookup"><span data-stu-id="d0516-175">Set this to **True** to allow.</span></span><br><span data-ttu-id="d0516-176">此设置为**False**以禁止用户共享在会议中的 PowerPoint 文件。</span><span class="sxs-lookup"><span data-stu-id="d0516-176">Set this to **False** to prohibit user from sharing PowerPoint files in a meeting.</span></span>         |
|<span data-ttu-id="d0516-177">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="d0516-177">AllowWhiteboard</span></span>     |<span data-ttu-id="d0516-178">确定是否在用户的会议中允许白板。</span><span class="sxs-lookup"><span data-stu-id="d0516-178">Determines whether whiteboard is allowed in a user’s meetings.</span></span>         |<span data-ttu-id="d0516-179">此设置为**False**可禁止在会议中的白板应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0516-179">Set this to **False** to prohibit whiteboard application in a meeting.</span></span>         |
|<span data-ttu-id="d0516-180">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="d0516-180">AllowTranscription</span></span>     |<span data-ttu-id="d0516-181">确定是否在用户的会议中允许实时和/或后 meeting 标题和录音。</span><span class="sxs-lookup"><span data-stu-id="d0516-181">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>         |<span data-ttu-id="d0516-182">此设置为**False**可禁止转录和字幕会议中。</span><span class="sxs-lookup"><span data-stu-id="d0516-182">Set this to **False** to prohibit transcription and captioning in a meeting.</span></span>         |

### <a name="powershell-instructions"></a><span data-ttu-id="d0516-183">PowerShell 说明</span><span class="sxs-lookup"><span data-stu-id="d0516-183">PowerShell instructions</span></span>

1.  <span data-ttu-id="d0516-184">以管理员身份启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d0516-184">Launch PowerShell as an Administrator.</span></span>
2.  <span data-ttu-id="d0516-185">连接到 Skype 联机连接器：</span><span class="sxs-lookup"><span data-stu-id="d0516-185">Connect to Skype Online Connector:</span></span><br>
<span data-ttu-id="d0516-186">\>> *# 设置 Office 365 用户名和密码*</span><span class="sxs-lookup"><span data-stu-id="d0516-186">\>> *# Set Office 365 User Name and Password*</span></span><br>
<span data-ttu-id="d0516-187">\>> *$username ="管理电子邮件地址"*</span><span class="sxs-lookup"><span data-stu-id="d0516-187">\>> *$username = “admin email address”*</span></span><br>
<span data-ttu-id="d0516-188">\>> *$password = ConvertTo SecureString"密码"-AsPlainText-Force*</span><span class="sxs-lookup"><span data-stu-id="d0516-188">\>> *$password = ConvertTo-SecureString "password" -AsPlainText -Force*</span></span><br>
<span data-ttu-id="d0516-189">\>> *$LiveCred = 新对象 typename System.Management.Automation.PSCredential-参数列表 $username，$password*</span><span class="sxs-lookup"><span data-stu-id="d0516-189">\>> *$LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password*</span></span><br><br>
<span data-ttu-id="d0516-190">\>> *# 连接到 Skype Online*</span><span class="sxs-lookup"><span data-stu-id="d0516-190">\>> *# Connect to Skype Online*</span></span><br>
<span data-ttu-id="d0516-191">\>> *导入模块 SkypeOnlineConnector*</span><span class="sxs-lookup"><span data-stu-id="d0516-191">\>> *Import-Module SkypeOnlineConnector*</span></span><br>
<span data-ttu-id="d0516-192">\>> *$sfboSession = 新建 CsOnlineSession-凭据 $LiveCred*</span><span class="sxs-lookup"><span data-stu-id="d0516-192">\>> *$sfboSession = New-CsOnlineSession -Credential $LiveCred*</span></span><br>
<span data-ttu-id="d0516-193">\>> *导入 PSSession $sfboSession*</span><span class="sxs-lookup"><span data-stu-id="d0516-193">\>> *Import-PSSession $sfboSession*</span></span>
3.  <span data-ttu-id="d0516-194">查看的会议策略选项的列表：</span><span class="sxs-lookup"><span data-stu-id="d0516-194">View list of Meeting Policy Options:</span></span><br>
<span data-ttu-id="d0516-195">\>> *Get CsTeamsMeetingPolicy*</span><span class="sxs-lookup"><span data-stu-id="d0516-195">\>> *Get-CsTeamsMeetingPolicy*</span></span>
4.  <span data-ttu-id="d0516-196">查找其中禁用所有会议策略前 canned 选项：</span><span class="sxs-lookup"><span data-stu-id="d0516-196">Look for the pre-canned option where all meeting policies are disabled:</span></span><br>
<span data-ttu-id="d0516-197">![调用不带禁用的所有会议策略选项的屏幕截图。](media/virtual-environment-image1.png)</span><span class="sxs-lookup"><span data-stu-id="d0516-197">![Screenshot of calling option with all meeting policies disabled.](media/virtual-environment-image1.png)</span></span>
5.  <span data-ttu-id="d0516-198">适用于所有用户都将使用团队虚拟化环境中的"AllOff"前 canned 的策略选项：</span><span class="sxs-lookup"><span data-stu-id="d0516-198">Apply the “AllOff” pre-canned policy option to all users who will be using Teams in a virtualized environment:</span></span><br>
<span data-ttu-id="d0516-199">\>> *授予 CsTeamsMeetingPolicy PolicyName AllOff-Identity"用户电子邮件 id"*</span><span class="sxs-lookup"><span data-stu-id="d0516-199">\>> *Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”*</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d0516-200">已知限制</span><span class="sxs-lookup"><span data-stu-id="d0516-200">Known limitations</span></span>

<span data-ttu-id="d0516-201">除了提到音频和视频限制因此，有一些上虚拟化环境的用户可能面临的附加限制：</span><span class="sxs-lookup"><span data-stu-id="d0516-201">Besides the audio and video limitations previosly mentioned, there are some additional limitations users on virtualized environments might face:</span></span>

- <span data-ttu-id="d0516-202">**加入由其他人创建的会议。**</span><span class="sxs-lookup"><span data-stu-id="d0516-202">**Joining meetings created by others.**</span></span> <span data-ttu-id="d0516-203">即使上述策略限制从创建会议的用户，他们仍然能够加入由其他用户发送的会议。</span><span class="sxs-lookup"><span data-stu-id="d0516-203">Even though the above policies restrict users from creating meetings, they will still be able to join meetings sent out by other users.</span></span> <span data-ttu-id="d0516-204">这些会议中共享视频，其能够使用白板和其他功能将取决于是否管理员是否已禁用它们。</span><span class="sxs-lookup"><span data-stu-id="d0516-204">Within these meetings, their ability to share video, use WhiteBoard and other features will depend on whether the admin disabled them or not.</span></span>

- <span data-ttu-id="d0516-205">**缓存内容相关的问题。**</span><span class="sxs-lookup"><span data-stu-id="d0516-205">**Issues related to cached content.**</span></span> <span data-ttu-id="d0516-206">如果虚拟环境中运行团队不持续存在 （数据清理的每个用户会话结束时），用户可能会注意到由于无需重新所有内容再次都下载，无论是否在客户端的性能下降给定的用户在以前的会话中访问相同的内容。</span><span class="sxs-lookup"><span data-stu-id="d0516-206">If the virtual environment that Teams is running in is not persisted (data is cleaned up at the end of each user session), users might notice performance degradation due to the client having to re-download all content again, regardless of whether the given user accessed the same content in a previous session.</span></span> <span data-ttu-id="d0516-207">可以使用漫游缓存解决方案，例如所提供的 FSLogix 缓解这种性能影响。</span><span class="sxs-lookup"><span data-stu-id="d0516-207">This performance impact can be mitigated by using roaming cache solutions, such as those provided by FSLogix.</span></span>

<span data-ttu-id="d0516-208">一旦团队优化虚拟桌面环境中使用了，管理员可以还原这些策略和允许用户使用团队，他们通常的方式。</span><span class="sxs-lookup"><span data-stu-id="d0516-208">Once Teams has been optimized for use within Virtual Desktop environments, admins can revert these policies and allow users to use Teams as they normally would.</span></span>

         
        
        
        
        
        
        
        
        
        
        


