---
title: Teams 策略中采用了哪些特殊字数限制？
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
- ms.teamsadmincenter.policies.naming.error
description: 查看策略名称中有特殊字符以及可以执行哪些操作来修复这些问题。
ms.openlocfilehash: a3b7c8dfcba8d88f0428711a913344b33b431c37
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707587"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="2d7c3-103">Teams 策略中采用了哪些特殊字数限制？</span><span class="sxs-lookup"><span data-stu-id="2d7c3-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="2d7c3-104">**不能在 Microsoft 团队管理中心的名称中创建或编辑具有特殊字符的策略（对于邮件、会议等）**。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="2d7c3-105">如果策略名称包含特殊字符，则在 Microsoft 团队管理中心中管理这些策略将受到限制。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2d7c3-106">**因此，我们强烈建议策略名称不要包含特殊字符**。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="2d7c3-107">在团队中使用 PowerShell 为会议和消息创建的策略名称可以有特殊字符，如 @、#、$。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="2d7c3-108">但是，如果你想要更改 Microsoft 团队管理中心中的策略，你将无法执行。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="2d7c3-109">如果你有带有特殊字符的策略，你将需要使用 Windows PowerShell （永久）编辑策略，或在 Microsoft 团队管理中心中使用与旧策略相同的设置创建新策略，并将其分配给同一组用户。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="2d7c3-110">删除特殊字符</span><span class="sxs-lookup"><span data-stu-id="2d7c3-110">To remove special characters</span></span>

<span data-ttu-id="2d7c3-111">**步骤 1-使用 PowerShell 进行远程连接。**
如果尚未[安装 Windows PowerShell，请设置计算机](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="2d7c3-112">**步骤 2-获取旧策略的设置并捕获输出。**</span><span class="sxs-lookup"><span data-stu-id="2d7c3-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="2d7c3-113">此示例适用于[消息](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)策略。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="2d7c3-114">对于其他策略类型，步骤是相同的，但你必须使用正确的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="2d7c3-115">**步骤 3-创建新策略。**</span><span class="sxs-lookup"><span data-stu-id="2d7c3-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="2d7c3-116">你可以使用 Microsoft 团队管理中心或 PowerShell 创建具有相同设置的新策略。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="2d7c3-117">运行此操作将为你创建新策略，但你需要添加正确的设置，方法是先查看 "[设置-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) "，然后运行它：</span><span class="sxs-lookup"><span data-stu-id="2d7c3-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="2d7c3-118">**步骤 4-分配策略。**</span><span class="sxs-lookup"><span data-stu-id="2d7c3-118">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="2d7c3-119">有关此 cmdlet 的详细信息，请参阅、[授权 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="2d7c3-120">**步骤 5-删除旧策略。**</span><span class="sxs-lookup"><span data-stu-id="2d7c3-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="2d7c3-121">这将删除具有特殊字符的旧策略。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-121">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="2d7c3-122">有关此 cmdlet 的详细信息，请参阅[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="2d7c3-123">如果此命令成功，您就已完成。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="2d7c3-124">如果上面的命令返回错误，则是因为旧策略已分配给用户，因此你需要运行以从策略中删除所有分配的用户：</span><span class="sxs-lookup"><span data-stu-id="2d7c3-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="2d7c3-125">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="2d7c3-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="2d7c3-p105">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="2d7c3-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2d7c3-129">为什么需要使用 Office 365 PowerShell？</span><span class="sxs-lookup"><span data-stu-id="2d7c3-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="2d7c3-130">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="2d7c3-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="2d7c3-131">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你在一次为多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="2d7c3-132">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="2d7c3-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="2d7c3-133">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="2d7c3-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="2d7c3-134">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2d7c3-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="2d7c3-135">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="2d7c3-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="2d7c3-136">适用于 Skype for Business Online 的 Windows PowerShell 模块可创建连接到 Skype for business Online 和 Microsoft 团队的远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="2d7c3-137">此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="2d7c3-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

