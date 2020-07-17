---
title: Skype for Business Online 中使用用户标识的 cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aee680c6e55de62ff9d49724d3e480c00159aa4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755104"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="e84f8-102">Skype for Business Online 中使用用户标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="e84f8-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="e84f8-103">在 Skype for Business Online 中，可以通过多种不同的方式引用单个用户标识：</span><span class="sxs-lookup"><span data-stu-id="e84f8-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="e84f8-104">使用用户的 Active Directory 域服务显示名称。</span><span class="sxs-lookup"><span data-stu-id="e84f8-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="e84f8-105">例如：</span><span class="sxs-lookup"><span data-stu-id="e84f8-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="e84f8-106">使用用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="e84f8-106">Use the user’s SIP address.</span></span> <span data-ttu-id="e84f8-107">例如：</span><span class="sxs-lookup"><span data-stu-id="e84f8-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e84f8-108">使用用户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="e84f8-108">Use the user’s UPN.</span></span> <span data-ttu-id="e84f8-109">例如：</span><span class="sxs-lookup"><span data-stu-id="e84f8-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="e84f8-110">使用用户的 Active Directory 域服务可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="e84f8-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="e84f8-111">例如：</span><span class="sxs-lookup"><span data-stu-id="e84f8-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="e84f8-112">以下 cmdlet 接受用户标识：</span><span class="sxs-lookup"><span data-stu-id="e84f8-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="e84f8-113">[Disable-Disable-csmeetingroom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-114">[Enable-Disable-csmeetingroom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-115">[CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-116">[Disable-csmeetingroom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-117">[Get-csonlineuser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-118">[CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-119">[新 CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-120">[CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-121">[CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-122">[CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-123">[Disable-csmeetingroom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e84f8-124">[CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="e84f8-125">请注意，调用**Cs** cmdlet 之一时无需指定用户标识。</span><span class="sxs-lookup"><span data-stu-id="e84f8-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="e84f8-126">在这种情况下，cmdlet 将返回指定项目的所有实例。</span><span class="sxs-lookup"><span data-stu-id="e84f8-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="e84f8-127">例如，以下命令将返回已为 Skype for Business Online 启用的所有用户的相关信息：</span><span class="sxs-lookup"><span data-stu-id="e84f8-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="e84f8-128">只有当您要返回特定用户的信息时，Identity 参数才是必需的：</span><span class="sxs-lookup"><span data-stu-id="e84f8-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="e84f8-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e84f8-129">See Also</span></span>


[<span data-ttu-id="e84f8-130">Skype for Business Online 中的标识、范围和租户</span><span class="sxs-lookup"><span data-stu-id="e84f8-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="e84f8-131">[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e84f8-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

