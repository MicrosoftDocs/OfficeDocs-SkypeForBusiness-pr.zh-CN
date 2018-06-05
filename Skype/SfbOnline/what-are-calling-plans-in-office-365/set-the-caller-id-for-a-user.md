---
title: 为用户设置来电显示
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Office 365 中的电话系统提供的默认呼叫者 ID 的用户的分配的电话号码。 你可以为用户更改或阻止来电显示（也称为主叫号码）。 您可以了解有关如何使用您的组织中的呼叫者 ID，转如何可以呼叫者 ID 是您组织中使用的详细信息。
ms.openlocfilehash: a48edfd6f0b6967f1f9c628b415f781b8c4832c7
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500850"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="b7c6c-105">为用户设置来电显示</span><span class="sxs-lookup"><span data-stu-id="b7c6c-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="b7c6c-106">Office 365 中的电话系统提供的默认呼叫者 ID 的用户的分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="b7c6c-107">你可以为用户更改或阻止来电显示（也称为主叫号码）。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-107">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="b7c6c-108">您可以了解有关如何使用您的组织中的呼叫者 ID，转[如何可以呼叫者 ID 是您组织中使用](how-can-caller-id-be-used-in-your-organization.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-108">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="b7c6c-109">不能为业务 Online 阻止正在 Skype 的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="b7c6c-110">你可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7c6c-111">[!注释] 这一点 **不适用于** 使用 Lync 或 Skype for Business Server 的内部部署组织。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="b7c6c-p103">**更改其传出来电显示** 你可以用其他电话号码替换用户的来电显示（默认情况下，显示的是用户的电话号码）。例如，你可以将用户的来电显示从其电话号码改为企业的主要电话号码，或者将用户的主叫号码从其电话号码改为法律部门的主要电话号码。你可以将来电显示号码改为任何在线 **服务** 号码（收费或免费）。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b7c6c-115">[!注释] 如果要使用  _Service_ 参数，必须指定有效的服务号码。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="b7c6c-116">**阻止其出站呼叫者 ID**您可以阻止发送用户的传出 PSTN 呼叫传出的呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-116">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="b7c6c-117">执行此操作将阻止其电话号码显示在被呼叫者的电话上。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-117">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="b7c6c-118">**阻止其传入的呼叫者 ID**您可以阻止用户接收任何传入 PSTN 呼叫的呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b7c6c-119">[!重要信息] 紧急呼叫始终发送用户的电话号码（来电显示号码）。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="b7c6c-p105">默认情况下，所有这些来电显示设置都为 **关闭** 状态。这表示当 Skype for Business Online 用户呼叫某个 PSTN 电话时，将显示该用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="b7c6c-122">要了解有关这些设置以及如何使用它们的详细信息，请访问[如何在你的组织中使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="b7c6c-123">设置你的来电显示策略设置</span><span class="sxs-lookup"><span data-stu-id="b7c6c-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="b7c6c-124">对于所有的呼叫者 ID 设置 Skype 中的业务 Online，您必须使用 Windows PowerShell 和您**不能使用****业务管理中心的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="b7c6c-125">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7c6c-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="b7c6c-126">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="b7c6c-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="b7c6c-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b7c6c-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b7c6c-128">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="b7c6c-p106">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="b7c6c-p107">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="b7c6c-135">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="b7c6c-136">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="b7c6c-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="b7c6c-137">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b7c6c-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b7c6c-138">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b7c6c-139">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
> 
  ```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```
> 
  ```
  $credential = Get-Credential
  ```
> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```
> 
  ```
  Import-PSSession $session
  ```

<span data-ttu-id="b7c6c-140">如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Connecting to Skype 业务 online 使用 Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="b7c6c-141">查看你组织中的所有来电显示策略设置</span><span class="sxs-lookup"><span data-stu-id="b7c6c-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="b7c6c-142">若要查看您的组织中的所有呼叫者 ID 策略设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
<span data-ttu-id="b7c6c-143">有关[获取 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx)，请参阅更多示例和详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="b7c6c-144">为你的组织创建新的来电显示策略</span><span class="sxs-lookup"><span data-stu-id="b7c6c-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="b7c6c-145">若要创建新的呼叫者 ID 策略将呼叫者 ID 设置为匿名，请运行：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="b7c6c-146">在所有情况下，在"服务号码"字段不应包含初始"+"。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="b7c6c-147">用于[新建 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)，请参阅更多示例和详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="b7c6c-148">若要向 Amos 大理石应用您创建的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="b7c6c-149">请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="b7c6c-150">如果您已经创建策略，可以使用[集 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet 可以更改现有的策略，并将[授予 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 将设置应用于您的用户。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="b7c6c-151">对其进行设置以阻止传入来电显示</span><span class="sxs-lookup"><span data-stu-id="b7c6c-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="b7c6c-152">若要阻止的传入呼叫者 ID，请运行：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-152">To block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="b7c6c-153">有关[设置 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)，请参阅更多示例和详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="b7c6c-154">若要向您的组织中的用户应用您创建的策略设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="b7c6c-155">请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="b7c6c-156">删除来电显示策略</span><span class="sxs-lookup"><span data-stu-id="b7c6c-156">Remove a caller ID policy</span></span>

<span data-ttu-id="b7c6c-157">要删除组织的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-157">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="b7c6c-158">要删除用户的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-158">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b7c6c-159">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="b7c6c-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="b7c6c-160">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b7c6c-161">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="b7c6c-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b7c6c-162">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b7c6c-163">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="b7c6c-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b7c6c-164">为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）</span><span class="sxs-lookup"><span data-stu-id="b7c6c-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="b7c6c-p109">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="b7c6c-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b7c6c-167">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="b7c6c-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="b7c6c-168">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b7c6c-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b7c6c-169">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="b7c6c-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="b7c6c-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="b7c6c-170">Related topics</span></span>
[<span data-ttu-id="b7c6c-171">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="b7c6c-171">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="b7c6c-172">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="b7c6c-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="b7c6c-173">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="b7c6c-173">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="b7c6c-174">更多关于呼叫线路 ID 和主叫方名称的信息</span><span class="sxs-lookup"><span data-stu-id="b7c6c-174">More about Calling Line ID and Calling Party Name</span></span>](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[<span data-ttu-id="b7c6c-175">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="b7c6c-175">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="b7c6c-176">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="b7c6c-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
  
 
 
