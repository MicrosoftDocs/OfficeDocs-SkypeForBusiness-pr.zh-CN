---
title: Lync Server 2013： tblLastChatId
description: Lync Server 2013： tblLastChatId。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e80a735e70c8a03441038f5e58eb93e0af1f82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547598"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="4935d-103">Lync Server 2013 中的 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="4935d-103">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4935d-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4935d-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4935d-105">LastChatId 包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="4935d-105">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="4935d-106">列数</span><span class="sxs-lookup"><span data-stu-id="4935d-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4935d-107">列</span><span class="sxs-lookup"><span data-stu-id="4935d-107">Column</span></span></th>
<th><span data-ttu-id="4935d-108">类型</span><span class="sxs-lookup"><span data-stu-id="4935d-108">Type</span></span></th>
<th><span data-ttu-id="4935d-109">说明</span><span class="sxs-lookup"><span data-stu-id="4935d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4935d-110">个</span><span class="sxs-lookup"><span data-stu-id="4935d-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="4935d-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="4935d-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4935d-112">节点 ID（仅限聊天室类型）。</span><span class="sxs-lookup"><span data-stu-id="4935d-112">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4935d-113">lastChatID</span><span class="sxs-lookup"><span data-stu-id="4935d-113">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="4935d-114">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="4935d-114">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4935d-115">上次使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="4935d-115">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4935d-116">Keys</span><span class="sxs-lookup"><span data-stu-id="4935d-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4935d-117">列</span><span class="sxs-lookup"><span data-stu-id="4935d-117">Column</span></span></th>
<th><span data-ttu-id="4935d-118">说明</span><span class="sxs-lookup"><span data-stu-id="4935d-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4935d-119">&lt;lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="4935d-119">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="4935d-120">主键（只有 nodeID 足以进行处理）。</span><span class="sxs-lookup"><span data-stu-id="4935d-120">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4935d-121">个</span><span class="sxs-lookup"><span data-stu-id="4935d-121">nodeID</span></span></p></td>
<td><p><span data-ttu-id="4935d-122">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="4935d-122">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4935d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4935d-123">See Also</span></span>


[<span data-ttu-id="4935d-124">Lync Server 2013 中的 tblChat</span><span class="sxs-lookup"><span data-stu-id="4935d-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

