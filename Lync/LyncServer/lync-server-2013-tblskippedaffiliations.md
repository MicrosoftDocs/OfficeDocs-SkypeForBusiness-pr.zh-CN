---
title: Lync Server 2013：tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06269ede55a46757f78595d7573f3cd77414d1d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="5c7fc-102">Lync Server 2013 中的 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="5c7fc-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c7fc-103">_**主题上次修改时间:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5c7fc-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5c7fc-104">tblSkippedAffiliations 包含无法读取的隶属关系 (通常是由于 Active Directory 域服务访问错误)。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="5c7fc-105">多</span><span class="sxs-lookup"><span data-stu-id="5c7fc-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c7fc-106">列</span><span class="sxs-lookup"><span data-stu-id="5c7fc-106">Column</span></span></th>
<th><span data-ttu-id="5c7fc-107">类型</span><span class="sxs-lookup"><span data-stu-id="5c7fc-107">Type</span></span></th>
<th><span data-ttu-id="5c7fc-108">说明</span><span class="sxs-lookup"><span data-stu-id="5c7fc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c7fc-109">prinID</span><span class="sxs-lookup"><span data-stu-id="5c7fc-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="5c7fc-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="5c7fc-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5c7fc-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c7fc-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="5c7fc-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="5c7fc-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="5c7fc-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5c7fc-114">标识隶属关系的字符串。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="5c7fc-115">格式为: guid: {0} uri: {1} &gt; id:{2}</span><span class="sxs-lookup"><span data-stu-id="5c7fc-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c7fc-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="5c7fc-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="5c7fc-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="5c7fc-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5c7fc-118">已更新此行的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="5c7fc-119">由于 Active Directory 同步是这些条目的唯一源, 因此始终为 1 (系统用户)。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5c7fc-120">标示</span><span class="sxs-lookup"><span data-stu-id="5c7fc-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c7fc-121">列</span><span class="sxs-lookup"><span data-stu-id="5c7fc-121">Column(s)</span></span></th>
<th><span data-ttu-id="5c7fc-122">说明</span><span class="sxs-lookup"><span data-stu-id="5c7fc-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c7fc-123">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="5c7fc-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="5c7fc-124">主键。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c7fc-125">prinID</span><span class="sxs-lookup"><span data-stu-id="5c7fc-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="5c7fc-126">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

