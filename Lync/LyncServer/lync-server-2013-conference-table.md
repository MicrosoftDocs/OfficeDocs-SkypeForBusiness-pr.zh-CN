---
title: Lync Server 2013：会议表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7b6627f6976001bdb1440db9aa40c33d89cfc7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="ff549-102">Lync Server 2013 中的会议表</span><span class="sxs-lookup"><span data-stu-id="ff549-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff549-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ff549-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ff549-p101">会议表是一个支持表。每条记录代表一个会议或点对点会话。</span><span class="sxs-lookup"><span data-stu-id="ff549-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff549-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ff549-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ff549-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="ff549-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ff549-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="ff549-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ff549-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="ff549-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff549-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="ff549-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ff549-111">int</span><span class="sxs-lookup"><span data-stu-id="ff549-111">int</span></span></p></td>
<td><p><span data-ttu-id="ff549-112">主</span><span class="sxs-lookup"><span data-stu-id="ff549-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff549-113">标识该会议记录的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="ff549-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff549-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="ff549-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="ff549-115">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ff549-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ff549-116">unique</span><span class="sxs-lookup"><span data-stu-id="ff549-116">unique</span></span></p></td>
<td><p><span data-ttu-id="ff549-117">如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。</span><span class="sxs-lookup"><span data-stu-id="ff549-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff549-118"><strong>校验和</strong></span><span class="sxs-lookup"><span data-stu-id="ff549-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="ff549-119">int</span><span class="sxs-lookup"><span data-stu-id="ff549-119">int</span></span></p></td>
<td><p><span data-ttu-id="ff549-120">index</span><span class="sxs-lookup"><span data-stu-id="ff549-120">index</span></span></p></td>
<td><p><span data-ttu-id="ff549-p102">会议 URI 的校验和。该项仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="ff549-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff549-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ff549-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ff549-124">datetime</span><span class="sxs-lookup"><span data-stu-id="ff549-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff549-125">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="ff549-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

