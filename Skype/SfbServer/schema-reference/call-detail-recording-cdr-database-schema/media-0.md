---
title: 媒体视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒体视图存储对等会话中使用的一种媒体类型的相关信息。 如果使用多个媒体类型, 则表中的多个记录将表示一个会话。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295998"
---
# <a name="media-view"></a><span data-ttu-id="dc372-105">媒体视图</span><span class="sxs-lookup"><span data-stu-id="dc372-105">Media view</span></span>
 
<span data-ttu-id="dc372-106">媒体视图存储对等会话中使用的一种媒体类型的相关信息。</span><span class="sxs-lookup"><span data-stu-id="dc372-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="dc372-107">如果使用多个媒体类型, 则表中的多个记录将表示一个会话。</span><span class="sxs-lookup"><span data-stu-id="dc372-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="dc372-108">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="dc372-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc372-109">不应使用 "媒体" 视图计算会话的媒体持续时间。</span><span class="sxs-lookup"><span data-stu-id="dc372-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="dc372-110">此视图包含会话中媒体交换的信号详细信息。</span><span class="sxs-lookup"><span data-stu-id="dc372-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="dc372-111">媒体交换由邀请请求完成, 并且 StartTime 指示发送邀请的时间。邀请时间不一定意味着媒体开始时间, 因为媒体仅在接受会话后才开始。</span><span class="sxs-lookup"><span data-stu-id="dc372-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="dc372-112">"媒体" 视图包含 " [SessionDetails" 视图](sessiondetails-0.md)中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="dc372-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="dc372-113">**列**</span><span class="sxs-lookup"><span data-stu-id="dc372-113">**Column**</span></span>|<span data-ttu-id="dc372-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="dc372-114">**Data Type**</span></span>|<span data-ttu-id="dc372-115">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="dc372-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dc372-116">**媒体**</span><span class="sxs-lookup"><span data-stu-id="dc372-116">**Media**</span></span> <br/> |<span data-ttu-id="dc372-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dc372-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="dc372-118">媒体类型。</span><span class="sxs-lookup"><span data-stu-id="dc372-118">Media type.</span></span> <span data-ttu-id="dc372-119">有关详细信息, 请参阅[MediaList 表](medialist.md)。</span><span class="sxs-lookup"><span data-stu-id="dc372-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="dc372-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="dc372-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="dc372-121">datetime</span><span class="sxs-lookup"><span data-stu-id="dc372-121">datetime</span></span>  <br/> |<span data-ttu-id="dc372-122">媒体请求发出的时间。</span><span class="sxs-lookup"><span data-stu-id="dc372-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="dc372-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="dc372-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="dc372-124">datetime</span><span class="sxs-lookup"><span data-stu-id="dc372-124">datetime</span></span>  <br/> |<span data-ttu-id="dc372-125">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="dc372-125">End time of the session.</span></span>  <br/> |
   

