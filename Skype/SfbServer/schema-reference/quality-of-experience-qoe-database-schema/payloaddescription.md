---
title: PayloadDescription 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 表是支持表。 每个记录表示音频或视频会话中使用的一个编解码器。
ms.openlocfilehash: fb4acb8182db920e25305b2be72cbc19700792bb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="payloaddescription-table"></a><span data-ttu-id="8b67f-104">PayloadDescription 表</span><span class="sxs-lookup"><span data-stu-id="8b67f-104">PayloadDescription table</span></span>
 
<span data-ttu-id="8b67f-105">PayloadDescription 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="8b67f-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="8b67f-106">每个记录表示音频或视频会话中使用的一个编解码器。</span><span class="sxs-lookup"><span data-stu-id="8b67f-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="8b67f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8b67f-107">**Column**</span></span>|<span data-ttu-id="8b67f-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8b67f-108">**Data Type**</span></span>|<span data-ttu-id="8b67f-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8b67f-109">**Key/Index**</span></span>|<span data-ttu-id="8b67f-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8b67f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b67f-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="8b67f-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="8b67f-112">int</span><span class="sxs-lookup"><span data-stu-id="8b67f-112">int</span></span>  <br/> |<span data-ttu-id="8b67f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8b67f-113">Primary</span></span>  <br/> |<span data-ttu-id="8b67f-114">标识编解码器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="8b67f-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="8b67f-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="8b67f-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="8b67f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b67f-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8b67f-117">唯一</span><span class="sxs-lookup"><span data-stu-id="8b67f-117">Unique</span></span>  <br/> |<span data-ttu-id="8b67f-118">编解码器名称。</span><span class="sxs-lookup"><span data-stu-id="8b67f-118">Codec name.</span></span>  <br/> |
   

