---
title: 阻止点到点文件传输
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: 在业务 online Skype，您可以控制现有会议策略设置的一部分 (P2P) 点对点文件传输功能。 但是，这将允许或阻止文件传输他们用户属于同一组织中或从另一个组织的联合用户传输的文件的用户。 下面的下面的步骤，您可以阻止与联盟的组织或合作伙伴的 P2P 文件传输。
ms.openlocfilehash: 3ae7bce22a99858af36696e1fde41bb614f2c008
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858488"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="41efa-105">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="41efa-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="41efa-106">在业务 online Skype，您可以控制现有会议策略设置的一部分 (P2P) 点对点文件传输功能。</span><span class="sxs-lookup"><span data-stu-id="41efa-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="41efa-107">但是，这将允许或阻止文件传输他们用户属于同一组织中或从另一个组织的联合用户传输的文件的用户。</span><span class="sxs-lookup"><span data-stu-id="41efa-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="41efa-108">下面的下面的步骤，您可以阻止与联盟的组织或合作伙伴的 P2P 文件传输。</span><span class="sxs-lookup"><span data-stu-id="41efa-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="41efa-109">要允许内部用户使用 P2P 文件传输，但与联盟伙伴的阻止文件传输时非常常见方案。</span><span class="sxs-lookup"><span data-stu-id="41efa-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="41efa-110">对于此方案，您将需要执行操作：</span><span class="sxs-lookup"><span data-stu-id="41efa-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="41efa-111">与启用 P2P 文件传输 (_EnableP2PFileTransfer_将设置为_True_) 的会议策略分配给您组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="41efa-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="41efa-112">创建全局外部用户通信策略设置来阻止外部 P2P 文件传输 （_EnableP2PFileTransfer_设置为_False_），并将其分配给您的组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="41efa-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="41efa-113">您可以了解这些设置的详细信息[此处](https://technet.microsoft.com/en-us/library/mt228132.aspx)。</span><span class="sxs-lookup"><span data-stu-id="41efa-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="41efa-114">如果组织外部的联合的用户试图将文件发送给用户其中应用了策略，他们将收到**转接失败**错误。</span><span class="sxs-lookup"><span data-stu-id="41efa-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="41efa-115">并且，如果用户尝试发送文件，他们将收到**处于关闭状态文件传输**错误。</span><span class="sxs-lookup"><span data-stu-id="41efa-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="41efa-116">若要使此项工作，用户必须使用 2016年单击即点即用 Skype 是受支持的版本支持的业务应用程序。</span><span class="sxs-lookup"><span data-stu-id="41efa-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="41efa-117">下面的最低版本的 Skype 业务 2016年单击即点即用客户端时，需要：</span><span class="sxs-lookup"><span data-stu-id="41efa-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="41efa-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="41efa-118">**Type**</span></span>|<span data-ttu-id="41efa-119">**发布日期**</span><span class="sxs-lookup"><span data-stu-id="41efa-119">**Release date**</span></span>|<span data-ttu-id="41efa-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="41efa-120">**Version**</span></span>|<span data-ttu-id="41efa-121">**生成**</span><span class="sxs-lookup"><span data-stu-id="41efa-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41efa-122">第一版当前通道</span><span class="sxs-lookup"><span data-stu-id="41efa-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="41efa-123">2016 年 11/17</span><span class="sxs-lookup"><span data-stu-id="41efa-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="41efa-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="41efa-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="41efa-125">版本 1611 （构建 7571.2006）</span><span class="sxs-lookup"><span data-stu-id="41efa-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="41efa-126">当前通道</span><span class="sxs-lookup"><span data-stu-id="41efa-126">Current Channel</span></span>  <br/> |<span data-ttu-id="41efa-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="41efa-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="41efa-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="41efa-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="41efa-129">版本 1611 （构建 7571.2072）</span><span class="sxs-lookup"><span data-stu-id="41efa-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="41efa-130">延迟的通道</span><span class="sxs-lookup"><span data-stu-id="41efa-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="41efa-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="41efa-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="41efa-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="41efa-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="41efa-133">版本 1609 （构建 7369.2118）</span><span class="sxs-lookup"><span data-stu-id="41efa-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="41efa-134">使用较早版本的 Skype 业务 Windows 应用程序或 Mac 客户端的用户仍可以传输文件。</span><span class="sxs-lookup"><span data-stu-id="41efa-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="41efa-135">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41efa-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="41efa-136">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="41efa-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="41efa-137">若要验证正在运行的版本是 3.0 或更高：**开始菜单** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="41efa-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="41efa-138">通过在**Windows PowerShell**窗口中键入_Get 主机_检查版本。</span><span class="sxs-lookup"><span data-stu-id="41efa-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="41efa-p106">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="41efa-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="41efa-p107">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="41efa-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="41efa-145">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="41efa-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="41efa-146">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="41efa-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="41efa-147">从 **开始菜单** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="41efa-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="41efa-148">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="41efa-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41efa-149">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="41efa-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="41efa-150">如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Connecting to Skype 业务 online 使用 Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="41efa-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="41efa-151">禁用组织的 P2P 文件传输</span><span class="sxs-lookup"><span data-stu-id="41efa-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="41efa-152">默认情况下，对组织的全局策略启用_EnableP2PFileTransfer_ 。</span><span class="sxs-lookup"><span data-stu-id="41efa-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="41efa-153">当创建它时，您的用户分配给_BposSAllModality_策略。</span><span class="sxs-lookup"><span data-stu-id="41efa-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="41efa-154">若要允许您组织但阻止的外部文件传输到另一个组织内的 P2P 传输，只需在全局级别更改它。</span><span class="sxs-lookup"><span data-stu-id="41efa-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="41efa-155">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="41efa-155">To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="41efa-156">禁用的用户的 P2P 文件传输</span><span class="sxs-lookup"><span data-stu-id="41efa-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="41efa-157">您可以应用于此用户通过创建新策略，并授予该用户。</span><span class="sxs-lookup"><span data-stu-id="41efa-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="41efa-158">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="41efa-158">To do that, run:</span></span> 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="41efa-159">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="41efa-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="41efa-160">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="41efa-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="41efa-161">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="41efa-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="41efa-162">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="41efa-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="41efa-163">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="41efa-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="41efa-164">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="41efa-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="41efa-p112">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="41efa-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="41efa-167">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="41efa-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="41efa-168">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="41efa-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="41efa-169">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="41efa-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="41efa-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="41efa-170">Related topics</span></span>
[<span data-ttu-id="41efa-171">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="41efa-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="41efa-172">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="41efa-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="41efa-173">设置您的组织中的会议策略</span><span class="sxs-lookup"><span data-stu-id="41efa-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 