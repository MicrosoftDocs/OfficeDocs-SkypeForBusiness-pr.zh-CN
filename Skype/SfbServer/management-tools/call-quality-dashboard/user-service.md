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
description: 摘要： 了解用户的服务，这是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: c4bb2395ea3fa4541140a7966bbfb554ef53c168
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="a846a-104">CQD 的用户服务</span><span class="sxs-lookup"><span data-stu-id="a846a-104">User Service for CQD</span></span>
 
<span data-ttu-id="a846a-105">**摘要：**了解用户的服务，这是呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a846a-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a846a-106">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="a846a-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a846a-107">用户服务是为呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a846a-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="a846a-108">用户服务</span><span class="sxs-lookup"><span data-stu-id="a846a-108">User Service</span></span>

<span data-ttu-id="a846a-109">知识库 API 提供了自动和隐式资源调配 （创建新用户帐户） 的用户所在的简化的用户管理模型。</span><span class="sxs-lookup"><span data-stu-id="a846a-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="a846a-110">当用户第一次进行针对存储库 API 的请求时，存储库会创建新的用户记录。</span><span class="sxs-lookup"><span data-stu-id="a846a-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="a846a-111">通话质量面板还会自动创建一个用户专门为新用户的项目。</span><span class="sxs-lookup"><span data-stu-id="a846a-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="a846a-112">新的用户专用项目是完全克隆的系统用户的项目。</span><span class="sxs-lookup"><span data-stu-id="a846a-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="a846a-113">这样一来，用户开始自己的报告和查询，他们立即可以开始自定义副本。</span><span class="sxs-lookup"><span data-stu-id="a846a-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a846a-114">使用调用质量面板，用户可以重置其专用的项目任何时候。</span><span class="sxs-lookup"><span data-stu-id="a846a-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="a846a-115">**特殊用户 Id**</span><span class="sxs-lookup"><span data-stu-id="a846a-115">**Special User IDs**</span></span>
  
<span data-ttu-id="a846a-116">知识库 API 包括需要一个整数值，以指定特定用户的 REST API Uri。</span><span class="sxs-lookup"><span data-stu-id="a846a-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="a846a-117">例如： `https://<portal>/QoERepositoryService/repository/user/{userId}`。</span><span class="sxs-lookup"><span data-stu-id="a846a-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="a846a-118">在这里，{用户 Id} 应由一个整数值，如从 0，1，等等。</span><span class="sxs-lookup"><span data-stu-id="a846a-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="a846a-119">此外，存储库 API 将接受用户 {Id} 在 Uri 中的两个特殊的用户 Id。</span><span class="sxs-lookup"><span data-stu-id="a846a-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="a846a-120">*默认*的代表目前正在与 API 进行交互的用户。</span><span class="sxs-lookup"><span data-stu-id="a846a-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="a846a-121">这允许应用程序访问当前用户的内容，而无需跟踪的实际用户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="a846a-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="a846a-122">例如： ` https://<portal>/QoERepositoryService/repository/user/default`。</span><span class="sxs-lookup"><span data-stu-id="a846a-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="a846a-123">*系统*-代表系统用户。</span><span class="sxs-lookup"><span data-stu-id="a846a-123">*system*  - represents the system user.</span></span> <span data-ttu-id="a846a-124">这允许应用程序访问系统用户的内容，而无需知道实际用户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="a846a-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="a846a-125">例如： `https://<portal>/QoERepositoryService/repository/user/system`。</span><span class="sxs-lookup"><span data-stu-id="a846a-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="a846a-126">除非另行说明，否则这些特殊用户 Id 可在用户 {Id} Uri 中。</span><span class="sxs-lookup"><span data-stu-id="a846a-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="a846a-127">下表中包括的其余操作。</span><span class="sxs-lookup"><span data-stu-id="a846a-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="a846a-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="a846a-128">**Operation**</span></span>|<span data-ttu-id="a846a-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="a846a-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a846a-130">获取用户</span><span class="sxs-lookup"><span data-stu-id="a846a-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="a846a-131">返回在存储库中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="a846a-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="a846a-132">获取用户</span><span class="sxs-lookup"><span data-stu-id="a846a-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="a846a-133">返回用户记录。</span><span class="sxs-lookup"><span data-stu-id="a846a-133">Returns a user record.</span></span>  <br/> |
   

