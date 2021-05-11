---
title: 为用户设置来电显示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 了解Microsoft 365 Office 365呼叫者 ID (用户分配的电话号码) 呼叫线路 ID。 可以更改或阻止用户的来电显示。
ms.openlocfilehash: dbbb48952264d82ca24bdd82dbb45538b0428368
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308331"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="75eb0-104">为用户设置来电显示</span><span class="sxs-lookup"><span data-stu-id="75eb0-104">Set the Caller ID for a user</span></span>

<span data-ttu-id="75eb0-105">电话系统中Microsoft 365提供默认呼叫者 ID，即用户分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="75eb0-105">Phone System in Microsoft 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="75eb0-106">你可以为用户更改或阻止来电显示（也称为主叫号码）。</span><span class="sxs-lookup"><span data-stu-id="75eb0-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="75eb0-107">可以通过访问"如何在组织中使用来电显示"，详细了解如何在组织中 [使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="75eb0-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
<span data-ttu-id="75eb0-108">默认情况下，以下来电显示设置 **已关闭**。</span><span class="sxs-lookup"><span data-stu-id="75eb0-108">By default, the following caller ID settings are **turned off**.</span></span> <span data-ttu-id="75eb0-109">这意味着，Teams呼叫 PSTN 电话时，可以看到该用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="75eb0-109">This means that the Teams user's phone number can be seen when that user makes a call to a PSTN phone.</span></span> <span data-ttu-id="75eb0-110">可以更改这些设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="75eb0-110">You can change these settings as follows:</span></span>
  
- <span data-ttu-id="75eb0-111">**传出来电显示** 你可以将用户的来电显示（默认为用户的电话号码）替换为另一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="75eb0-111">**Outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="75eb0-112">例如，你可以将用户的来电显示从其电话号码改为企业的主要电话号码，或者将用户的主叫号码从其电话号码改为法律部门的主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="75eb0-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="75eb0-113">您可以将呼叫 ID 号码更改为收费或免费 (的任何联机服务) 。</span><span class="sxs-lookup"><span data-stu-id="75eb0-113">You can change the Calling ID number to any online service number (toll or toll-free).</span></span> <span data-ttu-id="75eb0-114">您还可以通过直接路由将呼叫 ID 号码更改为本地电话号码，该路由分配给呼叫队列或呼叫自动助理资源帐户。</span><span class="sxs-lookup"><span data-stu-id="75eb0-114">You can also change the Calling ID number to an on-premises phone number through Direct Routing that is assigned to a resource account used by an Auto Attendant or Call Queue.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="75eb0-115">若要使用 Service *参数，* 必须指定有效的服务编号。</span><span class="sxs-lookup"><span data-stu-id="75eb0-115">If you want to use the *Service* parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="75eb0-116">**阻止出站来电显示。**</span><span class="sxs-lookup"><span data-stu-id="75eb0-116">**Block outbound caller ID.**</span></span> <span data-ttu-id="75eb0-117">你可以阻止传出呼叫者 ID 在用户的传出 PSTN 呼叫上发送。</span><span class="sxs-lookup"><span data-stu-id="75eb0-117">You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="75eb0-118">执行此操作将阻止其电话号码显示在被呼叫者的电话上。</span><span class="sxs-lookup"><span data-stu-id="75eb0-118">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="75eb0-119">**阻止传入来电显示。**</span><span class="sxs-lookup"><span data-stu-id="75eb0-119">**Block incoming caller ID.**</span></span> <span data-ttu-id="75eb0-120">你可以阻止用户接收任何传入 PSTN 呼叫的来电显示。</span><span class="sxs-lookup"><span data-stu-id="75eb0-120">You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>

