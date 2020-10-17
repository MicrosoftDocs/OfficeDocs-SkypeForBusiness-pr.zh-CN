---
title: Lync Server 2013： tblLastInviteId
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
ms.openlocfilehash: a49682d5c154b154ddda6c5fd411905f5850722d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523789"
---
# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="2e5d7-102">Lync Server 2013 中的 tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="2e5d7-102">tblLastInviteId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e5d7-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2e5d7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2e5d7-104">tblLastInviteId 包含上次为每个用户生成的并且在 tblPrincipalInvites 表中使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="2e5d7-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="2e5d7-105">列数</span><span class="sxs-lookup"><span data-stu-id="2e5d7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e5d7-106">列</span><span class="sxs-lookup"><span data-stu-id="2e5d7-106">Column</span></span></th>
<th><span data-ttu-id="2e5d7-107">类型</span><span class="sxs-lookup"><span data-stu-id="2e5d7-107">Type</span></span></th>
<th><span data-ttu-id="2e5d7-108">说明</span><span class="sxs-lookup"><span data-stu-id="2e5d7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e5d7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="2e5d7-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="2e5d7-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="2e5d7-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2e5d7-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="2e5d7-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e5d7-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="2e5d7-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="2e5d7-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="2e5d7-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2e5d7-114">上次使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="2e5d7-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2e5d7-115">Keys</span><span class="sxs-lookup"><span data-stu-id="2e5d7-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e5d7-116">列</span><span class="sxs-lookup"><span data-stu-id="2e5d7-116">Column</span></span></th>
<th><span data-ttu-id="2e5d7-117">说明</span><span class="sxs-lookup"><span data-stu-id="2e5d7-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e5d7-118">prinID</span><span class="sxs-lookup"><span data-stu-id="2e5d7-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="2e5d7-119">主键。</span><span class="sxs-lookup"><span data-stu-id="2e5d7-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e5d7-120">prinID</span><span class="sxs-lookup"><span data-stu-id="2e5d7-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="2e5d7-121">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="2e5d7-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="2e5d7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e5d7-122">See Also</span></span>


[<span data-ttu-id="2e5d7-123">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="2e5d7-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

