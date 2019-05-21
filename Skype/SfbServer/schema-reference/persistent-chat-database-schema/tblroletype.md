---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是一个具有角色类型及其关联权限集的静态查找表。
ms.openlocfilehash: 8d49e9f2c61b8672a01a9c77bcc825925a4e7b2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295214"
---
# <a name="tblroletype"></a><span data-ttu-id="9e598-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="9e598-103">tblRoleType</span></span>
 
<span data-ttu-id="9e598-104">tblRoleType 是一个具有角色类型及其关联权限集的静态查找表。</span><span class="sxs-lookup"><span data-stu-id="9e598-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="9e598-105">**多**</span><span class="sxs-lookup"><span data-stu-id="9e598-105">**Columns**</span></span>

|<span data-ttu-id="9e598-106">**列**</span><span class="sxs-lookup"><span data-stu-id="9e598-106">**Column**</span></span>|<span data-ttu-id="9e598-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e598-107">**Type**</span></span>|<span data-ttu-id="9e598-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e598-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e598-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="9e598-109">rtypeID</span></span>  <br/> |<span data-ttu-id="9e598-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="9e598-110">int, not null</span></span>  <br/> |<span data-ttu-id="9e598-111">角色类型 ID。</span><span class="sxs-lookup"><span data-stu-id="9e598-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="9e598-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="9e598-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="9e598-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="9e598-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="9e598-114">角色类型说明。</span><span class="sxs-lookup"><span data-stu-id="9e598-114">Role type description.</span></span> <span data-ttu-id="9e598-115">有四个可用的角色:</span><span class="sxs-lookup"><span data-stu-id="9e598-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="9e598-116">成员: 聊天室成员</span><span class="sxs-lookup"><span data-stu-id="9e598-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="9e598-117">管理器: 聊天室管理器</span><span class="sxs-lookup"><span data-stu-id="9e598-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="9e598-118">浊音: 演示者使用 auditorium 聊天室</span><span class="sxs-lookup"><span data-stu-id="9e598-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="9e598-119">创建者: 可以创建聊天室</span><span class="sxs-lookup"><span data-stu-id="9e598-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="9e598-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="9e598-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="9e598-121">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="9e598-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="9e598-122">角色的权限集。</span><span class="sxs-lookup"><span data-stu-id="9e598-122">Permission set for the role.</span></span> <span data-ttu-id="9e598-123">所用位为:</span><span class="sxs-lookup"><span data-stu-id="9e598-123">The used bits are:</span></span> <br/>  <span data-ttu-id="9e598-124">2: 如果角色可以管理节点, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="9e598-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="9e598-125">4: 如果角色可以创建子节点, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="9e598-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="9e598-126">7: 如果角色可以加入聊天室 (或类别的子聊天室), 则为 True。</span><span class="sxs-lookup"><span data-stu-id="9e598-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="9e598-127">8: 如果角色可以在聊天室中 (或在子类别的子聊天室中) 聊天, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="9e598-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="9e598-128">10: 如果角色可以读取聊天历史记录 (即使未加入聊天室), 则为 True。</span><span class="sxs-lookup"><span data-stu-id="9e598-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="9e598-129">11: 如果角色可以查看聊天室, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="9e598-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="9e598-130">(这将通过范围和可见性等因素进一步改进。)</span><span class="sxs-lookup"><span data-stu-id="9e598-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="9e598-131">12: 如果角色可以在 auditorium 聊天室中聊天, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="9e598-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="9e598-132">13: 如果角色在查看节点时可以绕过可见性规则, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="9e598-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="9e598-133">**关键字**</span><span class="sxs-lookup"><span data-stu-id="9e598-133">**Key**</span></span>

|<span data-ttu-id="9e598-134">**列**</span><span class="sxs-lookup"><span data-stu-id="9e598-134">**Column**</span></span>|<span data-ttu-id="9e598-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e598-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e598-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="9e598-136">rtypeID</span></span>  <br/> |<span data-ttu-id="9e598-137">主键。</span><span class="sxs-lookup"><span data-stu-id="9e598-137">Primary key.</span></span>  <br/> |
   

