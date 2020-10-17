---
title: Lync Server 2013： tblSkippedAffiliations
description: Lync Server 2013： tblSkippedAffiliations。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31746cee7302d34a1d19b3059ca1da6beab9345d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563798"
---
# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="334bc-103">Lync Server 2013 中的 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="334bc-103">tblSkippedAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="334bc-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="334bc-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="334bc-105">由于 Active Directory 域服务访问错误) ，tblSkippedAffiliations 包含无法读取的隶属关系 (。</span><span class="sxs-lookup"><span data-stu-id="334bc-105">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="334bc-106">列数</span><span class="sxs-lookup"><span data-stu-id="334bc-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="334bc-107">列</span><span class="sxs-lookup"><span data-stu-id="334bc-107">Column</span></span></th>
<th><span data-ttu-id="334bc-108">类型</span><span class="sxs-lookup"><span data-stu-id="334bc-108">Type</span></span></th>
<th><span data-ttu-id="334bc-109">说明</span><span class="sxs-lookup"><span data-stu-id="334bc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="334bc-110">prinID</span><span class="sxs-lookup"><span data-stu-id="334bc-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="334bc-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="334bc-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="334bc-112">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="334bc-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="334bc-113">affDescription</span><span class="sxs-lookup"><span data-stu-id="334bc-113">affDescription</span></span></p></td>
<td><p><span data-ttu-id="334bc-114">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="334bc-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="334bc-115">标识隶属项的字符串。</span><span class="sxs-lookup"><span data-stu-id="334bc-115">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="334bc-116">格式为： guid： {0} uri： {1} &gt; id：{2}</span><span class="sxs-lookup"><span data-stu-id="334bc-116">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="334bc-117">updatedBy</span><span class="sxs-lookup"><span data-stu-id="334bc-117">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="334bc-118">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="334bc-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="334bc-p101">更新此行的主体的 ID。该值始终为 1（系统用户），因为 Active Directory 同步是这些条目的唯一来源。</span><span class="sxs-lookup"><span data-stu-id="334bc-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="334bc-121">Keys</span><span class="sxs-lookup"><span data-stu-id="334bc-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="334bc-122">列 (s) </span><span class="sxs-lookup"><span data-stu-id="334bc-122">Column(s)</span></span></th>
<th><span data-ttu-id="334bc-123">说明</span><span class="sxs-lookup"><span data-stu-id="334bc-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="334bc-124">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="334bc-124">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="334bc-125">主键。</span><span class="sxs-lookup"><span data-stu-id="334bc-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="334bc-126">prinID</span><span class="sxs-lookup"><span data-stu-id="334bc-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="334bc-127">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="334bc-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

