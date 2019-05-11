---
title: MediaList 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 表是一个静态表，用于存储各种媒体类型的列表。
ms.openlocfilehash: 3eaa40cb5ae03129edaa36effa7b40012fc38429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930649"
---
# <a name="medialist-table"></a><span data-ttu-id="9bf29-103">MediaList 表</span><span class="sxs-lookup"><span data-stu-id="9bf29-103">MediaList table</span></span>
 
<span data-ttu-id="9bf29-104">MediaList 表是一个静态表，用于存储各种媒体类型的列表。</span><span class="sxs-lookup"><span data-stu-id="9bf29-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="9bf29-105">**列**</span><span class="sxs-lookup"><span data-stu-id="9bf29-105">**Column**</span></span>|<span data-ttu-id="9bf29-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9bf29-106">**Data Type**</span></span>|<span data-ttu-id="9bf29-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9bf29-107">**Key/Index**</span></span>|<span data-ttu-id="9bf29-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9bf29-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9bf29-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="9bf29-109">**MediaId**</span></span> <br/> |<span data-ttu-id="9bf29-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="9bf29-110">tinyint</span></span>  <br/> |<span data-ttu-id="9bf29-111">Primary</span><span class="sxs-lookup"><span data-stu-id="9bf29-111">Primary</span></span>  <br/> |<span data-ttu-id="9bf29-112">值：1-7</span><span class="sxs-lookup"><span data-stu-id="9bf29-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="9bf29-113">**媒体**</span><span class="sxs-lookup"><span data-stu-id="9bf29-113">**Media**</span></span> <br/> |<span data-ttu-id="9bf29-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9bf29-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9bf29-115">MediaID 与媒体值的静态映射：</span><span class="sxs-lookup"><span data-stu-id="9bf29-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="9bf29-116">1 – IM</span><span class="sxs-lookup"><span data-stu-id="9bf29-116">1 -- IM</span></span> <br/>  <span data-ttu-id="9bf29-117">2-文件传输</span><span class="sxs-lookup"><span data-stu-id="9bf29-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="9bf29-118">3-远程协助</span><span class="sxs-lookup"><span data-stu-id="9bf29-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="9bf29-119">4-应用程序共享</span><span class="sxs-lookup"><span data-stu-id="9bf29-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="9bf29-120">5 – 音频</span><span class="sxs-lookup"><span data-stu-id="9bf29-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="9bf29-121">6 – 视频</span><span class="sxs-lookup"><span data-stu-id="9bf29-121">6 -- Video</span></span> <br/>  <span data-ttu-id="9bf29-122">7-应用程序邀请</span><span class="sxs-lookup"><span data-stu-id="9bf29-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="9bf29-123">如果你尝试确定 LcsCDR.SessionDetailsView.MediaTypes 中的值的形式类型，则需要使用以下加入代码段：</span><span class="sxs-lookup"><span data-stu-id="9bf29-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
