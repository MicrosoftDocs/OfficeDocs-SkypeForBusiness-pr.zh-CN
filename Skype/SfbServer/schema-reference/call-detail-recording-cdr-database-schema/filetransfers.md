---
title: FileTransfers 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTranfer 视图存储有关对等文件传输会话信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 69b986c24a3a8f3646738eb3e1e3e97794be8e9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-view"></a><span data-ttu-id="34273-104">FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="34273-104">FileTransfers view</span></span>
 
<span data-ttu-id="34273-105">FileTranfer 视图存储有关对等文件传输会话信息。</span><span class="sxs-lookup"><span data-stu-id="34273-105">The FileTranfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="34273-106">在 Microsoft Lync Server 2013 引入了此视图。</span><span class="sxs-lookup"><span data-stu-id="34273-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34273-107">FileTransfers 视图它包含[SessionDetails 视图](sessiondetails-0.md)中的列的所有除了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="34273-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="34273-108">**列**</span><span class="sxs-lookup"><span data-stu-id="34273-108">**Column**</span></span>|<span data-ttu-id="34273-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="34273-109">**Data Type**</span></span>|<span data-ttu-id="34273-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="34273-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34273-111">**文件名**</span><span class="sxs-lookup"><span data-stu-id="34273-111">**FileName**</span></span> <br/> |<span data-ttu-id="34273-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34273-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="34273-113">传输的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="34273-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="34273-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="34273-114">**Cookie**</span></span> <br/> |<span data-ttu-id="34273-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="34273-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="34273-116">用来标识每个后续消息作为与此相关联。</span><span class="sxs-lookup"><span data-stu-id="34273-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="34273-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="34273-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="34273-118">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="34273-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="34273-119">若要区分涉及文件名称相同的文件传输的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="34273-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="34273-120">**接受**</span><span class="sxs-lookup"><span data-stu-id="34273-120">**Accept**</span></span> <br/> |<span data-ttu-id="34273-121">bit</span><span class="sxs-lookup"><span data-stu-id="34273-121">bit</span></span>  <br/> |<span data-ttu-id="34273-122">可以为真或为空。</span><span class="sxs-lookup"><span data-stu-id="34273-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="34273-123">如果为 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="34273-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="34273-124">**拒绝**</span><span class="sxs-lookup"><span data-stu-id="34273-124">**Reject**</span></span> <br/> |<span data-ttu-id="34273-125">bit</span><span class="sxs-lookup"><span data-stu-id="34273-125">bit</span></span>  <br/> |<span data-ttu-id="34273-126">可以为真或为空。</span><span class="sxs-lookup"><span data-stu-id="34273-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="34273-127">如果为 TRUE，则接受和取消将空值。</span><span class="sxs-lookup"><span data-stu-id="34273-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="34273-128">**取消**</span><span class="sxs-lookup"><span data-stu-id="34273-128">**Cancel**</span></span> <br/> |<span data-ttu-id="34273-129">bit</span><span class="sxs-lookup"><span data-stu-id="34273-129">bit</span></span>  <br/> |<span data-ttu-id="34273-130">可以为真或为空。</span><span class="sxs-lookup"><span data-stu-id="34273-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="34273-131">如果为 TRUE，接受和拒绝都将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="34273-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

