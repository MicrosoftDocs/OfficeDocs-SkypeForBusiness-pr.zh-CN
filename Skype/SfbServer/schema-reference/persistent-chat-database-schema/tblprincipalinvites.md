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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295291"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="8f3ea-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="8f3ea-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="8f3ea-104">tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。</span><span class="sxs-lookup"><span data-stu-id="8f3ea-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="8f3ea-105">**多**</span><span class="sxs-lookup"><span data-stu-id="8f3ea-105">**Columns**</span></span>

|<span data-ttu-id="8f3ea-106">**列**</span><span class="sxs-lookup"><span data-stu-id="8f3ea-106">**Column**</span></span>|<span data-ttu-id="8f3ea-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="8f3ea-107">**Type**</span></span>|<span data-ttu-id="8f3ea-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f3ea-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8f3ea-109">prinID</span><span class="sxs-lookup"><span data-stu-id="8f3ea-109">prinID</span></span>  <br/> |<span data-ttu-id="8f3ea-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="8f3ea-110">int, not null</span></span>  <br/> |<span data-ttu-id="8f3ea-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="8f3ea-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8f3ea-112">invID</span><span class="sxs-lookup"><span data-stu-id="8f3ea-112">invID</span></span>  <br/> |<span data-ttu-id="8f3ea-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="8f3ea-113">int, not null</span></span>  <br/> |<span data-ttu-id="8f3ea-114">从 tblLastInviteId 表生成的唯一序列号 (每个主体 ID)。</span><span class="sxs-lookup"><span data-stu-id="8f3ea-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="8f3ea-115">a</span><span class="sxs-lookup"><span data-stu-id="8f3ea-115">nodeID</span></span>  <br/> |<span data-ttu-id="8f3ea-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="8f3ea-116">int, not null</span></span>  <br/> |<span data-ttu-id="8f3ea-117">节点 ID (仅聊天室)。</span><span class="sxs-lookup"><span data-stu-id="8f3ea-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="8f3ea-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="8f3ea-118">createdOn</span></span>  <br/> |<span data-ttu-id="8f3ea-119">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="8f3ea-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="8f3ea-120">创建时间。</span><span class="sxs-lookup"><span data-stu-id="8f3ea-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="8f3ea-121">**标示**</span><span class="sxs-lookup"><span data-stu-id="8f3ea-121">**Keys**</span></span>

|<span data-ttu-id="8f3ea-122">**列**</span><span class="sxs-lookup"><span data-stu-id="8f3ea-122">**Column**</span></span>|<span data-ttu-id="8f3ea-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f3ea-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f3ea-124">\<prinID、\></span><span class="sxs-lookup"><span data-stu-id="8f3ea-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="8f3ea-125">主键。</span><span class="sxs-lookup"><span data-stu-id="8f3ea-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8f3ea-126">prinID</span><span class="sxs-lookup"><span data-stu-id="8f3ea-126">prinID</span></span>  <br/> |<span data-ttu-id="8f3ea-127">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="8f3ea-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="8f3ea-128">a</span><span class="sxs-lookup"><span data-stu-id="8f3ea-128">nodeID</span></span>  <br/> |<span data-ttu-id="8f3ea-129">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="8f3ea-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

