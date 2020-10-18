---
title: 'Lync Server 2013：基于角色的访问控制 (RBAC) '
description: Lync Server 2013：基于角色的访问控制 (RBAC) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6586517083ff6cd2c4e20d83e9b8f861edf800c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576578"
---
# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="08679-103">Lync Server 2013 的基于角色的访问控制 (RBAC) </span><span class="sxs-lookup"><span data-stu-id="08679-103">Role-based access control (RBAC) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08679-104">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="08679-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="08679-105">Microsoft Lync Server 2013 包括 Role-Based 访问控制 (RBAC) 组中，使您能够在保持高标准安全性的同时委派管理任务。</span><span class="sxs-lookup"><span data-stu-id="08679-105">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="08679-106">这些组是在林准备期间创建的。</span><span class="sxs-lookup"><span data-stu-id="08679-106">These groups are created during forest preparation.</span></span> <span data-ttu-id="08679-107">有关林准备的详细信息，请参阅 [适用于 Lync Server 2013 的 Active Directory 域服务](lync-server-2013-active-directory-domain-services-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="08679-107">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="08679-108">有关林准备创建的特定组的详细信息，请参阅部署文档中的 [Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md) 。</span><span class="sxs-lookup"><span data-stu-id="08679-108">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="08679-109">使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。</span><span class="sxs-lookup"><span data-stu-id="08679-109">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="08679-110">每个角色都与该角色中的用户允许运行的 Lync Server Management Shell cmdlet 的特定列表相关联。</span><span class="sxs-lookup"><span data-stu-id="08679-110">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="08679-111">可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。</span><span class="sxs-lookup"><span data-stu-id="08679-111">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="08679-112">有关详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="08679-112">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

