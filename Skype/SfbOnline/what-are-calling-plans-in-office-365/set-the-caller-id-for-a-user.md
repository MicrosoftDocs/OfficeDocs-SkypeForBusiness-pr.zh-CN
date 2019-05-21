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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going How can caller ID be used in your organization.
ms.openlocfilehash: e6cf065207afa04772930adf866c0557440c07ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291924"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="d033d-105">为用户设置来电显示</span><span class="sxs-lookup"><span data-stu-id="d033d-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="d033d-p102">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="d033d-p102">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="d033d-109">不能阻止当前在 Skype for Business Online 中的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="d033d-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="d033d-110">你可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="d033d-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="d033d-111">[!注释] 这一点 **不适用于** 使用 Lync 或 Skype for Business Server 的内部部署组织。</span><span class="sxs-lookup"><span data-stu-id="d033d-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="d033d-p103">**更改其传出来电显示** 你可以用其他电话号码替换用户的来电显示（默认情况下，显示的是用户的电话号码）。例如，你可以将用户的来电显示从其电话号码改为企业的主要电话号码，或者将用户的主叫号码从其电话号码改为法律部门的主要电话号码。你可以将来电显示号码改为任何在线 **服务** 号码（收费或免费）。</span><span class="sxs-lookup"><span data-stu-id="d033d-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d033d-115">[!注释] 如果要使用  _Service_ 参数，必须指定有效的服务号码。</span><span class="sxs-lookup"><span data-stu-id="d033d-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="d033d-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span><span class="sxs-lookup"><span data-stu-id="d033d-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="d033d-118">**阻止其来电呼叫者 ID**你可以阻止用户在任何传入 PSTN 呼叫上接收来电显示。</span><span class="sxs-lookup"><span data-stu-id="d033d-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d033d-119">[!重要信息] 紧急呼叫始终发送用户的电话号码（来电显示号码）。</span><span class="sxs-lookup"><span data-stu-id="d033d-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="d033d-p105">默认情况下，所有这些来电显示设置都为 **关闭** 状态。这表示当 Skype for Business Online 用户呼叫某个 PSTN 电话时，将显示该用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="d033d-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="d033d-122">要了解有关这些设置以及如何使用它们的详细信息，请访问[如何在你的组织中使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d033d-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="d033d-123">设置你的来电显示策略设置</span><span class="sxs-lookup"><span data-stu-id="d033d-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="d033d-124">对于 Skype for Business Online 中的所有来电显示设置, 必须使用 Windows PowerShell, 并且**不能使用** **Skype for business 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d033d-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="d033d-125">验证并启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d033d-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="d033d-126">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="d033d-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="d033d-127">若要验证您运行版本 3.0 或更高：**开始菜单** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="d033d-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d033d-128">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="d033d-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="d033d-p106">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="d033d-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="d033d-p107">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="d033d-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="d033d-135">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d033d-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="d033d-136">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="d033d-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="d033d-137">从 **开始菜单** > **Windows PowerShell** 。</span><span class="sxs-lookup"><span data-stu-id="d033d-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d033d-138">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="d033d-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d033d-139">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="d033d-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="d033d-140">如果需要有关启动 Windows PowerShell 的详细信息, 请参阅[在单个 Windows powershell 窗口中连接到所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[设置适用于 Windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="d033d-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="d033d-141">查看你组织中的所有来电显示策略设置</span><span class="sxs-lookup"><span data-stu-id="d033d-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="d033d-142">若要查看组织中的所有来电显示策略设置, 请运行:</span><span class="sxs-lookup"><span data-stu-id="d033d-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="d033d-143">有关 CsCallingLineIdentity 的详细信息, 请参阅[获取](https://technet.microsoft.com/en-us/library/mt793856.aspx)更多示例和详细信息。</span><span class="sxs-lookup"><span data-stu-id="d033d-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="d033d-144">为你的组织创建新的来电显示策略</span><span class="sxs-lookup"><span data-stu-id="d033d-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="d033d-145">若要创建将呼叫方 ID 设置为匿名的新来电显示策略, 请运行:</span><span class="sxs-lookup"><span data-stu-id="d033d-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="d033d-146">在所有情况下，在"服务号码"字段不应包含初始"+"。</span><span class="sxs-lookup"><span data-stu-id="d033d-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="d033d-147">有关详细信息, 请参阅[CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)的更多示例和详细信息。</span><span class="sxs-lookup"><span data-stu-id="d033d-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="d033d-148">若要将您创建的新策略应用于 Amos 大理石, 请运行:</span><span class="sxs-lookup"><span data-stu-id="d033d-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="d033d-149">请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="d033d-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="d033d-150">如果你已创建策略, 你可以使用[CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet 对现有策略进行更改, 然后使用[CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 将设置应用到你的用户。</span><span class="sxs-lookup"><span data-stu-id="d033d-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="d033d-151">对其进行设置以阻止传入来电显示</span><span class="sxs-lookup"><span data-stu-id="d033d-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="d033d-152">要阻止传入来电显示, 请运行:</span><span class="sxs-lookup"><span data-stu-id="d033d-152">To block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="d033d-153">请参阅[CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)的更多示例和详细信息。</span><span class="sxs-lookup"><span data-stu-id="d033d-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="d033d-154">若要将您创建的策略设置应用于您的组织中的用户, 请运行:</span><span class="sxs-lookup"><span data-stu-id="d033d-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="d033d-155">请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="d033d-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="d033d-156">删除来电显示策略</span><span class="sxs-lookup"><span data-stu-id="d033d-156">Remove a caller ID policy</span></span>

<span data-ttu-id="d033d-157">要删除组织的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="d033d-157">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="d033d-158">要删除用户的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="d033d-158">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d033d-159">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="d033d-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d033d-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="d033d-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d033d-163">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="d033d-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d033d-164">为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由） </span><span class="sxs-lookup"><span data-stu-id="d033d-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d033d-p109">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="d033d-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d033d-167">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="d033d-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d033d-168">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d033d-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d033d-169">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="d033d-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="d033d-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="d033d-170">Related topics</span></span>
[<span data-ttu-id="d033d-171">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="d033d-171">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="d033d-172">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="d033d-172">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="d033d-173">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="d033d-173">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="d033d-174">更多关于呼叫线路 ID 和主叫方名称的信息</span><span class="sxs-lookup"><span data-stu-id="d033d-174">More about Calling Line ID and Calling Party Name</span></span>](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[<span data-ttu-id="d033d-175">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="d033d-175">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="d033d-176">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d033d-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
