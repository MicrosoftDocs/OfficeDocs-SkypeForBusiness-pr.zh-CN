---
title: User 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: 用户表是一个支持的表来存储各种参加会话记录在数据库中的用户的列表。 每个表中的记录表示一个用户。
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a><span data-ttu-id="0a934-104">User 表</span><span class="sxs-lookup"><span data-stu-id="0a934-104">User table</span></span>
 
<span data-ttu-id="0a934-105">用户表是一个支持的表来存储各种参加会话记录在数据库中的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="0a934-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0a934-106">每个表中的记录表示一个用户。</span><span class="sxs-lookup"><span data-stu-id="0a934-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="0a934-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0a934-107">**Column**</span></span>|<span data-ttu-id="0a934-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0a934-108">**Data Type**</span></span>|<span data-ttu-id="0a934-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="0a934-109">**Key/Index**</span></span>|<span data-ttu-id="0a934-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0a934-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0a934-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="0a934-111">**UserKey**</span></span> <br/> |<span data-ttu-id="0a934-112">int</span><span class="sxs-lookup"><span data-stu-id="0a934-112">int</span></span>  <br/> |<span data-ttu-id="0a934-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0a934-113">Primary</span></span>  <br/> |<span data-ttu-id="0a934-114">识别该用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="0a934-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="0a934-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="0a934-115">**URI**</span></span> <br/> |<span data-ttu-id="0a934-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0a934-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0a934-117">唯一</span><span class="sxs-lookup"><span data-stu-id="0a934-117">Unique</span></span>  <br/> |<span data-ttu-id="0a934-118">URI 字符串。</span><span class="sxs-lookup"><span data-stu-id="0a934-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="0a934-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="0a934-119">**URIType**</span></span> <br/> |<span data-ttu-id="0a934-120">int</span><span class="sxs-lookup"><span data-stu-id="0a934-120">int</span></span>  <br/> ||<span data-ttu-id="0a934-121">1 是 URI 类型未知。</span><span class="sxs-lookup"><span data-stu-id="0a934-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="0a934-122">2 是用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="0a934-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="0a934-123">4 是 URI 的会议。</span><span class="sxs-lookup"><span data-stu-id="0a934-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="0a934-124">8 是电话 URI。</span><span class="sxs-lookup"><span data-stu-id="0a934-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="0a934-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="0a934-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="0a934-126">int</span><span class="sxs-lookup"><span data-stu-id="0a934-126">int</span></span>  <br/> |<span data-ttu-id="0a934-127">外</span><span class="sxs-lookup"><span data-stu-id="0a934-127">Foreign</span></span>  <br/> |<span data-ttu-id="0a934-128">客户端的用户，从租户表引用。</span><span class="sxs-lookup"><span data-stu-id="0a934-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="0a934-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="0a934-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="0a934-130">datetime</span><span class="sxs-lookup"><span data-stu-id="0a934-130">datetime</span></span>  <br/> ||<span data-ttu-id="0a934-131">最新时间戳时用户有较差的音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="0a934-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="0a934-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="0a934-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="0a934-133">datetime</span><span class="sxs-lookup"><span data-stu-id="0a934-133">datetime</span></span>  <br/> ||<span data-ttu-id="0a934-134">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="0a934-134">For internal use only.</span></span>  <br/> |
   

