---
title: Lync Server 2013： tblPreference
description: Lync Server 2013： tblPreference。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e8b81a6af93e9bf1d7673e54492579a1bed08e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547508"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="7cef9-103">Lync Server 2013 中的 tblPreference</span><span class="sxs-lookup"><span data-stu-id="7cef9-103">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cef9-104">_**上次修改的主题：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="7cef9-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="7cef9-105">tblPreference 包含用户的客户端首选项。</span><span class="sxs-lookup"><span data-stu-id="7cef9-105">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="7cef9-106">这通常由 Lync 2013 之前的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="7cef9-106">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="7cef9-107">列数</span><span class="sxs-lookup"><span data-stu-id="7cef9-107">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cef9-108">列</span><span class="sxs-lookup"><span data-stu-id="7cef9-108">Column</span></span></th>
<th><span data-ttu-id="7cef9-109">类型</span><span class="sxs-lookup"><span data-stu-id="7cef9-109">Type</span></span></th>
<th><span data-ttu-id="7cef9-110">说明</span><span class="sxs-lookup"><span data-stu-id="7cef9-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cef9-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="7cef9-111">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="7cef9-112">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="7cef9-112">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="7cef9-113">带有如下格式的标签： &lt; 用户 sip uri &gt; | username。 &lt;首选项集 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="7cef9-113">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cef9-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="7cef9-114">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="7cef9-115">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="7cef9-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7cef9-116"> (每个标签) 的顺序编号，用于实现版本控制。</span><span class="sxs-lookup"><span data-stu-id="7cef9-116">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cef9-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="7cef9-117">prefContent</span></span></p></td>
<td><p><span data-ttu-id="7cef9-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="7cef9-118">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="7cef9-119">编码的内容。</span><span class="sxs-lookup"><span data-stu-id="7cef9-119">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cef9-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="7cef9-120">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="7cef9-121">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="7cef9-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7cef9-122">更新了首选项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="7cef9-122">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7cef9-123">键</span><span class="sxs-lookup"><span data-stu-id="7cef9-123">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cef9-124">列</span><span class="sxs-lookup"><span data-stu-id="7cef9-124">Column</span></span></th>
<th><span data-ttu-id="7cef9-125">说明</span><span class="sxs-lookup"><span data-stu-id="7cef9-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cef9-126">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="7cef9-126">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="7cef9-127">主键。</span><span class="sxs-lookup"><span data-stu-id="7cef9-127">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

