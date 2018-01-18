---
title: "设置您的组织的移动策略"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "您可以设置如何您的用户连接到 Skype 的在线业务的业务应用程序等功能，使用户可以拨打和接听电话在他们的移动电话而不是他们的移动电话 nu 通过其单位电话号码的移动设备上使用 Skypember。 移动策略还可以用于需要 Wi-Fi 连接发出或接收呼叫时。"
ms.openlocfilehash: 0772091e33043ed9ce5019b5c26ec8857d158260
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="95743-104">设置您的组织的移动策略</span><span class="sxs-lookup"><span data-stu-id="95743-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="95743-105">您可以设置如何您的用户连接到 Skype 的在线业务的业务应用程序等功能，使用户可以拨打和接听电话在他们的移动电话而不是他们的移动电话 nu 通过其单位电话号码的移动设备上使用 Skypember。</span><span class="sxs-lookup"><span data-stu-id="95743-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="95743-106">移动策略还可以用于需要 Wi-Fi 连接发出或接收呼叫时。</span><span class="sxs-lookup"><span data-stu-id="95743-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="95743-107">移动的策略设置可以配置在创建策略时，也可以使用**一组 CsMobilityPolicy** cmdlet 要修改的现有策略设置。</span><span class="sxs-lookup"><span data-stu-id="95743-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="95743-108">设置你的移动策略</span><span class="sxs-lookup"><span data-stu-id="95743-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="95743-109">对于所有的移动策略设置在 Skype 业务联机，您必须使用 Windows PowerShell 并且您**不能使用** **Skype 的业务管理中心**。</span><span class="sxs-lookup"><span data-stu-id="95743-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="95743-110">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95743-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="95743-111">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="95743-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="95743-112">若要验证正在运行版本 3.0 或更高: **「 开始 」 菜单** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="95743-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="95743-113">通过在" **Windows PowerShell**"窗口中键入  _Get-Host_ 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="95743-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="95743-p103">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="95743-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="95743-p104">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="95743-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="95743-120">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="95743-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="95743-121">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="95743-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="95743-122">从**「 开始 」 菜单** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="95743-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="95743-123">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="95743-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="95743-124">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="95743-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="95743-125">如果希望在启动 Windows PowerShell 的详细信息，请参阅[连接到一个 Windows PowerShell 窗口中的所有 Office 365 提供服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[连接到使用 Windows PowerShell 在线业务 Skype](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="95743-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="95743-126">要求用户进行视频操作时使用 WiFi 连接</span><span class="sxs-lookup"><span data-stu-id="95743-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="95743-127">若要创建新的策略，这些设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="95743-127">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  <span data-ttu-id="95743-128">请参阅详细信息[新建 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95743-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="95743-129">若要授予组织中为所有用户都创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="95743-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  <span data-ttu-id="95743-130">请参阅详细信息[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95743-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="95743-131">如果您已经创建一个策略，可以使用[一组 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet 可以更改现有的策略，并将[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 将设置应用到您的用户。</span><span class="sxs-lookup"><span data-stu-id="95743-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="95743-132">禁止用户使用 Skype for Business 应用</span><span class="sxs-lookup"><span data-stu-id="95743-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="95743-133">若要创建新的策略，这些设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="95743-133">To create a new policy for these settings, run:</span></span>
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  <span data-ttu-id="95743-134">请参阅详细信息[新建 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95743-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="95743-135">若要创建新策略授予 Amos 大理石，运行：</span><span class="sxs-lookup"><span data-stu-id="95743-135">To grant the new policy you created to Amos Marble, run:</span></span>  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  <span data-ttu-id="95743-136">请参阅详细信息[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95743-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="95743-137">如果您已经创建一个策略，可以使用[一组 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet 可以更改现有的策略，并将[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 将设置应用到您的用户。</span><span class="sxs-lookup"><span data-stu-id="95743-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="95743-138">禁止用户使用移动设备拨打 IP 语音电话。</span><span class="sxs-lookup"><span data-stu-id="95743-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="95743-139">若要创建新的策略，这些设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="95743-139">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  <span data-ttu-id="95743-140">请参阅详细信息[新建 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95743-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="95743-141">若要授予组织中为所有用户都创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="95743-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  <span data-ttu-id="95743-142">请参阅详细信息[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95743-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="95743-143">如果您已经创建一个策略，可以使用[一组 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet 可以更改现有的策略，并将[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 将设置应用到您的用户。</span><span class="sxs-lookup"><span data-stu-id="95743-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="95743-144">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="95743-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="95743-p105">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="95743-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="95743-148">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="95743-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="95743-149">为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）</span><span class="sxs-lookup"><span data-stu-id="95743-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="95743-p106">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="95743-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="95743-152">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="95743-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="95743-153">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95743-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="95743-154">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="95743-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="95743-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="95743-155">Related topics</span></span>
[<span data-ttu-id="95743-156">创建自定义的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="95743-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="95743-157">块的点对点文件传输</span><span class="sxs-lookup"><span data-stu-id="95743-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="95743-158">设置您的组织的客户端策略</span><span class="sxs-lookup"><span data-stu-id="95743-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="95743-159">设置您的组织中的会议策略</span><span class="sxs-lookup"><span data-stu-id="95743-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

