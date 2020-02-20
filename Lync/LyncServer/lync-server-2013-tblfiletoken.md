---
title: Lync Server 2013： tblFileToken
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
ms.openlocfilehash: 9e3d80b1a326140a94b840c212fc8577a73e468f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="ea07b-102">Lync Server 2013 中的 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="ea07b-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea07b-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ea07b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ea07b-104">tblFileToken 包含用于文件传输的临时令牌。</span><span class="sxs-lookup"><span data-stu-id="ea07b-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="ea07b-105">Columns</span><span class="sxs-lookup"><span data-stu-id="ea07b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea07b-106">列</span><span class="sxs-lookup"><span data-stu-id="ea07b-106">Column</span></span></th>
<th><span data-ttu-id="ea07b-107">类型</span><span class="sxs-lookup"><span data-stu-id="ea07b-107">Type</span></span></th>
<th><span data-ttu-id="ea07b-108">说明</span><span class="sxs-lookup"><span data-stu-id="ea07b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea07b-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="ea07b-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="ea07b-110">nvarchar (50)，不为 null</span><span class="sxs-lookup"><span data-stu-id="ea07b-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="ea07b-111">唯一令牌（一个 GUID）。</span><span class="sxs-lookup"><span data-stu-id="ea07b-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea07b-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="ea07b-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="ea07b-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="ea07b-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ea07b-114">要传输文件的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="ea07b-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea07b-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="ea07b-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="ea07b-116">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="ea07b-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="ea07b-117">聊天室节点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ea07b-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea07b-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="ea07b-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="ea07b-119">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="ea07b-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="ea07b-p101">过期时间。除非固定，令牌的有效期为 30 分钟（请参阅此列中以下说明）。</span><span class="sxs-lookup"><span data-stu-id="ea07b-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea07b-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="ea07b-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="ea07b-123">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ea07b-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ea07b-124">已传输文件的 URL（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="ea07b-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea07b-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="ea07b-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="ea07b-126">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ea07b-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ea07b-127">已传输文件的缩略图的 URL（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="ea07b-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea07b-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="ea07b-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="ea07b-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="ea07b-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="ea07b-130">实际文件传输操作的时间戳（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="ea07b-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea07b-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="ea07b-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="ea07b-132">位</span><span class="sxs-lookup"><span data-stu-id="ea07b-132">bit</span></span></p></td>
<td><p><span data-ttu-id="ea07b-133">如果上载，则为 True；如果下载，则为 False（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="ea07b-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea07b-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="ea07b-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="ea07b-135">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="ea07b-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ea07b-p102">如果令牌是固定的，则为 True。它将不会用于保存表中的令牌，除非合规性服务有机会从其中检索相关字段。</span><span class="sxs-lookup"><span data-stu-id="ea07b-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ea07b-138">Keys</span><span class="sxs-lookup"><span data-stu-id="ea07b-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea07b-139">列</span><span class="sxs-lookup"><span data-stu-id="ea07b-139">Column</span></span></th>
<th><span data-ttu-id="ea07b-140">说明</span><span class="sxs-lookup"><span data-stu-id="ea07b-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea07b-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="ea07b-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="ea07b-142">主键。</span><span class="sxs-lookup"><span data-stu-id="ea07b-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea07b-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="ea07b-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="ea07b-144">其查找包含在 tblNode.nodeGuid 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="ea07b-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

