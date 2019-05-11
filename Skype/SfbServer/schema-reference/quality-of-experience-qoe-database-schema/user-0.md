---
title: User 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: 用户表是一个支持表，用于存储已参与记录数据库中的会话的不同用户列表。 表中的每条记录代表一个用户。
ms.openlocfilehash: 426d272a5c8bee2fd37511edc62bcb3e1a0c533e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907036"
---
# <a name="user-table"></a><span data-ttu-id="9d083-104">User 表</span><span class="sxs-lookup"><span data-stu-id="9d083-104">User table</span></span>
 
<span data-ttu-id="9d083-105">用户表是一个支持表，用于存储已参与记录数据库中的会话的不同用户列表。</span><span class="sxs-lookup"><span data-stu-id="9d083-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="9d083-106">表中的每条记录代表一个用户。</span><span class="sxs-lookup"><span data-stu-id="9d083-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="9d083-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9d083-107">**Column**</span></span>|<span data-ttu-id="9d083-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9d083-108">**Data Type**</span></span>|<span data-ttu-id="9d083-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9d083-109">**Key/Index**</span></span>|<span data-ttu-id="9d083-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9d083-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d083-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="9d083-111">**UserKey**</span></span> <br/> |<span data-ttu-id="9d083-112">int</span><span class="sxs-lookup"><span data-stu-id="9d083-112">int</span></span>  <br/> |<span data-ttu-id="9d083-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9d083-113">Primary</span></span>  <br/> |<span data-ttu-id="9d083-114">标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="9d083-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="9d083-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="9d083-115">**URI**</span></span> <br/> |<span data-ttu-id="9d083-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9d083-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="9d083-117">唯一</span><span class="sxs-lookup"><span data-stu-id="9d083-117">Unique</span></span>  <br/> |<span data-ttu-id="9d083-118">URI 字符串。</span><span class="sxs-lookup"><span data-stu-id="9d083-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="9d083-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="9d083-119">**URIType**</span></span> <br/> |<span data-ttu-id="9d083-120">int</span><span class="sxs-lookup"><span data-stu-id="9d083-120">int</span></span>  <br/> ||<span data-ttu-id="9d083-121">1 是未知的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="9d083-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="9d083-122">2 是用户 URI。</span><span class="sxs-lookup"><span data-stu-id="9d083-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="9d083-123">4 是会议 URI。</span><span class="sxs-lookup"><span data-stu-id="9d083-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="9d083-124">8 是电话 URI。</span><span class="sxs-lookup"><span data-stu-id="9d083-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="9d083-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="9d083-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="9d083-126">int</span><span class="sxs-lookup"><span data-stu-id="9d083-126">int</span></span>  <br/> |<span data-ttu-id="9d083-127">外</span><span class="sxs-lookup"><span data-stu-id="9d083-127">Foreign</span></span>  <br/> |<span data-ttu-id="9d083-128">租户的用户，被 tenant 表引用。</span><span class="sxs-lookup"><span data-stu-id="9d083-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="9d083-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="9d083-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="9d083-130">datetime</span><span class="sxs-lookup"><span data-stu-id="9d083-130">datetime</span></span>  <br/> ||<span data-ttu-id="9d083-131">最新时间戳时用户具有较差音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="9d083-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="9d083-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="9d083-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="9d083-133">datetime</span><span class="sxs-lookup"><span data-stu-id="9d083-133">datetime</span></span>  <br/> ||<span data-ttu-id="9d083-134">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="9d083-134">For internal use only.</span></span>  <br/> |
   

