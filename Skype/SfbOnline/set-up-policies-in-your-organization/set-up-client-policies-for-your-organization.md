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
ms.openlocfilehash: 65a346f0f16892d5995b723431fc796e3faa1a3b
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569224"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="d0fb0-103">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="d0fb0-103">Set up client policies for your organization</span></span>

<span data-ttu-id="d0fb0-104">客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="d0fb0-105">可以在创建策略时配置客户端策略设置，或者可以使用 **Set-CsClientPolicy** cmdlet 修改现有策略的设置。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="d0fb0-106">设置你的客户端策略</span><span class="sxs-lookup"><span data-stu-id="d0fb0-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="d0fb0-107">对于 Skype for Business Online 中的所有客户端策略设置，必须使用 Windows PowerShell并且不能使用Skype for **Business 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="d0fb0-108">启动Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0fb0-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="d0fb0-109">Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="d0fb0-110">如果你使用的是最新的 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="d0fb0-111">安装 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-111">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="d0fb0-112">打开Windows PowerShell提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d0fb0-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="d0fb0-113">如果需要有关启动 Windows PowerShell，请参阅"在单个 Windows PowerShell 窗口中连接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服务，或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d0fb0-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="d0fb0-114">禁用图释和状态通知，并阻止保存 VM</span><span class="sxs-lookup"><span data-stu-id="d0fb0-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="d0fb0-115">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="d0fb0-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="d0fb0-116">详细了解 [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-116">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d0fb0-117">若要向组织中所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="d0fb0-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="d0fb0-118">详细了解 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-118">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="d0fb0-119">如果已创建策略，可以使用 [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet 对现有策略进行更改，然后使用 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-119">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="d0fb0-120">启用要在即时消息中可单击的 URL 或超链接</span><span class="sxs-lookup"><span data-stu-id="d0fb0-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="d0fb0-121">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="d0fb0-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="d0fb0-122">详细了解 [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-122">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d0fb0-123">若要向组织中所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="d0fb0-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="d0fb0-124">详细了解 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-124">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="d0fb0-125">如果已创建策略，可以使用 [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet 对现有策略进行更改，然后使用 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-125">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="d0fb0-126">禁止显示最近的联系人</span><span class="sxs-lookup"><span data-stu-id="d0fb0-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="d0fb0-127">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="d0fb0-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="d0fb0-128">详细了解 [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-128">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d0fb0-129">若要向 Amos Marble 授予创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="d0fb0-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="d0fb0-130">详细了解 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-130">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="d0fb0-131">如果已创建策略，可以使用 [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet 对现有策略进行更改，然后使用 [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-131">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d0fb0-132">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="d0fb0-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d0fb0-133">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d0fb0-134">借助Windows PowerShell，当你有多个任务需要执行时，可以使用单点管理来管理 Microsoft 365 或 Office 365 和 Skype for Business Online，从而简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d0fb0-135">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d0fb0-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d0fb0-136">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="d0fb0-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d0fb0-137">你可能想要使用 office 365 Windows PowerShell Office 365 的六大原因</span><span class="sxs-lookup"><span data-stu-id="d0fb0-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d0fb0-138">Windows PowerShell使用 Microsoft 365 管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次对多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="d0fb0-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d0fb0-139">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="d0fb0-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d0fb0-140">使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0fb0-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d0fb0-141">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d0fb0-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d0fb0-142">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="d0fb0-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="d0fb0-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="d0fb0-143">Related topics</span></span>
[<span data-ttu-id="d0fb0-144">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="d0fb0-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="d0fb0-145">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="d0fb0-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="d0fb0-146">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="d0fb0-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
