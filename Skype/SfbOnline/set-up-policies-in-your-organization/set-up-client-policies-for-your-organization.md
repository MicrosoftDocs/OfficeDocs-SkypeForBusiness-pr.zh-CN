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
ms.openlocfilehash: 59bc9ab406d530bc09803b61cfc4341617dc911d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240084"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="af30c-103">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="af30c-103">Set up client policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="af30c-104">客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="af30c-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="af30c-105">可以在创建策略时配置客户端策略设置，或者可以使用 **Set-CsClientPolicy** cmdlet 修改现有策略的设置。</span><span class="sxs-lookup"><span data-stu-id="af30c-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="af30c-106">设置你的客户端策略</span><span class="sxs-lookup"><span data-stu-id="af30c-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="af30c-107">对于 Skype for Business Online 中的所有客户端策略设置，必须使用 Windows PowerShell 并且不能 **使用** Skype for Business **管理中心**。</span><span class="sxs-lookup"><span data-stu-id="af30c-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="af30c-108">启动Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af30c-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="af30c-109">Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="af30c-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="af30c-110">如果使用最新的 PowerShell Teams版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="af30c-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="af30c-111">安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="af30c-111">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="af30c-112">打开Windows PowerShell命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="af30c-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="af30c-113">如果需要有关启动 Windows PowerShell Windows PowerShell，请参阅在单个 Microsoft 365 窗口中连接所有 Microsoft 365 或[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务Windows PowerShell或为计算机设置[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="af30c-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="af30c-114">禁用图释和状态通知，并阻止保存 VM</span><span class="sxs-lookup"><span data-stu-id="af30c-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="af30c-115">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="af30c-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="af30c-116">有关详细信息，请参阅 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af30c-116">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="af30c-117">若要向组织中所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="af30c-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="af30c-118">有关详细信息，请参阅 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af30c-118">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="af30c-119">如果已创建策略，可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet 更改现有策略，然后使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="af30c-119">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="af30c-120">启用要在即时消息中可单击的 URL 或超链接</span><span class="sxs-lookup"><span data-stu-id="af30c-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="af30c-121">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="af30c-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="af30c-122">有关详细信息，请参阅 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af30c-122">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="af30c-123">若要向组织中所有用户授予你创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="af30c-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="af30c-124">有关详细信息，请参阅 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af30c-124">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="af30c-125">如果已创建策略，可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet 更改现有策略，然后使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="af30c-125">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="af30c-126">禁止显示最近的联系人</span><span class="sxs-lookup"><span data-stu-id="af30c-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="af30c-127">若要为这些设置创建新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="af30c-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="af30c-128">有关详细信息，请参阅 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af30c-128">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="af30c-129">若要向 Amos Marble 授予创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="af30c-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="af30c-130">有关详细信息，请参阅 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af30c-130">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="af30c-131">如果已创建策略，可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet 更改现有策略，然后使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="af30c-131">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="af30c-132">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="af30c-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="af30c-133">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="af30c-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="af30c-134">使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="af30c-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="af30c-135">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="af30c-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="af30c-136">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="af30c-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="af30c-137">你可能希望使用 Windows PowerShell 管理Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="af30c-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="af30c-138">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="af30c-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="af30c-139">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="af30c-139">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="af30c-140">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="af30c-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="af30c-141">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="af30c-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="af30c-142">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="af30c-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="af30c-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="af30c-143">Related topics</span></span>
[<span data-ttu-id="af30c-144">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="af30c-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="af30c-145">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="af30c-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="af30c-146">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="af30c-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
