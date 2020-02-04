---
title: Lync Server 2013：迁移和共存 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence cmdlets
ms:assetid: ff1a56e0-e883-473d-92fe-ca77ea4eb63b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415682(v=OCS.15)
ms:contentKeyID: 48185968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbae93a344909139fba3b40e2864ca3b943e77a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="60921-102">Lync Server 2013 中的迁移和共存 cmdlet</span><span class="sxs-lookup"><span data-stu-id="60921-102">Migration and coexistence cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60921-103">_**主题上次修改时间：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="60921-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="60921-104">[CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15)) cmdlet 提供了一种将用户帐户从 Office 通信服务器2007或 Microsoft lync server 2010 移动到 Microsoft lync server 2013 的方法。</span><span class="sxs-lookup"><span data-stu-id="60921-104">The [Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15)) cmdlet provides a way for you to move user accounts from Office Communications Server 2007 or Microsoft Lync Server 2010 to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="60921-105">如果需要将用户帐户移动到 "反向" （例如，从 Microsoft Lync Server 2013 到 Microsoft Lync Server 2010），请使用[move-csuser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15)) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="60921-105">If you need to move a user account "backward" (for example, from Microsoft Lync Server 2013 to Microsoft Lync Server 2010) use the [Move-CsUser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15)) cmdlet.</span></span>

  - <span></span>  
    <span data-ttu-id="60921-106">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60921-106">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60921-107">[Import-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60921-107">[Import-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60921-108">[合并-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60921-108">[Merge-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60921-109">[Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60921-109">[Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60921-110">[Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60921-110">[Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="60921-111">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60921-111">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="60921-112">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60921-112">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="60921-113">[Import-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60921-113">[Import-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="60921-114">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60921-114">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="60921-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60921-115">See Also</span></span>


[<span data-ttu-id="60921-116">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="60921-116">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

