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
ms.openlocfilehash: ff0603ca68f4e828fc3b6977065ac9ec3ca6a33d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103798"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="414b3-103">打开或关闭允许使用 Outlook 为会议预加载内容</span><span class="sxs-lookup"><span data-stu-id="414b3-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="414b3-104">用户可以将附加到 Outlook 会议邀请的内容、文件或附件预加载到 Skype for Business Online 会议，但你可以将其打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="414b3-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="414b3-105">默认情况下，所有使用 Skype for Business Online 的组织都启用它。</span><span class="sxs-lookup"><span data-stu-id="414b3-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="414b3-106">请参阅如何[为 Skype for Business 会议预加载附件](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。</span><span class="sxs-lookup"><span data-stu-id="414b3-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="414b3-107">目前，Skype for Business Online 中没有任何 cmdlet 可用于设置或查看  _MaxContentStorageMB_ 和 _MaxUploadFileMB_ 的联机值。</span><span class="sxs-lookup"><span data-stu-id="414b3-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="414b3-108">它们仅适用于本地部署。</span><span class="sxs-lookup"><span data-stu-id="414b3-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="414b3-109">必须知道，如果附加内容超过  _MaxUploadFileSizeMB_ 或达到 _MaxContentStorageMB_ 限制，则不会将内容上载到会议。</span><span class="sxs-lookup"><span data-stu-id="414b3-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="414b3-110">开始使用</span><span class="sxs-lookup"><span data-stu-id="414b3-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="414b3-111">启动Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="414b3-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="414b3-112">Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="414b3-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="414b3-113">如果你使用的是最新的 Teams PowerShell 公共版本，则不需要安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="414b3-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="414b3-114">安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="414b3-114">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="414b3-115">打开 Windows PowerShell 命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="414b3-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="414b3-116">如果需要有关启动 Windows PowerShell，请参阅在单个 Windows PowerShell 窗口中连接到所有[Microsoft 365 或 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="414b3-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="414b3-117">打开或关闭该功能</span><span class="sxs-lookup"><span data-stu-id="414b3-117">Turning it on or off</span></span>

<span data-ttu-id="414b3-118">默认情况下，可以预加载附加到 Skype for Business Online 会议的 Outlook 会议邀请的内容，但您可能需要防止贵组织的用户预加载其会议中的内容。</span><span class="sxs-lookup"><span data-stu-id="414b3-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="414b3-119">此设置只能为整个组织启用或关闭;无法为单个用户打开或关闭它。</span><span class="sxs-lookup"><span data-stu-id="414b3-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="414b3-120">**若要将其关闭，请打开 Windows PowerShell 并执行下列操作：**</span><span class="sxs-lookup"><span data-stu-id="414b3-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="414b3-121">**如果想要将其重新打开，请打开 Windows PowerShell 并执行下列操作：**</span><span class="sxs-lookup"><span data-stu-id="414b3-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="414b3-122">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="414b3-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="414b3-123">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="414b3-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="414b3-124">使用 Windows PowerShell，当你有多个任务需要执行时，可以使用可以简化日常工作的单一管理点来管理 Microsoft 365 或 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="414b3-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="414b3-125">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="414b3-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="414b3-126">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="414b3-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="414b3-127">你可能希望使用 Office 365 Windows PowerShell Office 365 的六大原因</span><span class="sxs-lookup"><span data-stu-id="414b3-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="414b3-128">Windows PowerShell比使用 Microsoft 365 管理中心（例如，一次对许多用户进行设置更改时）具有许多速度、简单性和工作效率优势。</span><span class="sxs-lookup"><span data-stu-id="414b3-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="414b3-129">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="414b3-129">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="414b3-130">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="414b3-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="414b3-131">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="414b3-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="414b3-132">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="414b3-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="414b3-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="414b3-133">Related topics</span></span>
[<span data-ttu-id="414b3-134">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="414b3-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="414b3-135">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="414b3-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
