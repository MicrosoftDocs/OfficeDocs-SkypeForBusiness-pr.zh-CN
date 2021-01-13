---
title: Skype for Business Server 2015 中的 CallPriorities 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态表，用于存储可能的呼叫优先级列表，例如"紧急"、"紧急"或"正常"。
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813432"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="74447-103">Skype for Business Server 2015 中的 CallPriorities 表</span><span class="sxs-lookup"><span data-stu-id="74447-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="74447-104">CallPriorities 表是一个静态表，用于存储可能的呼叫优先级列表，例如"紧急"、"紧急"或"正常"。</span><span class="sxs-lookup"><span data-stu-id="74447-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="74447-105">**列**</span><span class="sxs-lookup"><span data-stu-id="74447-105">**Column**</span></span>|<span data-ttu-id="74447-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="74447-106">**Data Type**</span></span>|<span data-ttu-id="74447-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="74447-107">**Key/Index**</span></span>|<span data-ttu-id="74447-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="74447-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="74447-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="74447-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="74447-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="74447-110">tinyint</span></span>  <br/> |<span data-ttu-id="74447-111">主</span><span class="sxs-lookup"><span data-stu-id="74447-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="74447-112">**Priority**</span><span class="sxs-lookup"><span data-stu-id="74447-112">**Priority**</span></span> <br/> |<span data-ttu-id="74447-113">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="74447-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="74447-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="74447-114">Allowed values:</span></span> <br/>  <span data-ttu-id="74447-115">0 -- 未知</span><span class="sxs-lookup"><span data-stu-id="74447-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="74447-116">1 - 非紧急</span><span class="sxs-lookup"><span data-stu-id="74447-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="74447-117">2 – 普通</span><span class="sxs-lookup"><span data-stu-id="74447-117">2 - Normal</span></span> <br/>  <span data-ttu-id="74447-118">3 – 紧急</span><span class="sxs-lookup"><span data-stu-id="74447-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="74447-119">4 – 紧迫</span><span class="sxs-lookup"><span data-stu-id="74447-119">4 - Emergency</span></span> <br/> |
   

