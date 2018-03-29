---
title: tblComplianceData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含有尚未处理法规遵从性在适配器的法规遵从性事件。
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a><span data-ttu-id="41486-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="41486-103">tblComplianceData</span></span>
 
<span data-ttu-id="41486-104">tblComplianceData 包含有尚未处理法规遵从性在适配器的法规遵从性事件。</span><span class="sxs-lookup"><span data-stu-id="41486-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="41486-105">**列**</span><span class="sxs-lookup"><span data-stu-id="41486-105">**Columns**</span></span>

|<span data-ttu-id="41486-106">**列**</span><span class="sxs-lookup"><span data-stu-id="41486-106">**Column**</span></span>|<span data-ttu-id="41486-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="41486-107">**Type**</span></span>|<span data-ttu-id="41486-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="41486-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41486-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="41486-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="41486-110">bigint，不为空</span><span class="sxs-lookup"><span data-stu-id="41486-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="41486-111">事件 id。</span><span class="sxs-lookup"><span data-stu-id="41486-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="41486-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="41486-112">entryDate</span></span>  <br/> |<span data-ttu-id="41486-113">短格式不为空</span><span class="sxs-lookup"><span data-stu-id="41486-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="41486-114">插入时 (可能是到目前为止在将来为 cmplType = 9，因为在这种情况下对应的项是只是一个占位符)。</span><span class="sxs-lookup"><span data-stu-id="41486-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="41486-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="41486-115">cmplType</span></span>  <br/> |<span data-ttu-id="41486-116">int，不为空</span><span class="sxs-lookup"><span data-stu-id="41486-116">int, not null</span></span>  <br/> | <span data-ttu-id="41486-117">法规遵从性事件类型：</span><span class="sxs-lookup"><span data-stu-id="41486-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="41486-118">1： 聊天</span><span class="sxs-lookup"><span data-stu-id="41486-118">1: Chat</span></span> <br/>  <span data-ttu-id="41486-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="41486-119">2: Backchat</span></span> <br/>  <span data-ttu-id="41486-120">3： 文件下载</span><span class="sxs-lookup"><span data-stu-id="41486-120">3: File download</span></span> <br/>  <span data-ttu-id="41486-121">4： 文件上载</span><span class="sxs-lookup"><span data-stu-id="41486-121">4: File upload</span></span> <br/>  <span data-ttu-id="41486-122">9： 临时文件传输</span><span class="sxs-lookup"><span data-stu-id="41486-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="41486-123">10： 聊天 （替换） 的删除</span><span class="sxs-lookup"><span data-stu-id="41486-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="41486-124">11： 聊天清除</span><span class="sxs-lookup"><span data-stu-id="41486-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="41486-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="41486-125">cmplTime</span></span>  <br/> |<span data-ttu-id="41486-126">bigint，不为空</span><span class="sxs-lookup"><span data-stu-id="41486-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="41486-127">该事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="41486-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="41486-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="41486-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="41486-129">nvarchar (255) 不为空</span><span class="sxs-lookup"><span data-stu-id="41486-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="41486-130">统一资源标识符 (URI) 的通道。</span><span class="sxs-lookup"><span data-stu-id="41486-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="41486-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="41486-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="41486-132">bigint</span><span class="sxs-lookup"><span data-stu-id="41486-132">bigint</span></span>  <br/> |<span data-ttu-id="41486-133">聊天 （对应于 tblChat.chatId 表） 的 ID。</span><span class="sxs-lookup"><span data-stu-id="41486-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="41486-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="41486-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="41486-135">int，不为空</span><span class="sxs-lookup"><span data-stu-id="41486-135">int, not null</span></span>  <br/> |<span data-ttu-id="41486-136">（对应于 tblPrincipal.prinID 表） 的海报的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="41486-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="41486-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="41486-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="41486-138">nvarchar (255) 不为空</span><span class="sxs-lookup"><span data-stu-id="41486-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="41486-139">用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="41486-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="41486-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="41486-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="41486-141">nvarchar （最大）</span><span class="sxs-lookup"><span data-stu-id="41486-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="41486-142">消息 （编码取决于 cmplType）。</span><span class="sxs-lookup"><span data-stu-id="41486-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="41486-143">**密钥**</span><span class="sxs-lookup"><span data-stu-id="41486-143">**Key**</span></span>

|<span data-ttu-id="41486-144">**列**</span><span class="sxs-lookup"><span data-stu-id="41486-144">**Column**</span></span>|<span data-ttu-id="41486-145">**说明**</span><span class="sxs-lookup"><span data-stu-id="41486-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41486-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="41486-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="41486-147">为主键。</span><span class="sxs-lookup"><span data-stu-id="41486-147">Primary key.</span></span>  <br/> |
   

