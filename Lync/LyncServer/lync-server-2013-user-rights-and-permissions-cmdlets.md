---
title: Lync Server 2013：用户权利和权限 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User rights and permissions cmdlets
ms:assetid: b53aae4c-651f-4cbc-a762-ba818d63897e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415672(v=OCS.15)
ms:contentKeyID: 48185178
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2db174c6bd50bee3904267790127c9d2845b1dd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508689"
---
# <a name="user-rights-and-permissions-cmdlets-in-lync-server-2013"></a><span data-ttu-id="8ff81-102">Lync Server 2013 中的用户权限和权限 cmdlet</span><span class="sxs-lookup"><span data-stu-id="8ff81-102">User rights and permissions cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ff81-103">_**上次修改的主题：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="8ff81-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="8ff81-104">用户权限 cmdlet 主要用于管理基于角色的访问控制 (RBAC) ，这是用于委派 Microsoft Lync Server 2013 管理控制权的新技术。</span><span class="sxs-lookup"><span data-stu-id="8ff81-104">The user permission cmdlets are primarily used to manage role-based access control (RBAC), the new technology for delegating administrative control of Microsoft Lync Server 2013.</span></span>

<div>

## <a name="user-permission-cmdlets"></a><span data-ttu-id="8ff81-105">用户权限 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8ff81-105">User Permission Cmdlets</span></span>

<span data-ttu-id="8ff81-106">以下是与管理用户权限直接相关的 cmdlet 列表：</span><span class="sxs-lookup"><span data-stu-id="8ff81-106">The following is a list of cmdlets that relate directly to managing user permissions:</span></span>

<span data-ttu-id="8ff81-107">**用户权限**</span><span class="sxs-lookup"><span data-stu-id="8ff81-107">**User Permissions**</span></span>

  - <span></span>  
    <span data-ttu-id="8ff81-108">[CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-108">[Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8ff81-109">[新 CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-109">[New-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8ff81-110">[CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-110">[Remove-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8ff81-111">[CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-111">[Set-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8ff81-112">[更新-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-112">[Update-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8ff81-113">[CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-113">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8ff81-114">[Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-114">[Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8ff81-115">[CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-115">[Revoke-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8ff81-116">[Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-116">[Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8ff81-117">[Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-117">[Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8ff81-118">[CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-118">[Revoke-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8ff81-119">[Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8ff81-119">[Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ff81-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ff81-120">See Also</span></span>


[<span data-ttu-id="8ff81-121">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="8ff81-121">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

