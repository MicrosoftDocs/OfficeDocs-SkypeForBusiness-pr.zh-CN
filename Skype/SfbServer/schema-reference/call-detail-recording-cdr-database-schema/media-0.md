---
title: 媒体视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒体视图存储信息的对等会话中使用的一种媒体类型。 如果使用多个媒体类型，将可以由多个记录在表中，表示一个会话。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 0cbcb353ec768b9d3ee66f1a10d59b5c4523acea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="media-view"></a><span data-ttu-id="d6999-105">媒体视图</span><span class="sxs-lookup"><span data-stu-id="d6999-105">Media view</span></span>
 
<span data-ttu-id="d6999-106">媒体视图存储信息的对等会话中使用的一种媒体类型。</span><span class="sxs-lookup"><span data-stu-id="d6999-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="d6999-107">如果使用多个媒体类型，将可以由多个记录在表中，表示一个会话。</span><span class="sxs-lookup"><span data-stu-id="d6999-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="d6999-108">在 Microsoft Lync Server 2013 引入了此视图。</span><span class="sxs-lookup"><span data-stu-id="d6999-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6999-109">媒体视图不应该用于计算会话的媒体持续时间。</span><span class="sxs-lookup"><span data-stu-id="d6999-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="d6999-110">该视图包含媒体交换会话中信号传输的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="d6999-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="d6999-111">媒体交换通过 INVITE 请求，并开始时间指示已发出邀请的时间。邀请时间并不意味着媒体开始时间，因为媒体开始仅在会话被接受后。</span><span class="sxs-lookup"><span data-stu-id="d6999-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="d6999-112">媒体视图它包含[SessionDetails 视图](sessiondetails-0.md)中的列的所有除了下面列出的。</span><span class="sxs-lookup"><span data-stu-id="d6999-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="d6999-113">**列**</span><span class="sxs-lookup"><span data-stu-id="d6999-113">**Column**</span></span>|<span data-ttu-id="d6999-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d6999-114">**Data Type**</span></span>|<span data-ttu-id="d6999-115">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d6999-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6999-116">**媒体**</span><span class="sxs-lookup"><span data-stu-id="d6999-116">**Media**</span></span> <br/> |<span data-ttu-id="d6999-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6999-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6999-118">媒体类型。</span><span class="sxs-lookup"><span data-stu-id="d6999-118">Media type.</span></span> <span data-ttu-id="d6999-119">[MediaList 表](medialist.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="d6999-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d6999-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="d6999-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="d6999-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d6999-121">datetime</span></span>  <br/> |<span data-ttu-id="d6999-122">已发出介质请求的时间。</span><span class="sxs-lookup"><span data-stu-id="d6999-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="d6999-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="d6999-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="d6999-124">datetime</span><span class="sxs-lookup"><span data-stu-id="d6999-124">datetime</span></span>  <br/> |<span data-ttu-id="d6999-125">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="d6999-125">End time of the session.</span></span>  <br/> |
   

