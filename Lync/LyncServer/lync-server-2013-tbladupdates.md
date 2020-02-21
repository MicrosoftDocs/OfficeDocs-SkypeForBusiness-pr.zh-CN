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
ms.openlocfilehash: ad3ef2afaa162219d140a4eaef204dc6e1e2ab02
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="76cb6-102">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="76cb6-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76cb6-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="76cb6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="76cb6-104">tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="76cb6-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="76cb6-105">Columns</span><span class="sxs-lookup"><span data-stu-id="76cb6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76cb6-106">列</span><span class="sxs-lookup"><span data-stu-id="76cb6-106">Column</span></span></th>
<th><span data-ttu-id="76cb6-107">类型</span><span class="sxs-lookup"><span data-stu-id="76cb6-107">Type</span></span></th>
<th><span data-ttu-id="76cb6-108">Description</span><span class="sxs-lookup"><span data-stu-id="76cb6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76cb6-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="76cb6-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="76cb6-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="76cb6-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="76cb6-111">被更改对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="76cb6-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cb6-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="76cb6-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="76cb6-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="76cb6-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="76cb6-114">对象的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="76cb6-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cb6-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="76cb6-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="76cb6-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="76cb6-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="76cb6-117">如果对象至少有一个属性被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="76cb6-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cb6-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="76cb6-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="76cb6-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="76cb6-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="76cb6-120">如果成员身份被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="76cb6-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cb6-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="76cb6-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="76cb6-122">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="76cb6-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="76cb6-123">未使用。</span><span class="sxs-lookup"><span data-stu-id="76cb6-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cb6-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="76cb6-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="76cb6-125">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="76cb6-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="76cb6-126">如果对象已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="76cb6-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cb6-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="76cb6-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="76cb6-128">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="76cb6-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="76cb6-129">插入行时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="76cb6-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

