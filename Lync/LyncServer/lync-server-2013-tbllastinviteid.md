---
title: Lync Server 2013： tblLastInviteId
description: Lync Server 2013： tblLastInviteId。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5a13cfc7edc29ea20c95f7f4d587b0cfb84eb73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547538"
---
# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="73b7c-103">Lync Server 2013 中的 tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="73b7c-103">tblLastInviteId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73b7c-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="73b7c-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="73b7c-105">tblLastInviteId 包含上次为每个用户生成的并且在 tblPrincipalInvites 表中使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="73b7c-105">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="73b7c-106">列数</span><span class="sxs-lookup"><span data-stu-id="73b7c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73b7c-107">列</span><span class="sxs-lookup"><span data-stu-id="73b7c-107">Column</span></span></th>
<th><span data-ttu-id="73b7c-108">类型</span><span class="sxs-lookup"><span data-stu-id="73b7c-108">Type</span></span></th>
<th><span data-ttu-id="73b7c-109">说明</span><span class="sxs-lookup"><span data-stu-id="73b7c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73b7c-110">prinID</span><span class="sxs-lookup"><span data-stu-id="73b7c-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="73b7c-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="73b7c-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="73b7c-112">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="73b7c-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73b7c-113">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="73b7c-113">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="73b7c-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="73b7c-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="73b7c-115">上次使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="73b7c-115">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="73b7c-116">Keys</span><span class="sxs-lookup"><span data-stu-id="73b7c-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73b7c-117">列</span><span class="sxs-lookup"><span data-stu-id="73b7c-117">Column</span></span></th>
<th><span data-ttu-id="73b7c-118">说明</span><span class="sxs-lookup"><span data-stu-id="73b7c-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73b7c-119">prinID</span><span class="sxs-lookup"><span data-stu-id="73b7c-119">prinID</span></span></p></td>
<td><p><span data-ttu-id="73b7c-120">主键。</span><span class="sxs-lookup"><span data-stu-id="73b7c-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73b7c-121">prinID</span><span class="sxs-lookup"><span data-stu-id="73b7c-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="73b7c-122">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="73b7c-122">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="73b7c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73b7c-123">See Also</span></span>


[<span data-ttu-id="73b7c-124">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="73b7c-124">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

