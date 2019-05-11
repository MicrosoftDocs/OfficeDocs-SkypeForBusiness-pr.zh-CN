---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含具有合规性适配器尚未处理的合规性事件。
ms.openlocfilehash: 88319da90c1f3e03b6ca3e441259972f51d0bcf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929929"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="fac00-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="fac00-103">tblComplianceData</span></span>
 
<span data-ttu-id="fac00-104">tblComplianceData 包含具有合规性适配器尚未处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="fac00-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="fac00-105">**列**</span><span class="sxs-lookup"><span data-stu-id="fac00-105">**Columns**</span></span>

|<span data-ttu-id="fac00-106">**列**</span><span class="sxs-lookup"><span data-stu-id="fac00-106">**Column**</span></span>|<span data-ttu-id="fac00-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="fac00-107">**Type**</span></span>|<span data-ttu-id="fac00-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="fac00-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fac00-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="fac00-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="fac00-110">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="fac00-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="fac00-111">事件 id。</span><span class="sxs-lookup"><span data-stu-id="fac00-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="fac00-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="fac00-112">entryDate</span></span>  <br/> |<span data-ttu-id="fac00-113">smalldatetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="fac00-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="fac00-114">插入时间 (可能遥远将来对于 cmplType = 9，因为该条目在此情况下是只是一个占位符)。</span><span class="sxs-lookup"><span data-stu-id="fac00-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="fac00-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="fac00-115">cmplType</span></span>  <br/> |<span data-ttu-id="fac00-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="fac00-116">int, not null</span></span>  <br/> | <span data-ttu-id="fac00-117">合规性事件的类型：</span><span class="sxs-lookup"><span data-stu-id="fac00-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="fac00-118">1： 聊天</span><span class="sxs-lookup"><span data-stu-id="fac00-118">1: Chat</span></span> <br/>  <span data-ttu-id="fac00-119">2： 聊天记录</span><span class="sxs-lookup"><span data-stu-id="fac00-119">2: Backchat</span></span> <br/>  <span data-ttu-id="fac00-120">3： 文件下载</span><span class="sxs-lookup"><span data-stu-id="fac00-120">3: File download</span></span> <br/>  <span data-ttu-id="fac00-121">4： 文件上载</span><span class="sxs-lookup"><span data-stu-id="fac00-121">4: File upload</span></span> <br/>  <span data-ttu-id="fac00-122">9： 临时文件传输</span><span class="sxs-lookup"><span data-stu-id="fac00-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="fac00-123">10： 删除聊天 （通过替换）</span><span class="sxs-lookup"><span data-stu-id="fac00-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="fac00-124">11： 清除聊天</span><span class="sxs-lookup"><span data-stu-id="fac00-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="fac00-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="fac00-125">cmplTime</span></span>  <br/> |<span data-ttu-id="fac00-126">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="fac00-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="fac00-127">该事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="fac00-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="fac00-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="fac00-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="fac00-129">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="fac00-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="fac00-130">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="fac00-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="fac00-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="fac00-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="fac00-132">bigint</span><span class="sxs-lookup"><span data-stu-id="fac00-132">bigint</span></span>  <br/> |<span data-ttu-id="fac00-133">聊天 ID （与 tblChat.chatId 表对应）。</span><span class="sxs-lookup"><span data-stu-id="fac00-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="fac00-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="fac00-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="fac00-135">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="fac00-135">int, not null</span></span>  <br/> |<span data-ttu-id="fac00-136">（与 tblPrincipal.prinID 表对应） 的海报的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="fac00-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="fac00-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="fac00-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="fac00-138">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="fac00-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="fac00-139">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="fac00-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="fac00-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="fac00-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="fac00-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="fac00-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="fac00-142">消息 （编码取决于 cmplType）。</span><span class="sxs-lookup"><span data-stu-id="fac00-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="fac00-143">**关键字**</span><span class="sxs-lookup"><span data-stu-id="fac00-143">**Key**</span></span>

|<span data-ttu-id="fac00-144">**列**</span><span class="sxs-lookup"><span data-stu-id="fac00-144">**Column**</span></span>|<span data-ttu-id="fac00-145">**说明**</span><span class="sxs-lookup"><span data-stu-id="fac00-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fac00-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="fac00-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="fac00-147">主键。</span><span class="sxs-lookup"><span data-stu-id="fac00-147">Primary key.</span></span>  <br/> |
   

