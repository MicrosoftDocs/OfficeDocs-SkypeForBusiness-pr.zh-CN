---
title: PayloadDescription 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: 自 PayloadDescription 表是一个支持表。 每条记录代表一个编解码器，用于在音频或视频会话。
ms.openlocfilehash: 320542593479e3051992e8079abfdf9f54b0efc0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874198"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="ea19c-104">PayloadDescription 表</span><span class="sxs-lookup"><span data-stu-id="ea19c-104">PayloadDescription table</span></span>
 
<span data-ttu-id="ea19c-105">自 PayloadDescription 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="ea19c-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="ea19c-106">每条记录代表一个编解码器，用于在音频或视频会话。</span><span class="sxs-lookup"><span data-stu-id="ea19c-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="ea19c-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ea19c-107">**Column**</span></span>|<span data-ttu-id="ea19c-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ea19c-108">**Data Type**</span></span>|<span data-ttu-id="ea19c-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="ea19c-109">**Key/Index**</span></span>|<span data-ttu-id="ea19c-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="ea19c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ea19c-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="ea19c-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="ea19c-112">int</span><span class="sxs-lookup"><span data-stu-id="ea19c-112">int</span></span>  <br/> |<span data-ttu-id="ea19c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ea19c-113">Primary</span></span>  <br/> |<span data-ttu-id="ea19c-114">标识该编解码器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="ea19c-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="ea19c-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="ea19c-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="ea19c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ea19c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ea19c-117">唯一</span><span class="sxs-lookup"><span data-stu-id="ea19c-117">Unique</span></span>  <br/> |<span data-ttu-id="ea19c-118">编解码器的名称。</span><span class="sxs-lookup"><span data-stu-id="ea19c-118">Codec name.</span></span>  <br/> |
   

