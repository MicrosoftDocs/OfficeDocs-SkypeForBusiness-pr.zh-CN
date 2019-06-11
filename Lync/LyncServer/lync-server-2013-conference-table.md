---
title: Lync Server 2013：Conference 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f57f7baf017507da44677cc475c99d192fe868f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="5f564-102">Lync Server 2013 中的 Conference 表</span><span class="sxs-lookup"><span data-stu-id="5f564-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f564-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5f564-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5f564-104">会议表是支持表。</span><span class="sxs-lookup"><span data-stu-id="5f564-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="5f564-105">每条记录表示一个会议或对等会话。</span><span class="sxs-lookup"><span data-stu-id="5f564-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f564-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="5f564-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5f564-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="5f564-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5f564-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="5f564-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5f564-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="5f564-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f564-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="5f564-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5f564-111">int</span><span class="sxs-lookup"><span data-stu-id="5f564-111">int</span></span></p></td>
<td><p><span data-ttu-id="5f564-112">Primary</span><span class="sxs-lookup"><span data-stu-id="5f564-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5f564-113">标识此会议记录的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="5f564-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f564-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="5f564-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="5f564-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5f564-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f564-116">唯一</span><span class="sxs-lookup"><span data-stu-id="5f564-116">unique</span></span></p></td>
<td><p><span data-ttu-id="5f564-117">会议 URI (如果这是会议) 或 DialogID (如果这是对等会话)。</span><span class="sxs-lookup"><span data-stu-id="5f564-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f564-118"><strong>检查</strong></span><span class="sxs-lookup"><span data-stu-id="5f564-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="5f564-119">int</span><span class="sxs-lookup"><span data-stu-id="5f564-119">int</span></span></p></td>
<td><p><span data-ttu-id="5f564-120">食指</span><span class="sxs-lookup"><span data-stu-id="5f564-120">index</span></span></p></td>
<td><p><span data-ttu-id="5f564-121">会议 URI 的校验和。</span><span class="sxs-lookup"><span data-stu-id="5f564-121">Checksum of the conference URI.</span></span> <span data-ttu-id="5f564-122">此功能在内部使用。</span><span class="sxs-lookup"><span data-stu-id="5f564-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f564-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="5f564-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="5f564-124">datetime</span><span class="sxs-lookup"><span data-stu-id="5f564-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f564-125">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="5f564-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

