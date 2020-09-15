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
description: 查看策略名称中有特殊字符以及可以执行哪些操作来修复这些问题。
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814711"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="4d35b-103">Teams 策略中采用了哪些特殊字数限制？</span><span class="sxs-lookup"><span data-stu-id="4d35b-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="4d35b-104">**无法创建或编辑邮件、会议等的策略 (在 Microsoft 团队管理中心的名称中有特殊字符的 ) 。**</span><span class="sxs-lookup"><span data-stu-id="4d35b-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="4d35b-105">如果策略名称包含特殊字符，则在 Microsoft 团队管理中心中管理这些策略将受到限制。</span><span class="sxs-lookup"><span data-stu-id="4d35b-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4d35b-106">**因此，我们强烈建议策略名称不要包含特殊字符**。</span><span class="sxs-lookup"><span data-stu-id="4d35b-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="4d35b-107">在团队中使用 PowerShell 为会议和消息创建的策略名称可以有特殊字符，如 @、#、$。</span><span class="sxs-lookup"><span data-stu-id="4d35b-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="4d35b-108">但是，如果你想要更改 Microsoft 团队管理中心中的策略，你将无法执行。</span><span class="sxs-lookup"><span data-stu-id="4d35b-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="4d35b-109">如果你有带特殊字符的策略，你将需要使用 Windows PowerShell (永久) 或使用与旧策略相同的设置在 Microsoft 团队管理中心中创建新策略，并将其分配给同一组用户。</span><span class="sxs-lookup"><span data-stu-id="4d35b-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="4d35b-110">删除特殊字符</span><span class="sxs-lookup"><span data-stu-id="4d35b-110">To remove special characters</span></span>

<span data-ttu-id="4d35b-111">**步骤 1-使用 PowerShell 进行远程连接。**</span><span class="sxs-lookup"><span data-stu-id="4d35b-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="4d35b-112">Skype for Business Online 连接器目前是最新团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="4d35b-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="4d35b-113">如果您使用的是最新的 [团队 PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="4d35b-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="4d35b-114">**步骤 2-获取旧策略的设置并捕获输出。**</span><span class="sxs-lookup"><span data-stu-id="4d35b-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="4d35b-115">此示例适用于 [消息](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 策略。</span><span class="sxs-lookup"><span data-stu-id="4d35b-115">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="4d35b-116">对于其他策略类型，步骤是相同的，但你必须使用正确的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4d35b-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="4d35b-117">**步骤 3-创建新策略。**</span><span class="sxs-lookup"><span data-stu-id="4d35b-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="4d35b-118">你可以使用 Microsoft 团队管理中心或 PowerShell 创建具有相同设置的新策略。</span><span class="sxs-lookup"><span data-stu-id="4d35b-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="4d35b-119">运行此操作将为你创建新策略，但你需要添加正确的设置，方法是先查看 " [设置-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) "，然后运行它：</span><span class="sxs-lookup"><span data-stu-id="4d35b-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="4d35b-120">**步骤 4-分配策略。**</span><span class="sxs-lookup"><span data-stu-id="4d35b-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="4d35b-121">有关此 cmdlet 的详细信息，请参阅、 [授权 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="4d35b-121">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="4d35b-122">**步骤 5-删除旧策略。**</span><span class="sxs-lookup"><span data-stu-id="4d35b-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="4d35b-123">这将删除具有特殊字符的旧策略。</span><span class="sxs-lookup"><span data-stu-id="4d35b-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="4d35b-124">有关此 cmdlet 的详细信息，请参阅 [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="4d35b-124">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="4d35b-125">如果此命令成功，您就已完成。</span><span class="sxs-lookup"><span data-stu-id="4d35b-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="4d35b-126">如果上面的命令返回错误，则是因为旧策略已分配给用户，因此你需要运行以从策略中删除所有分配的用户：</span><span class="sxs-lookup"><span data-stu-id="4d35b-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4d35b-127">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="4d35b-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="4d35b-128">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="4d35b-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4d35b-129">使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365，这可以在你有多个任务时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="4d35b-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4d35b-130">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="4d35b-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4d35b-131">为什么需要使用 Office 365 PowerShell？</span><span class="sxs-lookup"><span data-stu-id="4d35b-131">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4d35b-132">通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="4d35b-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4d35b-133">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你在一次为多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="4d35b-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="4d35b-134">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="4d35b-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4d35b-135">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="4d35b-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="4d35b-136">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4d35b-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4d35b-137">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="4d35b-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4d35b-138">适用于 Skype for Business Online 的 Windows PowerShell 模块可创建连接到 Skype for business Online 和 Microsoft 团队的远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="4d35b-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="4d35b-139">此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="4d35b-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

