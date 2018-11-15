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
description: 文件传输视图存储有关对等文件传输会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 97bc5f957192c8a2c6d888f81fce0891aa2b4f75
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531217"
---
# <a name="filetransfers-view"></a><span data-ttu-id="13926-104">FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="13926-104">FileTransfers view</span></span>
 
<span data-ttu-id="13926-105">文件传输视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="13926-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="13926-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="13926-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13926-107">FileTransfers 视图还包含[SessionDetails view](sessiondetails-0.md)中的列的所有中下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="13926-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="13926-108">**列**</span><span class="sxs-lookup"><span data-stu-id="13926-108">**Column**</span></span>|<span data-ttu-id="13926-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="13926-109">**Data Type**</span></span>|<span data-ttu-id="13926-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="13926-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13926-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="13926-111">**FileName**</span></span> <br/> |<span data-ttu-id="13926-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="13926-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="13926-113">传输文件的名称。</span><span class="sxs-lookup"><span data-stu-id="13926-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="13926-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="13926-114">**Cookie**</span></span> <br/> |<span data-ttu-id="13926-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="13926-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="13926-116">用于标识与此关联时每个后续消息。</span><span class="sxs-lookup"><span data-stu-id="13926-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="13926-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="13926-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="13926-118">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="13926-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="13926-119">来区分涉及同一文件名的文件传输的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="13926-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="13926-120">**接受**</span><span class="sxs-lookup"><span data-stu-id="13926-120">**Accept**</span></span> <br/> |<span data-ttu-id="13926-121">bit</span><span class="sxs-lookup"><span data-stu-id="13926-121">bit</span></span>  <br/> |<span data-ttu-id="13926-122">可以是 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="13926-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="13926-123">如果为 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="13926-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="13926-124">**拒绝**</span><span class="sxs-lookup"><span data-stu-id="13926-124">**Reject**</span></span> <br/> |<span data-ttu-id="13926-125">bit</span><span class="sxs-lookup"><span data-stu-id="13926-125">bit</span></span>  <br/> |<span data-ttu-id="13926-126">可以是 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="13926-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="13926-127">如果为 TRUE，接受和取消都将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="13926-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="13926-128">**取消**</span><span class="sxs-lookup"><span data-stu-id="13926-128">**Cancel**</span></span> <br/> |<span data-ttu-id="13926-129">bit</span><span class="sxs-lookup"><span data-stu-id="13926-129">bit</span></span>  <br/> |<span data-ttu-id="13926-130">可以是 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="13926-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="13926-131">如果为 true，则接受和拒绝都将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="13926-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

