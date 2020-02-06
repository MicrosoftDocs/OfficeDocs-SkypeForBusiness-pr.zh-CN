---
title: Media 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每条记录表示对等会话中使用的一种媒体类型。 如果使用多个媒体类型，则表中的多个记录将表示一个会话。
ms.openlocfilehash: b96f1e9fccf2ac3416e505eb19a54a5e227bb01f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815040"
---
# <a name="media-table"></a><span data-ttu-id="1136c-104">Media 表</span><span class="sxs-lookup"><span data-stu-id="1136c-104">Media table</span></span>
 
<span data-ttu-id="1136c-105">每条记录表示对等会话中使用的一种媒体类型。</span><span class="sxs-lookup"><span data-stu-id="1136c-105">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="1136c-106">如果使用多个媒体类型，则表中的多个记录将表示一个会话。</span><span class="sxs-lookup"><span data-stu-id="1136c-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1136c-107">不应使用 Media 表计算会话的媒体持续时间。</span><span class="sxs-lookup"><span data-stu-id="1136c-107">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="1136c-108">此表包含会话中媒体交换的信号详细信息。</span><span class="sxs-lookup"><span data-stu-id="1136c-108">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="1136c-109">媒体交换由邀请请求完成，并且 StartTime 指示发送邀请的时间。邀请时间不一定表示媒体开始时间，因为媒体仅在 sessionee 接受会话后才开始。</span><span class="sxs-lookup"><span data-stu-id="1136c-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="1136c-110">"结束时间" 通常表示本次会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="1136c-110">The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="1136c-111">**列**</span><span class="sxs-lookup"><span data-stu-id="1136c-111">**Column**</span></span>|<span data-ttu-id="1136c-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1136c-112">**Data Type**</span></span>|<span data-ttu-id="1136c-113">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="1136c-113">**Key/Index**</span></span>|<span data-ttu-id="1136c-114">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="1136c-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1136c-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="1136c-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="1136c-116">datetime</span><span class="sxs-lookup"><span data-stu-id="1136c-116">datetime</span></span>  <br/> |<span data-ttu-id="1136c-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="1136c-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1136c-118">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="1136c-118">Time of session request.</span></span> <span data-ttu-id="1136c-119">与**SessionIdSeq**结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="1136c-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="1136c-120">有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。</span><span class="sxs-lookup"><span data-stu-id="1136c-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1136c-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="1136c-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="1136c-122">int</span><span class="sxs-lookup"><span data-stu-id="1136c-122">int</span></span>  <br/> |<span data-ttu-id="1136c-123">主、外部</span><span class="sxs-lookup"><span data-stu-id="1136c-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1136c-124">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1136c-124">ID number to identify the session.</span></span> <span data-ttu-id="1136c-125">与**SessionIdTime**结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="1136c-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="1136c-126">有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。</span><span class="sxs-lookup"><span data-stu-id="1136c-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1136c-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="1136c-127">**MediaId**</span></span> <br/> |<span data-ttu-id="1136c-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="1136c-128">tinyint</span></span>  <br/> |<span data-ttu-id="1136c-129">主、外部</span><span class="sxs-lookup"><span data-stu-id="1136c-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1136c-130">标识此媒体类型的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="1136c-130">Unique number identifying this media type.</span></span> <span data-ttu-id="1136c-131">有关详细信息，请参阅[MediaList 表](medialist.md)。</span><span class="sxs-lookup"><span data-stu-id="1136c-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1136c-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="1136c-132">**StartTime**</span></span> <br/> |<span data-ttu-id="1136c-133">datetime</span><span class="sxs-lookup"><span data-stu-id="1136c-133">datetime</span></span>  <br/> |<span data-ttu-id="1136c-134">Primary</span><span class="sxs-lookup"><span data-stu-id="1136c-134">Primary</span></span>  <br/> |<span data-ttu-id="1136c-135">这是发送媒体请求的时间，而不是真正的媒体开始时间。</span><span class="sxs-lookup"><span data-stu-id="1136c-135">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="1136c-136">**StartTime**包括会话设置时间。</span><span class="sxs-lookup"><span data-stu-id="1136c-136">**StartTime** includes the session setup time.</span></span> <br/> |
|<span data-ttu-id="1136c-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="1136c-137">**EndTime**</span></span> <br/> |<span data-ttu-id="1136c-138">datetime</span><span class="sxs-lookup"><span data-stu-id="1136c-138">datetime</span></span>  <br/> ||<span data-ttu-id="1136c-139">这是会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="1136c-139">This is the end time of the session.</span></span>  <br/> |
   

