---
title: tblComplianceData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含具有合规性适配器尚未处理的合规性事件。
ms.openlocfilehash: e617f7821fcf026f279f333d45f526a1322509a1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885819"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="3c512-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="3c512-103">tblComplianceData</span></span>
 
<span data-ttu-id="3c512-104">tblComplianceData 包含具有合规性适配器尚未处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="3c512-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="3c512-105">**列**</span><span class="sxs-lookup"><span data-stu-id="3c512-105">**Columns**</span></span>

|<span data-ttu-id="3c512-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3c512-106">**Column**</span></span>|<span data-ttu-id="3c512-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="3c512-107">**Type**</span></span>|<span data-ttu-id="3c512-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="3c512-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3c512-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="3c512-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="3c512-110">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="3c512-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="3c512-111">事件 id。</span><span class="sxs-lookup"><span data-stu-id="3c512-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="3c512-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="3c512-112">entryDate</span></span>  <br/> |<span data-ttu-id="3c512-113">smalldatetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="3c512-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="3c512-114">插入时间 (可能遥远将来对于 cmplType = 9，因为该条目在此情况下是只是一个占位符)。</span><span class="sxs-lookup"><span data-stu-id="3c512-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="3c512-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="3c512-115">cmplType</span></span>  <br/> |<span data-ttu-id="3c512-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="3c512-116">int, not null</span></span>  <br/> | <span data-ttu-id="3c512-117">合规性事件的类型：</span><span class="sxs-lookup"><span data-stu-id="3c512-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="3c512-118">1： 聊天</span><span class="sxs-lookup"><span data-stu-id="3c512-118">1: Chat</span></span> <br/>  <span data-ttu-id="3c512-119">2： 聊天记录</span><span class="sxs-lookup"><span data-stu-id="3c512-119">2: Backchat</span></span> <br/>  <span data-ttu-id="3c512-120">3： 文件下载</span><span class="sxs-lookup"><span data-stu-id="3c512-120">3: File download</span></span> <br/>  <span data-ttu-id="3c512-121">4： 文件上载</span><span class="sxs-lookup"><span data-stu-id="3c512-121">4: File upload</span></span> <br/>  <span data-ttu-id="3c512-122">9： 临时文件传输</span><span class="sxs-lookup"><span data-stu-id="3c512-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="3c512-123">10： 删除聊天 （通过替换）</span><span class="sxs-lookup"><span data-stu-id="3c512-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="3c512-124">11： 清除聊天</span><span class="sxs-lookup"><span data-stu-id="3c512-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="3c512-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="3c512-125">cmplTime</span></span>  <br/> |<span data-ttu-id="3c512-126">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="3c512-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="3c512-127">该事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="3c512-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="3c512-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="3c512-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="3c512-129">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="3c512-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3c512-130">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="3c512-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="3c512-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="3c512-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="3c512-132">bigint</span><span class="sxs-lookup"><span data-stu-id="3c512-132">bigint</span></span>  <br/> |<span data-ttu-id="3c512-133">聊天 ID （与 tblChat.chatId 表对应）。</span><span class="sxs-lookup"><span data-stu-id="3c512-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="3c512-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="3c512-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="3c512-135">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="3c512-135">int, not null</span></span>  <br/> |<span data-ttu-id="3c512-136">（与 tblPrincipal.prinID 表对应） 的海报的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="3c512-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="3c512-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="3c512-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="3c512-138">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="3c512-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3c512-139">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="3c512-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="3c512-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="3c512-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="3c512-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="3c512-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="3c512-142">消息 （编码取决于 cmplType）。</span><span class="sxs-lookup"><span data-stu-id="3c512-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="3c512-143">**关键字**</span><span class="sxs-lookup"><span data-stu-id="3c512-143">**Key**</span></span>

|<span data-ttu-id="3c512-144">**列**</span><span class="sxs-lookup"><span data-stu-id="3c512-144">**Column**</span></span>|<span data-ttu-id="3c512-145">**说明**</span><span class="sxs-lookup"><span data-stu-id="3c512-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c512-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="3c512-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="3c512-147">主键。</span><span class="sxs-lookup"><span data-stu-id="3c512-147">Primary key.</span></span>  <br/> |
   

