---
title: Lync Server 2013： MediationServers 表
description: Lync Server 2013： MediationServers 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediationServers table
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48184929
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a227f76272790d3a23ff06f0c97ba4a263f418a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568598"
---
# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="b0979-103">Lync Server 2013 中的 MediationServers 表</span><span class="sxs-lookup"><span data-stu-id="b0979-103">MediationServers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0979-104">_**上次修改的主题：** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="b0979-104">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="b0979-105">MediationServers 表是一个支持表格。</span><span class="sxs-lookup"><span data-stu-id="b0979-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="b0979-106">每个记录存储有关在数据库中包含记录的呼叫中涉及的一台中介服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="b0979-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0979-107">列</span><span class="sxs-lookup"><span data-stu-id="b0979-107">Column</span></span></th>
<th><span data-ttu-id="b0979-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="b0979-108">Data Type</span></span></th>
<th><span data-ttu-id="b0979-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="b0979-109">Key/Index</span></span></th>
<th><span data-ttu-id="b0979-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="b0979-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0979-111"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b0979-111"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b0979-112">int</span><span class="sxs-lookup"><span data-stu-id="b0979-112">int</span></span></p></td>
<td><p><span data-ttu-id="b0979-113">主</span><span class="sxs-lookup"><span data-stu-id="b0979-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b0979-114">标识此中介服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="b0979-114">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0979-115"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="b0979-115"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b0979-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b0979-116">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0979-117">中介服务器名称。</span><span class="sxs-lookup"><span data-stu-id="b0979-117">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

