---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含尚未由合规性适配器处理的合规性事件。
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295508"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="d96d0-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="d96d0-103">tblComplianceData</span></span>
 
<span data-ttu-id="d96d0-104">tblComplianceData 包含尚未由合规性适配器处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="d96d0-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="d96d0-105">**多**</span><span class="sxs-lookup"><span data-stu-id="d96d0-105">**Columns**</span></span>

|<span data-ttu-id="d96d0-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d96d0-106">**Column**</span></span>|<span data-ttu-id="d96d0-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="d96d0-107">**Type**</span></span>|<span data-ttu-id="d96d0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="d96d0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d96d0-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="d96d0-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="d96d0-110">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="d96d0-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="d96d0-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="d96d0-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="d96d0-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="d96d0-112">entryDate</span></span>  <br/> |<span data-ttu-id="d96d0-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="d96d0-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="d96d0-114">插入时间 (对于 cmplType = 9, 将来可能会是很远), 因为在该情况下, 条目只是占位符。</span><span class="sxs-lookup"><span data-stu-id="d96d0-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="d96d0-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="d96d0-115">cmplType</span></span>  <br/> |<span data-ttu-id="d96d0-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="d96d0-116">int, not null</span></span>  <br/> | <span data-ttu-id="d96d0-117">合规性事件的类型:</span><span class="sxs-lookup"><span data-stu-id="d96d0-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="d96d0-118">1: 聊天</span><span class="sxs-lookup"><span data-stu-id="d96d0-118">1: Chat</span></span> <br/>  <span data-ttu-id="d96d0-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="d96d0-119">2: Backchat</span></span> <br/>  <span data-ttu-id="d96d0-120">3: 文件下载</span><span class="sxs-lookup"><span data-stu-id="d96d0-120">3: File download</span></span> <br/>  <span data-ttu-id="d96d0-121">4: 文件上载</span><span class="sxs-lookup"><span data-stu-id="d96d0-121">4: File upload</span></span> <br/>  <span data-ttu-id="d96d0-122">9: 临时文件传输</span><span class="sxs-lookup"><span data-stu-id="d96d0-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="d96d0-123">10: 删除聊天 (带替换)</span><span class="sxs-lookup"><span data-stu-id="d96d0-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="d96d0-124">11: 聊天清除</span><span class="sxs-lookup"><span data-stu-id="d96d0-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="d96d0-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="d96d0-125">cmplTime</span></span>  <br/> |<span data-ttu-id="d96d0-126">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="d96d0-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="d96d0-127">事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="d96d0-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="d96d0-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="d96d0-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="d96d0-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="d96d0-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d96d0-130">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="d96d0-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="d96d0-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="d96d0-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="d96d0-132">bigint</span><span class="sxs-lookup"><span data-stu-id="d96d0-132">bigint</span></span>  <br/> |<span data-ttu-id="d96d0-133">聊天 ID (对应于 tblChat 表)。</span><span class="sxs-lookup"><span data-stu-id="d96d0-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="d96d0-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="d96d0-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="d96d0-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="d96d0-135">int, not null</span></span>  <br/> |<span data-ttu-id="d96d0-136">海报的主体 ID (对应于 tblPrincipal 表)。</span><span class="sxs-lookup"><span data-stu-id="d96d0-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="d96d0-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="d96d0-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="d96d0-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="d96d0-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d96d0-139">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="d96d0-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="d96d0-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="d96d0-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="d96d0-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="d96d0-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="d96d0-142">邮件 (编码取决于 cmplType)。</span><span class="sxs-lookup"><span data-stu-id="d96d0-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="d96d0-143">**关键字**</span><span class="sxs-lookup"><span data-stu-id="d96d0-143">**Key**</span></span>

|<span data-ttu-id="d96d0-144">**列**</span><span class="sxs-lookup"><span data-stu-id="d96d0-144">**Column**</span></span>|<span data-ttu-id="d96d0-145">**说明**</span><span class="sxs-lookup"><span data-stu-id="d96d0-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d96d0-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="d96d0-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="d96d0-147">主键。</span><span class="sxs-lookup"><span data-stu-id="d96d0-147">Primary key.</span></span>  <br/> |
   

