---
title: UserStatistics 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是支持表。 表中的每条记录存储系统的单个用户使用的信息。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a><span data-ttu-id="10698-105">UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="10698-105">UserStatistics table</span></span>
 
<span data-ttu-id="10698-106">UserStatistics 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="10698-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="10698-107">表中的每条记录存储系统的单个用户使用的信息。</span><span class="sxs-lookup"><span data-stu-id="10698-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="10698-108">在 Microsoft Lync Server 2013 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="10698-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="10698-109">**列**</span><span class="sxs-lookup"><span data-stu-id="10698-109">**Column**</span></span>|<span data-ttu-id="10698-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="10698-110">**Data Type**</span></span>|<span data-ttu-id="10698-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="10698-111">**Key/Index**</span></span>|<span data-ttu-id="10698-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="10698-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10698-113">**用户 Id**</span><span class="sxs-lookup"><span data-stu-id="10698-113">**UserId**</span></span> <br/> |<span data-ttu-id="10698-114">int</span><span class="sxs-lookup"><span data-stu-id="10698-114">int</span></span>  <br/> |<span data-ttu-id="10698-115">Primary</span><span class="sxs-lookup"><span data-stu-id="10698-115">Primary</span></span>  <br/> |<span data-ttu-id="10698-116">识别该用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="10698-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="10698-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="10698-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="10698-118">datetime</span><span class="sxs-lookup"><span data-stu-id="10698-118">datetime</span></span>  <br/> ||<span data-ttu-id="10698-119">上一次用户登录。</span><span class="sxs-lookup"><span data-stu-id="10698-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="10698-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="10698-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="10698-121">datetime</span><span class="sxs-lookup"><span data-stu-id="10698-121">datetime</span></span>  <br/> ||<span data-ttu-id="10698-122">上一次用户组织的会议。</span><span class="sxs-lookup"><span data-stu-id="10698-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="10698-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="10698-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="10698-124">datetime</span><span class="sxs-lookup"><span data-stu-id="10698-124">datetime</span></span>  <br/> ||<span data-ttu-id="10698-125">上一次用户遇到呼叫失败。</span><span class="sxs-lookup"><span data-stu-id="10698-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="10698-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="10698-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="10698-127">datetime</span><span class="sxs-lookup"><span data-stu-id="10698-127">datetime</span></span>  <br/> ||<span data-ttu-id="10698-128">上一次用户体验作为会议组织者调用失败。</span><span class="sxs-lookup"><span data-stu-id="10698-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

