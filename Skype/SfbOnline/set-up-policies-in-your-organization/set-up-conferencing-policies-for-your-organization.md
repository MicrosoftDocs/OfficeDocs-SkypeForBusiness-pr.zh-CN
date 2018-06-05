---
title: 设置为您的组织的会议策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。
ms.openlocfilehash: 9e4c0bc5a90a97ae249b9308fd0ffc62a654a824
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500561"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="5f562-103">设置为您的组织的会议策略</span><span class="sxs-lookup"><span data-stu-id="5f562-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="5f562-104">会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。</span><span class="sxs-lookup"><span data-stu-id="5f562-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="5f562-105">务必要维护对会议的控制和会议设置。</span><span class="sxs-lookup"><span data-stu-id="5f562-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="5f562-106">在有些情况下，可能会有安全问题：默认情况下，任何人（包括未经身份验证的用户）都可以参与会议，并保存在那些会议期间分发的任何幻灯片或讲义。</span><span class="sxs-lookup"><span data-stu-id="5f562-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="5f562-107">此外，偶尔可能有法律问题。</span><span class="sxs-lookup"><span data-stu-id="5f562-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="5f562-108">例如，默认情况下，会议允许参与者共享内容; 上进行注释但是，存档会议时，不会保存这些批注。</span><span class="sxs-lookup"><span data-stu-id="5f562-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="5f562-109">如果你的组织需要保留所有电子通信记录，你可能希望禁用批注。</span><span class="sxs-lookup"><span data-stu-id="5f562-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="5f562-110">业务 online Skype，通过使用会议策略进行管理会议。</span><span class="sxs-lookup"><span data-stu-id="5f562-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="5f562-111">会议策略确定可以在会议中使用的特性和功能，包括从会议是否可以包括 IP 音频和视频到可以参加会议的最大人数等所有内容。</span><span class="sxs-lookup"><span data-stu-id="5f562-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="5f562-112">可以按全局范围或单个用户范围来配置会议策略。</span><span class="sxs-lookup"><span data-stu-id="5f562-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="5f562-113">这为管理员在决定哪些功能可供哪些用户使用时提供了极大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="5f562-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="5f562-114">策略设置可以配置时创建的策略，或者您可以使用**Set-csconferencingpolicy** cmdlet 修改现有的策略的设置。</span><span class="sxs-lookup"><span data-stu-id="5f562-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="5f562-115">设置你的会议策略</span><span class="sxs-lookup"><span data-stu-id="5f562-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="5f562-116">对于所有会议策略的设置中 Skype 业务 online，您必须都使用 Windows PowerShell 和您都**不能都使用****业务管理中心的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="5f562-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="5f562-117">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f562-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="5f562-118">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="5f562-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="5f562-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5f562-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5f562-120">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="5f562-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="5f562-p103">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="5f562-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="5f562-p104">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="5f562-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="5f562-127">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5f562-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="5f562-128">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="5f562-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="5f562-129">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5f562-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5f562-130">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="5f562-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f562-131">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="5f562-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="5f562-132">如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Connecting to Skype 业务 online 使用 Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5f562-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="5f562-133">在会议期间阻止文件传输和桌面共享</span><span class="sxs-lookup"><span data-stu-id="5f562-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="5f562-134">若要创建这些设置的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="5f562-134">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```
  <span data-ttu-id="5f562-135">请参阅有关[-New-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f562-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="5f562-136">若要授予您的组织中的为所有用户创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="5f562-136">To grant the new policy you created to all users in your organization, run:</span></span>
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```
  <span data-ttu-id="5f562-137">请参阅[Grant-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f562-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="5f562-138">如果您已经创建策略，可以使用[Set-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet 可以更改现有的策略，并将[Grant-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet 将设置应用于您的用户。</span><span class="sxs-lookup"><span data-stu-id="5f562-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="5f562-139">阻止录制的会议，并防止匿名会议参与者</span><span class="sxs-lookup"><span data-stu-id="5f562-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="5f562-140">若要创建这些设置的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="5f562-140">To create a new policy for these settings, run:</span></span> 
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```
<span data-ttu-id="5f562-141">请参阅有关[-New-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f562-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="5f562-142">若要授予 Amos 大理石您创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="5f562-142">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```
<span data-ttu-id="5f562-143">请参阅[Grant-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f562-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="5f562-144">如果您已经创建策略，可以使用[Set-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet 可以更改现有的策略，并将[Grant-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet 将设置应用于您的用户。</span><span class="sxs-lookup"><span data-stu-id="5f562-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="5f562-145">阻止匿名参与者录制会议和外部用户保存会议内容</span><span class="sxs-lookup"><span data-stu-id="5f562-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="5f562-146">若要创建这些设置的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="5f562-146">To create a new policy for these settings, run:</span></span>  
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```
<span data-ttu-id="5f562-147">请参阅有关[-New-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f562-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="5f562-148">若要授予对所有用户在组织中都创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="5f562-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

<span data-ttu-id="5f562-149">请参阅[Grant-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f562-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="5f562-150">如果您已经创建策略，可以使用[Set-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet 可以更改现有的策略，并将[Grant-csconferencingpolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet 将设置应用于您的用户。</span><span class="sxs-lookup"><span data-stu-id="5f562-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5f562-151">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="5f562-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5f562-152">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="5f562-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5f562-153">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="5f562-153">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5f562-154">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5f562-154">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5f562-155">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="5f562-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5f562-156">为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）</span><span class="sxs-lookup"><span data-stu-id="5f562-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="5f562-p106">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="5f562-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5f562-159">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="5f562-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="5f562-160">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5f562-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5f562-161">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="5f562-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="5f562-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="5f562-162">Related topics</span></span>
[<span data-ttu-id="5f562-163">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="5f562-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="5f562-164">阻止点对点文件传输</span><span class="sxs-lookup"><span data-stu-id="5f562-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="5f562-165">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="5f562-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 