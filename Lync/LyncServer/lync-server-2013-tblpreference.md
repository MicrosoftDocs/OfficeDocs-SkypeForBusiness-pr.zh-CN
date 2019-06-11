---
title: Lync Server 2013：tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 652312c5ca48a140ee7f17486ef98debb4e08672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="b5177-102">Lync Server 2013 中的 tblPreference</span><span class="sxs-lookup"><span data-stu-id="b5177-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5177-103">_**主题上次修改时间:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="b5177-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="b5177-104">tblPreference 包含用户的客户端首选项。</span><span class="sxs-lookup"><span data-stu-id="b5177-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="b5177-105">这通常由 Lync 2013 之前的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="b5177-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="b5177-106">多</span><span class="sxs-lookup"><span data-stu-id="b5177-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5177-107">列</span><span class="sxs-lookup"><span data-stu-id="b5177-107">Column</span></span></th>
<th><span data-ttu-id="b5177-108">类型</span><span class="sxs-lookup"><span data-stu-id="b5177-108">Type</span></span></th>
<th><span data-ttu-id="b5177-109">说明</span><span class="sxs-lookup"><span data-stu-id="b5177-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5177-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="b5177-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="b5177-111">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="b5177-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="b5177-112">带格式的标签, 如: &lt;用户 sip uri&gt;| 用户名。&lt;首选项&gt;集。</span><span class="sxs-lookup"><span data-stu-id="b5177-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5177-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="b5177-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="b5177-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="b5177-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b5177-115">用于进行版本控制的序列号 (每个标签)。</span><span class="sxs-lookup"><span data-stu-id="b5177-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5177-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="b5177-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="b5177-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="b5177-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="b5177-118">编码内容。</span><span class="sxs-lookup"><span data-stu-id="b5177-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5177-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="b5177-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="b5177-120">int, not null</span><span class="sxs-lookup"><span data-stu-id="b5177-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b5177-121">已更新首选项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="b5177-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b5177-122">关键字</span><span class="sxs-lookup"><span data-stu-id="b5177-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5177-123">列</span><span class="sxs-lookup"><span data-stu-id="b5177-123">Column</span></span></th>
<th><span data-ttu-id="b5177-124">说明</span><span class="sxs-lookup"><span data-stu-id="b5177-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5177-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="b5177-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b5177-126">主键。</span><span class="sxs-lookup"><span data-stu-id="b5177-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

