---
title: MediaList 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 表是一个静态表，用于存储各种媒体类型的列表。
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813132"
---
# <a name="medialist-table"></a><span data-ttu-id="17194-103">MediaList 表</span><span class="sxs-lookup"><span data-stu-id="17194-103">MediaList table</span></span>
 
<span data-ttu-id="17194-104">MediaList 表是一个静态表，用于存储各种媒体类型的列表。</span><span class="sxs-lookup"><span data-stu-id="17194-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="17194-105">**列**</span><span class="sxs-lookup"><span data-stu-id="17194-105">**Column**</span></span>|<span data-ttu-id="17194-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="17194-106">**Data Type**</span></span>|<span data-ttu-id="17194-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="17194-107">**Key/Index**</span></span>|<span data-ttu-id="17194-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="17194-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="17194-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="17194-109">**MediaId**</span></span> <br/> |<span data-ttu-id="17194-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="17194-110">tinyint</span></span>  <br/> |<span data-ttu-id="17194-111">主</span><span class="sxs-lookup"><span data-stu-id="17194-111">Primary</span></span>  <br/> |<span data-ttu-id="17194-112">值：1-7</span><span class="sxs-lookup"><span data-stu-id="17194-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="17194-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="17194-113">**Media**</span></span> <br/> |<span data-ttu-id="17194-114">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="17194-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="17194-115">MediaID 和媒体值的静态映射：</span><span class="sxs-lookup"><span data-stu-id="17194-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="17194-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="17194-116">1 -- IM</span></span> <br/>  <span data-ttu-id="17194-117">2 - 文件传输</span><span class="sxs-lookup"><span data-stu-id="17194-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="17194-118">3 - 远程协助</span><span class="sxs-lookup"><span data-stu-id="17194-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="17194-119">4 - 应用程序共享</span><span class="sxs-lookup"><span data-stu-id="17194-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="17194-120">5 -- 音频</span><span class="sxs-lookup"><span data-stu-id="17194-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="17194-121">6 -- 视频</span><span class="sxs-lookup"><span data-stu-id="17194-121">6 -- Video</span></span> <br/>  <span data-ttu-id="17194-122">7 - 应用邀请</span><span class="sxs-lookup"><span data-stu-id="17194-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="17194-123">如果尝试确定 LcsCDR.SessionDetailsView.MediaTypes 中值的模态类型，则需要使用以下 Join 代码段：</span><span class="sxs-lookup"><span data-stu-id="17194-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
