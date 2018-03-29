---
title: tblFileToken
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含临时标记用于文件传输的目的。
ms.openlocfilehash: 86047611c21301543a12486fa1c15bb15fde4c65
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblfiletoken"></a><span data-ttu-id="40083-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="40083-103">tblFileToken</span></span>
 
<span data-ttu-id="40083-104">tblFileToken 包含临时标记用于文件传输的目的。</span><span class="sxs-lookup"><span data-stu-id="40083-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="40083-105">**列**</span><span class="sxs-lookup"><span data-stu-id="40083-105">**Columns**</span></span>

|<span data-ttu-id="40083-106">**列**</span><span class="sxs-lookup"><span data-stu-id="40083-106">**Column**</span></span>|<span data-ttu-id="40083-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="40083-107">**Type**</span></span>|<span data-ttu-id="40083-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="40083-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40083-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="40083-109">fileToken</span></span>  <br/> |<span data-ttu-id="40083-110">nvarchar (50) 不为空</span><span class="sxs-lookup"><span data-stu-id="40083-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="40083-111">唯一的标记 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="40083-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="40083-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="40083-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="40083-113">int，不为空</span><span class="sxs-lookup"><span data-stu-id="40083-113">int, not null</span></span>  <br/> |<span data-ttu-id="40083-114">将文件传送的承担者的 ID。</span><span class="sxs-lookup"><span data-stu-id="40083-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="40083-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="40083-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="40083-116">GUID，不为空</span><span class="sxs-lookup"><span data-stu-id="40083-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="40083-117">聊天室节点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="40083-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="40083-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="40083-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="40083-119">日期时间不为空</span><span class="sxs-lookup"><span data-stu-id="40083-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="40083-120">到期时间。</span><span class="sxs-lookup"><span data-stu-id="40083-120">Expiration time.</span></span> <span data-ttu-id="40083-121">（令牌过期，30 分钟后，除非固定 （请参阅以下说明此列中的）。</span><span class="sxs-lookup"><span data-stu-id="40083-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="40083-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="40083-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="40083-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="40083-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="40083-124">（用于法规遵从性服务） 传输的文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="40083-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="40083-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="40083-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="40083-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="40083-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="40083-127">（用于法规遵从性服务） 传输的文件的缩略图的 URL。</span><span class="sxs-lookup"><span data-stu-id="40083-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="40083-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="40083-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="40083-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="40083-129">datetime2</span></span>  <br/> |<span data-ttu-id="40083-130">实际的文件传输操作 （用于法规遵从性服务） 的时间戳。</span><span class="sxs-lookup"><span data-stu-id="40083-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="40083-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="40083-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="40083-132">bit</span><span class="sxs-lookup"><span data-stu-id="40083-132">bit</span></span>  <br/> |<span data-ttu-id="40083-133">True 传;假如果下载 （用于法规遵从性服务）。</span><span class="sxs-lookup"><span data-stu-id="40083-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="40083-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="40083-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="40083-135">位，不为空</span><span class="sxs-lookup"><span data-stu-id="40083-135">bit, not null</span></span>  <br/> |<span data-ttu-id="40083-136">如果令牌被固定，则为 true。</span><span class="sxs-lookup"><span data-stu-id="40083-136">True if token is pinned.</span></span> <span data-ttu-id="40083-137">它用来标记保留的表中，直到法规遵从性服务有机会从中检索的相关字段。</span><span class="sxs-lookup"><span data-stu-id="40083-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="40083-138">**密钥**</span><span class="sxs-lookup"><span data-stu-id="40083-138">**Keys**</span></span>

|<span data-ttu-id="40083-139">**列**</span><span class="sxs-lookup"><span data-stu-id="40083-139">**Column**</span></span>|<span data-ttu-id="40083-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="40083-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40083-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="40083-141">fileToken</span></span>  <br/> |<span data-ttu-id="40083-142">为主键。</span><span class="sxs-lookup"><span data-stu-id="40083-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="40083-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="40083-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="40083-144">TblNode.nodeGuid 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="40083-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

