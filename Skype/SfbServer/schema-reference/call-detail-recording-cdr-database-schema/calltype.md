---
title: 在业务服务器 2015年的 Skype 的 CallType 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表是一个静态的表来存储可能调用类型的列表。
ms.openlocfilehash: e2353176a69db9eada137525561541d26caa7a8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0c45e-103">在业务服务器 2015年的 Skype 的 CallType 表</span><span class="sxs-lookup"><span data-stu-id="0c45e-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0c45e-104">CallType 表是一个静态的表来存储可能调用类型的列表。</span><span class="sxs-lookup"><span data-stu-id="0c45e-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="0c45e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="0c45e-105">**Column**</span></span>|<span data-ttu-id="0c45e-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0c45e-106">**Data Type**</span></span>|<span data-ttu-id="0c45e-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="0c45e-107">**Key/Index**</span></span>|<span data-ttu-id="0c45e-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0c45e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c45e-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="0c45e-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="0c45e-110">int</span><span class="sxs-lookup"><span data-stu-id="0c45e-110">int</span></span>  <br/> |<span data-ttu-id="0c45e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="0c45e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="0c45e-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="0c45e-112">**CallType**</span></span> <br/> |<span data-ttu-id="0c45e-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="0c45e-113">nvarchar</span></span>  <br/> || <span data-ttu-id="0c45e-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="0c45e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="0c45e-115">0--未知</span><span class="sxs-lookup"><span data-stu-id="0c45e-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="0c45e-116">1-即时消息</span><span class="sxs-lookup"><span data-stu-id="0c45e-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="0c45e-117">2--应用程序共享</span><span class="sxs-lookup"><span data-stu-id="0c45e-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="0c45e-118">3-音频</span><span class="sxs-lookup"><span data-stu-id="0c45e-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="0c45e-119">4-音频和视频</span><span class="sxs-lookup"><span data-stu-id="0c45e-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="0c45e-120">5-文件传输</span><span class="sxs-lookup"><span data-stu-id="0c45e-120">5 - File Transfer</span></span> <br/> |
   

