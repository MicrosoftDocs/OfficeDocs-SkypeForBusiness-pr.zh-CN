---
title: 什么是团队策略中的特殊字符限制？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: 请参阅有与特殊字符的策略和解决办法可以执行的操作的名称中哪些问题。
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192161"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="a307a-103">什么是团队策略中的特殊字符限制？</span><span class="sxs-lookup"><span data-stu-id="a307a-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="a307a-104">**虽然可以在工作组中创建的策略的名称中使用特殊字符，我们强烈建议您不。**</span><span class="sxs-lookup"><span data-stu-id="a307a-104">**Although you can use special characters in the names of policies you created in Teams, we strongly recommend that you don't.**</span></span>

<span data-ttu-id="a307a-105">策略名称为会议、 聊天和 prescense，创建并在团队中的其他事项可以具有特殊字符，如 @，#、 $。</span><span class="sxs-lookup"><span data-stu-id="a307a-105">Policy names that you create for meetings, chat and prescense, and other things in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="a307a-106">但是，如果您想要更改业务管理中心中的 Microsoft 团队和 Skype 的名称，将看不到。</span><span class="sxs-lookup"><span data-stu-id="a307a-106">However, if you are wanting to make changes to the name in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="a307a-107">您必须使用 Windows PowerShell 和正确的策略 cmdlet 进行更改。</span><span class="sxs-lookup"><span data-stu-id="a307a-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="a307a-108">例如，如果您有一个会议策略与特殊字符，并且想要更改名称或名称中删除特殊字符，您需要使用集 CsMeetingPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a307a-108">For example, if you have a meeting policy with special characters and you want to change the name or remove the special characters from the name, you will need to use the Set-CsMeetingPolicy cmdlet.</span></span> 

<span data-ttu-id="a307a-109">下面是您可能需要执行此操作的策略 cmdlet 的列表：</span><span class="sxs-lookup"><span data-stu-id="a307a-109">Here is a list of the policy cmdlets that you may need to do this:</span></span>
1. <span data-ttu-id="a307a-110">设置 CsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a307a-110">Set-CsMeetingPolicy</span></span>
2. <span data-ttu-id="a307a-111">设置 CsAppPolicy</span><span class="sxs-lookup"><span data-stu-id="a307a-111">Set-CsAppPolicy</span></span>
3. <span data-ttu-id="a307a-112">Set-\*</span><span class="sxs-lookup"><span data-stu-id="a307a-112">Set-\*</span></span>


