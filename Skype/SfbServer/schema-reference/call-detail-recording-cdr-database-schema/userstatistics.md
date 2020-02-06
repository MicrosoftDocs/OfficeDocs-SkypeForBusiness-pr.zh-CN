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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是支持表。 表中的每条记录存储有关系统的单个用户使用情况的信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814790"
---
# <a name="userstatistics-table"></a><span data-ttu-id="d5f26-105">UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="d5f26-105">UserStatistics table</span></span>
 
<span data-ttu-id="d5f26-106">UserStatistics 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="d5f26-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="d5f26-107">表中的每条记录存储有关系统的单个用户使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="d5f26-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="d5f26-108">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d5f26-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d5f26-109">**列**</span><span class="sxs-lookup"><span data-stu-id="d5f26-109">**Column**</span></span>|<span data-ttu-id="d5f26-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d5f26-110">**Data Type**</span></span>|<span data-ttu-id="d5f26-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d5f26-111">**Key/Index**</span></span>|<span data-ttu-id="d5f26-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d5f26-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5f26-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="d5f26-113">**UserId**</span></span> <br/> |<span data-ttu-id="d5f26-114">int</span><span class="sxs-lookup"><span data-stu-id="d5f26-114">int</span></span>  <br/> |<span data-ttu-id="d5f26-115">Primary</span><span class="sxs-lookup"><span data-stu-id="d5f26-115">Primary</span></span>  <br/> |<span data-ttu-id="d5f26-116">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="d5f26-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d5f26-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="d5f26-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="d5f26-118">datetime</span><span class="sxs-lookup"><span data-stu-id="d5f26-118">datetime</span></span>  <br/> ||<span data-ttu-id="d5f26-119">上次登录用户的时间。</span><span class="sxs-lookup"><span data-stu-id="d5f26-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="d5f26-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="d5f26-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="d5f26-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d5f26-121">datetime</span></span>  <br/> ||<span data-ttu-id="d5f26-122">上次用户组织会议的时间。</span><span class="sxs-lookup"><span data-stu-id="d5f26-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="d5f26-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="d5f26-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="d5f26-124">datetime</span><span class="sxs-lookup"><span data-stu-id="d5f26-124">datetime</span></span>  <br/> ||<span data-ttu-id="d5f26-125">上次用户遇到通话失败的时间。</span><span class="sxs-lookup"><span data-stu-id="d5f26-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="d5f26-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="d5f26-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="d5f26-127">datetime</span><span class="sxs-lookup"><span data-stu-id="d5f26-127">datetime</span></span>  <br/> ||<span data-ttu-id="d5f26-128">上次用户遇到作为会议组织者的呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="d5f26-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

