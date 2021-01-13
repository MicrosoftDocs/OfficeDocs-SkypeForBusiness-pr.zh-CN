---
title: Skype for Business Server 2015 中的 ConferenceUris 表
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表是一个支持表，用于存储已参与数据库中记录的会议会话的各种会议 URI 列表。表中的每条记录代表一个会议 URI。
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816132"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fb106-104">Skype for Business Server 2015 中的 ConferenceUris 表</span><span class="sxs-lookup"><span data-stu-id="fb106-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fb106-p102">ConfereneUris 表是一个支持表，用于存储已参与数据库中记录的会议会话的各种会议 URI 列表。表中的每条记录代表一个会议 URI。</span><span class="sxs-lookup"><span data-stu-id="fb106-p102">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="fb106-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fb106-107">**Column**</span></span>|<span data-ttu-id="fb106-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fb106-108">**Data Type**</span></span>|<span data-ttu-id="fb106-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="fb106-109">**Key/Index**</span></span>|<span data-ttu-id="fb106-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="fb106-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fb106-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="fb106-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="fb106-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fb106-112">datetime</span></span>  <br/> |<span data-ttu-id="fb106-113">主</span><span class="sxs-lookup"><span data-stu-id="fb106-113">Primary</span></span>  <br/> |<span data-ttu-id="fb106-114">内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="fb106-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="fb106-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="fb106-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="fb106-116">int</span><span class="sxs-lookup"><span data-stu-id="fb106-116">int</span></span>  <br/> |<span data-ttu-id="fb106-117">主</span><span class="sxs-lookup"><span data-stu-id="fb106-117">Primary</span></span>  <br/> |<span data-ttu-id="fb106-118">标识此会议 URI 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="fb106-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="fb106-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="fb106-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="fb106-120">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="fb106-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="fb106-121">会议 URI。</span><span class="sxs-lookup"><span data-stu-id="fb106-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="fb106-122">**校验和**</span><span class="sxs-lookup"><span data-stu-id="fb106-122">**Checksum**</span></span> <br/> |<span data-ttu-id="fb106-123">int</span><span class="sxs-lookup"><span data-stu-id="fb106-123">int</span></span>  <br/> ||<span data-ttu-id="fb106-p103">ConferenceUri 的校验和。用于增加数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="fb106-p103">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="fb106-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="fb106-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="fb106-127">int</span><span class="sxs-lookup"><span data-stu-id="fb106-127">int</span></span>  <br/> |<span data-ttu-id="fb106-128">Foreign</span><span class="sxs-lookup"><span data-stu-id="fb106-128">Foreign</span></span>  <br/> |<span data-ttu-id="fb106-129">URI 类型，如 conf:chat 代表 IM 会议，conf:audio-video 代表音频/视频会议。</span><span class="sxs-lookup"><span data-stu-id="fb106-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="fb106-130">有关详细信息， [请参阅 UriTypes](uritypes.md) 表表。</span><span class="sxs-lookup"><span data-stu-id="fb106-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

