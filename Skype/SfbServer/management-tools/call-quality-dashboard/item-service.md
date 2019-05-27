---
title: 通话质量仪表板 (CQD) 的项目服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '摘要: 了解项目服务, 它是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274609"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="d51de-104">通话质量仪表板 (CQD) 的项目服务</span><span class="sxs-lookup"><span data-stu-id="d51de-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="d51de-105">**摘要:** 了解项目服务, 该服务是 "呼叫质量" 仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="d51de-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d51de-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="d51de-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d51de-107">项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="d51de-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="d51de-108">项目服务</span><span class="sxs-lookup"><span data-stu-id="d51de-108">Item Service</span></span>

<span data-ttu-id="d51de-109">知识库 API 提供了一个简单的内容管理服务 (称为项目服务), 可用于为用户存储任何应用程序定义的内容。</span><span class="sxs-lookup"><span data-stu-id="d51de-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="d51de-110">系统内容由系统用户拥有, 并且由具有只读访问权限的所有用户共享。</span><span class="sxs-lookup"><span data-stu-id="d51de-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="d51de-111">专用用户内容由普通用户拥有, 只有所有者可以修改或删除它们, 但所有用户仍具有对它们的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="d51de-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d51de-112">此 API 文档介绍知识库 API 的只读操作。</span><span class="sxs-lookup"><span data-stu-id="d51de-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="d51de-113">通话质量仪表板将报表和查询保存为存储库数据库中的项目。</span><span class="sxs-lookup"><span data-stu-id="d51de-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="d51de-114">项目可以具有可选子项目, 而通话质量仪表板使用子项目功能组织报表和查询的层次结构。</span><span class="sxs-lookup"><span data-stu-id="d51de-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="d51de-115">项目服务包括以下概念:</span><span class="sxs-lookup"><span data-stu-id="d51de-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="d51de-116">**Item** -存储库的基本元素。</span><span class="sxs-lookup"><span data-stu-id="d51de-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="d51de-117">每个项目仅归一个用户所有。</span><span class="sxs-lookup"><span data-stu-id="d51de-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="d51de-118">**子项目**-存储库的基本组织结构。</span><span class="sxs-lookup"><span data-stu-id="d51de-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="d51de-119">项目可以有零个、一个或多个下属项目。</span><span class="sxs-lookup"><span data-stu-id="d51de-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="d51de-120">**项目上级**-从最顶层项目 (即用户的默认项目) 开始, 指向给定项目的项目列表。</span><span class="sxs-lookup"><span data-stu-id="d51de-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="d51de-121">**项目内容**-存储在项目中的特定于应用程序的内容。</span><span class="sxs-lookup"><span data-stu-id="d51de-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="d51de-122">通话质量仪表板在内容中保存报表和查询的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="d51de-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="d51de-123">下表中包括其余操作。</span><span class="sxs-lookup"><span data-stu-id="d51de-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="d51de-124">**操作**</span><span class="sxs-lookup"><span data-stu-id="d51de-124">**Operation**</span></span>|<span data-ttu-id="d51de-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="d51de-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d51de-126">获取项目</span><span class="sxs-lookup"><span data-stu-id="d51de-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="d51de-127">获取项目将返回存储库中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="d51de-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="d51de-128">获取项目</span><span class="sxs-lookup"><span data-stu-id="d51de-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="d51de-129">获取项目返回特定项目。</span><span class="sxs-lookup"><span data-stu-id="d51de-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="d51de-130">获取子项</span><span class="sxs-lookup"><span data-stu-id="d51de-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="d51de-131">获取子项目返回特定项目的子项目。</span><span class="sxs-lookup"><span data-stu-id="d51de-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="d51de-132">获取项目上级</span><span class="sxs-lookup"><span data-stu-id="d51de-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="d51de-133">获取项目祖先返回特定项目的上级。</span><span class="sxs-lookup"><span data-stu-id="d51de-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="d51de-134">更新项目</span><span class="sxs-lookup"><span data-stu-id="d51de-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="d51de-135">更新存储库中的特定项目。</span><span class="sxs-lookup"><span data-stu-id="d51de-135">Update a specific item in the repository.</span></span>  <br/> |
   

