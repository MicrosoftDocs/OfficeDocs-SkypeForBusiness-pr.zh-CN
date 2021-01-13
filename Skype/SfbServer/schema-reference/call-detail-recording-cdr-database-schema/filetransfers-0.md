---
title: Skype for Business Server 2015 中的 FileTransfers 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每条记录代表一个文件传输会话。
ms.openlocfilehash: fde871bb434a2aa458bc59cfdf098c82ba3a7093
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821692"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="80f1b-103">Skype for Business Server 2015 中的 FileTransfers 表</span><span class="sxs-lookup"><span data-stu-id="80f1b-103">FileTransfers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="80f1b-104">每条记录代表一个文件传输会话。</span><span class="sxs-lookup"><span data-stu-id="80f1b-104">Each record represents one file transfer session.</span></span>
  
|<span data-ttu-id="80f1b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="80f1b-105">**Column**</span></span>|<span data-ttu-id="80f1b-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="80f1b-106">**Data Type**</span></span>|<span data-ttu-id="80f1b-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="80f1b-107">**Key/Index**</span></span>|<span data-ttu-id="80f1b-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="80f1b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80f1b-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="80f1b-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="80f1b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="80f1b-110">datetime</span></span>  <br/> |<span data-ttu-id="80f1b-111">主、外</span><span class="sxs-lookup"><span data-stu-id="80f1b-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="80f1b-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="80f1b-112">Time of session request.</span></span> <span data-ttu-id="80f1b-113">与 **SessionIdSeq** 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="80f1b-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="80f1b-114">有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。</span><span class="sxs-lookup"><span data-stu-id="80f1b-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="80f1b-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="80f1b-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="80f1b-116">int</span><span class="sxs-lookup"><span data-stu-id="80f1b-116">int</span></span>  <br/> |<span data-ttu-id="80f1b-117">主、外</span><span class="sxs-lookup"><span data-stu-id="80f1b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="80f1b-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="80f1b-118">ID number to identify the session.</span></span> <span data-ttu-id="80f1b-119">与 **SessionIdTime** 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="80f1b-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="80f1b-120">有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。</span><span class="sxs-lookup"><span data-stu-id="80f1b-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="80f1b-121">**File Name**</span><span class="sxs-lookup"><span data-stu-id="80f1b-121">**File Name**</span></span> <br/> |<span data-ttu-id="80f1b-122">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="80f1b-122">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="80f1b-123">文件的名称。</span><span class="sxs-lookup"><span data-stu-id="80f1b-123">Name of the file.</span></span>  <br/> |
|<span data-ttu-id="80f1b-124">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="80f1b-124">**FileIdentity**</span></span> <br/> |<span data-ttu-id="80f1b-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="80f1b-125">uniqueidentifier</span></span>  <br/> ||<span data-ttu-id="80f1b-126">用于区分涉及同一文件名的各个文件传输的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="80f1b-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="80f1b-127">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="80f1b-127">**Cookie**</span></span> <br/> |<span data-ttu-id="80f1b-128">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="80f1b-128">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="80f1b-129">主</span><span class="sxs-lookup"><span data-stu-id="80f1b-129">Primary</span></span>  <br/> |<span data-ttu-id="80f1b-130">用于标识与此关联时的每条后续消息。</span><span class="sxs-lookup"><span data-stu-id="80f1b-130">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="80f1b-131">**Accept**</span><span class="sxs-lookup"><span data-stu-id="80f1b-131">**Accept**</span></span> <br/> |<span data-ttu-id="80f1b-132">bit</span><span class="sxs-lookup"><span data-stu-id="80f1b-132">bit</span></span>  <br/> ||<span data-ttu-id="80f1b-p103">可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="80f1b-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="80f1b-135">**Reject**</span><span class="sxs-lookup"><span data-stu-id="80f1b-135">**Reject**</span></span> <br/> |<span data-ttu-id="80f1b-136">bit</span><span class="sxs-lookup"><span data-stu-id="80f1b-136">bit</span></span>  <br/> ||<span data-ttu-id="80f1b-p104">可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="80f1b-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="80f1b-139">**Cancel**</span><span class="sxs-lookup"><span data-stu-id="80f1b-139">**Cancel**</span></span> <br/> |<span data-ttu-id="80f1b-140">bit</span><span class="sxs-lookup"><span data-stu-id="80f1b-140">bit</span></span>  <br/> ||<span data-ttu-id="80f1b-p105">可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="80f1b-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
|<span data-ttu-id="80f1b-143">**LastModifiedTime**</span><span class="sxs-lookup"><span data-stu-id="80f1b-143">**LastModifiedTime**</span></span> <br/> |<span data-ttu-id="80f1b-144">Datetime</span><span class="sxs-lookup"><span data-stu-id="80f1b-144">Datetime</span></span>  <br/> ||<span data-ttu-id="80f1b-145">供监控服务内部使用。</span><span class="sxs-lookup"><span data-stu-id="80f1b-145">For internal use by the Monitoring service.</span></span>  <br/> <span data-ttu-id="80f1b-146">此字段在 Skype for Business Server 2015 中引入。</span><span class="sxs-lookup"><span data-stu-id="80f1b-146">This field was introduced in Skype for Business Server 2015.</span></span>  <br/> |
   

