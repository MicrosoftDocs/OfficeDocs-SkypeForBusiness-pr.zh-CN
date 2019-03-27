---
title: 用户视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 用户视图存储已参与呼叫或在数据库中包含记录的会话的用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877641"
---
# <a name="user-view"></a><span data-ttu-id="46646-104">用户视图</span><span class="sxs-lookup"><span data-stu-id="46646-104">User view</span></span>
 
<span data-ttu-id="46646-105">用户视图存储已参与呼叫或在数据库中包含记录的会话的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="46646-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="46646-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="46646-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="46646-107">**列**</span><span class="sxs-lookup"><span data-stu-id="46646-107">**Column**</span></span>|<span data-ttu-id="46646-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="46646-108">**Data Type**</span></span>|<span data-ttu-id="46646-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="46646-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46646-110">用户 Id</span><span class="sxs-lookup"><span data-stu-id="46646-110">UserId</span></span>  <br/> |<span data-ttu-id="46646-111">int</span><span class="sxs-lookup"><span data-stu-id="46646-111">int</span></span>  <br/> |<span data-ttu-id="46646-112">标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="46646-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="46646-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="46646-113">UserUri</span></span>  <br/> |<span data-ttu-id="46646-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="46646-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="46646-115">用户的 Uri。</span><span class="sxs-lookup"><span data-stu-id="46646-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="46646-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="46646-116">TenantKey</span></span>  <br/> |<span data-ttu-id="46646-117">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="46646-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="46646-118">用户的租户。</span><span class="sxs-lookup"><span data-stu-id="46646-118">Tenant of user.</span></span> <span data-ttu-id="46646-119">请参阅[Tenants 表](tenants.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="46646-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="46646-120">UriType</span><span class="sxs-lookup"><span data-stu-id="46646-120">UriType</span></span>  <br/> |<span data-ttu-id="46646-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="46646-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="46646-122">用户 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="46646-122">Type of user URI.</span></span> <span data-ttu-id="46646-123">请参阅[UriTypes 表](uritypes.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="46646-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

