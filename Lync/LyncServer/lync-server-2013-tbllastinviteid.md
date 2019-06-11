---
title: Lync Server 2013：tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be882798a620933af28c7e6697a388ef01817e5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="e68e7-102">Lync Server 2013 中的 tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="e68e7-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e68e7-103">_**主题上次修改时间:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e68e7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e68e7-104">tblLastInviteId 包含为每位用户生成 (并在 tblPrincipalInvites 表中使用) 的最后一个邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="e68e7-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="e68e7-105">多</span><span class="sxs-lookup"><span data-stu-id="e68e7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e68e7-106">列</span><span class="sxs-lookup"><span data-stu-id="e68e7-106">Column</span></span></th>
<th><span data-ttu-id="e68e7-107">类型</span><span class="sxs-lookup"><span data-stu-id="e68e7-107">Type</span></span></th>
<th><span data-ttu-id="e68e7-108">说明</span><span class="sxs-lookup"><span data-stu-id="e68e7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e68e7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e68e7-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="e68e7-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e68e7-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e68e7-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="e68e7-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e68e7-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="e68e7-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="e68e7-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="e68e7-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e68e7-114">上次使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="e68e7-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e68e7-115">标示</span><span class="sxs-lookup"><span data-stu-id="e68e7-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e68e7-116">列</span><span class="sxs-lookup"><span data-stu-id="e68e7-116">Column</span></span></th>
<th><span data-ttu-id="e68e7-117">说明</span><span class="sxs-lookup"><span data-stu-id="e68e7-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e68e7-118">prinID</span><span class="sxs-lookup"><span data-stu-id="e68e7-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="e68e7-119">主键。</span><span class="sxs-lookup"><span data-stu-id="e68e7-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e68e7-120">prinID</span><span class="sxs-lookup"><span data-stu-id="e68e7-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="e68e7-121">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="e68e7-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="e68e7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e68e7-122">See Also</span></span>


[<span data-ttu-id="e68e7-123">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="e68e7-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

