---
title: 媒体视图
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: “媒体”视图存储有关在对等会话中使用的一种媒体类型的信息。 如果使用多个媒体类型，则一个会话由表中的多条记录表示。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831783"
---
# <a name="media-view"></a><span data-ttu-id="59f0e-105">媒体视图</span><span class="sxs-lookup"><span data-stu-id="59f0e-105">Media view</span></span>
 
<span data-ttu-id="59f0e-106">“媒体”视图存储有关在对等会话中使用的一种媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="59f0e-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="59f0e-107">如果使用多个媒体类型，则一个会话由表中的多条记录表示。</span><span class="sxs-lookup"><span data-stu-id="59f0e-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="59f0e-108">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="59f0e-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="59f0e-p103">“媒体”视图不应用来计算会话的媒体持续时间。此视图包含会话中的媒体交换信号详情。媒体交换通过 INVITE 请求实现，StartTime 指示发出 INVITE 的时间。邀请时间不一定表示媒体的启动时间，因为仅在会话被接受后，媒体才启动。</span><span class="sxs-lookup"><span data-stu-id="59f0e-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="59f0e-112">媒体视图包含 [SessionDetails](sessiondetails-0.md) 视图中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="59f0e-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="59f0e-113">**列**</span><span class="sxs-lookup"><span data-stu-id="59f0e-113">**Column**</span></span>|<span data-ttu-id="59f0e-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="59f0e-114">**Data Type**</span></span>|<span data-ttu-id="59f0e-115">**Details**</span><span class="sxs-lookup"><span data-stu-id="59f0e-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="59f0e-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="59f0e-116">**Media**</span></span> <br/> |<span data-ttu-id="59f0e-117">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="59f0e-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="59f0e-118">媒体类型。</span><span class="sxs-lookup"><span data-stu-id="59f0e-118">Media type.</span></span> <span data-ttu-id="59f0e-119">有关详细信息， [请参阅 MediaList](medialist.md) 表。</span><span class="sxs-lookup"><span data-stu-id="59f0e-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="59f0e-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="59f0e-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="59f0e-121">datetime</span><span class="sxs-lookup"><span data-stu-id="59f0e-121">datetime</span></span>  <br/> |<span data-ttu-id="59f0e-122">发出媒体请求的时间。</span><span class="sxs-lookup"><span data-stu-id="59f0e-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="59f0e-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="59f0e-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="59f0e-124">datetime</span><span class="sxs-lookup"><span data-stu-id="59f0e-124">datetime</span></span>  <br/> |<span data-ttu-id="59f0e-125">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="59f0e-125">End time of the session.</span></span>  <br/> |
   

