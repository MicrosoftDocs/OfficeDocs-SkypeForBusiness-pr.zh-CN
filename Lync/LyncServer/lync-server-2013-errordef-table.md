---
title: Lync Server 2013： ErrorDef 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6db93ea1b09e50d48ee5e0276d90e3db3975e9fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="0a7dc-102">Lync Server 2013 中的 ErrorDef 表</span><span class="sxs-lookup"><span data-stu-id="0a7dc-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a7dc-103">_**上次修改的主题：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="0a7dc-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="0a7dc-104">ErrorDef 表存储可能出现的每种错误类型的相关信息。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="0a7dc-105">每条记录是一种类型的错误。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a7dc-106">列</span><span class="sxs-lookup"><span data-stu-id="0a7dc-106">Column</span></span></th>
<th><span data-ttu-id="0a7dc-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="0a7dc-107">Data Type</span></span></th>
<th><span data-ttu-id="0a7dc-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="0a7dc-108">Key/Index</span></span></th>
<th><span data-ttu-id="0a7dc-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="0a7dc-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a7dc-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="0a7dc-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a7dc-111">int</span><span class="sxs-lookup"><span data-stu-id="0a7dc-111">int</span></span></p></td>
<td><p><span data-ttu-id="0a7dc-112">主</span><span class="sxs-lookup"><span data-stu-id="0a7dc-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="0a7dc-113">标识此类型的错误的唯一 ID 号。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7dc-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="0a7dc-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="0a7dc-115">int</span><span class="sxs-lookup"><span data-stu-id="0a7dc-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0a7dc-116">与此错误关联的标准 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a7dc-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="0a7dc-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a7dc-118">int</span><span class="sxs-lookup"><span data-stu-id="0a7dc-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0a7dc-119">Microsoft 诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7dc-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="0a7dc-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a7dc-121">Int</span><span class="sxs-lookup"><span data-stu-id="0a7dc-121">Int</span></span></p></td>
<td><p><span data-ttu-id="0a7dc-122">对外</span><span class="sxs-lookup"><span data-stu-id="0a7dc-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a7dc-123">呼叫的类型。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-123">Type of the call.</span></span> <span data-ttu-id="0a7dc-124">有关详细信息，请参阅<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a>。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a7dc-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="0a7dc-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="0a7dc-126">varbinary （33）</span><span class="sxs-lookup"><span data-stu-id="0a7dc-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0a7dc-127">失败的请求的类型。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="0a7dc-128">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="0a7dc-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7dc-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="0a7dc-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="0a7dc-130">varbinary （257）</span><span class="sxs-lookup"><span data-stu-id="0a7dc-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0a7dc-131">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="0a7dc-132">可以使用此 syntaxt 将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="0a7dc-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

