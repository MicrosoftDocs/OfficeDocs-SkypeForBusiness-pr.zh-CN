---
title: Lync Server 2013：用户管理 cmdlet
description: Lync Server 2013：用户管理 cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b94f2b48017fd29fa7a5a814da8a3c80d8f57968
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569778"
---
# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="53cbd-103">Lync Server 2013 中的用户管理 cmdlet</span><span class="sxs-lookup"><span data-stu-id="53cbd-103">User management cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53cbd-104">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="53cbd-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="53cbd-105">Microsoft Lync Server 2013 中包含的用户管理 cmdlet 允许您启用、禁用和修改 Lync Server 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="53cbd-105">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="53cbd-106">用户管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="53cbd-106">User Management Cmdlets</span></span>

<span data-ttu-id="53cbd-107">大多数适用于用户和用户帐户的管理任务都可以从 Lync Server 控制面板中执行。</span><span class="sxs-lookup"><span data-stu-id="53cbd-107">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="53cbd-108">主要的例外是处理音频会议提供商的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="53cbd-108">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="53cbd-109">可以使用 Lync Server 命令行管理程序中的 cmdlet 或在脚本中执行用户管理任务。</span><span class="sxs-lookup"><span data-stu-id="53cbd-109">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="53cbd-110">通过使用脚本，可以自动完成某些任务。</span><span class="sxs-lookup"><span data-stu-id="53cbd-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="53cbd-111">以下是与管理用户和用户帐户直接相关的 cmdlet 列表：</span><span class="sxs-lookup"><span data-stu-id="53cbd-111">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="53cbd-112">CsAdContact</span><span class="sxs-lookup"><span data-stu-id="53cbd-112">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="53cbd-113">CsAdUser</span><span class="sxs-lookup"><span data-stu-id="53cbd-113">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="53cbd-114">CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="53cbd-114">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="53cbd-115">CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="53cbd-115">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="53cbd-116">调用 Invoke-csucsrollback</span><span class="sxs-lookup"><span data-stu-id="53cbd-116">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="53cbd-117">调试-Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="53cbd-117">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="53cbd-118">Test-Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="53cbd-118">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="53cbd-119">Disable-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="53cbd-119">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="53cbd-120">Enable-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="53cbd-120">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="53cbd-121">Get-csuser</span><span class="sxs-lookup"><span data-stu-id="53cbd-121">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="53cbd-122">移动-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="53cbd-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="53cbd-123">Get-csuser</span><span class="sxs-lookup"><span data-stu-id="53cbd-123">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="53cbd-124">CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="53cbd-124">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="53cbd-125">CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="53cbd-125">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="53cbd-126">CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="53cbd-126">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="53cbd-127">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="53cbd-127">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="53cbd-128">CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="53cbd-128">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="53cbd-129">CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="53cbd-129">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="53cbd-130">Grant-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="53cbd-130">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="53cbd-131">新 CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="53cbd-131">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="53cbd-132">CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="53cbd-132">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="53cbd-133">CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="53cbd-133">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53cbd-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53cbd-134">See Also</span></span>


[<span data-ttu-id="53cbd-135">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="53cbd-135">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

