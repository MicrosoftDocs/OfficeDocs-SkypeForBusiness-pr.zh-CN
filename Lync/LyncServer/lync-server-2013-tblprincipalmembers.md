---
title: Lync Server 2013： tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba78067f076169a808129d83c8d4202e183a3a8f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="bb8b5-102">Lync Server 2013 中的 tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="bb8b5-102">tblPrincipalMembers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb8b5-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bb8b5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bb8b5-104">tblPrincipalMembers 包含主体成员身份。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="bb8b5-105">Columns</span><span class="sxs-lookup"><span data-stu-id="bb8b5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb8b5-106">列</span><span class="sxs-lookup"><span data-stu-id="bb8b5-106">Column</span></span></th>
<th><span data-ttu-id="bb8b5-107">类型</span><span class="sxs-lookup"><span data-stu-id="bb8b5-107">Type</span></span></th>
<th><span data-ttu-id="bb8b5-108">Description</span><span class="sxs-lookup"><span data-stu-id="bb8b5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb8b5-109">prinID</span><span class="sxs-lookup"><span data-stu-id="bb8b5-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="bb8b5-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="bb8b5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bb8b5-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb8b5-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="bb8b5-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="bb8b5-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="bb8b5-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="bb8b5-p101">成员的可分辨名称。成员不必是主体（在 tblPrincipal 表中）。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bb8b5-116">Keys</span><span class="sxs-lookup"><span data-stu-id="bb8b5-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb8b5-117">列</span><span class="sxs-lookup"><span data-stu-id="bb8b5-117">Column</span></span></th>
<th><span data-ttu-id="bb8b5-118">说明</span><span class="sxs-lookup"><span data-stu-id="bb8b5-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb8b5-119">&lt;prinID, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="bb8b5-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="bb8b5-120">主键。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb8b5-121">prinID</span><span class="sxs-lookup"><span data-stu-id="bb8b5-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="bb8b5-122">在 tblPrincipal.prinID 中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

