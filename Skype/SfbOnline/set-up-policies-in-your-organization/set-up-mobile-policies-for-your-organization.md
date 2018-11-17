---
title: 为你的组织设置移动策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 您可以设置如何您的用户连接到 Skype 业务 online 对等功能使用户能够发起和接收电话呼叫在其移动电话上使用而不是其移动电话 nu 其单位电话号码的移动设备上的业务应用程序使用 Skypember。 还需要使用移动策略来要求在拨打或接听电话时使用 Wi-Fi 连接。
ms.openlocfilehash: 7985dc1a1dcdbad63d1c302be8054efb904ac15b
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561599"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="83504-104">为你的组织设置移动策略</span><span class="sxs-lookup"><span data-stu-id="83504-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="83504-105">您可以设置如何您的用户连接到 Skype 业务 online 对等功能使用户能够发起和接收电话呼叫在其移动电话上使用而不是其移动电话 nu 其单位电话号码的移动设备上的业务应用程序使用 Skypember。</span><span class="sxs-lookup"><span data-stu-id="83504-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="83504-106">还需要使用移动策略来要求在拨打或接听电话时使用 Wi-Fi 连接。</span><span class="sxs-lookup"><span data-stu-id="83504-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="83504-107">移动策略设置可以配置时创建的策略，或者您可以使用**Set-csmobilitypolicy** cmdlet 修改现有的策略的设置。</span><span class="sxs-lookup"><span data-stu-id="83504-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="83504-108">设置你的移动策略</span><span class="sxs-lookup"><span data-stu-id="83504-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="83504-109">对于所有业务 online Skype 中的移动策略设置，您必须都使用 Windows PowerShell 和您都**不能都使用\*\*\*\*业务管理中心的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="83504-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="83504-110">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="83504-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="83504-111">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="83504-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="83504-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="83504-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="83504-113">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="83504-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="83504-p103">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="83504-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="83504-p104">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="83504-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="83504-120">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="83504-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="83504-121">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="83504-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="83504-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="83504-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="83504-123">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="83504-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="83504-124">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="83504-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="83504-125">如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Windows PowerShell 将计算机设置](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="83504-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="83504-126">要求用户进行视频操作时使用 WiFi 连接</span><span class="sxs-lookup"><span data-stu-id="83504-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="83504-127">若要创建这些设置的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="83504-127">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  > ```
  > <span data-ttu-id="83504-128">请参阅[New-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="83504-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="83504-129">若要授予对所有用户在组织中都创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="83504-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
  > 
  > ```
  > Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  > ```
  > <span data-ttu-id="83504-130">请参阅[Grant-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="83504-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="83504-131">如果您已经创建策略，您可以使用[Set-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet 可以更改现有的策略，并将[Grant-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 将设置应用到您的用户。</span><span class="sxs-lookup"><span data-stu-id="83504-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="83504-132">禁止用户使用 Skype for Business 应用</span><span class="sxs-lookup"><span data-stu-id="83504-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="83504-133">若要创建这些设置的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="83504-133">To create a new policy for these settings, run:</span></span>
  ```
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="83504-134">请参阅[New-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="83504-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="83504-135">若要授予 Amos 大理石您创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="83504-135">To grant the new policy you created to Amos Marble, run:</span></span>  
  > 
  > ```
  > Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  > ```
  > <span data-ttu-id="83504-136">请参阅[Grant-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="83504-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="83504-137">如果您已经创建策略，您可以使用[Set-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet 可以更改现有的策略，并将[Grant-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 将设置应用到您的用户。</span><span class="sxs-lookup"><span data-stu-id="83504-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="83504-138">禁止用户使用移动设备拨打 IP 语音电话。</span><span class="sxs-lookup"><span data-stu-id="83504-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="83504-139">若要创建这些设置的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="83504-139">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  > ```
  > <span data-ttu-id="83504-140">请参阅[New-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="83504-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="83504-141">若要授予对所有用户在组织中都创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="83504-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
  > 
  > ```
  > Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  > ```

  <span data-ttu-id="83504-142">请参阅[Grant-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="83504-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="83504-143">如果您已经创建策略，您可以使用[Set-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet 可以更改现有的策略，并将[Grant-csmobilitypolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 将设置应用到您的用户。</span><span class="sxs-lookup"><span data-stu-id="83504-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="83504-144">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="83504-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="83504-145">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="83504-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="83504-146">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="83504-146">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="83504-147">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="83504-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="83504-148">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="83504-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="83504-149">为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）</span><span class="sxs-lookup"><span data-stu-id="83504-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="83504-p106">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="83504-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="83504-152">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="83504-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="83504-153">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="83504-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="83504-154">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="83504-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="83504-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="83504-155">Related topics</span></span>
[<span data-ttu-id="83504-156">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="83504-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="83504-157">阻止点对点文件传输</span><span class="sxs-lookup"><span data-stu-id="83504-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="83504-158">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="83504-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="83504-159">设置您的组织中的会议策略</span><span class="sxs-lookup"><span data-stu-id="83504-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 