---
title: Users 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: 用户表是支持表。 表中的每条记录存储调用或数据库中具有记录的会话中涉及的一个用户有关的信息。
ms.openlocfilehash: b14350d060485a57b4af42cbfe26db729872f6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="users-table"></a><span data-ttu-id="2afc5-104">Users 表</span><span class="sxs-lookup"><span data-stu-id="2afc5-104">Users table</span></span>
 
<span data-ttu-id="2afc5-105">用户表是支持表。</span><span class="sxs-lookup"><span data-stu-id="2afc5-105">The Users table is a supporting table.</span></span> <span data-ttu-id="2afc5-106">表中的每条记录存储调用或数据库中具有记录的会话中涉及的一个用户有关的信息。</span><span class="sxs-lookup"><span data-stu-id="2afc5-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="2afc5-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2afc5-107">**Column**</span></span>|<span data-ttu-id="2afc5-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2afc5-108">**Data Type**</span></span>|<span data-ttu-id="2afc5-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="2afc5-109">**Key/Index**</span></span>|<span data-ttu-id="2afc5-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="2afc5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2afc5-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2afc5-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2afc5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2afc5-112">datetime</span></span>  <br/> ||<span data-ttu-id="2afc5-113">供内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="2afc5-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="2afc5-114">**用户 Id**</span><span class="sxs-lookup"><span data-stu-id="2afc5-114">**UserId**</span></span> <br/> |<span data-ttu-id="2afc5-115">int</span><span class="sxs-lookup"><span data-stu-id="2afc5-115">int</span></span>  <br/> |<span data-ttu-id="2afc5-116">Primary</span><span class="sxs-lookup"><span data-stu-id="2afc5-116">Primary</span></span>  <br/> |<span data-ttu-id="2afc5-117">识别该用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="2afc5-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="2afc5-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="2afc5-118">**UserUri**</span></span> <br/> |<span data-ttu-id="2afc5-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="2afc5-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="2afc5-120">用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="2afc5-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="2afc5-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="2afc5-121">**TenantId**</span></span> <br/> |<span data-ttu-id="2afc5-122">int</span><span class="sxs-lookup"><span data-stu-id="2afc5-122">int</span></span>  <br/> |<span data-ttu-id="2afc5-123">外</span><span class="sxs-lookup"><span data-stu-id="2afc5-123">Foreign</span></span>  <br/> |<span data-ttu-id="2afc5-124">此用户的租户 id。</span><span class="sxs-lookup"><span data-stu-id="2afc5-124">This user's Tenant ID.</span></span> <span data-ttu-id="2afc5-125">[租户表](tenants.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="2afc5-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2afc5-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="2afc5-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="2afc5-127">int</span><span class="sxs-lookup"><span data-stu-id="2afc5-127">int</span></span>  <br/> |<span data-ttu-id="2afc5-128">外</span><span class="sxs-lookup"><span data-stu-id="2afc5-128">Foreign</span></span>  <br/> |<span data-ttu-id="2afc5-129">此用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="2afc5-129">This user's URI type.</span></span> <span data-ttu-id="2afc5-130">[UriTypes 表](uritypes.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="2afc5-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

