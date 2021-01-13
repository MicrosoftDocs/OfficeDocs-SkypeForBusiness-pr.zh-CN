---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815852"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="75e68-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="75e68-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="75e68-104">tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。</span><span class="sxs-lookup"><span data-stu-id="75e68-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="75e68-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="75e68-105">**Columns**</span></span>

|<span data-ttu-id="75e68-106">**列**</span><span class="sxs-lookup"><span data-stu-id="75e68-106">**Column**</span></span>|<span data-ttu-id="75e68-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="75e68-107">**Type**</span></span>|<span data-ttu-id="75e68-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="75e68-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="75e68-109">prinID</span><span class="sxs-lookup"><span data-stu-id="75e68-109">prinID</span></span>  <br/> |<span data-ttu-id="75e68-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="75e68-110">int, not null</span></span>  <br/> |<span data-ttu-id="75e68-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="75e68-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="75e68-112">invID</span><span class="sxs-lookup"><span data-stu-id="75e68-112">invID</span></span>  <br/> |<span data-ttu-id="75e68-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="75e68-113">int, not null</span></span>  <br/> |<span data-ttu-id="75e68-114">从 tblLastInviteId 表中生成的唯一连续数字（每个主体 ID）。</span><span class="sxs-lookup"><span data-stu-id="75e68-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="75e68-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="75e68-115">nodeID</span></span>  <br/> |<span data-ttu-id="75e68-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="75e68-116">int, not null</span></span>  <br/> |<span data-ttu-id="75e68-117">节点 ID（仅聊天室）。</span><span class="sxs-lookup"><span data-stu-id="75e68-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="75e68-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="75e68-118">createdOn</span></span>  <br/> |<span data-ttu-id="75e68-119">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="75e68-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="75e68-120">创建的时间。</span><span class="sxs-lookup"><span data-stu-id="75e68-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="75e68-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="75e68-121">**Keys**</span></span>

|<span data-ttu-id="75e68-122">**列**</span><span class="sxs-lookup"><span data-stu-id="75e68-122">**Column**</span></span>|<span data-ttu-id="75e68-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="75e68-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="75e68-124">主键。</span><span class="sxs-lookup"><span data-stu-id="75e68-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="75e68-125">prinID</span><span class="sxs-lookup"><span data-stu-id="75e68-125">prinID</span></span>  <br/> |<span data-ttu-id="75e68-126">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="75e68-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="75e68-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="75e68-127">nodeID</span></span>  <br/> |<span data-ttu-id="75e68-128">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="75e68-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

