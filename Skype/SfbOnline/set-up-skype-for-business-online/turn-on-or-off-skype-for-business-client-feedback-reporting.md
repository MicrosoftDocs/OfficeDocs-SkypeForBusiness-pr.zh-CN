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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 你可以让你的 Skype for Business 用户使用内置的 Skype for Business 应用反馈工具，让用户报告问题并直接向 Microsoft 提供有关其体验的反馈。
ms.openlocfilehash: 9b9134f857be540a528ca12b51a4793c01f70fa4
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568998"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="abf8d-103">开启或关闭 Skype for Business 客户端反馈报告</span><span class="sxs-lookup"><span data-stu-id="abf8d-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="abf8d-104">你可以让你的 Skype for Business Online 用户使用内置的 Skype for Business 应用反馈工具，让用户报告问题并直接向 Microsoft 提供有关其体验的反馈。</span><span class="sxs-lookup"><span data-stu-id="abf8d-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
!["提供反馈"图标](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="abf8d-106">使用此工具，用户可以从他们的设备上复制应用中的日志，以帮助 Microsoft 更好地调查和排查他们可能存在的问题。</span><span class="sxs-lookup"><span data-stu-id="abf8d-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![使用"设置"图标报告问题](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="abf8d-108">你还可以使用  _EnableOnlineFeedbackScreenshot_ 设置，以便用户可以在其反馈中包含其设备的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="abf8d-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="abf8d-110">当问题正在调查时，应用的反馈工具收集的日志将在美国最多存储 90 天。</span><span class="sxs-lookup"><span data-stu-id="abf8d-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="abf8d-111">因此，如果这违反你组织的数据保护政策，请勿启用此反馈工具。</span><span class="sxs-lookup"><span data-stu-id="abf8d-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="abf8d-112">启动Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="abf8d-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="abf8d-113">Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="abf8d-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="abf8d-114">如果你使用的是最新的 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="abf8d-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="abf8d-115">安装 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="abf8d-115">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="abf8d-116">打开Windows PowerShell提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="abf8d-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="abf8d-117">如果需要有关启动 Windows PowerShell，请参阅"在单个 Windows PowerShell 窗口中连接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服务，或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="abf8d-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="abf8d-118">为你组织中的所有用户开启客户端应用反馈报告</span><span class="sxs-lookup"><span data-stu-id="abf8d-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="abf8d-119">若要为组织中用户启用反馈报告并允许他们提交设备屏幕截图，请运行：</span><span class="sxs-lookup"><span data-stu-id="abf8d-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="abf8d-120">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="abf8d-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="abf8d-121">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="abf8d-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="abf8d-122">借助Windows PowerShell，当你有多个任务需要执行时，可以使用单点管理来管理 Microsoft 365 或 Office 365 和 Skype for Business Online，从而简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="abf8d-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="abf8d-123">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="abf8d-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="abf8d-124">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="abf8d-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="abf8d-125">你可能想要使用 office 365 Windows PowerShell Office 365 的六大原因</span><span class="sxs-lookup"><span data-stu-id="abf8d-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="abf8d-126">Windows PowerShell使用 Microsoft 365 管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次对多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="abf8d-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="abf8d-127">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="abf8d-127">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="abf8d-128">使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="abf8d-128">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="abf8d-129">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="abf8d-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="abf8d-130">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="abf8d-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="abf8d-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="abf8d-131">Related topics</span></span>
[<span data-ttu-id="abf8d-132">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="abf8d-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="abf8d-133">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="abf8d-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
