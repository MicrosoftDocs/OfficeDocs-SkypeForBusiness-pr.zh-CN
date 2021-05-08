---
title: 阻止点到点文件传输
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: 在 Skype for Business Online 中，你可以控制点到点 (P2P) 文件传输作为现有会议策略设置的一部分。 但是，无论用户是否将文件传输到同一组织内部的用户或另一组织的联合用户，这都允许或阻止用户进行文件传输。 按照以下步骤，可以阻止与联合组织或合作伙伴进行 P2P 文件传输。
ms.openlocfilehash: e20cf0d5ff7a884e81fe2ee5de57ed026c53552e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240171"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="5ca11-105">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="5ca11-105">Block Point-to-Point file transfers</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="5ca11-106">在 Skype for Business Online 中，你可以控制点到点 (P2P) 文件传输作为现有会议策略设置的一部分。</span><span class="sxs-lookup"><span data-stu-id="5ca11-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="5ca11-107">但是，无论用户是否将文件传输到同一组织内部的用户或另一组织的联合用户，这都允许或阻止用户进行文件传输。</span><span class="sxs-lookup"><span data-stu-id="5ca11-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="5ca11-108">按照以下步骤，可以阻止与联合组织或合作伙伴进行 P2P 文件传输。</span><span class="sxs-lookup"><span data-stu-id="5ca11-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="5ca11-109">一种很常见的情况是，希望允许内部用户使用 P2P 文件传输，但阻止与联合合作伙伴进行文件传输。</span><span class="sxs-lookup"><span data-stu-id="5ca11-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="5ca11-110">对于此方案，需要：</span><span class="sxs-lookup"><span data-stu-id="5ca11-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="5ca11-111">将已启用 P2P 文件传输的会议策略 (_EnableP2PFileTransfer_ 设置为 _True_) 组织中用户。</span><span class="sxs-lookup"><span data-stu-id="5ca11-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="5ca11-112">创建全局外部用户通信策略设置为阻止外部 P2P 文件传输 (_EnableP2PFileTransfer_ 设置为 _False_) 并将其分配给组织的用户。</span><span class="sxs-lookup"><span data-stu-id="5ca11-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="5ca11-113">可在此处了解有关这些设置 [的更多信息](/previous-versions//mt228132(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="5ca11-113">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="5ca11-114">如果组织外部的联合用户尝试向应用了策略的用户发送文件，则会收到"传输失败 **"** 错误。</span><span class="sxs-lookup"><span data-stu-id="5ca11-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="5ca11-115">如果用户尝试发送文件，他们将收到"文件传输 **已关闭"** 错误。</span><span class="sxs-lookup"><span data-stu-id="5ca11-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="5ca11-116">若要使此操作正常工作，用户必须使用支持它的 2016 即点即Skype for Business版本。</span><span class="sxs-lookup"><span data-stu-id="5ca11-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="5ca11-117">2016 Skype for Business运行客户端需要以下最低版本：</span><span class="sxs-lookup"><span data-stu-id="5ca11-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="5ca11-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="5ca11-118">**Type**</span></span>|<span data-ttu-id="5ca11-119">**发布日期**</span><span class="sxs-lookup"><span data-stu-id="5ca11-119">**Release date**</span></span>|<span data-ttu-id="5ca11-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="5ca11-120">**Version**</span></span>|<span data-ttu-id="5ca11-121">**生成**</span><span class="sxs-lookup"><span data-stu-id="5ca11-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ca11-122">当前频道的首次发布</span><span class="sxs-lookup"><span data-stu-id="5ca11-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="5ca11-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="5ca11-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="5ca11-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="5ca11-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="5ca11-125">版本 1611 (内部版本 7571.2006) </span><span class="sxs-lookup"><span data-stu-id="5ca11-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="5ca11-126">当前频道</span><span class="sxs-lookup"><span data-stu-id="5ca11-126">Current Channel</span></span>  <br/> |<span data-ttu-id="5ca11-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="5ca11-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="5ca11-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="5ca11-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="5ca11-129">版本 1611 (内部版本 7571.2072) </span><span class="sxs-lookup"><span data-stu-id="5ca11-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="5ca11-130">延期频道</span><span class="sxs-lookup"><span data-stu-id="5ca11-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="5ca11-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="5ca11-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="5ca11-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="5ca11-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="5ca11-133">版本 1609 (内部版本 7369.2118) </span><span class="sxs-lookup"><span data-stu-id="5ca11-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="5ca11-134">使用较旧版本的 Skype for Business Windows 或 Mac 客户端的用户仍可传输文件。</span><span class="sxs-lookup"><span data-stu-id="5ca11-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="5ca11-135">启动Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ca11-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="5ca11-136">Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="5ca11-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="5ca11-137">如果使用最新的 PowerShell Teams版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="5ca11-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="5ca11-138">安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="5ca11-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="5ca11-139">打开Windows PowerShell命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ca11-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="5ca11-140">如果需要有关启动 Windows PowerShell Windows PowerShell，请参阅在单个 Microsoft 365 窗口中连接所有 Microsoft 365 或[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务Windows PowerShell或为计算机设置[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="5ca11-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="5ca11-141">为组织禁用 P2P 文件传输</span><span class="sxs-lookup"><span data-stu-id="5ca11-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="5ca11-142">默认情况下，对组织的全局策略启用 _EnableP2PFileTransfer。_</span><span class="sxs-lookup"><span data-stu-id="5ca11-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="5ca11-143">创建时，会为用户分配 _BposSAllModality_ 策略。</span><span class="sxs-lookup"><span data-stu-id="5ca11-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="5ca11-144">若要允许在组织内部进行 P2P 传输，但阻止将外部文件传输给另一个组织，只需在全局级别更改它。</span><span class="sxs-lookup"><span data-stu-id="5ca11-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="5ca11-145">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="5ca11-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="5ca11-146">为用户禁用 P2P 文件传输</span><span class="sxs-lookup"><span data-stu-id="5ca11-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="5ca11-147">可以通过创建新策略并授予该用户来向用户应用此策略。</span><span class="sxs-lookup"><span data-stu-id="5ca11-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="5ca11-148">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="5ca11-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5ca11-149">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="5ca11-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5ca11-150">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="5ca11-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5ca11-151">使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="5ca11-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5ca11-152">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5ca11-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5ca11-153">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="5ca11-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5ca11-154">为何需要将 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ca11-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="5ca11-155">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="5ca11-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5ca11-156">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="5ca11-156">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="5ca11-157">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5ca11-157">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="5ca11-158">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5ca11-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5ca11-159">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="5ca11-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="5ca11-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="5ca11-160">Related topics</span></span>
[<span data-ttu-id="5ca11-161">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="5ca11-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="5ca11-162">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="5ca11-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="5ca11-163">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="5ca11-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
