---
title: Lync Server 2013：tblFileToken
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
ms.openlocfilehash: b469b79e680c202654024d1ac20a55b9929e4b10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="6191e-102">Lync Server 2013 中的 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="6191e-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6191e-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6191e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6191e-104">tblFileToken 包含用于文件传输目的的临时令牌。</span><span class="sxs-lookup"><span data-stu-id="6191e-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="6191e-105">多</span><span class="sxs-lookup"><span data-stu-id="6191e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6191e-106">列</span><span class="sxs-lookup"><span data-stu-id="6191e-106">Column</span></span></th>
<th><span data-ttu-id="6191e-107">类型</span><span class="sxs-lookup"><span data-stu-id="6191e-107">Type</span></span></th>
<th><span data-ttu-id="6191e-108">说明</span><span class="sxs-lookup"><span data-stu-id="6191e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6191e-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="6191e-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="6191e-110">nvarchar （50），not null</span><span class="sxs-lookup"><span data-stu-id="6191e-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="6191e-111">唯一标记（GUID）。</span><span class="sxs-lookup"><span data-stu-id="6191e-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6191e-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="6191e-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="6191e-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="6191e-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6191e-114">传输文件的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="6191e-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6191e-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="6191e-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="6191e-116">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="6191e-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="6191e-117">聊天室节点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="6191e-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6191e-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="6191e-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="6191e-119">datetime，not null</span><span class="sxs-lookup"><span data-stu-id="6191e-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="6191e-120">过期时间。</span><span class="sxs-lookup"><span data-stu-id="6191e-120">Expiration time.</span></span> <span data-ttu-id="6191e-121">（令牌将在30分钟后到期，除非已固定（请参阅本专栏中的以下说明）。</span><span class="sxs-lookup"><span data-stu-id="6191e-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6191e-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="6191e-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="6191e-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6191e-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6191e-124">已传送文件的 URL （用于合规性服务使用）。</span><span class="sxs-lookup"><span data-stu-id="6191e-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6191e-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="6191e-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="6191e-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6191e-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6191e-127">传输文件的缩略图的 URL （适用于合规性服务使用）。</span><span class="sxs-lookup"><span data-stu-id="6191e-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6191e-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="6191e-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="6191e-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="6191e-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="6191e-130">实际文件传输操作的时间戳（用于合规性服务使用）。</span><span class="sxs-lookup"><span data-stu-id="6191e-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6191e-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="6191e-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="6191e-132">bit</span><span class="sxs-lookup"><span data-stu-id="6191e-132">bit</span></span></p></td>
<td><p><span data-ttu-id="6191e-133">如果上载，则为 True;如果下载（适用于合规性服务使用），则为 False。</span><span class="sxs-lookup"><span data-stu-id="6191e-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6191e-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="6191e-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="6191e-135">位，not null</span><span class="sxs-lookup"><span data-stu-id="6191e-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="6191e-136">如果标记已固定，则为 True。</span><span class="sxs-lookup"><span data-stu-id="6191e-136">True if token is pinned.</span></span> <span data-ttu-id="6191e-137">它用于在表中保留令牌，直到合规性服务有机会从中检索相关字段。</span><span class="sxs-lookup"><span data-stu-id="6191e-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="6191e-138">标示</span><span class="sxs-lookup"><span data-stu-id="6191e-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6191e-139">列</span><span class="sxs-lookup"><span data-stu-id="6191e-139">Column</span></span></th>
<th><span data-ttu-id="6191e-140">说明</span><span class="sxs-lookup"><span data-stu-id="6191e-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6191e-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="6191e-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="6191e-142">主键。</span><span class="sxs-lookup"><span data-stu-id="6191e-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6191e-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="6191e-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="6191e-144">TblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="6191e-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

