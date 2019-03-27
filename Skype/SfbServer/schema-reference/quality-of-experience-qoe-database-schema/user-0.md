---
title: User 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: 用户表是一个支持表，用于存储已参与记录数据库中的会话的不同用户列表。 表中的每条记录代表一个用户。
ms.openlocfilehash: fcdc8682b86432613af79d5e4d2abbdb248fef0f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881672"
---
# <a name="user-table"></a><span data-ttu-id="c50e3-104">User 表</span><span class="sxs-lookup"><span data-stu-id="c50e3-104">User table</span></span>
 
<span data-ttu-id="c50e3-105">用户表是一个支持表，用于存储已参与记录数据库中的会话的不同用户列表。</span><span class="sxs-lookup"><span data-stu-id="c50e3-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c50e3-106">表中的每条记录代表一个用户。</span><span class="sxs-lookup"><span data-stu-id="c50e3-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="c50e3-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c50e3-107">**Column**</span></span>|<span data-ttu-id="c50e3-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c50e3-108">**Data Type**</span></span>|<span data-ttu-id="c50e3-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="c50e3-109">**Key/Index**</span></span>|<span data-ttu-id="c50e3-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="c50e3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c50e3-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="c50e3-111">**UserKey**</span></span> <br/> |<span data-ttu-id="c50e3-112">int</span><span class="sxs-lookup"><span data-stu-id="c50e3-112">int</span></span>  <br/> |<span data-ttu-id="c50e3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c50e3-113">Primary</span></span>  <br/> |<span data-ttu-id="c50e3-114">标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="c50e3-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="c50e3-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="c50e3-115">**URI**</span></span> <br/> |<span data-ttu-id="c50e3-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c50e3-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c50e3-117">唯一</span><span class="sxs-lookup"><span data-stu-id="c50e3-117">Unique</span></span>  <br/> |<span data-ttu-id="c50e3-118">URI 字符串。</span><span class="sxs-lookup"><span data-stu-id="c50e3-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="c50e3-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="c50e3-119">**URIType**</span></span> <br/> |<span data-ttu-id="c50e3-120">int</span><span class="sxs-lookup"><span data-stu-id="c50e3-120">int</span></span>  <br/> ||<span data-ttu-id="c50e3-121">1 是未知的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="c50e3-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="c50e3-122">2 是用户 URI。</span><span class="sxs-lookup"><span data-stu-id="c50e3-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="c50e3-123">4 是会议 URI。</span><span class="sxs-lookup"><span data-stu-id="c50e3-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="c50e3-124">8 是电话 URI。</span><span class="sxs-lookup"><span data-stu-id="c50e3-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="c50e3-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="c50e3-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="c50e3-126">int</span><span class="sxs-lookup"><span data-stu-id="c50e3-126">int</span></span>  <br/> |<span data-ttu-id="c50e3-127">外</span><span class="sxs-lookup"><span data-stu-id="c50e3-127">Foreign</span></span>  <br/> |<span data-ttu-id="c50e3-128">租户的用户，被 tenant 表引用。</span><span class="sxs-lookup"><span data-stu-id="c50e3-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="c50e3-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="c50e3-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="c50e3-130">datetime</span><span class="sxs-lookup"><span data-stu-id="c50e3-130">datetime</span></span>  <br/> ||<span data-ttu-id="c50e3-131">最新时间戳时用户具有较差音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="c50e3-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="c50e3-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="c50e3-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="c50e3-133">datetime</span><span class="sxs-lookup"><span data-stu-id="c50e3-133">datetime</span></span>  <br/> ||<span data-ttu-id="c50e3-134">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="c50e3-134">For internal use only.</span></span>  <br/> |
   

