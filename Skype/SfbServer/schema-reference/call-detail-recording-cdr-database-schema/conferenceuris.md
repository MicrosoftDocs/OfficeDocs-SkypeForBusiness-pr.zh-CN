---
title: 在业务服务器 2015年的 Skype 的 ConferenceUris 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表是一个支持的表来存储各种会议参加讲座记录在数据库中的 Uri 的列表。 每个表中的记录表示一个会议的 URI。
ms.openlocfilehash: 921bb448ffe50d62aa7680db0e8097c186eef8e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8d9c7-104">在业务服务器 2015年的 Skype 的 ConferenceUris 表</span><span class="sxs-lookup"><span data-stu-id="8d9c7-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8d9c7-105">ConfereneUris 表是一个支持的表来存储各种会议参加讲座记录在数据库中的 Uri 的列表。</span><span class="sxs-lookup"><span data-stu-id="8d9c7-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="8d9c7-106">每个表中的记录表示一个会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="8d9c7-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="8d9c7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8d9c7-107">**Column**</span></span>|<span data-ttu-id="8d9c7-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8d9c7-108">**Data Type**</span></span>|<span data-ttu-id="8d9c7-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8d9c7-109">**Key/Index**</span></span>|<span data-ttu-id="8d9c7-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8d9c7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d9c7-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="8d9c7-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="8d9c7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="8d9c7-112">datetime</span></span>  <br/> |<span data-ttu-id="8d9c7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8d9c7-113">Primary</span></span>  <br/> |<span data-ttu-id="8d9c7-114">内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="8d9c7-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="8d9c7-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="8d9c7-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="8d9c7-116">int</span><span class="sxs-lookup"><span data-stu-id="8d9c7-116">int</span></span>  <br/> |<span data-ttu-id="8d9c7-117">Primary</span><span class="sxs-lookup"><span data-stu-id="8d9c7-117">Primary</span></span>  <br/> |<span data-ttu-id="8d9c7-118">标识的 URI 的这次会议的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="8d9c7-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="8d9c7-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="8d9c7-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="8d9c7-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="8d9c7-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="8d9c7-121">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="8d9c7-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="8d9c7-122">**校验和**</span><span class="sxs-lookup"><span data-stu-id="8d9c7-122">**Checksum**</span></span> <br/> |<span data-ttu-id="8d9c7-123">int</span><span class="sxs-lookup"><span data-stu-id="8d9c7-123">int</span></span>  <br/> ||<span data-ttu-id="8d9c7-124">ConferenceUri 的校验和。</span><span class="sxs-lookup"><span data-stu-id="8d9c7-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="8d9c7-125">使用为增加数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="8d9c7-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="8d9c7-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="8d9c7-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="8d9c7-127">int</span><span class="sxs-lookup"><span data-stu-id="8d9c7-127">int</span></span>  <br/> |<span data-ttu-id="8d9c7-128">外</span><span class="sxs-lookup"><span data-stu-id="8d9c7-128">Foreign</span></span>  <br/> |<span data-ttu-id="8d9c7-129">URI 类型，如 IM 会议或 conf:audio conf:chat-视频的音频/视频会议。</span><span class="sxs-lookup"><span data-stu-id="8d9c7-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="8d9c7-130">[UriTypes](uritypes.md)表的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="8d9c7-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

