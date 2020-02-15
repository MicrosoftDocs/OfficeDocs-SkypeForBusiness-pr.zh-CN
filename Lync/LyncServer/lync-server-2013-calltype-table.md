---
title: Lync Server 2013： CallType 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f90be73c63921ebe9971abae85b2da22e76a560
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="a046d-102">Lync Server 2013 中的 CallType 表</span><span class="sxs-lookup"><span data-stu-id="a046d-102">CallType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a046d-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a046d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a046d-104">CallType 表是存储可能的呼叫类型列表的静态表。</span><span class="sxs-lookup"><span data-stu-id="a046d-104">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a046d-105">列</span><span class="sxs-lookup"><span data-stu-id="a046d-105">Column</span></span></th>
<th><span data-ttu-id="a046d-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="a046d-106">Data Type</span></span></th>
<th><span data-ttu-id="a046d-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="a046d-107">Key/Index</span></span></th>
<th><span data-ttu-id="a046d-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="a046d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a046d-109"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a046d-109"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a046d-110">int</span><span class="sxs-lookup"><span data-stu-id="a046d-110">int</span></span></p></td>
<td><p><span data-ttu-id="a046d-111">主</span><span class="sxs-lookup"><span data-stu-id="a046d-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a046d-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="a046d-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="a046d-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="a046d-113">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a046d-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="a046d-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a046d-115">0 -- 未知</span><span class="sxs-lookup"><span data-stu-id="a046d-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="a046d-116">1 - 即时消息</span><span class="sxs-lookup"><span data-stu-id="a046d-116">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="a046d-117">2--应用程序共享</span><span class="sxs-lookup"><span data-stu-id="a046d-117">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="a046d-118">3 -- 音频</span><span class="sxs-lookup"><span data-stu-id="a046d-118">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="a046d-119">4 - 音频和视频</span><span class="sxs-lookup"><span data-stu-id="a046d-119">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="a046d-120">5 - 文件传输</span><span class="sxs-lookup"><span data-stu-id="a046d-120">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

