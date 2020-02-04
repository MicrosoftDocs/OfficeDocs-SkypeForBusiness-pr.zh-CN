---
title: Lync Server 2013：用户管理 cmdlet
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
ms.openlocfilehash: 2396cb1a157b88d8beb9458006c1c8a44874dba3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="9c09d-102">Lync Server 2013 中的用户管理 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9c09d-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c09d-103">_**主题上次修改时间：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="9c09d-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="9c09d-104">Microsoft Lync Server 2013 中包含的用户管理 cmdlet 允许你启用、禁用和修改 Lync Server 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9c09d-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="9c09d-105">用户管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9c09d-105">User Management Cmdlets</span></span>

<span data-ttu-id="9c09d-106">大多数适用于用户和用户帐户的管理任务都可以从 Lync Server 控制面板执行。</span><span class="sxs-lookup"><span data-stu-id="9c09d-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="9c09d-107">主要例外是与音频会议提供商进行交易的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9c09d-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="9c09d-108">可使用 Lync Server 命令行管理程序或脚本中的 cmdlet 执行用户管理任务。</span><span class="sxs-lookup"><span data-stu-id="9c09d-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="9c09d-109">通过使用脚本，您可以自动执行某些任务。</span><span class="sxs-lookup"><span data-stu-id="9c09d-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="9c09d-110">以下是与管理用户和用户帐户直接相关的 cmdlet 的列表：</span><span class="sxs-lookup"><span data-stu-id="9c09d-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="9c09d-111">CsAdContact</span><span class="sxs-lookup"><span data-stu-id="9c09d-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="9c09d-112">CsAdUser</span><span class="sxs-lookup"><span data-stu-id="9c09d-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="9c09d-113">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="9c09d-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="9c09d-114">Get-CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="9c09d-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="9c09d-115">Invoke-CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="9c09d-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="9c09d-116">Debug-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="9c09d-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="9c09d-117">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="9c09d-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="9c09d-118">Disable-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="9c09d-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="9c09d-119">Enable-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="9c09d-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="9c09d-120">Move-csuser</span><span class="sxs-lookup"><span data-stu-id="9c09d-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="9c09d-121">移动-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="9c09d-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="9c09d-122">Set-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="9c09d-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="9c09d-123">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="9c09d-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="9c09d-124">Remove-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="9c09d-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="9c09d-125">Set-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="9c09d-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="9c09d-126">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="9c09d-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="9c09d-127">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="9c09d-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="9c09d-128">Get-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="9c09d-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="9c09d-129">Grant-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="9c09d-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="9c09d-130">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="9c09d-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="9c09d-131">Remove-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="9c09d-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="9c09d-132">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="9c09d-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c09d-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c09d-133">See Also</span></span>


[<span data-ttu-id="9c09d-134">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="9c09d-134">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

