---
title: 阻止点到点文件传输
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: 在 Skype for Business Online 中，你可以将点到点 (P2P) 文件传输控制为现有会议策略设置的一部分。 但是，这将允许或阻止用户将文件传输到同一组织中的用户或其他组织中的联盟用户。 按照以下步骤，你可以阻止联盟组织或合作伙伴的 P2P 文件传输。
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814631"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="7b82a-105">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="7b82a-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="7b82a-106">在 Skype for Business Online 中，你可以将点到点 (P2P) 文件传输控制为现有会议策略设置的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b82a-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="7b82a-107">但是，这将允许或阻止用户将文件传输到同一组织中的用户或其他组织中的联盟用户。</span><span class="sxs-lookup"><span data-stu-id="7b82a-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="7b82a-108">按照以下步骤，你可以阻止联盟组织或合作伙伴的 P2P 文件传输。</span><span class="sxs-lookup"><span data-stu-id="7b82a-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="7b82a-109">最常见的情况是，您希望允许内部用户使用 P2P 文件传输，但阻止与联盟伙伴进行的文件传输。</span><span class="sxs-lookup"><span data-stu-id="7b82a-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="7b82a-110">对于此方案，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b82a-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="7b82a-111">为组织中的用户将 (_EnableP2PFileTransfer_ 设置为 _True_) 的会议策略分配了 P2P 文件传输。</span><span class="sxs-lookup"><span data-stu-id="7b82a-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="7b82a-112">创建全局外部用户通信策略集以阻止外部 P2P 文件传输 (_EnableP2PFileTransfer_ 设置为 _False_) 并将其分配给组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="7b82a-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="7b82a-113">你可以在 [此处](https://technet.microsoft.com/library/mt228132.aspx)了解有关这些设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7b82a-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="7b82a-114">如果组织外部的联盟用户尝试将文件发送到已应用策略的用户，则它们将收到 " **传输失败** " 错误。</span><span class="sxs-lookup"><span data-stu-id="7b82a-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="7b82a-115">如果用户尝试发送文件，他们将收到 " **已关闭文件传输** " 错误。</span><span class="sxs-lookup"><span data-stu-id="7b82a-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="7b82a-116">若要执行此操作，用户必须使用支持版本的2016即点即用 Skype for business 应用（支持它）。</span><span class="sxs-lookup"><span data-stu-id="7b82a-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="7b82a-117">需要以下最低版本的 Skype for Business 2016 即点即用客户端：</span><span class="sxs-lookup"><span data-stu-id="7b82a-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="7b82a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="7b82a-118">**Type**</span></span>|<span data-ttu-id="7b82a-119">**发布日期**</span><span class="sxs-lookup"><span data-stu-id="7b82a-119">**Release date**</span></span>|<span data-ttu-id="7b82a-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="7b82a-120">**Version**</span></span>|<span data-ttu-id="7b82a-121">**版本号**</span><span class="sxs-lookup"><span data-stu-id="7b82a-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b82a-122">当前频道的首次发布</span><span class="sxs-lookup"><span data-stu-id="7b82a-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="7b82a-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="7b82a-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="7b82a-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="7b82a-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="7b82a-125">版本 1611 (内部版本 7571.2006) </span><span class="sxs-lookup"><span data-stu-id="7b82a-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="7b82a-126">当前频道</span><span class="sxs-lookup"><span data-stu-id="7b82a-126">Current Channel</span></span>  <br/> |<span data-ttu-id="7b82a-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="7b82a-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="7b82a-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="7b82a-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="7b82a-129">版本 1611 (内部版本 7571.2072) </span><span class="sxs-lookup"><span data-stu-id="7b82a-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="7b82a-130">延期频道</span><span class="sxs-lookup"><span data-stu-id="7b82a-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="7b82a-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="7b82a-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="7b82a-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="7b82a-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="7b82a-133">版本 1609 (内部版本 7369.2118) </span><span class="sxs-lookup"><span data-stu-id="7b82a-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="7b82a-134">使用旧版本的 Skype for Business Windows 应用或 Mac 客户端的用户仍能传输文件。</span><span class="sxs-lookup"><span data-stu-id="7b82a-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="7b82a-135">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b82a-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="7b82a-136">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="7b82a-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="7b82a-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7b82a-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="7b82a-138">通过在**Windows PowerShell**窗口中键入_Get Host_检查版本。</span><span class="sxs-lookup"><span data-stu-id="7b82a-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="7b82a-139">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="7b82a-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="7b82a-140">请参阅 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 windows PowerShell 并将其更新到版本4.0。</span><span class="sxs-lookup"><span data-stu-id="7b82a-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="7b82a-141">出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="7b82a-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="7b82a-142">你还需要为团队安装 Windows PowerShell 模块，使你能够创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="7b82a-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="7b82a-143">如果需要了解详细信息，请参阅 [在单个 Windows PowerShell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7b82a-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="7b82a-144">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="7b82a-144">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="7b82a-145">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7b82a-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="7b82a-146">在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="7b82a-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="7b82a-147">Skype for Business Online 连接器目前是最新团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b82a-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
        >
        > <span data-ttu-id="7b82a-148">如果您使用的是最新的 [团队 PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="7b82a-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="7b82a-149">如果需要有关启动 Windows PowerShell 的详细信息，请参阅 [在单个 Windows powershell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx) 或 [设置适用于 windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="7b82a-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="7b82a-150">为你的组织禁用 P2P 文件传输</span><span class="sxs-lookup"><span data-stu-id="7b82a-150">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="7b82a-151">默认情况下，在组织的全局策略上启用 _EnableP2PFileTransfer_ 。</span><span class="sxs-lookup"><span data-stu-id="7b82a-151">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="7b82a-152">创建后，您的用户被分配了 _BposSAllModality_ 策略。</span><span class="sxs-lookup"><span data-stu-id="7b82a-152">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="7b82a-153">若要允许组织内部的 P2P 传输，但阻止外部文件传输到另一个组织，只需在全局级别进行更改即可。</span><span class="sxs-lookup"><span data-stu-id="7b82a-153">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="7b82a-154">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="7b82a-154">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="7b82a-155">为用户禁用 P2P 文件传输</span><span class="sxs-lookup"><span data-stu-id="7b82a-155">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="7b82a-156">你可以通过创建新策略并将其授予该用户来将其应用到用户。</span><span class="sxs-lookup"><span data-stu-id="7b82a-156">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="7b82a-157">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="7b82a-157">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7b82a-158">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="7b82a-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="7b82a-159">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="7b82a-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7b82a-160">使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365 和 Skype for business Online，这样你有多个任务可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="7b82a-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="7b82a-161">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="7b82a-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7b82a-162">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="7b82a-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7b82a-163">为什么需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b82a-163">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="7b82a-164">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="7b82a-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="7b82a-165">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="7b82a-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7b82a-166">通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="7b82a-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="7b82a-167">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7b82a-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7b82a-168">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="7b82a-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="7b82a-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="7b82a-169">Related topics</span></span>
[<span data-ttu-id="7b82a-170">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="7b82a-170">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="7b82a-171">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="7b82a-171">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="7b82a-172">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="7b82a-172">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
