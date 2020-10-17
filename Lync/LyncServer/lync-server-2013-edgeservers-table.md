---
title: Lync Server 2013： EdgeServers 表
description: Lync Server 2013： EdgeServers 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: EdgeServers table
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412833(v=OCS.15)
ms:contentKeyID: 48185081
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e4097ca58b75f873dcc12b84e5d971e9e378d07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551648"
---
# <a name="edgeservers-table-in-lync-server-2013"></a><span data-ttu-id="70f32-103">Lync Server 2013 中的 EdgeServers 表</span><span class="sxs-lookup"><span data-stu-id="70f32-103">EdgeServers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70f32-104">_**上次修改的主题：** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="70f32-104">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="70f32-105">EdgeServers 表是一个支持表格。</span><span class="sxs-lookup"><span data-stu-id="70f32-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="70f32-106">每个记录存储有关在数据库中包含记录的呼叫中涉及的一台边缘服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="70f32-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70f32-107">列</span><span class="sxs-lookup"><span data-stu-id="70f32-107">Column</span></span></th>
<th><span data-ttu-id="70f32-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="70f32-108">Data Type</span></span></th>
<th><span data-ttu-id="70f32-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="70f32-109">Key/Index</span></span></th>
<th><span data-ttu-id="70f32-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="70f32-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70f32-111"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="70f32-111"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="70f32-112">int</span><span class="sxs-lookup"><span data-stu-id="70f32-112">int</span></span></p></td>
<td><p><span data-ttu-id="70f32-113">主</span><span class="sxs-lookup"><span data-stu-id="70f32-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="70f32-114">标识此边缘服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="70f32-114">Unique number identifying this Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70f32-115"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="70f32-115"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="70f32-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="70f32-116">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="70f32-117">边缘服务器名称。</span><span class="sxs-lookup"><span data-stu-id="70f32-117">Edge Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

