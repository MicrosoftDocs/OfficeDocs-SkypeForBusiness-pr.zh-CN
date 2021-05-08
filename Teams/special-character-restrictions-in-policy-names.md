---
title: Teams 策略中的特殊字符限制
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: 查看策略名称中的特殊字符存在哪些问题，以及可以执行哪些措施来修复它。
ms.openlocfilehash: 15df8b64f423d1ee20df6e230e4a9cdbebcb56db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116980"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="2305a-103">Teams 策略中采用了哪些特殊字数限制？</span><span class="sxs-lookup"><span data-stu-id="2305a-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="2305a-104">**不能创建或** 编辑消息 (会议等) 在管理中心中名称中具有特殊字符Microsoft Teams策略。</span><span class="sxs-lookup"><span data-stu-id="2305a-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="2305a-105">如果策略名称包含特殊字符，则管理中心管理这些Microsoft Teams受到限制。</span><span class="sxs-lookup"><span data-stu-id="2305a-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2305a-106">**因此，我们强烈建议策略名称不要包含特殊字符**。</span><span class="sxs-lookup"><span data-stu-id="2305a-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="2305a-107">已使用 PowerShell 创建的策略名称可用于会议Teams消息，例如 @、#、$等特殊字符。</span><span class="sxs-lookup"><span data-stu-id="2305a-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="2305a-108">但是，如果要在管理中心内更改Microsoft Teams策略，则不能。</span><span class="sxs-lookup"><span data-stu-id="2305a-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="2305a-109">如果策略包含特殊字符，则需要使用 Windows PowerShell (forever) 编辑策略，或在 Microsoft Teams 管理中心中创建新策略，其设置与旧策略相同，并将其分配给同一组用户。</span><span class="sxs-lookup"><span data-stu-id="2305a-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="2305a-110">删除特殊字符</span><span class="sxs-lookup"><span data-stu-id="2305a-110">To remove special characters</span></span>

<span data-ttu-id="2305a-111">**步骤 1 - 使用 PowerShell 建立远程连接。**</span><span class="sxs-lookup"><span data-stu-id="2305a-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="2305a-112">Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="2305a-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="2305a-113">如果使用的是[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams最新版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="2305a-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


<span data-ttu-id="2305a-114">**步骤 2 - 获取旧策略的设置并捕获输出。**</span><span class="sxs-lookup"><span data-stu-id="2305a-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="2305a-115">此示例适用于消息 [传送](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 策略。</span><span class="sxs-lookup"><span data-stu-id="2305a-115">This example is for a [Messaging](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="2305a-116">对于其他策略类型，步骤相同，但必须使用正确的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2305a-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="2305a-117">**步骤 3 - 创建新策略。**</span><span class="sxs-lookup"><span data-stu-id="2305a-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="2305a-118">可以使用管理中心或 PowerShell 使用相同的设置Microsoft Teams策略。</span><span class="sxs-lookup"><span data-stu-id="2305a-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="2305a-119">运行此操作会创建一个新策略，但需要通过查看 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 并运行它来添加正确的设置：</span><span class="sxs-lookup"><span data-stu-id="2305a-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="2305a-120">**步骤 4 - 分配策略。**</span><span class="sxs-lookup"><span data-stu-id="2305a-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="2305a-121">有关此 cmdlet 的信息，请参阅[Grant-CsTeamsMessagingPolicy。](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2305a-121">See, [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="2305a-122">**步骤 5 - 删除旧策略。**</span><span class="sxs-lookup"><span data-stu-id="2305a-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="2305a-123">这会删除包含特殊字符的旧策略。</span><span class="sxs-lookup"><span data-stu-id="2305a-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="2305a-124">有关此 cmdlet 详细信息，请参阅[Remove-CsTeamsMessagingPolicy。](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2305a-124">See, [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="2305a-125">如果此命令成功，则操作完成。</span><span class="sxs-lookup"><span data-stu-id="2305a-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="2305a-126">如果上述命令返回错误，这是因为旧策略已分配给用户，因此需要运行 以从策略中删除所有分配的用户：</span><span class="sxs-lookup"><span data-stu-id="2305a-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="2305a-127">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="2305a-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="2305a-128">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="2305a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2305a-129">使用Windows PowerShell，Microsoft 365管理Office 365管理点，可在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="2305a-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="2305a-130">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="2305a-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2305a-131">为何需要使用 powerShell Office 365？</span><span class="sxs-lookup"><span data-stu-id="2305a-131">Why you need to use Office 365 PowerShell?</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="2305a-132">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="2305a-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="2305a-133">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户更改设置时。</span><span class="sxs-lookup"><span data-stu-id="2305a-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="2305a-134">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="2305a-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="2305a-135">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="2305a-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [<span data-ttu-id="2305a-136">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2305a-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="2305a-137">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="2305a-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="2305a-138">使用 Windows PowerShell Online 的 Skype for Business 模块可以创建连接到 Windows PowerShell Online 和 Skype for Business Microsoft Teams 的远程Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="2305a-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="2305a-139">此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="2305a-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
