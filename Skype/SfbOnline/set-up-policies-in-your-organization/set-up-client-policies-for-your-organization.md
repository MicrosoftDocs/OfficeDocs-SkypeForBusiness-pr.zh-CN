---
title: 设置您的组织的客户端策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: 客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。
ms.openlocfilehash: 98bf7f0dba39e7fd56a0b6dd79600245eec4b7da
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="f5657-103">设置您的组织的客户端策略</span><span class="sxs-lookup"><span data-stu-id="f5657-103">Set up client policies for your organization</span></span>

<span data-ttu-id="f5657-104">客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="f5657-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="f5657-105">客户端策略设置可以配置在创建策略时，也可以使用**一组 CsClientPolicy** cmdlet 要修改的现有策略设置。</span><span class="sxs-lookup"><span data-stu-id="f5657-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="f5657-106">设置你的客户端策略</span><span class="sxs-lookup"><span data-stu-id="f5657-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="f5657-107">对于所有客户端策略中设置的 Skype 的在线业务，您必须使用 Windows PowerShell 并且您**不能使用** **Skype 的业务管理中心**。</span><span class="sxs-lookup"><span data-stu-id="f5657-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="f5657-108">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5657-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="f5657-109">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="f5657-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="f5657-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f5657-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f5657-111">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="f5657-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="f5657-p101">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="f5657-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="f5657-p102">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="f5657-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="f5657-118">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f5657-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="f5657-119">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="f5657-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="f5657-120">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f5657-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f5657-121">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="f5657-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f5657-122">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="f5657-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="f5657-123">如果希望在启动 Windows PowerShell 的详细信息，请参阅[连接到一个 Windows PowerShell 窗口中的所有 Office 365 提供服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[连接到使用 Windows PowerShell 在线业务 Skype](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f5657-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="f5657-124">禁用图释和状态通知并防止保存的即时消息</span><span class="sxs-lookup"><span data-stu-id="f5657-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="f5657-125">若要创建新的策略，这些设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="f5657-125">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  <span data-ttu-id="f5657-126">请参阅详细信息[新建 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5657-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f5657-127">若要授予组织中为所有用户都创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="f5657-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  <span data-ttu-id="f5657-128">请参阅详细信息[授予 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5657-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="f5657-129">如果您已经创建一个策略，可以使用[一组 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet 可以更改现有的策略，并将[授予 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 将设置应用于您的用户。</span><span class="sxs-lookup"><span data-stu-id="f5657-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="f5657-130">启用要在即时消息中可单击的 URL 或超链接</span><span class="sxs-lookup"><span data-stu-id="f5657-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="f5657-131">若要创建新的策略，这些设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="f5657-131">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  <span data-ttu-id="f5657-132">请参阅详细信息[新建 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5657-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f5657-133">若要授予组织中为所有用户都创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="f5657-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  <span data-ttu-id="f5657-134">请参阅详细信息[授予 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5657-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="f5657-135">如果您已经创建一个策略，可以使用[一组 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet 可以更改现有的策略，并将[授予 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 将设置应用于您的用户。</span><span class="sxs-lookup"><span data-stu-id="f5657-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="f5657-136">禁止显示最近的联系人</span><span class="sxs-lookup"><span data-stu-id="f5657-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="f5657-137">若要创建新的策略，这些设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="f5657-137">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  <span data-ttu-id="f5657-138">请参阅详细信息[新建 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5657-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f5657-139">若要创建新策略授予 Amos 大理石，运行：</span><span class="sxs-lookup"><span data-stu-id="f5657-139">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  <span data-ttu-id="f5657-140">请参阅详细信息[授予 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5657-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="f5657-141">如果您已经创建一个策略，可以使用[一组 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet 可以更改现有的策略，并将[授予 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 将设置应用于您的用户。</span><span class="sxs-lookup"><span data-stu-id="f5657-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f5657-142">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="f5657-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="f5657-p103">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f5657-p103">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f5657-146">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="f5657-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f5657-147">为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）</span><span class="sxs-lookup"><span data-stu-id="f5657-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f5657-p104">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="f5657-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f5657-150">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="f5657-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f5657-151">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f5657-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f5657-152">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="f5657-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="f5657-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="f5657-153">Related topics</span></span>
[<span data-ttu-id="f5657-154">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="f5657-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="f5657-155">块的点对点文件传输</span><span class="sxs-lookup"><span data-stu-id="f5657-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="f5657-156">设置您的组织中的会议策略</span><span class="sxs-lookup"><span data-stu-id="f5657-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 