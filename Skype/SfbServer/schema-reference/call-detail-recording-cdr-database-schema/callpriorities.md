---
title: Skype for Business Server 2015 中的 CallPriorities 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态表, 用于存储可能的调用优先级列表, 例如 "紧急"、"紧急" 或 "正常"。
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296565"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b2f13-103">Skype for Business Server 2015 中的 CallPriorities 表</span><span class="sxs-lookup"><span data-stu-id="b2f13-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b2f13-104">CallPriorities 表是一个静态表, 用于存储可能的调用优先级列表, 例如 "紧急"、"紧急" 或 "正常"。</span><span class="sxs-lookup"><span data-stu-id="b2f13-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="b2f13-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b2f13-105">**Column**</span></span>|<span data-ttu-id="b2f13-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b2f13-106">**Data Type**</span></span>|<span data-ttu-id="b2f13-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b2f13-107">**Key/Index**</span></span>|<span data-ttu-id="b2f13-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b2f13-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b2f13-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="b2f13-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="b2f13-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="b2f13-110">tinyint</span></span>  <br/> |<span data-ttu-id="b2f13-111">Primary</span><span class="sxs-lookup"><span data-stu-id="b2f13-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="b2f13-112">**优先级**</span><span class="sxs-lookup"><span data-stu-id="b2f13-112">**Priority**</span></span> <br/> |<span data-ttu-id="b2f13-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b2f13-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="b2f13-114">允许的值:</span><span class="sxs-lookup"><span data-stu-id="b2f13-114">Allowed values:</span></span> <br/>  <span data-ttu-id="b2f13-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="b2f13-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="b2f13-116">1-非紧急</span><span class="sxs-lookup"><span data-stu-id="b2f13-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="b2f13-117">2-正常</span><span class="sxs-lookup"><span data-stu-id="b2f13-117">2 - Normal</span></span> <br/>  <span data-ttu-id="b2f13-118">3-紧急</span><span class="sxs-lookup"><span data-stu-id="b2f13-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="b2f13-119">4-紧急情况</span><span class="sxs-lookup"><span data-stu-id="b2f13-119">4 - Emergency</span></span> <br/> |
   

