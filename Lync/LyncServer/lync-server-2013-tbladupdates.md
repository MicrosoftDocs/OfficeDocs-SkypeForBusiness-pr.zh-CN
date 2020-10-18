---
title: Lync Server 2013： tblADUpdates
description: Lync Server 2013： tblADUpdates。
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
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573678"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="ebbd8-103">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="ebbd8-103">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebbd8-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ebbd8-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ebbd8-105">tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="ebbd8-105">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="ebbd8-106">列数</span><span class="sxs-lookup"><span data-stu-id="ebbd8-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebbd8-107">列</span><span class="sxs-lookup"><span data-stu-id="ebbd8-107">Column</span></span></th>
<th><span data-ttu-id="ebbd8-108">类型</span><span class="sxs-lookup"><span data-stu-id="ebbd8-108">Type</span></span></th>
<th><span data-ttu-id="ebbd8-109">说明</span><span class="sxs-lookup"><span data-stu-id="ebbd8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebbd8-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ebbd8-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-111">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="ebbd8-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-112">被更改对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="ebbd8-112">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebbd8-113">prinADPath</span><span class="sxs-lookup"><span data-stu-id="ebbd8-113">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-114">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="ebbd8-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-115">对象的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="ebbd8-115">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebbd8-116">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="ebbd8-116">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-117">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="ebbd8-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-118">如果对象至少有一个属性被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="ebbd8-118">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebbd8-119">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="ebbd8-119">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-120">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="ebbd8-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-121">如果成员身份被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="ebbd8-121">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebbd8-122">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="ebbd8-122">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-123">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="ebbd8-123">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-124">未使用。</span><span class="sxs-lookup"><span data-stu-id="ebbd8-124">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebbd8-125">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="ebbd8-125">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-126">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="ebbd8-126">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-127">如果对象已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="ebbd8-127">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebbd8-128">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="ebbd8-128">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-129">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="ebbd8-129">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="ebbd8-130">插入行时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="ebbd8-130">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

