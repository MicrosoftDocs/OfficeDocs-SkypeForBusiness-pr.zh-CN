---
title: Lync Server 2013： tblPrincipalMemberDifference
description: Lync Server 2013： tblPrincipalMemberDifference。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce7c770a6fed02dc27d2493816fae58943d391a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573218"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="6103e-103">Lync Server 2013 中的 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="6103e-103">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6103e-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6103e-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6103e-105">tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除的成员) 后续的 Active Directory 域服务同步步骤尚未处理。</span><span class="sxs-lookup"><span data-stu-id="6103e-105">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="6103e-106">列数</span><span class="sxs-lookup"><span data-stu-id="6103e-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6103e-107">列</span><span class="sxs-lookup"><span data-stu-id="6103e-107">Column</span></span></th>
<th><span data-ttu-id="6103e-108">类型</span><span class="sxs-lookup"><span data-stu-id="6103e-108">Type</span></span></th>
<th><span data-ttu-id="6103e-109">说明</span><span class="sxs-lookup"><span data-stu-id="6103e-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6103e-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6103e-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="6103e-111">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="6103e-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="6103e-112">更改的组的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="6103e-112">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6103e-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="6103e-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="6103e-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6103e-114">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="6103e-115">成员的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="6103e-115">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6103e-116">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="6103e-116">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="6103e-117">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="6103e-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="6103e-p101">在添加成员时，设置为 False。在删除成员时，设置为 True。</span><span class="sxs-lookup"><span data-stu-id="6103e-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="6103e-120">键</span><span class="sxs-lookup"><span data-stu-id="6103e-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6103e-121">列</span><span class="sxs-lookup"><span data-stu-id="6103e-121">Column</span></span></th>
<th><span data-ttu-id="6103e-122">说明</span><span class="sxs-lookup"><span data-stu-id="6103e-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6103e-123">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="6103e-123">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="6103e-124">主键。</span><span class="sxs-lookup"><span data-stu-id="6103e-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

