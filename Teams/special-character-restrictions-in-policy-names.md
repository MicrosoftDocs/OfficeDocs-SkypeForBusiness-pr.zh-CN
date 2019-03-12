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
- Teams_ITAdmin_Help
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: 请参阅有与特殊字符的策略和解决办法可以执行的操作的名称中哪些问题。
ms.openlocfilehash: 40cf70b61c8e939c2a1096825e83c676083b9950
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541053"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="735c5-103">Teams 策略中采用了哪些特殊字数限制？</span><span class="sxs-lookup"><span data-stu-id="735c5-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="735c5-104">**无法创建或编辑策略 （对于消息、 会议、 等） 的已在名称中的 Microsoft 团队管理特殊字符居中**。</span><span class="sxs-lookup"><span data-stu-id="735c5-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="735c5-105">如果某个策略名称包含特殊字符，您将在管理这些策略的 Microsoft 团队管理中心中的限制。</span><span class="sxs-lookup"><span data-stu-id="735c5-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="735c5-106">**因此，我们强烈建议策略名称不包含特殊字符**。</span><span class="sxs-lookup"><span data-stu-id="735c5-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="735c5-107">使用 PowerShell 的会议和消息团队可以如具有特殊字符已创建的策略名称 @，#、 $。</span><span class="sxs-lookup"><span data-stu-id="735c5-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="735c5-108">但是，如果您想要更改的 Microsoft 团队管理中心中的策略，将看不到。</span><span class="sxs-lookup"><span data-stu-id="735c5-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="735c5-109">如果必须具有特殊字符的策略，您需要编辑策略使用 Windows PowerShell （始终） 或在与旧策略相同的设置的 Microsoft 团队管理中心创建新的策略和将其分配给同一组的用户。</span><span class="sxs-lookup"><span data-stu-id="735c5-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="735c5-110">若要删除特殊字符</span><span class="sxs-lookup"><span data-stu-id="735c5-110">To remove special characters</span></span>

<span data-ttu-id="735c5-111">**步骤 1 – 进行远程 powershell 连接。**
如果尚未尚未[设置您的计算机的 Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="735c5-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="735c5-112">**步骤 2-获取旧策略设置和捕获输出。**</span><span class="sxs-lookup"><span data-stu-id="735c5-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="735c5-113">此示例适用于[消息](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)策略。</span><span class="sxs-lookup"><span data-stu-id="735c5-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="735c5-114">步骤是其他策略类型相同，但您必须使用正确的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="735c5-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="735c5-115">**步骤 3-创建新的策略。**</span><span class="sxs-lookup"><span data-stu-id="735c5-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="735c5-116">您可以使用的 Microsoft 团队管理中心或 PowerShell 相同的设置创建新策略。</span><span class="sxs-lookup"><span data-stu-id="735c5-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="735c5-117">运行此会为您创建新策略，但您需要通过查看[设置 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ，然后运行它添加正确设置：</span><span class="sxs-lookup"><span data-stu-id="735c5-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="735c5-118">**步骤 4-将策略分配。**</span><span class="sxs-lookup"><span data-stu-id="735c5-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="735c5-119">请参阅[授予 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)有关此 cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="735c5-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="735c5-120">**步骤 5-删除旧的策略。**</span><span class="sxs-lookup"><span data-stu-id="735c5-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="735c5-121">这将删除特殊字符的旧策略。</span><span class="sxs-lookup"><span data-stu-id="735c5-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="735c5-122">请参阅[删除 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)有关此 cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="735c5-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="735c5-123">如果此命令成功执行，即已完成。</span><span class="sxs-lookup"><span data-stu-id="735c5-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="735c5-124">如果上述命令将返回错误，这是因为旧策略分配给用户，因此您需要运行以从策略中删除所有已分配的用户：</span><span class="sxs-lookup"><span data-stu-id="735c5-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="735c5-125">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="735c5-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="735c5-p105">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="735c5-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="735c5-129">为什么需要使用 Office 365 PowerShell？</span><span class="sxs-lookup"><span data-stu-id="735c5-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="735c5-130">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="735c5-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="735c5-131">Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。</span><span class="sxs-lookup"><span data-stu-id="735c5-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="735c5-132">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="735c5-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="735c5-133">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="735c5-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="735c5-134">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="735c5-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="735c5-135">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="735c5-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="735c5-136">Skype 业务 online 的 Windows PowerShell 模块使您能够创建了业务 Online 和 Microsoft 团队连接到 Skype 远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="735c5-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="735c5-137">此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="735c5-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

