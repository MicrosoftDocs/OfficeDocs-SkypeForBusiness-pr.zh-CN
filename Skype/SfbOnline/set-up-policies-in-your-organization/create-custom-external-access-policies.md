---
title: 创建自定义外部访问策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype 业务 online 允许您创建其他外部访问策略。 与客户端或会议策略，其中可以有多个的组合，有三个可以代替大多数的方案的预定义的外部访问策略。
ms.openlocfilehash: e0af31d015c69ebd91c28a229a20d3d2c6c926c4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850154"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="b9a0e-104">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="b9a0e-104">Create custom external access policies</span></span>

<span data-ttu-id="b9a0e-105">Skype 业务 online 允许您创建其他外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="b9a0e-106">与客户端或会议策略，其中可以有多个的组合，有三个可以代替大多数的方案的预定义的外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="b9a0e-107">包括：</span><span class="sxs-lookup"><span data-stu-id="b9a0e-107">These are:</span></span>
  
- <span data-ttu-id="b9a0e-108">无联盟或 Skype 使用者访问 (_标记： NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="b9a0e-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="b9a0e-109">仅联盟的访问 (_标记： FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="b9a0e-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="b9a0e-110">联盟和使用者访问 (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="b9a0e-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="b9a0e-111">自定义外部策略允许您创建其他策略不包含上面的设置的。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="b9a0e-112">已创建策略，您将需要设置所有必需的参数和更高版本无法更改它们。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="b9a0e-113">创建新的自定义策略允许您控制功能，如 Skype 使用者访问或一个策略来禁用公共云音频/视频，这是使用预定义的设置未涵盖的内容。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="b9a0e-114">自定义外部访问策略按照语法与客户端和移动性、 会议策略相同。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="b9a0e-115">您可以了解这些设置的详细信息[此处](https://technet.microsoft.com/en-us/library/mt228132.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="b9a0e-116">若要使此项工作，用户必须使用 2016年是受支持的版本支持的业务应用程序的单击即点即用 Skype。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="b9a0e-117">下面的最低版本的 Skype 业务 2016年单击即点即用客户端时，需要：</span><span class="sxs-lookup"><span data-stu-id="b9a0e-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="b9a0e-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="b9a0e-118">**Type**</span></span>|<span data-ttu-id="b9a0e-119">**发布日期**</span><span class="sxs-lookup"><span data-stu-id="b9a0e-119">**Release date**</span></span>|<span data-ttu-id="b9a0e-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="b9a0e-120">**Version**</span></span>|<span data-ttu-id="b9a0e-121">**生成**</span><span class="sxs-lookup"><span data-stu-id="b9a0e-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9a0e-122">第一版当前通道</span><span class="sxs-lookup"><span data-stu-id="b9a0e-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="b9a0e-123">2016 年 11/17</span><span class="sxs-lookup"><span data-stu-id="b9a0e-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="b9a0e-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="b9a0e-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="b9a0e-125">版本 1611 （构建 7571.2006）</span><span class="sxs-lookup"><span data-stu-id="b9a0e-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="b9a0e-126">当前通道</span><span class="sxs-lookup"><span data-stu-id="b9a0e-126">Current Channel</span></span>  <br/> |<span data-ttu-id="b9a0e-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="b9a0e-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="b9a0e-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="b9a0e-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="b9a0e-129">版本 1611 （构建 7571.2072）</span><span class="sxs-lookup"><span data-stu-id="b9a0e-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="b9a0e-130">延迟的通道</span><span class="sxs-lookup"><span data-stu-id="b9a0e-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="b9a0e-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="b9a0e-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="b9a0e-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="b9a0e-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="b9a0e-133">版本 1609 （构建 7369.2118）</span><span class="sxs-lookup"><span data-stu-id="b9a0e-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="b9a0e-134">使用较早版本的 Skype 业务 Windows 应用程序或 Mac 客户端的用户仍可以传输文件。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="b9a0e-135">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9a0e-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="b9a0e-136">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="b9a0e-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="b9a0e-137">若要验证正在运行的版本是 3.0 或更高：**开始菜单** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b9a0e-138">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="b9a0e-p105">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="b9a0e-p106">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="b9a0e-145">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="b9a0e-146">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="b9a0e-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="b9a0e-147">从 **开始菜单** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b9a0e-148">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="b9a0e-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9a0e-149">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="b9a0e-150">如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Connecting to Skype 业务 online 使用 Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="b9a0e-151">创建自定义外部访问策略的用户</span><span class="sxs-lookup"><span data-stu-id="b9a0e-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="b9a0e-152">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="b9a0e-152">To do this, run:</span></span>
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b9a0e-153">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="b9a0e-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="b9a0e-154">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b9a0e-155">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="b9a0e-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b9a0e-156">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b9a0e-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b9a0e-157">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="b9a0e-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b9a0e-158">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9a0e-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="b9a0e-p108">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="b9a0e-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b9a0e-161">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="b9a0e-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="b9a0e-162">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b9a0e-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b9a0e-163">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="b9a0e-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="b9a0e-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="b9a0e-164">Related topics</span></span>
[<span data-ttu-id="b9a0e-165">阻止点对点文件传输</span><span class="sxs-lookup"><span data-stu-id="b9a0e-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="b9a0e-166">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="b9a0e-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="b9a0e-167">设置您的组织中的会议策略</span><span class="sxs-lookup"><span data-stu-id="b9a0e-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 