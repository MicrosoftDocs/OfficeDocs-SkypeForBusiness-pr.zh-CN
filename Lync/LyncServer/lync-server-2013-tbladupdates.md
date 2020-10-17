---
title: Lync Server 2013： tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27fbbc6bb2fe68c2f4bfff91b999934069548d00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509479"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="bd9c7-102">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="bd9c7-102">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd9c7-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bd9c7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bd9c7-104">tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="bd9c7-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="bd9c7-105">列数</span><span class="sxs-lookup"><span data-stu-id="bd9c7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd9c7-106">列</span><span class="sxs-lookup"><span data-stu-id="bd9c7-106">Column</span></span></th>
<th><span data-ttu-id="bd9c7-107">类型</span><span class="sxs-lookup"><span data-stu-id="bd9c7-107">Type</span></span></th>
<th><span data-ttu-id="bd9c7-108">说明</span><span class="sxs-lookup"><span data-stu-id="bd9c7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd9c7-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bd9c7-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="bd9c7-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-111">被更改对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="bd9c7-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd9c7-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="bd9c7-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="bd9c7-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-114">对象的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="bd9c7-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd9c7-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="bd9c7-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="bd9c7-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-117">如果对象至少有一个属性被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="bd9c7-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd9c7-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="bd9c7-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="bd9c7-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-120">如果成员身份被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="bd9c7-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd9c7-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="bd9c7-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-122">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="bd9c7-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-123">未使用。</span><span class="sxs-lookup"><span data-stu-id="bd9c7-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd9c7-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="bd9c7-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-125">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="bd9c7-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-126">如果对象已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="bd9c7-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd9c7-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="bd9c7-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-128">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="bd9c7-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="bd9c7-129">插入行时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="bd9c7-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

