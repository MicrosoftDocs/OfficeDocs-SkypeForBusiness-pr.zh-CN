---
title: 用户表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: User 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户的列表。该表中的每条记录表示一个用户。
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800072"
---
# <a name="user-table"></a><span data-ttu-id="36dc7-104">用户表</span><span class="sxs-lookup"><span data-stu-id="36dc7-104">User table</span></span>
 
<span data-ttu-id="36dc7-p102">User 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户的列表。该表中的每条记录表示一个用户。</span><span class="sxs-lookup"><span data-stu-id="36dc7-p102">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="36dc7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="36dc7-107">**Column**</span></span>|<span data-ttu-id="36dc7-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="36dc7-108">**Data Type**</span></span>|<span data-ttu-id="36dc7-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="36dc7-109">**Key/Index**</span></span>|<span data-ttu-id="36dc7-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="36dc7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="36dc7-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="36dc7-111">**UserKey**</span></span> <br/> |<span data-ttu-id="36dc7-112">int</span><span class="sxs-lookup"><span data-stu-id="36dc7-112">int</span></span>  <br/> |<span data-ttu-id="36dc7-113">主</span><span class="sxs-lookup"><span data-stu-id="36dc7-113">Primary</span></span>  <br/> |<span data-ttu-id="36dc7-114">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="36dc7-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="36dc7-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="36dc7-115">**URI**</span></span> <br/> |<span data-ttu-id="36dc7-116">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="36dc7-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="36dc7-117">独特</span><span class="sxs-lookup"><span data-stu-id="36dc7-117">Unique</span></span>  <br/> |<span data-ttu-id="36dc7-118">URI 字符串。</span><span class="sxs-lookup"><span data-stu-id="36dc7-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="36dc7-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="36dc7-119">**URIType**</span></span> <br/> |<span data-ttu-id="36dc7-120">int</span><span class="sxs-lookup"><span data-stu-id="36dc7-120">int</span></span>  <br/> ||<span data-ttu-id="36dc7-121">1 是未知 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="36dc7-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="36dc7-122">2 是用户 URI。</span><span class="sxs-lookup"><span data-stu-id="36dc7-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="36dc7-123">4 是会议 URI。</span><span class="sxs-lookup"><span data-stu-id="36dc7-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="36dc7-124">8 是电话 URI。</span><span class="sxs-lookup"><span data-stu-id="36dc7-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="36dc7-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="36dc7-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="36dc7-126">int</span><span class="sxs-lookup"><span data-stu-id="36dc7-126">int</span></span>  <br/> |<span data-ttu-id="36dc7-127">Foreign</span><span class="sxs-lookup"><span data-stu-id="36dc7-127">Foreign</span></span>  <br/> |<span data-ttu-id="36dc7-128">用户的租户，被 Tenant 表引用。</span><span class="sxs-lookup"><span data-stu-id="36dc7-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="36dc7-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="36dc7-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="36dc7-130">datetime</span><span class="sxs-lookup"><span data-stu-id="36dc7-130">datetime</span></span>  <br/> ||<span data-ttu-id="36dc7-131">用户具有较差音频呼叫时的最新时间戳。</span><span class="sxs-lookup"><span data-stu-id="36dc7-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="36dc7-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="36dc7-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="36dc7-133">datetime</span><span class="sxs-lookup"><span data-stu-id="36dc7-133">datetime</span></span>  <br/> ||<span data-ttu-id="36dc7-134">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="36dc7-134">For internal use only.</span></span>  <br/> |
   

