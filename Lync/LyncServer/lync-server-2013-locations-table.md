---
title: Lync Server 2013：Locations 表
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
ms.openlocfilehash: e2d16ffd08184a650f993d175239f5aff72b8b3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="0e472-102">Lync Server 2013 中的 Locations 表</span><span class="sxs-lookup"><span data-stu-id="0e472-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e472-103">_**主题上次修改时间：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="0e472-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="0e472-104">每条记录代表紧急呼叫中的一个位置引用，如 E9-1-1 通话。</span><span class="sxs-lookup"><span data-stu-id="0e472-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e472-105">列</span><span class="sxs-lookup"><span data-stu-id="0e472-105">Column</span></span></th>
<th><span data-ttu-id="0e472-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="0e472-106">Data Type</span></span></th>
<th><span data-ttu-id="0e472-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="0e472-107">Key/Index</span></span></th>
<th><span data-ttu-id="0e472-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="0e472-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e472-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e472-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e472-110">datetime</span><span class="sxs-lookup"><span data-stu-id="0e472-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e472-111">主、外部</span><span class="sxs-lookup"><span data-stu-id="0e472-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e472-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="0e472-112">Time of session request.</span></span> <span data-ttu-id="0e472-113">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="0e472-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0e472-114">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="0e472-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e472-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0e472-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0e472-116">int</span><span class="sxs-lookup"><span data-stu-id="0e472-116">int</span></span></p></td>
<td><p><span data-ttu-id="0e472-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="0e472-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e472-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="0e472-118">ID number to identify the session.</span></span> <span data-ttu-id="0e472-119">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="0e472-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0e472-120">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="0e472-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e472-121"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="0e472-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="0e472-122">nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="0e472-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e472-123">紧急电话的位置。</span><span class="sxs-lookup"><span data-stu-id="0e472-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

