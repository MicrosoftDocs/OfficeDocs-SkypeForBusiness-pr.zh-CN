---
title: CQD 的用户服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 摘要： 了解用户服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 80eeea6bc64d106c67c03a6c39ca3126335b2713
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294516"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="85fb1-104">CQD 的用户服务</span><span class="sxs-lookup"><span data-stu-id="85fb1-104">User Service for CQD</span></span>
 
<span data-ttu-id="85fb1-105">**摘要：** 了解用户服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="85fb1-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="85fb1-106">呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="85fb1-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="85fb1-107">用户服务是用于呼叫的质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="85fb1-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="85fb1-108">用户服务</span><span class="sxs-lookup"><span data-stu-id="85fb1-108">User Service</span></span>

<span data-ttu-id="85fb1-109">存储库 API 提供了其中设置 （创建新的用户帐户） 的用户是自动和隐式简化的用户管理模型。</span><span class="sxs-lookup"><span data-stu-id="85fb1-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="85fb1-110">当用户发出第一次对存储库 API 请求时，存储库创建新用户记录。</span><span class="sxs-lookup"><span data-stu-id="85fb1-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="85fb1-111">呼叫质量仪表板还会自动创建用户专用的新用户的项目。</span><span class="sxs-lookup"><span data-stu-id="85fb1-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="85fb1-112">新的专用用户项目是完整克隆的系统用户的项目。</span><span class="sxs-lookup"><span data-stu-id="85fb1-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="85fb1-113">这种方式，用户开始使用自己的报告和查询，他们会立即开始自定义的副本。</span><span class="sxs-lookup"><span data-stu-id="85fb1-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="85fb1-114">使用呼叫质量仪表板，用户可以重置其专用的项目随时随地。</span><span class="sxs-lookup"><span data-stu-id="85fb1-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="85fb1-115">**特殊的用户 Id**</span><span class="sxs-lookup"><span data-stu-id="85fb1-115">**Special User IDs**</span></span>
  
<span data-ttu-id="85fb1-116">存储库 API 包含需要整数值来指定某个特定用户的 REST API Uri。</span><span class="sxs-lookup"><span data-stu-id="85fb1-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="85fb1-117">示例： `https://<portal>/QoERepositoryService/repository/user/{userId}`。</span><span class="sxs-lookup"><span data-stu-id="85fb1-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="85fb1-118">此处，{userId} 应替换为一个整数值，如 0，1，等。</span><span class="sxs-lookup"><span data-stu-id="85fb1-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="85fb1-119">此外，存储库 API 将接受 {userId} 在 Uri 中的两个特殊用户 Id。</span><span class="sxs-lookup"><span data-stu-id="85fb1-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="85fb1-120">*默认*-表示当前正在使用 API 进行交互的用户。</span><span class="sxs-lookup"><span data-stu-id="85fb1-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="85fb1-121">这允许应用程序访问当前用户的内容，而跟踪的实际用户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="85fb1-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="85fb1-122">示例： ` https://<portal>/QoERepositoryService/repository/user/default`。</span><span class="sxs-lookup"><span data-stu-id="85fb1-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="85fb1-123">*系统*-表示系统用户。</span><span class="sxs-lookup"><span data-stu-id="85fb1-123">*system*  - represents the system user.</span></span> <span data-ttu-id="85fb1-124">这使应用程序访问系统用户的内容，而无需了解的实际用户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="85fb1-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="85fb1-125">示例： `https://<portal>/QoERepositoryService/repository/user/system`。</span><span class="sxs-lookup"><span data-stu-id="85fb1-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="85fb1-126">除非另行说明，特殊用户 Id 可在 {userId} 在 Uri 中。</span><span class="sxs-lookup"><span data-stu-id="85fb1-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="85fb1-127">下表中包含的其余部分操作。</span><span class="sxs-lookup"><span data-stu-id="85fb1-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="85fb1-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="85fb1-128">**Operation**</span></span>|<span data-ttu-id="85fb1-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="85fb1-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="85fb1-130">获取用户</span><span class="sxs-lookup"><span data-stu-id="85fb1-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="85fb1-131">在存储库中返回用户的列表。</span><span class="sxs-lookup"><span data-stu-id="85fb1-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="85fb1-132">获取用户</span><span class="sxs-lookup"><span data-stu-id="85fb1-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="85fb1-133">返回用户记录。</span><span class="sxs-lookup"><span data-stu-id="85fb1-133">Returns a user record.</span></span>  <br/> |
   

