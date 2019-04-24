---
title: CallPriorities 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态表，用于存储可能的呼叫优先级，例如紧急、 紧迫或正常列表。
ms.openlocfilehash: faf4e7f04d7a63b096cb2369c21916e5fcb71a24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213331"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="509c7-103">CallPriorities 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="509c7-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="509c7-104">CallPriorities 表是一个静态表，用于存储可能的呼叫优先级，例如紧急、 紧迫或正常列表。</span><span class="sxs-lookup"><span data-stu-id="509c7-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="509c7-105">**列**</span><span class="sxs-lookup"><span data-stu-id="509c7-105">**Column**</span></span>|<span data-ttu-id="509c7-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="509c7-106">**Data Type**</span></span>|<span data-ttu-id="509c7-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="509c7-107">**Key/Index**</span></span>|<span data-ttu-id="509c7-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="509c7-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="509c7-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="509c7-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="509c7-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="509c7-110">tinyint</span></span>  <br/> |<span data-ttu-id="509c7-111">Primary</span><span class="sxs-lookup"><span data-stu-id="509c7-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="509c7-112">**优先级**</span><span class="sxs-lookup"><span data-stu-id="509c7-112">**Priority**</span></span> <br/> |<span data-ttu-id="509c7-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="509c7-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="509c7-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="509c7-114">Allowed values:</span></span> <br/>  <span data-ttu-id="509c7-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="509c7-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="509c7-116">1-非紧迫</span><span class="sxs-lookup"><span data-stu-id="509c7-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="509c7-117">2-普通</span><span class="sxs-lookup"><span data-stu-id="509c7-117">2 - Normal</span></span> <br/>  <span data-ttu-id="509c7-118">3-紧急</span><span class="sxs-lookup"><span data-stu-id="509c7-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="509c7-119">4-紧急</span><span class="sxs-lookup"><span data-stu-id="509c7-119">4 - Emergency</span></span> <br/> |
   

