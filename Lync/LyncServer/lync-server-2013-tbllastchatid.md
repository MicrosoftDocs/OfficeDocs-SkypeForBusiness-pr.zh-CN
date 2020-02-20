---
title: Lync Server 2013： tblLastChatId
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
ms.openlocfilehash: 542b9f2006572edab4c9ca0adb29836174bc7aa7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="a1cf6-102">Lync Server 2013 中的 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="a1cf6-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1cf6-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a1cf6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a1cf6-104">LastChatId 包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="a1cf6-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="a1cf6-105">Columns</span><span class="sxs-lookup"><span data-stu-id="a1cf6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1cf6-106">列</span><span class="sxs-lookup"><span data-stu-id="a1cf6-106">Column</span></span></th>
<th><span data-ttu-id="a1cf6-107">类型</span><span class="sxs-lookup"><span data-stu-id="a1cf6-107">Type</span></span></th>
<th><span data-ttu-id="a1cf6-108">说明</span><span class="sxs-lookup"><span data-stu-id="a1cf6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1cf6-109">个</span><span class="sxs-lookup"><span data-stu-id="a1cf6-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="a1cf6-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="a1cf6-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a1cf6-111">节点 ID（仅限聊天室类型）。</span><span class="sxs-lookup"><span data-stu-id="a1cf6-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1cf6-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="a1cf6-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="a1cf6-113">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="a1cf6-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a1cf6-114">上次使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="a1cf6-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a1cf6-115">Keys</span><span class="sxs-lookup"><span data-stu-id="a1cf6-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1cf6-116">列</span><span class="sxs-lookup"><span data-stu-id="a1cf6-116">Column</span></span></th>
<th><span data-ttu-id="a1cf6-117">说明</span><span class="sxs-lookup"><span data-stu-id="a1cf6-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1cf6-118">&lt;lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="a1cf6-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="a1cf6-119">主键（只有 nodeID 足以进行处理）。</span><span class="sxs-lookup"><span data-stu-id="a1cf6-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1cf6-120">个</span><span class="sxs-lookup"><span data-stu-id="a1cf6-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="a1cf6-121">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="a1cf6-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="a1cf6-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1cf6-122">See Also</span></span>


[<span data-ttu-id="a1cf6-123">Lync Server 2013 中的 tblChat</span><span class="sxs-lookup"><span data-stu-id="a1cf6-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

