---
title: Lync Server 2013：受信任的应用程序 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trusted applications cmdlets
ms:assetid: 4d6ae0dc-e3e0-4519-8b74-9e941dea21e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415652(v=OCS.15)
ms:contentKeyID: 48184071
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878ce959b10c6868f415ec86d717de590b9c8c29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="trusted-applications-cmdlets-in-lync-server-2013"></a><span data-ttu-id="1714d-102">Lync Server 2013 中的 "受信任的应用程序" cmdlet</span><span class="sxs-lookup"><span data-stu-id="1714d-102">Trusted applications cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1714d-103">_**主题上次修改时间：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1714d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1714d-104">受信任的应用程序是由具有受信任状态的第三方开发的应用程序，该应用程序作为 Microsoft Lync Server 2013 的一部分运行，但不是产品的内置部分。</span><span class="sxs-lookup"><span data-stu-id="1714d-104">A trusted application is an application developed by a third party that is given trusted status to run as part of Microsoft Lync Server 2013 but that is not a built-in part of the product.</span></span> <span data-ttu-id="1714d-105">Lync Server 2013 提供了可用于配置和管理受信任的应用程序的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1714d-105">Lync Server 2013 provides cmdlets that can be used to configure and managed trusted applications.</span></span>

<div>

## <a name="trusted-applications-cmdlets"></a><span data-ttu-id="1714d-106">受信任的应用程序 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1714d-106">Trusted Applications Cmdlets</span></span>

<span data-ttu-id="1714d-107">使用以下 cmdlet 管理受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1714d-107">Use the following cmdlets to manage trusted applications.</span></span>

<span data-ttu-id="1714d-108">**受信任的应用程序**</span><span class="sxs-lookup"><span data-stu-id="1714d-108">**Trusted Applications**</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-109">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-109">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-110">[New-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-110">[New-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-111">[Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-111">[Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-112">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-112">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1714d-113">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-113">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-114">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-114">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-115">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-115">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1714d-116">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-116">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-117">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-117">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-118">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-118">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-119">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-119">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1714d-120">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-120">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-121">[New-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-121">[New-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-122">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-122">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1714d-123">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1714d-123">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1714d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1714d-124">See Also</span></span>


[<span data-ttu-id="1714d-125">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="1714d-125">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

