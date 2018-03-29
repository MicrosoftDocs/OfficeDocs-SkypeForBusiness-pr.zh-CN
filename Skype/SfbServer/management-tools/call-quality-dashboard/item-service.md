---
title: 项目服务呼叫质量仪表板 (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 摘要： 了解项目服务，这是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 218fdb4f2c4b3d73fb4e7f78b5679b66eecf34cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="80ae0-104">项目服务呼叫质量仪表板 (CQD)</span><span class="sxs-lookup"><span data-stu-id="80ae0-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="80ae0-105">**摘要：**了解项目服务，这是呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="80ae0-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="80ae0-106">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="80ae0-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="80ae0-107">此项服务是呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="80ae0-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="80ae0-108">项目服务</span><span class="sxs-lookup"><span data-stu-id="80ae0-108">Item Service</span></span>

<span data-ttu-id="80ae0-109">知识库 API 提供了简单的内容管理服务，称为项服务，可用于存储用户的任何应用程序定义的内容。</span><span class="sxs-lookup"><span data-stu-id="80ae0-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="80ae0-110">系统的内容是系统用户所拥有的并具有只读访问权限的所有用户都共享。</span><span class="sxs-lookup"><span data-stu-id="80ae0-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="80ae0-111">专用的用户内容均由普通用户，并只有所有者才可以修改或删除它们，但所有用户仍然都有它们的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="80ae0-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80ae0-112">此 API 文档介绍存储库 API 的只读的操作。</span><span class="sxs-lookup"><span data-stu-id="80ae0-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="80ae0-113">通话质量仪表板以项的形式保存的报告和查询知识库数据库中。</span><span class="sxs-lookup"><span data-stu-id="80ae0-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="80ae0-114">一个项目可以有可选的子项目，并呼叫质量仪表板使用子项目功能层次结构中组织的报告和查询。</span><span class="sxs-lookup"><span data-stu-id="80ae0-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="80ae0-115">项目服务包括以下概念：</span><span class="sxs-lookup"><span data-stu-id="80ae0-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="80ae0-116">**项目**的存储库的基本元素。</span><span class="sxs-lookup"><span data-stu-id="80ae0-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="80ae0-117">每个项由一个用户拥有。</span><span class="sxs-lookup"><span data-stu-id="80ae0-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="80ae0-118">**子项目**-存储库中的基本组织结构。</span><span class="sxs-lookup"><span data-stu-id="80ae0-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="80ae0-119">项可以有零，一个或多个从属项。</span><span class="sxs-lookup"><span data-stu-id="80ae0-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="80ae0-120">**项上级**的项目，开始从最上面的项目，这是默认的用户来说，通向给定项的项的列表。</span><span class="sxs-lookup"><span data-stu-id="80ae0-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="80ae0-121">**项目内容**的项中存储的特定于应用程序的内容。</span><span class="sxs-lookup"><span data-stu-id="80ae0-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="80ae0-122">通话质量仪表板中内容保存报告和查询的 JSON 的表示。</span><span class="sxs-lookup"><span data-stu-id="80ae0-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="80ae0-123">下表中包括的其余操作。</span><span class="sxs-lookup"><span data-stu-id="80ae0-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="80ae0-124">**操作**</span><span class="sxs-lookup"><span data-stu-id="80ae0-124">**Operation**</span></span>|<span data-ttu-id="80ae0-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="80ae0-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="80ae0-126">获取项</span><span class="sxs-lookup"><span data-stu-id="80ae0-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="80ae0-127">在存储库中获取项目返回所有项。</span><span class="sxs-lookup"><span data-stu-id="80ae0-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="80ae0-128">获取项</span><span class="sxs-lookup"><span data-stu-id="80ae0-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="80ae0-129">获取项返回的特定项。</span><span class="sxs-lookup"><span data-stu-id="80ae0-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="80ae0-130">获取子项目</span><span class="sxs-lookup"><span data-stu-id="80ae0-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="80ae0-131">获取子项目返回特定项的子项。</span><span class="sxs-lookup"><span data-stu-id="80ae0-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="80ae0-132">获取项的祖先</span><span class="sxs-lookup"><span data-stu-id="80ae0-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="80ae0-133">获取项上级返回特定项的祖先。</span><span class="sxs-lookup"><span data-stu-id="80ae0-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="80ae0-134">更新项目</span><span class="sxs-lookup"><span data-stu-id="80ae0-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="80ae0-135">更新存储库中的特定项。</span><span class="sxs-lookup"><span data-stu-id="80ae0-135">Update a specific item in the repository.</span></span>  <br/> |
   

