---
title: MediaList 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 7742baf17240ca810268721c0e47e37f17e555cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815030"
---
# <a name="medialist-table"></a><span data-ttu-id="87465-103">MediaList 表</span><span class="sxs-lookup"><span data-stu-id="87465-103">MediaList table</span></span>
 
<span data-ttu-id="87465-104">MediaList 表是一个静态表，用于存储各种媒体类型的列表。</span><span class="sxs-lookup"><span data-stu-id="87465-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="87465-105">**列**</span><span class="sxs-lookup"><span data-stu-id="87465-105">**Column**</span></span>|<span data-ttu-id="87465-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="87465-106">**Data Type**</span></span>|<span data-ttu-id="87465-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="87465-107">**Key/Index**</span></span>|<span data-ttu-id="87465-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="87465-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="87465-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="87465-109">**MediaId**</span></span> <br/> |<span data-ttu-id="87465-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="87465-110">tinyint</span></span>  <br/> |<span data-ttu-id="87465-111">Primary</span><span class="sxs-lookup"><span data-stu-id="87465-111">Primary</span></span>  <br/> |<span data-ttu-id="87465-112">值：1-7</span><span class="sxs-lookup"><span data-stu-id="87465-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="87465-113">**媒体**</span><span class="sxs-lookup"><span data-stu-id="87465-113">**Media**</span></span> <br/> |<span data-ttu-id="87465-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87465-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="87465-115">MediaID 与媒体值的静态映射：</span><span class="sxs-lookup"><span data-stu-id="87465-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="87465-116">1 – IM</span><span class="sxs-lookup"><span data-stu-id="87465-116">1 -- IM</span></span> <br/>  <span data-ttu-id="87465-117">2-文件传输</span><span class="sxs-lookup"><span data-stu-id="87465-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="87465-118">3-远程协助</span><span class="sxs-lookup"><span data-stu-id="87465-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="87465-119">4-应用程序共享</span><span class="sxs-lookup"><span data-stu-id="87465-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="87465-120">5 – 音频</span><span class="sxs-lookup"><span data-stu-id="87465-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="87465-121">6 – 视频</span><span class="sxs-lookup"><span data-stu-id="87465-121">6 -- Video</span></span> <br/>  <span data-ttu-id="87465-122">7-应用邀请</span><span class="sxs-lookup"><span data-stu-id="87465-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="87465-123">如果你尝试确定 LcsCDR.SessionDetailsView.MediaTypes 中的值的形式类型，则需要使用以下加入代码段：</span><span class="sxs-lookup"><span data-stu-id="87465-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
