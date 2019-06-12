---
title: Lync Server 2013：tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddc89952b544a71c469538cf11f65658e19e38d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="feb30-102">Lync Server 2013 中的 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="feb30-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feb30-103">_**主题上次修改时间:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="feb30-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="feb30-104">tblLastChatId 包含为每位用户生成 (并在 tblChat 表中使用) 的最后一个聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="feb30-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="feb30-105">多</span><span class="sxs-lookup"><span data-stu-id="feb30-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feb30-106">列</span><span class="sxs-lookup"><span data-stu-id="feb30-106">Column</span></span></th>
<th><span data-ttu-id="feb30-107">类型</span><span class="sxs-lookup"><span data-stu-id="feb30-107">Type</span></span></th>
<th><span data-ttu-id="feb30-108">说明</span><span class="sxs-lookup"><span data-stu-id="feb30-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feb30-109">a</span><span class="sxs-lookup"><span data-stu-id="feb30-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="feb30-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="feb30-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="feb30-111">节点 ID (聊天室-仅类型)。</span><span class="sxs-lookup"><span data-stu-id="feb30-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feb30-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="feb30-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="feb30-113">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="feb30-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="feb30-114">上次使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="feb30-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="feb30-115">标示</span><span class="sxs-lookup"><span data-stu-id="feb30-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feb30-116">列</span><span class="sxs-lookup"><span data-stu-id="feb30-116">Column</span></span></th>
<th><span data-ttu-id="feb30-117">说明</span><span class="sxs-lookup"><span data-stu-id="feb30-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feb30-118">&lt;lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="feb30-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="feb30-119">主关键字 (仅一个参数 a 足以处理)。</span><span class="sxs-lookup"><span data-stu-id="feb30-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feb30-120">a</span><span class="sxs-lookup"><span data-stu-id="feb30-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="feb30-121">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="feb30-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="feb30-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feb30-122">See Also</span></span>


[<span data-ttu-id="feb30-123">Lync Server 2013 中的 tblChat</span><span class="sxs-lookup"><span data-stu-id="feb30-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

