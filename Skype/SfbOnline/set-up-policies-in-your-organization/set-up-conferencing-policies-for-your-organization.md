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
ms.openlocfilehash: aba41b8c1e527157c9ff8d58a2a7a78bfebb0a82
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887891"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="0fbdc-103">为你的组织设置会议策略</span><span class="sxs-lookup"><span data-stu-id="0fbdc-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="0fbdc-104">会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="0fbdc-p101">保持对会议和会议设置的控制非常重要。在某些情况下，可能存在安全问题：默认情况下，任何人（包括未经身份验证的用户）都可以加入会议，并保存在这些会议中分发的任何幻灯片或讲义。此外，可能还存在一些偶然的法律问题。例如，默认情况下，会议参与者可以在共享内容上进行注释;但是，在存档会议时，这些注释不会保存。如果您的组织需要保留所有电子通信的记录，您可能希望禁用注释。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="0fbdc-p102">在 Skype for Business Online 中，通过使用会议策略管理会议。会议策略确定可在会议中使用的功能和功能，包括来自会议的所有内容，包括从会议到可参加会议的最大人数。可以在全局范围内或在每用户范围内配置会议策略。这在确定哪些功能将提供给哪些用户的情况下为管理员提供了巨大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="0fbdc-114">策略设置可以在创建策略时进行配置，也可以使用**CsConferencingPolicy** cmdlet 修改现有策略的设置。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="0fbdc-115">设置你的会议策略</span><span class="sxs-lookup"><span data-stu-id="0fbdc-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="0fbdc-116">对于 Skype for Business Online 中的所有会议策略设置，必须使用 Windows PowerShell，并且**不能使用** **Skype for business 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="0fbdc-117">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0fbdc-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="0fbdc-118">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="0fbdc-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="0fbdc-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0fbdc-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="0fbdc-120">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="0fbdc-p103">如果你没有版本3.0 或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。出现提示时，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="0fbdc-p104">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="0fbdc-127">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="0fbdc-128">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="0fbdc-128">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="0fbdc-129">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0fbdc-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="0fbdc-130">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="0fbdc-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
        
        > [!NOTE]
        > <span data-ttu-id="0fbdc-131">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="0fbdc-132">如果需要有关启动 Windows PowerShell 的详细信息，请参阅[在单个 Windows powershell 窗口中连接到所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[设置适用于 Windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="0fbdc-133">在会议期间阻止文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="0fbdc-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="0fbdc-134">若要为这些设置创建新的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="0fbdc-134">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="0fbdc-135">有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0fbdc-136">若要向组织中的所有用户授予您创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="0fbdc-136">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="0fbdc-137">有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="0fbdc-138">如果你已创建策略，你可以使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet 对现有策略进行更改，然后使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="0fbdc-139">阻止录制会议和阻止匿名会议参与者</span><span class="sxs-lookup"><span data-stu-id="0fbdc-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="0fbdc-140">若要为这些设置创建新的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="0fbdc-140">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="0fbdc-141">有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0fbdc-142">若要将您创建的新策略授予 Amos 大理石，请运行：</span><span class="sxs-lookup"><span data-stu-id="0fbdc-142">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="0fbdc-143">有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0fbdc-144">如果你已创建策略，你可以使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet 对现有策略进行更改，然后使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="0fbdc-145">阻止匿名参与者录制会议和外部用户保存会议内容</span><span class="sxs-lookup"><span data-stu-id="0fbdc-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="0fbdc-146">若要为这些设置创建新的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="0fbdc-146">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="0fbdc-147">有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0fbdc-148">若要为你的组织中的所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="0fbdc-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="0fbdc-149">有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0fbdc-150">如果你已创建策略，你可以使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet 对现有策略进行更改，然后使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0fbdc-151">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="0fbdc-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0fbdc-152">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0fbdc-153">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-153">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0fbdc-154">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="0fbdc-154">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0fbdc-155">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="0fbdc-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0fbdc-156">可能希望使用 Windows PowerShell 管理 Office 365 的六个原因</span><span class="sxs-lookup"><span data-stu-id="0fbdc-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0fbdc-157">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="0fbdc-157">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0fbdc-158">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="0fbdc-158">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0fbdc-159">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="0fbdc-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0fbdc-160">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0fbdc-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0fbdc-161">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="0fbdc-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="0fbdc-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="0fbdc-162">Related topics</span></span>
[<span data-ttu-id="0fbdc-163">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="0fbdc-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="0fbdc-164">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="0fbdc-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="0fbdc-165">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="0fbdc-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
