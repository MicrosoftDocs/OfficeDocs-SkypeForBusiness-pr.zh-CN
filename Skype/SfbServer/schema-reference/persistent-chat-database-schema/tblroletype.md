---
title: tblRoleType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是静态查找表与角色类型及其关联的权限集。
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a><span data-ttu-id="9f50c-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="9f50c-103">tblRoleType</span></span>
 
<span data-ttu-id="9f50c-104">tblRoleType 是静态查找表与角色类型及其关联的权限集。</span><span class="sxs-lookup"><span data-stu-id="9f50c-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="9f50c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="9f50c-105">**Columns**</span></span>

|<span data-ttu-id="9f50c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="9f50c-106">**Column**</span></span>|<span data-ttu-id="9f50c-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="9f50c-107">**Type**</span></span>|<span data-ttu-id="9f50c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="9f50c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9f50c-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="9f50c-109">rtypeID</span></span>  <br/> |<span data-ttu-id="9f50c-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="9f50c-110">int, not null</span></span>  <br/> |<span data-ttu-id="9f50c-111">角色类型 id。</span><span class="sxs-lookup"><span data-stu-id="9f50c-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="9f50c-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="9f50c-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="9f50c-113">nvarchar (256) 不为空</span><span class="sxs-lookup"><span data-stu-id="9f50c-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="9f50c-114">角色类型说明。</span><span class="sxs-lookup"><span data-stu-id="9f50c-114">Role type description.</span></span> <span data-ttu-id="9f50c-115">有四个可用的角色：</span><span class="sxs-lookup"><span data-stu-id="9f50c-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="9f50c-116">成员： 聊天室成员</span><span class="sxs-lookup"><span data-stu-id="9f50c-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="9f50c-117">经理： 聊天室经理</span><span class="sxs-lookup"><span data-stu-id="9f50c-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="9f50c-118">对于大会堂聊天室浊音： 演示者</span><span class="sxs-lookup"><span data-stu-id="9f50c-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="9f50c-119">创建者： 可以创建聊天室</span><span class="sxs-lookup"><span data-stu-id="9f50c-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="9f50c-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="9f50c-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="9f50c-121">bigint，不为空</span><span class="sxs-lookup"><span data-stu-id="9f50c-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="9f50c-122">设置为该角色的权限。</span><span class="sxs-lookup"><span data-stu-id="9f50c-122">Permission set for the role.</span></span> <span data-ttu-id="9f50c-123">所使用的位：</span><span class="sxs-lookup"><span data-stu-id="9f50c-123">The used bits are:</span></span> <br/>  <span data-ttu-id="9f50c-124">2： 如果该角色可以管理节点则为 true。</span><span class="sxs-lookup"><span data-stu-id="9f50c-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="9f50c-125">4： 如果该角色可以创建子节点。</span><span class="sxs-lookup"><span data-stu-id="9f50c-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="9f50c-126">7： 如果该角色可以加入聊天室 （或某一类别的儿童聊天室） 则为 true。</span><span class="sxs-lookup"><span data-stu-id="9f50c-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="9f50c-127">8： 如果该角色可以聊天，在聊天室中 （或在某一类别的儿童聊天室） 则为 true。</span><span class="sxs-lookup"><span data-stu-id="9f50c-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="9f50c-128">10： 如果该角色可以读取即使没有加入聊天室聊天历史则为 true。</span><span class="sxs-lookup"><span data-stu-id="9f50c-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="9f50c-129">11： 如果该角色可以看到聊天室则为 true。</span><span class="sxs-lookup"><span data-stu-id="9f50c-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="9f50c-130">（这是进一步改进了范围和可见性等因素。）</span><span class="sxs-lookup"><span data-stu-id="9f50c-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="9f50c-131">12： 如果该角色可以在大会堂聊天室聊天。</span><span class="sxs-lookup"><span data-stu-id="9f50c-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="9f50c-132">13： 如果该角色可以查看节点时跳过可见性规则。</span><span class="sxs-lookup"><span data-stu-id="9f50c-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="9f50c-133">**密钥**</span><span class="sxs-lookup"><span data-stu-id="9f50c-133">**Key**</span></span>

|<span data-ttu-id="9f50c-134">**列**</span><span class="sxs-lookup"><span data-stu-id="9f50c-134">**Column**</span></span>|<span data-ttu-id="9f50c-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="9f50c-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9f50c-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="9f50c-136">rtypeID</span></span>  <br/> |<span data-ttu-id="9f50c-137">为主键。</span><span class="sxs-lookup"><span data-stu-id="9f50c-137">Primary key.</span></span>  <br/> |
   

