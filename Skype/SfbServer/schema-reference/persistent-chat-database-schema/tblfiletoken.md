---
title: tblFileToken
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含用于文件传输的临时令牌。
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816012"
---
# <a name="tblfiletoken"></a><span data-ttu-id="46943-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="46943-103">tblFileToken</span></span>
 
<span data-ttu-id="46943-104">tblFileToken 包含用于文件传输的临时令牌。</span><span class="sxs-lookup"><span data-stu-id="46943-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="46943-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="46943-105">**Columns**</span></span>

|<span data-ttu-id="46943-106">**列**</span><span class="sxs-lookup"><span data-stu-id="46943-106">**Column**</span></span>|<span data-ttu-id="46943-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="46943-107">**Type**</span></span>|<span data-ttu-id="46943-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="46943-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46943-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="46943-109">fileToken</span></span>  <br/> |<span data-ttu-id="46943-110">nvarchar (50)，不为 null</span><span class="sxs-lookup"><span data-stu-id="46943-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="46943-111">唯一令牌（一个 GUID）。</span><span class="sxs-lookup"><span data-stu-id="46943-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="46943-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="46943-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="46943-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="46943-113">int, not null</span></span>  <br/> |<span data-ttu-id="46943-114">要传输文件的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="46943-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="46943-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="46943-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="46943-116">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="46943-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="46943-117">聊天室节点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="46943-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="46943-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="46943-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="46943-119">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="46943-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="46943-p101">过期时间。除非固定，令牌的有效期为 30 分钟（请参阅此列中以下说明）。</span><span class="sxs-lookup"><span data-stu-id="46943-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="46943-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="46943-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="46943-123">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="46943-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="46943-124">已传输文件的 URL（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="46943-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="46943-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="46943-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="46943-126">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="46943-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="46943-127">已传输文件的缩略图的 URL（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="46943-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="46943-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="46943-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="46943-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="46943-129">datetime2</span></span>  <br/> |<span data-ttu-id="46943-130">实际文件传输操作的时间戳（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="46943-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="46943-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="46943-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="46943-132">bit</span><span class="sxs-lookup"><span data-stu-id="46943-132">bit</span></span>  <br/> |<span data-ttu-id="46943-133">如果上载，则为 True；如果下载，则为 False（用于合规性服务）。</span><span class="sxs-lookup"><span data-stu-id="46943-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="46943-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="46943-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="46943-135">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="46943-135">bit, not null</span></span>  <br/> |<span data-ttu-id="46943-136">如果令牌是固定的，则为 True。</span><span class="sxs-lookup"><span data-stu-id="46943-136">True if token is pinned.</span></span> <span data-ttu-id="46943-137">它用于将令牌保留到表中，直到合规性服务有机会从表中检索相关字段。</span><span class="sxs-lookup"><span data-stu-id="46943-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="46943-138">**Keys**</span><span class="sxs-lookup"><span data-stu-id="46943-138">**Keys**</span></span>

|<span data-ttu-id="46943-139">**列**</span><span class="sxs-lookup"><span data-stu-id="46943-139">**Column**</span></span>|<span data-ttu-id="46943-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="46943-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="46943-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="46943-141">fileToken</span></span>  <br/> |<span data-ttu-id="46943-142">主键。</span><span class="sxs-lookup"><span data-stu-id="46943-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="46943-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="46943-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="46943-144">其查找包含在 tblNode.nodeGuid 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="46943-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

