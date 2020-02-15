---
title: Skype for Business Online 中使用全局作用域和标记作用域的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998201bf7772003c83ae27d56b3a238f9f0ca055
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001147"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="6f126-102">Skype for Business Online 中使用全局作用域和标记作用域的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="6f126-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="6f126-103">在 Skype for Business Online 中，可以在*全局范围*或在*标记范围*（或*每用户范围*）内配置策略。</span><span class="sxs-lookup"><span data-stu-id="6f126-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="6f126-104">使用**Cs** cmdlet 时，不必指定范围或标识。</span><span class="sxs-lookup"><span data-stu-id="6f126-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="6f126-105">如果调用其中一个不带任何参数的 cmdlet，则将返回所有相关项目。</span><span class="sxs-lookup"><span data-stu-id="6f126-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="6f126-106">例如，以下命令将返回有关所有外部访问策略的信息：</span><span class="sxs-lookup"><span data-stu-id="6f126-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="6f126-107">如果要限制返回的数据，则需要仅包含 Identity 参数或 Filter 参数。</span><span class="sxs-lookup"><span data-stu-id="6f126-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="6f126-108">例如，若要仅返回全局策略，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="6f126-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="6f126-109">若要返回具有标识 "RedmondAccessPolicy" 的每用户策略，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="6f126-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="6f126-110">在引用每用户策略时，标记<STRONG>前缀</STRONG>是可选的。</span><span class="sxs-lookup"><span data-stu-id="6f126-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="6f126-111">此语法（包括前缀）也有效：</span><span class="sxs-lookup"><span data-stu-id="6f126-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="6f126-112">Set-csexternalaccesspolicy – Identity "标记： RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="6f126-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="6f126-113">若要返回除全局策略之外的所有策略（即每个用户的所有策略），请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="6f126-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="6f126-114">以下 cmdlet 对全局作用域和每用户（标记）作用域运行：</span><span class="sxs-lookup"><span data-stu-id="6f126-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="6f126-115">[Set-csclientpolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6f126-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6f126-116">[Set-csconferencingpolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6f126-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6f126-117">[Grant-csdialplan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6f126-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6f126-118">[Set-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6f126-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6f126-119">[CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6f126-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6f126-120">[CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6f126-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6f126-121">[Set-csvoicepolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6f126-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="6f126-122">尽管名称，但在功能上讲，拨号计划是策略。</span><span class="sxs-lookup"><span data-stu-id="6f126-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="6f126-123">使用 "<EM>拨号计划</EM>" 来代替（例如，拨号策略），以保留旧版 Lync Server 使用的术语。</span><span class="sxs-lookup"><span data-stu-id="6f126-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="6f126-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f126-124">See Also</span></span>


[<span data-ttu-id="6f126-125">Skype for Business Online 中的标识、范围和租户</span><span class="sxs-lookup"><span data-stu-id="6f126-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="6f126-126">[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6f126-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

