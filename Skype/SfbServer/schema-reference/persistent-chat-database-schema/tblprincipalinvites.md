---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876688"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="61237-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="61237-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="61237-104">tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。</span><span class="sxs-lookup"><span data-stu-id="61237-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="61237-105">**列**</span><span class="sxs-lookup"><span data-stu-id="61237-105">**Columns**</span></span>

|<span data-ttu-id="61237-106">**列**</span><span class="sxs-lookup"><span data-stu-id="61237-106">**Column**</span></span>|<span data-ttu-id="61237-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="61237-107">**Type**</span></span>|<span data-ttu-id="61237-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="61237-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="61237-109">prinID</span><span class="sxs-lookup"><span data-stu-id="61237-109">prinID</span></span>  <br/> |<span data-ttu-id="61237-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="61237-110">int, not null</span></span>  <br/> |<span data-ttu-id="61237-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="61237-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="61237-112">invID</span><span class="sxs-lookup"><span data-stu-id="61237-112">invID</span></span>  <br/> |<span data-ttu-id="61237-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="61237-113">int, not null</span></span>  <br/> |<span data-ttu-id="61237-114">生成的唯一连续数字 （每个主体 ID) 从 tblLastInviteId 表。</span><span class="sxs-lookup"><span data-stu-id="61237-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="61237-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="61237-115">nodeID</span></span>  <br/> |<span data-ttu-id="61237-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="61237-116">int, not null</span></span>  <br/> |<span data-ttu-id="61237-117">节点 ID （仅聊天室）。</span><span class="sxs-lookup"><span data-stu-id="61237-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="61237-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="61237-118">createdOn</span></span>  <br/> |<span data-ttu-id="61237-119">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="61237-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="61237-120">创建的时间。</span><span class="sxs-lookup"><span data-stu-id="61237-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="61237-121">**键**</span><span class="sxs-lookup"><span data-stu-id="61237-121">**Keys**</span></span>

|<span data-ttu-id="61237-122">**列**</span><span class="sxs-lookup"><span data-stu-id="61237-122">**Column**</span></span>|<span data-ttu-id="61237-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="61237-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61237-124">\<prinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="61237-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="61237-125">主键。</span><span class="sxs-lookup"><span data-stu-id="61237-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="61237-126">prinID</span><span class="sxs-lookup"><span data-stu-id="61237-126">prinID</span></span>  <br/> |<span data-ttu-id="61237-127">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="61237-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="61237-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="61237-128">nodeID</span></span>  <br/> |<span data-ttu-id="61237-129">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="61237-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

