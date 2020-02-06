---
title: Skype for Business Server 2015 中的 ConferenceUris 表
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表是一个支持表，用于存储参与数据库中记录的会议会话的各种会议 Uri 的列表。 表中的每条记录表示一个会议 URI。
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815310"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d3058-104">Skype for Business Server 2015 中的 ConferenceUris 表</span><span class="sxs-lookup"><span data-stu-id="d3058-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d3058-105">ConfereneUris 表是一个支持表，用于存储参与数据库中记录的会议会话的各种会议 Uri 的列表。</span><span class="sxs-lookup"><span data-stu-id="d3058-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="d3058-106">表中的每条记录表示一个会议 URI。</span><span class="sxs-lookup"><span data-stu-id="d3058-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="d3058-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d3058-107">**Column**</span></span>|<span data-ttu-id="d3058-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d3058-108">**Data Type**</span></span>|<span data-ttu-id="d3058-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d3058-109">**Key/Index**</span></span>|<span data-ttu-id="d3058-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d3058-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d3058-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d3058-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d3058-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d3058-112">datetime</span></span>  <br/> |<span data-ttu-id="d3058-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d3058-113">Primary</span></span>  <br/> |<span data-ttu-id="d3058-114">时间戳，内部使用。</span><span class="sxs-lookup"><span data-stu-id="d3058-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="d3058-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="d3058-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="d3058-116">int</span><span class="sxs-lookup"><span data-stu-id="d3058-116">int</span></span>  <br/> |<span data-ttu-id="d3058-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d3058-117">Primary</span></span>  <br/> |<span data-ttu-id="d3058-118">标识此会议 URI 的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="d3058-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="d3058-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="d3058-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="d3058-120">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d3058-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="d3058-121">会议 URI。</span><span class="sxs-lookup"><span data-stu-id="d3058-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="d3058-122">**检查**</span><span class="sxs-lookup"><span data-stu-id="d3058-122">**Checksum**</span></span> <br/> |<span data-ttu-id="d3058-123">int</span><span class="sxs-lookup"><span data-stu-id="d3058-123">int</span></span>  <br/> ||<span data-ttu-id="d3058-124">ConferenceUri 的校验和。</span><span class="sxs-lookup"><span data-stu-id="d3058-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="d3058-125">用于提高数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="d3058-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="d3058-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="d3058-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="d3058-127">int</span><span class="sxs-lookup"><span data-stu-id="d3058-127">int</span></span>  <br/> |<span data-ttu-id="d3058-128">外表</span><span class="sxs-lookup"><span data-stu-id="d3058-128">Foreign</span></span>  <br/> |<span data-ttu-id="d3058-129">URI 类型，例如会议：用于即时消息会议的聊天或会议：音频-音频/视频会议的视频。</span><span class="sxs-lookup"><span data-stu-id="d3058-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="d3058-130">有关详细信息，请参阅[UriTypes 表](uritypes.md)表。</span><span class="sxs-lookup"><span data-stu-id="d3058-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

