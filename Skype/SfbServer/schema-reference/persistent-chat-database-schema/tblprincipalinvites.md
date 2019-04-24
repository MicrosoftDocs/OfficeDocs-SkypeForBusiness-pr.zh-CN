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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212465"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="aed6e-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="aed6e-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="aed6e-104">tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。</span><span class="sxs-lookup"><span data-stu-id="aed6e-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="aed6e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="aed6e-105">**Columns**</span></span>

|<span data-ttu-id="aed6e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="aed6e-106">**Column**</span></span>|<span data-ttu-id="aed6e-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="aed6e-107">**Type**</span></span>|<span data-ttu-id="aed6e-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="aed6e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aed6e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="aed6e-109">prinID</span></span>  <br/> |<span data-ttu-id="aed6e-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aed6e-110">int, not null</span></span>  <br/> |<span data-ttu-id="aed6e-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="aed6e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="aed6e-112">invID</span><span class="sxs-lookup"><span data-stu-id="aed6e-112">invID</span></span>  <br/> |<span data-ttu-id="aed6e-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aed6e-113">int, not null</span></span>  <br/> |<span data-ttu-id="aed6e-114">生成的唯一连续数字 （每个主体 ID) 从 tblLastInviteId 表。</span><span class="sxs-lookup"><span data-stu-id="aed6e-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="aed6e-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="aed6e-115">nodeID</span></span>  <br/> |<span data-ttu-id="aed6e-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aed6e-116">int, not null</span></span>  <br/> |<span data-ttu-id="aed6e-117">节点 ID （仅聊天室）。</span><span class="sxs-lookup"><span data-stu-id="aed6e-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="aed6e-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="aed6e-118">createdOn</span></span>  <br/> |<span data-ttu-id="aed6e-119">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="aed6e-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="aed6e-120">创建的时间。</span><span class="sxs-lookup"><span data-stu-id="aed6e-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="aed6e-121">**键**</span><span class="sxs-lookup"><span data-stu-id="aed6e-121">**Keys**</span></span>

|<span data-ttu-id="aed6e-122">**列**</span><span class="sxs-lookup"><span data-stu-id="aed6e-122">**Column**</span></span>|<span data-ttu-id="aed6e-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="aed6e-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aed6e-124">\<prinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="aed6e-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="aed6e-125">主键。</span><span class="sxs-lookup"><span data-stu-id="aed6e-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="aed6e-126">prinID</span><span class="sxs-lookup"><span data-stu-id="aed6e-126">prinID</span></span>  <br/> |<span data-ttu-id="aed6e-127">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="aed6e-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="aed6e-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="aed6e-128">nodeID</span></span>  <br/> |<span data-ttu-id="aed6e-129">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="aed6e-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

