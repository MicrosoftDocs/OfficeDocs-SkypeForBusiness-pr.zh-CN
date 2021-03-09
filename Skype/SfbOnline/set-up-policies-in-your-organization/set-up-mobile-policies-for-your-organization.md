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
description: 你可以设置你的用户如何在移动设备上使用 Skype for Business 应用连接到 Skype for Business Online，例如允许用户使用工作电话号码而不是移动电话号码在移动电话上拨打和接听电话的功能。 还需要使用移动策略来要求在拨打或接听电话时使用 Wi-Fi 连接。
ms.openlocfilehash: 36162c64490edf58bbfac5c7022bebf6f39595ca
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569194"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="7e367-104">为你的组织设置移动策略</span><span class="sxs-lookup"><span data-stu-id="7e367-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="7e367-105">你可以设置你的用户如何在移动设备上使用 Skype for Business 应用连接到 Skype for Business Online，例如允许用户使用工作电话号码而不是移动电话号码在移动电话上拨打和接听电话的功能。</span><span class="sxs-lookup"><span data-stu-id="7e367-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="7e367-106">还需要使用移动策略来要求在拨打或接听电话时使用 Wi-Fi 连接。</span><span class="sxs-lookup"><span data-stu-id="7e367-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="7e367-107">可以在创建策略时配置移动策略设置，或者可以使用 **Set-CsMobilityPolicy** cmdlet 修改现有策略的设置。</span><span class="sxs-lookup"><span data-stu-id="7e367-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="7e367-108">设置你的移动策略</span><span class="sxs-lookup"><span data-stu-id="7e367-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="7e367-109">对于 Skype for Business Online 中的所有移动策略设置，必须使用 Windows PowerShell 并且不能使用 Skype **for Business 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="7e367-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="7e367-110">启动Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e367-110">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="7e367-111">Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="7e367-111">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="7e367-112">如果你使用的是最新的 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="7e367-112">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="7e367-113">安装 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="7e367-113">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="7e367-114">打开Windows PowerShell提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7e367-114">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="7e367-115">如果需要有关启动 Windows PowerShell，请参阅"在单个 Windows PowerShell 窗口中连接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服务，或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="7e367-115">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="7e367-116">要求用户进行视频操作时使用 WiFi 连接</span><span class="sxs-lookup"><span data-stu-id="7e367-116">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="7e367-117">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="7e367-117">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="7e367-118">详细了解 [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7e367-118">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7e367-119">若要向组织中所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="7e367-119">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="7e367-120">详细了解 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7e367-120">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="7e367-121">如果已创建策略，可以使用 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet 更改现有策略，然后使用[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="7e367-121">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="7e367-122">禁止用户使用 Skype for Business 应用</span><span class="sxs-lookup"><span data-stu-id="7e367-122">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="7e367-123">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="7e367-123">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="7e367-124">详细了解 [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7e367-124">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7e367-125">若要向 Amos Marble 授予创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="7e367-125">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="7e367-126">详细了解 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7e367-126">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="7e367-127">如果已创建策略，可以使用 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet 更改现有策略，然后使用 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="7e367-127">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="7e367-128">禁止用户使用移动设备拨打 IP 语音电话。</span><span class="sxs-lookup"><span data-stu-id="7e367-128">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="7e367-129">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="7e367-129">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="7e367-130">详细了解 [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7e367-130">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7e367-131">若要向组织中所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="7e367-131">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="7e367-132">详细了解 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7e367-132">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="7e367-133">如果已创建策略，可以使用 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet 更改现有策略，然后使用[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="7e367-133">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7e367-134">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="7e367-134">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="7e367-135">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="7e367-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7e367-136">借助Windows PowerShell，当你有多个任务需要执行时，可以使用单点管理来管理 Microsoft 365 或 Office 365 和 Skype for Business Online，从而简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="7e367-136">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="7e367-137">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="7e367-137">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7e367-138">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="7e367-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7e367-139">你可能想要使用 office 365 Windows PowerShell Office 365 的六大原因</span><span class="sxs-lookup"><span data-stu-id="7e367-139">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="7e367-140">Windows PowerShell使用 Microsoft 365 管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次对多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="7e367-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="7e367-141">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="7e367-141">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7e367-142">使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e367-142">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="7e367-143">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7e367-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7e367-144">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="7e367-144">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="7e367-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="7e367-145">Related topics</span></span>
[<span data-ttu-id="7e367-146">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="7e367-146">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="7e367-147">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="7e367-147">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="7e367-148">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="7e367-148">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="7e367-149">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="7e367-149">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
