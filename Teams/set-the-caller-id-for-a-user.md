---
title: 为用户设置来电显示
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 了解用户分配的电话号码 (的 Microsoft 365 和 Office 365 默认呼叫者 ID) 也称为呼叫线 ID。 可以更改或阻止用户的来电显示。
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569414"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="53d84-104">为用户设置来电显示</span><span class="sxs-lookup"><span data-stu-id="53d84-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="53d84-105">Microsoft 365 和 Office 365 中的电话系统提供用户分配的电话号码的默认呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="53d84-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="53d84-106">你可以为用户更改或阻止来电显示（也称为主叫号码）。</span><span class="sxs-lookup"><span data-stu-id="53d84-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="53d84-107">通过了解如何在组织中使用来电显示，可以详细了解如何在组织中 [使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="53d84-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="53d84-108">不能阻止当前在 Skype for Business Online 中的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="53d84-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="53d84-109">你可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="53d84-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="53d84-110">[!注释] 这一点 **不适用于** 使用 Lync 或 Skype for Business Server 的内部部署组织。</span><span class="sxs-lookup"><span data-stu-id="53d84-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="53d84-p103">**更改其传出来电显示** 你可以用其他电话号码替换用户的来电显示（默认情况下，显示的是用户的电话号码）。例如，你可以将用户的来电显示从其电话号码改为企业的主要电话号码，或者将用户的主叫号码从其电话号码改为法律部门的主要电话号码。你可以将来电显示号码改为任何在线 **服务** 号码（收费或免费）。</span><span class="sxs-lookup"><span data-stu-id="53d84-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="53d84-114">[!注释] 如果要使用  _Service_ 参数，必须指定有效的服务号码。</span><span class="sxs-lookup"><span data-stu-id="53d84-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="53d84-115">**阻止其出站来电显示** 你可以阻止在用户的传出 PSTN 呼叫上发送传出呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="53d84-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="53d84-116">执行此操作将阻止其电话号码显示在被呼叫者的电话上。</span><span class="sxs-lookup"><span data-stu-id="53d84-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="53d84-117">**阻止其来电显示** 你可以阻止用户接收任何传入 PSTN 呼叫的来电显示。</span><span class="sxs-lookup"><span data-stu-id="53d84-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="53d84-118">[!重要信息] 紧急呼叫始终发送用户的电话号码（来电显示号码）。</span><span class="sxs-lookup"><span data-stu-id="53d84-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="53d84-p105">默认情况下，所有这些来电显示设置都为 **关闭** 状态。这表示当 Skype for Business Online 用户呼叫某个 PSTN 电话时，将显示该用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="53d84-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="53d84-121">要了解有关这些设置以及如何使用它们的详细信息，请访问[如何在你的组织中使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="53d84-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="53d84-122">设置你的来电显示策略设置</span><span class="sxs-lookup"><span data-stu-id="53d84-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="53d84-123">对于 Skype for Business Online 中所有的来电显示设置，必须使用Windows PowerShell并且不能使用 **Skype for Business 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="53d84-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-powershell"></a><span data-ttu-id="53d84-124">启动 PowerShell</span><span class="sxs-lookup"><span data-stu-id="53d84-124">Start PowerShell</span></span>

- <span data-ttu-id="53d84-125">打开Windows PowerShell提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="53d84-125">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="53d84-126">查看你组织中的所有来电显示策略设置</span><span class="sxs-lookup"><span data-stu-id="53d84-126">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="53d84-127">若要查看组织中所有来电显示策略设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="53d84-127">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="53d84-128">查看 [Get-CsCallingLineIdentity 的更多示例和详细信息](https://technet.microsoft.com/library/mt793856.aspx)。</span><span class="sxs-lookup"><span data-stu-id="53d84-128">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="53d84-129">为你的组织创建新的来电显示策略</span><span class="sxs-lookup"><span data-stu-id="53d84-129">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="53d84-130">若要创建新的调用方 ID 策略，将调用方 ID 设置为匿名，请运行：</span><span class="sxs-lookup"><span data-stu-id="53d84-130">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="53d84-131">在所有情况下，在"服务号码"字段不应包含初始"+"。</span><span class="sxs-lookup"><span data-stu-id="53d84-131">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="53d84-132">请参阅 [New-CsCallingLineIdentity 的更多示例和详细信息](https://technet.microsoft.com/library/mt793855.aspx)。</span><span class="sxs-lookup"><span data-stu-id="53d84-132">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="53d84-133">若要将创建的新策略应用到 Amos Marble，请运行：</span><span class="sxs-lookup"><span data-stu-id="53d84-133">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="53d84-134">请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="53d84-134">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="53d84-135">如果已创建策略，可以使用 [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet 对现有策略进行更改，然后使用 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="53d84-135">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="53d84-136">对其进行设置以阻止传入来电显示</span><span class="sxs-lookup"><span data-stu-id="53d84-136">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="53d84-137">若要阻止传入的来电显示，请运行：</span><span class="sxs-lookup"><span data-stu-id="53d84-137">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="53d84-138">查看 [Set-CsCallingLineIdentity 的更多示例和详细信息](https://technet.microsoft.com/library/mt793854.aspx)。</span><span class="sxs-lookup"><span data-stu-id="53d84-138">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="53d84-139">若要将创建的策略设置应用到组织中用户，请运行：</span><span class="sxs-lookup"><span data-stu-id="53d84-139">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="53d84-140">请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="53d84-140">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="53d84-141">删除来电显示策略</span><span class="sxs-lookup"><span data-stu-id="53d84-141">Remove a caller ID policy</span></span>

<span data-ttu-id="53d84-142">要删除组织的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="53d84-142">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="53d84-143">要删除用户的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="53d84-143">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="53d84-144">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="53d84-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="53d84-145">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="53d84-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="53d84-146">借助Windows PowerShell，当你有多个任务需要执行时，可以使用单点管理来管理 Microsoft 365 或 Office 365 和 Skype for Business Online，从而简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="53d84-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="53d84-147">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="53d84-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="53d84-148">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="53d84-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="53d84-149">你可能想要使用 office 365 Windows PowerShell Office 365 的六大原因</span><span class="sxs-lookup"><span data-stu-id="53d84-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="53d84-150">Windows PowerShell使用 Microsoft 365 管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次对多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="53d84-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="53d84-151">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="53d84-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="53d84-152">使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53d84-152">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="53d84-153">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="53d84-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="53d84-154">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="53d84-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="53d84-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="53d84-155">Related topics</span></span>
[<span data-ttu-id="53d84-156">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="53d84-156">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="53d84-157">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="53d84-157">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="53d84-158">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="53d84-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="53d84-159">更多关于呼叫线路 ID 和主叫方名称的信息</span><span class="sxs-lookup"><span data-stu-id="53d84-159">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="53d84-160">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="53d84-160">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="53d84-161">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="53d84-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
