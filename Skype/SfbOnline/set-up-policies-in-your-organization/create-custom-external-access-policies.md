---
title: 创建自定义外部访问策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype for business Online 允许您创建其他外部访问策略。 与客户端或会议策略（你可以有多个组合）不同，有三个预定义的外部访问策略可涵盖大多数方案。
ms.openlocfilehash: 02fba48a6b8acf2a2b66078624ab36eb7453df0c
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164641"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="79740-104">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="79740-104">Create custom external access policies</span></span>

<span data-ttu-id="79740-105">Skype for business Online 允许您创建其他外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="79740-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="79740-106">与客户端或会议策略（你可以有多个组合）不同，有三个预定义的外部访问策略可涵盖大多数方案。</span><span class="sxs-lookup"><span data-stu-id="79740-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="79740-107">包括：</span><span class="sxs-lookup"><span data-stu-id="79740-107">These are:</span></span>
  
- <span data-ttu-id="79740-108">无联盟或 Skype 消费者访问权限（_标记： NoFederationAndPIC_ ）</span><span class="sxs-lookup"><span data-stu-id="79740-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="79740-109">仅限联盟访问（_标记： FederationOnly_ ）</span><span class="sxs-lookup"><span data-stu-id="79740-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="79740-110">联盟和使用者访问（_FederationAndPICDefault_）</span><span class="sxs-lookup"><span data-stu-id="79740-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="79740-111">自定义外部策略允许你创建上述设置未涵盖的其他策略。</span><span class="sxs-lookup"><span data-stu-id="79740-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="79740-112">创建策略时，需要设置所有必需的参数，并且以后无法更改它们。</span><span class="sxs-lookup"><span data-stu-id="79740-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="79740-113">创建新的自定义策略使你能够控制 Skype 消费者访问等功能或禁用公共云音频/视频的策略，这些功能不属于预定义设置。</span><span class="sxs-lookup"><span data-stu-id="79740-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="79740-114">自定义外部访问策略遵循与客户端、移动性和会议策略相同的语法。</span><span class="sxs-lookup"><span data-stu-id="79740-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="79740-115">你可以在[此处](https://technet.microsoft.com/library/mt228132.aspx)了解有关这些设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="79740-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="79740-116">若要执行此操作，用户必须使用支持版本的2016即点即用 Skype for business 应用（支持它）。</span><span class="sxs-lookup"><span data-stu-id="79740-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="79740-117">需要以下最低版本的 Skype for Business 2016 即点即用客户端：</span><span class="sxs-lookup"><span data-stu-id="79740-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="79740-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="79740-118">**Type**</span></span>|<span data-ttu-id="79740-119">**发布日期**</span><span class="sxs-lookup"><span data-stu-id="79740-119">**Release date**</span></span>|<span data-ttu-id="79740-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="79740-120">**Version**</span></span>|<span data-ttu-id="79740-121">**版本号**</span><span class="sxs-lookup"><span data-stu-id="79740-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="79740-122">当前频道的首次发布</span><span class="sxs-lookup"><span data-stu-id="79740-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="79740-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="79740-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="79740-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="79740-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="79740-125">版本1611（内部版本7571.2006）</span><span class="sxs-lookup"><span data-stu-id="79740-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="79740-126">当前频道</span><span class="sxs-lookup"><span data-stu-id="79740-126">Current Channel</span></span>  <br/> |<span data-ttu-id="79740-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="79740-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="79740-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="79740-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="79740-129">版本1611（内部版本7571.2072）</span><span class="sxs-lookup"><span data-stu-id="79740-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="79740-130">延期频道</span><span class="sxs-lookup"><span data-stu-id="79740-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="79740-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="79740-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="79740-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="79740-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="79740-133">版本1609（内部版本7369.2118）</span><span class="sxs-lookup"><span data-stu-id="79740-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="79740-134">使用旧版本的 Skype for Business Windows 应用或 Mac 客户端的用户仍能传输文件。</span><span class="sxs-lookup"><span data-stu-id="79740-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="79740-135">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79740-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="79740-136">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="79740-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="79740-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="79740-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="79740-138">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="79740-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="79740-139">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="79740-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="79740-140">请参阅[Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855)以下载 windows PowerShell 并将其更新到版本4.0。</span><span class="sxs-lookup"><span data-stu-id="79740-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="79740-141">出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="79740-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="79740-p106">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="79740-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="79740-145">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="79740-145">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="79740-146">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="79740-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="79740-147">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="79740-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="79740-148">在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="79740-148">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79740-149">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="79740-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="79740-150">如果需要有关启动 Windows PowerShell 的详细信息，请参阅[在单个 Windows powershell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[设置适用于 windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="79740-150">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="79740-151">为用户创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="79740-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="79740-152">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="79740-152">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="79740-153">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="79740-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="79740-154">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="79740-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="79740-155">使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365 和 Skype for business Online，这样你有多个任务可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="79740-155">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="79740-156">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="79740-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="79740-157">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="79740-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="79740-158">为什么需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="79740-158">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="79740-159">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="79740-159">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="79740-160">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="79740-160">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="79740-161">通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="79740-161">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="79740-162">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="79740-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="79740-163">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="79740-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="79740-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="79740-164">Related topics</span></span>
[<span data-ttu-id="79740-165">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="79740-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="79740-166">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="79740-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="79740-167">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="79740-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
