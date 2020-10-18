---
title: Lync Server 2013： IM 和状态 cmdlet
description: Lync Server 2013： IM 和状态 cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b6447219006737ba77cddd76aad0ac96368dab3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573298"
---
# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2f309-103">Lync Server 2013 中的 IM 和状态 cmdlet</span><span class="sxs-lookup"><span data-stu-id="2f309-103">IM and presence cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f309-104">_**上次修改的主题：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="2f309-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="2f309-105">即时消息 (IM) 和状态 cmdlet 允许您通过 Windows PowerShell 管理这些客户端功能。</span><span class="sxs-lookup"><span data-stu-id="2f309-105">Instant Messaging (IM) and presence cmdlets allow you to manage those client features through Windows PowerShell.</span></span> <span data-ttu-id="2f309-106">可以在 global、site 或每用户作用域设置应用于用户的状态策略。</span><span class="sxs-lookup"><span data-stu-id="2f309-106">You can set presence policies that apply to users at the global, site, or per-user scope.</span></span> <span data-ttu-id="2f309-107">还可以配置各种隐私和 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="2f309-107">You can also configure various privacy and IM features.</span></span>

<div>

## <a name="im-and-presence-cmdlets"></a><span data-ttu-id="2f309-108">IM 和状态 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2f309-108">IM and Presence Cmdlets</span></span>

<span data-ttu-id="2f309-109">要配置 IM 和状态，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2f309-109">The configure IM and presence, use the following cmdlets:</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-110">[CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-110">[Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-111">[Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-111">[Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-112">[新 CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-112">[New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-113">[CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-113">[Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-114">[CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-114">[Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2f309-115">[CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-115">[Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="2f309-116">[新 CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-116">[New-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="2f309-117">[CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-117">[Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="2f309-118">[CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-118">[Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-119">[CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-119">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-120">[新 CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-120">[New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-121">[CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-121">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-122">[CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-123">[CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-123">[Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-124">[CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-124">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-125">[新 CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-125">[New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-126">[CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-126">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-127">[CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-127">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-128">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-128">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-129">[新 CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-129">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-130">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-130">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-131">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-131">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-132">[CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-132">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-133">[新 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-133">[New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-134">[CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-134">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2f309-135">[CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-135">[Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-136">[Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-136">[Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-137">[Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-137">[Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-138">[Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-138">[Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-139">[Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-139">[Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2f309-140">[Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2f309-140">[Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f309-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f309-141">See Also</span></span>


[<span data-ttu-id="2f309-142">Lync Server 2013 中的客户端管理 cmdlet</span><span class="sxs-lookup"><span data-stu-id="2f309-142">Client management cmdlets in Lync Server 2013</span></span>](lync-server-2013-client-management-cmdlets.md)  


[<span data-ttu-id="2f309-143">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="2f309-143">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

