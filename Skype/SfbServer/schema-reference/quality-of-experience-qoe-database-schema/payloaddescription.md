---
title: PayloadDescription 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 表是支持表。 每条记录表示一个编解码器，用于音频或视频会话。
ms.openlocfilehash: 3a5719d7fbfe23eb8c1457565a36df0a02617fde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807490"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="e1737-104">PayloadDescription 表</span><span class="sxs-lookup"><span data-stu-id="e1737-104">PayloadDescription table</span></span>
 
<span data-ttu-id="e1737-105">PayloadDescription 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="e1737-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="e1737-106">每条记录表示一个编解码器，用于音频或视频会话。</span><span class="sxs-lookup"><span data-stu-id="e1737-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="e1737-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e1737-107">**Column**</span></span>|<span data-ttu-id="e1737-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e1737-108">**Data Type**</span></span>|<span data-ttu-id="e1737-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="e1737-109">**Key/Index**</span></span>|<span data-ttu-id="e1737-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e1737-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e1737-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="e1737-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="e1737-112">int</span><span class="sxs-lookup"><span data-stu-id="e1737-112">int</span></span>  <br/> |<span data-ttu-id="e1737-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e1737-113">Primary</span></span>  <br/> |<span data-ttu-id="e1737-114">标识编解码器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="e1737-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="e1737-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="e1737-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="e1737-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e1737-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e1737-117">唯一</span><span class="sxs-lookup"><span data-stu-id="e1737-117">Unique</span></span>  <br/> |<span data-ttu-id="e1737-118">编解码器名称。</span><span class="sxs-lookup"><span data-stu-id="e1737-118">Codec name.</span></span>  <br/> |
   

