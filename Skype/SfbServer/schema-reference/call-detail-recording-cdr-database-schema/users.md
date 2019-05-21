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
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: "\"用户\" 表是支持表。 表中的每条记录存储有关在数据库中具有记录的通话或会话中涉及的一个用户的信息。"
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295697"
---
# <a name="users-table"></a><span data-ttu-id="bfdf5-104">Users 表</span><span class="sxs-lookup"><span data-stu-id="bfdf5-104">Users table</span></span>
 
<span data-ttu-id="bfdf5-105">"用户" 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="bfdf5-105">The Users table is a supporting table.</span></span> <span data-ttu-id="bfdf5-106">表中的每条记录存储有关在数据库中具有记录的通话或会话中涉及的一个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="bfdf5-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="bfdf5-107">**列**</span><span class="sxs-lookup"><span data-stu-id="bfdf5-107">**Column**</span></span>|<span data-ttu-id="bfdf5-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="bfdf5-108">**Data Type**</span></span>|<span data-ttu-id="bfdf5-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="bfdf5-109">**Key/Index**</span></span>|<span data-ttu-id="bfdf5-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="bfdf5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bfdf5-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="bfdf5-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="bfdf5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="bfdf5-112">datetime</span></span>  <br/> ||<span data-ttu-id="bfdf5-113">供内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="bfdf5-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="bfdf5-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="bfdf5-114">**UserId**</span></span> <br/> |<span data-ttu-id="bfdf5-115">int</span><span class="sxs-lookup"><span data-stu-id="bfdf5-115">int</span></span>  <br/> |<span data-ttu-id="bfdf5-116">Primary</span><span class="sxs-lookup"><span data-stu-id="bfdf5-116">Primary</span></span>  <br/> |<span data-ttu-id="bfdf5-117">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="bfdf5-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="bfdf5-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="bfdf5-118">**UserUri**</span></span> <br/> |<span data-ttu-id="bfdf5-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bfdf5-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="bfdf5-120">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="bfdf5-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="bfdf5-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="bfdf5-121">**TenantId**</span></span> <br/> |<span data-ttu-id="bfdf5-122">int</span><span class="sxs-lookup"><span data-stu-id="bfdf5-122">int</span></span>  <br/> |<span data-ttu-id="bfdf5-123">外表</span><span class="sxs-lookup"><span data-stu-id="bfdf5-123">Foreign</span></span>  <br/> |<span data-ttu-id="bfdf5-124">此用户的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="bfdf5-124">This user's Tenant ID.</span></span> <span data-ttu-id="bfdf5-125">有关详细信息, 请参阅[租户表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdf5-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="bfdf5-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="bfdf5-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="bfdf5-127">int</span><span class="sxs-lookup"><span data-stu-id="bfdf5-127">int</span></span>  <br/> |<span data-ttu-id="bfdf5-128">外表</span><span class="sxs-lookup"><span data-stu-id="bfdf5-128">Foreign</span></span>  <br/> |<span data-ttu-id="bfdf5-129">此用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="bfdf5-129">This user's URI type.</span></span> <span data-ttu-id="bfdf5-130">有关详细信息, 请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdf5-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

