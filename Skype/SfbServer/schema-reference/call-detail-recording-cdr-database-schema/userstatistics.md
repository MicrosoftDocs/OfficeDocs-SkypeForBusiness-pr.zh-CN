---
title: UserStatistics 表
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是一个支持表。 表中的每条记录存储有关单个用户对系统使用情况的信息。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813102"
---
# <a name="userstatistics-table"></a><span data-ttu-id="fc0af-105">UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="fc0af-105">UserStatistics table</span></span>
 
<span data-ttu-id="fc0af-106">UserStatistics 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="fc0af-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="fc0af-107">表中的每条记录存储有关单个用户对系统使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="fc0af-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="fc0af-108">此表在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fc0af-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="fc0af-109">**列**</span><span class="sxs-lookup"><span data-stu-id="fc0af-109">**Column**</span></span>|<span data-ttu-id="fc0af-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fc0af-110">**Data Type**</span></span>|<span data-ttu-id="fc0af-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="fc0af-111">**Key/Index**</span></span>|<span data-ttu-id="fc0af-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="fc0af-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc0af-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="fc0af-113">**UserId**</span></span> <br/> |<span data-ttu-id="fc0af-114">int</span><span class="sxs-lookup"><span data-stu-id="fc0af-114">int</span></span>  <br/> |<span data-ttu-id="fc0af-115">主</span><span class="sxs-lookup"><span data-stu-id="fc0af-115">Primary</span></span>  <br/> |<span data-ttu-id="fc0af-116">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="fc0af-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="fc0af-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="fc0af-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="fc0af-118">datetime</span><span class="sxs-lookup"><span data-stu-id="fc0af-118">datetime</span></span>  <br/> ||<span data-ttu-id="fc0af-119">用户上次登录时间。</span><span class="sxs-lookup"><span data-stu-id="fc0af-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="fc0af-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="fc0af-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="fc0af-121">datetime</span><span class="sxs-lookup"><span data-stu-id="fc0af-121">datetime</span></span>  <br/> ||<span data-ttu-id="fc0af-122">用户上次组织会议的时间。</span><span class="sxs-lookup"><span data-stu-id="fc0af-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="fc0af-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="fc0af-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="fc0af-124">datetime</span><span class="sxs-lookup"><span data-stu-id="fc0af-124">datetime</span></span>  <br/> ||<span data-ttu-id="fc0af-125">用户上次遇到呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="fc0af-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="fc0af-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="fc0af-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="fc0af-127">datetime</span><span class="sxs-lookup"><span data-stu-id="fc0af-127">datetime</span></span>  <br/> ||<span data-ttu-id="fc0af-128">用户上次以会议组织者身份遇到呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="fc0af-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

