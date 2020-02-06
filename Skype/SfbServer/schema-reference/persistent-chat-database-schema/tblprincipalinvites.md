---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814180"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="799a6-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="799a6-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="799a6-104">tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。</span><span class="sxs-lookup"><span data-stu-id="799a6-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="799a6-105">**多**</span><span class="sxs-lookup"><span data-stu-id="799a6-105">**Columns**</span></span>

|<span data-ttu-id="799a6-106">**列**</span><span class="sxs-lookup"><span data-stu-id="799a6-106">**Column**</span></span>|<span data-ttu-id="799a6-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="799a6-107">**Type**</span></span>|<span data-ttu-id="799a6-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="799a6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="799a6-109">prinID</span><span class="sxs-lookup"><span data-stu-id="799a6-109">prinID</span></span>  <br/> |<span data-ttu-id="799a6-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="799a6-110">int, not null</span></span>  <br/> |<span data-ttu-id="799a6-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="799a6-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="799a6-112">invID</span><span class="sxs-lookup"><span data-stu-id="799a6-112">invID</span></span>  <br/> |<span data-ttu-id="799a6-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="799a6-113">int, not null</span></span>  <br/> |<span data-ttu-id="799a6-114">从 tblLastInviteId 表生成的唯一序列号（每个主体 ID）。</span><span class="sxs-lookup"><span data-stu-id="799a6-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="799a6-115">a</span><span class="sxs-lookup"><span data-stu-id="799a6-115">nodeID</span></span>  <br/> |<span data-ttu-id="799a6-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="799a6-116">int, not null</span></span>  <br/> |<span data-ttu-id="799a6-117">节点 ID （仅聊天室）。</span><span class="sxs-lookup"><span data-stu-id="799a6-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="799a6-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="799a6-118">createdOn</span></span>  <br/> |<span data-ttu-id="799a6-119">datetime，not null</span><span class="sxs-lookup"><span data-stu-id="799a6-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="799a6-120">创建时间。</span><span class="sxs-lookup"><span data-stu-id="799a6-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="799a6-121">**标示**</span><span class="sxs-lookup"><span data-stu-id="799a6-121">**Keys**</span></span>

|<span data-ttu-id="799a6-122">**列**</span><span class="sxs-lookup"><span data-stu-id="799a6-122">**Column**</span></span>|<span data-ttu-id="799a6-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="799a6-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="799a6-124">\<prinID、\></span><span class="sxs-lookup"><span data-stu-id="799a6-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="799a6-125">主键。</span><span class="sxs-lookup"><span data-stu-id="799a6-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="799a6-126">prinID</span><span class="sxs-lookup"><span data-stu-id="799a6-126">prinID</span></span>  <br/> |<span data-ttu-id="799a6-127">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="799a6-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="799a6-128">a</span><span class="sxs-lookup"><span data-stu-id="799a6-128">nodeID</span></span>  <br/> |<span data-ttu-id="799a6-129">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="799a6-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

