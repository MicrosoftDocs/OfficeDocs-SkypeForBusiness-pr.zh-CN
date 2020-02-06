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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态表，用于存储可能的调用优先级列表，例如 "紧急"、"紧急" 或 "正常"。
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815440"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ade32-103">Skype for Business Server 2015 中的 CallPriorities 表</span><span class="sxs-lookup"><span data-stu-id="ade32-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ade32-104">CallPriorities 表是一个静态表，用于存储可能的调用优先级列表，例如 "紧急"、"紧急" 或 "正常"。</span><span class="sxs-lookup"><span data-stu-id="ade32-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="ade32-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ade32-105">**Column**</span></span>|<span data-ttu-id="ade32-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ade32-106">**Data Type**</span></span>|<span data-ttu-id="ade32-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="ade32-107">**Key/Index**</span></span>|<span data-ttu-id="ade32-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="ade32-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ade32-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="ade32-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="ade32-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade32-110">tinyint</span></span>  <br/> |<span data-ttu-id="ade32-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ade32-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ade32-112">**优先级**</span><span class="sxs-lookup"><span data-stu-id="ade32-112">**Priority**</span></span> <br/> |<span data-ttu-id="ade32-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ade32-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ade32-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="ade32-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ade32-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="ade32-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="ade32-116">1-非紧急</span><span class="sxs-lookup"><span data-stu-id="ade32-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="ade32-117">2-正常</span><span class="sxs-lookup"><span data-stu-id="ade32-117">2 - Normal</span></span> <br/>  <span data-ttu-id="ade32-118">3-紧急</span><span class="sxs-lookup"><span data-stu-id="ade32-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="ade32-119">4-紧急情况</span><span class="sxs-lookup"><span data-stu-id="ade32-119">4 - Emergency</span></span> <br/> |
   

