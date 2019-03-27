---
title: Users 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users 表是一个支持表。 表中的每条记录存储呼叫或在数据库中包含记录的会话所涉及的一个用户的信息。
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885559"
---
# <a name="users-table"></a><span data-ttu-id="6c1b2-104">Users 表</span><span class="sxs-lookup"><span data-stu-id="6c1b2-104">Users table</span></span>
 
<span data-ttu-id="6c1b2-105">Users 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="6c1b2-105">The Users table is a supporting table.</span></span> <span data-ttu-id="6c1b2-106">表中的每条记录存储呼叫或在数据库中包含记录的会话所涉及的一个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="6c1b2-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="6c1b2-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6c1b2-107">**Column**</span></span>|<span data-ttu-id="6c1b2-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="6c1b2-108">**Data Type**</span></span>|<span data-ttu-id="6c1b2-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="6c1b2-109">**Key/Index**</span></span>|<span data-ttu-id="6c1b2-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="6c1b2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6c1b2-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="6c1b2-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6c1b2-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6c1b2-112">datetime</span></span>  <br/> ||<span data-ttu-id="6c1b2-113">供内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="6c1b2-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="6c1b2-114">**用户 Id**</span><span class="sxs-lookup"><span data-stu-id="6c1b2-114">**UserId**</span></span> <br/> |<span data-ttu-id="6c1b2-115">int</span><span class="sxs-lookup"><span data-stu-id="6c1b2-115">int</span></span>  <br/> |<span data-ttu-id="6c1b2-116">Primary</span><span class="sxs-lookup"><span data-stu-id="6c1b2-116">Primary</span></span>  <br/> |<span data-ttu-id="6c1b2-117">标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="6c1b2-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="6c1b2-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="6c1b2-118">**UserUri**</span></span> <br/> |<span data-ttu-id="6c1b2-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6c1b2-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="6c1b2-120">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="6c1b2-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="6c1b2-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="6c1b2-121">**TenantId**</span></span> <br/> |<span data-ttu-id="6c1b2-122">int</span><span class="sxs-lookup"><span data-stu-id="6c1b2-122">int</span></span>  <br/> |<span data-ttu-id="6c1b2-123">外</span><span class="sxs-lookup"><span data-stu-id="6c1b2-123">Foreign</span></span>  <br/> |<span data-ttu-id="6c1b2-124">此用户的租户 id。</span><span class="sxs-lookup"><span data-stu-id="6c1b2-124">This user's Tenant ID.</span></span> <span data-ttu-id="6c1b2-125">请参阅[Tenants 表](tenants.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c1b2-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6c1b2-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="6c1b2-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="6c1b2-127">int</span><span class="sxs-lookup"><span data-stu-id="6c1b2-127">int</span></span>  <br/> |<span data-ttu-id="6c1b2-128">外</span><span class="sxs-lookup"><span data-stu-id="6c1b2-128">Foreign</span></span>  <br/> |<span data-ttu-id="6c1b2-129">此用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="6c1b2-129">This user's URI type.</span></span> <span data-ttu-id="6c1b2-130">请参阅[UriTypes 表](uritypes.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c1b2-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

