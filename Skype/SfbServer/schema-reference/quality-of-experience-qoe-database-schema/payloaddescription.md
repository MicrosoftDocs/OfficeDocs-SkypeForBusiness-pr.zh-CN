---
title: PayloadDescription 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 表是一个支持表。 每条记录都代表一个音频或视频会话使用的编解码器。
ms.openlocfilehash: c9476aea28993a053096a095469d2d4e13251581
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806292"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="f9d0f-104">PayloadDescription 表</span><span class="sxs-lookup"><span data-stu-id="f9d0f-104">PayloadDescription table</span></span>
 
<span data-ttu-id="f9d0f-p102">PayloadDescription 表是一个支持表。每条记录都代表一个音频或视频会话使用的编解码器。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-p102">The PayloadDescription table is a supporting table. Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="f9d0f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="f9d0f-107">**Column**</span></span>|<span data-ttu-id="f9d0f-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f9d0f-108">**Data Type**</span></span>|<span data-ttu-id="f9d0f-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="f9d0f-109">**Key/Index**</span></span>|<span data-ttu-id="f9d0f-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f9d0f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f9d0f-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="f9d0f-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="f9d0f-112">int</span><span class="sxs-lookup"><span data-stu-id="f9d0f-112">int</span></span>  <br/> |<span data-ttu-id="f9d0f-113">主</span><span class="sxs-lookup"><span data-stu-id="f9d0f-113">Primary</span></span>  <br/> |<span data-ttu-id="f9d0f-114">用于标识该编解码器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="f9d0f-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="f9d0f-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="f9d0f-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f9d0f-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f9d0f-117">独特</span><span class="sxs-lookup"><span data-stu-id="f9d0f-117">Unique</span></span>  <br/> |<span data-ttu-id="f9d0f-118">编解码器的名称。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-118">Codec name.</span></span>  <br/> |
   

