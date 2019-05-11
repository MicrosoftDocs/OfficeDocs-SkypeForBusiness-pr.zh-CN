---
title: 媒体视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒体视图中存储的对等会话中使用的一个媒体类型的信息。 将由多个记录在表中，表示一个会话，如果使用多个媒体类型。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 83caf609efae4e97961e7c62c3a1ed6c6004e8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930691"
---
# <a name="media-view"></a><span data-ttu-id="8ede7-105">媒体视图</span><span class="sxs-lookup"><span data-stu-id="8ede7-105">Media view</span></span>
 
<span data-ttu-id="8ede7-106">媒体视图中存储的对等会话中使用的一个媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="8ede7-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="8ede7-107">将由多个记录在表中，表示一个会话，如果使用多个媒体类型。</span><span class="sxs-lookup"><span data-stu-id="8ede7-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="8ede7-108">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8ede7-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ede7-109">媒体视图不应用于计算会话的媒体持续时间。</span><span class="sxs-lookup"><span data-stu-id="8ede7-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="8ede7-110">该视图包含会话中的媒体交换的信号详细信息。</span><span class="sxs-lookup"><span data-stu-id="8ede7-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="8ede7-111">媒体交换通过 INVITE 请求，并 StartTime 指示邀请已发送的时间。邀请时间不一定意味着媒体开始时间，因为媒体的起始位置仅接受会话。</span><span class="sxs-lookup"><span data-stu-id="8ede7-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="8ede7-112">媒体视图它包含[SessionDetails view](sessiondetails-0.md)中的列的所有此外下面列出的内容。</span><span class="sxs-lookup"><span data-stu-id="8ede7-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="8ede7-113">**列**</span><span class="sxs-lookup"><span data-stu-id="8ede7-113">**Column**</span></span>|<span data-ttu-id="8ede7-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8ede7-114">**Data Type**</span></span>|<span data-ttu-id="8ede7-115">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8ede7-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ede7-116">**媒体**</span><span class="sxs-lookup"><span data-stu-id="8ede7-116">**Media**</span></span> <br/> |<span data-ttu-id="8ede7-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8ede7-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8ede7-118">媒体类型。</span><span class="sxs-lookup"><span data-stu-id="8ede7-118">Media type.</span></span> <span data-ttu-id="8ede7-119">请参阅[MediaList 表](medialist.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8ede7-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8ede7-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="8ede7-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="8ede7-121">datetime</span><span class="sxs-lookup"><span data-stu-id="8ede7-121">datetime</span></span>  <br/> |<span data-ttu-id="8ede7-122">已发送媒体请求的时间。</span><span class="sxs-lookup"><span data-stu-id="8ede7-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="8ede7-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="8ede7-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="8ede7-124">datetime</span><span class="sxs-lookup"><span data-stu-id="8ede7-124">datetime</span></span>  <br/> |<span data-ttu-id="8ede7-125">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="8ede7-125">End time of the session.</span></span>  <br/> |
   

