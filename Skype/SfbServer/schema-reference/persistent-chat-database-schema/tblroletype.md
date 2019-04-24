---
title: tblRoleType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是一个静态查找表包含角色类型及其关联的权限集。
ms.openlocfilehash: 6b5e545306c402fbfb89094a19799fe3ff6d2e34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212409"
---
# <a name="tblroletype"></a><span data-ttu-id="d1726-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="d1726-103">tblRoleType</span></span>
 
<span data-ttu-id="d1726-104">tblRoleType 是一个静态查找表包含角色类型及其关联的权限集。</span><span class="sxs-lookup"><span data-stu-id="d1726-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="d1726-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d1726-105">**Columns**</span></span>

|<span data-ttu-id="d1726-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d1726-106">**Column**</span></span>|<span data-ttu-id="d1726-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="d1726-107">**Type**</span></span>|<span data-ttu-id="d1726-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1726-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d1726-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="d1726-109">rtypeID</span></span>  <br/> |<span data-ttu-id="d1726-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="d1726-110">int, not null</span></span>  <br/> |<span data-ttu-id="d1726-111">角色类型 id。</span><span class="sxs-lookup"><span data-stu-id="d1726-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="d1726-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="d1726-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="d1726-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="d1726-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="d1726-114">角色类型说明。</span><span class="sxs-lookup"><span data-stu-id="d1726-114">Role type description.</span></span> <span data-ttu-id="d1726-115">有四个可用的角色：</span><span class="sxs-lookup"><span data-stu-id="d1726-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="d1726-116">成员： 聊天室成员</span><span class="sxs-lookup"><span data-stu-id="d1726-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="d1726-117">管理员： 聊天室管理员</span><span class="sxs-lookup"><span data-stu-id="d1726-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="d1726-118">有： 大会堂聊天室的演讲者</span><span class="sxs-lookup"><span data-stu-id="d1726-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="d1726-119">创建者： 可以创建聊天室</span><span class="sxs-lookup"><span data-stu-id="d1726-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="d1726-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="d1726-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="d1726-121">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="d1726-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="d1726-122">权限集的角色。</span><span class="sxs-lookup"><span data-stu-id="d1726-122">Permission set for the role.</span></span> <span data-ttu-id="d1726-123">使用的预留有位：</span><span class="sxs-lookup"><span data-stu-id="d1726-123">The used bits are:</span></span> <br/>  <span data-ttu-id="d1726-124">2： 在角色可以管理节点时为 true。</span><span class="sxs-lookup"><span data-stu-id="d1726-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="d1726-125">4： 在角色可以创建子节点时为 true。</span><span class="sxs-lookup"><span data-stu-id="d1726-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="d1726-126">7： 在角色可以加入聊天室 （或某类别的子聊天室） 时为 true。</span><span class="sxs-lookup"><span data-stu-id="d1726-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="d1726-127">8： 在角色可以聊天在聊天室中 （或某类别的子聊天室） 时为 true。</span><span class="sxs-lookup"><span data-stu-id="d1726-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="d1726-128">10： 在角色可以读取即使不加入聊天室的聊天历史记录时为 true。</span><span class="sxs-lookup"><span data-stu-id="d1726-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="d1726-129">11： 在角色可以看到该聊天室时为 true。</span><span class="sxs-lookup"><span data-stu-id="d1726-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="d1726-130">（这被细化由如范围和可视性的因素。）</span><span class="sxs-lookup"><span data-stu-id="d1726-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="d1726-131">12： 在角色可以在大会堂聊天室中聊天时为 true。</span><span class="sxs-lookup"><span data-stu-id="d1726-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="d1726-132">13： 在角色可以查看节点时绕过可见性规则时为 true。</span><span class="sxs-lookup"><span data-stu-id="d1726-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="d1726-133">**关键字**</span><span class="sxs-lookup"><span data-stu-id="d1726-133">**Key**</span></span>

|<span data-ttu-id="d1726-134">**列**</span><span class="sxs-lookup"><span data-stu-id="d1726-134">**Column**</span></span>|<span data-ttu-id="d1726-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1726-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1726-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="d1726-136">rtypeID</span></span>  <br/> |<span data-ttu-id="d1726-137">主键。</span><span class="sxs-lookup"><span data-stu-id="d1726-137">Primary key.</span></span>  <br/> |
   

