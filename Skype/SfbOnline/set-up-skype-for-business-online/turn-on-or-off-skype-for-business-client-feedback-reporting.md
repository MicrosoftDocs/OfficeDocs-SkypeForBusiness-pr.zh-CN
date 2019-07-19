---
title: 开启或关闭 Skype for Business 客户端反馈报告
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 你可以使 Skype for Business 用户能够使用内置的 Skype for business 应用反馈工具, 让用户能够直接向 Microsoft 报告问题并向 Microsoft 提供反馈, 以了解他们的体验。
ms.openlocfilehash: d7d80110be63b60fcfa1581c806d01ab0f056077
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792664"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="c1fa5-103">开启或关闭 Skype for Business 客户端反馈报告</span><span class="sxs-lookup"><span data-stu-id="c1fa5-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="c1fa5-104">你可以启用 Skype for business Online 用户使用内置的 Skype for business 应用反馈工具, 让用户能够直接向 Microsoft 报告问题并向 Microsoft 提供反馈意见。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="c1fa5-106">使用此工具, 用户可以从其设备上的应用复制日志, 以帮助 Microsoft 更好地调查和解决他们可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="c1fa5-108">你还可以使用  _EnableOnlineFeedbackScreenshot_ 设置，以便用户可以在其反馈中包含其设备的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="c1fa5-110">在调查问题时, 应用的反馈工具收集的日志最多可存储在美国的90天。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="c1fa5-111">因此，如果这违反你组织的数据保护政策，请勿启用此反馈工具。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="c1fa5-112">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1fa5-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="c1fa5-113">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="c1fa5-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="c1fa5-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c1fa5-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c1fa5-115">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="c1fa5-116">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="c1fa5-117">请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="c1fa5-118">出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-118">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="c1fa5-p103">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="c1fa5-122">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="c1fa5-123">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="c1fa5-123">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="c1fa5-124">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c1fa5-124">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c1fa5-125">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="c1fa5-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1fa5-126">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
 
   ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="c1fa5-127">如果需要有关启动 Windows PowerShell 的详细信息, 请参阅[在单个 Windows powershell 窗口中连接到所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[设置适用于 Windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="c1fa5-128">为你组织中的所有用户开启客户端应用反馈报告</span><span class="sxs-lookup"><span data-stu-id="c1fa5-128">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="c1fa5-129">若要为组织中的用户启用反馈报告, 并允许他们提交设备屏幕截图, 请运行:</span><span class="sxs-lookup"><span data-stu-id="c1fa5-129">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c1fa5-130">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="c1fa5-130">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="c1fa5-131">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c1fa5-132">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-132">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c1fa5-133">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="c1fa5-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c1fa5-134">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="c1fa5-134">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c1fa5-135">可能希望使用 Windows PowerShell 管理 Office 365 的六个原因</span><span class="sxs-lookup"><span data-stu-id="c1fa5-135">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c1fa5-136">Windows PowerShell 在速度、简洁性和效率方面具有许多优势, 仅限于使用 Microsoft 365 管理中心, 例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="c1fa5-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c1fa5-137">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="c1fa5-137">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c1fa5-138">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="c1fa5-138">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c1fa5-139">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c1fa5-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c1fa5-140">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="c1fa5-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="c1fa5-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="c1fa5-141">Related topics</span></span>
[<span data-ttu-id="c1fa5-142">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c1fa5-142">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="c1fa5-143">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="c1fa5-143">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
