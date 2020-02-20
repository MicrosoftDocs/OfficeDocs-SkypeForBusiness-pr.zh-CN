---
title: Lync Server 2013： tblSkippedAffiliations
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
ms.openlocfilehash: d21dbda8b649588e691d285c62ff865e9f001308
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="53617-102">Lync Server 2013 中的 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="53617-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53617-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="53617-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="53617-104">tblSkippedAffiliations 包含无法读取的隶属关系（通常是由于 Active Directory 域服务访问错误而引起的）。</span><span class="sxs-lookup"><span data-stu-id="53617-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="53617-105">Columns</span><span class="sxs-lookup"><span data-stu-id="53617-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53617-106">列</span><span class="sxs-lookup"><span data-stu-id="53617-106">Column</span></span></th>
<th><span data-ttu-id="53617-107">类型</span><span class="sxs-lookup"><span data-stu-id="53617-107">Type</span></span></th>
<th><span data-ttu-id="53617-108">说明</span><span class="sxs-lookup"><span data-stu-id="53617-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53617-109">prinID</span><span class="sxs-lookup"><span data-stu-id="53617-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="53617-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="53617-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="53617-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="53617-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53617-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="53617-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="53617-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="53617-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="53617-114">标识隶属项的字符串。</span><span class="sxs-lookup"><span data-stu-id="53617-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="53617-115">格式为： guid： {0} uri： {1} &gt; id：{2}</span><span class="sxs-lookup"><span data-stu-id="53617-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53617-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="53617-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="53617-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="53617-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="53617-p101">更新此行的主体的 ID。该值始终为 1（系统用户），因为 Active Directory 同步是这些条目的唯一来源。</span><span class="sxs-lookup"><span data-stu-id="53617-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="53617-120">Keys</span><span class="sxs-lookup"><span data-stu-id="53617-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53617-121">列</span><span class="sxs-lookup"><span data-stu-id="53617-121">Column(s)</span></span></th>
<th><span data-ttu-id="53617-122">说明</span><span class="sxs-lookup"><span data-stu-id="53617-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53617-123">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="53617-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="53617-124">主键。</span><span class="sxs-lookup"><span data-stu-id="53617-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53617-125">prinID</span><span class="sxs-lookup"><span data-stu-id="53617-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="53617-126">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="53617-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

