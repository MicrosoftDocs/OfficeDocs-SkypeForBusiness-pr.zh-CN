---
title: Skype for Business Online 中使用用户标识的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e0086f4b04dd199a285820db811a57899cdc0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837095"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="34dea-102">Skype for Business Online 中使用用户标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="34dea-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="34dea-103">在 Skype for Business Online 中, 可以通过多种不同的方式引用单个用户标识:</span><span class="sxs-lookup"><span data-stu-id="34dea-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="34dea-104">使用用户的 Active Directory 域服务显示名称。</span><span class="sxs-lookup"><span data-stu-id="34dea-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="34dea-105">例如：</span><span class="sxs-lookup"><span data-stu-id="34dea-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="34dea-106">使用用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="34dea-106">Use the user’s SIP address.</span></span> <span data-ttu-id="34dea-107">例如：</span><span class="sxs-lookup"><span data-stu-id="34dea-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="34dea-108">使用用户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="34dea-108">Use the user’s UPN.</span></span> <span data-ttu-id="34dea-109">例如：</span><span class="sxs-lookup"><span data-stu-id="34dea-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="34dea-110">使用用户的 Active Directory 域服务可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="34dea-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="34dea-111">例如：</span><span class="sxs-lookup"><span data-stu-id="34dea-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="34dea-112">以下 cmdlet 接受用户标识:</span><span class="sxs-lookup"><span data-stu-id="34dea-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="34dea-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="34dea-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="34dea-125">请注意, 在调用其中一个 "**获取 Cs** " cmdlet 时无需指定用户标识。</span><span class="sxs-lookup"><span data-stu-id="34dea-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="34dea-126">在这种情况下, cmdlet 将返回指定项目的所有实例。</span><span class="sxs-lookup"><span data-stu-id="34dea-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="34dea-127">例如, 此命令将返回已启用 Skype for Business Online 的所有用户的相关信息:</span><span class="sxs-lookup"><span data-stu-id="34dea-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="34dea-128">只有当你希望返回特定用户的信息时, Identity 参数才是必需的:</span><span class="sxs-lookup"><span data-stu-id="34dea-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="34dea-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34dea-129">See Also</span></span>


[<span data-ttu-id="34dea-130">Skype for Business Online 中的身份、范围和租户</span><span class="sxs-lookup"><span data-stu-id="34dea-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="34dea-131">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34dea-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

