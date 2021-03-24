---
title: 为你的组织设置会议策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。
ms.openlocfilehash: f4c8831408ed5c17073456306c0f48add73161ff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100518"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="1e4eb-103">为你的组织设置会议策略</span><span class="sxs-lookup"><span data-stu-id="1e4eb-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="1e4eb-104">会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="1e4eb-105">务必要维护对会议的控制和会议设置。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="1e4eb-106">在有些情况下，可能会有安全问题：默认情况下，任何人（包括未经身份验证的用户）都可以参与会议，并保存在那些会议期间分发的任何幻灯片或讲义。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="1e4eb-107">此外，偶尔可能有法律问题。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="1e4eb-108">例如，默认情况下，允许会议参与者对共享内容进行批注;但是，存档会议时不会保存这些批注。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="1e4eb-109">如果你的组织需要保留所有电子通信记录，你可能希望禁用批注。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="1e4eb-110">在 Skype for Business Online 中，会议使用会议策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="1e4eb-111">会议策略确定可以在会议中使用的特性和功能，包括从会议是否可以包括 IP 音频和视频到可以参加会议的最大人数等所有内容。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="1e4eb-112">可以按全局范围或单个用户范围来配置会议策略。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="1e4eb-113">这为管理员在决定哪些功能可供哪些用户使用时提供了极大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="1e4eb-114">可以在创建策略时配置策略设置，或者可以使用 **Set-CsConferencingPolicy** cmdlet 修改现有策略的设置。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="1e4eb-115">设置你的会议策略</span><span class="sxs-lookup"><span data-stu-id="1e4eb-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="1e4eb-116">对于 Skype for Business Online 中的所有会议策略设置，必须使用 Windows PowerShell 并且不能使用 **Skype for Business 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 

### <a name="start-windows-powershell"></a><span data-ttu-id="1e4eb-117">启动Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e4eb-117">Start Windows PowerShell</span></span>

 > [!Note]
> <span data-ttu-id="1e4eb-118">Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="1e4eb-119">如果你使用的是最新的 Teams PowerShell 公共版本，则不需要安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-119">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="1e4eb-120">安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-120">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="1e4eb-121">打开 Windows PowerShell 命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1e4eb-121">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="1e4eb-122">如果需要有关启动 Windows PowerShell，请参阅在单个 Windows PowerShell 窗口中连接到所有[Microsoft 365 或 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1e4eb-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="1e4eb-123">在会议期间阻止文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="1e4eb-123">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="1e4eb-124">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="1e4eb-124">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="1e4eb-125">有关详细信息，请参阅 [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-125">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="1e4eb-126">若要向组织中所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="1e4eb-126">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="1e4eb-127">有关详细信息，请参阅 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-127">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="1e4eb-128">如果已创建策略，可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet 更改现有策略，然后使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-128">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="1e4eb-129">阻止录制会议并防止匿名会议参与者</span><span class="sxs-lookup"><span data-stu-id="1e4eb-129">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="1e4eb-130">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="1e4eb-130">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="1e4eb-131">有关详细信息，请参阅 [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-131">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="1e4eb-132">若要向 Amos Marble 授予创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="1e4eb-132">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="1e4eb-133">有关详细信息，请参阅 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-133">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="1e4eb-134">如果已创建策略，可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet 更改现有策略，然后使用 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-134">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="1e4eb-135">阻止匿名参与者录制会议和外部用户保存会议内容</span><span class="sxs-lookup"><span data-stu-id="1e4eb-135">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="1e4eb-136">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="1e4eb-136">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="1e4eb-137">有关详细信息，请参阅 [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-137">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="1e4eb-138">若要向组织中所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="1e4eb-138">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="1e4eb-139">有关详细信息，请参阅 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-139">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="1e4eb-140">如果已创建策略，可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet 更改现有策略，然后使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-140">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1e4eb-141">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="1e4eb-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1e4eb-142">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1e4eb-143">使用 Windows PowerShell，当你有多个任务需要执行时，可以使用可以简化日常工作的单一管理点来管理 Microsoft 365 或 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1e4eb-144">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="1e4eb-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1e4eb-145">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="1e4eb-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="1e4eb-146">你可能希望使用 Office 365 Windows PowerShell Office 365 的六大原因</span><span class="sxs-lookup"><span data-stu-id="1e4eb-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="1e4eb-147">Windows PowerShell比使用 Microsoft 365 管理中心（例如，一次对许多用户进行设置更改时）具有许多速度、简单性和工作效率优势。</span><span class="sxs-lookup"><span data-stu-id="1e4eb-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1e4eb-148">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="1e4eb-148">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="1e4eb-149">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="1e4eb-149">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="1e4eb-150">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1e4eb-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="1e4eb-151">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="1e4eb-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="1e4eb-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="1e4eb-152">Related topics</span></span>
[<span data-ttu-id="1e4eb-153">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="1e4eb-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="1e4eb-154">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="1e4eb-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="1e4eb-155">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="1e4eb-155">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
