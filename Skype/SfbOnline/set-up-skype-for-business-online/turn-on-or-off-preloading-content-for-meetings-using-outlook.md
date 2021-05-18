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
ms.openlocfilehash: b6ff40e34c6459a75d0b79a8d750902a3457e00d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239105"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="fbbf7-103">打开或关闭允许使用 Outlook 为会议预加载内容</span><span class="sxs-lookup"><span data-stu-id="fbbf7-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="fbbf7-104">用户可以将附加到 Outlook 会议邀请的内容、文件或附件预Skype for Business联机会议，但你可以将其打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="fbbf7-105">默认情况下，对于使用 Skype for Business Online 的所有组织，它Skype for Business打开。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="fbbf7-106">请参阅如何[为 Skype for Business 会议预加载附件](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fbbf7-107">目前，Skype for Business Online 中没有任何 cmdlet 可用于设置或查看 _MaxContentStorageMB_ 和 _MaxUploadFileMB_ 的联机值。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="fbbf7-108">它们仅适用于本地部署。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="fbbf7-109">必须知道，如果附加内容超过  _MaxUploadFileSizeMB_ 或达到 _MaxContentStorageMB_ 限制，则不会将内容上载到会议。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="fbbf7-110">开始使用</span><span class="sxs-lookup"><span data-stu-id="fbbf7-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="fbbf7-111">启动Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbbf7-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="fbbf7-112">Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="fbbf7-113">如果使用最新的 PowerShell Teams版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="fbbf7-114">安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-114">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="fbbf7-115">打开Windows PowerShell命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fbbf7-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="fbbf7-116">如果需要有关启动 Windows PowerShell Windows PowerShell，请参阅在单个 Microsoft 365 窗口中连接所有 Microsoft 365 或[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务Windows PowerShell或为计算机设置[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="fbbf7-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="fbbf7-117">打开或关闭该功能</span><span class="sxs-lookup"><span data-stu-id="fbbf7-117">Turning it on or off</span></span>

<span data-ttu-id="fbbf7-118">默认情况下，可以预加载附加到 Outlook 会议邀请的内容以加入 Skype for Business Online 会议，但您可能需要阻止您的组织中的用户预加载其会议中的内容。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fbbf7-119">此设置只能为整个组织启用或关闭;无法为单个用户打开或关闭它。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="fbbf7-120">**若要将其关闭，请打开 Windows PowerShell 并执行下列操作：**</span><span class="sxs-lookup"><span data-stu-id="fbbf7-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="fbbf7-121">**如果想要将其重新打开，请打开 Windows PowerShell 并执行下列操作：**</span><span class="sxs-lookup"><span data-stu-id="fbbf7-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fbbf7-122">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="fbbf7-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="fbbf7-123">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fbbf7-124">使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="fbbf7-125">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="fbbf7-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fbbf7-126">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="fbbf7-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="fbbf7-127">你可能希望使用 Windows PowerShell 管理Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="fbbf7-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="fbbf7-128">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="fbbf7-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="fbbf7-129">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="fbbf7-129">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="fbbf7-130">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="fbbf7-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="fbbf7-131">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fbbf7-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="fbbf7-132">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="fbbf7-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="fbbf7-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="fbbf7-133">Related topics</span></span>
[<span data-ttu-id="fbbf7-134">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fbbf7-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fbbf7-135">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="fbbf7-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
