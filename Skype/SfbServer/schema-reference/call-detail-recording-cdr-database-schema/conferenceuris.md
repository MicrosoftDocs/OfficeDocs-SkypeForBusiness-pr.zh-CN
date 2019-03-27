---
title: ConferenceUris 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表是一个支持表，用于存储各种会议已参与记录数据库中的会议会话的 Uri 的列表。 表中的每条记录代表一个会议 URI。
ms.openlocfilehash: 6f373774b652e9858af84dd4c16b51fcb3c5d493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887769"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="383aa-104">ConferenceUris 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="383aa-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="383aa-105">ConfereneUris 表是一个支持表，用于存储各种会议已参与记录数据库中的会议会话的 Uri 的列表。</span><span class="sxs-lookup"><span data-stu-id="383aa-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="383aa-106">表中的每条记录代表一个会议 URI。</span><span class="sxs-lookup"><span data-stu-id="383aa-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="383aa-107">**列**</span><span class="sxs-lookup"><span data-stu-id="383aa-107">**Column**</span></span>|<span data-ttu-id="383aa-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="383aa-108">**Data Type**</span></span>|<span data-ttu-id="383aa-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="383aa-109">**Key/Index**</span></span>|<span data-ttu-id="383aa-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="383aa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="383aa-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="383aa-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="383aa-112">datetime</span><span class="sxs-lookup"><span data-stu-id="383aa-112">datetime</span></span>  <br/> |<span data-ttu-id="383aa-113">Primary</span><span class="sxs-lookup"><span data-stu-id="383aa-113">Primary</span></span>  <br/> |<span data-ttu-id="383aa-114">内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="383aa-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="383aa-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="383aa-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="383aa-116">int</span><span class="sxs-lookup"><span data-stu-id="383aa-116">int</span></span>  <br/> |<span data-ttu-id="383aa-117">Primary</span><span class="sxs-lookup"><span data-stu-id="383aa-117">Primary</span></span>  <br/> |<span data-ttu-id="383aa-118">标识此会议 URI 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="383aa-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="383aa-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="383aa-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="383aa-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="383aa-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="383aa-121">会议 URI。</span><span class="sxs-lookup"><span data-stu-id="383aa-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="383aa-122">**校验和**</span><span class="sxs-lookup"><span data-stu-id="383aa-122">**Checksum**</span></span> <br/> |<span data-ttu-id="383aa-123">int</span><span class="sxs-lookup"><span data-stu-id="383aa-123">int</span></span>  <br/> ||<span data-ttu-id="383aa-124">ConferenceUri 校验和。</span><span class="sxs-lookup"><span data-stu-id="383aa-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="383aa-125">使用到提高的搜索数据库的速度。</span><span class="sxs-lookup"><span data-stu-id="383aa-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="383aa-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="383aa-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="383aa-127">int</span><span class="sxs-lookup"><span data-stu-id="383aa-127">int</span></span>  <br/> |<span data-ttu-id="383aa-128">外</span><span class="sxs-lookup"><span data-stu-id="383aa-128">Foreign</span></span>  <br/> |<span data-ttu-id="383aa-129">URI 类型，如 IM 会议，或 conf:audio conf:chat-音频/视频会议的视频。</span><span class="sxs-lookup"><span data-stu-id="383aa-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="383aa-130">[UriTypes 表](uritypes.md)表的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="383aa-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

