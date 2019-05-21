---
title: UserStatistics 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是支持表。 表中的每条记录存储有关系统的单个用户使用情况的信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295690"
---
# <a name="userstatistics-table"></a><span data-ttu-id="a4225-105">UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="a4225-105">UserStatistics table</span></span>
 
<span data-ttu-id="a4225-106">UserStatistics 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="a4225-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="a4225-107">表中的每条记录存储有关系统的单个用户使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="a4225-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="a4225-108">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a4225-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a4225-109">**列**</span><span class="sxs-lookup"><span data-stu-id="a4225-109">**Column**</span></span>|<span data-ttu-id="a4225-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a4225-110">**Data Type**</span></span>|<span data-ttu-id="a4225-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a4225-111">**Key/Index**</span></span>|<span data-ttu-id="a4225-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a4225-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a4225-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="a4225-113">**UserId**</span></span> <br/> |<span data-ttu-id="a4225-114">int</span><span class="sxs-lookup"><span data-stu-id="a4225-114">int</span></span>  <br/> |<span data-ttu-id="a4225-115">Primary</span><span class="sxs-lookup"><span data-stu-id="a4225-115">Primary</span></span>  <br/> |<span data-ttu-id="a4225-116">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="a4225-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="a4225-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="a4225-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="a4225-118">datetime</span><span class="sxs-lookup"><span data-stu-id="a4225-118">datetime</span></span>  <br/> ||<span data-ttu-id="a4225-119">上次登录用户的时间。</span><span class="sxs-lookup"><span data-stu-id="a4225-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="a4225-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="a4225-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="a4225-121">datetime</span><span class="sxs-lookup"><span data-stu-id="a4225-121">datetime</span></span>  <br/> ||<span data-ttu-id="a4225-122">上次用户组织会议的时间。</span><span class="sxs-lookup"><span data-stu-id="a4225-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="a4225-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="a4225-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="a4225-124">datetime</span><span class="sxs-lookup"><span data-stu-id="a4225-124">datetime</span></span>  <br/> ||<span data-ttu-id="a4225-125">上次用户遇到通话失败的时间。</span><span class="sxs-lookup"><span data-stu-id="a4225-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="a4225-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="a4225-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="a4225-127">datetime</span><span class="sxs-lookup"><span data-stu-id="a4225-127">datetime</span></span>  <br/> ||<span data-ttu-id="a4225-128">上次用户遇到作为会议组织者的呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="a4225-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

