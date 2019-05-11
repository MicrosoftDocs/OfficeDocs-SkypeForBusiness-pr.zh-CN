---
title: Media 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每条记录代表一个的对等会话中使用的媒体类型。 将由多个记录在表中，表示一个会话，如果使用多个媒体类型。
ms.openlocfilehash: 76441c350241415aacac150e1e5dec2638302075
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930642"
---
# <a name="media-table"></a><span data-ttu-id="71a2f-104">Media 表</span><span class="sxs-lookup"><span data-stu-id="71a2f-104">Media table</span></span>
 
<span data-ttu-id="71a2f-105">每条记录代表一个的对等会话中使用的媒体类型。</span><span class="sxs-lookup"><span data-stu-id="71a2f-105">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="71a2f-106">将由多个记录在表中，表示一个会话，如果使用多个媒体类型。</span><span class="sxs-lookup"><span data-stu-id="71a2f-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71a2f-107">Media 表不应用于计算会话的媒体持续时间。</span><span class="sxs-lookup"><span data-stu-id="71a2f-107">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="71a2f-108">此表包含会话中的媒体交换的信号详细信息。</span><span class="sxs-lookup"><span data-stu-id="71a2f-108">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="71a2f-109">媒体交换通过 INVITE 请求，并 StartTime 指示邀请已发送的时间。邀请时间不一定意味着媒体开始时间，因为媒体开始仅后 sessionee 接受会话。</span><span class="sxs-lookup"><span data-stu-id="71a2f-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="71a2f-110">EndTime 通常意味着此会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="71a2f-110">The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="71a2f-111">**列**</span><span class="sxs-lookup"><span data-stu-id="71a2f-111">**Column**</span></span>|<span data-ttu-id="71a2f-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="71a2f-112">**Data Type**</span></span>|<span data-ttu-id="71a2f-113">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="71a2f-113">**Key/Index**</span></span>|<span data-ttu-id="71a2f-114">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="71a2f-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71a2f-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="71a2f-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="71a2f-116">datetime</span><span class="sxs-lookup"><span data-stu-id="71a2f-116">datetime</span></span>  <br/> |<span data-ttu-id="71a2f-117">主、 外</span><span class="sxs-lookup"><span data-stu-id="71a2f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="71a2f-118">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="71a2f-118">Time of session request.</span></span> <span data-ttu-id="71a2f-119">与**SessionIdSeq**结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="71a2f-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="71a2f-120">[Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="71a2f-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="71a2f-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="71a2f-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="71a2f-122">int</span><span class="sxs-lookup"><span data-stu-id="71a2f-122">int</span></span>  <br/> |<span data-ttu-id="71a2f-123">主、 外</span><span class="sxs-lookup"><span data-stu-id="71a2f-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="71a2f-124">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="71a2f-124">ID number to identify the session.</span></span> <span data-ttu-id="71a2f-125">与**SessionIdTime**结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="71a2f-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="71a2f-126">[Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="71a2f-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="71a2f-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="71a2f-127">**MediaId**</span></span> <br/> |<span data-ttu-id="71a2f-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="71a2f-128">tinyint</span></span>  <br/> |<span data-ttu-id="71a2f-129">主、 外</span><span class="sxs-lookup"><span data-stu-id="71a2f-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="71a2f-130">标识此媒体类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="71a2f-130">Unique number identifying this media type.</span></span> <span data-ttu-id="71a2f-131">请参阅[MediaList 表](medialist.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71a2f-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="71a2f-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="71a2f-132">**StartTime**</span></span> <br/> |<span data-ttu-id="71a2f-133">datetime</span><span class="sxs-lookup"><span data-stu-id="71a2f-133">datetime</span></span>  <br/> |<span data-ttu-id="71a2f-134">Primary</span><span class="sxs-lookup"><span data-stu-id="71a2f-134">Primary</span></span>  <br/> |<span data-ttu-id="71a2f-135">这是出发送媒体请求的时间，不是实际的媒体开始时间。</span><span class="sxs-lookup"><span data-stu-id="71a2f-135">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="71a2f-136">**StartTime**包括会话建立时间。</span><span class="sxs-lookup"><span data-stu-id="71a2f-136">**StartTime** includes the session setup time.</span></span> <br/> |
|<span data-ttu-id="71a2f-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="71a2f-137">**EndTime**</span></span> <br/> |<span data-ttu-id="71a2f-138">datetime</span><span class="sxs-lookup"><span data-stu-id="71a2f-138">datetime</span></span>  <br/> ||<span data-ttu-id="71a2f-139">这是会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="71a2f-139">This is the end time of the session.</span></span>  <br/> |
   

