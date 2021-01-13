---
title: tblRoleType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是一个静态查找表，其中包含角色类型及其关联的权限集。
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831522"
---
# <a name="tblroletype"></a><span data-ttu-id="6e786-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="6e786-103">tblRoleType</span></span>
 
<span data-ttu-id="6e786-104">tblRoleType 是一个静态查找表，其中包含角色类型及其关联的权限集。</span><span class="sxs-lookup"><span data-stu-id="6e786-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="6e786-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="6e786-105">**Columns**</span></span>

|<span data-ttu-id="6e786-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6e786-106">**Column**</span></span>|<span data-ttu-id="6e786-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="6e786-107">**Type**</span></span>|<span data-ttu-id="6e786-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="6e786-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e786-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="6e786-109">rtypeID</span></span>  <br/> |<span data-ttu-id="6e786-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="6e786-110">int, not null</span></span>  <br/> |<span data-ttu-id="6e786-111">角色类型 ID。</span><span class="sxs-lookup"><span data-stu-id="6e786-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="6e786-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="6e786-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="6e786-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="6e786-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="6e786-p101">角色类型描述。可用角色有四种：</span><span class="sxs-lookup"><span data-stu-id="6e786-p101">Role type description. There are four available roles:</span></span> <br/>  <span data-ttu-id="6e786-116">成员：聊天室成员</span><span class="sxs-lookup"><span data-stu-id="6e786-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="6e786-117">管理员：聊天室管理员</span><span class="sxs-lookup"><span data-stu-id="6e786-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="6e786-118">有发布权的人：大会堂聊天室的演讲者</span><span class="sxs-lookup"><span data-stu-id="6e786-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="6e786-119">创建者：可以创建聊天室</span><span class="sxs-lookup"><span data-stu-id="6e786-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="6e786-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="6e786-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="6e786-121">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="6e786-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="6e786-p102">角色的权限集。使用的位为：</span><span class="sxs-lookup"><span data-stu-id="6e786-p102">Permission set for the role. The used bits are:</span></span> <br/>  <span data-ttu-id="6e786-124">2：在角色可以管理节点时为 True。</span><span class="sxs-lookup"><span data-stu-id="6e786-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="6e786-125">4：在角色可以创建子节点时为 True。</span><span class="sxs-lookup"><span data-stu-id="6e786-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="6e786-126">7：在角色可以加入聊天室（或某类别的子聊天室）时为 True。</span><span class="sxs-lookup"><span data-stu-id="6e786-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="6e786-127">8：在角色可以在聊天室中（或某类别的子聊天室中）聊天时为 True。</span><span class="sxs-lookup"><span data-stu-id="6e786-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="6e786-128">10：在角色即使不加入聊天室也可读取聊天历史记录时为 True。</span><span class="sxs-lookup"><span data-stu-id="6e786-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="6e786-p103">11：在角色可以看到聊天室时为 True。（该值可通过作用域和可见性等因素进一步优化。）</span><span class="sxs-lookup"><span data-stu-id="6e786-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="6e786-131">12：在角色可以在大会堂聊天室中聊天时为 True。</span><span class="sxs-lookup"><span data-stu-id="6e786-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="6e786-132">13：在角色查看节点后可以绕过可见性规则时为 True。</span><span class="sxs-lookup"><span data-stu-id="6e786-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="6e786-133">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="6e786-133">**Key**</span></span>

|<span data-ttu-id="6e786-134">**列**</span><span class="sxs-lookup"><span data-stu-id="6e786-134">**Column**</span></span>|<span data-ttu-id="6e786-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="6e786-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6e786-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="6e786-136">rtypeID</span></span>  <br/> |<span data-ttu-id="6e786-137">主键。</span><span class="sxs-lookup"><span data-stu-id="6e786-137">Primary key.</span></span>  <br/> |
   

