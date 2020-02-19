---
title: Lync Server 2013：集中日志记录 cmdlet
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
ms.openlocfilehash: 12e85666b9aad15243feeeb423f87f1a442d7f52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="centralized-logging-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6bfc2-102">Lync Server 2013 中的集中日志记录 cmdlet</span><span class="sxs-lookup"><span data-stu-id="6bfc2-102">Centralized Logging cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bfc2-103">_**上次修改的主题：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="6bfc2-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="6bfc2-104">集中日志记录 cmdlet 为管理员提供了一种管理和配置 Microsoft Lync Server 2013 中引入的集中日志记录功能的方法。</span><span class="sxs-lookup"><span data-stu-id="6bfc2-104">The centralized logging cmdlets provide a way for administrators to manage and configure the centralized logging capabilities introduced in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6bfc2-105">集中日志记录允许管理员同时在多台计算机上启用或禁用事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="6bfc2-105">Centralized logging allows administrators to simultaneously enable or disable event tracing on multiple computers.</span></span>

<div>

## <a name="centralized-logging-cmdlets"></a><span data-ttu-id="6bfc2-106">集中日志记录 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6bfc2-106">Centralized Logging Cmdlets</span></span>

<span data-ttu-id="6bfc2-107">集中日志记录 cmdlet 使您能够管理 Lync Server 2013 中引入的集中日志记录服务：</span><span class="sxs-lookup"><span data-stu-id="6bfc2-107">The centralized logging cmdlets enable you to manage the centralized logging service introduced in Lync Server 2013:</span></span>

<span data-ttu-id="6bfc2-108">**集中日志记录 Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="6bfc2-108">**Centralized Logging Cmdlets**</span></span>

  - <span data-ttu-id="6bfc2-109">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-109">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-110">[新 New-csclsconfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-110">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-111">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-111">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-112">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-112">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6bfc2-113">[搜索-Search-csclslogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-113">[Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-114">[显示-Search-csclslogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-114">[Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-115">[启动-Search-csclslogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-115">[Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-116">[Search-csclslogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-116">[Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-117">[Sync-Search-csclslogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-117">[Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-118">[更新-Search-csclslogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-118">[Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6bfc2-119">[新 CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-119">[New-CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6bfc2-120">[CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-120">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-121">[新 CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-121">[New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-122">[CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-122">[Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-123">[CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-123">[Set-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6bfc2-124">[New-csclsscenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-124">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-125">[新 New-csclsscenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-125">[New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-126">[New-csclsscenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-126">[Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-127">[New-csclsscenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-127">[Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6bfc2-128">[CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-128">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-129">[CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6bfc2-130">[CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-130">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-131">[新 CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-131">[New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-132">[CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-132">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="6bfc2-133">[CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bfc2-133">[Set-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

