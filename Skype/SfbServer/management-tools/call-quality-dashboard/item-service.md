---
title: '呼叫质量仪表板项目服务 (CQD) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 摘要：了解项目服务，该服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827702"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="ce8cb-104">呼叫质量仪表板项目服务 (CQD) </span><span class="sxs-lookup"><span data-stu-id="ce8cb-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="ce8cb-105">**摘要：** 了解项目服务，该服务是通话质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ce8cb-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ce8cb-107">项目服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="ce8cb-108">项目服务</span><span class="sxs-lookup"><span data-stu-id="ce8cb-108">Item Service</span></span>

<span data-ttu-id="ce8cb-109">存储库 API 提供简单的内容管理服务（称为项目服务）来存储用户的任何应用程序定义的内容。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="ce8cb-110">系统内容归系统用户所有，并且由具有只读访问权限的所有用户共享。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="ce8cb-111">专用用户内容归常规用户所有，只有所有者可以修改或删除这些内容，但所有用户仍具有对这些内容的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce8cb-112">此 API 文档介绍了存储库 API 的只读操作。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="ce8cb-113">呼叫质量仪表板将报告和查询保存为存储库数据库中的项目。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="ce8cb-114">项目可以具有可选的子项目，呼叫质量仪表板使用子项目功能在层次结构中组织报告和查询。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="ce8cb-115">项目服务包括以下概念：</span><span class="sxs-lookup"><span data-stu-id="ce8cb-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="ce8cb-116">**Item** - 存储库的基本元素。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="ce8cb-117">每个项目完全归一个用户所有。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="ce8cb-118">**子项** - 存储库的基本组织机制。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="ce8cb-119">项目可以有零个、一个或多个从属项目。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="ce8cb-120">**项目上级** - 项目列表，从最顶端的项目开始，这是用户的默认项目，导致给定项目。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="ce8cb-121">**项目内容** - 存储在"项"中的特定于应用程序的内容。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="ce8cb-122">呼叫质量仪表板将报告和查询的 JSON 表示形式保存在内容中。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="ce8cb-123">REST 操作包含在下表中。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="ce8cb-124">**操作**</span><span class="sxs-lookup"><span data-stu-id="ce8cb-124">**Operation**</span></span>|<span data-ttu-id="ce8cb-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="ce8cb-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ce8cb-126">获取项目</span><span class="sxs-lookup"><span data-stu-id="ce8cb-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="ce8cb-127">获取项目将返回存储库中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="ce8cb-128">获取项目</span><span class="sxs-lookup"><span data-stu-id="ce8cb-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="ce8cb-129">获取项目返回特定项目。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="ce8cb-130">获取子项</span><span class="sxs-lookup"><span data-stu-id="ce8cb-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="ce8cb-131">获取Sub-Items返回特定项目的子项。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="ce8cb-132">获取项目上级</span><span class="sxs-lookup"><span data-stu-id="ce8cb-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="ce8cb-133">获取项目上级返回特定项的上级。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="ce8cb-134">更新项目</span><span class="sxs-lookup"><span data-stu-id="ce8cb-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="ce8cb-135">更新存储库中的特定项。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-135">Update a specific item in the repository.</span></span>  <br/> |
   

