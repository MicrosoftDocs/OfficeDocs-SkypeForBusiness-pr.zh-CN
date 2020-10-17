---
title: Lync Server 2013：位置表
description: Lync Server 2013：位置表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570578"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="aa6c9-103">Lync Server 2013 中的位置表</span><span class="sxs-lookup"><span data-stu-id="aa6c9-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa6c9-104">_**上次修改的主题：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="aa6c9-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="aa6c9-105">每条记录均表示紧急呼叫（例如 E9-1-1 呼叫）中的一个位置引用。</span><span class="sxs-lookup"><span data-stu-id="aa6c9-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa6c9-106">列</span><span class="sxs-lookup"><span data-stu-id="aa6c9-106">Column</span></span></th>
<th><span data-ttu-id="aa6c9-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="aa6c9-107">Data Type</span></span></th>
<th><span data-ttu-id="aa6c9-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="aa6c9-108">Key/Index</span></span></th>
<th><span data-ttu-id="aa6c9-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="aa6c9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa6c9-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="aa6c9-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6c9-111">datetime</span><span class="sxs-lookup"><span data-stu-id="aa6c9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa6c9-112">主、外</span><span class="sxs-lookup"><span data-stu-id="aa6c9-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa6c9-113">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="aa6c9-113">Time of session request.</span></span> <span data-ttu-id="aa6c9-114">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="aa6c9-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="aa6c9-115">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="aa6c9-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6c9-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="aa6c9-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6c9-117">int</span><span class="sxs-lookup"><span data-stu-id="aa6c9-117">int</span></span></p></td>
<td><p><span data-ttu-id="aa6c9-118">主、外</span><span class="sxs-lookup"><span data-stu-id="aa6c9-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa6c9-119">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="aa6c9-119">ID number to identify the session.</span></span> <span data-ttu-id="aa6c9-120">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="aa6c9-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="aa6c9-121">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="aa6c9-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6c9-122"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="aa6c9-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6c9-123">nvarchar (max) </span><span class="sxs-lookup"><span data-stu-id="aa6c9-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aa6c9-124">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="aa6c9-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

