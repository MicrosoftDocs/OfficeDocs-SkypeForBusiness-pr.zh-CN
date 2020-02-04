---
title: Skype for Business Online 中使用用户标识和标记作用域的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727562"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="a74c8-102">Skype for Business Online 中使用用户标识和标记作用域的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="a74c8-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="a74c8-103">**授权-Cs** cmdlet （用于为用户分配策略）需要两个标识符：用户标识（identity 参数）和每用户策略的标识（PolicyName 参数）。</span><span class="sxs-lookup"><span data-stu-id="a74c8-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="a74c8-104">例如，若要向用户 Ken Myer 分配语音策略 RedmondVoicePolicy，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="a74c8-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="a74c8-105">向用户分配策略时需要注意两个事项。</span><span class="sxs-lookup"><span data-stu-id="a74c8-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="a74c8-106">首先，只能分配每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="a74c8-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="a74c8-107">不能将全局策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a74c8-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="a74c8-108">例如，此命令将失败：</span><span class="sxs-lookup"><span data-stu-id="a74c8-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="a74c8-109">此命令失败，因为无需分配全局策略。</span><span class="sxs-lookup"><span data-stu-id="a74c8-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="a74c8-110">如果想要使用全局策略管理用户，请确保不要为该用户分配每用户策略。</span><span class="sxs-lookup"><span data-stu-id="a74c8-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="a74c8-111">如果没有为用户分配每用户策略，则将通过使用全局策略自动管理该用户。</span><span class="sxs-lookup"><span data-stu-id="a74c8-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="a74c8-112">如果用户以前已分配了每用户策略，并且想要取消分配该策略，并且用户改为由全局策略管理的用户，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="a74c8-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="a74c8-113">在这种情况下，你将首先使用以下语法，该语法通过向该用户授予 null 策略来取消每用户策略：</span><span class="sxs-lookup"><span data-stu-id="a74c8-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="a74c8-114">授权-CsVoicePolicy-身份 "Ken Myer"-PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="a74c8-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="a74c8-115">其次，请记住，每个用户的策略是在标记作用域创建的。</span><span class="sxs-lookup"><span data-stu-id="a74c8-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="a74c8-116">但是，你可以在指定策略名称时省略标记**前缀**。</span><span class="sxs-lookup"><span data-stu-id="a74c8-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="a74c8-117">这两个命令相同：</span><span class="sxs-lookup"><span data-stu-id="a74c8-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="a74c8-118">如果你想要为你的所有每用户策略（或者至少是指定类型的每个用户策略，如语音策略）返回标识，请使用类似下面的命令：</span><span class="sxs-lookup"><span data-stu-id="a74c8-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="a74c8-119">以下 cmdlet 使用用户标识和标记作用域：</span><span class="sxs-lookup"><span data-stu-id="a74c8-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="a74c8-120">[授权-Set-csclientpolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a74c8-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a74c8-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a74c8-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a74c8-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a74c8-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a74c8-123">[授权-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a74c8-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a74c8-124">[授权-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a74c8-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a74c8-125">[授权-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a74c8-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="a74c8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a74c8-126">See Also</span></span>


[<span data-ttu-id="a74c8-127">Skype for Business Online 中的身份、范围和租户</span><span class="sxs-lookup"><span data-stu-id="a74c8-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="a74c8-128">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a74c8-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

