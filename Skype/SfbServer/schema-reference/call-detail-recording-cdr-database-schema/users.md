---
title: Users 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: "\"用户\" 表是支持表。 表中的每条记录存储有关在数据库中具有记录的通话或会话中涉及的一个用户的信息。"
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814800"
---
# <a name="users-table"></a><span data-ttu-id="e7a8a-104">Users 表</span><span class="sxs-lookup"><span data-stu-id="e7a8a-104">Users table</span></span>
 
<span data-ttu-id="e7a8a-105">"用户" 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="e7a8a-105">The Users table is a supporting table.</span></span> <span data-ttu-id="e7a8a-106">表中的每条记录存储有关在数据库中具有记录的通话或会话中涉及的一个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="e7a8a-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="e7a8a-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e7a8a-107">**Column**</span></span>|<span data-ttu-id="e7a8a-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e7a8a-108">**Data Type**</span></span>|<span data-ttu-id="e7a8a-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="e7a8a-109">**Key/Index**</span></span>|<span data-ttu-id="e7a8a-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e7a8a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7a8a-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="e7a8a-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e7a8a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e7a8a-112">datetime</span></span>  <br/> ||<span data-ttu-id="e7a8a-113">供内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="e7a8a-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="e7a8a-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="e7a8a-114">**UserId**</span></span> <br/> |<span data-ttu-id="e7a8a-115">int</span><span class="sxs-lookup"><span data-stu-id="e7a8a-115">int</span></span>  <br/> |<span data-ttu-id="e7a8a-116">Primary</span><span class="sxs-lookup"><span data-stu-id="e7a8a-116">Primary</span></span>  <br/> |<span data-ttu-id="e7a8a-117">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="e7a8a-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e7a8a-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="e7a8a-118">**UserUri**</span></span> <br/> |<span data-ttu-id="e7a8a-119">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e7a8a-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="e7a8a-120">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="e7a8a-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="e7a8a-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="e7a8a-121">**TenantId**</span></span> <br/> |<span data-ttu-id="e7a8a-122">int</span><span class="sxs-lookup"><span data-stu-id="e7a8a-122">int</span></span>  <br/> |<span data-ttu-id="e7a8a-123">外表</span><span class="sxs-lookup"><span data-stu-id="e7a8a-123">Foreign</span></span>  <br/> |<span data-ttu-id="e7a8a-124">此用户的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="e7a8a-124">This user's Tenant ID.</span></span> <span data-ttu-id="e7a8a-125">有关详细信息，请参阅[租户表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="e7a8a-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e7a8a-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="e7a8a-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="e7a8a-127">int</span><span class="sxs-lookup"><span data-stu-id="e7a8a-127">int</span></span>  <br/> |<span data-ttu-id="e7a8a-128">外表</span><span class="sxs-lookup"><span data-stu-id="e7a8a-128">Foreign</span></span>  <br/> |<span data-ttu-id="e7a8a-129">此用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="e7a8a-129">This user's URI type.</span></span> <span data-ttu-id="e7a8a-130">有关详细信息，请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="e7a8a-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

