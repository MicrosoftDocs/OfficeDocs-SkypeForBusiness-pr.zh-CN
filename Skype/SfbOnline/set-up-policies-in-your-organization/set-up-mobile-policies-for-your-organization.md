---
title: 为你的组织设置移动策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: 你可以使用移动设备上的 Skype for Business 应用来设置你的用户如何连接到 Skype for business Online，例如允许用户通过其工作电话号码（而不是移动电话号码）在手机上拨打和接听电话的功能。mber.移动策略还可用于在拨打或接听电话时要求 Wlan 连接。
ms.openlocfilehash: 2d608356e08ae989d0be79bd61f14a4d6ba3b9f0
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887851"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="98e59-104">为你的组织设置移动策略</span><span class="sxs-lookup"><span data-stu-id="98e59-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="98e59-p102">你可以使用移动设备上的 Skype for Business 应用来设置你的用户如何连接到 Skype for business Online，例如允许用户通过其工作电话号码（而不是移动电话号码）在手机上拨打和接听电话的功能。mber.移动策略还可用于在拨打或接听电话时要求 Wlan 连接。</span><span class="sxs-lookup"><span data-stu-id="98e59-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="98e59-107">移动策略设置可以在创建策略时进行配置，也可以使用**CsMobilityPolicy** cmdlet 修改现有策略的设置。</span><span class="sxs-lookup"><span data-stu-id="98e59-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="98e59-108">设置你的移动策略</span><span class="sxs-lookup"><span data-stu-id="98e59-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="98e59-109">对于 Skype for Business Online 中的所有移动策略设置，必须使用 Windows PowerShell，并且**不能使用** **Skype for business 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="98e59-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="98e59-110">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98e59-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="98e59-111">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="98e59-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="98e59-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="98e59-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="98e59-113">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="98e59-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="98e59-p103">如果你没有版本3.0 或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。出现提示时，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="98e59-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="98e59-p104">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="98e59-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="98e59-120">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="98e59-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="98e59-121">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="98e59-121">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="98e59-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="98e59-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="98e59-123">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="98e59-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
        
        > [!NOTE]
        > <span data-ttu-id="98e59-124">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="98e59-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="98e59-125">如果需要有关启动 Windows PowerShell 的详细信息，请参阅[在单个 Windows powershell 窗口中连接到所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[设置适用于 Windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="98e59-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="98e59-126">要求用户进行视频操作时使用 WiFi 连接</span><span class="sxs-lookup"><span data-stu-id="98e59-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="98e59-127">若要为这些设置创建新的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="98e59-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="98e59-128">有关[CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="98e59-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="98e59-129">若要为你的组织中的所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="98e59-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="98e59-130">有关[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="98e59-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="98e59-131">如果你已创建策略，你可以使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet 对现有策略进行更改，然后使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="98e59-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="98e59-132">禁止用户使用 Skype for Business 应用</span><span class="sxs-lookup"><span data-stu-id="98e59-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="98e59-133">若要为这些设置创建新的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="98e59-133">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="98e59-134">有关[CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="98e59-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="98e59-135">若要将您创建的新策略授予 Amos 大理石，请运行：</span><span class="sxs-lookup"><span data-stu-id="98e59-135">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="98e59-136">有关[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="98e59-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="98e59-137">如果你已创建策略，你可以使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet 对现有策略进行更改，然后使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="98e59-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="98e59-138">禁止用户使用移动设备拨打 IP 语音电话。</span><span class="sxs-lookup"><span data-stu-id="98e59-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="98e59-139">若要为这些设置创建新的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="98e59-139">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="98e59-140">有关[CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="98e59-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="98e59-141">若要为你的组织中的所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="98e59-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="98e59-142">有关[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="98e59-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="98e59-143">如果你已创建策略，你可以使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet 对现有策略进行更改，然后使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="98e59-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="98e59-144">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="98e59-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="98e59-145">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="98e59-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="98e59-146">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="98e59-146">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="98e59-147">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="98e59-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="98e59-148">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="98e59-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="98e59-149">可能希望使用 Windows PowerShell 管理 Office 365 的六个原因</span><span class="sxs-lookup"><span data-stu-id="98e59-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="98e59-150">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="98e59-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="98e59-151">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="98e59-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="98e59-152">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="98e59-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="98e59-153">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="98e59-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="98e59-154">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="98e59-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="98e59-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="98e59-155">Related topics</span></span>
[<span data-ttu-id="98e59-156">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="98e59-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="98e59-157">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="98e59-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="98e59-158">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="98e59-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="98e59-159">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="98e59-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
