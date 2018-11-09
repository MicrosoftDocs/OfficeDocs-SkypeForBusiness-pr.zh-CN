---
title: 呼叫质量仪表板 (CQD) 的项服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 摘要： 了解项服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 5e5198afd95d6c9e1de517054053b724a54b1105
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035622"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="7cc66-104">呼叫质量仪表板 (CQD) 的项服务</span><span class="sxs-lookup"><span data-stu-id="7cc66-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="7cc66-105">**摘要：** 了解项服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="7cc66-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7cc66-106">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="7cc66-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7cc66-107">项服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="7cc66-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="7cc66-108">项服务</span><span class="sxs-lookup"><span data-stu-id="7cc66-108">Item Service</span></span>

<span data-ttu-id="7cc66-109">存储库 API 提供了一个简单的内容管理服务，亦称项服务，可用于存储用户的任何应用程序定义的内容。</span><span class="sxs-lookup"><span data-stu-id="7cc66-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="7cc66-110">系统的内容是由系统用户拥有，由具有只读访问权限的所有用户共享。</span><span class="sxs-lookup"><span data-stu-id="7cc66-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="7cc66-111">专用的用户内容归一般用户和只有所有者可以修改或删除，但所有用户仍都具有对它们的只读访问。</span><span class="sxs-lookup"><span data-stu-id="7cc66-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7cc66-112">此 API 文档介绍存储库 API 的只读的操作。</span><span class="sxs-lookup"><span data-stu-id="7cc66-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="7cc66-113">呼叫质量仪表板可将报告和查询保存为项目，在存储库数据库中。</span><span class="sxs-lookup"><span data-stu-id="7cc66-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="7cc66-114">项目可具有可选子项目，并且呼叫质量仪表板以使用子项功能层次结构组织报告和查询。</span><span class="sxs-lookup"><span data-stu-id="7cc66-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="7cc66-115">项服务包括以下概念：</span><span class="sxs-lookup"><span data-stu-id="7cc66-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="7cc66-116">**项目**的存储库的基本元素。</span><span class="sxs-lookup"><span data-stu-id="7cc66-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="7cc66-117">由准确按照一用户拥有每个项目。</span><span class="sxs-lookup"><span data-stu-id="7cc66-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="7cc66-118">**子项目**的存储库的基本组织机制。</span><span class="sxs-lookup"><span data-stu-id="7cc66-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="7cc66-119">项目可具有零，一个或多个从属项目。</span><span class="sxs-lookup"><span data-stu-id="7cc66-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="7cc66-120">**项目祖先**-项目，开始从顶层项目，这是默认的用户，从而给定项的项的列表。</span><span class="sxs-lookup"><span data-stu-id="7cc66-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="7cc66-121">**项目内容**-存储项中的特定于应用程序的内容。</span><span class="sxs-lookup"><span data-stu-id="7cc66-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="7cc66-122">呼叫质量仪表板中内容将保存报告和查询的 JSON 表示的形式。</span><span class="sxs-lookup"><span data-stu-id="7cc66-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="7cc66-123">下表中包含的其余部分操作。</span><span class="sxs-lookup"><span data-stu-id="7cc66-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="7cc66-124">**操作**</span><span class="sxs-lookup"><span data-stu-id="7cc66-124">**Operation**</span></span>|<span data-ttu-id="7cc66-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="7cc66-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7cc66-126">获取项</span><span class="sxs-lookup"><span data-stu-id="7cc66-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="7cc66-127">在存储库中获取项目返回的所有项目。</span><span class="sxs-lookup"><span data-stu-id="7cc66-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="7cc66-128">获取项目</span><span class="sxs-lookup"><span data-stu-id="7cc66-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="7cc66-129">获取项返回的特定项目。</span><span class="sxs-lookup"><span data-stu-id="7cc66-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="7cc66-130">获取子项</span><span class="sxs-lookup"><span data-stu-id="7cc66-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="7cc66-131">获取子项目返回的特定项目的子项目。</span><span class="sxs-lookup"><span data-stu-id="7cc66-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="7cc66-132">获取项祖先</span><span class="sxs-lookup"><span data-stu-id="7cc66-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="7cc66-133">获取项祖先返回特定项目的上级。</span><span class="sxs-lookup"><span data-stu-id="7cc66-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="7cc66-134">更新项</span><span class="sxs-lookup"><span data-stu-id="7cc66-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="7cc66-135">更新存储库中的特定项目。</span><span class="sxs-lookup"><span data-stu-id="7cc66-135">Update a specific item in the repository.</span></span>  <br/> |
   

