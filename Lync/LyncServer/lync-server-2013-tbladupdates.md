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
ms.openlocfilehash: ee3f0d881e26c3d26773b1b59feca3d1d02665dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="40526-102">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="40526-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40526-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="40526-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="40526-104">tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="40526-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="40526-105">Columns</span><span class="sxs-lookup"><span data-stu-id="40526-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40526-106">列</span><span class="sxs-lookup"><span data-stu-id="40526-106">Column</span></span></th>
<th><span data-ttu-id="40526-107">类型</span><span class="sxs-lookup"><span data-stu-id="40526-107">Type</span></span></th>
<th><span data-ttu-id="40526-108">说明</span><span class="sxs-lookup"><span data-stu-id="40526-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40526-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="40526-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="40526-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="40526-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="40526-111">被更改对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="40526-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40526-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="40526-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="40526-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="40526-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="40526-114">对象的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="40526-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40526-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="40526-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="40526-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="40526-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="40526-117">如果对象至少有一个属性被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="40526-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40526-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="40526-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="40526-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="40526-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="40526-120">如果成员身份被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="40526-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40526-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="40526-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="40526-122">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="40526-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="40526-123">未使用。</span><span class="sxs-lookup"><span data-stu-id="40526-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40526-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="40526-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="40526-125">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="40526-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="40526-126">如果对象已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="40526-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40526-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="40526-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="40526-128">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="40526-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="40526-129">插入行时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="40526-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

