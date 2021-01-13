---
title: 适用于 CQD 的用户服务
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 摘要：了解用户服务，它是通话质量仪表板的存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803072"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="f0b80-104">适用于 CQD 的用户服务</span><span class="sxs-lookup"><span data-stu-id="f0b80-104">User Service for CQD</span></span>
 
<span data-ttu-id="f0b80-105">**摘要：** 了解用户服务，它是通话质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f0b80-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="f0b80-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="f0b80-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f0b80-107">用户服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f0b80-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="f0b80-108">用户服务</span><span class="sxs-lookup"><span data-stu-id="f0b80-108">User Service</span></span>

<span data-ttu-id="f0b80-109">存储库 API 提供了简化的用户管理模型，其中用户预配 (自动和隐式) 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f0b80-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="f0b80-110">当用户首次对存储库 API 提出请求时，存储库将创建新的用户记录。</span><span class="sxs-lookup"><span data-stu-id="f0b80-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="f0b80-111">呼叫质量仪表板还会自动为新用户创建用户专用项目。</span><span class="sxs-lookup"><span data-stu-id="f0b80-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="f0b80-112">新用户专用项目是系统用户项目的完整克隆。</span><span class="sxs-lookup"><span data-stu-id="f0b80-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="f0b80-113">这样，用户就可以从自己的报表和查询副本开始，他们可以立即开始自定义。</span><span class="sxs-lookup"><span data-stu-id="f0b80-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f0b80-114">使用通话质量仪表板，用户可以随时重置其专用项目。</span><span class="sxs-lookup"><span data-stu-id="f0b80-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="f0b80-115">**特殊用户 ID**</span><span class="sxs-lookup"><span data-stu-id="f0b80-115">**Special User IDs**</span></span>
  
<span data-ttu-id="f0b80-116">存储库 API 包括需要整数值以指定特定用户的 REST API URI。</span><span class="sxs-lookup"><span data-stu-id="f0b80-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="f0b80-117">示例  `https://<portal>/QoERepositoryService/repository/user/{userId}` ：。</span><span class="sxs-lookup"><span data-stu-id="f0b80-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="f0b80-118">在这里，{userId} 应替换为整数值，如 0、1 等。</span><span class="sxs-lookup"><span data-stu-id="f0b80-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="f0b80-119">此外，存储库 API 将在 URI 中的 {userId} 接受两个特殊用户 ID。</span><span class="sxs-lookup"><span data-stu-id="f0b80-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="f0b80-120">*default*  - 表示当前正在与 API 交互的用户。</span><span class="sxs-lookup"><span data-stu-id="f0b80-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="f0b80-121">这允许应用程序访问当前用户的内容，而无需跟踪实际用户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="f0b80-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="f0b80-122">示例：`https://<portal>/QoERepositoryService/repository/user/default`。</span><span class="sxs-lookup"><span data-stu-id="f0b80-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="f0b80-123">*system*  - 表示系统用户。</span><span class="sxs-lookup"><span data-stu-id="f0b80-123">*system*  - represents the system user.</span></span> <span data-ttu-id="f0b80-124">这允许应用程序在不知道实际用户 ID 值的情况下访问系统用户的内容。</span><span class="sxs-lookup"><span data-stu-id="f0b80-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="f0b80-125">示例：`https://<portal>/QoERepositoryService/repository/user/system`。</span><span class="sxs-lookup"><span data-stu-id="f0b80-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="f0b80-126">除非另有说明，否则特殊用户 ID 可在 URI 中的 {userId} 使用。</span><span class="sxs-lookup"><span data-stu-id="f0b80-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="f0b80-127">REST 操作包含在下表中。</span><span class="sxs-lookup"><span data-stu-id="f0b80-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="f0b80-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="f0b80-128">**Operation**</span></span>|<span data-ttu-id="f0b80-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="f0b80-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f0b80-130">获取用户</span><span class="sxs-lookup"><span data-stu-id="f0b80-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="f0b80-131">返回存储库中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="f0b80-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="f0b80-132">获取用户</span><span class="sxs-lookup"><span data-stu-id="f0b80-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="f0b80-133">返回用户记录。</span><span class="sxs-lookup"><span data-stu-id="f0b80-133">Returns a user record.</span></span>  <br/> |
   

