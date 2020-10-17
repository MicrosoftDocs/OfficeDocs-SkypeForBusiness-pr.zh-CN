---
title: Lync Server 2013：增强的 9-1-1 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 cmdlets
ms:assetid: e560c688-7b34-4bd7-8104-24f390644105
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415678(v=OCS.15)
ms:contentKeyID: 48185650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bdea8e9aeed89a52b6e288be00afb9ed5fbeb27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533209"
---
# <a name="enhanced-9-1-1-cmdlets-in-lync-server-2013"></a><span data-ttu-id="5d5f3-102">Lync Server 2013 中增强的 9-1-1 cmdlet</span><span class="sxs-lookup"><span data-stu-id="5d5f3-102">Enhanced 9-1-1 cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d5f3-103">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="5d5f3-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="5d5f3-104">Microsoft Lync Server 2013 随附的 cmdlet 允许您实施和管理增强的 9-1-1 (E9-1-1) 企业语音解决方案的实施。</span><span class="sxs-lookup"><span data-stu-id="5d5f3-104">Microsoft Lync Server 2013 ships with cmdlets that allow you to implement and manage the Enhanced 9-1-1 (E9-1-1) implementation of an Enterprise Voice solution.</span></span> <span data-ttu-id="5d5f3-105">使用这些 cmdlet 将连接点映射到物理地址，并配置企业语音用户所需的设置，以成功完成紧急呼叫并将位置自动发送给紧急服务提供商。</span><span class="sxs-lookup"><span data-stu-id="5d5f3-105">Use these cmdlets to map connection points to physical addresses and to configure settings required for Enterprise Voice users to successfully complete emergency calls and automatically send a location to the emergency services provider.</span></span> <span data-ttu-id="5d5f3-106">无法配置 Lync Server 控制面板中的 E9-1-1，必须使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5d5f3-106">You cannot configure E9-1-1 from the Lync Server Control Panel, you must use cmdlets.</span></span>

<div>

## <a name="enhanced-9-1-1-cmdlets"></a><span data-ttu-id="5d5f3-107">增强型 9-1-1 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5d5f3-107">Enhanced 9-1-1 Cmdlets</span></span>

<span data-ttu-id="5d5f3-108">使用以下 cmdlet 配置 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="5d5f3-108">Use the following cmdlets to configure E9-1-1.</span></span>

<span data-ttu-id="5d5f3-109">**增强型 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="5d5f3-109">**Enhanced 9-1-1**</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-110">[CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-110">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-111">[CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-111">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-112">[CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-112">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-113">[CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-113">[Get-CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-114">[Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-114">[Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-115">[Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-115">[Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-116">[Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-116">[Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-117">[调试-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-117">[Debug-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-118">[Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-118">[Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-119">[发布-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-119">[Publish-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-120">[取消发布-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-120">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-121">[CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-121">[Get-CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-122">[CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-122">[Remove-CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-123">[CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-123">[Set-CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-124">[CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-124">[Get-CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-125">[CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-125">[Remove-CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-126">[CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-126">[Set-CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-127">[CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-127">[Get-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-128">[CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-128">[Remove-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-129">[CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-129">[Set-CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-130">[CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-130">[Get-CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-131">[CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-131">[Remove-CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-132">[CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-132">[Set-CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-133">[CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-133">[Get-CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-134">[CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-134">[Remove-CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-135">[CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-135">[Set-CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-136">[CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-136">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-137">[CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-137">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-138">[CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-138">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-139">[New-cslocationpolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-139">[Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-140">[Grant-New-cslocationpolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-140">[Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-141">[新 New-cslocationpolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-141">[New-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-142">[New-cslocationpolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-142">[Remove-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-143">[New-cslocationpolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-143">[Set-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-144">[Test-New-cslocationpolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-144">[Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d5f3-145">[CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-145">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-146">[新 CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-146">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-147">[CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-147">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d5f3-148">[CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d5f3-148">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d5f3-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d5f3-149">See Also</span></span>


[<span data-ttu-id="5d5f3-150">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="5d5f3-150">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

