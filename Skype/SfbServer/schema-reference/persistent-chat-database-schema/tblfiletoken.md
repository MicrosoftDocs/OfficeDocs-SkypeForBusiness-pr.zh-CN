---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含用于文件传输目的的临时令牌。
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814590"
---
# <a name="tblfiletoken"></a><span data-ttu-id="fc98d-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="fc98d-103">tblFileToken</span></span>
 
<span data-ttu-id="fc98d-104">tblFileToken 包含用于文件传输目的的临时令牌。</span><span class="sxs-lookup"><span data-stu-id="fc98d-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="fc98d-105">**多**</span><span class="sxs-lookup"><span data-stu-id="fc98d-105">**Columns**</span></span>

|<span data-ttu-id="fc98d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="fc98d-106">**Column**</span></span>|<span data-ttu-id="fc98d-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="fc98d-107">**Type**</span></span>|<span data-ttu-id="fc98d-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="fc98d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fc98d-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="fc98d-109">fileToken</span></span>  <br/> |<span data-ttu-id="fc98d-110">nvarchar （50），not null</span><span class="sxs-lookup"><span data-stu-id="fc98d-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="fc98d-111">唯一标记（GUID）。</span><span class="sxs-lookup"><span data-stu-id="fc98d-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="fc98d-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="fc98d-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="fc98d-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="fc98d-113">int, not null</span></span>  <br/> |<span data-ttu-id="fc98d-114">传输文件的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="fc98d-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="fc98d-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="fc98d-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="fc98d-116">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="fc98d-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="fc98d-117">聊天室节点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="fc98d-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="fc98d-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="fc98d-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="fc98d-119">datetime，not null</span><span class="sxs-lookup"><span data-stu-id="fc98d-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="fc98d-120">过期时间。</span><span class="sxs-lookup"><span data-stu-id="fc98d-120">Expiration time.</span></span> <span data-ttu-id="fc98d-121">（令牌将在30分钟后到期，除非已固定（请参阅本专栏中的以下说明）。</span><span class="sxs-lookup"><span data-stu-id="fc98d-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="fc98d-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="fc98d-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="fc98d-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fc98d-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fc98d-124">已传送文件的 URL （用于合规性服务使用）。</span><span class="sxs-lookup"><span data-stu-id="fc98d-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="fc98d-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="fc98d-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="fc98d-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fc98d-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fc98d-127">传输文件的缩略图的 URL （适用于合规性服务使用）。</span><span class="sxs-lookup"><span data-stu-id="fc98d-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="fc98d-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="fc98d-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="fc98d-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="fc98d-129">datetime2</span></span>  <br/> |<span data-ttu-id="fc98d-130">实际文件传输操作的时间戳（用于合规性服务使用）。</span><span class="sxs-lookup"><span data-stu-id="fc98d-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="fc98d-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="fc98d-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="fc98d-132">bit</span><span class="sxs-lookup"><span data-stu-id="fc98d-132">bit</span></span>  <br/> |<span data-ttu-id="fc98d-133">如果上载，则为 True;如果下载（适用于合规性服务使用），则为 False。</span><span class="sxs-lookup"><span data-stu-id="fc98d-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="fc98d-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="fc98d-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="fc98d-135">位，not null</span><span class="sxs-lookup"><span data-stu-id="fc98d-135">bit, not null</span></span>  <br/> |<span data-ttu-id="fc98d-136">如果标记已固定，则为 True。</span><span class="sxs-lookup"><span data-stu-id="fc98d-136">True if token is pinned.</span></span> <span data-ttu-id="fc98d-137">它用于在表中保留令牌，直到合规性服务有机会从中检索相关字段。</span><span class="sxs-lookup"><span data-stu-id="fc98d-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="fc98d-138">**标示**</span><span class="sxs-lookup"><span data-stu-id="fc98d-138">**Keys**</span></span>

|<span data-ttu-id="fc98d-139">**列**</span><span class="sxs-lookup"><span data-stu-id="fc98d-139">**Column**</span></span>|<span data-ttu-id="fc98d-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="fc98d-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fc98d-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="fc98d-141">fileToken</span></span>  <br/> |<span data-ttu-id="fc98d-142">主键。</span><span class="sxs-lookup"><span data-stu-id="fc98d-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fc98d-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="fc98d-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="fc98d-144">TblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="fc98d-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

