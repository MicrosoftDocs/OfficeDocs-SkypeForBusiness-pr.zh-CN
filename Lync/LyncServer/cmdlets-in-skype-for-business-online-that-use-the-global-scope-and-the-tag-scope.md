---
title: Skype for Business Online 中使用全局范围和标记范围的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51327b98be69f92736c1c8523c97b4de6463273b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837094"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="353ab-102">Skype for Business Online 中使用全局范围和标记范围的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="353ab-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="353ab-103">在 Skype for Business Online 中, 可以在*全局范围内*或在*标记作用*域 (或*每用户范围*) 内配置策略。</span><span class="sxs-lookup"><span data-stu-id="353ab-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="353ab-104">使用**Cs** cmdlet 时, 无需指定范围或标识。</span><span class="sxs-lookup"><span data-stu-id="353ab-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="353ab-105">如果您调用其中一个 cmdlet 且不带任何参数, 则将返回所有相关项。</span><span class="sxs-lookup"><span data-stu-id="353ab-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="353ab-106">例如, 此命令将返回有关所有外部访问策略的信息:</span><span class="sxs-lookup"><span data-stu-id="353ab-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="353ab-107">如果要限制返回的数据, 只需包含 Identity 参数或 Filter 参数。</span><span class="sxs-lookup"><span data-stu-id="353ab-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="353ab-108">例如, 若要仅返回全局策略, 请使用以下命令:</span><span class="sxs-lookup"><span data-stu-id="353ab-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="353ab-109">若要返回具有 "RedmondAccessPolicy" 标识的每用户策略, 请使用以下命令:</span><span class="sxs-lookup"><span data-stu-id="353ab-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="353ab-110">引用每用户策略时, 标记<STRONG>前缀</STRONG>是可选的。</span><span class="sxs-lookup"><span data-stu-id="353ab-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="353ab-111">此语法 (包括前缀) 也有效:</span><span class="sxs-lookup"><span data-stu-id="353ab-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="353ab-112">CsExternalAccessPolicy-Identity "tag: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="353ab-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="353ab-113">若要返回除全局策略 (即所有每用户策略) 之外的所有策略, 请使用以下命令:</span><span class="sxs-lookup"><span data-stu-id="353ab-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="353ab-114">以下 cmdlet 对全局范围和每用户 (标记) 作用域进行操作:</span><span class="sxs-lookup"><span data-stu-id="353ab-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="353ab-115">[Set-csclientpolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="353ab-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="353ab-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="353ab-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="353ab-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="353ab-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="353ab-118">[CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="353ab-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="353ab-119">[CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="353ab-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="353ab-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="353ab-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="353ab-121">[CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="353ab-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="353ab-122">尽管名称、拨号计划和功能, 请说出策略。</span><span class="sxs-lookup"><span data-stu-id="353ab-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="353ab-123">使用 "<EM>拨号计划</EM>" 而不是 "拨号策略", 以保留早期版本的 Lync Server 所使用的术语。</span><span class="sxs-lookup"><span data-stu-id="353ab-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="353ab-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="353ab-124">See Also</span></span>


[<span data-ttu-id="353ab-125">Skype for Business Online 中的身份、范围和租户</span><span class="sxs-lookup"><span data-stu-id="353ab-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="353ab-126">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="353ab-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

