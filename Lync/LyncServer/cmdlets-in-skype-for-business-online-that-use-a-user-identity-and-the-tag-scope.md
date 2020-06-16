---
title: Skype for Business Online 中使用用户标识和标记作用域的 cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9adf86a6ec6d2bd859411005dcc67b0dcbe09c7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755114"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="3546d-102">Skype for Business Online 中使用用户标识和标记作用域的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="3546d-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="3546d-103">**Grant-Cs** cmdlet （用于为用户分配策略）需要两个标识符：用户标识（identity 参数）和每用户策略的标识（PolicyName 参数）。</span><span class="sxs-lookup"><span data-stu-id="3546d-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="3546d-104">例如，若要向用户 Ken Myer 分配语音策略 RedmondVoicePolicy，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="3546d-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="3546d-105">向用户分配策略时有两个要记住的事项。</span><span class="sxs-lookup"><span data-stu-id="3546d-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="3546d-106">首先，只能分配每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="3546d-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="3546d-107">您不能向用户分配全局策略。</span><span class="sxs-lookup"><span data-stu-id="3546d-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="3546d-108">例如，以下命令将失败：</span><span class="sxs-lookup"><span data-stu-id="3546d-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="3546d-109">此命令将失败，因为无需分配全局策略。</span><span class="sxs-lookup"><span data-stu-id="3546d-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="3546d-110">如果要使用全局策略管理用户，只需确保为该用户分配每用户策略即可。</span><span class="sxs-lookup"><span data-stu-id="3546d-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="3546d-111">如果没有为用户分配每用户策略，则将自动使用全局策略管理用户。</span><span class="sxs-lookup"><span data-stu-id="3546d-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="3546d-112">如果已为用户分配每用户策略，并且您想要取消分配该策略并改为由全局策略管理的用户，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="3546d-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="3546d-113">在这种情况下，您将首先使用以下语法，它通过向该用户授予 null 策略来取消分配每个用户的策略：</span><span class="sxs-lookup"><span data-stu-id="3546d-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="3546d-114">Set-csvoicepolicy – Identity "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="3546d-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="3546d-115">其次，请记住，每个用户的策略是在标记作用域创建的。</span><span class="sxs-lookup"><span data-stu-id="3546d-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="3546d-116">但是，在指定策略名称时，可以省略标记**前缀**。</span><span class="sxs-lookup"><span data-stu-id="3546d-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="3546d-117">这两个命令相同：</span><span class="sxs-lookup"><span data-stu-id="3546d-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="3546d-118">如果要返回所有每用户策略的标识（或者至少，指定类型的每个用户的所有策略，如语音策略），请使用与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="3546d-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="3546d-119">以下 cmdlet 使用用户标识和标记作用域：</span><span class="sxs-lookup"><span data-stu-id="3546d-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="3546d-120">[Grant-Set-csclientpolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3546d-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3546d-121">[Grant-Set-csconferencingpolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3546d-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3546d-122">[Grant-Grant-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3546d-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3546d-123">[Grant-Set-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3546d-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3546d-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3546d-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3546d-125">[Grant-Set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3546d-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="3546d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3546d-126">See Also</span></span>


[<span data-ttu-id="3546d-127">Skype for Business Online 中的标识、范围和租户</span><span class="sxs-lookup"><span data-stu-id="3546d-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="3546d-128">[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3546d-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