- <span data-ttu-id="75eb0-121">**将"呼叫方名称" (CNAM) 。**</span><span class="sxs-lookup"><span data-stu-id="75eb0-121">**Set Calling Party Name (CNAM).**</span></span> <span data-ttu-id="75eb0-122">对于您的Microsoft Teams用户可以在出站 PSTN 呼叫上发送 CNAM。</span><span class="sxs-lookup"><span data-stu-id="75eb0-122">For your Microsoft Teams users you can send a CNAM on outbound PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="75eb0-123">[!重要信息] 紧急呼叫始终发送用户的电话号码（来电显示号码）。</span><span class="sxs-lookup"><span data-stu-id="75eb0-123">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  

  
<span data-ttu-id="75eb0-124">若要详细了解这些设置及其使用方式，请参阅 [如何在组织中使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="75eb0-124">To learn more about these settings and how you can use them, see [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="75eb0-125">设置你的来电显示策略设置</span><span class="sxs-lookup"><span data-stu-id="75eb0-125">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="75eb0-126">若要将呼叫方 ID 设置为资源帐户电话号码并设置呼叫方名称，请使用 Teams PowerShell 模块 2.3.1 或更高版本中的 PowerShell cmdlet New-CsCallingLineIdentity 或 Set-CsCallingLineIdentity。</span><span class="sxs-lookup"><span data-stu-id="75eb0-126">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="75eb0-127"> (管理中心.) 中目前Microsoft Teams这些选项不可用</span><span class="sxs-lookup"><span data-stu-id="75eb0-127">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="75eb0-128">打开Windows PowerShell命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="75eb0-128">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a><span data-ttu-id="75eb0-129">查看、创建和应用策略设置</span><span class="sxs-lookup"><span data-stu-id="75eb0-129">View, create, and apply policy settings</span></span>

1. <span data-ttu-id="75eb0-130">若要查看组织的所有来电显示策略设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="75eb0-130">To view all of the caller ID policy settings in your organization, run:</span></span>

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   <span data-ttu-id="75eb0-131">有关详细信息，请参阅 [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="75eb0-131">For more information, see [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
2. <span data-ttu-id="75eb0-132">若要为组织创建新的来电显示策略，请使用 New-CsCallingIdentity cmdlet：</span><span class="sxs-lookup"><span data-stu-id="75eb0-132">To create a new caller ID policy for your organization, use the New-CsCallingIdentity cmdlet:</span></span>
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    <span data-ttu-id="75eb0-133">在所有情况下，在"服务号码"字段不应包含初始"+"。</span><span class="sxs-lookup"><span data-stu-id="75eb0-133">In all cases, the "Service Number" field should not include an initial "+".</span></span>

   <span data-ttu-id="75eb0-134">有关详细信息，请参阅 [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="75eb0-134">For more information, see [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
3. <span data-ttu-id="75eb0-135">使用 Grant-CsCallingIdentity cmdlet 应用创建的新策略。</span><span class="sxs-lookup"><span data-stu-id="75eb0-135">Apply the new policy you created by using the Grant-CsCallingIdentity cmdlet.</span></span> <span data-ttu-id="75eb0-136">例如，以下示例将新策略应用到用户 Amos Marble。</span><span class="sxs-lookup"><span data-stu-id="75eb0-136">For example, the following example applies the new policy to user Amos Marble.</span></span>
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   <span data-ttu-id="75eb0-137">有关详细信息，请参阅 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="75eb0-137">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    

4. <span data-ttu-id="75eb0-138">如果要阻止传入的来电显示，请运行：</span><span class="sxs-lookup"><span data-stu-id="75eb0-138">If you want to block the incoming caller ID, run:</span></span>
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   <span data-ttu-id="75eb0-139">有关详细信息，请参阅 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="75eb0-139">For more information, see [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
5. <span data-ttu-id="75eb0-140">若要将创建的策略设置应用到组织中用户，请运行：</span><span class="sxs-lookup"><span data-stu-id="75eb0-140">To apply the policy setting you created to a user in your organization, run:</span></span>
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   <span data-ttu-id="75eb0-141">有关详细信息，请参阅 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="75eb0-141">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span></span>

6. <span data-ttu-id="75eb0-142">若要创建新的来电显示策略，将呼叫者 ID 设置到指定资源帐户的电话号码，将呼叫方名称设置为 Contoso：</span><span class="sxs-lookup"><span data-stu-id="75eb0-142">To create a new Caller ID policy that sets the Caller ID to the phone number of the specified resource account and sets the Calling party name to Contoso:</span></span>

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

<span data-ttu-id="75eb0-143">如果已创建策略，可以使用 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet 更改现有策略，然后使用 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet 将设置应用到用户。</span><span class="sxs-lookup"><span data-stu-id="75eb0-143">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
    
### <a name="remove-a-policy-setting"></a><span data-ttu-id="75eb0-144">删除策略设置</span><span class="sxs-lookup"><span data-stu-id="75eb0-144">Remove a policy setting</span></span>

<span data-ttu-id="75eb0-145">要删除组织的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="75eb0-145">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="75eb0-146">要删除用户的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="75eb0-146">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="75eb0-147">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="75eb0-147">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="75eb0-148">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="75eb0-148">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="75eb0-149">使用Windows PowerShell，Microsoft 365单点管理来管理任务，从而简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="75eb0-149">With Windows PowerShell, you can manage Microsoft 365 using a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="75eb0-150">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="75eb0-150">To get started with Windows PowerShell, see these topics:</span></span>
    
- [<span data-ttu-id="75eb0-151">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75eb0-151">An introduction to Windows PowerShell</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="75eb0-152">你可能想要使用 Windows PowerShell 管理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75eb0-152">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="75eb0-153">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="75eb0-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="75eb0-154">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="75eb0-154">Learn about these advantages in the following topics:</span></span>
    
- <span data-ttu-id="75eb0-155">[使用 Microsoft 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="75eb0-155">[Best ways to manage Microsoft 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- [<span data-ttu-id="75eb0-156">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="75eb0-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="75eb0-157">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="75eb0-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="75eb0-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="75eb0-158">Related topics</span></span>
[<span data-ttu-id="75eb0-159">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="75eb0-159">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="75eb0-160">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="75eb0-160">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="75eb0-161">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="75eb0-161">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="75eb0-162">更多关于呼叫线路 ID 和主叫方名称的信息</span><span class="sxs-lookup"><span data-stu-id="75eb0-162">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="75eb0-163">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="75eb0-163">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="75eb0-164">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="75eb0-164">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
