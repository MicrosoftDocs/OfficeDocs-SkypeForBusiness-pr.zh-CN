---
title: Lync Server 2013：tblADUpdates
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
ms.openlocfilehash: cb4b5b73fb74c2337eeaa6b065396253a2cb0be4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="7aa6b-102">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="7aa6b-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa6b-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7aa6b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7aa6b-104">tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="7aa6b-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="7aa6b-105">多</span><span class="sxs-lookup"><span data-stu-id="7aa6b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aa6b-106">列</span><span class="sxs-lookup"><span data-stu-id="7aa6b-106">Column</span></span></th>
<th><span data-ttu-id="7aa6b-107">类型</span><span class="sxs-lookup"><span data-stu-id="7aa6b-107">Type</span></span></th>
<th><span data-ttu-id="7aa6b-108">说明</span><span class="sxs-lookup"><span data-stu-id="7aa6b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aa6b-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7aa6b-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-110">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="7aa6b-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-111">已更改对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="7aa6b-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa6b-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="7aa6b-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-113">nvarchar （384），not null</span><span class="sxs-lookup"><span data-stu-id="7aa6b-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-114">对象的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="7aa6b-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aa6b-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="7aa6b-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-116">位，not null</span><span class="sxs-lookup"><span data-stu-id="7aa6b-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-117">如果对象的至少一个属性发生更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="7aa6b-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa6b-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="7aa6b-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-119">位，not null</span><span class="sxs-lookup"><span data-stu-id="7aa6b-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-120">如果成员身份已更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="7aa6b-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aa6b-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="7aa6b-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-122">位，not null</span><span class="sxs-lookup"><span data-stu-id="7aa6b-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-123">未使用。</span><span class="sxs-lookup"><span data-stu-id="7aa6b-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa6b-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="7aa6b-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-125">位，not null</span><span class="sxs-lookup"><span data-stu-id="7aa6b-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-126">如果对象已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="7aa6b-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aa6b-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="7aa6b-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-128">datetime，not null</span><span class="sxs-lookup"><span data-stu-id="7aa6b-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="7aa6b-129">插入行的时间戳。</span><span class="sxs-lookup"><span data-stu-id="7aa6b-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

