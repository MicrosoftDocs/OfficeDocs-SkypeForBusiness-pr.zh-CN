---
title: 为你的组织设置客户端策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: 客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814351"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="12280-103">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="12280-103">Set up client policies for your organization</span></span>

<span data-ttu-id="12280-104">客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="12280-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="12280-105">客户端策略设置可以在创建策略时配置，也可以使用 **set-csclientpolicy** cmdlet 修改现有策略的设置。</span><span class="sxs-lookup"><span data-stu-id="12280-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="12280-106">设置你的客户端策略</span><span class="sxs-lookup"><span data-stu-id="12280-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="12280-107">对于 Skype for Business Online 中的所有客户端策略设置，必须使用 Windows PowerShell，并且 **不能使用** **Skype for business 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="12280-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="12280-108">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12280-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="12280-109">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="12280-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="12280-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="12280-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="12280-111">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="12280-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="12280-p101">如果你没有版本3.0 或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 windows PowerShell 并将其更新到版本4.0。出现提示时，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="12280-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="12280-115">你还需要为团队安装 Windows PowerShell 模块，使你能够创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="12280-115">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="12280-116">如果需要了解详细信息，请参阅 [在单个 Windows PowerShell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="12280-116">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="12280-117">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="12280-117">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="12280-118">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="12280-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="12280-119">在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="12280-119">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12280-120">Skype for Business Online 连接器目前是最新团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="12280-120">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="12280-121">如果您使用的是最新的 [团队 PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="12280-121">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
<span data-ttu-id="12280-122">如果需要有关启动 Windows PowerShell 的详细信息，请参阅 [在单个 Windows powershell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx) 或 [设置适用于 windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="12280-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="12280-123">禁用表情符和状态通知并阻止保存 Im</span><span class="sxs-lookup"><span data-stu-id="12280-123">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="12280-124">若要为这些设置创建新的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="12280-124">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="12280-125">有关 [set-csclientpolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="12280-125">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="12280-126">若要为你的组织中的所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="12280-126">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="12280-127">有关 [set-csclientpolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="12280-127">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="12280-128">如果你已创建策略，你可以使用 [set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet 对现有策略进行更改，然后使用 [set-csclientpolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="12280-128">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="12280-129">启用要在即时消息中可单击的 URL 或超链接</span><span class="sxs-lookup"><span data-stu-id="12280-129">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="12280-130">若要为这些设置创建新的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="12280-130">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="12280-131">有关 [set-csclientpolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="12280-131">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="12280-132">若要为你的组织中的所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="12280-132">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="12280-133">有关 [set-csclientpolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="12280-133">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="12280-134">如果你已创建策略，你可以使用 [set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet 对现有策略进行更改，然后使用 [set-csclientpolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="12280-134">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="12280-135">禁止显示最近的联系人</span><span class="sxs-lookup"><span data-stu-id="12280-135">Prevent showing recent contacts</span></span>

- <span data-ttu-id="12280-136">若要为这些设置创建新的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="12280-136">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="12280-137">有关 [set-csclientpolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="12280-137">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="12280-138">若要将您创建的新策略授予 Amos 大理石，请运行：</span><span class="sxs-lookup"><span data-stu-id="12280-138">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="12280-139">有关 [set-csclientpolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="12280-139">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="12280-140">如果你已创建策略，你可以使用 [set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet 对现有策略进行更改，然后使用 [set-csclientpolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="12280-140">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="12280-141">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="12280-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="12280-142">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="12280-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="12280-143">使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365 和 Skype for business Online，这样你有多个任务可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="12280-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="12280-144">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="12280-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="12280-145">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="12280-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="12280-146">可能希望使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六个原因</span><span class="sxs-lookup"><span data-stu-id="12280-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="12280-147">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="12280-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="12280-148">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="12280-148">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="12280-149">通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="12280-149">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="12280-150">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="12280-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="12280-151">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="12280-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="12280-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="12280-152">Related topics</span></span>
[<span data-ttu-id="12280-153">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="12280-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="12280-154">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="12280-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="12280-155">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="12280-155">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
