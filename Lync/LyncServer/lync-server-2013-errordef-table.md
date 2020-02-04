---
title: Lync Server 2013：ErrorDef 表
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
ms.openlocfilehash: 55a6ab9a8bf50639267824c8330701ee74cb3f5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="fd6df-102">Lync Server 2013 中的 ErrorDef 表</span><span class="sxs-lookup"><span data-stu-id="fd6df-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd6df-103">_**主题上次修改时间：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="fd6df-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="fd6df-104">ErrorDef 表存储可能出现的每种类型的错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="fd6df-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="fd6df-105">每条记录是一种类型的错误。</span><span class="sxs-lookup"><span data-stu-id="fd6df-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd6df-106">列</span><span class="sxs-lookup"><span data-stu-id="fd6df-106">Column</span></span></th>
<th><span data-ttu-id="fd6df-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="fd6df-107">Data Type</span></span></th>
<th><span data-ttu-id="fd6df-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="fd6df-108">Key/Index</span></span></th>
<th><span data-ttu-id="fd6df-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="fd6df-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd6df-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="fd6df-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="fd6df-111">int</span><span class="sxs-lookup"><span data-stu-id="fd6df-111">int</span></span></p></td>
<td><p><span data-ttu-id="fd6df-112">Primary</span><span class="sxs-lookup"><span data-stu-id="fd6df-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="fd6df-113">标识此类型错误的唯一 ID 号。</span><span class="sxs-lookup"><span data-stu-id="fd6df-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd6df-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="fd6df-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="fd6df-115">int</span><span class="sxs-lookup"><span data-stu-id="fd6df-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd6df-116">与此错误相关联的标准 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="fd6df-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd6df-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="fd6df-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="fd6df-118">int</span><span class="sxs-lookup"><span data-stu-id="fd6df-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd6df-119">Microsoft 诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="fd6df-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd6df-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="fd6df-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="fd6df-121">整形</span><span class="sxs-lookup"><span data-stu-id="fd6df-121">Int</span></span></p></td>
<td><p><span data-ttu-id="fd6df-122">外表</span><span class="sxs-lookup"><span data-stu-id="fd6df-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fd6df-123">通话的类型。</span><span class="sxs-lookup"><span data-stu-id="fd6df-123">Type of the call.</span></span> <span data-ttu-id="fd6df-124">有关详细信息，请参阅<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a>。</span><span class="sxs-lookup"><span data-stu-id="fd6df-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd6df-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="fd6df-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="fd6df-126">varbinary （33）</span><span class="sxs-lookup"><span data-stu-id="fd6df-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd6df-127">失败的请求类型。</span><span class="sxs-lookup"><span data-stu-id="fd6df-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="fd6df-128">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="fd6df-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd6df-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="fd6df-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="fd6df-130">varbinary （257）</span><span class="sxs-lookup"><span data-stu-id="fd6df-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd6df-131">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="fd6df-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="fd6df-132">可使用此 syntaxt 将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="fd6df-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

