---
title: Lync Server 2013： Active Directory cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory cmdlets
ms:assetid: 313d73cb-f3db-4bc4-8708-de4da1d719c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415640(v=OCS.15)
ms:contentKeyID: 48183769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f77009f20cfbd3e76f5cfc3786bcd9fa9ba2be9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e3847-102">Lync Server 2013 中的 Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="e3847-102">Active Directory cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3847-103">_**主题上次修改时间：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="e3847-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="e3847-104">Active Directory cmdlet 通常由安装程序使用，并且很少会由管理员直接调用。</span><span class="sxs-lookup"><span data-stu-id="e3847-104">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="e3847-105">但是，管理员可以使用这些 cmdlet 准备（或 unprepare） Microsoft Lync Server 2013 的域或林，并安装所需的 Active Directory 架构文件。</span><span class="sxs-lookup"><span data-stu-id="e3847-105">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="e3847-106">Active Directory Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e3847-106">Active Directory Cmdlets</span></span>

<span data-ttu-id="e3847-107">以下是与管理 Lync Server 2013 Active Directory 设置直接相关的 cmdlet 的列表：</span><span class="sxs-lookup"><span data-stu-id="e3847-107">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="e3847-108">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="e3847-108">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="e3847-109">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3847-109">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e3847-110">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3847-110">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e3847-111">[CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3847-111">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e3847-112">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3847-112">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e3847-113">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3847-113">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e3847-114">[CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3847-114">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e3847-115">[CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3847-115">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e3847-116">[安装-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3847-116">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3847-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3847-117">See Also</span></span>


[<span data-ttu-id="e3847-118">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="e3847-118">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

