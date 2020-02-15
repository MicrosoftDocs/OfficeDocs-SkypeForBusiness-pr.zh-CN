---
title: Lync Server 2013：呼叫寄存应用程序 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park application cmdlets
ms:assetid: 30cc001f-b29e-4d44-bad7-65e1133e67b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415639(v=OCS.15)
ms:contentKeyID: 48183764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fb129114962a6f530ad1d52f6b0314d439d9c5d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="06248-102">Lync Server 2013 中的呼叫寄存应用程序 cmdlet</span><span class="sxs-lookup"><span data-stu-id="06248-102">Call Park application cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06248-103">_**上次修改的主题：** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="06248-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="06248-104">呼叫寄存应用程序允许用户将呼叫置于保持状态，然后从其他电话检索该呼叫。</span><span class="sxs-lookup"><span data-stu-id="06248-104">Call Park application allows a user to place a call on hold, then retrieve that call from a different phone.</span></span> <span data-ttu-id="06248-105">使用这些 cmdlet 可配置呼叫寄存轨道式和呼叫寄存应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="06248-105">Use these cmdlets to configure settings for call park orbits and the Call Park application.</span></span>

<div>

## <a name="call-park-application-cmdlets"></a><span data-ttu-id="06248-106">呼叫寄存应用程序 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="06248-106">Call Park Application Cmdlets</span></span>

<span data-ttu-id="06248-107">以下 cmdlet 可用于管理呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="06248-107">The following cmdlets can be used to manage Call Park application.</span></span>

<span data-ttu-id="06248-108">**呼叫寄存应用程序**</span><span class="sxs-lookup"><span data-stu-id="06248-108">**Call Park Application**</span></span>

  - <span></span>  
    <span data-ttu-id="06248-109">[CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06248-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06248-110">[新 CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06248-110">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06248-111">[CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06248-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06248-112">[CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06248-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="06248-113">[CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06248-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="06248-114">[CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06248-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06248-115">[新 CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06248-115">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06248-116">[CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06248-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06248-117">[CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06248-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06248-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06248-118">See Also</span></span>


[<span data-ttu-id="06248-119">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="06248-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

