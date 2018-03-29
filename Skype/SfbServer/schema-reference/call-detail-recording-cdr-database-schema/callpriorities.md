---
title: 在业务服务器 2015年的 Skype 的 CallPriorities 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态的表来存储可能调用优先级，如紧急的紧急或标准列表。
ms.openlocfilehash: ccd92857015e865e36cbef4147c4355369263e90
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9d7be-103">在业务服务器 2015年的 Skype 的 CallPriorities 表</span><span class="sxs-lookup"><span data-stu-id="9d7be-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9d7be-104">CallPriorities 表是一个静态的表来存储可能调用优先级，如紧急的紧急或标准列表。</span><span class="sxs-lookup"><span data-stu-id="9d7be-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="9d7be-105">**列**</span><span class="sxs-lookup"><span data-stu-id="9d7be-105">**Column**</span></span>|<span data-ttu-id="9d7be-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9d7be-106">**Data Type**</span></span>|<span data-ttu-id="9d7be-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9d7be-107">**Key/Index**</span></span>|<span data-ttu-id="9d7be-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9d7be-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d7be-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="9d7be-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="9d7be-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="9d7be-110">tinyint</span></span>  <br/> |<span data-ttu-id="9d7be-111">Primary</span><span class="sxs-lookup"><span data-stu-id="9d7be-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="9d7be-112">**优先级**</span><span class="sxs-lookup"><span data-stu-id="9d7be-112">**Priority**</span></span> <br/> |<span data-ttu-id="9d7be-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9d7be-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9d7be-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="9d7be-114">Allowed values:</span></span> <br/>  <span data-ttu-id="9d7be-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="9d7be-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="9d7be-116">1-非紧急</span><span class="sxs-lookup"><span data-stu-id="9d7be-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="9d7be-117">2-正常</span><span class="sxs-lookup"><span data-stu-id="9d7be-117">2 - Normal</span></span> <br/>  <span data-ttu-id="9d7be-118">3-紧急</span><span class="sxs-lookup"><span data-stu-id="9d7be-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="9d7be-119">4-紧急情况</span><span class="sxs-lookup"><span data-stu-id="9d7be-119">4 - Emergency</span></span> <br/> |
   

