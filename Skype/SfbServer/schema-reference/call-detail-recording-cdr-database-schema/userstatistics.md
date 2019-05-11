---
title: UserStatistics 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是一个支持表。 每个表中的记录存储有关单个用户的使用情况的系统的信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: c2e0acffa7b75b3c54781e3e4e9a8b033be5e440
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929978"
---
# <a name="userstatistics-table"></a><span data-ttu-id="0761b-105">UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="0761b-105">UserStatistics table</span></span>
 
<span data-ttu-id="0761b-106">UserStatistics 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="0761b-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="0761b-107">每个表中的记录存储有关单个用户的使用情况的系统的信息。</span><span class="sxs-lookup"><span data-stu-id="0761b-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="0761b-108">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="0761b-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="0761b-109">**列**</span><span class="sxs-lookup"><span data-stu-id="0761b-109">**Column**</span></span>|<span data-ttu-id="0761b-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0761b-110">**Data Type**</span></span>|<span data-ttu-id="0761b-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="0761b-111">**Key/Index**</span></span>|<span data-ttu-id="0761b-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0761b-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0761b-113">**用户 Id**</span><span class="sxs-lookup"><span data-stu-id="0761b-113">**UserId**</span></span> <br/> |<span data-ttu-id="0761b-114">int</span><span class="sxs-lookup"><span data-stu-id="0761b-114">int</span></span>  <br/> |<span data-ttu-id="0761b-115">Primary</span><span class="sxs-lookup"><span data-stu-id="0761b-115">Primary</span></span>  <br/> |<span data-ttu-id="0761b-116">标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="0761b-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="0761b-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="0761b-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="0761b-118">datetime</span><span class="sxs-lookup"><span data-stu-id="0761b-118">datetime</span></span>  <br/> ||<span data-ttu-id="0761b-119">最后一次用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="0761b-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="0761b-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="0761b-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="0761b-121">datetime</span><span class="sxs-lookup"><span data-stu-id="0761b-121">datetime</span></span>  <br/> ||<span data-ttu-id="0761b-122">最后一次用户组织会议。</span><span class="sxs-lookup"><span data-stu-id="0761b-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="0761b-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="0761b-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="0761b-124">datetime</span><span class="sxs-lookup"><span data-stu-id="0761b-124">datetime</span></span>  <br/> ||<span data-ttu-id="0761b-125">最后一次用户遇到呼叫失败。</span><span class="sxs-lookup"><span data-stu-id="0761b-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="0761b-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="0761b-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="0761b-127">datetime</span><span class="sxs-lookup"><span data-stu-id="0761b-127">datetime</span></span>  <br/> ||<span data-ttu-id="0761b-128">最后一次用户作为会议组织者遇到呼叫失败。</span><span class="sxs-lookup"><span data-stu-id="0761b-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

