---
title: UserStatistics 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是一个支持表。 每个表中的记录存储有关单个用户的使用情况的系统的信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883593"
---
# <a name="userstatistics-table"></a><span data-ttu-id="d0c84-105">UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="d0c84-105">UserStatistics table</span></span>
 
<span data-ttu-id="d0c84-106">UserStatistics 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="d0c84-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="d0c84-107">每个表中的记录存储有关单个用户的使用情况的系统的信息。</span><span class="sxs-lookup"><span data-stu-id="d0c84-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="d0c84-108">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d0c84-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d0c84-109">**列**</span><span class="sxs-lookup"><span data-stu-id="d0c84-109">**Column**</span></span>|<span data-ttu-id="d0c84-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d0c84-110">**Data Type**</span></span>|<span data-ttu-id="d0c84-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d0c84-111">**Key/Index**</span></span>|<span data-ttu-id="d0c84-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d0c84-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d0c84-113">**用户 Id**</span><span class="sxs-lookup"><span data-stu-id="d0c84-113">**UserId**</span></span> <br/> |<span data-ttu-id="d0c84-114">int</span><span class="sxs-lookup"><span data-stu-id="d0c84-114">int</span></span>  <br/> |<span data-ttu-id="d0c84-115">Primary</span><span class="sxs-lookup"><span data-stu-id="d0c84-115">Primary</span></span>  <br/> |<span data-ttu-id="d0c84-116">标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="d0c84-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d0c84-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="d0c84-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="d0c84-118">datetime</span><span class="sxs-lookup"><span data-stu-id="d0c84-118">datetime</span></span>  <br/> ||<span data-ttu-id="d0c84-119">最后一次用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="d0c84-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="d0c84-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="d0c84-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="d0c84-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d0c84-121">datetime</span></span>  <br/> ||<span data-ttu-id="d0c84-122">最后一次用户组织会议。</span><span class="sxs-lookup"><span data-stu-id="d0c84-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="d0c84-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="d0c84-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="d0c84-124">datetime</span><span class="sxs-lookup"><span data-stu-id="d0c84-124">datetime</span></span>  <br/> ||<span data-ttu-id="d0c84-125">最后一次用户遇到呼叫失败。</span><span class="sxs-lookup"><span data-stu-id="d0c84-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="d0c84-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="d0c84-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="d0c84-127">datetime</span><span class="sxs-lookup"><span data-stu-id="d0c84-127">datetime</span></span>  <br/> ||<span data-ttu-id="d0c84-128">最后一次用户作为会议组织者遇到呼叫失败。</span><span class="sxs-lookup"><span data-stu-id="d0c84-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

