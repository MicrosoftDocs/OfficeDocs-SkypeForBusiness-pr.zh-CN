---
title: CQD 用户服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 摘要：了解用户服务，它是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816651"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="de5fd-104">CQD 用户服务</span><span class="sxs-lookup"><span data-stu-id="de5fd-104">User Service for CQD</span></span>
 
<span data-ttu-id="de5fd-105">**摘要：** 了解用户服务，该服务是 "呼叫质量" 仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="de5fd-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="de5fd-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="de5fd-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="de5fd-107">用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="de5fd-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="de5fd-108">用户服务</span><span class="sxs-lookup"><span data-stu-id="de5fd-108">User Service</span></span>

<span data-ttu-id="de5fd-109">知识库 API 提供了简化的用户管理模型，在此模型中，用户预配（创建新用户帐户）是自动和隐式的。</span><span class="sxs-lookup"><span data-stu-id="de5fd-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="de5fd-110">当用户首次向存储库 API 发出请求时，存储库会创建新的用户记录。</span><span class="sxs-lookup"><span data-stu-id="de5fd-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="de5fd-111">通话质量仪表板还会自动为新用户创建用户专用项目。</span><span class="sxs-lookup"><span data-stu-id="de5fd-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="de5fd-112">新的用户专用项目是系统用户项目的完整克隆。</span><span class="sxs-lookup"><span data-stu-id="de5fd-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="de5fd-113">这样，用户就可以从自己的报表和查询副本开始自定义。</span><span class="sxs-lookup"><span data-stu-id="de5fd-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="de5fd-114">使用 "通话质量" 仪表板，用户可以随时重置其专用项目。</span><span class="sxs-lookup"><span data-stu-id="de5fd-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="de5fd-115">**特殊用户 Id**</span><span class="sxs-lookup"><span data-stu-id="de5fd-115">**Special User IDs**</span></span>
  
<span data-ttu-id="de5fd-116">存储库 API 包括需要整数值以指定特定用户的 REST API Uri。</span><span class="sxs-lookup"><span data-stu-id="de5fd-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="de5fd-117">示例： `https://<portal>/QoERepositoryService/repository/user/{userId}`。</span><span class="sxs-lookup"><span data-stu-id="de5fd-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="de5fd-118">此处，{userId} 应由整数值（如0、1等）替换。</span><span class="sxs-lookup"><span data-stu-id="de5fd-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="de5fd-119">此外，知识库 API 将在 Uri 中的 {userId} 处接受两个特殊的用户 Id。</span><span class="sxs-lookup"><span data-stu-id="de5fd-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="de5fd-120">*默认值*-表示当前与 API 交互的用户。</span><span class="sxs-lookup"><span data-stu-id="de5fd-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="de5fd-121">这允许应用程序访问当前用户的内容，而无需跟踪实际的用户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="de5fd-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="de5fd-122">示例： `https://<portal>/QoERepositoryService/repository/user/default`。</span><span class="sxs-lookup"><span data-stu-id="de5fd-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="de5fd-123">*system* -表示系统用户。</span><span class="sxs-lookup"><span data-stu-id="de5fd-123">*system*  - represents the system user.</span></span> <span data-ttu-id="de5fd-124">这使应用程序无需知道实际的用户 ID 值即可访问系统用户的内容。</span><span class="sxs-lookup"><span data-stu-id="de5fd-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="de5fd-125">示例： `https://<portal>/QoERepositoryService/repository/user/system`。</span><span class="sxs-lookup"><span data-stu-id="de5fd-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="de5fd-126">除非另有说明，否则可以在 Uri 中使用 {userId} 的特殊用户 Id。</span><span class="sxs-lookup"><span data-stu-id="de5fd-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="de5fd-127">下表中包括其余操作。</span><span class="sxs-lookup"><span data-stu-id="de5fd-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="de5fd-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="de5fd-128">**Operation**</span></span>|<span data-ttu-id="de5fd-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="de5fd-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="de5fd-130">获取用户</span><span class="sxs-lookup"><span data-stu-id="de5fd-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="de5fd-131">返回存储库中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="de5fd-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="de5fd-132">获取用户</span><span class="sxs-lookup"><span data-stu-id="de5fd-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="de5fd-133">返回用户记录。</span><span class="sxs-lookup"><span data-stu-id="de5fd-133">Returns a user record.</span></span>  <br/> |
   

