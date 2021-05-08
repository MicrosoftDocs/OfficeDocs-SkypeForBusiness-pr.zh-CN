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
description: Skype for Business"联机"允许创建其他外部访问策略。 与客户端或会议策略（可以有多个组合）不同，有三个预定义的外部访问策略可以涵盖大多数方案。
ms.openlocfilehash: f9d99789bdb400cee9b7597bfcdc4079c1d3612d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240141"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="4c750-104">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="4c750-104">Create custom external access policies</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="4c750-105">Skype for Business"联机"允许创建其他外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="4c750-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="4c750-106">与客户端或会议策略（可以有多个组合）不同，有三个预定义的外部访问策略可以涵盖大多数方案。</span><span class="sxs-lookup"><span data-stu-id="4c750-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="4c750-107">包括：</span><span class="sxs-lookup"><span data-stu-id="4c750-107">These are:</span></span>
  
- <span data-ttu-id="4c750-108">标记 _：NoFederationAndPIC_ Skype联合或 (使用者访问) </span><span class="sxs-lookup"><span data-stu-id="4c750-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="4c750-109">仅联合访问 (_Tag：FederationOnly )_</span><span class="sxs-lookup"><span data-stu-id="4c750-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="4c750-110">_FederationAndPICDefault_ (联合访问和使用者) </span><span class="sxs-lookup"><span data-stu-id="4c750-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="4c750-111">自定义外部策略允许创建上述设置未涵盖的其他策略。</span><span class="sxs-lookup"><span data-stu-id="4c750-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="4c750-112">创建策略时，需要设置所有必需的参数，以后无法更改它们。</span><span class="sxs-lookup"><span data-stu-id="4c750-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="4c750-113">创建新的自定义策略允许你控制功能，例如Skype访问或禁用公有云音频/视频的策略，这是预定义设置未涵盖的内容。</span><span class="sxs-lookup"><span data-stu-id="4c750-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="4c750-114">自定义外部访问策略遵循的语法与客户端、移动性和会议策略相同。</span><span class="sxs-lookup"><span data-stu-id="4c750-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="4c750-115">可在此处了解有关这些设置 [的更多信息](/previous-versions//mt228132(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="4c750-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="4c750-116">若要使此操作正常工作，用户必须使用受支持的 2016 即点即用版本Skype for Business支持该应用。</span><span class="sxs-lookup"><span data-stu-id="4c750-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="4c750-117">2016 Skype for Business运行客户端需要以下最低版本：</span><span class="sxs-lookup"><span data-stu-id="4c750-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="4c750-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4c750-118">**Type**</span></span>|<span data-ttu-id="4c750-119">**发布日期**</span><span class="sxs-lookup"><span data-stu-id="4c750-119">**Release date**</span></span>|<span data-ttu-id="4c750-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="4c750-120">**Version**</span></span>|<span data-ttu-id="4c750-121">**生成**</span><span class="sxs-lookup"><span data-stu-id="4c750-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c750-122">当前频道的首次发布</span><span class="sxs-lookup"><span data-stu-id="4c750-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="4c750-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="4c750-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="4c750-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="4c750-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="4c750-125">版本 1611 (内部版本 7571.2006) </span><span class="sxs-lookup"><span data-stu-id="4c750-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="4c750-126">当前频道</span><span class="sxs-lookup"><span data-stu-id="4c750-126">Current Channel</span></span>  <br/> |<span data-ttu-id="4c750-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="4c750-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="4c750-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="4c750-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="4c750-129">版本 1611 (内部版本 7571.2072) </span><span class="sxs-lookup"><span data-stu-id="4c750-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="4c750-130">延期频道</span><span class="sxs-lookup"><span data-stu-id="4c750-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="4c750-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="4c750-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="4c750-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="4c750-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="4c750-133">版本 1609 (内部版本 7369.2118) </span><span class="sxs-lookup"><span data-stu-id="4c750-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="4c750-134">使用较旧版本的 Skype for Business Windows 或 Mac 客户端的用户仍可传输文件。</span><span class="sxs-lookup"><span data-stu-id="4c750-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="4c750-135">启动Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c750-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="4c750-136">Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="4c750-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="4c750-137">如果使用最新的 PowerShell Teams版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="4c750-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="4c750-138">安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="4c750-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="4c750-139">打开Windows PowerShell命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4c750-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="4c750-140">如果需要有关启动 Windows PowerShell Windows PowerShell，请参阅在单个 Microsoft 365 窗口中连接所有 Microsoft 365 或[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务Windows PowerShell或为计算机设置[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="4c750-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="4c750-141">为用户创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="4c750-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="4c750-142">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="4c750-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4c750-143">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="4c750-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="4c750-144">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="4c750-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4c750-145">使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="4c750-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4c750-146">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="4c750-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4c750-147">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="4c750-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="4c750-148">为何需要将 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c750-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="4c750-149">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="4c750-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4c750-150">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="4c750-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="4c750-151">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="4c750-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="4c750-152">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4c750-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="4c750-153">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="4c750-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="4c750-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="4c750-154">Related topics</span></span>
[<span data-ttu-id="4c750-155">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="4c750-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="4c750-156">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="4c750-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="4c750-157">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="4c750-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
