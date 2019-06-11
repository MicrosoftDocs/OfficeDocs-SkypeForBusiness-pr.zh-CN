---
title: Lync Server 2013：Roles 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Roles table
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399043(v=OCS.15)
ms:contentKeyID: 48185893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12ed7ed4a6f152ce103e3e100bf14918cf945345
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roles-table-in-lync-server-2013"></a><span data-ttu-id="e74ac-102">Lync Server 2013 中的 Roles 表</span><span class="sxs-lookup"><span data-stu-id="e74ac-102">Roles table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e74ac-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e74ac-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e74ac-104">Roles 表是一个静态表, 它存储了可能的会议角色 (如与会者和演示者) 的列表。</span><span class="sxs-lookup"><span data-stu-id="e74ac-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e74ac-105">列</span><span class="sxs-lookup"><span data-stu-id="e74ac-105">Column</span></span></th>
<th><span data-ttu-id="e74ac-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="e74ac-106">Data Type</span></span></th>
<th><span data-ttu-id="e74ac-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="e74ac-107">Key/Index</span></span></th>
<th><span data-ttu-id="e74ac-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="e74ac-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e74ac-109"><strong>RoleId</strong></span><span class="sxs-lookup"><span data-stu-id="e74ac-109"><strong>RoleId</strong></span></span></p></td>
<td><p><span data-ttu-id="e74ac-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74ac-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74ac-111">Primary</span><span class="sxs-lookup"><span data-stu-id="e74ac-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74ac-112"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="e74ac-112"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="e74ac-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e74ac-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e74ac-114">允许的值:</span><span class="sxs-lookup"><span data-stu-id="e74ac-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="e74ac-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="e74ac-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="e74ac-116">1-演示者</span><span class="sxs-lookup"><span data-stu-id="e74ac-116">1 - Presenter</span></span></p></li>
<li><p><span data-ttu-id="e74ac-117">2-与会者</span><span class="sxs-lookup"><span data-stu-id="e74ac-117">2 - Attendee</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

