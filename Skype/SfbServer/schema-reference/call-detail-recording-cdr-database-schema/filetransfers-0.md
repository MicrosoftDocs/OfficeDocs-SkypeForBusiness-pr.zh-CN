---
title: Skype for Business Server 2015 中的 FileTransfers 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每条记录表示一个文件传输会话。
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815210"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3e35a-103">Skype for Business Server 2015 中的 FileTransfers 表</span><span class="sxs-lookup"><span data-stu-id="3e35a-103">FileTransfers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3e35a-104">每条记录表示一个文件传输会话。</span><span class="sxs-lookup"><span data-stu-id="3e35a-104">Each record represents one file transfer session.</span></span>
  
|<span data-ttu-id="3e35a-105">**列**</span><span class="sxs-lookup"><span data-stu-id="3e35a-105">**Column**</span></span>|<span data-ttu-id="3e35a-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3e35a-106">**Data Type**</span></span>|<span data-ttu-id="3e35a-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="3e35a-107">**Key/Index**</span></span>|<span data-ttu-id="3e35a-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="3e35a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3e35a-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="3e35a-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="3e35a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="3e35a-110">datetime</span></span>  <br/> |<span data-ttu-id="3e35a-111">主、外部</span><span class="sxs-lookup"><span data-stu-id="3e35a-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3e35a-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="3e35a-112">Time of session request.</span></span> <span data-ttu-id="3e35a-113">与**SessionIdSeq**结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="3e35a-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="3e35a-114">有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。</span><span class="sxs-lookup"><span data-stu-id="3e35a-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3e35a-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="3e35a-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="3e35a-116">int</span><span class="sxs-lookup"><span data-stu-id="3e35a-116">int</span></span>  <br/> |<span data-ttu-id="3e35a-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="3e35a-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3e35a-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="3e35a-118">ID number to identify the session.</span></span> <span data-ttu-id="3e35a-119">与**SessionIdTime**结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="3e35a-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="3e35a-120">有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。</span><span class="sxs-lookup"><span data-stu-id="3e35a-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3e35a-121">**文件名**</span><span class="sxs-lookup"><span data-stu-id="3e35a-121">**File Name**</span></span> <br/> |<span data-ttu-id="3e35a-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3e35a-122">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="3e35a-123">文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3e35a-123">Name of the file.</span></span>  <br/> |
|<span data-ttu-id="3e35a-124">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="3e35a-124">**FileIdentity**</span></span> <br/> |<span data-ttu-id="3e35a-125">标识符</span><span class="sxs-lookup"><span data-stu-id="3e35a-125">uniqueidentifier</span></span>  <br/> ||<span data-ttu-id="3e35a-126">唯一标识符，用于区分涉及相同文件名的文件传输。</span><span class="sxs-lookup"><span data-stu-id="3e35a-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="3e35a-127">**票证**</span><span class="sxs-lookup"><span data-stu-id="3e35a-127">**Cookie**</span></span> <br/> |<span data-ttu-id="3e35a-128">nvarchar</span><span class="sxs-lookup"><span data-stu-id="3e35a-128">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="3e35a-129">Primary</span><span class="sxs-lookup"><span data-stu-id="3e35a-129">Primary</span></span>  <br/> |<span data-ttu-id="3e35a-130">用于标识要与此邮件关联的每个后续消息。</span><span class="sxs-lookup"><span data-stu-id="3e35a-130">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="3e35a-131">**容纳**</span><span class="sxs-lookup"><span data-stu-id="3e35a-131">**Accept**</span></span> <br/> |<span data-ttu-id="3e35a-132">bit</span><span class="sxs-lookup"><span data-stu-id="3e35a-132">bit</span></span>  <br/> ||<span data-ttu-id="3e35a-133">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="3e35a-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="3e35a-134">如果为 TRUE，则 "拒绝" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3e35a-134">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="3e35a-135">**&**</span><span class="sxs-lookup"><span data-stu-id="3e35a-135">**Reject**</span></span> <br/> |<span data-ttu-id="3e35a-136">bit</span><span class="sxs-lookup"><span data-stu-id="3e35a-136">bit</span></span>  <br/> ||<span data-ttu-id="3e35a-137">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="3e35a-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="3e35a-138">如果为 TRUE，则 "接受" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3e35a-138">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="3e35a-139">**取消**</span><span class="sxs-lookup"><span data-stu-id="3e35a-139">**Cancel**</span></span> <br/> |<span data-ttu-id="3e35a-140">bit</span><span class="sxs-lookup"><span data-stu-id="3e35a-140">bit</span></span>  <br/> ||<span data-ttu-id="3e35a-141">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="3e35a-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="3e35a-142">如果为 TRUE，则 "接受" 和 "拒绝" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3e35a-142">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
|<span data-ttu-id="3e35a-143">**LastModifiedTime**</span><span class="sxs-lookup"><span data-stu-id="3e35a-143">**LastModifiedTime**</span></span> <br/> |<span data-ttu-id="3e35a-144">从中</span><span class="sxs-lookup"><span data-stu-id="3e35a-144">Datetime</span></span>  <br/> ||<span data-ttu-id="3e35a-145">供监视服务内部使用。</span><span class="sxs-lookup"><span data-stu-id="3e35a-145">For internal use by the Monitoring service.</span></span>  <br/> <span data-ttu-id="3e35a-146">此字段是在 Skype for Business Server 2015 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3e35a-146">This field was introduced in Skype for Business Server 2015.</span></span>  <br/> |
   

