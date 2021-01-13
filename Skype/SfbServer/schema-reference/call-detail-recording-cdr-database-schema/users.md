---
title: Users 表
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users 表是一个支持表。 表中的每条记录都存储有关数据库中具有记录的呼叫或会话中涉及的一个用户的信息。
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831612"
---
# <a name="users-table"></a><span data-ttu-id="98216-104">Users 表</span><span class="sxs-lookup"><span data-stu-id="98216-104">Users table</span></span>
 
<span data-ttu-id="98216-105">Users 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="98216-105">The Users table is a supporting table.</span></span> <span data-ttu-id="98216-106">表中的每条记录都存储有关数据库中具有记录的呼叫或会话中涉及的一个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="98216-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="98216-107">**列**</span><span class="sxs-lookup"><span data-stu-id="98216-107">**Column**</span></span>|<span data-ttu-id="98216-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="98216-108">**Data Type**</span></span>|<span data-ttu-id="98216-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="98216-109">**Key/Index**</span></span>|<span data-ttu-id="98216-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="98216-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="98216-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="98216-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="98216-112">datetime</span><span class="sxs-lookup"><span data-stu-id="98216-112">datetime</span></span>  <br/> ||<span data-ttu-id="98216-113">供内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="98216-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="98216-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="98216-114">**UserId**</span></span> <br/> |<span data-ttu-id="98216-115">int</span><span class="sxs-lookup"><span data-stu-id="98216-115">int</span></span>  <br/> |<span data-ttu-id="98216-116">主</span><span class="sxs-lookup"><span data-stu-id="98216-116">Primary</span></span>  <br/> |<span data-ttu-id="98216-117">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="98216-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="98216-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="98216-118">**UserUri**</span></span> <br/> |<span data-ttu-id="98216-119">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="98216-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="98216-120">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="98216-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="98216-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="98216-121">**TenantId**</span></span> <br/> |<span data-ttu-id="98216-122">int</span><span class="sxs-lookup"><span data-stu-id="98216-122">int</span></span>  <br/> |<span data-ttu-id="98216-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="98216-123">Foreign</span></span>  <br/> |<span data-ttu-id="98216-124">此用户的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="98216-124">This user's Tenant ID.</span></span> <span data-ttu-id="98216-125">有关详细信息 [，请参阅"租户](tenants.md) "表。</span><span class="sxs-lookup"><span data-stu-id="98216-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="98216-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="98216-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="98216-127">int</span><span class="sxs-lookup"><span data-stu-id="98216-127">int</span></span>  <br/> |<span data-ttu-id="98216-128">Foreign</span><span class="sxs-lookup"><span data-stu-id="98216-128">Foreign</span></span>  <br/> |<span data-ttu-id="98216-129">此用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="98216-129">This user's URI type.</span></span> <span data-ttu-id="98216-130">有关详细信息， [请参阅 UriTypes](uritypes.md) 表。</span><span class="sxs-lookup"><span data-stu-id="98216-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

