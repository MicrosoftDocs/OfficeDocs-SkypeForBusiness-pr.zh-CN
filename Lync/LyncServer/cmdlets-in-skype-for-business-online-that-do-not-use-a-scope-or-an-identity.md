---
title: Skype for Business Online 中不使用作用域或标识的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7f6632640277a6a99626c18f458100f6a8cea0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837092"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="53f15-102">Skype for Business Online 中不使用作用域或标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="53f15-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="53f15-103">修改允许的列表和阻止的列表时使用的 cmdlet (确定允许用户与哪些外部组织通信的列表) 不使用范围或标识。</span><span class="sxs-lookup"><span data-stu-id="53f15-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="53f15-104">实际上, **CsEdgeAllowAllKnownDomains** cmdlet 没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="53f15-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="53f15-105">不使用作用域或标识的 cmdlet 为:</span><span class="sxs-lookup"><span data-stu-id="53f15-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="53f15-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53f15-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="53f15-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53f15-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="53f15-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53f15-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="53f15-109">请注意, 对于**CsEdgeAllowList** Cmdlet 和**CsEdgeDomainPattern** Cmdlet, 必须包含 Domain 参数。</span><span class="sxs-lookup"><span data-stu-id="53f15-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="53f15-110">例如：</span><span class="sxs-lookup"><span data-stu-id="53f15-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="53f15-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53f15-111">See Also</span></span>


[<span data-ttu-id="53f15-112">Skype for Business Online 中的身份、范围和租户</span><span class="sxs-lookup"><span data-stu-id="53f15-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="53f15-113">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53f15-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

