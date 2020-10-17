---
title: Lync Server 2013： tblFileToken
description: Lync Server 2013： tblFileToken。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547628"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="7d031-103">Lync Server 2013 中的 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="7d031-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d031-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7d031-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7d031-105">tblFileToken 包含用于文件传输的临时令牌。</span><span class="sxs-lookup"><span data-stu-id="7d031-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="7d031-106">列数</span><span class="sxs-lookup"><span data-stu-id="7d031-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d031-107">列</span><span class="sxs-lookup"><span data-stu-id="7d031-107">Column</span></span></th>
<th><span data-ttu-id="7d031-108">类型</span><span class="sxs-lookup"><span data-stu-id="7d031-108">Type</span></span></th>
<th><span data-ttu-id="7d031-109">说明</span><span class="sxs-lookup"><span data-stu-id="7d031-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d031-110">fileToken</span><span class="sxs-lookup"><span data-stu-id="7d031-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="7d031-111">nvarchar (50)，不为 null</span><span class="sxs-lookup"><span data-stu-id="7d031-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="7d031-112">唯一令牌（一个 GUID）。</span><span class="sxs-lookup"><span data-stu-id="7d031-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d031-113">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="7d031-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="7d031-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="7d031-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7d031-115">要传输文件的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="7d031-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d031-116">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="7d031-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="7d031-117">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="7d031-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="7d031-118">聊天室节点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="7d031-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d031-119">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="7d031-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="7d031-120">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="7d031-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="7d031-p101">过期时间。除非固定，令牌的有效期为 30 分钟（请参阅此列中以下说明）。</span><span class="sxs-lookup"><span data-stu-id="7d031-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d031-123">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="7d031-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="7d031-124">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7d031-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7d031-125">已传输文件的 URL（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="7d031-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d031-126">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="7d031-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="7d031-127">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7d031-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7d031-128">已传输文件的缩略图的 URL（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="7d031-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d031-129">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="7d031-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="7d031-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="7d031-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="7d031-131">实际文件传输操作的时间戳（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="7d031-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d031-132">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="7d031-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="7d031-133">位</span><span class="sxs-lookup"><span data-stu-id="7d031-133">bit</span></span></p></td>
<td><p><span data-ttu-id="7d031-134">如果上载，则为 True；如果下载，则为 False（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="7d031-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d031-135">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="7d031-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="7d031-136">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="7d031-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7d031-p102">如果令牌是固定的，则为 True。它将不会用于保存表中的令牌，除非合规性服务有机会从其中检索相关字段。</span><span class="sxs-lookup"><span data-stu-id="7d031-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7d031-139">Keys</span><span class="sxs-lookup"><span data-stu-id="7d031-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d031-140">列</span><span class="sxs-lookup"><span data-stu-id="7d031-140">Column</span></span></th>
<th><span data-ttu-id="7d031-141">说明</span><span class="sxs-lookup"><span data-stu-id="7d031-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d031-142">fileToken</span><span class="sxs-lookup"><span data-stu-id="7d031-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="7d031-143">主键。</span><span class="sxs-lookup"><span data-stu-id="7d031-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d031-144">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="7d031-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="7d031-145">其查找包含在 tblNode.nodeGuid 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="7d031-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

