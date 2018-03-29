---
title: Media 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每个记录表示的对等会话中使用的一种媒体类型。 如果使用多个媒体类型，将可以由多个记录在表中，表示一个会话。
ms.openlocfilehash: 8833e7272c82dcbb7eef0da89d915680198589b5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="media-table"></a><span data-ttu-id="e6cd1-104">Media 表</span><span class="sxs-lookup"><span data-stu-id="e6cd1-104">Media table</span></span>
 
<span data-ttu-id="e6cd1-105">每个记录表示的对等会话中使用的一种媒体类型。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-105">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="e6cd1-106">如果使用多个媒体类型，将可以由多个记录在表中，表示一个会话。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6cd1-107">媒体表不应该用于计算会话的媒体持续时间。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-107">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="e6cd1-108">此表包含媒体交换会话中信号传输的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-108">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="e6cd1-109">媒体交换通过 INVITE 请求，并开始时间指示已发出邀请的时间。邀请的时间并不意味着媒体开始时，因为媒体开始 sessionee 接受会话后才。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="e6cd1-110">结束时间通常意味着此会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-110">The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="e6cd1-111">**列**</span><span class="sxs-lookup"><span data-stu-id="e6cd1-111">**Column**</span></span>|<span data-ttu-id="e6cd1-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e6cd1-112">**Data Type**</span></span>|<span data-ttu-id="e6cd1-113">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="e6cd1-113">**Key/Index**</span></span>|<span data-ttu-id="e6cd1-114">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e6cd1-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6cd1-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="e6cd1-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="e6cd1-116">datetime</span><span class="sxs-lookup"><span data-stu-id="e6cd1-116">datetime</span></span>  <br/> |<span data-ttu-id="e6cd1-117">主键和外</span><span class="sxs-lookup"><span data-stu-id="e6cd1-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e6cd1-118">会议请求的时间。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-118">Time of session request.</span></span> <span data-ttu-id="e6cd1-119">与**SessionIdSeq**配合使用，以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="e6cd1-120">[对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e6cd1-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="e6cd1-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="e6cd1-122">int</span><span class="sxs-lookup"><span data-stu-id="e6cd1-122">int</span></span>  <br/> |<span data-ttu-id="e6cd1-123">主键和外</span><span class="sxs-lookup"><span data-stu-id="e6cd1-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e6cd1-124">以标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-124">ID number to identify the session.</span></span> <span data-ttu-id="e6cd1-125">与**SessionIdTime**配合使用，以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="e6cd1-126">[对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e6cd1-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="e6cd1-127">**MediaId**</span></span> <br/> |<span data-ttu-id="e6cd1-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6cd1-128">tinyint</span></span>  <br/> |<span data-ttu-id="e6cd1-129">主键和外</span><span class="sxs-lookup"><span data-stu-id="e6cd1-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e6cd1-130">标识此媒体类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-130">Unique number identifying this media type.</span></span> <span data-ttu-id="e6cd1-131">[MediaList 表](medialist.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e6cd1-132">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="e6cd1-132">**StartTime**</span></span> <br/> |<span data-ttu-id="e6cd1-133">datetime</span><span class="sxs-lookup"><span data-stu-id="e6cd1-133">datetime</span></span>  <br/> |<span data-ttu-id="e6cd1-134">Primary</span><span class="sxs-lookup"><span data-stu-id="e6cd1-134">Primary</span></span>  <br/> |<span data-ttu-id="e6cd1-135">这是媒体请求被发送出去的时间，不实的媒体开始时间。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-135">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="e6cd1-136">**开始时间**包括会话设置时间。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-136">**StartTime** includes the session setup time.</span></span> <br/> |
|<span data-ttu-id="e6cd1-137">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="e6cd1-137">**EndTime**</span></span> <br/> |<span data-ttu-id="e6cd1-138">datetime</span><span class="sxs-lookup"><span data-stu-id="e6cd1-138">datetime</span></span>  <br/> ||<span data-ttu-id="e6cd1-139">这是会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e6cd1-139">This is the end time of the session.</span></span>  <br/> |
   

