---
title: Lync Server 2013：位置表
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
ms.openlocfilehash: accab39d1f1f7cb1855ba651ea217aa3b0a4bd8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="9c737-102">Lync Server 2013 中的位置表</span><span class="sxs-lookup"><span data-stu-id="9c737-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c737-103">_**上次修改的主题：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="9c737-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="9c737-104">每条记录均表示紧急呼叫（例如 E9-1-1 呼叫）中的一个位置引用。</span><span class="sxs-lookup"><span data-stu-id="9c737-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c737-105">列</span><span class="sxs-lookup"><span data-stu-id="9c737-105">Column</span></span></th>
<th><span data-ttu-id="9c737-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c737-106">Data Type</span></span></th>
<th><span data-ttu-id="9c737-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="9c737-107">Key/Index</span></span></th>
<th><span data-ttu-id="9c737-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="9c737-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c737-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c737-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c737-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9c737-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c737-111">主、外</span><span class="sxs-lookup"><span data-stu-id="9c737-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9c737-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="9c737-112">Time of session request.</span></span> <span data-ttu-id="9c737-113">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="9c737-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9c737-114">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="9c737-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c737-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9c737-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9c737-116">int</span><span class="sxs-lookup"><span data-stu-id="9c737-116">int</span></span></p></td>
<td><p><span data-ttu-id="9c737-117">主、外</span><span class="sxs-lookup"><span data-stu-id="9c737-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9c737-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="9c737-118">ID number to identify the session.</span></span> <span data-ttu-id="9c737-119">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="9c737-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9c737-120">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="9c737-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c737-121"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="9c737-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="9c737-122">nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="9c737-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9c737-123">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="9c737-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

