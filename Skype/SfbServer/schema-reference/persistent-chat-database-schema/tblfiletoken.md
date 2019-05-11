---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含用于文件传输的临时令牌。
ms.openlocfilehash: c6735cf7da1412cca86817360c1a35030e8b0df4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929852"
---
# <a name="tblfiletoken"></a><span data-ttu-id="92c1d-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="92c1d-103">tblFileToken</span></span>
 
<span data-ttu-id="92c1d-104">tblFileToken 包含用于文件传输的临时令牌。</span><span class="sxs-lookup"><span data-stu-id="92c1d-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="92c1d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="92c1d-105">**Columns**</span></span>

|<span data-ttu-id="92c1d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="92c1d-106">**Column**</span></span>|<span data-ttu-id="92c1d-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="92c1d-107">**Type**</span></span>|<span data-ttu-id="92c1d-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="92c1d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92c1d-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="92c1d-109">fileToken</span></span>  <br/> |<span data-ttu-id="92c1d-110">nvarchar (50)，不为 null</span><span class="sxs-lookup"><span data-stu-id="92c1d-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="92c1d-111">唯一的令牌 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="92c1d-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="92c1d-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="92c1d-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="92c1d-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="92c1d-113">int, not null</span></span>  <br/> |<span data-ttu-id="92c1d-114">要传输文件的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="92c1d-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="92c1d-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="92c1d-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="92c1d-116">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="92c1d-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="92c1d-117">聊天室节点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="92c1d-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="92c1d-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="92c1d-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="92c1d-119">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="92c1d-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="92c1d-120">过期时间。</span><span class="sxs-lookup"><span data-stu-id="92c1d-120">Expiration time.</span></span> <span data-ttu-id="92c1d-121">（令牌过期后 30 分钟，除非固定 （请参阅此列中的以下说明）。</span><span class="sxs-lookup"><span data-stu-id="92c1d-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="92c1d-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="92c1d-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="92c1d-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="92c1d-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="92c1d-124">已传输文件 （用于合规性服务） 的 URL。</span><span class="sxs-lookup"><span data-stu-id="92c1d-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="92c1d-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="92c1d-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="92c1d-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="92c1d-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="92c1d-127">已传输文件 （用于合规性服务） 的缩略图的 URL。</span><span class="sxs-lookup"><span data-stu-id="92c1d-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="92c1d-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="92c1d-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="92c1d-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="92c1d-129">datetime2</span></span>  <br/> |<span data-ttu-id="92c1d-130">（用于合规性服务） 的实际文件传输操作的时间戳。</span><span class="sxs-lookup"><span data-stu-id="92c1d-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="92c1d-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="92c1d-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="92c1d-132">bit</span><span class="sxs-lookup"><span data-stu-id="92c1d-132">bit</span></span>  <br/> |<span data-ttu-id="92c1d-133">True 如果上载;则为 false （用于合规性服务） 下载。</span><span class="sxs-lookup"><span data-stu-id="92c1d-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="92c1d-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="92c1d-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="92c1d-135">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="92c1d-135">bit, not null</span></span>  <br/> |<span data-ttu-id="92c1d-136">如果固定令牌，则为 true。</span><span class="sxs-lookup"><span data-stu-id="92c1d-136">True if token is pinned.</span></span> <span data-ttu-id="92c1d-137">它用于保留标记的表中，直到合规性服务有机会从中检索相关字段。</span><span class="sxs-lookup"><span data-stu-id="92c1d-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="92c1d-138">**键**</span><span class="sxs-lookup"><span data-stu-id="92c1d-138">**Keys**</span></span>

|<span data-ttu-id="92c1d-139">**列**</span><span class="sxs-lookup"><span data-stu-id="92c1d-139">**Column**</span></span>|<span data-ttu-id="92c1d-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="92c1d-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="92c1d-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="92c1d-141">fileToken</span></span>  <br/> |<span data-ttu-id="92c1d-142">主键。</span><span class="sxs-lookup"><span data-stu-id="92c1d-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="92c1d-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="92c1d-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="92c1d-144">包含在 tblNode.nodeGuid 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="92c1d-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

