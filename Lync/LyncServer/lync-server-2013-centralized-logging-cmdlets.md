---
title: Lync Server 2013：集中日志记录 cmdlet
description: Lync Server 2013：集中日志记录 cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Centralized Logging cmdlets
ms:assetid: 8ba5bcae-8b99-489c-9355-6e77d4ad9100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205064(v=OCS.15)
ms:contentKeyID: 48184743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98457564de22b719e0741a6f5364c409e2b4d3ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544338"
---
# <a name="centralized-logging-cmdlets-in-lync-server-2013"></a><span data-ttu-id="cfa72-103">Lync Server 2013 中的集中日志记录 cmdlet</span><span class="sxs-lookup"><span data-stu-id="cfa72-103">Centralized Logging cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfa72-104">_**上次修改的主题：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="cfa72-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="cfa72-105">集中日志记录 cmdlet 为管理员提供了一种管理和配置 Microsoft Lync Server 2013 中引入的集中日志记录功能的方法。</span><span class="sxs-lookup"><span data-stu-id="cfa72-105">The centralized logging cmdlets provide a way for administrators to manage and configure the centralized logging capabilities introduced in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="cfa72-106">集中日志记录允许管理员同时在多台计算机上启用或禁用事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="cfa72-106">Centralized logging allows administrators to simultaneously enable or disable event tracing on multiple computers.</span></span>

<div>

## <a name="centralized-logging-cmdlets"></a><span data-ttu-id="cfa72-107">集中日志记录 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cfa72-107">Centralized Logging Cmdlets</span></span>

<span data-ttu-id="cfa72-108">集中日志记录 cmdlet 使您能够管理 Lync Server 2013 中引入的集中日志记录服务：</span><span class="sxs-lookup"><span data-stu-id="cfa72-108">The centralized logging cmdlets enable you to manage the centralized logging service introduced in Lync Server 2013:</span></span>

<span data-ttu-id="cfa72-109">**集中日志记录 Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="cfa72-109">**Centralized Logging Cmdlets**</span></span>

  - <span data-ttu-id="cfa72-110">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-110">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-111">[新 New-csclsconfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-111">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-112">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-112">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-113">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-113">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="cfa72-114">[搜索-Search-csclslogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-114">[Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-115">[显示-Search-csclslogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-115">[Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-116">[启动-Search-csclslogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-116">[Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-117">[Search-csclslogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-117">[Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-118">[Sync-Search-csclslogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-118">[Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-119">[更新-Search-csclslogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-119">[Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="cfa72-120">[新 CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-120">[New-CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="cfa72-121">[CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-121">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-122">[新 CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-122">[New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-123">[CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-123">[Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-124">[CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-124">[Set-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="cfa72-125">[New-csclsscenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-125">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-126">[新 New-csclsscenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-126">[New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-127">[New-csclsscenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-127">[Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-128">[New-csclsscenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-128">[Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="cfa72-129">[CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-129">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-130">[CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-130">[Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="cfa72-131">[CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-131">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-132">[新 CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-132">[New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-133">[CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-133">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="cfa72-134">[CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cfa72-134">[Set-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

