---
title: 打开或关闭允许使用 Outlook 为会议预加载内容
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 079d0642158aa6d28b3c92a63e77afa0a0024d94
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814581"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="eda33-103">打开或关闭允许使用 Outlook 为会议预加载内容</span><span class="sxs-lookup"><span data-stu-id="eda33-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="eda33-104">用户可以将附加到 Outlook 会议邀请的内容、文件或附件预加载到 Skype for business Online 会议，但您可以打开或关闭它。</span><span class="sxs-lookup"><span data-stu-id="eda33-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="eda33-105">默认情况下，它为使用 Skype for Business Online 的所有组织打开。</span><span class="sxs-lookup"><span data-stu-id="eda33-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="eda33-106">请参阅如何[为 Skype for Business 会议预加载附件](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。</span><span class="sxs-lookup"><span data-stu-id="eda33-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eda33-107">目前，Skype for Business Online 中没有可用的 cmdlet，无法设置或查看  _MaxContentStorageMB_ 和 _MaxUploadFileMB_的在线值。</span><span class="sxs-lookup"><span data-stu-id="eda33-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="eda33-108">它们仅适用于本地部署。</span><span class="sxs-lookup"><span data-stu-id="eda33-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="eda33-109">如果附件内容超过  _MaxUploadFileSizeMB_ 或 _MaxContentStorageMB_ 限额，请务必知道内容不会上载到会议。</span><span class="sxs-lookup"><span data-stu-id="eda33-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="eda33-110">开始使用</span><span class="sxs-lookup"><span data-stu-id="eda33-110">To get you started</span></span>

### 

 <span data-ttu-id="eda33-111">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="eda33-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="eda33-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="eda33-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="eda33-113">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="eda33-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="eda33-114">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="eda33-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="eda33-115">请参阅 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 windows PowerShell 并将其更新到版本4.0。</span><span class="sxs-lookup"><span data-stu-id="eda33-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="eda33-116">出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="eda33-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="eda33-p104">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="eda33-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="eda33-120">如果需要了解详细信息，请参阅 [在单个 Windows PowerShell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="eda33-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="eda33-121">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="eda33-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="eda33-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="eda33-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="eda33-123">在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="eda33-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
> [!NOTE]
> <span data-ttu-id="eda33-124">Skype for Business Online 连接器目前是最新团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="eda33-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="eda33-125">如果您使用的是最新的 [团队 PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="eda33-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
  
```PowerShell
Import-Module -Name MicrosoftTeams
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="eda33-126">如果需要有关启动 Windows PowerShell 的详细信息，请参阅 [在单个 Windows powershell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx) 或 [设置适用于 windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="eda33-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="eda33-127">打开或关闭该功能</span><span class="sxs-lookup"><span data-stu-id="eda33-127">Turning it on or off</span></span>

<span data-ttu-id="eda33-128">默认情况下，可以预加载到 Skype for business Online 会议邀请的 Outlook 会议邀请的内容处于打开状态，但你可能需要阻止组织中的用户在其会议中预加载内容。</span><span class="sxs-lookup"><span data-stu-id="eda33-128">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eda33-129">此设置仅可为您的整个组织打开或关闭;不能为单个用户打开或关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="eda33-129">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="eda33-130">**若要将其关闭，请打开 Windows PowerShell 并执行下列操作：**</span><span class="sxs-lookup"><span data-stu-id="eda33-130">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="eda33-131">**如果想要将其重新打开，请打开 Windows PowerShell 并执行下列操作：**</span><span class="sxs-lookup"><span data-stu-id="eda33-131">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="eda33-132">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="eda33-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="eda33-133">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="eda33-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="eda33-134">使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365 和 Skype for business Online，这样你有多个任务可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="eda33-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="eda33-135">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="eda33-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eda33-136">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="eda33-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="eda33-137">可能希望使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六个原因</span><span class="sxs-lookup"><span data-stu-id="eda33-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="eda33-138">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="eda33-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="eda33-139">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="eda33-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="eda33-140">通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="eda33-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="eda33-141">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eda33-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="eda33-142">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="eda33-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="eda33-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="eda33-143">Related topics</span></span>
[<span data-ttu-id="eda33-144">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eda33-144">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="eda33-145">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="eda33-145">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
