---
title: Lync Server 2013：Pools 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pools table
ms:assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398991(v=OCS.15)
ms:contentKeyID: 48185680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8df31be5f0ede7217c8b6ed1539bfddea50a7280
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pools-table-in-lync-server-2013"></a><span data-ttu-id="26120-102">Lync Server 2013 中的 Pools 表</span><span class="sxs-lookup"><span data-stu-id="26120-102">Pools table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26120-103">_**主题上次修改时间：** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="26120-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="26120-104">Pool 表是存储有关各种池的信息的支持表。</span><span class="sxs-lookup"><span data-stu-id="26120-104">The Pools table is a supporting table that stores information about the various pool.</span></span> <span data-ttu-id="26120-105">表中的每条记录表示一个池。</span><span class="sxs-lookup"><span data-stu-id="26120-105">Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26120-106">列</span><span class="sxs-lookup"><span data-stu-id="26120-106">Column</span></span></th>
<th><span data-ttu-id="26120-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="26120-107">Data Type</span></span></th>
<th><span data-ttu-id="26120-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="26120-108">Key/Index</span></span></th>
<th><span data-ttu-id="26120-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="26120-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26120-110"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="26120-110"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="26120-111">int</span><span class="sxs-lookup"><span data-stu-id="26120-111">int</span></span></p></td>
<td><p><span data-ttu-id="26120-112">Primary</span><span class="sxs-lookup"><span data-stu-id="26120-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="26120-113">标识此池的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="26120-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26120-114"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="26120-114"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="26120-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="26120-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="26120-116">池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="26120-116">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

