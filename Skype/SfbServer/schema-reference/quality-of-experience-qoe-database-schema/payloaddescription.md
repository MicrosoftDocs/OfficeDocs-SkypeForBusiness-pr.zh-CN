---
title: PayloadDescription 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: 自 PayloadDescription 表是一个支持表。 每条记录代表一个编解码器，用于在音频或视频会话。
ms.openlocfilehash: 2854d3b1dd5338b9d150bb1a9c36a0409d0f8099
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920064"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="5a280-104">PayloadDescription 表</span><span class="sxs-lookup"><span data-stu-id="5a280-104">PayloadDescription table</span></span>
 
<span data-ttu-id="5a280-105">自 PayloadDescription 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="5a280-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="5a280-106">每条记录代表一个编解码器，用于在音频或视频会话。</span><span class="sxs-lookup"><span data-stu-id="5a280-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="5a280-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5a280-107">**Column**</span></span>|<span data-ttu-id="5a280-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5a280-108">**Data Type**</span></span>|<span data-ttu-id="5a280-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="5a280-109">**Key/Index**</span></span>|<span data-ttu-id="5a280-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="5a280-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5a280-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="5a280-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="5a280-112">int</span><span class="sxs-lookup"><span data-stu-id="5a280-112">int</span></span>  <br/> |<span data-ttu-id="5a280-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5a280-113">Primary</span></span>  <br/> |<span data-ttu-id="5a280-114">标识该编解码器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="5a280-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="5a280-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="5a280-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="5a280-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5a280-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5a280-117">唯一</span><span class="sxs-lookup"><span data-stu-id="5a280-117">Unique</span></span>  <br/> |<span data-ttu-id="5a280-118">编解码器的名称。</span><span class="sxs-lookup"><span data-stu-id="5a280-118">Codec name.</span></span>  <br/> |
   

