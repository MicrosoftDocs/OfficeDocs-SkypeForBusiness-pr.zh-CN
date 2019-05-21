---
title: User 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: 用户表是一个支持表, 用于存储参与数据库中记录的会话的各种用户的列表。 表中的每条记录表示一个用户。
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294612"
---
# <a name="user-table"></a><span data-ttu-id="ddf44-104">User 表</span><span class="sxs-lookup"><span data-stu-id="ddf44-104">User table</span></span>
 
<span data-ttu-id="ddf44-105">用户表是一个支持表, 用于存储参与数据库中记录的会话的各种用户的列表。</span><span class="sxs-lookup"><span data-stu-id="ddf44-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ddf44-106">表中的每条记录表示一个用户。</span><span class="sxs-lookup"><span data-stu-id="ddf44-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="ddf44-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ddf44-107">**Column**</span></span>|<span data-ttu-id="ddf44-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ddf44-108">**Data Type**</span></span>|<span data-ttu-id="ddf44-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="ddf44-109">**Key/Index**</span></span>|<span data-ttu-id="ddf44-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="ddf44-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ddf44-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="ddf44-111">**UserKey**</span></span> <br/> |<span data-ttu-id="ddf44-112">int</span><span class="sxs-lookup"><span data-stu-id="ddf44-112">int</span></span>  <br/> |<span data-ttu-id="ddf44-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ddf44-113">Primary</span></span>  <br/> |<span data-ttu-id="ddf44-114">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="ddf44-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="ddf44-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="ddf44-115">**URI**</span></span> <br/> |<span data-ttu-id="ddf44-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ddf44-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ddf44-117">唯一</span><span class="sxs-lookup"><span data-stu-id="ddf44-117">Unique</span></span>  <br/> |<span data-ttu-id="ddf44-118">URI 字符串。</span><span class="sxs-lookup"><span data-stu-id="ddf44-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="ddf44-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="ddf44-119">**URIType**</span></span> <br/> |<span data-ttu-id="ddf44-120">int</span><span class="sxs-lookup"><span data-stu-id="ddf44-120">int</span></span>  <br/> ||<span data-ttu-id="ddf44-121">1是未知的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="ddf44-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="ddf44-122">2是用户 URI。</span><span class="sxs-lookup"><span data-stu-id="ddf44-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="ddf44-123">4是会议 URI。</span><span class="sxs-lookup"><span data-stu-id="ddf44-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="ddf44-124">8是电话 URI。</span><span class="sxs-lookup"><span data-stu-id="ddf44-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="ddf44-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="ddf44-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="ddf44-126">int</span><span class="sxs-lookup"><span data-stu-id="ddf44-126">int</span></span>  <br/> |<span data-ttu-id="ddf44-127">外表</span><span class="sxs-lookup"><span data-stu-id="ddf44-127">Foreign</span></span>  <br/> |<span data-ttu-id="ddf44-128">用户的租户, 从租户表引用。</span><span class="sxs-lookup"><span data-stu-id="ddf44-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="ddf44-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="ddf44-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="ddf44-130">datetime</span><span class="sxs-lookup"><span data-stu-id="ddf44-130">datetime</span></span>  <br/> ||<span data-ttu-id="ddf44-131">当用户的音频通话较差时的最晚时间戳。</span><span class="sxs-lookup"><span data-stu-id="ddf44-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="ddf44-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="ddf44-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ddf44-133">datetime</span><span class="sxs-lookup"><span data-stu-id="ddf44-133">datetime</span></span>  <br/> ||<span data-ttu-id="ddf44-134">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="ddf44-134">For internal use only.</span></span>  <br/> |
   

