---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含合规适配器尚未处理的合规事件。
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809852"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="3993a-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="3993a-103">tblComplianceData</span></span>
 
<span data-ttu-id="3993a-104">tblComplianceData 包含合规适配器尚未处理的合规事件。</span><span class="sxs-lookup"><span data-stu-id="3993a-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="3993a-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="3993a-105">**Columns**</span></span>

|<span data-ttu-id="3993a-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3993a-106">**Column**</span></span>|<span data-ttu-id="3993a-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="3993a-107">**Type**</span></span>|<span data-ttu-id="3993a-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="3993a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3993a-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="3993a-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="3993a-110">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="3993a-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="3993a-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="3993a-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="3993a-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="3993a-112">entryDate</span></span>  <br/> |<span data-ttu-id="3993a-113">smalldatetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="3993a-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="3993a-114">插入时间（将来对于 cmplType=9，可能比较遥远，因为该条目在那种情况下只是一个占位符）。</span><span class="sxs-lookup"><span data-stu-id="3993a-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="3993a-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="3993a-115">cmplType</span></span>  <br/> |<span data-ttu-id="3993a-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="3993a-116">int, not null</span></span>  <br/> | <span data-ttu-id="3993a-117">合规事件的类型：</span><span class="sxs-lookup"><span data-stu-id="3993a-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="3993a-118">1：聊天</span><span class="sxs-lookup"><span data-stu-id="3993a-118">1: Chat</span></span> <br/>  <span data-ttu-id="3993a-119">2：聊天记录</span><span class="sxs-lookup"><span data-stu-id="3993a-119">2: Backchat</span></span> <br/>  <span data-ttu-id="3993a-120">3：文件下载</span><span class="sxs-lookup"><span data-stu-id="3993a-120">3: File download</span></span> <br/>  <span data-ttu-id="3993a-121">4：文件上载</span><span class="sxs-lookup"><span data-stu-id="3993a-121">4: File upload</span></span> <br/>  <span data-ttu-id="3993a-122">9：临时文件传输</span><span class="sxs-lookup"><span data-stu-id="3993a-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="3993a-123">10：删除聊天（通过替换）</span><span class="sxs-lookup"><span data-stu-id="3993a-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="3993a-124">11：清除聊天</span><span class="sxs-lookup"><span data-stu-id="3993a-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="3993a-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="3993a-125">cmplTime</span></span>  <br/> |<span data-ttu-id="3993a-126">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="3993a-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="3993a-127">事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="3993a-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="3993a-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="3993a-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="3993a-129">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="3993a-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3993a-130">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="3993a-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="3993a-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="3993a-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="3993a-132">bigint</span><span class="sxs-lookup"><span data-stu-id="3993a-132">bigint</span></span>  <br/> |<span data-ttu-id="3993a-133">聊天 ID（与 tblChat.chatId 表对应）。</span><span class="sxs-lookup"><span data-stu-id="3993a-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="3993a-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="3993a-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="3993a-135">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="3993a-135">int, not null</span></span>  <br/> |<span data-ttu-id="3993a-136">发布人的主体 ID（与 tblPrincipal.prinID 表对应）。</span><span class="sxs-lookup"><span data-stu-id="3993a-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="3993a-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="3993a-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="3993a-138">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="3993a-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3993a-139">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="3993a-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="3993a-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="3993a-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="3993a-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="3993a-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="3993a-142">消息（编码方式取决于 cmplType）。</span><span class="sxs-lookup"><span data-stu-id="3993a-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="3993a-143">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="3993a-143">**Key**</span></span>

|<span data-ttu-id="3993a-144">**列**</span><span class="sxs-lookup"><span data-stu-id="3993a-144">**Column**</span></span>|<span data-ttu-id="3993a-145">**说明**</span><span class="sxs-lookup"><span data-stu-id="3993a-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3993a-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="3993a-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="3993a-147">主键。</span><span class="sxs-lookup"><span data-stu-id="3993a-147">Primary key.</span></span>  <br/> |
   

