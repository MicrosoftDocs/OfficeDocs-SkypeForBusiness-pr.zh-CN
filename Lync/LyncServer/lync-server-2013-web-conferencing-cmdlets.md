---
title: Lync Server 2013： Web 会议 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing cmdlets
ms:assetid: dac4d934-1500-4799-be4d-82809d4e7eb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415675(v=OCS.15)
ms:contentKeyID: 48185556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61b9c45ce3ed5b2076ba981d74323757c5d73ab8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e62e5-102">Lync Server 2013 中的 Web 会议 cmdlet</span><span class="sxs-lookup"><span data-stu-id="e62e5-102">Web conferencing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e62e5-103">_**上次修改的主题：** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="e62e5-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="e62e5-104">会议和联机会议是 Microsoft Lync Server 2013 中的重要元素。</span><span class="sxs-lookup"><span data-stu-id="e62e5-104">Conferencing and online meetings are important elements in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e62e5-105">CsConferencingConfiguration 和 Set-csconferencingpolicy cmdlet 是使用 Windows PowerShell 管理会议的主要管理工具。</span><span class="sxs-lookup"><span data-stu-id="e62e5-105">The CsConferencingConfiguration and CsConferencingPolicy cmdlets are the primary administrative tools for managing conferences by using Windows PowerShell.</span></span>

<div>

## <a name="web-conferencing-cmdlets"></a><span data-ttu-id="e62e5-106">Web Conferencing Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e62e5-106">Web Conferencing Cmdlets</span></span>

<span data-ttu-id="e62e5-107">[Set-csclientpolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))和[set-csclientpolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15)) cmdlet 提供了其他配置和管理 Lync Server 2013 的方法。</span><span class="sxs-lookup"><span data-stu-id="e62e5-107">The [New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15)) and [Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15)) cmdlets provide additional ways to configure and manage Lync Server 2013.</span></span>

<span data-ttu-id="e62e5-108">**Web 会议**</span><span class="sxs-lookup"><span data-stu-id="e62e5-108">**Web Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-109">[CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-109">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-110">[CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-110">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-111">[CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-111">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e62e5-112">[CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-112">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e62e5-113">[CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-113">[Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-114">[新 CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-114">[New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-115">[CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-115">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-116">[CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-116">[Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e62e5-117">[Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-118">[Grant-Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-118">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-119">[新 Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-119">[New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-120">[Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-120">[Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-121">[Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-121">[Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e62e5-122">[Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-122">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-123">[新 Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-123">[New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-124">[Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-124">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-125">[Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-125">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e62e5-126">[Disable-Disable-csmeetingroom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-126">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="e62e5-127">[Enable-Disable-csmeetingroom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-127">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="e62e5-128">[Disable-csmeetingroom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-128">[Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="e62e5-129">[移动-Disable-csmeetingroom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-129">[Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="e62e5-130">[Disable-csmeetingroom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-130">[Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e62e5-131">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-131">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-132">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-132">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-133">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-133">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-134">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-134">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-135">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-135">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e62e5-136">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e62e5-136">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e62e5-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e62e5-137">See Also</span></span>


[<span data-ttu-id="e62e5-138">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="e62e5-138">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

