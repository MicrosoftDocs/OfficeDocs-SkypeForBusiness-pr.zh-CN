---
title: Media 表
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每条记录表示一个用于点对点会话的媒体类型。如果使用多个媒体类型，则一个会话由表中的多条记录表示。
ms.openlocfilehash: ce5b5a2b312307e608367279e4e871ed03063860
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800102"
---
# <a name="media-table"></a><span data-ttu-id="76430-104">Media 表</span><span class="sxs-lookup"><span data-stu-id="76430-104">Media table</span></span>
 
<span data-ttu-id="76430-p102">每条记录表示一个用于点对点会话的媒体类型。如果使用多个媒体类型，则一个会话由表中的多条记录表示。</span><span class="sxs-lookup"><span data-stu-id="76430-p102">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76430-p103">不应使用媒体表计算会话的媒体持续时间。该表包含会话中的媒体交换信号详情。媒体交换通过 INVITE 请求实现，StartTime 指示发出 INVITE 的时间。邀请时间不一定表示媒体的启动时间，因为仅在会话接收方接受会话后，媒体才启动。EndTime 通常表示该会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="76430-p103">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="76430-111">**列**</span><span class="sxs-lookup"><span data-stu-id="76430-111">**Column**</span></span>|<span data-ttu-id="76430-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="76430-112">**Data Type**</span></span>|<span data-ttu-id="76430-113">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="76430-113">**Key/Index**</span></span>|<span data-ttu-id="76430-114">**Details**</span><span class="sxs-lookup"><span data-stu-id="76430-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76430-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="76430-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="76430-116">datetime</span><span class="sxs-lookup"><span data-stu-id="76430-116">datetime</span></span>  <br/> |<span data-ttu-id="76430-117">主、外</span><span class="sxs-lookup"><span data-stu-id="76430-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="76430-118">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="76430-118">Time of session request.</span></span> <span data-ttu-id="76430-119">与 **SessionIdSeq** 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="76430-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="76430-120">有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。</span><span class="sxs-lookup"><span data-stu-id="76430-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="76430-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="76430-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="76430-122">int</span><span class="sxs-lookup"><span data-stu-id="76430-122">int</span></span>  <br/> |<span data-ttu-id="76430-123">主、外</span><span class="sxs-lookup"><span data-stu-id="76430-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="76430-124">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="76430-124">ID number to identify the session.</span></span> <span data-ttu-id="76430-125">与 **SessionIdTime** 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="76430-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="76430-126">有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。</span><span class="sxs-lookup"><span data-stu-id="76430-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="76430-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="76430-127">**MediaId**</span></span> <br/> |<span data-ttu-id="76430-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="76430-128">tinyint</span></span>  <br/> |<span data-ttu-id="76430-129">主、外</span><span class="sxs-lookup"><span data-stu-id="76430-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="76430-130">标识媒体类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="76430-130">Unique number identifying this media type.</span></span> <span data-ttu-id="76430-131">有关详细信息， [请参阅 MediaList](medialist.md) 表。</span><span class="sxs-lookup"><span data-stu-id="76430-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="76430-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="76430-132">**StartTime**</span></span> <br/> |<span data-ttu-id="76430-133">datetime</span><span class="sxs-lookup"><span data-stu-id="76430-133">datetime</span></span>  <br/> |<span data-ttu-id="76430-134">主</span><span class="sxs-lookup"><span data-stu-id="76430-134">Primary</span></span>  <br/> |<span data-ttu-id="76430-p107">这是发出媒体请求的时间，而不是实际的媒体启动时间。**StartTime** 包括会话建立时间。</span><span class="sxs-lookup"><span data-stu-id="76430-p107">This is the time that a media request was sent out, not the real media start time. **StartTime** includes the session setup time. </span></span><br/> |
|<span data-ttu-id="76430-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="76430-137">**EndTime**</span></span> <br/> |<span data-ttu-id="76430-138">datetime</span><span class="sxs-lookup"><span data-stu-id="76430-138">datetime</span></span>  <br/> ||<span data-ttu-id="76430-139">这是会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="76430-139">This is the end time of the session.</span></span>  <br/> |
   

